# FormatMessageToBuffer

- ea: `0x180066d8c`
- end: `0x180066ebd`
- name: `FormatMessageToBuffer`
- size: `305`
- prototype: `__int64 __fastcall(DWORD dwMessageId, wchar_t *, LPCWSTR lpLibFileName, EmdStringBuffer *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001df70`

## callees

- `0x180066d8c`
- `0x180066ec4`
- `0x1800d13b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066e61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066e61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066e7a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066e69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066e69`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180066ddf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180066ddf`

## pseudocode

```c
__int64 __fastcall FormatMessageToBuffer(DWORD dwMessageId, wchar_t *a2, LPCWSTR lpLibFileName, EmdStringBuffer *this)
{
  HMODULE Library; // rdi
  DWORD v8; // ecx
  __int64 v9; // r9
  unsigned int v10; // ecx
  __int64 v12; // r9
  wchar_t *Buffer; // [rsp+70h] [rbp+18h] BYREF

  Buffer = 0;
  if ( lpLibFileName )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0x22u);
    if ( !Library )
    {
LABEL_19:
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      EmdStringBuffer::AppendWide(this, a2, v12);
      EmdStringBuffer::AppendInteger<16,unsigned int>(this);
      goto LABEL_10;
    }
    v8 = 2816;
  }
  else
  {
    Library = 0;
    v8 = 4864;
  }
  FormatMessageW(v8, Library, dwMessageId, 0, (LPWSTR)&Buffer, 0, 0);
  if ( !Buffer )
    goto LABEL_19;
  v9 = -1;
  do
    ++v9;
  while ( Buffer[v9] );
  if ( (unsigned int)v9 >= 2 && *(_DWORD *)&Buffer[(unsigned int)(v9 - 2)] == 655373 )
    LODWORD(v9) = v9 - 2;
  EmdStringBuffer::AppendWide(this, Buffer, v9);
LABEL_10:
  v10 = *((_DWORD *)this + 3);
  *((_DWORD *)this + 3) = v10 + 1;
  if ( v10 + 1 <= *((_DWORD *)this + 2) )
    *(_WORD *)(*(_QWORD *)this + 2LL * v10) = 0;
  if ( Library )
    FreeLibrary(Library);
  if ( Buffer )
    LocalFree(Buffer);
  return 0;
}

```

## disassembly

```asm
0x180066d8c  mov     [rsp+arg_0], rbx
0x180066d91  mov     [rsp+arg_8], rbp
0x180066d96  push    rsi
0x180066d97  push    rdi
0x180066d98  push    r14
0x180066d9a  sub     rsp, 40h
0x180066d9e  xor     r14d, r14d
0x180066da1  mov     rbx, r9
0x180066da4  mov     [rsp+58h+Buffer], r14
0x180066da9  mov     rax, r8
0x180066dac  mov     rsi, rdx
0x180066daf  mov     ebp, ecx
0x180066db1  test    r8, r8
0x180066db4  jnz     loc_180066E71
0x180066dba  mov     edi, r14d
0x180066dbd  mov     ecx, 1300h; dwFlags
0x180066dc2  mov     [rsp+58h+Arguments], r14; Arguments
0x180066dc7  lea     rax, [rsp+58h+Buffer]
0x180066dcc  mov     [rsp+58h+nSize], r14d; nSize
0x180066dd1  xor     r9d, r9d; dwLanguageId
0x180066dd4  mov     r8d, ebp; dwMessageId
0x180066dd7  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x180066ddc  mov     rdx, rdi; lpSource
0x180066ddf  call    cs:__imp_FormatMessageW
0x180066de5  mov     rdx, [rsp+58h+Buffer]; wchar_t *
0x180066dea  test    rdx, rdx
0x180066ded  jz      loc_180066E92
0x180066df3  or      r9, 0FFFFFFFFFFFFFFFFh
0x180066df7  inc     r9
0x180066dfa  cmp     [rdx+r9*2], r14w
0x180066dff  jnz     short loc_180066DF7
0x180066e01  cmp     r9d, 2
0x180066e05  jb      short loc_180066E17
0x180066e07  lea     r8d, [r9-2]
0x180066e0b  cmp     dword ptr [rdx+r8*2], 0A000Dh
0x180066e13  cmovz   r9d, r8d
0x180066e17  mov     r8d, r9d; unsigned int
0x180066e1a  mov     rcx, rbx; this
0x180066e1d  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x180066e22  mov     ecx, [rbx+0Ch]
0x180066e25  lea     eax, [rcx+1]
0x180066e28  mov     [rbx+0Ch], eax
0x180066e2b  cmp     eax, [rbx+8]
0x180066e2e  ja      short loc_180066E3A
0x180066e30  mov     edx, ecx
0x180066e32  mov     rcx, [rbx]
0x180066e35  mov     [rcx+rdx*2], r14w
0x180066e3a  test    rdi, rdi
0x180066e3d  jnz     short loc_180066E5E
0x180066e3f  mov     rcx, [rsp+58h+Buffer]; hMem
0x180066e44  test    rcx, rcx
0x180066e47  jnz     short loc_180066E69
0x180066e49  mov     rbx, [rsp+58h+arg_0]
0x180066e4e  xor     eax, eax
0x180066e50  mov     rbp, [rsp+58h+arg_8]
0x180066e55  add     rsp, 40h
0x180066e59  pop     r14
0x180066e5b  pop     rdi
0x180066e5c  pop     rsi
0x180066e5d  retn
0x180066e5e  mov     rcx, rdi; hLibModule
0x180066e61  call    cs:__imp_FreeLibrary
0x180066e67  jmp     short loc_180066E3F
0x180066e69  call    cs:__imp_LocalFree
0x180066e6f  jmp     short loc_180066E49
0x180066e71  xor     edx, edx; hFile
0x180066e73  mov     rcx, rax; lpLibFileName
0x180066e76  lea     r8d, [rdx+22h]; dwFlags
0x180066e7a  call    cs:__imp_LoadLibraryExW
0x180066e80  mov     rdi, rax
0x180066e83  test    rax, rax
0x180066e86  jz      short loc_180066E92
0x180066e88  mov     ecx, 0B00h
0x180066e8d  jmp     loc_180066DC2
0x180066e92  or      r9, 0FFFFFFFFFFFFFFFFh
0x180066e96  inc     r9
0x180066e99  cmp     [rsi+r9*2], r14w
0x180066e9e  jnz     short loc_180066E96
0x180066ea0  mov     r8d, r9d; unsigned int
0x180066ea3  mov     rdx, rsi; wchar_t *
0x180066ea6  mov     rcx, rbx; this
0x180066ea9  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x180066eae  mov     edx, ebp
0x180066eb0  mov     rcx, rbx; this
0x180066eb3  call    ??$AppendInteger@$0BA@I@EmdStringBuffer@@AEAAXI@Z; EmdStringBuffer::AppendInteger<16,uint>(uint)
0x180066eb8  jmp     loc_180066E22
```
