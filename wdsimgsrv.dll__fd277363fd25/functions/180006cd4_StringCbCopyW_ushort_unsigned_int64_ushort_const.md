# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006cd4`
- end: `0x180006d08`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `52`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007120`
- `0x18000fe8c`

## callees

- `0x180006cd4`
- `0x180006d48`

## pseudocode

```c
HRESULT __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, size_t *a3)
{
  size_t v3; // rdx
  HRESULT result; // eax
  size_t v5; // [rsp+20h] [rbp-18h]

  v3 = a2 >> 1;
  if ( v3 - 1 <= 0x7FFFFFFE )
    return StringCopyWorkerW(a1, v3, a3, (STRSAFE_PCNZWCH)a3, v5);
  result = -2147024809;
  if ( v3 )
    *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180006cd4  sub     rsp, 38h
0x180006cd8  shr     rdx, 1; cchDest
0x180006cdb  lea     rax, [rdx-1]
0x180006cdf  cmp     rax, 7FFFFFFEh
0x180006ce5  jbe     short loc_180006CFA
0x180006ce7  xor     r8d, r8d; pcchNewDestLength
0x180006cea  mov     eax, 80070057h
0x180006cef  test    rdx, rdx
0x180006cf2  jz      short loc_180006D02
0x180006cf4  mov     [rcx], r8w
0x180006cf8  jmp     short loc_180006D02
0x180006cfa  mov     r9, r8; pszSrc
0x180006cfd  call    StringCopyWorkerW
0x180006d02  add     rsp, 38h
0x180006d06  retn
```
