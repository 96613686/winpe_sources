# ScBackupTraceFile(ushort const *,ushort const *)

- ea: `0x140086e24`
- end: `0x14008706a`
- name: `?ScBackupTraceFile@@YAXPEBG0@Z`
- size: `582`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140031618`
- `0x140087070`

## callees

- `0x140008b90`
- `0x14001df34`
- `0x14004b4fc`
- `0x14004be40`
- `0x1400575b0`
- `0x140086e24`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087029`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087029`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140086eb7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140087038`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140086eb7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140087038`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140086f1d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140086f1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140086fe9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140086fe9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140086ea4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140086ef7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140086ea4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140086ef7`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140087020`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140087020`

## pseudocode

```c
void __fastcall ScBackupTraceFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HANDLE FirstFileW; // rax
  unsigned int v4; // r11d
  HANDLE v5; // r14
  int v6; // esi
  FILETIME ftLastWriteTime; // rbx
  int v8; // r12d
  int v9; // r15d
  unsigned int v10; // eax
  HANDLE FileW; // rax
  void *v12; // rbx
  wchar_t Buffer[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD FileInformation[70]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  *(_DWORD *)Buffer = 0;
  memset(FileInformation, 0, 0x224u);
  memset(FileName, 0, 0x20Cu);
  memset(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a1, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    FindClose(FirstFileW);
    StringCchCopyW(FileName, 0x106u, a1);
    StringCchCatW(FileName, v4, L".*");
    v5 = FindFirstFileW(FileName, &FindFileData);
    v6 = 1;
    if ( v5 != (HANDLE)-1LL )
    {
      ftLastWriteTime = (FILETIME)-1LL;
      v8 = 1;
      v9 = 0;
      while ( FindNextFileW(v5, &FindFileData) )
      {
        if ( (unsigned int)++v9 > 0x32 )
        {
          v6 = 5;
          break;
        }
        v10 = wcstoul(&FindFileData.cFileName[8], 0, 10);
        if ( v10 - 1 <= 4 )
        {
          if ( *(_QWORD *)&FindFileData.ftLastWriteTime < *(unsigned __int64 *)&ftLastWriteTime )
          {
            ftLastWriteTime = FindFileData.ftLastWriteTime;
            v8 = v10;
          }
          if ( v10 == 5 )
          {
            v6 = v8;
            break;
          }
          if ( v6 != v10 )
            break;
          ++v6;
        }
      }
    }
    ltow_s(v6, Buffer, 2u, 10);
    StringCchCopyW((unsigned __int16 *)&FileInformation[2] + 2, 0x106u, a1);
    StringCchCatW((unsigned __int16 *)&FileInformation[2] + 2, 0x104u, L".");
    StringCchCatW((unsigned __int16 *)&FileInformation[2] + 2, 0x104u, Buffer);
    FileW = CreateFileW(a1, 0x40010000u, 0, 0, 3u, 0, 0);
    v12 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      LOBYTE(FileInformation[0]) = 1;
      FileInformation[1] = 0;
      LODWORD(FileInformation[2]) = 260;
      SetFileInformationByHandle(FileW, FileRenameInfo, FileInformation, 0x224u);
      CloseHandle(v12);
    }
    if ( v5 != (HANDLE)-1LL )
      FindClose(v5);
  }
}

```

## disassembly

