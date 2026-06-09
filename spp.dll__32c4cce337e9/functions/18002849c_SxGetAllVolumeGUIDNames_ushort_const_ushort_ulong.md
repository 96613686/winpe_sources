# SxGetAllVolumeGUIDNames(ushort const *,ushort * * *,ulong *)

- ea: `0x18002849c`
- end: `0x180028b75`
- name: `?SxGetAllVolumeGUIDNames@@YAJPEBGPEAPEAPEAGPEAK@Z`
- size: `1753`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028b7c`

## callees

- `0x18000702c`
- `0x18000e040`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002758c`
- `0x18002849c`
- `0x1800299c4`
- `0x18002b164`
- `0x18002be5c`
- `0x18002d6e8`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002886a`
- `msvcrt!_wcsicmp` at `0x18002886a`
- `KERNEL32!GetLastError` at `0x1800286b3`
- `KERNEL32!GetLastError` at `0x1800286b3`
- `KERNEL32!CreateFileW` at `0x180028615`
- `KERNEL32!CreateFileW` at `0x180028615`
- `KERNEL32!DeviceIoControl` at `0x1800286a2`
- `KERNEL32!DeviceIoControl` at `0x1800286a2`
- `KERNEL32!CloseHandle` at `0x180028b2c`
- `KERNEL32!CloseHandle` at `0x180028b2c`
- `ntdll!RtlEqualUnicodeString` at `0x1800289f6`
- `ntdll!RtlEqualUnicodeString` at `0x1800289f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028b01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028b01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180028654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180028654`

## string_xrefs

- `0x1800285f1`: `\\.\MountPointManager`

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
  __int64 v17; // rcx
  unsigned int v18; // edi
  __int16 v19; // dx
  _WORD *v20; // rcx
  USHORT v21; // ax
  unsigned int v22; // edi
  __int16 v23; // dx
  _WORD *v24; // rcx
  void *v25; // rcx
  unsigned __int16 **v26; // rax
  __int64 v27; // rdi
  unsigned int v28; // edi
  __int64 v29; // rdx
  __int64 v30; // r8
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetAllVolumeGUIDNames", 226, 1);
  v6 = 0;
  Block = 0;
  nOutBufferSize = 0;
  v43 = 0;
  String2 = 0;
  InBuffer = 0;
  v7 = 0;
  v8 = 0;
  FileW = -1;
  memset_0(v45, 0, 0x208u);
  String1[1] = 0;
  pv = 0;
  String1[0] = (wchar_t *)&FileName;
  v37 = 0;
  v41 = 0;
  v40 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v10 = 246;
  if ( !a1 || (v35 = 246, v10 = 247, !a2) || (v35 = 247, v10 = 248, !a3) )
  {
    v36 = v10;
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_91;
  }
  LastFailureAsHRESULT = 0;
  v35 = 248;
  v11 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&Block);
  v7 = Block;
  v12 = v11 < 0;
  LastFailureAsHRESULT = v11;
  v13 = 250;
  if ( v12 )
    goto LABEL_86;
  v35 = 250;
  FileW = (__int64)CreateFileW(L"\\\\.\\MountPointManager", 0, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
    v13 = 259;
LABEL_86:
    v36 = v13;
    if ( v7 && *((_DWORD *)v7 + 4) )
    {
      do
      {
        v27 = v6;
        CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v7 + 1) + 8LL * v6++));
        *(_QWORD *)(*((_QWORD *)v7 + 1) + 8 * v27) = 0;
      }
      while ( v6 < *((_DWORD *)v7 + 4) );
    }
    goto LABEL_91;
  }
  LastFailureAsHRESULT = 0;
  v35 = 259;
  v43 = 0;
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
    v35 = 269;
    LastFailureAsHRESULT = 0;
    v16 = DeviceIoControl((HANDLE)FileW, 0x6D0008u, &InBuffer, 0x18u, v8, nOutBufferSize, &nOutBufferSize, 0);
    nOutBufferSize = *v8;
    if ( v16 )
      break;
    if ( GetLastError() != 234 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v17);
      v13 = 283;
      goto LABEL_86;
    }
    v15 = nOutBufferSize;
  }
  LastFailureAsHRESULT = 0;
  v35 = 283;
  LastFailureAsHRESULT = SxGetUniqueVolumeForPath(a1, &String2, 0x105u);
  v13 = 288;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v35 = 288;
  LastFailureAsHRESULT = SxCopyString(&String2, (unsigned __int16 **)&pv);
  v13 = 289;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v35 = 289;
  LastFailureAsHRESULT = CSxSimpleArray<unsigned short *>::Append((__int64)v7, (__int64)pv);
  v13 = 290;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_86;
  v35 = 290;
  v18 = 0;
  pv = 0;
  while ( 1 )
  {
    if ( v18 >= v8[1] )
      goto LABEL_82;
    v19 = v8[6 * v18 + 3];
    v20 = (_WORD *)((char *)v8 + (unsigned int)v8[6 * v18 + 2]);
    WORD1(v37) = v19;
    LOWORD(v37) = v19;
    *((_QWORD *)&v37 + 1) = v20;
    if ( (v19 == 96 || v19 == 98 && v20[48] == 92)
      && *v20 == 92
      && (v20[1] == 63 || v20[1] == 92)
      && v20[2] == 63
      && v20[3] == 92
      && v20[4] == 86
      && v20[5] == 111
      && v20[6] == 108
      && v20[7] == 117
      && v20[8] == 109
      && v20[9] == 101
      && v20[10] == 123
      && v20[19] == 45
      && v20[24] == 45
      && v20[29] == 45
      && v20[34] == 45
      && v20[47] == 125
      && v19 == 96
      && v20[1] == 63 )
    {
      LastFailureAsHRESULT = ConvertNtNameToWin32Name(&v37, String1);
      v13 = 310;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_83;
      v35 = 310;
      if ( !_wcsicmp(String1[0], &String2) )
        break;
    }
    ++v18;
  }
  v21 = v8[6 * v18 + 7];
  v8[6 * v18 + 2] = 0;
  v41.MaximumLength = v21;
  v41.Length = v21;
  v41.Buffer = (PWSTR)((char *)v8 + (unsigned int)v8[6 * v18 + 6]);
  if ( v18 >= v8[1] )
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
  v22 = 0;
  v35 = 325;
  while ( v22 < v8[1] )
  {
    v23 = v8[6 * v22 + 3];
    if ( v23 )
    {
      v24 = (_WORD *)((char *)v8 + (unsigned int)v8[6 * v22 + 2]);
      WORD1(v37) = v8[6 * v22 + 3];
      LOWORD(v37) = v23;
      *((_QWORD *)&v37 + 1) = v24;
      if ( (v23 == 96 || v23 == 98 && v24[48] == 92)
        && *v24 == 92
        && (v24[1] == 63 || v24[1] == 92)
        && v24[2] == 63
        && v24[3] == 92
        && v24[4] == 86
        && v24[5] == 111
        && v24[6] == 108
        && v24[7] == 117
        && v24[8] == 109
        && v24[9] == 101
        && v24[10] == 123
        && v24[19] == 45
        && v24[24] == 45
        && v24[29] == 45
        && v24[34] == 45
        && v24[47] == 125
        && v23 == 96
        && v24[1] == 63 )
      {
        v40.MaximumLength = v8[6 * v22 + 7];
        v40.Length = v40.MaximumLength;
        v40.Buffer = (PWSTR)((char *)v8 + (unsigned int)v8[6 * v22 + 6]);
        if ( RtlEqualUnicodeString(&v41, &v40, 1u) )
        {
          LastFailureAsHRESULT = ConvertNtNameToWin32Name(&v37, String1);
          v13 = 362;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v35 = 362;
          LastFailureAsHRESULT = SxCopyString(String1[0], (unsigned __int16 **)&pv);
          v13 = 363;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v35 = 363;
          LastFailureAsHRESULT = CSxSimpleArray<unsigned short *>::Append((__int64)v7, (__int64)pv);
          v13 = 364;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_86;
          v35 = 364;
          pv = 0;
        }
      }
    }
    ++v22;
  }
  v25 = v7;
  *a3 = *((_DWORD *)v7 + 4);
  v26 = (unsigned __int16 **)*((_QWORD *)v7 + 1);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  v7 = 0;
  *a2 = v26;
  CSxSimpleArray<_GUID>::Release(v25);
LABEL_91:
  CoTaskMemFree(v8);
  CoTaskMemFree(pv);
  v28 = LastFailureAsHRESULT;
  CBsString::_Release(String1);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( v7 )
    CSxSimpleArray<_GUID>::Release(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v29, v30);
  return v28;
}

```

