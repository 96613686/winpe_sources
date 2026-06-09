# WdsClientSessionCreate

- ea: `0x18000d0f0`
- end: `0x18000d114`
- name: `WdsClientSessionCreate`
- size: `36`
- prototype: `__int64 __fastcall(struct WDS_CRED *, struct tagWDS_ENDPOINT *Src, struct tagWDS_ENDPOINT *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009b30`

## pseudocode

```c
__int64 __fastcall WdsClientSessionCreate(
        struct WDS_CRED *a1,
        struct tagWDS_ENDPOINT *Src,
        struct tagWDS_ENDPOINT *a3,
        void **a4)
{
  return CClientLibrary::SessionCreate((CClientLibrary *)&stru_1800158D0, a1, Src, a3, a4);
}

```

## disassembly

```asm
0x18000d0f0  sub     rsp, 38h
0x18000d0f4  mov     [rsp+38h+var_18], r9; void **
0x18000d0f9  mov     r9, r8; struct tagWDS_ENDPOINT *
0x18000d0fc  mov     r8, rdx; Src
0x18000d0ff  mov     rdx, rcx; struct WDS_CRED *
0x18000d102  lea     rcx, stru_1800158D0; this
0x18000d109  call    ?SessionCreate@CClientLibrary@@QEAAKPEAUWDS_CRED@@PEAUtagWDS_ENDPOINT@@1PEAPEAX@Z; CClientLibrary::SessionCreate(WDS_CRED *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void * *)
0x18000d10e  add     rsp, 38h
0x18000d112  retn
```
