# CElevationConfig::get_Mode(_ElevationConfigOptions *)

- ea: `0x180004840`
- end: `0x180004873`
- name: `?get_Mode@CElevationConfig@@UEAAJPEAW4_ElevationConfigOptions@@@Z`
- size: `51`
- prototype: `__int64 __fastcall(CElevationConfig *__hidden this, enum _ElevationConfigOptions *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004840`

## pseudocode

```c
__int64 __fastcall CElevationConfig::get_Mode(CElevationConfig *this, enum _ElevationConfigOptions *a2)
{
  unsigned int v2; // ebx

  if ( a2 )
  {
    v2 = 0;
    *(_DWORD *)a2 = *((_DWORD *)this + 34);
  }
  else
  {
    v2 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  return v2;
}

```

## disassembly

```asm
0x180004840  push    rbx
0x180004842  sub     rsp, 20h
0x180004846  test    rdx, rdx
0x180004849  jnz     short loc_180004859
0x18000484b  mov     ebx, 80070057h
0x180004850  mov     ecx, ebx
0x180004852  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180004857  jmp     short loc_180004863
0x180004859  mov     ecx, [rcx+88h]
0x18000485f  xor     ebx, ebx
0x180004861  mov     [rdx], ecx
0x180004863  mov     ecx, ebx
0x180004865  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000486a  mov     eax, ebx
0x18000486c  add     rsp, 20h
0x180004870  pop     rbx
0x180004871  retn
```
