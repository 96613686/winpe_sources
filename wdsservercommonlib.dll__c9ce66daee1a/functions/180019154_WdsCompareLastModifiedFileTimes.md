# WdsCompareLastModifiedFileTimes

- ea: `0x180019154`
- end: `0x1800192f0`
- name: `WdsCompareLastModifiedFileTimes`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ac00`

## callees

- `0x180019154`
- `0x18001a28c`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x1800192a4`
- `KERNEL32!CompareFileTime` at `0x1800192a4`
- `KERNEL32!GetLastError` at `0x1800191ac`
- `KERNEL32!GetLastError` at `0x180019210`
- `KERNEL32!GetLastError` at `0x180019255`
- `KERNEL32!GetLastError` at `0x180019286`
- `KERNEL32!GetLastError` at `0x1800191ac`
- `KERNEL32!GetLastError` at `0x180019210`
- `KERNEL32!GetLastError` at `0x180019255`
- `KERNEL32!GetLastError` at `0x180019286`
- `KERNEL32!CloseHandle` at `0x1800192b6`
- `KERNEL32!CloseHandle` at `0x1800192cb`
- `KERNEL32!CloseHandle` at `0x1800192b6`
- `KERNEL32!CloseHandle` at `0x1800192cb`
- `KERNEL32!CreateFileW` at `0x180019197`
- `KERNEL32!CreateFileW` at `0x1800191fb`
- `KERNEL32!CreateFileW` at `0x180019197`
- `KERNEL32!CreateFileW` at `0x1800191fb`
- `KERNEL32!GetFileTime` at `0x180019245`
- `KERNEL32!GetFileTime` at `0x180019276`
- `KERNEL32!GetFileTime` at `0x180019245`
- `KERNEL32!GetFileTime` at `0x180019276`

## pseudocode

```c
__int64 __fastcall WdsCompareLastModifiedFileTimes(const WCHAR *a1, const WCHAR *a2, LONG *a3)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rsi
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  HANDLE v10; // rdi
  DWORD v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  struct _FILETIME LastWriteTime; // [rsp+40h] [rbp-18h] BYREF
  FILETIME FileTime2; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  LastWriteTime = 0;
  FileTime2 = 0;
  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = ElValidateWin32_8(LastError, v8, v9, 3074);
    if ( !v3 )
      return 31;
    return v3;
  }
  v10 = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( v10 == (HANDLE)-1LL )
  {
    v11 = GetLastError();
    v14 = 3089;
    goto LABEL_6;
  }
  if ( !GetFileTime(FileW, 0, 0, &LastWriteTime) )
  {
    v11 = GetLastError();
    v14 = 3100;
    goto LABEL_6;
  }
  if ( !GetFileTime(v10, 0, 0, &FileTime2) )
  {
    v11 = GetLastError();
    v14 = 3108;
LABEL_6:
    v3 = ElValidateWin32_8(v11, v12, v13, v14);
    if ( !v3 )
      v3 = 31;
    goto LABEL_13;
  }
  *a3 = CompareFileTime(&LastWriteTime, &FileTime2);
LABEL_13:
  CloseHandle(FileW);
  if ( v10 != (HANDLE)-1LL )
    CloseHandle(v10);
  return v3;
}

```

## disassembly

