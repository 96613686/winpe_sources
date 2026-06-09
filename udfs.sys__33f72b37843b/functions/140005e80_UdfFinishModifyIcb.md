# UdfFinishModifyIcb

- ea: `0x140005e80`
- end: `0x1400062ba`
- name: `UdfFinishModifyIcb`
- size: `1082`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400010f0`
- `0x140004514`
- `0x1400050d8`
- `0x1400154ec`
- `0x140016478`
- `0x14001662c`
- `0x1400177ac`
- `0x1400312c0`
- `0x1400316e8`
- `0x140032d78`
- `0x1400333bc`
- `0x140033548`
- `0x140034450`
- `0x140051d74`
- `0x1400570f4`

## callees

- `0x140005e80`
- `0x1400062c0`
- `0x14000653c`
- `0x14000a6c4`
- `0x14003dd50`
- `0x14004ce00`

## import_xrefs

- `ntoskrnl!CcSetDirtyPinnedData` at `0x14000620c`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14000620c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005fc9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000607c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005fc9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000607c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006045`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400060d5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001cd58`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006045`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400060d5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001cd58`
- `ntoskrnl!CcFlushCache` at `0x14000629d`
- `ntoskrnl!CcFlushCache` at `0x14000629d`

## pseudocode

```c
void __fastcall UdfFinishModifyIcb(__int64 a1, __int64 a2, char a3, __int16 *a4)
{
  char v5; // si
  __int64 v7; // r13
  __int16 *v8; // rbx
  int v9; // r15d
  int *v10; // rcx
  _OWORD *v11; // rax
  __int16 v12; // cx
  __int16 v13; // dx
  int v14; // r8d
  __int64 v15; // r9
  int v16; // eax
  int v17; // eax
  int v18; // esi
  struct _KTHREAD *CurrentThread; // r13
  __int64 v20; // rcx
  __int64 v21; // rax
  struct _KTHREAD *v22; // r13
  __int64 v23; // rcx
  __int64 v24; // rax
  _QWORD *v25; // rcx
  __int16 v26; // ax
  bool v27; // zf
  int v28; // ecx
  _DWORD *v29; // rax
  unsigned int v30; // edx
  unsigned __int16 v31; // ax
  char v32; // cl
  unsigned int i; // edx
  int v34; // edi
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // r8
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+38h] [rbp-50h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+98h] [rbp+10h] BYREF
  char v41; // [rsp+A0h] [rbp+18h]
  __int16 *v42; // [rsp+A8h] [rbp+20h]

  v42 = a4;
  v41 = a3;
  FileOffset.QuadPart = a2;
  v5 = a3;
  v7 = a1;
  v8 = *(__int16 **)a2;
  v9 = 0;
  if ( a3 )
  {
    v10 = (int *)(v8 + 84);
    v11 = v8 + 64;
    if ( *v8 != 261 )
      v11 = v8 + 84;
    *v11 = UdfMsRegId;
    v11[1] = xmmword_140025350;
    if ( a4 )
    {
      v8[17] &= 0x21C7u;
      v12 = v8[17];
      if ( (*((_DWORD *)a4 + 55) & 4) != 0 )
      {
        v12 |= 0x400u;
        v8[17] = v12;
      }
      if ( (*((_DWORD *)a4 + 55) & 0x20) != 0 )
      {
        v12 |= 0x20u;
        v8[17] = v12;
      }
      v13 = *a4;
      v14 = *((_DWORD *)v8 + 11);
      v15 = 2355;
      v16 = 16912;
      if ( (*((_DWORD *)a4 + 55) & 1) != 0 )
      {
        if ( v13 != 2355 )
          v16 = 19026;
        v17 = v14 & ~v16;
      }
      else
      {
        if ( v13 != 2355 )
          v16 = 19026;
        v17 = v14 | v16;
      }
      *((_DWORD *)v8 + 11) = v17;
      if ( (*((_DWORD *)a4 + 53) & 0x40000) != 0 )
      {
        v8[17] = v12 & 0xFF3F;
        *(_QWORD *)(v8 + 18) = -1;
        v9 = 0x40000;
      }
      v18 = 216;
      if ( (*((_DWORD *)a4 + 53) & 0x10000) != 0 )
      {
        CurrentThread = KeGetCurrentThread();
        v20 = *((_QWORD *)a4 + 17);
        if ( CurrentThread != *(struct _KTHREAD **)(v20 + 64) )
        {
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v20 + 80) + 216LL));
          *(_QWORD *)(*((_QWORD *)a4 + 17) + 64LL) = CurrentThread;
        }
        ++*(_DWORD *)(*((_QWORD *)a4 + 17) + 72LL);
        v7 = a1;
        UdfUpdateTimestampsToIcb(a1, a4 + 232, a2, v15);
        *((_DWORD *)a4 + 53) &= ~(v9 | 0x10000);
        --*(_DWORD *)(*((_QWORD *)a4 + 17) + 72LL);
        v21 = *((_QWORD *)a4 + 17);
        if ( !*(_DWORD *)(v21 + 72) )
        {
          *(_QWORD *)(v21 + 64) = 0;
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*((_QWORD *)a4 + 17) + 80LL) + 216LL));
        }
      }
      else if ( v9 )
      {
        v22 = KeGetCurrentThread();
        v23 = *((_QWORD *)a4 + 17);
        if ( v22 != *(struct _KTHREAD **)(v23 + 64) )
        {
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v23 + 80) + 216LL));
          *(_QWORD *)(*((_QWORD *)a4 + 17) + 64LL) = v22;
        }
        ++*(_DWORD *)(*((_QWORD *)a4 + 17) + 72LL);
        *((_DWORD *)a4 + 53) &= ~v9;
        --*(_DWORD *)(*((_QWORD *)a4 + 17) + 72LL);
        v24 = *((_QWORD *)a4 + 17);
        if ( !*(_DWORD *)(v24 + 72) )
        {
          *(_QWORD *)(v24 + 64) = 0;
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*((_QWORD *)a4 + 17) + 80LL) + 216LL));
        }
        v7 = a1;
      }
      v8[24] = a4[250];
      v25 = v8 + 32;
      if ( *v8 != 261 )
        v25 = v8 + 36;
      *v25 = *((unsigned int *)a4 + 80);
      v10 = (int *)(v8 + 84);
    }
    else
    {
      v18 = 216;
    }
    v26 = *v8;
    if ( *v8 != 266 )
      v18 = 176;
    v27 = v26 == 261;
    if ( v26 != 261 )
      v10 = (int *)(v8 + 104);
    v28 = *v10;
    v29 = v8 + 86;
    if ( !v27 )
      v29 = v8 + 106;
    v30 = v18 + v28 + *v29 - 16;
    v31 = -1;
    if ( v30 <= 0xFFFF )
      v31 = v30;
    v8[5] = v31;
    v8[4] = UdfComputeCrc16(v8 + 8, v31);
    v32 = *(_BYTE *)v8 + *((_BYTE *)v8 + 1) + *((_BYTE *)v8 + 2) + *((_BYTE *)v8 + 3);
    *((_BYTE *)v8 + 4) = v32;
    for ( i = 5; i < 0x10; ++i )
    {
      v32 += *((_BYTE *)v8 + i);
      *((_BYTE *)v8 + 4) = v32;
    }
    v34 = *(_DWORD *)(a2 + 28);
    UdfMarkVolumeOpenAndQueueCloseDpc(v7);
    v35 = *(_QWORD *)(v7 + 16);
    if ( *(_QWORD *)(v35 + 352) || *(_WORD *)(a2 + 16) == *(_WORD *)(*(_QWORD *)(v35 + 16) + 84LL) )
      CcSetDirtyPinnedData(*(PVOID *)(a2 + 8), 0);
    else
      UdfVmcbSetSectorState(*(_WORD *)(a2 + 16) == *(_WORD *)(*(_QWORD *)(v35 + 16) + 84LL), v35 + 984, v34, 1, a2);
    v5 = v41;
  }
  UdfUnpinView(v7, a2);
  v36 = *(_QWORD *)(v7 + 16);
  if ( (*(_DWORD *)(v36 + 48) & 0x200) != 0 && v5 && !*(_BYTE *)(a2 + 32) )
  {
    FileOffset.QuadPart = 0;
    IoStatus = 0;
    v37 = *(_QWORD *)((*(_BYTE *)(a2 + 33) != 0 ? 0x30 : 0) + v36 + 272);
    FileOffset.QuadPart = (unsigned __int64)*(unsigned int *)(a2 + 28) << *(_DWORD *)(v36 + 72);
    CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v37 + 424) + 8LL), &FileOffset, *(_DWORD *)(a2 + 24), &IoStatus);
  }
}

