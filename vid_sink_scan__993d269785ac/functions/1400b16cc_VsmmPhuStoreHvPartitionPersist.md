# VsmmPhuStoreHvPartitionPersist

- ea: `0x1400b16cc`
- end: `0x1400b1a1b`
- name: `VsmmPhuStoreHvPartitionPersist`
- size: `847`
- prototype: `__int64 __fastcall(char *DeferredContext, char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14009eb9c`

## callees

- `0x140021650`
- `0x140021800`
- `0x14002f524`
- `0x140075460`
- `0x1400b16cc`
- `0x1400b662c`
- `0x1400b8954`
- `0x1400b8974`
- `0x1400fab38`

## import_xrefs

- `winhvr!WinHvGetSystemInformation` at `0x1400b18f6`
- `winhvr!WinHvGetSystemInformation` at `0x1400b18f6`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b1923`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b1923`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b17ae`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b17eb`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b17ae`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b17eb`
- `winhvr!WinHvCreatePartitionRemote` at `0x1400b189e`
- `winhvr!WinHvCreatePartitionRemote` at `0x1400b189e`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b1969`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b1969`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreHvPartitionPersist(char *DeferredContext, char *a2)
{
  char *v2; // r14
  char v3; // r15
  int v5; // eax
  int v7; // edi
  unsigned __int8 v8; // di
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v16; // [rsp+40h] [rbp-40h] BYREF
  __int64 v17; // [rsp+48h] [rbp-38h] BYREF
  __int64 v18; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  __int128 v20; // [rsp+60h] [rbp-20h] BYREF
  __int64 v21; // [rsp+70h] [rbp-10h]

  v2 = DeferredContext + 16;
  v21 = 0;
  v3 = 0;
  v17 = 0;
  v16 = 0;
  v5 = *((_DWORD *)DeferredContext + 4);
  v20 = 0;
  if ( (v5 & 0x200) != 0 )
  {
    v7 = -1070137298;
    VidTraceErrorStatusInternal0("VsmmPhuStoreHvPartitionPersist", "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c", 3230);
    goto LABEL_20;
  }
  v7 = VsmmPhuStorepSerializationChargeIncrease(*((_QWORD *)DeferredContext + 1081), 144, 1);
  if ( v7 < 0 )
  {
    VidTraceErrorStatusInternal0("VsmmPhuStoreHvPartitionPersist", "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c", 3240);
    goto LABEL_20;
  }
  v20 = 0;
  v21 = 0;
  v8 = 0;
  v3 = 1;
  do
  {
    WinHvGetPartitionProperty(*((_QWORD *)DeferredContext + 81), (unsigned int)v8 + 393226, &v17);
    v9 = v8++;
    *((_QWORD *)&v20 + v9) = ~v17;
  }
  while ( v8 < 2u );
  v10 = *((_QWORD *)DeferredContext + 81);
  v18 = 0;
  WinHvGetPartitionProperty(v10, 393218, &v18);
  v21 = ~v18;
  v11 = *((_DWORD *)DeferredContext + 2160);
  if ( (v11 & 2) == 0 )
    goto LABEL_16;
  if ( (v11 & 4) != 0 )
  {
    v7 = VsmmPhuStorepHvPartitionMirrorPrep(DeferredContext);
    if ( v7 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreHvPartitionPersist",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        3283);
      goto LABEL_20;
    }
    v12 = *((_QWORD *)DeferredContext + 81);
LABEL_26:
    memset(a2, 0, 0x70u);
    *(_QWORD *)a2 = *((_QWORD *)DeferredContext + 84);
    *((_DWORD *)a2 + 2) = *((_DWORD *)DeferredContext + 170);
    VsmmPhuStoreCreationPropertiesSerialize(&v20, a2, v14);
    *((_DWORD *)a2 + 8) = *((_DWORD *)DeferredContext + 800);
    VsmmPhuStoreHvPartitionMakeInvariantFlags(v2, DeferredContext + 40, a2 + 40);
    *((_QWORD *)DeferredContext + 1096) = v12;
    v7 = 0;
    *(_WORD *)(DeferredContext + 8761) = 257;
    DeferredContext[8760] = 1;
    return (unsigned int)v7;
  }
  v13 = (unsigned __int8)DeferredContext[2105];
  LODWORD(v13) = v13 | 0x80000000;
  if ( *v2 < 0 )
    v13 = (unsigned __int8)DeferredContext[2105];
  v7 = WinHvCreatePartitionRemote(
         *((_QWORD *)DeferredContext + 81),
         *((_QWORD *)DeferredContext + 84),
         v13,
         *((unsigned int *)DeferredContext + 170),
         &v20,
         &v16,
         VidHvMemLowMemPolicyCallbackRemote,
         DeferredContext);
  if ( v7 < 0 )
  {
    VidTraceErrorStatusInternal0("VsmmPhuStoreHvPartitionPersist", "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c", 3313);
  }
  else
  {
LABEL_16:
    v19 = 0;
    if ( (int)WinHvGetSystemInformation(14, 0, 0, &v19, 8, 0) < 0
      || v19 != 1
      || (v7 = WinHvSetPartitionProperty(*((_QWORD *)DeferredContext + 81)), v7 >= 0) )
    {
      v12 = v16;
      goto LABEL_26;
    }
    VidTraceErrorStatusInternal0("VsmmPhuStoreHvPartitionPersist", "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c", 3345);
  }
LABEL_20:
  if ( v16 && (*((_DWORD *)DeferredContext + 2160) & 4) == 0 )
    WinHvDeletePartitionRemote(*((_QWORD *)DeferredContext + 81));
  if ( v3 )
    VsmmPhuStorepSerializationChargeDecrease(*((_QWORD *)DeferredContext + 1081), 144);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400b16cc  mov     [rsp-28h+arg_10], rbx
0x1400b16d1  mov     [rsp-28h+arg_18], rsi
0x1400b16d6  push    rbp
0x1400b16d7  push    rdi
0x1400b16d8  push    r12
0x1400b16da  push    r14
0x1400b16dc  push    r15
0x1400b16de  mov     rbp, rsp
0x1400b16e1  sub     rsp, 80h
0x1400b16e8  mov     rax, cs:__security_cookie
0x1400b16ef  xor     rax, rsp
0x1400b16f2  mov     [rbp+var_8], rax
0x1400b16f6  xor     eax, eax
0x1400b16f8  lea     r14, [rcx+10h]
0x1400b16fc  mov     [rbp+var_10], rax
0x1400b1700  xor     r15b, r15b
0x1400b1703  mov     [rbp+var_38], rax
0x1400b1707  xorps   xmm0, xmm0
0x1400b170a  mov     [rbp+var_40], rax
0x1400b170e  mov     rsi, rdx
0x1400b1711  mov     eax, [r14]
0x1400b1714  mov     rbx, rcx
0x1400b1717  movups  [rbp+var_20], xmm0
0x1400b171b  bt      rax, 9
0x1400b1720  jnb     short loc_1400B1748
0x1400b1722  mov     edi, 0C037002Eh
0x1400b1727  mov     r9d, edi
0x1400b172a  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b1731  mov     r8d, 0C9Eh
0x1400b1737  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b173e  call    VidTraceErrorStatusInternal0
0x1400b1743  jmp     loc_1400B1951
0x1400b1748  mov     rcx, [rcx+21C8h]
0x1400b174f  mov     edx, 90h
0x1400b1754  mov     r8d, 1
0x1400b175a  call    VsmmPhuStorepSerializationChargeIncrease
0x1400b175f  mov     edi, eax
0x1400b1761  test    eax, eax
0x1400b1763  jns     short loc_1400B1786
0x1400b1765  mov     r9d, eax
0x1400b1768  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b176f  mov     r8d, 0CA8h
0x1400b1775  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b177c  call    VidTraceErrorStatusInternal0
0x1400b1781  jmp     loc_1400B1951
0x1400b1786  xor     eax, eax
0x1400b1788  xorps   xmm0, xmm0
0x1400b178b  movups  [rbp+var_20], xmm0
0x1400b178f  mov     [rbp+var_10], rax
0x1400b1793  xor     dil, dil
0x1400b1796  mov     r15b, 1
0x1400b1799  mov     rcx, [rbx+288h]
0x1400b17a0  lea     r8, [rbp+var_38]
0x1400b17a4  movzx   edx, dil
0x1400b17a8  add     edx, 6000Ah
0x1400b17ae  call    cs:__imp_WinHvGetPartitionProperty
0x1400b17b5  nop     dword ptr [rax+rax+00h]
0x1400b17ba  mov     rcx, [rbp+var_38]
0x1400b17be  movzx   eax, dil
0x1400b17c2  not     rcx
0x1400b17c5  inc     dil
0x1400b17c8  mov     qword ptr [rbp+rax*8+var_20], rcx
0x1400b17cd  cmp     dil, 2
0x1400b17d1  jb      short loc_1400B1799
0x1400b17d3  mov     rcx, [rbx+288h]
0x1400b17da  lea     r8, [rbp+var_30]
0x1400b17de  mov     edx, 60002h
0x1400b17e3  mov     [rbp+var_30], 0
0x1400b17eb  call    cs:__imp_WinHvGetPartitionProperty
0x1400b17f2  nop     dword ptr [rax+rax+00h]
0x1400b17f7  mov     rax, [rbp+var_30]
0x1400b17fb  not     rax
0x1400b17fe  mov     [rbp+var_10], rax
0x1400b1802  mov     eax, [rbx+21C0h]
0x1400b1808  test    al, 2
0x1400b180a  jz      loc_1400B18D1
0x1400b1810  test    al, 4
0x1400b1812  jz      short loc_1400B184F
0x1400b1814  mov     rcx, rbx; DeferredContext
0x1400b1817  call    VsmmPhuStorepHvPartitionMirrorPrep
0x1400b181c  mov     edi, eax
0x1400b181e  test    eax, eax
0x1400b1820  jns     short loc_1400B1843
0x1400b1822  mov     r9d, eax
0x1400b1825  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b182c  mov     r8d, 0CD3h
0x1400b1832  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b1839  call    VidTraceErrorStatusInternal0
0x1400b183e  jmp     loc_1400B1951
0x1400b1843  mov     rdi, [rbx+288h]
0x1400b184a  jmp     loc_1400B1991
0x1400b184f  movzx   ecx, byte ptr [rbx+839h]
0x1400b1856  lea     rax, VidHvMemLowMemPolicyCallbackRemote
0x1400b185d  mov     r9d, [rbx+2A8h]
0x1400b1864  mov     r8d, ecx
0x1400b1867  mov     rdx, [rbx+2A0h]
0x1400b186e  bts     r8d, 1Fh
0x1400b1873  test    byte ptr [r14], 80h
0x1400b1877  mov     [rsp+80h+var_48], rbx
0x1400b187c  mov     [rsp+80h+var_50], rax
0x1400b1881  cmovnz  r8d, ecx
0x1400b1885  mov     rcx, [rbx+288h]
0x1400b188c  lea     rax, [rbp+var_40]
0x1400b1890  mov     [rsp+80h+var_58], rax
0x1400b1895  lea     rax, [rbp+var_20]
0x1400b1899  mov     [rsp+80h+var_60], rax
0x1400b189e  call    cs:__imp_WinHvCreatePartitionRemote
0x1400b18a5  nop     dword ptr [rax+rax+00h]
0x1400b18aa  mov     edi, eax
0x1400b18ac  test    eax, eax
0x1400b18ae  jns     short loc_1400B18D1
0x1400b18b0  mov     r9d, eax
0x1400b18b3  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b18ba  mov     r8d, 0CF1h
0x1400b18c0  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b18c7  call    VidTraceErrorStatusInternal0
0x1400b18cc  jmp     loc_1400B1951
0x1400b18d1  xor     edx, edx
0x1400b18d3  mov     [rsp+80h+var_58], 0
0x1400b18dc  lea     r9, [rbp+var_28]
0x1400b18e0  mov     [rbp+var_28], 0
0x1400b18e8  xor     r8d, r8d
0x1400b18eb  mov     dword ptr [rsp+80h+var_60], 8
0x1400b18f3  lea     ecx, [rdx+0Eh]
0x1400b18f6  call    cs:__imp_WinHvGetSystemInformation
0x1400b18fd  nop     dword ptr [rax+rax+00h]
0x1400b1902  test    eax, eax
0x1400b1904  js      loc_1400B198D
0x1400b190a  cmp     [rbp+var_28], 1
0x1400b190f  jnz     short loc_1400B198D
0x1400b1911  mov     rcx, [rbx+288h]
0x1400b1918  mov     edx, 5001Fh
0x1400b191d  mov     r8d, 2
0x1400b1923  call    cs:__imp_WinHvSetPartitionProperty
0x1400b192a  nop     dword ptr [rax+rax+00h]
0x1400b192f  mov     edi, eax
0x1400b1931  test    eax, eax
0x1400b1933  jns     short loc_1400B198D
0x1400b1935  mov     r9d, eax
0x1400b1938  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b193f  mov     r8d, 0D11h
0x1400b1945  lea     rcx, aVsmmphustorehv; "VsmmPhuStoreHvPartitionPersist"
0x1400b194c  call    VidTraceErrorStatusInternal0
0x1400b1951  cmp     [rbp+var_40], 0
0x1400b1956  jz      short loc_1400B1975
0x1400b1958  mov     eax, [rbx+21C0h]
0x1400b195e  test    al, 4
0x1400b1960  jnz     short loc_1400B1975
0x1400b1962  mov     rcx, [rbx+288h]
0x1400b1969  call    cs:__imp_WinHvDeletePartitionRemote
0x1400b1970  nop     dword ptr [rax+rax+00h]
0x1400b1975  test    r15b, r15b
0x1400b1978  jz      short loc_1400B19F0
0x1400b197a  mov     rcx, [rbx+21C8h]
0x1400b1981  mov     edx, 90h
0x1400b1986  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b198b  jmp     short loc_1400B19F0
0x1400b198d  mov     rdi, [rbp+var_40]
0x1400b1991  xor     edx, edx; Val
0x1400b1993  mov     rcx, rsi; void *
0x1400b1996  lea     r8d, [rdx+70h]; Size
0x1400b199a  call    memset
0x1400b199f  mov     rax, [rbx+2A0h]
0x1400b19a6  lea     rcx, [rbp+var_20]
0x1400b19aa  mov     [rsi], rax
0x1400b19ad  mov     rdx, rsi
0x1400b19b0  mov     eax, [rbx+2A8h]
0x1400b19b6  mov     [rsi+8], eax
0x1400b19b9  call    VsmmPhuStoreCreationPropertiesSerialize
0x1400b19be  mov     edx, [rbx+0C80h]
0x1400b19c4  lea     r8, [rsi+28h]
0x1400b19c8  mov     [rsi+20h], edx
0x1400b19cb  mov     rcx, r14
0x1400b19ce  lea     rdx, [rbx+28h]
0x1400b19d2  call    VsmmPhuStoreHvPartitionMakeInvariantFlags
0x1400b19d7  mov     [rbx+2240h], rdi
0x1400b19de  xor     edi, edi
0x1400b19e0  mov     word ptr [rbx+2239h], 101h
0x1400b19e9  mov     [rbx+2238h], r15b
0x1400b19f0  mov     eax, edi
0x1400b19f2  mov     rcx, [rbp+var_8]
0x1400b19f6  xor     rcx, rsp; StackCookie
0x1400b19f9  call    __security_check_cookie
0x1400b19fe  lea     r11, [rsp+80h+var_s0]
0x1400b1a06  mov     rbx, [r11+40h]
0x1400b1a0a  mov     rsi, [r11+48h]
0x1400b1a0e  mov     rsp, r11
0x1400b1a11  pop     r15
0x1400b1a13  pop     r14
0x1400b1a15  pop     r12
0x1400b1a17  pop     rdi
0x1400b1a18  pop     rbp
0x1400b1a19  retn
```
