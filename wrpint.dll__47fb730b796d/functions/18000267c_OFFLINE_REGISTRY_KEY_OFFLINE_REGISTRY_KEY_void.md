# OFFLINE_REGISTRY_KEY::OFFLINE_REGISTRY_KEY(void)

- ea: `0x18000267c`
- end: `0x18000268c`
- name: `??0OFFLINE_REGISTRY_KEY@@QEAA@XZ`
- size: `16`
- prototype: `OFFLINE_REGISTRY_KEY *__fastcall(OFFLINE_REGISTRY_KEY *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180002500`

## pseudocode

```c
OFFLINE_REGISTRY_KEY *__fastcall OFFLINE_REGISTRY_KEY::OFFLINE_REGISTRY_KEY(OFFLINE_REGISTRY_KEY *this)
{
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  return this;
}

```

## disassembly

```asm
0x18000267c  xor     eax, eax
0x18000267e  mov     [rcx], rax
0x180002681  mov     [rcx+8], eax
0x180002684  mov     [rcx+10h], rax
0x180002688  mov     rax, rcx
0x18000268b  retn
```
