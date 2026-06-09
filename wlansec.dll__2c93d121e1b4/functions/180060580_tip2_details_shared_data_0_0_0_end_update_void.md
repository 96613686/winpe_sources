# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180060580`
- end: `0x1800606bb`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005e8c8`
- `0x18005fe60`

## callees

- `0x180043a30`
- `0x18005e950`
- `0x180060580`
- `0x1800619f4`
- `0x180062208`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006068e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006068e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060675`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060675`

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
0x180060580  mov     [rsp-8+arg_8], rbx
0x180060585  push    rbp
0x180060586  lea     rbp, [rsp-790h]
0x18006058e  sub     rsp, 890h
0x180060595  mov     rax, cs:__security_cookie
0x18006059c  xor     rax, rsp
0x18006059f  mov     [rbp+790h+var_10], rax
0x1800605a6  bts     dword ptr [rcx+40h], 0Bh
0x1800605ab  mov     rbx, rcx
0x1800605ae  cmp     qword ptr [rcx+0F0h], 0
0x1800605b6  jz      loc_180060681
0x1800605bc  test    dword ptr [rcx+40h], 100h
0x1800605c3  jnz     loc_180060681
0x1800605c9  test    dword ptr [rcx+14h], 8000h
0x1800605d0  jnz     loc_180060681
0x1800605d6  xorps   xmm0, xmm0
0x1800605d9  mov     [rsp+890h+var_840], 0
0x1800605e2  lea     rax, [rsp+890h+var_837]
0x1800605e7  mov     [rsp+890h+var_838], 0
0x1800605ec  mov     [rbp+790h+var_30], rax
0x1800605f3  lea     rdx, [rsp+890h+var_840]
0x1800605f8  lea     rax, [rbp+790h+var_37]
0x1800605ff  mov     [rsp+890h+var_837], 80408040h
0x180060607  mov     [rbp+790h+var_20], rax
0x18006060e  mov     r8d, 1
0x180060614  lea     rax, [rsp+890h+var_832]
0x180060619  mov     [rsp+890h+var_833], 0
0x18006061e  mov     [rbp+790h+var_28], rax
0x180060625  movups  [rsp+890h+var_870], xmm0
0x18006062a  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18006062f  movups  [rsp+890h+var_850], xmm0
0x180060634  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180060639  mov     rcx, [rbx+0F0h]
0x180060640  lea     r9, [rsp+890h+var_870]
0x180060645  mov     r8, rax
0x180060648  call    TestUnlockData
0x18006064d  mov     eax, dword ptr [rsp+890h+pv+4]
0x180060651  or      [rbx+40h], eax
0x180060654  cmp     [rsp+890h+pv+8], 0
0x18006065a  jnz     short loc_180060666
0x18006065c  mov     eax, dword ptr [rsp+890h+pv]
0x180060660  mov     [rbx+0B8h], eax
0x180060666  lea     rcx, [rsp+890h+var_840]
0x18006066b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180060670  mov     rcx, [rsp+890h+pv+8]; pv
0x180060675  call    cs:__imp_CoTaskMemFree
0x18006067c  nop     dword ptr [rax+rax+00h]
0x180060681  dec     dword ptr [rbx+0E8h]
0x180060687  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18006068e  call    cs:__imp_LeaveCriticalSection
0x180060695  nop     dword ptr [rax+rax+00h]
0x18006069a  mov     rcx, [rbp+790h+var_10]
0x1800606a1  xor     rcx, rsp; StackCookie
0x1800606a4  call    __security_check_cookie
0x1800606a9  mov     rbx, [rsp+890h+arg_8]
0x1800606b1  add     rsp, 890h
0x1800606b8  pop     rbp
0x1800606b9  retn
```
