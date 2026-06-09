# _anonymous_namespace_::GetDiskSizeInternal

- ea: `0x180038e54`
- end: `0x18003911b`
- name: `_anonymous_namespace_::GetDiskSizeInternal`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x180039c58`

## callees

- `0x18000d030`
- `0x18000d450`
- `0x18000ddb0`
- `0x180012c50`
- `0x180012c9c`
- `0x180024638`
- `0x180025210`
- `0x1800375c0`
- `0x180038e54`
- `0x180039124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ffc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ffc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180038ff1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180038ff1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180038f1c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180038f1c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800390c6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800390c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038faf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038faf`

## pseudocode

```c
signed int __fastcall anonymous_namespace_::GetDiskSizeInternal(
        unsigned int a1,
        unsigned int a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 v9; // rcx
  signed int result; // eax
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  HANDLE FileW; // r14
  BOOL v15; // ebx
  StorageService *v16; // rcx
  int v17; // ebx
  DWORD FileAttributesW; // eax
  int v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  __int64 OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szVolumeMountPoint[282]; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v26; // [rsp+2A8h] [rbp+1A8h]
  WCHAR szVolumeName[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  wchar_t v28[264]; // [rsp+6E0h] [rbp+5E0h] BYREF

  memset_0(v28, 0, 0x208u);
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  memset_0(szVolumeMountPoint, 0, 0x454u);
  v24 = 1112;
  result = StorageService::GetStorageDeviceInfo(v9, 0, a1, a2, (__int64)&v24);
  if ( result < 0 )
    return result;
  result = StringCchCatW(szVolumeMountPoint, v11, L"\\");
  if ( result < 0 )
    return result;
  BytesReturned = 0;
  OutBuffer = 0;
  if ( !GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x104u) )
    goto LABEL_4;
  v12 = -1;
  do
    ++v12;
  while ( szVolumeName[v12] );
  v13 = 2 * v12 - 2;
  if ( v13 >= 0x208 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)szVolumeName + v13) = 0;
  FileW = CreateFileW(szVolumeName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL
    || (v15 = DeviceIoControl(FileW, 0x7405Cu, 0, 0, &OutBuffer, 8u, &BytesReturned, 0), CloseHandle(FileW), !v15) )
  {
LABEL_4:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  *a3 += OutBuffer;
  if ( a1 || a2 )
  {
    v19[0] = 0;
    if ( a1 || a2 )
      goto LABEL_19;
  }
  else
  {
    *a4 = v26;
    v19[0] = 0;
  }
  if ( StorageService::GetUserDataPath(v16, v28, v19) < 0 )
  {
LABEL_19:
    v17 = 0;
    StringCchCopyW(v28, 0x104u, szVolumeMountPoint);
    goto LABEL_20;
  }
  v17 = v19[0];
LABEL_20:
  if ( v17 )
    *a4 += OutBuffer;
  v23 = 0;
  v22 = 0;
  if ( (int)SvcGetStorageDeviceSize(0, v28, &v22, &v23, 0) >= 0 )
  {
    *a5 = v22;
    if ( v17 )
      *a3 += v23;
  }
  FileAttributesW = GetFileAttributesW(L"C:\\SDCard");
  if ( FileAttributesW != -1 && (FileAttributesW & 0x410) == 0x410 )
  {
    *(_QWORD *)v19 = 0;
    if ( (int)anonymous_namespace_::GetDiskSizeSD(1, 0, v19, a5) >= 0 && !a1 && *(_QWORD *)v19 < *a3 )
      *a3 -= *(_QWORD *)v19;
  }
  return 0;
}

