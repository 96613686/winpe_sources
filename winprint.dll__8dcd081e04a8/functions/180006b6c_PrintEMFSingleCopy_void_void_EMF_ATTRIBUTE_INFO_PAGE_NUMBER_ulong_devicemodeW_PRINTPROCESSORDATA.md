# PrintEMFSingleCopy(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,ulong,_devicemodeW *,_PRINTPROCESSORDATA *)

- ea: `0x180006b6c`
- end: `0x180006bc6`
- name: `?PrintEMFSingleCopy@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@KPEAU_devicemodeW@@PEAU_PRINTPROCESSORDATA@@@Z`
- size: `90`
- prototype: `int(void *, void *, struct _EMF_ATTRIBUTE_INFO *, struct _PAGE_NUMBER *, unsigned int, struct _devicemodeW *, struct _PRINTPROCESSORDATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003890`

## callees

- `0x180003b40`
- `0x18000699c`
- `0x180006b6c`

## pseudocode

```c
int __fastcall PrintEMFSingleCopy(
        void *a1,
        void *a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        struct _PAGE_NUMBER *a4,
        unsigned int a5,
        struct _devicemodeW *a6,
        struct _PRINTPROCESSORDATA *a7)
{
  BOOL v8; // r9d

  v8 = *((_DWORD *)a3 + 13) != 0;
  if ( *((_DWORD *)a3 + 19) || *((_DWORD *)a3 + 18) )
    return PrintEMFInPredeterminedOrder(a1, a2, a3, a4, v8, a5, a6, a7);
  else
    return PrintForwardEMF(a1, a2, a3, v8, a5, a6, a7);
}

```

## disassembly

```asm
0x180006b6c  sub     rsp, 48h
0x180006b70  xor     eax, eax
0x180006b72  mov     r10, r9
0x180006b75  cmp     [r8+34h], eax
0x180006b79  mov     r9d, eax
0x180006b7c  setnz   r9b; int
0x180006b80  cmp     [r8+4Ch], eax
0x180006b84  jnz     short loc_180006B95
0x180006b86  cmp     [r8+48h], eax
0x180006b8a  jnz     short loc_180006B95
0x180006b8c  add     rsp, 48h
0x180006b90  jmp     ?PrintForwardEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HKPEAU_devicemodeW@@PEAU_PRINTPROCESSORDATA@@@Z; PrintForwardEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,ulong,_devicemodeW *,_PRINTPROCESSORDATA *)
0x180006b95  mov     rax, [rsp+48h+arg_30]
0x180006b9d  mov     [rsp+48h+var_10], rax; struct _PRINTPROCESSORDATA *
0x180006ba2  mov     rax, [rsp+48h+arg_28]
0x180006ba7  mov     [rsp+48h+var_18], rax; struct _devicemodeW *
0x180006bac  mov     eax, [rsp+48h+arg_20]
0x180006bb0  mov     [rsp+48h+var_20], eax; unsigned int
0x180006bb4  mov     [rsp+48h+var_28], r9d; int
0x180006bb9  mov     r9, r10; struct _PAGE_NUMBER *
0x180006bbc  call    ?PrintEMFInPredeterminedOrder@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@HKPEAU_devicemodeW@@PEAU_PRINTPROCESSORDATA@@@Z; PrintEMFInPredeterminedOrder(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,int,ulong,_devicemodeW *,_PRINTPROCESSORDATA *)
0x180006bc1  add     rsp, 48h
0x180006bc5  retn
```
