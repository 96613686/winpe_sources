# SxGetAllVolumeGUIDNames(ushort const *,ushort * * *,ulong *)

- ea: `0x180094d48`
- end: `0x180095461`
- name: `?SxGetAllVolumeGUIDNames@@YAJPEBGPEAPEAPEAGPEAK@Z`
- size: `1817`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, service_task`

## callers

- `0x180095468`

## callees

- `0x180008370`
- `0x180072e08`
- `0x180072f14`
- `0x180092cb0`
- `0x1800935fc`
- `0x180094074`
- `0x1800941a8`
- `0x180094670`
- `0x180094d48`
- `0x180095fd4`
- `0x180097958`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180095131`
- `msvcrt!_wcsicmp` at `0x180095131`
- `ntdll!RtlEqualUnicodeString` at `0x1800952c3`
- `ntdll!RtlEqualUnicodeString` at `0x1800952c3`
- `KERNEL32!CreateFileW` at `0x180094ec1`
- `KERNEL32!CreateFileW` at `0x180094ec1`
- `KERNEL32!GetLastError` at `0x180094f71`
- `KERNEL32!GetLastError` at `0x180094f71`
- `KERNEL32!CloseHandle` at `0x180095411`
- `KERNEL32!CloseHandle` at `0x180095411`
- `KERNEL32!DeviceIoControl` at `0x180094f5a`
- `KERNEL32!DeviceIoControl` at `0x180094f5a`
- `ole32!CoTaskMemFree` at `0x1800953ac`
- `ole32!CoTaskMemFree` at `0x1800953da`
- `ole32!CoTaskMemFree` at `0x1800953eb`
- `ole32!CoTaskMemFree` at `0x1800953ac`
- `ole32!CoTaskMemFree` at `0x1800953da`
- `ole32!CoTaskMemFree` at `0x1800953eb`
- `ole32!CoTaskMemRealloc` at `0x180094f06`
- `ole32!CoTaskMemRealloc` at `0x180094f06`

## string_xrefs

- `0x180094e9d`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall SxGetAllVolumeGUIDNames(
        const unsigned __int16 *a1,
        unsigned __int16 ***a2,
        unsigned int *a3,
        __int64 a4)
{
  unsigned int v7; // esi
  void *v8; // r14
  _DWORD *v9; // r15
  __int64 FileW; // rbx
  __int16 v11; // ax
  int v12; // eax
  bool v13; // sf
  __int16 v14; // ax
  __int64 v15; // rcx
  DWORD v16; // eax
  BOOL v17; // eax
  unsigned int v18; // r8d
  __int64 v19; // rcx
  unsigned int v20; // edi
  __int16 v21; // dx
  _WORD *v22; // rcx
  USHORT v23; // ax
  unsigned int v24; // edi
  __int16 v25; // dx
  _WORD *v26; // rcx
  void *v27; // rcx
  unsigned __int16 **v28; // rax
  __int64 v29; // rdi
  unsigned int v30; // edi
  DWORD nOutBufferSize; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  int LastFailureAsHRESULT; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v35; // [rsp+54h] [rbp-ACh]
  __int16 v36; // [rsp+56h] [rbp-AAh]
  __int128 v37; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *String1[2]; // [rsp+98h] [rbp-68h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING v40; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING v41; // [rsp+C0h] [rbp-40h] BYREF
  __int128 InBuffer; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v43; // [rsp+E0h] [rbp-20h]
  wchar_t String2; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v45[526]; // [rsp+F2h] [rbp-Eh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a4);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetAllVolumeGUIDNames", 0xE2u, 1u);
  v7 = 0;
  Block = 0;
  nOutBufferSize = 0;
  v43 = 0;
  String2 = 0;
  InBuffer = 0;
  v8 = 0;
  v9 = 0;
  FileW = -1;
  memset_0(v45, 0, 0x208u);
  String1[1] = 0;
  pv = 0;
  String1[0] = (wchar_t *)qword_1800EE510;
  v37 = 0;
  v41 = 0;
  v40 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v11 = 246;
  if ( !a1 || (v35 = 246, v11 = 247, !a2) || (v35 = 247, v11 = 248, !a3) )
  {
    v36 = v11;
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_91;
  }
  LastFailureAsHRESULT = 0;
  v35 = 248;
  v12 = CSxSimpleArray<unsigned short *>::CreateInstance(&Block);
  v8 = Block;
  v13 = v12 < 0;
  LastFailureAsHRESULT = v12;
  v14 = 250;
  if ( v13 )
    goto LABEL_86;
  v35 = 250;
  FileW = (__int64)CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15);
    v14 = 259;
