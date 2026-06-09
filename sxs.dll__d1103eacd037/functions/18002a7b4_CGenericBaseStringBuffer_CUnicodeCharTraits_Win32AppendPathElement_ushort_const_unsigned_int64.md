# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement(ushort const *,unsigned __int64)

- ea: `0x18002a7b4`
- end: `0x18002aa39`
- name: `?Win32AppendPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z`
- size: `645`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001c320`
- `0x18002a2b4`
- `0x18002aa40`
- `0x18005d888`

## callees

- `0x18000dffc`
- `0x18001c2c8`
- `0x18001d6f0`
- `0x18002a7b4`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18002a8e1`
- `ntdll!RtlPopFrame` at `0x18002a8e1`
- `ntdll!RtlPushFrame` at `0x18002a818`
- `ntdll!RtlPushFrame` at `0x18002a818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a83b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a859`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a919`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a83b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a859`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a919`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement(
        __int64 a1,
        const void *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v6; // r15
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  _WORD *v11; // rsi
  unsigned int v12; // ebx
  unsigned int (__fastcall **v14)(__int64, __int64, void **); // rax
  __int64 v15; // rdx
  const void *v16; // rdx
  char *v17; // r12
  unsigned __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rbx
  char **v21; // rcx
  DWORD LastError; // eax
  void *v23; // [rsp+20h] [rbp-50h] BYREF
  int v24; // [rsp+28h] [rbp-48h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+30h] [rbp-40h] BYREF
  __int64 v26; // [rsp+48h] [rbp-28h]
  int v27; // [rsp+50h] [rbp-20h]
  int *v28; // [rsp+58h] [rbp-18h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement'::`2'::__stc;
  v26 = 544438355;
  v28 = &v24;
  v24 = 0;
  Frame.Previous = 0;
  v27 = 884;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( *(_DWORD *)(a1 + 8) )
  {
    SetLastError(0x54Fu);
    *v28 = 0;
  }
  else
  {
    SetLastError(0);
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(a1) )
    {
      SetLastError(0);
      v6 = a3 + 1;
      if ( a3 + 1 <= 1 )
      {
LABEL_13:
        v24 = 1;
        goto LABEL_14;
      }
      v7 = *(_QWORD *)(a1 + 24);
      v8 = v6 + *(_QWORD *)(a1 + 32);
      if ( v8 <= v7 )
      {
LABEL_7:
        v9 = *(_QWORD *)(a1 + 32);
        v10 = v7 - v9;
        if ( v10 )
        {
          v11 = (_WORD *)(*(_QWORD *)(a1 + 16) + 2 * v9);
          if ( a2 )
          {
            if ( a3 >= v10 )
              a3 = v10 - 1;
            memcpy_0(v11, a2, 2 * a3);
            v11[a3] = 0;
          }
          else
          {
            *v11 = 0;
          }
        }
        *(_QWORD *)(a1 + 32) += v6 - 1;
        goto LABEL_13;
      }
      v14 = *(unsigned int (__fastcall ***)(__int64, __int64, void **))a1;
      v15 = v6 + *(_QWORD *)(a1 + 32);
      v23 = 0;
      if ( (*v14)(a1, v15, &v23) )
      {
        if ( v8 )
        {
          v16 = *(const void **)(a1 + 16);
          v17 = (char *)v23;
          if ( v16 )
          {
            v18 = v8 - 1;
            if ( *(_QWORD *)(a1 + 32) < v8 )
              v18 = *(_QWORD *)(a1 + 32);
            v19 = 2 * v18;
            memcpy_0(v23, v16, 2 * v18);
            *(_WORD *)&v17[v19] = 0;
          }
          else
          {
            *(_WORD *)v23 = 0;
          }
        }
        v20 = *(_QWORD *)(a1 + 16);
        if ( v20 && v20 != (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, v20);
        v7 = v8;
        *(_QWORD *)(a1 + 16) = v23;
        *(_QWORD *)(a1 + 24) = v8;
        goto LABEL_7;
      }
      v21 = `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement'::`37'::__callsite;
    }
    else
    {
      v21 = `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement'::`24'::__callsite;
    }
    *v28 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v21);
  }
LABEL_14:
  v12 = v24;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v28 )
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
  return v12;
}

