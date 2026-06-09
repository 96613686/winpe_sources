# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x180031cac`
- end: `0x180031dda`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002fc48`
- `0x180030ef0`

## callees

- `0x180002280`
- `0x180031cac`
- `0x180031f0c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031d21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031daf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031daf`

## string_xrefs

- `0x180031d1a`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::complete_helper(__int64 a1, unsigned int a2)
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
      tip2::details::shared_data<0,0,1>::evaluate_and_report(a1, v11);
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
0x180031cac  mov     [rsp+arg_10], rbx
0x180031cb1  push    rbp
0x180031cb2  push    rsi
0x180031cb3  push    rdi
0x180031cb4  sub     rsp, 70h
0x180031cb8  mov     rax, cs:__security_cookie
0x180031cbf  xor     rax, rsp
0x180031cc2  mov     [rsp+88h+var_28], rax
0x180031cc7  mov     edi, edx
0x180031cc9  mov     rbx, rcx
0x180031ccc  xorps   xmm0, xmm0
0x180031ccf  movups  [rsp+88h+var_58], xmm0
0x180031cd4  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180031cd9  movups  [rsp+88h+var_38], xmm0
0x180031cde  cmp     dword ptr [rcx+0E8h], 0
0x180031ce5  jbe     short loc_180031CEA
0x180031ce7  or      edi, 8
0x180031cea  mov     esi, [rcx+0B8h]
0x180031cf0  mov     rbp, [rcx+0F0h]
0x180031cf7  mov     qword ptr [rcx+0F0h], 0
0x180031d02  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180031d09  test    rax, rax
0x180031d0c  jnz     short loc_180031D6A
0x180031d0e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180031d15  test    rax, rax
0x180031d18  jnz     short loc_180031D34
0x180031d1a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180031d21  call    cs:__imp_GetModuleHandleW
0x180031d28  nop     dword ptr [rax+rax+00h]
0x180031d2d  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180031d34  lea     rdx, aTestquerydata; "TestQueryData"
0x180031d3b  mov     rcx, rax; hModule
0x180031d3e  call    cs:__imp_GetProcAddress
0x180031d45  nop     dword ptr [rax+rax+00h]
0x180031d4a  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180031d51  test    rax, rax
0x180031d54  jnz     short loc_180031D6A
0x180031d56  xorps   xmm0, xmm0
0x180031d59  movups  [rsp+88h+var_58], xmm0
0x180031d5e  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180031d63  movups  [rsp+88h+var_38], xmm0
0x180031d68  jmp     short loc_180031DAA
0x180031d6a  lea     r9, [rsp+88h+var_58]
0x180031d6f  mov     r8d, esi
0x180031d72  mov     edx, edi
0x180031d74  mov     rcx, rbp
0x180031d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d7c  test    eax, eax
0x180031d7e  jz      short loc_180031DAA
0x180031d80  mov     rdx, [rsp+88h+pv]
0x180031d85  mov     rax, rdx
0x180031d88  shr     rax, 20h
0x180031d8c  or      [rbx+40h], eax
0x180031d8f  cmp     [rsp+88h+pv+8], 0
0x180031d95  jnz     short loc_180031D9D
0x180031d97  mov     [rbx+0B8h], edx
0x180031d9d  mov     rdx, qword ptr [rsp+88h+var_38]
0x180031da2  mov     rcx, rbx
0x180031da5  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x180031daa  mov     rcx, [rsp+88h+pv+8]; pv
0x180031daf  call    cs:__imp_CoTaskMemFree
0x180031db6  nop     dword ptr [rax+rax+00h]
0x180031dbb  nop
0x180031dbc  mov     rcx, [rsp+88h+var_28]
0x180031dc1  xor     rcx, rsp; StackCookie
0x180031dc4  call    __security_check_cookie
0x180031dc9  mov     rbx, [rsp+88h+arg_10]
0x180031dd1  add     rsp, 70h
0x180031dd5  pop     rdi
0x180031dd6  pop     rsi
0x180031dd7  pop     rbp
0x180031dd8  retn
```
