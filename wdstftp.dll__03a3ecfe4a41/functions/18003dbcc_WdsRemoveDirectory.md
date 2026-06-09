# WdsRemoveDirectory

- ea: `0x18003dbcc`
- end: `0x18003dd24`
- name: `WdsRemoveDirectory`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003e7c0`

## callees

- `0x18003d150`
- `0x18003d5cc`
- `0x18003dbcc`
- `0x18003f704`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18003dc1b`
- `KERNEL32!SetFileAttributesW` at `0x18003dc1b`
- `KERNEL32!HeapFree` at `0x18003dcd8`
- `KERNEL32!HeapFree` at `0x18003dcd8`
- `KERNEL32!GetLastError` at `0x18003dc2b`
- `KERNEL32!GetLastError` at `0x18003dc6c`
- `KERNEL32!GetLastError` at `0x18003dc7a`
- `KERNEL32!GetLastError` at `0x18003dc92`
- `KERNEL32!GetLastError` at `0x18003dc2b`
- `KERNEL32!GetLastError` at `0x18003dc6c`
- `KERNEL32!GetLastError` at `0x18003dc7a`
- `KERNEL32!GetLastError` at `0x18003dc92`
- `KERNEL32!SetLastError` at `0x18003dce6`
- `KERNEL32!SetLastError` at `0x18003dcfb`
- `KERNEL32!SetLastError` at `0x18003dce6`
- `KERNEL32!SetLastError` at `0x18003dcfb`
- `KERNEL32!GetProcessHeap` at `0x18003dcc4`
- `KERNEL32!GetProcessHeap` at `0x18003dcc4`

## string_xrefs

- `0x18003dc3a`: `WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x`
- `0x18003dc89`: `WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x`
- `0x18003dca1`: `WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall WdsRemoveDirectory(unsigned __int16 *a1)
{
  unsigned int v2; // ebp
  DWORD LastError; // edi
  const WCHAR *v4; // rax
  unsigned __int16 *v5; // rbx
  DWORD v6; // eax
  unsigned __int16 *v7; // r9
  const wchar_t *v8; // r8
  HANDLE ProcessHeap; // rax
  __int64 v11; // [rsp+20h] [rbp-18h]

  v2 = 0;
  LastError = 0;
  if ( !a1 || !*a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v4 = (const WCHAR *)PrepareUnicodePath(a1);
  v5 = (unsigned __int16 *)v4;
  if ( v4 )
  {
    if ( !SetFileAttributesW(v4, 0x80u) )
    {
      LastError = GetLastError();
      LibLog(
        &g_WdsLibLog,
        50331648,
        L"WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x",
        v5,
        LastError);
    }
    v2 = DeleteFileEx2(v5, 0);
    if ( v2 )
      goto LABEL_12;
    if ( !LastError )
      LastError = GetLastError();
    v6 = GetLastError();
    v7 = v5;
    v8 = L"WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x";
  }
  else
  {
    v6 = GetLastError();
    v7 = a1;
    v8 = L"WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x";
    LastError = v6;
  }
  LODWORD(v11) = v6;
  LibLog(&g_WdsLibLog, 50331648, v8, v7, v11);
LABEL_12:
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  SetLastError(LastError);
  return v2;
}

```

## disassembly

