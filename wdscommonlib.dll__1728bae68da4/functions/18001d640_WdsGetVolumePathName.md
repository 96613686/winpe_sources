# WdsGetVolumePathName

- ea: `0x18001d640`
- end: `0x18001d71f`
- name: `WdsGetVolumePathName`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001dc80`

## callees

- `0x18000214c`
- `0x18001b0cc`
- `0x18001cda0`
- `0x18001d640`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d6e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d6ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d6e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d6ff`
- `KERNEL32!GetVolumePathNameW` at `0x18001d6a3`
- `KERNEL32!GetVolumePathNameW` at `0x18001d6a3`
- `KERNEL32!GetLastError` at `0x18001d6b3`
- `KERNEL32!GetLastError` at `0x18001d6b3`

## pseudocode

```c
__int64 __fastcall WdsGetVolumePathName(const WCHAR *a1, WCHAR **a2)
{
  WCHAR *v3; // rdi
  unsigned int FullPath; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  WCHAR *v7; // rax
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8

  v3 = 0;
  FullPath = WdsGetFullPath(a1);
  if ( !(unsigned int)ElValidateWin32_8(FullPath, v5, v6, 4090) )
  {
    v7 = (WCHAR *)operator new[](0x20Au, (const struct std::nothrow_t *)&std::nothrow);
    v3 = v7;
    if ( !v7 )
      return 8;
    if ( !GetVolumePathNameW(0, v7, 0x105u) )
    {
      LastError = GetLastError();
      FullPath = ElValidateWin32_8(LastError, v9, v10, 4103);
      if ( !FullPath )
        FullPath = 31;
      goto LABEL_10;
    }
    *a2 = v3;
  }
  if ( FullPath && v3 )
LABEL_10:
    operator delete(v3);
  return FullPath;
}

```

## disassembly

```asm
0x18001d640  mov     rax, rsp
0x18001d643  mov     [rax+8], rbx
0x18001d647  mov     [rax+10h], rdi
0x18001d64b  push    r14
0x18001d64d  sub     rsp, 20h
0x18001d651  and     qword ptr [rax+20h], 0
0x18001d656  mov     r14, rdx
0x18001d659  lea     rdx, [rax+20h]
0x18001d65d  xor     edi, edi
0x18001d65f  call    WdsGetFullPath
0x18001d664  mov     r9d, 0FFAh
0x18001d66a  mov     ecx, eax
0x18001d66c  mov     ebx, eax
0x18001d66e  call    ElValidateWin32_8
0x18001d673  test    eax, eax
0x18001d675  jnz     short loc_18001D6DA
0x18001d677  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d67e  mov     ecx, 20Ah; unsigned __int64
0x18001d683  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d688  mov     rdi, rax
0x18001d68b  test    rax, rax
0x18001d68e  jnz     short loc_18001D695
0x18001d690  lea     ebx, [rax+8]
0x18001d693  jmp     short loc_18001D6F2
0x18001d695  mov     rcx, [rsp+28h+lpszFileName]; lpszFileName
0x18001d69a  mov     r8d, 105h; cchBufferLength
0x18001d6a0  mov     rdx, rdi; lpszVolumePathName
0x18001d6a3  call    cs:__imp_GetVolumePathNameW
0x18001d6aa  nop     dword ptr [rax+rax+00h]
0x18001d6af  test    eax, eax
0x18001d6b1  jnz     short loc_18001D6D7
0x18001d6b3  call    cs:__imp_GetLastError
0x18001d6ba  nop     dword ptr [rax+rax+00h]
0x18001d6bf  mov     ecx, eax
0x18001d6c1  mov     r9d, 1007h
0x18001d6c7  call    ElValidateWin32_8
0x18001d6cc  mov     ebx, eax
0x18001d6ce  test    eax, eax
0x18001d6d0  jnz     short loc_18001D6E3
0x18001d6d2  lea     ebx, [rax+1Fh]
0x18001d6d5  jmp     short loc_18001D6E3
0x18001d6d7  mov     [r14], rdi
0x18001d6da  test    ebx, ebx
0x18001d6dc  jz      short loc_18001D6F2
0x18001d6de  test    rdi, rdi
0x18001d6e1  jz      short loc_18001D6F2
0x18001d6e3  mov     rcx, rdi
0x18001d6e6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d6ed  nop     dword ptr [rax+rax+00h]
0x18001d6f2  cmp     [rsp+28h+lpszFileName], 0
0x18001d6f8  jz      short loc_18001D70B
0x18001d6fa  mov     rcx, [rsp+28h+lpszFileName]
0x18001d6ff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d706  nop     dword ptr [rax+rax+00h]
0x18001d70b  mov     rdi, [rsp+28h+arg_8]
0x18001d710  mov     eax, ebx
0x18001d712  mov     rbx, [rsp+28h+arg_0]
0x18001d717  add     rsp, 20h
0x18001d71b  pop     r14
0x18001d71d  retn
```
