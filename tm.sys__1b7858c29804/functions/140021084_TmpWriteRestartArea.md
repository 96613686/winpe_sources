# TmpWriteRestartArea

- ea: `0x140021084`
- end: `0x14002129d`
- name: `TmpWriteRestartArea`
- size: `537`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d330`
- `0x14001ec00`

## callees

- `0x140001330`
- `0x1400024e0`
- `0x140021084`

## import_xrefs

- `CLFS!CLFS_LSN_INVALID` at `0x14002110e`
- `CLFS!CLFS_LSN_NULL` at `0x1400210a3`
- `CLFS!ClfsLsnInvalid` at `0x140021129`
- `CLFS!ClfsLsnInvalid` at `0x1400211f9`
- `CLFS!ClfsLsnInvalid` at `0x140021129`
- `CLFS!ClfsLsnInvalid` at `0x1400211f9`
- `CLFS!ClfsWriteRestartArea` at `0x14002116f`
- `CLFS!ClfsWriteRestartArea` at `0x14002116f`
- `CLFS!ClfsAdvanceLogBase` at `0x14002126b`
- `CLFS!ClfsAdvanceLogBase` at `0x14002126b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021213`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021213`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400210f0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400210f0`

## pseudocode

```c
__int64 __fastcall TmpWriteRestartArea(__int64 a1, const CLFS_LSN *a2, char a3)
{
  __int128 v6; // xmm0
  CLFS_LSN *plsnNext; // r14
  CLFS_LSN *v9; // rsi
  BOOLEAN v10; // al
  CLFS_LSN *v11; // r9
  NTSTATUS v12; // edi
  CLFS_LSN **v13; // rcx
  CLFS_LSN *v14; // rdx
  ULONG pcbWritten; // [rsp+40h] [rbp-58h] BYREF
  _OWORD pvRestartBuffer[2]; // [rsp+48h] [rbp-50h] BYREF

  pcbWritten = 0;
  memset(pvRestartBuffer, 0, sizeof(pvRestartBuffer));
  v6 = *(_OWORD *)(a1 + 112);
  *(CLFS_LSN *)&pvRestartBuffer[0] = CLFS_LSN_NULL;
  DWORD2(pvRestartBuffer[0]) = 260;
  *(_OWORD *)((char *)pvRestartBuffer + 12) = v6;
  plsnNext = (CLFS_LSN *)ExAllocatePoolWithTag(PagedPool, 0x18u, 0x72526D54u);
  if ( !plsnNext )
    return 3221225626LL;
  v9 = plsnNext + 1;
  *plsnNext = CLFS_LSN_INVALID;
  plsnNext[2].ullOffset = (ULONGLONG)&plsnNext[1];
  plsnNext[1].ullOffset = (ULONGLONG)&plsnNext[1];
  v10 = ClfsLsnInvalid(a2);
  v11 = (CLFS_LSN *)a2;
  if ( v10 )
    v11 = 0;
  v12 = ClfsWriteRestartArea(*(PVOID *)(a1 + 160), pvRestartBuffer, 0x20u, v11, a3 != 0 ? 4 : 0, &pcbWritten, plsnNext);
  if ( v12 < 0 )
  {
    ExFreePoolWithTag(plsnNext, 0);
    if ( v12 != -1072037859 || !a3 )
      return (unsigned int)v12;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 31, WPP_0ccf9a6ce45e3f3869fd5164044f21be_Traceguids, a1);
    v14 = (CLFS_LSN *)a2;
  }
  else
  {
    if ( a3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 30, WPP_0ccf9a6ce45e3f3869fd5164044f21be_Traceguids, a1);
      _InterlockedAnd((volatile signed __int32 *)(a1 + 888), 0xFFFFFFFD);
    }
    v13 = *(CLFS_LSN ***)(a1 + 920);
    if ( *v13 != (CLFS_LSN *)(a1 + 912) )
      __fastfail(3u);
    v9->ullOffset = a1 + 912;
    plsnNext[2].ullOffset = (ULONGLONG)v13;
    *v13 = v9;
    *(_QWORD *)(a1 + 920) = v9;
    _InterlockedAnd((volatile signed __int32 *)(a1 + 132), 0xFFFFFEFF);
    if ( !ClfsLsnInvalid(a2) )
      return (unsigned int)v12;
    v14 = plsnNext;
  }
  return (unsigned int)ClfsAdvanceLogBase(*(PVOID *)(a1 + 160), v14, 0);
}

