# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000ae10`
- end: `0x18000ae3f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007898`
- `0x18000b290`
- `0x180013f00`

## callees

- `0x1800047c8`
- `0x18000ae10`
- `0x18000af74`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  size_t v8; // [rsp+20h] [rbp-18h]

  v6 = StringValidateDestW(a1, a2, (const size_t)a3);
  if ( v6 < 0 )
  {
    if ( v3 )
      *v4 = 0;
  }
  else
  {
    return (unsigned int)StringCopyWorkerW(v4, v3, v5, (STRSAFE_PCNZWCH)v5, v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ae10  sub     rsp, 38h
0x18000ae14  call    StringValidateDestW
0x18000ae19  mov     r9d, eax
0x18000ae1c  test    eax, eax
0x18000ae1e  js      short loc_18000AE2D
0x18000ae20  mov     r9, r8; pszSrc
0x18000ae23  call    StringCopyWorkerW
0x18000ae28  mov     r9d, eax
0x18000ae2b  jmp     short loc_18000AE37
0x18000ae2d  test    rdx, rdx
0x18000ae30  jz      short loc_18000AE37
0x18000ae32  xor     eax, eax
0x18000ae34  mov     [rcx], ax
0x18000ae37  mov     eax, r9d
0x18000ae3a  add     rsp, 38h
0x18000ae3e  retn
```