```

## disassembly

```asm
0x180038e54  push    rbp
0x180038e56  push    rbx
0x180038e57  push    rsi
0x180038e58  push    rdi
0x180038e59  push    r12
0x180038e5b  push    r13
0x180038e5d  push    r14
0x180038e5f  push    r15
0x180038e61  lea     rbp, [rsp-808h]
0x180038e69  sub     rsp, 908h
0x180038e70  mov     rax, cs:__security_cookie
0x180038e77  xor     rax, rsp
0x180038e7a  mov     [rbp+840h+var_50], rax
0x180038e81  mov     r13, [rbp+840h+arg_20]
0x180038e88  mov     rdi, r8
0x180038e8b  mov     r12d, edx
0x180038e8e  mov     r15d, ecx
0x180038e91  mov     r14d, 208h
0x180038e97  lea     rcx, [rbp+840h+var_260]; void *
0x180038e9e  mov     r8d, r14d; Size
0x180038ea1  xor     edx, edx; Val
0x180038ea3  mov     rsi, r9
0x180038ea6  call    memset_0
0x180038eab  xor     ebx, ebx
0x180038ead  lea     rcx, [rsp+940h+szVolumeMountPoint]; void *
0x180038eb2  mov     [rdi], rbx
0x180038eb5  xor     edx, edx; Val
0x180038eb7  mov     [rsi], rbx
0x180038eba  mov     r8d, 454h; Size
0x180038ec0  mov     [r13+0], rbx
0x180038ec4  call    memset_0
0x180038ec9  lea     rax, [rsp+940h+var_8D0]
0x180038ece  mov     [rsp+940h+var_8D0], 458h
0x180038ed6  mov     r9d, r12d
0x180038ed9  mov     qword ptr [rsp+940h+dwCreationDisposition], rax
0x180038ede  mov     r8d, r15d
0x180038ee1  xor     edx, edx
0x180038ee3  call    ?GetStorageDeviceInfo@StorageService@@QEAAJPEAXW4_STORAGE_DEVICE_TYPE@@KPEAU_STORAGE_DEVICE_INFO@@@Z; StorageService::GetStorageDeviceInfo(void *,_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DEVICE_INFO *)
0x180038ee8  test    eax, eax
0x180038eea  js      short loc_180038F38
0x180038eec  lea     r8, asc_180092790; "\\"
0x180038ef3  lea     rcx, [rsp+940h+szVolumeMountPoint]; unsigned __int16 *
0x180038ef8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180038efd  test    eax, eax
0x180038eff  js      short loc_180038F38
0x180038f01  mov     r8d, 104h; cchBufferLength
0x180038f07  mov     [rsp+940h+BytesReturned], ebx
0x180038f0b  lea     rdx, [rbp+840h+szVolumeName]; lpszVolumeName
0x180038f12  mov     [rsp+940h+OutBuffer], rbx
0x180038f17  lea     rcx, [rsp+940h+szVolumeMountPoint]; lpszVolumeMountPoint
0x180038f1c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180038f22  test    eax, eax
0x180038f24  jnz     short loc_180038F5B
0x180038f26  call    cs:__imp_GetLastError
0x180038f2c  test    eax, eax
0x180038f2e  jle     short loc_180038F38
0x180038f30  movzx   eax, ax
0x180038f33  or      eax, 80070000h
0x180038f38  mov     rcx, [rbp+840h+var_50]
0x180038f3f  xor     rcx, rsp; StackCookie
0x180038f42  call    __security_check_cookie
0x180038f47  add     rsp, 908h
0x180038f4e  pop     r15
0x180038f50  pop     r14
0x180038f52  pop     r13
0x180038f54  pop     r12
0x180038f56  pop     rdi
0x180038f57  pop     rsi
0x180038f58  pop     rbx
0x180038f59  pop     rbp
0x180038f5a  retn
0x180038f5b  lea     rcx, [rbp+840h+szVolumeName]
0x180038f62  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038f66  inc     rax
0x180038f69  cmp     [rcx+rax*2], bx
0x180038f6d  jnz     short loc_180038F66
0x180038f6f  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180038f77  cmp     rcx, r14
0x180038f7a  jnb     loc_180039115
0x180038f80  mov     [rbp+rcx+840h+szVolumeName], bx
0x180038f88  mov     r8d, 3; dwShareMode
0x180038f8e  mov     [rsp+940h+hTemplateFile], rbx; hTemplateFile
0x180038f93  lea     rcx, [rbp+840h+szVolumeName]; lpFileName
0x180038f9a  mov     [rsp+940h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180038fa2  xor     r9d, r9d; lpSecurityAttributes
0x180038fa5  mov     edx, 80000000h; dwDesiredAccess
0x180038faa  mov     [rsp+940h+dwCreationDisposition], r8d; dwCreationDisposition
0x180038faf  call    cs:__imp_CreateFileW
0x180038fb5  mov     r14, rax
0x180038fb8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038fbc  jz      loc_180038F26
0x180038fc2  mov     [rsp+940h+lpOverlapped], rbx; lpOverlapped
0x180038fc7  lea     rax, [rsp+940h+BytesReturned]
0x180038fcc  mov     [rsp+940h+hTemplateFile], rax; lpBytesReturned
0x180038fd1  xor     r9d, r9d; nInBufferSize
0x180038fd4  lea     rax, [rsp+940h+OutBuffer]
0x180038fd9  mov     [rsp+940h+dwFlagsAndAttributes], 8; nOutBufferSize
0x180038fe1  xor     r8d, r8d; lpInBuffer
0x180038fe4  mov     qword ptr [rsp+940h+dwCreationDisposition], rax; lpOutBuffer
0x180038fe9  mov     edx, 7405Ch; dwIoControlCode
0x180038fee  mov     rcx, r14; hDevice
0x180038ff1  call    cs:__imp_DeviceIoControl
0x180038ff7  mov     rcx, r14; hObject
0x180038ffa  mov     ebx, eax
0x180038ffc  call    cs:__imp_CloseHandle
0x180039002  xor     r14d, r14d
0x180039005  test    ebx, ebx
0x180039007  jz      loc_180038F26
0x18003900d  mov     rax, [rsp+940h+OutBuffer]
0x180039012  add     [rdi], rax
0x180039015  test    r15d, r15d
0x180039018  jnz     short loc_180039030
0x18003901a  test    r12d, r12d
0x18003901d  jnz     short loc_180039030
0x18003901f  mov     rax, [rbp+840h+var_698]
0x180039026  mov     [rsi], rax
0x180039029  mov     [rsp+940h+var_900], r14d
0x18003902e  jmp     short loc_18003903F
0x180039030  mov     [rsp+940h+var_900], r14d
0x180039035  test    r15d, r15d
0x180039038  jnz     short loc_18003905A
0x18003903a  test    r12d, r12d
0x18003903d  jnz     short loc_18003905A
0x18003903f  lea     r8, [rsp+940h+var_900]; int *
0x180039044  lea     rdx, [rbp+840h+var_260]; unsigned __int16 *
0x18003904b  call    ?GetUserDataPath@StorageService@@QEAAJPEAGPEAH@Z; StorageService::GetUserDataPath(ushort *,int *)
0x180039050  test    eax, eax
0x180039052  js      short loc_18003905A
0x180039054  mov     ebx, [rsp+940h+var_900]
0x180039058  jmp     short loc_180039073
0x18003905a  lea     r8, [rsp+940h+szVolumeMountPoint]; wchar_t *
0x18003905f  mov     edx, 104h; unsigned __int64
0x180039064  lea     rcx, [rbp+840h+var_260]; wchar_t *
0x18003906b  mov     ebx, r14d
0x18003906e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180039073  test    ebx, ebx
0x180039075  jz      short loc_18003907F
0x180039077  mov     rax, [rsp+940h+OutBuffer]
0x18003907c  add     [rsi], rax
0x18003907f  lea     r9, [rsp+940h+var_8E0]
0x180039084  mov     [rsp+940h+var_8E0], r14
0x180039089  lea     r8, [rsp+940h+var_8E8]
0x18003908e  mov     [rsp+940h+var_8E8], r14
0x180039093  lea     rdx, [rbp+840h+var_260]
0x18003909a  mov     qword ptr [rsp+940h+dwCreationDisposition], r14
0x18003909f  xor     ecx, ecx
0x1800390a1  call    SvcGetStorageDeviceSize
0x1800390a6  test    eax, eax
0x1800390a8  js      short loc_1800390BF
0x1800390aa  mov     rax, [rsp+940h+var_8E8]
0x1800390af  mov     [r13+0], rax
0x1800390b3  test    ebx, ebx
0x1800390b5  jz      short loc_1800390BF
0x1800390b7  mov     rax, [rsp+940h+var_8E0]
0x1800390bc  add     [rdi], rax
0x1800390bf  lea     rcx, FileName; "C:\\SDCard"
0x1800390c6  call    cs:__imp_GetFileAttributesW
0x1800390cc  cmp     eax, 0FFFFFFFFh
0x1800390cf  jz      short loc_18003910E
0x1800390d1  mov     ecx, 410h
0x1800390d6  and     eax, ecx
0x1800390d8  cmp     eax, ecx
0x1800390da  jnz     short loc_18003910E
0x1800390dc  xor     edx, edx
0x1800390de  mov     qword ptr [rsp+940h+var_900], r14
0x1800390e3  mov     r9, r13
0x1800390e6  lea     r8, [rsp+940h+var_900]
0x1800390eb  lea     ecx, [rdx+1]
0x1800390ee  call    _anonymous_namespace___GetDiskSizeSD
0x1800390f3  test    eax, eax
0x1800390f5  js      short loc_18003910E
0x1800390f7  test    r15d, r15d
0x1800390fa  jnz     short loc_18003910E
0x1800390fc  mov     rax, [rdi]
0x1800390ff  cmp     qword ptr [rsp+940h+var_900], rax
0x180039104  jnb     short loc_18003910E
0x180039106  sub     rax, qword ptr [rsp+940h+var_900]
0x18003910b  mov     [rdi], rax
0x18003910e  xor     eax, eax
0x180039110  jmp     loc_180038F38
0x180039115  call    __report_rangecheckfailure
```
