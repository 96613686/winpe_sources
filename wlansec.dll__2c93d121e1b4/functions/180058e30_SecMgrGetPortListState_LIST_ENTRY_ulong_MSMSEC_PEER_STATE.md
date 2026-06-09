# SecMgrGetPortListState(_LIST_ENTRY *,ulong,MSMSEC_PEER_STATE * *)

- ea: `0x180058e30`
- end: `0x180058fc0`
- name: `?SecMgrGetPortListState@@YAKPEAU_LIST_ENTRY@@KPEAPEAUMSMSEC_PEER_STATE@@@Z`
- size: `400`
- prototype: `unsigned int __fastcall(struct _LIST_ENTRY *, unsigned int, struct MSMSEC_PEER_STATE **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180008e4c`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000b3d4`
- `0x18002bb08`
- `0x180034924`
- `0x180058e30`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180058f06`
- `MobileNetworking!ReleaseWriteLock` at `0x180058f06`
- `MobileNetworking!AcquireWriteLock` at `0x180058ec6`
- `MobileNetworking!AcquireWriteLock` at `0x180058ec6`

## pseudocode

```c
__int64 __fastcall SecMgrGetPortListState(struct _LIST_ENTRY *a1, unsigned int a2, struct MSMSEC_PEER_STATE **a3)
{
  unsigned int PortState; // r14d
  struct _LIST_ENTRY *Flink; // rsi
  __int64 i; // rbp
  struct _LIST_ENTRY *v9; // rdi
  int v10; // r8d
  PVOID *v11; // rcx
  __int64 v12; // rbx

  PortState = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 164, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  Flink = a1->Flink;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a2 || Flink == a1 )
      goto LABEL_15;
    v9 = Flink[1].Flink;
    TracePortId((unsigned int)v9[19].Blink, ">>> Locking >>>");
    AcquireWriteLock(v9, &v9[20], "SecMgrGetPortListState", 2544);
    PortState = SecMgrGetPortState((struct MSMSEC_PORT_CONTEXT *)v9, &a3[i], v10);
    TracePortId((unsigned int)v9[19].Blink, "<<< Unlocking <<<");
    ReleaseWriteLock(v9, &v9[20], "SecMgrGetPortListState", 2546);
    if ( PortState )
      break;
    Flink = Flink->Flink;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 165, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, PortState);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    v12 = 0;
    if ( a2 )
    {
      do
      {
        FreeMSMSecPeerState(&a3[v12]);
        v12 = (unsigned int)(v12 + 1);
      }
      while ( (unsigned int)v12 < a2 );
LABEL_15:
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 166, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, PortState);
  return PortState;
}

```

## disassembly

