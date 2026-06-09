# EtwTraceMessageCheckDelay

- ea: `0x140197af0`
- end: `0x140198426`
- name: `EtwTraceMessageCheckDelay`
- size: `2358`
- prototype: `__int64 __fastcall(struct tagTHREADINFO *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14002edcc`

## callees

- `0x140067c00`
- `0x140067c3c`
- `0x1400a23d0`
- `0x1400dcc90`
- `0x140103b6c`
- `0x140113280`
- `0x1401147f0`
- `0x140127684`
- `0x14013ad3c`
- `0x14014d558`
- `0x1401940e0`
- `0x140197af0`
- `0x1401aa4fc`
- `0x140238b10`
- `0x1402bd208`
- `0x1402bd244`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x140197d6c`
- `ntoskrnl!PsGetProcessPeb` at `0x140197d6c`
- `ntoskrnl!ProbeForRead` at `0x140197da2`
- `ntoskrnl!ProbeForRead` at `0x140197dd7`
- `ntoskrnl!ProbeForRead` at `0x140197e4b`
- `ntoskrnl!ProbeForRead` at `0x140197da2`
- `ntoskrnl!ProbeForRead` at `0x140197dd7`
- `ntoskrnl!ProbeForRead` at `0x140197e4b`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140197ec7`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140197ec7`
- `ntoskrnl!PsGetThreadProcess` at `0x140197d5d`
- `ntoskrnl!PsGetThreadProcess` at `0x140197d5d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140197f4c`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140197f4c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401983ce`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401983ec`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401983ce`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401983ec`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140198202`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140198202`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140197fa5`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140197fa5`
- `WIN32K!W32GetUserSessionState` at `0x140197c3f`
- `WIN32K!W32GetUserSessionState` at `0x140197c3f`

## pseudocode

```c
void __fastcall EtwTraceMessageCheckDelay(struct tagTHREADINFO *a1)
{
  char v2; // al
  int v3; // eax
  unsigned __int64 v4; // rdi
  unsigned int v5; // ebx
  unsigned int ThreadInfoFlags; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  PWSTR Buffer; // r14
  PWSTR v11; // r15
  struct tagWND *v12; // rax
  struct tagWND *v13; // rbx
  struct tagWND *TopLevelWindow; // rax
  PEPROCESS ThreadProcess; // rax
  char *v16; // rbx
  unsigned int ULongFromUser; // edi
  int v18; // r8d
  unsigned int v19; // ebx
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // r10d
  __int64 v23; // r13
  const WCHAR *v24; // rdx
  const WCHAR *v25; // rcx
  unsigned int v26; // edi
  int v27; // ecx
  WCHAR *v28; // r8
  int v29; // r10d
  WCHAR *v30; // rax
  WCHAR *v31; // rax
  unsigned int v32; // edi
  int v33; // ecx
  int v34; // r8d
  unsigned int v35; // r9d
  unsigned int v36; // [rsp+90h] [rbp-2B8h] BYREF
  unsigned int v37; // [rsp+94h] [rbp-2B4h] BYREF
  unsigned int v38; // [rsp+98h] [rbp-2B0h] BYREF
  unsigned int v39; // [rsp+9Ch] [rbp-2ACh] BYREF
  int v40; // [rsp+A0h] [rbp-2A8h] BYREF
  unsigned int v41; // [rsp+A4h] [rbp-2A4h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-2A0h] BYREF
  volatile void *Address; // [rsp+B0h] [rbp-298h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-290h] BYREF
  PWSTR v45; // [rsp+C0h] [rbp-288h]
  PWSTR v46; // [rsp+C8h] [rbp-280h]
  __int128 v47; // [rsp+D0h] [rbp-278h] BYREF
  __int64 v48; // [rsp+E0h] [rbp-268h] BYREF
  __int64 v49; // [rsp+E8h] [rbp-260h] BYREF
  __int64 v50; // [rsp+F0h] [rbp-258h] BYREF
  PWSTR v51; // [rsp+F8h] [rbp-250h] BYREF
  PWSTR v52; // [rsp+100h] [rbp-248h] BYREF
  _BYTE *v53; // [rsp+108h] [rbp-240h] BYREF
  PACCESS_TOKEN PrimaryToken[2]; // [rsp+110h] [rbp-238h] BYREF
  __int64 v55; // [rsp+120h] [rbp-228h]
  __int64 v56; // [rsp+128h] [rbp-220h]
  __int128 *v57; // [rsp+130h] [rbp-218h]
  __int64 v58; // [rsp+138h] [rbp-210h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+140h] [rbp-208h] BYREF
  struct _UNICODE_STRING v60; // [rsp+150h] [rbp-1F8h] BYREF
  _BYTE v61[144]; // [rsp+180h] [rbp-1C8h] BYREF
  _BYTE v62[256]; // [rsp+210h] [rbp-138h] BYREF

  v48 = (__int64)a1;
  if ( (W32kEtwEnabledKeyword & 0x8001000000040000uLL) == 0
    || ((unsigned __int8)(byte_140294DD8 - 1) <= 2u
     || (qword_140294DC0 & 0x8001000000040000uLL) == 0
     || (qword_140294DC8 & 0x8001000000040000uLL) != qword_140294DC8
      ? (v2 = 0)
      : (v2 = 1),
        !v2) )
  {
    if ( (unsigned int)dword_140294F90 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_140294F90, 0x40000) )
      return;
  }
  v37 = 0;
  v39 = 0;
  UnicodeString = 0;
  v60 = 0;
  v47 = 0;
  v3 = *((_DWORD *)a1 + 326);
  if ( !v3 )
    return;
  v4 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  v5 = v4 - v3;
  v41 = v4 - v3;
  if ( (unsigned int)(v4 - v3) < 0xC8 )
    return;
  ThreadInfoFlags = EtwpGetThreadInfoFlags(a1);
  v38 = ThreadInfoFlags;
  LOBYTE(v9) = (ThreadInfoFlags & 3) == 0;
  if ( (unsigned __int8)v9 | ((ThreadInfoFlags & 0x28) == 0) )
    return;
  if ( (ThreadInfoFlags & 0x200) != 0 )
  {
    LOBYTE(v7) = v9 | ((ThreadInfoFlags & 0x28) == 0);
    if ( v5 < *(_DWORD *)(W32GetUserSessionState(v9, v7, v8) + 69104) )
      return;
  }
  Buffer = 0;
  v46 = 0;
  v11 = 0;
  v45 = 0;
  v12 = (struct tagWND *)ValidateHwndEx(*((_QWORD *)a1 + 164), 1, 0);
  v13 = v12;
  if ( v12 )
  {
    if ( EtwpGetClassName(v12, &UnicodeString) >= 0 )
      Buffer = UnicodeString.Buffer;
    v46 = Buffer;
    if ( (int)Is_GetTopLevelWindowSupported() < 0 )
      TopLevelWindow = 0;
    else
      TopLevelWindow = (struct tagWND *)GetTopLevelWindow(v13);
    if ( TopLevelWindow )
    {
      if ( v13 == TopLevelWindow )
      {
        v11 = Buffer;
        v45 = Buffer;
      }
      else if ( EtwpGetClassName(TopLevelWindow, &v60) >= 0 )
      {
        v11 = v60.Buffer;
        v45 = v60.Buffer;
      }
    }
  }
  EtwpGetLastInputProcessTime(*((struct tagQ *const *)a1 + 58), v4, &v37, &v39, 0, 0);
  v36 = *((_DWORD *)a1 + 330);
  v40 = v36;
  v42 = *((_QWORD *)a1 + 166);
  v49 = v42;
  v44 = 0;
  ThreadProcess = PsGetThreadProcess(*(PETHREAD *)a1);
  Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
  v55 = 1;
  ProbeForRead(Address, 1u, 1u);
  v16 = (char *)*((_QWORD *)Address + 4);
  v56 = 1;
  ProbeForRead(v16, 1u, 1u);
  *(_OWORD *)PrimaryToken = 0;
  ULongFromUser = RtlReadULongFromUser(v16 + 96);
  LODWORD(PrimaryToken[0]) = ULongFromUser;
  PrimaryToken[1] = (PACCESS_TOKEN)RtlReadULong64FromUser(v16 + 104);
  *(_QWORD *)&v47 = __PAIR64__(HIDWORD(PrimaryToken[0]), ULongFromUser);
  *((PACCESS_TOKEN *)&v47 + 1) = PrimaryToken[1];
  ProbeForRead(PrimaryToken[1], (unsigned __int16)ULongFromUser + 2LL, 2u);
  if ( (unsigned __int16)v47 > WORD1(v47) )
  {
    if ( (v47 & 1) == 0 )
      goto LABEL_31;
    goto LABEL_30;
  }
  if ( (v47 & 1) != 0 )
  {
LABEL_30:
    v36 = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 896);
