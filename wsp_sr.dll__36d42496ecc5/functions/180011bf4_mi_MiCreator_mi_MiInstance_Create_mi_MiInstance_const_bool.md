# mi::MiCreator<mi::MiInstance>::Create(mi::MiInstance const &,bool)

- ea: `0x180011bf4`
- end: `0x180011c3e`
- name: `?Create@?$MiCreator@VMiInstance@mi@@@mi@@SA?AVMiInstance@2@AEBV32@_N@Z`
- size: `74`
- prototype: `mi::MiInstance *__fastcall(mi::MiInstance *this, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800118c0`
- `0x180013048`
- `0x1800206a8`
- `0x18002095c`
- `0x180021080`
- `0x18002933c`
- `0x18002998c`

## callees

- `0x180011bf4`
- `0x1800267a8`
- `0x180026dfc`

## pseudocode

```c
mi::MiInstance *__fastcall mi::MiCreator<mi::MiInstance>::Create(mi::MiInstance *this, __int64 a2)
{
  const struct _MI_Instance **v3; // r11

  mi::MiInstance::MiInstance(this, a2 + 16, a2 + 32, 0, 0);
  if ( *v3 )
    mi::MiInstance::Attach(this, *v3);
  return this;
}

```

## disassembly

```asm
0x180011bf4  mov     [rsp+arg_0], rcx
0x180011bf9  push    rbx
0x180011bfa  sub     rsp, 30h
0x180011bfe  mov     r11, rdx
0x180011c01  mov     rbx, rcx
0x180011c04  mov     [rsp+38h+var_18], 0
0x180011c0c  lea     r8, [rdx+20h]
0x180011c10  add     rdx, 10h
0x180011c14  xor     r9d, r9d
0x180011c17  call    ??0MiInstance@mi@@AEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@3@_N@Z; mi::MiInstance::MiInstance(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,bool)
0x180011c1c  mov     [rsp+38h+var_18], 1
0x180011c24  mov     rdx, [r11]; struct _MI_Instance *
0x180011c27  test    rdx, rdx
0x180011c2a  jz      short loc_180011C34
0x180011c2c  mov     rcx, rbx; this
0x180011c2f  call    ?Attach@MiInstance@mi@@QEAAXPEBU_MI_Instance@@@Z; mi::MiInstance::Attach(_MI_Instance const *)
0x180011c34  mov     rax, rbx
0x180011c37  add     rsp, 30h
0x180011c3b  pop     rbx
0x180011c3c  retn
```
