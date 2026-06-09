# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x18001779c`
- end: `0x180017948`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f708`

## callees

- `0x180001e40`
- `0x18000ffd0`
- `0x180015a68`
- `0x18001779c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800177fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800178af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800177fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800178af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017812`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800178c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017812`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800178c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800178e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800178e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017920`

## string_xrefs

- `0x1800177f4`: `kernelbase.dll`
- `0x1800178a8`: `kernelbase.dll`
- `0x180017808`: `TestOpen`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::open_without_lock(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  unsigned int v6; // r14d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // r14
  __int64 v10; // rdi
  DWORD LastError; // esi
  FARPROC v12; // rax
  HMODULE v13; // rax
  __int64 v14; // [rsp+30h] [rbp-40h] BYREF
  __int128 v15; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-28h]
  __int128 v17; // [rsp+58h] [rbp-18h]

  v15 = 0;
  *(_OWORD *)pv = 0;
  v17 = 0;
  v5 = *(_BYTE *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestOpen'::`2'::s_pfnTestOpen;
  if ( `TestOpen'::`2'::s_pfnTestOpen )
    goto LABEL_6;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestOpen");
  `TestOpen'::`2'::s_pfnTestOpen = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_6:
    LOBYTE(a3) = v5;
    v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int128 *))ProcAddress)(v6, 2097154, a3, a2, &v15);
    v14 = v9;
    if ( v9 )
    {
      *(_OWORD *)(a1 + 144) = v15;
      v14 = 0;
      v10 = *(_QWORD *)(a1 + 240);
      if ( v10 )
      {
        LastError = GetLastError();
        v12 = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
        if ( `TestClose'::`2'::s_pfnTestClose )
          goto LABEL_12;
        v13 = g_tip_details_kernelbaseModuleHandle;
        if ( !g_tip_details_kernelbaseModuleHandle )
        {
          v13 = GetModuleHandleW(L"kernelbase.dll");
          g_tip_details_kernelbaseModuleHandle = v13;
        }
        v12 = GetProcAddress(v13, "TestClose");
        `TestClose'::`2'::s_pfnTestClose = (__int64)v12;
        if ( v12 )
LABEL_12:
          ((void (__fastcall *)(__int64))v12)(v10);
        SetLastError(LastError);
      }
      *(_QWORD *)(a1 + 240) = v9;
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v15);
      else
        *(_DWORD *)(a1 + 184) = pv[0];
    }
  }
  else
  {
    v15 = 0;
    *(_OWORD *)pv = 0;
    v17 = 0;
    v14 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(&v14);
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x18001779c  mov     [rsp-18h+arg_10], rbx
0x1800177a1  mov     [rsp-18h+arg_18], rsi
0x1800177a6  push    rbp
0x1800177a7  push    rdi
0x1800177a8  push    r14
0x1800177aa  mov     rbp, rsp
0x1800177ad  sub     rsp, 70h
0x1800177b1  mov     rax, cs:__security_cookie
0x1800177b8  xor     rax, rsp
0x1800177bb  mov     [rbp+var_8], rax
0x1800177bf  mov     rdi, rdx
0x1800177c2  mov     rbx, rcx
0x1800177c5  xorps   xmm0, xmm0
0x1800177c8  movups  [rbp+var_38], xmm0
0x1800177cc  movups  xmmword ptr [rbp+pv], xmm0
0x1800177d0  movups  [rbp+var_18], xmm0
0x1800177d4  mov     sil, [rcx+20h]
0x1800177d8  mov     r14d, [rcx+10h]
0x1800177dc  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x1800177e3  test    rax, rax
0x1800177e6  jnz     short loc_18001783C
0x1800177e8  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800177ef  test    rax, rax
0x1800177f2  jnz     short loc_180017808
0x1800177f4  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800177fb  call    cs:__imp_GetModuleHandleW
0x180017801  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180017808  lea     rdx, aTestopen; "TestOpen"
0x18001780f  mov     rcx, rax; hModule
0x180017812  call    cs:__imp_GetProcAddress
0x180017818  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18001781f  test    rax, rax
0x180017822  jnz     short loc_18001783C
0x180017824  xorps   xmm0, xmm0
0x180017827  movups  [rbp+var_38], xmm0
0x18001782b  movups  xmmword ptr [rbp+pv], xmm0
0x18001782f  movups  [rbp+var_18], xmm0
0x180017833  mov     [rbp+var_40], rax
0x180017837  jmp     loc_180017913
0x18001783c  lea     rcx, [rbp+var_38]
0x180017840  mov     [rsp+70h+var_50], rcx
0x180017845  mov     r9, rdi
0x180017848  mov     r8b, sil
0x18001784b  mov     edx, 200002h
0x180017850  mov     ecx, r14d
0x180017853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017858  mov     r14, rax
0x18001785b  mov     [rbp+var_40], rax
0x18001785f  test    rax, rax
0x180017862  jz      loc_180017913
0x180017868  movups  xmm0, [rbp+var_38]
0x18001786c  movdqu  xmmword ptr [rbx+90h], xmm0
0x180017874  mov     [rbp+var_40], 0
0x18001787c  mov     rdi, [rbx+0F0h]
0x180017883  test    rdi, rdi
0x180017886  jz      short loc_1800178E8
0x180017888  call    cs:__imp_GetLastError
0x18001788e  mov     esi, eax
0x180017890  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180017897  test    rax, rax
0x18001789a  jnz     short loc_1800178D8
0x18001789c  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800178a3  test    rax, rax
0x1800178a6  jnz     short loc_1800178BC
0x1800178a8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800178af  call    cs:__imp_GetModuleHandleW
0x1800178b5  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800178bc  lea     rdx, aTestclose; "TestClose"
0x1800178c3  mov     rcx, rax; hModule
0x1800178c6  call    cs:__imp_GetProcAddress
0x1800178cc  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x1800178d3  test    rax, rax
0x1800178d6  jz      short loc_1800178E0
0x1800178d8  mov     rcx, rdi
0x1800178db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178e0  mov     ecx, esi; dwErrCode
0x1800178e2  call    cs:__imp_SetLastError
0x1800178e8  mov     [rbx+0F0h], r14
0x1800178ef  mov     eax, dword ptr [rbp+pv+4]
0x1800178f2  or      [rbx+40h], eax
0x1800178f5  cmp     [rbp+pv+8], 0
0x1800178fa  jz      short loc_18001790A
0x1800178fc  lea     rdx, [rbp+var_38]
0x180017900  mov     rcx, rbx
0x180017903  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180017908  jmp     short loc_180017913
0x18001790a  mov     eax, dword ptr [rbp+pv]
0x18001790d  mov     [rbx+0B8h], eax
0x180017913  lea     rcx, [rbp+var_40]
0x180017917  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18001791c  mov     rcx, [rbp+pv+8]; pv
0x180017920  call    cs:__imp_CoTaskMemFree
0x180017926  nop
0x180017927  mov     rcx, [rbp+var_8]
0x18001792b  xor     rcx, rsp; StackCookie
0x18001792e  call    __security_check_cookie
0x180017933  lea     r11, [rsp+70h+var_s0]
0x180017938  mov     rbx, [r11+30h]
0x18001793c  mov     rsi, [r11+38h]
0x180017940  mov     rsp, r11
0x180017943  pop     r14
0x180017945  pop     rdi
0x180017946  pop     rbp
0x180017947  retn
```
