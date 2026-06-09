# VhdmpiVhd2SubIoRoutineEx(_VHD2_FILE *,_VHD2_READ_WRITE *,_VHD2_RANGE_TYPE,ulong,ulong,unsigned __int64,uchar,AE_TODO *)

- ea: `0x140015210`
- end: `0x1400156f9`
- name: `?VhdmpiVhd2SubIoRoutineEx@@YAJPEAU_VHD2_FILE@@PEAU_VHD2_READ_WRITE@@W4_VHD2_RANGE_TYPE@@KK_KEPEAUAE_TODO@@@Z`
- size: `1257`
- prototype: `int __high(struct _VHD2_FILE *, struct _VHD2_READ_WRITE *, enum _VHD2_RANGE_TYPE, unsigned int, unsigned int, unsigned __int64, unsigned __int8, struct AE_TODO *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14000f818`
- `0x14000f854`
- `0x140010b60`
- `0x140011630`
- `0x140011810`
- `0x140014790`
- `0x140015210`
- `0x140016e6c`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!IoSizeOfIrpEx` at `0x1400154d0`
- `ntoskrnl!IoSizeOfIrpEx` at `0x1400154d0`
- `ntoskrnl!IoInitializeIrpEx` at `0x140015524`
- `ntoskrnl!IoInitializeIrpEx` at `0x140015524`
- `ntoskrnl!ExAllocatePool2` at `0x1400154f2`
- `ntoskrnl!ExAllocatePool2` at `0x1400154f2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015346`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015346`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015385`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001563f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015385`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001563f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400153ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015679`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400153ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015679`

## pseudocode

