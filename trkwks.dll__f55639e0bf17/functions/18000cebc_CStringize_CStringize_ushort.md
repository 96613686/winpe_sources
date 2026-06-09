# CStringize::CStringize(ushort)

- ea: `0x18000cebc`
- end: `0x18000ceef`
- name: `??0CStringize@@QEAA@G@Z`
- size: `51`
- prototype: `CStringize *__fastcall(CStringize *__hidden this, unsigned __int16)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002488`
- `0x180002b50`
- `0x180003798`
- `0x180006a80`
- `0x18000c158`
- `0x18000c430`
- `0x18000cd40`
- `0x18000f22c`

## callees

- `0x18000b520`

## pseudocode

```c
CStringize *__fastcall CStringize::CStringize(CStringize *this, unsigned __int16 a2)
{
  *(_WORD *)this = 0;
  *((_QWORD *)this + 130) = this;
  StringCchPrintfW((unsigned __int16 *)this, 0x208u, L"%c", a2);
  return this;
}

```

## disassembly

```asm
0x18000cebc  push    rbx
0x18000cebe  sub     rsp, 20h
0x18000cec2  xor     eax, eax
0x18000cec4  movzx   r9d, dx
0x18000cec8  mov     edx, 208h; unsigned __int64
0x18000cecd  mov     [rcx], ax
0x18000ced0  lea     r8, aC; "%c"
0x18000ced7  mov     [rcx+410h], rcx
0x18000cede  mov     rbx, rcx
0x18000cee1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cee6  mov     rax, rbx
0x18000cee9  add     rsp, 20h
0x18000ceed  pop     rbx
0x18000ceee  retn
```
