# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x14000fe7c`
- end: `0x14000ffb9`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14000e990`

## callees

- `0x140002480`
- `0x14000cfc0`
- `0x14000fce8`
- `0x14000fe7c`
- `0x140011ff8`
- `0x140012d08`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000ff8c`
- `KERNEL32!LeaveCriticalSection` at `0x14000ff8c`
- `ole32!CoTaskMemFree` at `0x14000ff73`
- `ole32!CoTaskMemFree` at `0x14000ff73`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h]
  void *v7; // [rsp+50h] [rbp-B0h] BYREF
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
0x14000fe7c  mov     [rsp-8+arg_8], rbx
0x14000fe81  push    rbp
0x14000fe82  lea     rbp, [rsp-790h]
0x14000fe8a  sub     rsp, 890h
0x14000fe91  mov     rax, cs:__security_cookie
0x14000fe98  xor     rax, rsp
0x14000fe9b  mov     [rbp+790h+var_10], rax
0x14000fea2  bts     dword ptr [rcx+40h], 0Bh
0x14000fea7  mov     rbx, rcx
0x14000feaa  cmp     qword ptr [rcx+0F0h], 0
0x14000feb2  jz      loc_14000FF7F
0x14000feb8  test    dword ptr [rcx+40h], 100h
0x14000febf  jnz     loc_14000FF7F
0x14000fec5  xorps   xmm0, xmm0
0x14000fec8  mov     [rsp+890h+var_840], 0
0x14000fed1  lea     rax, [rsp+890h+var_837]
0x14000fed6  mov     [rsp+890h+var_838], 0
0x14000fedb  mov     [rbp+790h+var_30], rax
0x14000fee2  lea     rdx, [rsp+890h+var_840]
0x14000fee7  lea     rax, [rbp+790h+var_37]
0x14000feee  mov     [rsp+890h+var_837], 80408040h
0x14000fef6  mov     [rbp+790h+var_20], rax
0x14000fefd  mov     r8d, 1
0x14000ff03  lea     rax, [rsp+890h+var_832]
0x14000ff08  mov     [rsp+890h+var_833], 0
0x14000ff0d  mov     [rbp+790h+var_28], rax
0x14000ff14  movups  [rsp+890h+var_870], xmm0
0x14000ff19  movups  xmmword ptr [rsp+890h+pv], xmm0
0x14000ff1e  movups  [rsp+890h+var_850], xmm0
0x14000ff23  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14000ff28  mov     rcx, [rbx+0F0h]
0x14000ff2f  lea     r9, [rsp+890h+var_870]
0x14000ff34  mov     r8, rax
0x14000ff37  call    TestUnlockData
0x14000ff3c  mov     eax, dword ptr [rsp+890h+pv+4]
0x14000ff40  or      [rbx+40h], eax
0x14000ff43  cmp     [rsp+890h+pv+8], 0
0x14000ff49  jz      short loc_14000FF5A
0x14000ff4b  lea     rdx, [rsp+890h+var_870]
0x14000ff50  mov     rcx, rbx
0x14000ff53  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x14000ff58  jmp     short loc_14000FF64
0x14000ff5a  mov     eax, dword ptr [rsp+890h+pv]
0x14000ff5e  mov     [rbx+0B8h], eax
0x14000ff64  lea     rcx, [rsp+890h+var_840]
0x14000ff69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000ff6e  mov     rcx, [rsp+890h+pv+8]; pv
0x14000ff73  call    cs:__imp_CoTaskMemFree
0x14000ff7a  nop     dword ptr [rax+rax+00h]
0x14000ff7f  dec     dword ptr [rbx+0E8h]
0x14000ff85  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x14000ff8c  call    cs:__imp_LeaveCriticalSection
0x14000ff93  nop     dword ptr [rax+rax+00h]
0x14000ff98  mov     rcx, [rbp+790h+var_10]
0x14000ff9f  xor     rcx, rsp; StackCookie
0x14000ffa2  call    __security_check_cookie
0x14000ffa7  mov     rbx, [rsp+890h+arg_8]
0x14000ffaf  add     rsp, 890h
0x14000ffb6  pop     rbp
0x14000ffb7  retn
```
