# CACHED_USER_SID::CACHED_USER_SID(void)

- ea: `0x180002b64`
- end: `0x180002b81`
- name: `??0CACHED_USER_SID@@QEAA@XZ`
- size: `29`
- prototype: `CACHED_USER_SID *__fastcall(CACHED_USER_SID *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1800032f8`

## pseudocode

```c
CACHED_USER_SID *__fastcall CACHED_USER_SID::CACHED_USER_SID(CACHED_USER_SID *this)
{
  *((_QWORD *)this + 4) = this;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 10) = 32;
  *((_WORD *)this + 22) = 256;
  *((_DWORD *)this + 12) = 0;
  return this;
}

```

## disassembly

```asm
0x180002b64  xor     eax, eax
0x180002b66  mov     [rcx+20h], rcx
0x180002b6a  mov     [rcx], rax
0x180002b6d  mov     dword ptr [rcx+28h], 20h ; ' '
0x180002b74  mov     word ptr [rcx+2Ch], 100h
0x180002b7a  mov     [rcx+30h], eax
0x180002b7d  mov     rax, rcx
0x180002b80  retn
```
