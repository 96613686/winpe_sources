# FilePathCanBeExcluded(ushort const *,ushort const *,ushort const *)

- ea: `0x18000f52c`
- end: `0x18000f5fd`
- name: `?FilePathCanBeExcluded@@YA_NPEBG00@Z`
- size: `209`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005c80`

## callees

- `0x180001384`
- `0x1800054d0`
- `0x18000f52c`
- `0x180010110`
- `0x180010228`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000f5e8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000f5e8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000f5af`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000f5af`

## pseudocode

```c
bool __fastcall FilePathCanBeExcluded(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  bool v5; // bl
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned int v8; // r14d
  unsigned __int16 *v9; // rax
  WCHAR *v10; // rdi
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v12; // rcx

  v5 = 1;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v8 = v7 + v6 + 1;
  v9 = (unsigned __int16 *)operator new[](saturated_mul(v8, 2u));
  v10 = v9;
  if ( v9 )
    v5 = (int)StringCchPrintfW(v9, v8, L"%s%s", a1, a3) >= 0
      && ((FileAttributesW = GetFileAttributesW(v10), FileAttributesW == -1)
       || (FileAttributesW & 0x10) == 0
       || *a3 != 92
       || a3[1])
      && !IsBlackListedFile(v10)
      && !IsPageFile(v12);
  operator delete[](v10);
  return v5;
}

```

## disassembly

```asm
0x18000f52c  push    rbx
0x18000f52e  push    rbp
0x18000f52f  push    rsi
0x18000f530  push    rdi
0x18000f531  push    r14
0x18000f533  push    r15
0x18000f535  sub     rsp, 38h
0x18000f539  mov     rbp, rcx
0x18000f53c  mov     rsi, r8
0x18000f53f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000f543  mov     bl, 1
0x18000f545  mov     rdx, rcx
0x18000f548  xor     r15d, r15d
0x18000f54b  inc     rdx
0x18000f54e  cmp     [r8+rdx*2], r15w
0x18000f553  jnz     short loc_18000F54B
0x18000f555  mov     rax, rcx
0x18000f558  inc     rax
0x18000f55b  cmp     [rbp+rax*2+0], r15w
0x18000f561  jnz     short loc_18000F558
0x18000f563  lea     r14, [rdx+1]
0x18000f567  add     r14, rax
0x18000f56a  mov     eax, 2
0x18000f56f  mov     r14d, r14d
0x18000f572  mul     r14
0x18000f575  cmovb   rax, rcx
0x18000f579  mov     rcx, rax; unsigned __int64
0x18000f57c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f581  mov     rdi, rax
0x18000f584  test    rax, rax
0x18000f587  jz      short loc_18000F5E5
0x18000f589  mov     r9, rbp
0x18000f58c  mov     [rsp+68h+var_48], rsi
0x18000f591  lea     r8, aSS_0; "%s%s"
0x18000f598  mov     edx, r14d; unsigned __int64
0x18000f59b  mov     rcx, rax; unsigned __int16 *
0x18000f59e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f5a3  test    eax, eax
0x18000f5a5  jns     short loc_18000F5AC
0x18000f5a7  mov     bl, r15b
0x18000f5aa  jmp     short loc_18000F5E5
0x18000f5ac  mov     rcx, rdi; lpFileName
0x18000f5af  call    cs:__imp_GetFileAttributesW
0x18000f5b5  cmp     eax, 0FFFFFFFFh
0x18000f5b8  jz      short loc_18000F5CB
0x18000f5ba  test    al, 10h
0x18000f5bc  jz      short loc_18000F5CB
0x18000f5be  cmp     word ptr [rsi], 5Ch ; '\'
0x18000f5c2  jnz     short loc_18000F5CB
0x18000f5c4  cmp     [rsi+2], r15w
0x18000f5c9  jz      short loc_18000F5A7
0x18000f5cb  mov     rcx, rdi; unsigned __int16 *
0x18000f5ce  call    ?IsBlackListedFile@@YA_NPEBG@Z; IsBlackListedFile(ushort const *)
0x18000f5d3  test    al, al
0x18000f5d5  jnz     short loc_18000F5A7
0x18000f5d7  call    ?IsPageFile@@YA_NPEBG@Z; IsPageFile(ushort const *)
0x18000f5dc  test    al, al
0x18000f5de  movzx   ebx, bl
0x18000f5e1  cmovnz  ebx, r15d
0x18000f5e5  mov     rcx, rdi
0x18000f5e8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000f5ee  mov     al, bl
0x18000f5f0  add     rsp, 38h
0x18000f5f4  pop     r15
0x18000f5f6  pop     r14
0x18000f5f8  pop     rdi
0x18000f5f9  pop     rsi
0x18000f5fa  pop     rbp
0x18000f5fb  pop     rbx
0x18000f5fc  retn
```
