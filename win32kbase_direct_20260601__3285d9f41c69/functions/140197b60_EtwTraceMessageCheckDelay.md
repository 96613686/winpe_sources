# EtwTraceMessageCheckDelay

- ea: `0x140197b60`
- end: `0x140198496`
- name: `EtwTraceMessageCheckDelay`
- size: `2358`
- prototype: `__int64 __fastcall(struct tagTHREADINFO *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14003804c`

## callees

- `0x1400656b0`
- `0x1400991d0`
- `0x1400c3790`
- `0x1400ff3dc`
- `0x140112db0`
- `0x140114320`
- `0x1401276e4`
- `0x14013b31c`
- `0x14014e008`
- `0x14015b53c`
- `0x140194210`
- `0x140197b60`
- `0x1401a9f9c`
- `0x140238160`
- `0x1402bb164`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x140197ddc`
- `ntoskrnl!PsGetProcessPeb` at `0x140197ddc`
- `ntoskrnl!ProbeForRead` at `0x140197e12`
- `ntoskrnl!ProbeForRead` at `0x140197e47`
- `ntoskrnl!ProbeForRead` at `0x140197ebb`
- `ntoskrnl!ProbeForRead` at `0x140197e12`
- `ntoskrnl!ProbeForRead` at `0x140197e47`
- `ntoskrnl!ProbeForRead` at `0x140197ebb`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140197f37`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140197f37`
- `ntoskrnl!PsGetThreadProcess` at `0x140197dcd`
- `ntoskrnl!PsGetThreadProcess` at `0x140197dcd`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140197fbc`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140197fbc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14019843e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14019845c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14019843e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14019845c`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140198272`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140198272`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140198015`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140198015`
- `WIN32K!W32GetUserSessionState` at `0x140197caf`
- `WIN32K!W32GetUserSessionState` at `0x140197caf`

## pseudocode

```c
void __fastcall EtwTraceMessageCheckDelay(struct tagTHREADINFO *a1, __int64 a2, __int64 a3)
{
  char v4; // al
  int v5; // eax
  unsigned __int64 v6; // rdi
  unsigned int v7; // ebx
  unsigned int ThreadInfoFlags; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  PWSTR Buffer; // r14
  PWSTR v13; // r15
  struct tagWND *v14; // rax
  struct tagWND *v15; // rbx
  struct tagWND *TopLevelWindow; // rax
  PEPROCESS ThreadProcess; // rax
  char *v18; // rbx
  unsigned int ULongFromUser; // edi
  __int64 v20; // r8
  unsigned int v21; // ebx
  __int64 v22; // rdx
  int v23; // r8d
  int v24; // r10d
  __int64 v25; // r13
  const WCHAR *v26; // rdx
  const WCHAR *v27; // rcx
  unsigned int v28; // edi
  int v29; // ecx
  WCHAR *v30; // r8
  int v31; // r10d
  WCHAR *v32; // rax
  WCHAR *v33; // rax
  unsigned int v34; // edi
  int v35; // ecx
  int v36; // r8d
  unsigned int v37; // r9d
  unsigned int v38; // [rsp+90h] [rbp-2B8h] BYREF
  unsigned int v39; // [rsp+94h] [rbp-2B4h] BYREF
  unsigned int v40; // [rsp+98h] [rbp-2B0h] BYREF
  unsigned int v41; // [rsp+9Ch] [rbp-2ACh] BYREF
  int v42; // [rsp+A0h] [rbp-2A8h] BYREF
  unsigned int v43; // [rsp+A4h] [rbp-2A4h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-2A0h] BYREF
  volatile void *Address; // [rsp+B0h] [rbp-298h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-290h] BYREF
  PWSTR v47; // [rsp+C0h] [rbp-288h]
  PWSTR v48; // [rsp+C8h] [rbp-280h]
  __int128 v49; // [rsp+D0h] [rbp-278h] BYREF
  __int64 v50; // [rsp+E0h] [rbp-268h] BYREF
  __int64 v51; // [rsp+E8h] [rbp-260h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-258h] BYREF
  PWSTR v53; // [rsp+F8h] [rbp-250h] BYREF
  PWSTR v54; // [rsp+100h] [rbp-248h] BYREF
  _BYTE *v55; // [rsp+108h] [rbp-240h] BYREF
  PACCESS_TOKEN PrimaryToken[2]; // [rsp+110h] [rbp-238h] BYREF
  __int64 v57; // [rsp+120h] [rbp-228h]
  __int64 v58; // [rsp+128h] [rbp-220h]
  __int128 *v59; // [rsp+130h] [rbp-218h]
  __int64 v60; // [rsp+138h] [rbp-210h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+140h] [rbp-208h] BYREF
  struct _UNICODE_STRING v62; // [rsp+150h] [rbp-1F8h] BYREF
  _BYTE v63[144]; // [rsp+180h] [rbp-1C8h] BYREF
  _BYTE v64[256]; // [rsp+210h] [rbp-138h] BYREF

  v50 = (__int64)a1;
  if ( (W32kEtwEnabledKeyword & 0x8001000000040000uLL) == 0
    || ((unsigned __int8)(byte_140292DD8 - 1) <= 2u
     || (qword_140292DC0 & 0x8001000000040000uLL) == 0
     || (qword_140292DC8 & 0x8001000000040000uLL) != qword_140292DC8
      ? (v4 = 0)
      : (v4 = 1),
        !v4) )
  {
    if ( (unsigned int)dword_140292F90 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_140292F90, 0x40000, a3) )
      return;
  }
  v39 = 0;
  v41 = 0;
  UnicodeString = 0;
  v62 = 0;
  v49 = 0;
  v5 = *((_DWORD *)a1 + 326);
  if ( !v5 )
    return;
  v6 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  v7 = v6 - v5;
  v43 = v6 - v5;
  if ( (unsigned int)(v6 - v5) < 0xC8 )
    return;
  ThreadInfoFlags = EtwpGetThreadInfoFlags(a1);
  v40 = ThreadInfoFlags;
  LOBYTE(v11) = (ThreadInfoFlags & 3) == 0;
  if ( (unsigned __int8)v11 | ((ThreadInfoFlags & 0x28) == 0) )
    return;
  if ( (ThreadInfoFlags & 0x200) != 0 )
  {
    LOBYTE(v9) = v11 | ((ThreadInfoFlags & 0x28) == 0);
    if ( v7 < *(_DWORD *)(W32GetUserSessionState(v11, v9, v10) + 69104) )
      return;
  }
  Buffer = 0;
  v48 = 0;
  v13 = 0;
  v47 = 0;
  v14 = (struct tagWND *)ValidateHwndEx(*((_QWORD *)a1 + 164), 1, 0);
  v15 = v14;
  if ( v14 )
  {
    if ( EtwpGetClassName(v14, &UnicodeString) >= 0 )
      Buffer = UnicodeString.Buffer;
    v48 = Buffer;
    if ( (int)Is_GetTopLevelWindowSupported() < 0 )
      TopLevelWindow = 0;
    else
      TopLevelWindow = (struct tagWND *)GetTopLevelWindow(v15);
    if ( TopLevelWindow )
    {
      if ( v15 == TopLevelWindow )
      {
        v13 = Buffer;
        v47 = Buffer;
      }
      else if ( EtwpGetClassName(TopLevelWindow, &v62) >= 0 )
      {
        v13 = v62.Buffer;
        v47 = v62.Buffer;
      }
    }
  }
  EtwpGetLastInputProcessTime(*((struct tagQ *const *)a1 + 58), v6, &v39, &v41, 0, 0);
  v38 = *((_DWORD *)a1 + 330);
  v42 = v38;
  v44 = *((_QWORD *)a1 + 166);
  v51 = v44;
  v46 = 0;
  ThreadProcess = PsGetThreadProcess(*(PETHREAD *)a1);
  Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
  v57 = 1;
  ProbeForRead(Address, 1u, 1u);
  v18 = (char *)*((_QWORD *)Address + 4);
  v58 = 1;
  ProbeForRead(v18, 1u, 1u);
  *(_OWORD *)PrimaryToken = 0;
  ULongFromUser = RtlReadULongFromUser(v18 + 96);
  LODWORD(PrimaryToken[0]) = ULongFromUser;
  PrimaryToken[1] = (PACCESS_TOKEN)RtlReadULong64FromUser(v18 + 104);
  *(_QWORD *)&v49 = __PAIR64__(HIDWORD(PrimaryToken[0]), ULongFromUser);
  *((PACCESS_TOKEN *)&v49 + 1) = PrimaryToken[1];
  ProbeForRead(PrimaryToken[1], (unsigned __int16)ULongFromUser + 2LL, 2u);
  if ( (unsigned __int16)v49 > WORD1(v49) )
  {
    if ( (v49 & 1) == 0 )
      goto LABEL_31;
    goto LABEL_30;
  }
  if ( (v49 & 1) != 0 )
  {
LABEL_30:
    v38 = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 896);