```asm
0x180019154  mov     rax, rsp
0x180019157  mov     [rax+8], rbx
0x18001915b  mov     [rax+10h], rsi
0x18001915f  mov     [rax+18h], rdi
0x180019163  push    r14
0x180019165  sub     rsp, 50h
0x180019169  xor     ebx, ebx
0x18001916b  mov     r14, r8
0x18001916e  and     [rax-28h], rbx
0x180019172  mov     rdi, rdx
0x180019175  and     [rax-18h], rbx
0x180019179  xor     r9d, r9d; lpSecurityAttributes
0x18001917c  and     [rax+20h], rbx
0x180019180  mov     edx, 80000000h; dwDesiredAccess
0x180019185  mov     dword ptr [rax-30h], 80h
0x18001918c  lea     r8d, [rbx+7]; dwShareMode
0x180019190  mov     dword ptr [rax-38h], 3
0x180019197  call    cs:__imp_CreateFileW
0x18001919e  nop     dword ptr [rax+rax+00h]
0x1800191a3  mov     rsi, rax
0x1800191a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800191aa  jnz     short loc_1800191D7
0x1800191ac  call    cs:__imp_GetLastError
0x1800191b3  nop     dword ptr [rax+rax+00h]
0x1800191b8  mov     ecx, eax
0x1800191ba  mov     r9d, 0C02h
0x1800191c0  call    ElValidateWin32_8
0x1800191c5  mov     ebx, eax
0x1800191c7  test    eax, eax
0x1800191c9  jnz     loc_1800192D7
0x1800191cf  lea     ebx, [rsi+20h]
0x1800191d2  jmp     loc_1800192D7
0x1800191d7  and     [rsp+58h+var_28], rbx
0x1800191dc  xor     r9d, r9d; lpSecurityAttributes
0x1800191df  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800191e7  mov     edx, 80000000h; dwDesiredAccess
0x1800191ec  mov     rcx, rdi; lpFileName
0x1800191ef  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800191f7  lea     r8d, [r9+7]; dwShareMode
0x1800191fb  call    cs:__imp_CreateFileW
0x180019202  nop     dword ptr [rax+rax+00h]
0x180019207  mov     rdi, rax
0x18001920a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001920e  jnz     short loc_180019238
0x180019210  call    cs:__imp_GetLastError
0x180019217  nop     dword ptr [rax+rax+00h]
0x18001921c  mov     r9d, 0C11h
0x180019222  mov     ecx, eax
0x180019224  call    ElValidateWin32_8
0x180019229  mov     ebx, eax
0x18001922b  test    eax, eax
0x18001922d  jnz     loc_1800192B3
0x180019233  lea     ebx, [rax+1Fh]
0x180019236  jmp     short loc_1800192B3
0x180019238  lea     r9, [rsp+58h+LastWriteTime]; lpLastWriteTime
0x18001923d  xor     r8d, r8d; lpLastAccessTime
0x180019240  xor     edx, edx; lpCreationTime
0x180019242  mov     rcx, rsi; hFile
0x180019245  call    cs:__imp_GetFileTime
0x18001924c  nop     dword ptr [rax+rax+00h]
0x180019251  test    eax, eax
0x180019253  jnz     short loc_180019269
0x180019255  call    cs:__imp_GetLastError
0x18001925c  nop     dword ptr [rax+rax+00h]
0x180019261  mov     r9d, 0C1Ch
0x180019267  jmp     short loc_180019222
0x180019269  lea     r9, [rsp+58h+FileTime2]; lpLastWriteTime
0x18001926e  xor     r8d, r8d; lpLastAccessTime
0x180019271  xor     edx, edx; lpCreationTime
0x180019273  mov     rcx, rdi; hFile
0x180019276  call    cs:__imp_GetFileTime
0x18001927d  nop     dword ptr [rax+rax+00h]
0x180019282  test    eax, eax
0x180019284  jnz     short loc_18001929A
0x180019286  call    cs:__imp_GetLastError
0x18001928d  nop     dword ptr [rax+rax+00h]
0x180019292  mov     r9d, 0C24h
0x180019298  jmp     short loc_180019222
0x18001929a  lea     rdx, [rsp+58h+FileTime2]; lpFileTime2
0x18001929f  lea     rcx, [rsp+58h+LastWriteTime]; lpFileTime1
0x1800192a4  call    cs:__imp_CompareFileTime
0x1800192ab  nop     dword ptr [rax+rax+00h]
0x1800192b0  mov     [r14], eax
0x1800192b3  mov     rcx, rsi; hObject
0x1800192b6  call    cs:__imp_CloseHandle
0x1800192bd  nop     dword ptr [rax+rax+00h]
0x1800192c2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800192c6  jz      short loc_1800192D7
0x1800192c8  mov     rcx, rdi; hObject
0x1800192cb  call    cs:__imp_CloseHandle
0x1800192d2  nop     dword ptr [rax+rax+00h]
0x1800192d7  mov     rsi, [rsp+58h+arg_8]
0x1800192dc  mov     eax, ebx
0x1800192de  mov     rbx, [rsp+58h+arg_0]
0x1800192e3  mov     rdi, [rsp+58h+arg_10]
0x1800192e8  add     rsp, 50h
0x1800192ec  pop     r14
0x1800192ee  retn
```
