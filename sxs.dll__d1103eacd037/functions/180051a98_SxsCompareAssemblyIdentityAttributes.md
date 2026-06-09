# SxsCompareAssemblyIdentityAttributes

- ea: `0x180051a98`
- end: `0x180051d55`
- name: `SxsCompareAssemblyIdentityAttributes`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c700`

## callees

- `0x18000df40`
- `0x180051a98`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180051b8c`
- `ntdll!RtlCompareUnicodeString` at `0x180051c74`
- `ntdll!RtlCompareUnicodeString` at `0x180051cd7`
- `ntdll!RtlCompareUnicodeString` at `0x180051b8c`
- `ntdll!RtlCompareUnicodeString` at `0x180051c74`
- `ntdll!RtlCompareUnicodeString` at `0x180051cd7`
- `ntdll!RtlPopFrame` at `0x180051bcd`
- `ntdll!RtlPopFrame` at `0x180051bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051d3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051baa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051c0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051baa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051c0b`

## pseudocode

```c
__int64 __fastcall SxsCompareAssemblyIdentityAttributes(int a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v5; // edi
  const char *v9; // rcx
  int v10; // r14d
  WCHAR *v11; // rax
  WCHAR *v12; // rax
  LONG v13; // eax
  bool v14; // sf
  WCHAR *v16; // rax
  WCHAR *v17; // rax
  LONG v18; // eax
  WCHAR *v19; // rax
  WCHAR *v20; // rax
  LONG v21; // eax
  DWORD LastError; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-60h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-50h] BYREF
  int v25; // [rsp+40h] [rbp-40h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+48h] [rbp-38h] BYREF
  __int64 v27; // [rsp+60h] [rbp-20h]
  int v28; // [rsp+68h] [rbp-18h]
  int *v29; // [rsp+70h] [rbp-10h]

  v25 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800710D0;
  Frame.Previous = 0;
  v5 = 1;
  v29 = &v25;
  Frame.Flags = 1;
  v27 = 544438355;
  v28 = 952;
  CFrame::BaseEnter((CFrame *)&Frame);
  v10 = 7;
  if ( a1 )
    v10 = a1;
  if ( (v10 & 0xFFFFFFF8) != 0 )
  {
    v28 = 962;
    goto LABEL_15;
  }
  if ( !a2 )
  {
    v28 = 963;
    goto LABEL_15;
  }
  if ( !a3 )
  {
    v28 = 964;
LABEL_15:
    FusionpTraceParameterCheck(v9);
    SetLastError(0x57u);
    v5 = 0;
    *v29 = 0;
    goto LABEL_12;
  }
  if ( !a4 )
  {
    v28 = 965;
    goto LABEL_15;
  }
  if ( (v10 & 1) != 0 )
  {
    v11 = *(WCHAR **)(a2 + 32);
    *(_QWORD *)&String1.Length = 0;
    String1.Buffer = v11;
    String1.Length = 2 * *(_WORD *)(a2 + 8);
    String1.MaximumLength = String1.Length;
    v12 = *(WCHAR **)(a3 + 32);
    *(_QWORD *)&String2.Length = 0;
    String2.Buffer = v12;
    String2.Length = 2 * *(_WORD *)(a3 + 8);
    String2.MaximumLength = String2.Length;
    v13 = RtlCompareUnicodeString(&String1, &String2, 0);
    v14 = v13 < 0;
    if ( v13 )
      goto LABEL_9;
  }
  if ( (v10 & 2) != 0 )
  {
    v16 = *(WCHAR **)(a2 + 40);
    *(_QWORD *)&String2.Length = 0;
    String2.Buffer = v16;
    String2.Length = 2 * *(_WORD *)(a2 + 16);
    String2.MaximumLength = String2.Length;
    v17 = *(WCHAR **)(a3 + 40);
    *(_QWORD *)&String1.Length = 0;
    String1.Buffer = v17;
    String1.Length = 2 * *(_WORD *)(a3 + 16);
    String1.MaximumLength = String1.Length;
    v18 = RtlCompareUnicodeString(&String2, &String1, 0);
    v14 = v18 < 0;
    if ( v18 )
      goto LABEL_9;
  }
  if ( (v10 & 4) == 0 )
    goto LABEL_22;
  v19 = *(WCHAR **)(a2 + 48);
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = v19;
  String2.Length = 2 * *(_WORD *)(a2 + 24);
  String2.MaximumLength = String2.Length;
  v20 = *(WCHAR **)(a3 + 48);
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = v20;
  String1.Length = 2 * *(_WORD *)(a3 + 24);
  String1.MaximumLength = String1.Length;
  v21 = RtlCompareUnicodeString(&String2, &String1, 1u);
  v14 = v21 < 0;
  if ( v21 )
  {
LABEL_9:
    if ( v14 )
      *a4 = 1;
    else
      *a4 = 3;
  }
  else
  {
LABEL_22:
    *a4 = 2;
  }
  SetLastError(0);
  *v29 = 1;
LABEL_12:
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v5 )
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
0x180051a98  push    rbp
0x180051a9a  push    rbx
0x180051a9b  push    rsi
0x180051a9c  push    rdi
0x180051a9d  push    r13
0x180051a9f  push    r14
0x180051aa1  push    r15
0x180051aa3  mov     rbp, rsp
0x180051aa6  sub     rsp, 80h
0x180051aad  mov     rax, cs:__security_cookie
0x180051ab4  xor     rax, rsp
0x180051ab7  mov     [rbp+var_8], rax
0x180051abb  lea     rax, qword_1800710D0
0x180051ac2  mov     [rbp+var_40], 0
0x180051ac9  mov     [rbp+Frame.Context], rax
0x180051acd  mov     ebx, ecx
0x180051acf  lea     rax, [rbp+var_40]
0x180051ad3  mov     [rbp+Frame.Previous], 0
0x180051adb  mov     edi, 1
0x180051ae0  mov     [rbp+var_10], rax
0x180051ae4  lea     rcx, [rbp+Frame]; this
0x180051ae8  mov     [rbp+Frame.Flags], edi
0x180051aeb  mov     rsi, r9
0x180051aee  mov     [rbp+var_20], 20737853h
0x180051af6  mov     r13, r8
0x180051af9  mov     [rbp+var_18], 3B8h
0x180051b00  mov     r15, rdx
0x180051b03  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180051b08  test    ebx, ebx
0x180051b0a  lea     r14d, [rdi+6]
0x180051b0e  cmovnz  r14d, ebx
0x180051b12  test    r14d, 0FFFFFFF8h
0x180051b19  jnz     loc_180051D08
0x180051b1f  test    r15, r15
0x180051b22  jz      loc_180051D14
0x180051b28  test    r13, r13
0x180051b2b  jz      loc_180051BFA
0x180051b31  test    rsi, rsi
0x180051b34  jz      loc_180051CFC
0x180051b3a  test    dil, r14b
0x180051b3d  jz      loc_180051C25
0x180051b43  mov     rax, [r15+20h]
0x180051b47  lea     rdx, [rbp+String2]; String2
0x180051b4b  xorps   xmm0, xmm0
0x180051b4e  lea     rcx, [rbp+String1]; String1
0x180051b52  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180051b56  mov     [rbp+String1.Buffer], rax
0x180051b5a  xor     r8d, r8d; CaseInsensitive
0x180051b5d  movzx   eax, word ptr [r15+8]
0x180051b62  xorps   xmm1, xmm1
0x180051b65  add     ax, ax
0x180051b68  mov     [rbp+String1.Length], ax
0x180051b6c  mov     [rbp+String1.MaximumLength], ax
0x180051b70  mov     rax, [r13+20h]
0x180051b74  movups  xmmword ptr [rbp+String2.Length], xmm1
0x180051b78  mov     [rbp+String2.Buffer], rax
0x180051b7c  movzx   eax, word ptr [r13+8]
0x180051b81  add     ax, ax
0x180051b84  mov     [rbp+String2.Length], ax
0x180051b88  mov     [rbp+String2.MaximumLength], ax
0x180051b8c  call    cs:__imp_RtlCompareUnicodeString
0x180051b93  nop     dword ptr [rax+rax+00h]
0x180051b98  test    eax, eax
0x180051b9a  jz      loc_180051C25
0x180051ba0  jns     loc_180051CED
0x180051ba6  mov     [rsi], edi
0x180051ba8  xor     ecx, ecx; dwErrCode
0x180051baa  call    cs:__imp_SetLastError
0x180051bb1  nop     dword ptr [rax+rax+00h]
0x180051bb6  mov     rax, [rbp+var_10]
0x180051bba  mov     [rax], edi
0x180051bbc  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180051bc3  jnz     loc_180051D2B
0x180051bc9  lea     rcx, [rbp+Frame]; Frame
0x180051bcd  call    cs:__imp_RtlPopFrame
0x180051bd4  nop     dword ptr [rax+rax+00h]
0x180051bd9  mov     eax, edi
0x180051bdb  mov     rcx, [rbp+var_8]
0x180051bdf  xor     rcx, rsp; StackCookie
0x180051be2  call    __security_check_cookie
0x180051be7  add     rsp, 80h
0x180051bee  pop     r15
0x180051bf0  pop     r14
0x180051bf2  pop     r13
0x180051bf4  pop     rdi
0x180051bf5  pop     rsi
0x180051bf6  pop     rbx
0x180051bf7  pop     rbp
0x180051bf8  retn
0x180051bfa  mov     [rbp+var_18], 3C4h
0x180051c01  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180051c06  mov     ecx, 57h ; 'W'; dwErrCode
0x180051c0b  call    cs:__imp_SetLastError
0x180051c12  nop     dword ptr [rax+rax+00h]
0x180051c17  mov     rax, [rbp+var_10]
0x180051c1b  xor     edi, edi
0x180051c1d  mov     dword ptr [rax], 0
0x180051c23  jmp     short loc_180051BBC
0x180051c25  test    r14b, 2
0x180051c29  jz      short loc_180051C88
0x180051c2b  mov     rax, [r15+28h]
0x180051c2f  lea     rdx, [rbp+String1]; String2
0x180051c33  xorps   xmm0, xmm0
0x180051c36  lea     rcx, [rbp+String2]; String1
0x180051c3a  movups  xmmword ptr [rbp+String2.Length], xmm0
0x180051c3e  mov     [rbp+String2.Buffer], rax
0x180051c42  xor     r8d, r8d; CaseInsensitive
0x180051c45  movzx   eax, word ptr [r15+10h]
0x180051c4a  xorps   xmm1, xmm1
0x180051c4d  add     ax, ax
0x180051c50  mov     [rbp+String2.Length], ax
0x180051c54  mov     [rbp+String2.MaximumLength], ax
0x180051c58  mov     rax, [r13+28h]
0x180051c5c  movups  xmmword ptr [rbp+String1.Length], xmm1
0x180051c60  mov     [rbp+String1.Buffer], rax
0x180051c64  movzx   eax, word ptr [r13+10h]
0x180051c69  add     ax, ax
0x180051c6c  mov     [rbp+String1.Length], ax
0x180051c70  mov     [rbp+String1.MaximumLength], ax
0x180051c74  call    cs:__imp_RtlCompareUnicodeString
0x180051c7b  nop     dword ptr [rax+rax+00h]
0x180051c80  test    eax, eax
0x180051c82  jnz     loc_180051BA0
0x180051c88  test    r14b, 4
0x180051c8c  jz      short loc_180051CF1
0x180051c8e  mov     rax, [r15+30h]
0x180051c92  lea     rdx, [rbp+String1]; String2
0x180051c96  xorps   xmm0, xmm0
0x180051c99  lea     rcx, [rbp+String2]; String1
0x180051c9d  movups  xmmword ptr [rbp+String2.Length], xmm0
0x180051ca1  mov     [rbp+String2.Buffer], rax
0x180051ca5  mov     r8b, dil; CaseInsensitive
0x180051ca8  movzx   eax, word ptr [r15+18h]
0x180051cad  xorps   xmm1, xmm1
0x180051cb0  add     ax, ax
0x180051cb3  mov     [rbp+String2.Length], ax
0x180051cb7  mov     [rbp+String2.MaximumLength], ax
0x180051cbb  mov     rax, [r13+30h]
0x180051cbf  movups  xmmword ptr [rbp+String1.Length], xmm1
0x180051cc3  mov     [rbp+String1.Buffer], rax
0x180051cc7  movzx   eax, word ptr [r13+18h]
0x180051ccc  add     ax, ax
0x180051ccf  mov     [rbp+String1.Length], ax
0x180051cd3  mov     [rbp+String1.MaximumLength], ax
0x180051cd7  call    cs:__imp_RtlCompareUnicodeString
0x180051cde  nop     dword ptr [rax+rax+00h]
0x180051ce3  test    eax, eax
0x180051ce5  jnz     loc_180051BA0
0x180051ceb  jmp     short loc_180051CF1
0x180051ced  test    eax, eax
0x180051cef  jnz     short loc_180051D20
0x180051cf1  mov     dword ptr [rsi], 2
0x180051cf7  jmp     loc_180051BA8
0x180051cfc  mov     [rbp+var_18], 3C5h
0x180051d03  jmp     loc_180051C01
0x180051d08  mov     [rbp+var_18], 3C2h
0x180051d0f  jmp     loc_180051C01
0x180051d14  mov     [rbp+var_18], 3C3h
0x180051d1b  jmp     loc_180051C01
0x180051d20  mov     dword ptr [rsi], 3
0x180051d26  jmp     loc_180051BA8
0x180051d2b  test    edi, edi
0x180051d2d  jz      short loc_180051D3B
0x180051d2f  xor     ecx, ecx; char *
0x180051d31  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180051d36  jmp     loc_180051BC9
0x180051d3b  call    cs:__imp_GetLastError
0x180051d42  nop     dword ptr [rax+rax+00h]
0x180051d47  mov     ecx, eax; unsigned int
0x180051d49  xor     edx, edx; Format
0x180051d4b  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180051d50  jmp     loc_180051BC9
```
