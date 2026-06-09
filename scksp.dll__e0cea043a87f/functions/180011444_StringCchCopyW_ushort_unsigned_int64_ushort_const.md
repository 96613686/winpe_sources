# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180011444`
- end: `0x180011473`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d360`
- `0x180011974`
- `0x180013e10`
- `0x18001423c`
- `0x180015a5c`
- `0x1800199b0`
- `0x18001f61c`
- `0x18001fea4`
- `0x1800232ec`
- `0x180024250`
- `0x1800253c0`
- `0x180030e7c`
- `0x180032770`
- `0x1800361c0`

## callees

- `0x180011444`
- `0x180011518`
- `0x180011570`

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
0x180011444  sub     rsp, 38h
0x180011448  call    StringValidateDestW
0x18001144d  mov     r9d, eax
0x180011450  test    eax, eax
0x180011452  js      short loc_180011461
0x180011454  mov     r9, r8; pszSrc
0x180011457  call    StringCopyWorkerW
0x18001145c  mov     r9d, eax
0x18001145f  jmp     short loc_18001146B
0x180011461  test    rdx, rdx
0x180011464  jz      short loc_18001146B
0x180011466  xor     eax, eax
0x180011468  mov     [rcx], ax
0x18001146b  mov     eax, r9d
0x18001146e  add     rsp, 38h
0x180011472  retn
```