LABEL_86:
    v36 = v14;
    if ( v8 && *((_DWORD *)v8 + 4) )
    {
      do
      {
        v29 = v7;
        CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v8 + 1) + 8LL * v7++));
        *(_QWORD *)(*((_QWORD *)v8 + 1) + 8 * v29) = 0;
      }
      while ( v7 < *((_DWORD *)v8 + 4) );
    }
    goto LABEL_91;
  }
  LastFailureAsHRESULT = 0;
  v35 = 259;
  v43 = 0;
  v16 = 32;
  nOutBufferSize = 32;
  InBuffer = 0;
  while ( 1 )
  {
    v9 = CoTaskMemRealloc(v9, v16);
    v14 = 269;
    if ( !v9 )
    {
      LastFailureAsHRESULT = -2147024882;
      goto LABEL_86;
    }
    v35 = 269;
    LastFailureAsHRESULT = 0;
    v17 = DeviceIoControl((HANDLE)FileW, 0x6D0008u, &InBuffer, 0x18u, v9, nOutBufferSize, &nOutBufferSize, 0);
    nOutBufferSize = *v9;
    if ( v17 )
      break;
    if ( GetLastError() != 234 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v19);
      v14 = 283;
      goto LABEL_86;
    }
    v16 = nOutBufferSize;
  }
  LastFailureAsHRESULT = 0;
  v35 = 283;
  LastFailureAsHRESULT = SxGetUniqueVolumeForPath(a1, &String2, v18);
  v14 = 288;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v35 = 288;
  LastFailureAsHRESULT = SxCopyString(&String2, (unsigned __int16 **)&pv);
  v14 = 289;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v35 = 289;
  LastFailureAsHRESULT = CSxSimpleArray<unsigned short *>::Append(v8, pv);
  v14 = 290;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v35 = 290;
  v20 = 0;
  pv = 0;
  while ( 1 )
  {
    if ( v20 >= v9[1] )
      goto LABEL_82;
    v21 = v9[6 * v20 + 3];
    v22 = (_WORD *)((char *)v9 + (unsigned int)v9[6 * v20 + 2]);
    WORD1(v37) = v21;
    LOWORD(v37) = v21;
    *((_QWORD *)&v37 + 1) = v22;
    if ( (v21 == 96 || v21 == 98 && v22[48] == 92)
      && *v22 == 92
      && (v22[1] == 63 || v22[1] == 92)
      && v22[2] == 63
      && v22[3] == 92
      && v22[4] == 86
      && v22[5] == 111
      && v22[6] == 108
      && v22[7] == 117
      && v22[8] == 109
      && v22[9] == 101
      && v22[10] == 123
      && v22[19] == 45
      && v22[24] == 45
      && v22[29] == 45
      && v22[34] == 45
      && v22[47] == 125
      && v21 == 96
      && v22[1] == 63 )
    {
      LastFailureAsHRESULT = ConvertNtNameToWin32Name(&v37, String1);
      v14 = 310;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_83;
      v35 = 310;
      if ( !_wcsicmp(String1[0], &String2) )
        break;
    }
    ++v20;
  }
  v23 = v9[6 * v20 + 7];
  v9[6 * v20 + 2] = 0;
  v41.MaximumLength = v23;
  v41.Length = v23;
  v41.Buffer = (PWSTR)((char *)v9 + (unsigned int)v9[6 * v20 + 6]);
  if ( v20 >= v9[1] )
  {
LABEL_82:
    LastFailureAsHRESULT = -2147024809;
    v14 = 325;
LABEL_83:
    v7 = 0;
    goto LABEL_86;
  }
  v7 = 0;
  LastFailureAsHRESULT = 0;
  v24 = 0;
  v35 = 325;
  while ( v24 < v9[1] )
  {
    v25 = v9[6 * v24 + 3];
    if ( v25 )
    {
      v26 = (_WORD *)((char *)v9 + (unsigned int)v9[6 * v24 + 2]);
      WORD1(v37) = v9[6 * v24 + 3];
      LOWORD(v37) = v25;
      *((_QWORD *)&v37 + 1) = v26;
      if ( (v25 == 96 || v25 == 98 && v26[48] == 92)
        && *v26 == 92
        && (v26[1] == 63 || v26[1] == 92)
        && v26[2] == 63
        && v26[3] == 92
        && v26[4] == 86
        && v26[5] == 111
        && v26[6] == 108
        && v26[7] == 117
        && v26[8] == 109
        && v26[9] == 101
        && v26[10] == 123
        && v26[19] == 45
        && v26[24] == 45
        && v26[29] == 45
        && v26[34] == 45
        && v26[47] == 125
        && v25 == 96
        && v26[1] == 63 )
      {
        v40.MaximumLength = v9[6 * v24 + 7];
        v40.Length = v40.MaximumLength;
        v40.Buffer = (PWSTR)((char *)v9 + (unsigned int)v9[6 * v24 + 6]);
        if ( RtlEqualUnicodeString(&v41, &v40, 1u) )
        {
          LastFailureAsHRESULT = ConvertNtNameToWin32Name(&v37, String1);
          v14 = 362;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v35 = 362;
          LastFailureAsHRESULT = SxCopyString(String1[0], (unsigned __int16 **)&pv);
          v14 = 363;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v35 = 363;
          LastFailureAsHRESULT = CSxSimpleArray<unsigned short *>::Append(v8, pv);
          v14 = 364;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v35 = 364;
          pv = 0;
        }
      }
    }
    ++v24;
  }
  v27 = v8;
  *a3 = *((_DWORD *)v8 + 4);
  v28 = (unsigned __int16 **)*((_QWORD *)v8 + 1);
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  v8 = 0;
  *a2 = v28;
  CSxSimpleArray<unsigned short *>::Release(v27);
