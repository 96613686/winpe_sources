# TrkRaiseWin32Error(long)

- ea: `0x18000d038`
- end: `0x18000d058`
- name: `?TrkRaiseWin32Error@@YAXJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(signed int)`
- caller_count: `53`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c1c`
- `0x180001cb8`
- `0x180001d4c`
- `0x1800022d4`
- `0x180002c90`
- `0x180003180`
- `0x180004750`
- `0x1800048e0`
- `0x180004f90`
- `0x1800053b0`
- `0x180005590`
- `0x180005660`
- `0x180006700`
- `0x180006bf0`
- `0x180007b20`
- `0x180007cb0`
- `0x180008230`
- `0x180008430`
- `0x180008460`
- `0x180008960`
- `0x180008d10`
- `0x180009698`
- `0x180009800`
- `0x180009ce8`
- `0x180009ecc`
- `0x18000a27c`
- `0x18000a880`
- `0x18000a9d0`
- `0x18000aacc`
- `0x18000add0`
- `0x18000afcc`
- `0x18000b060`
- `0x18000b5b0`
- `0x18000b924`
- `0x18000baac`
- `0x18000c158`
- `0x18000cc64`
- `0x18000cfd0`
- `0x18000d020`
- `0x18000d060`
- `0x18000d0a4`
- `0x18000d268`
- `0x18000d594`
- `0x18000e7c0`
- `0x18000e8a8`
- `0x18000eac0`
- `0x18000ebec`
- `0x18000f548`
- `0x18000fdc8`
- `0x18000fe2c`

## callees

- `0x18000d038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d051`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d051`

## pseudocode

```c
void __fastcall __noreturn TrkRaiseWin32Error(signed int a1)
{
  if ( a1 > 0 )
    a1 = (unsigned __int16)a1 | 0x80070000;
  RaiseException(a1, 0, 0, 0);
  JUMPOUT(0x18000D057LL);
}

```

## disassembly

```asm
0x18000d038  sub     rsp, 28h
0x18000d03c  test    ecx, ecx
0x18000d03e  jle     short loc_18000D049
0x18000d040  movzx   ecx, cx
0x18000d043  or      ecx, 80070000h; dwExceptionCode
0x18000d049  xor     r9d, r9d; lpArguments
0x18000d04c  xor     r8d, r8d; nNumberOfArguments
0x18000d04f  xor     edx, edx; dwExceptionFlags
0x18000d051  call    cs:__imp_RaiseException
```
