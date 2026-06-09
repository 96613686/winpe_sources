# windiag::system_exception::what(void)

- ea: `0x18003ecb0`
- end: `0x18003ed78`
- name: `?what@system_exception@windiag@@UEBAPEBDXZ`
- size: `200`
- prototype: `const char *__fastcall(windiag::system_exception *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18003dc34`
- `0x18003ecb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ed3f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ed3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003ed1b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003ed1b`

## pseudocode

```c
const char *__fastcall windiag::system_exception::what(windiag::system_exception *this, __int64 a2, const void *a3)
{
  char *v4; // rax
  __int64 v5; // rdi
  int v6; // esi
  __int64 v7; // rbp
  HMODULE Library; // rax
  const void *v9; // r8
  HMODULE v10; // r14
  const char *result; // rax

  if ( !*((_QWORD *)this + 133) )
  {
    v4 = windiag::format_error(*((_QWORD *)this + 3), *((_QWORD *)this + 132), a3);
    *((_QWORD *)this + 133) = v4;
    if ( !v4 && !*((_QWORD *)this + 132) )
    {
      v5 = windiag::system_error_modules;
      v6 = *((_WORD *)this + 13) & 0x1FFF;
      v7 = qword_1800BECE0;
      while ( v5 != v7 )
      {
        if ( v6 == *(_DWORD *)v5 )
        {
          Library = LoadLibraryExA(*(LPCSTR *)(v5 + 8), 0, 0x803u);
          v10 = Library;
          if ( Library )
          {
            *((_QWORD *)this + 133) = windiag::format_error(*((_QWORD *)this + 3), (__int64)Library, v9);
            FreeLibrary(v10);
            if ( *((_QWORD *)this + 133) )
              break;
          }
        }
        v5 += 16;
      }
    }
  }
  result = "<n/a>";
  if ( *((_QWORD *)this + 133) )
    return (const char *)*((_QWORD *)this + 133);
  return result;
}

```

## disassembly

```asm
0x18003ecb0  push    rbx
0x18003ecb2  push    rbp
0x18003ecb3  push    rsi
0x18003ecb4  push    rdi
0x18003ecb5  push    r14
0x18003ecb7  sub     rsp, 20h
0x18003ecbb  cmp     qword ptr [rcx+428h], 0
0x18003ecc3  mov     rbx, rcx
0x18003ecc6  jnz     loc_18003ED58
0x18003eccc  mov     rdx, [rcx+420h]; __int64
0x18003ecd3  mov     rcx, [rcx+18h]; dwMessageId
0x18003ecd7  call    ?format_error@windiag@@YAPEAD_JPEBX@Z; windiag::format_error(__int64,void const *)
0x18003ecdc  mov     [rbx+428h], rax
0x18003ece3  test    rax, rax
0x18003ece6  jnz     short loc_18003ED58
0x18003ece8  cmp     [rbx+420h], rax
0x18003ecef  jnz     short loc_18003ED58
0x18003ecf1  movsx   esi, word ptr [rbx+1Ah]
0x18003ecf5  mov     rdi, cs:?system_error_modules@windiag@@3V?$vector@U?$pair@HPEBD@std@@V?$allocator@U?$pair@HPEBD@std@@@2@@std@@B; std::vector<std::pair<int,char const *>> const windiag::system_error_modules
0x18003ecfc  and     esi, 1FFFh
0x18003ed02  mov     rbp, cs:qword_1800BECE0
0x18003ed09  jmp     short loc_18003ED53
0x18003ed0b  cmp     esi, [rdi]
0x18003ed0d  jnz     short loc_18003ED4F
0x18003ed0f  mov     rcx, [rdi+8]; lpLibFileName
0x18003ed13  xor     edx, edx; hFile
0x18003ed15  mov     r8d, 803h; dwFlags
0x18003ed1b  call    cs:__imp_LoadLibraryExA
0x18003ed21  mov     r14, rax
0x18003ed24  test    rax, rax
0x18003ed27  jz      short loc_18003ED4F
0x18003ed29  mov     rcx, [rbx+18h]; dwMessageId
0x18003ed2d  mov     rdx, rax; __int64
0x18003ed30  call    ?format_error@windiag@@YAPEAD_JPEBX@Z; windiag::format_error(__int64,void const *)
0x18003ed35  mov     rcx, r14; hLibModule
0x18003ed38  mov     [rbx+428h], rax
0x18003ed3f  call    cs:__imp_FreeLibrary
0x18003ed45  cmp     qword ptr [rbx+428h], 0
0x18003ed4d  jnz     short loc_18003ED58
0x18003ed4f  add     rdi, 10h
0x18003ed53  cmp     rdi, rbp
0x18003ed56  jnz     short loc_18003ED0B
0x18003ed58  mov     rcx, [rbx+428h]
0x18003ed5f  lea     rax, aNA_1; "<n/a>"
0x18003ed66  test    rcx, rcx
0x18003ed69  cmovnz  rax, rcx
0x18003ed6d  add     rsp, 20h
0x18003ed71  pop     r14
0x18003ed73  pop     rdi
0x18003ed74  pop     rsi
0x18003ed75  pop     rbp
0x18003ed76  pop     rbx
0x18003ed77  retn
```
