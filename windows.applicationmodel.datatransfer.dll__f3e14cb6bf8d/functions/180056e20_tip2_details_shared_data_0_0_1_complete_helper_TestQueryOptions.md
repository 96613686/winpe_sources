# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x180056e20`
- end: `0x180056f3b`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e5a0`
- `0x18000e874`
- `0x18000eb1c`
- `0x18000edc0`
- `0x18000f09c`
- `0x18000f340`
- `0x18000f5e8`
- `0x180016c04`

## callees

- `0x180002ad0`
- `0x180056e20`
- `0x1800573ac`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056eac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056eac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180056e95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180056e95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056f17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056f17`

## string_xrefs

- `0x180056e8e`: `kernelbase.dll`

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
0x180056e20  mov     [rsp+arg_10], rbx
0x180056e25  push    rbp
0x180056e26  push    rsi
0x180056e27  push    rdi
0x180056e28  sub     rsp, 70h
0x180056e2c  mov     rax, cs:__security_cookie
0x180056e33  xor     rax, rsp
0x180056e36  mov     [rsp+88h+var_28], rax
0x180056e3b  mov     edi, edx
0x180056e3d  mov     rbx, rcx
0x180056e40  xorps   xmm0, xmm0
0x180056e43  movups  [rsp+88h+var_58], xmm0
0x180056e48  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180056e4d  movups  [rsp+88h+var_38], xmm0
0x180056e52  cmp     dword ptr [rcx+0E8h], 0
0x180056e59  jbe     short loc_180056E5E
0x180056e5b  or      edi, 8
0x180056e5e  mov     esi, [rcx+0B8h]
0x180056e64  mov     rbp, [rcx+0F0h]
0x180056e6b  mov     qword ptr [rcx+0F0h], 0
0x180056e76  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180056e7d  test    rax, rax
0x180056e80  jnz     short loc_180056ED2
0x180056e82  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180056e89  test    rax, rax
0x180056e8c  jnz     short loc_180056EA2
0x180056e8e  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180056e95  call    cs:__imp_GetModuleHandleW
0x180056e9b  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180056ea2  lea     rdx, aTestquerydata; "TestQueryData"
0x180056ea9  mov     rcx, rax; hModule
0x180056eac  call    cs:__imp_GetProcAddress
0x180056eb2  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180056eb9  test    rax, rax
0x180056ebc  jnz     short loc_180056ED2
0x180056ebe  xorps   xmm0, xmm0
0x180056ec1  movups  [rsp+88h+var_58], xmm0
0x180056ec6  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180056ecb  movups  [rsp+88h+var_38], xmm0
0x180056ed0  jmp     short loc_180056F12
0x180056ed2  lea     r9, [rsp+88h+var_58]
0x180056ed7  mov     r8d, esi
0x180056eda  mov     edx, edi
0x180056edc  mov     rcx, rbp
0x180056edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ee4  test    eax, eax
0x180056ee6  jz      short loc_180056F12
0x180056ee8  mov     rdx, [rsp+88h+pv]
0x180056eed  mov     rax, rdx
0x180056ef0  shr     rax, 20h
0x180056ef4  or      [rbx+40h], eax
0x180056ef7  cmp     [rsp+88h+pv+8], 0
0x180056efd  jnz     short loc_180056F05
0x180056eff  mov     [rbx+0B8h], edx
0x180056f05  mov     rdx, qword ptr [rsp+88h+var_38]
0x180056f0a  mov     rcx, rbx
0x180056f0d  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x180056f12  mov     rcx, [rsp+88h+pv+8]; pv
0x180056f17  call    cs:__imp_CoTaskMemFree
0x180056f1d  nop
0x180056f1e  mov     rcx, [rsp+88h+var_28]
0x180056f23  xor     rcx, rsp; StackCookie
0x180056f26  call    __security_check_cookie
0x180056f2b  mov     rbx, [rsp+88h+arg_10]
0x180056f33  add     rsp, 70h
0x180056f37  pop     rdi
0x180056f38  pop     rsi
0x180056f39  pop     rbp
0x180056f3a  retn
```