```asm
0x18003dbcc  mov     rax, rsp
0x18003dbcf  mov     [rax+8], rbx
0x18003dbd3  mov     [rax+10h], rbp
0x18003dbd7  mov     [rax+18h], rsi
0x18003dbdb  mov     [rax+20h], rdi
0x18003dbdf  push    r14
0x18003dbe1  sub     rsp, 30h
0x18003dbe5  xor     r14d, r14d
0x18003dbe8  mov     rsi, rcx
0x18003dbeb  mov     ebp, r14d
0x18003dbee  mov     edi, r14d
0x18003dbf1  test    rcx, rcx
0x18003dbf4  jz      loc_18003DCF6
0x18003dbfa  cmp     r14w, [rcx]
0x18003dbfe  jz      loc_18003DCF6
0x18003dc04  xor     edx, edx
0x18003dc06  call    PrepareUnicodePath
0x18003dc0b  mov     rbx, rax
0x18003dc0e  test    rax, rax
0x18003dc11  jz      short loc_18003DC92
0x18003dc13  mov     edx, 80h; dwFileAttributes
0x18003dc18  mov     rcx, rax; lpFileName
0x18003dc1b  call    cs:__imp_SetFileAttributesW
0x18003dc22  nop     dword ptr [rax+rax+00h]
0x18003dc27  test    eax, eax
0x18003dc29  jnz     short loc_18003DC58
0x18003dc2b  call    cs:__imp_GetLastError
0x18003dc32  nop     dword ptr [rax+rax+00h]
0x18003dc37  mov     r9, rbx
0x18003dc3a  lea     r8, aWdsremovedirec; "WdsRemoveDirectory: Unable to clear att"...
0x18003dc41  lea     rcx, g_WdsLibLog
0x18003dc48  mov     dword ptr [rsp+38h+var_18], eax
0x18003dc4c  mov     edx, 3000000h
0x18003dc51  mov     edi, eax
0x18003dc53  call    LibLog
0x18003dc58  xor     edx, edx
0x18003dc5a  mov     rcx, rbx
0x18003dc5d  call    DeleteFileEx2
0x18003dc62  mov     ebp, eax
0x18003dc64  test    eax, eax
0x18003dc66  jnz     short loc_18003DCBF
0x18003dc68  test    edi, edi
0x18003dc6a  jnz     short loc_18003DC7A
0x18003dc6c  call    cs:__imp_GetLastError
0x18003dc73  nop     dword ptr [rax+rax+00h]
0x18003dc78  mov     edi, eax
0x18003dc7a  call    cs:__imp_GetLastError
0x18003dc81  nop     dword ptr [rax+rax+00h]
0x18003dc86  mov     r9, rbx
0x18003dc89  lea     r8, aWdsremovedirec_0; "WdsRemoveDirectory: Unable to remove di"...
0x18003dc90  jmp     short loc_18003DCAA
0x18003dc92  call    cs:__imp_GetLastError
0x18003dc99  nop     dword ptr [rax+rax+00h]
0x18003dc9e  mov     r9, rsi
0x18003dca1  lea     r8, aWdsremovedirec_1; "WdsRemoveDirectory: Unable to prepare p"...
0x18003dca8  mov     edi, eax
0x18003dcaa  mov     edx, 3000000h
0x18003dcaf  mov     dword ptr [rsp+38h+var_18], eax
0x18003dcb3  lea     rcx, g_WdsLibLog
0x18003dcba  call    LibLog
0x18003dcbf  test    rbx, rbx
0x18003dcc2  jz      short loc_18003DCE4
0x18003dcc4  call    cs:__imp_GetProcessHeap
0x18003dccb  nop     dword ptr [rax+rax+00h]
0x18003dcd0  mov     r8, rbx; lpMem
0x18003dcd3  xor     edx, edx; dwFlags
0x18003dcd5  mov     rcx, rax; hHeap
0x18003dcd8  call    cs:__imp_HeapFree
0x18003dcdf  nop     dword ptr [rax+rax+00h]
0x18003dce4  mov     ecx, edi; dwErrCode
0x18003dce6  call    cs:__imp_SetLastError
0x18003dced  nop     dword ptr [rax+rax+00h]
0x18003dcf2  mov     eax, ebp
0x18003dcf4  jmp     short loc_18003DD09
0x18003dcf6  mov     ecx, 57h ; 'W'; dwErrCode
0x18003dcfb  call    cs:__imp_SetLastError
0x18003dd02  nop     dword ptr [rax+rax+00h]
0x18003dd07  xor     eax, eax
0x18003dd09  mov     rbx, [rsp+38h+arg_0]
0x18003dd0e  mov     rbp, [rsp+38h+arg_8]
0x18003dd13  mov     rsi, [rsp+38h+arg_10]
0x18003dd18  mov     rdi, [rsp+38h+arg_18]
0x18003dd1d  add     rsp, 30h
0x18003dd21  pop     r14
0x18003dd23  retn
```
