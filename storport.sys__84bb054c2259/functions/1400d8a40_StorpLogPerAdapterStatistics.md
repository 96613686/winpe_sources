# StorpLogPerAdapterStatistics

- ea: `0x1400d8a40`
- end: `0x1400d8fdc`
- name: `StorpLogPerAdapterStatistics`
- size: `1436`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14004d690`

## callees

- `0x1400312c8`
- `0x140046c60`
- `0x140054800`
- `0x1400706b8`
- `0x140071888`
- `0x1400d8a40`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x1400d8f0c`
- `ntoskrnl!IoQueueWorkItem` at `0x1400d8f9b`
- `ntoskrnl!IoQueueWorkItem` at `0x1400d8f0c`
- `ntoskrnl!IoQueueWorkItem` at `0x1400d8f9b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400d8f21`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400d8fb0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400d8f21`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400d8fb0`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400d8eeb`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400d8f7a`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400d8eeb`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400d8f7a`

## pseudocode

```c
void __fastcall StorpLogPerAdapterStatistics(__int64 a1, char a2)
{
  int v4; // r8d
  int v5; // r9d
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rcx
  struct _IO_WORKITEM *WorkItem; // rax
  struct _IO_WORKITEM *v11; // rax
  char v12; // [rsp+30h] [rbp-D0h] BYREF
  char v13; // [rsp+31h] [rbp-CFh] BYREF
  char v14; // [rsp+32h] [rbp-CEh] BYREF
  char v15; // [rsp+33h] [rbp-CDh] BYREF
  _BYTE v16[4]; // [rsp+34h] [rbp-CCh] BYREF
  int v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+3Ch] [rbp-C4h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+5Ch] [rbp-A4h] BYREF
  _DWORD v27[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  int *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  int *v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  int *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  char *v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  int *v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  int *v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  char *v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  int *v45; // [rsp+110h] [rbp+10h]
  __int64 v46; // [rsp+118h] [rbp+18h]
  int *v47; // [rsp+120h] [rbp+20h]
  __int64 v48; // [rsp+128h] [rbp+28h]
  char *v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  int *v51; // [rsp+140h] [rbp+40h]
  __int64 v52; // [rsp+148h] [rbp+48h]
  int *v53; // [rsp+150h] [rbp+50h]
  __int64 v54; // [rsp+158h] [rbp+58h]
  char *v55; // [rsp+160h] [rbp+60h]
  __int64 v56; // [rsp+168h] [rbp+68h]
  int *v57; // [rsp+170h] [rbp+70h]
  __int64 v58; // [rsp+178h] [rbp+78h]
  int *v59; // [rsp+180h] [rbp+80h]
  __int64 v60; // [rsp+188h] [rbp+88h]
  char *v61; // [rsp+190h] [rbp+90h]
  __int64 v62; // [rsp+198h] [rbp+98h]

  if ( (*(_DWORD *)(a1 + 5156)
     || *(_DWORD *)(a1 + 5168)
     || *(_DWORD *)(a1 + 5180)
     || *(_DWORD *)(a1 + 5192)
     || *(_DWORD *)(a1 + 5204))
    && (unsigned int)dword_140176178 > 5
    && (unsigned __int8)tlgKeywordOn(a1, 0x400000000000LL) )
  {
    v30 = 16;
    v29 = a1 + 5128;
    v17 = *(_DWORD *)(a1 + 56);
    v31 = &v17;
    v18 = *(_DWORD *)(a1 + 5156);
    v33 = &v18;
    v19 = *(_DWORD *)(a1 + 5160);
    v35 = &v19;
    v12 = *(_BYTE *)(a1 + 5164);
    v37 = &v12;
    v20 = *(_DWORD *)(a1 + 5168);
    v39 = &v20;
    v21 = *(_DWORD *)(a1 + 5172);
    v41 = &v21;
    v13 = *(_BYTE *)(a1 + 5176);
    v43 = &v13;
    v22 = *(_DWORD *)(a1 + 5180);
    v45 = &v22;
    v23 = *(_DWORD *)(a1 + 5184);
    v47 = &v23;
    v14 = *(_BYTE *)(a1 + 5188);
    v49 = &v14;
    v24 = *(_DWORD *)(a1 + 5192);
    v51 = &v24;
    v25 = *(_DWORD *)(a1 + 5196);
    v53 = &v25;
    v15 = *(_BYTE *)(a1 + 5200);
    v55 = &v15;
    v26 = *(_DWORD *)(a1 + 5204);
    v57 = &v26;
    v27[0] = *(_DWORD *)(a1 + 5208);
    v59 = v27;
    v16[0] = *(_BYTE *)(a1 + 5212);
    v32 = 4;
    v34 = 4;
    v36 = 4;
    v38 = 1;
    v40 = 4;
    v42 = 4;
    v44 = 1;
    v46 = 4;
    v48 = 4;
    v50 = 1;
    v52 = 4;
    v54 = 4;
    v56 = 1;
    v58 = 4;
    v60 = 4;
    v61 = v16;
    v62 = 1;
    tlgWriteTransfer_EtwWriteTransfer(a1, (int)&byte_1401667CB, v4, v5, 0x13u, (__int64)v28);
  }
  if ( (*(_DWORD *)(a1 + 5216)
     || *(_DWORD *)(a1 + 5228)
     || *(_DWORD *)(a1 + 5240)
     || *(_DWORD *)(a1 + 5252)
     || *(_DWORD *)(a1 + 5264))
    && (unsigned int)dword_140176178 > 5
    && (unsigned __int8)tlgKeywordOn(a1, 0x400000000000LL) )
  {
    v30 = 16;
    v29 = a1 + 5128;
    v27[0] = *(_DWORD *)(a1 + 56);
    v31 = v27;
    v26 = *(_DWORD *)(a1 + 5216);
    v33 = &v26;
    v25 = *(_DWORD *)(a1 + 5220);
    v35 = &v25;
    v16[0] = *(_BYTE *)(a1 + 5224);
    v37 = v16;
    v24 = *(_DWORD *)(a1 + 5228);
    v39 = &v24;
    v23 = *(_DWORD *)(a1 + 5232);
    v41 = &v23;
    v15 = *(_BYTE *)(a1 + 5236);
    v43 = &v15;
    v22 = *(_DWORD *)(a1 + 5240);
    v45 = &v22;
    v21 = *(_DWORD *)(a1 + 5244);
    v47 = &v21;
    v14 = *(_BYTE *)(a1 + 5248);
    v49 = &v14;
    v20 = *(_DWORD *)(a1 + 5252);
    v51 = &v20;
    v19 = *(_DWORD *)(a1 + 5256);
    v53 = &v19;
    v13 = *(_BYTE *)(a1 + 5260);
    v55 = &v13;
    v18 = *(_DWORD *)(a1 + 5264);
    v57 = &v18;
    v17 = *(_DWORD *)(a1 + 5268);
    v59 = &v17;
    v12 = *(_BYTE *)(a1 + 5272);
    v32 = 4;
    v34 = 4;
    v36 = 4;
    v38 = 1;
    v40 = 4;
    v42 = 4;
    v44 = 1;
    v46 = 4;
    v48 = 4;
    v50 = 1;
    v52 = 4;
    v54 = 4;
    v56 = 1;
    v58 = 4;
    v60 = 4;
    v61 = &v12;
    v62 = 1;
    tlgWriteTransfer_EtwWriteTransfer(v6, (int)&word_140167866, v7, v8, 0x13u, (__int64)v28);
  }
  StorpInitializeHierarchicalResetBuckets(a1);
  if ( (*(_DWORD *)(a1 + 5408) & 1) == 0 && (int)RaidAcquireAdapterRemoveLock(v9) >= 0 )
  {
    WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 8));
    if ( WorkItem )
      IoQueueWorkItem(WorkItem, StorpAdapterTopologyWorkItemRoutine, NormalWorkQueue, WorkItem);
    else
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 320));
  }
  if ( a2 < 0
    && (!*(_BYTE *)(a1 + 5424)
     && (*(_BYTE *)(a1 + 5408) & 0xC) != 0xC
     && *(_DWORD *)(a1 + 4340) == 17
     && (unsigned __int8)StorIsMFNDSupported(a1)
     || *(_DWORD *)(a1 + 4340) == 19)
    && (int)RaidAcquireAdapterRemoveLock(a1) >= 0 )
  {
    v11 = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 8));
    if ( v11 )
      IoQueueWorkItem(v11, StorpAdapterHealthWorkItemRoutine, NormalWorkQueue, v11);
    else
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 320));
  }
}

```

