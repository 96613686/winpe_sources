# LsaInitializeSecurityContextA(_SecHandle *,_SecHandle *,char *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *)

- ea: `0x180002050`
- end: `0x1800020af`
- name: `?LsaInitializeSecurityContextA@@YAJPEAU_SecHandle@@0PEADKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(struct _SecHandle *, struct _SecHandle *, char *, unsigned int, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned int, struct _SecHandle *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002130`

## pseudocode

```c
__int64 __fastcall LsaInitializeSecurityContextA(
        struct _SecHandle *a1,
        struct _SecHandle *a2,
        char *a3,
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

  return LsaInitializeSecurityContextCommon(a1, a2, a3, a4, v13, a6, a7, v14, a9, a10, a11, a12, 0);
}

```

## disassembly

```asm
0x180002050  sub     rsp, 78h
0x180002054  mov     rax, [rsp+78h+arg_58]
0x18000205c  mov     [rsp+78h+var_18], 0; unsigned __int8
0x180002061  mov     [rsp+78h+var_20], rax; union _LARGE_INTEGER *
0x180002066  mov     rax, [rsp+78h+arg_50]
0x18000206e  mov     [rsp+78h+var_28], rax; unsigned int *
0x180002073  mov     rax, [rsp+78h+arg_48]
0x18000207b  mov     [rsp+78h+var_30], rax; struct _SecBufferDesc *
0x180002080  mov     rax, [rsp+78h+arg_40]
0x180002088  mov     [rsp+78h+var_38], rax; struct _SecHandle *
0x18000208d  mov     rax, [rsp+78h+arg_30]
0x180002095  mov     [rsp+78h+var_48], rax; struct _SecBufferDesc *
0x18000209a  mov     eax, [rsp+78h+arg_28]
0x1800020a1  mov     [rsp+78h+var_50], eax; unsigned int
0x1800020a5  call    ?LsaInitializeSecurityContextCommon@@YAJPEAU_SecHandle@@0PEAGKKKPEAU_SecBufferDesc@@K02PEAKPEAT_LARGE_INTEGER@@E@Z; LsaInitializeSecurityContextCommon(_SecHandle *,_SecHandle *,ushort *,ulong,ulong,ulong,_SecBufferDesc *,ulong,_SecHandle *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar)
0x1800020aa  add     rsp, 78h
0x1800020ae  retn
```
