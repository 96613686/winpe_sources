# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180015820`
- end: `0x18001594a`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fc3c`
- `0x18000fcd4`
- `0x180010b80`
- `0x180010f28`

## callees

- `0x180001e40`
- `0x180015820`
- `0x180015a68`
- `0x18001620c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001589a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001589a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015922`

## string_xrefs

- `0x180015893`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // r14
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v8; // ecx
  __int128 v9; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-30h]
  __int128 v11; // [rsp+50h] [rbp-20h]

  v2 = a2;
  v9 = 0;
  *(_OWORD *)pv = 0;
  v11 = 0;
  if ( *(_DWORD *)(a1 + 232) )
    v2 = a2 | 8;
  v4 = *(_DWORD *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  if ( `TestQueryData'::`2'::s_pfnTestQueryData )
    goto LABEL_16;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestQueryData");
  `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_16:
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v5, v2, v4, &v9) )
    {
      v8 = (int)pv[0];
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v9);
      else
        *(_DWORD *)(a1 + 184) = v8;
      tip2::details::shared_data<1,0,0>::evaluate_and_report(a1, v11);
    }
  }
  else
  {
    v9 = 0;
    *(_OWORD *)pv = 0;
    v11 = 0;
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x180015820  mov     [rsp-18h+arg_10], rbx
0x180015825  mov     [rsp-18h+arg_18], rsi
0x18001582a  push    rbp
0x18001582b  push    rdi
0x18001582c  push    r14
0x18001582e  mov     rbp, rsp
0x180015831  sub     rsp, 70h
0x180015835  mov     rax, cs:__security_cookie
0x18001583c  xor     rax, rsp
0x18001583f  mov     [rbp+var_10], rax
0x180015843  mov     edi, edx
0x180015845  mov     rbx, rcx
0x180015848  xorps   xmm0, xmm0
0x18001584b  movups  [rbp+var_40], xmm0
0x18001584f  movups  xmmword ptr [rbp+pv], xmm0
0x180015853  movups  [rbp+var_20], xmm0
0x180015857  cmp     dword ptr [rcx+0E8h], 0
0x18001585e  jbe     short loc_180015863
0x180015860  or      edi, 8
0x180015863  mov     esi, [rcx+0B8h]
0x180015869  mov     r14, [rcx+0F0h]
0x180015870  mov     qword ptr [rcx+0F0h], 0
0x18001587b  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180015882  test    rax, rax
0x180015885  jnz     short loc_1800158D4
0x180015887  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001588e  test    rax, rax
0x180015891  jnz     short loc_1800158A7
0x180015893  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001589a  call    cs:__imp_GetModuleHandleW
0x1800158a0  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800158a7  lea     rdx, aTestquerydata; "TestQueryData"
0x1800158ae  mov     rcx, rax; hModule
0x1800158b1  call    cs:__imp_GetProcAddress
0x1800158b7  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800158be  test    rax, rax
0x1800158c1  jnz     short loc_1800158D4
0x1800158c3  xorps   xmm0, xmm0
0x1800158c6  movups  [rbp+var_40], xmm0
0x1800158ca  movups  xmmword ptr [rbp+pv], xmm0
0x1800158ce  movups  [rbp+var_20], xmm0
0x1800158d2  jmp     short loc_18001591E
0x1800158d4  lea     r9, [rbp+var_40]
0x1800158d8  mov     r8d, esi
0x1800158db  mov     edx, edi
0x1800158dd  mov     rcx, r14
0x1800158e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158e5  test    eax, eax
0x1800158e7  jz      short loc_18001591E
0x1800158e9  mov     rcx, [rbp+pv]
0x1800158ed  mov     rax, rcx
0x1800158f0  shr     rax, 20h
0x1800158f4  or      [rbx+40h], eax
0x1800158f7  cmp     [rbp+pv+8], 0
0x1800158fc  jz      short loc_18001590C
0x1800158fe  lea     rdx, [rbp+var_40]
0x180015902  mov     rcx, rbx
0x180015905  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18001590a  jmp     short loc_180015912
0x18001590c  mov     [rbx+0B8h], ecx
0x180015912  mov     rdx, qword ptr [rbp+var_20]
0x180015916  mov     rcx, rbx
0x180015919  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x18001591e  mov     rcx, [rbp+pv+8]; pv
0x180015922  call    cs:__imp_CoTaskMemFree
0x180015928  nop
0x180015929  mov     rcx, [rbp+var_10]
0x18001592d  xor     rcx, rsp; StackCookie
0x180015930  call    __security_check_cookie
0x180015935  lea     r11, [rsp+70h+var_s0]
0x18001593a  mov     rbx, [r11+30h]
0x18001593e  mov     rsi, [r11+38h]
0x180015942  mov     rsp, r11
0x180015945  pop     r14
0x180015947  pop     rdi
0x180015948  pop     rbp
0x180015949  retn
```
