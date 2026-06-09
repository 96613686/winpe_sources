# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x1800255d4`
- end: `0x180025704`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180023d40`
- `0x1800253f0`
- `0x18004c32c`
- `0x18004c730`
- `0x18004d7b8`
- `0x180053354`
- `0x180083b48`

## callees

- `0x1800255d4`
- `0x180026494`
- `0x18002701c`
- `0x18002dd48`
- `0x18005bfe0`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800256de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800256de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800256cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800256cb`

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
0x1800255d4  mov     [rsp-8+arg_8], rbx
0x1800255d9  push    rbp
0x1800255da  lea     rbp, [rsp-790h]
0x1800255e2  sub     rsp, 890h
0x1800255e9  mov     rax, cs:__security_cookie
0x1800255f0  xor     rax, rsp
0x1800255f3  mov     [rbp+790h+var_10], rax
0x1800255fa  bts     dword ptr [rcx+40h], 0Bh
0x1800255ff  mov     rbx, rcx
0x180025602  cmp     qword ptr [rcx+0F0h], 0
0x18002560a  jz      loc_1800256D1
0x180025610  test    dword ptr [rcx+40h], 100h
0x180025617  jnz     loc_1800256D1
0x18002561d  xorps   xmm0, xmm0
0x180025620  mov     [rsp+890h+var_840], 0
0x180025629  lea     rax, [rsp+890h+var_837]
0x18002562e  mov     [rsp+890h+var_838], 0
0x180025633  mov     [rbp+790h+var_30], rax
0x18002563a  lea     rdx, [rsp+890h+var_840]
0x18002563f  lea     rax, [rbp+790h+var_37]
0x180025646  mov     [rsp+890h+var_837], 80408040h
0x18002564e  mov     [rbp+790h+var_20], rax
0x180025655  mov     r8d, 1
0x18002565b  lea     rax, [rsp+890h+var_832]
0x180025660  mov     [rsp+890h+var_833], 0
0x180025665  mov     [rbp+790h+var_28], rax
0x18002566c  movups  [rsp+890h+var_870], xmm0
0x180025671  movups  xmmword ptr [rsp+890h+pv], xmm0
0x180025676  movups  [rsp+890h+var_850], xmm0
0x18002567b  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180025680  mov     rcx, [rbx+0F0h]
0x180025687  lea     r9, [rsp+890h+var_870]
0x18002568c  mov     r8, rax
0x18002568f  call    TestUnlockData
0x180025694  mov     eax, dword ptr [rsp+890h+pv+4]
0x180025698  or      [rbx+40h], eax
0x18002569b  cmp     [rsp+890h+pv+8], 0
0x1800256a1  jz      short loc_1800256B2
0x1800256a3  lea     rdx, [rsp+890h+var_870]
0x1800256a8  mov     rcx, rbx
0x1800256ab  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800256b0  jmp     short loc_1800256BC
0x1800256b2  mov     eax, dword ptr [rsp+890h+pv]
0x1800256b6  mov     [rbx+0B8h], eax
0x1800256bc  lea     rcx, [rsp+890h+var_840]
0x1800256c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800256c6  mov     rcx, [rsp+890h+pv+8]; pv
0x1800256cb  call    cs:__imp_CoTaskMemFree
0x1800256d1  dec     dword ptr [rbx+0E8h]
0x1800256d7  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800256de  call    cs:__imp_LeaveCriticalSection
0x1800256e4  mov     rcx, [rbp+790h+var_10]
0x1800256eb  xor     rcx, rsp; StackCookie
0x1800256ee  call    __security_check_cookie
0x1800256f3  mov     rbx, [rsp+890h+arg_8]
0x1800256fb  add     rsp, 890h
0x180025702  pop     rbp
0x180025703  retn
```
