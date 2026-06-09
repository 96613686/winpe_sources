# IsBootVolume(ushort const *)

- ea: `0x18004089c`
- end: `0x180040a4e`
- name: `?IsBootVolume@@YA_NPEBG@Z`
- size: `434`
- prototype: `char __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x180021bc4`

## callees

- `0x180001580`
- `0x18000212c`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x18004089c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040991`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004099e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004099e`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18004095e`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18004095e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004093f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004093f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004097d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004097d`

## string_xrefs

- `0x1800409f9`: `GetVolumeNameForVolumeMountPoint(%s) failed with 0x%08lx`

## pseudocode

```c
char __fastcall IsBootVolume(const unsigned __int16 *a1)
{
  char v2; // dl
  signed int LastError; // eax
  unsigned int v4; // ebx
  char v5; // bl
  unsigned int v7; // [rsp+20h] [rbp-E0h]
  const wchar_t *v8; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-C0h]
  const wchar_t *v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+54h] [rbp-ACh]
  int v13; // [rsp+58h] [rbp-A8h]
  _BYTE v14[120]; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+D8h] [rbp-28h]
  LPVOID v16[14]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR Buffer[264]; // [rsp+360h] [rbp+260h] BYREF
  WCHAR szVolumeName[264]; // [rsp+570h] [rbp+470h] BYREF

  v8 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
  v9 = L"IsBootVolume";
  v10 = L"VOLUMEC";
  v11 = 226;
  v12 = 11;
  v13 = 255;
  v15 = 0x1000000;
  memset_0(v14, 0, sizeof(v14));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v16, (__int64)&v8, 0);
  if ( !GetSystemDirectoryW(Buffer, 0x105u) || !GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
  {
LABEL_8:
    v2 = 0;
    goto LABEL_9;
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v8 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
    v9 = L"IsBootVolume";
    v10 = L"VOLUMEC";
    v11 = 238;
    v12 = 11;
    v13 = 255;
    v15 = 0x1000000;
    memset_0(v14, 0, sizeof(v14));
    v7 = v4;
    CVssFunctionTracer::Trace(
      v16,
      &v8,
      L"GetVolumeNameForVolumeMountPoint(%s) failed with 0x%08lx",
      szVolumePathName,
      v7);
    goto LABEL_8;
  }
  v2 = (unsigned int)_o__wcsicmp(szVolumeName, a1) == 0;
LABEL_9:
  v5 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v16, v2);
  CVssFunctionTracer::~CVssFunctionTracer(v16);
  return v5;
}

```

## disassembly

