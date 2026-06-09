# EtwTraceMessageCheckDelay

- ea: `0x140199800`
- end: `0x14019a136`
- name: `EtwTraceMessageCheckDelay`
- size: `2358`
- prototype: `__int64 __fastcall(struct tagTHREADINFO *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400d98bc`

## callees

- `0x140062f70`
- `0x14006c210`
- `0x1400a4260`
- `0x1401067fc`
- `0x140115c20`
- `0x140117190`
- `0x140129744`
- `0x14013d4d0`
- `0x1401501b0`
- `0x14015db9c`
- `0x140196d30`
- `0x140199800`
- `0x1401aab9c`
- `0x1402388e0`
- `0x1402bb164`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x140199a7c`
- `ntoskrnl!PsGetProcessPeb` at `0x140199a7c`
- `ntoskrnl!ProbeForRead` at `0x140199ab2`
- `ntoskrnl!ProbeForRead` at `0x140199ae7`
- `ntoskrnl!ProbeForRead` at `0x140199b5b`
- `ntoskrnl!ProbeForRead` at `0x140199ab2`
- `ntoskrnl!ProbeForRead` at `0x140199ae7`
- `ntoskrnl!ProbeForRead` at `0x140199b5b`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140199bd7`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140199bd7`
- `ntoskrnl!PsGetThreadProcess` at `0x140199a6d`
- `ntoskrnl!PsGetThreadProcess` at `0x140199a6d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140199c5c`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140199c5c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14019a0de`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14019a0fc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14019a0de`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14019a0fc`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140199f12`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140199f12`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140199cb5`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140199cb5`
- `WIN32K!W32GetUserSessionState` at `0x14019994f`
- `WIN32K!W32GetUserSessionState` at `0x14019994f`

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
    || ((unsigned __int8)(byte_140293DD8 - 1) <= 2u
     || (qword_140293DC0 & 0x8001000000040000uLL) == 0
     || (qword_140293DC8 & 0x8001000000040000uLL) != qword_140293DC8
      ? (v2 = 0)
      : (v2 = 1),
        !v2) )
  {
    if ( (unsigned int)dword_140293F90 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_140293F90, 0x40000) )
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
        v24 = &word_140256630;
      v25 = (const WCHAR *)v62;
      if ( v22 < 0 )
        v25 = &word_140256630;
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
    if ( (unsigned int)dword_140293F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140293F90, 0x40000) )
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
        (unsigned int)&unk_140270308,
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
    if ( (unsigned int)dword_140293F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140293F90, 0x40000) )
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
        (unsigned int)byte_140270231,
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
0x140199800  mov     [rsp+arg_8], rbx
0x140199805  mov     [rsp+arg_10], rsi
0x14019980a  push    rdi
0x14019980b  push    r12
0x14019980d  push    r13
0x14019980f  push    r14
0x140199811  push    r15
0x140199813  sub     rsp, 320h
0x14019981a  mov     rax, cs:__security_cookie
0x140199821  xor     rax, rsp
0x140199824  mov     [rsp+348h+var_38], rax
0x14019982c  mov     r13, rcx
0x14019982f  mov     [rsp+348h+var_268], rcx
0x140199837  mov     rdx, 8001000000040000h
0x140199841  mov     r12d, 1
0x140199847  test    cs:W32kEtwEnabledKeyword, rdx
0x14019984e  jz      short loc_14019988B
0x140199850  mov     al, cs:byte_140293DD8
0x140199856  sub     al, r12b
0x140199859  cmp     al, 2
0x14019985b  jbe     short loc_140199880
0x14019985d  test    cs:qword_140293DC0, rdx
0x140199864  jz      short loc_140199880
0x140199866  mov     rax, cs:qword_140293DC8
0x14019986d  and     rax, rdx
0x140199870  cmp     rax, cs:qword_140293DC8
0x140199877  jnz     short loc_140199880
0x140199879  mov     al, r12b
0x14019987c  xor     esi, esi
0x14019987e  jmp     short loc_140199885
0x140199880  xor     esi, esi
0x140199882  mov     al, sil
0x140199885  test    al, al
0x140199887  jz      short loc_14019988D
0x140199889  jmp     short loc_1401998B5
0x14019988b  xor     esi, esi
0x14019988d  mov     eax, cs:dword_140293F90
0x140199893  cmp     eax, 5
0x140199896  jbe     loc_14019A108
0x14019989c  mov     edx, 40000h
0x1401998a1  lea     rcx, dword_140293F90
0x1401998a8  call    _tlgKeywordOn
0x1401998ad  test    al, al
0x1401998af  jz      loc_14019A108
0x1401998b5  mov     [rsp+348h+var_2B4], esi
0x1401998bc  mov     [rsp+348h+var_2AC], esi
0x1401998c3  xorps   xmm0, xmm0
0x1401998c6  movups  xmmword ptr [rsp+348h+UnicodeString.Length], xmm0
0x1401998ce  xorps   xmm1, xmm1
0x1401998d1  movups  xmmword ptr [rsp+348h+var_1F8.Length], xmm1
0x1401998d9  movups  [rsp+348h+var_278], xmm0
0x1401998e1  mov     rcx, 0FFFFF78000000320h
0x1401998eb  mov     rcx, [rcx]
0x1401998ee  mov     eax, [r13+518h]
0x1401998f5  test    eax, eax
0x1401998f7  jz      loc_14019A108
0x1401998fd  mov     rdx, 0FFFFF78000000004h
0x140199907  mov     edi, [rdx]
0x140199909  imul    rdi, rcx
0x14019990d  shr     rdi, 18h
0x140199911  mov     ebx, edi
0x140199913  sub     ebx, eax
0x140199915  mov     [rsp+348h+var_2A4], ebx
0x14019991c  cmp     ebx, 0C8h
0x140199922  jb      loc_14019A108
0x140199928  mov     rcx, r13; struct tagTHREADINFO *
0x14019992b  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x140199930  mov     [rsp+348h+var_2B0], eax
0x140199937  test    al, 28h
0x140199939  setz    dl
0x14019993c  test    al, 3
0x14019993e  setz    cl
0x140199941  or      dl, cl
0x140199943  jnz     loc_14019A108
0x140199949  bt      eax, 9
0x14019994d  jnb     short loc_140199967
0x14019994f  call    cs:__imp_W32GetUserSessionState
0x140199956  nop     dword ptr [rax+rax+00h]
0x14019995b  cmp     ebx, [rax+10DF0h]
0x140199961  jb      loc_14019A108
0x140199967  mov     r14, rsi
0x14019996a  mov     [rsp+348h+var_280], rsi
0x140199972  mov     r15, rsi
0x140199975  mov     [rsp+348h+var_288], rsi
0x14019997d  xor     r8d, r8d
0x140199980  mov     edx, r12d
0x140199983  mov     rcx, [r13+520h]
0x14019998a  call    ValidateHwndEx
0x14019998f  mov     rbx, rax
0x140199992  test    rax, rax
0x140199995  jz      short loc_140199A0B
0x140199997  lea     rdx, [rsp+348h+UnicodeString]; struct _UNICODE_STRING *
0x14019999f  mov     rcx, rax; struct tagWND *
0x1401999a2  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x1401999a7  test    eax, eax
0x1401999a9  cmovns  r14, [rsp+348h+UnicodeString.Buffer]
0x1401999b2  mov     [rsp+348h+var_280], r14
0x1401999ba  call    Is_GetTopLevelWindowSupported
0x1401999bf  test    eax, eax
0x1401999c1  js      short loc_1401999CD
0x1401999c3  mov     rcx, rbx
0x1401999c6  call    _GetTopLevelWindow
0x1401999cb  jmp     short loc_1401999D0
0x1401999cd  mov     rax, rsi
0x1401999d0  test    rax, rax
0x1401999d3  jz      short loc_140199A0B
0x1401999d5  cmp     rbx, rax
0x1401999d8  jz      short loc_140199A00
0x1401999da  lea     rdx, [rsp+348h+var_1F8]; struct _UNICODE_STRING *
0x1401999e2  mov     rcx, rax; struct tagWND *
0x1401999e5  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x1401999ea  test    eax, eax
0x1401999ec  js      short loc_140199A0B
0x1401999ee  mov     r15, [rsp+348h+var_1F8.Buffer]
0x1401999f6  mov     [rsp+348h+var_288], r15
0x1401999fe  jmp     short loc_140199A0B
0x140199a00  mov     r15, r14
0x140199a03  mov     [rsp+348h+var_288], r14
0x140199a0b  mov     [rsp+348h+var_320], rsi; unsigned __int64 *
0x140199a10  mov     [rsp+348h+var_328], rsi; unsigned int *
0x140199a15  lea     r9, [rsp+348h+var_2AC]; unsigned int *
0x140199a1d  lea     r8, [rsp+348h+var_2B4]; unsigned int *
0x140199a25  mov     edx, edi; unsigned int
0x140199a27  mov     rcx, [r13+1D0h]; struct tagQ *
0x140199a2e  call    ?EtwpGetLastInputProcessTime@@YAXQEAUtagQ@@KPEAK1PEAIPEA_K@Z; EtwpGetLastInputProcessTime(tagQ * const,ulong,ulong *,ulong *,uint *,unsigned __int64 *)
0x140199a33  mov     r9d, [r13+528h]
0x140199a3a  mov     [rsp+348h+var_2B8], r9d
0x140199a42  mov     [rsp+348h+var_2A8], r9d
0x140199a4a  mov     rax, [r13+530h]
0x140199a51  mov     [rsp+348h+var_2A0], rax
0x140199a59  mov     [rsp+348h+var_260], rax
0x140199a61  mov     [rsp+348h+var_290], rsi
0x140199a69  mov     rcx, [r13+0]; Thread
0x140199a6d  call    cs:__imp_PsGetThreadProcess
0x140199a74  nop     dword ptr [rax+rax+00h]
0x140199a79  mov     rcx, rax
0x140199a7c  call    cs:__imp_PsGetProcessPeb
0x140199a83  nop     dword ptr [rax+rax+00h]
0x140199a88  mov     [rsp+348h+Address], rax
0x140199a90  mov     [rsp+348h+var_228], 7D0h
0x140199a9c  mov     rcx, [rsp+348h+Address]; Address
0x140199aa4  mov     [rsp+348h+var_228], r12
0x140199aac  mov     r8d, r12d; Alignment
0x140199aaf  mov     rdx, r12; Length
0x140199ab2  call    cs:__imp_ProbeForRead
0x140199ab9  nop     dword ptr [rax+rax+00h]
0x140199abe  mov     rax, [rsp+348h+Address]
0x140199ac6  mov     rbx, [rax+20h]
0x140199aca  mov     [rsp+348h+var_220], 448h
0x140199ad6  mov     [rsp+348h+var_220], r12
0x140199ade  mov     r8d, r12d; Alignment
0x140199ae1  mov     rdx, r12; Length
0x140199ae4  mov     rcx, rbx; Address
0x140199ae7  call    cs:__imp_ProbeForRead
0x140199aee  nop     dword ptr [rax+rax+00h]
0x140199af3  xorps   xmm0, xmm0
0x140199af6  movups  xmmword ptr [rsp+348h+PrimaryToken], xmm0
0x140199afe  lea     rcx, [rbx+60h]
0x140199b02  call    RtlReadULongFromUser
0x140199b07  mov     edi, eax
0x140199b09  mov     dword ptr [rsp+348h+PrimaryToken], edi
0x140199b10  lea     rcx, [rbx+68h]
0x140199b14  call    RtlReadULong64FromUser
0x140199b19  mov     [rsp+348h+PrimaryToken+8], rax
0x140199b21  movzx   edx, di
0x140199b24  mov     word ptr [rsp+348h+var_278], dx
0x140199b2c  shr     edi, 10h
0x140199b2f  mov     word ptr [rsp+348h+var_278+2], di
0x140199b37  mov     ecx, dword ptr [rsp+348h+PrimaryToken+4]
0x140199b3e  mov     dword ptr [rsp+348h+var_278+4], ecx
0x140199b45  mov     qword ptr [rsp+348h+var_278+8], rax
0x140199b4d  mov     edi, 2
0x140199b52  add     rdx, rdi; Length
0x140199b55  mov     r8d, edi; Alignment
0x140199b58  mov     rcx, rax; Address
0x140199b5b  call    cs:__imp_ProbeForRead
0x140199b62  nop     dword ptr [rax+rax+00h]
0x140199b67  movzx   eax, word ptr [rsp+348h+var_278]
0x140199b6f  cmp     ax, word ptr [rsp+348h+var_278+2]
0x140199b77  ja      short loc_140199BA9
0x140199b79  test    r12b, al
0x140199b7c  jnz     short loc_140199BB3
0x140199b7e  lea     rax, [rsp+348h+var_278]
0x140199b86  mov     [rsp+348h+var_218], rax
0x140199b8e  mov     ebx, [rsp+348h+var_2A4]
0x140199b95  mov     edi, [rsp+348h+var_2B8]
0x140199b9c  mov     rcx, [rsp+348h+var_2A0]
0x140199ba4  jmp     loc_140199C31
0x140199ba9  test    byte ptr [rsp+348h+var_278], r12b
0x140199bb1  jz      short loc_140199BD7
0x140199bb3  mov     [rsp+348h+var_2B8], 20000h
0x140199bbe  mov     r8d, 380h
0x140199bc4  mov     edx, [rsp+348h+var_2B8]
0x140199bcb  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140199bd2  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140199bd7  call    cs:__imp_ExRaiseAccessViolation
0x140199bde  nop     dword ptr [rax+rax+00h]
0x140199be3  nop
0x140199be4  xor     eax, eax
0x140199be6  mov     [rsp+348h+var_218], rax
0x140199bee  xor     esi, esi
0x140199bf0  lea     r12d, [rax+1]
0x140199bf4  mov     r14, [rsp+348h+var_280]
0x140199bfc  mov     r15, [rsp+348h+var_288]
0x140199c04  mov     r13, [rsp+348h+var_268]
0x140199c0c  mov     edi, [rsp+348h+var_2A8]
0x140199c13  mov     [rsp+348h+var_2B8], edi
0x140199c1a  mov     rcx, [rsp+348h+var_260]
0x140199c22  mov     [rsp+348h+var_2A0], rcx
0x140199c2a  mov     ebx, [rsp+348h+var_2A4]
0x140199c31  test    rax, rax
0x140199c34  jz      short loc_140199C42
0x140199c36  mov     rax, [rax+8]
0x140199c3a  mov     [rsp+348h+var_290], rax
0x140199c42  mov     rdx, [r13+1C8h]
0x140199c49  mov     al, [rdx+328h]
0x140199c4f  and     al, 30h
0x140199c51  cmp     al, 10h
0x140199c53  jnz     loc_140199F23
0x140199c59  mov     rcx, [rdx]; Process
0x140199c5c  call    cs:__imp_PsReferencePrimaryToken
0x140199c63  nop     dword ptr [rax+rax+00h]
0x140199c68  mov     [rsp+348h+PrimaryToken], rax
0x140199c70  mov     [rsp+348h+var_268], 100h
0x140199c7c  mov     [rsp+348h+var_260], 82h
0x140199c88  mov     [rsp+348h+var_320], rsi
0x140199c8d  lea     rcx, [rsp+348h+var_260]
0x140199c95  mov     [rsp+348h+var_328], rcx
0x140199c9a  lea     r9, [rsp+348h+var_1C8]
0x140199ca2  lea     r8, [rsp+348h+var_268]
0x140199caa  lea     rdx, [rsp+348h+var_138]
0x140199cb2  mov     rcx, rax
0x140199cb5  call    cs:__imp_RtlQueryPackageIdentity
0x140199cbc  nop     dword ptr [rax+rax+00h]
0x140199cc1  mov     r10d, eax
0x140199cc4  mov     [rsp+348h+var_2A8], eax
0x140199ccb  mov     r13, [rsp+348h+var_2A0]
0x140199cd3  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, r12b
0x140199cda  jz      short loc_140199D4E
0x140199cdc  lea     rax, word_140256630
0x140199ce3  lea     rdx, [rsp+348h+var_1C8]
0x140199ceb  test    r10d, r10d
0x140199cee  cmovs   rdx, rax
0x140199cf2  lea     rcx, [rsp+348h+var_138]
0x140199cfa  cmovs   rcx, rax
0x140199cfe  mov     [rsp+348h+var_2E8], r13
0x140199d03  mov     dword ptr [rsp+348h+var_2F0], edi
0x140199d07  mov     [rsp+348h+var_2F8], rdx
0x140199d0c  mov     [rsp+348h+var_300], rcx
0x140199d11  mov     [rsp+348h+var_308], r15
0x140199d16  mov     [rsp+348h+var_310], r14
0x140199d1b  mov     eax, [rsp+348h+var_2AC]
0x140199d22  mov     dword ptr [rsp+348h+var_318], eax
0x140199d26  mov     eax, [rsp+348h+var_2B4]
0x140199d2d  mov     dword ptr [rsp+348h+var_320], eax
0x140199d31  mov     dword ptr [rsp+348h+var_328], ebx
0x140199d35  mov     edi, [rsp+348h+var_2B0]
0x140199d3c  mov     r9d, edi
0x140199d3f  call    McTemplateK0qqqqzzzzqx_EtwWriteTransfer
0x140199d44  mov     r10d, [rsp+348h+var_2A8]
0x140199d4c  jmp     short loc_140199D55
0x140199d4e  mov     edi, [rsp+348h+var_2B0]
0x140199d55  lea     r8, word_140256630
0x140199d5c  mov     eax, cs:dword_140293F90
0x140199d62  cmp     eax, 5
0x140199d65  jbe     loc_140199EF8
0x140199d6b  mov     edx, 40000h
0x140199d70  lea     rcx, dword_140293F90
0x140199d77  call    _tlgKeywordOn
0x140199d7c  test    al, al
0x140199d7e  jz      loc_140199EF8
0x140199d84  mov     [rsp+348h+var_2A0], 1000000h
0x140199d90  mov     [rsp+348h+var_2A8], 2
0x140199d9b  mov     [rsp+348h+var_2A4], r12d
0x140199da3  mov     [rsp+348h+var_210], r13
0x140199dab  mov     r9d, [rsp+348h+var_2B8]
0x140199db3  mov     [rsp+348h+var_2B8], r9d
0x140199dbb  mov     [rsp+348h+var_258], r15
0x140199dc3  mov     [rsp+348h+var_250], r14
0x140199dcb  mov     rax, [rsp+348h+var_290]
0x140199dd3  mov     [rsp+348h+var_290], rax
0x140199ddb  lea     rax, [rsp+348h+var_1C8]
0x140199de3  test    r10d, r10d
0x140199de6  cmovs   rax, r8
0x140199dea  mov     [rsp+348h+var_248], rax
0x140199df2  lea     rax, [rsp+348h+var_138]
0x140199dfa  cmovs   rax, r8
0x140199dfe  mov     [rsp+348h+var_240], rax
0x140199e06  mov     eax, [rsp+348h+var_2AC]
0x140199e0d  mov     [rsp+348h+var_2B0], eax
0x140199e14  mov     eax, [rsp+348h+var_2B4]
0x140199e1b  mov     [rsp+348h+var_2B4], eax
0x140199e22  mov     [rsp+348h+var_2AC], ebx
0x140199e29  mov     dword ptr [rsp+348h+Address], edi
0x140199e30  lea     rax, [rsp+348h+var_2A0]
0x140199e38  mov     [rsp+348h+var_2C0], rax
0x140199e40  lea     rax, [rsp+348h+var_2A8]
0x140199e48  mov     [rsp+348h+var_2C8], rax
0x140199e50  lea     rax, [rsp+348h+var_2A4]
0x140199e58  mov     [rsp+348h+var_2D0], rax
  ... truncated ...
```
