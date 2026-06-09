# UtilVerifyFilePath(ushort const *,void *)

- ea: `0x180012d68`
- end: `0x180013263`
- name: `?UtilVerifyFilePath@@YAJPEBGPEAX@Z`
- size: `1275`
- prototype: `int(const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800115c4`

## callees

- `0x180001234`
- `0x180001300`
- `0x180001350`
- `0x1800015b8`
- `0x180001740`
- `0x18000181c`
- `0x180001918`
- `0x180009580`
- `0x1800096a8`
- `0x1800096d0`
- `0x18000f4a8`
- `0x18000f6b0`
- `0x1800118a8`
- `0x180012598`
- `0x180012d68`
- `0x180016a0c`
- `0x180016c50`

## import_xrefs

- `KERNEL32!GetLongPathNameW` at `0x180012fc2`
- `KERNEL32!GetLongPathNameW` at `0x18001304f`
- `KERNEL32!GetLongPathNameW` at `0x180012fc2`
- `KERNEL32!GetLongPathNameW` at `0x18001304f`
- `KERNEL32!GetCurrentProcess` at `0x180012e1f`
- `KERNEL32!GetCurrentProcess` at `0x180012e1f`
- `KERNEL32!GetLastError` at `0x180012fce`
- `KERNEL32!GetLastError` at `0x180012fce`
- `KERNEL32!CompareStringOrdinal` at `0x180013120`
- `KERNEL32!CompareStringOrdinal` at `0x180013120`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x18001312f`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x18001312f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilVerifyFilePath(WCHAR *a1, void *a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rcx
  signed int FinalPathByHandle; // ebx
  HANDLE CurrentProcess; // rax
  int v10; // r8d
  int v11; // r9d
  __int16 *v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // r8
  char v15; // di
  __int64 v16; // rax
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // r9
  DWORD LongPathNameW; // eax
  DWORD v21; // edi
  signed int LastError; // eax
  int v23; // r8d
  int v24; // r9d
  LPWSTR v25; // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // r8d
  __int64 v32; // r9
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  LPWSTR lpszLongPath; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszShortPath; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v39; // [rsp+60h] [rbp-A0h]
  _WORD v40[8]; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v41; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v42; // [rsp+80h] [rbp-80h]
  _WORD v43[8]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v44[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v45[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v46[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v47[24]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR szLongPath[264]; // [rsp+E0h] [rbp-20h] BYREF

  v41 = v43;
  v42 = v43;
  v43[0] = 0;
  lpszShortPath = v40;
  v39 = v40;
  v40[0] = 0;
  if ( (unsigned int)dword_180022000 > 4 && (unsigned __int8)tlgKeywordOn(a1, 8) )
  {
    lpszLongPath = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v4,
      (unsigned int)word_18001C422,
      v5,
      v6,
      (__int64)&lpszLongPath);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !(unsigned int)UtilIsLowRightsProcess(CurrentProcess) )
    {
      if ( (unsigned int)dword_180022000 > 4 && (unsigned __int8)tlgKeywordOn(v7, 8) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v7,
          byte_18001C3F1);
      FinalPathByHandle = 0;
      goto LABEL_62;
    }
    goto LABEL_11;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_11:
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v7, 8) )
      goto LABEL_62;
    LODWORD(lpszLongPath) = FinalPathByHandle;
    v12 = (__int16 *)byte_18001C3C3;
    goto LABEL_14;
  }
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( a1[v14] );
  if ( !v14 )
  {
    FinalPathByHandle = -2147024809;
    goto LABEL_62;
  }
  if ( v41 == v42 || (v15 = 1, *(v42 - 1) != 92) )
    v15 = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpszShortPath,
                           a1) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_180022000 <= 2 || !(unsigned __int8)tlgKeywordOn(v7, 8) )
      goto LABEL_62;
    LODWORD(lpszLongPath) = -2147024882;
    v12 = &word_18001C38E;
LABEL_14:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v7,
      (_DWORD)v12,
      v10,
      v11,
      (__int64)&lpszLongPath);
    goto LABEL_62;
  }
  if ( v15 && (unsigned int)dword_180022000 > 4 && (unsigned __int8)tlgKeywordOn(v7, 8) )
  {
    _tlgWrapBinary<unsigned short,2>(v45, lpszShortPath, (unsigned __int16)(v39 - lpszShortPath));
    v16 = _tlgWrapBinary<unsigned short,2>(v44, v41, (unsigned __int16)(v42 - v41));
    lpszLongPath = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
      v17,
      (unsigned int)byte_18001C32D,
      v18,
      v19,
      (__int64)&lpszLongPath,
      v16,
      v19);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v21 = LongPathNameW;
  if ( !LongPathNameW )
  {
    LastError = GetLastError();
    FinalPathByHandle = LastError;
    if ( LastError > 0 )
      FinalPathByHandle = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v7, 8) )
    {
      LODWORD(lpszLongPath) = FinalPathByHandle;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&dword_18001C2F4,
        v23,
        v24,
        (__int64)&lpszLongPath);
    }
LABEL_43:
    if ( FinalPathByHandle < 0 )
      goto LABEL_62;
    goto LABEL_48;
  }
  if ( LongPathNameW > 0x105 )
  {
    utl::make_unique_for_overwrite<unsigned short [0],0>(&lpszLongPath, LongPathNameW);
    v25 = lpszLongPath;
    if ( lpszLongPath )
    {
      if ( v21 > GetLongPathNameW(lpszShortPath, lpszLongPath, v21) )
        FinalPathByHandle = (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                               &lpszShortPath,
                                               v25) == 0
                          ? 0x8007000E
                          : 0;
      else
        FinalPathByHandle = -2147418113;
    }
    else
    {
      FinalPathByHandle = -2147024882;
    }
    utl::unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>(&lpszLongPath);
    goto LABEL_43;
  }
  do
    ++v13;
  while ( szLongPath[v13] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpszShortPath,
                           szLongPath) )
  {
    FinalPathByHandle = -2147024882;
    goto LABEL_62;
  }
  FinalPathByHandle = 0;
LABEL_48:
  if ( !lpszShortPath
    || *lpszShortPath != 92
    || lpszShortPath[1] != 92
    || lpszShortPath[2] != 63
    || (v26 = 0, lpszShortPath[3] != 92) )
  {
    v26 = 1;
  }
  v27 = (unsigned int)(4 * v26);
  v28 = v39 - lpszShortPath;
  if ( v28 != v42 - v41 - v27 || CompareStringOrdinal(lpszShortPath, v28, &v41[v27], v28, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode() == 3
      && (unsigned int)dword_180022000 > 2
      && (unsigned __int8)tlgKeywordOn(v29, 0x200000000008LL) )
    {
      LODWORD(lpszLongPath) = v27;
      _tlgWrapBinary<unsigned short,2>(v46, v41, (unsigned __int16)(v42 - v41));
      v30 = _tlgWrapBinary<unsigned short,2>(v47, lpszShortPath, (unsigned __int16)(v39 - lpszShortPath));
      v44[0] = a1;
      v45[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(
        (unsigned int)&lpszLongPath,
        (unsigned int)&unk_18001C280,
        v31,
        v32,
        (__int64)v45,
        (__int64)v44,
        v30,
        v32,
        (__int64)&lpszLongPath);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
    FinalPathByHandle = -2147024735;
  }
LABEL_62:
  if ( (unsigned int)dword_180022000 > 4 && (unsigned __int8)tlgKeywordOn(v7, 8) )
  {
    LODWORD(lpszLongPath) = FinalPathByHandle;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v33,
      (unsigned int)byte_18001C253,
      v34,
      v35,
      (__int64)&lpszLongPath);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&lpszShortPath);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v41);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x180012d68  mov     [rsp-8+arg_10], rbx
0x180012d6d  mov     [rsp-8+arg_18], rsi
0x180012d72  push    rbp
0x180012d73  push    rdi
0x180012d74  push    r12
0x180012d76  push    r14
0x180012d78  push    r15
0x180012d7a  lea     rbp, [rsp-200h]
0x180012d82  sub     rsp, 300h
0x180012d89  mov     rax, cs:__security_cookie
0x180012d90  xor     rax, rsp
0x180012d93  mov     [rbp+220h+var_30], rax
0x180012d9a  mov     rbx, rdx
0x180012d9d  mov     rsi, rcx
0x180012da0  lea     rax, [rbp+220h+var_298]
0x180012da4  mov     [rsp+320h+var_2A8], rax
0x180012da9  lea     rax, [rbp+220h+var_298]
0x180012dad  mov     [rbp+220h+var_2A0], rax
0x180012db1  xor     r14d, r14d
0x180012db4  mov     [rbp+220h+var_298], r14w
0x180012db9  lea     rax, [rsp+320h+var_2B8]
0x180012dbe  mov     [rsp+320h+lpszShortPath], rax
0x180012dc3  lea     rax, [rsp+320h+var_2B8]
0x180012dc8  mov     [rsp+320h+var_2C0], rax
0x180012dcd  mov     [rsp+320h+var_2B8], r14w
0x180012dd3  mov     eax, cs:dword_180022000
0x180012dd9  lea     r15d, [r14+8]
0x180012ddd  cmp     eax, 4
0x180012de0  jbe     short loc_180012E09
0x180012de2  mov     edx, r15d
0x180012de5  call    _tlgKeywordOn
0x180012dea  test    al, al
0x180012dec  jz      short loc_180012E09
0x180012dee  mov     [rsp+320h+lpszLongPath], rsi
0x180012df3  lea     rax, [rsp+320h+lpszLongPath]
0x180012df8  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180012dfd  lea     rdx, word_18001C422
0x180012e04  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180012e09  lea     rdx, [rsp+320h+var_2A8]
0x180012e0e  mov     rcx, rbx; hFile
0x180012e11  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180012e16  mov     ebx, eax
0x180012e18  cmp     eax, 80070005h
0x180012e1d  jnz     short loc_180012E5C
0x180012e1f  call    cs:__imp_GetCurrentProcess
0x180012e25  mov     rcx, rax; ProcessHandle
0x180012e28  call    ?UtilIsLowRightsProcess@@YAJPEAX@Z; UtilIsLowRightsProcess(void *)
0x180012e2d  test    eax, eax
0x180012e2f  jnz     short loc_180012E60
0x180012e31  mov     eax, cs:dword_180022000
0x180012e37  cmp     eax, 4
0x180012e3a  jbe     short loc_180012E54
0x180012e3c  mov     rdx, r15
0x180012e3f  call    _tlgKeywordOn
0x180012e44  test    al, al
0x180012e46  jz      short loc_180012E54
0x180012e48  lea     rdx, byte_18001C3F1
0x180012e4f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180012e54  mov     ebx, r14d
0x180012e57  jmp     loc_1800131EF
0x180012e5c  test    ebx, ebx
0x180012e5e  jns     short loc_180012E9E
0x180012e60  mov     eax, cs:dword_180022000
0x180012e66  cmp     eax, 2
0x180012e69  jbe     loc_1800131EF
0x180012e6f  mov     rdx, r15
0x180012e72  call    _tlgKeywordOn
0x180012e77  test    al, al
0x180012e79  jz      loc_1800131EF
0x180012e7f  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x180012e83  lea     rdx, byte_18001C3C3
0x180012e8a  lea     rax, [rsp+320h+lpszLongPath]
0x180012e8f  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180012e94  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180012e99  jmp     loc_1800131EF
0x180012e9e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012ea2  mov     r8, rbx
0x180012ea5  inc     r8
0x180012ea8  cmp     [rsi+r8*2], r14w
0x180012ead  jnz     short loc_180012EA5
0x180012eaf  cmp     r8, 1
0x180012eb3  jnb     short loc_180012EBF
0x180012eb5  mov     ebx, 80070057h
0x180012eba  jmp     loc_1800131EF
0x180012ebf  mov     r12d, 5Ch ; '\'
0x180012ec5  mov     rax, [rbp+220h+var_2A0]
0x180012ec9  cmp     [rsp+320h+var_2A8], rax
0x180012ece  jz      short loc_180012EDA
0x180012ed0  cmp     r12w, [rax-2]
0x180012ed5  mov     dil, 1
0x180012ed8  jz      short loc_180012EDD
0x180012eda  mov     dil, r14b
0x180012edd  cmp     [rsi+r8*2-2], r12w
0x180012ee3  jnz     short loc_180012EED
0x180012ee5  test    dil, dil
0x180012ee8  jnz     short loc_180012EED
0x180012eea  dec     r8
0x180012eed  mov     rdx, rsi
0x180012ef0  lea     rcx, [rsp+320h+lpszShortPath]
0x180012ef5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180012efa  test    al, al
0x180012efc  jnz     short loc_180012F36
0x180012efe  mov     ebx, 8007000Eh
0x180012f03  mov     eax, cs:dword_180022000
0x180012f09  cmp     eax, 2
0x180012f0c  jbe     loc_1800131EF
0x180012f12  mov     rdx, r15
0x180012f15  call    _tlgKeywordOn
0x180012f1a  test    al, al
0x180012f1c  jz      loc_1800131EF
0x180012f22  mov     dword ptr [rsp+320h+lpszLongPath], 8007000Eh
0x180012f2a  lea     rdx, word_18001C38E
0x180012f31  jmp     loc_180012E8A
0x180012f36  test    dil, dil
0x180012f39  jz      short loc_180012FB3
0x180012f3b  mov     eax, cs:dword_180022000
0x180012f41  cmp     eax, 4
0x180012f44  jbe     short loc_180012FB3
0x180012f46  mov     rdx, r15
0x180012f49  call    _tlgKeywordOn
0x180012f4e  test    al, al
0x180012f50  jz      short loc_180012FB3
0x180012f52  mov     rax, [rsp+320h+var_2C0]
0x180012f57  mov     rdx, [rsp+320h+lpszShortPath]
0x180012f5c  sub     rax, rdx
0x180012f5f  sar     rax, 1
0x180012f62  movzx   r8d, ax
0x180012f66  lea     rcx, [rbp+220h+var_278]
0x180012f6a  call    ??$_tlgWrapBinary@G$01@@YA?AU?$_tlgWrapperArray@$00@@PEBG_K@Z; _tlgWrapBinary<ushort,2>(ushort const *,unsigned __int64)
0x180012f6f  mov     r9, rax
0x180012f72  mov     rcx, [rbp+220h+var_2A0]
0x180012f76  mov     rdx, [rsp+320h+var_2A8]
0x180012f7b  sub     rcx, rdx
0x180012f7e  sar     rcx, 1
0x180012f81  movzx   r8d, cx
0x180012f85  lea     rcx, [rbp+220h+var_288]
0x180012f89  call    ??$_tlgWrapBinary@G$01@@YA?AU?$_tlgWrapperArray@$00@@PEBG_K@Z; _tlgWrapBinary<ushort,2>(ushort const *,unsigned __int64)
0x180012f8e  mov     [rsp+320h+lpszLongPath], rsi
0x180012f93  mov     [rsp+320h+var_2F0], r9
0x180012f98  mov     [rsp+320h+var_2F8], rax
0x180012f9d  lea     rax, [rsp+320h+lpszLongPath]
0x180012fa2  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180012fa7  lea     rdx, byte_18001C32D
0x180012fae  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperArray@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperArray@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x180012fb3  mov     r8d, 105h; cchBuffer
0x180012fb9  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x180012fbd  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x180012fc2  call    cs:__imp_GetLongPathNameW
0x180012fc8  mov     edi, eax
0x180012fca  test    eax, eax
0x180012fcc  jnz     short loc_18001301E
0x180012fce  call    cs:__imp_GetLastError
0x180012fd4  mov     ebx, eax
0x180012fd6  test    eax, eax
0x180012fd8  jle     short loc_180012FE3
0x180012fda  movzx   ebx, ax
0x180012fdd  or      ebx, 80070000h
0x180012fe3  mov     eax, cs:dword_180022000
0x180012fe9  cmp     eax, 2
0x180012fec  jbe     loc_180013084
0x180012ff2  mov     rdx, r15
0x180012ff5  call    _tlgKeywordOn
0x180012ffa  test    al, al
0x180012ffc  jz      loc_180013084
0x180013002  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x180013006  lea     rax, [rsp+320h+lpszLongPath]
0x18001300b  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180013010  lea     rdx, dword_18001C2F4
0x180013017  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001301c  jmp     short loc_180013084
0x18001301e  cmp     edi, 105h
0x180013024  jbe     short loc_18001308E
0x180013026  mov     rdx, rdi
0x180013029  lea     rcx, [rsp+320h+lpszLongPath]
0x18001302e  call    ??$make_unique_for_overwrite@$$BY0A@G$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@0@_K@Z; utl::make_unique_for_overwrite<ushort [0],0>(unsigned __int64)
0x180013033  mov     rbx, [rsp+320h+lpszLongPath]
0x180013038  test    rbx, rbx
0x18001303b  jnz     short loc_180013044
0x18001303d  mov     ebx, 8007000Eh
0x180013042  jmp     short loc_18001307A
0x180013044  mov     r8d, edi; cchBuffer
0x180013047  mov     rdx, rbx; lpszLongPath
0x18001304a  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x18001304f  call    cs:__imp_GetLongPathNameW
0x180013055  cmp     edi, eax
0x180013057  ja      short loc_180013060
0x180013059  mov     ebx, 8000FFFFh
0x18001305e  jmp     short loc_18001307A
0x180013060  mov     rdx, rbx
0x180013063  lea     rcx, [rsp+320h+lpszShortPath]
0x180013068  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18001306d  neg     al
0x18001306f  sbb     ecx, ecx
0x180013071  not     ecx
0x180013073  mov     ebx, 8007000Eh
0x180013078  and     ebx, ecx
0x18001307a  lea     rcx, [rsp+320h+lpszLongPath]
0x18001307f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>>::~unique_ptr<ushort [0],utl::default_delete<ushort [0]>>(void)
0x180013084  test    ebx, ebx
0x180013086  js      loc_1800131EF
0x18001308c  jmp     short loc_1800130B8
0x18001308e  lea     rax, [rbp+220h+szLongPath]
0x180013092  inc     rbx
0x180013095  cmp     [rax+rbx*2], r14w
0x18001309a  jnz     short loc_180013092
0x18001309c  mov     r8, rbx
0x18001309f  lea     rdx, [rbp+220h+szLongPath]
0x1800130a3  lea     rcx, [rsp+320h+lpszShortPath]
0x1800130a8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800130ad  test    al, al
0x1800130af  jz      loc_1800131EA
0x1800130b5  mov     ebx, r14d
0x1800130b8  mov     rcx, [rsp+320h+lpszShortPath]; lpString1
0x1800130bd  test    rcx, rcx
0x1800130c0  jz      short loc_1800130E0
0x1800130c2  cmp     [rcx], r12w
0x1800130c6  jnz     short loc_1800130E0
0x1800130c8  cmp     [rcx+2], r12w
0x1800130cd  jnz     short loc_1800130E0
0x1800130cf  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1800130d4  jnz     short loc_1800130E0
0x1800130d6  cmp     [rcx+6], r12w
0x1800130db  mov     eax, r14d
0x1800130de  jz      short loc_1800130E5
0x1800130e0  mov     eax, 1
0x1800130e5  lea     edi, ds:0[rax*4]
0x1800130ec  mov     r8d, edi
0x1800130ef  mov     rdx, [rsp+320h+var_2C0]
0x1800130f4  sub     rdx, rcx
0x1800130f7  sar     rdx, 1; cchCount1
0x1800130fa  mov     rax, [rbp+220h+var_2A0]
0x1800130fe  mov     r9, [rsp+320h+var_2A8]
0x180013103  sub     rax, r9
0x180013106  sar     rax, 1
0x180013109  sub     rax, r8
0x18001310c  cmp     rdx, rax
0x18001310f  jnz     short loc_18001312F
0x180013111  lea     r8, [r9+rdi*2]; lpString2
0x180013115  mov     [rsp+320h+bIgnoreCase], 1; bIgnoreCase
0x18001311d  mov     r9d, edx; cchCount2
0x180013120  call    cs:__imp_CompareStringOrdinal
0x180013126  cmp     eax, 2
0x180013129  jz      loc_1800131EF
0x18001312f  call    cs:__imp_TelGetWerTelemetryMode
0x180013135  cmp     eax, 3
0x180013138  jnz     loc_1800131DE
0x18001313e  mov     eax, cs:dword_180022000
0x180013144  cmp     eax, 2
0x180013147  jbe     loc_1800131DE
0x18001314d  mov     rdx, 200000000008h
0x180013157  call    _tlgKeywordOn
0x18001315c  test    al, al
0x18001315e  jz      short loc_1800131DE
0x180013160  mov     dword ptr [rsp+320h+lpszLongPath], edi
0x180013164  mov     rax, [rbp+220h+var_2A0]
0x180013168  mov     rdx, [rsp+320h+var_2A8]
0x18001316d  sub     rax, rdx
0x180013170  sar     rax, 1
0x180013173  movzx   r8d, ax
0x180013177  lea     rcx, [rbp+220h+var_268]
0x18001317b  call    ??$_tlgWrapBinary@G$01@@YA?AU?$_tlgWrapperArray@$00@@PEBG_K@Z; _tlgWrapBinary<ushort,2>(ushort const *,unsigned __int64)
0x180013180  mov     r9, rax
0x180013183  mov     rcx, [rsp+320h+var_2C0]
0x180013188  mov     rdx, [rsp+320h+lpszShortPath]
0x18001318d  sub     rcx, rdx
0x180013190  sar     rcx, 1
0x180013193  movzx   r8d, cx
0x180013197  lea     rcx, [rbp+220h+var_258]
0x18001319b  call    ??$_tlgWrapBinary@G$01@@YA?AU?$_tlgWrapperArray@$00@@PEBG_K@Z; _tlgWrapBinary<ushort,2>(ushort const *,unsigned __int64)
0x1800131a0  mov     [rbp+220h+var_288], rsi
0x1800131a4  mov     [rbp+220h+var_278], 1000000h
0x1800131ac  lea     rcx, [rsp+320h+lpszLongPath]
0x1800131b1  mov     [rsp+320h+var_2E0], rcx
0x1800131b6  mov     [rsp+320h+var_2E8], r9
0x1800131bb  mov     [rsp+320h+var_2F0], rax
0x1800131c0  lea     rax, [rbp+220h+var_288]
0x1800131c4  mov     [rsp+320h+var_2F8], rax
0x1800131c9  lea     rax, [rbp+220h+var_278]
0x1800131cd  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x1800131d2  lea     rdx, unk_18001C280
0x1800131d9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperArray@$00@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperArray@$00@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &)
0x1800131de  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800131e3  mov     ebx, 800700A1h
0x1800131e8  jmp     short loc_1800131EF
0x1800131ea  mov     ebx, 8007000Eh
0x1800131ef  mov     eax, cs:dword_180022000
0x1800131f5  cmp     eax, 4
0x1800131f8  jbe     short loc_180013221
0x1800131fa  mov     rdx, r15
0x1800131fd  call    _tlgKeywordOn
0x180013202  test    al, al
0x180013204  jz      short loc_180013221
0x180013206  mov     dword ptr [rsp+320h+lpszLongPath], ebx
0x18001320a  lea     rax, [rsp+320h+lpszLongPath]
0x18001320f  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x180013214  lea     rdx, byte_18001C253
0x18001321b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180013220  nop
0x180013221  lea     rcx, [rsp+320h+lpszShortPath]
0x180013226  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
  ... truncated ...
```
