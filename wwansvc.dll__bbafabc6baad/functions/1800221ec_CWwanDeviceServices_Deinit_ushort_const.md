# CWwanDeviceServices::Deinit(ushort const *)

- ea: `0x1800221ec`
- end: `0x1800223f0`
- name: `?Deinit@CWwanDeviceServices@@QEAAXPEBG@Z`
- size: `516`
- prototype: `void __fastcall(struct _GUID *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18005dbbc`

## callees

- `0x180008a7c`
- `0x1800094f4`
- `0x180014f1c`
- `0x180017640`
- `0x18002182c`
- `0x180021864`
- `0x1800221ec`
- `0x180024504`
- `0x180024538`
- `0x1800246dc`
- `0x180025084`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180022304`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180022304`
- `MobileNetworking!DeleteReadWriteLock` at `0x1800223c5`
- `MobileNetworking!DeleteReadWriteLock` at `0x1800223c5`
- `MobileNetworking!DeleteTimer` at `0x1800223b8`
- `MobileNetworking!DeleteTimer` at `0x1800223b8`

## string_xrefs

- `0x180022209`: ` Interface supported device services. Sending capable interface removal notification`
- `0x180022212`: `CWwanDeviceServices::Deinit`
- `0x180022390`: `CWwanDeviceServices::multiCarrierDeinit`
- `0x1800223d4`: `CWwanDeviceServices::multiCarrierDeinit`
- `0x1800223cb`: ` multiCarrierDeinit completed`

## pseudocode

```c
void __fastcall CWwanDeviceServices::Deinit(struct _GUID *this, const unsigned __int16 *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned __int8 *Data4; // rcx
  _OWORD *v9; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int64 v18; // rax
  bool v19; // zf
  _BYTE v20[552]; // [rsp+40h] [rbp-228h] BYREF

  if ( !this[1].Data1 && *(_QWORD *)this[2].Data4 )
  {
    WwanLog::Info(
      "CWwanDeviceServices::Deinit",
      0,
      L" Interface supported device services. Sending capable interface removal notification");
    WwanNhNotificationDispatcherWithHeader(0x10u, 5u, this, 0, 0, 0x32u, L"Mobile Broadband Adapter");
  }
  CWwanDeviceServices::flushAllDeviceServiceRequests(this);
  if ( *(_QWORD *)&this[6].Data1 )
  {
    CWwanDeviceServices::completeDeviceServiceRequest(this);
    std::shared_ptr<_WWAN_DS_REQUEST_CONTEXT>::reset(&this[6]);
  }
  std::_List_node<_WWAN_DS_CLIENT_STATE,void *>::_Free_non_head<std::allocator<std::_List_node<_WWAN_DS_CLIENT_STATE,void *>>>(
    v3,
    *(_QWORD *)&this[3].Data1);
  **(_QWORD **)&this[3].Data1 = *(_QWORD *)&this[3].Data1;
  *(_QWORD *)(*(_QWORD *)&this[3].Data1 + 8LL) = *(_QWORD *)&this[3].Data1;
  *(_QWORD *)this[3].Data4 = 0;
  std::_List_node<_WWAN_DSS_STATE,void *>::_Free_non_head<std::allocator<std::_List_node<_WWAN_DSS_STATE,void *>>>(
    v4,
    *(_QWORD *)&this[5].Data1);
  **(_QWORD **)&this[5].Data1 = *(_QWORD *)&this[5].Data1;
  *(_QWORD *)(*(_QWORD *)&this[5].Data1 + 8LL) = *(_QWORD *)&this[5].Data1;
  *(_QWORD *)this[5].Data4 = 0;
  std::list<_WWAN_DS_STATE>::clear(&this[2]);
  *this = 0;
  this[1].Data1 = -1;
  v5 = *(void **)this[1].Data4;
  *(_QWORD *)this[1].Data4 = 0;
  if ( v5 )
    operator delete(v5);
  v6 = *(_QWORD *)&this[9].Data1;
  this[7] = 0;
  this[8].Data1 = 0;
  if ( v6 )
    SwDeviceClose();
  memset_0(v20, 0, 0x218u);
  v7 = 4;
  Data4 = this[8].Data4;
  v9 = v20;
  do
  {
    v10 = v9[1];
    *(_OWORD *)Data4 = *v9;
    v11 = v9[2];
    *((_OWORD *)Data4 + 1) = v10;
    v12 = v9[3];
    *((_OWORD *)Data4 + 2) = v11;
    v13 = v9[4];
    *((_OWORD *)Data4 + 3) = v12;
    v14 = v9[5];
    *((_OWORD *)Data4 + 4) = v13;
    v15 = v9[6];
    *((_OWORD *)Data4 + 5) = v14;
    v16 = v9[7];
    v9 += 8;
    *((_OWORD *)Data4 + 6) = v15;
    *((_OWORD *)Data4 + 7) = v16;
    Data4 += 128;
    --v7;
  }
  while ( v7 );
  v17 = *v9;
  v18 = *((_QWORD *)v9 + 2);
  *(_OWORD *)Data4 = v17;
  *((_QWORD *)Data4 + 2) = v18;
  WwanLog::Info("CWwanDeviceServices::multiCarrierDeinit", 0, L" multiCarrierDeinit Invoked");
  v19 = *(_QWORD *)&this[43].Data1 == 0;
  this[42].Data1 = -1;
  if ( v19 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  DeleteTimer(*(_QWORD *)&this[43].Data1);
  DeleteReadWriteLock(this[43].Data4);
  WwanLog::Info("CWwanDeviceServices::multiCarrierDeinit", 0, L" multiCarrierDeinit completed");
}

```

