# SADatCreate(ushort const *,int)

- ea: `0x1800168b8`
- end: `0x180016a10`
- name: `?SADatCreate@@YAJPEBGH@Z`
- size: `344`
- prototype: `signed int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006010`

## callees

- `0x180016824`
- `0x1800168b8`
- `0x180016b94`
- `0x180016bf4`
- `0x180016c54`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016916`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800169c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800169e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800169c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800169e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001699d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001699d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016976`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016976`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18001690c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18001690c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x1800168b8  mov     [rsp-8+arg_8], rbx
0x1800168bd  mov     [rsp-8+arg_10], rdi
0x1800168c2  push    rbp
0x1800168c3  lea     rbp, [rsp-290h]
0x1800168cb  sub     rsp, 390h
0x1800168d2  mov     rax, cs:__security_cookie
0x1800168d9  xor     rax, rsp
0x1800168dc  mov     [rbp+290h+var_10], rax
0x1800168e3  mov     rbx, rcx
0x1800168e6  mov     dword ptr [rbp+290h+var_230], 6
0x1800168ed  lea     rcx, [rsp+390h+VersionInformation.dwMajorVersion]; void *
0x1800168f2  xor     edx, edx; Val
0x1800168f4  mov     r8d, 110h; Size
0x1800168fa  call    memset_0
0x1800168ff  lea     rcx, [rsp+390h+VersionInformation]; lpVersionInformation
0x180016904  mov     [rsp+390h+VersionInformation.dwOSVersionInfoSize], 114h
0x18001690c  call    cs:__imp_GetVersionExW
0x180016912  test    eax, eax
0x180016914  jnz     short loc_180016931
0x180016916  call    cs:__imp_GetLastError
0x18001691c  test    eax, eax
0x18001691e  jle     loc_1800169EC
0x180016924  movzx   eax, ax
0x180016927  or      eax, 80070000h
0x18001692c  jmp     loc_1800169EC
0x180016931  mov     edi, 2
0x180016936  cmp     [rsp+390h+VersionInformation.dwPlatformId], edi
0x18001693a  setz    al
0x18001693d  inc     al
0x18001693f  mov     [rbp+290h+var_22C], al
0x180016942  call    ?ResumeTimersSupported@@YAHXZ; ResumeTimersSupported(void)
0x180016947  neg     eax
0x180016949  lea     rcx, [rbp+290h+FileName]; void *
0x18001694d  mov     r8d, 20Ah; Size
0x180016953  sbb     dl, dl
0x180016955  and     dl, dil
0x180016958  inc     dl
0x18001695a  mov     [rbp+290h+var_22B], dl
0x18001695d  xor     edx, edx; Val
0x18001695f  call    memset_0
0x180016964  lea     rdx, [rbp+290h+FileName]; unsigned __int16 *
0x180016968  mov     rcx, rbx; unsigned __int16 *
0x18001696b  call    ?SADatPath@@YAXPEBGPEAG_K@Z; SADatPath(ushort const *,ushort *,unsigned __int64)
0x180016970  mov     edx, edi; dwFileAttributes
0x180016972  lea     rcx, [rbp+290h+FileName]; lpFileName
0x180016976  call    cs:__imp_SetFileAttributesW
0x18001697c  mov     [rsp+390h+hTemplateFile], 0; hTemplateFile
0x180016985  lea     r8d, [rdi+1]; dwShareMode
0x180016989  mov     [rsp+390h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18001698d  lea     rcx, [rbp+290h+FileName]; lpFileName
0x180016991  xor     r9d, r9d; lpSecurityAttributes
0x180016994  mov     [rsp+390h+dwCreationDisposition], edi; dwCreationDisposition
0x180016998  mov     edx, 0C0040000h; dwDesiredAccess
0x18001699d  call    cs:__imp_CreateFileW
0x1800169a3  mov     rdi, rax
0x1800169a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800169aa  jz      loc_180016916
0x1800169b0  mov     rcx, rax; handle
0x1800169b3  call    ?SADatSetSecurity@@YAKPEAX@Z; SADatSetSecurity(void *)
0x1800169b8  mov     ebx, eax
0x1800169ba  mov     rcx, rdi; void *
0x1800169bd  test    eax, eax
0x1800169bf  jz      short loc_1800169D6
0x1800169c1  call    cs:__imp_CloseHandle
0x1800169c7  test    ebx, ebx
0x1800169c9  jle     short loc_1800169EA
0x1800169cb  movzx   ebx, bx
0x1800169ce  or      ebx, 80070000h
0x1800169d4  jmp     short loc_1800169EA
0x1800169d6  lea     r8, [rbp+290h+var_230]; unsigned __int8 *
0x1800169da  call    ?SADatSetData@@YAJPEAXKQEBE@Z; SADatSetData(void *,ulong,uchar const * const)
0x1800169df  mov     rcx, rdi; hObject
0x1800169e2  mov     ebx, eax
0x1800169e4  call    cs:__imp_CloseHandle
0x1800169ea  mov     eax, ebx
0x1800169ec  mov     rcx, [rbp+290h+var_10]
0x1800169f3  xor     rcx, rsp; StackCookie
0x1800169f6  call    __security_check_cookie
0x1800169fb  lea     r11, [rsp+390h+var_s0]
0x180016a03  mov     rbx, [r11+18h]
0x180016a07  mov     rdi, [r11+20h]
0x180016a0b  mov     rsp, r11
0x180016a0e  pop     rbp
0x180016a0f  retn
```
