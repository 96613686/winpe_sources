# Cache::ValueProxy<double>::GetValue(void)

- ea: `0x180011230`
- end: `0x180011265`
- name: `?GetValue@?$ValueProxy@N@Cache@@QEBAAEBNXZ`
- size: `53`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180012178`
- `0x1800123b8`

## callees

- `0x180002960`
- `0x18000dae0`
- `0x180011230`

## pseudocode

```c
__int64 __fastcall Cache::ValueProxy<double>::GetValue(__int64 *a1)
{
  __int64 result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  result = *a1;
  if ( !*(_BYTE *)(*a1 + 8) )
  {
    std::logic_error::logic_error(
      (std::logic_error *)pExceptionObject,
      "value must be set before it can be retrieved (check IsSet)");
    throw (std::logic_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180011230  sub     rsp, 48h
0x180011234  mov     rax, [rcx]
0x180011237  cmp     byte ptr [rax+8], 0
0x18001123b  jnz     short loc_180011260
0x18001123d  lea     rdx, aValueMustBeSet; "value must be set before it can be retr"...
0x180011244  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180011249  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18001124e  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180011255  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001125a  call    _CxxThrowException_0
0x180011260  add     rsp, 48h
0x180011264  retn
```
