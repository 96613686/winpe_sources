# VhdmpiVhd2SubIoRoutineEx(_VHD2_FILE *,_VHD2_READ_WRITE *,_VHD2_RANGE_TYPE,ulong,ulong,unsigned __int64,uchar,AE_TODO *)

- ea: `0x1400156b0`
- end: `0x140015b99`
- name: `?VhdmpiVhd2SubIoRoutineEx@@YAJPEAU_VHD2_FILE@@PEAU_VHD2_READ_WRITE@@W4_VHD2_RANGE_TYPE@@KK_KEPEAUAE_TODO@@@Z`
- size: `1257`
- prototype: `int __high(struct _VHD2_FILE *, struct _VHD2_READ_WRITE *, enum _VHD2_RANGE_TYPE, unsigned int, unsigned int, unsigned __int64, unsigned __int8, struct AE_TODO *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140010bc0`
- `0x140010bfc`
- `0x140011e90`
- `0x140012960`
- `0x140012b40`
- `0x140014c30`
- `0x1400156b0`
- `0x14001730c`
- `0x140036284`

## import_xrefs

- `ntoskrnl!IoSizeOfIrpEx` at `0x140015970`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140015970`
- `ntoskrnl!IoInitializeIrpEx` at `0x1400159c4`
- `ntoskrnl!IoInitializeIrpEx` at `0x1400159c4`
- `ntoskrnl!ExAllocatePool2` at `0x140015992`
- `ntoskrnl!ExAllocatePool2` at `0x140015992`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400157e6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400157e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015825`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015adf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015825`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015adf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001584b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015b19`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001584b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015b19`

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
    if ( (unsigned int)dword_1400876D0 > 5
      && (qword_1400876E0 & 0x2000) != 0
      && (qword_1400876E8 & 0x2000) == qword_1400876E8 )
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
0x1400156b0  mov     [rsp+arg_0], rbx
0x1400156b5  mov     [rsp+arg_8], rbp
0x1400156ba  push    rsi
0x1400156bb  push    rdi
0x1400156bc  push    r12
0x1400156be  push    r14
0x1400156c0  push    r15
0x1400156c2  sub     rsp, 60h
0x1400156c6  lea     rbp, [rdx-48h]
0x1400156ca  mov     [rsp+88h+arg_10], 0
0x1400156d2  movzx   edx, [rsp+88h+arg_30]
0x1400156da  lea     r14, [rcx-8C0h]
0x1400156e1  movzx   eax, dl
0x1400156e4  lea     rsi, [rbp-70h]
0x1400156e8  neg     al
0x1400156ea  mov     r10d, r9d
0x1400156ed  movzx   eax, byte ptr [rbp+28h]
0x1400156f1  sbb     cl, cl
0x1400156f3  and     al, 0FDh
0x1400156f5  and     cl, 2
0x1400156f8  or      cl, al
0x1400156fa  mov     [rbp+28h], cl
0x1400156fd  test    r8d, r8d
0x140015700  jz      loc_140015B41; jumptable 0000000140015731 case 1
0x140015706  cmp     r8d, 7
0x14001570a  jz      loc_140015952
0x140015710  lea     eax, [r8-1]; switch 6 cases
0x140015714  cmp     eax, 5
0x140015717  ja      def_140015731; jumptable 0000000140015731 default case
0x14001571d  lea     r9, cs:140000000h
0x140015724  cdqe
0x140015726  mov     ecx, ds:(jpt_140015731 - 140000000h)[r9+rax*4]
0x14001572e  add     rcx, r9
0x140015731  jmp     rcx; switch jump
0x140015737  mov     rdi, [rsi]; jumptable 0000000140015731 case 5
0x14001573a  xorps   xmm0, xmm0
0x14001573d  mov     r12d, [rsi+58h]
0x140015741  mov     rbx, [rsi+28h]
0x140015745  movups  xmmword ptr [rsp+88h+var_38.Flink], xmm0
0x14001574a  sub     r12d, [rdi+20h]
0x14001574e  add     r12d, r10d
0x140015751  cmp     rbx, [rdi+88h]
0x140015758  jnz     short loc_14001579F
0x14001575a  mov     rcx, [rdi+80h]
0x140015761  xor     edi, edi
0x140015763  test    rcx, rcx
0x140015766  jnz     short loc_14001577F
0x140015768  mov     eax, [rsp+88h+arg_20]
0x14001576f  mov     ecx, edi
0x140015771  mov     dword ptr [rcx], 4
0x140015777  mov     [rcx+4], eax
0x14001577a  jmp     loc_140015B7D
0x14001577f  mov     eax, r12d
0x140015782  shr     rax, 9
0x140015786  lea     rcx, [rcx+rax*8]
0x14001578a  mov     eax, [rsp+88h+arg_20]
0x140015791  mov     dword ptr [rcx], 4
0x140015797  mov     [rcx+4], eax
0x14001579a  jmp     loc_140015B7D
0x14001579f  mov     rbx, [rbx+478h]
0x1400157a6  test    rbx, rbx
0x1400157a9  jnz     short loc_1400157B5
0x1400157ab  mov     edi, 0C00000E5h
0x1400157b0  jmp     loc_140015B7D
0x1400157b5  mov     r15d, [rsp+88h+arg_20]
0x1400157bd  test    r10d, r10d
0x1400157c0  jnz     short loc_1400157D3
0x1400157c2  cmp     r15d, [rsi+60h]
0x1400157c6  jnz     short loc_1400157D3
0x1400157c8  mov     byte ptr [rsi+6Eh], 1
0x1400157cc  xor     edi, edi
0x1400157ce  jmp     loc_140015B7D
0x1400157d3  mov     rax, [rsp+88h+arg_38]
0x1400157db  lea     rcx, [rbx+600h]; Lookaside
0x1400157e2  mov     r14, [rax+20h]
0x1400157e6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400157ed  nop     dword ptr [rax+rax+00h]
0x1400157f2  mov     rbp, rax
0x1400157f5  test    rax, rax
0x1400157f8  jnz     short loc_140015804
0x1400157fa  mov     edi, 0C000009Ah
0x1400157ff  jmp     loc_140015B7D
0x140015804  mov     r9d, r12d; unsigned int
0x140015807  mov     dword ptr [rsp+88h+var_68], r15d; unsigned int
0x14001580c  mov     r8, rdi; struct _VHD_SRB_EXTENSION *
0x14001580f  mov     rdx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x140015812  mov     rcx, rbp; struct VHD_SRB_PART *
0x140015815  call    ?VhdmpiSrbPartInitialize@@YAXPEAUVHD_SRB_PART@@PEAU_VHD_BACKING_STORE_HEADER@@PEAU_VHD_SRB_EXTENSION@@KK@Z; VhdmpiSrbPartInitialize(VHD_SRB_PART *,_VHD_BACKING_STORE_HEADER *,_VHD_SRB_EXTENSION *,ulong,ulong)
0x14001581a  lea     rcx, [rdi+0A8h]; SpinLock
0x140015821  mov     [rbp+30h], rbx
0x140015825  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001582c  nop     dword ptr [rax+rax+00h]
0x140015831  lea     rdx, [rbp+8]; struct _LIST_ENTRY *
0x140015835  lea     rcx, [rdi+0B0h]; struct _LIST_ENTRY *
0x14001583c  call    ?VhdmpiInsertTailList@@YAXPEAU_LIST_ENTRY@@0@Z; VhdmpiInsertTailList(_LIST_ENTRY *,_LIST_ENTRY *)
0x140015841  lea     rcx, [rdi+0A8h]; SpinLock
0x140015848  movzx   edx, al; NewIrql
0x14001584b  call    cs:__imp_KeReleaseSpinLock
0x140015852  nop     dword ptr [rax+rax+00h]
0x140015857  mov     r9d, 1
0x14001585d  lock xadd [rdi+28h], r9
0x140015863  inc     r9
0x140015866  cmp     r9, 1
0x14001586a  jg      short loc_140015873
0x14001586c  mov     ecx, 0Eh
0x140015871  int     29h; Win8: RtlFailFast(ecx)
0x140015873  lea     rdx, [rbp+18h]; struct _LIST_ENTRY *
0x140015877  test    r14, r14
0x14001587a  jz      short loc_140015886
0x14001587c  mov     rcx, r14; struct _LIST_ENTRY *
0x14001587f  call    ?VhdmpiInsertTailList@@YAXPEAU_LIST_ENTRY@@0@Z; VhdmpiInsertTailList(_LIST_ENTRY *,_LIST_ENTRY *)
0x140015884  jmp     short loc_1400158B0
0x140015886  lea     rax, [rsp+88h+var_38]
0x14001588b  mov     [rsp+88h+var_38.Blink], rax
0x140015890  lea     rcx, [rsp+88h+var_38]; struct _LIST_ENTRY *
0x140015895  lea     rax, [rsp+88h+var_38]
0x14001589a  mov     [rsp+88h+var_38.Flink], rax
0x14001589f  call    ?VhdmpiInsertTailList@@YAXPEAU_LIST_ENTRY@@0@Z; VhdmpiInsertTailList(_LIST_ENTRY *,_LIST_ENTRY *)
0x1400158a4  lea     rcx, [rsp+88h+var_38]
0x1400158a9  xor     edx, edx
0x1400158ab  call    VhdmpiProcessParseThreadContext
0x1400158b0  test    dword ptr [rdi+40h], 100h
0x1400158b7  jz      short loc_1400158BD
0x1400158b9  mov     byte ptr [rsi+6Dh], 1
0x1400158bd  xor     edi, edi
0x1400158bf  jmp     loc_140015B7D
0x1400158c4  cmp     r8d, 2; jumptable 0000000140015731 cases 2-4
0x1400158c8  jnz     short loc_1400158E8
0x1400158ca  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x1400158d2  mov     r9d, 1
0x1400158d8  mov     edx, r10d; unsigned int
0x1400158db  mov     rcx, rsi; struct VHD_SRB_PART *
0x1400158de  call    VhdmpiSrbPartReportZero
0x1400158e3  jmp     loc_140015B7B
0x1400158e8  xor     edi, edi
0x1400158ea  mov     edx, r10d; unsigned int
0x1400158ed  cmp     r8d, 3
0x1400158f1  mov     rcx, rsi; struct VHD_SRB_PART *
0x1400158f4  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x1400158fc  setz    dil
0x140015900  lea     r9d, [rdi+2]
0x140015904  call    VhdmpiSrbPartReportZero
0x140015909  jmp     loc_140015B7B
0x14001590e  mov     r8d, [rsp+88h+arg_20]; jumptable 0000000140015731 case 6
0x140015916  lea     r9, [rsp+88h+arg_10]
0x14001591e  mov     edx, r10d
0x140015921  mov     rcx, rsi; struct VHD_SRB_PART *
0x140015924  call    VhdmpiSrbPartCheckZero
0x140015929  mov     edi, eax
0x14001592b  test    eax, eax
0x14001592d  js      loc_140015B7D
0x140015933  cmp     [rsp+88h+arg_10], 0
0x14001593b  jz      loc_140015B7D
0x140015941  mov     edi, 117h
0x140015946  jmp     loc_140015B7D
0x14001594b  mov     ecx, 25h ; '%'; jumptable 0000000140015731 default case
0x140015950  int     29h; Win8: RtlFailFast(ecx)
0x140015952  mov     rsi, [rbp+20h]
0x140015956  xor     edi, edi
0x140015958  test    rsi, rsi
0x14001595b  jnz     loc_1400159F8
0x140015961  movzx   edx, byte ptr [r14+268h]
0x140015969  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140015970  call    cs:__imp_IoSizeOfIrpEx
0x140015977  nop     dword ptr [rax+rax+00h]
0x14001597c  movzx   r15d, ax
0x140015980  mov     ecx, 40h ; '@'
0x140015985  mov     r8d, 43444856h
0x14001598b  lea     rdx, [r15+250h]
0x140015992  call    cs:__imp_ExAllocatePool2
0x140015999  nop     dword ptr [rax+rax+00h]
0x14001599e  mov     rsi, rax
0x1400159a1  test    rax, rax
0x1400159a4  jz      loc_140015B7D
0x1400159aa  movzx   r9d, byte ptr [r14+268h]
0x1400159b2  lea     rbx, [rax+48h]
0x1400159b6  mov     rcx, rbx
0x1400159b9  movzx   r8d, r15w
0x1400159bd  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1400159c4  call    cs:__imp_IoInitializeIrpEx
0x1400159cb  nop     dword ptr [rax+rax+00h]
0x1400159d0  mov     [rbx+90h], rdi
0x1400159d7  lea     rcx, [r15+48h]
0x1400159db  add     rcx, rsi
0x1400159de  mov     [rsi], r14
0x1400159e1  mov     [rsi+10h], rcx
0x1400159e5  mov     ecx, edi
0x1400159e7  mov     [rsi+8], rbx
0x1400159eb  mov     dword ptr [rsi+18h], 20h ; ' '
0x1400159f2  mov     [rbp+20h], rsi
0x1400159f6  jmp     short loc_1400159FF
0x1400159f8  mov     rax, [rsi+10h]
0x1400159fc  mov     ecx, [rax+4]
0x1400159ff  mov     rbx, [rsi+10h]
0x140015a03  lea     r12d, [rcx+1]
0x140015a07  mov     r15d, [rsi+18h]
0x140015a0b  mov     rdx, [rsp+88h+arg_28]
0x140015a13  mov     r8d, [rsp+88h+arg_20]
0x140015a1b  mov     [rsi+30h], rbp
0x140015a1f  mov     eax, ecx
0x140015a21  add     rax, rax
0x140015a24  mov     [rbx+rax*8+8], rdx
0x140015a29  mov     [rbx+rax*8+10h], r8
0x140015a2e  inc     dword ptr [rbx+4]
0x140015a31  mov     eax, cs:dword_1400876D0
0x140015a37  cmp     eax, 5
0x140015a3a  jbe     loc_140015AC5
0x140015a40  mov     rcx, cs:qword_1400876E8
0x140015a47  mov     rax, cs:qword_1400876E0
0x140015a4e  bt      rax, 0Dh
0x140015a53  jnb     short loc_140015AC5
0x140015a55  mov     rax, rcx
0x140015a58  and     eax, 2000h
0x140015a5d  cmp     rax, rcx
0x140015a60  jnz     short loc_140015AC5
0x140015a62  add     r14, 58h ; 'X'
0x140015a66  cmp     r12d, r15d
0x140015a69  jz      short loc_140015A78
0x140015a6b  test    byte ptr [rbp+28h], 2
0x140015a6f  lea     rax, aNo; "No"
0x140015a76  jz      short loc_140015A7F
0x140015a78  lea     rax, aYes; "Yes"
0x140015a7f  mov     [rsp+88h+var_40], r14
0x140015a84  mov     ecx, 1154h
0x140015a89  mov     [rsp+88h+var_48], rax
0x140015a8e  mov     r9d, 2000h; int
0x140015a94  mov     eax, [rbx+4]
0x140015a97  mov     [rsp+88h+var_50], eax
0x140015a9b  lea     rax, aAddingFileTrim_0; "Adding file trim range: Offset: 0x%I64x"...
0x140015aa2  mov     [rsp+88h+var_58], r8
0x140015aa7  mov     r8d, 5; int
0x140015aad  mov     qword ptr [rsp+88h+var_60], rdx; char
0x140015ab2  mov     edx, ecx; int
0x140015ab4  lea     rcx, aVhdmpivhd2hand; "VhdmpiVhd2HandleFileTrimSubIo"
0x140015abb  mov     [rsp+88h+var_68], rax; char *
0x140015ac0  call    TraceEvents
0x140015ac5  cmp     r12d, r15d
0x140015ac8  jz      short loc_140015AD4
0x140015aca  test    byte ptr [rbp+28h], 2
0x140015ace  jz      loc_140015B7D
0x140015ad4  mov     [rbp+20h], rdi
0x140015ad8  lea     rdi, [rbp+30h]
0x140015adc  mov     rcx, rdi; SpinLock
0x140015adf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015ae6  nop     dword ptr [rax+rax+00h]
0x140015aeb  mov     rcx, [rbp+38h]
0x140015aef  add     rbp, 38h ; '8'
0x140015af3  movzx   edx, al; NewIrql
0x140015af6  cmp     [rcx+8], rbp
0x140015afa  jz      short loc_140015B03
0x140015afc  mov     ecx, 3
0x140015b01  int     29h; Win8: RtlFailFast(ecx)
0x140015b03  lea     rax, [rsi+38h]
0x140015b07  mov     [rax], rcx
0x140015b0a  mov     [rax+8], rbp
0x140015b0e  mov     [rcx+8], rax
0x140015b12  mov     rcx, rdi; SpinLock
0x140015b15  mov     [rbp+0], rax
0x140015b19  call    cs:__imp_KeReleaseSpinLock
0x140015b20  nop     dword ptr [rax+rax+00h]
0x140015b25  mov     r9, rsi; void *
0x140015b28  lea     r8, ?VhdmpiVhd2FileTrimCompletion@@YAXPEAXJ@Z; void (*)(void *, int)
0x140015b2f  mov     rdx, rbx; struct _FILE_LEVEL_TRIM *
0x140015b32  mov     rcx, rsi; struct _TP_IRP_CONTEXT *
0x140015b35  call    ?TpSendFileTrim@@YAXPEAU_TP_IRP_CONTEXT@@PEAU_FILE_LEVEL_TRIM@@P6AXPEAXJ@Z2@Z; TpSendFileTrim(_TP_IRP_CONTEXT *,_FILE_LEVEL_TRIM *,void (*)(void *,long),void *)
0x140015b3a  mov     edi, 103h
0x140015b3f  jmp     short loc_140015B7D
0x140015b41  mov     r8d, [rsp+88h+arg_20]; jumptable 0000000140015731 case 1
0x140015b49  lea     rax, ?VhdmpiVhd2SubIoCompletionRoutine@@YAXPEAUVHD_SRB_PART@@PEAXJ_K@Z; VhdmpiVhd2SubIoCompletionRoutine(VHD_SRB_PART *,void *,long,unsigned __int64)
0x140015b50  mov     byte ptr [rsp+88h+var_50], dl
0x140015b54  xor     edi, edi
0x140015b56  mov     [rsp+88h+var_58], rdi
0x140015b5b  mov     r9, r14
0x140015b5e  mov     qword ptr [rsp+88h+var_60], rax
0x140015b63  mov     edx, r10d
0x140015b66  mov     rax, [rsp+88h+arg_28]
0x140015b6e  mov     rcx, rsi
0x140015b71  mov     [rsp+88h+var_68], rax
0x140015b76  call    VhdmpiSrbPartReportPresent
0x140015b7b  mov     edi, eax
0x140015b7d  lea     r11, [rsp+88h+var_28]
0x140015b82  mov     eax, edi
0x140015b84  mov     rbx, [r11+30h]
0x140015b88  mov     rbp, [r11+38h]
0x140015b8c  mov     rsp, r11
0x140015b8f  pop     r15
0x140015b91  pop     r14
0x140015b93  pop     r12
0x140015b95  pop     rdi
0x140015b96  pop     rsi
0x140015b97  retn
```
