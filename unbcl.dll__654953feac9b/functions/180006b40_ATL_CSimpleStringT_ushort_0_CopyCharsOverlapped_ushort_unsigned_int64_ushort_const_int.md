# ATL::CSimpleStringT<ushort,0>::CopyCharsOverlapped(ushort *,unsigned __int64,ushort const *,int)

- ea: `0x180006b40`
- end: `0x180006b62`
- name: `?CopyCharsOverlapped@?$CSimpleStringT@G$0A@@ATL@@SAXPEAG_KPEBGH@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!memmove_s` at `0x180006b56`
- `msvcrt!memmove_s` at `0x180006b56`

## pseudocode

```c
errno_t __fastcall ATL::CSimpleStringT<unsigned short,0>::CopyCharsOverlapped(
        void *a1,
        __int64 a2,
        const void *a3,
        int a4)
{
  return memmove_s(a1, 2 * a2, a3, 2LL * a4);
}

```

## disassembly

```asm
0x180006b40  sub     rsp, 38h
0x180006b44  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180006b4d  movsxd  r9, r9d
0x180006b50  add     r9, r9; SourceSize
0x180006b53  add     rdx, rdx; DestinationSize
0x180006b56  call    cs:__imp_memmove_s
0x180006b5c  nop
0x180006b5d  add     rsp, 38h
0x180006b61  retn
```
