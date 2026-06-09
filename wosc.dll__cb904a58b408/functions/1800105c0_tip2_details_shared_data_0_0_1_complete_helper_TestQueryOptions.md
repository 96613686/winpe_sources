# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x1800105c0`
- end: `0x1800106c0`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800106c8`
- `0x180011434`

## callees

- `0x180003110`
- `0x1800105c0`
- `0x1800109dc`
- `0x180012cf8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010631`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001069c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001069c`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::complete_helper(__int64 a1, unsigned int a2)
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
0x1800105c0  mov     [rsp+arg_10], rbx
0x1800105c5  push    rbp
0x1800105c6  push    rsi
0x1800105c7  push    rdi
0x1800105c8  sub     rsp, 70h
0x1800105cc  mov     rax, cs:__security_cookie
0x1800105d3  xor     rax, rsp
0x1800105d6  mov     [rsp+88h+var_28], rax
0x1800105db  mov     edi, edx
0x1800105dd  mov     rbx, rcx
0x1800105e0  xorps   xmm0, xmm0
0x1800105e3  movups  [rsp+88h+var_58], xmm0
0x1800105e8  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800105ed  movups  [rsp+88h+var_38], xmm0
0x1800105f2  cmp     dword ptr [rcx+0E8h], 0
0x1800105f9  jbe     short loc_1800105FE
0x1800105fb  or      edi, 8
0x1800105fe  mov     esi, [rcx+0B8h]
0x180010604  mov     rbp, [rcx+0F0h]
0x18001060b  mov     qword ptr [rcx+0F0h], 0
0x180010616  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001061d  test    rax, rax
0x180010620  jnz     short loc_180010657
0x180010622  call    tip_details_GetKernelBaseModuleHandle
0x180010627  mov     rcx, rax; hModule
0x18001062a  lea     rdx, aTestquerydata; "TestQueryData"
0x180010631  call    cs:__imp_GetProcAddress
0x180010637  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001063e  test    rax, rax
0x180010641  jnz     short loc_180010657
0x180010643  xorps   xmm0, xmm0
0x180010646  movups  [rsp+88h+var_58], xmm0
0x18001064b  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180010650  movups  [rsp+88h+var_38], xmm0
0x180010655  jmp     short loc_180010697
0x180010657  lea     r9, [rsp+88h+var_58]
0x18001065c  mov     r8d, esi
0x18001065f  mov     edx, edi
0x180010661  mov     rcx, rbp
0x180010664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010669  test    eax, eax
0x18001066b  jz      short loc_180010697
0x18001066d  mov     rdx, [rsp+88h+pv]
0x180010672  mov     rax, rdx
0x180010675  shr     rax, 20h
0x180010679  or      [rbx+40h], eax
0x18001067c  cmp     [rsp+88h+pv+8], 0
0x180010682  jnz     short loc_18001068A
0x180010684  mov     [rbx+0B8h], edx
0x18001068a  mov     rdx, qword ptr [rsp+88h+var_38]
0x18001068f  mov     rcx, rbx
0x180010692  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x180010697  mov     rcx, [rsp+88h+pv+8]; pv
0x18001069c  call    cs:__imp_CoTaskMemFree
0x1800106a2  nop
0x1800106a3  mov     rcx, [rsp+88h+var_28]
0x1800106a8  xor     rcx, rsp; StackCookie
0x1800106ab  call    __security_check_cookie
0x1800106b0  mov     rbx, [rsp+88h+arg_10]
0x1800106b8  add     rsp, 70h
0x1800106bc  pop     rdi
0x1800106bd  pop     rsi
0x1800106be  pop     rbp
0x1800106bf  retn
```