## disassembly

```asm
0x1800221ec  mov     [rsp+arg_0], rbx
0x1800221f1  push    rdi
0x1800221f2  sub     rsp, 260h
0x1800221f9  cmp     dword ptr [rcx+10h], 0
0x1800221fd  mov     rbx, rcx
0x180022200  jnz     short loc_18002224D
0x180022202  cmp     qword ptr [rcx+28h], 0
0x180022207  jbe     short loc_18002224D
0x180022209  lea     r8, aInterfaceSuppo_1; " Interface supported device services. S"...
0x180022210  xor     edx, edx; struct _GUID *
0x180022212  lea     rcx, aCwwandeviceser_44; "CWwanDeviceServices::Deinit"
0x180022219  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002221e  xor     r9d, r9d; unsigned int
0x180022221  lea     rax, ?sc_szExecutorDescription@CWwanExecutorMbim@@0QBGB; "Mobile Broadband Adapter"
0x180022228  mov     [rsp+268h+var_238], rax; void *
0x18002222d  mov     r8, rbx; struct _GUID *
0x180022230  mov     [rsp+268h+var_240], 32h ; '2'; unsigned int
0x180022238  mov     [rsp+268h+var_248], 0; void *
0x180022241  lea     edx, [r9+5]; unsigned int
0x180022245  lea     ecx, [rdx+0Bh]; unsigned int
0x180022248  call    ?WwanNhNotificationDispatcherWithHeader@@YAXKKPEBU_GUID@@KPEBXK1@Z; WwanNhNotificationDispatcherWithHeader(ulong,ulong,_GUID const *,ulong,void const *,ulong,void const *)
0x18002224d  mov     rcx, rbx; this
0x180022250  call    ?flushAllDeviceServiceRequests@CWwanDeviceServices@@AEAAXXZ; CWwanDeviceServices::flushAllDeviceServiceRequests(void)
0x180022255  lea     rdi, [rbx+60h]
0x180022259  cmp     qword ptr [rdi], 0
0x18002225d  jz      short loc_180022278
0x18002225f  mov     r8d, 4C7h
0x180022265  mov     rdx, rdi
0x180022268  mov     rcx, rbx; struct _GUID *
0x18002226b  call    ?completeDeviceServiceRequest@CWwanDeviceServices@@AEAAXAEBV?$shared_ptr@U_WWAN_DS_REQUEST_CONTEXT@@@std@@K@Z; CWwanDeviceServices::completeDeviceServiceRequest(std::shared_ptr<_WWAN_DS_REQUEST_CONTEXT> const &,ulong)
0x180022270  mov     rcx, rdi
0x180022273  call    ?reset@?$shared_ptr@U_WWAN_DS_REQUEST_CONTEXT@@@std@@QEAAXXZ; std::shared_ptr<_WWAN_DS_REQUEST_CONTEXT>::reset(void)
0x180022278  mov     rdx, [rbx+30h]
0x18002227c  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U_WWAN_DS_CLIENT_STATE@@PEAX@std@@@std@@@?$_List_node@U_WWAN_DS_CLIENT_STATE@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U_WWAN_DS_CLIENT_STATE@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<_WWAN_DS_CLIENT_STATE,void *>::_Free_non_head<std::allocator<std::_List_node<_WWAN_DS_CLIENT_STATE,void *>>>(std::allocator<std::_List_node<_WWAN_DS_CLIENT_STATE,void *>> &,std::_List_node<_WWAN_DS_CLIENT_STATE,void *> *)
0x180022281  mov     rax, [rbx+30h]
0x180022285  mov     [rax], rax
0x180022288  mov     rax, [rbx+30h]
0x18002228c  mov     [rax+8], rax
0x180022290  mov     qword ptr [rbx+38h], 0
0x180022298  mov     rdx, [rbx+50h]
0x18002229c  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U_WWAN_DSS_STATE@@PEAX@std@@@std@@@?$_List_node@U_WWAN_DSS_STATE@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U_WWAN_DSS_STATE@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<_WWAN_DSS_STATE,void *>::_Free_non_head<std::allocator<std::_List_node<_WWAN_DSS_STATE,void *>>>(std::allocator<std::_List_node<_WWAN_DSS_STATE,void *>> &,std::_List_node<_WWAN_DSS_STATE,void *> *)
0x1800222a1  mov     rax, [rbx+50h]
0x1800222a5  lea     rcx, [rbx+20h]
0x1800222a9  mov     [rax], rax
0x1800222ac  mov     rax, [rbx+50h]
0x1800222b0  mov     [rax+8], rax
0x1800222b4  mov     qword ptr [rbx+58h], 0
0x1800222bc  call    ?clear@?$list@U_WWAN_DS_STATE@@V?$allocator@U_WWAN_DS_STATE@@@std@@@std@@QEAAXXZ; std::list<_WWAN_DS_STATE>::clear(void)
0x1800222c1  or      edi, 0FFFFFFFFh
0x1800222c4  xorps   xmm0, xmm0
0x1800222c7  movdqu  xmmword ptr [rbx], xmm0
0x1800222cb  mov     [rbx+10h], edi
0x1800222ce  mov     rcx, [rbx+18h]; Block
0x1800222d2  mov     qword ptr [rbx+18h], 0
0x1800222da  test    rcx, rcx
0x1800222dd  jz      short loc_1800222E9
0x1800222df  mov     edx, 14h
0x1800222e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800222e9  mov     rcx, [rbx+90h]
0x1800222f0  xor     eax, eax
0x1800222f2  xorps   xmm0, xmm0
0x1800222f5  movups  xmmword ptr [rbx+70h], xmm0
0x1800222f9  mov     [rbx+80h], eax
0x1800222ff  test    rcx, rcx
0x180022302  jz      short loc_18002230A
0x180022304  call    cs:__imp_SwDeviceClose
0x18002230a  xor     edx, edx; Val
0x18002230c  lea     rcx, [rsp+268h+var_228]; void *
0x180022311  mov     r8d, 218h; Size
0x180022317  call    memset_0
0x18002231c  mov     edx, 4
0x180022321  lea     rcx, [rbx+88h]
0x180022328  lea     rax, [rsp+268h+var_228]
0x18002232d  lea     r8d, [rdx+7Ch]
0x180022331  movups  xmm0, xmmword ptr [rax]
0x180022334  movups  xmm1, xmmword ptr [rax+10h]
0x180022338  movups  xmmword ptr [rcx], xmm0
0x18002233b  movups  xmm0, xmmword ptr [rax+20h]
0x18002233f  movups  xmmword ptr [rcx+10h], xmm1
0x180022343  movups  xmm1, xmmword ptr [rax+30h]
0x180022347  movups  xmmword ptr [rcx+20h], xmm0
0x18002234b  movups  xmm0, xmmword ptr [rax+40h]
0x18002234f  movups  xmmword ptr [rcx+30h], xmm1
0x180022353  movups  xmm1, xmmword ptr [rax+50h]
0x180022357  movups  xmmword ptr [rcx+40h], xmm0
0x18002235b  movups  xmm0, xmmword ptr [rax+60h]
0x18002235f  movups  xmmword ptr [rcx+50h], xmm1
0x180022363  movups  xmm1, xmmword ptr [rax+70h]
0x180022367  add     rax, r8
0x18002236a  movups  xmmword ptr [rcx+60h], xmm0
0x18002236e  movups  xmmword ptr [rcx+70h], xmm1
0x180022372  add     rcx, r8
0x180022375  sub     rdx, 1; struct _GUID *
0x180022379  jnz     short loc_180022331
0x18002237b  movups  xmm0, xmmword ptr [rax]
0x18002237e  mov     rax, [rax+10h]
0x180022382  lea     r8, aMulticarrierde_0; " multiCarrierDeinit Invoked"
0x180022389  movups  xmmword ptr [rcx], xmm0
0x18002238c  mov     [rcx+10h], rax
0x180022390  lea     rcx, aCwwandeviceser_39; "CWwanDeviceServices::multiCarrierDeinit"
0x180022397  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002239c  cmp     qword ptr [rbx+2B0h], 0
0x1800223a4  mov     [rbx+2A0h], edi
0x1800223aa  jnz     short loc_1800223B1
0x1800223ac  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800223b1  mov     rcx, [rbx+2B0h]
0x1800223b8  call    cs:__imp_DeleteTimer
0x1800223be  lea     rcx, [rbx+2B8h]
0x1800223c5  call    cs:__imp_DeleteReadWriteLock
0x1800223cb  lea     r8, aMulticarrierde; " multiCarrierDeinit completed"
0x1800223d2  xor     edx, edx; struct _GUID *
0x1800223d4  lea     rcx, aCwwandeviceser_39; "CWwanDeviceServices::multiCarrierDeinit"
0x1800223db  mov     rbx, [rsp+268h+arg_0]
0x1800223e3  add     rsp, 260h
0x1800223ea  pop     rdi
0x1800223eb  jmp     ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
```