```c
__int64 __fastcall VhdmpiVhd2SubIoRoutineEx(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        char a7,
        __int64 a8)
{
  __int64 v8; // rbp
  __int64 v9; // r14
  __int64 *v10; // rsi
  __int64 v11; // rdi
  int v12; // r12d
  __int64 v13; // rbx
  unsigned int v14; // r12d
  __int64 v15; // rcx
  unsigned int v16; // edi
  _DWORD *v17; // rcx
  __int64 v18; // rbx
  struct _LIST_ENTRY *v19; // r14
  struct VHD_SRB_PART *v20; // rax
  struct VHD_SRB_PART *v21; // rbp
  KIRQL v22; // al
  struct _LIST_ENTRY *v23; // rdx
  __int64 v25; // rsi
  __int64 v26; // r15
  __int64 Pool2; // rax
  __int64 v28; // rbx
  unsigned int v29; // ecx
  __int64 v30; // rbx
  unsigned int v31; // r12d
  int v32; // r15d
  __int64 v33; // rax
  __int64 v34; // r14
  const char *v35; // rax
  KSPIN_LOCK *v36; // rdi
  KIRQL v37; // al
  __int64 v38; // rcx
  _QWORD *v39; // rbp
  struct _LIST_ENTRY v41; // [rsp+50h] [rbp-38h] BYREF

  v8 = a2 - 72;
  v9 = a1 - 2240;
  v10 = (__int64 *)(a2 - 184);
  *(_BYTE *)(a2 - 72 + 40) = *(_BYTE *)(a2 - 72 + 40) & 0xFD | (a7 != 0 ? 2 : 0);
  if ( a3 )
  {
    if ( a3 != 7 )
    {
      switch ( a3 )
      {
        case 1:
          return (unsigned int)VhdmpiSrbPartReportPresent(
                                 a2 - 184,
                                 a4,
                                 a5,
                                 v9,
                                 a6,
                                 VhdmpiVhd2SubIoCompletionRoutine,
                                 0,
                                 a7);
        case 2:
        case 3:
        case 4:
          return (unsigned int)VhdmpiSrbPartReportZero((struct VHD_SRB_PART *)(a2 - 184), a4, a5);
        case 5:
          v11 = *v10;
          v12 = *((_DWORD *)v10 + 22);
          v13 = v10[5];
          v41 = 0;
          v14 = a4 + v12 - *(_DWORD *)(v11 + 32);
          if ( v13 == *(_QWORD *)(v11 + 136) )
          {
            v15 = *(_QWORD *)(v11 + 128);
            v16 = 0;
            if ( v15 )
            {
              v17 = (_DWORD *)(v15 + 8 * ((unsigned __int64)v14 >> 9));
              *v17 = 4;
              v17[1] = a5;
            }
            else
            {
              MEMORY[0] = 4;
              MEMORY[4] = a5;
            }
          }
          else
          {
            v18 = *(_QWORD *)(v13 + 1144);
            if ( v18 )
            {
              if ( a4 || a5 != *((_DWORD *)v10 + 24) )
              {
                v19 = *(struct _LIST_ENTRY **)(a8 + 32);
                v20 = (struct VHD_SRB_PART *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v18 + 1536));
                v21 = v20;
                if ( v20 )
                {
                  VhdmpiSrbPartInitialize(
                    v20,
                    (struct _VHD_BACKING_STORE_HEADER *)v18,
                    (struct _VHD_SRB_EXTENSION *)v11,
                    v14,
                    a5);
                  *((_QWORD *)v21 + 6) = v18;
                  KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 168));
                  VhdmpiInsertTailList((struct _LIST_ENTRY *)(v11 + 176), (struct _LIST_ENTRY *)((char *)v21 + 8));
                  KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 168), v22);
                  if ( _InterlockedIncrement64((volatile signed __int64 *)(v11 + 40)) <= 1 )
                    __fastfail(0xEu);
                  v23 = (struct _LIST_ENTRY *)((char *)v21 + 24);
                  if ( v19 )
                  {
                    VhdmpiInsertTailList(v19, v23);
                  }
                  else
                  {
                    v41.Blink = &v41;
                    v41.Flink = &v41;
                    VhdmpiInsertTailList(&v41, v23);
                    VhdmpiProcessParseThreadContext(&v41, 0);
                  }
                  if ( (*(_DWORD *)(v11 + 64) & 0x100) != 0 )
                    *((_BYTE *)v10 + 109) = 1;
                  return 0;
                }
                else
                {
                  return (unsigned int)-1073741670;
                }
              }
              else
              {
                *((_BYTE *)v10 + 110) = 1;
                return 0;
              }
            }
            else
            {
              return (unsigned int)-1073741595;
            }
          }
          return v16;
        case 6:
          return (unsigned int)VhdmpiSrbPartCheckZero((struct VHD_SRB_PART *)(a2 - 184));
        default:
          __fastfail(0x25u);
      }
    }
    v25 = *(_QWORD *)(v8 + 32);
    v16 = 0;
    if ( v25 )
    {
      v29 = *(_DWORD *)(*(_QWORD *)(v25 + 16) + 4LL);
    }
    else
    {
      v26 = (unsigned __int16)IoSizeOfIrpEx(-1, *(unsigned __int8 *)(v9 + 616));
      Pool2 = ExAllocatePool2(64, v26 + 592, 1128548438);
      v25 = Pool2;
      if ( !Pool2 )
        return v16;
      v28 = Pool2 + 72;
      IoInitializeIrpEx(Pool2 + 72, -1, (unsigned __int16)v26, *(unsigned __int8 *)(v9 + 616));
      *(_QWORD *)(v28 + 144) = 0;
      *(_QWORD *)v25 = v9;
      *(_QWORD *)(v25 + 16) = v25 + v26 + 72;
      v29 = 0;
      *(_QWORD *)(v25 + 8) = v28;
      *(_DWORD *)(v25 + 24) = 32;
      *(_QWORD *)(v8 + 32) = v25;
    }
    v30 = *(_QWORD *)(v25 + 16);
    v31 = v29 + 1;
    v32 = *(_DWORD *)(v25 + 24);
    *(_QWORD *)(v25 + 48) = v8;
    v33 = 2LL * v29;
    *(_QWORD *)(v30 + 8 * v33 + 8) = a6;
    *(_QWORD *)(v30 + 8 * v33 + 16) = a5;
    ++*(_DWORD *)(v30 + 4);
    if ( (unsigned int)dword_140087708 > 5
      && (qword_140087718 & 0x2000) != 0
      && (qword_140087720 & 0x2000) == qword_140087720 )
    {
      v34 = v9 + 88;
      if ( v31 == v32 || (v35 = "No", (*(_BYTE *)(v8 + 40) & 2) != 0) )
        v35 = "Yes";
      TraceEvents(
        "VhdmpiVhd2HandleFileTrimSubIo",
        0x1154u,
        5u,
        0x2000u,
        "Adding file trim range: Offset: 0x%I64x, Length: 0x%I64x, Range Count: %lu, Issuing: %s, Filename: %wZ",
        a6,
        a5,
        *(_DWORD *)(v30 + 4),
        v35,
        v34);
    }
    if ( v31 == v32 || (*(_BYTE *)(v8 + 40) & 2) != 0 )
    {
      *(_QWORD *)(v8 + 32) = 0;
      v36 = (KSPIN_LOCK *)(v8 + 48);
      v37 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 48));
      v38 = *(_QWORD *)(v8 + 56);
      v39 = (_QWORD *)(v8 + 56);
      if ( *(_QWORD **)(v38 + 8) != v39 )
        __fastfail(3u);
      *(_QWORD *)(v25 + 56) = v38;
      *(_QWORD *)(v25 + 64) = v39;
      *(_QWORD *)(v38 + 8) = v25 + 56;
      *v39 = v25 + 56;
      KeReleaseSpinLock(v36, v37);
      TpSendFileTrim(
        (struct _TP_IRP_CONTEXT *)v25,
        (struct _FILE_LEVEL_TRIM *)v30,
        (void (*)(void *, int))VhdmpiVhd2FileTrimCompletion,
        (void *)v25);
      return 259;
    }
  }
  else
  {
    return (unsigned int)VhdmpiSrbPartReportPresent(a2 - 184, a4, a5, v9, a6, VhdmpiVhd2SubIoCompletionRoutine, 0, a7);
  }
  return v16;
}

```

