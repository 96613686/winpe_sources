# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x180014134`
- end: `0x180014151`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `29`
- prototype: `_com_error *__fastcall(_com_error *this, int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180014208`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, int a2, struct IErrorInfo *a3)
{
  *(_QWORD *)this = &_com_error::`vftable';
  *((_DWORD *)this + 2) = a2;
  *((_QWORD *)this + 2) = a3;
  *((_QWORD *)this + 3) = 0;
  return this;
}

```

## disassembly

```asm
0x180014134  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001413b  mov     [rcx], rax
0x18001413e  mov     [rcx+8], edx
0x180014141  mov     [rcx+10h], r8
0x180014145  mov     qword ptr [rcx+18h], 0
0x18001414d  mov     rax, rcx
0x180014150  retn
```
