# CDlpWimCapture::Capture(void (*)(void *,unsigned __int64,unsigned __int64,int *),void *,ushort *,_ULARGE_INTEGER,ulong,ulong)

- ea: `0x18000a088`
- end: `0x18000a4e7`
- name: `?Capture@CDlpWimCapture@@QEAAJP6AXPEAX_K1PEAH@Z0PEAGT_ULARGE_INTEGER@@KK@Z`
- size: `1119`
- prototype: `__int64 __fastcall(CDlpWimCapture *this, void (*)(void *, unsigned __int64, unsigned __int64, int *), void *, unsigned __int16 *, union _ULARGE_INTEGER, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000cad8`

## callees

- `0x180002898`
- `0x18000a088`
- `0x18000aba4`
- `0x18000ea20`
- `0x18000f3d8`
- `0x180012f5c`
- `0x18001fcc8`
- `0x18001fd60`
- `0x18002baec`
- `0x1800309dc`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x18000a273`
- `WIMGAPI!WIMCloseHandle` at `0x18000a291`
- `WIMGAPI!WIMCloseHandle` at `0x18000a38f`
- `WIMGAPI!WIMCloseHandle` at `0x18000a3a2`
- `WIMGAPI!WIMCloseHandle` at `0x18000a3b5`
- `WIMGAPI!WIMCloseHandle` at `0x18000a3c8`
- `WIMGAPI!WIMCloseHandle` at `0x18000a40c`
- `WIMGAPI!WIMCloseHandle` at `0x18000a41b`
- `WIMGAPI!WIMCloseHandle` at `0x18000a273`
- `WIMGAPI!WIMCloseHandle` at `0x18000a291`
- `WIMGAPI!WIMCloseHandle` at `0x18000a38f`
- `WIMGAPI!WIMCloseHandle` at `0x18000a3a2`
- `WIMGAPI!WIMCloseHandle` at `0x18000a3b5`
- `WIMGAPI!WIMCloseHandle` at `0x18000a3c8`
- `WIMGAPI!WIMCloseHandle` at `0x18000a40c`
- `WIMGAPI!WIMCloseHandle` at `0x18000a41b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000a48d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000a4db`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000a48d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000a4db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a3ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a49d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a49d`

## string_xrefs

