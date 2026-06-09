# StackLockFileWin32Reader::Open(std::filesystem::path const &)

- ea: `0x18000c0e0`
- end: `0x18000c1b1`
- name: `?Open@StackLockFileWin32Reader@@UEAA_NAEBVpath@filesystem@std@@@Z`
- size: `209`
- prototype: `char __fastcall(StackLockFileWin32Reader *this, const WCHAR *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180005450`
- `0x18000c0e0`
- `0x180026cd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c144`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c157`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c157`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c14f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c14f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c12c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c12c`

## pseudocode

```c
char __fastcall StackLockFileWin32Reader::Open(StackLockFileWin32Reader *this, const WCHAR *a2)
{
  const WCHAR *v2; // rax
  HANDLE FileW; // rax
  wil::details *v5; // rcx
  void *v6; // rdi
  HANDLE v7; // rsi
  DWORD LastError; // ebx
  int LastErrorFailHr; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v2 = *(const WCHAR **)a2;
  FileW = CreateFileW(v2, 0x80000000, 1u, 0, 4u, 0x80u, 0);
  v6 = (void *)*((_QWORD *)this + 1);
  v7 = FileW;
  if ( v6 != (void *)-1LL && v6 )
  {
    LastError = GetLastError();
    CloseHandle(v6);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = v7;
  if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    return 1;
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  if ( (_WORD)LastErrorFailHr != 32 )
  {
    if ( LastErrorFailHr < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
        (const char *)(unsigned int)LastErrorFailHr,
        dwCreationDisposition);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c0e0  mov     [rsp+arg_0], rbx
0x18000c0e5  mov     [rsp+arg_8], rbp
0x18000c0ea  mov     [rsp+arg_10], rsi
0x18000c0ef  push    rdi
0x18000c0f0  sub     rsp, 40h
0x18000c0f4  cmp     qword ptr [rdx+18h], 7
0x18000c0f9  mov     rax, rdx
0x18000c0fc  mov     rbp, rcx
0x18000c0ff  jbe     short loc_18000C104
0x18000c101  mov     rax, [rdx]
0x18000c104  xor     r9d, r9d; lpSecurityAttributes
0x18000c107  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000c110  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c118  mov     edx, 80000000h; dwDesiredAccess
0x18000c11d  mov     rcx, rax; lpFileName
0x18000c120  mov     [rsp+48h+dwCreationDisposition], 4; int
0x18000c128  lea     r8d, [r9+1]; dwShareMode
0x18000c12c  call    cs:__imp_CreateFileW
0x18000c132  mov     rdi, [rbp+8]
0x18000c136  mov     rsi, rax
0x18000c139  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c13d  jz      short loc_18000C15D
0x18000c13f  test    rdi, rdi
0x18000c142  jz      short loc_18000C15D
0x18000c144  call    cs:__imp_GetLastError
0x18000c14a  mov     rcx, rdi; hObject
0x18000c14d  mov     ebx, eax
0x18000c14f  call    cs:__imp_CloseHandle
0x18000c155  mov     ecx, ebx; dwErrCode
0x18000c157  call    cs:__imp_SetLastError
0x18000c15d  lea     rax, [rsi+1]
0x18000c161  mov     [rbp+8], rsi
0x18000c165  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000c16b  jnz     short loc_18000C17F
0x18000c16d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c172  mov     r9d, eax; char *
0x18000c175  cmp     ax, 20h ; ' '
0x18000c179  jz      short loc_18000C196
0x18000c17b  test    eax, eax
0x18000c17d  js      short loc_18000C19A
0x18000c17f  mov     al, 1
0x18000c181  mov     rbx, [rsp+48h+arg_0]
0x18000c186  mov     rbp, [rsp+48h+arg_8]
0x18000c18b  mov     rsi, [rsp+48h+arg_10]
0x18000c190  add     rsp, 40h
0x18000c194  pop     rdi
0x18000c195  retn
0x18000c196  xor     al, al
0x18000c198  jmp     short loc_18000C181
0x18000c19a  mov     rcx, [rsp+48h]; this
0x18000c19f  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000c1a6  mov     edx, 9Ch; void *
0x18000c1ab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
