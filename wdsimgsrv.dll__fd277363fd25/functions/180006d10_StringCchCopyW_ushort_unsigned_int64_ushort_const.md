# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006d10`
- end: `0x180006d41`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `49`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003dc4`
- `0x180007880`
- `0x18000bdc4`
- `0x18000c3f8`
- `0x18000cdc8`

## callees

- `0x180006d10`
- `0x180006d48`

## pseudocode

```c
HRESULT __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  HRESULT result; // eax
  size_t v4; // [rsp+20h] [rbp-18h]

  if ( a2 - 1 <= 0x7FFFFFFE )
    return StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v4);
  result = -2147024809;
  if ( a2 )
    *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180006d10  sub     rsp, 38h
0x180006d14  lea     rax, [rdx-1]
0x180006d18  cmp     rax, 7FFFFFFEh
0x180006d1e  jbe     short loc_180006D33
0x180006d20  xor     r8d, r8d; pcchNewDestLength
0x180006d23  mov     eax, 80070057h
0x180006d28  test    rdx, rdx
0x180006d2b  jz      short loc_180006D3B
0x180006d2d  mov     [rcx], r8w
0x180006d31  jmp     short loc_180006D3B
0x180006d33  mov     r9, r8; pszSrc
0x180006d36  call    StringCopyWorkerW
0x180006d3b  add     rsp, 38h
0x180006d3f  retn
```
