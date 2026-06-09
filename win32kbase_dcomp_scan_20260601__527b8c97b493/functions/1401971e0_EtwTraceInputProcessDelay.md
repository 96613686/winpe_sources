# EtwTraceInputProcessDelay

- ea: `0x1401971e0`
- end: `0x140197ae1`
- name: `EtwTraceInputProcessDelay`
- size: `2305`
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
- `0x1401155c4`
- `0x1401440e8`
- `0x14014c5d8`
- `0x14014d558`
- `0x14015fd3c`
- `0x1401940e0`
- `0x1401971e0`
- `0x1401aa4fc`
- `0x140238b10`
- `0x1402bd208`
- `0x1402bd244`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x14019745a`
- `ntoskrnl!PsGetProcessPeb` at `0x14019745a`
- `ntoskrnl!ProbeForRead` at `0x140197490`
- `ntoskrnl!ProbeForRead` at `0x1401974c5`
- `ntoskrnl!ProbeForRead` at `0x140197539`
- `ntoskrnl!ProbeForRead` at `0x140197490`
- `ntoskrnl!ProbeForRead` at `0x1401974c5`
- `ntoskrnl!ProbeForRead` at `0x140197539`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140197604`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140197604`
- `ntoskrnl!PsGetThreadProcess` at `0x14019744b`
- `ntoskrnl!PsGetThreadProcess` at `0x14019744b`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140197665`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140197665`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140197a89`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140197aa7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140197a89`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140197aa7`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1401978e9`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1401978e9`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1401976c1`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1401976c1`

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
    && ((unsigned __int8)(byte_140294DD8 - 1) <= 2u
     || (qword_140294DC0 & 0x8001000000040000uLL) == 0
     || (qword_140294DC8 & 0x8001000000040000uLL) != qword_140294DC8
      ? (v2 = 0)
      : (v2 = 1),
        v2)
    || (unsigned int)dword_140294F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140294F90, 0x400000000000LL)
    || (unsigned int)dword_140294F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140294F90, 0x40000) )
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
              v19 = &word_140257388;
            v20 = (const WCHAR *)v55;
            if ( v18 < 0 )
              v20 = &word_140257388;
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
          if ( (unsigned int)dword_140294F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140294F90, 0x400000040000LL) )
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
              (unsigned int)byte_1402703CD,
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
          if ( (unsigned int)dword_140294F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140294F90, 0x400000040000LL) )
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
              (unsigned int)byte_140270313,
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
0x1401971e0  mov     [rsp+arg_8], rbx
0x1401971e5  mov     [rsp+arg_10], rsi
0x1401971ea  push    rdi
0x1401971eb  push    r12
0x1401971ed  push    r13
0x1401971ef  push    r14
0x1401971f1  push    r15
0x1401971f3  sub     rsp, 300h
0x1401971fa  mov     rax, cs:__security_cookie
0x140197201  xor     rax, rsp
0x140197204  mov     [rsp+328h+var_38], rax
0x14019720c  mov     rbx, rcx
0x14019720f  mov     [rsp+328h+var_258], rcx
0x140197217  mov     [rsp+328h+var_250], rcx
0x14019721f  mov     rdx, 8001000000040000h
0x140197229  mov     r12d, 1
0x14019722f  test    cs:W32kEtwEnabledKeyword, rdx
0x140197236  jz      short loc_140197273
0x140197238  mov     al, cs:byte_140294DD8
0x14019723e  sub     al, r12b
0x140197241  cmp     al, 2
0x140197243  jbe     short loc_140197268
0x140197245  test    cs:qword_140294DC0, rdx
0x14019724c  jz      short loc_140197268
0x14019724e  mov     rax, cs:qword_140294DC8
0x140197255  and     rax, rdx
0x140197258  cmp     rax, cs:qword_140294DC8
0x14019725f  jnz     short loc_140197268
0x140197261  mov     al, r12b
0x140197264  xor     esi, esi
0x140197266  jmp     short loc_14019726D
0x140197268  xor     esi, esi
0x14019726a  mov     al, sil
0x14019726d  test    al, al
0x14019726f  jz      short loc_140197275
0x140197271  jmp     short loc_1401972C2
0x140197273  xor     esi, esi
0x140197275  mov     eax, cs:dword_140294F90
0x14019727b  cmp     eax, 5
0x14019727e  jbe     short loc_14019729A
0x140197280  mov     rdx, 400000000000h
0x14019728a  lea     rcx, dword_140294F90
0x140197291  call    _tlgKeywordOn
0x140197296  test    al, al
0x140197298  jnz     short loc_1401972C2
0x14019729a  mov     eax, cs:dword_140294F90
0x1401972a0  cmp     eax, 5
0x1401972a3  jbe     loc_140197AB3
0x1401972a9  mov     edx, 40000h
0x1401972ae  lea     rcx, dword_140294F90
0x1401972b5  call    _tlgKeywordOn
0x1401972ba  test    al, al
0x1401972bc  jz      loc_140197AB3
0x1401972c2  mov     [rsp+328h+var_2A8], esi
0x1401972c9  mov     [rsp+328h+var_2A0], esi
0x1401972d0  mov     [rsp+328h+var_2A4], esi
0x1401972d7  mov     [rsp+328h+var_280], rsi
0x1401972df  xorps   xmm0, xmm0
0x1401972e2  movups  xmmword ptr [rsp+328h+UnicodeString.Length], xmm0
0x1401972ea  xorps   xmm1, xmm1
0x1401972ed  movups  xmmword ptr [rsp+328h+var_1F0.Length], xmm1
0x1401972f5  movups  [rsp+328h+var_268], xmm0
0x1401972fd  mov     rax, 0FFFFF78000000320h
0x140197307  mov     rax, [rax]
0x14019730a  mov     rcx, 0FFFFF78000000004h
0x140197314  mov     edx, [rcx]
0x140197316  imul    rdx, rax
0x14019731a  shr     rdx, 18h; unsigned int
0x14019731e  lea     rax, [rsp+328h+var_280]
0x140197326  mov     [rsp+328h+var_300], rax; unsigned __int64 *
0x14019732b  lea     rax, [rsp+328h+var_2A4]
0x140197333  mov     [rsp+328h+var_308], rax; unsigned int *
0x140197338  lea     r9, [rsp+328h+var_2A0]; unsigned int *
0x140197340  lea     r8, [rsp+328h+var_2A8]; unsigned int *
0x140197348  mov     rcx, [rbx+1D0h]; struct tagQ *
0x14019734f  call    ?EtwpGetLastInputProcessTime@@YAXQEAUtagQ@@KPEAK1PEAIPEA_K@Z; EtwpGetLastInputProcessTime(tagQ * const,ulong,ulong *,ulong *,uint *,unsigned __int64 *)
0x140197354  cmp     [rsp+328h+var_2A8], 32h ; '2'
0x14019735c  jb      loc_140197AB3
0x140197362  cmp     [rsp+328h+var_2A0], 32h ; '2'
0x14019736a  jb      loc_140197AB3
0x140197370  mov     rcx, rbx; struct tagTHREADINFO *
0x140197373  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x140197378  mov     r13d, eax
0x14019737b  mov     [rsp+328h+var_29C], eax
0x140197382  test    al, 28h
0x140197384  setz    dl
0x140197387  test    al, 3
0x140197389  setz    cl
0x14019738c  or      dl, cl
0x14019738e  jnz     loc_140197AB3
0x140197394  mov     r14, rsi
0x140197397  mov     [rsp+328h+var_270], rsi
0x14019739f  mov     r15, rsi
0x1401973a2  mov     [rsp+328h+var_278], rsi
0x1401973aa  xor     r8d, r8d
0x1401973ad  mov     edx, r12d
0x1401973b0  mov     rcx, [rbx+520h]
0x1401973b7  call    ValidateHwndEx
0x1401973bc  mov     rdi, rax
0x1401973bf  test    rax, rax
0x1401973c2  jz      short loc_140197438
0x1401973c4  lea     rdx, [rsp+328h+UnicodeString]; struct _UNICODE_STRING *
0x1401973cc  mov     rcx, rax; struct tagWND *
0x1401973cf  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x1401973d4  test    eax, eax
0x1401973d6  cmovns  r14, [rsp+328h+UnicodeString.Buffer]
0x1401973df  mov     [rsp+328h+var_270], r14
0x1401973e7  call    Is_GetTopLevelWindowSupported
0x1401973ec  test    eax, eax
0x1401973ee  js      short loc_1401973FA
0x1401973f0  mov     rcx, rdi
0x1401973f3  call    _GetTopLevelWindow
0x1401973f8  jmp     short loc_1401973FD
0x1401973fa  mov     rax, rsi
0x1401973fd  test    rax, rax
0x140197400  jz      short loc_140197438
0x140197402  cmp     rdi, rax
0x140197405  jz      short loc_14019742D
0x140197407  lea     rdx, [rsp+328h+var_1F0]; struct _UNICODE_STRING *
0x14019740f  mov     rcx, rax; struct tagWND *
0x140197412  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x140197417  test    eax, eax
0x140197419  js      short loc_140197438
0x14019741b  mov     r15, [rsp+328h+var_1F0.Buffer]
0x140197423  mov     [rsp+328h+var_278], r15
0x14019742b  jmp     short loc_140197438
0x14019742d  mov     r15, r14
0x140197430  mov     [rsp+328h+var_278], r14
0x140197438  mov     [rsp+328h+var_288], rsi
0x140197440  mov     [rsp+328h+var_290], rsi
0x140197448  mov     rcx, [rbx]; Thread
0x14019744b  call    cs:__imp_PsGetThreadProcess
0x140197452  nop     dword ptr [rax+rax+00h]
0x140197457  mov     rcx, rax
0x14019745a  call    cs:__imp_PsGetProcessPeb
0x140197461  nop     dword ptr [rax+rax+00h]
0x140197466  mov     [rsp+328h+Address], rax
0x14019746e  mov     [rsp+328h+var_220], 7D0h
0x14019747a  mov     rcx, [rsp+328h+Address]; Address
0x140197482  mov     [rsp+328h+var_220], r12
0x14019748a  mov     r8d, r12d; Alignment
0x14019748d  mov     rdx, r12; Length
0x140197490  call    cs:__imp_ProbeForRead
0x140197497  nop     dword ptr [rax+rax+00h]
0x14019749c  mov     rax, [rsp+328h+Address]
0x1401974a4  mov     rbx, [rax+20h]
0x1401974a8  mov     [rsp+328h+var_218], 450h
0x1401974b4  mov     [rsp+328h+var_218], r12
0x1401974bc  mov     r8d, r12d; Alignment
0x1401974bf  mov     rdx, r12; Length
0x1401974c2  mov     rcx, rbx; Address
0x1401974c5  call    cs:__imp_ProbeForRead
0x1401974cc  nop     dword ptr [rax+rax+00h]
0x1401974d1  xorps   xmm0, xmm0
0x1401974d4  movups  [rsp+328h+var_230], xmm0
0x1401974dc  lea     rcx, [rbx+60h]
0x1401974e0  call    RtlReadULongFromUser
0x1401974e5  mov     edi, eax
0x1401974e7  mov     dword ptr [rsp+328h+var_230], edi
0x1401974ee  lea     rcx, [rbx+68h]
0x1401974f2  call    RtlReadULong64FromUser
0x1401974f7  mov     qword ptr [rsp+328h+var_230+8], rax
0x1401974ff  movzx   edx, di
0x140197502  mov     word ptr [rsp+328h+var_268], dx
0x14019750a  shr     edi, 10h
0x14019750d  mov     word ptr [rsp+328h+var_268+2], di
0x140197515  mov     ecx, dword ptr [rsp+328h+var_230+4]
0x14019751c  mov     dword ptr [rsp+328h+var_268+4], ecx
0x140197523  mov     qword ptr [rsp+328h+var_268+8], rax
0x14019752b  mov     ebx, 2
0x140197530  add     rdx, rbx; Length
0x140197533  mov     r8d, ebx; Alignment
0x140197536  mov     rcx, rax; Address
0x140197539  call    cs:__imp_ProbeForRead
0x140197540  nop     dword ptr [rax+rax+00h]
0x140197545  movzx   eax, word ptr [rsp+328h+var_268]
0x14019754d  cmp     ax, word ptr [rsp+328h+var_268+2]
0x140197555  ja      short loc_1401975D6
0x140197557  mov     byte ptr [rsp+328h+var_268], al
0x14019755e  test    r12b, al
0x140197561  jnz     short loc_1401975D6
0x140197563  mov     rdx, qword ptr [rsp+328h+var_268+8]
0x14019756b  mov     [rsp+328h+var_288], rdx
0x140197573  test    ax, ax
0x140197576  jz      short loc_1401975AF
0x140197578  mov     ecx, eax
0x14019757a  shr     rcx, 1
0x14019757d  mov     rax, rcx
0x140197580  mov     [rsp+328h+var_210], rcx
0x140197588  test    rax, rax
0x14019758b  jz      short loc_1401975AF
0x14019758d  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x140197593  jnz     short loc_140197610
0x140197595  cmp     rax, rcx
0x140197598  jnz     short loc_1401975A3
0x14019759a  lea     rax, aInvalid; "Invalid"
0x1401975a1  jmp     short loc_1401975A7
0x1401975a3  lea     rax, [rdx+rax*2]
0x1401975a7  mov     [rsp+328h+var_290], rax
0x1401975af  mov     rax, [rsp+328h+var_290]
0x1401975b7  test    rax, rax
0x1401975ba  jnz     short loc_1401975CC
0x1401975bc  mov     rax, [rsp+328h+var_288]
0x1401975c4  mov     [rsp+328h+var_290], rax
0x1401975cc  mov     rax, [rsp+328h+var_258]
0x1401975d4  jmp     short loc_14019764B
0x1401975d6  test    byte ptr [rsp+328h+var_268], r12b
0x1401975de  jz      short loc_140197604
0x1401975e0  mov     dword ptr [rsp+328h+Address], 20000h
0x1401975eb  mov     r8d, 471h
0x1401975f1  mov     edx, dword ptr [rsp+328h+Address]
0x1401975f8  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401975ff  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140197604  call    cs:__imp_ExRaiseAccessViolation
0x14019760b  nop     dword ptr [rax+rax+00h]
0x140197610  sub     rax, r12
0x140197613  mov     [rsp+328h+var_210], rax
0x14019761b  jmp     loc_140197588
0x140197620  mov     ebx, 2
0x140197625  xor     esi, esi
0x140197627  lea     r12d, [rbx-1]
0x14019762b  mov     r13d, [rsp+328h+var_29C]
0x140197633  mov     r14, [rsp+328h+var_270]
0x14019763b  mov     r15, [rsp+328h+var_278]
0x140197643  mov     rax, [rsp+328h+var_250]
0x14019764b  mov     rcx, [rax+1C8h]
0x140197652  mov     al, [rcx+328h]
0x140197658  and     al, 30h
0x14019765a  cmp     al, 10h
0x14019765c  jnz     loc_1401978FA
0x140197662  mov     rcx, [rcx]; Process
0x140197665  call    cs:__imp_PsReferencePrimaryToken
0x14019766c  nop     dword ptr [rax+rax+00h]
0x140197671  mov     rdi, rax
0x140197674  mov     qword ptr [rsp+328h+var_230], rax
0x14019767c  mov     [rsp+328h+var_258], 100h
0x140197688  mov     [rsp+328h+var_250], 82h
0x140197694  mov     [rsp+328h+var_300], rsi
0x140197699  lea     rax, [rsp+328h+var_250]
0x1401976a1  mov     [rsp+328h+var_308], rax
0x1401976a6  lea     r9, [rsp+328h+var_1C8]
0x1401976ae  lea     r8, [rsp+328h+var_258]
0x1401976b6  lea     rdx, [rsp+328h+var_138]
0x1401976be  mov     rcx, rdi
0x1401976c1  call    cs:__imp_RtlQueryPackageIdentity
0x1401976c8  nop     dword ptr [rax+rax+00h]
0x1401976cd  mov     r9d, eax
0x1401976d0  mov     [rsp+328h+var_29C], eax
0x1401976d7  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, r12b
0x1401976de  jz      short loc_140197754
0x1401976e0  lea     rax, word_140257388
0x1401976e7  lea     rdx, [rsp+328h+var_1C8]
0x1401976ef  test    r9d, r9d
0x1401976f2  cmovs   rdx, rax
0x1401976f6  lea     rcx, [rsp+328h+var_138]
0x1401976fe  cmovs   rcx, rax
0x140197702  mov     rax, [rsp+328h+var_280]
0x14019770a  mov     [rsp+328h+var_2D0], rax
0x14019770f  mov     eax, [rsp+328h+var_2A4]
0x140197716  mov     dword ptr [rsp+328h+var_2D8], eax
0x14019771a  mov     [rsp+328h+var_2E0], rdx
0x14019771f  mov     [rsp+328h+var_2E8], rcx
0x140197724  mov     [rsp+328h+var_2F0], r15
0x140197729  mov     [rsp+328h+var_2F8], r14
0x14019772e  mov     eax, [rsp+328h+var_2A0]
0x140197735  mov     dword ptr [rsp+328h+var_300], eax
0x140197739  mov     eax, [rsp+328h+var_2A8]
0x140197740  mov     dword ptr [rsp+328h+var_308], eax
0x140197744  mov     r9d, r13d
0x140197747  call    McTemplateK0qqqzzzzqx_EtwWriteTransfer
0x14019774c  mov     r9d, [rsp+328h+var_29C]
0x140197754  lea     r8, word_140257388
0x14019775b  mov     eax, cs:dword_140294F90
0x140197761  cmp     eax, 5
0x140197764  jbe     loc_1401978CC
0x14019776a  mov     rdx, 400000040000h
0x140197774  lea     rcx, dword_140294F90
0x14019777b  call    _tlgKeywordOn
0x140197780  test    al, al
0x140197782  jz      loc_1401978CC
0x140197788  mov     [rsp+328h+var_29C], ebx
0x14019778f  mov     dword ptr [rsp+328h+Address], r12d
0x140197797  mov     rax, [rsp+328h+var_280]
0x14019779f  mov     [rsp+328h+var_280], rax
0x1401977a7  mov     eax, [rsp+328h+var_2A4]
0x1401977ae  mov     [rsp+328h+var_2A4], eax
0x1401977b5  mov     [rsp+328h+var_208], r15
0x1401977bd  mov     [rsp+328h+var_248], r14
0x1401977c5  mov     rax, [rsp+328h+var_290]
0x1401977cd  mov     [rsp+328h+var_290], rax
0x1401977d5  lea     rax, [rsp+328h+var_1C8]
0x1401977dd  test    r9d, r9d
0x1401977e0  cmovs   rax, r8
0x1401977e4  mov     [rsp+328h+var_240], rax
0x1401977ec  lea     rax, [rsp+328h+var_138]
0x1401977f4  cmovs   rax, r8
0x1401977f8  mov     [rsp+328h+var_238], rax
0x140197800  mov     eax, [rsp+328h+var_2A0]
0x140197807  mov     [rsp+328h+var_2A0], eax
0x14019780e  mov     eax, [rsp+328h+var_2A8]
  ... truncated ...
```
