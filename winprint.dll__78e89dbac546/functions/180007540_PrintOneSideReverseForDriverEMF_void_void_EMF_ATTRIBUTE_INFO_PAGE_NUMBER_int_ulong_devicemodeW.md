# PrintOneSideReverseForDriverEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,int,ulong,_devicemodeW *)

- ea: `0x180007540`
- end: `0x180007576`
- name: `?PrintOneSideReverseForDriverEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@HKPEAU_devicemodeW@@@Z`
- size: `54`
- prototype: `int(void *, void *, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, int, unsigned int, struct _devicemodeW *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180006bcc`

## pseudocode

```c
__int64 __fastcall PrintOneSideReverseForDriverEMF(
        void *a1,
        void *a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        struct _PAGE_NUMBER *a4,
        int a5,
        unsigned int a6,
        struct _devicemodeW *a7)
{
  return PrintOneSheetPreDeterminedForDriverEMF(a1, a2, a3, a5, a4, a6, 0, a7);
}

```

## disassembly

```asm
0x180007540  sub     rsp, 48h
0x180007544  mov     rax, [rsp+48h+arg_30]
0x18000754c  mov     [rsp+48h+var_10], rax; struct _devicemodeW *
0x180007551  mov     eax, [rsp+48h+arg_28]
0x180007555  mov     [rsp+48h+var_18], 0; int *
0x18000755e  mov     [rsp+48h+var_20], eax; unsigned int
0x180007562  mov     [rsp+48h+var_28], r9; struct _PAGE_NUMBER *
0x180007567  mov     r9d, [rsp+48h+arg_20]; int
0x18000756c  call    ?PrintOneSheetPreDeterminedForDriverEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HPEAU_PAGE_NUMBER@@KPEAHPEAU_devicemodeW@@@Z; PrintOneSheetPreDeterminedForDriverEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,_PAGE_NUMBER *,ulong,int *,_devicemodeW *)
0x180007571  add     rsp, 48h
0x180007575  retn
```