## disassembly

```asm
0x140015210  mov     [rsp+arg_0], rbx
0x140015215  mov     [rsp+arg_8], rbp
0x14001521a  push    rsi
0x14001521b  push    rdi
0x14001521c  push    r12
0x14001521e  push    r14
0x140015220  push    r15
0x140015222  sub     rsp, 60h
0x140015226  lea     rbp, [rdx-48h]
0x14001522a  mov     [rsp+88h+arg_10], 0
0x140015232  movzx   edx, [rsp+88h+arg_30]
0x14001523a  lea     r14, [rcx-8C0h]
0x140015241  movzx   eax, dl
0x140015244  lea     rsi, [rbp-70h]
0x140015248  neg     al
0x14001524a  mov     r10d, r9d
0x14001524d  movzx   eax, byte ptr [rbp+28h]
0x140015251  sbb     cl, cl
0x140015253  and     al, 0FDh
0x140015255  and     cl, 2
0x140015258  or      cl, al
0x14001525a  mov     [rbp+28h], cl
0x14001525d  test    r8d, r8d
0x140015260  jz      loc_1400156A1; jumptable 0000000140015291 case 1
0x140015266  cmp     r8d, 7
0x14001526a  jz      loc_1400154B2
0x140015270  lea     eax, [r8-1]; switch 6 cases
0x140015274  cmp     eax, 5
0x140015277  ja      def_140015291; jumptable 0000000140015291 default case
0x14001527d  lea     r9, cs:140000000h
0x140015284  cdqe
0x140015286  mov     ecx, ds:(jpt_140015291 - 140000000h)[r9+rax*4]
0x14001528e  add     rcx, r9
0x140015291  jmp     rcx; switch jump
0x140015297  mov     rdi, [rsi]; jumptable 0000000140015291 case 5
0x14001529a  xorps   xmm0, xmm0
0x14001529d  mov     r12d, [rsi+58h]
0x1400152a1  mov     rbx, [rsi+28h]
0x1400152a5  movups  xmmword ptr [rsp+88h+var_38.Flink], xmm0
0x1400152aa  sub     r12d, [rdi+20h]
0x1400152ae  add     r12d, r10d
0x1400152b1  cmp     rbx, [rdi+88h]
0x1400152b8  jnz     short loc_1400152FF
0x1400152ba  mov     rcx, [rdi+80h]
0x1400152c1  xor     edi, edi
0x1400152c3  test    rcx, rcx
0x1400152c6  jnz     short loc_1400152DF
0x1400152c8  mov     eax, [rsp+88h+arg_20]
0x1400152cf  mov     ecx, edi
0x1400152d1  mov     dword ptr [rcx], 4
0x1400152d7  mov     [rcx+4], eax
0x1400152da  jmp     loc_1400156DD
0x1400152df  mov     eax, r12d
0x1400152e2  shr     rax, 9
0x1400152e6  lea     rcx, [rcx+rax*8]
0x1400152ea  mov     eax, [rsp+88h+arg_20]
0x1400152f1  mov     dword ptr [rcx], 4
0x1400152f7  mov     [rcx+4], eax
0x1400152fa  jmp     loc_1400156DD
0x1400152ff  mov     rbx, [rbx+478h]
0x140015306  test    rbx, rbx
0x140015309  jnz     short loc_140015315
0x14001530b  mov     edi, 0C00000E5h
0x140015310  jmp     loc_1400156DD
0x140015315  mov     r15d, [rsp+88h+arg_20]
0x14001531d  test    r10d, r10d
0x140015320  jnz     short loc_140015333
0x140015322  cmp     r15d, [rsi+60h]
0x140015326  jnz     short loc_140015333
0x140015328  mov     byte ptr [rsi+6Eh], 1
0x14001532c  xor     edi, edi
0x14001532e  jmp     loc_1400156DD
0x140015333  mov     rax, [rsp+88h+arg_38]
0x14001533b  lea     rcx, [rbx+600h]; Lookaside
0x140015342  mov     r14, [rax+20h]
0x140015346  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001534d  nop     dword ptr [rax+rax+00h]
0x140015352  mov     rbp, rax
0x140015355  test    rax, rax
0x140015358  jnz     short loc_140015364
0x14001535a  mov     edi, 0C000009Ah
0x14001535f  jmp     loc_1400156DD
0x140015364  mov     r9d, r12d; unsigned int
0x140015367  mov     dword ptr [rsp+88h+var_68], r15d; unsigned int
0x14001536c  mov     r8, rdi; struct _VHD_SRB_EXTENSION *
0x14001536f  mov     rdx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x140015372  mov     rcx, rbp; struct VHD_SRB_PART *
0x140015375  call    ?VhdmpiSrbPartInitialize@@YAXPEAUVHD_SRB_PART@@PEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_SRB_EXTENSION@@KK@Z; VhdmpiSrbPartInitialize(VHD_SRB_PART *,_VHD_BACKING_STORE_HEADER *,_VHD_SRB_EXTENSION *,ulong,ulong)
0x14001537a  lea     rcx, [rdi+0A8h]; SpinLock
0x140015381  mov     [rbp+30h], rbx
0x140015385  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001538c  nop     dword ptr [rax+rax+00h]
0x140015391  lea     rdx, [rbp+8]; struct _LIST_ENTRY *
0x140015395  lea     rcx, [rdi+0B0h]; struct _LIST_ENTRY *
0x14001539c  call    ?VhdmpiInsertTailList@@YAXPEAU_LIST_ENTRY@@0@Z; VhdmpiInsertTailList(_LIST_ENTRY *,_LIST_ENTRY *)
0x1400153a1  lea     rcx, [rdi+0A8h]; SpinLock
0x1400153a8  movzx   edx, al; NewIrql
0x1400153ab  call    cs:__imp_KeReleaseSpinLock
0x1400153b2  nop     dword ptr [rax+rax+00h]
0x1400153b7  mov     r9d, 1
0x1400153bd  lock xadd [rdi+28h], r9
0x1400153c3  inc     r9
0x1400153c6  cmp     r9, 1
0x1400153ca  jg      short loc_1400153D3
0x1400153cc  mov     ecx, 0Eh
0x1400153d1  int     29h; Win8: RtlFailFast(ecx)
0x1400153d3  lea     rdx, [rbp+18h]; struct _LIST_ENTRY *
0x1400153d7  test    r14, r14
0x1400153da  jz      short loc_1400153E6
0x1400153dc  mov     rcx, r14; struct _LIST_ENTRY *
0x1400153df  call    ?VhdmpiInsertTailList@@YAXPEAU_LIST_ENTRY@@0@Z; VhdmpiInsertTailList(_LIST_ENTRY *,_LIST_ENTRY *)
0x1400153e4  jmp     short loc_140015410
0x1400153e6  lea     rax, [rsp+88h+var_38]
0x1400153eb  mov     [rsp+88h+var_38.Blink], rax
0x1400153f0  lea     rcx, [rsp+88h+var_38]; struct _LIST_ENTRY *
0x1400153f5  lea     rax, [rsp+88h+var_38]
0x1400153fa  mov     [rsp+88h+var_38.Flink], rax
0x1400153ff  call    ?VhdmpiInsertTailList@@YAXPEAU_LIST_ENTRY@@0@Z; VhdmpiInsertTailList(_LIST_ENTRY *,_LIST_ENTRY *)
0x140015404  lea     rcx, [rsp+88h+var_38]
0x140015409  xor     edx, edx
0x14001540b  call    VhdmpiProcessParseThreadContext
0x140015410  test    dword ptr [rdi+40h], 100h
0x140015417  jz      short loc_14001541D
0x140015419  mov     byte ptr [rsi+6Dh], 1
0x14001541d  xor     edi, edi
0x14001541f  jmp     loc_1400156DD
0x140015424  cmp     r8d, 2; jumptable 0000000140015291 cases 2-4
0x140015428  jnz     short loc_140015448
0x14001542a  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x140015432  mov     r9d, 1
0x140015438  mov     edx, r10d; unsigned int
0x14001543b  mov     rcx, rsi; struct VHD_SRB_PART *
0x14001543e  call    VhdmpiSrbPartReportZero
0x140015443  jmp     loc_1400156DB
0x140015448  xor     edi, edi
0x14001544a  mov     edx, r10d; unsigned int
0x14001544d  cmp     r8d, 3
0x140015451  mov     rcx, rsi; struct VHD_SRB_PART *
0x140015454  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x14001545c  setz    dil
0x140015460  lea     r9d, [rdi+2]
0x140015464  call    VhdmpiSrbPartReportZero
0x140015469  jmp     loc_1400156DB
0x14001546e  mov     r8d, [rsp+88h+arg_20]; jumptable 0000000140015291 case 6
0x140015476  lea     r9, [rsp+88h+arg_10]
0x14001547e  mov     edx, r10d
0x140015481  mov     rcx, rsi; struct VHD_SRB_PART *
0x140015484  call    VhdmpiSrbPartCheckZero
0x140015489  mov     edi, eax
0x14001548b  test    eax, eax
0x14001548d  js      loc_1400156DD
0x140015493  cmp     [rsp+88h+arg_10], 0
0x14001549b  jz      loc_1400156DD
0x1400154a1  mov     edi, 117h
0x1400154a6  jmp     loc_1400156DD
0x1400154ab  mov     ecx, 25h ; '%'; jumptable 0000000140015291 default case
0x1400154b0  int     29h; Win8: RtlFailFast(ecx)
0x1400154b2  mov     rsi, [rbp+20h]
0x1400154b6  xor     edi, edi
0x1400154b8  test    rsi, rsi
0x1400154bb  jnz     loc_140015558
0x1400154c1  movzx   edx, byte ptr [r14+268h]
0x1400154c9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400154d0  call    cs:__imp_IoSizeOfIrpEx
0x1400154d7  nop     dword ptr [rax+rax+00h]
0x1400154dc  movzx   r15d, ax
0x1400154e0  mov     ecx, 40h ; '@'
0x1400154e5  mov     r8d, 43444856h
0x1400154eb  lea     rdx, [r15+250h]
0x1400154f2  call    cs:__imp_ExAllocatePool2
0x1400154f9  nop     dword ptr [rax+rax+00h]
0x1400154fe  mov     rsi, rax
0x140015501  test    rax, rax
0x140015504  jz      loc_1400156DD
0x14001550a  movzx   r9d, byte ptr [r14+268h]
0x140015512  lea     rbx, [rax+48h]
0x140015516  mov     rcx, rbx
0x140015519  movzx   r8d, r15w
0x14001551d  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140015524  call    cs:__imp_IoInitializeIrpEx
0x14001552b  nop     dword ptr [rax+rax+00h]
0x140015530  mov     [rbx+90h], rdi
0x140015537  lea     rcx, [r15+48h]
0x14001553b  add     rcx, rsi
0x14001553e  mov     [rsi], r14
0x140015541  mov     [rsi+10h], rcx
0x140015545  mov     ecx, edi
0x140015547  mov     [rsi+8], rbx
0x14001554b  mov     dword ptr [rsi+18h], 20h ; ' '
0x140015552  mov     [rbp+20h], rsi
0x140015556  jmp     short loc_14001555F
0x140015558  mov     rax, [rsi+10h]
0x14001555c  mov     ecx, [rax+4]
0x14001555f  mov     rbx, [rsi+10h]
0x140015563  lea     r12d, [rcx+1]
0x140015567  mov     r15d, [rsi+18h]
0x14001556b  mov     rdx, [rsp+88h+arg_28]
0x140015573  mov     r8d, [rsp+88h+arg_20]
0x14001557b  mov     [rsi+30h], rbp
0x14001557f  mov     eax, ecx
0x140015581  add     rax, rax
0x140015584  mov     [rbx+rax*8+8], rdx
0x140015589  mov     [rbx+rax*8+10h], r8
0x14001558e  inc     dword ptr [rbx+4]
0x140015591  mov     eax, cs:dword_140087708
0x140015597  cmp     eax, 5
0x14001559a  jbe     loc_140015625
0x1400155a0  mov     rcx, cs:qword_140087720
0x1400155a7  mov     rax, cs:qword_140087718
0x1400155ae  bt      rax, 0Dh
0x1400155b3  jnb     short loc_140015625
0x1400155b5  mov     rax, rcx
0x1400155b8  and     eax, 2000h
0x1400155bd  cmp     rax, rcx
0x1400155c0  jnz     short loc_140015625
0x1400155c2  add     r14, 58h ; 'X'
0x1400155c6  cmp     r12d, r15d
0x1400155c9  jz      short loc_1400155D8
0x1400155cb  test    byte ptr [rbp+28h], 2
0x1400155cf  lea     rax, aNo; "No"
0x1400155d6  jz      short loc_1400155DF
0x1400155d8  lea     rax, aYes; "Yes"
0x1400155df  mov     [rsp+88h+var_40], r14
0x1400155e4  mov     ecx, 1154h
0x1400155e9  mov     [rsp+88h+var_48], rax
0x1400155ee  mov     r9d, 2000h; int
0x1400155f4  mov     eax, [rbx+4]
0x1400155f7  mov     [rsp+88h+var_50], eax
0x1400155fb  lea     rax, aAddingFileTrim_0; "Adding file trim range: Offset: 0x%I64x"...
0x140015602  mov     [rsp+88h+var_58], r8
0x140015607  mov     r8d, 5; int
0x14001560d  mov     qword ptr [rsp+88h+var_60], rdx; char
0x140015612  mov     edx, ecx; int
0x140015614  lea     rcx, aVhdmpivhd2hand; "VhdmpiVhd2HandleFileTrimSubIo"
0x14001561b  mov     [rsp+88h+var_68], rax; char *
0x140015620  call    TraceEvents
0x140015625  cmp     r12d, r15d
0x140015628  jz      short loc_140015634
0x14001562a  test    byte ptr [rbp+28h], 2
0x14001562e  jz      loc_1400156DD
0x140015634  mov     [rbp+20h], rdi
0x140015638  lea     rdi, [rbp+30h]
0x14001563c  mov     rcx, rdi; SpinLock
0x14001563f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015646  nop     dword ptr [rax+rax+00h]
0x14001564b  mov     rcx, [rbp+38h]
0x14001564f  add     rbp, 38h ; '8'
0x140015653  movzx   edx, al; NewIrql
0x140015656  cmp     [rcx+8], rbp
0x14001565a  jz      short loc_140015663
0x14001565c  mov     ecx, 3
0x140015661  int     29h; Win8: RtlFailFast(ecx)
0x140015663  lea     rax, [rsi+38h]
0x140015667  mov     [rax], rcx
0x14001566a  mov     [rax+8], rbp
0x14001566e  mov     [rcx+8], rax
0x140015672  mov     rcx, rdi; SpinLock
0x140015675  mov     [rbp+0], rax
0x140015679  call    cs:__imp_KeReleaseSpinLock
0x140015680  nop     dword ptr [rax+rax+00h]
0x140015685  mov     r9, rsi; void *
0x140015688  lea     r8, ?VhdmpiVhd2FileTrimCompletion@@YAXPEAXJ@Z; void (*)(void *, int)
0x14001568f  mov     rdx, rbx; struct _FILE_LEVEL_TRIM *
0x140015692  mov     rcx, rsi; struct _TP_IRP_CONTEXT *
0x140015695  call    ?TpSendFileTrim@@YAXPEAU_TP_IRP_CONTEXT@@PEAU_FILE_LEVEL_TRIM@@P6AXPEAXJ@Z2@Z; TpSendFileTrim(_TP_IRP_CONTEXT *,_FILE_LEVEL_TRIM *,void (*)(void *,long),void *)
0x14001569a  mov     edi, 103h
0x14001569f  jmp     short loc_1400156DD
0x1400156a1  mov     r8d, [rsp+88h+arg_20]; jumptable 0000000140015291 case 1
0x1400156a9  lea     rax, ?VhdmpiVhd2SubIoCompletionRoutine@@YAXPEAUVHD_SRB_PART@@PEAXJ_K@Z; VhdmpiVhd2SubIoCompletionRoutine(VHD_SRB_PART *,void *,long,unsigned __int64)
0x1400156b0  mov     byte ptr [rsp+88h+var_50], dl
0x1400156b4  xor     edi, edi
0x1400156b6  mov     [rsp+88h+var_58], rdi
0x1400156bb  mov     r9, r14
0x1400156be  mov     qword ptr [rsp+88h+var_60], rax
0x1400156c3  mov     edx, r10d
0x1400156c6  mov     rax, [rsp+88h+arg_28]
0x1400156ce  mov     rcx, rsi
0x1400156d1  mov     [rsp+88h+var_68], rax
0x1400156d6  call    VhdmpiSrbPartReportPresent
0x1400156db  mov     edi, eax
0x1400156dd  lea     r11, [rsp+88h+var_28]
0x1400156e2  mov     eax, edi
0x1400156e4  mov     rbx, [r11+30h]
0x1400156e8  mov     rbp, [r11+38h]
0x1400156ec  mov     rsp, r11
0x1400156ef  pop     r15
0x1400156f1  pop     r14
0x1400156f3  pop     r12
0x1400156f5  pop     rdi
0x1400156f6  pop     rsi
0x1400156f7  retn
```
