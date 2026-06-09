# CWsmLogConfig::GetData(void)

- ea: `0x14000aa00`
- end: `0x14000aa39`
- name: `?GetData@CWsmLogConfig@@UEBAPEBEXZ`
- size: `57`
- prototype: `const unsigned __int8 *__fastcall(CWsmLogConfig *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000aa00`
- `0x14000f9e0`

## pseudocode

```c
__int64 (__fastcall **__fastcall CWsmLogConfig::GetData(__int64 (__fastcall ***this)(char *)))(char *)
{
  _QWORD *v2; // rax

  v2 = (_QWORD *)(**(this - 1))((char *)this - 8);
  if ( v2 && *v2 || v2[1] )
    return this[1];
  else
    return 0;
}

```

## disassembly

```asm
0x14000aa00  push    rbx
0x14000aa02  sub     rsp, 20h
0x14000aa06  mov     rbx, rcx
0x14000aa09  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000aa0d  mov     rax, [rcx]
0x14000aa10  mov     rax, [rax]
0x14000aa13  call    _guard_dispatch_icall
0x14000aa18  test    rax, rax
0x14000aa1b  jz      short loc_14000AA23
0x14000aa1d  cmp     qword ptr [rax], 0
0x14000aa21  jnz     short loc_14000AA2A
0x14000aa23  cmp     qword ptr [rax+8], 0
0x14000aa28  jbe     short loc_14000AA30
0x14000aa2a  mov     rax, [rbx+8]
0x14000aa2e  jmp     short loc_14000AA32
0x14000aa30  xor     eax, eax
0x14000aa32  add     rsp, 20h
0x14000aa36  pop     rbx
0x14000aa37  retn
```
