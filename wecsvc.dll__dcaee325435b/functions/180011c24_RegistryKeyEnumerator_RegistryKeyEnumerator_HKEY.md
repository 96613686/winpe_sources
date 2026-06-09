# RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *)

- ea: `0x180011c24`
- end: `0x180011c58`
- name: `??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@@Z`
- size: `52`
- prototype: `RegistryKeyEnumerator *__fastcall(RegistryKeyEnumerator *__hidden this, HKEY)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d15c`
- `0x1800155e8`
- `0x180015f78`
- `0x18001764c`
- `0x18001ab58`
- `0x18001b998`

## callees

- `0x180011fd8`

## pseudocode

```c
RegistryKeyEnumerator *__fastcall RegistryKeyEnumerator::RegistryKeyEnumerator(RegistryKeyEnumerator *this, HKEY a2)
{
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  RegistryKeyEnumerator::QueryInfoKey(this, a2);
  return this;
}

```

## disassembly

```asm
0x180011c24  mov     [rsp+arg_0], rcx
0x180011c29  push    rbx
0x180011c2a  sub     rsp, 20h
0x180011c2e  mov     rbx, rcx
0x180011c31  mov     [rcx], rdx
0x180011c34  xor     eax, eax
0x180011c36  mov     [rcx+8], eax
0x180011c39  mov     [rcx+10h], rax
0x180011c3d  mov     [rcx+18h], rax
0x180011c41  mov     [rcx+20h], rax
0x180011c45  mov     [rcx+28h], rax
0x180011c49  call    ?QueryInfoKey@RegistryKeyEnumerator@@AEAAXPEAUHKEY__@@@Z; RegistryKeyEnumerator::QueryInfoKey(HKEY__ *)
0x180011c4e  nop
0x180011c4f  mov     rax, rbx
0x180011c52  add     rsp, 20h
0x180011c56  pop     rbx
0x180011c57  retn
```
