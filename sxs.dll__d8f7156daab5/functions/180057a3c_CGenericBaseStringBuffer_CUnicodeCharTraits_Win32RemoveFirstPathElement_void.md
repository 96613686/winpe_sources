# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement(void)

- ea: `0x180057a3c`
- end: `0x180057b4b`
- name: `?Win32RemoveFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002ae38`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180057a3c`
- `0x180057b54`
- `0x180057bb8`
- `0x180057c04`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057aa6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057ac0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057afd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057aa6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057ac0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057afd`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement(__int64 a1)
{
  __int64 PathElement; // rax
  char **v3; // rcx
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-40h] BYREF
  int v7; // [rsp+28h] [rbp-38h] BYREF
  __int64 v8; // [rsp+30h] [rbp-30h]
  __int64 *v9; // [rsp+38h] [rbp-28h]
  __int64 v10; // [rsp+40h] [rbp-20h]
  int v11; // [rsp+48h] [rbp-18h]
  int *v12; // [rsp+50h] [rbp-10h]

  v6 = 0;
  v9 = &`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement'::`2'::__stc;
  v7 = 1;
  v12 = &v6;
  v8 = 0;
  v10 = 544438355;
  v11 = 1134;
  CFrame::BaseEnter((CFrame *)&v7);
  if ( *(_DWORD *)(a1 + 8) )
  {
    SetLastError(0x54Fu);
    *v12 = 0;
  }
  else
  {
    SetLastError(0);
    PathElement = CGenericBaseStringBuffer<CUnicodeCharTraits>::CchWithoutFirstPathElement(a1);
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Right(a1, PathElement) )
    {
      SetLastError(0);
      if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::RemoveLeadingPathSeparators(a1) )
      {
        v6 = 1;
        goto LABEL_9;
      }
      v3 = `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement'::`37'::__callsite;
    }
    else
    {
      v3 = `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement'::`24'::__callsite;
    }
    *v12 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v3);
  }
LABEL_9:
  v4 = v6;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v7);
  return v4;
}

```

## disassembly

```asm
0x180057a3c  mov     [rsp-8+arg_8], rbx
0x180057a41  push    rbp
0x180057a42  mov     rbp, rsp
0x180057a45  sub     rsp, 60h
0x180057a49  mov     rax, cs:__security_cookie
0x180057a50  xor     rax, rsp
0x180057a53  mov     [rbp+var_8], rax
0x180057a57  lea     rax, ?__stc@?1??Win32RemoveFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement(void)'::`2'::__stc
0x180057a5e  mov     [rbp+var_40], 0
0x180057a65  mov     [rbp+var_28], rax
0x180057a69  mov     rbx, rcx
0x180057a6c  lea     rax, [rbp+var_40]
0x180057a70  mov     [rbp+var_38], 1
0x180057a77  lea     rcx, [rbp+var_38]; this
0x180057a7b  mov     [rbp+var_10], rax
0x180057a7f  mov     [rbp+var_30], 0
0x180057a87  mov     [rbp+var_20], 20737853h
0x180057a8f  mov     [rbp+var_18], 46Eh
0x180057a96  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180057a9b  cmp     dword ptr [rbx+8], 0
0x180057a9f  jz      short loc_180057ABE
0x180057aa1  mov     ecx, 54Fh; dwErrCode
0x180057aa6  call    cs:__imp_SetLastError
0x180057aad  nop     dword ptr [rax+rax+00h]
0x180057ab2  mov     rax, [rbp+var_10]
0x180057ab6  mov     dword ptr [rax], 0
0x180057abc  jmp     short loc_180057B25
0x180057abe  xor     ecx, ecx; dwErrCode
0x180057ac0  call    cs:__imp_SetLastError
0x180057ac7  nop     dword ptr [rax+rax+00h]
0x180057acc  mov     rcx, rbx
0x180057acf  call    ?CchWithoutFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBA_KXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::CchWithoutFirstPathElement(void)
0x180057ad4  mov     rdx, rax
0x180057ad7  mov     rcx, rbx
0x180057ada  call    ?Right@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Right(unsigned __int64)
0x180057adf  test    eax, eax
0x180057ae1  jnz     short loc_180057AFB
0x180057ae3  lea     rcx, ?__callsite@?BI@??Win32RemoveFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x180057aea  mov     rax, [rbp+var_10]
0x180057aee  mov     dword ptr [rax], 0
0x180057af4  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180057af9  jmp     short loc_180057B25
0x180057afb  xor     ecx, ecx; dwErrCode
0x180057afd  call    cs:__imp_SetLastError
0x180057b04  nop     dword ptr [rax+rax+00h]
0x180057b09  mov     rcx, rbx
0x180057b0c  call    ?RemoveLeadingPathSeparators@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::RemoveLeadingPathSeparators(void)
0x180057b11  test    eax, eax
0x180057b13  jnz     short loc_180057B1E
0x180057b15  lea     rcx, ?__callsite@?CF@??Win32RemoveFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ@4U_CALL_SITE_INFO@@B; _CALL_SITE_INFO const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement(void)'::`37'::__callsite
0x180057b1c  jmp     short loc_180057AEA
0x180057b1e  mov     [rbp+var_40], 1
0x180057b25  mov     ebx, [rbp+var_40]
0x180057b28  lea     rcx, [rbp+var_38]; this
0x180057b2c  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180057b31  mov     eax, ebx
0x180057b33  mov     rcx, [rbp+var_8]
0x180057b37  xor     rcx, rsp; StackCookie
0x180057b3a  call    __security_check_cookie
0x180057b3f  mov     rbx, [rsp+60h+arg_8]
0x180057b44  add     rsp, 60h
0x180057b48  pop     rbp
0x180057b49  retn
```