LABEL_31:
    ExRaiseAccessViolation();
  }
  v59 = &v49;
  v21 = v43;
  if ( &v49 )
    v46 = *((_QWORD *)&v49 + 1);
  v22 = *((_QWORD *)a1 + 57);
  if ( (*(_BYTE *)(v22 + 808) & 0x30) == 0x10 )
  {
    PrimaryToken[0] = PsReferencePrimaryToken(*(PEPROCESS *)v22);
    v50 = 256;
    v51 = 130;
    v24 = RtlQueryPackageIdentity(PrimaryToken[0], v64, &v50, v63, &v51, 0);
    v42 = v24;
    v25 = v44;
    if ( (Microsoft_Windows_Win32kEnableBits & 0x100) != 0 )
    {
      v26 = (const WCHAR *)v63;
      if ( v24 < 0 )
        v26 = &word_1402558A8;
      v27 = (const WCHAR *)v64;
      if ( v24 < 0 )
        v27 = &word_1402558A8;
      v28 = v40;
      McTemplateK0qqqqzzzzqx_EtwWriteTransfer(
        (_DWORD)v27,
        (_DWORD)v26,
        v23,
        v40,
        v21,
        v39,
        v41,
        (__int64)Buffer,
        (__int64)v13,
        (__int64)v27,
        (__int64)v26,
        v38,
        v44);
    }
    else
    {
      v28 = v40;
    }
    if ( (unsigned int)dword_140292F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140292F90, 0x40000, &word_1402558A8) )
    {
      v44 = 0x1000000;
      v42 = 2;
      v43 = 1;
      v60 = v25;
      v52 = (__int64)v13;
      v53 = Buffer;
      v32 = (WCHAR *)v63;
      if ( v31 < 0 )
        v32 = v30;
      v54 = v32;
      v33 = (WCHAR *)v64;
      if ( v31 < 0 )
        v33 = v30;
      v55 = v33;
      v40 = v41;
      v41 = v21;
      LODWORD(Address) = v28;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v29,
        (unsigned int)&unk_14026F408,
        (_DWORD)v30,
        v38,
        (__int64)&Address,
        (__int64)&v41,
        (__int64)&v39,
        (__int64)&v40,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v46,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v38,
        (__int64)&v60,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v44);
    }
    PsDereferencePrimaryToken(PrimaryToken[0]);
  }
  else
  {
    v34 = v40;
    if ( (Microsoft_Windows_Win32kEnableBits & 0x100) != 0 )
      McTemplateK0qqqqzzzqx_EtwWriteTransfer(
        v44,
        v22,
        v20,
        v40,
        v43,
        v39,
        v41,
        (__int64)Buffer,
        (__int64)v13,
        v46,
        v38,
        v44);
    if ( (unsigned int)dword_140292F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140292F90, 0x40000, v20) )
    {
      PrimaryToken[0] = (PACCESS_TOKEN)0x1000000;
      LODWORD(Address) = 1;
      v55 = (_BYTE *)v44;
      v37 = v38;
      v42 = v38;
      v54 = v13;
      v53 = Buffer;
      v52 = v46;
      v43 = v41;
      v38 = v39;
      v40 = v21;
      v39 = v34;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v35,
        (unsigned int)byte_14026F331,
        v36,
        v37,
        (__int64)&v39,
        (__int64)&v40,
        (__int64)&v38,
        (__int64)&v43,
        (__int64)&v52,
        (__int64)&v53,
        (__int64)&v54,
        (__int64)&v42,
        (__int64)&v55,
        (__int64)&Address,
        (__int64)PrimaryToken);
    }
  }
  if ( Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v13 )
  {
    if ( Buffer != v13 )
      RtlFreeUnicodeString(&v62);
  }
}

