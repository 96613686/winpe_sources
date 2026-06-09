# EtwTraceInputProcessDelay

- ea: `0x140198ef0`
- end: `0x1401997f1`
- name: `EtwTraceInputProcessDelay`
- size: `2305`
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
- `0x140117f64`
- `0x140146238`
- `0x14014d8b8`
- `0x1401501b0`
- `0x14015db9c`
- `0x140162cf8`
- `0x140196d30`
- `0x140198ef0`
- `0x1401aab9c`
- `0x1402388e0`
- `0x1402bb164`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x14019916a`
- `ntoskrnl!PsGetProcessPeb` at `0x14019916a`
- `ntoskrnl!ProbeForRead` at `0x1401991a0`
- `ntoskrnl!ProbeForRead` at `0x1401991d5`
- `ntoskrnl!ProbeForRead` at `0x140199249`
- `ntoskrnl!ProbeForRead` at `0x1401991a0`
- `ntoskrnl!ProbeForRead` at `0x1401991d5`
- `ntoskrnl!ProbeForRead` at `0x140199249`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140199314`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140199314`
- `ntoskrnl!PsGetThreadProcess` at `0x14019915b`
- `ntoskrnl!PsGetThreadProcess` at `0x14019915b`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140199375`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140199375`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140199799`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401997b7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140199799`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401997b7`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1401995f9`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1401995f9`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1401993d1`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1401993d1`

## pseudocode

