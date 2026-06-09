# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x180015e20`
- end: `0x180015fb9`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `409`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fdb4`
- `0x18000fe3c`
- `0x180014590`

## callees

- `0x180001e40`
- `0x180015a68`
- `0x180015e20`
- `0x1800189d8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015ef4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015ef4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015f84`

## string_xrefs

- `0x180015eed`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v6; // ecx
  __int128 v7; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v8[2]; // [rsp+40h] [rbp-C0h]
  __int128 v9; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
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
    *(_OWORD *)v8 = 0;
    v9 = 0;
    pv = 0;
    v11 = 0;
    v16 = &v12;
    v18 = &v15;
    v12 = -2143256512;
    v13 = 0;
    v17 = &v14;
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_8;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestUnlockData");
    `TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_8:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v7);
    }
    else
    {
      v7 = 0;
      *(_OWORD *)v8 = 0;
      v9 = 0;
    }
    v6 = (int)v8[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v8[0]);
    if ( v8[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v7);
    else
      *(_DWORD *)(a1 + 184) = v6;
    if ( pv )
      CoTaskMemFree(pv);
    CoTaskMemFree(v8[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180015e20  push    rbp
0x180015e22  push    rbx
0x180015e23  push    rsi
0x180015e24  push    rdi
0x180015e25  lea     rbp, [rsp-7A8h]
0x180015e2d  sub     rsp, 8A8h
0x180015e34  mov     rax, cs:__security_cookie
0x180015e3b  xor     rax, rsp
0x180015e3e  mov     [rbp+7C0h+var_30], rax
0x180015e45  mov     rbx, rcx
0x180015e48  bts     dword ptr [rcx+40h], 0Bh
0x180015e4d  cmp     qword ptr [rcx+0F0h], 0
0x180015e55  jz      loc_180015F8A
0x180015e5b  test    dword ptr [rcx+40h], 100h
0x180015e62  jnz     loc_180015F8A
0x180015e68  xorps   xmm0, xmm0
0x180015e6b  movups  [rsp+8C0h+var_890], xmm0
0x180015e70  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180015e75  movups  [rsp+8C0h+var_870], xmm0
0x180015e7a  mov     [rsp+8C0h+pv], 0
0x180015e83  mov     [rsp+8C0h+var_858], 0
0x180015e88  lea     rax, [rsp+8C0h+var_857]
0x180015e8d  mov     [rbp+7C0h+var_50], rax
0x180015e94  lea     rax, [rbp+7C0h+var_57]
0x180015e9b  mov     [rbp+7C0h+var_40], rax
0x180015ea2  mov     [rsp+8C0h+var_857], 80408040h
0x180015eaa  mov     [rsp+8C0h+var_853], 0
0x180015eaf  lea     rax, [rsp+8C0h+var_852]
0x180015eb4  mov     [rbp+7C0h+var_48], rax
0x180015ebb  mov     r8d, 1
0x180015ec1  lea     rdx, [rsp+8C0h+pv]
0x180015ec6  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180015ecb  mov     rdi, rax
0x180015ece  mov     rsi, [rbx+0F0h]
0x180015ed5  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180015edc  test    rax, rax
0x180015edf  jnz     short loc_180015F31
0x180015ee1  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180015ee8  test    rax, rax
0x180015eeb  jnz     short loc_180015F01
0x180015eed  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180015ef4  call    cs:__imp_GetModuleHandleW
0x180015efa  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180015f01  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180015f08  mov     rcx, rax; hModule
0x180015f0b  call    cs:__imp_GetProcAddress
0x180015f11  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180015f18  test    rax, rax
0x180015f1b  jnz     short loc_180015F31
0x180015f1d  xorps   xmm0, xmm0
0x180015f20  movups  [rsp+8C0h+var_890], xmm0
0x180015f25  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180015f2a  movups  [rsp+8C0h+var_870], xmm0
0x180015f2f  jmp     short loc_180015F43
0x180015f31  lea     r9, [rsp+8C0h+var_890]
0x180015f36  mov     r8, rdi
0x180015f39  xor     edx, edx
0x180015f3b  mov     rcx, rsi
0x180015f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f43  mov     rcx, [rsp+8C0h+var_880]
0x180015f48  mov     rax, rcx
0x180015f4b  shr     rax, 20h
0x180015f4f  or      [rbx+40h], eax
0x180015f52  cmp     [rsp+8C0h+var_880+8], 0
0x180015f58  jz      short loc_180015F69
0x180015f5a  lea     rdx, [rsp+8C0h+var_890]
0x180015f5f  mov     rcx, rbx
0x180015f62  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180015f67  jmp     short loc_180015F6F
0x180015f69  mov     [rbx+0B8h], ecx
0x180015f6f  mov     rcx, [rsp+8C0h+pv]; pv
0x180015f74  test    rcx, rcx
0x180015f77  jz      short loc_180015F7F
0x180015f79  call    cs:__imp_CoTaskMemFree
0x180015f7f  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x180015f84  call    cs:__imp_CoTaskMemFree
0x180015f8a  dec     dword ptr [rbx+0E8h]
0x180015f90  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180015f97  call    cs:__imp_LeaveCriticalSection
0x180015f9d  nop
0x180015f9e  mov     rcx, [rbp+7C0h+var_30]
0x180015fa5  xor     rcx, rsp; StackCookie
0x180015fa8  call    __security_check_cookie
0x180015fad  add     rsp, 8A8h
0x180015fb4  pop     rdi
0x180015fb5  pop     rsi
0x180015fb6  pop     rbx
0x180015fb7  pop     rbp
0x180015fb8  retn
```
