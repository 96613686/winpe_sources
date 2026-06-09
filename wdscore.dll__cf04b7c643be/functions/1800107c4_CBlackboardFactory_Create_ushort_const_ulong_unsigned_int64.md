# CBlackboardFactory::Create(ushort const *,ulong,unsigned __int64)

- ea: `0x1800107c4`
- end: `0x180010a9d`
- name: `?Create@CBlackboardFactory@@QEAAPEAU_BLACKBOARD@@PEBGK_K@Z`
- size: `729`
- prototype: `struct _BLACKBOARD *(CBlackboardFactory *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180018d60`

## callees

- `0x180001144`
- `0x180009da4`
- `0x180009e30`
- `0x18000f200`
- `0x18000f568`
- `0x18000f9b8`
- `0x1800107c4`
- `0x180014c9c`
- `0x180016950`
- `0x180017ab4`
- `0x180017f94`
- `0x1800180b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _BLACKBOARD *__fastcall CBlackboardFactory::Create(
        CBlackboardFactory *this,
        unsigned __int16 *a2,
        unsigned int a3,
        char *a4)
{
  CBlackboardFactory *v7; // rsi
  const unsigned __int16 *v8; // r13
  __int64 v9; // rcx
  __int64 v10; // rdi
  unsigned __int16 *v11; // r14
  int v12; // eax
  unsigned __int64 v13; // rbx
  struct CBlackboardFactory::SKeeperEntry *Entry; // rax
  CBlackboard *v15; // rdi
  char *v16; // rax
  unsigned int v17; // edx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  _QWORD *v20; // r8
  __int128 v21; // [rsp+48h] [rbp-38h]
  unsigned __int16 *v22; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v23; // [rsp+60h] [rbp-20h]
  __int64 v24; // [rsp+68h] [rbp-18h]
  __int64 v25; // [rsp+70h] [rbp-10h]
  CBlackboardFactory *v26; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int64 v27; // [rsp+C8h] [rbp+48h] BYREF
  char *v28; // [rsp+D8h] [rbp+58h] BYREF

  v28 = a4;
  v26 = this;
  if ( !a2 )
    return 0;
  v7 = Block;
  v8 = 0;
  v23 = 0;
  v24 = 0;
  v22 = 0;
  v25 = 10;
  if ( a2[1] == 58 || *a2 == 92 && a2[1] == 92 || (a3 & 2) != 0 )
  {
    v11 = a2;
  }
  else
  {
    v9 = -1;
    if ( *((_QWORD *)Block + 6) )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(*((_QWORD *)Block + 5) + 2 * v10) );
    }
    else
    {
      LODWORD(v10) = 0;
    }
    do
      ++v9;
    while ( a2[v9] );
    if ( !(unsigned int)CDynamicArray<unsigned short,unsigned short *>::SetSize(&v22, v9 + 1 + (unsigned int)v10) )
      goto LABEL_21;
    if ( (_DWORD)v10 )
    {
      v11 = v22;
      if ( (int)StringCchCopyW(v22, v23, *((size_t **)v7 + 5)) < 0 )
        goto LABEL_21;
      v12 = StringCchCatW(v11, v23, a2);
    }
    else
    {
      v11 = v22;
      v12 = StringCchCopyW(v22, v23, (size_t *)a2);
    }
    if ( v12 < 0 )
      goto LABEL_21;
    if ( (a3 & 0xB) == 8 )
      v8 = a2;
  }
  AcquireWriteAccess((volatile int *)v7);
  LODWORD(v28) = 0;
  LODWORD(v26) = 0;
  v27 = 0;
  Entry = CBlackboardFactory::GetEntry(v7, v11, v8, a3, (int *)&v28, (int *)&v26, &v27);
  v15 = 0;
  if ( !(_DWORD)v28 && !(_DWORD)v26 )
  {
    if ( Entry )
    {
      ++*((_DWORD *)Entry + 2);
      v15 = *(CBlackboard **)Entry;
      goto LABEL_39;
    }
    v16 = (char *)operator new(0x88u);
    v15 = (CBlackboard *)v16;
    v28 = v16;
    if ( v16 )
    {
      *((_QWORD *)v16 + 2) = 0;
      *((_QWORD *)v16 + 3) = 0;
      *((_QWORD *)v16 + 1) = 0;
      *((_QWORD *)v16 + 4) = 10;
      *((_QWORD *)v16 + 7) = 0;
      *((_QWORD *)v16 + 9) = 0;
      *((_QWORD *)v16 + 10) = 0;
      *((_QWORD *)v16 + 11) = 0;
      *((_QWORD *)v16 + 12) = 0;
      *((_DWORD *)v16 + 26) = 0;
      *(_QWORD *)v16 = 0;
      *((_QWORD *)v16 + 14) = 0;
      *((_QWORD *)v16 + 8) = 0;
      *(_QWORD *)(v16 + 44) = 0;
      *((_QWORD *)v16 + 15) = 0;
      *((_DWORD *)v16 + 32) = 0;
      *((_QWORD *)&v21 + 1) = 1;
      *(_QWORD *)&v21 = v16;
      if ( (unsigned int)CBlackboard::Open((CBlackboard *)v16, v11, a3) )
      {
        v18 = *((_QWORD *)v7 + 2);
        if ( v18 )
        {
          v19 = 0;
          while ( 1 )
          {
            v20 = (_QWORD *)(*((_QWORD *)v7 + 1) + 16 * v19);
            if ( v20 )
            {
              if ( !*v20 )
                break;
            }
            if ( ++v19 >= v18 )
              goto LABEL_35;
          }
          *(_OWORD *)v20 = v21;
          v27 = v19;
        }
        else
        {
LABEL_35:
          v27 = *((_QWORD *)v7 + 2);
          CDynamicArray<CBlackboardFactory::SKeeperEntry,CBlackboardFactory::SKeeperEntry *>::SetSize(
            (char *)v7 + 8,
            v18 + 1);
          *(_OWORD *)(*((_QWORD *)v7 + 1) + 16LL * *((_QWORD *)v7 + 2) - 16) = v21;
        }
        goto LABEL_39;
      }
      CBlackboard::`scalar deleting destructor'(v15, v17);
    }
    v15 = 0;
  }
