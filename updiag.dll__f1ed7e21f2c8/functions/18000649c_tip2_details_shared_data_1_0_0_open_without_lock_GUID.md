# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x18000649c`
- end: `0x1800065da`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005c34`

## callees

- `0x180005e00`
- `0x18000649c`
- `0x1800065e0`
- `0x180006680`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800065b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800065b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006512`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006512`

## string_xrefs

- `0x180006508`: `TestOpen`
- `0x1800064f4`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::open_without_lock(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  unsigned int v6; // r14d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // rax
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-28h]
  __int128 v13; // [rsp+58h] [rbp-18h]

  v11 = 0;
  *(_OWORD *)pv = 0;
  v13 = 0;
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
    v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int128 *))ProcAddress)(v6, 2097154, a3, a2, &v11);
    v10 = v9;
    if ( v9 )
    {
      *(_OWORD *)(a1 + 144) = v11;
      v10 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
        a1 + 240,
        v9);
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v11);
      else
        *(_DWORD *)(a1 + 184) = pv[0];
    }
  }
  else
  {
    v11 = 0;
    *(_OWORD *)pv = 0;
    v13 = 0;
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(&v10);
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x18000649c  mov     [rsp-18h+arg_10], rbx
0x1800064a1  mov     [rsp-18h+arg_18], rsi
0x1800064a6  push    rbp
0x1800064a7  push    rdi
0x1800064a8  push    r14
0x1800064aa  mov     rbp, rsp
0x1800064ad  sub     rsp, 70h
0x1800064b1  mov     rax, cs:__security_cookie
0x1800064b8  xor     rax, rsp
0x1800064bb  mov     [rbp+var_8], rax
0x1800064bf  mov     rdi, rdx
0x1800064c2  mov     rbx, rcx
0x1800064c5  xorps   xmm0, xmm0
0x1800064c8  movups  [rbp+var_38], xmm0
0x1800064cc  movups  xmmword ptr [rbp+pv], xmm0
0x1800064d0  movups  [rbp+var_18], xmm0
0x1800064d4  mov     sil, [rcx+20h]
0x1800064d8  mov     r14d, [rcx+10h]
0x1800064dc  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x1800064e3  test    rax, rax
0x1800064e6  jnz     short loc_180006539
0x1800064e8  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800064ef  test    rax, rax
0x1800064f2  jnz     short loc_180006508
0x1800064f4  lea     rcx, ModuleName; "kernelbase.dll"
0x1800064fb  call    cs:__imp_GetModuleHandleW
0x180006501  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180006508  lea     rdx, aTestopen; "TestOpen"
0x18000650f  mov     rcx, rax; hModule
0x180006512  call    cs:__imp_GetProcAddress
0x180006518  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18000651f  test    rax, rax
0x180006522  jnz     short loc_180006539
0x180006524  xorps   xmm0, xmm0
0x180006527  movups  [rbp+var_38], xmm0
0x18000652b  movups  xmmword ptr [rbp+pv], xmm0
0x18000652f  movups  [rbp+var_18], xmm0
0x180006533  mov     [rbp+var_40], rax
0x180006537  jmp     short loc_1800065A5
0x180006539  lea     rcx, [rbp+var_38]
0x18000653d  mov     [rsp+70h+var_50], rcx
0x180006542  mov     r9, rdi
0x180006545  mov     r8b, sil
0x180006548  mov     edx, 200002h
0x18000654d  mov     ecx, r14d
0x180006550  call    _guard_dispatch_icall
0x180006555  mov     [rbp+var_40], rax
0x180006559  test    rax, rax
0x18000655c  jz      short loc_1800065A5
0x18000655e  movups  xmm0, [rbp+var_38]
0x180006562  movdqu  xmmword ptr [rbx+90h], xmm0
0x18000656a  mov     [rbp+var_40], 0
0x180006572  lea     rcx, [rbx+0F0h]
0x180006579  mov     rdx, rax
0x18000657c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x180006581  mov     eax, dword ptr [rbp+pv+4]
0x180006584  or      [rbx+40h], eax
0x180006587  cmp     [rbp+pv+8], 0
0x18000658c  jz      short loc_18000659C
0x18000658e  lea     rdx, [rbp+var_38]
0x180006592  mov     rcx, rbx
0x180006595  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18000659a  jmp     short loc_1800065A5
0x18000659c  mov     eax, dword ptr [rbp+pv]
0x18000659f  mov     [rbx+0B8h], eax
0x1800065a5  lea     rcx, [rbp+var_40]
0x1800065a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800065ae  mov     rcx, [rbp+pv+8]; pv
0x1800065b2  call    cs:__imp_CoTaskMemFree
0x1800065b8  nop
0x1800065b9  mov     rcx, [rbp+var_8]
0x1800065bd  xor     rcx, rsp; StackCookie
0x1800065c0  call    __security_check_cookie
0x1800065c5  lea     r11, [rsp+70h+var_s0]
0x1800065ca  mov     rbx, [r11+30h]
0x1800065ce  mov     rsi, [r11+38h]
0x1800065d2  mov     rsp, r11
0x1800065d5  pop     r14
0x1800065d7  pop     rdi
0x1800065d8  pop     rbp
0x1800065d9  retn
```
