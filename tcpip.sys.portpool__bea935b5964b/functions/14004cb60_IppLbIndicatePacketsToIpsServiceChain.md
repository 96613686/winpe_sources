# IppLbIndicatePacketsToIpsServiceChain

- ea: `0x14004cb60`
- end: `0x14004d039`
- name: `IppLbIndicatePacketsToIpsServiceChain`
- size: `1241`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002d4e0`

## callees

- `0x14004cb60`
- `0x14004d040`
- `0x14004d160`
- `0x14004e070`
- `0x1400ff954`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14004cecf`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14004cecf`
- `ntoskrnl!IoQueueWorkItem` at `0x14004ccd7`
- `ntoskrnl!IoQueueWorkItem` at `0x14004cfa0`
- `ntoskrnl!IoQueueWorkItem` at `0x14004ccd7`
- `ntoskrnl!IoQueueWorkItem` at `0x14004cfa0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004cc4f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004cf28`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004cc4f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004cf28`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14004cc19`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14004cefd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14004cc19`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14004cefd`

## pseudocode

```c
void __fastcall IppLbIndicatePacketsToIpsServiceChain(__int64 a1, __int64 a2)
{
  bool v2; // r12
  __int64 v3; // rdi
  __int64 v4; // r15
  __int64 AnySubInterfaceOnInterface; // rsi
  __int64 *v6; // rbx
  _DWORD *v7; // rax
  signed __int64 v8; // rax
  bool v9; // cc
  signed __int64 v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // r9
  _OWORD *v13; // r10
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  _QWORD *v16; // r13
  unsigned __int16 v17; // dx
  _DWORD *v18; // r15
  __int64 v19; // r14
  __int64 v20; // rcx
  char *v21; // r8
  _QWORD *v22; // rcx
  signed __int64 v23; // r14
  signed __int64 v24; // r14
  _QWORD *v25; // rdi
  int v26; // r15d
  _QWORD *v27; // rcx
  bool v28; // [rsp+50h] [rbp-B0h]
  __int128 v29; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v32; // [rsp+78h] [rbp-88h]
  _QWORD *v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  int v35[2]; // [rsp+90h] [rbp-70h]
  _QWORD *v36; // [rsp+98h] [rbp-68h]
  _QWORD *v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  _OWORD v40[61]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = 0;
  v38 = a1;
  v3 = a1;
  v39 = a2;
  v28 = 0;
  v34 = 0;
  v4 = 0;
  v31 = 0;
  AnySubInterfaceOnInterface = 0;
  v32 = &v31;
  while ( 1 )
  {
    v6 = *(__int64 **)v3;
    if ( !*(_QWORD *)v3 )
      break;
    *(_QWORD *)v3 = *v6;
    *v6 = 0;
    if ( *(__int64 **)(v3 + 8) == v6 )
      *(_QWORD *)(v3 + 8) = v3;
    v7 = (_DWORD *)v6[25];
    *v6 = 0;
    if ( *v7 != 1 )
      goto LABEL_21;
    if ( *(_QWORD *)(v6[27] + 8) != v4 )
    {
      if ( v2 )
      {
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v4 + 96) + 16LL), 1u);
        v2 = 0;
        v28 = 0;
      }
      if ( AnySubInterfaceOnInterface )
      {
        v8 = _InterlockedExchangeAdd64(
               (volatile signed __int64 *)(AnySubInterfaceOnInterface + 64),
               0xFFFFFFFFFFFFFFFFuLL);
        v9 = v8 <= 1;
        v10 = v8 - 1;
        if ( v9 )
        {
          if ( v10 )
            __fastfail(0xEu);
          if ( KeGetCurrentIrql() )
            IoQueueWorkItem(
              *(PIO_WORKITEM *)(AnySubInterfaceOnInterface + 56),
              IppCleanupSubInterfaceWorkerRoutine,
              DelayedWorkQueue,
              (PVOID)AnySubInterfaceOnInterface);
          else
            IppCleanupSubInterfaceWorkerRoutine(IppDeviceObject, (PVOID)AnySubInterfaceOnInterface);
        }
      }
      v34 = *(_QWORD *)(v6[27] + 8);
      v4 = v34;
      AnySubInterfaceOnInterface = IppFindAnySubInterfaceOnInterface(v34);
      if ( AnySubInterfaceOnInterface )
      {
        v11 = *(_QWORD *)(v4 + 96);
        v2 = v11
          && !*(_BYTE *)(v11 + 40)
          && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v11 + 16), 1u);
        v28 = v2;
      }
    }
    if ( !v2 )
      goto LABEL_21;
    LOBYTE(v30) = 0;
    v29 = 0;
    memset(v40, 0, 0x3C4u);
    v12 = v6 + 1;
    v33 = *(_QWORD **)(AnySubInterfaceOnInterface + 8);
    v13 = &v40[3];
    v14 = *v33;
    v15 = v6[1];
    v37 = (_QWORD *)v33[12];
    v16 = (_QWORD *)*v37;
    *(_QWORD *)v35 = *(_QWORD *)(v14 + 40);
    *(_QWORD *)&v40[3] = 0;
    v17 = -1;
    *(_QWORD *)&v40[2] = 0x1000000000FFFFLL;
    LODWORD(v40[0]) = 1918062665;
    *(_QWORD *)&v40[6] = 0x800000000LL;
    *((_QWORD *)&v40[0] + 1) = AnySubInterfaceOnInterface;
    *(_QWORD *)&v40[1] = 0;
    *((_QWORD *)&v40[1] + 1) = &v40[3];
    BYTE8(v40[2]) = 0;
    HIDWORD(v40[2]) = 1;
    *((_QWORD *)&v40[3] + 1) = v15;
    v40[4] = v15;
    v40[5] = 0;
    if ( v16 != v37 )
    {
      v18 = v33;
      do
      {
        v19 = v16[2];
        while ( 1 )
        {
          LOWORD(v40[2]) = ++v17;
          if ( v17 > WORD1(v40[2]) )
            break;
          v21 = (char *)v13 + 56 * v17;
          v22 = v21 + 8;
          if ( *((_QWORD *)v21 + 1) && (v21[52] & 4) == 0 && !*((_DWORD *)v21 + 12) )
          {
            v29 = *(_OWORD *)v21;
            v30 = (_QWORD *)*((_QWORD *)v21 + 2);
            *v22 = 0;
            *((_QWORD *)v21 + 2) = v22;
            if ( *(_BYTE *)(v19 + 62) && (BYTE8(v40[2]) & 2) == 0 )
            {
              v25 = (_QWORD *)*((_QWORD *)&v29 + 1);
              v26 = v35[0];
              v30 = (_QWORD *)&v29 + 1;
              *((_QWORD *)&v29 + 1) = 0;
              do
              {
                v36 = v25;
                v25 = (_QWORD *)*v25;
                *v36 = 0;
                if ( !(unsigned __int8)IppGroupFragmentsForIpsnpi(v26) )
                {
                  v27 = v36;
                  *v30 = v36;
                  v30 = v27;
                }
              }
              while ( v25 );
              v18 = v33;
            }
            if ( *((_QWORD *)&v29 + 1) )
              (*(void (__fastcall **)(_QWORD, _OWORD *, _QWORD, _QWORD, _DWORD, _QWORD, __int128 *, int))(*(_QWORD *)(v19 + 80) + 16LL))(
                *(_QWORD *)(v19 + 88),
                v40,
                **(unsigned int **)v18,
                *(unsigned int *)(*(_QWORD *)v18 + 20LL),
                v18[2],
                v16[3],
                &v29,
                1);
            v17 = v40[2];
            v13 = (_OWORD *)*((_QWORD *)&v40[1] + 1);
          }
        }
        v17 = -1;
        LOWORD(v40[2]) = -1;
        WORD1(v40[2]) = WORD2(v40[2]);
        if ( *(_BYTE *)(v19 + 62) )
          BYTE8(v40[2]) |= 2u;
        v16 = (_QWORD *)*v16;
      }
      while ( v16 != v37 );
      v3 = v38;
      v12 = v6 + 1;
      v4 = v34;
      v2 = v28;
    }
    IppCompleteIpsReceiveContext((__int64)v40, v12);
    if ( !v6[1] )
    {
      v20 = v39;
      **(_QWORD **)(v39 + 8) = v6;
      *(_QWORD *)(v20 + 8) = v6;
    }
    else
    {
LABEL_21:
      *v32 = (__int64)v6;
      v32 = v6;
    }
  }
  if ( v2 )
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v4 + 96) + 16LL), 1u);
  if ( AnySubInterfaceOnInterface )
  {
    v23 = _InterlockedExchangeAdd64((volatile signed __int64 *)(AnySubInterfaceOnInterface + 64), 0xFFFFFFFFFFFFFFFFuLL);
    v9 = v23 <= 1;
    v24 = v23 - 1;
    if ( v9 )
    {
      if ( v24 )
        __fastfail(0xEu);
      if ( KeGetCurrentIrql() )
        IoQueueWorkItem(
          *(PIO_WORKITEM *)(AnySubInterfaceOnInterface + 56),
          IppCleanupSubInterfaceWorkerRoutine,
          DelayedWorkQueue,
          (PVOID)AnySubInterfaceOnInterface);
      else
        IppCleanupSubInterfaceWorkerRoutine(IppDeviceObject, (PVOID)AnySubInterfaceOnInterface);
    }
  }
  if ( v31 )
  {
    **(_QWORD **)(v3 + 8) = v31;
    *(_QWORD *)(v3 + 8) = v32;
  }
}