LABEL_91:
  CoTaskMemFree(v9);
  CoTaskMemFree(pv);
  v30 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)String1);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( v8 )
    CSxSimpleArray<unsigned short *>::Release(v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v30;
}

```

## disassembly

```asm
0x180094d48  mov     [rsp-8+arg_18], rbx
0x180094d4d  push    rbp
0x180094d4e  push    rsi
0x180094d4f  push    rdi
0x180094d50  push    r12
0x180094d52  push    r13
0x180094d54  push    r14
0x180094d56  push    r15
0x180094d58  lea     rbp, [rsp-210h]
0x180094d60  sub     rsp, 310h
0x180094d67  mov     rax, cs:__security_cookie
0x180094d6e  xor     rax, rsp
0x180094d71  mov     [rbp+240h+var_40], rax
0x180094d78  mov     r12, r8
0x180094d7b  mov     r13, rdx
0x180094d7e  mov     rdi, rcx
0x180094d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180094d88  lea     rax, WPP_GLOBAL_Control
0x180094d8f  cmp     rcx, rax
0x180094d92  jz      short loc_180094DB2
0x180094d94  test    dword ptr [rcx+1Ch], 20000000h
0x180094d9b  jz      short loc_180094DB2
0x180094d9d  mov     rcx, [rcx+10h]
0x180094da1  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180094da8  mov     edx, 0Fh
0x180094dad  call    WPP_SF_
0x180094db2  mov     r9d, 1; unsigned __int16
0x180094db8  lea     rdx, aSxgetallvolume; "SxGetAllVolumeGUIDNames"
0x180094dbf  mov     r8d, 0E2h; unsigned __int16
0x180094dc5  lea     rcx, [rsp+340h+var_2F0]; this
0x180094dca  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180094dcf  xor     esi, esi
0x180094dd1  lea     rcx, [rbp+240h+var_24E]; void *
0x180094dd5  xorps   xmm0, xmm0
0x180094dd8  mov     [rbp+240h+Block], rsi
0x180094ddc  xor     eax, eax
0x180094dde  mov     [rsp+340h+nOutBufferSize], esi
0x180094de2  xor     edx, edx; Val
0x180094de4  mov     [rbp+240h+var_260], rax
0x180094de8  mov     r8d, 208h; Size
0x180094dee  mov     [rbp+240h+String2], si
0x180094df2  movups  [rbp+240h+InBuffer], xmm0
0x180094df6  mov     r14d, esi
0x180094df9  mov     r15d, esi
0x180094dfc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180094e00  call    memset_0
0x180094e05  mov     [rbp+240h+var_2A0], rsi
0x180094e09  xorps   xmm0, xmm0
0x180094e0c  mov     [rsp+340h+pv], rsi
0x180094e11  lea     rax, qword_1800EE510
0x180094e18  mov     [rbp+240h+String1], rax
0x180094e1c  xorps   xmm1, xmm1
0x180094e1f  movups  [rbp+240h+var_2B8], xmm0
0x180094e23  movups  xmmword ptr [rbp+240h+var_280.Length], xmm1
0x180094e27  movups  xmmword ptr [rbp+240h+var_290.Length], xmm0
0x180094e2b  test    r13, r13
0x180094e2e  jz      short loc_180094E34
0x180094e30  mov     [r13+0], rsi
0x180094e34  test    r12, r12
0x180094e37  jz      short loc_180094E3D
0x180094e39  mov     [r12], esi
0x180094e3d  mov     eax, 0F6h
0x180094e42  test    rdi, rdi
0x180094e45  jz      loc_1800953CA
0x180094e4b  mov     [rsp+340h+var_2EC], ax
0x180094e50  mov     eax, 0F7h
0x180094e55  test    r13, r13
0x180094e58  jz      loc_1800953CA
0x180094e5e  mov     [rsp+340h+var_2EC], ax
0x180094e63  mov     eax, 0F8h
0x180094e68  test    r12, r12
0x180094e6b  jz      loc_1800953CA
0x180094e71  lea     rcx, [rbp+240h+Block]
0x180094e75  mov     [rsp+340h+var_2F0], esi
0x180094e79  mov     [rsp+340h+var_2EC], ax
0x180094e7e  call    ?CreateInstance@?$CSxSimpleArray@PEAG@@SAJPEAPEAV1@@Z; CSxSimpleArray<ushort *>::CreateInstance(CSxSimpleArray<ushort *> * *)
0x180094e83  mov     r14, [rbp+240h+Block]
0x180094e87  test    eax, eax
0x180094e89  mov     [rsp+340h+var_2F0], eax
0x180094e8d  mov     eax, 0FAh
0x180094e92  js      loc_18009538F
0x180094e98  mov     [rsp+340h+hTemplateFile], rbx; hTemplateFile
0x180094e9d  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x180094ea4  mov     r8d, 3; dwShareMode
0x180094eaa  mov     [rsp+340h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180094eb2  xor     r9d, r9d; lpSecurityAttributes
0x180094eb5  mov     [rsp+340h+dwCreationDisposition], r8d; dwCreationDisposition
0x180094eba  xor     edx, edx; dwDesiredAccess
0x180094ebc  mov     [rsp+340h+var_2EC], ax
0x180094ec1  call    cs:__imp_CreateFileW
0x180094ec8  nop     dword ptr [rax+rax+00h]
0x180094ecd  mov     rbx, rax
0x180094ed0  dec     rax
0x180094ed3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180094ed7  ja      loc_180095381
0x180094edd  mov     eax, 103h
0x180094ee2  mov     [rsp+340h+var_2F0], esi
0x180094ee6  mov     [rsp+340h+var_2EC], ax
0x180094eeb  xorps   xmm0, xmm0
0x180094eee  xor     eax, eax
0x180094ef0  mov     [rbp+240h+var_260], rax
0x180094ef4  mov     eax, 20h ; ' '
0x180094ef9  mov     [rsp+340h+nOutBufferSize], eax
0x180094efd  movups  [rbp+240h+InBuffer], xmm0
0x180094f01  mov     edx, eax; cb
0x180094f03  mov     rcx, r15; pv
0x180094f06  call    cs:__imp_CoTaskMemRealloc
0x180094f0d  nop     dword ptr [rax+rax+00h]
0x180094f12  mov     r15, rax
0x180094f15  test    rax, rax
0x180094f18  mov     eax, 10Dh
0x180094f1d  jz      loc_180095377
0x180094f23  mov     [rsp+340h+lpOverlapped], rsi; lpOverlapped
0x180094f28  lea     rcx, [rsp+340h+nOutBufferSize]
0x180094f2d  mov     [rsp+340h+hTemplateFile], rcx; lpBytesReturned
0x180094f32  lea     r8, [rbp+240h+InBuffer]; lpInBuffer
0x180094f36  mov     [rsp+340h+var_2EC], ax
0x180094f3b  mov     rcx, rbx; hDevice
0x180094f3e  mov     eax, [rsp+340h+nOutBufferSize]
0x180094f42  mov     r9d, 18h; nInBufferSize
0x180094f48  mov     [rsp+340h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180094f4c  mov     edx, 6D0008h; dwIoControlCode
0x180094f51  mov     qword ptr [rsp+340h+dwCreationDisposition], r15; lpOutBuffer
0x180094f56  mov     [rsp+340h+var_2F0], esi
0x180094f5a  call    cs:__imp_DeviceIoControl
0x180094f61  nop     dword ptr [rax+rax+00h]
0x180094f66  mov     ecx, [r15]
0x180094f69  mov     [rsp+340h+nOutBufferSize], ecx
0x180094f6d  test    eax, eax
0x180094f6f  jnz     short loc_180094FA0
0x180094f71  call    cs:__imp_GetLastError
0x180094f78  nop     dword ptr [rax+rax+00h]
0x180094f7d  cmp     eax, 0EAh
0x180094f82  jnz     short loc_180094F8D
0x180094f84  mov     eax, [rsp+340h+nOutBufferSize]
0x180094f88  jmp     loc_180094F01
0x180094f8d  call    GetLastFailureAsHRESULT
0x180094f92  mov     [rsp+340h+var_2F0], eax
0x180094f96  mov     eax, 11Bh
0x180094f9b  jmp     loc_18009538F
0x180094fa0  mov     eax, 11Bh
0x180094fa5  mov     [rsp+340h+var_2F0], esi
0x180094fa9  lea     rdx, [rbp+240h+String2]; lpszVolumeName
0x180094fad  mov     [rsp+340h+var_2EC], ax
0x180094fb2  mov     rcx, rdi; unsigned __int16 *
0x180094fb5  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x180094fba  mov     [rsp+340h+var_2F0], eax
0x180094fbe  test    eax, eax
0x180094fc0  mov     eax, 120h
0x180094fc5  js      loc_18009538F
0x180094fcb  lea     rdx, [rsp+340h+pv]; unsigned __int16 **
0x180094fd0  mov     [rsp+340h+var_2EC], ax
0x180094fd5  lea     rcx, [rbp+240h+String2]; Src
0x180094fd9  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180094fde  mov     [rsp+340h+var_2F0], eax
0x180094fe2  test    eax, eax
0x180094fe4  mov     eax, 121h
0x180094fe9  js      loc_18009538F
0x180094fef  mov     rdx, [rsp+340h+pv]
0x180094ff4  mov     rcx, r14
0x180094ff7  mov     [rsp+340h+var_2EC], ax
0x180094ffc  call    ?Append@?$CSxSimpleArray@PEAG@@QEAAJPEAG@Z; CSxSimpleArray<ushort *>::Append(ushort *)
0x180095001  mov     [rsp+340h+var_2F0], eax
0x180095005  test    eax, eax
0x180095007  mov     eax, 122h
0x18009500c  js      loc_18009538F
0x180095012  mov     [rsp+340h+var_2EC], ax
0x180095017  mov     edi, esi
0x180095019  mov     [rsp+340h+pv], rsi
0x18009501e  cmp     edi, [r15+4]
0x180095022  jnb     loc_180095366
0x180095028  mov     eax, edi
0x18009502a  lea     rsi, [rax+rax*2]
0x18009502e  movzx   edx, word ptr [r15+rsi*8+0Ch]
0x180095034  mov     ecx, [r15+rsi*8+8]
0x180095039  add     rcx, r15
0x18009503c  mov     word ptr [rbp+240h+var_2B8+2], dx
0x180095040  mov     word ptr [rbp+240h+var_2B8], dx
0x180095044  mov     qword ptr [rbp+240h+var_2B8+8], rcx
0x180095048  cmp     dx, 60h ; '`'
0x18009504c  jz      short loc_180095063
0x18009504e  cmp     dx, 62h ; 'b'
0x180095052  jnz     loc_180095143
0x180095058  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x18009505d  jnz     loc_180095143
0x180095063  cmp     word ptr [rcx], 5Ch ; '\'
0x180095067  jnz     loc_180095143
0x18009506d  cmp     word ptr [rcx+2], 3Fh ; '?'
0x180095072  jz      short loc_18009507F
0x180095074  cmp     word ptr [rcx+2], 5Ch ; '\'
0x180095079  jnz     loc_180095143
0x18009507f  cmp     word ptr [rcx+4], 3Fh ; '?'
0x180095084  jnz     loc_180095143
0x18009508a  cmp     word ptr [rcx+6], 5Ch ; '\'
0x18009508f  jnz     loc_180095143
0x180095095  cmp     word ptr [rcx+8], 56h ; 'V'
0x18009509a  jnz     loc_180095143
0x1800950a0  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x1800950a5  jnz     loc_180095143
0x1800950ab  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1800950b0  jnz     loc_180095143
0x1800950b6  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1800950bb  jnz     loc_180095143
0x1800950c1  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1800950c6  jnz     short loc_180095143
0x1800950c8  cmp     word ptr [rcx+12h], 65h ; 'e'
0x1800950cd  jnz     short loc_180095143
0x1800950cf  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x1800950d4  jnz     short loc_180095143
0x1800950d6  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x1800950db  jnz     short loc_180095143
0x1800950dd  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x1800950e2  jnz     short loc_180095143
0x1800950e4  cmp     word ptr [rcx+3Ah], 2Dh ; '-'
0x1800950e9  jnz     short loc_180095143
0x1800950eb  cmp     word ptr [rcx+44h], 2Dh ; '-'
0x1800950f0  jnz     short loc_180095143
0x1800950f2  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x1800950f7  jnz     short loc_180095143
0x1800950f9  cmp     dx, 60h ; '`'
0x1800950fd  jnz     short loc_180095143
0x1800950ff  cmp     word ptr [rcx+2], 3Fh ; '?'
0x180095104  jnz     short loc_180095143
0x180095106  lea     rdx, [rbp+240h+String1]
0x18009510a  lea     rcx, [rbp+240h+var_2B8]
0x18009510e  call    _ConvertNtNameToWin32Name
0x180095113  mov     [rsp+340h+var_2F0], eax
0x180095117  test    eax, eax
0x180095119  mov     eax, 136h
0x18009511e  js      loc_180095373
0x180095124  mov     rcx, [rbp+240h+String1]; String1
0x180095128  lea     rdx, [rbp+240h+String2]; String2
0x18009512c  mov     [rsp+340h+var_2EC], ax
0x180095131  call    cs:__imp__wcsicmp
0x180095138  nop     dword ptr [rax+rax+00h]
0x18009513d  xor     ecx, ecx
0x18009513f  test    eax, eax
0x180095141  jz      short loc_18009514A
0x180095143  inc     edi
0x180095145  jmp     loc_18009501E
0x18009514a  movzx   eax, word ptr [r15+rsi*8+1Ch]
0x180095150  mov     [r15+rsi*8+8], ecx
0x180095155  mov     [rbp+240h+var_280.MaximumLength], ax
0x180095159  mov     [rbp+240h+var_280.Length], ax
0x18009515d  mov     eax, [r15+rsi*8+18h]
0x180095162  add     rax, r15
0x180095165  mov     [rbp+240h+var_280.Buffer], rax
0x180095169  cmp     edi, [r15+4]
0x18009516d  jnb     loc_180095366
0x180095173  xor     esi, esi
0x180095175  mov     eax, 145h
0x18009517a  mov     [rsp+340h+var_2F0], esi
0x18009517e  mov     edi, esi
0x180095180  mov     [rsp+340h+var_2EC], ax
0x180095185  cmp     edi, [r15+4]
0x180095189  jnb     loc_180095341
0x18009518f  mov     eax, edi
0x180095191  lea     r8, [rax+rax*2]
0x180095195  movzx   edx, word ptr [r15+r8*8+0Ch]
0x18009519b  test    dx, dx
0x18009519e  jz      loc_18009533A
0x1800951a4  mov     ecx, [r15+r8*8+8]
0x1800951a9  add     rcx, r15
0x1800951ac  mov     word ptr [rbp+240h+var_2B8+2], dx
0x1800951b0  mov     word ptr [rbp+240h+var_2B8], dx
0x1800951b4  mov     qword ptr [rbp+240h+var_2B8+8], rcx
0x1800951b8  cmp     dx, 60h ; '`'
0x1800951bc  jz      short loc_1800951D3
0x1800951be  cmp     dx, 62h ; 'b'
0x1800951c2  jnz     loc_18009533A
0x1800951c8  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x1800951cd  jnz     loc_18009533A
0x1800951d3  cmp     word ptr [rcx], 5Ch ; '\'
0x1800951d7  jnz     loc_18009533A
0x1800951dd  cmp     word ptr [rcx+2], 3Fh ; '?'
0x1800951e2  jz      short loc_1800951EF
0x1800951e4  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1800951e9  jnz     loc_18009533A
0x1800951ef  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1800951f4  jnz     loc_18009533A
0x1800951fa  cmp     word ptr [rcx+6], 5Ch ; '\'
0x1800951ff  jnz     loc_18009533A
0x180095205  cmp     word ptr [rcx+8], 56h ; 'V'
0x18009520a  jnz     loc_18009533A
0x180095210  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x180095215  jnz     loc_18009533A
0x18009521b  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x180095220  jnz     loc_18009533A
0x180095226  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x18009522b  jnz     loc_18009533A
0x180095231  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x180095236  jnz     loc_18009533A
0x18009523c  cmp     word ptr [rcx+12h], 65h ; 'e'
0x180095241  jnz     loc_18009533A
0x180095247  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x18009524c  jnz     loc_18009533A
0x180095252  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x180095257  jnz     loc_18009533A
0x18009525d  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x180095262  jnz     loc_18009533A
  ... truncated ...
```
