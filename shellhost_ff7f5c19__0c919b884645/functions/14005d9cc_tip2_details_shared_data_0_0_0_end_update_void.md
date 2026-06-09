# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x14005d9cc`
- end: `0x14005db42`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140052eec`

## callees

- `0x14000a2d4`
- `0x14000f7e0`
- `0x140052fe0`
- `0x14005d9cc`
- `0x14005f544`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005daa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005daa9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005db20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005db20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005db0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005db0d`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v6; // ecx
  __int128 v7; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h]
  __int128 v9; // [rsp+50h] [rbp-B0h]
  void *v10; // [rsp+60h] [rbp-A0h] BYREF
  char v11; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+69h] [rbp-97h] BYREF
  char v13; // [rsp+6Dh] [rbp-93h]
  char v14; // [rsp+6Eh] [rbp-92h] BYREF
  char v15; // [rsp+869h] [rbp+769h] BYREF
  int *v16; // [rsp+870h] [rbp+770h]
  char *v17; // [rsp+878h] [rbp+778h]
  char *v18; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
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
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v10, 1);
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
    if ( !pv[1] )
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
0x14005d9cc  push    rbp
0x14005d9ce  push    rbx
0x14005d9cf  push    rsi
0x14005d9d0  push    rdi
0x14005d9d1  lea     rbp, [rsp-7A8h]
0x14005d9d9  sub     rsp, 8A8h
0x14005d9e0  mov     rax, cs:__security_cookie
0x14005d9e7  xor     rax, rsp
0x14005d9ea  mov     [rbp+7C0h+var_30], rax
0x14005d9f1  mov     rbx, rcx
0x14005d9f4  bts     dword ptr [rcx+40h], 0Bh
0x14005d9f9  cmp     qword ptr [rcx+0F0h], 0
0x14005da01  jz      loc_14005DB13
0x14005da07  test    dword ptr [rcx+40h], 100h
0x14005da0e  jnz     loc_14005DB13
0x14005da14  test    dword ptr [rcx+14h], 8000h
0x14005da1b  jnz     loc_14005DB13
0x14005da21  xorps   xmm0, xmm0
0x14005da24  movups  [rsp+8C0h+var_890], xmm0
0x14005da29  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x14005da2e  movups  [rsp+8C0h+var_870], xmm0
0x14005da33  mov     [rsp+8C0h+var_860], 0
0x14005da3c  mov     [rsp+8C0h+var_858], 0
0x14005da41  lea     rax, [rsp+8C0h+var_857]
0x14005da46  mov     [rbp+7C0h+var_50], rax
0x14005da4d  lea     rax, [rbp+7C0h+var_57]
0x14005da54  mov     [rbp+7C0h+var_40], rax
0x14005da5b  mov     [rsp+8C0h+var_857], 80408040h
0x14005da63  mov     [rsp+8C0h+var_853], 0
0x14005da68  lea     rax, [rsp+8C0h+var_852]
0x14005da6d  mov     [rbp+7C0h+var_48], rax
0x14005da74  mov     r8d, 1
0x14005da7a  lea     rdx, [rsp+8C0h+var_860]
0x14005da7f  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14005da84  mov     rdi, rax
0x14005da87  mov     rsi, [rbx+0F0h]
0x14005da8e  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x14005da95  test    rax, rax
0x14005da98  jnz     short loc_14005DACF
0x14005da9a  call    tip_details_GetKernelBaseModuleHandle
0x14005da9f  mov     rcx, rax; hModule
0x14005daa2  lea     rdx, aTestunlockdata; "TestUnlockData"
0x14005daa9  call    cs:__imp_GetProcAddress
0x14005daaf  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x14005dab6  test    rax, rax
0x14005dab9  jnz     short loc_14005DACF
0x14005dabb  xorps   xmm0, xmm0
0x14005dabe  movups  [rsp+8C0h+var_890], xmm0
0x14005dac3  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x14005dac8  movups  [rsp+8C0h+var_870], xmm0
0x14005dacd  jmp     short loc_14005DAE1
0x14005dacf  lea     r9, [rsp+8C0h+var_890]
0x14005dad4  mov     r8, rdi
0x14005dad7  xor     edx, edx
0x14005dad9  mov     rcx, rsi
0x14005dadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005dae1  mov     rcx, [rsp+8C0h+pv]
0x14005dae6  mov     rax, rcx
0x14005dae9  shr     rax, 20h
0x14005daed  or      [rbx+40h], eax
0x14005daf0  cmp     [rsp+8C0h+pv+8], 0
0x14005daf6  jnz     short loc_14005DAFE
0x14005daf8  mov     [rbx+0B8h], ecx
0x14005dafe  lea     rcx, [rsp+8C0h+var_860]
0x14005db03  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005db08  mov     rcx, [rsp+8C0h+pv+8]; pv
0x14005db0d  call    cs:__imp_CoTaskMemFree
0x14005db13  dec     dword ptr [rbx+0E8h]
0x14005db19  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x14005db20  call    cs:__imp_LeaveCriticalSection
0x14005db26  nop
0x14005db27  mov     rcx, [rbp+7C0h+var_30]
0x14005db2e  xor     rcx, rsp; StackCookie
0x14005db31  call    __security_check_cookie
0x14005db36  add     rsp, 8A8h
0x14005db3d  pop     rdi
0x14005db3e  pop     rsi
0x14005db3f  pop     rbx
0x14005db40  pop     rbp
0x14005db41  retn
```
