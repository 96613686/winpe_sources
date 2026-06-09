# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x14005d6fc`
- end: `0x14005d7fc`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140052e08`
- `0x14005d6a8`

## callees

- `0x14000a2d4`
- `0x14000f7e0`
- `0x14005d6fc`
- `0x14005dd48`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005d76d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005d76d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d7d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d7d8`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
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
  if ( `TestQueryData'::`2'::s_pfnTestQueryData
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestQueryData"),
        (`TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress) != 0) )
  {
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
0x14005d6fc  mov     [rsp+arg_10], rbx
0x14005d701  push    rbp
0x14005d702  push    rsi
0x14005d703  push    rdi
0x14005d704  sub     rsp, 70h
0x14005d708  mov     rax, cs:__security_cookie
0x14005d70f  xor     rax, rsp
0x14005d712  mov     [rsp+88h+var_28], rax
0x14005d717  mov     edi, edx
0x14005d719  mov     rbx, rcx
0x14005d71c  xorps   xmm0, xmm0
0x14005d71f  movups  [rsp+88h+var_58], xmm0
0x14005d724  movups  xmmword ptr [rsp+88h+pv], xmm0
0x14005d729  movups  [rsp+88h+var_38], xmm0
0x14005d72e  cmp     dword ptr [rcx+0E8h], 0
0x14005d735  jbe     short loc_14005D73A
0x14005d737  or      edi, 8
0x14005d73a  mov     esi, [rcx+0B8h]
0x14005d740  mov     rbp, [rcx+0F0h]
0x14005d747  mov     qword ptr [rcx+0F0h], 0
0x14005d752  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x14005d759  test    rax, rax
0x14005d75c  jnz     short loc_14005D793
0x14005d75e  call    tip_details_GetKernelBaseModuleHandle
0x14005d763  mov     rcx, rax; hModule
0x14005d766  lea     rdx, aTestquerydata; "TestQueryData"
0x14005d76d  call    cs:__imp_GetProcAddress
0x14005d773  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x14005d77a  test    rax, rax
0x14005d77d  jnz     short loc_14005D793
0x14005d77f  xorps   xmm0, xmm0
0x14005d782  movups  [rsp+88h+var_58], xmm0
0x14005d787  movups  xmmword ptr [rsp+88h+pv], xmm0
0x14005d78c  movups  [rsp+88h+var_38], xmm0
0x14005d791  jmp     short loc_14005D7D3
0x14005d793  lea     r9, [rsp+88h+var_58]
0x14005d798  mov     r8d, esi
0x14005d79b  mov     edx, edi
0x14005d79d  mov     rcx, rbp
0x14005d7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d7a5  test    eax, eax
0x14005d7a7  jz      short loc_14005D7D3
0x14005d7a9  mov     rdx, [rsp+88h+pv]
0x14005d7ae  mov     rax, rdx
0x14005d7b1  shr     rax, 20h
0x14005d7b5  or      [rbx+40h], eax
0x14005d7b8  cmp     [rsp+88h+pv+8], 0
0x14005d7be  jnz     short loc_14005D7C6
0x14005d7c0  mov     [rbx+0B8h], edx
0x14005d7c6  mov     rdx, qword ptr [rsp+88h+var_38]
0x14005d7cb  mov     rcx, rbx
0x14005d7ce  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x14005d7d3  mov     rcx, [rsp+88h+pv+8]; pv
0x14005d7d8  call    cs:__imp_CoTaskMemFree
0x14005d7de  nop
0x14005d7df  mov     rcx, [rsp+88h+var_28]
0x14005d7e4  xor     rcx, rsp; StackCookie
0x14005d7e7  call    __security_check_cookie
0x14005d7ec  mov     rbx, [rsp+88h+arg_10]
0x14005d7f4  add     rsp, 70h
0x14005d7f8  pop     rdi
0x14005d7f9  pop     rsi
0x14005d7fa  pop     rbp
0x14005d7fb  retn
```
