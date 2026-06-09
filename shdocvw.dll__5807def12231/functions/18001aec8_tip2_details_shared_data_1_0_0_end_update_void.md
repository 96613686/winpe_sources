# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18001aec8`
- end: `0x18001b040`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014cf0`

## callees

- `0x180008320`
- `0x180014d58`
- `0x18001aba8`
- `0x18001aec8`
- `0x18001c9e0`
- `0x18001db40`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001af98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001af98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b01e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b01e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b00b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b00b`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v6; // ecx
  __int128 v7; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h]
  __int128 v9; // [rsp+50h] [rbp-B0h]
  __int64 v10; // [rsp+60h] [rbp-A0h] BYREF
  char v11; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+69h] [rbp-97h] BYREF
  char v13; // [rsp+6Dh] [rbp-93h]
  char v14; // [rsp+6Eh] [rbp-92h] BYREF
  char v15; // [rsp+869h] [rbp+769h] BYREF
  int *v16; // [rsp+870h] [rbp+770h]
  char *v17; // [rsp+878h] [rbp+778h]
  char *v18; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v7 = 0;
    *(_OWORD *)pv = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v16 = &v12;
    v18 = &v15;
    v12 = -2143256512;
    v13 = 0;
    v17 = &v14;
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v10, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData
      || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
          ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestUnlockData"),
          (`TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v7);
    }
    else
    {
      v7 = 0;
      *(_OWORD *)pv = 0;
      v9 = 0;
    }
    v6 = (int)pv[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v7);
    else
      *(_DWORD *)(a1 + 184) = v6;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x18001aec8  push    rbp
0x18001aeca  push    rbx
0x18001aecb  push    rsi
0x18001aecc  push    rdi
0x18001aecd  lea     rbp, [rsp-7A8h]
0x18001aed5  sub     rsp, 8A8h
0x18001aedc  mov     rax, cs:__security_cookie
0x18001aee3  xor     rax, rsp
0x18001aee6  mov     [rbp+7C0h+var_30], rax
0x18001aeed  mov     rbx, rcx
0x18001aef0  bts     dword ptr [rcx+40h], 0Bh
0x18001aef5  cmp     qword ptr [rcx+0F0h], 0
0x18001aefd  jz      loc_18001B011
0x18001af03  test    dword ptr [rcx+40h], 100h
0x18001af0a  jnz     loc_18001B011
0x18001af10  xorps   xmm0, xmm0
0x18001af13  movups  [rsp+8C0h+var_890], xmm0
0x18001af18  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x18001af1d  movups  [rsp+8C0h+var_870], xmm0
0x18001af22  mov     [rsp+8C0h+var_860], 0
0x18001af2b  mov     [rsp+8C0h+var_858], 0
0x18001af30  lea     rax, [rsp+8C0h+var_857]
0x18001af35  mov     [rbp+7C0h+var_50], rax
0x18001af3c  lea     rax, [rbp+7C0h+var_57]
0x18001af43  mov     [rbp+7C0h+var_40], rax
0x18001af4a  mov     [rsp+8C0h+var_857], 80408040h
0x18001af52  mov     [rsp+8C0h+var_853], 0
0x18001af57  lea     rax, [rsp+8C0h+var_852]
0x18001af5c  mov     [rbp+7C0h+var_48], rax
0x18001af63  mov     r8d, 1
0x18001af69  lea     rdx, [rsp+8C0h+var_860]
0x18001af6e  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18001af73  mov     rdi, rax
0x18001af76  mov     rsi, [rbx+0F0h]
0x18001af7d  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18001af84  test    rax, rax
0x18001af87  jnz     short loc_18001AFBE
0x18001af89  call    tip_details_GetKernelBaseModuleHandle
0x18001af8e  mov     rcx, rax; hModule
0x18001af91  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18001af98  call    cs:__imp_GetProcAddress
0x18001af9e  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18001afa5  test    rax, rax
0x18001afa8  jnz     short loc_18001AFBE
0x18001afaa  xorps   xmm0, xmm0
0x18001afad  movups  [rsp+8C0h+var_890], xmm0
0x18001afb2  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x18001afb7  movups  [rsp+8C0h+var_870], xmm0
0x18001afbc  jmp     short loc_18001AFD0
0x18001afbe  lea     r9, [rsp+8C0h+var_890]
0x18001afc3  mov     r8, rdi
0x18001afc6  xor     edx, edx
0x18001afc8  mov     rcx, rsi
0x18001afcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afd0  mov     rcx, [rsp+8C0h+pv]
0x18001afd5  mov     rax, rcx
0x18001afd8  shr     rax, 20h
0x18001afdc  or      [rbx+40h], eax
0x18001afdf  cmp     [rsp+8C0h+pv+8], 0
0x18001afe5  jz      short loc_18001AFF6
0x18001afe7  lea     rdx, [rsp+8C0h+var_890]
0x18001afec  mov     rcx, rbx
0x18001afef  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18001aff4  jmp     short loc_18001AFFC
0x18001aff6  mov     [rbx+0B8h], ecx
0x18001affc  lea     rcx, [rsp+8C0h+var_860]
0x18001b001  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001b006  mov     rcx, [rsp+8C0h+pv+8]; pv
0x18001b00b  call    cs:__imp_CoTaskMemFree
0x18001b011  dec     dword ptr [rbx+0E8h]
0x18001b017  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18001b01e  call    cs:__imp_LeaveCriticalSection
0x18001b024  nop
0x18001b025  mov     rcx, [rbp+7C0h+var_30]
0x18001b02c  xor     rcx, rsp; StackCookie
0x18001b02f  call    __security_check_cookie
0x18001b034  add     rsp, 8A8h
0x18001b03b  pop     rdi
0x18001b03c  pop     rsi
0x18001b03d  pop     rbx
0x18001b03e  pop     rbp
0x18001b03f  retn
```
