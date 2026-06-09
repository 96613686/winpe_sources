# FilterInit

- ea: `0x140002c90`
- end: `0x140003173`
- name: `FilterInit`
- size: `1251`
- prototype: `__int64 __fastcall(NDIS_HANDLE NdisHandle)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1400027d0`

## callees

- `0x140002710`
- `0x140002c90`
- `0x1400032fc`
- `0x140003634`
- `0x140007d00`
- `0x14000cd04`
- `0x14000cd98`
- `0x14000cdd8`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000f110`
- `0x14000f200`
- `0x14000f500`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x1400030b3`
- `ntoskrnl!KeInitializeMutex` at `0x1400030b3`
- `ntoskrnl!RtlGUIDFromString` at `0x140002f24`
- `ntoskrnl!RtlGUIDFromString` at `0x140002f24`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003079`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003079`
- `NDIS!NdisFreeMemory` at `0x140002d71`
- `NDIS!NdisFreeMemory` at `0x140002d71`
- `NDIS!NdisFreeNetBufferListPool` at `0x140002fe1`
- `NDIS!NdisFreeNetBufferListPool` at `0x140002fe1`
- `NDIS!NdisInitializeEvent` at `0x14000308f`
- `NDIS!NdisInitializeEvent` at `0x14000308f`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140002dc9`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140002dc9`
- `NDIS!NdisResetEvent` at `0x14000309e`
- `NDIS!NdisResetEvent` at `0x14000309e`

## pseudocode

