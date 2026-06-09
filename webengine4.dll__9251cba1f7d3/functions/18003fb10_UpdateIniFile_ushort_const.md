# UpdateIniFile(ushort const *)

- ea: `0x18003fb10`
- end: `0x18003fd6e`
- name: `?UpdateIniFile@@YAXPEBG@Z`
- size: `606`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180039d9c`

## callees

- `0x18003fb10`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x1800653ba`
- `0x1800653c0`
- `0x1800653e6`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18003fbe1`
- `KERNEL32!ReadFile` at `0x18003fbe1`
- `KERNEL32!WriteFile` at `0x18003fd2d`
- `KERNEL32!WriteFile` at `0x18003fd2d`
- `KERNEL32!CloseHandle` at `0x18003fd3f`
- `KERNEL32!CloseHandle` at `0x18003fd3f`
- `KERNEL32!lstrlenW` at `0x18003fc11`
- `KERNEL32!lstrlenW` at `0x18003fcc4`
- `KERNEL32!lstrlenW` at `0x18003fcd0`
- `KERNEL32!lstrlenW` at `0x18003fcde`
- `KERNEL32!lstrlenW` at `0x18003fd15`
- `KERNEL32!lstrlenW` at `0x18003fc11`
- `KERNEL32!lstrlenW` at `0x18003fcc4`
- `KERNEL32!lstrlenW` at `0x18003fcd0`
- `KERNEL32!lstrlenW` at `0x18003fcde`
- `KERNEL32!lstrlenW` at `0x18003fd15`
- `KERNEL32!CreateFileW` at `0x18003fb60`
- `KERNEL32!CreateFileW` at `0x18003fb60`
- `KERNEL32!GetFileSize` at `0x18003fb81`
- `KERNEL32!GetFileSize` at `0x18003fb81`

## pseudocode

```c
void __fastcall UpdateIniFile(const unsigned __int16 *a1)
{
  HANDLE FileW; // rax
  void *v2; // rdi
  DWORD FileSize; // ebx
  __int64 v4; // rbx
  void *v5; // rax
  void *v6; // r14
  wchar_t *v7; // rbx
  int v8; // eax
  WCHAR *v9; // r8
  __int64 v10; // rdx
  wchar_t *v11; // rsi
  int v12; // r9d
  WCHAR v13; // cx
  WCHAR *v14; // rcx
  WCHAR v15; // ax
  WCHAR *v16; // rax
  int v17; // ebx
  int v18; // eax
  size_t v19; // rbx
  int v20; // eax
  DWORD FileSizeHigh; // [rsp+48h] [rbp-19h] BYREF
  WCHAR String[8]; // [rsp+50h] [rbp-11h] BYREF
  __int128 v23; // [rsp+60h] [rbp-1h]
  __int64 v24; // [rsp+70h] [rbp+Fh]
  WCHAR SubStr[8]; // [rsp+78h] [rbp+17h] BYREF
  __int128 v26; // [rsp+88h] [rbp+27h]
  __int64 v27; // [rsp+98h] [rbp+37h]

  FileW = CreateFileW(a1, 0xC0000000, 0, 0, 3u, 0x80u, 0);
  v2 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileSizeHigh = 0;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    if ( FileSize != -1 && !FileSizeHigh )
    {
      v4 = (FileSize >> 1) + 1;
      v5 = MemAlloc(saturated_mul((unsigned int)v4, 2u));
      v6 = v5;
      if ( v5 )
      {
        memset_0(v5, 0, 2 * v4);
        if ( !ReadFile(v2, v6, 2 * v4, 0, 0) )
          goto LABEL_24;
        v7 = wcsstr_0((const wchar_t *)v6, L"drivername=ASP.NET_");
        if ( v7 )
        {
          v8 = lstrlenW(L"drivername=ASP.NET_");
          v9 = SubStr;
          v27 = 0;
          v24 = 0;
          v10 = 20;
          v11 = &v7[v8];
          v12 = 0;
          *(_OWORD *)SubStr = 0;
          v26 = 0;
          *(_OWORD *)String = 0;
          v23 = 0;
          do
          {
            v13 = *(WCHAR *)((char *)v9 + (char *)&v7[v8] - (char *)SubStr);
            if ( !v13 )
              break;
            if ( v13 == 46 || (unsigned __int16)(v13 - 48) <= 9u )
              *v9 = v13;
            ++v12;
            ++v9;
          }
          while ( v12 < 20 );
          v14 = String;
          do
          {
            if ( v10 == -2147483626 )
              break;
            v15 = *(WCHAR *)((char *)v14 + (char *)L"4.0.30319" - (char *)String);
            if ( !v15 )
              break;
            *v14++ = v15;
            --v10;
          }
          while ( v10 );
          v16 = v14 - 1;
          if ( v10 )
            v16 = v14;
          *v16 = 0;
          v17 = lstrlenW(String);
          if ( lstrlenW(SubStr) == v17 )
          {
            v18 = lstrlenW(String);
            if ( v11 )
            {
              v19 = 2LL * v18;
              do
              {
                memcpy_0(v11, String, v19);
                v11 = wcsstr_0(v11, SubStr);
              }
              while ( v11 );
            }
            v20 = lstrlenW((LPCWSTR)v6);
            if ( !WriteFile(v2, v6, 2 * v20, 0, 0) )
LABEL_24:
              GetLastWin32Error();
          }
        }
      }
    }
    CloseHandle(v2);
  }
}