LABEL_31:
    ExRaiseAccessViolation();
  }
  v57 = &v47;
  v19 = v41;
  if ( &v47 )
    v44 = *((_QWORD *)&v47 + 1);
  v20 = *((_QWORD *)a1 + 57);
  if ( (*(_BYTE *)(v20 + 808) & 0x30) == 0x10 )
  {
    PrimaryToken[0] = PsReferencePrimaryToken(*(PEPROCESS *)v20);
    v48 = 256;
    v49 = 130;
    v22 = RtlQueryPackageIdentity(PrimaryToken[0], v62, &v48, v61, &v49, 0);
    v40 = v22;
    v23 = v42;
    if ( (Microsoft_Windows_Win32kEnableBits & 0x100) != 0 )
    {
      v24 = (const WCHAR *)v61;
      if ( v22 < 0 )
        v24 = &word_140257388;
      v25 = (const WCHAR *)v62;
      if ( v22 < 0 )
        v25 = &word_140257388;
      v26 = v38;
      McTemplateK0qqqqzzzzqx_EtwWriteTransfer(
        (_DWORD)v25,
        (_DWORD)v24,
        v21,
        v38,
        v19,
        v37,
        v39,
        (__int64)Buffer,
        (__int64)v11,
        (__int64)v25,
        (__int64)v24,
        v36,
        v42);
    }
    else
    {
      v26 = v38;
    }
    if ( (unsigned int)dword_140294F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140294F90, 0x40000) )
    {
      v42 = 0x1000000;
      v40 = 2;
      v41 = 1;
      v58 = v23;
      v50 = (__int64)v11;
      v51 = Buffer;
      v30 = (WCHAR *)v61;
      if ( v29 < 0 )
        v30 = v28;
      v52 = v30;
      v31 = (WCHAR *)v62;
      if ( v29 < 0 )
        v31 = v28;
      v53 = v31;
      v38 = v39;
      v39 = v19;
      LODWORD(Address) = v26;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v27,
        (unsigned int)&unk_140270588,
        (_DWORD)v28,
        v36,
        (__int64)&Address,
        (__int64)&v39,
        (__int64)&v37,
        (__int64)&v38,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v44,
        (__int64)&v51,
        (__int64)&v50,
        (__int64)&v36,
        (__int64)&v58,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v42);
    }
    PsDereferencePrimaryToken(PrimaryToken[0]);
  }
  else
  {
    v32 = v38;
    if ( (Microsoft_Windows_Win32kEnableBits & 0x100) != 0 )
      McTemplateK0qqqqzzzqx_EtwWriteTransfer(
        v42,
        v20,
        v18,
        v38,
        v41,
        v37,
        v39,
        (__int64)Buffer,
        (__int64)v11,
        v44,
        v36,
        v42);
    if ( (unsigned int)dword_140294F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140294F90, 0x40000) )
    {
      PrimaryToken[0] = (PACCESS_TOKEN)0x1000000;
      LODWORD(Address) = 1;
      v53 = (_BYTE *)v42;
      v35 = v36;
      v40 = v36;
      v52 = v11;
      v51 = Buffer;
      v50 = v44;
      v41 = v39;
      v36 = v37;
      v38 = v19;
      v37 = v32;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v33,
        (unsigned int)byte_1402704B1,
        v34,
        v35,
        (__int64)&v37,
        (__int64)&v38,
        (__int64)&v36,
        (__int64)&v41,
        (__int64)&v50,
        (__int64)&v51,
        (__int64)&v52,
        (__int64)&v40,
        (__int64)&v53,
        (__int64)&Address,
        (__int64)PrimaryToken);
    }
  }
  if ( Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v11 )
  {
    if ( Buffer != v11 )
      RtlFreeUnicodeString(&v60);
  }
}

