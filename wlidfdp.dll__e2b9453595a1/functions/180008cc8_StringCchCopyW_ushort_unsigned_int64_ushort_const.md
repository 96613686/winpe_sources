# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008cc8`
- end: `0x180008cf7`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005f40`
- `0x18000912c`

## callees

- `0x180008cc8`
- `0x180008d88`
- `0x180008e7c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  size_t v8; // [rsp+20h] [rbp-18h]

  v6 = StringValidateDestW(a1, 0x104u, (const size_t)a3);
  if ( v6 < 0 )
    *v4 = 0;
  else
    return (unsigned int)StringCopyWorkerW(v4, v3, v5, (STRSAFE_PCNZWCH)v5, v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008cc8  sub     rsp, 38h
0x180008ccc  mov     edx, 104h; cchDest
0x180008cd1  call    StringValidateDestW
0x180008cd6  mov     r9d, eax
0x180008cd9  test    eax, eax
0x180008cdb  js      short loc_180008CEA
0x180008cdd  mov     r9, r8; pszSrc
0x180008ce0  call    StringCopyWorkerW
0x180008ce5  mov     r9d, eax
0x180008ce8  jmp     short loc_180008CEF
0x180008cea  xor     eax, eax
0x180008cec  mov     [rcx], ax
0x180008cef  mov     eax, r9d
0x180008cf2  add     rsp, 38h
0x180008cf6  retn
```
