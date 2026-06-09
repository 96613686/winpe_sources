# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18008a29c`
- end: `0x18008a3ca`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800397d0`
- `0x180039e34`
- `0x180039f3c`
- `0x1800d1cd0`
- `0x1800d2a8c`

## callees

- `0x180073f00`
- `0x1800748d0`
- `0x180088ed0`
- `0x18008a29c`
- `0x180095130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a3a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a3a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a391`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008a391`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
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
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
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
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v7, 1);
    TestUnlockData(*(_QWORD *)(a1 + 240), v3, v2, &v4);
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( !pv[1] )
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
0x18008a29c  mov     [rsp-8+arg_8], rbx
0x18008a2a1  push    rbp
0x18008a2a2  lea     rbp, [rsp-790h]
0x18008a2aa  sub     rsp, 890h
0x18008a2b1  mov     rax, cs:__security_cookie
0x18008a2b8  xor     rax, rsp
0x18008a2bb  mov     [rbp+790h+var_10], rax
0x18008a2c2  bts     dword ptr [rcx+40h], 0Bh
0x18008a2c7  mov     rbx, rcx
0x18008a2ca  cmp     qword ptr [rcx+0F0h], 0
0x18008a2d2  jz      loc_18008A397
0x18008a2d8  test    dword ptr [rcx+40h], 100h
0x18008a2df  jnz     loc_18008A397
0x18008a2e5  test    dword ptr [rcx+14h], 8000h
0x18008a2ec  jnz     loc_18008A397
0x18008a2f2  xorps   xmm0, xmm0
0x18008a2f5  mov     [rsp+890h+var_840], 0
0x18008a2fe  lea     rax, [rsp+890h+var_837]
0x18008a303  mov     [rsp+890h+var_838], 0
0x18008a308  mov     [rbp+790h+var_30], rax
0x18008a30f  lea     rdx, [rsp+890h+var_840]
0x18008a314  lea     rax, [rbp+790h+var_37]
0x18008a31b  mov     [rsp+890h+var_837], 80408040h
0x18008a323  mov     [rbp+790h+var_20], rax
0x18008a32a  mov     r8d, 1
0x18008a330  lea     rax, [rsp+890h+var_832]
0x18008a335  mov     [rsp+890h+var_833], 0
0x18008a33a  mov     [rbp+790h+var_28], rax
0x18008a341  movups  [rsp+890h+var_870], xmm0
0x18008a346  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18008a34b  movups  [rsp+890h+var_850], xmm0
0x18008a350  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18008a355  mov     rcx, [rbx+0F0h]
0x18008a35c  lea     r9, [rsp+890h+var_870]
0x18008a361  mov     r8, rax
0x18008a364  call    TestUnlockData
0x18008a369  mov     eax, dword ptr [rsp+890h+pv+4]
0x18008a36d  or      [rbx+40h], eax
0x18008a370  cmp     [rsp+890h+pv+8], 0
0x18008a376  jnz     short loc_18008A382
0x18008a378  mov     eax, dword ptr [rsp+890h+pv]
0x18008a37c  mov     [rbx+0B8h], eax
0x18008a382  lea     rcx, [rsp+890h+var_840]
0x18008a387  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a38c  mov     rcx, [rsp+890h+pv+8]; pv
0x18008a391  call    cs:__imp_CoTaskMemFree
0x18008a397  dec     dword ptr [rbx+0E8h]
0x18008a39d  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18008a3a4  call    cs:__imp_LeaveCriticalSection
0x18008a3aa  mov     rcx, [rbp+790h+var_10]
0x18008a3b1  xor     rcx, rsp; StackCookie
0x18008a3b4  call    __security_check_cookie
0x18008a3b9  mov     rbx, [rsp+890h+arg_8]
0x18008a3c1  add     rsp, 890h
0x18008a3c8  pop     rbp
0x18008a3c9  retn
```
