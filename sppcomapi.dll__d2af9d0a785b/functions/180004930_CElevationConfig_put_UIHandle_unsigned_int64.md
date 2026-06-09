# CElevationConfig::put_UIHandle(unsigned __int64)

- ea: `0x180004930`
- end: `0x18000494a`
- name: `?put_UIHandle@CElevationConfig@@UEAAJ_K@Z`
- size: `26`
- prototype: `__int64 __fastcall(CElevationConfig *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180004288`

## pseudocode

```c
__int64 __fastcall CElevationConfig::put_UIHandle(CElevationConfig *this, __int64 a2)
{
  *((_QWORD *)this + 19) = a2;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  return 0;
}

```

## disassembly

```asm
0x180004930  sub     rsp, 28h
0x180004934  mov     [rcx+98h], rdx
0x18000493b  xor     ecx, ecx
0x18000493d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004942  xor     eax, eax
0x180004944  add     rsp, 28h
0x180004948  retn
```
