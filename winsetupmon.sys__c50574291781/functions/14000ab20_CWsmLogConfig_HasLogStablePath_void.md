# CWsmLogConfig::HasLogStablePath(void)

- ea: `0x14000ab20`
- end: `0x14000ab46`
- name: `?HasLogStablePath@CWsmLogConfig@@UEBAEXZ`
- size: `38`
- prototype: `unsigned __int8 __fastcall(CWsmLogConfig *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000ab20`
- `0x14000f9e0`

## pseudocode

```c
bool __fastcall CWsmLogConfig::HasLogStablePath(CWsmLogConfig *this)
{
  _QWORD *v1; // rax

  v1 = (_QWORD *)(**(__int64 (__fastcall ***)(CWsmLogConfig *))this)(this);
  return v1 && *v1;
}

```

## disassembly

```asm
0x14000ab20  sub     rsp, 28h
0x14000ab24  mov     rax, [rcx]
0x14000ab27  mov     rax, [rax]
0x14000ab2a  call    _guard_dispatch_icall
0x14000ab2f  test    rax, rax
0x14000ab32  jz      short loc_14000AB3E
0x14000ab34  cmp     qword ptr [rax], 0
0x14000ab38  jz      short loc_14000AB3E
0x14000ab3a  mov     al, 1
0x14000ab3c  jmp     short loc_14000AB40
0x14000ab3e  xor     eax, eax
0x14000ab40  add     rsp, 28h
0x14000ab44  retn
```
