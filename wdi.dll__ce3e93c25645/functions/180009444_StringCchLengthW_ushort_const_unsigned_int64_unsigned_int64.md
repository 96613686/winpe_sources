# StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)

- ea: `0x180009444`
- end: `0x18000946e`
- name: `?StringCchLengthW@@YAJPEBG_KPEA_K@Z`
- size: `42`
- prototype: `HRESULT __fastcall(const unsigned __int16 *, size_t, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800098e0`
- `0x18000bff0`
- `0x18000ed58`

## callees

- `0x180009444`
- `0x180009500`

## pseudocode

```c
HRESULT __fastcall StringCchLengthW(const unsigned __int16 *a1, size_t a2, unsigned __int64 *a3)
{
  HRESULT result; // eax

  if ( a1 )
  {
    result = StringLengthWorkerW(a1, a2, a3);
    if ( result >= 0 )
      return result;
  }
  else
  {
    result = -2147024809;
  }
  if ( a3 )
    *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180009444  sub     rsp, 28h
0x180009448  test    rcx, rcx
0x18000944b  jz      short loc_180009458
0x18000944d  call    StringLengthWorkerW
0x180009452  test    eax, eax
0x180009454  jns     short loc_180009469
0x180009456  jmp     short loc_18000945D
0x180009458  mov     eax, 80070057h
0x18000945d  test    r8, r8
0x180009460  jz      short loc_180009469
0x180009462  mov     qword ptr [r8], 0
0x180009469  add     rsp, 28h
0x18000946d  retn
```
