# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)

- ea: `0x18001d6f0`
- end: `0x18001d981`
- name: `?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ`
- size: `657`
- prototype: ``
- caller_count: `10`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001c320`
- `0x1800278b0`
- `0x18002a7b4`
- `0x18002df40`
- `0x180053760`
- `0x180059f28`
- `0x18005ae60`
- `0x18005d888`
- `0x18005f8cc`
- `0x180063d20`

## callees

- `0x18000dffc`
- `0x18001c2c8`
- `0x18001d6f0`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18001d7cf`
- `ntdll!RtlPopFrame` at `0x18001d7cf`
- `ntdll!RtlPushFrame` at `0x18001d74b`
- `ntdll!RtlPushFrame` at `0x18001d74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d967`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d7fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d90e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d7fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d90e`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(__int64 a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rsi
  __int16 v4; // dx
  unsigned int v5; // ebx
  __int64 v7; // rcx
  unsigned __int64 v8; // rbp
  unsigned int (__fastcall **v9)(__int64, __int64, void **); // rax
  const void *v10; // rdx
  void **v11; // r14
  char *v12; // r15
  unsigned __int64 v13; // rdi
  size_t v14; // rdi
  void *v15; // rdi
  DWORD LastError; // eax
  void *v17; // [rsp+20h] [rbp-78h] BYREF
  int v18; // [rsp+28h] [rbp-70h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+30h] [rbp-68h] BYREF
  __int64 v20; // [rsp+48h] [rbp-50h]
  int v21; // [rsp+50h] [rbp-48h]
  int *v22; // [rsp+58h] [rbp-40h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator'::`2'::__stc;
  v20 = 544438355;
  Frame.Previous = 0;
  v21 = 857;
  v22 = &v18;
  v18 = 0;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( *(_DWORD *)(a1 + 8) )
  {
    SetLastError(0x54Fu);
    *v22 = 0;
  }
  else
  {
    v2 = *(_QWORD *)(a1 + 32);
    v3 = (_QWORD *)(a1 + 16);
    if ( v2 )
    {
      v4 = *(_WORD *)(*v3 + 2 * v2 - 2);
      if ( v4 == 92 || v4 == 47 )
        goto LABEL_6;
    }
    SetLastError(0);
    v7 = *(_QWORD *)(a1 + 32);
    v8 = v7 + 2;
    if ( (unsigned __int64)(v7 + 2) <= *(_QWORD *)(a1 + 24) )
    {
LABEL_11:
      *(_WORD *)(*v3 + 2 * v7) = 92;
      ++*(_QWORD *)(a1 + 32);
      *(_WORD *)(*v3 + 2LL * *(_QWORD *)(a1 + 32)) = 0;
LABEL_6:
      v18 = 1;
      goto LABEL_7;
    }
    v9 = *(unsigned int (__fastcall ***)(__int64, __int64, void **))a1;
    v17 = 0;
    if ( (*v9)(a1, v7 + 2, &v17) )
    {
      if ( v8 )
      {
        v10 = *(const void **)(a1 + 16);
        v11 = (void **)(a1 + 16);
        v12 = (char *)v17;
        if ( v10 )
        {
          v13 = *(_QWORD *)(a1 + 32);
          if ( v13 >= v8 )
            v13 = v8 - 1;
          v14 = 2 * v13;
          memcpy_0(v17, v10, v14);
          *(_WORD *)&v12[v14] = 0;
        }
        else
        {
          *(_WORD *)v17 = 0;
        }
      }
      else
      {
        v11 = (void **)(a1 + 16);
      }
      v15 = *v11;
      if ( *v11 && v15 != (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
        (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)a1 + 8LL))(a1, v15);
      v7 = *(_QWORD *)(a1 + 32);
      *v11 = v17;
      *(_QWORD *)(a1 + 24) = v8;
      goto LABEL_11;
    }
    *v22 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator'::`27'::__callsite);
  }
LABEL_7:
  v5 = v18;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v22 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v5;
}

