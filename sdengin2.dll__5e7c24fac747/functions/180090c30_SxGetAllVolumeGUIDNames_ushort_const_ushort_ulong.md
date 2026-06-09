# SxGetAllVolumeGUIDNames(ushort const *,ushort * * *,ulong *)

- ea: `0x180090c30`
- end: `0x180091305`
- name: `?SxGetAllVolumeGUIDNames@@YAJPEBGPEAPEAPEAGPEAK@Z`
- size: `1749`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, service_task`

## callers

- `0x18009130c`

## callees

- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008ecfc`
- `0x18008f5d0`
- `0x18008ffb8`
- `0x1800900d8`
- `0x18009057c`
- `0x180090c30`
- `0x180091e04`
- `0x1800936c4`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180090ffa`
- `msvcrt!_wcsicmp` at `0x180090ffa`
- `ntdll!RtlEqualUnicodeString` at `0x180091186`
- `ntdll!RtlEqualUnicodeString` at `0x180091186`
- `KERNEL32!CreateFileW` at `0x180090da9`
- `KERNEL32!CreateFileW` at `0x180090da9`
- `KERNEL32!GetLastError` at `0x180090e47`
- `KERNEL32!GetLastError` at `0x180090e47`
- `KERNEL32!CloseHandle` at `0x1800912bc`
- `KERNEL32!CloseHandle` at `0x1800912bc`
- `KERNEL32!DeviceIoControl` at `0x180090e36`
- `KERNEL32!DeviceIoControl` at `0x180090e36`
- `ole32!CoTaskMemFree` at `0x180091269`
- `ole32!CoTaskMemFree` at `0x180091291`
- `ole32!CoTaskMemFree` at `0x18009129c`
- `ole32!CoTaskMemFree` at `0x180091269`
- `ole32!CoTaskMemFree` at `0x180091291`
- `ole32!CoTaskMemFree` at `0x18009129c`
- `ole32!CoTaskMemRealloc` at `0x180090de8`
- `ole32!CoTaskMemRealloc` at `0x180090de8`

## string_xrefs

- `0x180090d85`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall SxGetAllVolumeGUIDNames(const unsigned __int16 *a1, unsigned __int16 ***a2, unsigned int *a3)
{
  unsigned int v6; // esi
  void *v7; // r14
  _DWORD *v8; // r15
  __int64 FileW; // rbx
  __int16 v10; // ax
  int v11; // eax
  bool v12; // sf
  __int16 v13; // ax
  __int64 v14; // rcx
  DWORD v15; // eax
  BOOL v16; // eax
  unsigned int v17; // r8d
  __int64 v18; // rcx
  unsigned int v19; // edi
  __int16 v20; // dx
  _WORD *v21; // rcx
  USHORT v22; // ax
  unsigned int v23; // edi
  __int16 v24; // dx
  _WORD *v25; // rcx
  void *v26; // rcx
  unsigned __int16 **v27; // rax
  __int64 v28; // rdi
  unsigned int v29; // edi
  DWORD nOutBufferSize; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  int LastFailureAsHRESULT; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v34; // [rsp+54h] [rbp-ACh]
  __int16 v35; // [rsp+56h] [rbp-AAh]
  __int128 v36; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *String1[2]; // [rsp+98h] [rbp-68h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING v39; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING v40; // [rsp+C0h] [rbp-40h] BYREF
  __int128 InBuffer; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-20h]
  wchar_t String2; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v44[526]; // [rsp+F2h] [rbp-Eh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetAllVolumeGUIDNames", 226, 1);
  v6 = 0;
  Block = 0;
  nOutBufferSize = 0;
  v42 = 0;
  String2 = 0;
  InBuffer = 0;
  v7 = 0;
  v8 = 0;
  FileW = -1;
  memset_0(v44, 0, 0x208u);
  String1[1] = 0;
  pv = 0;
  String1[0] = (wchar_t *)qword_1800E8530;
  v36 = 0;
  v40 = 0;
  v39 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v10 = 246;
  if ( !a1 || (v34 = 246, v10 = 247, !a2) || (v34 = 247, v10 = 248, !a3) )
  {
    v35 = v10;
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_91;
  }
  LastFailureAsHRESULT = 0;
  v34 = 248;
  v11 = CSxSimpleArray<unsigned short *>::CreateInstance(&Block);
  v7 = Block;
  v12 = v11 < 0;
  LastFailureAsHRESULT = v11;
  v13 = 250;
  if ( v12 )
    goto LABEL_86;
  v34 = 250;
  FileW = (__int64)CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
    v13 = 259;
LABEL_86:
    v35 = v13;
    if ( v7 && *((_DWORD *)v7 + 4) )
    {
      do
      {
        v28 = v6;
        CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v7 + 1) + 8LL * v6++));
        *(_QWORD *)(*((_QWORD *)v7 + 1) + 8 * v28) = 0;
      }
      while ( v6 < *((_DWORD *)v7 + 4) );
    }
    goto LABEL_91;
  }
  LastFailureAsHRESULT = 0;
  v34 = 259;
  v42 = 0;
  v15 = 32;
  nOutBufferSize = 32;
  InBuffer = 0;
  while ( 1 )
  {
    v8 = CoTaskMemRealloc(v8, v15);
    v13 = 269;
    if ( !v8 )
    {
      LastFailureAsHRESULT = -2147024882;
      goto LABEL_86;
    }
    v34 = 269;
    LastFailureAsHRESULT = 0;
    v16 = DeviceIoControl((HANDLE)FileW, 0x6D0008u, &InBuffer, 0x18u, v8, nOutBufferSize, &nOutBufferSize, 0);
    nOutBufferSize = *v8;
    if ( v16 )
      break;
    if ( GetLastError() != 234 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18);
      v13 = 283;
      goto LABEL_86;
    }
    v15 = nOutBufferSize;
  }
  LastFailureAsHRESULT = 0;
  v34 = 283;
  LastFailureAsHRESULT = SxGetUniqueVolumeForPath(a1, &String2, v17);
  v13 = 288;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v34 = 288;
  LastFailureAsHRESULT = SxCopyString(&String2, (unsigned __int16 **)&pv);
  v13 = 289;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v34 = 289;
  LastFailureAsHRESULT = CSxSimpleArray<unsigned short *>::Append(v7, pv);
  v13 = 290;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v34 = 290;
  v19 = 0;
  pv = 0;
  while ( 1 )
  {
    if ( v19 >= v8[1] )
      goto LABEL_82;
    v20 = v8[6 * v19 + 3];
    v21 = (_WORD *)((char *)v8 + (unsigned int)v8[6 * v19 + 2]);
    WORD1(v36) = v20;
    LOWORD(v36) = v20;
    *((_QWORD *)&v36 + 1) = v21;
    if ( (v20 == 96 || v20 == 98 && v21[48] == 92)
      && *v21 == 92
      && (v21[1] == 63 || v21[1] == 92)
      && v21[2] == 63
      && v21[3] == 92
      && v21[4] == 86
      && v21[5] == 111
      && v21[6] == 108
      && v21[7] == 117
      && v21[8] == 109
      && v21[9] == 101
      && v21[10] == 123
      && v21[19] == 45
      && v21[24] == 45
      && v21[29] == 45
      && v21[34] == 45
      && v21[47] == 125
      && v20 == 96
      && v21[1] == 63 )
    {
      LastFailureAsHRESULT = ConvertNtNameToWin32Name(&v36, String1);
      v13 = 310;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_83;
      v34 = 310;
      if ( !_wcsicmp(String1[0], &String2) )
        break;
    }
    ++v19;
  }
  v22 = v8[6 * v19 + 7];
  v8[6 * v19 + 2] = 0;
  v40.MaximumLength = v22;
  v40.Length = v22;
  v40.Buffer = (PWSTR)((char *)v8 + (unsigned int)v8[6 * v19 + 6]);
  if ( v19 >= v8[1] )
  {
LABEL_82:
    LastFailureAsHRESULT = -2147024809;
    v13 = 325;
LABEL_83:
    v6 = 0;
    goto LABEL_86;
  }
  v6 = 0;
  LastFailureAsHRESULT = 0;
  v23 = 0;
  v34 = 325;
  while ( v23 < v8[1] )
  {
    v24 = v8[6 * v23 + 3];
    if ( v24 )
    {
      v25 = (_WORD *)((char *)v8 + (unsigned int)v8[6 * v23 + 2]);
      WORD1(v36) = v8[6 * v23 + 3];
      LOWORD(v36) = v24;
      *((_QWORD *)&v36 + 1) = v25;
      if ( (v24 == 96 || v24 == 98 && v25[48] == 92)
        && *v25 == 92
        && (v25[1] == 63 || v25[1] == 92)
        && v25[2] == 63
        && v25[3] == 92
        && v25[4] == 86
        && v25[5] == 111
        && v25[6] == 108
        && v25[7] == 117
        && v25[8] == 109
        && v25[9] == 101
        && v25[10] == 123
        && v25[19] == 45
        && v25[24] == 45
        && v25[29] == 45
        && v25[34] == 45
        && v25[47] == 125
        && v24 == 96
        && v25[1] == 63 )
      {
        v39.MaximumLength = v8[6 * v23 + 7];
        v39.Length = v39.MaximumLength;
        v39.Buffer = (PWSTR)((char *)v8 + (unsigned int)v8[6 * v23 + 6]);
        if ( RtlEqualUnicodeString(&v40, &v39, 1u) )
        {
          LastFailureAsHRESULT = ConvertNtNameToWin32Name(&v36, String1);
          v13 = 362;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v34 = 362;
          LastFailureAsHRESULT = SxCopyString(String1[0], (unsigned __int16 **)&pv);
          v13 = 363;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v34 = 363;
          LastFailureAsHRESULT = CSxSimpleArray<unsigned short *>::Append(v7, pv);
          v13 = 364;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v34 = 364;
          pv = 0;
        }
      }
    }
    ++v23;
  }
  v26 = v7;
  *a3 = *((_DWORD *)v7 + 4);
  v27 = (unsigned __int16 **)*((_QWORD *)v7 + 1);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  v7 = 0;
  *a2 = v27;
  CSxSimpleArray<unsigned short *>::Release(v26);
LABEL_91:
  CoTaskMemFree(v8);
  CoTaskMemFree(pv);
  v29 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)String1);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( v7 )
    CSxSimpleArray<unsigned short *>::Release(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v29;
}

```

