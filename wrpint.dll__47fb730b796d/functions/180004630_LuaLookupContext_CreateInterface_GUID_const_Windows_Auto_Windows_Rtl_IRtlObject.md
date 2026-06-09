# LuaLookupContext::CreateInterface(_GUID const &,Windows::Auto<Windows::Rtl::IRtlObject *> *)

- ea: `0x180004630`
- end: `0x180004675`
- name: `?CreateInterface@LuaLookupContext@@UEAAJAEBU_GUID@@PEAV?$Auto@PEAUIRtlObject@Rtl@Windows@@@Windows@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004630`

## pseudocode

```c
__int64 __fastcall LuaLookupContext::CreateInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  if ( (*a2 != *(_QWORD *)&GUID_38218435_079f_49e9_bb3f_149cb22b88cd.Data1
     || a2[1] != *(_QWORD *)GUID_38218435_079f_49e9_bb3f_149cb22b88cd.Data4)
    && (*a2 != *(_QWORD *)&GUID_86a72d18_2a36_428e_a31e_b4cc8b18ca42.Data1
     || a2[1] != *(_QWORD *)GUID_86a72d18_2a36_428e_a31e_b4cc8b18ca42.Data4) )
  {
    return 3221226169LL;
  }
  if ( *a3 )
    __debugbreak();
  *a3 = a1;
  return 0;
}

```

## disassembly

```asm
0x180004630  mov     rax, [rdx]
0x180004633  cmp     rax, qword ptr cs:_GUID_38218435_079f_49e9_bb3f_149cb22b88cd.Data1
0x18000463a  jnz     short loc_180004649
0x18000463c  mov     rax, [rdx+8]
0x180004640  cmp     rax, qword ptr cs:_GUID_38218435_079f_49e9_bb3f_149cb22b88cd.Data4
0x180004647  jz      short loc_180004662
0x180004649  mov     rax, [rdx]
0x18000464c  cmp     rax, qword ptr cs:_GUID_86a72d18_2a36_428e_a31e_b4cc8b18ca42.Data1
0x180004653  jnz     short loc_18000466F
0x180004655  mov     rax, [rdx+8]
0x180004659  cmp     rax, qword ptr cs:_GUID_86a72d18_2a36_428e_a31e_b4cc8b18ca42.Data4
0x180004660  jnz     short loc_18000466F
0x180004662  cmp     qword ptr [r8], 0
0x180004666  jz      short loc_180004669
0x180004668  int     3; Trap to Debugger
0x180004669  mov     [r8], rcx
0x18000466c  xor     eax, eax
0x18000466e  retn
0x18000466f  mov     eax, 0C00002B9h
0x180004674  retn
```
