# CVolume::RaiseIfWriteProtectedVolume(void)

- ea: `0x18000da64`
- end: `0x18000da8a`
- name: `?RaiseIfWriteProtectedVolume@CVolume@@AEBAXXZ`
- size: `38`
- prototype: `void __fastcall(CVolume *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002488`
- `0x18000297c`
- `0x18000f548`

## callees

- `0x18000da64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000da7e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000da7e`

## pseudocode

```c
void __fastcall CVolume::RaiseIfWriteProtectedVolume(CVolume *this)
{
  if ( (*((_BYTE *)this + 344) & 1) != 0 )
  {
    RaiseException(0x8000FFFF, 0, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x18000da64  sub     rsp, 28h
0x18000da68  test    byte ptr [rcx+158h], 1
0x18000da6f  jz      short loc_18000DA85
0x18000da71  xor     r9d, r9d; lpArguments
0x18000da74  xor     r8d, r8d; nNumberOfArguments
0x18000da77  xor     edx, edx; dwExceptionFlags
0x18000da79  mov     ecx, 8000FFFFh; dwExceptionCode
0x18000da7e  call    cs:__imp_RaiseException
0x18000da84  int     3; Trap to Debugger
0x18000da85  add     rsp, 28h
0x18000da89  retn
```