```asm
0x18004089c  mov     [rsp-8+arg_8], rbx
0x1800408a1  mov     [rsp-8+arg_10], rsi
0x1800408a6  push    rbp
0x1800408a7  push    r14
0x1800408a9  push    r15
0x1800408ab  lea     rbp, [rsp-690h]
0x1800408b3  sub     rsp, 790h
0x1800408ba  mov     rax, cs:__security_cookie
0x1800408c1  xor     rax, rsp
0x1800408c4  mov     [rbp+6A0h+var_20], rax
0x1800408cb  mov     rbx, rcx
0x1800408ce  lea     rsi, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\volume\\volum"...
0x1800408d5  mov     [rsp+7A0h+var_768], rsi
0x1800408da  lea     r14, aIsbootvolume; "IsBootVolume"
0x1800408e1  mov     [rsp+7A0h+var_760], r14
0x1800408e6  lea     r15, aVolumec; "VOLUMEC"
0x1800408ed  mov     [rsp+7A0h+var_758], r15
0x1800408f2  mov     [rsp+7A0h+var_750], 0E2h
0x1800408fa  mov     [rsp+7A0h+var_74C], 0Bh
0x180040902  mov     [rsp+7A0h+var_748], 0FFh
0x18004090a  mov     [rbp+6A0h+var_6C8], 1000000h
0x180040911  xor     edx, edx; Val
0x180040913  lea     r8d, [rdx+78h]; Size
0x180040917  lea     rcx, [rsp+7A0h+var_740]; void *
0x18004091c  call    memset_0
0x180040921  xor     r8d, r8d
0x180040924  lea     rdx, [rsp+7A0h+var_768]
0x180040929  lea     rcx, [rbp+6A0h+var_6C0]
0x18004092d  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180040932  nop
0x180040933  mov     edx, 105h; uSize
0x180040938  lea     rcx, [rbp+6A0h+Buffer]; lpBuffer
0x18004093f  call    cs:__imp_GetSystemDirectoryW
0x180040945  test    eax, eax
0x180040947  jz      loc_180040A0E
0x18004094d  mov     r8d, 104h; cchBufferLength
0x180040953  lea     rdx, [rbp+6A0h+szVolumePathName]; lpszVolumePathName
0x180040957  lea     rcx, [rbp+6A0h+Buffer]; lpszFileName
0x18004095e  call    cs:__imp_GetVolumePathNameW
0x180040964  test    eax, eax
0x180040966  jz      loc_180040A0E
0x18004096c  mov     r8d, 104h; cchBufferLength
0x180040972  lea     rdx, [rbp+6A0h+szVolumeName]; lpszVolumeName
0x180040979  lea     rcx, [rbp+6A0h+szVolumePathName]; lpszVolumeMountPoint
0x18004097d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180040983  test    eax, eax
0x180040985  jz      short loc_18004099E
0x180040987  mov     rdx, rbx
0x18004098a  lea     rcx, [rbp+6A0h+szVolumeName]
0x180040991  call    cs:__imp__o__wcsicmp
0x180040997  test    eax, eax
0x180040999  setz    dl
0x18004099c  jmp     short loc_180040A10
0x18004099e  call    cs:__imp_GetLastError
0x1800409a4  mov     ebx, eax
0x1800409a6  test    eax, eax
0x1800409a8  jle     short loc_1800409B3
0x1800409aa  movzx   ebx, ax
0x1800409ad  or      ebx, 80070000h
0x1800409b3  mov     [rsp+7A0h+var_768], rsi
0x1800409b8  mov     [rsp+7A0h+var_760], r14
0x1800409bd  mov     [rsp+7A0h+var_758], r15
0x1800409c2  mov     [rsp+7A0h+var_750], 0EEh
0x1800409ca  mov     [rsp+7A0h+var_74C], 0Bh
0x1800409d2  mov     [rsp+7A0h+var_748], 0FFh
0x1800409da  mov     [rbp+6A0h+var_6C8], 1000000h
0x1800409e1  xor     edx, edx; Val
0x1800409e3  lea     r8d, [rdx+78h]; Size
0x1800409e7  lea     rcx, [rsp+7A0h+var_740]; void *
0x1800409ec  call    memset_0
0x1800409f1  mov     [rsp+7A0h+var_780], ebx
0x1800409f5  lea     r9, [rbp+6A0h+szVolumePathName]
0x1800409f9  lea     r8, aGetvolumenamef_4; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x180040a00  lea     rdx, [rsp+7A0h+var_768]
0x180040a05  lea     rcx, [rbp+6A0h+var_6C0]
0x180040a09  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180040a0e  xor     edx, edx; bool
0x180040a10  lea     rcx, [rbp+6A0h+var_6C0]; this
0x180040a14  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x180040a19  mov     bl, al
0x180040a1b  lea     rcx, [rbp+6A0h+var_6C0]; this
0x180040a1f  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180040a24  mov     al, bl
0x180040a26  mov     rcx, [rbp+6A0h+var_20]
0x180040a2d  xor     rcx, rsp; StackCookie
0x180040a30  call    __security_check_cookie
0x180040a35  lea     r11, [rsp+7A0h+var_10]
0x180040a3d  mov     rbx, [r11+28h]
0x180040a41  mov     rsi, [r11+30h]
0x180040a45  mov     rsp, r11
0x180040a48  pop     r15
0x180040a4a  pop     r14
0x180040a4c  pop     rbp
0x180040a4d  retn
```