```asm
0x140086e24  mov     [rsp-8+arg_8], rbx
0x140086e29  mov     [rsp-8+arg_10], rsi
0x140086e2e  push    rbp
0x140086e2f  push    r12
0x140086e31  push    r13
0x140086e33  push    r14
0x140086e35  push    r15
0x140086e37  lea     rbp, [rsp-5F0h]
0x140086e3f  sub     rsp, 6F0h
0x140086e46  mov     rax, cs:__security_cookie
0x140086e4d  xor     rax, rsp
0x140086e50  mov     [rbp+610h+var_30], rax
0x140086e57  mov     r13, rcx
0x140086e5a  mov     dword ptr [rsp+710h+Buffer], 0
0x140086e62  lea     rcx, [rbp+610h+FileInformation]; void *
0x140086e69  xor     edx, edx; Val
0x140086e6b  mov     r8d, 224h; Size
0x140086e71  call    memset
0x140086e76  xor     edx, edx; Val
0x140086e78  lea     rcx, [rbp+610h+FileName]; void *
0x140086e7f  mov     r8d, 20Ch; Size
0x140086e85  call    memset
0x140086e8a  xor     edx, edx; Val
0x140086e8c  lea     rcx, [rsp+710h+FindFileData]; void *
0x140086e91  mov     r8d, 250h; Size
0x140086e97  call    memset
0x140086e9c  lea     rdx, [rsp+710h+FindFileData]; lpFindFileData
0x140086ea1  mov     rcx, r13; lpFileName
0x140086ea4  call    cs:__imp_FindFirstFileW
0x140086eaa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140086eae  jz      loc_14008703E
0x140086eb4  mov     rcx, rax; hFindFile
0x140086eb7  call    cs:__imp_FindClose
0x140086ebd  mov     r11d, 106h
0x140086ec3  lea     rcx, [rbp+610h+FileName]; unsigned __int16 *
0x140086eca  mov     edx, r11d; unsigned __int64
0x140086ecd  mov     r8, r13; unsigned __int16 *
0x140086ed0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140086ed5  lea     r8, asc_1400A8548; ".*"
0x140086edc  mov     edx, r11d; unsigned __int64
0x140086edf  lea     rcx, [rbp+610h+FileName]; unsigned __int16 *
0x140086ee6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140086eeb  lea     rdx, [rsp+710h+FindFileData]; lpFindFileData
0x140086ef0  lea     rcx, [rbp+610h+FileName]; lpFileName
0x140086ef7  call    cs:__imp_FindFirstFileW
0x140086efd  mov     r14, rax
0x140086f00  mov     esi, 1
0x140086f05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140086f09  jz      short loc_140086F6D
0x140086f0b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140086f0f  mov     r12d, esi
0x140086f12  xor     r15d, r15d
0x140086f15  lea     rdx, [rsp+710h+FindFileData]; lpFindFileData
0x140086f1a  mov     rcx, r14; hFindFile
0x140086f1d  call    cs:__imp_FindNextFileW
0x140086f23  test    eax, eax
0x140086f25  jz      short loc_140086F6D
0x140086f27  inc     r15d
0x140086f2a  cmp     r15d, 32h ; '2'
0x140086f2e  ja      short loc_140086F68
0x140086f30  xor     edx, edx; EndPtr
0x140086f32  lea     rcx, [rbp+610h+FindFileData.cFileName+10h]; String
0x140086f36  lea     r8d, [rdx+0Ah]; Radix
0x140086f3a  call    wcstoul
0x140086f3f  lea     ecx, [rax-1]
0x140086f42  cmp     ecx, 4
0x140086f45  ja      short loc_140086F15
0x140086f47  cmp     qword ptr [rsp+710h+FindFileData.ftLastWriteTime.dwLowDateTime], rbx
0x140086f4c  jnb     short loc_140086F56
0x140086f4e  mov     rbx, qword ptr [rsp+710h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x140086f53  mov     r12d, eax
0x140086f56  cmp     eax, 5
0x140086f59  jz      short loc_140086F63
0x140086f5b  cmp     esi, eax
0x140086f5d  jnz     short loc_140086F6D
0x140086f5f  inc     esi
0x140086f61  jmp     short loc_140086F15
0x140086f63  mov     esi, r12d
0x140086f66  jmp     short loc_140086F6D
0x140086f68  mov     esi, 5
0x140086f6d  mov     r9d, 0Ah; Radix
0x140086f73  lea     rdx, [rsp+710h+Buffer]; Buffer
0x140086f78  mov     ecx, esi; Value
0x140086f7a  lea     r8d, [r9-8]; BufferCount
0x140086f7e  call    _ltow_s
0x140086f83  mov     r8, r13; unsigned __int16 *
0x140086f86  lea     rcx, [rbp+610h+var_45C]; unsigned __int16 *
0x140086f8d  mov     edx, 106h; unsigned __int64
0x140086f92  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140086f97  mov     r15d, 104h
0x140086f9d  lea     r8, asc_1400A65F4; "."
0x140086fa4  mov     edx, r15d; unsigned __int64
0x140086fa7  lea     rcx, [rbp+610h+var_45C]; unsigned __int16 *
0x140086fae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140086fb3  lea     r8, [rsp+710h+Buffer]; unsigned __int16 *
0x140086fb8  mov     edx, r15d; unsigned __int64
0x140086fbb  lea     rcx, [rbp+610h+var_45C]; unsigned __int16 *
0x140086fc2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140086fc7  xor     esi, esi
0x140086fc9  xor     r9d, r9d; lpSecurityAttributes
0x140086fcc  mov     [rsp+710h+hTemplateFile], rsi; hTemplateFile
0x140086fd1  xor     r8d, r8d; dwShareMode
0x140086fd4  mov     [rsp+710h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x140086fd8  mov     edx, 40010000h; dwDesiredAccess
0x140086fdd  mov     rcx, r13; lpFileName
0x140086fe0  lea     r12d, [rsi+3]
0x140086fe4  mov     [rsp+710h+dwCreationDisposition], r12d; dwCreationDisposition
0x140086fe9  call    cs:__imp_CreateFileW
0x140086fef  mov     rbx, rax
0x140086ff2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140086ff6  jz      short loc_14008702F
0x140086ff8  mov     r9d, 224h; dwBufferSize
0x140086ffe  mov     [rbp+610h+FileInformation], 1
0x140087005  lea     r8, [rbp+610h+FileInformation]; lpFileInformation
0x14008700c  mov     [rbp+610h+var_468], rsi
0x140087013  mov     edx, r12d; FileInformationClass
0x140087016  mov     [rbp+610h+var_460], r15d
0x14008701d  mov     rcx, rax; hFile
0x140087020  call    cs:__imp_SetFileInformationByHandle
0x140087026  mov     rcx, rbx; hObject
0x140087029  call    cs:__imp_CloseHandle
0x14008702f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140087033  jz      short loc_14008703E
0x140087035  mov     rcx, r14; hFindFile
0x140087038  call    cs:__imp_FindClose
0x14008703e  mov     rcx, [rbp+610h+var_30]
0x140087045  xor     rcx, rsp; StackCookie
0x140087048  call    __security_check_cookie
0x14008704d  lea     r11, [rsp+710h+var_20]
0x140087055  mov     rbx, [r11+38h]
0x140087059  mov     rsi, [r11+40h]
0x14008705d  mov     rsp, r11
0x140087060  pop     r15
0x140087062  pop     r14
0x140087064  pop     r13
0x140087066  pop     r12
0x140087068  pop     rbp
0x140087069  retn
```
