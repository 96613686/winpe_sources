# CopyRupDirectory(ushort const *,ushort const *,int)

- ea: `0x18000cce0`
- end: `0x18000cdbb`
- name: `?CopyRupDirectory@@YAJPEBG0H@Z`
- size: `219`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ab88`

## callees

- `0x1800067b8`
- `0x18000cce0`
- `0x18000da0c`
- `0x18000dc30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ccfa`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ccfa`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000cda1`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000cda1`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18000cd76`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18000cd76`

## string_xrefs

- `0x18000cd25`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000cd8b`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000cd19`: `Failed to create the destination directory <%ls>.`

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
0x18000cce0  push    rbx
0x18000cce2  push    rbp
0x18000cce3  push    rsi
0x18000cce4  push    rdi
0x18000cce5  sub     rsp, 38h
0x18000cce9  mov     rdi, rdx
0x18000ccec  mov     rbp, rcx
0x18000ccef  mov     rcx, rdi; lpFileName
0x18000ccf2  mov     edx, 80h; dwFileAttributes
0x18000ccf7  mov     esi, r8d
0x18000ccfa  call    cs:__imp_SetFileAttributesW
0x18000cd01  nop     dword ptr [rax+rax+00h]
0x18000cd06  mov     rcx, rdi; pszSrc
0x18000cd09  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000cd0e  mov     ebx, eax
0x18000cd10  test    eax, eax
0x18000cd12  jns     short loc_18000CD42
0x18000cd14  mov     rcx, [rsp+58h]; this
0x18000cd19  lea     rax, aFailedToCreate; "Failed to create the destination direct"...
0x18000cd20  mov     [rsp+58h+var_30], rdi; char *
0x18000cd25  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cd2c  mov     r9d, ebx; char *
0x18000cd2f  mov     qword ptr [rsp+58h+var_38], rax; int
0x18000cd34  mov     edx, 182h; void *
0x18000cd39  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cd3e  mov     eax, ebx
0x18000cd40  jmp     short loc_18000CDB1
0x18000cd42  neg     esi
0x18000cd44  mov     [rsp+58h+arg_18], 0
0x18000cd4c  lea     r8, _CopyProgressRoutine
0x18000cd53  mov     rdx, rdi
0x18000cd56  sbb     eax, eax
0x18000cd58  mov     rcx, rbp
0x18000cd5b  and     eax, 0FFFFFBF0h
0x18000cd60  xor     r9d, r9d
0x18000cd63  add     eax, 690h
0x18000cd68  mov     dword ptr [rsp+58h+var_30], eax
0x18000cd6c  lea     rax, [rsp+58h+arg_18]
0x18000cd71  mov     qword ptr [rsp+58h+var_38], rax
0x18000cd76  call    cs:__imp_PrivCopyFileExW
0x18000cd7d  nop     dword ptr [rax+rax+00h]
0x18000cd82  test    eax, eax
0x18000cd84  jnz     short loc_18000CDAF
0x18000cd86  mov     rcx, [rsp+58h]; this
0x18000cd8b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000cd92  mov     edx, 195h; void *
0x18000cd97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cd9c  mov     rcx, rdi; lpPathName
0x18000cd9f  mov     ebx, eax
0x18000cda1  call    cs:__imp_RemoveDirectoryW
0x18000cda8  nop     dword ptr [rax+rax+00h]
0x18000cdad  jmp     short loc_18000CD3E
0x18000cdaf  xor     eax, eax
0x18000cdb1  add     rsp, 38h
0x18000cdb5  pop     rdi
0x18000cdb6  pop     rsi
0x18000cdb7  pop     rbp
0x18000cdb8  pop     rbx
0x18000cdb9  retn
```
