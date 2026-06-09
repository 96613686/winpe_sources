# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18001962c`
- end: `0x180019747`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `32`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013a68`
- `0x180018380`
- `0x180019750`
- `0x1800229ac`
- `0x180022a38`
- `0x180022ac4`
- `0x180022b50`
- `0x180022bdc`
- `0x180024678`
- `0x180024794`
- `0x1800254a8`
- `0x1800264c0`
- `0x18002aae0`
- `0x18002be40`
- `0x18002dbe4`
- `0x18002dc40`
- `0x1800327f8`
- `0x180032890`
- `0x1800334a0`
- `0x180036900`
- `0x180040674`
- `0x1800515bc`
- `0x1800583f0`
- `0x180058488`
- `0x180058544`
- `0x180059840`
- `0x18005ba20`
- `0x18005d2e8`
- `0x180060e40`
- `0x180061d10`
- `0x180069484`
- `0x1800750be`

## callees

- `0x180002810`
- `0x18001962c`
- `0x180019cfc`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019723`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800196b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800196b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800196a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800196a1`

## string_xrefs

- `0x18001969a`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v8; // edx
  __int128 v9; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-48h]
  __int128 v11; // [rsp+50h] [rbp-38h]

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
    goto LABEL_15;
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
LABEL_15:
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v5, v2, v4, &v9) )
    {
      v8 = (int)pv[0];
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( !pv[1] )
        *(_DWORD *)(a1 + 184) = v8;
      tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v11);
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
0x18001962c  mov     [rsp+arg_10], rbx
0x180019631  push    rbp
0x180019632  push    rsi
0x180019633  push    rdi
0x180019634  sub     rsp, 70h
0x180019638  mov     rax, cs:__security_cookie
0x18001963f  xor     rax, rsp
0x180019642  mov     [rsp+88h+var_28], rax
0x180019647  mov     edi, edx
0x180019649  mov     rbx, rcx
0x18001964c  xorps   xmm0, xmm0
0x18001964f  movups  [rsp+88h+var_58], xmm0
0x180019654  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180019659  movups  [rsp+88h+var_38], xmm0
0x18001965e  cmp     dword ptr [rcx+0E8h], 0
0x180019665  jbe     short loc_18001966A
0x180019667  or      edi, 8
0x18001966a  mov     esi, [rcx+0B8h]
0x180019670  mov     rbp, [rcx+0F0h]
0x180019677  mov     qword ptr [rcx+0F0h], 0
0x180019682  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180019689  test    rax, rax
0x18001968c  jnz     short loc_1800196DE
0x18001968e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180019695  test    rax, rax
0x180019698  jnz     short loc_1800196AE
0x18001969a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800196a1  call    cs:__imp_GetModuleHandleW
0x1800196a7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800196ae  lea     rdx, aTestquerydata; "TestQueryData"
0x1800196b5  mov     rcx, rax; hModule
0x1800196b8  call    cs:__imp_GetProcAddress
0x1800196be  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800196c5  test    rax, rax
0x1800196c8  jnz     short loc_1800196DE
0x1800196ca  xorps   xmm0, xmm0
0x1800196cd  movups  [rsp+88h+var_58], xmm0
0x1800196d2  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800196d7  movups  [rsp+88h+var_38], xmm0
0x1800196dc  jmp     short loc_18001971E
0x1800196de  lea     r9, [rsp+88h+var_58]
0x1800196e3  mov     r8d, esi
0x1800196e6  mov     edx, edi
0x1800196e8  mov     rcx, rbp
0x1800196eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f0  test    eax, eax
0x1800196f2  jz      short loc_18001971E
0x1800196f4  mov     rdx, [rsp+88h+pv]
0x1800196f9  mov     rax, rdx
0x1800196fc  shr     rax, 20h
0x180019700  or      [rbx+40h], eax
0x180019703  cmp     [rsp+88h+pv+8], 0
0x180019709  jnz     short loc_180019711
0x18001970b  mov     [rbx+0B8h], edx
0x180019711  mov     rdx, qword ptr [rsp+88h+var_38]
0x180019716  mov     rcx, rbx
0x180019719  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18001971e  mov     rcx, [rsp+88h+pv+8]; pv
0x180019723  call    cs:__imp_CoTaskMemFree
0x180019729  nop
0x18001972a  mov     rcx, [rsp+88h+var_28]
0x18001972f  xor     rcx, rsp; StackCookie
0x180019732  call    __security_check_cookie
0x180019737  mov     rbx, [rsp+88h+arg_10]
0x18001973f  add     rsp, 70h
0x180019743  pop     rdi
0x180019744  pop     rsi
0x180019745  pop     rbp
0x180019746  retn
```