```

## disassembly

```asm
0x140021084  mov     [rsp+arg_10], rbx
0x140021089  push    rbp
0x14002108a  push    rsi
0x14002108b  push    rdi
0x14002108c  push    r14
0x14002108e  push    r15
0x140021090  sub     rsp, 70h
0x140021094  mov     rax, cs:__security_cookie
0x14002109b  xor     rax, rsp
0x14002109e  mov     [rsp+98h+var_30], rax
0x1400210a3  mov     rax, cs:__imp_CLFS_LSN_NULL
0x1400210aa  mov     rbx, rcx
0x1400210ad  xorps   xmm0, xmm0
0x1400210b0  mov     [rsp+98h+var_58], 0
0x1400210b8  movups  [rsp+98h+pvRestartBuffer], xmm0
0x1400210bd  mov     r15, rdx
0x1400210c0  mov     edx, 18h; NumberOfBytes
0x1400210c5  movups  [rsp+98h+var_40], xmm0
0x1400210ca  mov     rcx, [rax]
0x1400210cd  mov     bpl, r8b
0x1400210d0  movups  xmm0, xmmword ptr [rbx+70h]
0x1400210d4  mov     qword ptr [rsp+98h+pvRestartBuffer], rcx
0x1400210d9  mov     r8d, 72526D54h; Tag
0x1400210df  lea     ecx, [rdx-17h]; PoolType
0x1400210e2  mov     dword ptr [rsp+98h+pvRestartBuffer+8], 104h
0x1400210ea  movdqu  [rsp+98h+pvRestartBuffer+0Ch], xmm0
0x1400210f0  call    cs:__imp_ExAllocatePoolWithTag
0x1400210f7  nop     dword ptr [rax+rax+00h]
0x1400210fc  mov     r14, rax
0x1400210ff  test    rax, rax
0x140021102  jnz     short loc_14002110E
0x140021104  mov     eax, 0C000009Ah
0x140021109  jmp     loc_14002127B
0x14002110e  mov     rax, cs:__imp_CLFS_LSN_INVALID
0x140021115  lea     rsi, [r14+8]
0x140021119  mov     rcx, [rax]
0x14002111c  mov     [r14], rcx
0x14002111f  mov     rcx, r15; plsn
0x140021122  mov     [rsi+8], rsi
0x140021126  mov     [rsi], rsi
0x140021129  call    cs:__imp_ClfsLsnInvalid
0x140021130  nop     dword ptr [rax+rax+00h]
0x140021135  xor     ecx, ecx
0x140021137  mov     [rsp+98h+plsnNext], r14; plsnNext
0x14002113c  test    al, al
0x14002113e  lea     rdx, [rsp+98h+pvRestartBuffer]; pvRestartBuffer
0x140021143  mov     al, bpl
0x140021146  mov     r9, r15
0x140021149  cmovnz  r9, rcx; plsnBase
0x14002114d  mov     r8d, 20h ; ' '; cbRestartBuffer
0x140021153  neg     al
0x140021155  lea     rax, [rsp+98h+var_58]
0x14002115a  sbb     ecx, ecx
0x14002115c  mov     [rsp+98h+pcbWritten], rax; pcbWritten
0x140021161  and     ecx, 4
0x140021164  mov     [rsp+98h+fFlags], ecx; fFlags
0x140021168  mov     rcx, [rbx+0A0h]; pvMarshalContext
0x14002116f  call    cs:__imp_ClfsWriteRestartArea
0x140021176  nop     dword ptr [rax+rax+00h]
0x14002117b  mov     edi, eax
0x14002117d  test    eax, eax
0x14002117f  js      loc_14002120E
0x140021185  test    bpl, bpl
0x140021188  jz      short loc_1400211C6
0x14002118a  mov     r10, cs:WPP_GLOBAL_Control
0x140021191  lea     rax, WPP_GLOBAL_Control
0x140021198  cmp     r10, rax
0x14002119b  jz      short loc_1400211BE
0x14002119d  mov     ecx, [r10+2Ch]
0x1400211a1  test    cl, 1
0x1400211a4  jz      short loc_1400211BE
0x1400211a6  mov     rcx, [r10+18h]
0x1400211aa  lea     r8, WPP_0ccf9a6ce45e3f3869fd5164044f21be_Traceguids
0x1400211b1  mov     edx, 1Eh
0x1400211b6  mov     r9, rbx
0x1400211b9  call    WPP_SF_q
0x1400211be  lock and dword ptr [rbx+378h], 0FFFFFFFDh
0x1400211c6  lea     rax, [rbx+390h]
0x1400211cd  mov     rcx, [rax+8]
0x1400211d1  cmp     [rcx], rax
0x1400211d4  jz      short loc_1400211DD
0x1400211d6  mov     ecx, 3
0x1400211db  int     29h; Win8: RtlFailFast(ecx)
0x1400211dd  mov     [rsi], rax
0x1400211e0  mov     [rsi+8], rcx
0x1400211e4  mov     [rcx], rsi
0x1400211e7  mov     [rax+8], rsi
0x1400211eb  lock and dword ptr [rbx+84h], 0FFFFFEFFh
0x1400211f6  mov     rcx, r15; plsn
0x1400211f9  call    cs:__imp_ClfsLsnInvalid
0x140021200  nop     dword ptr [rax+rax+00h]
0x140021205  test    al, al
0x140021207  jz      short loc_140021279
0x140021209  mov     rdx, r14
0x14002120c  jmp     short loc_140021261
0x14002120e  xor     edx, edx; Tag
0x140021210  mov     rcx, r14; P
0x140021213  call    cs:__imp_ExFreePoolWithTag
0x14002121a  nop     dword ptr [rax+rax+00h]
0x14002121f  cmp     edi, 0C01A001Dh
0x140021225  jnz     short loc_140021279
0x140021227  test    bpl, bpl
0x14002122a  jz      short loc_140021279
0x14002122c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021233  lea     rax, WPP_GLOBAL_Control
0x14002123a  cmp     rcx, rax
0x14002123d  jz      short loc_14002125E
0x14002123f  mov     eax, [rcx+2Ch]
0x140021242  test    al, 2
0x140021244  jz      short loc_14002125E
0x140021246  mov     rcx, [rcx+18h]
0x14002124a  lea     r8, WPP_0ccf9a6ce45e3f3869fd5164044f21be_Traceguids
0x140021251  mov     edx, 1Fh
0x140021256  mov     r9, rbx
0x140021259  call    WPP_SF_q
0x14002125e  mov     rdx, r15; plsnBase
0x140021261  mov     rcx, [rbx+0A0h]; pvMarshalContext
0x140021268  xor     r8d, r8d; fFlags
0x14002126b  call    cs:__imp_ClfsAdvanceLogBase
0x140021272  nop     dword ptr [rax+rax+00h]
0x140021277  mov     edi, eax
0x140021279  mov     eax, edi
0x14002127b  mov     rcx, [rsp+98h+var_30]
0x140021280  xor     rcx, rsp; StackCookie
0x140021283  call    __security_check_cookie
0x140021288  mov     rbx, [rsp+98h+arg_10]
0x140021290  add     rsp, 70h
0x140021294  pop     r15
0x140021296  pop     r14
0x140021298  pop     rdi
0x140021299  pop     rsi
0x14002129a  pop     rbp
0x14002129b  retn
```