## disassembly

```asm
0x1400d8a40  push    rbp
0x1400d8a42  push    rbx
0x1400d8a43  push    rsi
0x1400d8a44  push    rdi
0x1400d8a45  push    r14
0x1400d8a47  push    r15
0x1400d8a49  lea     rbp, [rsp-0B8h]
0x1400d8a51  sub     rsp, 1B8h
0x1400d8a58  mov     rax, cs:__security_cookie
0x1400d8a5f  xor     rax, rsp
0x1400d8a62  mov     [rbp+0E0h+var_40], rax
0x1400d8a69  xor     esi, esi
0x1400d8a6b  movzx   edi, dx
0x1400d8a6e  mov     rbx, rcx
0x1400d8a71  lea     r15d, [rsi+1]
0x1400d8a75  cmp     [rcx+1424h], esi
0x1400d8a7b  jnz     short loc_1400D8AA1
0x1400d8a7d  cmp     [rcx+1430h], esi
0x1400d8a83  jnz     short loc_1400D8AA1
0x1400d8a85  cmp     [rcx+143Ch], esi
0x1400d8a8b  jnz     short loc_1400D8AA1
0x1400d8a8d  cmp     [rcx+1448h], esi
0x1400d8a93  jnz     short loc_1400D8AA1
0x1400d8a95  cmp     [rcx+1454h], esi
0x1400d8a9b  jz      loc_1400D8C9D
0x1400d8aa1  mov     eax, cs:dword_140176178
0x1400d8aa7  cmp     eax, 5
0x1400d8aaa  jbe     loc_1400D8C9D
0x1400d8ab0  mov     rdx, 400000000000h
0x1400d8aba  call    _tlgKeywordOn
0x1400d8abf  test    al, al
0x1400d8ac1  jz      loc_1400D8C9D
0x1400d8ac7  lea     rax, [rbx+1408h]
0x1400d8ace  mov     [rbp+0E0h+var_148], 10h
0x1400d8ad6  mov     [rbp+0E0h+var_150], rax
0x1400d8ada  mov     eax, [rbx+38h]
0x1400d8add  mov     [rsp+1E0h+var_1A8], eax
0x1400d8ae1  lea     rax, [rsp+1E0h+var_1A8]
0x1400d8ae6  mov     [rbp+0E0h+var_140], rax
0x1400d8aea  mov     eax, [rbx+1424h]
0x1400d8af0  mov     [rsp+1E0h+var_1A4], eax
0x1400d8af4  lea     rax, [rsp+1E0h+var_1A4]
0x1400d8af9  mov     [rbp+0E0h+var_130], rax
0x1400d8afd  mov     eax, [rbx+1428h]
0x1400d8b03  mov     [rsp+1E0h+var_1A0], eax
0x1400d8b07  lea     rax, [rsp+1E0h+var_1A0]
0x1400d8b0c  mov     [rbp+0E0h+var_120], rax
0x1400d8b10  mov     al, [rbx+142Ch]
0x1400d8b16  mov     [rsp+1E0h+var_1B0], al
0x1400d8b1a  lea     rax, [rsp+1E0h+var_1B0]
0x1400d8b1f  mov     [rbp+0E0h+var_110], rax
0x1400d8b23  mov     eax, [rbx+1430h]
0x1400d8b29  mov     [rsp+1E0h+var_19C], eax
0x1400d8b2d  lea     rax, [rsp+1E0h+var_19C]
0x1400d8b32  mov     [rbp+0E0h+var_100], rax
0x1400d8b36  mov     eax, [rbx+1434h]
0x1400d8b3c  mov     [rsp+1E0h+var_198], eax
0x1400d8b40  lea     rax, [rsp+1E0h+var_198]
0x1400d8b45  mov     [rbp+0E0h+var_F0], rax
0x1400d8b49  mov     al, [rbx+1438h]
0x1400d8b4f  mov     [rsp+1E0h+var_1AF], al
0x1400d8b53  lea     rax, [rsp+1E0h+var_1AF]
0x1400d8b58  mov     [rbp+0E0h+var_E0], rax
0x1400d8b5c  mov     eax, [rbx+143Ch]
0x1400d8b62  mov     [rsp+1E0h+var_194], eax
0x1400d8b66  lea     rax, [rsp+1E0h+var_194]
0x1400d8b6b  mov     [rbp+0E0h+var_D0], rax
0x1400d8b6f  mov     eax, [rbx+1440h]
0x1400d8b75  mov     [rsp+1E0h+var_190], eax
0x1400d8b79  lea     rax, [rsp+1E0h+var_190]
0x1400d8b7e  mov     [rbp+0E0h+var_C0], rax
0x1400d8b82  mov     al, [rbx+1444h]
0x1400d8b88  mov     [rsp+1E0h+var_1AE], al
0x1400d8b8c  lea     rax, [rsp+1E0h+var_1AE]
0x1400d8b91  mov     [rbp+0E0h+var_B0], rax
0x1400d8b95  mov     eax, [rbx+1448h]
0x1400d8b9b  mov     [rsp+1E0h+var_18C], eax
0x1400d8b9f  lea     rax, [rsp+1E0h+var_18C]
0x1400d8ba4  mov     [rbp+0E0h+var_A0], rax
0x1400d8ba8  mov     eax, [rbx+144Ch]
0x1400d8bae  mov     [rsp+1E0h+var_188], eax
0x1400d8bb2  lea     rax, [rsp+1E0h+var_188]
0x1400d8bb7  mov     [rbp+0E0h+var_90], rax
0x1400d8bbb  mov     al, [rbx+1450h]
0x1400d8bc1  mov     [rsp+1E0h+var_1AD], al
0x1400d8bc5  lea     rax, [rsp+1E0h+var_1AD]
0x1400d8bca  mov     [rbp+0E0h+var_80], rax
0x1400d8bce  mov     eax, [rbx+1454h]
0x1400d8bd4  mov     [rsp+1E0h+var_184], eax
0x1400d8bd8  lea     rax, [rsp+1E0h+var_184]
0x1400d8bdd  mov     [rbp+0E0h+var_70], rax
0x1400d8be1  mov     eax, [rbx+1458h]
0x1400d8be7  mov     [rsp+1E0h+var_180], eax
0x1400d8beb  lea     rax, [rsp+1E0h+var_180]
0x1400d8bf0  mov     [rbp+0E0h+var_60], rax
0x1400d8bf7  mov     al, [rbx+145Ch]
0x1400d8bfd  mov     [rsp+1E0h+var_1AC], al
0x1400d8c01  lea     rax, [rsp+1E0h+var_1AC]
0x1400d8c06  mov     [rbp+0E0h+var_138], 4
0x1400d8c0e  mov     [rbp+0E0h+var_128], 4
0x1400d8c16  mov     [rbp+0E0h+var_118], 4
0x1400d8c1e  mov     [rbp+0E0h+var_108], r15
0x1400d8c22  mov     [rbp+0E0h+var_F8], 4
0x1400d8c2a  mov     [rbp+0E0h+var_E8], 4
0x1400d8c32  mov     [rbp+0E0h+var_D8], r15
0x1400d8c36  mov     [rbp+0E0h+var_C8], 4
0x1400d8c3e  mov     [rbp+0E0h+var_B8], 4
0x1400d8c46  mov     [rbp+0E0h+var_A8], r15
0x1400d8c4a  mov     [rbp+0E0h+var_98], 4
0x1400d8c52  mov     [rbp+0E0h+var_88], 4
0x1400d8c5a  mov     [rbp+0E0h+var_78], r15
0x1400d8c5e  mov     [rbp+0E0h+var_68], 4
0x1400d8c66  mov     [rbp+0E0h+var_58], 4
0x1400d8c71  mov     [rbp+0E0h+var_50], rax
0x1400d8c78  lea     rdx, byte_1401667CB; int
0x1400d8c7f  lea     rax, [rsp+1E0h+var_170]
0x1400d8c84  mov     [rbp+0E0h+var_48], r15
0x1400d8c8b  mov     [rsp+1E0h+var_1B8], rax; __int64
0x1400d8c90  mov     [rsp+1E0h+var_1C0], 13h; ULONG
0x1400d8c98  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400d8c9d  cmp     [rbx+1460h], esi
0x1400d8ca3  jnz     short loc_1400D8CC9
0x1400d8ca5  cmp     [rbx+146Ch], esi
0x1400d8cab  jnz     short loc_1400D8CC9
0x1400d8cad  cmp     [rbx+1478h], esi
0x1400d8cb3  jnz     short loc_1400D8CC9
0x1400d8cb5  cmp     [rbx+1484h], esi
0x1400d8cbb  jnz     short loc_1400D8CC9
0x1400d8cbd  cmp     [rbx+1490h], esi
0x1400d8cc3  jz      loc_1400D8EC5
0x1400d8cc9  mov     eax, cs:dword_140176178
0x1400d8ccf  cmp     eax, 5
0x1400d8cd2  jbe     loc_1400D8EC5
0x1400d8cd8  mov     rdx, 400000000000h
0x1400d8ce2  call    _tlgKeywordOn
0x1400d8ce7  test    al, al
0x1400d8ce9  jz      loc_1400D8EC5
0x1400d8cef  lea     rax, [rbx+1408h]
0x1400d8cf6  mov     [rbp+0E0h+var_148], 10h
0x1400d8cfe  mov     [rbp+0E0h+var_150], rax
0x1400d8d02  mov     eax, [rbx+38h]
0x1400d8d05  mov     [rsp+1E0h+var_180], eax
0x1400d8d09  lea     rax, [rsp+1E0h+var_180]
0x1400d8d0e  mov     [rbp+0E0h+var_140], rax
0x1400d8d12  mov     eax, [rbx+1460h]
0x1400d8d18  mov     [rsp+1E0h+var_184], eax
0x1400d8d1c  lea     rax, [rsp+1E0h+var_184]
0x1400d8d21  mov     [rbp+0E0h+var_130], rax
0x1400d8d25  mov     eax, [rbx+1464h]
0x1400d8d2b  mov     [rsp+1E0h+var_188], eax
0x1400d8d2f  lea     rax, [rsp+1E0h+var_188]
0x1400d8d34  mov     [rbp+0E0h+var_120], rax
0x1400d8d38  mov     al, [rbx+1468h]
0x1400d8d3e  mov     [rsp+1E0h+var_1AC], al
0x1400d8d42  lea     rax, [rsp+1E0h+var_1AC]
0x1400d8d47  mov     [rbp+0E0h+var_110], rax
0x1400d8d4b  mov     eax, [rbx+146Ch]
0x1400d8d51  mov     [rsp+1E0h+var_18C], eax
0x1400d8d55  lea     rax, [rsp+1E0h+var_18C]
0x1400d8d5a  mov     [rbp+0E0h+var_100], rax
0x1400d8d5e  mov     eax, [rbx+1470h]
0x1400d8d64  mov     [rsp+1E0h+var_190], eax
0x1400d8d68  lea     rax, [rsp+1E0h+var_190]
0x1400d8d6d  mov     [rbp+0E0h+var_F0], rax
0x1400d8d71  mov     al, [rbx+1474h]
0x1400d8d77  mov     [rsp+1E0h+var_1AD], al
0x1400d8d7b  lea     rax, [rsp+1E0h+var_1AD]
0x1400d8d80  mov     [rbp+0E0h+var_E0], rax
0x1400d8d84  mov     eax, [rbx+1478h]
0x1400d8d8a  mov     [rsp+1E0h+var_194], eax
0x1400d8d8e  lea     rax, [rsp+1E0h+var_194]
0x1400d8d93  mov     [rbp+0E0h+var_D0], rax
0x1400d8d97  mov     eax, [rbx+147Ch]
0x1400d8d9d  mov     [rsp+1E0h+var_198], eax
0x1400d8da1  lea     rax, [rsp+1E0h+var_198]
0x1400d8da6  mov     [rbp+0E0h+var_C0], rax
0x1400d8daa  mov     al, [rbx+1480h]
0x1400d8db0  mov     [rsp+1E0h+var_1AE], al
0x1400d8db4  lea     rax, [rsp+1E0h+var_1AE]
0x1400d8db9  mov     [rbp+0E0h+var_B0], rax
0x1400d8dbd  mov     eax, [rbx+1484h]
0x1400d8dc3  mov     [rsp+1E0h+var_19C], eax
0x1400d8dc7  lea     rax, [rsp+1E0h+var_19C]
0x1400d8dcc  mov     [rbp+0E0h+var_A0], rax
0x1400d8dd0  mov     eax, [rbx+1488h]
0x1400d8dd6  mov     [rsp+1E0h+var_1A0], eax
0x1400d8dda  lea     rax, [rsp+1E0h+var_1A0]
0x1400d8ddf  mov     [rbp+0E0h+var_90], rax
0x1400d8de3  mov     al, [rbx+148Ch]
0x1400d8de9  mov     [rsp+1E0h+var_1AF], al
0x1400d8ded  lea     rax, [rsp+1E0h+var_1AF]
0x1400d8df2  mov     [rbp+0E0h+var_80], rax
0x1400d8df6  mov     eax, [rbx+1490h]
0x1400d8dfc  mov     [rsp+1E0h+var_1A4], eax
0x1400d8e00  lea     rax, [rsp+1E0h+var_1A4]
0x1400d8e05  mov     [rbp+0E0h+var_70], rax
0x1400d8e09  mov     eax, [rbx+1494h]
0x1400d8e0f  mov     [rsp+1E0h+var_1A8], eax
0x1400d8e13  lea     rax, [rsp+1E0h+var_1A8]
0x1400d8e18  mov     [rbp+0E0h+var_60], rax
0x1400d8e1f  mov     al, [rbx+1498h]
0x1400d8e25  mov     [rsp+1E0h+var_1B0], al
0x1400d8e29  lea     rax, [rsp+1E0h+var_1B0]
0x1400d8e2e  mov     [rbp+0E0h+var_138], 4
0x1400d8e36  mov     [rbp+0E0h+var_128], 4
0x1400d8e3e  mov     [rbp+0E0h+var_118], 4
0x1400d8e46  mov     [rbp+0E0h+var_108], r15
0x1400d8e4a  mov     [rbp+0E0h+var_F8], 4
0x1400d8e52  mov     [rbp+0E0h+var_E8], 4
0x1400d8e5a  mov     [rbp+0E0h+var_D8], r15
0x1400d8e5e  mov     [rbp+0E0h+var_C8], 4
0x1400d8e66  mov     [rbp+0E0h+var_B8], 4
0x1400d8e6e  mov     [rbp+0E0h+var_A8], r15
0x1400d8e72  mov     [rbp+0E0h+var_98], 4
0x1400d8e7a  mov     [rbp+0E0h+var_88], 4
0x1400d8e82  mov     [rbp+0E0h+var_78], r15
0x1400d8e86  mov     [rbp+0E0h+var_68], 4
0x1400d8e8e  mov     [rbp+0E0h+var_58], 4
0x1400d8e99  mov     [rbp+0E0h+var_50], rax
0x1400d8ea0  lea     rdx, word_140167866; int
0x1400d8ea7  lea     rax, [rsp+1E0h+var_170]
0x1400d8eac  mov     [rbp+0E0h+var_48], r15
0x1400d8eb3  mov     [rsp+1E0h+var_1B8], rax; __int64
0x1400d8eb8  mov     [rsp+1E0h+var_1C0], 13h; ULONG
0x1400d8ec0  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400d8ec5  mov     rcx, rbx
0x1400d8ec8  call    StorpInitializeHierarchicalResetBuckets
0x1400d8ecd  mov     eax, [rbx+1520h]
0x1400d8ed3  mov     r14d, 3
0x1400d8ed9  test    r15b, al
0x1400d8edc  jnz     short loc_1400D8F2D
0x1400d8ede  call    RaidAcquireAdapterRemoveLock
0x1400d8ee3  test    eax, eax
0x1400d8ee5  js      short loc_1400D8F2D
0x1400d8ee7  mov     rcx, [rbx+8]; DeviceObject
0x1400d8eeb  call    cs:__imp_IoAllocateWorkItem
0x1400d8ef2  nop     dword ptr [rax+rax+00h]
0x1400d8ef7  test    rax, rax
0x1400d8efa  jz      short loc_1400D8F1A
0x1400d8efc  mov     r9, rax; Context
0x1400d8eff  lea     rdx, StorpAdapterTopologyWorkItemRoutine; WorkerRoutine
0x1400d8f06  mov     r8d, r14d; QueueType
0x1400d8f09  mov     rcx, rax; IoWorkItem
0x1400d8f0c  call    cs:__imp_IoQueueWorkItem
0x1400d8f13  nop     dword ptr [rax+rax+00h]
0x1400d8f18  jmp     short loc_1400D8F2D
0x1400d8f1a  mov     rcx, [rbx+140h]; RunRefCacheAware
0x1400d8f21  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400d8f28  nop     dword ptr [rax+rax+00h]
0x1400d8f2d  test    dil, dil
0x1400d8f30  jns     loc_1400D8FBC
0x1400d8f36  cmp     [rbx+1530h], sil
0x1400d8f3d  jnz     short loc_1400D8F61
0x1400d8f3f  mov     eax, [rbx+1520h]
0x1400d8f45  and     eax, 0Ch
0x1400d8f48  cmp     al, 0Ch
0x1400d8f4a  jz      short loc_1400D8F61
0x1400d8f4c  cmp     dword ptr [rbx+10F4h], 11h
0x1400d8f53  jnz     short loc_1400D8F61
0x1400d8f55  mov     rcx, rbx
0x1400d8f58  call    StorIsMFNDSupported
0x1400d8f5d  test    al, al
0x1400d8f5f  jnz     short loc_1400D8F6A
0x1400d8f61  cmp     dword ptr [rbx+10F4h], 13h
0x1400d8f68  jnz     short loc_1400D8FBC
0x1400d8f6a  mov     rcx, rbx
0x1400d8f6d  call    RaidAcquireAdapterRemoveLock
0x1400d8f72  test    eax, eax
0x1400d8f74  js      short loc_1400D8FBC
0x1400d8f76  mov     rcx, [rbx+8]; DeviceObject
0x1400d8f7a  call    cs:__imp_IoAllocateWorkItem
0x1400d8f81  nop     dword ptr [rax+rax+00h]
0x1400d8f86  test    rax, rax
0x1400d8f89  jz      short loc_1400D8FA9
0x1400d8f8b  mov     r9, rax; Context
0x1400d8f8e  lea     rdx, StorpAdapterHealthWorkItemRoutine; WorkerRoutine
0x1400d8f95  mov     r8d, r14d; QueueType
0x1400d8f98  mov     rcx, rax; IoWorkItem
0x1400d8f9b  call    cs:__imp_IoQueueWorkItem
0x1400d8fa2  nop     dword ptr [rax+rax+00h]
0x1400d8fa7  jmp     short loc_1400D8FBC
0x1400d8fa9  mov     rcx, [rbx+140h]; RunRefCacheAware
0x1400d8fb0  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400d8fb7  nop     dword ptr [rax+rax+00h]
0x1400d8fbc  mov     rcx, [rbp+0E0h+var_40]
0x1400d8fc3  xor     rcx, rsp; StackCookie
0x1400d8fc6  call    __security_check_cookie
0x1400d8fcb  add     rsp, 1B8h
0x1400d8fd2  pop     r15
0x1400d8fd4  pop     r14
0x1400d8fd6  pop     rdi
0x1400d8fd7  pop     rsi
0x1400d8fd8  pop     rbx
0x1400d8fd9  pop     rbp
0x1400d8fda  retn
```
