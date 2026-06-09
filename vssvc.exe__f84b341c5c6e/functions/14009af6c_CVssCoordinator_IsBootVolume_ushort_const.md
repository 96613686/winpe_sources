# CVssCoordinator::IsBootVolume(ushort const *)

- ea: `0x14009af6c`
- end: `0x14009b11d`
- name: `?IsBootVolume@CVssCoordinator@@AEAA_NPEBG@Z`
- size: `433`
- prototype: `bool __fastcall(CVssCoordinator *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x14006f180`
- `0x14008aa50`

## callees

- `0x140011a90`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140091560`
- `0x1400921dc`
- `0x14009af6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14009b060`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14009b060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009b06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009b06d`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14009b02d`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14009b02d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14009b04c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14009b04c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14009b00e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14009b00e`

## string_xrefs

- `0x14009b0c8`: `GetVolumeNameForVolumeMountPoint(%s) failed with 0x%08lx`

## pseudocode

```c
bool __fastcall CVssCoordinator::IsBootVolume(CVssCoordinator *this, const unsigned __int16 *a2)
{
  bool v3; // dl
  signed int LastError; // eax
  unsigned int v5; // ebx
  bool v6; // bl
  unsigned int v8; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v9; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v10; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v11; // [rsp+40h] [rbp-C0h]
  int v12; // [rsp+48h] [rbp-B8h]
  int v13; // [rsp+4Ch] [rbp-B4h]
  int v14; // [rsp+50h] [rbp-B0h]
  _BYTE v15[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v16; // [rsp+D0h] [rbp-30h]
  LPVOID v17[14]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR Buffer[264]; // [rsp+360h] [rbp+260h] BYREF
  WCHAR szVolumeName[264]; // [rsp+570h] [rbp+470h] BYREF

  v12 = 2980;
  v13 = 1;
  v14 = 255;
  v9 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v10 = L"CVssCoordinator::IsBootVolume";
  v11 = L"CORCOORC";
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v17, (__int64)&v9, 0);
  if ( !GetSystemDirectoryW(Buffer, 0x105u) || !GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
  {
LABEL_8:
    v3 = 0;
    goto LABEL_9;
  }
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v9 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v10 = L"CVssCoordinator::IsBootVolume";
    v11 = L"CORCOORC";
    v12 = 2992;
    v13 = 1;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    v8 = v5;
    CVssFunctionTracer::Trace(
      v17,
      &v9,
      L"GetVolumeNameForVolumeMountPoint(%s) failed with 0x%08lx",
      szVolumePathName,
      v8);
    goto LABEL_8;
  }
  v3 = (unsigned int)_o__wcsicmp(szVolumeName, a2) == 0;
LABEL_9:
  v6 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v17, v3);
  CVssFunctionTracer::~CVssFunctionTracer(v17);
  return v6;
}

```

## disassembly

