# IsDesiredProcess(ushort const *)

- ea: `0x18000277c`
- end: `0x18000281d`
- name: `?IsDesiredProcess@@YA_NPEBG@Z`
- size: `161`
- prototype: `bool __fastcall(PCNZWCH lpString2)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800036ec`
- `0x1800037fc`

## callees

- `0x18000277c`
- `0x180005320`
- `0x180010fcc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800027ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800027ad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800027eb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800027eb`

## pseudocode

```c
char __fastcall IsDesiredProcess(PCNZWCH lpString2)
{
  char v2; // bl
  unsigned __int16 v3; // dx
  unsigned __int16 *v4; // rax
  WCHAR *v5; // rax
  WCHAR Filename[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = 0;
  if ( GetModuleFileNameW(0, Filename, 0x105u) )
  {
    v4 = wcsrchr(Filename, v3);
    if ( v4 )
      v5 = v4 + 1;
    else
      v5 = Filename;
    return CompareStringW(0x7Fu, 1u, v5, -1, lpString2, -1) == 2;
  }
  return v2;
}

```

## disassembly

```asm
0x18000277c  mov     [rsp+arg_8], rbx
0x180002781  push    rdi
0x180002782  sub     rsp, 250h
0x180002789  mov     rax, cs:__security_cookie
0x180002790  xor     rax, rsp
0x180002793  mov     [rsp+258h+var_18], rax
0x18000279b  mov     rdi, rcx
0x18000279e  lea     rdx, [rsp+258h+Filename]; lpFilename
0x1800027a3  xor     ecx, ecx; hModule
0x1800027a5  mov     r8d, 105h; nSize
0x1800027ab  xor     bl, bl
0x1800027ad  call    cs:__imp_GetModuleFileNameW
0x1800027b3  test    eax, eax
0x1800027b5  jz      short loc_1800027FA
0x1800027b7  lea     rcx, [rsp+258h+Filename]; unsigned __int16 *
0x1800027bc  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x1800027c1  test    rax, rax
0x1800027c4  jnz     short loc_1800027CD
0x1800027c6  lea     rax, [rsp+258h+Filename]
0x1800027cb  jmp     short loc_1800027D1
0x1800027cd  add     rax, 2
0x1800027d1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800027d5  mov     r8, rax; lpString1
0x1800027d8  mov     [rsp+258h+cchCount2], r9d; cchCount2
0x1800027dd  mov     [rsp+258h+lpString2], rdi; lpString2
0x1800027e2  lea     edi, [r9+2]
0x1800027e6  mov     edx, edi; dwCmpFlags
0x1800027e8  lea     ecx, [rdi+7Eh]; Locale
0x1800027eb  call    cs:__imp_CompareStringW
0x1800027f1  cmp     eax, 2
0x1800027f4  movzx   ebx, bl
0x1800027f7  cmovz   ebx, edi
0x1800027fa  mov     al, bl
0x1800027fc  mov     rcx, [rsp+258h+var_18]
0x180002804  xor     rcx, rsp; StackCookie
0x180002807  call    __security_check_cookie
0x18000280c  mov     rbx, [rsp+258h+arg_8]
0x180002814  add     rsp, 250h
0x18000281b  pop     rdi
0x18000281c  retn
```