```

## disassembly

```asm
0x140197b60  mov     [rsp+arg_8], rbx
0x140197b65  mov     [rsp+arg_10], rsi
0x140197b6a  push    rdi
0x140197b6b  push    r12
0x140197b6d  push    r13
0x140197b6f  push    r14
0x140197b71  push    r15
0x140197b73  sub     rsp, 320h
0x140197b7a  mov     rax, cs:__security_cookie
0x140197b81  xor     rax, rsp
0x140197b84  mov     [rsp+348h+var_38], rax
0x140197b8c  mov     r13, rcx
0x140197b8f  mov     [rsp+348h+var_268], rcx
0x140197b97  mov     rdx, 8001000000040000h
0x140197ba1  mov     r12d, 1
0x140197ba7  test    cs:W32kEtwEnabledKeyword, rdx
0x140197bae  jz      short loc_140197BEB
0x140197bb0  mov     al, cs:byte_140292DD8
0x140197bb6  sub     al, r12b
0x140197bb9  cmp     al, 2
0x140197bbb  jbe     short loc_140197BE0
0x140197bbd  test    cs:qword_140292DC0, rdx
0x140197bc4  jz      short loc_140197BE0
0x140197bc6  mov     rax, cs:qword_140292DC8
0x140197bcd  and     rax, rdx
0x140197bd0  cmp     rax, cs:qword_140292DC8
0x140197bd7  jnz     short loc_140197BE0
0x140197bd9  mov     al, r12b
0x140197bdc  xor     esi, esi
0x140197bde  jmp     short loc_140197BE5
0x140197be0  xor     esi, esi
0x140197be2  mov     al, sil
0x140197be5  test    al, al
0x140197be7  jz      short loc_140197BED
0x140197be9  jmp     short loc_140197C15
0x140197beb  xor     esi, esi
0x140197bed  mov     eax, cs:dword_140292F90
0x140197bf3  cmp     eax, 5
0x140197bf6  jbe     loc_140198468
0x140197bfc  mov     edx, 40000h
0x140197c01  lea     rcx, dword_140292F90
0x140197c08  call    _tlgKeywordOn
0x140197c0d  test    al, al
0x140197c0f  jz      loc_140198468
0x140197c15  mov     [rsp+348h+var_2B4], esi
0x140197c1c  mov     [rsp+348h+var_2AC], esi
0x140197c23  xorps   xmm0, xmm0
0x140197c26  movups  xmmword ptr [rsp+348h+UnicodeString.Length], xmm0
0x140197c2e  xorps   xmm1, xmm1
0x140197c31  movups  xmmword ptr [rsp+348h+var_1F8.Length], xmm1
0x140197c39  movups  [rsp+348h+var_278], xmm0
0x140197c41  mov     rcx, 0FFFFF78000000320h
0x140197c4b  mov     rcx, [rcx]
0x140197c4e  mov     eax, [r13+518h]
0x140197c55  test    eax, eax
0x140197c57  jz      loc_140198468
0x140197c5d  mov     rdx, 0FFFFF78000000004h
0x140197c67  mov     edi, [rdx]
0x140197c69  imul    rdi, rcx
0x140197c6d  shr     rdi, 18h
0x140197c71  mov     ebx, edi
0x140197c73  sub     ebx, eax
0x140197c75  mov     [rsp+348h+var_2A4], ebx
0x140197c7c  cmp     ebx, 0C8h
0x140197c82  jb      loc_140198468
0x140197c88  mov     rcx, r13; struct tagTHREADINFO *
0x140197c8b  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x140197c90  mov     [rsp+348h+var_2B0], eax
0x140197c97  test    al, 28h
0x140197c99  setz    dl
0x140197c9c  test    al, 3
0x140197c9e  setz    cl
0x140197ca1  or      dl, cl
0x140197ca3  jnz     loc_140198468
0x140197ca9  bt      eax, 9
0x140197cad  jnb     short loc_140197CC7
0x140197caf  call    cs:__imp_W32GetUserSessionState
0x140197cb6  nop     dword ptr [rax+rax+00h]
0x140197cbb  cmp     ebx, [rax+10DF0h]
0x140197cc1  jb      loc_140198468
0x140197cc7  mov     r14, rsi
0x140197cca  mov     [rsp+348h+var_280], rsi
0x140197cd2  mov     r15, rsi
0x140197cd5  mov     [rsp+348h+var_288], rsi
0x140197cdd  xor     r8d, r8d
0x140197ce0  mov     edx, r12d
0x140197ce3  mov     rcx, [r13+520h]
0x140197cea  call    ValidateHwndEx
0x140197cef  mov     rbx, rax
0x140197cf2  test    rax, rax
0x140197cf5  jz      short loc_140197D6B
0x140197cf7  lea     rdx, [rsp+348h+UnicodeString]; struct _UNICODE_STRING *
0x140197cff  mov     rcx, rax; struct tagWND *
0x140197d02  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x140197d07  test    eax, eax
0x140197d09  cmovns  r14, [rsp+348h+UnicodeString.Buffer]
0x140197d12  mov     [rsp+348h+var_280], r14
0x140197d1a  call    Is_GetTopLevelWindowSupported
0x140197d1f  test    eax, eax
0x140197d21  js      short loc_140197D2D
0x140197d23  mov     rcx, rbx
0x140197d26  call    _GetTopLevelWindow
0x140197d2b  jmp     short loc_140197D30
0x140197d2d  mov     rax, rsi
0x140197d30  test    rax, rax
0x140197d33  jz      short loc_140197D6B
0x140197d35  cmp     rbx, rax
0x140197d38  jz      short loc_140197D60
0x140197d3a  lea     rdx, [rsp+348h+var_1F8]; struct _UNICODE_STRING *
0x140197d42  mov     rcx, rax; struct tagWND *
0x140197d45  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x140197d4a  test    eax, eax
0x140197d4c  js      short loc_140197D6B
0x140197d4e  mov     r15, [rsp+348h+var_1F8.Buffer]
0x140197d56  mov     [rsp+348h+var_288], r15
0x140197d5e  jmp     short loc_140197D6B
0x140197d60  mov     r15, r14
0x140197d63  mov     [rsp+348h+var_288], r14
0x140197d6b  mov     [rsp+348h+var_320], rsi; unsigned __int64 *
0x140197d70  mov     [rsp+348h+var_328], rsi; unsigned int *
0x140197d75  lea     r9, [rsp+348h+var_2AC]; unsigned int *
0x140197d7d  lea     r8, [rsp+348h+var_2B4]; unsigned int *
0x140197d85  mov     edx, edi; unsigned int
0x140197d87  mov     rcx, [r13+1D0h]; struct tagQ *
0x140197d8e  call    ?EtwpGetLastInputProcessTime@@YAXQEAUtagQ@@KPEAK1PEAIPEA_K@Z; EtwpGetLastInputProcessTime(tagQ * const,ulong,ulong *,ulong *,uint *,unsigned __int64 *)
0x140197d93  mov     r9d, [r13+528h]
0x140197d9a  mov     [rsp+348h+var_2B8], r9d
0x140197da2  mov     [rsp+348h+var_2A8], r9d
0x140197daa  mov     rax, [r13+530h]
0x140197db1  mov     [rsp+348h+var_2A0], rax
0x140197db9  mov     [rsp+348h+var_260], rax
0x140197dc1  mov     [rsp+348h+var_290], rsi
0x140197dc9  mov     rcx, [r13+0]; Thread
0x140197dcd  call    cs:__imp_PsGetThreadProcess
0x140197dd4  nop     dword ptr [rax+rax+00h]
0x140197dd9  mov     rcx, rax
0x140197ddc  call    cs:__imp_PsGetProcessPeb
0x140197de3  nop     dword ptr [rax+rax+00h]
0x140197de8  mov     [rsp+348h+Address], rax
0x140197df0  mov     [rsp+348h+var_228], 7D0h
0x140197dfc  mov     rcx, [rsp+348h+Address]; Address
0x140197e04  mov     [rsp+348h+var_228], r12
0x140197e0c  mov     r8d, r12d; Alignment
0x140197e0f  mov     rdx, r12; Length
0x140197e12  call    cs:__imp_ProbeForRead
0x140197e19  nop     dword ptr [rax+rax+00h]
0x140197e1e  mov     rax, [rsp+348h+Address]
0x140197e26  mov     rbx, [rax+20h]
0x140197e2a  mov     [rsp+348h+var_220], 450h
0x140197e36  mov     [rsp+348h+var_220], r12
0x140197e3e  mov     r8d, r12d; Alignment
0x140197e41  mov     rdx, r12; Length
0x140197e44  mov     rcx, rbx; Address
0x140197e47  call    cs:__imp_ProbeForRead
0x140197e4e  nop     dword ptr [rax+rax+00h]
0x140197e53  xorps   xmm0, xmm0
0x140197e56  movups  xmmword ptr [rsp+348h+PrimaryToken], xmm0
0x140197e5e  lea     rcx, [rbx+60h]
0x140197e62  call    RtlReadULongFromUser
0x140197e67  mov     edi, eax
0x140197e69  mov     dword ptr [rsp+348h+PrimaryToken], edi
0x140197e70  lea     rcx, [rbx+68h]
0x140197e74  call    RtlReadULong64FromUser
0x140197e79  mov     [rsp+348h+PrimaryToken+8], rax
0x140197e81  movzx   edx, di
0x140197e84  mov     word ptr [rsp+348h+var_278], dx
0x140197e8c  shr     edi, 10h
0x140197e8f  mov     word ptr [rsp+348h+var_278+2], di
0x140197e97  mov     ecx, dword ptr [rsp+348h+PrimaryToken+4]
0x140197e9e  mov     dword ptr [rsp+348h+var_278+4], ecx
0x140197ea5  mov     qword ptr [rsp+348h+var_278+8], rax
0x140197ead  mov     edi, 2
0x140197eb2  add     rdx, rdi; Length
0x140197eb5  mov     r8d, edi; Alignment
0x140197eb8  mov     rcx, rax; Address
0x140197ebb  call    cs:__imp_ProbeForRead
0x140197ec2  nop     dword ptr [rax+rax+00h]
0x140197ec7  movzx   eax, word ptr [rsp+348h+var_278]
0x140197ecf  cmp     ax, word ptr [rsp+348h+var_278+2]
0x140197ed7  ja      short loc_140197F09
0x140197ed9  test    r12b, al
0x140197edc  jnz     short loc_140197F13
0x140197ede  lea     rax, [rsp+348h+var_278]
0x140197ee6  mov     [rsp+348h+var_218], rax
0x140197eee  mov     ebx, [rsp+348h+var_2A4]
0x140197ef5  mov     edi, [rsp+348h+var_2B8]
0x140197efc  mov     rcx, [rsp+348h+var_2A0]
0x140197f04  jmp     loc_140197F91
0x140197f09  test    byte ptr [rsp+348h+var_278], r12b
0x140197f11  jz      short loc_140197F37
0x140197f13  mov     [rsp+348h+var_2B8], 20000h
0x140197f1e  mov     r8d, 380h
0x140197f24  mov     edx, [rsp+348h+var_2B8]
0x140197f2b  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140197f32  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140197f37  call    cs:__imp_ExRaiseAccessViolation
0x140197f3e  nop     dword ptr [rax+rax+00h]
0x140197f43  nop
0x140197f44  xor     eax, eax
0x140197f46  mov     [rsp+348h+var_218], rax
0x140197f4e  xor     esi, esi
0x140197f50  lea     r12d, [rax+1]
0x140197f54  mov     r14, [rsp+348h+var_280]
0x140197f5c  mov     r15, [rsp+348h+var_288]
0x140197f64  mov     r13, [rsp+348h+var_268]
0x140197f6c  mov     edi, [rsp+348h+var_2A8]
0x140197f73  mov     [rsp+348h+var_2B8], edi
0x140197f7a  mov     rcx, [rsp+348h+var_260]
0x140197f82  mov     [rsp+348h+var_2A0], rcx
0x140197f8a  mov     ebx, [rsp+348h+var_2A4]
0x140197f91  test    rax, rax
0x140197f94  jz      short loc_140197FA2
0x140197f96  mov     rax, [rax+8]
0x140197f9a  mov     [rsp+348h+var_290], rax
0x140197fa2  mov     rdx, [r13+1C8h]
0x140197fa9  mov     al, [rdx+328h]
0x140197faf  and     al, 30h
0x140197fb1  cmp     al, 10h
0x140197fb3  jnz     loc_140198283
0x140197fb9  mov     rcx, [rdx]; Process
0x140197fbc  call    cs:__imp_PsReferencePrimaryToken
0x140197fc3  nop     dword ptr [rax+rax+00h]
0x140197fc8  mov     [rsp+348h+PrimaryToken], rax
0x140197fd0  mov     [rsp+348h+var_268], 100h
0x140197fdc  mov     [rsp+348h+var_260], 82h
0x140197fe8  mov     [rsp+348h+var_320], rsi
0x140197fed  lea     rcx, [rsp+348h+var_260]
0x140197ff5  mov     [rsp+348h+var_328], rcx
0x140197ffa  lea     r9, [rsp+348h+var_1C8]
0x140198002  lea     r8, [rsp+348h+var_268]
0x14019800a  lea     rdx, [rsp+348h+var_138]
0x140198012  mov     rcx, rax
0x140198015  call    cs:__imp_RtlQueryPackageIdentity
0x14019801c  nop     dword ptr [rax+rax+00h]
0x140198021  mov     r10d, eax
0x140198024  mov     [rsp+348h+var_2A8], eax
0x14019802b  mov     r13, [rsp+348h+var_2A0]
0x140198033  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, r12b
0x14019803a  jz      short loc_1401980AE
0x14019803c  lea     rax, word_1402558A8
0x140198043  lea     rdx, [rsp+348h+var_1C8]
0x14019804b  test    r10d, r10d
0x14019804e  cmovs   rdx, rax
0x140198052  lea     rcx, [rsp+348h+var_138]
0x14019805a  cmovs   rcx, rax
0x14019805e  mov     [rsp+348h+var_2E8], r13
0x140198063  mov     dword ptr [rsp+348h+var_2F0], edi
0x140198067  mov     [rsp+348h+var_2F8], rdx
0x14019806c  mov     [rsp+348h+var_300], rcx
0x140198071  mov     [rsp+348h+var_308], r15
0x140198076  mov     [rsp+348h+var_310], r14
0x14019807b  mov     eax, [rsp+348h+var_2AC]
0x140198082  mov     dword ptr [rsp+348h+var_318], eax
0x140198086  mov     eax, [rsp+348h+var_2B4]
0x14019808d  mov     dword ptr [rsp+348h+var_320], eax
0x140198091  mov     dword ptr [rsp+348h+var_328], ebx
0x140198095  mov     edi, [rsp+348h+var_2B0]
0x14019809c  mov     r9d, edi
0x14019809f  call    McTemplateK0qqqqzzzzqx_EtwWriteTransfer
0x1401980a4  mov     r10d, [rsp+348h+var_2A8]
0x1401980ac  jmp     short loc_1401980B5
0x1401980ae  mov     edi, [rsp+348h+var_2B0]
0x1401980b5  lea     r8, word_1402558A8
0x1401980bc  mov     eax, cs:dword_140292F90
0x1401980c2  cmp     eax, 5
0x1401980c5  jbe     loc_140198258
0x1401980cb  mov     edx, 40000h
0x1401980d0  lea     rcx, dword_140292F90
0x1401980d7  call    _tlgKeywordOn
0x1401980dc  test    al, al
0x1401980de  jz      loc_140198258
0x1401980e4  mov     [rsp+348h+var_2A0], 1000000h
0x1401980f0  mov     [rsp+348h+var_2A8], 2
0x1401980fb  mov     [rsp+348h+var_2A4], r12d
0x140198103  mov     [rsp+348h+var_210], r13
0x14019810b  mov     r9d, [rsp+348h+var_2B8]
0x140198113  mov     [rsp+348h+var_2B8], r9d
0x14019811b  mov     [rsp+348h+var_258], r15
0x140198123  mov     [rsp+348h+var_250], r14
0x14019812b  mov     rax, [rsp+348h+var_290]
0x140198133  mov     [rsp+348h+var_290], rax
0x14019813b  lea     rax, [rsp+348h+var_1C8]
0x140198143  test    r10d, r10d
0x140198146  cmovs   rax, r8
0x14019814a  mov     [rsp+348h+var_248], rax
0x140198152  lea     rax, [rsp+348h+var_138]
0x14019815a  cmovs   rax, r8
0x14019815e  mov     [rsp+348h+var_240], rax
0x140198166  mov     eax, [rsp+348h+var_2AC]
0x14019816d  mov     [rsp+348h+var_2B0], eax
0x140198174  mov     eax, [rsp+348h+var_2B4]
0x14019817b  mov     [rsp+348h+var_2B4], eax
0x140198182  mov     [rsp+348h+var_2AC], ebx
0x140198189  mov     dword ptr [rsp+348h+Address], edi
0x140198190  lea     rax, [rsp+348h+var_2A0]
0x140198198  mov     [rsp+348h+var_2C0], rax
0x1401981a0  lea     rax, [rsp+348h+var_2A8]
0x1401981a8  mov     [rsp+348h+var_2C8], rax
0x1401981b0  lea     rax, [rsp+348h+var_2A4]
0x1401981b8  mov     [rsp+348h+var_2D0], rax
  ... truncated ...
```
