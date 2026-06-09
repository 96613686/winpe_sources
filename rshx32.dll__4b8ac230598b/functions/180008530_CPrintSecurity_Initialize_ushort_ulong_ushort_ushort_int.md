# CPrintSecurity::Initialize(ushort *,ulong,ushort *,ushort *,int)

- ea: `0x180008530`
- end: `0x18000853c`
- name: `?Initialize@CPrintSecurity@@UEAAJPEAGK00H@Z`
- size: `12`
- prototype: `int __fastcall(CPrintSecurity *this, unsigned __int16 *, int, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c2c0`

## pseudocode

```c
int __fastcall CPrintSecurity::Initialize(
        CPrintSecurity *this,
        unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6)
{
  return CSecurityInformation::Initialize(this, a2, a3 | 0x600, a4, a5, a6);
}

```

## disassembly

```asm
0x180008530  or      r8d, 600h; unsigned int
0x180008537  jmp     ?Initialize@CSecurityInformation@@UEAAJPEAGK00H@Z; CSecurityInformation::Initialize(ushort *,ulong,ushort *,ushort *,int)
```
