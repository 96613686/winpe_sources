# WimFSFCheckIntegrityOfBlocks

- ea: `0x140027fac`
- end: `0x140028480`
- name: `WimFSFCheckIntegrityOfBlocks`
- size: `1236`
- prototype: `__int64 __fastcall(PRTL_BITMAP BitMapHeader)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000cae0`
- `0x140028ef4`
- `0x14002a394`

## callees

- `0x140011560`
- `0x140011640`
- `0x140027fac`
- `0x1400295dc`
- `0x140029c50`
- `0x140029f28`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140028391`
- `ntoskrnl!RtlCompareMemory` at `0x140028391`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400280ac`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400280ac`
- `ntoskrnl!RtlSetBit` at `0x1400283bd`
- `ntoskrnl!RtlSetBit` at `0x1400283bd`
- `ntoskrnl!RtlAreBitsSet` at `0x14002807d`
- `ntoskrnl!RtlAreBitsSet` at `0x14002807d`
- `ntoskrnl!PsInitialSystemProcess` at `0x140028346`
- `ntoskrnl!KeStackAttachProcess` at `0x140028350`
- `ntoskrnl!KeStackAttachProcess` at `0x140028350`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002842f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002842f`
- `ntoskrnl!RtlTestBit` at `0x140028062`
- `ntoskrnl!RtlTestBit` at `0x140028107`
- `ntoskrnl!RtlTestBit` at `0x140028062`
- `ntoskrnl!RtlTestBit` at `0x140028107`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400283f9`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140028411`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400283f9`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140028411`

## pseudocode

