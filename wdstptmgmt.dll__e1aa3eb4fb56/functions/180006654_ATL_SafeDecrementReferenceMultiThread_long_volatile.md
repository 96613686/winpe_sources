# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180006654`
- end: `0x180006676`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800061fc`
- `0x1800065b0`
- `0x180006cc4`
- `0x1800078a0`
- `0x1800080b0`
- `0x1800086d0`
- `0x180008770`
- `0x1800087e0`
- `0x180008a30`
- `0x1800091f0`
- `0x180011128`
- `0x180011220`
- `0x180011344`
- `0x1800127a0`
- `0x1800148c0`
- `0x180014dd0`
- `0x180015530`
- `0x180015a70`
- `0x1800162d0`
- `0x180016b40`
- `0x180018348`
- `0x180018410`
- `0x180018890`
- `0x180018db0`
- `0x180019210`

## callees

- `0x180006654`

## pseudocode

```c
__int64 __fastcall ATL::SafeDecrementReferenceMultiThread(volatile int *a1)
{
  signed __int32 v1; // r8d

  do
    v1 = *a1;
  while ( *a1 != 0x7FFFFFFF && v1 != _InterlockedCompareExchange(a1, v1 - 1, v1) );
  return (unsigned int)(v1 - 1);
}

```

## disassembly

```asm
0x180006654  mov     r9d, 7FFFFFFFh
0x18000665a  jmp     short loc_180006669
0x18000665c  lea     edx, [r8-1]
0x180006660  mov     eax, r8d
0x180006663  lock cmpxchg [rcx], edx
0x180006667  jz      short loc_180006671
0x180006669  mov     r8d, [rcx]
0x18000666c  cmp     r8d, r9d
0x18000666f  jnz     short loc_18000665C
0x180006671  lea     eax, [r8-1]
0x180006675  retn
```
