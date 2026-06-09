# SetAppCompatFlags

- ea: `0x1401b55d0`
- end: `0x1401b5d59`
- name: `SetAppCompatFlags`
- size: `1929`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1401b55d0`
- `0x1401b5d60`
- `0x1401b5f68`
- `0x1401b60a0`
- `0x1402913f0`
- `0x1402a46f0`
- `0x1402d2650`
- `0x140341ff0`
- `0x140342240`
- `0x1403d21c8`
- `0x1403d2204`

## import_xrefs

- `ntoskrnl!PsGetThreadTeb` at `0x1401b5739`
- `ntoskrnl!PsGetThreadTeb` at `0x1401b5739`
- `ntoskrnl!PsGetThreadProcess` at `0x1401b5614`
- `ntoskrnl!PsGetThreadProcess` at `0x1401b5614`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1401b5d34`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1401b5d34`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401b5b62`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401b5b62`
- `ntoskrnl!ProbeForRead` at `0x1401b5759`
- `ntoskrnl!ProbeForRead` at `0x1401b5771`
- `ntoskrnl!ProbeForRead` at `0x1401b58c8`
- `ntoskrnl!ProbeForRead` at `0x1401b58fa`
- `ntoskrnl!ProbeForRead` at `0x1401b5963`
- `ntoskrnl!ProbeForRead` at `0x1401b5759`
- `ntoskrnl!ProbeForRead` at `0x1401b5771`
- `ntoskrnl!ProbeForRead` at `0x1401b58c8`
- `ntoskrnl!ProbeForRead` at `0x1401b58fa`
- `ntoskrnl!ProbeForRead` at `0x1401b5963`
- `ntoskrnl!PsGetProcessPeb` at `0x1401b5623`
- `ntoskrnl!PsGetProcessPeb` at `0x1401b5623`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401b56fb`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401b59de`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401b5a18`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401b5bad`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401b56fb`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401b59de`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401b5a18`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401b5bad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b5cc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b5d19`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b5cc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b5d19`
- `win32kbase!FastGetProfileDwordEx` at `0x1401b5abf`
- `win32kbase!FastGetProfileDwordEx` at `0x1401b5abf`
- `win32kbase!FastGetProfileStringW` at `0x1401b5c00`
- `win32kbase!FastGetProfileStringW` at `0x1401b5c00`
- `win32kbase!IsImmersiveBroker` at `0x1401b5880`
- `win32kbase!IsImmersiveBroker` at `0x1401b5880`
- `WIN32K!W32GetUserSessionState` at `0x1401b5c4d`
- `WIN32K!W32GetUserSessionState` at `0x1401b5c4d`

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
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  _WORD *v15; // rcx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int *v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  size_t v26; // r8
  unsigned int *v27; // rbx
  int v28; // ecx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  unsigned __int64 v36; // r14
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  bool v41; // di
  __int64 UserSessionState; // rax
  int v43; // r8d
  int v44; // edx
  ULONG Value; // [rsp+50h] [rbp-248h] BYREF
  volatile void *Address; // [rsp+58h] [rbp-240h]
  int v47; // [rsp+60h] [rbp-238h] BYREF
  __int128 v48; // [rsp+68h] [rbp-230h] BYREF
  unsigned int v49; // [rsp+78h] [rbp-220h]
  _WORD *v50; // [rsp+80h] [rbp-218h]
  UNICODE_STRING String; // [rsp+88h] [rbp-210h] BYREF
  _WORD *v52; // [rsp+98h] [rbp-200h]
  __int64 v53; // [rsp+A0h] [rbp-1F8h]
  __int64 v54; // [rsp+A8h] [rbp-1F0h]
  __int64 v55; // [rsp+B0h] [rbp-1E8h]
  __int64 v56; // [rsp+B8h] [rbp-1E0h]
  __int64 v57; // [rsp+C0h] [rbp-1D8h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-1D0h] BYREF
  WCHAR SourceString[96]; // [rsp+F0h] [rbp-1A8h] BYREF
  WCHAR v60[80]; // [rsp+1B0h] [rbp-E8h] BYREF

  Value = 0;
  DestinationString = 0;
  v48 = 0;
  ThreadProcess = PsGetThreadProcess((PETHREAD)*a1);
  Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
  v3 = a1[87];
  if ( v3 )
  {
    v28 = *(_DWORD *)(v3 + 672);
    *((_DWORD *)a1 + 168) = v28;
    a1[85] = *(_QWORD *)(v3 + 680);
    *(_DWORD *)(a1[64] + 20LL) = v28;
    *(_DWORD *)(a1[64] + 24LL) = *((_DWORD *)a1 + 170);
    return 0;
  }
  v4 = (unsigned __int16 *)a1[66];
  v5 = 1;
  if ( !v4 )
  {
    v53 = 1;
    ProbeForRead(Address, 1u, 1u);
    v27 = (unsigned int *)*((_QWORD *)Address + 4);
    v54 = 1;
    ProbeForRead(v27, 1u, 1u);
    *(_DWORD *)(&String.MaximumLength + 1) = 0;
    *(_DWORD *)&String.Length = RtlReadULongFromUser(v27 + 24);
    String.Buffer = (PWSTR)RtlReadULong64FromUser(v27 + 26);
    *(_QWORD *)&v48 = *(unsigned int *)&String.Length;
    *((_QWORD *)&v48 + 1) = String.Buffer;
    ProbeForRead(String.Buffer, String.Length + 2LL, 2u);
    if ( String.Length > String.MaximumLength )
    {
      if ( (v48 & 1) == 0 )
        goto LABEL_59;
    }
    else if ( (String.Length & 1) == 0 )
    {
      v4 = (unsigned __int16 *)&v48;
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
  v52 = v7;
  v8 = v7;
  v50 = v7;
  while ( v7 != v6 )
  {
    if ( *v7 == 46 )
      goto LABEL_7;
    v52 = --v7;
  }
  v7 = v8;
  v52 = v8;
LABEL_7:
  v9 = v7;
  v50 = v7;
  while ( v9 != v6 )
  {
    if ( *v9 == 92 || *v9 == 58 )
    {
      v50 = ++v9;
      break;
    }
    v50 = --v9;
  }
  v10 = 2 * (v7 - v9);
  v49 = v10;
  if ( v10 >= 0xA4 )
    v10 = 162;
  v49 = v10;
  v11 = v10;
  memmove(SourceString, v9, v10);
  v15 = (_WORD *)(a1[57] + 976LL);
  if ( !*v15 )
  {
    v26 = 30;
    if ( v10 < 0x1E )
      v26 = v10;
    memmove(v15, v9, v26);
    v15 = (_WORD *)a1[57];
    v15[503] = 0;
  }
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v15, v12, v13, v14);
  v55 = CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
  {
    CurrentProcessWin32Process &= -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
    v55 = CurrentProcessWin32Process;
  }
  if ( (*(_DWORD *)(CurrentProcessWin32Process + 12) & 0x80u) == 0 )
  {
    v21 = *((_QWORD *)Address + 90);
  }
  else
  {
    v19 = (unsigned int *)(PsGetThreadTeb(*a1) + 8240);
    ProbeForRead(v19, 4u, 4u);
    v20 = *v19;
    ProbeForRead((volatile void *)(unsigned int)v20, 0x488u, 4u);
    v21 = *(_QWORD *)(v20 + 480);
  }
  a1[85] = v21;
  if ( (v21 & 0x800000000000000LL) != 0 )
  {
    v47 = 0;
    FastGetProfileDwordEx(0, 4, L"ForceDisableGDIScaling", 0, 4, &v47, 0);
    if ( v47 )
    {
      a1[85] &= ~0x800000000000000uLL;
      v30 = PsGetCurrentProcessWin32Process(v33, v32, v34, v35);
      v56 = v30;
      if ( v30 )
      {
        v30 &= -(__int64)(*(_QWORD *)v30 != 0);
        v56 = v30;
      }
      *(_DWORD *)(v30 + 12) &= ~0x20000000u;
    }
    else
    {
      v31 = PsGetCurrentProcessWin32Process(v33, v32, v34, v35);
      v57 = v31;
      if ( v31 )
      {
        v31 &= -(__int64)(*(_QWORD *)v31 != 0);
        v57 = v31;
      }
      *(_DWORD *)(v31 + 12) |= 0x20000000u;
      TraceLoggingGDIScaledAppEvent();
    }
  }
  v22 = a1[64];
  *(_DWORD *)(v22 + 24) = *((_DWORD *)a1 + 170);
  if ( (a1[85] & 0x2000000) != 0 || (v25 = IsCurrentDesktopComposed(), v23 = 0, !v25) )
    v23 = 1;
  LOBYTE(v22) = *(_BYTE *)(a1[57] + 808LL) & 0x30;
  if ( (_BYTE)v22 == 16 )
    *(_QWORD *)a1[64] |= 0x10000000uLL;
  if ( !(_DWORD)v23 )
  {
    v22 = 0x880000000000000LL;
    if ( (a1[85] & 0x880000000000000LL) != 0 )
    {
      *(_QWORD *)(a1[64] + 224LL) |= 0x10uLL;
      goto LABEL_23;
    }
    v22 = a1[57];
    if ( (*(_BYTE *)(v22 + 808) & 0x30) != 0x10 )
    {
      if ( (unsigned int)IsImmersiveBroker(v22) )
        *(_QWORD *)(a1[64] + 224LL) |= 0x80uLL;
      goto LABEL_23;
    }
  }
  *(_QWORD *)a1[64] |= 0x20000000uLL;
LABEL_23:
  if ( _bittest64(a1 + 85, 0x38u) )
    *(_QWORD *)(a1[64] + 224LL) |= 0x20uLL;
  v24 = *((_DWORD *)a1 + 170);
  if ( (v24 & 0x10000000) == 0 )
  {
    v22 = 1536;
    if ( *((_WORD *)a1 + 332) < 0x600u )
    {
      *((_DWORD *)a1 + 170) = v24 | 0x20000000;
      *(_DWORD *)(a1[64] + 24LL) |= 0x20000000u;
    }
  }
  v36 = v11 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v36 >= 0xB4 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)SourceString + v36) = 0;
  v37 = PsGetCurrentProcessWin32Process(v22, v23, v17, v18);
  if ( v37 )
    v37 &= -(__int64)(*(_QWORD *)v37 != 0);
  if ( (unsigned int)FastGetProfileStringW(0, (*(_DWORD *)(v37 + 12) & 0x80u) != 0 ? 43 : 33, SourceString, 0) )
  {
    String = 0;
    RtlInitUnicodeString(&String, v60);
    RtlUnicodeStringToInteger(&String, 0, &Value);
  }
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v5 = 0;
  }
  v41 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v5 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v38, v39, v40);
    LOBYTE(v43) = v41;
    LOBYTE(v44) = v5;
    WPP_RECORDER_AND_TRACE_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v44,
      v43,
      *(_QWORD *)(UserSessionState + 69152),
      (unsigned int)v60,
      80,
      0);
  }
  *(_DWORD *)(a1[64] + 20LL) = Value;
  *((_DWORD *)a1 + 168) = Value;
  *(WCHAR *)((char *)SourceString + v36) = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  return SetAppImeCompatFlags(a1, &DestinationString);
}