## disassembly

```asm
0x180090c30  mov     [rsp-8+arg_18], rbx
0x180090c35  push    rbp
0x180090c36  push    rsi
0x180090c37  push    rdi
0x180090c38  push    r12
0x180090c3a  push    r13
0x180090c3c  push    r14
0x180090c3e  push    r15
0x180090c40  lea     rbp, [rsp-210h]
0x180090c48  sub     rsp, 310h
0x180090c4f  mov     rax, cs:__security_cookie
0x180090c56  xor     rax, rsp
0x180090c59  mov     [rbp+240h+var_40], rax
0x180090c60  mov     r12, r8
0x180090c63  mov     r13, rdx
0x180090c66  mov     rdi, rcx
0x180090c69  mov     rcx, cs:WPP_GLOBAL_Control
0x180090c70  lea     rax, WPP_GLOBAL_Control
0x180090c77  cmp     rcx, rax
0x180090c7a  jz      short loc_180090C9A
0x180090c7c  test    dword ptr [rcx+1Ch], 20000000h
0x180090c83  jz      short loc_180090C9A
0x180090c85  mov     rcx, [rcx+10h]
0x180090c89  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180090c90  mov     edx, 0Fh
0x180090c95  call    WPP_SF_
0x180090c9a  mov     r9d, 1; unsigned __int16
0x180090ca0  lea     rdx, aSxgetallvolume; "SxGetAllVolumeGUIDNames"
0x180090ca7  mov     r8d, 0E2h; unsigned __int16
0x180090cad  lea     rcx, [rsp+340h+var_2F0]; this
0x180090cb2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180090cb7  xor     esi, esi
0x180090cb9  lea     rcx, [rbp+240h+var_24E]; void *
0x180090cbd  xorps   xmm0, xmm0
0x180090cc0  mov     [rbp+240h+Block], rsi
0x180090cc4  xor     eax, eax
0x180090cc6  mov     [rsp+340h+nOutBufferSize], esi
0x180090cca  xor     edx, edx; Val
0x180090ccc  mov     [rbp+240h+var_260], rax
0x180090cd0  mov     r8d, 208h; Size
0x180090cd6  mov     [rbp+240h+String2], si
0x180090cda  movups  [rbp+240h+InBuffer], xmm0
0x180090cde  mov     r14d, esi
0x180090ce1  mov     r15d, esi
0x180090ce4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180090ce8  call    memset_0
0x180090ced  mov     [rbp+240h+var_2A0], rsi
0x180090cf1  xorps   xmm0, xmm0
0x180090cf4  mov     [rsp+340h+pv], rsi
0x180090cf9  lea     rax, qword_1800E8530
0x180090d00  mov     [rbp+240h+String1], rax
0x180090d04  xorps   xmm1, xmm1
0x180090d07  movups  [rbp+240h+var_2B8], xmm0
0x180090d0b  movups  xmmword ptr [rbp+240h+var_280.Length], xmm1
0x180090d0f  movups  xmmword ptr [rbp+240h+var_290.Length], xmm0
0x180090d13  test    r13, r13
0x180090d16  jz      short loc_180090D1C
0x180090d18  mov     [r13+0], rsi
0x180090d1c  test    r12, r12
0x180090d1f  jz      short loc_180090D25
0x180090d21  mov     [r12], esi
0x180090d25  mov     eax, 0F6h
0x180090d2a  test    rdi, rdi
0x180090d2d  jz      loc_180091281
0x180090d33  mov     [rsp+340h+var_2EC], ax
0x180090d38  mov     eax, 0F7h
0x180090d3d  test    r13, r13
0x180090d40  jz      loc_180091281
0x180090d46  mov     [rsp+340h+var_2EC], ax
0x180090d4b  mov     eax, 0F8h
0x180090d50  test    r12, r12
0x180090d53  jz      loc_180091281
0x180090d59  lea     rcx, [rbp+240h+Block]
0x180090d5d  mov     [rsp+340h+var_2F0], esi
0x180090d61  mov     [rsp+340h+var_2EC], ax
0x180090d66  call    ?CreateInstance@?$CSxSimpleArray@PEAG@@SAJPEAPEAV1@@Z; CSxSimpleArray<ushort *>::CreateInstance(CSxSimpleArray<ushort *> * *)
0x180090d6b  mov     r14, [rbp+240h+Block]
0x180090d6f  test    eax, eax
0x180090d71  mov     [rsp+340h+var_2F0], eax
0x180090d75  mov     eax, 0FAh
0x180090d7a  js      loc_18009124C
0x180090d80  mov     [rsp+340h+hTemplateFile], rbx; hTemplateFile
0x180090d85  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x180090d8c  mov     r8d, 3; dwShareMode
0x180090d92  mov     [rsp+340h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180090d9a  xor     r9d, r9d; lpSecurityAttributes
0x180090d9d  mov     [rsp+340h+dwCreationDisposition], r8d; dwCreationDisposition
0x180090da2  xor     edx, edx; dwDesiredAccess
0x180090da4  mov     [rsp+340h+var_2EC], ax
0x180090da9  call    cs:__imp_CreateFileW
0x180090daf  mov     rbx, rax
0x180090db2  dec     rax
0x180090db5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180090db9  ja      loc_18009123E
0x180090dbf  mov     eax, 103h
0x180090dc4  mov     [rsp+340h+var_2F0], esi
0x180090dc8  mov     [rsp+340h+var_2EC], ax
0x180090dcd  xorps   xmm0, xmm0
0x180090dd0  xor     eax, eax
0x180090dd2  mov     [rbp+240h+var_260], rax
0x180090dd6  mov     eax, 20h ; ' '
0x180090ddb  mov     [rsp+340h+nOutBufferSize], eax
0x180090ddf  movups  [rbp+240h+InBuffer], xmm0
0x180090de3  mov     edx, eax; cb
0x180090de5  mov     rcx, r15; pv
0x180090de8  call    cs:__imp_CoTaskMemRealloc
0x180090dee  mov     r15, rax
0x180090df1  test    rax, rax
0x180090df4  mov     eax, 10Dh
0x180090df9  jz      loc_180091234
0x180090dff  mov     [rsp+340h+lpOverlapped], rsi; lpOverlapped
0x180090e04  lea     rcx, [rsp+340h+nOutBufferSize]
0x180090e09  mov     [rsp+340h+hTemplateFile], rcx; lpBytesReturned
0x180090e0e  lea     r8, [rbp+240h+InBuffer]; lpInBuffer
0x180090e12  mov     [rsp+340h+var_2EC], ax
0x180090e17  mov     rcx, rbx; hDevice
0x180090e1a  mov     eax, [rsp+340h+nOutBufferSize]
0x180090e1e  mov     r9d, 18h; nInBufferSize
0x180090e24  mov     [rsp+340h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180090e28  mov     edx, 6D0008h; dwIoControlCode
0x180090e2d  mov     qword ptr [rsp+340h+dwCreationDisposition], r15; lpOutBuffer
0x180090e32  mov     [rsp+340h+var_2F0], esi
0x180090e36  call    cs:__imp_DeviceIoControl
0x180090e3c  mov     ecx, [r15]
0x180090e3f  mov     [rsp+340h+nOutBufferSize], ecx
0x180090e43  test    eax, eax
0x180090e45  jnz     short loc_180090E6D
0x180090e47  call    cs:__imp_GetLastError
0x180090e4d  cmp     eax, 0EAh
0x180090e52  jnz     short loc_180090E5A
0x180090e54  mov     eax, [rsp+340h+nOutBufferSize]
0x180090e58  jmp     short loc_180090DE3
0x180090e5a  call    GetLastFailureAsHRESULT
0x180090e5f  mov     [rsp+340h+var_2F0], eax
0x180090e63  mov     eax, 11Bh
0x180090e68  jmp     loc_18009124C
0x180090e6d  mov     eax, 11Bh
0x180090e72  mov     [rsp+340h+var_2F0], esi
0x180090e76  lea     rdx, [rbp+240h+String2]; lpszVolumeName
0x180090e7a  mov     [rsp+340h+var_2EC], ax
0x180090e7f  mov     rcx, rdi; unsigned __int16 *
0x180090e82  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x180090e87  mov     [rsp+340h+var_2F0], eax
0x180090e8b  test    eax, eax
0x180090e8d  mov     eax, 120h
0x180090e92  js      loc_18009124C
0x180090e98  lea     rdx, [rsp+340h+pv]; unsigned __int16 **
0x180090e9d  mov     [rsp+340h+var_2EC], ax
0x180090ea2  lea     rcx, [rbp+240h+String2]; Src
0x180090ea6  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180090eab  mov     [rsp+340h+var_2F0], eax
0x180090eaf  test    eax, eax
0x180090eb1  mov     eax, 121h
0x180090eb6  js      loc_18009124C
0x180090ebc  mov     rdx, [rsp+340h+pv]
0x180090ec1  mov     rcx, r14
0x180090ec4  mov     [rsp+340h+var_2EC], ax
0x180090ec9  call    ?Append@?$CSxSimpleArray@PEAG@@QEAAJPEAG@Z; CSxSimpleArray<ushort *>::Append(ushort *)
0x180090ece  mov     [rsp+340h+var_2F0], eax
0x180090ed2  test    eax, eax
0x180090ed4  mov     eax, 122h
0x180090ed9  js      loc_18009124C
0x180090edf  mov     [rsp+340h+var_2EC], ax
0x180090ee4  mov     edi, esi
0x180090ee6  mov     [rsp+340h+pv], rsi
0x180090eeb  cmp     edi, [r15+4]
0x180090eef  jnb     loc_180091223
0x180090ef5  mov     eax, edi
0x180090ef7  lea     rsi, [rax+rax*2]
0x180090efb  movzx   edx, word ptr [r15+rsi*8+0Ch]
0x180090f01  mov     ecx, [r15+rsi*8+8]
0x180090f06  add     rcx, r15
0x180090f09  mov     word ptr [rbp+240h+var_2B8+2], dx
0x180090f0d  mov     word ptr [rbp+240h+var_2B8], dx
0x180090f11  mov     qword ptr [rbp+240h+var_2B8+8], rcx
0x180090f15  cmp     dx, 60h ; '`'
0x180090f19  jz      short loc_180090F30
0x180090f1b  cmp     dx, 62h ; 'b'
0x180090f1f  jnz     loc_180091006
0x180090f25  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x180090f2a  jnz     loc_180091006
0x180090f30  cmp     word ptr [rcx], 5Ch ; '\'
0x180090f34  jnz     loc_180091006
0x180090f3a  cmp     word ptr [rcx+2], 3Fh ; '?'
0x180090f3f  jz      short loc_180090F4C
0x180090f41  cmp     word ptr [rcx+2], 5Ch ; '\'
0x180090f46  jnz     loc_180091006
0x180090f4c  cmp     word ptr [rcx+4], 3Fh ; '?'
0x180090f51  jnz     loc_180091006
0x180090f57  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180090f5c  jnz     loc_180091006
0x180090f62  cmp     word ptr [rcx+8], 56h ; 'V'
0x180090f67  jnz     loc_180091006
0x180090f6d  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x180090f72  jnz     loc_180091006
0x180090f78  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x180090f7d  jnz     loc_180091006
0x180090f83  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x180090f88  jnz     short loc_180091006
0x180090f8a  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x180090f8f  jnz     short loc_180091006
0x180090f91  cmp     word ptr [rcx+12h], 65h ; 'e'
0x180090f96  jnz     short loc_180091006
0x180090f98  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x180090f9d  jnz     short loc_180091006
0x180090f9f  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x180090fa4  jnz     short loc_180091006
0x180090fa6  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x180090fab  jnz     short loc_180091006
0x180090fad  cmp     word ptr [rcx+3Ah], 2Dh ; '-'
0x180090fb2  jnz     short loc_180091006
0x180090fb4  cmp     word ptr [rcx+44h], 2Dh ; '-'
0x180090fb9  jnz     short loc_180091006
0x180090fbb  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x180090fc0  jnz     short loc_180091006
0x180090fc2  cmp     dx, 60h ; '`'
0x180090fc6  jnz     short loc_180091006
0x180090fc8  cmp     word ptr [rcx+2], 3Fh ; '?'
0x180090fcd  jnz     short loc_180091006
0x180090fcf  lea     rdx, [rbp+240h+String1]
0x180090fd3  lea     rcx, [rbp+240h+var_2B8]
0x180090fd7  call    _ConvertNtNameToWin32Name
0x180090fdc  mov     [rsp+340h+var_2F0], eax
0x180090fe0  test    eax, eax
0x180090fe2  mov     eax, 136h
0x180090fe7  js      loc_180091230
0x180090fed  mov     rcx, [rbp+240h+String1]; String1
0x180090ff1  lea     rdx, [rbp+240h+String2]; String2
0x180090ff5  mov     [rsp+340h+var_2EC], ax
0x180090ffa  call    cs:__imp__wcsicmp
0x180091000  xor     ecx, ecx
0x180091002  test    eax, eax
0x180091004  jz      short loc_18009100D
0x180091006  inc     edi
0x180091008  jmp     loc_180090EEB
0x18009100d  movzx   eax, word ptr [r15+rsi*8+1Ch]
0x180091013  mov     [r15+rsi*8+8], ecx
0x180091018  mov     [rbp+240h+var_280.MaximumLength], ax
0x18009101c  mov     [rbp+240h+var_280.Length], ax
0x180091020  mov     eax, [r15+rsi*8+18h]
0x180091025  add     rax, r15
0x180091028  mov     [rbp+240h+var_280.Buffer], rax
0x18009102c  cmp     edi, [r15+4]
0x180091030  jnb     loc_180091223
0x180091036  xor     esi, esi
0x180091038  mov     eax, 145h
0x18009103d  mov     [rsp+340h+var_2F0], esi
0x180091041  mov     edi, esi
0x180091043  mov     [rsp+340h+var_2EC], ax
0x180091048  cmp     edi, [r15+4]
0x18009104c  jnb     loc_1800911FE
0x180091052  mov     eax, edi
0x180091054  lea     r8, [rax+rax*2]
0x180091058  movzx   edx, word ptr [r15+r8*8+0Ch]
0x18009105e  test    dx, dx
0x180091061  jz      loc_1800911F7
0x180091067  mov     ecx, [r15+r8*8+8]
0x18009106c  add     rcx, r15
0x18009106f  mov     word ptr [rbp+240h+var_2B8+2], dx
0x180091073  mov     word ptr [rbp+240h+var_2B8], dx
0x180091077  mov     qword ptr [rbp+240h+var_2B8+8], rcx
0x18009107b  cmp     dx, 60h ; '`'
0x18009107f  jz      short loc_180091096
0x180091081  cmp     dx, 62h ; 'b'
0x180091085  jnz     loc_1800911F7
0x18009108b  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x180091090  jnz     loc_1800911F7
0x180091096  cmp     word ptr [rcx], 5Ch ; '\'
0x18009109a  jnz     loc_1800911F7
0x1800910a0  cmp     word ptr [rcx+2], 3Fh ; '?'
0x1800910a5  jz      short loc_1800910B2
0x1800910a7  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1800910ac  jnz     loc_1800911F7
0x1800910b2  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1800910b7  jnz     loc_1800911F7
0x1800910bd  cmp     word ptr [rcx+6], 5Ch ; '\'
0x1800910c2  jnz     loc_1800911F7
0x1800910c8  cmp     word ptr [rcx+8], 56h ; 'V'
0x1800910cd  jnz     loc_1800911F7
0x1800910d3  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x1800910d8  jnz     loc_1800911F7
0x1800910de  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1800910e3  jnz     loc_1800911F7
0x1800910e9  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1800910ee  jnz     loc_1800911F7
0x1800910f4  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1800910f9  jnz     loc_1800911F7
0x1800910ff  cmp     word ptr [rcx+12h], 65h ; 'e'
0x180091104  jnz     loc_1800911F7
0x18009110a  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x18009110f  jnz     loc_1800911F7
0x180091115  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x18009111a  jnz     loc_1800911F7
0x180091120  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x180091125  jnz     loc_1800911F7
0x18009112b  cmp     word ptr [rcx+3Ah], 2Dh ; '-'
0x180091130  jnz     loc_1800911F7
0x180091136  cmp     word ptr [rcx+44h], 2Dh ; '-'
0x18009113b  jnz     loc_1800911F7
0x180091141  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
  ... truncated ...
```