```

## disassembly

```asm
0x18002a7b4  mov     [rsp-38h+arg_18], rbx
0x18002a7b9  push    rbp
0x18002a7ba  push    rsi
0x18002a7bb  push    rdi
0x18002a7bc  push    r12
0x18002a7be  push    r13
0x18002a7c0  push    r14
0x18002a7c2  push    r15
0x18002a7c4  mov     rbp, rsp
0x18002a7c7  sub     rsp, 70h
0x18002a7cb  mov     rax, cs:__security_cookie
0x18002a7d2  xor     rax, rsp
0x18002a7d5  mov     [rbp+var_10], rax
0x18002a7d9  lea     rax, ?__stc@?1??Win32AppendPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement(ushort const *,unsigned __int64)'::`2'::__stc
0x18002a7e0  mov     [rbp+Frame.Flags], 1
0x18002a7e7  mov     [rbp+Frame.Context], rax
0x18002a7eb  mov     rdi, rcx
0x18002a7ee  lea     rax, [rbp+var_48]
0x18002a7f2  mov     [rbp+var_28], 20737853h
0x18002a7fa  xor     ebx, ebx
0x18002a7fc  mov     [rbp+var_18], rax
0x18002a800  lea     rcx, [rbp+Frame]; Frame
0x18002a804  mov     [rbp+var_48], ebx
0x18002a807  mov     r14, r8
0x18002a80a  mov     [rbp+Frame.Previous], rbx
0x18002a80e  mov     r13, rdx
0x18002a811  mov     [rbp+var_20], 374h
0x18002a818  call    cs:__imp_RtlPushFrame
0x18002a81f  nop     dword ptr [rax+rax+00h]
0x18002a824  cmp     cs:g_FusionEnterExitTracingEnabled, bl
0x18002a82a  jnz     loc_18002A9C8
0x18002a830  cmp     [rdi+8], ebx
0x18002a833  jnz     loc_18002A914
0x18002a839  xor     ecx, ecx; dwErrCode
0x18002a83b  call    cs:__imp_SetLastError
0x18002a842  nop     dword ptr [rax+rax+00h]
0x18002a847  mov     rcx, rdi
0x18002a84a  call    ?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)
0x18002a84f  test    eax, eax
0x18002a851  jz      loc_18002A9E1
0x18002a857  xor     ecx, ecx; dwErrCode
0x18002a859  call    cs:__imp_SetLastError
0x18002a860  nop     dword ptr [rax+rax+00h]
0x18002a865  lea     r15, [r14+1]
0x18002a869  cmp     r15, 1
0x18002a86d  jbe     short loc_18002A8C6
0x18002a86f  mov     rsi, [rdi+20h]
0x18002a873  mov     rcx, [rdi+18h]
0x18002a877  add     rsi, r15
0x18002a87a  cmp     rsi, rcx
0x18002a87d  ja      loc_18002A92D
0x18002a883  mov     rdx, [rdi+20h]
0x18002a887  sub     rcx, rdx
0x18002a88a  jz      short loc_18002A8BE
0x18002a88c  mov     rax, [rdi+10h]
0x18002a890  lea     rsi, [rax+rdx*2]
0x18002a894  test    r13, r13
0x18002a897  jz      loc_18002A9D2
0x18002a89d  cmp     r14, rcx
0x18002a8a0  jnb     loc_18002AA01
0x18002a8a6  lea     rbx, [r14+r14]
0x18002a8aa  mov     rdx, r13; Src
0x18002a8ad  mov     r8, rbx; Size
0x18002a8b0  mov     rcx, rsi; void *
0x18002a8b3  call    memcpy_0
0x18002a8b8  xor     eax, eax
0x18002a8ba  mov     [rsi+rbx], ax
0x18002a8be  lea     rax, [r15-1]
0x18002a8c2  add     [rdi+20h], rax
0x18002a8c6  mov     [rbp+var_48], 1
0x18002a8cd  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18002a8d4  mov     ebx, [rbp+var_48]
0x18002a8d7  jnz     loc_18002AA0A
0x18002a8dd  lea     rcx, [rbp+Frame]; Frame
0x18002a8e1  call    cs:__imp_RtlPopFrame
0x18002a8e8  nop     dword ptr [rax+rax+00h]
0x18002a8ed  mov     eax, ebx
0x18002a8ef  mov     rcx, [rbp+var_10]
0x18002a8f3  xor     rcx, rsp; StackCookie
0x18002a8f6  call    __security_check_cookie
0x18002a8fb  mov     rbx, [rsp+70h+arg_18]
0x18002a903  add     rsp, 70h
0x18002a907  pop     r15
0x18002a909  pop     r14
0x18002a90b  pop     r13
0x18002a90d  pop     r12
0x18002a90f  pop     rdi
0x18002a910  pop     rsi
0x18002a911  pop     rbp
0x18002a912  retn
0x18002a914  mov     ecx, 54Fh; dwErrCode
0x18002a919  call    cs:__imp_SetLastError
0x18002a920  nop     dword ptr [rax+rax+00h]
0x18002a925  mov     rax, [rbp+var_18]
0x18002a929  mov     [rax], ebx
0x18002a92b  jmp     short loc_18002A8CD
0x18002a92d  mov     rax, [rdi]
0x18002a930  lea     r8, [rbp+var_50]
0x18002a934  mov     rdx, rsi
0x18002a937  mov     [rbp+var_50], rbx
0x18002a93b  mov     rcx, rdi
0x18002a93e  mov     rax, [rax]
0x18002a941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a946  test    eax, eax
0x18002a948  jz      loc_18002A9EA
0x18002a94e  test    rsi, rsi
0x18002a951  jz      short loc_18002A983
0x18002a953  mov     rdx, [rdi+10h]; Src
0x18002a957  mov     r12, [rbp+var_50]
0x18002a95b  test    rdx, rdx
0x18002a95e  jz      short loc_18002A9DA
0x18002a960  cmp     [rdi+20h], rsi
0x18002a964  lea     rax, [rsi-1]
0x18002a968  mov     rcx, r12; void *
0x18002a96b  cmovb   rax, [rdi+20h]
0x18002a970  lea     rbx, [rax+rax]
0x18002a974  mov     r8, rbx; Size
0x18002a977  call    memcpy_0
0x18002a97c  xor     eax, eax
0x18002a97e  mov     [rbx+r12], ax
0x18002a983  mov     rbx, [rdi+10h]
0x18002a987  test    rbx, rbx
0x18002a98a  jz      short loc_18002A9B2
0x18002a98c  mov     rax, [rdi]
0x18002a98f  mov     rcx, rdi
0x18002a992  mov     rax, [rax+10h]
0x18002a996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a99b  cmp     rbx, rax
0x18002a99e  jz      short loc_18002A9B2
0x18002a9a0  mov     rax, [rdi]
0x18002a9a3  mov     rdx, rbx
0x18002a9a6  mov     rcx, rdi
0x18002a9a9  mov     rax, [rax+8]
0x18002a9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9b2  mov     rax, [rbp+var_50]
0x18002a9b6  mov     rcx, rsi
0x18002a9b9  mov     [rdi+10h], rax
0x18002a9bd  xor     ebx, ebx
0x18002a9bf  mov     [rdi+18h], rsi
0x18002a9c3  jmp     loc_18002A883
0x18002a9c8  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18002a9cd  jmp     loc_18002A830
0x18002a9d2  mov     [rsi], bx
0x18002a9d5  jmp     loc_18002A8BE
0x18002a9da  mov     [r12], bx
0x18002a9df  jmp     short loc_18002A983
0x18002a9e1  lea     rcx, ?__callsite@?BI@??Win32AppendPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z@4U_CALL_SITE_INFO@@B; _CALL_SITE_INFO const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement(ushort const *,unsigned __int64)'::`24'::__callsite
0x18002a9e8  jmp     short loc_18002A9F1
0x18002a9ea  lea     rcx, ?__callsite@?CF@??Win32AppendPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x18002a9f1  mov     rax, [rbp+var_18]
0x18002a9f5  mov     [rax], ebx
0x18002a9f7  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002a9fc  jmp     loc_18002A8CD
0x18002aa01  lea     r14, [rcx-1]
0x18002aa05  jmp     loc_18002A8A6
0x18002aa0a  mov     rax, [rbp+var_18]
0x18002aa0e  cmp     dword ptr [rax], 0
0x18002aa11  jz      short loc_18002AA1F
0x18002aa13  xor     ecx, ecx; char *
0x18002aa15  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18002aa1a  jmp     loc_18002A8DD
0x18002aa1f  call    cs:__imp_GetLastError
0x18002aa26  nop     dword ptr [rax+rax+00h]
0x18002aa2b  mov     ecx, eax; unsigned int
0x18002aa2d  xor     edx, edx; Format
0x18002aa2f  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18002aa34  jmp     loc_18002A8DD
```