```

## disassembly

```asm
0x18001d6f0  mov     r11, rsp
0x18001d6f3  push    rbx
0x18001d6f4  sub     rsp, 90h
0x18001d6fb  mov     rax, cs:__security_cookie
0x18001d702  xor     rax, rsp
0x18001d705  mov     [rsp+98h+var_38], rax
0x18001d70a  mov     [rsp+98h+Frame.Flags], 1
0x18001d712  lea     rax, ?__stc@?1??Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)'::`2'::__stc
0x18001d719  mov     [r11-58h], rax
0x18001d71d  mov     rbx, rcx
0x18001d720  mov     [r11-18h], r12
0x18001d724  lea     rax, [r11-70h]
0x18001d728  xor     r12d, r12d
0x18001d72b  mov     qword ptr [r11-50h], 20737853h
0x18001d733  mov     [r11-60h], r12
0x18001d737  lea     rcx, [r11-68h]; Frame
0x18001d73b  mov     [rsp+98h+var_48], 359h
0x18001d743  mov     [r11-40h], rax
0x18001d747  mov     [r11-70h], r12d
0x18001d74b  call    cs:__imp_RtlPushFrame
0x18001d752  nop     dword ptr [rax+rax+00h]
0x18001d757  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x18001d75e  jnz     loc_18001D8F9
0x18001d764  cmp     [rbx+8], r12d
0x18001d768  jnz     loc_18001D909
0x18001d76e  mov     rcx, [rbx+20h]
0x18001d772  mov     [rsp+98h+arg_8], rbp
0x18001d77a  mov     [rsp+98h+arg_10], rsi
0x18001d782  lea     rsi, [rbx+10h]
0x18001d786  test    rcx, rcx
0x18001d789  jz      short loc_18001D7FA
0x18001d78b  mov     rax, [rsi]
0x18001d78e  movzx   edx, word ptr [rax+rcx*2-2]
0x18001d793  cmp     dx, 5Ch ; '\'
0x18001d797  jnz     short loc_18001D7F4
0x18001d799  mov     [rsp+98h+var_70], 1
0x18001d7a1  mov     rbp, [rsp+98h+arg_8]
0x18001d7a9  mov     rsi, [rsp+98h+arg_10]
0x18001d7b1  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18001d7b8  mov     ebx, [rsp+98h+var_70]
0x18001d7bc  mov     r12, [rsp+98h+var_18]
0x18001d7c4  jnz     loc_18001D951
0x18001d7ca  lea     rcx, [rsp+98h+Frame]; Frame
0x18001d7cf  call    cs:__imp_RtlPopFrame
0x18001d7d6  nop     dword ptr [rax+rax+00h]
0x18001d7db  mov     eax, ebx
0x18001d7dd  mov     rcx, [rsp+98h+var_38]
0x18001d7e2  xor     rcx, rsp; StackCookie
0x18001d7e5  call    __security_check_cookie
0x18001d7ea  add     rsp, 90h
0x18001d7f1  pop     rbx
0x18001d7f2  retn
0x18001d7f4  cmp     dx, 2Fh ; '/'
0x18001d7f8  jz      short loc_18001D799
0x18001d7fa  xor     ecx, ecx; dwErrCode
0x18001d7fc  call    cs:__imp_SetLastError
0x18001d803  nop     dword ptr [rax+rax+00h]
0x18001d808  mov     rcx, [rbx+20h]
0x18001d80c  lea     rbp, [rcx+2]
0x18001d810  cmp     rbp, [rbx+18h]
0x18001d814  ja      short loc_18001D834
0x18001d816  mov     rax, [rsi]
0x18001d819  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18001d81f  inc     qword ptr [rbx+20h]
0x18001d823  mov     rdx, [rbx+20h]
0x18001d827  mov     rcx, [rsi]
0x18001d82a  mov     [rcx+rdx*2], r12w
0x18001d82f  jmp     loc_18001D799
0x18001d834  mov     rax, [rbx]
0x18001d837  lea     r8, [rsp+98h+var_78]
0x18001d83c  mov     rdx, rbp
0x18001d83f  mov     [rsp+98h+var_78], r12
0x18001d844  mov     rcx, rbx
0x18001d847  mov     rax, [rax]
0x18001d84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d84f  test    eax, eax
0x18001d851  jz      loc_18001D938
0x18001d857  mov     [rsp+98h+var_10], rdi
0x18001d85f  mov     [rsp+98h+var_20], r14
0x18001d864  mov     [rsp+98h+var_28], r15
0x18001d869  test    rbp, rbp
0x18001d86c  jz      loc_18001D930
0x18001d872  mov     rdx, [rbx+10h]; Src
0x18001d876  lea     r14, [rbx+10h]
0x18001d87a  mov     r15, [rsp+98h+var_78]
0x18001d87f  test    rdx, rdx
0x18001d882  jz      short loc_18001D903
0x18001d884  mov     rdi, [rbx+20h]
0x18001d888  cmp     rdi, rbp
0x18001d88b  jnb     loc_18001D927
0x18001d891  add     rdi, rdi
0x18001d894  mov     rcx, r15; void *
0x18001d897  mov     r8, rdi; Size
0x18001d89a  call    memcpy_0
0x18001d89f  mov     [rdi+r15], r12w
0x18001d8a4  mov     rdi, [r14]
0x18001d8a7  mov     r15, [rsp+98h+var_28]
0x18001d8ac  test    rdi, rdi
0x18001d8af  jz      short loc_18001D8D7
0x18001d8b1  mov     rax, [rbx]
0x18001d8b4  mov     rcx, rbx
0x18001d8b7  mov     rax, [rax+10h]
0x18001d8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8c0  cmp     rdi, rax
0x18001d8c3  jz      short loc_18001D8D7
0x18001d8c5  mov     rax, [rbx]
0x18001d8c8  mov     rdx, rdi
0x18001d8cb  mov     rcx, rbx
0x18001d8ce  mov     rax, [rax+8]
0x18001d8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8d7  mov     rax, [rsp+98h+var_78]
0x18001d8dc  mov     rcx, [rbx+20h]
0x18001d8e0  mov     rdi, [rsp+98h+var_10]
0x18001d8e8  mov     [r14], rax
0x18001d8eb  mov     r14, [rsp+98h+var_20]
0x18001d8f0  mov     [rbx+18h], rbp
0x18001d8f4  jmp     loc_18001D816
0x18001d8f9  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18001d8fe  jmp     loc_18001D764
0x18001d903  mov     [r15], r12w
0x18001d907  jmp     short loc_18001D8A4
0x18001d909  mov     ecx, 54Fh; dwErrCode
0x18001d90e  call    cs:__imp_SetLastError
0x18001d915  nop     dword ptr [rax+rax+00h]
0x18001d91a  mov     rax, [rsp+98h+var_40]
0x18001d91f  mov     [rax], r12d
0x18001d922  jmp     loc_18001D7B1
0x18001d927  lea     rdi, [rbp-1]
0x18001d92b  jmp     loc_18001D891
0x18001d930  mov     r14, rsi
0x18001d933  jmp     loc_18001D8A4
0x18001d938  mov     rax, [rsp+98h+var_40]
0x18001d93d  lea     rcx, ?__callsite@?BL@??Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x18001d944  mov     [rax], r12d
0x18001d947  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18001d94c  jmp     loc_18001D7A1
0x18001d951  mov     rax, [rsp+98h+var_40]
0x18001d956  cmp     dword ptr [rax], 0
0x18001d959  jz      short loc_18001D967
0x18001d95b  xor     ecx, ecx; char *
0x18001d95d  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18001d962  jmp     loc_18001D7CA
0x18001d967  call    cs:__imp_GetLastError
0x18001d96e  nop     dword ptr [rax+rax+00h]
0x18001d973  mov     ecx, eax; unsigned int
0x18001d975  xor     edx, edx; Format
0x18001d977  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18001d97c  jmp     loc_18001D7CA
```
