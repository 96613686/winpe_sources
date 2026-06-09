# SADatCreate(ushort const *,int)

- ea: `0x1800177d4`
- end: `0x180017951`
- name: `?SADatCreate@@YAJPEBGH@Z`
- size: `381`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800063b0`

## callees

- `0x180017724`
- `0x1800177d4`
- `0x180017b00`
- `0x180017b60`
- `0x180017bcc`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001791e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001791e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800178cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800178cb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001789e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001789e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180017828`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180017828`

## pseudocode

```c
signed int __fastcall SADatCreate(const unsigned __int16 *a1)
{
  signed int result; // eax
  unsigned __int64 v3; // r8
  HANDLE FileW; // rax
  void *v5; // rdi
  unsigned int v6; // edx
  int v7; // ebx
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v9[4]; // [rsp+160h] [rbp+60h] BYREF
  char v10; // [rsp+164h] [rbp+64h]
  char v11; // [rsp+165h] [rbp+65h]
  WCHAR FileName[264]; // [rsp+170h] [rbp+70h] BYREF

  *(_DWORD *)v9 = 6;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( !GetVersionExW(&VersionInformation)
    || (v10 = (VersionInformation.dwPlatformId == 2) + 1,
        v11 = (unsigned int)ResumeTimersSupported() != 0 ? 3 : 1,
        memset_0(FileName, 0, 0x20Au),
        SADatPath(a1, FileName, v3),
        SetFileAttributesW(FileName, 2u),
        FileW = CreateFileW(FileName, 0xC0040000, 3u, 0, 2u, 2u, 0),
        v5 = FileW,
        FileW == (HANDLE)-1LL) )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v7 = SADatSetSecurity(FileW);
    if ( v7 )
    {
      CloseHandle(v5);
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      v7 = SADatSetData(v5, v6, v9);
      CloseHandle(v5);
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800177d4  mov     [rsp-8+arg_8], rbx
0x1800177d9  mov     [rsp-8+arg_10], rdi
0x1800177de  push    rbp
0x1800177df  lea     rbp, [rsp-290h]
0x1800177e7  sub     rsp, 390h
0x1800177ee  mov     rax, cs:__security_cookie
0x1800177f5  xor     rax, rsp
0x1800177f8  mov     [rbp+290h+var_10], rax
0x1800177ff  mov     rbx, rcx
0x180017802  mov     dword ptr [rbp+290h+var_230], 6
0x180017809  lea     rcx, [rsp+390h+VersionInformation.dwMajorVersion]; void *
0x18001780e  xor     edx, edx; Val
0x180017810  mov     r8d, 110h; Size
0x180017816  call    memset_0
0x18001781b  lea     rcx, [rsp+390h+VersionInformation]; lpVersionInformation
0x180017820  mov     [rsp+390h+VersionInformation.dwOSVersionInfoSize], 114h
0x180017828  call    cs:__imp_GetVersionExW
0x18001782f  nop     dword ptr [rax+rax+00h]
0x180017834  test    eax, eax
0x180017836  jnz     short loc_180017859
0x180017838  call    cs:__imp_GetLastError
0x18001783f  nop     dword ptr [rax+rax+00h]
0x180017844  test    eax, eax
0x180017846  jle     loc_18001792C
0x18001784c  movzx   eax, ax
0x18001784f  or      eax, 80070000h
0x180017854  jmp     loc_18001792C
0x180017859  mov     edi, 2
0x18001785e  cmp     [rsp+390h+VersionInformation.dwPlatformId], edi
0x180017862  setz    al
0x180017865  inc     al
0x180017867  mov     [rbp+290h+var_22C], al
0x18001786a  call    ?ResumeTimersSupported@@YAHXZ; ResumeTimersSupported(void)
0x18001786f  neg     eax
0x180017871  lea     rcx, [rbp+290h+FileName]; void *
0x180017875  mov     r8d, 20Ah; Size
0x18001787b  sbb     dl, dl
0x18001787d  and     dl, dil
0x180017880  inc     dl
0x180017882  mov     [rbp+290h+var_22B], dl
0x180017885  xor     edx, edx; Val
0x180017887  call    memset_0
0x18001788c  lea     rdx, [rbp+290h+FileName]; unsigned __int16 *
0x180017890  mov     rcx, rbx; unsigned __int16 *
0x180017893  call    ?SADatPath@@YAXPEBGPEAG_K@Z; SADatPath(ushort const *,ushort *,unsigned __int64)
0x180017898  mov     edx, edi; dwFileAttributes
0x18001789a  lea     rcx, [rbp+290h+FileName]; lpFileName
0x18001789e  call    cs:__imp_SetFileAttributesW
0x1800178a5  nop     dword ptr [rax+rax+00h]
0x1800178aa  mov     [rsp+390h+hTemplateFile], 0; hTemplateFile
0x1800178b3  lea     r8d, [rdi+1]; dwShareMode
0x1800178b7  mov     [rsp+390h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800178bb  lea     rcx, [rbp+290h+FileName]; lpFileName
0x1800178bf  xor     r9d, r9d; lpSecurityAttributes
0x1800178c2  mov     [rsp+390h+dwCreationDisposition], edi; dwCreationDisposition
0x1800178c6  mov     edx, 0C0040000h; dwDesiredAccess
0x1800178cb  call    cs:__imp_CreateFileW
0x1800178d2  nop     dword ptr [rax+rax+00h]
0x1800178d7  mov     rdi, rax
0x1800178da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800178de  jz      loc_180017838
0x1800178e4  mov     rcx, rax; handle
0x1800178e7  call    ?SADatSetSecurity@@YAKPEAX@Z; SADatSetSecurity(void *)
0x1800178ec  mov     ebx, eax
0x1800178ee  mov     rcx, rdi; void *
0x1800178f1  test    eax, eax
0x1800178f3  jz      short loc_180017910
0x1800178f5  call    cs:__imp_CloseHandle
0x1800178fc  nop     dword ptr [rax+rax+00h]
0x180017901  test    ebx, ebx
0x180017903  jle     short loc_18001792A
0x180017905  movzx   ebx, bx
0x180017908  or      ebx, 80070000h
0x18001790e  jmp     short loc_18001792A
0x180017910  lea     r8, [rbp+290h+var_230]; unsigned __int8 *
0x180017914  call    ?SADatSetData@@YAJPEAXKQEBE@Z; SADatSetData(void *,ulong,uchar const * const)
0x180017919  mov     rcx, rdi; hObject
0x18001791c  mov     ebx, eax
0x18001791e  call    cs:__imp_CloseHandle
0x180017925  nop     dword ptr [rax+rax+00h]
0x18001792a  mov     eax, ebx
0x18001792c  mov     rcx, [rbp+290h+var_10]
0x180017933  xor     rcx, rsp; StackCookie
0x180017936  call    __security_check_cookie
0x18001793b  lea     r11, [rsp+390h+var_s0]
0x180017943  mov     rbx, [r11+18h]
0x180017947  mov     rdi, [r11+20h]
0x18001794b  mov     rsp, r11
0x18001794e  pop     rbp
0x18001794f  retn
```