```asm
0x14009af6c  mov     [rsp-8+arg_0], rbx
0x14009af71  mov     [rsp-8+arg_10], r12
0x14009af76  push    rbp
0x14009af77  push    r14
0x14009af79  push    r15
0x14009af7b  lea     rbp, [rsp-690h]
0x14009af83  sub     rsp, 790h
0x14009af8a  mov     rax, cs:__security_cookie
0x14009af91  xor     rax, rsp
0x14009af94  mov     [rbp+6A0h+var_20], rax
0x14009af9b  mov     rbx, rdx
0x14009af9e  mov     [rsp+7A0h+var_758], 0BA4h
0x14009afa6  xor     edx, edx; Val
0x14009afa8  mov     [rsp+7A0h+var_754], 1
0x14009afb0  lea     r14, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14009afb7  mov     [rsp+7A0h+var_750], 0FFh
0x14009afbf  lea     r15, aCvsscoordinato_35; "CVssCoordinator::IsBootVolume"
0x14009afc6  mov     [rsp+7A0h+var_770], r14
0x14009afcb  lea     r12, aCorcoorc; "CORCOORC"
0x14009afd2  mov     [rsp+7A0h+var_768], r15
0x14009afd7  lea     r8d, [rdx+78h]; Size
0x14009afdb  mov     [rsp+7A0h+var_760], r12
0x14009afe0  lea     rcx, [rsp+7A0h+var_748]; void *
0x14009afe5  mov     [rbp+6A0h+var_6D0], 1000000h
0x14009afec  call    memset_0
0x14009aff1  xor     r8d, r8d
0x14009aff4  lea     rdx, [rsp+7A0h+var_770]
0x14009aff9  lea     rcx, [rbp+6A0h+var_6C0]
0x14009affd  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14009b002  mov     edx, 105h; uSize
0x14009b007  lea     rcx, [rbp+6A0h+Buffer]; lpBuffer
0x14009b00e  call    cs:__imp_GetSystemDirectoryW
0x14009b014  test    eax, eax
0x14009b016  jz      loc_14009B0DD
0x14009b01c  mov     r8d, 104h; cchBufferLength
0x14009b022  lea     rdx, [rbp+6A0h+szVolumePathName]; lpszVolumePathName
0x14009b026  lea     rcx, [rbp+6A0h+Buffer]; lpszFileName
0x14009b02d  call    cs:__imp_GetVolumePathNameW
0x14009b033  test    eax, eax
0x14009b035  jz      loc_14009B0DD
0x14009b03b  mov     r8d, 104h; cchBufferLength
0x14009b041  lea     rdx, [rbp+6A0h+szVolumeName]; lpszVolumeName
0x14009b048  lea     rcx, [rbp+6A0h+szVolumePathName]; lpszVolumeMountPoint
0x14009b04c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14009b052  test    eax, eax
0x14009b054  jz      short loc_14009B06D
0x14009b056  mov     rdx, rbx
0x14009b059  lea     rcx, [rbp+6A0h+szVolumeName]
0x14009b060  call    cs:__imp__o__wcsicmp
0x14009b066  test    eax, eax
0x14009b068  setz    dl
0x14009b06b  jmp     short loc_14009B0DF
0x14009b06d  call    cs:__imp_GetLastError
0x14009b073  mov     ebx, eax
0x14009b075  test    eax, eax
0x14009b077  jle     short loc_14009B082
0x14009b079  movzx   ebx, ax
0x14009b07c  or      ebx, 80070000h
0x14009b082  xor     edx, edx; Val
0x14009b084  mov     [rsp+7A0h+var_770], r14
0x14009b089  lea     rcx, [rsp+7A0h+var_748]; void *
0x14009b08e  mov     [rsp+7A0h+var_768], r15
0x14009b093  mov     [rsp+7A0h+var_760], r12
0x14009b098  mov     [rsp+7A0h+var_758], 0BB0h
0x14009b0a0  lea     r8d, [rdx+78h]; Size
0x14009b0a4  mov     [rsp+7A0h+var_754], 1
0x14009b0ac  mov     [rsp+7A0h+var_750], 0FFh
0x14009b0b4  mov     [rbp+6A0h+var_6D0], 1000000h
0x14009b0bb  call    memset_0
0x14009b0c0  lea     r9, [rbp+6A0h+szVolumePathName]
0x14009b0c4  mov     [rsp+7A0h+var_780], ebx
0x14009b0c8  lea     r8, aGetvolumenamef_13; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x14009b0cf  lea     rdx, [rsp+7A0h+var_770]
0x14009b0d4  lea     rcx, [rbp+6A0h+var_6C0]
0x14009b0d8  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14009b0dd  xor     edx, edx; bool
0x14009b0df  lea     rcx, [rbp+6A0h+var_6C0]; this
0x14009b0e3  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x14009b0e8  lea     rcx, [rbp+6A0h+var_6C0]; this
0x14009b0ec  mov     bl, al
0x14009b0ee  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14009b0f3  mov     al, bl
0x14009b0f5  mov     rcx, [rbp+6A0h+var_20]
0x14009b0fc  xor     rcx, rsp; StackCookie
0x14009b0ff  call    __security_check_cookie
0x14009b104  lea     r11, [rsp+7A0h+var_10]
0x14009b10c  mov     rbx, [r11+20h]
0x14009b110  mov     r12, [r11+30h]
0x14009b114  mov     rsp, r11
0x14009b117  pop     r15
0x14009b119  pop     r14
0x14009b11b  pop     rbp
0x14009b11c  retn
```
