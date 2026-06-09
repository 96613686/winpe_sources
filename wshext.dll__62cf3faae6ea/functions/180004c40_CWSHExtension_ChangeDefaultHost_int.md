# CWSHExtension::ChangeDefaultHost(int)

- ea: `0x180004c40`
- end: `0x180004c47`
- name: `?ChangeDefaultHost@CWSHExtension@@UEAAJH@Z`
- size: `7`
- prototype: `int(CWSHExtension *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000494c`

## pseudocode

```c
int __fastcall CWSHExtension::ChangeDefaultHost(CWSHExtension *this, int a2)
{
  return ChangeDefaultHost(a2);
}

```

## disassembly

```asm
0x180004c40  mov     ecx, edx; int
0x180004c42  jmp     ?ChangeDefaultHost@@YAJH@Z; ChangeDefaultHost(int)
```
