# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000b710`
- end: `0x18000b740`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `48`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007cb4`
- `0x18000bba4`
- `0x1800157d4`

## callees

- `0x180004afc`
- `0x18000b710`
- `0x18000b874`

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
0x18000b710  sub     rsp, 38h
0x18000b714  call    StringValidateDestW
0x18000b719  mov     r9d, eax
0x18000b71c  test    eax, eax
0x18000b71e  js      short loc_18000B72D
0x18000b720  mov     r9, r8; pszSrc
0x18000b723  call    StringCopyWorkerW
0x18000b728  mov     r9d, eax
0x18000b72b  jmp     short loc_18000B737
0x18000b72d  test    rdx, rdx
0x18000b730  jz      short loc_18000B737
0x18000b732  xor     eax, eax
0x18000b734  mov     [rcx], ax
0x18000b737  mov     eax, r9d
0x18000b73a  add     rsp, 38h
0x18000b73e  retn
```
