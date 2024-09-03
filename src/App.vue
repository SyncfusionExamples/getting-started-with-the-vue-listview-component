
<script setup>
  import {ListViewComponent} from '@syncfusion/ej2-vue-lists';
  import { DataManager, WebApiAdaptor, Query } from '@syncfusion/ej2-data';
  const hobbies = [
    { 'id': '1', 'name': 'Hiking', 'category': 'Adventure' },
    { 'id': '2', 'name': 'Camping', 'category': 'Adventure' },
    { 'id': '3', 'name': 'Fishing', 'category': 'Water Activities' },
    { 'id': '4', 'name': 'Climbing', 'category': 'Adventure' },
    { 'id': '5', 'name': 'Kayaking', 'category': 'Water Activities' },
    { 'id': '6', 'name': 'Bird Watching', 'category': 'Leisure' },
    { 'id': '7', 'name': 'Mountain Biking', 'category': 'Adventure' },
    { 'id': '8', 'name': 'Snorkeling', 'category': 'Water Activities' },
    { 'id': '9', 'name': 'Stargazing', 'category': 'Leisure' },
    { 'id': '10', 'name': 'Photography', 'category': 'Leisure' }
  ];
  const nestedListData = [
  {
        id: '01', text: 'Music', icon: 'folder',
        child: [
          { id: '01-01', text: 'Gouttes.mp3', icon: 'file' }
        ]
      },
      {
        id: '02', text: 'Videos', icon: 'folder',
        child: [
          { id: '02-01', text: 'Naturals.mp4', icon: 'file' },
          { id: '02-02', text: 'Wild.mpeg', icon: 'file' },
        ]
      },
      {
        id: '03', text: 'Documents', icon: 'folder',
        child: [
          { id: '03-01', text: 'Environment Pollution.docx', icon: 'file' },
          { id: '03-02', text: 'Global Water, Sanitation, & Hygiene.docx', icon: 'file' },
          { id: '03-03', text: 'Global Warming.ppt', icon: 'file' },
          { id: '03-04', text: 'Social Network.pdf', icon: 'file' },
          { id: '03-05', text: 'Youth Empowerment.pdf', icon: 'file' },
        ]
      },
      {
        id: '04', text: 'Pictures', icon: 'folder',
        child: [
          {
            id: '04-01', text: 'Camera Roll', icon: 'folder',
            child: [
              { id: '04-01-01', text: 'WIN_20160726_094117.JPG', icon: 'file' },
              { id: '04-01-02', text: 'WIN_20160726_094118.JPG', icon: 'file' },
              { id: '04-01-03', text: 'WIN_20160726_094119.JPG', icon: 'file' }
            ]
          },
          {
            id: '04-02', text: 'Wind.jpg', icon: 'file'
          },
          {
            id: '04-02', text: 'Stone.jpg', icon: 'file'
          },
          {
            id: '04-02', text: 'Home.jpg', icon: 'file'
          },
          {
            id: '04-02', text: 'Bridge.png', icon: 'file'
          }
        ]
      },
      {
        id: '05', text: 'Downloads', icon: 'folder',
        child: [
          { id: '05-01', text: 'UI-Guide.pdf', icon: 'file' },
          { id: '05-02', text: 'Tutorials.zip', icon: 'file' },
          { id: '05-03', text: 'Game.exe', icon: 'file' },
          { id: '05-04', text: 'TypeScript.7z', icon: 'file' },
        ]
      }
  ]
  const remoteData = new DataManager({
    url:'https://ej2services.syncfusion.com/production/web-services/api/Employees/',
    adaptor:new WebApiAdaptor,
    crossDomain:true
  });
  const dataQuery = new Query().select(['EmployeeId', 'FirstName']).
  take(10).requiresCount();
</script>
<template>
  <div style="height:1080px; width:400px; margin:10% 35%;">
    <ListViewComponent
      :dataSource="remoteData"
      :query="dataQuery"
      :fields="{ id:'EmployeeId', text:'FirstName' }"
      :showHeader="true" headerTitle="Employee List"
      :showCheckBox="false" checkBoxPosition="Right"
    >
    </ListViewComponent>
  </div>
</template>
<style>
   @import "../node_modules/@syncfusion/ej2-base/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-vue-lists/styles/material.css";
</style>
