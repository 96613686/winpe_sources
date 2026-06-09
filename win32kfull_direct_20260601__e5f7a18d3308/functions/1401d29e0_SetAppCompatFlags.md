# SetAppCompatFlags

- ea: `0x1401d29e0`
- end: `0x1401d3169`
- name: `SetAppCompatFlags`
- size: `1929`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1400beeb0`
- `0x1401d29e0`
- `0x1401d3170`
- `0x1401d3378`
- `0x1402938dc`
- `0x1402a6b30`
- `0x1402d4510`
- `0x140342fa0`
- `0x140343200`
- `0x1403d31c8`
- `0x1403d3204`

## import_xrefs

- `ntoskrnl!PsGetThreadTeb` at `0x1401d2b49`
- `ntoskrnl!PsGetThreadTeb` at `0x1401d2b49`
- `ntoskrnl!PsGetThreadProcess` at `0x1401d2a24`
- `ntoskrnl!PsGetThreadProcess` at `0x1401d2a24`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1401d3144`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1401d3144`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401d2f72`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401d2f72`
- `ntoskrnl!ProbeForRead` at `0x1401d2b69`
- `ntoskrnl!ProbeForRead` at `0x1401d2b81`
- `ntoskrnl!ProbeForRead` at `0x1401d2cd8`
- `ntoskrnl!ProbeForRead` at `0x1401d2d0a`
- `ntoskrnl!ProbeForRead` at `0x1401d2d73`
- `ntoskrnl!ProbeForRead` at `0x1401d2b69`
- `ntoskrnl!ProbeForRead` at `0x1401d2b81`
- `ntoskrnl!ProbeForRead` at `0x1401d2cd8`
- `ntoskrnl!ProbeForRead` at `0x1401d2d0a`
- `ntoskrnl!ProbeForRead` at `0x1401d2d73`
- `ntoskrnl!PsGetProcessPeb` at `0x1401d2a33`
- `ntoskrnl!PsGetProcessPeb` at `0x1401d2a33`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401d2b0b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401d2dee`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401d2e28`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401d2fbd`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401d2b0b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401d2dee`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401d2e28`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401d2fbd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d30d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d3129`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d30d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d3129`
- `win32kbase!FastGetProfileDwordEx` at `0x1401d2ecf`
- `win32kbase!FastGetProfileDwordEx` at `0x1401d2ecf`
- `win32kbase!FastGetProfileStringW` at `0x1401d3010`
- `win32kbase!FastGetProfileStringW` at `0x1401d3010`
- `win32kbase!IsImmersiveBroker` at `0x1401d2c90`
- `win32kbase!IsImmersiveBroker` at `0x1401d2c90`
- `WIN32K!W32GetUserSessionState` at `0x1401d305d`
- `WIN32K!W32GetUserSessionState` at `0x1401d305d`

## pseudocode

