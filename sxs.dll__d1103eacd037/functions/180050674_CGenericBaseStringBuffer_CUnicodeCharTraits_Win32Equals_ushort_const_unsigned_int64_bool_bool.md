# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Equals(ushort const *,unsigned __int64,bool &,bool)

- ea: `0x180050674`
- end: `0x18005079c`
- name: `?Win32Equals@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEA_N_N@Z`
- size: `296`
- prototype: `__int64 __fastcall(int, int, int, int, BOOLEAN CaseInsensitive)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a70`
- `0x18005caa0`
- `0x18005cb7c`

## callees

- `0x18000df40`
- `0x180050674`
- `0x180067548`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18005072e`
- `ntdll!RtlCompareUnicodeString` at `0x18005072e`
- `ntdll!RtlPopFrame` at `0x180050767`
- `ntdll!RtlPopFrame` at `0x180050767`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800506e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050744`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800506e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050744`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Equals(
        __int64 a1,
        WCHAR *a2,
        __int16 a3,
        bool *a4,
        BOOLEAN CaseInsensitive)
{
  WCHAR *v9; // rax
  UNICODE_STRING String2; // [rsp+20h] [rbp-60h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-50h] BYREF
  int v13; // [rsp+40h] [rbp-40h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+48h] [rbp-38h] BYREF
  __int64 v15; // [rsp+60h] [rbp-20h]
  int v16; // [rsp+68h] [rbp-18h]
  int *v17; // [rsp+70h] [rbp-10h]

  v13 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Equals'::`2'::__stc;
  Frame.Flags = 1;
  v17 = &v13;
  Frame.Previous = 0;
  v15 = 544438355;
  v16 = 654;
  CFrame::BaseEnter((CFrame *)&Frame);
  SetLastError(0);
  v9 = *(WCHAR **)(a1 + 16);
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = v9;
  LOWORD(v9) = *(_WORD *)(a1 + 32);
  *(&String2.MaximumLength + 2) = 0;
  String2.Buffer = a2;
  *(_QWORD *)&String1.Length = (unsigned __int16)(2 * (_WORD)v9);
  *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * (_WORD)v9);
  String2.Length = 2 * a3;
  *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * a3);
  *a4 = RtlCompareUnicodeString(&String1, &String2, CaseInsensitive) == 0;
  SetLastError(0);
  *v17 = 1;
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&Frame);
  return 1;
}

```

## disassembly

```asm
0x180050674  push    rbp
0x180050676  push    rbx
0x180050677  push    rsi
0x180050678  push    rdi
0x180050679  push    r14
0x18005067b  mov     rbp, rsp
0x18005067e  sub     rsp, 80h
0x180050685  mov     rax, cs:__security_cookie
0x18005068c  xor     rax, rsp
0x18005068f  mov     [rbp+var_8], rax
0x180050693  lea     rax, ?__stc@?1??Win32Equals@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEA_N_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Equals(ushort const *,unsigned __int64,bool &,bool)'::`2'::__stc
0x18005069a  mov     [rbp+var_40], 0
0x1800506a1  mov     [rbp+Frame.Context], rax
0x1800506a5  mov     rbx, rcx
0x1800506a8  lea     rax, [rbp+var_40]
0x1800506ac  mov     [rbp+Frame.Flags], 1
0x1800506b3  lea     rcx, [rbp+Frame]; this
0x1800506b7  mov     [rbp+var_10], rax
0x1800506bb  mov     r14, r9
0x1800506be  mov     [rbp+Frame.Previous], 0
0x1800506c6  mov     rsi, r8
0x1800506c9  mov     [rbp+var_20], 20737853h
0x1800506d1  mov     rdi, rdx
0x1800506d4  mov     [rbp+var_18], 28Eh
0x1800506db  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800506e0  xor     ecx, ecx; dwErrCode
0x1800506e2  call    cs:__imp_SetLastError
0x1800506e9  nop     dword ptr [rax+rax+00h]
0x1800506ee  mov     rax, [rbx+10h]
0x1800506f2  lea     rdx, [rbp+String2]; String2
0x1800506f6  mov     r8b, [rbp+CaseInsensitive]; CaseInsensitive
0x1800506fa  lea     rcx, [rbp+String1]; String1
0x1800506fe  xorps   xmm0, xmm0
0x180050701  xorps   xmm1, xmm1
0x180050704  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180050708  mov     [rbp+String1.Buffer], rax
0x18005070c  add     si, si
0x18005070f  movzx   eax, word ptr [rbx+20h]
0x180050713  movups  xmmword ptr [rbp+String2.Length], xmm1
0x180050717  add     ax, ax
0x18005071a  mov     [rbp+String2.Buffer], rdi
0x18005071e  mov     [rbp+String1.Length], ax
0x180050722  mov     [rbp+String1.MaximumLength], ax
0x180050726  mov     [rbp+String2.Length], si
0x18005072a  mov     [rbp+String2.MaximumLength], si
0x18005072e  call    cs:__imp_RtlCompareUnicodeString
0x180050735  nop     dword ptr [rax+rax+00h]
0x18005073a  test    eax, eax
0x18005073c  setz    al
0x18005073f  xor     ecx, ecx; dwErrCode
0x180050741  mov     [r14], al
0x180050744  call    cs:__imp_SetLastError
0x18005074b  nop     dword ptr [rax+rax+00h]
0x180050750  mov     rcx, [rbp+var_10]
0x180050754  mov     dword ptr [rcx], 1
0x18005075a  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180050761  jnz     short loc_180050793
0x180050763  lea     rcx, [rbp+Frame]; Frame
0x180050767  call    cs:__imp_RtlPopFrame
0x18005076e  nop     dword ptr [rax+rax+00h]
0x180050773  mov     eax, 1
0x180050778  mov     rcx, [rbp+var_8]
0x18005077c  xor     rcx, rsp; StackCookie
0x18005077f  call    __security_check_cookie
0x180050784  add     rsp, 80h
0x18005078b  pop     r14
0x18005078d  pop     rdi
0x18005078e  pop     rsi
0x18005078f  pop     rbx
0x180050790  pop     rbp
0x180050791  retn
0x180050793  xor     ecx, ecx; char *
0x180050795  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18005079a  jmp     short loc_180050763
```