LABEL_39:
  ReleaseAccess((volatile int *)v7);
  if ( v15 )
  {
    v13 = v27 + 100;
    goto LABEL_22;
  }
LABEL_21:
  v13 = 0;
LABEL_22:
  CBuffer::~CBuffer((CBuffer *)&v22);
  return (struct _BLACKBOARD *)v13;
}

```

## disassembly

```asm
0x1800107c4  mov     rax, rsp
0x1800107c7  mov     [rax+20h], r9
0x1800107cb  mov     [rax+8], rcx
0x1800107cf  push    rbp
0x1800107d0  push    rsi
0x1800107d1  push    rdi
0x1800107d2  push    r12
0x1800107d4  push    r13
0x1800107d6  push    r14
0x1800107d8  push    r15
0x1800107da  mov     rbp, rsp
0x1800107dd  sub     rsp, 80h
0x1800107e4  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1800107ec  mov     [rax+18h], rbx
0x1800107f0  mov     r15d, r8d
0x1800107f3  mov     rbx, rdx
0x1800107f6  xor     r12d, r12d
0x1800107f9  test    rdx, rdx
0x1800107fc  jnz     short loc_180010805
0x1800107fe  xor     eax, eax
0x180010800  jmp     loc_1800108FF
0x180010805  mov     rsi, cs:Block
0x18001080c  mov     r13, r12
0x18001080f  mov     [rbp+var_20], r12
0x180010813  mov     [rbp+var_18], r12
0x180010817  mov     [rbp+var_28], r12
0x18001081b  mov     [rbp+var_10], 0Ah
0x180010823  mov     eax, 3Ah ; ':'
0x180010828  cmp     ax, [rdx+2]
0x18001082c  jz      loc_18001091B
0x180010832  mov     eax, 5Ch ; '\'
0x180010837  cmp     ax, [rdx]
0x18001083a  jnz     short loc_180010846
0x18001083c  cmp     ax, [rdx+2]
0x180010840  jz      loc_18001091B
0x180010846  test    r15b, 2
0x18001084a  jnz     loc_18001091B
0x180010850  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180010854  cmp     [rsi+30h], r12
0x180010858  jz      short loc_18001086D
0x18001085a  mov     rax, [rsi+28h]
0x18001085e  mov     rdi, rcx
0x180010861  inc     rdi
0x180010864  cmp     [rax+rdi*2], r12w
0x180010869  jnz     short loc_180010861
0x18001086b  jmp     short loc_180010870
0x18001086d  mov     edi, r12d
0x180010870  mov     r14d, 28h ; '('
0x180010876  mov     r12, rsi
0x180010879  xor     eax, eax
0x18001087b  inc     rcx
0x18001087e  cmp     [rdx+rcx*2], ax
0x180010882  jnz     short loc_18001087B
0x180010884  mov     edx, edi
0x180010886  inc     rcx
0x180010889  add     rdx, rcx
0x18001088c  lea     rcx, [rbp+var_28]
0x180010890  call    ?SetSize@?$CDynamicArray@GPEAG@@QEAAH_K@Z; CDynamicArray<ushort,ushort *>::SetSize(unsigned __int64)
0x180010895  test    eax, eax
0x180010897  jz      short loc_1800108ED
0x180010899  mov     rdx, [rbp+var_20]; unsigned __int64
0x18001089d  test    edi, edi
0x18001089f  jz      short loc_1800108C9
0x1800108a1  mov     r8, [r12+r14]; unsigned __int16 *
0x1800108a5  mov     r14, [rbp+var_28]
0x1800108a9  mov     rcx, r14; unsigned __int16 *
0x1800108ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800108b1  xor     r12d, r12d
0x1800108b4  test    eax, eax
0x1800108b6  js      short loc_1800108F0
0x1800108b8  mov     r8, rbx; unsigned __int16 *
0x1800108bb  mov     rdx, [rbp+var_20]; unsigned __int64
0x1800108bf  mov     rcx, r14; unsigned __int16 *
0x1800108c2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800108c7  jmp     short loc_1800108DB
0x1800108c9  mov     r8, rbx; unsigned __int16 *
0x1800108cc  mov     r14, [rbp+var_28]
0x1800108d0  mov     rcx, r14; unsigned __int16 *
0x1800108d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800108d8  xor     r12d, r12d
0x1800108db  test    eax, eax
0x1800108dd  js      short loc_1800108F0
0x1800108df  mov     eax, r15d
0x1800108e2  and     al, 0Bh
0x1800108e4  cmp     al, 8
0x1800108e6  jnz     short loc_18001091E
0x1800108e8  mov     r13, rbx
0x1800108eb  jmp     short loc_18001091E
0x1800108ed  xor     r12d, r12d
0x1800108f0  mov     rbx, r12
0x1800108f3  lea     rcx, [rbp+var_28]; this
0x1800108f7  call    ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x1800108fc  mov     rax, rbx
0x1800108ff  mov     rbx, [rsp+80h+arg_10]
0x180010907  add     rsp, 80h
0x18001090e  pop     r15
0x180010910  pop     r14
0x180010912  pop     r13
0x180010914  pop     r12
0x180010916  pop     rdi
0x180010917  pop     rsi
0x180010918  pop     rbp
0x180010919  retn
0x18001091b  mov     r14, rbx
0x18001091e  mov     rcx, rsi; volatile int *
0x180010921  call    ?AcquireWriteAccess@@YAXPECJ@Z; AcquireWriteAccess(long volatile *)
0x180010926  mov     dword ptr [rbp+arg_18], r12d
0x18001092a  mov     dword ptr [rbp+arg_0], r12d
0x18001092e  mov     [rbp+arg_8], r12
0x180010932  lea     rax, [rbp+arg_8]
0x180010936  mov     [rsp+80h+var_50], rax; unsigned __int64 *
0x18001093b  lea     rax, [rbp+arg_0]
0x18001093f  mov     [rsp+80h+var_58], rax; int *
0x180010944  lea     rax, [rbp+arg_18]
0x180010948  mov     [rsp+80h+var_60], rax; int *
0x18001094d  mov     r9d, r15d; unsigned int
0x180010950  mov     r8, r13; unsigned __int16 *
0x180010953  mov     rdx, r14; unsigned __int16 *
0x180010956  mov     rcx, rsi; this
0x180010959  call    ?GetEntry@CBlackboardFactory@@IEAAPEAUSKeeperEntry@1@PEBG0KAEAH1AEA_K@Z; CBlackboardFactory::GetEntry(ushort const *,ushort const *,ulong,int &,int &,unsigned __int64 &)
0x18001095e  mov     rdi, r12
0x180010961  cmp     dword ptr [rbp+arg_18], r12d
0x180010965  jnz     loc_180010A7E
0x18001096b  cmp     dword ptr [rbp+arg_0], r12d
0x18001096f  jnz     loc_180010A7E
0x180010975  test    rax, rax
0x180010978  jz      short loc_180010985
0x18001097a  inc     dword ptr [rax+8]
0x18001097d  mov     rdi, [rax]
0x180010980  jmp     loc_180010A7E
0x180010985  mov     ecx, 88h; Size
0x18001098a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001098f  mov     rdi, rax
0x180010992  mov     [rbp+arg_18], rax
0x180010996  test    rax, rax
0x180010999  jz      loc_180010A7B
0x18001099f  mov     [rax+10h], r12
0x1800109a3  mov     [rax+18h], r12
0x1800109a7  mov     [rax+8], r12
0x1800109ab  mov     qword ptr [rax+20h], 0Ah
0x1800109b3  mov     [rax+38h], r12
0x1800109b7  mov     [rax+48h], r12
0x1800109bb  mov     [rax+50h], r12
0x1800109bf  mov     [rax+58h], r12
0x1800109c3  mov     [rax+60h], r12
0x1800109c7  mov     [rax+68h], r12d
0x1800109cb  mov     [rax], r12
0x1800109ce  mov     qword ptr [rax+70h], 0
0x1800109d6  mov     [rax+40h], r12
0x1800109da  mov     qword ptr [rax+2Ch], 0
0x1800109e2  mov     [rax+78h], r12
0x1800109e6  mov     [rax+80h], r12d
0x1800109ed  test    rax, rax
0x1800109f0  jz      loc_180010A7E
0x1800109f6  mov     qword ptr [rbp+var_38+8], 1
0x1800109fe  mov     qword ptr [rbp+var_38], rax
0x180010a02  mov     r8d, r15d; unsigned int
0x180010a05  mov     rdx, r14; unsigned __int16 *
0x180010a08  mov     rcx, rax; this
0x180010a0b  call    ?Open@CBlackboard@@QEAAHPEBGK@Z; CBlackboard::Open(ushort const *,ulong)
0x180010a10  test    eax, eax
0x180010a12  jz      short loc_180010A73
0x180010a14  mov     rdx, [rsi+10h]
0x180010a18  test    rdx, rdx
0x180010a1b  jz      short loc_180010A3D
0x180010a1d  mov     rcx, r12
0x180010a20  mov     r9, [rsi+8]
0x180010a24  mov     r8, rcx
0x180010a27  shl     r8, 4
0x180010a2b  add     r8, r9
0x180010a2e  jz      short loc_180010A35
0x180010a30  cmp     [r8], r12
0x180010a33  jz      short loc_180010A64
0x180010a35  inc     rcx
0x180010a38  cmp     rcx, rdx
0x180010a3b  jb      short loc_180010A24
0x180010a3d  mov     [rbp+arg_8], rdx
0x180010a41  inc     rdx
0x180010a44  lea     rcx, [rsi+8]
0x180010a48  call    ?SetSize@?$CDynamicArray@USKeeperEntry@CBlackboardFactory@@PEAU12@@@QEAAH_K@Z; CDynamicArray<CBlackboardFactory::SKeeperEntry,CBlackboardFactory::SKeeperEntry *>::SetSize(unsigned __int64)
0x180010a4d  mov     rcx, [rsi+10h]
0x180010a51  add     rcx, rcx
0x180010a54  mov     rax, [rsi+8]
0x180010a58  movups  xmm0, [rbp+var_38]
0x180010a5c  movdqu  xmmword ptr [rax+rcx*8-10h], xmm0
0x180010a62  jmp     short loc_180010A7E
0x180010a64  movups  xmm0, [rbp+var_38]
0x180010a68  movdqu  xmmword ptr [r8], xmm0
0x180010a6d  mov     [rbp+arg_8], rcx
0x180010a71  jmp     short loc_180010A7E
0x180010a73  mov     rcx, rdi; this
0x180010a76  call    ??_GCBlackboard@@QEAAPEAXI@Z; CBlackboard::`scalar deleting destructor'(uint)
0x180010a7b  mov     rdi, r12
0x180010a7e  mov     rcx, rsi; volatile int *
0x180010a81  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180010a86  test    rdi, rdi
0x180010a89  jz      loc_1800108F0
0x180010a8f  mov     rbx, [rbp+arg_8]
0x180010a93  add     rbx, 64h ; 'd'
0x180010a97  jmp     loc_1800108F3
```