```c
void __fastcall EtwTraceInputProcessDelay(struct tagQ **a1)
{
  char v2; // al
  unsigned int ThreadInfoFlags; // r13d
  PWSTR Buffer; // r14
  PWSTR v5; // r15
  struct tagWND *v6; // rax
  struct tagWND *v7; // rdi
  struct tagWND *TopLevelWindow; // rax
  PEPROCESS ThreadProcess; // rax
  char *v10; // rbx
  unsigned int ULongFromUser; // edi
  int v12; // r8d
  unsigned __int64 v13; // rax
  const wchar_t *v14; // rax
  __int64 v15; // rcx
  PACCESS_TOKEN v16; // rdi
  int v17; // r8d
  int v18; // r9d
  const WCHAR *v19; // rdx
  const WCHAR *v20; // rcx
  int v21; // ecx
  WCHAR *v22; // r8
  int v23; // r9d
  WCHAR *v24; // rax
  WCHAR *v25; // rax
  unsigned int v26; // ebx
  unsigned int v27; // edi
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  unsigned int v31; // [rsp+80h] [rbp-2A8h] BYREF
  unsigned int v32; // [rsp+84h] [rbp-2A4h] BYREF
  unsigned int v33; // [rsp+88h] [rbp-2A0h] BYREF
  unsigned int v34; // [rsp+8Ch] [rbp-29Ch] BYREF
  volatile void *Address; // [rsp+90h] [rbp-298h] BYREF
  __int64 v36; // [rsp+98h] [rbp-290h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-288h] BYREF
  unsigned __int64 v38; // [rsp+A8h] [rbp-280h] BYREF
  PWSTR v39; // [rsp+B0h] [rbp-278h]
  PWSTR v40; // [rsp+B8h] [rbp-270h]
  __int128 v41; // [rsp+C0h] [rbp-268h]
  __int64 v42; // [rsp+D0h] [rbp-258h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-250h] BYREF
  __int64 v44; // [rsp+E0h] [rbp-248h] BYREF
  PWSTR v45; // [rsp+E8h] [rbp-240h] BYREF
  PWSTR v46; // [rsp+F0h] [rbp-238h] BYREF
  __int128 v47; // [rsp+F8h] [rbp-230h] BYREF
  __int64 v48; // [rsp+108h] [rbp-220h]
  __int64 v49; // [rsp+110h] [rbp-218h]
  unsigned __int64 v50; // [rsp+118h] [rbp-210h]
  PWSTR v51; // [rsp+120h] [rbp-208h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+128h] [rbp-200h] BYREF
  struct _UNICODE_STRING v53; // [rsp+138h] [rbp-1F0h] BYREF
  _BYTE v54[144]; // [rsp+160h] [rbp-1C8h] BYREF
  _BYTE v55[256]; // [rsp+1F0h] [rbp-138h] BYREF

  v42 = (__int64)a1;
  v43 = (__int64)a1;
  if ( (W32kEtwEnabledKeyword & 0x8001000000040000uLL) != 0
    && ((unsigned __int8)(byte_140293DD8 - 1) <= 2u
     || (qword_140293DC0 & 0x8001000000040000uLL) == 0
     || (qword_140293DC8 & 0x8001000000040000uLL) != qword_140293DC8
      ? (v2 = 0)
      : (v2 = 1),
        v2)
    || (unsigned int)dword_140293F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140293F90, 0x400000000000LL)
    || (unsigned int)dword_140293F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140293F90, 0x40000) )
  {
    v31 = 0;
    v33 = 0;
    v32 = 0;
    v38 = 0;
    UnicodeString = 0;
    v53 = 0;
    v41 = 0;
    EtwpGetLastInputProcessTime(
      a1[58],
      (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24,
      &v31,
      &v33,
      &v32,
      &v38);
    if ( v31 >= 0x32 && v33 >= 0x32 )
    {
      ThreadInfoFlags = EtwpGetThreadInfoFlags((struct tagTHREADINFO *const)a1);
      v34 = ThreadInfoFlags;
      if ( (ThreadInfoFlags & 3) != 0 && (ThreadInfoFlags & 0x28) != 0 )
      {
        Buffer = 0;
        v40 = 0;
        v5 = 0;
        v39 = 0;
        v6 = (struct tagWND *)ValidateHwndEx(a1[164], 1, 0);
        v7 = v6;
        if ( v6 )
        {
          if ( EtwpGetClassName(v6, &UnicodeString) >= 0 )
            Buffer = UnicodeString.Buffer;
          v40 = Buffer;
          if ( (int)Is_GetTopLevelWindowSupported() < 0 )
            TopLevelWindow = 0;
          else
            TopLevelWindow = (struct tagWND *)GetTopLevelWindow(v7);
          if ( TopLevelWindow )
          {
            if ( v7 == TopLevelWindow )
            {
              v5 = Buffer;
              v39 = Buffer;
            }
            else if ( EtwpGetClassName(TopLevelWindow, &v53) >= 0 )
            {
              v5 = v53.Buffer;
              v39 = v53.Buffer;
            }
          }
        }
        v37 = 0;
        v36 = 0;
        ThreadProcess = PsGetThreadProcess(*a1);
        Address = (volatile void *)PsGetProcessPeb(ThreadProcess);
        v48 = 1;
        ProbeForRead(Address, 1u, 1u);
        v10 = (char *)*((_QWORD *)Address + 4);
        v49 = 1;
        ProbeForRead(v10, 1u, 1u);
        v47 = 0;
        ULongFromUser = RtlReadULongFromUser(v10 + 96);
        LODWORD(v47) = ULongFromUser;
        *((_QWORD *)&v47 + 1) = RtlReadULong64FromUser(v10 + 104);
        *(_QWORD *)&v41 = __PAIR64__(DWORD1(v47), ULongFromUser);
        *((_QWORD *)&v41 + 1) = *((_QWORD *)&v47 + 1);
        ProbeForRead(*((volatile void **)&v47 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
        if ( (unsigned __int16)v41 > WORD1(v41) || (v41 & 1) != 0 )
        {
          if ( (v41 & 1) != 0 )
          {
            LODWORD(Address) = 0x20000;
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1137);
          }
          ExRaiseAccessViolation();
        }
        v37 = *((_QWORD *)&v41 + 1);
        if ( (_WORD)v41 )
        {
          v13 = (unsigned __int64)(unsigned __int16)v41 >> 1;
          v50 = v13;
          while ( v13 )
          {
            if ( *(_WORD *)(*((_QWORD *)&v41 + 1) + 2 * v13 - 2) == 92 )
            {
              if ( v13 == (unsigned __int64)(unsigned __int16)v41 >> 1 )
                v14 = L"Invalid";
              else
                v14 = (const wchar_t *)(*((_QWORD *)&v41 + 1) + 2 * v13);
              v36 = (__int64)v14;
              break;
            }
            v50 = --v13;
          }
        }
        if ( !v36 )
          v36 = v37;
        v15 = *(_QWORD *)(v42 + 456);
        if ( (*(_BYTE *)(v15 + 808) & 0x30) == 0x10 )
        {
          v16 = PsReferencePrimaryToken(*(PEPROCESS *)v15);
          *(_QWORD *)&v47 = v16;
          v42 = 256;
          v43 = 130;
          v18 = RtlQueryPackageIdentity(v16, v55, &v42, v54, &v43, 0);
          v34 = v18;
          if ( (Microsoft_Windows_Win32kEnableBits & 0x100) != 0 )
          {
            v19 = (const WCHAR *)v54;
            if ( v18 < 0 )
              v19 = &word_140256630;
            v20 = (const WCHAR *)v55;
            if ( v18 < 0 )
              v20 = &word_140256630;
            McTemplateK0qqqzzzzqx_EtwWriteTransfer(
              (_DWORD)v20,
              (_DWORD)v19,
              v17,
              ThreadInfoFlags,
              v31,
              v33,
              (__int64)Buffer,
              (__int64)v5,
              (__int64)v20,
              (__int64)v19,
              v32,
              v38);
          }
          if ( (unsigned int)dword_140293F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140293F90, 0x400000040000LL) )
          {
            v34 = 2;
            LODWORD(Address) = 1;
            v51 = v5;
            v44 = (__int64)Buffer;
            v24 = (WCHAR *)v54;
            if ( v23 < 0 )
              v24 = v22;
            v45 = v24;
            v25 = (WCHAR *)v55;
            if ( v23 < 0 )
              v25 = v22;
            v46 = v25;
            LODWORD(v37) = ThreadInfoFlags;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v21,
              (unsigned int)byte_14027014D,
              (_DWORD)v22,
              v23,
              (__int64)&v37,
              (__int64)&v31,
              (__int64)&v33,
              (__int64)&v46,
              (__int64)&v45,
              (__int64)&v36,
              (__int64)&v44,
              (__int64)&v51,
              (__int64)&v32,
              (__int64)&v38,
              (__int64)&Address,
              (__int64)&v34);
          }
          PsDereferencePrimaryToken(v16);
        }
        else
        {
          v26 = v33;
          v27 = v31;
          if ( (Microsoft_Windows_Win32kEnableBits & 0x100) != 0 )
            McTemplateK0qqqzzzqx_EtwWriteTransfer(
              v15,
              DWORD2(v41),
              v12,
              ThreadInfoFlags,
              v31,
              v33,
              (__int64)Buffer,
              (__int64)v5,
              v37,
              v32,
              v38);
          if ( (unsigned int)dword_140293F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140293F90, 0x400000040000LL) )
          {
            LODWORD(v37) = 1;
            *(_QWORD *)&v47 = v38;
            v34 = v32;
            v46 = v5;
            v45 = Buffer;
            v44 = v36;
            LODWORD(Address) = v26;
            v32 = v27;
            v31 = ThreadInfoFlags;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v28,
              (unsigned int)byte_140270093,
              v29,
              v30,
              (__int64)&v31,
              (__int64)&v32,
              (__int64)&Address,
              (__int64)&v44,
              (__int64)&v45,
              (__int64)&v46,
              (__int64)&v34,
              (__int64)&v47,
              (__int64)&v37);
          }
        }
        if ( Buffer )
          RtlFreeUnicodeString(&UnicodeString);
        if ( v5 )
        {
          if ( Buffer != v5 )
            RtlFreeUnicodeString(&v53);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140198ef0  mov     [rsp+arg_8], rbx
0x140198ef5  mov     [rsp+arg_10], rsi
0x140198efa  push    rdi
0x140198efb  push    r12
0x140198efd  push    r13
0x140198eff  push    r14
0x140198f01  push    r15
0x140198f03  sub     rsp, 300h
0x140198f0a  mov     rax, cs:__security_cookie
0x140198f11  xor     rax, rsp
0x140198f14  mov     [rsp+328h+var_38], rax
0x140198f1c  mov     rbx, rcx
0x140198f1f  mov     [rsp+328h+var_258], rcx
0x140198f27  mov     [rsp+328h+var_250], rcx
0x140198f2f  mov     rdx, 8001000000040000h
0x140198f39  mov     r12d, 1
0x140198f3f  test    cs:W32kEtwEnabledKeyword, rdx
0x140198f46  jz      short loc_140198F83
0x140198f48  mov     al, cs:byte_140293DD8
0x140198f4e  sub     al, r12b
0x140198f51  cmp     al, 2
0x140198f53  jbe     short loc_140198F78
0x140198f55  test    cs:qword_140293DC0, rdx
0x140198f5c  jz      short loc_140198F78
0x140198f5e  mov     rax, cs:qword_140293DC8
0x140198f65  and     rax, rdx
0x140198f68  cmp     rax, cs:qword_140293DC8
0x140198f6f  jnz     short loc_140198F78
0x140198f71  mov     al, r12b
0x140198f74  xor     esi, esi
0x140198f76  jmp     short loc_140198F7D
0x140198f78  xor     esi, esi
0x140198f7a  mov     al, sil
0x140198f7d  test    al, al
0x140198f7f  jz      short loc_140198F85
0x140198f81  jmp     short loc_140198FD2
0x140198f83  xor     esi, esi
0x140198f85  mov     eax, cs:dword_140293F90
0x140198f8b  cmp     eax, 5
0x140198f8e  jbe     short loc_140198FAA
0x140198f90  mov     rdx, 400000000000h
0x140198f9a  lea     rcx, dword_140293F90
0x140198fa1  call    _tlgKeywordOn
0x140198fa6  test    al, al
0x140198fa8  jnz     short loc_140198FD2
0x140198faa  mov     eax, cs:dword_140293F90
0x140198fb0  cmp     eax, 5
0x140198fb3  jbe     loc_1401997C3
0x140198fb9  mov     edx, 40000h
0x140198fbe  lea     rcx, dword_140293F90
0x140198fc5  call    _tlgKeywordOn
0x140198fca  test    al, al
0x140198fcc  jz      loc_1401997C3
0x140198fd2  mov     [rsp+328h+var_2A8], esi
0x140198fd9  mov     [rsp+328h+var_2A0], esi
0x140198fe0  mov     [rsp+328h+var_2A4], esi
0x140198fe7  mov     [rsp+328h+var_280], rsi
0x140198fef  xorps   xmm0, xmm0
0x140198ff2  movups  xmmword ptr [rsp+328h+UnicodeString.Length], xmm0
0x140198ffa  xorps   xmm1, xmm1
0x140198ffd  movups  xmmword ptr [rsp+328h+var_1F0.Length], xmm1
0x140199005  movups  [rsp+328h+var_268], xmm0
0x14019900d  mov     rax, 0FFFFF78000000320h
0x140199017  mov     rax, [rax]
0x14019901a  mov     rcx, 0FFFFF78000000004h
0x140199024  mov     edx, [rcx]
0x140199026  imul    rdx, rax
0x14019902a  shr     rdx, 18h; unsigned int
0x14019902e  lea     rax, [rsp+328h+var_280]
0x140199036  mov     [rsp+328h+var_300], rax; unsigned __int64 *
0x14019903b  lea     rax, [rsp+328h+var_2A4]
0x140199043  mov     [rsp+328h+var_308], rax; unsigned int *
0x140199048  lea     r9, [rsp+328h+var_2A0]; unsigned int *
0x140199050  lea     r8, [rsp+328h+var_2A8]; unsigned int *
0x140199058  mov     rcx, [rbx+1D0h]; struct tagQ *
0x14019905f  call    ?EtwpGetLastInputProcessTime@@YAXQEAUtagQ@@KPEAK1PEAIPEA_K@Z; EtwpGetLastInputProcessTime(tagQ * const,ulong,ulong *,ulong *,uint *,unsigned __int64 *)
0x140199064  cmp     [rsp+328h+var_2A8], 32h ; '2'
0x14019906c  jb      loc_1401997C3
0x140199072  cmp     [rsp+328h+var_2A0], 32h ; '2'
0x14019907a  jb      loc_1401997C3
0x140199080  mov     rcx, rbx; struct tagTHREADINFO *
0x140199083  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x140199088  mov     r13d, eax
0x14019908b  mov     [rsp+328h+var_29C], eax
0x140199092  test    al, 28h
0x140199094  setz    dl
0x140199097  test    al, 3
0x140199099  setz    cl
0x14019909c  or      dl, cl
0x14019909e  jnz     loc_1401997C3
0x1401990a4  mov     r14, rsi
0x1401990a7  mov     [rsp+328h+var_270], rsi
0x1401990af  mov     r15, rsi
0x1401990b2  mov     [rsp+328h+var_278], rsi
0x1401990ba  xor     r8d, r8d
0x1401990bd  mov     edx, r12d
0x1401990c0  mov     rcx, [rbx+520h]
0x1401990c7  call    ValidateHwndEx
0x1401990cc  mov     rdi, rax
0x1401990cf  test    rax, rax
0x1401990d2  jz      short loc_140199148
0x1401990d4  lea     rdx, [rsp+328h+UnicodeString]; struct _UNICODE_STRING *
0x1401990dc  mov     rcx, rax; struct tagWND *
0x1401990df  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x1401990e4  test    eax, eax
0x1401990e6  cmovns  r14, [rsp+328h+UnicodeString.Buffer]
0x1401990ef  mov     [rsp+328h+var_270], r14
0x1401990f7  call    Is_GetTopLevelWindowSupported
0x1401990fc  test    eax, eax
0x1401990fe  js      short loc_14019910A
0x140199100  mov     rcx, rdi
0x140199103  call    _GetTopLevelWindow
0x140199108  jmp     short loc_14019910D
0x14019910a  mov     rax, rsi
0x14019910d  test    rax, rax
0x140199110  jz      short loc_140199148
0x140199112  cmp     rdi, rax
0x140199115  jz      short loc_14019913D
0x140199117  lea     rdx, [rsp+328h+var_1F0]; struct _UNICODE_STRING *
0x14019911f  mov     rcx, rax; struct tagWND *
0x140199122  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x140199127  test    eax, eax
0x140199129  js      short loc_140199148
0x14019912b  mov     r15, [rsp+328h+var_1F0.Buffer]
0x140199133  mov     [rsp+328h+var_278], r15
0x14019913b  jmp     short loc_140199148
0x14019913d  mov     r15, r14
0x140199140  mov     [rsp+328h+var_278], r14
0x140199148  mov     [rsp+328h+var_288], rsi
0x140199150  mov     [rsp+328h+var_290], rsi
0x140199158  mov     rcx, [rbx]; Thread
0x14019915b  call    cs:__imp_PsGetThreadProcess
0x140199162  nop     dword ptr [rax+rax+00h]
0x140199167  mov     rcx, rax
0x14019916a  call    cs:__imp_PsGetProcessPeb
0x140199171  nop     dword ptr [rax+rax+00h]
0x140199176  mov     [rsp+328h+Address], rax
0x14019917e  mov     [rsp+328h+var_220], 7D0h
0x14019918a  mov     rcx, [rsp+328h+Address]; Address
0x140199192  mov     [rsp+328h+var_220], r12
0x14019919a  mov     r8d, r12d; Alignment
0x14019919d  mov     rdx, r12; Length
0x1401991a0  call    cs:__imp_ProbeForRead
0x1401991a7  nop     dword ptr [rax+rax+00h]
0x1401991ac  mov     rax, [rsp+328h+Address]
0x1401991b4  mov     rbx, [rax+20h]
0x1401991b8  mov     [rsp+328h+var_218], 448h
0x1401991c4  mov     [rsp+328h+var_218], r12
0x1401991cc  mov     r8d, r12d; Alignment
0x1401991cf  mov     rdx, r12; Length
0x1401991d2  mov     rcx, rbx; Address
0x1401991d5  call    cs:__imp_ProbeForRead
0x1401991dc  nop     dword ptr [rax+rax+00h]
0x1401991e1  xorps   xmm0, xmm0
0x1401991e4  movups  [rsp+328h+var_230], xmm0
0x1401991ec  lea     rcx, [rbx+60h]
0x1401991f0  call    RtlReadULongFromUser
0x1401991f5  mov     edi, eax
0x1401991f7  mov     dword ptr [rsp+328h+var_230], edi
0x1401991fe  lea     rcx, [rbx+68h]
0x140199202  call    RtlReadULong64FromUser
0x140199207  mov     qword ptr [rsp+328h+var_230+8], rax
0x14019920f  movzx   edx, di
0x140199212  mov     word ptr [rsp+328h+var_268], dx
0x14019921a  shr     edi, 10h
0x14019921d  mov     word ptr [rsp+328h+var_268+2], di
0x140199225  mov     ecx, dword ptr [rsp+328h+var_230+4]
0x14019922c  mov     dword ptr [rsp+328h+var_268+4], ecx
0x140199233  mov     qword ptr [rsp+328h+var_268+8], rax
0x14019923b  mov     ebx, 2
0x140199240  add     rdx, rbx; Length
0x140199243  mov     r8d, ebx; Alignment
0x140199246  mov     rcx, rax; Address
0x140199249  call    cs:__imp_ProbeForRead
0x140199250  nop     dword ptr [rax+rax+00h]
0x140199255  movzx   eax, word ptr [rsp+328h+var_268]
0x14019925d  cmp     ax, word ptr [rsp+328h+var_268+2]
0x140199265  ja      short loc_1401992E6
0x140199267  mov     byte ptr [rsp+328h+var_268], al
0x14019926e  test    r12b, al
0x140199271  jnz     short loc_1401992E6
0x140199273  mov     rdx, qword ptr [rsp+328h+var_268+8]
0x14019927b  mov     [rsp+328h+var_288], rdx
0x140199283  test    ax, ax
0x140199286  jz      short loc_1401992BF
0x140199288  mov     ecx, eax
0x14019928a  shr     rcx, 1
0x14019928d  mov     rax, rcx
0x140199290  mov     [rsp+328h+var_210], rcx
0x140199298  test    rax, rax
0x14019929b  jz      short loc_1401992BF
0x14019929d  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x1401992a3  jnz     short loc_140199320
0x1401992a5  cmp     rax, rcx
0x1401992a8  jnz     short loc_1401992B3
0x1401992aa  lea     rax, aInvalid; "Invalid"
0x1401992b1  jmp     short loc_1401992B7
0x1401992b3  lea     rax, [rdx+rax*2]
0x1401992b7  mov     [rsp+328h+var_290], rax
0x1401992bf  mov     rax, [rsp+328h+var_290]
0x1401992c7  test    rax, rax
0x1401992ca  jnz     short loc_1401992DC
0x1401992cc  mov     rax, [rsp+328h+var_288]
0x1401992d4  mov     [rsp+328h+var_290], rax
0x1401992dc  mov     rax, [rsp+328h+var_258]
0x1401992e4  jmp     short loc_14019935B
0x1401992e6  test    byte ptr [rsp+328h+var_268], r12b
0x1401992ee  jz      short loc_140199314
0x1401992f0  mov     dword ptr [rsp+328h+Address], 20000h
0x1401992fb  mov     r8d, 471h
0x140199301  mov     edx, dword ptr [rsp+328h+Address]
0x140199308  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14019930f  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140199314  call    cs:__imp_ExRaiseAccessViolation
0x14019931b  nop     dword ptr [rax+rax+00h]
0x140199320  sub     rax, r12
0x140199323  mov     [rsp+328h+var_210], rax
0x14019932b  jmp     loc_140199298
0x140199330  mov     ebx, 2
0x140199335  xor     esi, esi
0x140199337  lea     r12d, [rbx-1]
0x14019933b  mov     r13d, [rsp+328h+var_29C]
0x140199343  mov     r14, [rsp+328h+var_270]
0x14019934b  mov     r15, [rsp+328h+var_278]
0x140199353  mov     rax, [rsp+328h+var_250]
0x14019935b  mov     rcx, [rax+1C8h]
0x140199362  mov     al, [rcx+328h]
0x140199368  and     al, 30h
0x14019936a  cmp     al, 10h
0x14019936c  jnz     loc_14019960A
0x140199372  mov     rcx, [rcx]; Process
0x140199375  call    cs:__imp_PsReferencePrimaryToken
0x14019937c  nop     dword ptr [rax+rax+00h]
0x140199381  mov     rdi, rax
0x140199384  mov     qword ptr [rsp+328h+var_230], rax
0x14019938c  mov     [rsp+328h+var_258], 100h
0x140199398  mov     [rsp+328h+var_250], 82h
0x1401993a4  mov     [rsp+328h+var_300], rsi
0x1401993a9  lea     rax, [rsp+328h+var_250]
0x1401993b1  mov     [rsp+328h+var_308], rax
0x1401993b6  lea     r9, [rsp+328h+var_1C8]
0x1401993be  lea     r8, [rsp+328h+var_258]
0x1401993c6  lea     rdx, [rsp+328h+var_138]
0x1401993ce  mov     rcx, rdi
0x1401993d1  call    cs:__imp_RtlQueryPackageIdentity
0x1401993d8  nop     dword ptr [rax+rax+00h]
0x1401993dd  mov     r9d, eax
0x1401993e0  mov     [rsp+328h+var_29C], eax
0x1401993e7  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, r12b
0x1401993ee  jz      short loc_140199464
0x1401993f0  lea     rax, word_140256630
0x1401993f7  lea     rdx, [rsp+328h+var_1C8]
0x1401993ff  test    r9d, r9d
0x140199402  cmovs   rdx, rax
0x140199406  lea     rcx, [rsp+328h+var_138]
0x14019940e  cmovs   rcx, rax
0x140199412  mov     rax, [rsp+328h+var_280]
0x14019941a  mov     [rsp+328h+var_2D0], rax
0x14019941f  mov     eax, [rsp+328h+var_2A4]
0x140199426  mov     dword ptr [rsp+328h+var_2D8], eax
0x14019942a  mov     [rsp+328h+var_2E0], rdx
0x14019942f  mov     [rsp+328h+var_2E8], rcx
0x140199434  mov     [rsp+328h+var_2F0], r15
0x140199439  mov     [rsp+328h+var_2F8], r14
0x14019943e  mov     eax, [rsp+328h+var_2A0]
0x140199445  mov     dword ptr [rsp+328h+var_300], eax
0x140199449  mov     eax, [rsp+328h+var_2A8]
0x140199450  mov     dword ptr [rsp+328h+var_308], eax
0x140199454  mov     r9d, r13d
0x140199457  call    McTemplateK0qqqzzzzqx_EtwWriteTransfer
0x14019945c  mov     r9d, [rsp+328h+var_29C]
0x140199464  lea     r8, word_140256630
0x14019946b  mov     eax, cs:dword_140293F90
0x140199471  cmp     eax, 5
0x140199474  jbe     loc_1401995DC
0x14019947a  mov     rdx, 400000040000h
0x140199484  lea     rcx, dword_140293F90
0x14019948b  call    _tlgKeywordOn
0x140199490  test    al, al
0x140199492  jz      loc_1401995DC
0x140199498  mov     [rsp+328h+var_29C], ebx
0x14019949f  mov     dword ptr [rsp+328h+Address], r12d
0x1401994a7  mov     rax, [rsp+328h+var_280]
0x1401994af  mov     [rsp+328h+var_280], rax
0x1401994b7  mov     eax, [rsp+328h+var_2A4]
0x1401994be  mov     [rsp+328h+var_2A4], eax
0x1401994c5  mov     [rsp+328h+var_208], r15
0x1401994cd  mov     [rsp+328h+var_248], r14
0x1401994d5  mov     rax, [rsp+328h+var_290]
0x1401994dd  mov     [rsp+328h+var_290], rax
0x1401994e5  lea     rax, [rsp+328h+var_1C8]
0x1401994ed  test    r9d, r9d
0x1401994f0  cmovs   rax, r8
0x1401994f4  mov     [rsp+328h+var_240], rax
0x1401994fc  lea     rax, [rsp+328h+var_138]
0x140199504  cmovs   rax, r8
0x140199508  mov     [rsp+328h+var_238], rax
0x140199510  mov     eax, [rsp+328h+var_2A0]
0x140199517  mov     [rsp+328h+var_2A0], eax
0x14019951e  mov     eax, [rsp+328h+var_2A8]
  ... truncated ...
```