```c
__int64 __fastcall SetAppCompatFlags(_QWORD *a1)
{
  PEPROCESS ThreadProcess; // rax
  __int64 v3; // rax
  unsigned __int16 *v4; // rax
  char v5; // r15
  _WORD *v6; // rcx
  _WORD *v7; // rbx
  _WORD *v8; // rax
  _WORD *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // r14
  _WORD *v12; // rcx
  __int64 CurrentProcessWin32Process; // rax
  unsigned int *v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rax
  int v17; // edx
  int v18; // eax
  int v19; // eax
  size_t v20; // r8
  char *v21; // rbx
  int v22; // ecx
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned __int64 v26; // r14
  __int64 v27; // rax
  __int64 v28; // rdx
  bool v29; // di
  __int64 UserSessionState; // rax
  int v31; // r8d
  int v32; // edx
  ULONG Value; // [rsp+50h] [rbp-248h] BYREF
  volatile void *Address; // [rsp+58h] [rbp-240h]
  int v35; // [rsp+60h] [rbp-238h] BYREF
  __int128 v36; // [rsp+68h] [rbp-230h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-220h]
  _WORD *v38; // [rsp+80h] [rbp-218h]
  UNICODE_STRING String; // [rsp+88h] [rbp-210h] BYREF
  _WORD *v40; // [rsp+98h] [rbp-200h]
  __int64 v41; // [rsp+A0h] [rbp-1F8h]
  __int64 v42; // [rsp+A8h] [rbp-1F0h]
  __int64 v43; // [rsp+B0h] [rbp-1E8h]
  __int64 v44; // [rsp+B8h] [rbp-1E0h]
  __int64 v45; // [rsp+C0h] [rbp-1D8h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-1D0h] BYREF
  WCHAR SourceString[96]; // [rsp+F0h] [rbp-1A8h] BYREF
  WCHAR v48[80]; // [rsp+1B0h] [rbp-E8h] BYREF

  Value = 0;
  DestinationString = 0;
  v36 = 0;
  ThreadProcess = PsGetThreadProcess((PETHREAD)*a1);
  Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
  v3 = a1[87];
  if ( v3 )
  {
    v22 = *(_DWORD *)(v3 + 672);
    *((_DWORD *)a1 + 168) = v22;
    a1[85] = *(_QWORD *)(v3 + 680);
    *(_DWORD *)(a1[64] + 20LL) = v22;
    *(_DWORD *)(a1[64] + 24LL) = *((_DWORD *)a1 + 170);
    return 0;
  }
  v4 = (unsigned __int16 *)a1[66];
  v5 = 1;
  if ( !v4 )
  {
    v41 = 1;
    ProbeForRead(Address, 1u, 1u);
    v21 = (char *)*((_QWORD *)Address + 4);
    v42 = 1;
    ProbeForRead(v21, 1u, 1u);
    *(_DWORD *)(&String.MaximumLength + 1) = 0;
    *(_DWORD *)&String.Length = RtlReadULongFromUser(v21 + 96);
    String.Buffer = (PWSTR)RtlReadULong64FromUser(v21 + 104);
    *(_QWORD *)&v36 = *(unsigned int *)&String.Length;
    *((_QWORD *)&v36 + 1) = String.Buffer;
    ProbeForRead(String.Buffer, String.Length + 2LL, 2u);
    if ( String.Length > String.MaximumLength )
    {
      if ( (v36 & 1) == 0 )
        goto LABEL_59;
    }
    else if ( (String.Length & 1) == 0 )
    {
      v4 = (unsigned __int16 *)&v36;
      goto LABEL_3;
    }
    LODWORD(Address) = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 216);
LABEL_59:
    ExRaiseAccessViolation();
  }
LABEL_3:
  v6 = (_WORD *)*((_QWORD *)v4 + 1);
  v7 = &v6[(unsigned __int64)*v4 >> 1];
  v40 = v7;
  v8 = v7;
  v38 = v7;
  while ( v7 != v6 )
  {
    if ( *v7 == 46 )
      goto LABEL_7;
    v40 = --v7;
  }
  v7 = v8;
  v40 = v8;
LABEL_7:
  v9 = v7;
  v38 = v7;
  while ( v9 != v6 )
  {
    if ( *v9 == 92 || *v9 == 58 )
    {
      v38 = ++v9;
      break;
    }
    v38 = --v9;
  }
  v10 = 2 * (v7 - v9);
  v37 = v10;
  if ( v10 >= 0xA4 )
    v10 = 162;
  v37 = v10;
  v11 = v10;
  memmove(SourceString, v9, v10);
  v12 = (_WORD *)(a1[57] + 976LL);
  if ( !*v12 )
  {
    v20 = 30;
    if ( v10 < 0x1E )
      v20 = v10;
    memmove(v12, v9, v20);
    *(_WORD *)(a1[57] + 1006LL) = 0;
  }
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
  v43 = CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
  {
    CurrentProcessWin32Process &= -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
    v43 = CurrentProcessWin32Process;
  }
  if ( (*(_DWORD *)(CurrentProcessWin32Process + 12) & 0x80u) == 0 )
  {
    v16 = *((_QWORD *)Address + 90);
  }
  else
  {
    v14 = (unsigned int *)(PsGetThreadTeb(*a1) + 8240);
    ProbeForRead(v14, 4u, 4u);
    v15 = *v14;
    ProbeForRead((volatile void *)(unsigned int)v15, 0x488u, 4u);
    v16 = *(_QWORD *)(v15 + 480);
  }
  a1[85] = v16;
  if ( (v16 & 0x800000000000000LL) != 0 )
  {
    v35 = 0;
    FastGetProfileDwordEx(0, 4, L"ForceDisableGDIScaling", 0, 4, &v35, 0);
    if ( v35 )
    {
      a1[85] &= ~0x800000000000000uLL;
      v24 = PsGetCurrentProcessWin32Process();
      v44 = v24;
      if ( v24 )
      {
        v24 &= -(__int64)(*(_QWORD *)v24 != 0);
        v44 = v24;
      }
      *(_DWORD *)(v24 + 12) &= ~0x20000000u;
    }
    else
    {
      v25 = PsGetCurrentProcessWin32Process();
      v45 = v25;
      if ( v25 )
      {
        v25 &= -(__int64)(*(_QWORD *)v25 != 0);
        v45 = v25;
      }
      *(_DWORD *)(v25 + 12) |= 0x20000000u;
      TraceLoggingGDIScaledAppEvent();
    }
  }
  *(_DWORD *)(a1[64] + 24LL) = *((_DWORD *)a1 + 170);
  if ( (a1[85] & 0x2000000) != 0 || (v19 = IsCurrentDesktopComposed(), v17 = 0, !v19) )
    v17 = 1;
  if ( (*(_BYTE *)(a1[57] + 808LL) & 0x30) == 0x10 )
    *(_QWORD *)a1[64] |= 0x10000000uLL;
  if ( !v17 )
  {
    if ( (a1[85] & 0x880000000000000LL) != 0 )
    {
      *(_QWORD *)(a1[64] + 224LL) |= 0x10uLL;
      goto LABEL_23;
    }
    if ( (*(_BYTE *)(a1[57] + 808LL) & 0x30) != 0x10 )
    {
      if ( (unsigned int)IsImmersiveBroker() )
        *(_QWORD *)(a1[64] + 224LL) |= 0x80uLL;
      goto LABEL_23;
    }
  }
  *(_QWORD *)a1[64] |= 0x20000000uLL;
LABEL_23:
  if ( _bittest64(a1 + 85, 0x38u) )
    *(_QWORD *)(a1[64] + 224LL) |= 0x20uLL;
  v18 = *((_DWORD *)a1 + 170);
  if ( (v18 & 0x10000000) == 0 && *((_WORD *)a1 + 332) < 0x600u )
  {
    *((_DWORD *)a1 + 170) = v18 | 0x20000000;
    *(_DWORD *)(a1[64] + 24LL) |= 0x20000000u;
  }
  v26 = v11 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v26 >= 0xB4 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)SourceString + v26) = 0;
  v27 = PsGetCurrentProcessWin32Process();
  if ( v27 )
    v27 &= -(__int64)(*(_QWORD *)v27 != 0);
  if ( (unsigned int)FastGetProfileStringW(0, (*(_DWORD *)(v27 + 12) & 0x80u) != 0 ? 43 : 33, SourceString, 0) )
  {
    String = 0;
    RtlInitUnicodeString(&String, v48);
    RtlUnicodeStringToInteger(&String, 0, &Value);
  }
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v5 = 0;
  }
  v29 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v5 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v28);
    LOBYTE(v31) = v29;
    LOBYTE(v32) = v5;
    WPP_RECORDER_AND_TRACE_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v32,
      v31,
      *(_QWORD *)(UserSessionState + 69152),
      (unsigned int)v48,
      80,
      0);
  }
  *(_DWORD *)(a1[64] + 20LL) = Value;
  *((_DWORD *)a1 + 168) = Value;
  *(WCHAR *)((char *)SourceString + v26) = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  return SetAppImeCompatFlags(a1, &DestinationString);
}

```

