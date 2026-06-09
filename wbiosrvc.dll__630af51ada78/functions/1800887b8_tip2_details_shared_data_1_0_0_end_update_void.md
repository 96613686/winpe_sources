# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x1800887b8`
- end: `0x1800888e8`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180084d94`
- `0x180086e40`

## callees

- `0x180068f60`
- `0x180085790`
- `0x180088624`
- `0x1800887b8`
- `0x18008a358`
- `0x18008ac28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800888c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800888c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800888af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800888af`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h]
  __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
  char v8; // [rsp+58h] [rbp-A8h]
  int v9; // [rsp+59h] [rbp-A7h] BYREF
  char v10; // [rsp+5Dh] [rbp-A3h]
  char v11; // [rsp+5Eh] [rbp-A2h] BYREF
  char v12; // [rsp+859h] [rbp+759h] BYREF
  int *v13; // [rsp+860h] [rbp+760h]
  char *v14; // [rsp+868h] [rbp+768h]
  char *v15; // [rsp+870h] [rbp+770h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v7 = 0;
    v8 = 0;
    v13 = &v9;
    v9 = -2143256512;
    v15 = &v12;
    v10 = 0;
    v14 = &v11;
    v4 = 0;
    *(_OWORD *)pv = 0;
    v6 = 0;
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v7, 1);
    TestUnlockData(*(_QWORD *)(a1 + 240), v3, v2, &v4);
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v4);
    else
      *(_DWORD *)(a1 + 184) = pv[0];
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v7);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x1800887b8  mov     [rsp-8+arg_8], rbx
0x1800887bd  push    rbp
0x1800887be  lea     rbp, [rsp-790h]
0x1800887c6  sub     rsp, 890h
0x1800887cd  mov     rax, cs:__security_cookie
0x1800887d4  xor     rax, rsp
0x1800887d7  mov     [rbp+790h+var_10], rax
0x1800887de  bts     dword ptr [rcx+40h], 0Bh
0x1800887e3  mov     rbx, rcx
0x1800887e6  cmp     qword ptr [rcx+0F0h], 0
0x1800887ee  jz      loc_1800888B5
0x1800887f4  test    dword ptr [rcx+40h], 100h
0x1800887fb  jnz     loc_1800888B5
0x180088801  xorps   xmm0, xmm0
0x180088804  mov     [rsp+890h+var_840], 0
0x18008880d  lea     rax, [rsp+890h+var_837]
0x180088812  mov     [rsp+890h+var_838], 0
0x180088817  mov     [rbp+790h+var_30], rax
0x18008881e  lea     rdx, [rsp+890h+var_840]
0x180088823  lea     rax, [rbp+790h+var_37]
0x18008882a  mov     [rsp+890h+var_837], 80408040h
0x180088832  mov     [rbp+790h+var_20], rax
0x180088839  mov     r8d, 1
0x18008883f  lea     rax, [rsp+890h+var_832]
0x180088844  mov     [rsp+890h+var_833], 0
0x180088849  mov     [rbp+790h+var_28], rax
0x180088850  movups  [rsp+890h+var_870], xmm0
0x180088855  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18008885a  movups  [rsp+890h+var_850], xmm0
0x18008885f  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180088864  mov     rcx, [rbx+0F0h]
0x18008886b  lea     r9, [rsp+890h+var_870]
0x180088870  mov     r8, rax
0x180088873  call    TestUnlockData
0x180088878  mov     eax, dword ptr [rsp+890h+pv+4]
0x18008887c  or      [rbx+40h], eax
0x18008887f  cmp     [rsp+890h+pv+8], 0
0x180088885  jz      short loc_180088896
0x180088887  lea     rdx, [rsp+890h+var_870]
0x18008888c  mov     rcx, rbx
0x18008888f  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180088894  jmp     short loc_1800888A0
0x180088896  mov     eax, dword ptr [rsp+890h+pv]
0x18008889a  mov     [rbx+0B8h], eax
0x1800888a0  lea     rcx, [rsp+890h+var_840]
0x1800888a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800888aa  mov     rcx, [rsp+890h+pv+8]; pv
0x1800888af  call    cs:__imp_CoTaskMemFree
0x1800888b5  dec     dword ptr [rbx+0E8h]
0x1800888bb  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800888c2  call    cs:__imp_LeaveCriticalSection
0x1800888c8  mov     rcx, [rbp+790h+var_10]
0x1800888cf  xor     rcx, rsp; StackCookie
0x1800888d2  call    __security_check_cookie
0x1800888d7  mov     rbx, [rsp+890h+arg_8]
0x1800888df  add     rsp, 890h
0x1800888e6  pop     rbp
0x1800888e7  retn
```