```c
__int64 __fastcall FilterInit(NDIS_HANDLE NdisHandle, __int64 a2, _QWORD *a3)
{
  int v5; // eax
  char *v6; // rdi
  unsigned int MpCtxs; // r14d
  NDIS_HANDLE v8; // rax
  void *v9; // r13
  unsigned __int16 *v10; // rdx
  unsigned int v11; // ecx
  const void *v12; // rdx
  unsigned __int64 v13; // rbx
  __int16 *v14; // rax
  __int16 v15; // cx
  __int16 *v16; // rax
  __int16 v17; // cx
  void *v18; // rcx
  __int16 v19; // ax
  PDEVICE_OBJECT v20; // rcx
  unsigned __int16 v21; // dx
  int v22; // eax
  int v23; // eax
  unsigned int i; // edx
  __int64 v25; // rax
  __int64 v26; // rcx
  PVOID VirtualAddress; // [rsp+20h] [rbp-30h] BYREF
  _QWORD *v29; // [rsp+28h] [rbp-28h]
  _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+30h] [rbp-20h] BYREF

  v29 = a3;
  Parameters = 0;
  VirtualAddress = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x79u,
      (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v5 = AllocMem(
         NdisHandle,
         **(unsigned __int16 **)(a2 + 40) + 3128 + (unsigned int)**(unsigned __int16 **)(a2 + 16),
         a3,
         &VirtualAddress);
  v6 = (char *)VirtualAddress;
  MpCtxs = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x7Au,
        (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
        v5);
    goto LABEL_8;
  }
  AllocateSpinLock((char *)VirtualAddress + 24, "FilterInit", 2012);
  *((_QWORD *)v6 + 1) = v6;
  *(_QWORD *)v6 = v6;
  *((_DWORD *)v6 + 673) = *(_DWORD *)(a2 + 72);
  *(_QWORD *)&Parameters.Header.Type = 1048960;
  *(_QWORD *)&Parameters.PoolTag = 1179014998;
  v8 = NdisAllocateNetBufferListPool(NdisHandle, &Parameters);
  v9 = v8;
  if ( !v8 )
  {
    MpCtxs = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x7Bu,
        (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    goto LABEL_14;
  }
  *((_QWORD *)v6 + 321) = v8;
  v10 = *(unsigned __int16 **)(a2 + 32);
  v11 = *v10;
  v12 = (const void *)*((_QWORD *)v10 + 1);
  if ( (v11 & 0xFFFFFFFE) > 0x800 )
    v11 = 2048;
  v13 = v11;
  memmove(v6 + 160, v12, v11);
  *(_WORD *)&v6[2 * (v13 >> 1) + 160] = 0;
  v14 = *(__int16 **)(a2 + 16);
  v15 = *v14;
  *((_WORD *)v6 + 73) = *v14;
  *((_WORD *)v6 + 72) = v15;
  *((_QWORD *)v6 + 19) = v6 + 3128;
  memmove(v6 + 3128, *(const void **)(*(_QWORD *)(a2 + 16) + 8LL), *((unsigned __int16 *)v6 + 72));
  v16 = *(__int16 **)(a2 + 40);
  v17 = *v16;
  *((_WORD *)v6 + 1109) = *v16;
  *((_WORD *)v6 + 1108) = v17;
  v18 = (void *)(*((_QWORD *)v6 + 19) + *((unsigned __int16 *)v6 + 72));
  *((_QWORD *)v6 + 278) = v18;
  memmove(v18, *(const void **)(*(_QWORD *)(a2 + 40) + 8LL), *((unsigned __int16 *)v6 + 1108));
  v19 = *((_WORD *)v6 + 1108) - 16;
  *((_WORD *)v6 + 1117) = v19;
  *((_WORD *)v6 + 1116) = v19;
  *((_QWORD *)v6 + 280) = *((_QWORD *)v6 + 278) + 16LL;
  MpCtxs = RtlGUIDFromString((PCUNICODE_STRING)(v6 + 2232), (GUID *)(v6 + 2248));
  if ( MpCtxs )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_26;
    v21 = 124;
LABEL_25:
    WPP_SF_d((__int64)v20->AttachedDevice, v21, (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids, MpCtxs);
LABEL_26:
    NdisFreeNetBufferListPool(v9);
LABEL_14:
    memset(v6 + 24, 0, 0x60u);
    *((_DWORD *)v6 + 24) = 2134;
    *((_QWORD *)v6 + 11) = "FilterInit";
LABEL_8:
    if ( v6 )
      NdisFreeMemory(v6, 0, 0);
    goto LABEL_38;
  }
  *((_DWORD *)v6 + 567) = *(_DWORD *)(a2 + 98);
  *((_WORD *)v6 + 1136) = *(_WORD *)(a2 + 102);
  *((_DWORD *)v6 + 566) = *(_DWORD *)(a2 + 24);
  *((_QWORD *)v6 + 285) = *(_QWORD *)(a2 + 136);
  *((_QWORD *)v6 + 16) = NdisHandle;
  MpCtxs = FilterAllocateMpCtxs((__int64)NdisHandle, a2, (__int64)v6);
  if ( MpCtxs )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_26;
    v21 = 125;
    goto LABEL_25;
  }
  v22 = *((_DWORD *)v6 + 671);
  if ( *((_DWORD *)v6 + 673) == 16 )
    v23 = v22 - 4;
  else
    v23 = v22 - 1;
  *((_DWORD *)v6 + 672) = v23;
  FilterInitPrimaryAdapterMpCtx((__int64)v6);
  for ( i = 1; i < *((_DWORD *)v6 + 671); *(_DWORD *)(*((_QWORD *)v6 + 390) + 8 * v26 + 16) = -1 )
  {
    v25 = i++;
    v26 = 18 * v25;
    *(_QWORD *)(*((_QWORD *)v6 + 390) + 8 * v26 + 8) = v6;
    *(_BYTE *)(*((_QWORD *)v6 + 390) + 8 * v26) = 0;
    *(_DWORD *)(*((_QWORD *)v6 + 390) + 8 * v26 + 104) = -1;
  }
  v6[2288] = 0;
  RtlInitUnicodeString((PUNICODE_STRING)v6 + 165, 0);
  NdisInitializeEvent((PNDIS_EVENT)v6 + 106);
  NdisResetEvent((PNDIS_EVENT)v6 + 106);
  KeInitializeMutex((PRKMUTEX)v6 + 46, 0);
  if ( g_ulSerialNo == -1 )
  {
    InitVirtualizationGlobalData();
    if ( g_ulSerialNo == -1 )
      TraceAssert(
        (int)"INVALID_SERIAL_NUMBER != g_ulSerialNo",
        (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c",
        2111);
  }
  if ( (unsigned int)filterReadLong(0, L"DisableContext", &g_lDisableContext) )
    g_lDisableContext = 0;
  *v29 = v6;
LABEL_38:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x7Eu,
      (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
      MpCtxs);
  return MpCtxs;
}

```