## disassembly

```asm
0x1401d29e0  push    rbx
0x1401d29e2  push    rsi
0x1401d29e3  push    rdi
0x1401d29e4  push    r12
0x1401d29e6  push    r14
0x1401d29e8  push    r15
0x1401d29ea  sub     rsp, 268h
0x1401d29f1  mov     rax, cs:__security_cookie
0x1401d29f8  xor     rax, rsp
0x1401d29fb  mov     [rsp+298h+var_48], rax
0x1401d2a03  mov     rsi, rcx
0x1401d2a06  xor     r12d, r12d
0x1401d2a09  mov     [rsp+298h+Value], r12d
0x1401d2a0e  xorps   xmm0, xmm0
0x1401d2a11  movups  xmmword ptr [rsp+298h+DestinationString.Length], xmm0
0x1401d2a19  xorps   xmm1, xmm1
0x1401d2a1c  movups  [rsp+298h+var_230], xmm1
0x1401d2a21  mov     rcx, [rcx]; Thread
0x1401d2a24  call    cs:__imp_PsGetThreadProcess
0x1401d2a2b  nop     dword ptr [rax+rax+00h]
0x1401d2a30  mov     rcx, rax
0x1401d2a33  call    cs:__imp_PsGetProcessPeb
0x1401d2a3a  nop     dword ptr [rax+rax+00h]
0x1401d2a3f  mov     [rsp+298h+Address], rax
0x1401d2a44  mov     rax, [rsi+2B8h]
0x1401d2a4b  test    rax, rax
0x1401d2a4e  jnz     loc_1401D2DA2
0x1401d2a54  mov     rax, [rsi+210h]
0x1401d2a5b  lea     r15d, [r12+1]
0x1401d2a60  test    rax, rax
0x1401d2a63  jz      loc_1401D2CB9
0x1401d2a69  lea     r14d, [r12+2]
0x1401d2a6e  mov     rcx, [rax+8]
0x1401d2a72  movzx   eax, word ptr [rax]
0x1401d2a75  shr     rax, 1
0x1401d2a78  lea     rbx, [rcx+rax*2]
0x1401d2a7c  mov     [rsp+298h+var_200], rbx
0x1401d2a84  mov     rax, rbx
0x1401d2a87  mov     [rsp+298h+var_218], rbx
0x1401d2a8f  cmp     rbx, rcx
0x1401d2a92  jz      loc_1401D2E6A
0x1401d2a98  cmp     word ptr [rbx], 2Eh ; '.'
0x1401d2a9c  jz      short loc_1401D2AAB
0x1401d2a9e  sub     rbx, r14
0x1401d2aa1  mov     [rsp+298h+var_200], rbx
0x1401d2aa9  jmp     short loc_1401D2A8F
0x1401d2aab  mov     rdi, rbx
0x1401d2aae  mov     [rsp+298h+var_218], rbx
0x1401d2ab6  cmp     rdi, rcx
0x1401d2ab9  jnz     loc_1401D2E7A
0x1401d2abf  sub     rbx, rdi
0x1401d2ac2  sar     rbx, 1
0x1401d2ac5  add     ebx, ebx
0x1401d2ac7  mov     [rsp+298h+var_220], ebx
0x1401d2acb  mov     eax, 0A2h
0x1401d2ad0  cmp     ebx, 0A4h
0x1401d2ad6  cmovnb  ebx, eax
0x1401d2ad9  mov     [rsp+298h+var_220], ebx
0x1401d2add  mov     r14d, ebx
0x1401d2ae0  mov     r8d, ebx; Size
0x1401d2ae3  mov     rdx, rdi; Src
0x1401d2ae6  lea     rcx, [rsp+298h+SourceString]; void *
0x1401d2aee  call    memmove
0x1401d2af3  mov     rcx, [rsi+1C8h]
0x1401d2afa  add     rcx, 3D0h; void *
0x1401d2b01  cmp     [rcx], r12w
0x1401d2b05  jz      loc_1401D2C39
0x1401d2b0b  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401d2b12  nop     dword ptr [rax+rax+00h]
0x1401d2b17  mov     [rsp+298h+var_1E8], rax
0x1401d2b1f  test    rax, rax
0x1401d2b22  jz      short loc_1401D2B3B
0x1401d2b24  mov     rcx, [rax]
0x1401d2b27  neg     rcx
0x1401d2b2a  sbb     rdx, rdx
0x1401d2b2d  and     rdx, rax
0x1401d2b30  mov     rax, rdx
0x1401d2b33  mov     [rsp+298h+var_1E8], rdx
0x1401d2b3b  mov     eax, [rax+0Ch]
0x1401d2b3e  test    al, al
0x1401d2b40  jns     loc_1401D2C15
0x1401d2b46  mov     rcx, [rsi]
0x1401d2b49  call    cs:__imp_PsGetThreadTeb
0x1401d2b50  nop     dword ptr [rax+rax+00h]
0x1401d2b55  lea     rbx, [rax+2030h]
0x1401d2b5c  mov     edi, 4
0x1401d2b61  mov     r8d, edi; Alignment
0x1401d2b64  mov     edx, edi; Length
0x1401d2b66  mov     rcx, rbx; Address
0x1401d2b69  call    cs:__imp_ProbeForRead
0x1401d2b70  nop     dword ptr [rax+rax+00h]
0x1401d2b75  mov     ebx, [rbx]
0x1401d2b77  mov     r8d, edi; Alignment
0x1401d2b7a  mov     edx, 488h; Length
0x1401d2b7f  mov     ecx, ebx; Address
0x1401d2b81  call    cs:__imp_ProbeForRead
0x1401d2b88  nop     dword ptr [rax+rax+00h]
0x1401d2b8d  mov     rax, [rbx+1E0h]
0x1401d2b94  mov     [rsi+2A8h], rax
0x1401d2b9b  bt      rax, 3Bh ; ';'
0x1401d2ba0  jb      loc_1401D2EA9
0x1401d2ba6  mov     ebx, 20000000h
0x1401d2bab  mov     rcx, [rsi+200h]
0x1401d2bb2  mov     eax, [rsi+2A8h]
0x1401d2bb8  mov     [rcx+18h], eax
0x1401d2bbb  test    dword ptr [rsi+2A8h], 2000000h
0x1401d2bc5  jz      short loc_1401D2C2B
0x1401d2bc7  mov     edx, r15d
0x1401d2bca  mov     rax, [rsi+1C8h]
0x1401d2bd1  mov     cl, [rax+328h]
0x1401d2bd7  and     cl, 30h
0x1401d2bda  cmp     cl, 10h
0x1401d2bdd  jz      loc_1401D2EEB
0x1401d2be3  test    edx, edx
0x1401d2be5  jz      short loc_1401D2C62
0x1401d2be7  mov     rax, [rsi+200h]
0x1401d2bee  or      [rax], rbx
0x1401d2bf1  bt      qword ptr [rsi+2A8h], 38h ; '8'
0x1401d2bfa  jb      loc_1401D2F10
0x1401d2c00  mov     eax, [rsi+2A8h]
0x1401d2c06  bt      eax, 1Ch
0x1401d2c0a  jnb     loc_1401D2F24
0x1401d2c10  jmp     loc_1401D2FA3
0x1401d2c15  mov     rax, [rsp+298h+Address]
0x1401d2c1a  mov     rax, [rax+2D0h]
0x1401d2c21  mov     edi, 4
0x1401d2c26  jmp     loc_1401D2B94
0x1401d2c2b  call    IsCurrentDesktopComposed
0x1401d2c30  test    eax, eax
0x1401d2c32  mov     edx, r12d
0x1401d2c35  jnz     short loc_1401D2BCA
0x1401d2c37  jmp     short loc_1401D2BC7
0x1401d2c39  mov     r8d, 1Eh
0x1401d2c3f  cmp     ebx, r8d
0x1401d2c42  cmovb   r8, r14; Size
0x1401d2c46  mov     rdx, rdi; Src
0x1401d2c49  call    memmove
0x1401d2c4e  mov     rcx, [rsi+1C8h]
0x1401d2c55  mov     [rcx+3EEh], r12w
0x1401d2c5d  jmp     loc_1401D2B0B
0x1401d2c62  mov     rcx, 880000000000000h
0x1401d2c6c  test    [rsi+2A8h], rcx
0x1401d2c73  jnz     loc_1401D2EFC
0x1401d2c79  mov     rcx, [rsi+1C8h]
0x1401d2c80  mov     al, [rcx+328h]
0x1401d2c86  and     al, 30h
0x1401d2c88  cmp     al, 10h
0x1401d2c8a  jz      loc_1401D2BE7
0x1401d2c90  call    cs:__imp_IsImmersiveBroker
0x1401d2c97  nop     dword ptr [rax+rax+00h]
0x1401d2c9c  test    eax, eax
0x1401d2c9e  jz      loc_1401D2BF1
0x1401d2ca4  mov     rax, [rsi+200h]
0x1401d2cab  bts     qword ptr [rax+0E0h], 7
0x1401d2cb4  jmp     loc_1401D2BF1
0x1401d2cb9  mov     [rsp+298h+var_1F8], 7D0h
0x1401d2cc5  mov     rcx, [rsp+298h+Address]; Address
0x1401d2cca  mov     [rsp+298h+var_1F8], r15
0x1401d2cd2  mov     r8d, r15d; Alignment
0x1401d2cd5  mov     rdx, r15; Length
0x1401d2cd8  call    cs:__imp_ProbeForRead
0x1401d2cdf  nop     dword ptr [rax+rax+00h]
0x1401d2ce4  mov     rax, [rsp+298h+Address]
0x1401d2ce9  mov     rbx, [rax+20h]
0x1401d2ced  mov     [rsp+298h+var_1F0], 448h
0x1401d2cf9  mov     [rsp+298h+var_1F0], r15
0x1401d2d01  mov     r8d, r15d; Alignment
0x1401d2d04  mov     rdx, r15; Length
0x1401d2d07  mov     rcx, rbx; Address
0x1401d2d0a  call    cs:__imp_ProbeForRead
0x1401d2d11  nop     dword ptr [rax+rax+00h]
0x1401d2d16  xorps   xmm0, xmm0
0x1401d2d19  movups  xmmword ptr [rsp+298h+String.Length], xmm0
0x1401d2d21  lea     rcx, [rbx+60h]
0x1401d2d25  call    RtlReadULongFromUser
0x1401d2d2a  mov     edi, eax
0x1401d2d2c  mov     dword ptr [rsp+298h+String.Length], edi
0x1401d2d33  lea     rcx, [rbx+68h]
0x1401d2d37  call    RtlReadULong64FromUser
0x1401d2d3c  mov     [rsp+298h+String.Buffer], rax
0x1401d2d44  movzx   edx, di
0x1401d2d47  mov     word ptr [rsp+298h+var_230], dx
0x1401d2d4c  shr     edi, 10h
0x1401d2d4f  mov     word ptr [rsp+298h+var_230+2], di
0x1401d2d54  mov     ecx, dword ptr [rsp+298h+String+4]
0x1401d2d5b  mov     dword ptr [rsp+298h+var_230+4], ecx
0x1401d2d5f  mov     qword ptr [rsp+298h+var_230+8], rax
0x1401d2d64  mov     r14d, 2
0x1401d2d6a  add     rdx, r14; Length
0x1401d2d6d  mov     r8d, r14d; Alignment
0x1401d2d70  mov     rcx, rax; Address
0x1401d2d73  call    cs:__imp_ProbeForRead
0x1401d2d7a  nop     dword ptr [rax+rax+00h]
0x1401d2d7f  movzx   eax, word ptr [rsp+298h+var_230]
0x1401d2d84  cmp     ax, word ptr [rsp+298h+var_230+2]
0x1401d2d89  ja      loc_1401D2F4D
0x1401d2d8f  test    r15b, al
0x1401d2d92  jnz     loc_1401D2F54
0x1401d2d98  lea     rax, [rsp+298h+var_230]
0x1401d2d9d  jmp     loc_1401D2A6E
0x1401d2da2  mov     ecx, [rax+2A0h]
0x1401d2da8  mov     [rsi+2A0h], ecx
0x1401d2dae  mov     rax, [rax+2A8h]
0x1401d2db5  mov     [rsi+2A8h], rax
0x1401d2dbc  mov     rax, [rsi+200h]
0x1401d2dc3  mov     [rax+14h], ecx
0x1401d2dc6  mov     rcx, [rsi+200h]
0x1401d2dcd  mov     eax, [rsi+2A8h]
0x1401d2dd3  mov     [rcx+18h], eax
0x1401d2dd6  xor     eax, eax
0x1401d2dd8  jmp     loc_1401D2F81
0x1401d2ddd  mov     rax, 0F7FFFFFFFFFFFFFFh
0x1401d2de7  and     [rsi+2A8h], rax
0x1401d2dee  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401d2df5  nop     dword ptr [rax+rax+00h]
0x1401d2dfa  mov     [rsp+298h+var_1E0], rax
0x1401d2e02  test    rax, rax
0x1401d2e05  jz      short loc_1401D2E1E
0x1401d2e07  mov     rcx, [rax]
0x1401d2e0a  neg     rcx
0x1401d2e0d  sbb     rdx, rdx
0x1401d2e10  and     rdx, rax
0x1401d2e13  mov     rax, rdx
0x1401d2e16  mov     [rsp+298h+var_1E0], rdx
0x1401d2e1e  btr     dword ptr [rax+0Ch], 1Dh
0x1401d2e23  jmp     loc_1401D2BA6
0x1401d2e28  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401d2e2f  nop     dword ptr [rax+rax+00h]
0x1401d2e34  mov     [rsp+298h+var_1D8], rax
0x1401d2e3c  test    rax, rax
0x1401d2e3f  jz      short loc_1401D2E58
0x1401d2e41  mov     rcx, [rax]
0x1401d2e44  neg     rcx
0x1401d2e47  sbb     rdx, rdx
0x1401d2e4a  and     rdx, rax
0x1401d2e4d  mov     rax, rdx
0x1401d2e50  mov     [rsp+298h+var_1D8], rdx
0x1401d2e58  mov     ebx, 20000000h
0x1401d2e5d  or      [rax+0Ch], ebx
0x1401d2e60  call    ?TraceLoggingGDIScaledAppEvent@@YAXXZ; TraceLoggingGDIScaledAppEvent(void)
0x1401d2e65  jmp     loc_1401D2BAB
0x1401d2e6a  mov     rbx, rax
0x1401d2e6d  mov     [rsp+298h+var_200], rax
0x1401d2e75  jmp     loc_1401D2AAB
0x1401d2e7a  movzx   eax, word ptr [rdi]
0x1401d2e7d  cmp     ax, 5Ch ; '\'
0x1401d2e81  jz      short loc_1401D2E99
0x1401d2e83  cmp     ax, 3Ah ; ':'
0x1401d2e87  jz      short loc_1401D2E99
0x1401d2e89  sub     rdi, r14
0x1401d2e8c  mov     [rsp+298h+var_218], rdi
0x1401d2e94  jmp     loc_1401D2AB6
0x1401d2e99  add     rdi, r14
0x1401d2e9c  mov     [rsp+298h+var_218], rdi
0x1401d2ea4  jmp     loc_1401D2ABF
0x1401d2ea9  mov     [rsp+298h+var_238], r12d
0x1401d2eae  mov     [rsp+298h+var_268], r12
0x1401d2eb3  lea     rax, [rsp+298h+var_238]
0x1401d2eb8  mov     [rsp+298h+var_270], rax
0x1401d2ebd  mov     dword ptr [rsp+298h+var_278], edi
0x1401d2ec1  xor     r9d, r9d
0x1401d2ec4  lea     r8, aForcedisablegd; "ForceDisableGDIScaling"
0x1401d2ecb  mov     edx, edi
0x1401d2ecd  xor     ecx, ecx
0x1401d2ecf  call    cs:__imp_FastGetProfileDwordEx
0x1401d2ed6  nop     dword ptr [rax+rax+00h]
0x1401d2edb  cmp     [rsp+298h+var_238], r12d
0x1401d2ee0  jbe     loc_1401D2E28
0x1401d2ee6  jmp     loc_1401D2DDD
0x1401d2eeb  mov     rax, [rsi+200h]
0x1401d2ef2  bts     qword ptr [rax], 1Ch
0x1401d2ef7  jmp     loc_1401D2BE3
0x1401d2efc  mov     rax, [rsi+200h]
0x1401d2f03  or      qword ptr [rax+0E0h], 10h
0x1401d2f0b  jmp     loc_1401D2BF1
0x1401d2f10  mov     rax, [rsi+200h]
0x1401d2f17  or      qword ptr [rax+0E0h], 20h
0x1401d2f1f  jmp     loc_1401D2C00
0x1401d2f24  mov     ecx, 600h
0x1401d2f29  cmp     [rsi+298h], cx
0x1401d2f30  jnb     loc_1401D2C10
0x1401d2f36  or      eax, ebx
0x1401d2f38  mov     [rsi+2A8h], eax
0x1401d2f3e  mov     rax, [rsi+200h]
0x1401d2f45  or      [rax+18h], ebx
0x1401d2f48  jmp     loc_1401D2C10
0x1401d2f4d  test    byte ptr [rsp+298h+var_230], r15b
0x1401d2f52  jz      short loc_1401D2F72
0x1401d2f54  mov     dword ptr [rsp+298h+Address], 20000h
0x1401d2f5c  mov     r8d, 0D8h
0x1401d2f62  mov     edx, dword ptr [rsp+298h+Address]
0x1401d2f66  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401d2f6d  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401d2f72  call    cs:__imp_ExRaiseAccessViolation
0x1401d2f79  nop     dword ptr [rax+rax+00h]
0x1401d2f7e  nop
0x1401d2f7f  xor     eax, eax
0x1401d2f81  mov     rcx, [rsp+298h+var_48]
0x1401d2f89  xor     rcx, rsp; StackCookie
0x1401d2f8c  call    __security_check_cookie
  ... truncated ...
```