```

## disassembly

```asm
0x14004cb60  mov     [rsp-8+arg_10], rbx
0x14004cb65  push    rbp
0x14004cb66  push    rsi
0x14004cb67  push    rdi
0x14004cb68  push    r12
0x14004cb6a  push    r13
0x14004cb6c  push    r14
0x14004cb6e  push    r15
0x14004cb70  lea     rbp, [rsp-3A0h]
0x14004cb78  sub     rsp, 4A0h
0x14004cb7f  mov     rax, cs:__security_cookie
0x14004cb86  xor     rax, rsp
0x14004cb89  mov     [rbp+3D0h+var_40], rax
0x14004cb90  xor     r12b, r12b
0x14004cb93  mov     [rbp+3D0h+var_420], rcx
0x14004cb97  mov     rdi, rcx
0x14004cb9a  mov     [rbp+3D0h+var_418], rdx
0x14004cb9e  xor     ecx, ecx
0x14004cba0  mov     [rsp+4D0h+var_480], r12b
0x14004cba5  lea     rax, [rsp+4D0h+var_460]
0x14004cbaa  mov     [rbp+3D0h+var_448], rcx
0x14004cbae  mov     r15d, ecx
0x14004cbb1  mov     [rsp+4D0h+var_460], rcx
0x14004cbb6  mov     esi, ecx
0x14004cbb8  mov     [rsp+4D0h+var_458], rax
0x14004cbbd  mov     r14, 0FFFFFFFFFFFFFFFFh
0x14004cbc4  mov     rbx, [rdi]
0x14004cbc7  test    rbx, rbx
0x14004cbca  jz      loc_14004CEEB
0x14004cbd0  mov     rax, [rbx]
0x14004cbd3  mov     [rdi], rax
0x14004cbd6  mov     [rbx], rcx
0x14004cbd9  cmp     [rdi+8], rbx
0x14004cbdd  jnz     short loc_14004CBE3
0x14004cbdf  mov     [rdi+8], rdi
0x14004cbe3  mov     rax, [rbx+0C8h]
0x14004cbea  mov     [rbx], rcx
0x14004cbed  cmp     dword ptr [rax], 1
0x14004cbf0  jnz     loc_14004CCAF
0x14004cbf6  mov     rax, [rbx+0D8h]
0x14004cbfd  cmp     [rax+8], r15
0x14004cc01  jz      loc_14004CCAA
0x14004cc07  test    r12b, r12b
0x14004cc0a  jz      short loc_14004CC2D
0x14004cc0c  mov     rcx, [r15+60h]
0x14004cc10  mov     edx, 1; Count
0x14004cc15  mov     rcx, [rcx+10h]; RunRef
0x14004cc19  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14004cc20  nop     dword ptr [rax+rax+00h]
0x14004cc25  xor     r12b, r12b
0x14004cc28  mov     [rsp+4D0h+var_480], r12b
0x14004cc2d  test    rsi, rsi
0x14004cc30  jz      short loc_14004CC6E
0x14004cc32  mov     rax, r14
0x14004cc35  lock xadd [rsi+40h], rax
0x14004cc3b  sub     rax, 1
0x14004cc3f  jg      short loc_14004CC6E
0x14004cc41  test    rax, rax
0x14004cc44  jz      short loc_14004CC4F
0x14004cc46  mov     ecx, 0Eh
0x14004cc4b  int     29h; Win8: RtlFailFast(ecx)
0x14004cc4d  jmp     short loc_14004CC6E
0x14004cc4f  call    cs:__imp_KeGetCurrentIrql
0x14004cc56  nop     dword ptr [rax+rax+00h]
0x14004cc5b  test    al, al
0x14004cc5d  jnz     short loc_14004CCC3
0x14004cc5f  mov     rcx, cs:IppDeviceObject; DeviceObject
0x14004cc66  mov     rdx, rsi; Context
0x14004cc69  call    IppCleanupSubInterfaceWorkerRoutine
0x14004cc6e  mov     rax, [rbx+0D8h]
0x14004cc75  mov     r15, [rax+8]
0x14004cc79  mov     rcx, r15
0x14004cc7c  mov     [rbp+3D0h+var_448], r15
0x14004cc80  call    IppFindAnySubInterfaceOnInterface
0x14004cc85  mov     rsi, rax
0x14004cc88  test    rax, rax
0x14004cc8b  jz      short loc_14004CCAA
0x14004cc8d  mov     rcx, [r15+60h]
0x14004cc91  test    rcx, rcx
0x14004cc94  jz      short loc_14004CCA2
0x14004cc96  movzx   eax, byte ptr [rcx+28h]
0x14004cc9a  test    al, al
0x14004cc9c  jz      loc_14004CEC6
0x14004cca2  xor     r12b, r12b
0x14004cca5  mov     [rsp+4D0h+var_480], r12b
0x14004ccaa  test    r12b, r12b
0x14004ccad  jnz     short loc_14004CCE5
0x14004ccaf  mov     rax, [rsp+4D0h+var_458]
0x14004ccb4  xor     ecx, ecx
0x14004ccb6  mov     [rax], rbx
0x14004ccb9  mov     [rsp+4D0h+var_458], rbx
0x14004ccbe  jmp     loc_14004CBC4
0x14004ccc3  mov     rcx, [rsi+38h]; IoWorkItem
0x14004ccc7  lea     rdx, IppCleanupSubInterfaceWorkerRoutine; WorkerRoutine
0x14004ccce  mov     r9, rsi; Context
0x14004ccd1  mov     r8d, 1; QueueType
0x14004ccd7  call    cs:__imp_IoQueueWorkItem
0x14004ccde  nop     dword ptr [rax+rax+00h]
0x14004cce3  jmp     short loc_14004CC6E
0x14004cce5  xor     eax, eax
0x14004cce7  lea     rcx, [rbp+3D0h+var_410]; void *
0x14004cceb  xorps   xmm0, xmm0
0x14004ccee  mov     byte ptr [rsp+4D0h+var_468], al
0x14004ccf2  xor     edx, edx; Val
0x14004ccf4  mov     [rbp+3D0h+var_40C], eax
0x14004ccf7  mov     r8d, 3C4h; Size
0x14004ccfd  movups  [rsp+4D0h+var_478], xmm0
0x14004cd02  call    memset
0x14004cd07  mov     rcx, [rsi+8]
0x14004cd0b  lea     r9, [rbx+8]
0x14004cd0f  xorps   xmm0, xmm0
0x14004cd12  mov     [rbp+3D0h+var_450], rcx
0x14004cd16  lea     r10, [rbp+3D0h+var_3E0]
0x14004cd1a  mov     r11, [rcx+60h]
0x14004cd1e  mov     rax, [rcx]
0x14004cd21  mov     rcx, [r9]
0x14004cd24  mov     [rbp+3D0h+var_428], r11
0x14004cd28  mov     r13, [r11]
0x14004cd2b  mov     rax, [rax+28h]
0x14004cd2f  mov     qword ptr [rbp+3D0h+var_440], rax
0x14004cd33  mov     eax, 0FFFFh
0x14004cd38  movups  [rbp+3D0h+var_3E0], xmm0
0x14004cd3c  movzx   edx, ax
0x14004cd3f  mov     [rbp+3D0h+var_3F0], eax
0x14004cd42  xor     eax, eax
0x14004cd44  mov     [rbp+3D0h+var_410], 72535049h
0x14004cd4b  mov     [rbp+3D0h+var_3B0], rax
0x14004cd4f  mov     byte ptr [rbp+3D0h+var_3B0+4], 8
0x14004cd53  mov     [rbp+3D0h+var_408], rsi
0x14004cd57  mov     [rbp+3D0h+var_400], 0
0x14004cd5f  mov     [rbp+3D0h+var_3F8], r10
0x14004cd63  mov     [rbp+3D0h+var_3EC], 100000h
0x14004cd6a  mov     [rbp+3D0h+var_3E8], 0
0x14004cd6e  mov     [rbp+3D0h+var_3E4], 1
0x14004cd75  mov     byte ptr [rbp+3D0h+var_3E0], al
0x14004cd78  mov     qword ptr [rbp+3D0h+var_3E0+8], rcx
0x14004cd7c  movups  [rbp+3D0h+var_3D0], xmm0
0x14004cd80  mov     qword ptr [rbp+3D0h+var_3D0], rcx
0x14004cd84  movups  [rbp+3D0h+var_3C0], xmm0
0x14004cd88  cmp     r13, r11
0x14004cd8b  jz      short loc_14004CDE1
0x14004cd8d  mov     r15, [rbp+3D0h+var_450]
0x14004cd91  mov     r14, [r13+10h]
0x14004cd95  inc     dx
0x14004cd98  mov     word ptr [rbp+3D0h+var_3F0], dx
0x14004cd9c  cmp     dx, word ptr [rbp+3D0h+var_3F0+2]
0x14004cda0  jbe     short loc_14004CE0E
0x14004cda2  movzx   eax, word ptr [rbp+3D0h+var_3EC]
0x14004cda6  mov     edx, 0FFFFh
0x14004cdab  mov     word ptr [rbp+3D0h+var_3F0], dx
0x14004cdaf  mov     word ptr [rbp+3D0h+var_3F0+2], ax
0x14004cdb3  cmp     byte ptr [r14+3Eh], 0
0x14004cdb8  jnz     loc_14004CFAE
0x14004cdbe  mov     r13, [r13+0]
0x14004cdc2  cmp     r13, [rbp+3D0h+var_428]
0x14004cdc6  jnz     short loc_14004CD91
0x14004cdc8  mov     rdi, [rbp+3D0h+var_420]
0x14004cdcc  lea     r9, [rbx+8]
0x14004cdd0  mov     r15, [rbp+3D0h+var_448]
0x14004cdd4  mov     r14, 0FFFFFFFFFFFFFFFFh
0x14004cddb  movzx   r12d, [rsp+4D0h+var_480]
0x14004cde1  mov     rdx, r9
0x14004cde4  lea     rcx, [rbp+3D0h+var_410]
0x14004cde8  call    IppCompleteIpsReceiveContext
0x14004cded  cmp     qword ptr [rbx+8], 0
0x14004cdf2  jnz     loc_14004CCAF
0x14004cdf8  mov     rcx, [rbp+3D0h+var_418]
0x14004cdfc  mov     rax, [rcx+8]
0x14004ce00  mov     [rax], rbx
0x14004ce03  mov     [rcx+8], rbx
0x14004ce07  xor     ecx, ecx
0x14004ce09  jmp     loc_14004CBC4
0x14004ce0e  movzx   eax, dx
0x14004ce11  imul    r8, rax, 38h ; '8'
0x14004ce15  add     r8, r10
0x14004ce18  cmp     qword ptr [r8+8], 0
0x14004ce1d  lea     rcx, [r8+8]
0x14004ce21  jz      loc_14004CD95
0x14004ce27  test    byte ptr [r8+34h], 4
0x14004ce2c  jnz     loc_14004CD95
0x14004ce32  cmp     dword ptr [r8+30h], 0
0x14004ce37  jnz     loc_14004CD95
0x14004ce3d  movups  xmm0, xmmword ptr [r8]
0x14004ce41  movups  [rsp+4D0h+var_478], xmm0
0x14004ce46  movsd   xmm1, qword ptr [r8+10h]
0x14004ce4c  movsd   [rsp+4D0h+var_468], xmm1
0x14004ce52  mov     qword ptr [rcx], 0
0x14004ce59  mov     [r8+10h], rcx
0x14004ce5d  cmp     byte ptr [r14+3Eh], 0
0x14004ce62  jnz     loc_14004CFB7
0x14004ce68  cmp     qword ptr [rsp+4D0h+var_478+8], 0
0x14004ce6e  jz      loc_14004D02C
0x14004ce74  mov     rax, [r15]
0x14004ce77  lea     rcx, [rsp+4D0h+var_478]
0x14004ce7c  mov     [rsp+4D0h+var_498], 1
0x14004ce84  lea     rdx, [rbp+3D0h+var_410]
0x14004ce88  mov     [rsp+4D0h+var_4A0], rcx
0x14004ce8d  mov     r9d, [rax+14h]
0x14004ce91  mov     rcx, [r13+18h]
0x14004ce95  mov     rax, [r14+50h]
0x14004ce99  mov     r8, [r15]
0x14004ce9c  mov     [rsp+4D0h+var_4A8], rcx
0x14004cea1  mov     ecx, [r15+8]
0x14004cea5  mov     rax, [rax+10h]
0x14004cea9  mov     r8d, [r8]
0x14004ceac  mov     [rsp+4D0h+var_4B0], ecx
0x14004ceb0  mov     rcx, [r14+58h]
0x14004ceb4  call    _guard_dispatch_icall
0x14004ceb9  movzx   edx, word ptr [rbp+3D0h+var_3F0]
0x14004cebd  mov     r10, [rbp+3D0h+var_3F8]
0x14004cec1  jmp     loc_14004CD95
0x14004cec6  mov     rcx, [rcx+10h]; RunRefCacheAware
0x14004ceca  mov     edx, 1; Count
0x14004cecf  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x14004ced6  nop     dword ptr [rax+rax+00h]
0x14004cedb  test    al, al
0x14004cedd  jz      loc_14004CCA2
0x14004cee3  mov     r12b, 1
0x14004cee6  jmp     loc_14004CCA5
0x14004ceeb  test    r12b, r12b
0x14004ceee  jz      short loc_14004CF09
0x14004cef0  mov     rcx, [r15+60h]
0x14004cef4  mov     edx, 1; Count
0x14004cef9  mov     rcx, [rcx+10h]; RunRef
0x14004cefd  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14004cf04  nop     dword ptr [rax+rax+00h]
0x14004cf09  test    rsi, rsi
0x14004cf0c  jz      short loc_14004CF47
0x14004cf0e  lock xadd [rsi+40h], r14
0x14004cf14  sub     r14, 1
0x14004cf18  jg      short loc_14004CF47
0x14004cf1a  test    r14, r14
0x14004cf1d  jz      short loc_14004CF28
0x14004cf1f  mov     ecx, 0Eh
0x14004cf24  int     29h; Win8: RtlFailFast(ecx)
0x14004cf26  jmp     short loc_14004CF47
0x14004cf28  call    cs:__imp_KeGetCurrentIrql
0x14004cf2f  nop     dword ptr [rax+rax+00h]
0x14004cf34  test    al, al
0x14004cf36  jnz     short loc_14004CF8C
0x14004cf38  mov     rcx, cs:IppDeviceObject; DeviceObject
0x14004cf3f  mov     rdx, rsi; Context
0x14004cf42  call    IppCleanupSubInterfaceWorkerRoutine
0x14004cf47  mov     rcx, [rsp+4D0h+var_460]
0x14004cf4c  test    rcx, rcx
0x14004cf4f  jz      short loc_14004CF61
0x14004cf51  mov     rax, [rdi+8]
0x14004cf55  mov     [rax], rcx
0x14004cf58  mov     rax, [rsp+4D0h+var_458]
0x14004cf5d  mov     [rdi+8], rax
0x14004cf61  mov     rcx, [rbp+3D0h+var_40]
0x14004cf68  xor     rcx, rsp; StackCookie
0x14004cf6b  call    __security_check_cookie
0x14004cf70  mov     rbx, [rsp+4D0h+arg_10]
0x14004cf78  add     rsp, 4A0h
0x14004cf7f  pop     r15
0x14004cf81  pop     r14
0x14004cf83  pop     r13
0x14004cf85  pop     r12
0x14004cf87  pop     rdi
0x14004cf88  pop     rsi
0x14004cf89  pop     rbp
0x14004cf8a  retn
0x14004cf8c  mov     rcx, [rsi+38h]; IoWorkItem
0x14004cf90  lea     rdx, IppCleanupSubInterfaceWorkerRoutine; WorkerRoutine
0x14004cf97  mov     r9, rsi; Context
0x14004cf9a  mov     r8d, 1; QueueType
0x14004cfa0  call    cs:__imp_IoQueueWorkItem
0x14004cfa7  nop     dword ptr [rax+rax+00h]
0x14004cfac  jmp     short loc_14004CF47
0x14004cfae  or      [rbp+3D0h+var_3E8], 2
0x14004cfb2  jmp     loc_14004CDBE
0x14004cfb7  test    [rbp+3D0h+var_3E8], 2
0x14004cfbb  jnz     loc_14004CE68
0x14004cfc1  mov     rdi, qword ptr [rsp+4D0h+var_478+8]
0x14004cfc6  lea     rax, [rsp+4D0h+var_478+8]
0x14004cfcb  mov     r15, qword ptr [rbp+3D0h+var_440]
0x14004cfcf  mov     [rsp+4D0h+var_468], rax
0x14004cfd4  mov     qword ptr [rsp+4D0h+var_478+8], 0
0x14004cfdd  nop     dword ptr [rax]
0x14004cfe0  mov     rcx, rdi
0x14004cfe3  lea     r9, [rsp+4D0h+var_468]
0x14004cfe8  mov     rax, rdi
0x14004cfeb  mov     [rbp+3D0h+var_438], rcx
0x14004cfef  mov     rdi, [rdi]
0x14004cff2  mov     r8, rcx
0x14004cff5  mov     rdx, rsi
0x14004cff8  mov     qword ptr [rcx], 0
0x14004cfff  mov     rcx, r15; int
0x14004d002  call    IppGroupFragmentsForIpsnpi
0x14004d007  test    al, al
0x14004d009  jz      short loc_14004D019
0x14004d00b  test    rdi, rdi
0x14004d00e  jnz     short loc_14004CFE0
0x14004d010  mov     r15, [rbp+3D0h+var_450]
0x14004d014  jmp     loc_14004CE68
0x14004d019  mov     rax, [rsp+4D0h+var_468]
0x14004d01e  mov     rcx, [rbp+3D0h+var_438]
0x14004d022  mov     [rax], rcx
0x14004d025  mov     [rsp+4D0h+var_468], rcx
  ... truncated ...
```
