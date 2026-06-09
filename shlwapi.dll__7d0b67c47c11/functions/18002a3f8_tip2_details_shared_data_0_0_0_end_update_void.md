# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18002a3f8`
- end: `0x18002a526`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800088e0`
- `0x180029300`
- `0x180029338`
- `0x180029370`

## callees

- `0x180012550`
- `0x1800293a8`
- `0x18002a3f8`
- `0x18002b9d0`
- `0x18002c334`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a500`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4ed`

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
0x18002a3f8  mov     [rsp-8+arg_8], rbx
0x18002a3fd  push    rbp
0x18002a3fe  lea     rbp, [rsp-790h]
0x18002a406  sub     rsp, 890h
0x18002a40d  mov     rax, cs:__security_cookie
0x18002a414  xor     rax, rsp
0x18002a417  mov     [rbp+790h+var_10], rax
0x18002a41e  bts     dword ptr [rcx+40h], 0Bh
0x18002a423  mov     rbx, rcx
0x18002a426  cmp     qword ptr [rcx+0F0h], 0
0x18002a42e  jz      loc_18002A4F3
0x18002a434  test    dword ptr [rcx+40h], 100h
0x18002a43b  jnz     loc_18002A4F3
0x18002a441  test    dword ptr [rcx+14h], 8000h
0x18002a448  jnz     loc_18002A4F3
0x18002a44e  xorps   xmm0, xmm0
0x18002a451  mov     [rsp+890h+var_840], 0
0x18002a45a  lea     rax, [rsp+890h+var_837]
0x18002a45f  mov     [rsp+890h+var_838], 0
0x18002a464  mov     [rbp+790h+var_30], rax
0x18002a46b  lea     rdx, [rsp+890h+var_840]
0x18002a470  lea     rax, [rbp+790h+var_37]
0x18002a477  mov     [rsp+890h+var_837], 80408040h
0x18002a47f  mov     [rbp+790h+var_20], rax
0x18002a486  mov     r8d, 1
0x18002a48c  lea     rax, [rsp+890h+var_832]
0x18002a491  mov     [rsp+890h+var_833], 0
0x18002a496  mov     [rbp+790h+var_28], rax
0x18002a49d  movups  [rsp+890h+var_870], xmm0
0x18002a4a2  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18002a4a7  movups  [rsp+890h+var_850], xmm0
0x18002a4ac  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002a4b1  mov     rcx, [rbx+0F0h]
0x18002a4b8  lea     r9, [rsp+890h+var_870]
0x18002a4bd  mov     r8, rax
0x18002a4c0  call    TestUnlockData
0x18002a4c5  mov     eax, dword ptr [rsp+890h+pv+4]
0x18002a4c9  or      [rbx+40h], eax
0x18002a4cc  cmp     [rsp+890h+pv+8], 0
0x18002a4d2  jnz     short loc_18002A4DE
0x18002a4d4  mov     eax, dword ptr [rsp+890h+pv]
0x18002a4d8  mov     [rbx+0B8h], eax
0x18002a4de  lea     rcx, [rsp+890h+var_840]
0x18002a4e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002a4e8  mov     rcx, [rsp+890h+pv+8]; pv
0x18002a4ed  call    cs:__imp_CoTaskMemFree
0x18002a4f3  dec     dword ptr [rbx+0E8h]
0x18002a4f9  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18002a500  call    cs:__imp_LeaveCriticalSection
0x18002a506  mov     rcx, [rbp+790h+var_10]
0x18002a50d  xor     rcx, rsp; StackCookie
0x18002a510  call    __security_check_cookie
0x18002a515  mov     rbx, [rsp+890h+arg_8]
0x18002a51d  add     rsp, 890h
0x18002a524  pop     rbp
0x18002a525  retn
```
