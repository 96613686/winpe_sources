# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)

- ea: `0x180018d14`
- end: `0x180018ddf`
- name: `?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001871c`

## callees

- `0x18000b92c`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        int a6)
{
  int v7; // [rsp+20h] [rbp-A8h]
  int v8; // [rsp+28h] [rbp-A0h]
  int v9; // [rsp+30h] [rbp-98h]
  int v10; // [rsp+38h] [rbp-90h]
  int v11; // [rsp+40h] [rbp-88h]
  int v12; // [rsp+48h] [rbp-80h]
  int v13; // [rsp+50h] [rbp-78h]
  int v14; // [rsp+58h] [rbp-70h]
  int v15; // [rsp+60h] [rbp-68h]
  int v16; // [rsp+68h] [rbp-60h]
  int v17; // [rsp+70h] [rbp-58h]

  v17 = *((unsigned __int8 *)a5 + 15);
  v16 = *((unsigned __int8 *)a5 + 14);
  v15 = *((unsigned __int8 *)a5 + 13);
  v14 = *((unsigned __int8 *)a5 + 12);
  v13 = *((unsigned __int8 *)a5 + 11);
  v12 = *((unsigned __int8 *)a5 + 10);
  v11 = *((unsigned __int8 *)a5 + 9);
  v10 = *((unsigned __int8 *)a5 + 8);
  v9 = *((unsigned __int16 *)a5 + 3);
  v8 = *((unsigned __int16 *)a5 + 2);
  v7 = *a5;
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
           a2,
           L"%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%02x%02x%02x%02x%x",
           a3,
           a4,
           v7,
           v8,
           v9,
           v10,
           v11,
           v12,
           v13,
           v14,
           v15,
           v16,
           v17,
           a6);
}

```

## disassembly

```asm
0x180018d14  mov     [rsp+arg_8], rdx
0x180018d19  push    rbx
0x180018d1a  push    rbp
0x180018d1b  push    rsi
0x180018d1c  push    rdi
0x180018d1d  push    r12
0x180018d1f  push    r13
0x180018d21  push    r14
0x180018d23  push    r15
0x180018d25  sub     rsp, 88h
0x180018d2c  mov     r12, [rsp+0C8h+arg_20]
0x180018d34  lea     rdx, aWsHs08x04x04x0; "%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%"...
0x180018d3b  mov     eax, [rsp+0C8h+arg_28]
0x180018d42  mov     r13, r9
0x180018d45  mov     [rsp+0C8h+var_50], eax
0x180018d49  movzx   ecx, byte ptr [r12+0Fh]
0x180018d4f  movzx   r9d, word ptr [r12+4]
0x180018d55  movzx   r10d, byte ptr [r12+0Eh]
0x180018d5b  movzx   r11d, byte ptr [r12+0Dh]
0x180018d61  movzx   ebx, byte ptr [r12+0Ch]
0x180018d67  movzx   edi, byte ptr [r12+0Bh]
0x180018d6d  movzx   esi, byte ptr [r12+0Ah]
0x180018d73  movzx   ebp, byte ptr [r12+9]
0x180018d79  movzx   r14d, byte ptr [r12+8]
0x180018d7f  movzx   r15d, word ptr [r12+6]
0x180018d85  mov     eax, [r12]
0x180018d89  mov     [rsp+0C8h+var_58], ecx
0x180018d8d  mov     rcx, [rsp+0C8h+arg_8]
0x180018d95  mov     [rsp+0C8h+var_60], r10d
0x180018d9a  mov     [rsp+0C8h+var_68], r11d
0x180018d9f  mov     [rsp+0C8h+var_70], ebx
0x180018da3  mov     [rsp+0C8h+var_78], edi
0x180018da7  mov     [rsp+0C8h+var_80], esi
0x180018dab  mov     [rsp+0C8h+var_88], ebp
0x180018daf  mov     [rsp+0C8h+var_90], r14d
0x180018db4  mov     [rsp+0C8h+var_98], r15d
0x180018db9  mov     [rsp+0C8h+var_A0], r9d
0x180018dbe  mov     r9, r13
0x180018dc1  mov     [rsp+0C8h+var_A8], eax
0x180018dc5  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180018dca  add     rsp, 88h
0x180018dd1  pop     r15
0x180018dd3  pop     r14
0x180018dd5  pop     r13
0x180018dd7  pop     r12
0x180018dd9  pop     rdi
0x180018dda  pop     rsi
0x180018ddb  pop     rbp
0x180018ddc  pop     rbx
0x180018ddd  retn
```