- `0x18000a343`: `Wim Capture: Capturing [%u] files from [%s] to [%s], PartSize: [0x%I64X]`
- `0x18000a4af`: `Failed to delete [%s]: [0x%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDlpWimCapture::Capture(
        CDlpWimCapture *this,
        void (*a2)(void *, unsigned __int64, unsigned __int64, int *),
        void *a3,
        unsigned __int16 *a4,
        union _ULARGE_INTEGER a5,
        unsigned int a6)
{
  void *v9; // rbx
  void *v10; // rdi
  int v11; // r15d
  __int64 v12; // rcx
  int StringCch; // eax
  const unsigned __int16 **v14; // rsi
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  void *v20; // rdi
  __int64 v21; // rcx
  void *v22; // r15
  __int64 v23; // rcx
  unsigned __int16 *v24; // r12
  int Internal; // eax
  __int64 v26; // r10
  unsigned int *v27; // r12
  int v28; // esi
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rsi
  HANDLE ProcessHeap; // rax
  int v37; // eax
  __int64 v38; // rcx
  unsigned int i; // esi
  __int64 v40; // [rsp+20h] [rbp-20h]
  __int64 v41; // [rsp+28h] [rbp-18h]
  void *v42; // [rsp+80h] [rbp+40h] BYREF
  void *v43; // [rsp+88h] [rbp+48h] BYREF

  v9 = 0;
  v43 = 0;
  v10 = 0;
  v42 = 0;
  if ( !a4 )
  {
    v11 = -2147024809;
    v12 = *((_QWORD *)this + 15);
    if ( v12 )
    {
      LODWORD(v41) = -2147024809;
      LODWORD(v40) = 168;
LABEL_58:
      v37 = CDlpLogT<CEmptyType>::DlpLogFormat(v12, 4, L"%s(%d): Result = 0x%X", L"CDlpWimCapture::Capture", v40, v41);
      v38 = (unsigned int)v37;
      if ( v37 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v37);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v38);
      goto LABEL_61;
    }
    goto LABEL_61;
  }
  if ( !*((_QWORD *)this + 7) )
  {
    v11 = -2147024875;
    v12 = *((_QWORD *)this + 15);
    if ( v12 )
    {
      LODWORD(v41) = -2147024875;
      LODWORD(v40) = 172;
      goto LABEL_58;
    }
LABEL_61:
    for ( i = 0; i < *((_DWORD *)this + 9); ++i )
    {
      if ( !DeleteFileW(*(LPCWSTR *)(*((_QWORD *)this + 5) + 8LL * (int)i)) && *((_QWORD *)this + 15) )
      {
        LODWORD(v40) = GetLastError();
        CDlpLogT<CEmptyType>::DlpLogFormat(
          *((_QWORD *)this + 15),
          3,
          L"Failed to delete [%s]: [0x%x]",
          *(_QWORD *)(*((_QWORD *)this + 5) + 8LL * (int)i),
          v40);
      }
    }
    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 32, 0);
    DeleteFileW(*((LPCWSTR *)this + 6));
    goto LABEL_45;
  }
  a6 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a4, &a6);
  v11 = StringCch;
  v14 = (const unsigned __int16 **)((char *)this + 64);
  if ( StringCch < 0
    || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a4),
        v11 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v11 < 0 )
  {
    v12 = *((_QWORD *)this + 15);
    if ( v12 )
    {
      LODWORD(v41) = v11;
      LODWORD(v40) = 176;
      goto LABEL_58;
    }
    goto LABEL_61;
  }
  *((_DWORD *)this + 32) = 2;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 12) = CDlpActionLayoutUsb::WimCaptureCallback;
  *((_QWORD *)this + 13) = a3;
  *((union _ULARGE_INTEGER *)this + 18) = a5;
  v15 = CDlpWimCapture::InvokeCallback(this, 0, 0);
  v11 = v15;
  v12 = *((_QWORD *)this + 15);
  if ( v15 < 0 )
  {
    if ( v12 )
    {
      LODWORD(v41) = v15;
      LODWORD(v40) = 186;
      goto LABEL_58;
    }
    goto LABEL_61;
  }
  if ( v12 )
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v12,
      2,
      L"Wim Capture: Creating target WIM file: [%s] (without verification)...",
      *v14);
  v16 = CDlpWimCapture::CreateWimForSplitCapture(this, *v14, &v43, &v42);
  v11 = v16;
  if ( v16 < 0 )
  {
    v17 = *((_QWORD *)this + 15);
    if ( v17 )
    {
      v18 = CDlpLogT<CEmptyType>::DlpLogFormat(v17, 4, L"%s(%d): Result = 0x%X", L"CDlpWimCapture::Capture", 191, v16);
      v19 = (unsigned int)v18;
      if ( v18 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v18);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
    }
    v9 = v43;
    v10 = v42;
    goto LABEL_61;
  }
  v20 = v43;
  v9 = 0;
  v43 = 0;
  v21 = *((_QWORD *)this + 10);
  if ( v21 )
    WIMCloseHandle(v21);
  *((_QWORD *)this + 10) = v20;
  v22 = v42;
  v10 = 0;
  v42 = 0;
  v23 = *((_QWORD *)this + 11);
  if ( v23 )
    WIMCloseHandle(v23);
  *((_QWORD *)this + 11) = v22;
  *((_DWORD *)this + 33) = 1;
  v24 = (unsigned __int16 *)*v14;
  if ( !*v14 )
  {
    v24 = 0;
    goto LABEL_31;
  }
  a6 = 0;
  Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v24, &a6);
  v11 = Internal;
  if ( Internal >= 0 )
  {
LABEL_31:
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v24);
    v11 = Internal;
    if ( Internal >= 0 )
      goto LABEL_33;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
LABEL_33:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  v26 = *((_QWORD *)this + 15);
  if ( v11 < 0 )
  {
    if ( v26 )
    {
      LODWORD(v41) = v11;
      LODWORD(v40) = 197;
      v12 = *((_QWORD *)this + 15);
      goto LABEL_58;
    }
    goto LABEL_61;
  }
  v27 = (unsigned int *)((char *)this + 20);
  if ( v26 )
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v26,
      2,
      L"Wim Capture: Capturing [%u] files from [%s] to [%s], PartSize: [0x%I64X]",
      *v27,
      *((_QWORD *)this + 7),
      *v14,
      *((_QWORD *)this + 18));
  v28 = 0;
  if ( *v27 )
  {
    while ( 1 )
    {
      v29 = CDlpWimCapture::WimSplitCaptureFile(this, *(const unsigned __int16 **)(*((_QWORD *)this + 3) + 8LL * v28));
      v11 = v29;
      if ( v29 < 0 )
        break;
      if ( (unsigned int)++v28 >= *((_DWORD *)this + 5) )
        goto LABEL_41;
    }
    v12 = *((_QWORD *)this + 15);
    if ( !v12 )
      goto LABEL_61;
    LODWORD(v41) = v29;
    LODWORD(v40) = 210;
    goto LABEL_58;
  }
LABEL_41:
  v30 = *((_QWORD *)this + 11);
  if ( v30 )
  {
    WIMCloseHandle(v30);
    *((_QWORD *)this + 11) = 0;
  }
  v31 = *((_QWORD *)this + 10);
  if ( v31 )
  {
    WIMCloseHandle(v31);
    *((_QWORD *)this + 10) = 0;
  }
LABEL_45:
  v32 = *((_QWORD *)this + 10);
  if ( v32 )
  {
    WIMCloseHandle(v32);
    *((_QWORD *)this + 10) = 0;
  }
  v33 = *((_QWORD *)this + 11);
  if ( v33 )
  {
    WIMCloseHandle(v33);
    *((_QWORD *)this + 11) = 0;
  }
  v34 = *((_QWORD *)this + 6);
  if ( v34 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v34 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 6) = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v10 )
    WIMCloseHandle(v10);
  if ( v9 )
    WIMCloseHandle(v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a088  mov     rax, rsp
0x18000a08b  mov     [rax+18h], rbx
0x18000a08f  mov     [rax+10h], rdx
0x18000a093  push    rbp
0x18000a094  push    rsi
0x18000a095  push    rdi
0x18000a096  push    r12
0x18000a098  push    r13
0x18000a09a  push    r14
0x18000a09c  push    r15
0x18000a09e  mov     rbp, rsp
0x18000a0a1  sub     rsp, 40h
0x18000a0a5  mov     r12, r9
0x18000a0a8  mov     r13, r8
0x18000a0ab  mov     r14, rcx
0x18000a0ae  xor     ebx, ebx
0x18000a0b0  mov     [rbp+arg_8], rbx
0x18000a0b4  xor     edi, edi
0x18000a0b6  mov     [rbp+arg_0], rdi
0x18000a0ba  test    r9, r9
0x18000a0bd  jnz     short loc_18000A0E5
0x18000a0bf  mov     r15d, 80070057h
0x18000a0c5  mov     rcx, [rcx+78h]
0x18000a0c9  xor     r13d, r13d
0x18000a0cc  test    rcx, rcx
0x18000a0cf  jz      loc_18000A479
0x18000a0d5  mov     [rax-50h], r15d
0x18000a0d9  mov     dword ptr [rax-58h], 0A8h
0x18000a0e0  jmp     loc_18000A451
0x18000a0e5  cmp     qword ptr [rcx+38h], 0
0x18000a0ea  jnz     short loc_18000A114
0x18000a0ec  mov     r15d, 80070015h
0x18000a0f2  mov     rcx, [rcx+78h]
0x18000a0f6  xor     r13d, r13d
0x18000a0f9  test    rcx, rcx
0x18000a0fc  jz      loc_18000A479
0x18000a102  mov     dword ptr [rsp+40h+var_18], r15d
0x18000a107  mov     dword ptr [rsp+40h+var_20], 0ACh
0x18000a10f  jmp     loc_18000A451
0x18000a114  mov     [rbp+arg_28], 0
0x18000a11b  lea     rdx, [rbp+arg_28]
0x18000a11f  mov     rcx, r12
0x18000a122  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18000a127  mov     r15d, eax
0x18000a12a  lea     rsi, [r14+40h]
0x18000a12e  test    eax, eax
0x18000a130  js      short loc_18000A147
0x18000a132  mov     r8, rsi
0x18000a135  mov     edx, [rbp+arg_28]
0x18000a138  mov     rcx, r12; Src
0x18000a13b  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18000a140  mov     r15d, eax
0x18000a143  test    eax, eax
0x18000a145  jns     short loc_18000A14E
0x18000a147  mov     ecx, eax
0x18000a149  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a14e  mov     ecx, r15d
0x18000a151  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a156  test    r15d, r15d
0x18000a159  jns     short loc_18000A17D
0x18000a15b  mov     rcx, [r14+78h]
0x18000a15f  xor     r13d, r13d
0x18000a162  test    rcx, rcx
0x18000a165  jz      loc_18000A479
0x18000a16b  mov     dword ptr [rsp+40h+var_18], r15d
0x18000a170  mov     dword ptr [rsp+40h+var_20], 0B0h
0x18000a178  jmp     loc_18000A451
0x18000a17d  mov     r12d, 2
0x18000a183  mov     [r14+80h], r12d
0x18000a18a  mov     dword ptr [r14+88h], 0
0x18000a195  lea     rax, ?WimCaptureCallback@CDlpActionLayoutUsb@@CAXPEAX_K1PEAH@Z; CDlpActionLayoutUsb::WimCaptureCallback(void *,unsigned __int64,unsigned __int64,int *)
0x18000a19c  mov     [r14+60h], rax
0x18000a1a0  mov     [r14+68h], r13
0x18000a1a4  mov     rax, qword ptr [rbp+arg_20]
0x18000a1a8  mov     [r14+90h], rax
0x18000a1af  xor     r8d, r8d; unsigned __int64
0x18000a1b2  xor     edx, edx; unsigned __int64
0x18000a1b4  mov     rcx, r14; this
0x18000a1b7  call    ?InvokeCallback@CDlpWimCapture@@AEAAJ_K0@Z; CDlpWimCapture::InvokeCallback(unsigned __int64,unsigned __int64)
0x18000a1bc  mov     r15d, eax
0x18000a1bf  mov     rcx, [r14+78h]
0x18000a1c3  xor     r13d, r13d
0x18000a1c6  test    eax, eax
0x18000a1c8  jns     short loc_18000A1E4
0x18000a1ca  test    rcx, rcx
0x18000a1cd  jz      loc_18000A479
0x18000a1d3  mov     dword ptr [rsp+40h+var_18], eax
0x18000a1d7  mov     dword ptr [rsp+40h+var_20], 0BAh
0x18000a1df  jmp     loc_18000A451
0x18000a1e4  test    rcx, rcx
0x18000a1e7  jz      short loc_18000A1FB
0x18000a1e9  mov     r9, [rsi]
0x18000a1ec  lea     r8, aWimCaptureCrea; "Wim Capture: Creating target WIM file: "...
0x18000a1f3  mov     edx, r12d
0x18000a1f6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000a1fb  lea     r9, [rbp+arg_0]; void **
0x18000a1ff  lea     r8, [rbp+arg_8]; void **
0x18000a203  mov     rdx, [rsi]; unsigned __int16 *
0x18000a206  mov     rcx, r14; this
0x18000a209  call    ?CreateWimForSplitCapture@CDlpWimCapture@@AEAAJPEBGPEAPEAX1@Z; CDlpWimCapture::CreateWimForSplitCapture(ushort const *,void * *,void * *)
0x18000a20e  mov     r15d, eax
0x18000a211  test    eax, eax
0x18000a213  jns     short loc_18000A25F
0x18000a215  mov     rcx, [r14+78h]
0x18000a219  test    rcx, rcx
0x18000a21c  jz      short loc_18000A252
0x18000a21e  mov     dword ptr [rsp+40h+var_18], eax
0x18000a222  mov     dword ptr [rsp+40h+var_20], 0BFh
0x18000a22a  lea     r9, aCdlpwimcapture_5; "CDlpWimCapture::Capture"
0x18000a231  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000a238  mov     edx, 4
0x18000a23d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000a242  mov     ecx, eax
0x18000a244  test    eax, eax
0x18000a246  jns     short loc_18000A24D
0x18000a248  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a24d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a252  mov     rbx, [rbp+arg_8]
0x18000a256  mov     rdi, [rbp+arg_0]
0x18000a25a  jmp     loc_18000A479
0x18000a25f  mov     rdi, [rbp+arg_8]
0x18000a263  mov     rbx, r13
0x18000a266  mov     [rbp+arg_8], rbx
0x18000a26a  mov     rcx, [r14+50h]
0x18000a26e  test    rcx, rcx
0x18000a271  jz      short loc_18000A279
0x18000a273  call    cs:__imp_WIMCloseHandle
0x18000a279  mov     [r14+50h], rdi
0x18000a27d  mov     r15, [rbp+arg_0]
0x18000a281  mov     rdi, r13
0x18000a284  mov     [rbp+arg_0], r13
0x18000a288  mov     rcx, [r14+58h]
0x18000a28c  test    rcx, rcx
0x18000a28f  jz      short loc_18000A297
0x18000a291  call    cs:__imp_WIMCloseHandle
0x18000a297  mov     [r14+58h], r15
0x18000a29b  mov     dword ptr [r14+84h], 1
0x18000a2a6  mov     r12, [rsi]
0x18000a2a9  test    r12, r12
0x18000a2ac  jnz     short loc_18000A2B6
0x18000a2ae  mov     r12, r13
0x18000a2b1  mov     edx, r13d
0x18000a2b4  jmp     short loc_18000A2D0
0x18000a2b6  mov     [rbp+arg_28], r13d
0x18000a2ba  lea     rdx, [rbp+arg_28]
0x18000a2be  mov     rcx, r12
0x18000a2c1  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18000a2c6  mov     r15d, eax
0x18000a2c9  test    eax, eax
0x18000a2cb  js      short loc_18000A2E3
0x18000a2cd  mov     edx, [rbp+arg_28]
0x18000a2d0  lea     r8, [r14+30h]
0x18000a2d4  mov     rcx, r12; Src
0x18000a2d7  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18000a2dc  mov     r15d, eax
0x18000a2df  test    eax, eax
0x18000a2e1  jns     short loc_18000A2EA
0x18000a2e3  mov     ecx, eax
0x18000a2e5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a2ea  mov     ecx, r15d
0x18000a2ed  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a2f2  mov     r10, [r14+78h]
0x18000a2f6  test    r15d, r15d
0x18000a2f9  jns     short loc_18000A319
0x18000a2fb  test    r10, r10
0x18000a2fe  jz      loc_18000A479
0x18000a304  mov     dword ptr [rsp+40h+var_18], r15d
0x18000a309  mov     dword ptr [rsp+40h+var_20], 0C5h
0x18000a311  mov     rcx, r10
0x18000a314  jmp     loc_18000A451
0x18000a319  lea     r12, [r14+14h]
0x18000a31d  test    r10, r10
0x18000a320  jz      short loc_18000A357
0x18000a322  mov     rcx, [r14+90h]
0x18000a329  mov     r8, [rsi]
0x18000a32c  mov     rax, [r14+38h]
0x18000a330  mov     [rsp+40h+var_10], rcx
0x18000a335  mov     [rsp+40h+var_18], r8
0x18000a33a  mov     [rsp+40h+var_20], rax
0x18000a33f  mov     r9d, [r12]
0x18000a343  lea     r8, aWimCaptureCapt_0; "Wim Capture: Capturing [%u] files from "...
0x18000a34a  mov     edx, 2
0x18000a34f  mov     rcx, r10
0x18000a352  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000a357  mov     esi, r13d
0x18000a35a  cmp     [r12], r13d
0x18000a35e  jbe     short loc_18000A386
0x18000a360  mov     rdx, [r14+18h]
0x18000a364  movsxd  rax, esi
0x18000a367  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x18000a36b  mov     rcx, r14; this
0x18000a36e  call    ?WimSplitCaptureFile@CDlpWimCapture@@AEAAJPEBG@Z; CDlpWimCapture::WimSplitCaptureFile(ushort const *)
0x18000a373  mov     r15d, eax
0x18000a376  test    eax, eax
0x18000a378  js      loc_18000A43C
0x18000a37e  inc     esi
0x18000a380  cmp     esi, [r14+14h]
0x18000a384  jb      short loc_18000A360
0x18000a386  mov     rcx, [r14+58h]
0x18000a38a  test    rcx, rcx
0x18000a38d  jz      short loc_18000A399
0x18000a38f  call    cs:__imp_WIMCloseHandle
0x18000a395  mov     [r14+58h], r13
0x18000a399  mov     rcx, [r14+50h]
0x18000a39d  test    rcx, rcx
0x18000a3a0  jz      short loc_18000A3AC
0x18000a3a2  call    cs:__imp_WIMCloseHandle
0x18000a3a8  mov     [r14+50h], r13
0x18000a3ac  mov     rcx, [r14+50h]
0x18000a3b0  test    rcx, rcx
0x18000a3b3  jz      short loc_18000A3BF
0x18000a3b5  call    cs:__imp_WIMCloseHandle
0x18000a3bb  mov     [r14+50h], r13
0x18000a3bf  mov     rcx, [r14+58h]
0x18000a3c3  test    rcx, rcx
0x18000a3c6  jz      short loc_18000A3D2
0x18000a3c8  call    cs:__imp_WIMCloseHandle
0x18000a3ce  mov     [r14+58h], r13
0x18000a3d2  mov     rsi, [r14+30h]
0x18000a3d6  test    rsi, rsi
0x18000a3d9  jz      short loc_18000A3FB
0x18000a3db  call    cs:__imp_GetProcessHeap
0x18000a3e1  mov     rcx, rax; hHeap
0x18000a3e4  lea     r8, [rsi-4]; lpMem
0x18000a3e8  xor     edx, edx; dwFlags
0x18000a3ea  call    cs:__imp_HeapFree
0x18000a3f0  xor     ecx, ecx
0x18000a3f2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a3f7  mov     [r14+30h], r13
0x18000a3fb  mov     ecx, r15d
0x18000a3fe  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a403  nop
0x18000a404  test    rdi, rdi
0x18000a407  jz      short loc_18000A413
0x18000a409  mov     rcx, rdi
0x18000a40c  call    cs:__imp_WIMCloseHandle
0x18000a412  nop
0x18000a413  test    rbx, rbx
0x18000a416  jz      short loc_18000A421
0x18000a418  mov     rcx, rbx
0x18000a41b  call    cs:__imp_WIMCloseHandle
0x18000a421  mov     eax, r15d
0x18000a424  mov     rbx, [rsp+40h+arg_10]
0x18000a42c  add     rsp, 40h
0x18000a430  pop     r15
0x18000a432  pop     r14
0x18000a434  pop     r13
0x18000a436  pop     r12
0x18000a438  pop     rdi
0x18000a439  pop     rsi
0x18000a43a  pop     rbp
0x18000a43b  retn
0x18000a43c  mov     rcx, [r14+78h]
0x18000a440  test    rcx, rcx
0x18000a443  jz      short loc_18000A479
0x18000a445  mov     dword ptr [rsp+40h+var_18], eax
0x18000a449  mov     dword ptr [rsp+40h+var_20], 0D2h
0x18000a451  lea     r9, aCdlpwimcapture_5; "CDlpWimCapture::Capture"
0x18000a458  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000a45f  mov     edx, 4
0x18000a464  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000a469  test    eax, eax
0x18000a46b  mov     ecx, eax
0x18000a46d  jns     short loc_18000A474
0x18000a46f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a474  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a479  mov     esi, r13d
0x18000a47c  cmp     [r14+24h], r13d
0x18000a480  jbe     short loc_18000A4CC
0x18000a482  mov     rcx, [r14+28h]
0x18000a486  movsxd  r12, esi
0x18000a489  mov     rcx, [rcx+r12*8]; lpFileName
0x18000a48d  call    cs:__imp_DeleteFileW
0x18000a493  test    eax, eax
0x18000a495  jnz     short loc_18000A4C4
0x18000a497  cmp     [r14+78h], r13
0x18000a49b  jz      short loc_18000A4C4
0x18000a49d  call    cs:__imp_GetLastError
0x18000a4a3  mov     rcx, [r14+28h]
0x18000a4a7  mov     dword ptr [rsp+40h+var_20], eax
0x18000a4ab  mov     r9, [rcx+r12*8]
0x18000a4af  lea     r8, aFailedToDelete_0; "Failed to delete [%s]: [0x%x]"
0x18000a4b6  mov     edx, 3
0x18000a4bb  mov     rcx, [r14+78h]
0x18000a4bf  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000a4c4  inc     esi
0x18000a4c6  cmp     esi, [r14+24h]
0x18000a4ca  jb      short loc_18000A482
0x18000a4cc  lea     rcx, [r14+20h]
0x18000a4d0  xor     edx, edx
0x18000a4d2  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18000a4d7  mov     rcx, [r14+30h]; lpFileName
0x18000a4db  call    cs:__imp_DeleteFileW
0x18000a4e1  jmp     loc_18000A3AC
```
