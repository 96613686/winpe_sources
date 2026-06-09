# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180060408`
- end: `0x180060515`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005e7e0`
- `0x18005ed48`

## callees

- `0x180043a30`
- `0x180060408`
- `0x1800608c0`
- `0x180062328`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060479`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060479`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800604ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800604ea`

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
0x180060408  mov     [rsp+arg_10], rbx
0x18006040d  push    rbp
0x18006040e  push    rsi
0x18006040f  push    rdi
0x180060410  sub     rsp, 70h
0x180060414  mov     rax, cs:__security_cookie
0x18006041b  xor     rax, rsp
0x18006041e  mov     [rsp+88h+var_28], rax
0x180060423  mov     edi, edx
0x180060425  mov     rbx, rcx
0x180060428  xorps   xmm0, xmm0
0x18006042b  movups  [rsp+88h+var_58], xmm0
0x180060430  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180060435  movups  [rsp+88h+var_38], xmm0
0x18006043a  cmp     dword ptr [rcx+0E8h], 0
0x180060441  jbe     short loc_180060446
0x180060443  or      edi, 8
0x180060446  mov     esi, [rcx+0B8h]
0x18006044c  mov     rbp, [rcx+0F0h]
0x180060453  mov     qword ptr [rcx+0F0h], 0
0x18006045e  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180060465  test    rax, rax
0x180060468  jnz     short loc_1800604A5
0x18006046a  call    tip_details_GetKernelBaseModuleHandle
0x18006046f  mov     rcx, rax; hModule
0x180060472  lea     rdx, ProcName; "TestQueryData"
0x180060479  call    cs:__imp_GetProcAddress
0x180060480  nop     dword ptr [rax+rax+00h]
0x180060485  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18006048c  test    rax, rax
0x18006048f  jnz     short loc_1800604A5
0x180060491  xorps   xmm0, xmm0
0x180060494  movups  [rsp+88h+var_58], xmm0
0x180060499  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18006049e  movups  [rsp+88h+var_38], xmm0
0x1800604a3  jmp     short loc_1800604E5
0x1800604a5  lea     r9, [rsp+88h+var_58]
0x1800604aa  mov     r8d, esi
0x1800604ad  mov     edx, edi
0x1800604af  mov     rcx, rbp
0x1800604b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604b7  test    eax, eax
0x1800604b9  jz      short loc_1800604E5
0x1800604bb  mov     rdx, [rsp+88h+pv]
0x1800604c0  mov     rax, rdx
0x1800604c3  shr     rax, 20h
0x1800604c7  or      [rbx+40h], eax
0x1800604ca  cmp     [rsp+88h+pv+8], 0
0x1800604d0  jnz     short loc_1800604D8
0x1800604d2  mov     [rbx+0B8h], edx
0x1800604d8  mov     rdx, qword ptr [rsp+88h+var_38]
0x1800604dd  mov     rcx, rbx
0x1800604e0  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x1800604e5  mov     rcx, [rsp+88h+pv+8]; pv
0x1800604ea  call    cs:__imp_CoTaskMemFree
0x1800604f1  nop     dword ptr [rax+rax+00h]
0x1800604f6  nop
0x1800604f7  mov     rcx, [rsp+88h+var_28]
0x1800604fc  xor     rcx, rsp; StackCookie
0x1800604ff  call    __security_check_cookie
0x180060504  mov     rbx, [rsp+88h+arg_10]
0x18006050c  add     rsp, 70h
0x180060510  pop     rdi
0x180060511  pop     rsi
0x180060512  pop     rbp
0x180060513  retn
```
