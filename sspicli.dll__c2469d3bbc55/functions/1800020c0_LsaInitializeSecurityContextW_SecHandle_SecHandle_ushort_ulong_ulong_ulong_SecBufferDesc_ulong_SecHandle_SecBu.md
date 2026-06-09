# LsaInitializeSecurityContextW(_SecHandle *,_SecHandle *,ushort *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *)

- ea: `0x1800020c0`
- end: `0x18000211f`
- name: `?LsaInitializeSecurityContextW@@YAJPEAU_SecHandle@@0PEAGKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(struct _SecHandle *, struct _SecHandle *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned int, struct _SecHandle *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002130`

## pseudocode

```c
__int64 __fastcall LsaInitializeSecurityContextW(
        struct _SecHandle *a1,
        struct _SecHandle *a2,
        const char *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        struct _SecBufferDesc *a7,
        unsigned int a8,
        struct _SecHandle *a9,
        struct _SecBufferDesc *a10,
        unsigned int *a11,
        union _LARGE_INTEGER *a12)
{
  unsigned int v13; // [rsp+20h] [rbp-58h]
  unsigned int v14; // [rsp+38h] [rbp-40h]

  return LsaInitializeSecurityContextCommon(a1, a2, a3, a4, v13, a6, a7, v14, a9, a10, a11, a12, 1u);
}

```

## disassembly

```asm
0x1800020c0  sub     rsp, 78h
0x1800020c4  mov     rax, [rsp+78h+arg_58]
0x1800020cc  mov     [rsp+78h+var_18], 1; unsigned __int8
0x1800020d1  mov     [rsp+78h+var_20], rax; union _LARGE_INTEGER *
0x1800020d6  mov     rax, [rsp+78h+arg_50]
0x1800020de  mov     [rsp+78h+var_28], rax; unsigned int *
0x1800020e3  mov     rax, [rsp+78h+arg_48]
0x1800020eb  mov     [rsp+78h+var_30], rax; struct _SecBufferDesc *
0x1800020f0  mov     rax, [rsp+78h+arg_40]
0x1800020f8  mov     [rsp+78h+var_38], rax; struct _SecHandle *
0x1800020fd  mov     rax, [rsp+78h+arg_30]
0x180002105  mov     [rsp+78h+var_48], rax; struct _SecBufferDesc *
0x18000210a  mov     eax, [rsp+78h+arg_28]
0x180002111  mov     [rsp+78h+var_50], eax; unsigned int
0x180002115  call    ?LsaInitializeSecurityContextCommon@@YAJPEAU_SecHandle@@0PEAGKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@E@Z; LsaInitializeSecurityContextCommon(_SecHandle *,_SecHandle *,ushort *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar)
0x18000211a  add     rsp, 78h
0x18000211e  retn
```
