# SecMgrGetIntfState(MSMSEC_INTF_CONTEXT *,int,MSMSEC_INTF_STATE * *)

- ea: `0x180008e4c`
- end: `0x1800091d5`
- name: `?SecMgrGetIntfState@@YAKPEAUMSMSEC_INTF_CONTEXT@@HPEAPEAUMSMSEC_INTF_STATE@@@Z`
- size: `905`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *, int, struct MSMSEC_INTF_STATE **)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x180008ce4`
- `0x1800539f0`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180008e4c`
- `0x18000b8fc`
- `0x18000c730`
- `0x18000e620`
- `0x180011030`
- `0x1800169c0`
- `0x180034924`
- `0x180036990`
- `0x180042b48`
- `0x180055a38`
- `0x180058e30`
- `0x180059d64`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18000904f`
- `MobileNetworking!ReleaseWriteLock` at `0x18000915b`
- `MobileNetworking!ReleaseWriteLock` at `0x18000904f`
- `MobileNetworking!ReleaseWriteLock` at `0x18000915b`

## pseudocode

```c
__int64 __fastcall SecMgrGetIntfState(struct MSMSEC_INTF_CONTEXT *a1, __int64 a2, struct MSMSEC_INTF_STATE **a3)
{
  _DWORD *v3; // rdi
  int v5; // r15d
  unsigned int PortPtrList; // eax
  unsigned int v8; // ebx
  int v9; // r13d
  unsigned int NumActivePorts; // r14d
  unsigned int MSMSecMemory; // eax
  unsigned int i; // r15d
  int v13; // r8d
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  struct _LIST_ENTRY v18; // [rsp+30h] [rbp-18h] BYREF
  _DWORD *v19; // [rsp+A8h] [rbp+60h] BYREF

  v3 = 0;
  v19 = 0;
  v18 = 0;
  v5 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 167, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  v18.Blink = &v18;
  v18.Flink = &v18;
  PortPtrList = SecMgrLockAndCheckAdapterDeleted(a1, a2, (int)a3);
  v8 = PortPtrList;
  if ( PortPtrList )
  {
    v9 = 0;
    NumActivePorts = 0;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_6;
    v15 = 168;
    goto LABEL_30;
  }
  v9 = 1;
  NumActivePorts = GetNumActivePorts(a1);
  MSMSecMemory = AllocateMSMSecMemory(v5 != 0 ? 8 * NumActivePorts + 32 : 32);
  v8 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 169, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, MSMSecMemory);
    v3 = v19;
    goto LABEL_6;
  }
  v16 = *((_QWORD *)a1 + 348);
  v3 = v19;
  if ( v16 )
  {
    *v19 = **(_DWORD **)(v16 + 24);
    v3[1] = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 348) + 24LL) + 4LL);
  }
  v3[2] = *((_DWORD *)a1 + 590);
  *((_WORD *)v3 + 6) = *((_WORD *)a1 + 1182);
  v3[4] = MapIntfSecState(*((unsigned int *)a1 + 681));
  v3[5] = *((_DWORD *)a1 + 832);
  *((_QWORD *)v3 + 3) = *((unsigned int *)a1 + 833);
  if ( !NumActivePorts || !v5 )
  {
LABEL_18:
    *a3 = (struct MSMSEC_INTF_STATE *)v3;
    goto LABEL_19;
  }
  PortPtrList = SecMgrRefPortsAndGetPortPtrList(
                  *((struct _LIST_ENTRY **)a1 + 334),
                  (struct _LIST_ENTRY *)a1 + 167,
                  &v18);
  v8 = PortPtrList;
  if ( !PortPtrList )
  {
    TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrGetIntfState", 2707);
    v9 = 0;
    PortPtrList = SecMgrGetPortListState(&v18, NumActivePorts, (struct MSMSEC_PEER_STATE **)v3 + 4);
    v8 = PortPtrList;
    if ( PortPtrList )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_6;
      v15 = 171;
      goto LABEL_30;
    }
    v3[7] = NumActivePorts;
    goto LABEL_18;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
    goto LABEL_6;
  v15 = 170;
LABEL_30:
  WPP_SF_d(v14[7], v15, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, PortPtrList);
