# FormatMessageToBuffer

- ea: `0x18000f0e0`
- end: `0x18000f247`
- name: `FormatMessageToBuffer`
- size: `359`
- prototype: `__int64 __fastcall(DWORD dwMessageId, wchar_t *, LPCWSTR lpLibFileName, EmdStringBuffer *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000dcb0`

## callees

- `0x18000e7c0`
- `0x18000f0e0`
- `0x180012b70`
- `0x180023b05`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f1d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f1d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f229`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f229`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f133`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f133`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f23c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f23c`

## pseudocode

```c
__int64 __fastcall FormatMessageToBuffer(DWORD dwMessageId, wchar_t *a2, LPCWSTR lpLibFileName, EmdStringBuffer *this)
{
  HMODULE Library; // rdi
  DWORD v8; // ecx
  void *v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  unsigned int v12; // ecx
  __int64 v14; // r8
  char *Buffer; // [rsp+70h] [rbp+18h] BYREF

  Buffer = 0;
  if ( lpLibFileName )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0x22u);
    if ( !Library )
    {
LABEL_22:
      v14 = -1;
      do
        ++v14;
      while ( a2[v14] );
      EmdStringBuffer::AppendWide(this, a2, v14);
      EmdStringBuffer::AppendInteger<16,unsigned int>(this, dwMessageId);
      goto LABEL_9;
    }
    v8 = 2816;
  }
  else
  {
    Library = 0;
    v8 = 4864;
  }
  FormatMessageW(v8, Library, dwMessageId, 0, (LPWSTR)&Buffer, 0, 0);
  v9 = Buffer;
  if ( !Buffer )
    goto LABEL_22;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)&Buffer[2 * v10] );
  if ( (unsigned int)v10 >= 2 && *(_DWORD *)&Buffer[2 * (unsigned int)(v10 - 2)] == 655373 )
    LODWORD(v10) = v10 - 2;
  v11 = *((unsigned int *)this + 3);
  *((_DWORD *)this + 3) = v11 + v10;
  if ( (unsigned int)(v11 + v10) <= *((_DWORD *)this + 2) )
  {
    memcpy_0((void *)(*(_QWORD *)this + 2 * v11), v9, 2LL * (unsigned int)v10);
LABEL_9:
    v9 = Buffer;
  }
  v12 = *((_DWORD *)this + 3);
  *((_DWORD *)this + 3) = v12 + 1;
  if ( v12 + 1 <= *((_DWORD *)this + 2) )
  {
    *(_WORD *)(*(_QWORD *)this + 2LL * v12) = 0;
    v9 = Buffer;
  }
  if ( Library )
  {
    FreeLibrary(Library);
    v9 = Buffer;
  }
  if ( v9 )
    LocalFree(v9);
  return 0;
}