```

## disassembly

```asm
0x140197af0  mov     [rsp+arg_8], rbx
0x140197af5  mov     [rsp+arg_10], rsi
0x140197afa  push    rdi
0x140197afb  push    r12
0x140197afd  push    r13
0x140197aff  push    r14
0x140197b01  push    r15
0x140197b03  sub     rsp, 320h
0x140197b0a  mov     rax, cs:__security_cookie
0x140197b11  xor     rax, rsp
0x140197b14  mov     [rsp+348h+var_38], rax
0x140197b1c  mov     r13, rcx
0x140197b1f  mov     [rsp+348h+var_268], rcx
0x140197b27  mov     rdx, 8001000000040000h
0x140197b31  mov     r12d, 1
0x140197b37  test    cs:W32kEtwEnabledKeyword, rdx
0x140197b3e  jz      short loc_140197B7B
0x140197b40  mov     al, cs:byte_140294DD8
0x140197b46  sub     al, r12b
0x140197b49  cmp     al, 2
0x140197b4b  jbe     short loc_140197B70
0x140197b4d  test    cs:qword_140294DC0, rdx
0x140197b54  jz      short loc_140197B70
0x140197b56  mov     rax, cs:qword_140294DC8
0x140197b5d  and     rax, rdx
0x140197b60  cmp     rax, cs:qword_140294DC8
0x140197b67  jnz     short loc_140197B70
0x140197b69  mov     al, r12b
0x140197b6c  xor     esi, esi
0x140197b6e  jmp     short loc_140197B75
0x140197b70  xor     esi, esi
0x140197b72  mov     al, sil
0x140197b75  test    al, al
0x140197b77  jz      short loc_140197B7D
0x140197b79  jmp     short loc_140197BA5
0x140197b7b  xor     esi, esi
0x140197b7d  mov     eax, cs:dword_140294F90
0x140197b83  cmp     eax, 5
0x140197b86  jbe     loc_1401983F8
0x140197b8c  mov     edx, 40000h
0x140197b91  lea     rcx, dword_140294F90
0x140197b98  call    _tlgKeywordOn
0x140197b9d  test    al, al
0x140197b9f  jz      loc_1401983F8
0x140197ba5  mov     [rsp+348h+var_2B4], esi
0x140197bac  mov     [rsp+348h+var_2AC], esi
0x140197bb3  xorps   xmm0, xmm0
0x140197bb6  movups  xmmword ptr [rsp+348h+UnicodeString.Length], xmm0
0x140197bbe  xorps   xmm1, xmm1
0x140197bc1  movups  xmmword ptr [rsp+348h+var_1F8.Length], xmm1
0x140197bc9  movups  [rsp+348h+var_278], xmm0
0x140197bd1  mov     rcx, 0FFFFF78000000320h
0x140197bdb  mov     rcx, [rcx]
0x140197bde  mov     eax, [r13+518h]
0x140197be5  test    eax, eax
0x140197be7  jz      loc_1401983F8
0x140197bed  mov     rdx, 0FFFFF78000000004h
0x140197bf7  mov     edi, [rdx]
0x140197bf9  imul    rdi, rcx
0x140197bfd  shr     rdi, 18h
0x140197c01  mov     ebx, edi
0x140197c03  sub     ebx, eax
0x140197c05  mov     [rsp+348h+var_2A4], ebx
0x140197c0c  cmp     ebx, 0C8h
0x140197c12  jb      loc_1401983F8
0x140197c18  mov     rcx, r13; struct tagTHREADINFO *
0x140197c1b  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x140197c20  mov     [rsp+348h+var_2B0], eax
0x140197c27  test    al, 28h
0x140197c29  setz    dl
0x140197c2c  test    al, 3
0x140197c2e  setz    cl
0x140197c31  or      dl, cl
0x140197c33  jnz     loc_1401983F8
0x140197c39  bt      eax, 9
0x140197c3d  jnb     short loc_140197C57
0x140197c3f  call    cs:__imp_W32GetUserSessionState
0x140197c46  nop     dword ptr [rax+rax+00h]
0x140197c4b  cmp     ebx, [rax+10DF0h]
0x140197c51  jb      loc_1401983F8
0x140197c57  mov     r14, rsi
0x140197c5a  mov     [rsp+348h+var_280], rsi
0x140197c62  mov     r15, rsi
0x140197c65  mov     [rsp+348h+var_288], rsi
0x140197c6d  xor     r8d, r8d
0x140197c70  mov     edx, r12d
0x140197c73  mov     rcx, [r13+520h]
0x140197c7a  call    ValidateHwndEx
0x140197c7f  mov     rbx, rax
0x140197c82  test    rax, rax
0x140197c85  jz      short loc_140197CFB
0x140197c87  lea     rdx, [rsp+348h+UnicodeString]; struct _UNICODE_STRING *
0x140197c8f  mov     rcx, rax; struct tagWND *
0x140197c92  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x140197c97  test    eax, eax
0x140197c99  cmovns  r14, [rsp+348h+UnicodeString.Buffer]
0x140197ca2  mov     [rsp+348h+var_280], r14
0x140197caa  call    Is_GetTopLevelWindowSupported
0x140197caf  test    eax, eax
0x140197cb1  js      short loc_140197CBD
0x140197cb3  mov     rcx, rbx
0x140197cb6  call    _GetTopLevelWindow
0x140197cbb  jmp     short loc_140197CC0
0x140197cbd  mov     rax, rsi
0x140197cc0  test    rax, rax
0x140197cc3  jz      short loc_140197CFB
0x140197cc5  cmp     rbx, rax
0x140197cc8  jz      short loc_140197CF0
0x140197cca  lea     rdx, [rsp+348h+var_1F8]; struct _UNICODE_STRING *
0x140197cd2  mov     rcx, rax; struct tagWND *
0x140197cd5  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x140197cda  test    eax, eax
0x140197cdc  js      short loc_140197CFB
0x140197cde  mov     r15, [rsp+348h+var_1F8.Buffer]
0x140197ce6  mov     [rsp+348h+var_288], r15
0x140197cee  jmp     short loc_140197CFB
0x140197cf0  mov     r15, r14
0x140197cf3  mov     [rsp+348h+var_288], r14
0x140197cfb  mov     [rsp+348h+var_320], rsi; unsigned __int64 *
0x140197d00  mov     [rsp+348h+var_328], rsi; unsigned int *
0x140197d05  lea     r9, [rsp+348h+var_2AC]; unsigned int *
0x140197d0d  lea     r8, [rsp+348h+var_2B4]; unsigned int *
0x140197d15  mov     edx, edi; unsigned int
0x140197d17  mov     rcx, [r13+1D0h]; struct tagQ *
0x140197d1e  call    ?EtwpGetLastInputProcessTime@@YAXQEAUtagQ@@KPEAK1PEAIPEA_K@Z; EtwpGetLastInputProcessTime(tagQ * const,ulong,ulong *,ulong *,uint *,unsigned __int64 *)
0x140197d23  mov     r9d, [r13+528h]
0x140197d2a  mov     [rsp+348h+var_2B8], r9d
0x140197d32  mov     [rsp+348h+var_2A8], r9d
0x140197d3a  mov     rax, [r13+530h]
0x140197d41  mov     [rsp+348h+var_2A0], rax
0x140197d49  mov     [rsp+348h+var_260], rax
0x140197d51  mov     [rsp+348h+var_290], rsi
0x140197d59  mov     rcx, [r13+0]; Thread
0x140197d5d  call    cs:__imp_PsGetThreadProcess
0x140197d64  nop     dword ptr [rax+rax+00h]
0x140197d69  mov     rcx, rax
0x140197d6c  call    cs:__imp_PsGetProcessPeb
0x140197d73  nop     dword ptr [rax+rax+00h]
0x140197d78  mov     [rsp+348h+Address], rax
0x140197d80  mov     [rsp+348h+var_228], 7D0h
0x140197d8c  mov     rcx, [rsp+348h+Address]; Address
0x140197d94  mov     [rsp+348h+var_228], r12
0x140197d9c  mov     r8d, r12d; Alignment
0x140197d9f  mov     rdx, r12; Length
0x140197da2  call    cs:__imp_ProbeForRead
0x140197da9  nop     dword ptr [rax+rax+00h]
0x140197dae  mov     rax, [rsp+348h+Address]
0x140197db6  mov     rbx, [rax+20h]
0x140197dba  mov     [rsp+348h+var_220], 450h
0x140197dc6  mov     [rsp+348h+var_220], r12
0x140197dce  mov     r8d, r12d; Alignment
0x140197dd1  mov     rdx, r12; Length
0x140197dd4  mov     rcx, rbx; Address
0x140197dd7  call    cs:__imp_ProbeForRead
0x140197dde  nop     dword ptr [rax+rax+00h]
0x140197de3  xorps   xmm0, xmm0
0x140197de6  movups  xmmword ptr [rsp+348h+PrimaryToken], xmm0
0x140197dee  lea     rcx, [rbx+60h]
0x140197df2  call    RtlReadULongFromUser
0x140197df7  mov     edi, eax
0x140197df9  mov     dword ptr [rsp+348h+PrimaryToken], edi
0x140197e00  lea     rcx, [rbx+68h]
0x140197e04  call    RtlReadULong64FromUser
0x140197e09  mov     [rsp+348h+PrimaryToken+8], rax
0x140197e11  movzx   edx, di
0x140197e14  mov     word ptr [rsp+348h+var_278], dx
0x140197e1c  shr     edi, 10h
0x140197e1f  mov     word ptr [rsp+348h+var_278+2], di
0x140197e27  mov     ecx, dword ptr [rsp+348h+PrimaryToken+4]
0x140197e2e  mov     dword ptr [rsp+348h+var_278+4], ecx
0x140197e35  mov     qword ptr [rsp+348h+var_278+8], rax
0x140197e3d  mov     edi, 2
0x140197e42  add     rdx, rdi; Length
0x140197e45  mov     r8d, edi; Alignment
0x140197e48  mov     rcx, rax; Address
0x140197e4b  call    cs:__imp_ProbeForRead
0x140197e52  nop     dword ptr [rax+rax+00h]
0x140197e57  movzx   eax, word ptr [rsp+348h+var_278]
0x140197e5f  cmp     ax, word ptr [rsp+348h+var_278+2]
0x140197e67  ja      short loc_140197E99
0x140197e69  test    r12b, al
0x140197e6c  jnz     short loc_140197EA3
0x140197e6e  lea     rax, [rsp+348h+var_278]
0x140197e76  mov     [rsp+348h+var_218], rax
0x140197e7e  mov     ebx, [rsp+348h+var_2A4]
0x140197e85  mov     edi, [rsp+348h+var_2B8]
0x140197e8c  mov     rcx, [rsp+348h+var_2A0]
0x140197e94  jmp     loc_140197F21
0x140197e99  test    byte ptr [rsp+348h+var_278], r12b
0x140197ea1  jz      short loc_140197EC7
0x140197ea3  mov     [rsp+348h+var_2B8], 20000h
0x140197eae  mov     r8d, 380h
0x140197eb4  mov     edx, [rsp+348h+var_2B8]
0x140197ebb  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140197ec2  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140197ec7  call    cs:__imp_ExRaiseAccessViolation
0x140197ece  nop     dword ptr [rax+rax+00h]
0x140197ed3  nop
0x140197ed4  xor     eax, eax
0x140197ed6  mov     [rsp+348h+var_218], rax
0x140197ede  xor     esi, esi
0x140197ee0  lea     r12d, [rax+1]
0x140197ee4  mov     r14, [rsp+348h+var_280]
0x140197eec  mov     r15, [rsp+348h+var_288]
0x140197ef4  mov     r13, [rsp+348h+var_268]
0x140197efc  mov     edi, [rsp+348h+var_2A8]
0x140197f03  mov     [rsp+348h+var_2B8], edi
0x140197f0a  mov     rcx, [rsp+348h+var_260]
0x140197f12  mov     [rsp+348h+var_2A0], rcx
0x140197f1a  mov     ebx, [rsp+348h+var_2A4]
0x140197f21  test    rax, rax
0x140197f24  jz      short loc_140197F32
0x140197f26  mov     rax, [rax+8]
0x140197f2a  mov     [rsp+348h+var_290], rax
0x140197f32  mov     rdx, [r13+1C8h]
0x140197f39  mov     al, [rdx+328h]
0x140197f3f  and     al, 30h
0x140197f41  cmp     al, 10h
0x140197f43  jnz     loc_140198213
0x140197f49  mov     rcx, [rdx]; Process
0x140197f4c  call    cs:__imp_PsReferencePrimaryToken
0x140197f53  nop     dword ptr [rax+rax+00h]
0x140197f58  mov     [rsp+348h+PrimaryToken], rax
0x140197f60  mov     [rsp+348h+var_268], 100h
0x140197f6c  mov     [rsp+348h+var_260], 82h
0x140197f78  mov     [rsp+348h+var_320], rsi
0x140197f7d  lea     rcx, [rsp+348h+var_260]
0x140197f85  mov     [rsp+348h+var_328], rcx
0x140197f8a  lea     r9, [rsp+348h+var_1C8]
0x140197f92  lea     r8, [rsp+348h+var_268]
0x140197f9a  lea     rdx, [rsp+348h+var_138]
0x140197fa2  mov     rcx, rax
0x140197fa5  call    cs:__imp_RtlQueryPackageIdentity
0x140197fac  nop     dword ptr [rax+rax+00h]
0x140197fb1  mov     r10d, eax
0x140197fb4  mov     [rsp+348h+var_2A8], eax
0x140197fbb  mov     r13, [rsp+348h+var_2A0]
0x140197fc3  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, r12b
0x140197fca  jz      short loc_14019803E
0x140197fcc  lea     rax, word_140257388
0x140197fd3  lea     rdx, [rsp+348h+var_1C8]
0x140197fdb  test    r10d, r10d
0x140197fde  cmovs   rdx, rax
0x140197fe2  lea     rcx, [rsp+348h+var_138]
0x140197fea  cmovs   rcx, rax
0x140197fee  mov     [rsp+348h+var_2E8], r13
0x140197ff3  mov     dword ptr [rsp+348h+var_2F0], edi
0x140197ff7  mov     [rsp+348h+var_2F8], rdx
0x140197ffc  mov     [rsp+348h+var_300], rcx
0x140198001  mov     [rsp+348h+var_308], r15
0x140198006  mov     [rsp+348h+var_310], r14
0x14019800b  mov     eax, [rsp+348h+var_2AC]
0x140198012  mov     dword ptr [rsp+348h+var_318], eax
0x140198016  mov     eax, [rsp+348h+var_2B4]
0x14019801d  mov     dword ptr [rsp+348h+var_320], eax
0x140198021  mov     dword ptr [rsp+348h+var_328], ebx
0x140198025  mov     edi, [rsp+348h+var_2B0]
0x14019802c  mov     r9d, edi
0x14019802f  call    McTemplateK0qqqqzzzzqx_EtwWriteTransfer
0x140198034  mov     r10d, [rsp+348h+var_2A8]
0x14019803c  jmp     short loc_140198045
0x14019803e  mov     edi, [rsp+348h+var_2B0]
0x140198045  lea     r8, word_140257388
0x14019804c  mov     eax, cs:dword_140294F90
0x140198052  cmp     eax, 5
0x140198055  jbe     loc_1401981E8
0x14019805b  mov     edx, 40000h
0x140198060  lea     rcx, dword_140294F90
0x140198067  call    _tlgKeywordOn
0x14019806c  test    al, al
0x14019806e  jz      loc_1401981E8
0x140198074  mov     [rsp+348h+var_2A0], 1000000h
0x140198080  mov     [rsp+348h+var_2A8], 2
0x14019808b  mov     [rsp+348h+var_2A4], r12d
0x140198093  mov     [rsp+348h+var_210], r13
0x14019809b  mov     r9d, [rsp+348h+var_2B8]
0x1401980a3  mov     [rsp+348h+var_2B8], r9d
0x1401980ab  mov     [rsp+348h+var_258], r15
0x1401980b3  mov     [rsp+348h+var_250], r14
0x1401980bb  mov     rax, [rsp+348h+var_290]
0x1401980c3  mov     [rsp+348h+var_290], rax
0x1401980cb  lea     rax, [rsp+348h+var_1C8]
0x1401980d3  test    r10d, r10d
0x1401980d6  cmovs   rax, r8
0x1401980da  mov     [rsp+348h+var_248], rax
0x1401980e2  lea     rax, [rsp+348h+var_138]
0x1401980ea  cmovs   rax, r8
0x1401980ee  mov     [rsp+348h+var_240], rax
0x1401980f6  mov     eax, [rsp+348h+var_2AC]
0x1401980fd  mov     [rsp+348h+var_2B0], eax
0x140198104  mov     eax, [rsp+348h+var_2B4]
0x14019810b  mov     [rsp+348h+var_2B4], eax
0x140198112  mov     [rsp+348h+var_2AC], ebx
0x140198119  mov     dword ptr [rsp+348h+Address], edi
0x140198120  lea     rax, [rsp+348h+var_2A0]
0x140198128  mov     [rsp+348h+var_2C0], rax
0x140198130  lea     rax, [rsp+348h+var_2A8]
0x140198138  mov     [rsp+348h+var_2C8], rax
0x140198140  lea     rax, [rsp+348h+var_2A4]
0x140198148  mov     [rsp+348h+var_2D0], rax
  ... truncated ...
```
