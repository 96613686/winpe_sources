# CTrkWksConfiguration::~CTrkWksConfiguration(void)

- ea: `0x18000ef2c`
- end: `0x18000ef47`
- name: `??1CTrkWksConfiguration@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(CTrkWksConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ef50`

## callees

- `0x180007440`
- `0x18000f704`

## pseudocode

```c
void __fastcall CTrkWksConfiguration::~CTrkWksConfiguration(CTrkWksConfiguration *this)
{
  CTrkWksConfiguration::UnInitialize(this);
  CTrkConfiguration::UnInitialize(this);
}

```

## disassembly

```asm
0x18000ef2c  push    rbx
0x18000ef2e  sub     rsp, 20h
0x18000ef32  mov     rbx, rcx
0x18000ef35  call    ?UnInitialize@CTrkWksConfiguration@@QEAAXXZ
0x18000ef3a  mov     rcx, rbx; this
0x18000ef3d  add     rsp, 20h
0x18000ef41  pop     rbx
0x18000ef42  jmp     ?UnInitialize@CTrkConfiguration@@QEAAXXZ
```
