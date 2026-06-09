# CRegistry::SetDefaultValues(void)

- ea: `0x180003ef0`
- end: `0x180003f21`
- name: `?SetDefaultValues@CRegistry@@AEAAXXZ`
- size: `49`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800034f0`
- `0x180003958`
- `0x18001d034`

## callees

- `0x180003f28`

## pseudocode

```c
void __fastcall CRegistry::SetDefaultValues(CRegistry *this)
{
  *((_QWORD *)this + 70) = 260;
  *((_WORD *)this + 19) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 146) = 0;
  *((_DWORD *)this + 8) = 0;
  CHString::Empty((CRegistry *)((char *)this + 24));
}

```

## disassembly

```asm
0x180003ef0  xor     edx, edx
0x180003ef2  mov     qword ptr [rcx+230h], 104h
0x180003efd  mov     [rcx+26h], dx
0x180003f01  mov     [rcx+238h], rdx
0x180003f08  mov     [rcx+240h], rdx
0x180003f0f  mov     [rcx+248h], edx
0x180003f15  mov     [rcx+20h], edx
0x180003f18  add     rcx, 18h; this
0x180003f1c  jmp     ?Empty@CHString@@QEAAXXZ; CHString::Empty(void)
```
