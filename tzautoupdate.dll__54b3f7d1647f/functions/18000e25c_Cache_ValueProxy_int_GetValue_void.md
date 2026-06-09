# Cache::ValueProxy<int>::GetValue(void)

- ea: `0x18000e25c`
- end: `0x18000e291`
- name: `?GetValue@?$ValueProxy@H@Cache@@QEBAAEBHXZ`
- size: `53`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dc80`
- `0x180013aa0`

## callees

- `0x180002960`
- `0x18000dae0`
- `0x18000e25c`

## pseudocode

```c
__int64 __fastcall Cache::ValueProxy<int>::GetValue(__int64 *a1)
{
  __int64 result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  result = *a1;
  if ( !*(_BYTE *)(*a1 + 4) )
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
0x18000e25c  sub     rsp, 48h
0x18000e260  mov     rax, [rcx]
0x18000e263  cmp     byte ptr [rax+4], 0
0x18000e267  jnz     short loc_18000E28C
0x18000e269  lea     rdx, aValueMustBeSet; "value must be set before it can be retr"...
0x18000e270  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000e275  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18000e27a  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18000e281  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e286  call    _CxxThrowException_0
0x18000e28c  add     rsp, 48h
0x18000e290  retn
```
