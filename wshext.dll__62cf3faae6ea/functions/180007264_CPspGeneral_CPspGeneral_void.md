# CPspGeneral::CPspGeneral(void)

- ea: `0x180007264`
- end: `0x1800072bd`
- name: `??0CPspGeneral@@QEAA@XZ`
- size: `89`
- prototype: `CPspGeneral *__fastcall(CPspGeneral *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006160`
- `0x180006440`
- `0x180009e90`

## callees

- `0x18000ac84`

## pseudocode

```c
CPspGeneral *__fastcall CPspGeneral::CPspGeneral(CPspGeneral *this)
{
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 20000;
  *((_QWORD *)this + 4) = 20000;
  *(_QWORD *)this = &CPspGeneral::`vftable';
  *((_BYTE *)this + 40) = 0;
  CSettings::CSettings((CPspGeneral *)((char *)this + 1092));
  CSettings::CSettings((CPspGeneral *)((char *)this + 1640));
  CSettings::CSettings((CPspGeneral *)((char *)this + 2188));
  return this;
}

```

## disassembly

```asm
0x180007264  push    rbx
0x180007266  sub     rsp, 20h
0x18000726a  mov     eax, 4E20h
0x18000726f  mov     qword ptr [rcx+10h], 0
0x180007277  mov     [rcx+18h], rax
0x18000727b  mov     rbx, rcx
0x18000727e  mov     [rcx+20h], rax
0x180007282  lea     rax, ??_7CPspGeneral@@6B@; const CPspGeneral::`vftable'
0x180007289  mov     [rcx], rax
0x18000728c  mov     byte ptr [rcx+28h], 0
0x180007290  add     rcx, 444h; this
0x180007297  call    ??0CSettings@@QEAA@XZ; CSettings::CSettings(void)
0x18000729c  lea     rcx, [rbx+668h]; this
0x1800072a3  call    ??0CSettings@@QEAA@XZ; CSettings::CSettings(void)
0x1800072a8  lea     rcx, [rbx+88Ch]; this
0x1800072af  call    ??0CSettings@@QEAA@XZ; CSettings::CSettings(void)
0x1800072b4  mov     rax, rbx
0x1800072b7  add     rsp, 20h
0x1800072bb  pop     rbx
0x1800072bc  retn
```
