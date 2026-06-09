# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x14001c818`
- end: `0x14001c933`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000cd58`
- `0x14000ecbc`

## callees

- `0x140005530`
- `0x14001c818`
- `0x14001ce4c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001c8a4`
- `KERNEL32!GetProcAddress` at `0x14001c8a4`
- `KERNEL32!GetModuleHandleW` at `0x14001c88d`
- `KERNEL32!GetModuleHandleW` at `0x14001c88d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c90f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001c90f`

## string_xrefs

- `0x14001c886`: `kernelbase.dll`

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
0x14001c818  mov     [rsp+arg_10], rbx
0x14001c81d  push    rbp
0x14001c81e  push    rsi
0x14001c81f  push    rdi
0x14001c820  sub     rsp, 70h
0x14001c824  mov     rax, cs:__security_cookie
0x14001c82b  xor     rax, rsp
0x14001c82e  mov     [rsp+88h+var_28], rax
0x14001c833  mov     edi, edx
0x14001c835  mov     rbx, rcx
0x14001c838  xorps   xmm0, xmm0
0x14001c83b  movups  [rsp+88h+var_58], xmm0
0x14001c840  movups  xmmword ptr [rsp+88h+pv], xmm0
0x14001c845  movups  [rsp+88h+var_38], xmm0
0x14001c84a  cmp     dword ptr [rcx+0E8h], 0
0x14001c851  jbe     short loc_14001C856
0x14001c853  or      edi, 8
0x14001c856  mov     esi, [rcx+0B8h]
0x14001c85c  mov     rbp, [rcx+0F0h]
0x14001c863  mov     qword ptr [rcx+0F0h], 0
0x14001c86e  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x14001c875  test    rax, rax
0x14001c878  jnz     short loc_14001C8CA
0x14001c87a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14001c881  test    rax, rax
0x14001c884  jnz     short loc_14001C89A
0x14001c886  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001c88d  call    cs:__imp_GetModuleHandleW
0x14001c893  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14001c89a  lea     rdx, aTestquerydata; "TestQueryData"
0x14001c8a1  mov     rcx, rax; hModule
0x14001c8a4  call    cs:__imp_GetProcAddress
0x14001c8aa  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x14001c8b1  test    rax, rax
0x14001c8b4  jnz     short loc_14001C8CA
0x14001c8b6  xorps   xmm0, xmm0
0x14001c8b9  movups  [rsp+88h+var_58], xmm0
0x14001c8be  movups  xmmword ptr [rsp+88h+pv], xmm0
0x14001c8c3  movups  [rsp+88h+var_38], xmm0
0x14001c8c8  jmp     short loc_14001C90A
0x14001c8ca  lea     r9, [rsp+88h+var_58]
0x14001c8cf  mov     r8d, esi
0x14001c8d2  mov     edx, edi
0x14001c8d4  mov     rcx, rbp
0x14001c8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8dc  test    eax, eax
0x14001c8de  jz      short loc_14001C90A
0x14001c8e0  mov     rdx, [rsp+88h+pv]
0x14001c8e5  mov     rax, rdx
0x14001c8e8  shr     rax, 20h
0x14001c8ec  or      [rbx+40h], eax
0x14001c8ef  cmp     [rsp+88h+pv+8], 0
0x14001c8f5  jnz     short loc_14001C8FD
0x14001c8f7  mov     [rbx+0B8h], edx
0x14001c8fd  mov     rdx, qword ptr [rsp+88h+var_38]
0x14001c902  mov     rcx, rbx
0x14001c905  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x14001c90a  mov     rcx, [rsp+88h+pv+8]; pv
0x14001c90f  call    cs:__imp_CoTaskMemFree
0x14001c915  nop
0x14001c916  mov     rcx, [rsp+88h+var_28]
0x14001c91b  xor     rcx, rsp; StackCookie
0x14001c91e  call    __security_check_cookie
0x14001c923  mov     rbx, [rsp+88h+arg_10]
0x14001c92b  add     rsp, 70h
0x14001c92f  pop     rdi
0x14001c930  pop     rsi
0x14001c931  pop     rbp
0x14001c932  retn
```