LABEL_6:
  if ( v3 )
  {
    for ( i = 0; i < NumActivePorts; ++i )
      FreeMSMSecPeerState((struct MSMSEC_PEER_STATE **)&v3[2 * i + 8]);
  }
  FreeMSMSecMemory(&v19);
LABEL_19:
  if ( v18.Flink != &v18 )
    DerefPortsAndFreePortPtrListHelper(&v18, 1);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
      WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v13, *((_DWORD *)a1 + 624), (__int64)"<<< Unlocking <<<");
    ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrGetIntfState", 2744);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 172, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180008e4c  push    rbp
0x180008e4e  push    rbx
0x180008e4f  push    rsi
0x180008e50  push    rdi
0x180008e51  push    r12
0x180008e53  push    r13
0x180008e55  push    r14
0x180008e57  push    r15
0x180008e59  mov     rbp, rsp
0x180008e5c  sub     rsp, 48h
0x180008e60  xor     edi, edi
0x180008e62  xorps   xmm0, xmm0
0x180008e65  mov     [rbp+arg_18], rdi
0x180008e69  mov     r12, r8
0x180008e6c  movups  xmmword ptr [rbp+var_18.Flink], xmm0
0x180008e70  mov     r15d, edx
0x180008e73  mov     rsi, rcx
0x180008e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e7d  lea     rax, WPP_GLOBAL_Control
0x180008e84  cmp     rcx, rax
0x180008e87  jnz     loc_180008F5B
0x180008e8d  lea     rax, [rbp+var_18]
0x180008e91  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180008e94  mov     [rbp+var_18.Blink], rax
0x180008e98  lea     rax, [rbp+var_18]
0x180008e9c  mov     [rbp+var_18.Flink], rax
0x180008ea0  call    ?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)
0x180008ea5  mov     ebx, eax
0x180008ea7  test    eax, eax
0x180008ea9  jnz     loc_180008F32
0x180008eaf  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180008eb2  lea     r13d, [rax+1]
0x180008eb6  call    ?GetNumActivePorts@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; GetNumActivePorts(MSMSEC_INTF_CONTEXT *)
0x180008ebb  mov     ecx, r15d
0x180008ebe  mov     r14d, eax
0x180008ec1  neg     ecx
0x180008ec3  sbb     ecx, ecx
0x180008ec5  lea     edx, ds:0[rax*8]
0x180008ecc  and     ecx, edx
0x180008ece  lea     rdx, [rbp+arg_18]
0x180008ed2  add     ecx, 20h ; ' '; dwBytes
0x180008ed5  call    AllocateMSMSecMemory
0x180008eda  mov     ebx, eax
0x180008edc  test    eax, eax
0x180008ede  jz      loc_180008F82
0x180008ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eeb  lea     r12, WPP_GLOBAL_Control
0x180008ef2  cmp     rcx, r12
0x180008ef5  jnz     loc_1800090BB
0x180008efb  mov     rdi, [rbp+arg_18]
0x180008eff  test    rdi, rdi
0x180008f02  jz      short loc_180008F24
0x180008f04  xor     r15d, r15d
0x180008f07  test    r14d, r14d
0x180008f0a  jz      short loc_180008F24
0x180008f0c  mov     eax, r15d
0x180008f0f  add     rax, 4
0x180008f13  lea     rcx, [rdi+rax*8]; struct MSMSEC_PEER_STATE **
0x180008f17  call    ?FreeMSMSecPeerState@@YAXPEAPEAUMSMSEC_PEER_STATE@@@Z; FreeMSMSecPeerState(MSMSEC_PEER_STATE * *)
0x180008f1c  inc     r15d
0x180008f1f  cmp     r15d, r14d
0x180008f22  jb      short loc_180008F0C
0x180008f24  lea     rcx, [rbp+arg_18]
0x180008f28  call    FreeMSMSecMemory
0x180008f2d  jmp     loc_180009002
0x180008f32  xor     r13d, r13d
0x180008f35  xor     r14d, r14d
0x180008f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f3f  lea     r12, WPP_GLOBAL_Control
0x180008f46  cmp     rcx, r12
0x180008f49  jz      short loc_180008EFF
0x180008f4b  test    byte ptr [rcx+44h], 1
0x180008f4f  jz      short loc_180008EFF
0x180008f51  mov     edx, 0A8h
0x180008f56  jmp     loc_1800090A3
0x180008f5b  test    dword ptr [rcx+44h], 100h
0x180008f62  jz      loc_180008E8D
0x180008f68  mov     rcx, [rcx+38h]
0x180008f6c  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180008f73  mov     edx, 0A7h
0x180008f78  call    WPP_SF_
0x180008f7d  jmp     loc_180008E8D
0x180008f82  mov     rax, [rsi+0AE0h]
0x180008f89  mov     rdi, [rbp+arg_18]
0x180008f8d  test    rax, rax
0x180008f90  jz      short loc_180008FAB
0x180008f92  mov     rax, [rax+18h]
0x180008f96  mov     ecx, [rax]
0x180008f98  mov     [rdi], ecx
0x180008f9a  mov     rax, [rsi+0AE0h]
0x180008fa1  mov     rcx, [rax+18h]
0x180008fa5  mov     eax, [rcx+4]
0x180008fa8  mov     [rdi+4], eax
0x180008fab  mov     eax, [rsi+938h]
0x180008fb1  mov     [rdi+8], eax
0x180008fb4  movzx   eax, word ptr [rsi+93Ch]
0x180008fbb  mov     [rdi+0Ch], ax
0x180008fbf  mov     ecx, [rsi+0AA4h]
0x180008fc5  call    ?MapIntfSecState@@YA?AW4MSMSEC_ADAPTER_STATE@@W4MSMSEC_INTF_SEC_STATE@@@Z; MapIntfSecState(MSMSEC_INTF_SEC_STATE)
0x180008fca  mov     [rdi+10h], eax
0x180008fcd  mov     eax, [rsi+0D00h]
0x180008fd3  mov     [rdi+14h], eax
0x180008fd6  mov     eax, [rsi+0D04h]
0x180008fdc  mov     [rdi+18h], eax
0x180008fdf  mov     dword ptr [rdi+1Ch], 0
0x180008fe6  test    r14d, r14d
0x180008fe9  jnz     loc_1800090E2
0x180008fef  mov     [r12], rdi
0x180008ff3  lea     r12, WPP_GLOBAL_Control
0x180008ffa  test    ebx, ebx
0x180008ffc  jnz     loc_180008EFF
0x180009002  lea     rax, [rbp+var_18]
0x180009006  cmp     [rbp+var_18.Flink], rax
0x18000900a  jz      short loc_18000901A
0x18000900c  mov     edx, 1; int
0x180009011  lea     rcx, [rbp+var_18]; struct _LIST_ENTRY *
0x180009015  call    ?DerefPortsAndFreePortPtrListHelper@@YAXPEAU_LIST_ENTRY@@H@Z; DerefPortsAndFreePortPtrListHelper(_LIST_ENTRY *,int)
0x18000901a  test    r13d, r13d
0x18000901d  jz      short loc_18000905B
0x18000901f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009026  cmp     rcx, r12
0x180009029  jz      short loc_180009038
0x18000902b  test    dword ptr [rcx+44h], 100h
0x180009032  jnz     loc_1800091AF
0x180009038  lea     rdx, [rsi+9D0h]
0x18000903f  mov     r9d, 0AB8h
0x180009045  lea     r8, aSecmgrgetintfs; "SecMgrGetIntfState"
0x18000904c  mov     rcx, rsi
0x18000904f  call    cs:__imp_ReleaseWriteLock
0x180009056  nop     dword ptr [rax+rax+00h]
0x18000905b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009062  cmp     rcx, r12
0x180009065  jnz     short loc_18000907B
0x180009067  mov     eax, ebx
0x180009069  add     rsp, 48h
0x18000906d  pop     r15
0x18000906f  pop     r14
0x180009071  pop     r13
0x180009073  pop     r12
0x180009075  pop     rdi
0x180009076  pop     rsi
0x180009077  pop     rbx
0x180009078  pop     rbp
0x180009079  retn
0x18000907b  test    dword ptr [rcx+44h], 100h
0x180009082  jz      short loc_180009067
0x180009084  mov     rcx, [rcx+38h]
0x180009088  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18000908f  mov     edx, 0ACh
0x180009094  mov     r9d, ebx
0x180009097  call    WPP_SF_d
0x18000909c  jmp     short loc_180009067
0x18000909e  mov     edx, 0ABh
0x1800090a3  mov     rcx, [rcx+38h]
0x1800090a7  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800090ae  mov     r9d, eax
0x1800090b1  call    WPP_SF_d
0x1800090b6  jmp     loc_180008EFF
0x1800090bb  test    [rcx+44h], r13b
0x1800090bf  jz      loc_180008EFB
0x1800090c5  mov     rcx, [rcx+38h]
0x1800090c9  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800090d0  mov     edx, 0A9h
0x1800090d5  mov     r9d, eax
0x1800090d8  call    WPP_SF_d
0x1800090dd  jmp     loc_180008EFB
0x1800090e2  test    r15d, r15d
0x1800090e5  jz      loc_180008FEF
0x1800090eb  lea     rcx, [rsi+0A70h]
0x1800090f2  mov     rdx, rcx; struct _LIST_ENTRY *
0x1800090f5  lea     r8, [rbp+var_18]; struct _LIST_ENTRY *
0x1800090f9  mov     rcx, [rcx]; struct _LIST_ENTRY *
0x1800090fc  call    ?SecMgrRefPortsAndGetPortPtrList@@YAKPEAU_LIST_ENTRY@@00@Z; SecMgrRefPortsAndGetPortPtrList(_LIST_ENTRY *,_LIST_ENTRY *,_LIST_ENTRY *)
0x180009101  mov     ebx, eax
0x180009103  test    eax, eax
0x180009105  jz      short loc_180009132
0x180009107  mov     rcx, cs:WPP_GLOBAL_Control
0x18000910e  lea     r12, WPP_GLOBAL_Control
0x180009115  cmp     rcx, r12
0x180009118  jz      loc_180008EFF
0x18000911e  test    [rcx+44h], r13b
0x180009122  jz      loc_180008EFF
0x180009128  mov     edx, 0AAh
0x18000912d  jmp     loc_1800090A3
0x180009132  mov     ecx, [rsi+9C0h]; unsigned int
0x180009138  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18000913f  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180009144  lea     rdx, [rsi+9D0h]
0x18000914b  mov     r9d, 0A93h
0x180009151  lea     r8, aSecmgrgetintfs; "SecMgrGetIntfState"
0x180009158  mov     rcx, rsi
0x18000915b  call    cs:__imp_ReleaseWriteLock
0x180009162  nop     dword ptr [rax+rax+00h]
0x180009167  lea     r8, [rdi+20h]; struct MSMSEC_PEER_STATE **
0x18000916b  mov     edx, r14d; unsigned int
0x18000916e  lea     rcx, [rbp+var_18]; struct _LIST_ENTRY *
0x180009172  xor     r13d, r13d
0x180009175  call    ?SecMgrGetPortListState@@YAKPEAU_LIST_ENTRY@@KPEAPEAUMSMSEC_PEER_STATE@@@Z; SecMgrGetPortListState(_LIST_ENTRY *,ulong,MSMSEC_PEER_STATE * *)
0x18000917a  mov     ebx, eax
0x18000917c  test    eax, eax
0x18000917e  jz      short loc_1800091A6
0x180009180  mov     rcx, cs:WPP_GLOBAL_Control
0x180009187  lea     r12, WPP_GLOBAL_Control
0x18000918e  cmp     rcx, r12
0x180009191  jz      loc_180008EFF
0x180009197  test    byte ptr [rcx+44h], 1
0x18000919b  jz      loc_180008EFF
0x1800091a1  jmp     loc_18000909E
0x1800091a6  mov     [rdi+1Ch], r14d
0x1800091aa  jmp     loc_180008FEF
0x1800091af  mov     r9d, [rsi+9C0h]
0x1800091b6  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x1800091bd  mov     rcx, [rcx+38h]
0x1800091c1  mov     edx, 0Bh
0x1800091c6  mov     [rsp+48h+var_28], rax
0x1800091cb  call    WPP_SF_Ls
0x1800091d0  jmp     loc_180009038
```
