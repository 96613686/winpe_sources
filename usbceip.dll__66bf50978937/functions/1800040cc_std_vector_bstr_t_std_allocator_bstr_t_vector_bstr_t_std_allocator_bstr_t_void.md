# std::vector<_bstr_t,std::allocator<_bstr_t>>::vector<_bstr_t,std::allocator<_bstr_t>>(void)

- ea: `0x1800040cc`
- end: `0x1800040dd`
- name: `??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ`
- size: `17`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180004240`
- `0x180004388`
- `0x180006d2c`
- `0x1800072b4`
- `0x180008290`
- `0x180008730`
- `0x1800089bc`
- `0x180008ac0`
- `0x180009260`
- `0x1800097ec`
- `0x180009b24`
- `0x18000a698`
- `0x18000aacc`
- `0x18000ab28`
- `0x18000ad38`
- `0x18000ad94`
- `0x18000adec`
- `0x18000ae48`
- `0x18000af94`
- `0x18000b140`
- `0x18000b5c8`
- `0x18000bc58`
- `0x18000bc7c`

## pseudocode

```c
_QWORD *__fastcall std::vector<_bstr_t>::vector<_bstr_t>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x1800040cc  xor     eax, eax
0x1800040ce  mov     [rcx], rax
0x1800040d1  mov     [rcx+8], rax
0x1800040d5  mov     [rcx+10h], rax
0x1800040d9  mov     rax, rcx
0x1800040dc  retn
```
