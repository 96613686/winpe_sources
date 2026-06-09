# WdsGetVolumePathName

- ea: `0x18001c730`
- end: `0x18001c801`
- name: `WdsGetVolumePathName`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001cd20`

## callees

- `0x18000179c`
- `0x18001a28c`
- `0x18001bec0`
- `0x18001c730`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x18001c793`
- `KERNEL32!GetVolumePathNameW` at `0x18001c793`
- `KERNEL32!GetLastError` at `0x18001c7a3`
- `KERNEL32!GetLastError` at `0x18001c7a3`

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
0x18001c730  mov     rax, rsp
0x18001c733  mov     [rax+8], rbx
0x18001c737  mov     [rax+10h], rdi
0x18001c73b  push    r14
0x18001c73d  sub     rsp, 20h
0x18001c741  and     qword ptr [rax+20h], 0
0x18001c746  mov     r14, rdx
0x18001c749  lea     rdx, [rax+20h]
0x18001c74d  xor     edi, edi
0x18001c74f  call    WdsGetFullPath
0x18001c754  mov     r9d, 0FFAh
0x18001c75a  mov     ecx, eax
0x18001c75c  mov     ebx, eax
0x18001c75e  call    ElValidateWin32_8
0x18001c763  test    eax, eax
0x18001c765  jnz     short loc_18001C7CA
0x18001c767  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c76e  mov     ecx, 20Ah; unsigned __int64
0x18001c773  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001c778  mov     rdi, rax
0x18001c77b  test    rax, rax
0x18001c77e  jnz     short loc_18001C785
0x18001c780  lea     ebx, [rax+8]
0x18001c783  jmp     short loc_18001C7DB
0x18001c785  mov     rcx, [rsp+28h+lpszFileName]; lpszFileName
0x18001c78a  mov     r8d, 105h; cchBufferLength
0x18001c790  mov     rdx, rdi; lpszVolumePathName
0x18001c793  call    cs:__imp_GetVolumePathNameW
0x18001c79a  nop     dword ptr [rax+rax+00h]
0x18001c79f  test    eax, eax
0x18001c7a1  jnz     short loc_18001C7C7
0x18001c7a3  call    cs:__imp_GetLastError
0x18001c7aa  nop     dword ptr [rax+rax+00h]
0x18001c7af  mov     ecx, eax
0x18001c7b1  mov     r9d, 1007h
0x18001c7b7  call    ElValidateWin32_8
0x18001c7bc  mov     ebx, eax
0x18001c7be  test    eax, eax
0x18001c7c0  jnz     short loc_18001C7D3
0x18001c7c2  lea     ebx, [rax+1Fh]
0x18001c7c5  jmp     short loc_18001C7D3
0x18001c7c7  mov     [r14], rdi
0x18001c7ca  test    ebx, ebx
0x18001c7cc  jz      short loc_18001C7DB
0x18001c7ce  test    rdi, rdi
0x18001c7d1  jz      short loc_18001C7DB
0x18001c7d3  mov     rcx, rdi; lpMem
0x18001c7d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c7db  cmp     [rsp+28h+lpszFileName], 0
0x18001c7e1  jz      short loc_18001C7ED
0x18001c7e3  mov     rcx, [rsp+28h+lpszFileName]; lpMem
0x18001c7e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c7ed  mov     rdi, [rsp+28h+arg_8]
0x18001c7f2  mov     eax, ebx
0x18001c7f4  mov     rbx, [rsp+28h+arg_0]
0x18001c7f9  add     rsp, 20h
0x18001c7fd  pop     r14
0x18001c7ff  retn
```