```

## disassembly

```asm
0x18000f0e0  mov     [rsp+arg_0], rbx
0x18000f0e5  mov     [rsp+arg_8], rbp
0x18000f0ea  push    rsi
0x18000f0eb  push    rdi
0x18000f0ec  push    r14
0x18000f0ee  sub     rsp, 40h
0x18000f0f2  xor     r14d, r14d
0x18000f0f5  mov     rbx, r9
0x18000f0f8  mov     [rsp+58h+Buffer], r14
0x18000f0fd  mov     rax, r8
0x18000f100  mov     rsi, rdx
0x18000f103  mov     ebp, ecx
0x18000f105  test    r8, r8
0x18000f108  jnz     loc_18000F1C8
0x18000f10e  mov     edi, r14d
0x18000f111  mov     ecx, 1300h; dwFlags
0x18000f116  mov     [rsp+58h+Arguments], r14; Arguments
0x18000f11b  lea     rax, [rsp+58h+Buffer]
0x18000f120  mov     [rsp+58h+nSize], r14d; nSize
0x18000f125  xor     r9d, r9d; dwLanguageId
0x18000f128  mov     r8d, ebp; dwMessageId
0x18000f12b  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x18000f130  mov     rdx, rdi; lpSource
0x18000f133  call    cs:__imp_FormatMessageW
0x18000f139  mov     r9, [rsp+58h+Buffer]
0x18000f13e  test    r9, r9
0x18000f141  jz      loc_18000F1FE
0x18000f147  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f14b  inc     r8
0x18000f14e  cmp     [r9+r8*2], r14w
0x18000f153  jnz     short loc_18000F14B
0x18000f155  cmp     r8d, 2
0x18000f159  jnb     loc_18000F1E9
0x18000f15f  mov     ecx, [rbx+0Ch]
0x18000f162  lea     eax, [rcx+r8]
0x18000f166  mov     [rbx+0Ch], eax
0x18000f169  cmp     eax, [rbx+8]
0x18000f16c  ja      short loc_18000F188
0x18000f16e  mov     rax, [rbx]
0x18000f171  mov     rdx, r9; Src
0x18000f174  mov     r8d, r8d
0x18000f177  add     r8, r8; Size
0x18000f17a  lea     rcx, [rax+rcx*2]; void *
0x18000f17e  call    memcpy_0
0x18000f183  mov     r9, [rsp+58h+Buffer]
0x18000f188  mov     ecx, [rbx+0Ch]
0x18000f18b  lea     eax, [rcx+1]
0x18000f18e  mov     [rbx+0Ch], eax
0x18000f191  cmp     eax, [rbx+8]
0x18000f194  ja      short loc_18000F1A5
0x18000f196  mov     edx, ecx
0x18000f198  mov     rcx, [rbx]
0x18000f19b  mov     [rcx+rdx*2], r14w
0x18000f1a0  mov     r9, [rsp+58h+Buffer]
0x18000f1a5  test    rdi, rdi
0x18000f1a8  jnz     short loc_18000F226
0x18000f1aa  test    r9, r9
0x18000f1ad  jnz     loc_18000F239
0x18000f1b3  mov     rbx, [rsp+58h+arg_0]
0x18000f1b8  xor     eax, eax
0x18000f1ba  mov     rbp, [rsp+58h+arg_8]
0x18000f1bf  add     rsp, 40h
0x18000f1c3  pop     r14
0x18000f1c5  pop     rdi
0x18000f1c6  pop     rsi
0x18000f1c7  retn
0x18000f1c8  xor     edx, edx; hFile
0x18000f1ca  mov     rcx, rax; lpLibFileName
0x18000f1cd  lea     r8d, [rdx+22h]; dwFlags
0x18000f1d1  call    cs:__imp_LoadLibraryExW
0x18000f1d7  mov     rdi, rax
0x18000f1da  test    rax, rax
0x18000f1dd  jz      short loc_18000F1FE
0x18000f1df  mov     ecx, 0B00h
0x18000f1e4  jmp     loc_18000F116
0x18000f1e9  lea     edx, [r8-2]
0x18000f1ed  cmp     dword ptr [r9+rdx*2], 0A000Dh
0x18000f1f5  cmovz   r8d, edx
0x18000f1f9  jmp     loc_18000F15F
0x18000f1fe  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f202  inc     r8; unsigned int
0x18000f205  cmp     [rsi+r8*2], r14w
0x18000f20a  jnz     short loc_18000F202
0x18000f20c  mov     rdx, rsi; wchar_t *
0x18000f20f  mov     rcx, rbx; this
0x18000f212  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x18000f217  mov     edx, ebp
0x18000f219  mov     rcx, rbx
0x18000f21c  call    ??$AppendInteger@$0BA@I@EmdStringBuffer@@AEAAXI@Z; EmdStringBuffer::AppendInteger<16,uint>(uint)
0x18000f221  jmp     loc_18000F183
0x18000f226  mov     rcx, rdi; hLibModule
0x18000f229  call    cs:__imp_FreeLibrary
0x18000f22f  mov     r9, [rsp+58h+Buffer]
0x18000f234  jmp     loc_18000F1AA
0x18000f239  mov     rcx, r9; hMem
0x18000f23c  call    cs:__imp_LocalFree
0x18000f242  jmp     loc_18000F1B3
```
