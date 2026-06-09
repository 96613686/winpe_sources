# _CollectorService::PutSubscription_::_1_::catch$15

- ea: `0x180020923`
- end: `0x180020951`
- name: `_CollectorService::PutSubscription_::_1_::catch$15`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x18000195c`
- `0x1800120f8`
- `0x180020923`

## pseudocode

```c
void __fastcall __noreturn CollectorService::PutSubscription_::_1_::catch_15(__int64 a1, __int64 a2)
{
  if ( *(_BYTE *)(*(_QWORD *)(a2 + 80) + 40LL) )
    RegDeleteKeyRecursive(*(HKEY *)(a2 + 72), *(const unsigned __int16 **)(a2 + 96));
  throw;
}

```

## disassembly

```asm
0x180020923  mov     [rsp+arg_8], rdx
0x180020928  push    rbp
0x180020929  sub     rsp, 40h
0x18002092d  mov     rbp, rdx
0x180020930  mov     rax, [rbp+50h]
0x180020934  cmp     byte ptr [rax+28h], 0
0x180020938  jz      short loc_180020947
0x18002093a  mov     rdx, [rbp+60h]; unsigned __int16 *
0x18002093e  mov     rcx, [rbp+48h]; HKEY
0x180020942  call    ?RegDeleteKeyRecursive@@YAKPEAUHKEY__@@PEBG@Z; RegDeleteKeyRecursive(HKEY__ *,ushort const *)
0x180020947  xor     edx, edx; pThrowInfo
0x180020949  xor     ecx, ecx; pExceptionObject
0x18002094b  call    _CxxThrowException_0
```
