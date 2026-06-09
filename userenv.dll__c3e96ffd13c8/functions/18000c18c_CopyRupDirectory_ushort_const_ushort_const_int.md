# CopyRupDirectory(ushort const *,ushort const *,int)

- ea: `0x18000c18c`
- end: `0x18000c254`
- name: `?CopyRupDirectory@@YAJPEBG0H@Z`
- size: `200`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a200`

## callees

- `0x1800061d4`
- `0x18000c18c`
- `0x18000cd2c`
- `0x18000cfc4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c1a6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c1a6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000c241`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000c241`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18000c21c`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18000c21c`

## string_xrefs

- `0x18000c1cb`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c22b`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c1bf`: `Failed to create the destination directory <%ls>.`

## pseudocode

```c
__int64 __fastcall CopyRupDirectory(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  struct _SECURITY_ATTRIBUTES *v6; // rdx
  unsigned int NestedDirectory; // ebx
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v11; // [rsp+78h] [rbp+20h] BYREF

  SetFileAttributesW(a2, 0x80u);
  NestedDirectory = CreateNestedDirectory(a2, v6);
  if ( (NestedDirectory & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
      (const char *)NestedDirectory,
      (int)"Failed to create the destination directory <%ls>.",
      (const char *)a2);
    return NestedDirectory;
  }
  v11 = 0;
  if ( !(unsigned int)PrivCopyFileExW(a1, a2, CopyProgressRoutine, 0, &v11, a3 != 0 ? 640 : 1680) )
  {
    NestedDirectory = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x195,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                        v9);
    RemoveDirectoryW(a2);
    return NestedDirectory;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c18c  push    rbx
0x18000c18e  push    rbp
0x18000c18f  push    rsi
0x18000c190  push    rdi
0x18000c191  sub     rsp, 38h
0x18000c195  mov     rdi, rdx
0x18000c198  mov     rbp, rcx
0x18000c19b  mov     rcx, rdi; lpFileName
0x18000c19e  mov     edx, 80h; dwFileAttributes
0x18000c1a3  mov     esi, r8d
0x18000c1a6  call    cs:__imp_SetFileAttributesW
0x18000c1ac  mov     rcx, rdi; pszSrc
0x18000c1af  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000c1b4  mov     ebx, eax
0x18000c1b6  test    eax, eax
0x18000c1b8  jns     short loc_18000C1E8
0x18000c1ba  mov     rcx, [rsp+58h]; this
0x18000c1bf  lea     rax, aFailedToCreate; "Failed to create the destination direct"...
0x18000c1c6  mov     [rsp+58h+var_30], rdi; char *
0x18000c1cb  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c1d2  mov     r9d, ebx; char *
0x18000c1d5  mov     qword ptr [rsp+58h+var_38], rax; int
0x18000c1da  mov     edx, 182h; void *
0x18000c1df  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000c1e4  mov     eax, ebx
0x18000c1e6  jmp     short loc_18000C24B
0x18000c1e8  neg     esi
0x18000c1ea  mov     [rsp+58h+arg_18], 0
0x18000c1f2  lea     r8, _CopyProgressRoutine
0x18000c1f9  mov     rdx, rdi
0x18000c1fc  sbb     eax, eax
0x18000c1fe  mov     rcx, rbp
0x18000c201  and     eax, 0FFFFFBF0h
0x18000c206  xor     r9d, r9d
0x18000c209  add     eax, 690h
0x18000c20e  mov     dword ptr [rsp+58h+var_30], eax
0x18000c212  lea     rax, [rsp+58h+arg_18]
0x18000c217  mov     qword ptr [rsp+58h+var_38], rax
0x18000c21c  call    cs:__imp_PrivCopyFileExW
0x18000c222  test    eax, eax
0x18000c224  jnz     short loc_18000C249
0x18000c226  mov     rcx, [rsp+58h]; this
0x18000c22b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c232  mov     edx, 195h; void *
0x18000c237  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c23c  mov     rcx, rdi; lpPathName
0x18000c23f  mov     ebx, eax
0x18000c241  call    cs:__imp_RemoveDirectoryW
0x18000c247  jmp     short loc_18000C1E4
0x18000c249  xor     eax, eax
0x18000c24b  add     rsp, 38h
0x18000c24f  pop     rdi
0x18000c250  pop     rsi
0x18000c251  pop     rbp
0x18000c252  pop     rbx
0x18000c253  retn
```
