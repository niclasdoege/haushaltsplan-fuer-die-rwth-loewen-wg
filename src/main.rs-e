//#[macro_use] extern crate rocket;

//use std::error::Error;
use yew::prelude::*;
use yew_router::prelude::*;
use serde::{Deserialize***REMOVED***;
use chrono::{TimeZone, Duration, Local, Datelike, Timelike, Utc***REMOVED***;
use yew::{html, Callback***REMOVED***;
use futures::Future;
use futures::FutureExt;

static name_list:[&str; 3] = ["niclas","marc","mikiya"];

#[derive(Properties, PartialEq)]
struct Model {
    // other fields here
    button_click_callback: Callback<usize>,
***REMOVED***


#[derive(Clone, Routable, PartialEq)]
enum Route {
    #[at("/")]
    Home,
    #[at("/secure")]
    Secure,
    #[not_found]
    #[at("/404")]
    NotFound,
***REMOVED***


#[function_component(Secure)]
fn secure() -> Html {
    let navigator = use_navigator().unwrap();

    let onclick = Callback::from(move |_| navigator.push(&Route::Home));
    html! {
        <div>
            <h1>{ "Secure" ***REMOVED***</h1>
            <button {onclick***REMOVED***>{ "Go Home" ***REMOVED***</button>
        </div>
    ***REMOVED***
***REMOVED***


fn switch(routes: Route) -> Html {
    match routes {
        Route::Home => html! { 
            <App /> ***REMOVED***,
        Route::Secure => html! {
            <Secure />
        ***REMOVED***,
        Route::NotFound => html! { <h1>{ "404" ***REMOVED***</h1> ***REMOVED***,
    ***REMOVED***
***REMOVED***

#[derive(Clone, PartialEq, Deserialize, Debug)]
struct Table {
    marc: (String,String),
    mikiya: (String,String),
    niclas: (String,String),
    week: usize,
***REMOVED***


#[derive(Clone, PartialEq, Deserialize, Debug)]
struct LastDone {
    kitchen: String,
    doorway: String,
    bathroom: String,
***REMOVED***


#[derive(Properties, PartialEq)]
struct TablesListProps {
    tables: Vec<Table>,
    on_click: Callback<Table>
***REMOVED***

#[function_component(TablesList)]
#[allow(non_snake_case)]
fn Tables_list(TablesListProps { tables, on_click ***REMOVED***: &TablesListProps) -> Html {
    let on_click = on_click.clone();
    tables.iter().map(|table| {
        let on_table_select = {
            let on_click = on_click.clone();
            let table = table.clone();
            Callback::from(move |_| {
                    on_click.emit(table.clone())
                ***REMOVED***)
            ***REMOVED***;
    
            html! {
                <p key={table.week***REMOVED*** onclick={on_table_select***REMOVED***>{format!("week: {***REMOVED*** mikiya: {***REMOVED*** marc: {***REMOVED***, niclas:{***REMOVED***", table.week, table.mikiya.0, table.marc.0, table.niclas.0)***REMOVED***</p>
            ***REMOVED***
        ***REMOVED***).collect()
***REMOVED***

#[derive(Properties, PartialEq)]
struct NamesListProps {
    names: Vec<String>,
//    on_click: Callback<Table>
***REMOVED***

#[function_component(NamesList)]
#[allow(non_snake_case)]
fn Names_list(NamesListProps {names***REMOVED***: &NamesListProps) -> Html {
    //let on_click = on_click.clone();
    names.iter().map(|name| {
        let on_table_select = {
            //let on_click = on_click.clone();
            let name = name.clone();
            //Callback::from(move |_| {
            //        on_click.emit(table.clone())
            //    ***REMOVED***)
            ***REMOVED***;
    
            html! {
                <p>{format!("{***REMOVED***",name)***REMOVED***</p>
            ***REMOVED***
        ***REMOVED***).collect()
***REMOVED***

//name_list_yew_thingie: NamesListProps = new NamesListProps


enum Person{
    Marc,
    Niclas,
    Mikiya
***REMOVED***









async fn send_postrequest_to_change_table_json(which_week: i64, who:&str) {
    
        //let temp_date=format!("{:02***REMOVED***-{:02***REMOVED***-{***REMOVED***", date.day(), date.month(), date.year());
        //fourteen_days.push((temp_date, environment_of_the_fourteen_days[blah+9]));
    let date_today = Local::now();
    let string_date=format!("{:02***REMOVED***-{:02***REMOVED***-{***REMOVED***", date_today.month(), date_today.day(), date_today.year());
    //let mut when = "we";
    let mut whoelse = vec!["marc","niclas","mikiya"];
    //whoelse.remove_item(who);
    whoelse.retain(|x| *x != who);

    let mut what_to_tell_marc = String::from("0");
    let mut what_to_tell_mikiya = String::from("0");
    let mut what_to_tell_niclas = String::from("0"); 

    let mut marc_task = String::from("0");
    let mut mikiya_task = String::from("0");
    let mut niclas_task = String::from("0"); 

    match who {
        "marc" => {what_to_tell_marc=string_date;***REMOVED***
        "mikiya" => {what_to_tell_mikiya=string_date;***REMOVED***
        "niclas" => {what_to_tell_niclas=string_date;***REMOVED***
    ***REMOVED***

    for name in name_list.iter().cloned().cycle().skip(which_week as usize).take(1){
        match name {
            "marc" => {marc_task="kitchen".to_string();***REMOVED***
            "mikiya" => {mikiya_task="kitchen".to_string();***REMOVED***
            "niclas" => {niclas_task="kitchen".to_string();***REMOVED***
        ***REMOVED***
    ***REMOVED***

    for name in name_list.iter().cloned().cycle().skip(which_week as usize +1).take(1){
        match name {
            "marc" => {marc_task="bathroom".to_string();***REMOVED***
            "mikiya" => {mikiya_task="bathroom".to_string();***REMOVED***
            "niclas" => {niclas_task="bathroom".to_string();***REMOVED***
        ***REMOVED***
    ***REMOVED***

    for name in name_list.iter().cloned().cycle().skip(which_week as usize +2).take(1){
        match name {
            "marc" => {marc_task="doorway".to_string();***REMOVED***
            "mikiya" => {mikiya_task="doorway".to_string();***REMOVED***
            "niclas" => {niclas_task="doorway".to_string();***REMOVED***
        ***REMOVED***
    ***REMOVED***

    let table = Table {
        marc: (what_to_tell_marc.to_string(), marc_task.to_string()),
        mikiya: (what_to_tell_mikiya.to_string(), mikiya_task.to_string()),
        niclas: (what_to_tell_niclas.to_string(), niclas_task.to_string()),
        week: which_week as usize,
    ***REMOVED***;

    //let params: [((&str, String), (&str, String, String), (&str, String, String), (&str, String, String)); 1]= ((&"week".to_string(), which_week.to_string()), (who, (*string_date).to_string(),"kitchen".to_string()), (whoelse[0], "0".to_string(),"kitchen".to_string()), (whoelse[1], "0".to_string(),"kitchen".to_string());
    let response = reqwest::Client::new()
    .post("http://192.168.0.81:8000/user")
    .form(&params)
    .send()
    .await
    .expect("send");
    println!("Response status {***REMOVED***", response.status());


***REMOVED***

async fn send_pullrequest_for_table_json<'a>(tables:&'a UseStateHandle<Vec<Table>>)-> Result<(Vec<Table>,&'a UseStateHandle<Vec<Table>>), reqwest::Error>{
    let echo_json :Vec<Table>  = reqwest::Client::new()
        .get("http://127.0.0.1:8000/example.json")
        .send()
        .await?
        .json()
        .await?;

    println!("{:#?***REMOVED***", echo_json);
    //let tables: Vec<Table> = echo_json.json().await?;
     Ok((echo_json,tables))
***REMOVED***



#[function_component(Main)]
fn main() -> Html {
    html! {
        <BrowserRouter>
            <Switch<Route> render={switch***REMOVED*** /> // <- must be child of <BrowserRouter>
        </BrowserRouter>
    ***REMOVED***
***REMOVED***








use log::info;
use wasm_bindgen::JsValue;
//use wasm-logger;













async fn map_err_example<'a>( tables : &'a UseStateHandle<Vec<Table>>){
    let mut tables = tables.clone();
 // tables.set(send_pullrequest_for_table_json().await.unwrap());

***REMOVED***

fn smoothen(vec: Vec<(usize, usize, usize)>) -> Vec<(usize, usize, usize)> {
    let mut result = vec![];
    for (i, &(r, g, b)) in vec.iter().enumerate() {
        if r == 100 && g == 100 && b == 100 {
            result.push((100, 100, 100));
        ***REMOVED*** else {
            if i == 0 {result.push((0, 0, 0));***REMOVED***
            else if i + 1 < vec.len(){
            let (prev_r, prev_g, prev_b) = result[i - 1];
            let (next_r, next_g, next_b) = vec[i + 1];
            let r_value = (prev_r*40 + next_r) / 51;
            let g_value = (prev_g*40 + next_g) / 51;
            let b_value = (prev_b*40 + next_b) / 51;
            result.push((r_value, g_value, b_value));
            ***REMOVED***
        ***REMOVED***
    ***REMOVED***
    result
***REMOVED***




//static mut tables: Option<UseStateHandle<Vec<_>>> = None;


use gloo_net::http::Request;
//use pin_utils::pin_mut;
//use pin_utils::unpin;
//use std::marker::Unpin;
//use std::pin::Pin;
//use yew;

#[function_component(App)]
fn app() -> Html {



    

    let selected_table = use_state(|| None);
    let on_table_select = {
                let selected_table = selected_table.clone();
                Callback::from(move |table: Table| {
                    selected_table.set(Some(table))
                ***REMOVED***)
            ***REMOVED***;

 
    
/* 
    struct MyStruct {
        vec: UseStateHandle<Vec<Table>>
    ***REMOVED***

    let mut tables:UseStateHandle<Vec<_>> = use_state(|| vec![]);
        pin_mut!(tables);
    //let mut tables: Vec<Table>= vec![];
    //let tables = tables.clone();
    //wasm_bindgen_futures::spawn_local(map_err_example(&tables));
    //wasm_bindgen_futures::spawn_local(send_postrequest_to_change_table_json());
    //wasm_bindgen_futures::spawn_local(send_pullrequest_for_table_json(&mut &tables));
//use_effect_with_deps(move |_| {
    
wasm_bindgen_futures::spawn_local(send_pullrequest_for_table_json( &mut tables).then(move |result| async move {
    //let  &mut tables = &mut tables.clone();
    
    match result {
        Ok(value) => {
            //let tables = tables.clone();
            //tables=value;
            &mut value.1.set(value.0);
            
        ***REMOVED***,
        Err(err) => {
            // handle the error
        ***REMOVED***
    ***REMOVED***
    //drop(tables);
    //Unpin(tables);
***REMOVED***));

//tables = tables.clone(); 
//let my_struct = MyStruct { vec: tables ***REMOVED***;
*/
        let zustande = use_state(|| vec![]);
    {
        let zustande = zustande.clone();
        use_effect_with_deps(move |_| {
            let zustande = zustande.clone();
            wasm_bindgen_futures::spawn_local(async move {
                let fetched_states: Vec<LastDone> = Request::get("http://192.168.0.81:8000/zustande.json")
                    .send()
                    .await
                    .unwrap()
                    .json()
                    .await
                    .unwrap();
                zustande.set(fetched_states);
                println!("{:#?***REMOVED***",zustande);
                println!("ghrghr");
                println!("ghrghr");
                println!("ghrghr");
                //let object = JsValue::from(tables);
                info!("Hello {:#?***REMOVED***", zustande);
            ***REMOVED***);
            || ()
        ***REMOVED***, ());
    ***REMOVED***
    info!("Hello {:#?***REMOVED***", zustande);


 

    let tables = use_state(|| vec![]);
    {
        let tables = tables.clone();
        use_effect_with_deps(move |_| {
            let tables = tables.clone();
            wasm_bindgen_futures::spawn_local(async move {
                let fetched_tables: Vec<Table> = Request::get("http://192.168.0.81:8000/example.json")
                    .send()
                    .await
                    .unwrap()
                    .json()
                    .await
                    .unwrap();
                tables.set(fetched_tables);
                println!("{:#?***REMOVED***",tables);
                println!("ghrghr");
                println!("ghrghr");
                println!("ghrghr");
                //let object = JsValue::from(tables);
                info!("Hello {:#?***REMOVED***", tables);
            ***REMOVED***);
            || ()
        ***REMOVED***, ());
    ***REMOVED***
    info!("Hello {:#?***REMOVED***", tables);
    //wasm_bindgen_futures::spawn_local(send_postrequest_to_change_table_json());

    
    

    //let name_list = ["niclas","marc","mikiya"];
    let start_time = Local.ymd(2023, 01, 01).and_hms(08, 00, 0);
    let date_today = Local::now();
    let weeks_elapsed;
    let days_elapsed;

    if date_today>start_time{
        weeks_elapsed = (date_today-start_time).num_weeks();
        days_elapsed = (date_today-start_time).num_days();
    ***REMOVED***
    else {
        weeks_elapsed = 0;
        days_elapsed = 0;
    ***REMOVED***

    let mut environment_of_the_fourteen_days:Vec<(usize,usize,usize)> = Vec::new();  
    let mut fourteen_days:Vec<(String,(usize,usize,usize))> = Vec::new();  
    let mut date = start_time + Duration::weeks(weeks_elapsed);
    

    let mut kitchen:Vec<NaiveDate> = Vec::new();
    let mut doorway:Vec<NaiveDate> = Vec::new();
    let mut bathroom:Vec<NaiveDate> = Vec::new();

    println!("{:?***REMOVED***", fourteen_days);
    println!("Hello, world!");

     for zustand in zustande.iter() {
        kitchen.push(NaiveDate::parse_from_str(&zustand.kitchen, "%Y-%m-%d").unwrap());
        doorway.push(NaiveDate::parse_from_str(&zustand.doorway, "%Y-%m-%d").unwrap());
        bathroom.push(NaiveDate::parse_from_str(&zustand.bathroom, "%Y-%m-%d").unwrap());
    ***REMOVED***
    kitchen.sort_by(|a, b| b.cmp(a));
    doorway.sort_by(|a, b| b.cmp(a));
    bathroom.sort_by(|a, b| b.cmp(a));

    //if day_in_table_as_chrono_thingy==date_today.naive_local().date()

    let mut how_was_the_kitchen_back_then=0;
    let mut how_was_the_bathroom_back_then=0;
    let mut how_was_the_doorway_back_then=0;

    for span in 0..24 {
        if kitchen.contains(&((date + Duration::days(span-10)).naive_local().date())){
            how_was_the_kitchen_back_then=100;
        ***REMOVED***
        else {how_was_the_kitchen_back_then=0;***REMOVED***
        if bathroom.contains(&((date + Duration::days(span-10)).naive_local().date())){
            how_was_the_bathroom_back_then=100;
        ***REMOVED***
        else {how_was_the_bathroom_back_then=0;***REMOVED***
         if bathroom.contains(&((date + Duration::days(span-10)).naive_local().date())){
            how_was_the_doorway_back_then=100;
        ***REMOVED***
        else {how_was_the_doorway_back_then=0;***REMOVED***
        environment_of_the_fourteen_days.push((how_was_the_kitchen_back_then,how_was_the_bathroom_back_then,how_was_the_doorway_back_then));
    ***REMOVED***

    info!("Hello {:#?***REMOVED***", environment_of_the_fourteen_days);
    let environment_of_the_fourteen_days = smoothen(environment_of_the_fourteen_days);
    info!("Hello {:#?***REMOVED***", environment_of_the_fourteen_days);

    for blah in 0..14 {
        let temp_date=format!("{***REMOVED***-{:02***REMOVED***-{:02***REMOVED***", date.year(), date.month(), date.day());
        //let temp_date=format!("{:02***REMOVED***-{:02***REMOVED***-{***REMOVED***", date.day(), date.month(), date.year());
        fourteen_days.push((temp_date, environment_of_the_fourteen_days[blah+9]));
        date = date + Duration::days(1);   
    ***REMOVED***


    //let name_list_yew_thingie= vec!["niclas","marc","mikiya","niclas","marc","mikiya","niclas","marc","mikiya","niclas","marc","mikiya","niclas","marc","mikiya","niclas"];
    //let name_list_yew_thingie = name_list.iter().map(|name| html! {
    //    <p>{format!("name: {***REMOVED***", name)***REMOVED***</p>
    //***REMOVED***).collect::<Html>();



    //let mut iteration_counter;
    html! {
        <div id="wrapper">
            <div>
                <table class="center">
                <tr>
                    <th class="collumnone">{"Datum"***REMOVED***</th>
                    <th>{"Kueche"***REMOVED***</th>
                    <th>{"Bad"***REMOVED***</th>
                    <th>{"Flur"***REMOVED***</th>
                </tr>

                {for fourteen_days.iter().enumerate().map(|(i,x)| html! { 
                    <tr>
                    <td class="date">{x.0.clone()***REMOVED***</td>
//                    <td><button>{ "marc" ***REMOVED***</button></td>
//                    <td><button>{ "marc" ***REMOVED***</button></td>
//                    <td><button>{ "marc" ***REMOVED***</button></td>
//                        if (0>1)
//                         {for name_list.iter().skip(0).take(3).map(|x| html! { <td><NamesList names={name_list_yew_thingie***REMOVED***  /></td> ***REMOVED***)***REMOVED***
                             //<td>{name_list***REMOVED*** </td>
                        {whatever_there_be_in_the_nth_line(i, fourteen_days.clone(),date_today.clone(), tables.clone(), weeks_elapsed, days_elapsed, zustande.clone())***REMOVED***
                    </tr> ***REMOVED***)***REMOVED***
            </table>
            <p></p>
            <p></p>
            </div>
            <table class="center">
                <tr>
                    <th>{"Woche"***REMOVED***</th>
                    <th>{"Kueche"***REMOVED***</th>
                    <th>{"Bad"***REMOVED***</th>
                    <th>{"Flur"***REMOVED***</th>
                </tr>

                {for fourteen_days.iter().enumerate().map(|(i,x)| html! { 
                    <tr>
                    <td>{x.0.clone()***REMOVED***</td>
                    {for name_list.iter().cloned().cycle().skip(i).take(3).map(|x| html! { <td>{x***REMOVED***</td> ***REMOVED***)***REMOVED***
                    </tr> ***REMOVED***)***REMOVED***
            </table>
            
           <TablesList tables={(*tables).clone()***REMOVED*** on_click={on_table_select.clone()***REMOVED*** />
            {for tables.iter().enumerate().map(|(i,x)| html! { 
                    <tr>
                    <p>{x.week***REMOVED***</p>
                    <p>{"oh mann"***REMOVED***</p>
                    {for tables.iter().skip(i).take(3).map(|x| html! { <td>{x.marc.0.to_string()***REMOVED***</td> ***REMOVED***)***REMOVED***
                    </tr> ***REMOVED***)***REMOVED***
                    <p>{"oh mannmannmann"***REMOVED***</p>
            
        </div>
    ***REMOVED***
    

***REMOVED*** 


use std::cell::Cell;

thread_local!(static WHEN: Cell<String> = Cell::new("".to_string()));
//static WHEN:&str = "sdf";
use chrono::DateTime;
use chrono::NaiveDate;
use std::sync::{Arc, Mutex***REMOVED***;
use yew::{ Html***REMOVED***;
fn whatever_there_be_in_the_nth_line(line: usize, fourteen_days: Vec<(std::string::String, (usize, usize, usize))>, date_today: DateTime<Local>, tables:yew::UseStateHandle<Vec<Table>>, weeks_elapsed:i64, days_elapsed:i64, zustande:yew::UseStateHandle<Vec<LastDone>>) -> Html {

    let mut name1 = "1";
    let mut name2= "1";
    let mut name3= "1";

    for name in name_list.iter().cloned().cycle().skip(weeks_elapsed as usize).take(1){
        name1=name;
    ***REMOVED***
    for name in name_list.iter().cloned().cycle().skip(weeks_elapsed as usize + 1).take(1){
        name2=name;
    ***REMOVED***
    for name in name_list.iter().cloned().cycle().skip(weeks_elapsed as usize + 2).take(1){
        name3=name;
    ***REMOVED***


    let onclick = Callback::from(move |x: &str| {
        wasm_bindgen_futures::spawn_local(send_postrequest_to_change_table_json(weeks_elapsed,name1.clone()));
    ***REMOVED***);

    let onclick2 = Callback::from(move |x: &str| {
        wasm_bindgen_futures::spawn_local(send_postrequest_to_change_table_json(weeks_elapsed,name2.clone()));
    ***REMOVED***);

    let onclick3 = Callback::from(move |x: &str| {
       wasm_bindgen_futures::spawn_local(send_postrequest_to_change_table_json(weeks_elapsed,name3.clone()));
    ***REMOVED***);

    let day_in_table_as_chrono_thingy = NaiveDate::parse_from_str(&fourteen_days[line].0.clone(), "%Y-%m-%d").unwrap();
    if day_in_table_as_chrono_thingy==date_today.naive_local().date()
    { 
      { return html! {
        
        <>
        <td style ={format!("background-color: hsl({***REMOVED***, 100%, 100%);", 40)***REMOVED***><button onclick={ move |_|{ onclick.emit(name1);***REMOVED******REMOVED***>{format!("Button {***REMOVED***", name1)***REMOVED***</button></td>
        <td><button onclick={ move |_|{ onclick2.emit(name2);***REMOVED******REMOVED***>{format!("Button {***REMOVED***", name2)***REMOVED***</button></td>
        <td><button onclick={ move |_|{ onclick3.emit(name3);***REMOVED******REMOVED***>{format!("Button {***REMOVED***", name3)***REMOVED***</button></td>
            </>
        ***REMOVED***

    ***REMOVED***

    ***REMOVED***
    else
    {
        //return html!{
       //{for zustande.iter().cloned().cycle().skip(weeks_elapsed as usize).take(3).map(|(x)| html! { 
       //     <td><button onclick={onclick.clone()***REMOVED***>{format!("Button {***REMOVED***", x.bathroom)***REMOVED***</button></td>
       // ***REMOVED***)
       // ***REMOVED*** 
       // ***REMOVED***
       let mut hue_vec : Vec<f64> = Vec::new();
        hue_vec.push( 1.2 * fourteen_days[line].1.0 as f64);
        hue_vec.push( 1.2 * fourteen_days[line].1.1 as f64);
        hue_vec.push( 1.2 * fourteen_days[line].1.2 as f64);
        
        return html!
        {
            //<td style ={format!("background-color: hsl({***REMOVED***, 100%, 50%);", hue1)***REMOVED***></td>
            //<td style ={format!("background-color: hsl({***REMOVED***, 100%, 50%);", hue2)***REMOVED***></td>
            //<td style ={format!("background-color: hsl({***REMOVED***, 100%, 50%);", hue3)***REMOVED***></td>

             {for hue_vec.iter().map(|(x)| html! { 
            <td style ={format!("background-color: hsl({***REMOVED***, 100%, 50%);", x)***REMOVED***></td>
        ***REMOVED***)
        ***REMOVED***

        ***REMOVED***

      
      
            
            
        
    ***REMOVED*** 
***REMOVED***

fn button_click_handler(id: usize) {
    // handle button click here
***REMOVED***

fn main() {

    wasm_logger::init(wasm_logger::Config::default());
    let object = JsValue::from("world");
    info!("Hello {***REMOVED***", object.as_string().unwrap());

    
    
    let now = Utc::now();

    let (is_pm, hour) = now.hour12();

    println!(
        "The current UTC time is {:02***REMOVED***:{:02***REMOVED***:{:02***REMOVED*** {***REMOVED***",
        hour,
        now.minute(),
        now.second(),
        if is_pm { "PM" ***REMOVED*** else { "AM" ***REMOVED***);

    let (is_common_era, year) = now.year_ce();
    println!(
        "The current UTC date is {***REMOVED***-{:02***REMOVED***-{:02***REMOVED*** {:?***REMOVED*** ({***REMOVED***)",
        year,
        now.month(),
        now.day(),
        now.weekday(),
        if is_common_era { "CE" ***REMOVED*** else { "BCE" ***REMOVED***
    );

    println!("Hello, world!");
    yew::Renderer::<Main>::new().render();
***REMOVED***