```

## disassembly

```asm
0x18003fb10  mov     rax, rsp
0x18003fb13  mov     [rax+10h], rbx
0x18003fb17  mov     [rax+18h], rsi
0x18003fb1b  mov     [rax+20h], rdi
0x18003fb1f  push    rbp
0x18003fb20  push    r14
0x18003fb22  push    r15
0x18003fb24  lea     rbp, [rax-5Fh]
0x18003fb28  sub     rsp, 0A0h
0x18003fb2f  mov     rax, cs:__security_cookie
0x18003fb36  xor     rax, rsp
0x18003fb39  mov     [rbp+57h+var_18], rax
0x18003fb3d  xor     r15d, r15d
0x18003fb40  xor     r9d, r9d; lpSecurityAttributes
0x18003fb43  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x18003fb48  xor     r8d, r8d; dwShareMode
0x18003fb4b  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003fb53  mov     edx, 0C0000000h; dwDesiredAccess
0x18003fb58  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003fb60  call    cs:__imp_CreateFileW
0x18003fb66  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003fb6a  mov     rdi, rax
0x18003fb6d  cmp     rax, r14
0x18003fb70  jz      loc_18003FD45
0x18003fb76  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x18003fb7a  mov     [rbp+57h+FileSizeHigh], r15d
0x18003fb7e  mov     rcx, rax; hFile
0x18003fb81  call    cs:__imp_GetFileSize
0x18003fb87  mov     ebx, eax
0x18003fb89  cmp     eax, 0FFFFFFFFh
0x18003fb8c  jz      loc_18003FD3C
0x18003fb92  cmp     [rbp+57h+FileSizeHigh], r15d
0x18003fb96  ja      loc_18003FD3C
0x18003fb9c  shr     ebx, 1
0x18003fb9e  lea     eax, [r15+2]
0x18003fba2  inc     ebx
0x18003fba4  mov     esi, ebx
0x18003fba6  mul     rsi
0x18003fba9  cmovo   rax, r14
0x18003fbad  mov     rcx, rax; unsigned __int64
0x18003fbb0  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18003fbb5  mov     r14, rax
0x18003fbb8  test    rax, rax
0x18003fbbb  jz      loc_18003FD3C
0x18003fbc1  lea     r8, [rbx+rbx]; Size
0x18003fbc5  xor     edx, edx; Val
0x18003fbc7  mov     rcx, rax; void *
0x18003fbca  call    memset_0
0x18003fbcf  lea     r8d, [rbx+rbx]; nNumberOfBytesToRead
0x18003fbd3  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r15; lpOverlapped
0x18003fbd8  xor     r9d, r9d; lpNumberOfBytesRead
0x18003fbdb  mov     rdx, r14; lpBuffer
0x18003fbde  mov     rcx, rdi; hFile
0x18003fbe1  call    cs:__imp_ReadFile
0x18003fbe7  test    eax, eax
0x18003fbe9  jz      loc_18003FD37
0x18003fbef  lea     rdx, aDrivernameAspN; "drivername=ASP.NET_"
0x18003fbf6  mov     rcx, r14; Str
0x18003fbf9  call    wcsstr_0
0x18003fbfe  mov     rbx, rax
0x18003fc01  test    rax, rax
0x18003fc04  jz      loc_18003FD3C
0x18003fc0a  lea     rcx, aDrivernameAspN; "drivername=ASP.NET_"
0x18003fc11  call    cs:__imp_lstrlenW
0x18003fc17  movsxd  rcx, eax
0x18003fc1a  xorps   xmm0, xmm0
0x18003fc1d  xor     eax, eax
0x18003fc1f  lea     r8, [rbp+57h+SubStr]
0x18003fc23  xorps   xmm1, xmm1
0x18003fc26  mov     [rbp+57h+var_20], rax
0x18003fc2a  mov     [rbp+57h+var_48], rax
0x18003fc2e  lea     edx, [r15+14h]
0x18003fc32  lea     rsi, [rbx+rcx*2]
0x18003fc36  mov     r9d, r15d
0x18003fc39  mov     r10, rsi
0x18003fc3c  lea     rax, [rbp+57h+SubStr]
0x18003fc40  sub     r10, rax
0x18003fc43  movups  xmmword ptr [rbp+57h+SubStr], xmm0
0x18003fc47  movups  [rbp+57h+var_30], xmm0
0x18003fc4b  movups  xmmword ptr [rbp+57h+String], xmm1
0x18003fc4f  movups  [rbp+57h+var_58], xmm1
0x18003fc53  movzx   ecx, word ptr [r10+r8]
0x18003fc58  test    cx, cx
0x18003fc5b  jz      short loc_18003FC7C
0x18003fc5d  cmp     cx, 2Eh ; '.'
0x18003fc61  jz      short loc_18003FC6C
0x18003fc63  lea     eax, [rcx-30h]
0x18003fc66  cmp     ax, 9
0x18003fc6a  ja      short loc_18003FC70
0x18003fc6c  mov     [r8], cx
0x18003fc70  inc     r9d
0x18003fc73  add     r8, 2
0x18003fc77  cmp     r9d, edx
0x18003fc7a  jl      short loc_18003FC53
0x18003fc7c  lea     r8, a4030319; "4.0.30319"
0x18003fc83  lea     rax, [rbp+57h+String]
0x18003fc87  sub     r8, rax
0x18003fc8a  lea     rcx, [rbp+57h+String]
0x18003fc8e  lea     rax, [rdx+7FFFFFEAh]
0x18003fc95  test    rax, rax
0x18003fc98  jz      short loc_18003FCB1
0x18003fc9a  movzx   eax, word ptr [r8+rcx]
0x18003fc9f  test    ax, ax
0x18003fca2  jz      short loc_18003FCB1
0x18003fca4  mov     [rcx], ax
0x18003fca7  add     rcx, 2
0x18003fcab  sub     rdx, 1
0x18003fcaf  jnz     short loc_18003FC8E
0x18003fcb1  lea     rax, [rcx-2]
0x18003fcb5  test    rdx, rdx
0x18003fcb8  cmovnz  rax, rcx
0x18003fcbc  lea     rcx, [rbp+57h+String]; lpString
0x18003fcc0  mov     [rax], r15w
0x18003fcc4  call    cs:__imp_lstrlenW
0x18003fcca  lea     rcx, [rbp+57h+SubStr]; lpString
0x18003fcce  mov     ebx, eax
0x18003fcd0  call    cs:__imp_lstrlenW
0x18003fcd6  cmp     eax, ebx
0x18003fcd8  jnz     short loc_18003FD3C
0x18003fcda  lea     rcx, [rbp+57h+String]; lpString
0x18003fcde  call    cs:__imp_lstrlenW
0x18003fce4  test    rsi, rsi
0x18003fce7  jz      short loc_18003FD12
0x18003fce9  movsxd  rbx, eax
0x18003fcec  add     rbx, rbx
0x18003fcef  mov     r8, rbx; Size
0x18003fcf2  lea     rdx, [rbp+57h+String]; Src
0x18003fcf6  mov     rcx, rsi; void *
0x18003fcf9  call    memcpy_0
0x18003fcfe  lea     rdx, [rbp+57h+SubStr]; SubStr
0x18003fd02  mov     rcx, rsi; Str
0x18003fd05  call    wcsstr_0
0x18003fd0a  mov     rsi, rax
0x18003fd0d  test    rax, rax
0x18003fd10  jnz     short loc_18003FCEF
0x18003fd12  mov     rcx, r14; lpString
0x18003fd15  call    cs:__imp_lstrlenW
0x18003fd1b  xor     r9d, r9d; lpNumberOfBytesWritten
0x18003fd1e  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r15; lpOverlapped
0x18003fd23  mov     rdx, r14; lpBuffer
0x18003fd26  mov     rcx, rdi; hFile
0x18003fd29  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x18003fd2d  call    cs:__imp_WriteFile
0x18003fd33  test    eax, eax
0x18003fd35  jnz     short loc_18003FD3C
0x18003fd37  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003fd3c  mov     rcx, rdi; hObject
0x18003fd3f  call    cs:__imp_CloseHandle
0x18003fd45  mov     rcx, [rbp+57h+var_18]
0x18003fd49  xor     rcx, rsp; StackCookie
0x18003fd4c  call    __security_check_cookie
0x18003fd51  lea     r11, [rsp+0B0h+var_10]
0x18003fd59  mov     rbx, [r11+28h]
0x18003fd5d  mov     rsi, [r11+30h]
0x18003fd61  mov     rdi, [r11+38h]
0x18003fd65  mov     rsp, r11
0x18003fd68  pop     r15
0x18003fd6a  pop     r14
0x18003fd6c  pop     rbp
0x18003fd6d  retn
```