## disassembly

```asm
0x140002c90  mov     [rsp-38h+arg_18], rbx
0x140002c95  push    rbp
0x140002c96  push    rsi
0x140002c97  push    rdi
0x140002c98  push    r12
0x140002c9a  push    r13
0x140002c9c  push    r14
0x140002c9e  push    r15
0x140002ca0  mov     rbp, rsp
0x140002ca3  sub     rsp, 50h
0x140002ca7  mov     rax, cs:__security_cookie
0x140002cae  xor     rax, rsp
0x140002cb1  mov     [rbp+var_10], rax
0x140002cb5  xorps   xmm0, xmm0
0x140002cb8  mov     [rbp+var_28], r8
0x140002cbc  movups  xmmword ptr [rbp+Parameters.Header.Type], xmm0
0x140002cc0  mov     r15, rdx
0x140002cc3  mov     [rbp+VirtualAddress], 0
0x140002ccb  mov     r12, rcx
0x140002cce  mov     rcx, cs:WPP_GLOBAL_Control
0x140002cd5  lea     rbx, WPP_GLOBAL_Control
0x140002cdc  cmp     rcx, rbx
0x140002cdf  jz      short loc_140002CFD
0x140002ce1  mov     eax, [rcx+2Ch]
0x140002ce4  test    al, 20h
0x140002ce6  jz      short loc_140002CFD
0x140002ce8  mov     rcx, [rcx+18h]
0x140002cec  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140002cf3  mov     edx, 79h ; 'y'
0x140002cf8  call    WPP_SF_
0x140002cfd  mov     rax, [r15+10h]
0x140002d01  lea     r9, [rbp+VirtualAddress]
0x140002d05  movzx   edx, word ptr [rax]
0x140002d08  mov     rax, [r15+28h]
0x140002d0c  movzx   ecx, word ptr [rax]
0x140002d0f  add     ecx, 0C38h
0x140002d15  add     edx, ecx
0x140002d17  mov     rcx, r12
0x140002d1a  call    AllocMem
0x140002d1f  mov     rdi, [rbp+VirtualAddress]
0x140002d23  mov     r14d, eax
0x140002d26  test    eax, eax
0x140002d28  jz      short loc_140002D82
0x140002d2a  mov     rax, cs:WPP_GLOBAL_Control
0x140002d31  cmp     rax, rbx
0x140002d34  jz      short loc_140002D59
0x140002d36  mov     ecx, [rax+2Ch]
0x140002d39  mov     esi, 1
0x140002d3e  test    sil, cl
0x140002d41  jz      short loc_140002D59
0x140002d43  mov     rcx, [rax+18h]
0x140002d47  lea     edx, [rsi+79h]
0x140002d4a  mov     r9d, r14d
0x140002d4d  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140002d54  call    WPP_SF_d
0x140002d59  lea     r15, WPP_GLOBAL_Control
0x140002d60  test    rdi, rdi
0x140002d63  jz      loc_140003120
0x140002d69  xor     r8d, r8d; MemoryFlags
0x140002d6c  xor     edx, edx; Length
0x140002d6e  mov     rcx, rdi; VirtualAddress
0x140002d71  call    cs:__imp_NdisFreeMemory
0x140002d78  nop     dword ptr [rax+rax+00h]
0x140002d7d  jmp     loc_140003120
0x140002d82  lea     rcx, [rdi+18h]
0x140002d86  mov     r8d, 7DCh
0x140002d8c  lea     rdx, aFilterinit; "FilterInit"
0x140002d93  call    AllocateSpinLock
0x140002d98  mov     [rdi+8], rdi
0x140002d9c  lea     rdx, [rbp+Parameters]; Parameters
0x140002da0  mov     [rdi], rdi
0x140002da3  mov     esi, 1
0x140002da8  mov     eax, [r15+48h]
0x140002dac  mov     rcx, r12; NdisHandle
0x140002daf  mov     [rdi+0A84h], eax
0x140002db5  mov     qword ptr [rbp+Parameters.Header.Type], 100180h
0x140002dbd  lea     r14d, [rsi+0Fh]
0x140002dc1  mov     qword ptr [rbp+Parameters.PoolTag], 46465756h
0x140002dc9  call    cs:__imp_NdisAllocateNetBufferListPool
0x140002dd0  nop     dword ptr [rax+rax+00h]
0x140002dd5  mov     r13, rax
0x140002dd8  test    rax, rax
0x140002ddb  jnz     short loc_140002E37
0x140002ddd  mov     r14d, 0C000009Ah
0x140002de3  mov     rcx, cs:WPP_GLOBAL_Control
0x140002dea  cmp     rcx, rbx
0x140002ded  jz      short loc_140002E0A
0x140002def  mov     eax, [rcx+2Ch]
0x140002df2  test    sil, al
0x140002df5  jz      short loc_140002E0A
0x140002df7  mov     rcx, [rcx+18h]
0x140002dfb  lea     edx, [rsi+7Ah]
0x140002dfe  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140002e05  call    WPP_SF_
0x140002e0a  lea     r15, WPP_GLOBAL_Control
0x140002e11  xor     edx, edx; Val
0x140002e13  lea     rcx, [rdi+18h]; void *
0x140002e17  lea     r8d, [rdx+60h]; Size
0x140002e1b  call    memset
0x140002e20  lea     rax, aFilterinit; "FilterInit"
0x140002e27  mov     dword ptr [rdi+60h], 856h
0x140002e2e  mov     [rdi+58h], rax
0x140002e32  jmp     loc_140002D60
0x140002e37  mov     [rdi+0A08h], r13
0x140002e3e  mov     r8d, 800h
0x140002e44  mov     rdx, [r15+20h]
0x140002e48  movzx   ecx, word ptr [rdx]
0x140002e4b  mov     rdx, [rdx+8]; Src
0x140002e4f  mov     eax, ecx
0x140002e51  and     eax, 0FFFFFFFEh
0x140002e54  cmp     eax, r8d
0x140002e57  cmova   ecx, r8d
0x140002e5b  mov     ebx, ecx
0x140002e5d  lea     rcx, [rdi+0A0h]; void *
0x140002e64  mov     r8d, ebx; Size
0x140002e67  call    memmove
0x140002e6c  xor     eax, eax
0x140002e6e  shr     rbx, 1
0x140002e71  mov     [rdi+rbx*2+0A0h], ax
0x140002e79  mov     rax, [r15+10h]
0x140002e7d  movzx   ecx, word ptr [rax]
0x140002e80  mov     [rdi+92h], cx
0x140002e87  mov     [rdi+90h], cx
0x140002e8e  lea     rcx, [rdi+0C38h]; void *
0x140002e95  mov     [rdi+98h], rcx
0x140002e9c  mov     rdx, [r15+10h]
0x140002ea0  movzx   r8d, word ptr [rdi+90h]; Size
0x140002ea8  mov     rdx, [rdx+8]; Src
0x140002eac  call    memmove
0x140002eb1  mov     rax, [r15+28h]
0x140002eb5  movzx   ecx, word ptr [rax]
0x140002eb8  mov     [rdi+8AAh], cx
0x140002ebf  mov     [rdi+8A8h], cx
0x140002ec6  movzx   ecx, word ptr [rdi+90h]
0x140002ecd  add     rcx, [rdi+98h]; void *
0x140002ed4  mov     [rdi+8B0h], rcx
0x140002edb  mov     rdx, [r15+28h]
0x140002edf  movzx   r8d, word ptr [rdi+8A8h]; Size
0x140002ee7  mov     rdx, [rdx+8]; Src
0x140002eeb  call    memmove
0x140002ef0  movzx   eax, word ptr [rdi+8A8h]
0x140002ef7  lea     rcx, [rdi+8B8h]; GuidString
0x140002efe  sub     ax, r14w
0x140002f02  lea     rdx, [rdi+8C8h]; Guid
0x140002f09  mov     [rdi+8BAh], ax
0x140002f10  mov     [rcx], ax
0x140002f13  mov     rax, [rdi+8B0h]
0x140002f1a  add     rax, r14
0x140002f1d  mov     [rdi+8C0h], rax
0x140002f24  call    cs:__imp_RtlGUIDFromString
0x140002f2b  nop     dword ptr [rax+rax+00h]
0x140002f30  mov     r14d, eax
0x140002f33  test    eax, eax
0x140002f35  jz      short loc_140002F61
0x140002f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f3e  lea     r15, WPP_GLOBAL_Control
0x140002f45  cmp     rcx, r15
0x140002f48  jz      loc_140002FDE
0x140002f4e  mov     eax, [rcx+2Ch]
0x140002f51  test    sil, al
0x140002f54  jz      loc_140002FDE
0x140002f5a  mov     edx, 7Ch ; '|'
0x140002f5f  jmp     short loc_140002FCB
0x140002f61  mov     eax, [r15+62h]
0x140002f65  mov     r8, rdi
0x140002f68  mov     [rdi+8DCh], eax
0x140002f6e  mov     rdx, r15
0x140002f71  movzx   eax, word ptr [r15+66h]
0x140002f76  mov     rcx, r12
0x140002f79  mov     [rdi+8E0h], ax
0x140002f80  mov     eax, [r15+18h]
0x140002f84  mov     [rdi+8D8h], eax
0x140002f8a  mov     rax, [r15+88h]
0x140002f91  mov     [rdi+8E8h], rax
0x140002f98  mov     [rdi+80h], r12
0x140002f9f  call    FilterAllocateMpCtxs
0x140002fa4  mov     r14d, eax
0x140002fa7  test    eax, eax
0x140002fa9  jz      short loc_140002FF2
0x140002fab  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fb2  lea     r15, WPP_GLOBAL_Control
0x140002fb9  cmp     rcx, r15
0x140002fbc  jz      short loc_140002FDE
0x140002fbe  mov     eax, [rcx+2Ch]
0x140002fc1  test    sil, al
0x140002fc4  jz      short loc_140002FDE
0x140002fc6  mov     edx, 7Dh ; '}'
0x140002fcb  mov     rcx, [rcx+18h]
0x140002fcf  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140002fd6  mov     r9d, r14d
0x140002fd9  call    WPP_SF_d
0x140002fde  mov     rcx, r13; PoolHandle
0x140002fe1  call    cs:__imp_NdisFreeNetBufferListPool
0x140002fe8  nop     dword ptr [rax+rax+00h]
0x140002fed  jmp     loc_140002E11
0x140002ff2  cmp     dword ptr [rdi+0A84h], 10h
0x140002ff9  mov     eax, [rdi+0A7Ch]
0x140002fff  jnz     short loc_140003006
0x140003001  sub     eax, 4
0x140003004  jmp     short loc_140003008
0x140003006  sub     eax, esi
0x140003008  mov     rcx, rdi
0x14000300b  mov     [rdi+0A80h], eax
0x140003011  call    FilterInitPrimaryAdapterMpCtx
0x140003016  or      r15d, 0FFFFFFFFh
0x14000301a  mov     edx, esi
0x14000301c  cmp     [rdi+0A7Ch], esi
0x140003022  jbe     short loc_140003069
0x140003024  mov     eax, edx
0x140003026  add     edx, esi
0x140003028  lea     rcx, [rax+rax*8]
0x14000302c  mov     rax, [rdi+0C30h]
0x140003033  add     rcx, rcx
0x140003036  mov     [rax+rcx*8+8], rdi
0x14000303b  mov     rax, [rdi+0C30h]
0x140003042  mov     byte ptr [rax+rcx*8], 0
0x140003046  mov     rax, [rdi+0C30h]
0x14000304d  mov     [rax+rcx*8+68h], r15d
0x140003052  mov     rax, [rdi+0C30h]
0x140003059  mov     dword ptr [rax+rcx*8+10h], 0FFFFFFFFh
0x140003061  cmp     edx, [rdi+0A7Ch]
0x140003067  jb      short loc_140003024
0x140003069  lea     rcx, [rdi+0A50h]; DestinationString
0x140003070  mov     byte ptr [rdi+8F0h], 0
0x140003077  xor     edx, edx; SourceString
0x140003079  call    cs:__imp_RtlInitUnicodeString
0x140003080  nop     dword ptr [rax+rax+00h]
0x140003085  lea     rbx, [rdi+9F0h]
0x14000308c  mov     rcx, rbx; Event
0x14000308f  call    cs:__imp_NdisInitializeEvent
0x140003096  nop     dword ptr [rax+rax+00h]
0x14000309b  mov     rcx, rbx; Event
0x14000309e  call    cs:__imp_NdisResetEvent
0x1400030a5  nop     dword ptr [rax+rax+00h]
0x1400030aa  lea     rcx, [rdi+0A10h]; Mutex
0x1400030b1  xor     edx, edx; Level
0x1400030b3  call    cs:__imp_KeInitializeMutex
0x1400030ba  nop     dword ptr [rax+rax+00h]
0x1400030bf  cmp     cs:g_ulSerialNo, r15d
0x1400030c6  jnz     short loc_1400030EF
0x1400030c8  call    InitVirtualizationGlobalData
0x1400030cd  cmp     cs:g_ulSerialNo, r15d
0x1400030d4  jnz     short loc_1400030EF
0x1400030d6  mov     r8d, 83Fh
0x1400030dc  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x1400030e3  lea     rcx, aInvalidSerialN_0; "INVALID_SERIAL_NUMBER != g_ulSerialNo"
0x1400030ea  call    TraceAssert
0x1400030ef  lea     r8, g_lDisableContext
0x1400030f6  xor     ecx, ecx
0x1400030f8  lea     rdx, aDisablecontext; "DisableContext"
0x1400030ff  call    filterReadLong
0x140003104  test    eax, eax
0x140003106  jz      short loc_140003112
0x140003108  mov     cs:g_lDisableContext, 0
0x140003112  mov     rax, [rbp+var_28]
0x140003116  lea     r15, WPP_GLOBAL_Control
0x14000311d  mov     [rax], rdi
0x140003120  mov     rcx, cs:WPP_GLOBAL_Control
0x140003127  cmp     rcx, r15
0x14000312a  jz      short loc_14000314B
0x14000312c  mov     eax, [rcx+2Ch]
0x14000312f  test    al, 20h
0x140003131  jz      short loc_14000314B
0x140003133  mov     rcx, [rcx+18h]
0x140003137  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000313e  mov     edx, 7Eh ; '~'
0x140003143  mov     r9d, r14d
0x140003146  call    WPP_SF_d
0x14000314b  mov     eax, r14d
0x14000314e  mov     rcx, [rbp+var_10]
0x140003152  xor     rcx, rsp; StackCookie
0x140003155  call    __security_check_cookie
0x14000315a  mov     rbx, [rsp+50h+arg_18]
0x140003162  add     rsp, 50h
0x140003166  pop     r15
0x140003168  pop     r14
0x14000316a  pop     r13
0x14000316c  pop     r12
0x14000316e  pop     rdi
0x14000316f  pop     rsi
0x140003170  pop     rbp
0x140003171  retn
```
