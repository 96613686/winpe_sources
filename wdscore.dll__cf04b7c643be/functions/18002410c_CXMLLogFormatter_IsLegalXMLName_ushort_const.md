# CXMLLogFormatter::IsLegalXMLName(ushort const *)

- ea: `0x18002410c`
- end: `0x1800241c2`
- name: `?IsLegalXMLName@CXMLLogFormatter@@CAHPEBG@Z`
- size: `182`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800240a0`

## callees

- `0x18002410c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002419b`
- `msvcrt!_wcsnicmp` at `0x18002419b`
- `msvcrt!iswctype` at `0x180024140`
- `msvcrt!iswctype` at `0x180024164`
- `msvcrt!iswctype` at `0x180024140`
- `msvcrt!iswctype` at `0x180024164`

## pseudocode

```c
_BOOL8 __fastcall CXMLLogFormatter::IsLegalXMLName(wchar_t *String1)
{
  wint_t v2; // bx
  wint_t *v3; // r14
  int v4; // esi

  if ( !String1 )
    return 0;
  v2 = *String1;
  v3 = String1;
  v4 = 0;
  while ( v2 )
  {
    if ( !iswctype(v2, 0x103u) && v2 != 95 && (!v4 || !iswctype(v2, 4u) && (unsigned __int16)(v2 - 45) > 1u) )
      return 0;
    ++v3;
    ++v4;
    v2 = *v3;
  }
  return _wcsnicmp(String1, L"XML", 3u) != 0;
}

```

## disassembly

```asm
0x18002410c  push    rbx
0x18002410e  push    rbp
0x18002410f  push    rsi
0x180024110  push    rdi
0x180024111  push    r14
0x180024113  push    r15
0x180024115  sub     rsp, 28h
0x180024119  xor     ebp, ebp
0x18002411b  mov     rdi, rcx
0x18002411e  test    rcx, rcx
0x180024121  jz      loc_1800241B2
0x180024127  movzx   ebx, word ptr [rcx]
0x18002412a  lea     r15d, [rbp+1]
0x18002412e  mov     r14, rcx
0x180024131  mov     esi, ebp
0x180024133  test    bx, bx
0x180024136  jz      short loc_18002418B
0x180024138  mov     edx, 103h; Type
0x18002413d  movzx   ecx, bx; C
0x180024140  call    cs:__imp_iswctype
0x180024147  nop     dword ptr [rax+rax+00h]
0x18002414c  test    eax, eax
0x18002414e  jnz     short loc_18002417E
0x180024150  mov     eax, 5Fh ; '_'
0x180024155  cmp     ax, bx
0x180024158  jz      short loc_18002417E
0x18002415a  test    esi, esi
0x18002415c  jz      short loc_1800241B2
0x18002415e  lea     edx, [rax-5Bh]; Type
0x180024161  movzx   ecx, bx; C
0x180024164  call    cs:__imp_iswctype
0x18002416b  nop     dword ptr [rax+rax+00h]
0x180024170  test    eax, eax
0x180024172  jnz     short loc_18002417E
0x180024174  sub     bx, 2Dh ; '-'
0x180024178  cmp     bx, r15w
0x18002417c  ja      short loc_1800241B2
0x18002417e  add     r14, 2
0x180024182  add     esi, r15d
0x180024185  movzx   ebx, word ptr [r14]
0x180024189  jmp     short loc_180024133
0x18002418b  mov     r8d, 3; MaxCount
0x180024191  lea     rdx, aXml; "XML"
0x180024198  mov     rcx, rdi; String1
0x18002419b  call    cs:__imp__wcsnicmp
0x1800241a2  nop     dword ptr [rax+rax+00h]
0x1800241a7  test    eax, eax
0x1800241a9  mov     ecx, ebp
0x1800241ab  setnz   cl
0x1800241ae  mov     eax, ecx
0x1800241b0  jmp     short loc_1800241B4
0x1800241b2  xor     eax, eax
0x1800241b4  add     rsp, 28h
0x1800241b8  pop     r15
0x1800241ba  pop     r14
0x1800241bc  pop     rdi
0x1800241bd  pop     rsi
0x1800241be  pop     rbp
0x1800241bf  pop     rbx
0x1800241c0  retn
```