## disassembly

```asm
0x18002849c  mov     [rsp-8+arg_18], rbx
0x1800284a1  push    rbp
0x1800284a2  push    rsi
0x1800284a3  push    rdi
0x1800284a4  push    r12
0x1800284a6  push    r13
0x1800284a8  push    r14
0x1800284aa  push    r15
0x1800284ac  lea     rbp, [rsp-210h]
0x1800284b4  sub     rsp, 310h
0x1800284bb  mov     rax, cs:__security_cookie
0x1800284c2  xor     rax, rsp
0x1800284c5  mov     [rbp+240h+var_40], rax
0x1800284cc  mov     r12, r8
0x1800284cf  mov     r13, rdx
0x1800284d2  mov     rdi, rcx
0x1800284d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284dc  lea     rax, WPP_GLOBAL_Control
0x1800284e3  cmp     rcx, rax
0x1800284e6  jz      short loc_180028506
0x1800284e8  test    dword ptr [rcx+1Ch], 20000000h
0x1800284ef  jz      short loc_180028506
0x1800284f1  mov     rcx, [rcx+10h]
0x1800284f5  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1800284fc  mov     edx, 0Fh
0x180028501  call    WPP_SF_
0x180028506  mov     r9d, 1; unsigned __int16
0x18002850c  lea     rdx, aSxgetallvolume; "SxGetAllVolumeGUIDNames"
0x180028513  mov     r8d, 0E2h; unsigned __int16
0x180028519  lea     rcx, [rsp+340h+var_2F0]; this
0x18002851e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180028523  xor     esi, esi
0x180028525  lea     rcx, [rbp+240h+var_24E]; void *
0x180028529  xorps   xmm0, xmm0
0x18002852c  mov     [rbp+240h+Block], rsi
0x180028530  xor     eax, eax
0x180028532  mov     [rsp+340h+nOutBufferSize], esi
0x180028536  xor     edx, edx; Val
0x180028538  mov     [rbp+240h+var_260], rax
0x18002853c  mov     r8d, 208h; Size
0x180028542  mov     [rbp+240h+String2], si
0x180028546  movups  [rbp+240h+InBuffer], xmm0
0x18002854a  mov     r14d, esi
0x18002854d  mov     r15d, esi
0x180028550  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028554  call    memset_0
0x180028559  mov     [rbp+240h+var_2A0], rsi
0x18002855d  xorps   xmm0, xmm0
0x180028560  mov     [rsp+340h+pv], rsi
0x180028565  lea     rax, FileName
0x18002856c  mov     [rbp+240h+String1], rax
0x180028570  xorps   xmm1, xmm1
0x180028573  movups  [rbp+240h+var_2B8], xmm0
0x180028577  movups  xmmword ptr [rbp+240h+var_280.Length], xmm1
0x18002857b  movups  xmmword ptr [rbp+240h+var_290.Length], xmm0
0x18002857f  test    r13, r13
0x180028582  jz      short loc_180028588
0x180028584  mov     [r13+0], rsi
0x180028588  test    r12, r12
0x18002858b  jz      short loc_180028591
0x18002858d  mov     [r12], esi
0x180028591  mov     eax, 0F6h
0x180028596  test    rdi, rdi
0x180028599  jz      loc_180028AF1
0x18002859f  mov     [rsp+340h+var_2EC], ax
0x1800285a4  mov     eax, 0F7h
0x1800285a9  test    r13, r13
0x1800285ac  jz      loc_180028AF1
0x1800285b2  mov     [rsp+340h+var_2EC], ax
0x1800285b7  mov     eax, 0F8h
0x1800285bc  test    r12, r12
0x1800285bf  jz      loc_180028AF1
0x1800285c5  lea     rcx, [rbp+240h+Block]
0x1800285c9  mov     [rsp+340h+var_2F0], esi
0x1800285cd  mov     [rsp+340h+var_2EC], ax
0x1800285d2  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x1800285d7  mov     r14, [rbp+240h+Block]
0x1800285db  test    eax, eax
0x1800285dd  mov     [rsp+340h+var_2F0], eax
0x1800285e1  mov     eax, 0FAh
0x1800285e6  js      loc_180028ABC
0x1800285ec  mov     [rsp+340h+hTemplateFile], rbx; hTemplateFile
0x1800285f1  lea     rcx, aMountpointmana; "\\\\.\\MountPointManager"
0x1800285f8  mov     r8d, 3; dwShareMode
0x1800285fe  mov     [rsp+340h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180028606  xor     r9d, r9d; lpSecurityAttributes
0x180028609  mov     [rsp+340h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002860e  xor     edx, edx; dwDesiredAccess
0x180028610  mov     [rsp+340h+var_2EC], ax
0x180028615  call    cs:__imp_CreateFileW
0x18002861b  mov     rbx, rax
0x18002861e  dec     rax
0x180028621  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028625  ja      loc_180028AAE
0x18002862b  mov     eax, 103h
0x180028630  mov     [rsp+340h+var_2F0], esi
0x180028634  mov     [rsp+340h+var_2EC], ax
0x180028639  xorps   xmm0, xmm0
0x18002863c  xor     eax, eax
0x18002863e  mov     [rbp+240h+var_260], rax
0x180028642  mov     eax, 20h ; ' '
0x180028647  mov     [rsp+340h+nOutBufferSize], eax
0x18002864b  movups  [rbp+240h+InBuffer], xmm0
0x18002864f  mov     edx, eax; cb
0x180028651  mov     rcx, r15; pv
0x180028654  call    cs:__imp_CoTaskMemRealloc
0x18002865a  mov     r15, rax
0x18002865d  test    rax, rax
0x180028660  mov     eax, 10Dh
0x180028665  jz      loc_180028AA4
0x18002866b  mov     [rsp+340h+lpOverlapped], rsi; lpOverlapped
0x180028670  lea     rcx, [rsp+340h+nOutBufferSize]
0x180028675  mov     [rsp+340h+hTemplateFile], rcx; lpBytesReturned
0x18002867a  lea     r8, [rbp+240h+InBuffer]; lpInBuffer
0x18002867e  mov     [rsp+340h+var_2EC], ax
0x180028683  mov     rcx, rbx; hDevice
0x180028686  mov     eax, [rsp+340h+nOutBufferSize]
0x18002868a  mov     r9d, 18h; nInBufferSize
0x180028690  mov     [rsp+340h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180028694  mov     edx, 6D0008h; dwIoControlCode
0x180028699  mov     qword ptr [rsp+340h+dwCreationDisposition], r15; lpOutBuffer
0x18002869e  mov     [rsp+340h+var_2F0], esi
0x1800286a2  call    cs:__imp_DeviceIoControl
0x1800286a8  mov     ecx, [r15]
0x1800286ab  mov     [rsp+340h+nOutBufferSize], ecx
0x1800286af  test    eax, eax
0x1800286b1  jnz     short loc_1800286D9
0x1800286b3  call    cs:__imp_GetLastError
0x1800286b9  cmp     eax, 0EAh
0x1800286be  jnz     short loc_1800286C6
0x1800286c0  mov     eax, [rsp+340h+nOutBufferSize]
0x1800286c4  jmp     short loc_18002864F
0x1800286c6  call    GetLastFailureAsHRESULT
0x1800286cb  mov     [rsp+340h+var_2F0], eax
0x1800286cf  mov     eax, 11Bh
0x1800286d4  jmp     loc_180028ABC
0x1800286d9  mov     eax, 11Bh
0x1800286de  mov     [rsp+340h+var_2F0], esi
0x1800286e2  lea     rdx, [rbp+240h+String2]; lpszVolumeName
0x1800286e6  mov     [rsp+340h+var_2EC], ax
0x1800286eb  mov     rcx, rdi; unsigned __int16 *
0x1800286ee  lea     r8d, [rax-16h]; cchBufferLength
0x1800286f2  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x1800286f7  mov     [rsp+340h+var_2F0], eax
0x1800286fb  test    eax, eax
0x1800286fd  mov     eax, 120h
0x180028702  js      loc_180028ABC
0x180028708  lea     rdx, [rsp+340h+pv]; unsigned __int16 **
0x18002870d  mov     [rsp+340h+var_2EC], ax
0x180028712  lea     rcx, [rbp+240h+String2]; Src
0x180028716  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x18002871b  mov     [rsp+340h+var_2F0], eax
0x18002871f  test    eax, eax
0x180028721  mov     eax, 121h
0x180028726  js      loc_180028ABC
0x18002872c  mov     rdx, [rsp+340h+pv]
0x180028731  mov     rcx, r14
0x180028734  mov     [rsp+340h+var_2EC], ax
0x180028739  call    ?Append@?$CSxSimpleArray@PEAG@@QEAAJPEAG@Z; CSxSimpleArray<ushort *>::Append(ushort *)
0x18002873e  mov     [rsp+340h+var_2F0], eax
0x180028742  test    eax, eax
0x180028744  mov     eax, 122h
0x180028749  js      loc_180028ABC
0x18002874f  mov     [rsp+340h+var_2EC], ax
0x180028754  mov     edi, esi
0x180028756  mov     [rsp+340h+pv], rsi
0x18002875b  cmp     edi, [r15+4]
0x18002875f  jnb     loc_180028A93
0x180028765  mov     eax, edi
0x180028767  lea     rsi, [rax+rax*2]
0x18002876b  movzx   edx, word ptr [r15+rsi*8+0Ch]
0x180028771  mov     ecx, [r15+rsi*8+8]
0x180028776  add     rcx, r15
0x180028779  mov     word ptr [rbp+240h+var_2B8+2], dx
0x18002877d  mov     word ptr [rbp+240h+var_2B8], dx
0x180028781  mov     qword ptr [rbp+240h+var_2B8+8], rcx
0x180028785  cmp     dx, 60h ; '`'
0x180028789  jz      short loc_1800287A0
0x18002878b  cmp     dx, 62h ; 'b'
0x18002878f  jnz     loc_180028876
0x180028795  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x18002879a  jnz     loc_180028876
0x1800287a0  cmp     word ptr [rcx], 5Ch ; '\'
0x1800287a4  jnz     loc_180028876
0x1800287aa  cmp     word ptr [rcx+2], 3Fh ; '?'
0x1800287af  jz      short loc_1800287BC
0x1800287b1  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1800287b6  jnz     loc_180028876
0x1800287bc  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1800287c1  jnz     loc_180028876
0x1800287c7  cmp     word ptr [rcx+6], 5Ch ; '\'
0x1800287cc  jnz     loc_180028876
0x1800287d2  cmp     word ptr [rcx+8], 56h ; 'V'
0x1800287d7  jnz     loc_180028876
0x1800287dd  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x1800287e2  jnz     loc_180028876
0x1800287e8  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1800287ed  jnz     loc_180028876
0x1800287f3  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1800287f8  jnz     short loc_180028876
0x1800287fa  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1800287ff  jnz     short loc_180028876
0x180028801  cmp     word ptr [rcx+12h], 65h ; 'e'
0x180028806  jnz     short loc_180028876
0x180028808  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x18002880d  jnz     short loc_180028876
0x18002880f  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x180028814  jnz     short loc_180028876
0x180028816  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x18002881b  jnz     short loc_180028876
0x18002881d  cmp     word ptr [rcx+3Ah], 2Dh ; '-'
0x180028822  jnz     short loc_180028876
0x180028824  cmp     word ptr [rcx+44h], 2Dh ; '-'
0x180028829  jnz     short loc_180028876
0x18002882b  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x180028830  jnz     short loc_180028876
0x180028832  cmp     dx, 60h ; '`'
0x180028836  jnz     short loc_180028876
0x180028838  cmp     word ptr [rcx+2], 3Fh ; '?'
0x18002883d  jnz     short loc_180028876
0x18002883f  lea     rdx, [rbp+240h+String1]
0x180028843  lea     rcx, [rbp+240h+var_2B8]
0x180028847  call    _ConvertNtNameToWin32Name
0x18002884c  mov     [rsp+340h+var_2F0], eax
0x180028850  test    eax, eax
0x180028852  mov     eax, 136h
0x180028857  js      loc_180028AA0
0x18002885d  mov     rcx, [rbp+240h+String1]; String1
0x180028861  lea     rdx, [rbp+240h+String2]; String2
0x180028865  mov     [rsp+340h+var_2EC], ax
0x18002886a  call    cs:__imp__wcsicmp
0x180028870  xor     ecx, ecx
0x180028872  test    eax, eax
0x180028874  jz      short loc_18002887D
0x180028876  inc     edi
0x180028878  jmp     loc_18002875B
0x18002887d  movzx   eax, word ptr [r15+rsi*8+1Ch]
0x180028883  mov     [r15+rsi*8+8], ecx
0x180028888  mov     [rbp+240h+var_280.MaximumLength], ax
0x18002888c  mov     [rbp+240h+var_280.Length], ax
0x180028890  mov     eax, [r15+rsi*8+18h]
0x180028895  add     rax, r15
0x180028898  mov     [rbp+240h+var_280.Buffer], rax
0x18002889c  cmp     edi, [r15+4]
0x1800288a0  jnb     loc_180028A93
0x1800288a6  xor     esi, esi
0x1800288a8  mov     eax, 145h
0x1800288ad  mov     [rsp+340h+var_2F0], esi
0x1800288b1  mov     edi, esi
0x1800288b3  mov     [rsp+340h+var_2EC], ax
0x1800288b8  cmp     edi, [r15+4]
0x1800288bc  jnb     loc_180028A6E
0x1800288c2  mov     eax, edi
0x1800288c4  lea     r8, [rax+rax*2]
0x1800288c8  movzx   edx, word ptr [r15+r8*8+0Ch]
0x1800288ce  test    dx, dx
0x1800288d1  jz      loc_180028A67
0x1800288d7  mov     ecx, [r15+r8*8+8]
0x1800288dc  add     rcx, r15
0x1800288df  mov     word ptr [rbp+240h+var_2B8+2], dx
0x1800288e3  mov     word ptr [rbp+240h+var_2B8], dx
0x1800288e7  mov     qword ptr [rbp+240h+var_2B8+8], rcx
0x1800288eb  cmp     dx, 60h ; '`'
0x1800288ef  jz      short loc_180028906
0x1800288f1  cmp     dx, 62h ; 'b'
0x1800288f5  jnz     loc_180028A67
0x1800288fb  cmp     word ptr [rcx+60h], 5Ch ; '\'
0x180028900  jnz     loc_180028A67
0x180028906  cmp     word ptr [rcx], 5Ch ; '\'
0x18002890a  jnz     loc_180028A67
0x180028910  cmp     word ptr [rcx+2], 3Fh ; '?'
0x180028915  jz      short loc_180028922
0x180028917  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18002891c  jnz     loc_180028A67
0x180028922  cmp     word ptr [rcx+4], 3Fh ; '?'
0x180028927  jnz     loc_180028A67
0x18002892d  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180028932  jnz     loc_180028A67
0x180028938  cmp     word ptr [rcx+8], 56h ; 'V'
0x18002893d  jnz     loc_180028A67
0x180028943  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x180028948  jnz     loc_180028A67
0x18002894e  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x180028953  jnz     loc_180028A67
0x180028959  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x18002895e  jnz     loc_180028A67
0x180028964  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x180028969  jnz     loc_180028A67
0x18002896f  cmp     word ptr [rcx+12h], 65h ; 'e'
0x180028974  jnz     loc_180028A67
0x18002897a  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x18002897f  jnz     loc_180028A67
0x180028985  cmp     word ptr [rcx+26h], 2Dh ; '-'
0x18002898a  jnz     loc_180028A67
0x180028990  cmp     word ptr [rcx+30h], 2Dh ; '-'
0x180028995  jnz     loc_180028A67
0x18002899b  cmp     word ptr [rcx+3Ah], 2Dh ; '-'
0x1800289a0  jnz     loc_180028A67
0x1800289a6  cmp     word ptr [rcx+44h], 2Dh ; '-'
0x1800289ab  jnz     loc_180028A67
  ... truncated ...
```