```asm
0x180058e30  push    rbx
0x180058e32  push    rbp
0x180058e33  push    rsi
0x180058e34  push    rdi
0x180058e35  push    r12
0x180058e37  push    r13
0x180058e39  push    r14
0x180058e3b  push    r15
0x180058e3d  sub     rsp, 28h
0x180058e41  mov     r12, r8
0x180058e44  mov     r15d, edx
0x180058e47  mov     r13, rcx
0x180058e4a  xor     r14d, r14d
0x180058e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180058e54  lea     rax, WPP_GLOBAL_Control
0x180058e5b  cmp     rcx, rax
0x180058e5e  jz      short loc_180058E7E
0x180058e60  test    dword ptr [rcx+44h], 100h
0x180058e67  jz      short loc_180058E7E
0x180058e69  mov     rcx, [rcx+38h]
0x180058e6d  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180058e74  mov     edx, 0A4h
0x180058e79  call    WPP_SF_
0x180058e7e  mov     rsi, [r13+0]
0x180058e82  xor     ebp, ebp
0x180058e84  cmp     ebp, r15d
0x180058e87  jnb     loc_180058F77
0x180058e8d  cmp     rsi, r13
0x180058e90  jz      loc_180058F77
0x180058e96  mov     rdi, [rsi+10h]
0x180058e9a  lea     rdx, aLocking; ">>> Locking >>>"
0x180058ea1  mov     ecx, [rdi+138h]; unsigned int
0x180058ea7  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180058eac  lea     rbx, [rdi+140h]
0x180058eb3  mov     r9d, 9F0h
0x180058eb9  mov     rdx, rbx
0x180058ebc  lea     r8, aSecmgrgetportl; "SecMgrGetPortListState"
0x180058ec3  mov     rcx, rdi
0x180058ec6  call    cs:__imp_AcquireWriteLock
0x180058ecd  nop     dword ptr [rax+rax+00h]
0x180058ed2  lea     rdx, [r12+rbp*8]; struct MSMSEC_PEER_STATE **
0x180058ed6  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180058ed9  call    ?SecMgrGetPortState@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAPEAUMSMSEC_PEER_STATE@@@Z; SecMgrGetPortState(MSMSEC_PORT_CONTEXT *,MSMSEC_PEER_STATE * *)
0x180058ede  mov     ecx, [rdi+138h]; unsigned int
0x180058ee4  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180058eeb  mov     r14d, eax
0x180058eee  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180058ef3  mov     r9d, 9F2h
0x180058ef9  lea     r8, aSecmgrgetportl; "SecMgrGetPortListState"
0x180058f00  mov     rdx, rbx
0x180058f03  mov     rcx, rdi
0x180058f06  call    cs:__imp_ReleaseWriteLock
0x180058f0d  nop     dword ptr [rax+rax+00h]
0x180058f12  test    r14d, r14d
0x180058f15  jnz     short loc_180058F21
0x180058f17  mov     rsi, [rsi]
0x180058f1a  inc     ebp
0x180058f1c  jmp     loc_180058E84
0x180058f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f28  lea     rdi, WPP_GLOBAL_Control
0x180058f2f  cmp     rcx, rdi
0x180058f32  jz      short loc_180058F59
0x180058f34  test    byte ptr [rcx+44h], 1
0x180058f38  jz      short loc_180058F59
0x180058f3a  mov     rcx, [rcx+38h]
0x180058f3e  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180058f45  mov     edx, 0A5h
0x180058f4a  mov     r9d, r14d
0x180058f4d  call    WPP_SF_d
0x180058f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f59  test    r12, r12
0x180058f5c  jz      short loc_180058F85
0x180058f5e  xor     ebx, ebx
0x180058f60  test    r15d, r15d
0x180058f63  jz      short loc_180058F85
0x180058f65  lea     rcx, [r12+rbx*8]; struct MSMSEC_PEER_STATE **
0x180058f69  call    ?FreeMSMSecPeerState@@YAXPEAPEAUMSMSEC_PEER_STATE@@@Z; FreeMSMSecPeerState(MSMSEC_PEER_STATE * *)
0x180058f6e  inc     ebx
0x180058f70  cmp     ebx, r15d
0x180058f73  jb      short loc_180058F65
0x180058f75  jmp     short loc_180058F7E
0x180058f77  lea     rdi, WPP_GLOBAL_Control
0x180058f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058f85  cmp     rcx, rdi
0x180058f88  jz      short loc_180058FAB
0x180058f8a  test    dword ptr [rcx+44h], 100h
0x180058f91  jz      short loc_180058FAB
0x180058f93  mov     rcx, [rcx+38h]
0x180058f97  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180058f9e  mov     edx, 0A6h
0x180058fa3  mov     r9d, r14d
0x180058fa6  call    WPP_SF_d
0x180058fab  mov     eax, r14d
0x180058fae  add     rsp, 28h
0x180058fb2  pop     r15
0x180058fb4  pop     r14
0x180058fb6  pop     r13
0x180058fb8  pop     r12
0x180058fba  pop     rdi
0x180058fbb  pop     rsi
0x180058fbc  pop     rbp
0x180058fbd  pop     rbx
0x180058fbe  retn
```
