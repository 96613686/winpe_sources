# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(ushort const *,unsigned __int64,StringComparisonResult &,bool)

- ea: `0x18004f0f8`
- end: `0x18004f21a`
- name: `?Win32Compare@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEAW4StringComparisonResult@@_N@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ed50`

## callees

- `0x18000df40`
- `0x18001c270`
- `0x18004f0f8`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18004f1b1`
- `ntdll!RtlCompareUnicodeString` at `0x18004f1b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f166`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f1ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f166`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f1ca`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(
        __int64 a1,
        WCHAR *a2,
        __int16 a3,
        int *a4)
{
  WCHAR *v8; // rax
  LONG v9; // eax
  int v11; // edx
  UNICODE_STRING String2; // [rsp+20h] [rbp-60h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-50h] BYREF
  int v14; // [rsp+40h] [rbp-40h] BYREF
  int v15; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+50h] [rbp-30h]
  __int64 *v17; // [rsp+58h] [rbp-28h]
  __int64 v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int *v20; // [rsp+70h] [rbp-10h]

  v14 = 0;
  v17 = &`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare'::`2'::__stc;
  v15 = 1;
  v20 = &v14;
  v16 = 0;
  v18 = 544438355;
  v19 = 644;
  CFrame::BaseEnter((CFrame *)&v15);
  SetLastError(0);
  v8 = *(WCHAR **)(a1 + 16);
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = v8;
  LOWORD(v8) = *(_WORD *)(a1 + 32);
  *(&String2.MaximumLength + 2) = 0;
  String2.Buffer = a2;
  *(_QWORD *)&String1.Length = (unsigned __int16)(2 * (_WORD)v8);
  *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * (_WORD)v8);
  String2.Length = 2 * a3;
  *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * a3);
  v9 = RtlCompareUnicodeString(&String1, &String2, 1u);
  if ( v9 )
  {
    v11 = 2;
    if ( v9 < 0 )
      v11 = 0;
    *a4 = v11;
  }
  else
  {
    *a4 = 1;
  }
  SetLastError(0);
  *v20 = 1;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v15);
  return 1;
}

```

## disassembly

```asm
0x18004f0f8  push    rbp
0x18004f0fa  push    rbx
0x18004f0fb  push    rsi
0x18004f0fc  push    rdi
0x18004f0fd  push    r14
0x18004f0ff  mov     rbp, rsp
0x18004f102  sub     rsp, 80h
0x18004f109  mov     rax, cs:__security_cookie
0x18004f110  xor     rax, rsp
0x18004f113  mov     [rbp+var_8], rax
0x18004f117  lea     rax, ?__stc@?1??Win32Compare@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEAW4StringComparisonResult@@_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Compare(ushort const *,unsigned __int64,StringComparisonResult &,bool)'::`2'::__stc
0x18004f11e  mov     [rbp+var_40], 0
0x18004f125  mov     [rbp+var_28], rax
0x18004f129  mov     rbx, rcx
0x18004f12c  lea     rax, [rbp+var_40]
0x18004f130  mov     [rbp+var_38], 1
0x18004f137  lea     rcx, [rbp+var_38]; this
0x18004f13b  mov     [rbp+var_10], rax
0x18004f13f  mov     r14, r9
0x18004f142  mov     [rbp+var_30], 0
0x18004f14a  mov     rsi, r8
0x18004f14d  mov     [rbp+var_20], 20737853h
0x18004f155  mov     rdi, rdx
0x18004f158  mov     [rbp+var_18], 284h
0x18004f15f  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004f164  xor     ecx, ecx; dwErrCode
0x18004f166  call    cs:__imp_SetLastError
0x18004f16d  nop     dword ptr [rax+rax+00h]
0x18004f172  mov     rax, [rbx+10h]
0x18004f176  lea     rdx, [rbp+String2]; String2
0x18004f17a  xorps   xmm0, xmm0
0x18004f17d  lea     rcx, [rbp+String1]; String1
0x18004f181  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18004f185  mov     [rbp+String1.Buffer], rax
0x18004f189  add     si, si
0x18004f18c  movzx   eax, word ptr [rbx+20h]
0x18004f190  xorps   xmm1, xmm1
0x18004f193  movups  xmmword ptr [rbp+String2.Length], xmm1
0x18004f197  add     ax, ax
0x18004f19a  mov     [rbp+String2.Buffer], rdi
0x18004f19e  mov     r8b, 1; CaseInsensitive
0x18004f1a1  mov     [rbp+String1.Length], ax
0x18004f1a5  mov     [rbp+String1.MaximumLength], ax
0x18004f1a9  mov     [rbp+String2.Length], si
0x18004f1ad  mov     [rbp+String2.MaximumLength], si
0x18004f1b1  call    cs:__imp_RtlCompareUnicodeString
0x18004f1b8  nop     dword ptr [rax+rax+00h]
0x18004f1bd  test    eax, eax
0x18004f1bf  jnz     short loc_18004F209
0x18004f1c1  mov     dword ptr [r14], 1
0x18004f1c8  xor     ecx, ecx; dwErrCode
0x18004f1ca  call    cs:__imp_SetLastError
0x18004f1d1  nop     dword ptr [rax+rax+00h]
0x18004f1d6  mov     rcx, [rbp+var_10]
0x18004f1da  mov     dword ptr [rcx], 1
0x18004f1e0  lea     rcx, [rbp+var_38]; this
0x18004f1e4  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18004f1e9  mov     eax, 1
0x18004f1ee  mov     rcx, [rbp+var_8]
0x18004f1f2  xor     rcx, rsp; StackCookie
0x18004f1f5  call    __security_check_cookie
0x18004f1fa  add     rsp, 80h
0x18004f201  pop     r14
0x18004f203  pop     rdi
0x18004f204  pop     rsi
0x18004f205  pop     rbx
0x18004f206  pop     rbp
0x18004f207  retn
0x18004f209  xor     ecx, ecx
0x18004f20b  mov     edx, 2
0x18004f210  test    eax, eax
0x18004f212  cmovs   edx, ecx
0x18004f215  mov     [r14], edx
0x18004f218  jmp     short loc_18004F1C8
```
