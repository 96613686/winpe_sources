# SrvNetGetQueueStatistics

- ea: `0x14000d2a0`
- end: `0x14000d54c`
- name: `SrvNetGetQueueStatistics`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140050940`

## callees

- `0x14000d2a0`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d38f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d38f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d308`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d308`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000d2d9`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000d2d9`
- `ntoskrnl!KeReadStateQueue` at `0x14002c2fa`
- `ntoskrnl!KeReadStateQueue` at `0x14002c426`
- `ntoskrnl!KeReadStateQueue` at `0x14002c2fa`
- `ntoskrnl!KeReadStateQueue` at `0x14002c426`

## pseudocode

```c
__int64 __fastcall SrvNetGetQueueStatistics(_DWORD *a1, unsigned int a2, int *a3)
{
  unsigned __int64 v3; // rdi
  ULONG TimeIncrement; // eax
  KIRQL v7; // al
  __int64 v8; // rdx
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r14
  unsigned int v11; // r12d
  unsigned int v12; // r13d
  int v13; // r12d
  _OWORD *v15; // rbx
  unsigned __int64 v16; // rdi
  int v17; // eax
  int v18; // esi
  __int64 v19; // r15
  int v20; // edx
  __int64 v21; // r8
  __int64 v22; // rcx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int64 v29; // rdi
  unsigned int v30; // r12d
  __int64 v31; // rsi
  _OWORD *i; // rbx
  __int64 v33; // r15
  struct _KQUEUE *v34; // rcx
  _DWORD *v35; // rax
  int v36; // ecx
  int *v37; // rax
  int v38; // ecx
  int *v39; // rax
  int v40; // ecx
  int *v41; // rax
  int v42; // ecx
  int *v43; // rax
  int v44; // ecx
  __int64 *v45; // rax
  __int64 v46; // rcx
  __int64 *v47; // rax
  __int64 v48; // rcx
  __int64 *v49; // rax
  __int64 v50; // rcx
  __int64 *v51; // rax
  __int64 v52; // rcx
  __int64 *v53; // rax
  __int64 v54; // rcx
  _QWORD *v55; // rax
  __int64 v56; // rcx
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  int v64; // r10d
  int *v65; // rax
  int v66; // ecx
  _QWORD *v67; // rax
  int v68; // r9d
  __int64 v69; // rcx
  __int64 v70; // r9
  _QWORD *v71; // rax
  __int64 v72; // r9
  _QWORD *v73; // rax
  __int64 v74; // r9
  _QWORD *v75; // rax
  __int64 v76; // r9
  _QWORD *v77; // rax
  __int64 v78; // r9
  _QWORD *v79; // rax
  _DWORD *v80; // rax
  unsigned int *v81; // rax
  unsigned int v82; // edx
  int v83; // ecx
  int *v84; // rax
  int v85; // ecx
  __int64 *v86; // rax
  __int128 v87; // xmm1
  __int64 v88; // rcx
  __int64 *v89; // rax
  __int64 v90; // rcx
  __int64 *v91; // rax
  __int64 v92; // rcx
  __int64 *v93; // rax
  __int64 v94; // rcx
  __int64 *v95; // rax
  __int64 v96; // rcx
  __int64 *v97; // rax
  __int64 v98; // rcx
  __int64 *v99; // rax
  __int64 v100; // rcx
  __int64 *v101; // rax
  __int64 v102; // rcx
  __int64 *v103; // rax
  __int64 v104; // rcx
  _QWORD *v105; // rax
  __int64 v106; // rcx
  __int64 v107; // rax
  __int128 v108; // xmm0
  __int128 v109; // xmm1
  __int128 v110; // xmm0
  __int128 v111; // xmm1
  __int128 v112; // xmm0
  __int128 v113; // xmm1
  int v114; // [rsp+20h] [rbp-99h]
  int v115; // [rsp+24h] [rbp-95h]
  signed int v116; // [rsp+28h] [rbp-91h]
  _OWORD v117[8]; // [rsp+30h] [rbp-89h] BYREF
  __int64 v118; // [rsp+B0h] [rbp-9h]
  __int64 v119; // [rsp+B8h] [rbp-1h]
  __int64 v120; // [rsp+C0h] [rbp+7h]
  __int64 v121; // [rsp+C8h] [rbp+Fh]
  __int64 v122; // [rsp+D0h] [rbp+17h]
  __int64 v123; // [rsp+D8h] [rbp+1Fh]
  KIRQL NewIrql; // [rsp+120h] [rbp+67h]
  int v126; // [rsp+138h] [rbp+7Fh]

  v3 = a2;
  memset((char *)v117 + 4, 0, 0x7Cu);
  TimeIncrement = KeQueryTimeIncrement();
  *a3 = 0;
  v116 = TimeIncrement;
  if ( a1 )
  {
    if ( (unsigned int)v3 < 8 )
    {
      return (unsigned int)-1073741789;
    }
    else
    {
      v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      v8 = pSrvNonBlockingStatisticsQueues;
      NewIrql = v7;
      v9 = 0x8E38E38E38E38E39uLL * ((eSrvNonBlockingStatisticsQueues - pSrvNonBlockingStatisticsQueues) >> 4);
      v10 = 0x8E38E38E38E38E39uLL * ((eSrv2StatisticsQueues - Srv2StatisticsQueues) >> 4);
      *a1 = v9;
      v11 = v10 + v9 + 1;
      a1[1] = v10;
      if ( v3 >= ((unsigned __int64)v11 << 7) + 8 )
      {
        v12 = 0;
        v15 = a1 + 2;
        if ( v8 && (_DWORD)v9 )
        {
          v30 = 0;
          do
          {
            v33 = pSrvNonBlockingStatisticsQueues;
            v34 = *(struct _KQUEUE **)(pSrvNonBlockingStatisticsQueues + 144LL * v30);
            if ( v34 )
            {
              LODWORD(v117[0]) = KeReadStateQueue(v34);
              v35 = *(_DWORD **)(v33 + 144LL * v30 + 16);
              DWORD2(v117[0]) = **(_DWORD **)(v33 + 144LL * v30 + 8);
              v36 = DWORD2(v117[0]) - *v35;
              v37 = *(int **)(v33 + 144LL * v30 + 24);
              DWORD1(v117[0]) = v36;
              v38 = *v37;
              v39 = *(int **)(v33 + 144LL * v30 + 32);
              HIDWORD(v117[0]) = v38;
              v40 = *v39;
              v41 = *(int **)(v33 + 144LL * v30 + 40);
              LODWORD(v117[1]) = v40;
              v42 = *v41;
              v43 = *(int **)(v33 + 144LL * v30 + 48);
              DWORD1(v117[1]) = v42;
              v44 = *v43;
              v45 = *(__int64 **)(v33 + 144LL * v30 + 56);
              DWORD2(v117[1]) = v44;
              v46 = *v45;
              v47 = *(__int64 **)(v33 + 144LL * v30 + 64);
              *(_QWORD *)&v117[2] = v46;
              v48 = *v47;
              v49 = *(__int64 **)(v33 + 144LL * v30 + 72);
              *((_QWORD *)&v117[2] + 1) = v48;
              v50 = *v49;
              v51 = *(__int64 **)(v33 + 144LL * v30 + 88);
              *(_QWORD *)&v117[3] = v50;
              v52 = *v51;
              v53 = *(__int64 **)(v33 + 144LL * v30 + 104);
              *((_QWORD *)&v117[3] + 1) = v52;
              v54 = *v53;
              v55 = *(_QWORD **)(v33 + 144LL * v30 + 120);
              *(_QWORD *)&v117[4] = v54;
              *((_QWORD *)&v117[4] + 1) = *v55;
              v56 = *(_QWORD *)(v33 + 144LL * v30 + 136);
              HIDWORD(v117[7]) = *(_DWORD *)(v56 + 12);
              DWORD2(v117[7]) = 16 * *(_DWORD *)(v56 + 8);
              *(_QWORD *)&v117[7] = *(_QWORD *)v56 * v116;
            }
            else
            {
              memset(v117, 0, sizeof(v117));
            }
            v57 = v117[1];
            ++v30;
            *v15 = v117[0];
            v58 = v117[2];
            v15[1] = v57;
            v59 = v117[3];
            v15[2] = v58;
            v60 = v117[4];
            v15[3] = v59;
            v61 = v117[5];
            v15[4] = v60;
            v62 = v117[6];
            v15[5] = v61;
            v63 = v117[7];
            v15[6] = v62;
            v15[7] = v63;
            v15 += 8;
          }
          while ( v30 < (unsigned int)v9 );
          v11 = v10 + v9 + 1;
          v12 = 0;
        }
        memset(v117, 0, sizeof(v117));
        v16 = pSrvBlockingStatisticsQueues;
        v17 = 0;
        if ( pSrvBlockingStatisticsQueues )
        {
          v126 = 0;
          v18 = 0;
          v115 = 0;
          v19 = 0;
          v119 = 0;
          v20 = 0;
          v121 = 0;
          v123 = 0;
          v21 = 0;
          v114 = 0;
          v118 = 0;
          v120 = 0;
          v122 = 0;
          do
          {
            v17 = v20;
            v22 = v21;
            if ( v16 >= eSrvBlockingStatisticsQueues )
              break;
            if ( *(_QWORD *)v16 )
            {
              v64 = KeReadStateQueue(*(PRKQUEUE *)v16) + v126;
              v65 = *(int **)(v16 + 8);
              v126 = v64;
              LODWORD(v117[0]) = v64;
              v66 = *v65;
              v67 = *(_QWORD **)(v16 + 56);
              v114 = v66 + v114 - **(_DWORD **)(v16 + 16);
              DWORD1(v117[0]) = v114;
              v68 = v66 + v115;
              v69 = *(_QWORD *)(v16 + 136);
              v115 = v68;
              DWORD2(v117[0]) = v68;
              v70 = *v67 + v118;
              v71 = *(_QWORD **)(v16 + 64);
              v18 += *(_DWORD *)(v69 + 8);
              v118 = v70;
              *(_QWORD *)&v117[2] = v70;
              v72 = *v71 + v119;
              v73 = *(_QWORD **)(v16 + 72);
              v119 = v72;
              *((_QWORD *)&v117[2] + 1) = v72;
              v74 = *v73 + v120;
              v75 = *(_QWORD **)(v16 + 88);
              v120 = v74;
              *(_QWORD *)&v117[3] = v74;
              v76 = *v75 + v121;
              v77 = *(_QWORD **)(v16 + 104);
              v121 = v76;
              *((_QWORD *)&v117[3] + 1) = v76;
              v78 = *v77 + v122;
              v79 = *(_QWORD **)(v16 + 120);
              v122 = v78;
              *(_QWORD *)&v117[4] = v78;
              v19 += *(_QWORD *)v69;
              v123 += *v79;
              *((_QWORD *)&v117[4] + 1) = v123;
            }
            else
            {
              memset(v117, 0, sizeof(v117));
              v18 = 0;
              v126 = 0;
              v114 = 0;
              v19 = 0;
              v115 = 0;
              v118 = 0;
              v119 = 0;
              v120 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
            }
            v20 = v18;
            v17 = v18;
            v21 = v19;
            v22 = v19;
            v16 += 144LL;
          }
          while ( v16 );
        }
        else
        {
          v22 = 0;
        }
        v23 = v117[1];
        *v15 = v117[0];
        v24 = v117[2];
        v15[1] = v23;
        DWORD2(v117[7]) = 16 * v17;
        v25 = v117[3];
        v15[2] = v24;
        v26 = v117[4];
        v15[3] = v25;
        v27 = v117[5];
        v15[4] = v26;
        v28 = v117[6];
        v15[5] = v27;
        v15[6] = v28;
        *(_QWORD *)&v117[7] = v116 * v22;
        v15[7] = v117[7];
        memset((char *)v117 + 4, 0, 0x7Cu);
        v29 = Srv2StatisticsQueues;
        if ( Srv2StatisticsQueues )
        {
          v31 = 0;
          for ( i = v15 + 8; (unsigned int)v31 < (unsigned int)v10; i += 8 )
          {
            v80 = *(_DWORD **)(v29 + 144 * v31);
            if ( v80 )
            {
              LODWORD(v117[0]) = *v80;
              v81 = *(unsigned int **)(v29 + 144 * v31 + 8);
              DWORD1(v117[1]) = 0;
              v82 = *v81;
              v83 = *v81 - **(_DWORD **)(v29 + 144 * v31 + 16);
              v84 = *(int **)(v29 + 144 * v31 + 48);
              *(_OWORD *)((char *)v117 + 4) = __PAIR64__(v82, v83);
              v85 = *v84;
              v86 = *(__int64 **)(v29 + 144 * v31 + 56);
              DWORD2(v117[1]) = v85;
              v87 = v117[1];
              v88 = *v86;
              v89 = *(__int64 **)(v29 + 144 * v31 + 64);
              *(_QWORD *)&v117[2] = v88;
              v90 = *v89;
              v91 = *(__int64 **)(v29 + 144 * v31 + 72);
              *((_QWORD *)&v117[2] + 1) = v90;
              v92 = *v91;
              v93 = *(__int64 **)(v29 + 144 * v31 + 88);
              *(_QWORD *)&v117[3] = v92;
              v94 = *v93;
              v95 = *(__int64 **)(v29 + 144 * v31 + 104);
              *((_QWORD *)&v117[3] + 1) = v94;
              v96 = *v95;
              v97 = *(__int64 **)(v29 + 144 * v31 + 120);
              *(_QWORD *)&v117[4] = v96;
              v98 = *v97;
              v99 = *(__int64 **)(v29 + 144 * v31 + 80);
              *((_QWORD *)&v117[4] + 1) = v98;
              v100 = *v99;
              v101 = *(__int64 **)(v29 + 144 * v31 + 96);
              *(_QWORD *)&v117[5] = v100;
              v102 = *v101;
              v103 = *(__int64 **)(v29 + 144 * v31 + 112);
              *((_QWORD *)&v117[5] + 1) = v102;
              v104 = *v103;
              v105 = *(_QWORD **)(v29 + 144 * v31 + 128);
              *(_QWORD *)&v117[6] = v104;
              *((_QWORD *)&v117[6] + 1) = *v105;
              v106 = *(_QWORD *)(v29 + 144 * v31 + 136);
              HIDWORD(v117[7]) = *(_DWORD *)(v106 + 12);
              DWORD2(v117[7]) = 16 * *(_DWORD *)(v106 + 8);
              v107 = *(_QWORD *)v106 * v116;
              *i = v117[0];
              v108 = v117[2];
              i[1] = v87;
              v109 = v117[3];
              i[2] = v108;
              *(_QWORD *)&v117[7] = v107;
              v110 = v117[4];
              i[3] = v109;
              v111 = v117[5];
              i[4] = v110;
              v112 = v117[6];
              i[5] = v111;
              v113 = v117[7];
              i[6] = v112;
              i[7] = v113;
            }
            else
            {
              memset(v117, 0, sizeof(v117));
            }
            v31 = (unsigned int)(v31 + 1);
          }
        }
        v13 = (v11 << 7) + 8;
      }
      else
      {
        v12 = -2147483643;
        v13 = 8;
      }
      *a3 = v13;
      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceContext, NewIrql);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v12;
}

```

## disassembly

```asm
0x14000d2a0  mov     [rsp-8+arg_8], rbx
0x14000d2a5  mov     [rsp-8+arg_10], r8
0x14000d2aa  push    rbp
0x14000d2ab  push    rsi
0x14000d2ac  push    rdi
0x14000d2ad  push    r12
0x14000d2af  push    r13
0x14000d2b1  push    r14
0x14000d2b3  push    r15
0x14000d2b5  lea     rbp, [rsp-27h]
0x14000d2ba  sub     rsp, 0E0h
0x14000d2c1  mov     edi, edx
0x14000d2c3  mov     rsi, r8
0x14000d2c6  xor     edx, edx; Val
0x14000d2c8  mov     rbx, rcx
0x14000d2cb  lea     rcx, [rsp+110h+var_E0+4]; void *
0x14000d2d0  lea     r8d, [rdx+7Ch]; Size
0x14000d2d4  call    memset
0x14000d2d9  call    cs:__imp_KeQueryTimeIncrement
0x14000d2e0  nop     dword ptr [rax+rax+00h]
0x14000d2e5  mov     dword ptr [rsi], 0
0x14000d2eb  mov     [rsp+110h+var_E8], eax
0x14000d2ef  test    rbx, rbx
0x14000d2f2  jz      loc_14000D50D
0x14000d2f8  cmp     edi, 8
0x14000d2fb  jb      loc_14000D518
0x14000d301  lea     rcx, WPP_MAIN_CB.Queue+20h; SpinLock
0x14000d308  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d30f  nop     dword ptr [rax+rax+00h]
0x14000d314  mov     rdx, cs:pSrvNonBlockingStatisticsQueues
0x14000d31b  mov     rsi, cs:eSrvNonBlockingStatisticsQueues
0x14000d322  mov     r14, cs:eSrv2StatisticsQueues
0x14000d329  sub     rsi, rdx
0x14000d32c  sub     r14, cs:Srv2StatisticsQueues
0x14000d333  sar     rsi, 4
0x14000d337  sar     r14, 4
0x14000d33b  mov     [rbp+57h+NewIrql], al
0x14000d33e  mov     rax, 8E38E38E38E38E39h
0x14000d348  imul    rsi, rax
0x14000d34c  imul    r14, rax
0x14000d350  lea     r12d, [rsi+1]
0x14000d354  mov     [rbx], esi
0x14000d356  add     r12d, r14d
0x14000d359  mov     [rbx+4], r14d
0x14000d35d  mov     ecx, r12d
0x14000d360  shl     rcx, 7
0x14000d364  add     rcx, 8
0x14000d368  mov     [rsp+110h+var_EC], r12d
0x14000d36d  cmp     rdi, rcx
0x14000d370  jnb     short loc_14000D3BA
0x14000d372  mov     r13d, 80000005h
0x14000d378  mov     r12d, 8
0x14000d37e  mov     rdx, [rbp+57h+arg_10]
0x14000d382  lea     rcx, WPP_MAIN_CB.Queue+20h; SpinLock
0x14000d389  mov     [rdx], r12d
0x14000d38c  mov     dl, [rbp+57h+NewIrql]; NewIrql
0x14000d38f  call    cs:__imp_KeReleaseSpinLock
0x14000d396  nop     dword ptr [rax+rax+00h]
0x14000d39b  mov     rbx, [rsp+110h+arg_8]
0x14000d3a3  mov     eax, r13d
0x14000d3a6  add     rsp, 0E0h
0x14000d3ad  pop     r15
0x14000d3af  pop     r14
0x14000d3b1  pop     r13
0x14000d3b3  pop     r12
0x14000d3b5  pop     rdi
0x14000d3b6  pop     rsi
0x14000d3b7  pop     rbp
0x14000d3b8  retn
0x14000d3ba  xor     r13d, r13d
0x14000d3bd  add     rbx, 8
0x14000d3c1  mov     [rsp+110h+var_F0], r13d
0x14000d3c6  mov     r8d, 80h; Size
0x14000d3cc  test    rdx, rdx
0x14000d3cf  jnz     loc_14000D523
0x14000d3d5  xor     edx, edx; Val
0x14000d3d7  lea     rcx, [rsp+110h+var_E0]; void *
0x14000d3dc  call    memset
0x14000d3e1  mov     rdi, cs:pSrvBlockingStatisticsQueues
0x14000d3e8  xor     eax, eax
0x14000d3ea  test    rdi, rdi
0x14000d3ed  jz      loc_14000D509
0x14000d3f3  xor     ecx, ecx
0x14000d3f5  mov     [rbp+57h+arg_18], eax
0x14000d3f8  xor     esi, esi
0x14000d3fa  mov     [rsp+110h+var_EC], ecx
0x14000d3fe  xor     r15d, r15d
0x14000d401  mov     [rbp+57h+var_58], rcx
0x14000d405  xor     edx, edx
0x14000d407  mov     [rbp+57h+var_48], rcx
0x14000d40b  mov     [rbp+57h+var_38], rcx
0x14000d40f  xor     r8d, r8d
0x14000d412  mov     [rsp+110h+var_F0], eax
0x14000d416  mov     [rbp+57h+var_60], rax
0x14000d41a  mov     [rbp+57h+var_50], rax
0x14000d41e  mov     [rbp+57h+var_40], rax
0x14000d422  cmp     rdi, cs:eSrvBlockingStatisticsQueues
0x14000d429  mov     eax, edx
0x14000d42b  mov     rcx, r8
0x14000d42e  jnb     short loc_14000D48D
0x14000d430  mov     rcx, [rdi]; Queue
0x14000d433  test    rcx, rcx
0x14000d436  jnz     loc_14002C426
0x14000d43c  xor     edx, edx; Val
0x14000d43e  lea     rcx, [rsp+110h+var_E0]; void *
0x14000d443  mov     r8d, 80h; Size
0x14000d449  call    memset
0x14000d44e  xor     eax, eax
0x14000d450  xor     ecx, ecx
0x14000d452  xor     esi, esi
0x14000d454  mov     [rbp+57h+arg_18], eax
0x14000d457  mov     [rsp+110h+var_F0], eax
0x14000d45b  xor     r15d, r15d
0x14000d45e  mov     [rsp+110h+var_EC], ecx
0x14000d462  mov     [rbp+57h+var_60], rax
0x14000d466  mov     [rbp+57h+var_58], rcx
0x14000d46a  mov     [rbp+57h+var_50], rax
0x14000d46e  mov     [rbp+57h+var_48], rcx
0x14000d472  mov     [rbp+57h+var_40], rax
0x14000d476  mov     [rbp+57h+var_38], rcx
0x14000d47a  mov     edx, esi
0x14000d47c  mov     eax, esi
0x14000d47e  mov     r8, r15
0x14000d481  mov     rcx, r15
0x14000d484  add     rdi, 90h
0x14000d48b  jnz     short loc_14000D422
0x14000d48d  movaps  xmm0, [rsp+110h+var_E0]
0x14000d492  xor     edx, edx; Val
0x14000d494  movaps  xmm1, [rbp+57h+var_D0]
0x14000d498  movsxd  r15, [rsp+110h+var_E8]
0x14000d49d  movups  xmmword ptr [rbx], xmm0
0x14000d4a0  lea     r8d, [rdx+7Ch]; Size
0x14000d4a4  shl     eax, 4
0x14000d4a7  movaps  xmm0, [rbp+57h+var_C0]
0x14000d4ab  movups  xmmword ptr [rbx+10h], xmm1
0x14000d4af  mov     dword ptr [rbp+57h+var_70+8], eax
0x14000d4b2  movaps  xmm1, [rbp+57h+var_B0]
0x14000d4b6  movups  xmmword ptr [rbx+20h], xmm0
0x14000d4ba  movaps  xmm0, [rbp+57h+var_A0]
0x14000d4be  movups  xmmword ptr [rbx+30h], xmm1
0x14000d4c2  movaps  xmm1, [rbp+57h+var_90]
0x14000d4c6  movups  xmmword ptr [rbx+40h], xmm0
0x14000d4ca  movaps  xmm0, [rbp+57h+var_80]
0x14000d4ce  movups  xmmword ptr [rbx+50h], xmm1
0x14000d4d2  imul    rcx, r15
0x14000d4d6  movups  xmmword ptr [rbx+60h], xmm0
0x14000d4da  mov     qword ptr [rbp+57h+var_70], rcx
0x14000d4de  lea     rcx, [rsp+110h+var_E0+4]; void *
0x14000d4e3  movaps  xmm1, [rbp+57h+var_70]
0x14000d4e7  movups  xmmword ptr [rbx+70h], xmm1
0x14000d4eb  call    memset
0x14000d4f0  mov     rdi, cs:Srv2StatisticsQueues
0x14000d4f7  test    rdi, rdi
0x14000d4fa  jnz     short loc_14000D538
0x14000d4fc  shl     r12d, 7
0x14000d500  add     r12d, 8
0x14000d504  jmp     loc_14000D37E
0x14000d509  xor     ecx, ecx
0x14000d50b  jmp     short loc_14000D48D
0x14000d50d  mov     r13d, 0C000000Dh
0x14000d513  jmp     loc_14000D39B
0x14000d518  mov     r13d, 0C0000023h
0x14000d51e  jmp     loc_14000D39B
0x14000d523  test    esi, esi
0x14000d525  jz      loc_14000D3D5
0x14000d52b  mov     r12d, r13d
0x14000d52e  movsxd  r13, [rsp+110h+var_E8]
0x14000d533  jmp     loc_14002C2DC
0x14000d538  mov     ecx, 80h
0x14000d53d  xor     esi, esi
0x14000d53f  add     rbx, rcx
0x14000d542  test    r14d, r14d
0x14000d545  jz      short loc_14000D4FC
0x14000d547  jmp     loc_14002C4F7
0x14002c2dc  mov     r15, cs:pSrvNonBlockingStatisticsQueues
0x14002c2e3  mov     eax, r12d
0x14002c2e6  lea     rdi, [rax+rax*8]
0x14002c2ea  add     rdi, rdi
0x14002c2ed  mov     rcx, [r15+rdi*8]; Queue
0x14002c2f1  test    rcx, rcx
0x14002c2f4  jz      loc_14002C3B6
0x14002c2fa  call    cs:__imp_KeReadStateQueue
0x14002c301  nop     dword ptr [rax+rax+00h]
0x14002c306  mov     dword ptr [rsp+110h+var_E0], eax
0x14002c30a  mov     rax, [r15+rdi*8+8]
0x14002c30f  mov     edx, [rax]
0x14002c311  mov     ecx, edx
0x14002c313  mov     rax, [r15+rdi*8+10h]
0x14002c318  mov     dword ptr [rsp+110h+var_E0+8], edx
0x14002c31c  sub     ecx, [rax]
0x14002c31e  mov     rax, [r15+rdi*8+18h]
0x14002c323  mov     dword ptr [rsp+110h+var_E0+4], ecx
0x14002c327  mov     ecx, [rax]
0x14002c329  mov     rax, [r15+rdi*8+20h]
0x14002c32e  mov     dword ptr [rbp+57h+var_E0+0Ch], ecx
0x14002c331  mov     ecx, [rax]
0x14002c333  mov     rax, [r15+rdi*8+28h]
0x14002c338  mov     dword ptr [rbp+57h+var_D0], ecx
0x14002c33b  mov     ecx, [rax]
0x14002c33d  mov     rax, [r15+rdi*8+30h]
0x14002c342  mov     dword ptr [rbp+57h+var_D0+4], ecx
0x14002c345  mov     ecx, [rax]
0x14002c347  mov     rax, [r15+rdi*8+38h]
0x14002c34c  mov     dword ptr [rbp+57h+var_D0+8], ecx
0x14002c34f  mov     rcx, [rax]
0x14002c352  mov     rax, [r15+rdi*8+40h]
0x14002c357  mov     qword ptr [rbp+57h+var_C0], rcx
0x14002c35b  mov     rcx, [rax]
0x14002c35e  mov     rax, [r15+rdi*8+48h]
0x14002c363  mov     qword ptr [rbp+57h+var_C0+8], rcx
0x14002c367  mov     rcx, [rax]
0x14002c36a  mov     rax, [r15+rdi*8+58h]
0x14002c36f  mov     qword ptr [rbp+57h+var_B0], rcx
0x14002c373  mov     rcx, [rax]
0x14002c376  mov     rax, [r15+rdi*8+68h]
0x14002c37b  mov     qword ptr [rbp+57h+var_B0+8], rcx
0x14002c37f  mov     rcx, [rax]
0x14002c382  mov     rax, [r15+rdi*8+78h]
0x14002c387  mov     qword ptr [rbp+57h+var_A0], rcx
0x14002c38b  mov     rcx, [rax]
0x14002c38e  mov     qword ptr [rbp+57h+var_A0+8], rcx
0x14002c392  mov     rcx, [r15+rdi*8+88h]
0x14002c39a  mov     eax, [rcx+0Ch]
0x14002c39d  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x14002c3a0  mov     eax, [rcx+8]
0x14002c3a3  shl     eax, 4
0x14002c3a6  mov     dword ptr [rbp+57h+var_70+8], eax
0x14002c3a9  mov     rax, r13
0x14002c3ac  imul    rax, [rcx]
0x14002c3b0  mov     qword ptr [rbp+57h+var_70], rax
0x14002c3b4  jmp     short loc_14002C3C2
0x14002c3b6  xor     edx, edx; Val
0x14002c3b8  lea     rcx, [rsp+110h+var_E0]; void *
0x14002c3bd  call    memset
0x14002c3c2  movaps  xmm0, [rsp+110h+var_E0]
0x14002c3c7  mov     r8d, 80h
0x14002c3cd  movaps  xmm1, [rbp+57h+var_D0]
0x14002c3d1  inc     r12d
0x14002c3d4  movups  xmmword ptr [rbx], xmm0
0x14002c3d7  movaps  xmm0, [rbp+57h+var_C0]
0x14002c3db  movups  xmmword ptr [rbx+10h], xmm1
0x14002c3df  movaps  xmm1, [rbp+57h+var_B0]
0x14002c3e3  movups  xmmword ptr [rbx+20h], xmm0
0x14002c3e7  movaps  xmm0, [rbp+57h+var_A0]
0x14002c3eb  movups  xmmword ptr [rbx+30h], xmm1
0x14002c3ef  movaps  xmm1, [rbp+57h+var_90]
0x14002c3f3  movups  xmmword ptr [rbx+40h], xmm0
0x14002c3f7  movaps  xmm0, [rbp+57h+var_80]
0x14002c3fb  movups  xmmword ptr [rbx+50h], xmm1
0x14002c3ff  movaps  xmm1, [rbp+57h+var_70]
0x14002c403  movups  xmmword ptr [rbx+60h], xmm0
0x14002c407  movups  xmmword ptr [rbx+70h], xmm1
0x14002c40b  add     rbx, r8
0x14002c40e  cmp     r12d, esi
0x14002c411  jb      loc_14002C2DC
0x14002c417  mov     r12d, [rsp+110h+var_EC]
0x14002c41c  mov     r13d, [rsp+110h+var_F0]
0x14002c421  jmp     loc_14000D3D5
0x14002c426  call    cs:__imp_KeReadStateQueue
0x14002c42d  nop     dword ptr [rax+rax+00h]
0x14002c432  mov     r9d, [rsp+110h+var_F0]
0x14002c437  mov     r10d, [rbp+57h+arg_18]
0x14002c43b  add     r10d, eax
0x14002c43e  mov     rax, [rdi+8]
0x14002c442  mov     [rbp+57h+arg_18], r10d
0x14002c446  mov     dword ptr [rsp+110h+var_E0], r10d
0x14002c44b  mov     ecx, [rax]
0x14002c44d  mov     rax, [rdi+10h]
0x14002c451  sub     r9d, [rax]
0x14002c454  mov     rax, [rdi+38h]
0x14002c458  add     r9d, ecx
0x14002c45b  mov     [rsp+110h+var_F0], r9d
0x14002c460  mov     dword ptr [rsp+110h+var_E0+4], r9d
0x14002c465  mov     r9d, [rsp+110h+var_EC]
0x14002c46a  add     r9d, ecx
0x14002c46d  mov     rcx, [rdi+88h]
0x14002c474  mov     [rsp+110h+var_EC], r9d
0x14002c479  mov     dword ptr [rsp+110h+var_E0+8], r9d
0x14002c47e  mov     r9, [rbp+57h+var_60]
0x14002c482  add     r9, [rax]
0x14002c485  mov     rax, [rdi+40h]
0x14002c489  add     esi, [rcx+8]
0x14002c48c  mov     [rbp+57h+var_60], r9
0x14002c490  mov     qword ptr [rbp+57h+var_C0], r9
0x14002c494  mov     r9, [rbp+57h+var_58]
0x14002c498  add     r9, [rax]
0x14002c49b  mov     rax, [rdi+48h]
0x14002c49f  mov     [rbp+57h+var_58], r9
0x14002c4a3  mov     qword ptr [rbp+57h+var_C0+8], r9
0x14002c4a7  mov     r9, [rbp+57h+var_50]
0x14002c4ab  add     r9, [rax]
0x14002c4ae  mov     rax, [rdi+58h]
0x14002c4b2  mov     [rbp+57h+var_50], r9
0x14002c4b6  mov     qword ptr [rbp+57h+var_B0], r9
0x14002c4ba  mov     r9, [rbp+57h+var_48]
0x14002c4be  add     r9, [rax]
0x14002c4c1  mov     rax, [rdi+68h]
0x14002c4c5  mov     [rbp+57h+var_48], r9
0x14002c4c9  mov     qword ptr [rbp+57h+var_B0+8], r9
0x14002c4cd  mov     r9, [rbp+57h+var_40]
  ... truncated ...
```
