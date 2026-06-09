# mi::MiCreator<mi::MiInstance>::Create(mi::MiInstance const &,bool)

- ea: `0x180011ab4`
- end: `0x180011afe`
- name: `?Create@?$MiCreator@VMiInstance@mi@@@mi@@SA?AVMiInstance@2@AEBV32@_N@Z`
- size: `74`
- prototype: `__int64 __fastcall(mi::MiInstance *this)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011784`
- `0x180012f18`
- `0x180020800`
- `0x180020ac0`
- `0x180021210`
- `0x1800297c8`
- `0x180029e34`

## callees

- `0x180011ab4`
- `0x180026aec`
- `0x180027154`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
mi::MiInstance *__fastcall mi::MiCreator<mi::MiInstance>::Create(mi::MiInstance *this, __int64 a2)
{
  const struct _MI_Instance **v3; // r11

  mi::MiInstance::MiInstance(this, a2 + 16, a2 + 32, 0);
  if ( *v3 )
    mi::MiInstance::Attach(this, *v3);
  return this;
}

```

## disassembly

```asm
0x180011ab4  mov     [rsp+arg_0], rcx
0x180011ab9  push    rbx
0x180011aba  sub     rsp, 30h
0x180011abe  mov     r11, rdx
0x180011ac1  mov     rbx, rcx
0x180011ac4  mov     [rsp+38h+var_18], 0
0x180011acc  lea     r8, [rdx+20h]
0x180011ad0  add     rdx, 10h
0x180011ad4  xor     r9d, r9d
0x180011ad7  call    ??0MiInstance@mi@@AEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@3@_N@Z; mi::MiInstance::MiInstance(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,bool)
0x180011adc  mov     [rsp+38h+var_18], 1
0x180011ae4  mov     rdx, [r11]; struct _MI_Instance *
0x180011ae7  test    rdx, rdx
0x180011aea  jz      short loc_180011AF4
0x180011aec  mov     rcx, rbx; this
0x180011aef  call    ?Attach@MiInstance@mi@@QEAAXPEBU_MI_Instance@@@Z; mi::MiInstance::Attach(_MI_Instance const *)
0x180011af4  mov     rax, rbx
0x180011af7  add     rsp, 30h
0x180011afb  pop     rbx
0x180011afc  retn
```
