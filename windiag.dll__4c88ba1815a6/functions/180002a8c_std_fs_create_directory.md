# __std_fs_create_directory

- ea: `0x180002a8c`
- end: `0x180002b1b`
- name: `__std_fs_create_directory`
- size: `143`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180067f58`
- `0x180069e7c`

## callees

- `0x180002a8c`
- `0x180002bf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002abc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180002aa3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180002aa3`

## pseudocode

```c
__int64 __fastcall _std_fs_create_directory(LPCWSTR lpFileName)
{
  DWORD LastError; // eax
  __int64 v4; // [rsp+58h] [rbp+18h]

  if ( CreateDirectoryW(lpFileName, 0) )
  {
    LastError = 0;
    LOBYTE(v4) = 1;
    *(_WORD *)((char *)&v4 + 1) = 0;
    BYTE3(v4) = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 183 )
    {
      LastError = _std_fs_get_stats(lpFileName);
      if ( !LastError )
        LastError = 183;
    }
    LOBYTE(v4) = 0;
    *(_WORD *)((char *)&v4 + 1) = 0;
    BYTE3(v4) = 0;
  }
  HIDWORD(v4) = LastError;
  return v4;
}

```

## disassembly

```asm
0x180002a8c  mov     [rsp-8+arg_0], rbx
0x180002a91  mov     [rsp-8+arg_10], rdi
0x180002a96  push    rbp
0x180002a97  mov     rbp, rsp
0x180002a9a  sub     rsp, 40h
0x180002a9e  xor     edx, edx; lpSecurityAttributes
0x180002aa0  mov     rbx, rcx
0x180002aa3  call    cs:__imp_CreateDirectoryW
0x180002aa9  test    eax, eax
0x180002aab  jz      short loc_180002ABC
0x180002aad  xor     eax, eax
0x180002aaf  mov     byte ptr [rbp+arg_8], 1
0x180002ab3  mov     word ptr [rbp+arg_8+1], ax
0x180002ab7  mov     byte ptr [rbp+arg_8+3], al
0x180002aba  jmp     short loc_180002B04
0x180002abc  call    cs:__imp_GetLastError
0x180002ac2  mov     edi, 0B7h
0x180002ac7  cmp     eax, edi
0x180002ac9  jnz     short loc_180002AF7
0x180002acb  xorps   xmm0, xmm0
0x180002ace  lea     rdx, [rbp+var_20]
0x180002ad2  or      r9d, 0FFFFFFFFh
0x180002ad6  mov     r8d, 3
0x180002adc  mov     rcx, rbx; lpFileName
0x180002adf  movups  [rbp+var_20], xmm0
0x180002ae3  movups  [rbp+var_10], xmm0
0x180002ae7  call    __std_fs_get_stats
0x180002aec  test    eax, eax
0x180002aee  jnz     short loc_180002AF7
0x180002af0  test    byte ptr [rbp+var_10], 10h
0x180002af4  cmovz   eax, edi
0x180002af7  xor     ecx, ecx
0x180002af9  mov     byte ptr [rbp+arg_8], 0
0x180002afd  mov     word ptr [rbp+arg_8+1], cx
0x180002b01  mov     byte ptr [rbp+arg_8+3], cl
0x180002b04  mov     rbx, [rsp+40h+arg_0]
0x180002b09  mov     rdi, [rsp+40h+arg_10]
0x180002b0e  mov     dword ptr [rbp+arg_8+4], eax
0x180002b11  mov     rax, [rbp+arg_8]
0x180002b15  add     rsp, 40h
0x180002b19  pop     rbp
0x180002b1a  retn
```
