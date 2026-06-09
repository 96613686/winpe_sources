# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18002a134`
- end: `0x18002a233`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `255`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800088e0`
- `0x18002a108`
- `0x18002af08`

## callees

- `0x180012550`
- `0x18002a134`
- `0x18002a934`
- `0x18002c3b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a1a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a1a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a210`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  bool v2; // zf
  unsigned int v3; // edi
  FARPROC ProcAddress; // rax
  unsigned int v6; // esi
  __int64 v7; // rbp
  HMODULE KernelBaseModuleHandle; // rax
  int v9; // edx
  __int128 v10; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-48h]
  __int128 v12; // [rsp+50h] [rbp-38h]

  v2 = *(_DWORD *)(a1 + 232) == 0;
  v10 = 0;
  v3 = a2;
  *(_OWORD *)pv = 0;
  v12 = 0;
  if ( !v2 )
    v3 = a2 | 8;
  ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  v6 = *(_DWORD *)(a1 + 184);
  v7 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  if ( ProcAddress
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestQueryData"),
        (`TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress) != 0) )
  {
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v7, v3, v6, &v10) )
    {
      v9 = (int)pv[0];
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( !pv[1] )
        *(_DWORD *)(a1 + 184) = v9;
      tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v12);
    }
  }
  else
  {
    v10 = 0;
    *(_OWORD *)pv = 0;
    v12 = 0;
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x18002a134  mov     [rsp+arg_10], rbx
0x18002a139  push    rbp
0x18002a13a  push    rsi
0x18002a13b  push    rdi
0x18002a13c  sub     rsp, 70h
0x18002a140  mov     rax, cs:__security_cookie
0x18002a147  xor     rax, rsp
0x18002a14a  mov     [rsp+88h+var_28], rax
0x18002a14f  cmp     dword ptr [rcx+0E8h], 0
0x18002a156  xorps   xmm0, xmm0
0x18002a159  movups  [rsp+88h+var_58], xmm0
0x18002a15e  mov     edi, edx
0x18002a160  mov     rbx, rcx
0x18002a163  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18002a168  movups  [rsp+88h+var_38], xmm0
0x18002a16d  jbe     short loc_18002A172
0x18002a16f  or      edi, 8
0x18002a172  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18002a179  mov     esi, [rcx+0B8h]
0x18002a17f  mov     rbp, [rcx+0F0h]
0x18002a186  mov     qword ptr [rcx+0F0h], 0
0x18002a191  test    rax, rax
0x18002a194  jnz     short loc_18002A1CB
0x18002a196  call    tip_details_GetKernelBaseModuleHandle
0x18002a19b  mov     rcx, rax; hModule
0x18002a19e  lea     rdx, aTestquerydata; "TestQueryData"
0x18002a1a5  call    cs:__imp_GetProcAddress
0x18002a1ab  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18002a1b2  test    rax, rax
0x18002a1b5  jnz     short loc_18002A1CB
0x18002a1b7  xorps   xmm0, xmm0
0x18002a1ba  movups  [rsp+88h+var_58], xmm0
0x18002a1bf  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18002a1c4  movups  [rsp+88h+var_38], xmm0
0x18002a1c9  jmp     short loc_18002A20B
0x18002a1cb  lea     r9, [rsp+88h+var_58]
0x18002a1d0  mov     r8d, esi
0x18002a1d3  mov     edx, edi
0x18002a1d5  mov     rcx, rbp
0x18002a1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1dd  test    eax, eax
0x18002a1df  jz      short loc_18002A20B
0x18002a1e1  mov     rdx, [rsp+88h+pv]
0x18002a1e6  mov     rax, rdx
0x18002a1e9  shr     rax, 20h
0x18002a1ed  or      [rbx+40h], eax
0x18002a1f0  cmp     [rsp+88h+pv+8], 0
0x18002a1f6  jnz     short loc_18002A1FE
0x18002a1f8  mov     [rbx+0B8h], edx
0x18002a1fe  mov     rdx, qword ptr [rsp+88h+var_38]
0x18002a203  mov     rcx, rbx
0x18002a206  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18002a20b  mov     rcx, [rsp+88h+pv+8]; pv
0x18002a210  call    cs:__imp_CoTaskMemFree
0x18002a216  mov     rcx, [rsp+88h+var_28]
0x18002a21b  xor     rcx, rsp; StackCookie
0x18002a21e  call    __security_check_cookie
0x18002a223  mov     rbx, [rsp+88h+arg_10]
0x18002a22b  add     rsp, 70h
0x18002a22f  pop     rdi
0x18002a230  pop     rsi
0x18002a231  pop     rbp
0x18002a232  retn
```