```

## disassembly

```asm
0x140005e80  mov     rax, rsp
0x140005e83  mov     [rax+20h], r9
0x140005e87  mov     [rax+18h], r8b
0x140005e8b  mov     [rax+10h], rdx
0x140005e8f  mov     [rax+8], rcx
0x140005e93  push    rbx
0x140005e94  push    rsi
0x140005e95  push    rdi
0x140005e96  push    r12
0x140005e98  push    r13
0x140005e9a  push    r14
0x140005e9c  push    r15
0x140005e9e  sub     rsp, 50h
0x140005ea2  mov     rdi, r9
0x140005ea5  mov     sil, r8b
0x140005ea8  mov     r14, rdx
0x140005eab  mov     r13, rcx
0x140005eae  mov     rbx, [rdx]
0x140005eb1  xor     r15d, r15d
0x140005eb4  test    r8b, r8b
0x140005eb7  jz      loc_140006220
0x140005ebd  lea     rcx, [rbx+0A8h]
0x140005ec4  mov     r9d, 105h
0x140005eca  cmp     [rbx], r9w
0x140005ece  lea     rax, [rbx+80h]
0x140005ed5  jz      short loc_140005EDA
0x140005ed7  mov     rax, rcx
0x140005eda  movups  xmm0, cs:UdfMsRegId
0x140005ee1  movups  xmmword ptr [rax], xmm0
0x140005ee4  movups  xmm1, cs:xmmword_140025350
0x140005eeb  movups  xmmword ptr [rax+10h], xmm1
0x140005eef  test    rdi, rdi
0x140005ef2  jz      loc_14000611A
0x140005ef8  mov     eax, 21C7h
0x140005efd  and     [rbx+22h], ax
0x140005f01  movzx   ecx, word ptr [rbx+22h]
0x140005f05  mov     eax, [rdi+0DCh]
0x140005f0b  test    al, 4
0x140005f0d  jz      short loc_140005F1B
0x140005f0f  mov     eax, 400h
0x140005f14  or      cx, ax
0x140005f17  mov     [rbx+22h], cx
0x140005f1b  mov     eax, [rdi+0DCh]
0x140005f21  test    al, 20h
0x140005f23  jz      short loc_140005F2D
0x140005f25  or      cx, 20h
0x140005f29  mov     [rbx+22h], cx
0x140005f2d  movzx   edx, word ptr [rdi]
0x140005f30  mov     r8d, [rbx+2Ch]
0x140005f34  mov     eax, [rdi+0DCh]
0x140005f3a  mov     r12d, 1
0x140005f40  mov     r9d, 933h
0x140005f46  mov     r10d, 4A52h
0x140005f4c  test    r12b, al
0x140005f4f  mov     eax, 4210h
0x140005f54  jz      short loc_140005F65
0x140005f56  cmp     dx, r9w
0x140005f5a  cmovnz  eax, r10d
0x140005f5e  not     eax
0x140005f60  and     eax, r8d
0x140005f63  jmp     short loc_140005F70
0x140005f65  cmp     dx, r9w
0x140005f69  cmovnz  eax, r10d
0x140005f6d  or      eax, r8d
0x140005f70  mov     [rbx+2Ch], eax
0x140005f73  mov     edx, 40000h
0x140005f78  test    [rdi+0D4h], edx
0x140005f7e  jz      short loc_140005F97
0x140005f80  mov     eax, 0FF3Fh
0x140005f85  and     cx, ax
0x140005f88  mov     [rbx+22h], cx
0x140005f8c  mov     qword ptr [rbx+24h], 0FFFFFFFFFFFFFFFFh
0x140005f94  mov     r15d, edx
0x140005f97  mov     esi, 0D8h
0x140005f9c  test    dword ptr [rdi+0D4h], 10000h
0x140005fa6  jz      loc_140006056
0x140005fac  mov     r13, gs:188h
0x140005fb5  mov     rcx, [rdi+88h]
0x140005fbc  cmp     r13, [rcx+40h]
0x140005fc0  jz      short loc_140005FE0
0x140005fc2  mov     rcx, [rcx+50h]
0x140005fc6  add     rcx, rsi; FastMutex
0x140005fc9  call    cs:__imp_ExAcquireFastMutex
0x140005fd0  nop     dword ptr [rax+rax+00h]
0x140005fd5  mov     rax, [rdi+88h]
0x140005fdc  mov     [rax+40h], r13
0x140005fe0  mov     rax, [rdi+88h]
0x140005fe7  add     [rax+48h], r12d
0x140005feb  lea     rdx, [rdi+1D0h]
0x140005ff2  mov     r8, r14
0x140005ff5  mov     r13, [rsp+88h+arg_0]
0x140005ffd  mov     rcx, r13
0x140006000  call    UdfUpdateTimestampsToIcb
0x140006005  bts     r15d, 10h
0x14000600a  not     r15d
0x14000600d  and     [rdi+0D4h], r15d
0x140006014  mov     rax, [rdi+88h]
0x14000601b  dec     dword ptr [rax+48h]
0x14000601e  mov     rax, [rdi+88h]
0x140006025  cmp     dword ptr [rax+48h], 0
0x140006029  jnz     loc_1400060E9
0x14000602f  mov     qword ptr [rax+40h], 0
0x140006037  mov     rax, [rdi+88h]
0x14000603e  mov     rcx, [rax+50h]
0x140006042  add     rcx, rsi; FastMutex
0x140006045  call    cs:__imp_ExReleaseFastMutex
0x14000604c  nop     dword ptr [rax+rax+00h]
0x140006051  jmp     loc_1400060E9
0x140006056  test    r15d, r15d
0x140006059  jz      loc_1400060E9
0x14000605f  mov     r13, gs:188h
0x140006068  mov     rcx, [rdi+88h]
0x14000606f  cmp     r13, [rcx+40h]
0x140006073  jz      short loc_140006093
0x140006075  mov     rcx, [rcx+50h]
0x140006079  add     rcx, rsi; FastMutex
0x14000607c  call    cs:__imp_ExAcquireFastMutex
0x140006083  nop     dword ptr [rax+rax+00h]
0x140006088  mov     rax, [rdi+88h]
0x14000608f  mov     [rax+40h], r13
0x140006093  mov     rax, [rdi+88h]
0x14000609a  add     [rax+48h], r12d
0x14000609e  not     r15d
0x1400060a1  and     [rdi+0D4h], r15d
0x1400060a8  mov     rax, [rdi+88h]
0x1400060af  dec     dword ptr [rax+48h]
0x1400060b2  mov     rax, [rdi+88h]
0x1400060b9  cmp     dword ptr [rax+48h], 0
0x1400060bd  jnz     short loc_1400060E1
0x1400060bf  mov     qword ptr [rax+40h], 0
0x1400060c7  mov     rax, [rdi+88h]
0x1400060ce  mov     rcx, [rax+50h]
0x1400060d2  add     rcx, rsi; FastMutex
0x1400060d5  call    cs:__imp_ExReleaseFastMutex
0x1400060dc  nop     dword ptr [rax+rax+00h]
0x1400060e1  mov     r13, [rsp+88h+arg_0]
0x1400060e9  movzx   eax, word ptr [rdi+1F4h]
0x1400060f0  mov     [rbx+30h], ax
0x1400060f4  mov     r9d, 105h
0x1400060fa  cmp     [rbx], r9w
0x1400060fe  lea     rcx, [rbx+40h]
0x140006102  jz      short loc_140006108
0x140006104  lea     rcx, [rbx+48h]
0x140006108  mov     eax, [rdi+140h]
0x14000610e  mov     [rcx], rax
0x140006111  lea     rcx, [rbx+0A8h]
0x140006118  jmp     short loc_140006125
0x14000611a  mov     esi, 0D8h
0x14000611f  mov     r12d, 1
0x140006125  movzx   eax, word ptr [rbx]
0x140006128  mov     edx, 0B0h
0x14000612d  lea     r8d, [rdx+5Ah]
0x140006131  cmp     ax, r8w
0x140006135  cmovnz  esi, edx
0x140006138  cmp     ax, r9w
0x14000613c  jz      short loc_140006145
0x14000613e  lea     rcx, [rbx+0D0h]
0x140006145  mov     ecx, [rcx]
0x140006147  lea     rax, [rbx+0ACh]
0x14000614e  jz      short loc_140006157
0x140006150  lea     rax, [rbx+0D4h]
0x140006157  add     ecx, esi
0x140006159  mov     edx, [rax]
0x14000615b  add     edx, 0FFFFFFF0h
0x14000615e  mov     [rsp+88h+var_54], 0
0x140006166  add     edx, ecx
0x140006168  mov     eax, 0FFFFh
0x14000616d  cmp     edx, eax
0x14000616f  ja      short loc_140006174
0x140006171  movzx   eax, dx
0x140006174  mov     [rbx+0Ah], ax
0x140006178  movzx   edx, ax
0x14000617b  lea     rcx, [rbx+10h]
0x14000617f  call    UdfComputeCrc16
0x140006184  mov     [rbx+8], ax
0x140006188  mov     cl, [rbx+3]
0x14000618b  add     cl, [rbx+2]
0x14000618e  add     cl, [rbx+1]
0x140006191  add     cl, [rbx]
0x140006193  mov     [rbx+4], cl
0x140006196  mov     edx, 5
0x14000619b  mov     [rsp+88h+var_54], edx
0x14000619f  cmp     edx, 10h
0x1400061a2  jnb     short loc_1400061B1
0x1400061a4  mov     eax, edx
0x1400061a6  add     cl, [rax+rbx]
0x1400061a9  mov     [rbx+4], cl
0x1400061ac  add     edx, r12d
0x1400061af  jmp     short loc_14000619B
0x1400061b1  mov     edi, [r14+1Ch]
0x1400061b5  xor     bl, bl
0x1400061b7  mov     [rsp+88h+var_58], bl
0x1400061bb  mov     rcx, r13
0x1400061be  call    UdfMarkVolumeOpenAndQueueCloseDpc
0x1400061c3  mov     rdx, [r13+10h]
0x1400061c7  mov     rax, [rdx+10h]
0x1400061cb  movzx   ecx, bl
0x1400061ce  movzx   eax, word ptr [rax+54h]
0x1400061d2  cmp     [r14+10h], ax
0x1400061d7  cmovz   ecx, r12d
0x1400061db  mov     [rsp+88h+var_58], cl
0x1400061df  cmp     qword ptr [rdx+160h], 0
0x1400061e7  jnz     short loc_140006206
0x1400061e9  test    cl, cl
0x1400061eb  jnz     short loc_140006206
0x1400061ed  add     rdx, 3D8h
0x1400061f4  mov     [rsp+88h+var_68], r14
0x1400061f9  mov     r9d, r12d
0x1400061fc  mov     r8d, edi
0x1400061ff  call    UdfVmcbSetSectorState
0x140006204  jmp     short loc_140006218
0x140006206  xor     edx, edx; Lsn
0x140006208  mov     rcx, [r14+8]; BcbVoid
0x14000620c  call    cs:__imp_CcSetDirtyPinnedData
0x140006213  nop     dword ptr [rax+rax+00h]
0x140006218  mov     sil, [rsp+88h+arg_10]
0x140006220  mov     rdx, r14
0x140006223  mov     rcx, r13
0x140006226  call    UdfUnpinView
0x14000622b  mov     rax, [r13+10h]
0x14000622f  test    dword ptr [rax+30h], 200h
0x140006236  jz      short loc_1400062A9
0x140006238  test    sil, sil
0x14000623b  jz      short loc_1400062A9
0x14000623d  cmp     byte ptr [r14+20h], 0
0x140006242  jnz     short loc_1400062A9
0x140006244  mov     qword ptr [rsp+88h+FileOffset], 0
0x140006250  xorps   xmm0, xmm0
0x140006253  movups  xmmword ptr [rsp+88h+IoStatus], xmm0
0x140006258  mov     rcx, rax
0x14000625b  mov     al, [r14+21h]
0x14000625f  neg     al
0x140006261  sbb     rdx, rdx
0x140006264  and     edx, 30h
0x140006267  mov     r8, [rdx+rcx+110h]
0x14000626f  mov     eax, [r14+1Ch]
0x140006273  mov     ecx, [rcx+48h]
0x140006276  shl     rax, cl
0x140006279  mov     qword ptr [rsp+88h+FileOffset], rax
0x140006281  mov     rcx, [r8+1A8h]
0x140006288  add     rcx, 8; SectionObjectPointer
0x14000628c  lea     r9, [rsp+88h+IoStatus]; IoStatus
0x140006291  mov     r8d, [r14+18h]; Length
0x140006295  lea     rdx, [rsp+88h+FileOffset]; FileOffset
0x14000629d  call    cs:__imp_CcFlushCache
0x1400062a4  nop     dword ptr [rax+rax+00h]
0x1400062a9  add     rsp, 50h
0x1400062ad  pop     r15
0x1400062af  pop     r14
0x1400062b1  pop     r13
0x1400062b3  pop     r12
0x1400062b5  pop     rdi
0x1400062b6  pop     rsi
0x1400062b7  pop     rbx
0x1400062b8  retn
0x14001cd12  push    rbp
0x14001cd14  sub     rsp, 30h
0x14001cd18  mov     rbp, rdx
0x14001cd1b  mov     rdx, [rbp+0A8h]
0x14001cd22  mov     rax, [rdx+88h]
0x14001cd29  mov     ecx, [rax+48h]
0x14001cd2c  dec     ecx
0x14001cd2e  mov     [rax+48h], ecx
0x14001cd31  mov     rax, [rdx+88h]
0x14001cd38  cmp     dword ptr [rax+48h], 0
0x14001cd3c  jnz     short loc_14001CD65
0x14001cd3e  mov     qword ptr [rax+40h], 0
0x14001cd46  mov     rax, [rdx+88h]
0x14001cd4d  mov     rcx, [rax+50h]
0x14001cd51  add     rcx, 0D8h; FastMutex
0x14001cd58  call    cs:__imp_ExReleaseFastMutex
0x14001cd5f  nop     dword ptr [rax+rax+00h]
0x14001cd64  nop
0x14001cd65  add     rsp, 30h
0x14001cd69  pop     rbp
0x14001cd6a  retn
0x14001cd6c  push    rbp
0x14001cd6e  sub     rsp, 30h
0x14001cd72  mov     rbp, rdx
0x14001cd75  mov     rdx, [rbp+98h]
0x14001cd7c  mov     rcx, [rbp+90h]
0x14001cd83  call    UdfUnpinView
0x14001cd88  nop
0x14001cd89  add     rsp, 30h
0x14001cd8d  pop     rbp
0x14001cd8e  retn
```