```

## disassembly

```asm
0x1401b55d0  push    rbx
0x1401b55d2  push    rsi
0x1401b55d3  push    rdi
0x1401b55d4  push    r12
0x1401b55d6  push    r14
0x1401b55d8  push    r15
0x1401b55da  sub     rsp, 268h
0x1401b55e1  mov     rax, cs:__security_cookie
0x1401b55e8  xor     rax, rsp
0x1401b55eb  mov     [rsp+298h+var_48], rax
0x1401b55f3  mov     rsi, rcx
0x1401b55f6  xor     r12d, r12d
0x1401b55f9  mov     [rsp+298h+Value], r12d
0x1401b55fe  xorps   xmm0, xmm0
0x1401b5601  movups  xmmword ptr [rsp+298h+DestinationString.Length], xmm0
0x1401b5609  xorps   xmm1, xmm1
0x1401b560c  movups  [rsp+298h+var_230], xmm1
0x1401b5611  mov     rcx, [rcx]; Thread
0x1401b5614  call    cs:__imp_PsGetThreadProcess
0x1401b561b  nop     dword ptr [rax+rax+00h]
0x1401b5620  mov     rcx, rax
0x1401b5623  call    cs:__imp_PsGetProcessPeb
0x1401b562a  nop     dword ptr [rax+rax+00h]
0x1401b562f  mov     [rsp+298h+Address], rax
0x1401b5634  mov     rax, [rsi+2B8h]
0x1401b563b  test    rax, rax
0x1401b563e  jnz     loc_1401B5992
0x1401b5644  mov     rax, [rsi+210h]
0x1401b564b  lea     r15d, [r12+1]
0x1401b5650  test    rax, rax
0x1401b5653  jz      loc_1401B58A9
0x1401b5659  lea     r14d, [r12+2]
0x1401b565e  mov     rcx, [rax+8]
0x1401b5662  movzx   eax, word ptr [rax]
0x1401b5665  shr     rax, 1
0x1401b5668  lea     rbx, [rcx+rax*2]
0x1401b566c  mov     [rsp+298h+var_200], rbx
0x1401b5674  mov     rax, rbx
0x1401b5677  mov     [rsp+298h+var_218], rbx
0x1401b567f  cmp     rbx, rcx
0x1401b5682  jz      loc_1401B5A5A
0x1401b5688  cmp     word ptr [rbx], 2Eh ; '.'
0x1401b568c  jz      short loc_1401B569B
0x1401b568e  sub     rbx, r14
0x1401b5691  mov     [rsp+298h+var_200], rbx
0x1401b5699  jmp     short loc_1401B567F
0x1401b569b  mov     rdi, rbx
0x1401b569e  mov     [rsp+298h+var_218], rbx
0x1401b56a6  cmp     rdi, rcx
0x1401b56a9  jnz     loc_1401B5A6A
0x1401b56af  sub     rbx, rdi
0x1401b56b2  sar     rbx, 1
0x1401b56b5  add     ebx, ebx
0x1401b56b7  mov     [rsp+298h+var_220], ebx
0x1401b56bb  mov     eax, 0A2h
0x1401b56c0  cmp     ebx, 0A4h
0x1401b56c6  cmovnb  ebx, eax
0x1401b56c9  mov     [rsp+298h+var_220], ebx
0x1401b56cd  mov     r14d, ebx
0x1401b56d0  mov     r8d, ebx; Size
0x1401b56d3  mov     rdx, rdi; Src
0x1401b56d6  lea     rcx, [rsp+298h+SourceString]; void *
0x1401b56de  call    memmove
0x1401b56e3  mov     rcx, [rsi+1C8h]
0x1401b56ea  add     rcx, 3D0h; void *
0x1401b56f1  cmp     [rcx], r12w
0x1401b56f5  jz      loc_1401B5829
0x1401b56fb  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401b5702  nop     dword ptr [rax+rax+00h]
0x1401b5707  mov     [rsp+298h+var_1E8], rax
0x1401b570f  test    rax, rax
0x1401b5712  jz      short loc_1401B572B
0x1401b5714  mov     rcx, [rax]
0x1401b5717  neg     rcx
0x1401b571a  sbb     rdx, rdx
0x1401b571d  and     rdx, rax
0x1401b5720  mov     rax, rdx
0x1401b5723  mov     [rsp+298h+var_1E8], rdx
0x1401b572b  mov     eax, [rax+0Ch]
0x1401b572e  test    al, al
0x1401b5730  jns     loc_1401B5805
0x1401b5736  mov     rcx, [rsi]
0x1401b5739  call    cs:__imp_PsGetThreadTeb
0x1401b5740  nop     dword ptr [rax+rax+00h]
0x1401b5745  lea     rbx, [rax+2030h]
0x1401b574c  mov     edi, 4
0x1401b5751  mov     r8d, edi; Alignment
0x1401b5754  mov     edx, edi; Length
0x1401b5756  mov     rcx, rbx; Address
0x1401b5759  call    cs:__imp_ProbeForRead
0x1401b5760  nop     dword ptr [rax+rax+00h]
0x1401b5765  mov     ebx, [rbx]
0x1401b5767  mov     r8d, edi; Alignment
0x1401b576a  mov     edx, 488h; Length
0x1401b576f  mov     ecx, ebx; Address
0x1401b5771  call    cs:__imp_ProbeForRead
0x1401b5778  nop     dword ptr [rax+rax+00h]
0x1401b577d  mov     rax, [rbx+1E0h]
0x1401b5784  mov     [rsi+2A8h], rax
0x1401b578b  bt      rax, 3Bh ; ';'
0x1401b5790  jb      loc_1401B5A99
0x1401b5796  mov     ebx, 20000000h
0x1401b579b  mov     rcx, [rsi+200h]
0x1401b57a2  mov     eax, [rsi+2A8h]
0x1401b57a8  mov     [rcx+18h], eax
0x1401b57ab  test    dword ptr [rsi+2A8h], 2000000h
0x1401b57b5  jz      short loc_1401B581B
0x1401b57b7  mov     edx, r15d
0x1401b57ba  mov     rax, [rsi+1C8h]
0x1401b57c1  mov     cl, [rax+328h]
0x1401b57c7  and     cl, 30h
0x1401b57ca  cmp     cl, 10h
0x1401b57cd  jz      loc_1401B5ADB
0x1401b57d3  test    edx, edx
0x1401b57d5  jz      short loc_1401B5852
0x1401b57d7  mov     rax, [rsi+200h]
0x1401b57de  or      [rax], rbx
0x1401b57e1  bt      qword ptr [rsi+2A8h], 38h ; '8'
0x1401b57ea  jb      loc_1401B5B00
0x1401b57f0  mov     eax, [rsi+2A8h]
0x1401b57f6  bt      eax, 1Ch
0x1401b57fa  jnb     loc_1401B5B14
0x1401b5800  jmp     loc_1401B5B93
0x1401b5805  mov     rax, [rsp+298h+Address]
0x1401b580a  mov     rax, [rax+2D0h]
0x1401b5811  mov     edi, 4
0x1401b5816  jmp     loc_1401B5784
0x1401b581b  call    IsCurrentDesktopComposed
0x1401b5820  test    eax, eax
0x1401b5822  mov     edx, r12d
0x1401b5825  jnz     short loc_1401B57BA
0x1401b5827  jmp     short loc_1401B57B7
0x1401b5829  mov     r8d, 1Eh
0x1401b582f  cmp     ebx, r8d
0x1401b5832  cmovb   r8, r14; Size
0x1401b5836  mov     rdx, rdi; Src
0x1401b5839  call    memmove
0x1401b583e  mov     rcx, [rsi+1C8h]
0x1401b5845  mov     [rcx+3EEh], r12w
0x1401b584d  jmp     loc_1401B56FB
0x1401b5852  mov     rcx, 880000000000000h
0x1401b585c  test    [rsi+2A8h], rcx
0x1401b5863  jnz     loc_1401B5AEC
0x1401b5869  mov     rcx, [rsi+1C8h]
0x1401b5870  mov     al, [rcx+328h]
0x1401b5876  and     al, 30h
0x1401b5878  cmp     al, 10h
0x1401b587a  jz      loc_1401B57D7
0x1401b5880  call    cs:__imp_IsImmersiveBroker
0x1401b5887  nop     dword ptr [rax+rax+00h]
0x1401b588c  test    eax, eax
0x1401b588e  jz      loc_1401B57E1
0x1401b5894  mov     rax, [rsi+200h]
0x1401b589b  bts     qword ptr [rax+0E0h], 7
0x1401b58a4  jmp     loc_1401B57E1
0x1401b58a9  mov     [rsp+298h+var_1F8], 7D0h
0x1401b58b5  mov     rcx, [rsp+298h+Address]; Address
0x1401b58ba  mov     [rsp+298h+var_1F8], r15
0x1401b58c2  mov     r8d, r15d; Alignment
0x1401b58c5  mov     rdx, r15; Length
0x1401b58c8  call    cs:__imp_ProbeForRead
0x1401b58cf  nop     dword ptr [rax+rax+00h]
0x1401b58d4  mov     rax, [rsp+298h+Address]
0x1401b58d9  mov     rbx, [rax+20h]
0x1401b58dd  mov     [rsp+298h+var_1F0], 450h
0x1401b58e9  mov     [rsp+298h+var_1F0], r15
0x1401b58f1  mov     r8d, r15d; Alignment
0x1401b58f4  mov     rdx, r15; Length
0x1401b58f7  mov     rcx, rbx; Address
0x1401b58fa  call    cs:__imp_ProbeForRead
0x1401b5901  nop     dword ptr [rax+rax+00h]
0x1401b5906  xorps   xmm0, xmm0
0x1401b5909  movups  xmmword ptr [rsp+298h+String.Length], xmm0
0x1401b5911  lea     rcx, [rbx+60h]
0x1401b5915  call    RtlReadULongFromUser
0x1401b591a  mov     edi, eax
0x1401b591c  mov     dword ptr [rsp+298h+String.Length], edi
0x1401b5923  lea     rcx, [rbx+68h]
0x1401b5927  call    RtlReadULong64FromUser
0x1401b592c  mov     [rsp+298h+String.Buffer], rax
0x1401b5934  movzx   edx, di
0x1401b5937  mov     word ptr [rsp+298h+var_230], dx
0x1401b593c  shr     edi, 10h
0x1401b593f  mov     word ptr [rsp+298h+var_230+2], di
0x1401b5944  mov     ecx, dword ptr [rsp+298h+String+4]
0x1401b594b  mov     dword ptr [rsp+298h+var_230+4], ecx
0x1401b594f  mov     qword ptr [rsp+298h+var_230+8], rax
0x1401b5954  mov     r14d, 2
0x1401b595a  add     rdx, r14; Length
0x1401b595d  mov     r8d, r14d; Alignment
0x1401b5960  mov     rcx, rax; Address
0x1401b5963  call    cs:__imp_ProbeForRead
0x1401b596a  nop     dword ptr [rax+rax+00h]
0x1401b596f  movzx   eax, word ptr [rsp+298h+var_230]
0x1401b5974  cmp     ax, word ptr [rsp+298h+var_230+2]
0x1401b5979  ja      loc_1401B5B3D
0x1401b597f  test    r15b, al
0x1401b5982  jnz     loc_1401B5B44
0x1401b5988  lea     rax, [rsp+298h+var_230]
0x1401b598d  jmp     loc_1401B565E
0x1401b5992  mov     ecx, [rax+2A0h]
0x1401b5998  mov     [rsi+2A0h], ecx
0x1401b599e  mov     rax, [rax+2A8h]
0x1401b59a5  mov     [rsi+2A8h], rax
0x1401b59ac  mov     rax, [rsi+200h]
0x1401b59b3  mov     [rax+14h], ecx
0x1401b59b6  mov     rcx, [rsi+200h]
0x1401b59bd  mov     eax, [rsi+2A8h]
0x1401b59c3  mov     [rcx+18h], eax
0x1401b59c6  xor     eax, eax
0x1401b59c8  jmp     loc_1401B5B71
0x1401b59cd  mov     rax, 0F7FFFFFFFFFFFFFFh
0x1401b59d7  and     [rsi+2A8h], rax
0x1401b59de  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401b59e5  nop     dword ptr [rax+rax+00h]
0x1401b59ea  mov     [rsp+298h+var_1E0], rax
0x1401b59f2  test    rax, rax
0x1401b59f5  jz      short loc_1401B5A0E
0x1401b59f7  mov     rcx, [rax]
0x1401b59fa  neg     rcx
0x1401b59fd  sbb     rdx, rdx
0x1401b5a00  and     rdx, rax
0x1401b5a03  mov     rax, rdx
0x1401b5a06  mov     [rsp+298h+var_1E0], rdx
0x1401b5a0e  btr     dword ptr [rax+0Ch], 1Dh
0x1401b5a13  jmp     loc_1401B5796
0x1401b5a18  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401b5a1f  nop     dword ptr [rax+rax+00h]
0x1401b5a24  mov     [rsp+298h+var_1D8], rax
0x1401b5a2c  test    rax, rax
0x1401b5a2f  jz      short loc_1401B5A48
0x1401b5a31  mov     rcx, [rax]
0x1401b5a34  neg     rcx
0x1401b5a37  sbb     rdx, rdx
0x1401b5a3a  and     rdx, rax
0x1401b5a3d  mov     rax, rdx
0x1401b5a40  mov     [rsp+298h+var_1D8], rdx
0x1401b5a48  mov     ebx, 20000000h
0x1401b5a4d  or      [rax+0Ch], ebx
0x1401b5a50  call    ?TraceLoggingGDIScaledAppEvent@@YAXXZ; TraceLoggingGDIScaledAppEvent(void)
0x1401b5a55  jmp     loc_1401B579B
0x1401b5a5a  mov     rbx, rax
0x1401b5a5d  mov     [rsp+298h+var_200], rax
0x1401b5a65  jmp     loc_1401B569B
0x1401b5a6a  movzx   eax, word ptr [rdi]
0x1401b5a6d  cmp     ax, 5Ch ; '\'
0x1401b5a71  jz      short loc_1401B5A89
0x1401b5a73  cmp     ax, 3Ah ; ':'
0x1401b5a77  jz      short loc_1401B5A89
0x1401b5a79  sub     rdi, r14
0x1401b5a7c  mov     [rsp+298h+var_218], rdi
0x1401b5a84  jmp     loc_1401B56A6
0x1401b5a89  add     rdi, r14
0x1401b5a8c  mov     [rsp+298h+var_218], rdi
0x1401b5a94  jmp     loc_1401B56AF
0x1401b5a99  mov     [rsp+298h+var_238], r12d
0x1401b5a9e  mov     [rsp+298h+var_268], r12
0x1401b5aa3  lea     rax, [rsp+298h+var_238]
0x1401b5aa8  mov     [rsp+298h+var_270], rax
0x1401b5aad  mov     dword ptr [rsp+298h+var_278], edi
0x1401b5ab1  xor     r9d, r9d
0x1401b5ab4  lea     r8, aForcedisablegd; "ForceDisableGDIScaling"
0x1401b5abb  mov     edx, edi
0x1401b5abd  xor     ecx, ecx
0x1401b5abf  call    cs:__imp_FastGetProfileDwordEx
0x1401b5ac6  nop     dword ptr [rax+rax+00h]
0x1401b5acb  cmp     [rsp+298h+var_238], r12d
0x1401b5ad0  jbe     loc_1401B5A18
0x1401b5ad6  jmp     loc_1401B59CD
0x1401b5adb  mov     rax, [rsi+200h]
0x1401b5ae2  bts     qword ptr [rax], 1Ch
0x1401b5ae7  jmp     loc_1401B57D3
0x1401b5aec  mov     rax, [rsi+200h]
0x1401b5af3  or      qword ptr [rax+0E0h], 10h
0x1401b5afb  jmp     loc_1401B57E1
0x1401b5b00  mov     rax, [rsi+200h]
0x1401b5b07  or      qword ptr [rax+0E0h], 20h
0x1401b5b0f  jmp     loc_1401B57F0
0x1401b5b14  mov     ecx, 600h
0x1401b5b19  cmp     [rsi+298h], cx
0x1401b5b20  jnb     loc_1401B5800
0x1401b5b26  or      eax, ebx
0x1401b5b28  mov     [rsi+2A8h], eax
0x1401b5b2e  mov     rax, [rsi+200h]
0x1401b5b35  or      [rax+18h], ebx
0x1401b5b38  jmp     loc_1401B5800
0x1401b5b3d  test    byte ptr [rsp+298h+var_230], r15b
0x1401b5b42  jz      short loc_1401B5B62
0x1401b5b44  mov     dword ptr [rsp+298h+Address], 20000h
0x1401b5b4c  mov     r8d, 0D8h
0x1401b5b52  mov     edx, dword ptr [rsp+298h+Address]
0x1401b5b56  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401b5b5d  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401b5b62  call    cs:__imp_ExRaiseAccessViolation
0x1401b5b69  nop     dword ptr [rax+rax+00h]
0x1401b5b6e  nop
0x1401b5b6f  xor     eax, eax
0x1401b5b71  mov     rcx, [rsp+298h+var_48]
0x1401b5b79  xor     rcx, rsp; StackCookie
0x1401b5b7c  call    __security_check_cookie
  ... truncated ...
```
