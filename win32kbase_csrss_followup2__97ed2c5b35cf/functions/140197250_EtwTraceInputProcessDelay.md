# EtwTraceInputProcessDelay

- ea: `0x140197250`
- end: `0x140197b51`
- name: `EtwTraceInputProcessDelay`
- size: `2305`
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
- `0x1401150f4`
- `0x1401446c8`
- `0x14014ba88`
- `0x14014e008`
- `0x14015b53c`
- `0x14016072c`
- `0x140194210`
- `0x140197250`
- `0x1401a9f9c`
- `0x140238160`
- `0x1402bb164`
- `0x1402bb1a0`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x1401974ca`
- `ntoskrnl!PsGetProcessPeb` at `0x1401974ca`
- `ntoskrnl!ProbeForRead` at `0x140197500`
- `ntoskrnl!ProbeForRead` at `0x140197535`
- `ntoskrnl!ProbeForRead` at `0x1401975a9`
- `ntoskrnl!ProbeForRead` at `0x140197500`
- `ntoskrnl!ProbeForRead` at `0x140197535`
- `ntoskrnl!ProbeForRead` at `0x1401975a9`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140197674`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140197674`
- `ntoskrnl!PsGetThreadProcess` at `0x1401974bb`
- `ntoskrnl!PsGetThreadProcess` at `0x1401974bb`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1401976d5`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1401976d5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140197af9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140197b17`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140197af9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140197b17`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140197959`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140197959`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140197731`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140197731`

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
    && ((unsigned __int8)(byte_140292DD8 - 1) <= 2u
     || (qword_140292DC0 & 0x8001000000040000uLL) == 0
     || (qword_140292DC8 & 0x8001000000040000uLL) != qword_140292DC8
      ? (v2 = 0)
      : (v2 = 1),
        v2)
    || (unsigned int)dword_140292F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140292F90, 0x400000000000LL)
    || (unsigned int)dword_140292F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140292F90, 0x40000) )
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
              v19 = &word_1402558A8;
            v20 = (const WCHAR *)v55;
            if ( v18 < 0 )
              v20 = &word_1402558A8;
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
          if ( (unsigned int)dword_140292F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140292F90, 0x400000040000LL) )
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
              (unsigned int)byte_14026F24D,
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
          if ( (unsigned int)dword_140292F90 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140292F90, 0x400000040000LL) )
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
              (unsigned int)byte_14026F193,
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
0x140197250  mov     [rsp+arg_8], rbx
0x140197255  mov     [rsp+arg_10], rsi
0x14019725a  push    rdi
0x14019725b  push    r12
0x14019725d  push    r13
0x14019725f  push    r14
0x140197261  push    r15
0x140197263  sub     rsp, 300h
0x14019726a  mov     rax, cs:__security_cookie
0x140197271  xor     rax, rsp
0x140197274  mov     [rsp+328h+var_38], rax
0x14019727c  mov     rbx, rcx
0x14019727f  mov     [rsp+328h+var_258], rcx
0x140197287  mov     [rsp+328h+var_250], rcx
0x14019728f  mov     rdx, 8001000000040000h
0x140197299  mov     r12d, 1
0x14019729f  test    cs:W32kEtwEnabledKeyword, rdx
0x1401972a6  jz      short loc_1401972E3
0x1401972a8  mov     al, cs:byte_140292DD8
0x1401972ae  sub     al, r12b
0x1401972b1  cmp     al, 2
0x1401972b3  jbe     short loc_1401972D8
0x1401972b5  test    cs:qword_140292DC0, rdx
0x1401972bc  jz      short loc_1401972D8
0x1401972be  mov     rax, cs:qword_140292DC8
0x1401972c5  and     rax, rdx
0x1401972c8  cmp     rax, cs:qword_140292DC8
0x1401972cf  jnz     short loc_1401972D8
0x1401972d1  mov     al, r12b
0x1401972d4  xor     esi, esi
0x1401972d6  jmp     short loc_1401972DD
0x1401972d8  xor     esi, esi
0x1401972da  mov     al, sil
0x1401972dd  test    al, al
0x1401972df  jz      short loc_1401972E5
0x1401972e1  jmp     short loc_140197332
0x1401972e3  xor     esi, esi
0x1401972e5  mov     eax, cs:dword_140292F90
0x1401972eb  cmp     eax, 5
0x1401972ee  jbe     short loc_14019730A
0x1401972f0  mov     rdx, 400000000000h
0x1401972fa  lea     rcx, dword_140292F90
0x140197301  call    _tlgKeywordOn
0x140197306  test    al, al
0x140197308  jnz     short loc_140197332
0x14019730a  mov     eax, cs:dword_140292F90
0x140197310  cmp     eax, 5
0x140197313  jbe     loc_140197B23
0x140197319  mov     edx, 40000h
0x14019731e  lea     rcx, dword_140292F90
0x140197325  call    _tlgKeywordOn
0x14019732a  test    al, al
0x14019732c  jz      loc_140197B23
0x140197332  mov     [rsp+328h+var_2A8], esi
0x140197339  mov     [rsp+328h+var_2A0], esi
0x140197340  mov     [rsp+328h+var_2A4], esi
0x140197347  mov     [rsp+328h+var_280], rsi
0x14019734f  xorps   xmm0, xmm0
0x140197352  movups  xmmword ptr [rsp+328h+UnicodeString.Length], xmm0
0x14019735a  xorps   xmm1, xmm1
0x14019735d  movups  xmmword ptr [rsp+328h+var_1F0.Length], xmm1
0x140197365  movups  [rsp+328h+var_268], xmm0
0x14019736d  mov     rax, 0FFFFF78000000320h
0x140197377  mov     rax, [rax]
0x14019737a  mov     rcx, 0FFFFF78000000004h
0x140197384  mov     edx, [rcx]
0x140197386  imul    rdx, rax
0x14019738a  shr     rdx, 18h; unsigned int
0x14019738e  lea     rax, [rsp+328h+var_280]
0x140197396  mov     [rsp+328h+var_300], rax; unsigned __int64 *
0x14019739b  lea     rax, [rsp+328h+var_2A4]
0x1401973a3  mov     [rsp+328h+var_308], rax; unsigned int *
0x1401973a8  lea     r9, [rsp+328h+var_2A0]; unsigned int *
0x1401973b0  lea     r8, [rsp+328h+var_2A8]; unsigned int *
0x1401973b8  mov     rcx, [rbx+1D0h]; struct tagQ *
0x1401973bf  call    ?EtwpGetLastInputProcessTime@@YAXQEAUtagQ@@KPEAK1PEAIPEA_K@Z; EtwpGetLastInputProcessTime(tagQ * const,ulong,ulong *,ulong *,uint *,unsigned __int64 *)
0x1401973c4  cmp     [rsp+328h+var_2A8], 32h ; '2'
0x1401973cc  jb      loc_140197B23
0x1401973d2  cmp     [rsp+328h+var_2A0], 32h ; '2'
0x1401973da  jb      loc_140197B23
0x1401973e0  mov     rcx, rbx; struct tagTHREADINFO *
0x1401973e3  call    ?EtwpGetThreadInfoFlags@@YAKQEAUtagTHREADINFO@@@Z; EtwpGetThreadInfoFlags(tagTHREADINFO * const)
0x1401973e8  mov     r13d, eax
0x1401973eb  mov     [rsp+328h+var_29C], eax
0x1401973f2  test    al, 28h
0x1401973f4  setz    dl
0x1401973f7  test    al, 3
0x1401973f9  setz    cl
0x1401973fc  or      dl, cl
0x1401973fe  jnz     loc_140197B23
0x140197404  mov     r14, rsi
0x140197407  mov     [rsp+328h+var_270], rsi
0x14019740f  mov     r15, rsi
0x140197412  mov     [rsp+328h+var_278], rsi
0x14019741a  xor     r8d, r8d
0x14019741d  mov     edx, r12d
0x140197420  mov     rcx, [rbx+520h]
0x140197427  call    ValidateHwndEx
0x14019742c  mov     rdi, rax
0x14019742f  test    rax, rax
0x140197432  jz      short loc_1401974A8
0x140197434  lea     rdx, [rsp+328h+UnicodeString]; struct _UNICODE_STRING *
0x14019743c  mov     rcx, rax; struct tagWND *
0x14019743f  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x140197444  test    eax, eax
0x140197446  cmovns  r14, [rsp+328h+UnicodeString.Buffer]
0x14019744f  mov     [rsp+328h+var_270], r14
0x140197457  call    Is_GetTopLevelWindowSupported
0x14019745c  test    eax, eax
0x14019745e  js      short loc_14019746A
0x140197460  mov     rcx, rdi
0x140197463  call    _GetTopLevelWindow
0x140197468  jmp     short loc_14019746D
0x14019746a  mov     rax, rsi
0x14019746d  test    rax, rax
0x140197470  jz      short loc_1401974A8
0x140197472  cmp     rdi, rax
0x140197475  jz      short loc_14019749D
0x140197477  lea     rdx, [rsp+328h+var_1F0]; struct _UNICODE_STRING *
0x14019747f  mov     rcx, rax; struct tagWND *
0x140197482  call    ?EtwpGetClassName@@YAJQEAUtagWND@@PEAU_UNICODE_STRING@@@Z; EtwpGetClassName(tagWND * const,_UNICODE_STRING *)
0x140197487  test    eax, eax
0x140197489  js      short loc_1401974A8
0x14019748b  mov     r15, [rsp+328h+var_1F0.Buffer]
0x140197493  mov     [rsp+328h+var_278], r15
0x14019749b  jmp     short loc_1401974A8
0x14019749d  mov     r15, r14
0x1401974a0  mov     [rsp+328h+var_278], r14
0x1401974a8  mov     [rsp+328h+var_288], rsi
0x1401974b0  mov     [rsp+328h+var_290], rsi
0x1401974b8  mov     rcx, [rbx]; Thread
0x1401974bb  call    cs:__imp_PsGetThreadProcess
0x1401974c2  nop     dword ptr [rax+rax+00h]
0x1401974c7  mov     rcx, rax
0x1401974ca  call    cs:__imp_PsGetProcessPeb
0x1401974d1  nop     dword ptr [rax+rax+00h]
0x1401974d6  mov     [rsp+328h+Address], rax
0x1401974de  mov     [rsp+328h+var_220], 7D0h
0x1401974ea  mov     rcx, [rsp+328h+Address]; Address
0x1401974f2  mov     [rsp+328h+var_220], r12
0x1401974fa  mov     r8d, r12d; Alignment
0x1401974fd  mov     rdx, r12; Length
0x140197500  call    cs:__imp_ProbeForRead
0x140197507  nop     dword ptr [rax+rax+00h]
0x14019750c  mov     rax, [rsp+328h+Address]
0x140197514  mov     rbx, [rax+20h]
0x140197518  mov     [rsp+328h+var_218], 450h
0x140197524  mov     [rsp+328h+var_218], r12
0x14019752c  mov     r8d, r12d; Alignment
0x14019752f  mov     rdx, r12; Length
0x140197532  mov     rcx, rbx; Address
0x140197535  call    cs:__imp_ProbeForRead
0x14019753c  nop     dword ptr [rax+rax+00h]
0x140197541  xorps   xmm0, xmm0
0x140197544  movups  [rsp+328h+var_230], xmm0
0x14019754c  lea     rcx, [rbx+60h]
0x140197550  call    RtlReadULongFromUser
0x140197555  mov     edi, eax
0x140197557  mov     dword ptr [rsp+328h+var_230], edi
0x14019755e  lea     rcx, [rbx+68h]
0x140197562  call    RtlReadULong64FromUser
0x140197567  mov     qword ptr [rsp+328h+var_230+8], rax
0x14019756f  movzx   edx, di
0x140197572  mov     word ptr [rsp+328h+var_268], dx
0x14019757a  shr     edi, 10h
0x14019757d  mov     word ptr [rsp+328h+var_268+2], di
0x140197585  mov     ecx, dword ptr [rsp+328h+var_230+4]
0x14019758c  mov     dword ptr [rsp+328h+var_268+4], ecx
0x140197593  mov     qword ptr [rsp+328h+var_268+8], rax
0x14019759b  mov     ebx, 2
0x1401975a0  add     rdx, rbx; Length
0x1401975a3  mov     r8d, ebx; Alignment
0x1401975a6  mov     rcx, rax; Address
0x1401975a9  call    cs:__imp_ProbeForRead
0x1401975b0  nop     dword ptr [rax+rax+00h]
0x1401975b5  movzx   eax, word ptr [rsp+328h+var_268]
0x1401975bd  cmp     ax, word ptr [rsp+328h+var_268+2]
0x1401975c5  ja      short loc_140197646
0x1401975c7  mov     byte ptr [rsp+328h+var_268], al
0x1401975ce  test    r12b, al
0x1401975d1  jnz     short loc_140197646
0x1401975d3  mov     rdx, qword ptr [rsp+328h+var_268+8]
0x1401975db  mov     [rsp+328h+var_288], rdx
0x1401975e3  test    ax, ax
0x1401975e6  jz      short loc_14019761F
0x1401975e8  mov     ecx, eax
0x1401975ea  shr     rcx, 1
0x1401975ed  mov     rax, rcx
0x1401975f0  mov     [rsp+328h+var_210], rcx
0x1401975f8  test    rax, rax
0x1401975fb  jz      short loc_14019761F
0x1401975fd  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x140197603  jnz     short loc_140197680
0x140197605  cmp     rax, rcx
0x140197608  jnz     short loc_140197613
0x14019760a  lea     rax, aInvalid; "Invalid"
0x140197611  jmp     short loc_140197617
0x140197613  lea     rax, [rdx+rax*2]
0x140197617  mov     [rsp+328h+var_290], rax
0x14019761f  mov     rax, [rsp+328h+var_290]
0x140197627  test    rax, rax
0x14019762a  jnz     short loc_14019763C
0x14019762c  mov     rax, [rsp+328h+var_288]
0x140197634  mov     [rsp+328h+var_290], rax
0x14019763c  mov     rax, [rsp+328h+var_258]
0x140197644  jmp     short loc_1401976BB
0x140197646  test    byte ptr [rsp+328h+var_268], r12b
0x14019764e  jz      short loc_140197674
0x140197650  mov     dword ptr [rsp+328h+Address], 20000h
0x14019765b  mov     r8d, 471h
0x140197661  mov     edx, dword ptr [rsp+328h+Address]
0x140197668  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14019766f  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140197674  call    cs:__imp_ExRaiseAccessViolation
0x14019767b  nop     dword ptr [rax+rax+00h]
0x140197680  sub     rax, r12
0x140197683  mov     [rsp+328h+var_210], rax
0x14019768b  jmp     loc_1401975F8
0x140197690  mov     ebx, 2
0x140197695  xor     esi, esi
0x140197697  lea     r12d, [rbx-1]
0x14019769b  mov     r13d, [rsp+328h+var_29C]
0x1401976a3  mov     r14, [rsp+328h+var_270]
0x1401976ab  mov     r15, [rsp+328h+var_278]
0x1401976b3  mov     rax, [rsp+328h+var_250]
0x1401976bb  mov     rcx, [rax+1C8h]
0x1401976c2  mov     al, [rcx+328h]
0x1401976c8  and     al, 30h
0x1401976ca  cmp     al, 10h
0x1401976cc  jnz     loc_14019796A
0x1401976d2  mov     rcx, [rcx]; Process
0x1401976d5  call    cs:__imp_PsReferencePrimaryToken
0x1401976dc  nop     dword ptr [rax+rax+00h]
0x1401976e1  mov     rdi, rax
0x1401976e4  mov     qword ptr [rsp+328h+var_230], rax
0x1401976ec  mov     [rsp+328h+var_258], 100h
0x1401976f8  mov     [rsp+328h+var_250], 82h
0x140197704  mov     [rsp+328h+var_300], rsi
0x140197709  lea     rax, [rsp+328h+var_250]
0x140197711  mov     [rsp+328h+var_308], rax
0x140197716  lea     r9, [rsp+328h+var_1C8]
0x14019771e  lea     r8, [rsp+328h+var_258]
0x140197726  lea     rdx, [rsp+328h+var_138]
0x14019772e  mov     rcx, rdi
0x140197731  call    cs:__imp_RtlQueryPackageIdentity
0x140197738  nop     dword ptr [rax+rax+00h]
0x14019773d  mov     r9d, eax
0x140197740  mov     [rsp+328h+var_29C], eax
0x140197747  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, r12b
0x14019774e  jz      short loc_1401977C4
0x140197750  lea     rax, word_1402558A8
0x140197757  lea     rdx, [rsp+328h+var_1C8]
0x14019775f  test    r9d, r9d
0x140197762  cmovs   rdx, rax
0x140197766  lea     rcx, [rsp+328h+var_138]
0x14019776e  cmovs   rcx, rax
0x140197772  mov     rax, [rsp+328h+var_280]
0x14019777a  mov     [rsp+328h+var_2D0], rax
0x14019777f  mov     eax, [rsp+328h+var_2A4]
0x140197786  mov     dword ptr [rsp+328h+var_2D8], eax
0x14019778a  mov     [rsp+328h+var_2E0], rdx
0x14019778f  mov     [rsp+328h+var_2E8], rcx
0x140197794  mov     [rsp+328h+var_2F0], r15
0x140197799  mov     [rsp+328h+var_2F8], r14
0x14019779e  mov     eax, [rsp+328h+var_2A0]
0x1401977a5  mov     dword ptr [rsp+328h+var_300], eax
0x1401977a9  mov     eax, [rsp+328h+var_2A8]
0x1401977b0  mov     dword ptr [rsp+328h+var_308], eax
0x1401977b4  mov     r9d, r13d
0x1401977b7  call    McTemplateK0qqqzzzzqx_EtwWriteTransfer
0x1401977bc  mov     r9d, [rsp+328h+var_29C]
0x1401977c4  lea     r8, word_1402558A8
0x1401977cb  mov     eax, cs:dword_140292F90
0x1401977d1  cmp     eax, 5
0x1401977d4  jbe     loc_14019793C
0x1401977da  mov     rdx, 400000040000h
0x1401977e4  lea     rcx, dword_140292F90
0x1401977eb  call    _tlgKeywordOn
0x1401977f0  test    al, al
0x1401977f2  jz      loc_14019793C
0x1401977f8  mov     [rsp+328h+var_29C], ebx
0x1401977ff  mov     dword ptr [rsp+328h+Address], r12d
0x140197807  mov     rax, [rsp+328h+var_280]
0x14019780f  mov     [rsp+328h+var_280], rax
0x140197817  mov     eax, [rsp+328h+var_2A4]
0x14019781e  mov     [rsp+328h+var_2A4], eax
0x140197825  mov     [rsp+328h+var_208], r15
0x14019782d  mov     [rsp+328h+var_248], r14
0x140197835  mov     rax, [rsp+328h+var_290]
0x14019783d  mov     [rsp+328h+var_290], rax
0x140197845  lea     rax, [rsp+328h+var_1C8]
0x14019784d  test    r9d, r9d
0x140197850  cmovs   rax, r8
0x140197854  mov     [rsp+328h+var_240], rax
0x14019785c  lea     rax, [rsp+328h+var_138]
0x140197864  cmovs   rax, r8
0x140197868  mov     [rsp+328h+var_238], rax
0x140197870  mov     eax, [rsp+328h+var_2A0]
0x140197877  mov     [rsp+328h+var_2A0], eax
0x14019787e  mov     eax, [rsp+328h+var_2A8]
  ... truncated ...
```