```c
__int64 __fastcall WimFSFCheckIntegrityOfBlocks(PRTL_BITMAP BitMapHeader, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // r13d
  int v7; // ebx
  ULONG v8; // r12d
  char *v9; // rsi
  ULONG v10; // ecx
  ULONG v11; // edx
  ULONG v12; // r15d
  unsigned int v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  ULONG v22; // eax
  ULONG Length; // [rsp+30h] [rbp-88h] BYREF
  ULONG BitNumber; // [rsp+34h] [rbp-84h] BYREF
  ULONG v27; // [rsp+3Ch] [rbp-7Ch] BYREF
  __int64 v28; // [rsp+40h] [rbp-78h]
  char *v29; // [rsp+48h] [rbp-70h]
  PLOOKASIDE_LIST_EX Lookaside; // [rsp+50h] [rbp-68h]
  _KAPC_STATE ApcState; // [rsp+58h] [rbp-60h] BYREF

  v4 = a4;
  v28 = a3;
  memset(&ApcState, 0, sizeof(ApcState));
  Length = 0;
  v27 = 0;
  BitNumber = 0;
  if ( BitMapHeader && a4 )
  {
    if ( !(unsigned __int8)WimpFSFCalculateBlockIndices(
                             (_DWORD)BitMapHeader,
                             a2,
                             a4,
                             (unsigned int)&BitNumber,
                             (__int64)&Length,
                             (__int64)&v27) )
    {
      WimpFSFIntegrityReportReadFailure(BitMapHeader, a2, v4);
      v7 = -1073741116;
      goto LABEL_39;
    }
    v8 = BitNumber;
    if ( RtlTestBit(BitMapHeader, BitNumber) && RtlAreBitsSet(BitMapHeader, v8, Length) )
    {
      _InterlockedAdd64(&g_PagesFaultedOnAgain, Length);
      return 0;
    }
    Lookaside = (PLOOKASIDE_LIST_EX)&BitMapHeader[4];
    v9 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)&BitMapHeader[4]);
    v29 = v9;
    if ( !v9 )
    {
      v7 = -1073741801;
      goto LABEL_39;
    }
    v7 = 0;
    while ( 1 )
    {
      if ( v8 >= v27 )
      {
        ExFreeToLookasideListEx(Lookaside, v9);
        if ( v7 >= 0 )
          return (unsigned int)v7;
LABEL_39:
        if ( WimSqmIsOptedIn )
          _InterlockedIncrement64(&WimIntegityFailureCount);
        return (unsigned int)v7;
      }
      v10 = 0;
      Length = 0;
      v11 = 32;
      if ( v27 - v8 < 0x20 )
        v11 = v27 - v8;
      BitNumber = v11;
      v12 = 0;
      if ( v11 )
        break;
LABEL_26:
      if ( v10 )
      {
        KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
LABEL_28:
        v22 = Length;
        while ( v12 )
        {
          if ( _bittest((const int *)&v22, --v12) )
          {
            if ( RtlCompareMemory(&v9[32 * v12 + 128], &BitMapHeader[2].Buffer[4 * v12 + 4 * v8], 0x10u) == 16 )
            {
              if ( !LODWORD(BitMapHeader[11].Buffer) )
                RtlSetBit(BitMapHeader, v12 + v8);
              _InterlockedIncrement(&g_PagesValidated);
            }
            else
            {
              WimpFSFIntegrityReportBlockFailure(BitMapHeader, v12 + v8);
              v7 = -1073741116;
            }
            goto LABEL_28;
          }
        }
        KeUnstackDetachProcess(&ApcState);
      }
      v8 += BitNumber;
    }
    while ( 1 )
    {
      if ( RtlTestBit(BitMapHeader, v12 + v8) )
      {
        v28 += 4096;
        _InterlockedIncrement64(&g_PagesFaultedOnAgain);
      }
      else
      {
        v13 = v4;
        if ( v4 > 0x1000 )
          v13 = 4096;
        v14 = v13 >> 2;
        *((_DWORD *)v9 + 290) = 0;
        *((_DWORD *)v9 + 291) = 1;
        v15 = v28;
        *((_QWORD *)v9 + 146) = v28;
        *((_DWORD *)v9 + 294) = v14;
        *((_DWORD *)v9 + 296) = 0;
        *((_DWORD *)v9 + 297) = 2;
        *((_QWORD *)v9 + 149) = v9;
        *((_DWORD *)v9 + 300) = 32;
        v16 = v14 + v15;
        *((_DWORD *)v9 + 302) = 1;
        *((_DWORD *)v9 + 303) = 1;
        *((_QWORD *)v9 + 152) = v16;
        *((_DWORD *)v9 + 306) = v14;
        *((_DWORD *)v9 + 308) = 1;
        *((_DWORD *)v9 + 309) = 2;
        *((_QWORD *)v9 + 155) = v9 + 32;
        *((_DWORD *)v9 + 312) = 32;
        v17 = v14 + v16;
        *((_DWORD *)v9 + 314) = 2;
        *((_DWORD *)v9 + 315) = 1;
        *((_QWORD *)v9 + 158) = v17;
        *((_DWORD *)v9 + 318) = v14;
        *((_DWORD *)v9 + 320) = 2;
        *((_DWORD *)v9 + 321) = 2;
        *((_QWORD *)v9 + 161) = v9 + 64;
        *((_DWORD *)v9 + 324) = 32;
        v18 = v14 + v17;
        *((_DWORD *)v9 + 326) = 3;
        *((_DWORD *)v9 + 327) = 1;
        *((_QWORD *)v9 + 164) = v18;
        v19 = v13 - 3 * (_DWORD)v14;
        *((_DWORD *)v9 + 330) = v19;
        *((_DWORD *)v9 + 332) = 3;
        *((_DWORD *)v9 + 333) = 2;
        *((_QWORD *)v9 + 167) = v9 + 96;
        *((_DWORD *)v9 + 336) = 32;
        v28 = v18 + v19;
        v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, __int64, _DWORD))(g_WimIntegrityCngExtensions + 16))(
                *((_QWORD *)v9 + 144),
                1,
                v9 + 1160,
                192,
                0);
        if ( v20 >= 0 )
        {
          *((_QWORD *)v9 + 146) = v9;
          *((_DWORD *)v9 + 294) = 128;
          *((_QWORD *)v9 + 149) = &v9[32 * v12 + 128];
          *((_DWORD *)v9 + 300) = 32;
          v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(g_WimIntegrityCngExtensions + 16))(
                  *((_QWORD *)v9 + 144),
                  1,
                  v9 + 1160);
          v10 = Length;
          if ( v21 >= 0 )
          {
            v10 = Length | (1 << v12);
            Length = v10;
          }
          else
          {
            v7 = v21;
          }
          goto LABEL_25;
        }
        v7 = v20;
      }
      v10 = Length;
LABEL_25:
      ++v12;
      v4 -= 4096;
      if ( v12 >= BitNumber )
        goto LABEL_26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140027fac  mov     [rsp+arg_10], rbx
0x140027fb1  push    rsi
0x140027fb2  push    r12
0x140027fb4  push    r13
0x140027fb6  push    r14
0x140027fb8  push    r15
0x140027fba  sub     rsp, 90h
0x140027fc1  mov     rax, cs:__security_cookie
0x140027fc8  xor     rax, rsp
0x140027fcb  mov     [rsp+0B8h+var_30], rax
0x140027fd3  mov     r13d, r9d
0x140027fd6  mov     [rsp+0B8h+var_78], r8
0x140027fdb  mov     rbx, rdx
0x140027fde  mov     r14, rcx
0x140027fe1  xorps   xmm0, xmm0
0x140027fe4  movups  xmmword ptr [rsp+0B8h+ApcState.ApcListHead.Flink], xmm0
0x140027fe9  movups  xmmword ptr [rsp+0B8h+ApcState.ApcListHead.Flink+10h], xmm0
0x140027fee  movups  xmmword ptr [rsp+0B8h+ApcState.Process], xmm0
0x140027ff3  mov     [rsp+0B8h+Length], 0
0x140027ffb  mov     [rsp+0B8h+var_7C], 0
0x140028003  mov     [rsp+0B8h+BitNumber], 0
0x14002800b  test    rcx, rcx
0x14002800e  jz      loc_140028454
0x140028014  test    r9d, r9d
0x140028017  jz      loc_140028454
0x14002801d  lea     rax, [rsp+0B8h+var_7C]
0x140028022  mov     [rsp+0B8h+var_90], rax
0x140028027  lea     rax, [rsp+0B8h+Length]
0x14002802c  mov     [rsp+0B8h+var_98], rax
0x140028031  lea     r9, [rsp+0B8h+BitNumber]
0x140028036  mov     r8d, r13d
0x140028039  call    WimpFSFCalculateBlockIndices
0x14002803e  mov     rcx, r14; BitMapHeader
0x140028041  test    al, al
0x140028043  jnz     short loc_14002805A
0x140028045  mov     r8d, r13d
0x140028048  mov     rdx, rbx
0x14002804b  call    WimpFSFIntegrityReportReadFailure
0x140028050  mov     ebx, 0C00002C4h
0x140028055  jmp     loc_14002843F
0x14002805a  mov     r12d, [rsp+0B8h+BitNumber]
0x14002805f  mov     edx, r12d; BitNumber
0x140028062  call    cs:__imp_RtlTestBit
0x140028069  nop     dword ptr [rax+rax+00h]
0x14002806e  test    al, al
0x140028070  jz      short loc_1400280A0
0x140028072  mov     r8d, [rsp+0B8h+Length]; Length
0x140028077  mov     edx, r12d; StartingIndex
0x14002807a  mov     rcx, r14; BitMapHeader
0x14002807d  call    cs:__imp_RtlAreBitsSet
0x140028084  nop     dword ptr [rax+rax+00h]
0x140028089  test    al, al
0x14002808b  jz      short loc_1400280A0
0x14002808d  mov     eax, [rsp+0B8h+Length]
0x140028091  lock add cs:g_PagesFaultedOnAgain, rax
0x140028099  xor     ebx, ebx
0x14002809b  jmp     loc_140028450
0x1400280a0  lea     rax, [r14+40h]
0x1400280a4  mov     [rsp+0B8h+Lookaside], rax
0x1400280a9  mov     rcx, rax; Lookaside
0x1400280ac  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400280b3  nop     dword ptr [rax+rax+00h]
0x1400280b8  mov     rsi, rax
0x1400280bb  mov     [rsp+0B8h+var_70], rax
0x1400280c0  test    rax, rax
0x1400280c3  jnz     short loc_1400280CF
0x1400280c5  mov     ebx, 0C0000017h
0x1400280ca  jmp     loc_14002843F
0x1400280cf  xor     ebx, ebx
0x1400280d1  cmp     r12d, [rsp+0B8h+var_7C]
0x1400280d6  jnb     loc_140028427
0x1400280dc  xor     ecx, ecx
0x1400280de  mov     [rsp+0B8h+Length], ecx
0x1400280e2  mov     eax, [rsp+0B8h+var_7C]
0x1400280e6  sub     eax, r12d
0x1400280e9  lea     edx, [rcx+20h]
0x1400280ec  cmp     eax, edx
0x1400280ee  cmovb   edx, eax
0x1400280f1  mov     [rsp+0B8h+BitNumber], edx
0x1400280f5  xor     r15d, r15d
0x1400280f8  test    edx, edx
0x1400280fa  jz      loc_140028339
0x140028100  lea     edx, [r15+r12]; BitNumber
0x140028104  mov     rcx, r14; BitMapHeader
0x140028107  call    cs:__imp_RtlTestBit
0x14002810e  nop     dword ptr [rax+rax+00h]
0x140028113  test    al, al
0x140028115  jz      short loc_140028131
0x140028117  add     [rsp+0B8h+var_78], 1000h
0x140028120  lock inc cs:g_PagesFaultedOnAgain
0x140028128  mov     ecx, [rsp+0B8h+Length]
0x14002812c  jmp     loc_140028324
0x140028131  mov     r8d, r13d
0x140028134  mov     eax, 1000h
0x140028139  cmp     r13d, eax
0x14002813c  cmova   r8d, eax
0x140028140  mov     edx, r8d
0x140028143  shr     edx, 2
0x140028146  lea     r10, [rsi+488h]
0x14002814d  mov     dword ptr [r10], 0
0x140028154  mov     dword ptr [rsi+48Ch], 1
0x14002815e  mov     rcx, [rsp+0B8h+var_78]
0x140028163  mov     [rsi+490h], rcx
0x14002816a  mov     [rsi+498h], edx
0x140028170  mov     dword ptr [rsi+4A0h], 0
0x14002817a  mov     r11d, 2
0x140028180  mov     [rsi+4A4h], r11d
0x140028187  mov     [rsi+4A8h], rsi
0x14002818e  lea     r9d, [r11+1Eh]
0x140028192  mov     [rsi+4B0h], r9d
0x140028199  add     rcx, rdx
0x14002819c  mov     dword ptr [rsi+4B8h], 1
0x1400281a6  mov     dword ptr [rsi+4BCh], 1
0x1400281b0  mov     [rsi+4C0h], rcx
0x1400281b7  mov     [rsi+4C8h], edx
0x1400281bd  mov     dword ptr [rsi+4D0h], 1
0x1400281c7  mov     [rsi+4D4h], r11d
0x1400281ce  lea     rax, [rsi+20h]
0x1400281d2  mov     [rsi+4D8h], rax
0x1400281d9  mov     [rsi+4E0h], r9d
0x1400281e0  add     rcx, rdx
0x1400281e3  mov     [rsi+4E8h], r11d
0x1400281ea  mov     dword ptr [rsi+4ECh], 1
0x1400281f4  mov     [rsi+4F0h], rcx
0x1400281fb  mov     [rsi+4F8h], edx
0x140028201  mov     [rsi+500h], r11d
0x140028208  mov     [rsi+504h], r11d
0x14002820f  lea     rax, [rsi+40h]
0x140028213  mov     [rsi+508h], rax
0x14002821a  mov     [rsi+510h], r9d
0x140028221  add     rcx, rdx
0x140028224  mov     dword ptr [rsi+518h], 3
0x14002822e  mov     dword ptr [rsi+51Ch], 1
0x140028238  mov     [rsi+520h], rcx
0x14002823f  lea     eax, [rdx+rdx*2]
0x140028242  sub     r8d, eax
0x140028245  mov     edx, r8d
0x140028248  mov     [rsi+528h], edx
0x14002824e  mov     dword ptr [rsi+530h], 3
0x140028258  mov     [rsi+534h], r11d
0x14002825f  lea     rax, [rsi+60h]
0x140028263  mov     [rsi+538h], rax
0x14002826a  mov     [rsi+540h], r9d
0x140028271  add     rdx, rcx
0x140028274  mov     [rsp+0B8h+var_78], rdx
0x140028279  mov     rax, cs:g_WimIntegrityCngExtensions
0x140028280  mov     rax, [rax+10h]
0x140028284  mov     dword ptr [rsp+0B8h+var_98], 0
0x14002828c  mov     r9d, 0C0h
0x140028292  mov     r8, r10
0x140028295  lea     edx, [r11-1]
0x140028299  mov     rcx, [rsi+480h]
0x1400282a0  call    _guard_dispatch_icall
0x1400282a5  test    eax, eax
0x1400282a7  jns     short loc_1400282B0
0x1400282a9  mov     ebx, eax
0x1400282ab  jmp     loc_140028128
0x1400282b0  mov     [rsi+490h], rsi
0x1400282b7  mov     dword ptr [rsi+498h], 80h
0x1400282c1  mov     eax, r15d
0x1400282c4  add     rax, 4
0x1400282c8  shl     rax, 5
0x1400282cc  add     rax, rsi
0x1400282cf  mov     [rsi+4A8h], rax
0x1400282d6  mov     dword ptr [rsi+4B0h], 20h ; ' '
0x1400282e0  mov     rax, cs:g_WimIntegrityCngExtensions
0x1400282e7  mov     rax, [rax+10h]
0x1400282eb  mov     dword ptr [rsp+0B8h+var_98], 0
0x1400282f3  mov     r9d, 30h ; '0'
0x1400282f9  lea     r8, [rsi+488h]
0x140028300  lea     edx, [r9-2Fh]
0x140028304  mov     rcx, [rsi+480h]
0x14002830b  call    _guard_dispatch_icall
0x140028310  mov     ecx, [rsp+0B8h+Length]
0x140028314  test    eax, eax
0x140028316  jns     short loc_14002831C
0x140028318  mov     ebx, eax
0x14002831a  jmp     short loc_140028324
0x14002831c  bts     ecx, r15d
0x140028320  mov     [rsp+0B8h+Length], ecx
0x140028324  inc     r15d
0x140028327  add     r13d, 0FFFFF000h
0x14002832e  cmp     r15d, [rsp+0B8h+BitNumber]
0x140028333  jb      loc_140028100
0x140028339  test    ecx, ecx
0x14002833b  jz      loc_14002841D
0x140028341  lea     rdx, [rsp+0B8h+ApcState]; ApcState
0x140028346  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002834d  mov     rcx, [rcx]; PROCESS
0x140028350  call    cs:__imp_KeStackAttachProcess
0x140028357  nop     dword ptr [rax+rax+00h]
0x14002835c  mov     eax, [rsp+0B8h+Length]
0x140028360  test    r15d, r15d
0x140028363  jz      loc_14002840C
0x140028369  dec     r15d
0x14002836c  bt      eax, r15d
0x140028370  jnb     short loc_140028360
0x140028372  lea     edx, [r15+r12]
0x140028376  shl     edx, 4
0x140028379  add     rdx, [r14+28h]; Source2
0x14002837d  mov     ecx, r15d
0x140028380  add     rcx, 4
0x140028384  shl     rcx, 5
0x140028388  add     rcx, rsi; Source1
0x14002838b  mov     r8d, 10h; Length
0x140028391  call    cs:__imp_RtlCompareMemory
0x140028398  nop     dword ptr [rax+rax+00h]
0x14002839d  cmp     rax, 10h
0x1400283a1  setz    al
0x1400283a4  mov     [rsp+0B8h+var_80], al
0x1400283a8  test    al, al
0x1400283aa  jz      short loc_1400283D2
0x1400283ac  cmp     dword ptr [r14+0B8h], 0
0x1400283b4  jnz     short loc_1400283C9
0x1400283b6  lea     edx, [r15+r12]; BitNumber
0x1400283ba  mov     rcx, r14; BitMapHeader
0x1400283bd  call    cs:__imp_RtlSetBit
0x1400283c4  nop     dword ptr [rax+rax+00h]
0x1400283c9  lock inc cs:g_PagesValidated
0x1400283d0  jmp     short loc_14002835C
0x1400283d2  lea     edx, [r15+r12]
0x1400283d6  mov     rcx, r14
0x1400283d9  call    WimpFSFIntegrityReportBlockFailure
0x1400283de  mov     ebx, 0C00002C4h
0x1400283e3  jmp     loc_14002835C
0x1400283e8  mov     ebx, eax
0x1400283ea  mov     eax, 0C00002C4h
0x1400283ef  test    ebx, ebx
0x1400283f1  cmovns  ebx, eax
0x1400283f4  lea     rcx, [rsp+0B8h+ApcState]; ApcState
0x1400283f9  call    cs:__imp_KeUnstackDetachProcess
0x140028400  nop     dword ptr [rax+rax+00h]
0x140028405  mov     rsi, [rsp+0B8h+var_70]
0x14002840a  jmp     short loc_140028427
0x14002840c  lea     rcx, [rsp+0B8h+ApcState]; ApcState
0x140028411  call    cs:__imp_KeUnstackDetachProcess
0x140028418  nop     dword ptr [rax+rax+00h]
0x14002841d  add     r12d, [rsp+0B8h+BitNumber]
0x140028422  jmp     loc_1400280D1
0x140028427  mov     rdx, rsi; Entry
0x14002842a  mov     rcx, [rsp+0B8h+Lookaside]; Lookaside
0x14002842f  call    cs:__imp_ExFreeToLookasideListEx
0x140028436  nop     dword ptr [rax+rax+00h]
0x14002843b  test    ebx, ebx
0x14002843d  jns     short loc_140028450
0x14002843f  cmp     cs:WimSqmIsOptedIn, 0
0x140028446  jz      short loc_140028450
0x140028448  lock inc cs:WimIntegityFailureCount
0x140028450  mov     eax, ebx
0x140028452  jmp     short loc_140028456
0x140028454  xor     eax, eax
0x140028456  mov     rcx, [rsp+0B8h+var_30]
0x14002845e  xor     rcx, rsp; StackCookie
0x140028461  call    __security_check_cookie
0x140028466  mov     rbx, [rsp+0B8h+arg_10]
0x14002846e  add     rsp, 90h
0x140028475  pop     r15
0x140028477  pop     r14
0x140028479  pop     r13
0x14002847b  pop     r12
0x14002847d  pop     rsi
0x14002847e  retn
```
