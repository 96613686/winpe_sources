# MSMSecQueryPeerState

- ea: `0x180053c30`
- end: `0x1800540bb`
- name: `MSMSecQueryPeerState`
- size: `1163`
- prototype: `__int64 __fastcall(void *, unsigned __int8 (*)[6])`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000b3d4`
- `0x1800125b0`
- `0x180013600`
- `0x180013bc0`
- `0x1800148d0`
- `0x1800163e0`
- `0x1800169c0`
- `0x180018d40`
- `0x18002abec`
- `0x18002b3f8`
- `0x18002bb08`
- `0x18003346c`
- `0x180034924`
- `0x180053c30`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180053d29`
- `MobileNetworking!ReleaseWriteLock` at `0x180053eef`
- `MobileNetworking!ReleaseWriteLock` at `0x180053fd1`
- `MobileNetworking!ReleaseWriteLock` at `0x180053d29`
- `MobileNetworking!ReleaseWriteLock` at `0x180053eef`
- `MobileNetworking!ReleaseWriteLock` at `0x180053fd1`

## pseudocode

```c
__int64 __fastcall MSMSecQueryPeerState(void *a1, unsigned __int8 (*a2)[6], struct MSMSEC_PEER_STATE **a3)
{
  unsigned int *v4; // rdi
  struct MSMSEC_PORT_CONTEXT *v5; // rsi
  int v6; // r13d
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int v11; // r14d
  int v12; // r15d
  unsigned int v13; // eax
  PVOID *v14; // rbx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int PortState; // eax
  int v19; // [rsp+54h] [rbp-24h]
  struct MSMSEC_INTF_CONTEXT *v20; // [rsp+58h] [rbp-20h] BYREF
  struct MSMSEC_PORT_CONTEXT *v21; // [rsp+60h] [rbp-18h] BYREF
  struct MSMSEC_PEER_STATE *v22[2]; // [rsp+68h] [rbp-10h] BYREF

  v4 = 0;
  v20 = 0;
  v5 = 0;
  v21 = 0;
  v6 = 0;
  v19 = 0;
  v22[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 195, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v9 = IncThreadCountAndCheckInitializedEx("MSMSecQueryPeerState", 1721);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 196, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v9);
    goto LABEL_8;
  }
  if ( a1 && a2 && a3 && !*a3 )
  {
    v13 = SecMgrValidateRefAndLockAdapter(a1, &v20);
    v10 = v13;
    if ( !v13 )
    {
      v19 = 1;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      v4 = (unsigned int *)v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        {
          WPP_SF_Lq(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            199,
            &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            *((unsigned int *)v20 + 624),
            a1);
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 68) & 0x20) != 0 )
          WPP_SF_LDDDDDD(
            v14[7],
            200,
            &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            v4[624],
            (*a2)[0],
            (*a2)[1],
            (*a2)[2],
            (*a2)[3],
            (*a2)[4],
            (*a2)[5]);
      }
      v15 = SecMgrValidateAndRefPort((struct MSMSEC_INTF_CONTEXT *)v4, a2, &v21);
      v10 = v15;
      if ( v15 )
      {
        v6 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 201, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v15);
        v11 = 0;
        v5 = v21;
        v12 = 0;
      }
      else
      {
        v12 = 1;
        TraceAdapterId(v4[624], "<<< Unlocking <<<");
        ReleaseWriteLock(v4, v4 + 628, "MSMSecQueryPeerState", 1754);
        v5 = v21;
        v16 = SecMgrLockAndCheckPortActive(v21);
        v10 = v16;
        if ( v16 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 202, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v16);
          v11 = 0;
        }
        else
        {
          PortState = SecMgrGetPortState(v5, v22);
          v10 = PortState;
          if ( !PortState )
          {
            *a3 = v22[0];
LABEL_45:
            TracePortId(*((_DWORD *)v5 + 78), "<<< Unlocking <<<");
            ReleaseWriteLock(v5, (char *)v5 + 320, "MSMSecQueryPeerState", 1780);
LABEL_46:
            if ( v12 )
            {
              TracePortId(*((_DWORD *)v5 + 78), "<<< Derefing <<<");
              SecMgrDerefPortEx(v5, "MSMSecQueryPeerState", 1784);
            }
            if ( v19 )
            {
              TraceAdapterId(v4[624], "<<< Derefing <<<");
              SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v4, "MSMSecQueryPeerState", 1788);
            }
            goto LABEL_53;
          }
          v11 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              203,
              &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
              PortState);
        }
      }
LABEL_9:
      if ( v22[0] )
        FreeMSMSecPeerState(v22);
      if ( v6 )
      {
        TraceAdapterId(v4[624], "<<< Unlocking <<<");
        ReleaseWriteLock(v4, v4 + 628, "MSMSecQueryPeerState", 1776);
      }
      if ( !v11 )
        goto LABEL_46;
      goto LABEL_45;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 198, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v13);
    v4 = (unsigned int *)v20;
LABEL_8:
    v11 = 0;
    v12 = 0;
    goto LABEL_9;
  }
  v10 = 87;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 197, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
LABEL_53:
  DecThreadCountEx("MSMSecQueryPeerState", 1790);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 204, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180053c30  push    rbp
0x180053c32  push    rbx
0x180053c33  push    rsi
0x180053c34  push    rdi
0x180053c35  push    r12
0x180053c37  push    r13
0x180053c39  push    r14
0x180053c3b  push    r15
0x180053c3d  mov     rbp, rsp
0x180053c40  sub     rsp, 78h
0x180053c44  xor     eax, eax
0x180053c46  mov     r12, r8
0x180053c49  mov     edi, eax
0x180053c4b  mov     [rbp+var_20], rax
0x180053c4f  mov     esi, eax
0x180053c51  mov     [rbp+var_18], rax
0x180053c55  mov     r13d, eax
0x180053c58  mov     [rbp+var_24], eax
0x180053c5b  mov     [rbp+arg_18], eax
0x180053c5e  mov     r14, rdx
0x180053c61  mov     [rbp+var_10], rax
0x180053c65  mov     r15, rcx
0x180053c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180053c6f  lea     rax, WPP_GLOBAL_Control
0x180053c76  cmp     rcx, rax
0x180053c79  jz      short loc_180053C99
0x180053c7b  test    dword ptr [rcx+44h], 100h
0x180053c82  jz      short loc_180053C99
0x180053c84  mov     rcx, [rcx+38h]
0x180053c88  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053c8f  mov     edx, 0C3h
0x180053c94  call    WPP_SF_
0x180053c99  mov     edx, 6B9h; int
0x180053c9e  lea     rcx, aMsmsecquerypee_0; "MSMSecQueryPeerState"
0x180053ca5  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180053caa  mov     ebx, eax
0x180053cac  test    eax, eax
0x180053cae  jz      loc_180053D43
0x180053cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180053cbb  lea     r12, WPP_GLOBAL_Control
0x180053cc2  cmp     rcx, r12
0x180053cc5  jz      short loc_180053CE5
0x180053cc7  test    byte ptr [rcx+44h], 1
0x180053ccb  jz      short loc_180053CE5
0x180053ccd  mov     rcx, [rcx+38h]
0x180053cd1  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053cd8  mov     edx, 0C4h
0x180053cdd  mov     r9d, eax
0x180053ce0  call    WPP_SF_d
0x180053ce5  mov     r14d, esi
0x180053ce8  mov     r15d, esi
0x180053ceb  cmp     [rbp+var_10], 0
0x180053cf0  jz      short loc_180053CFB
0x180053cf2  lea     rcx, [rbp+var_10]; struct MSMSEC_PEER_STATE **
0x180053cf6  call    ?FreeMSMSecPeerState@@YAXPEAPEAUMSMSEC_PEER_STATE@@@Z; FreeMSMSecPeerState(MSMSEC_PEER_STATE * *)
0x180053cfb  test    r13d, r13d
0x180053cfe  jz      short loc_180053D35
0x180053d00  mov     ecx, [rdi+9C0h]; unsigned int
0x180053d06  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180053d0d  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180053d12  lea     rdx, [rdi+9D0h]
0x180053d19  mov     r9d, 6F0h
0x180053d1f  lea     r8, aMsmsecquerypee_0; "MSMSecQueryPeerState"
0x180053d26  mov     rcx, rdi
0x180053d29  call    cs:__imp_ReleaseWriteLock
0x180053d30  nop     dword ptr [rax+rax+00h]
0x180053d35  test    r14d, r14d
0x180053d38  jz      loc_180053FDD
0x180053d3e  jmp     loc_180053FA8
0x180053d43  test    r15, r15
0x180053d46  jz      loc_180054038
0x180053d4c  test    r14, r14
0x180053d4f  jz      loc_180054038
0x180053d55  test    r12, r12
0x180053d58  jz      loc_180054038
0x180053d5e  cmp     [r12], rsi
0x180053d62  jnz     loc_180054038
0x180053d68  lea     rdx, [rbp+var_20]; struct MSMSEC_INTF_CONTEXT **
0x180053d6c  mov     rcx, r15; void *
0x180053d6f  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180053d74  mov     ebx, eax
0x180053d76  test    eax, eax
0x180053d78  jz      short loc_180053DB4
0x180053d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d81  lea     r12, WPP_GLOBAL_Control
0x180053d88  cmp     rcx, r12
0x180053d8b  jz      short loc_180053DAB
0x180053d8d  test    byte ptr [rcx+44h], 1
0x180053d91  jz      short loc_180053DAB
0x180053d93  mov     rcx, [rcx+38h]
0x180053d97  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053d9e  mov     edx, 0C6h
0x180053da3  mov     r9d, eax
0x180053da6  call    WPP_SF_d
0x180053dab  mov     rdi, [rbp+var_20]
0x180053daf  jmp     loc_180053CE5
0x180053db4  mov     [rbp+var_24], 1
0x180053dbb  mov     rbx, cs:WPP_GLOBAL_Control
0x180053dc2  lea     rsi, WPP_GLOBAL_Control
0x180053dc9  mov     rdi, [rbp+var_20]
0x180053dcd  cmp     rbx, rsi
0x180053dd0  jz      loc_180053E64
0x180053dd6  test    byte ptr [rbx+44h], 20h
0x180053dda  jz      short loc_180053E04
0x180053ddc  mov     r9d, [rdi+9C0h]
0x180053de3  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053dea  mov     rcx, [rbx+38h]
0x180053dee  mov     edx, 0C7h
0x180053df3  mov     [rsp+78h+var_58], r15
0x180053df8  call    WPP_SF_Lq
0x180053dfd  mov     rbx, cs:WPP_GLOBAL_Control
0x180053e04  cmp     rbx, rsi
0x180053e07  jz      short loc_180053E64
0x180053e09  test    byte ptr [rbx+44h], 20h
0x180053e0d  jz      short loc_180053E64
0x180053e0f  movzx   ecx, byte ptr [r14+4]
0x180053e14  mov     edx, 0C8h
0x180053e19  movzx   r8d, byte ptr [r14+3]
0x180053e1e  movzx   r9d, byte ptr [r14+2]
0x180053e23  movzx   eax, byte ptr [r14+5]
0x180053e28  movzx   r10d, byte ptr [r14+1]
0x180053e2d  movzx   r11d, byte ptr [r14]
0x180053e31  mov     [rsp+78h+var_30], eax
0x180053e35  mov     [rsp+78h+var_38], ecx
0x180053e39  mov     rcx, [rbx+38h]
0x180053e3d  mov     [rsp+78h+var_40], r8d
0x180053e42  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053e49  mov     [rsp+78h+var_48], r9d
0x180053e4e  mov     r9d, [rdi+9C0h]
0x180053e55  mov     [rsp+78h+var_50], r10d
0x180053e5a  mov     dword ptr [rsp+78h+var_58], r11d
0x180053e5f  call    WPP_SF_LDDDDDD
0x180053e64  lea     r8, [rbp+var_18]; struct MSMSEC_PORT_CONTEXT **
0x180053e68  mov     rdx, r14; unsigned __int8 (*)[6]
0x180053e6b  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180053e6e  call    ?SecMgrValidateAndRefPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrValidateAndRefPort(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x180053e73  mov     ebx, eax
0x180053e75  test    eax, eax
0x180053e77  jz      short loc_180053EC0
0x180053e79  mov     r13d, 1
0x180053e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e86  cmp     rcx, rsi
0x180053e89  jz      short loc_180053EA9
0x180053e8b  test    [rcx+44h], r13b
0x180053e8f  jz      short loc_180053EA9
0x180053e91  mov     rcx, [rcx+38h]
0x180053e95  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053e9c  mov     edx, 0C9h
0x180053ea1  mov     r9d, eax
0x180053ea4  call    WPP_SF_d
0x180053ea9  mov     r14d, [rbp+arg_18]
0x180053ead  lea     r12, WPP_GLOBAL_Control
0x180053eb4  mov     rsi, [rbp+var_18]
0x180053eb8  mov     r15d, r14d
0x180053ebb  jmp     loc_180053CEB
0x180053ec0  mov     ecx, [rdi+9C0h]; unsigned int
0x180053ec6  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180053ecd  mov     r15d, 1
0x180053ed3  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180053ed8  lea     rdx, [rdi+9D0h]
0x180053edf  mov     r9d, 6DAh
0x180053ee5  lea     r8, aMsmsecquerypee_0; "MSMSecQueryPeerState"
0x180053eec  mov     rcx, rdi
0x180053eef  call    cs:__imp_ReleaseWriteLock
0x180053ef6  nop     dword ptr [rax+rax+00h]
0x180053efb  mov     rsi, [rbp+var_18]
0x180053eff  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x180053f02  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x180053f07  mov     ebx, eax
0x180053f09  test    eax, eax
0x180053f0b  jz      short loc_180053F46
0x180053f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f14  lea     r12, WPP_GLOBAL_Control
0x180053f1b  cmp     rcx, r12
0x180053f1e  jz      short loc_180053F3E
0x180053f20  test    [rcx+44h], r15b
0x180053f24  jz      short loc_180053F3E
0x180053f26  mov     rcx, [rcx+38h]
0x180053f2a  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053f31  mov     edx, 0CAh
0x180053f36  mov     r9d, eax
0x180053f39  call    WPP_SF_d
0x180053f3e  mov     r14d, r13d
0x180053f41  jmp     loc_180053CEB
0x180053f46  lea     rdx, [rbp+var_10]; struct MSMSEC_PEER_STATE **
0x180053f4a  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x180053f4d  call    ?SecMgrGetPortState@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAPEAUMSMSEC_PEER_STATE@@@Z; SecMgrGetPortState(MSMSEC_PORT_CONTEXT *,MSMSEC_PEER_STATE * *)
0x180053f52  mov     ebx, eax
0x180053f54  test    eax, eax
0x180053f56  jz      short loc_180053F99
0x180053f58  mov     r14d, r15d
0x180053f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f62  lea     r12, WPP_GLOBAL_Control
0x180053f69  cmp     rcx, r12
0x180053f6c  jz      loc_180053CEB
0x180053f72  test    [rcx+44h], r14b
0x180053f76  jz      loc_180053CEB
0x180053f7c  mov     rcx, [rcx+38h]
0x180053f80  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180053f87  mov     edx, 0CBh
0x180053f8c  mov     r9d, eax
0x180053f8f  call    WPP_SF_d
0x180053f94  jmp     loc_180053CEB
0x180053f99  mov     rax, [rbp+var_10]
0x180053f9d  mov     [r12], rax
0x180053fa1  lea     r12, WPP_GLOBAL_Control
0x180053fa8  mov     ecx, [rsi+138h]; unsigned int
0x180053fae  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180053fb5  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180053fba  lea     rdx, [rsi+140h]
0x180053fc1  mov     r9d, 6F4h
0x180053fc7  lea     r8, aMsmsecquerypee_0; "MSMSecQueryPeerState"
0x180053fce  mov     rcx, rsi
0x180053fd1  call    cs:__imp_ReleaseWriteLock
0x180053fd8  nop     dword ptr [rax+rax+00h]
0x180053fdd  test    r15d, r15d
0x180053fe0  jz      short loc_180054009
0x180053fe2  mov     ecx, [rsi+138h]; unsigned int
0x180053fe8  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180053fef  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180053ff4  mov     r8d, 6F8h; int
0x180053ffa  lea     rdx, aMsmsecquerypee_0; "MSMSecQueryPeerState"
0x180054001  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x180054004  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180054009  cmp     [rbp+var_24], 0
0x18005400d  jz      short loc_180054069
0x18005400f  mov     ecx, [rdi+9C0h]; unsigned int
0x180054015  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18005401c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180054021  mov     r8d, 6FCh; int
0x180054027  lea     rdx, aMsmsecquerypee_0; "MSMSecQueryPeerState"
0x18005402e  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180054031  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180054036  jmp     short loc_180054069
0x180054038  mov     ebx, 57h ; 'W'
0x18005403d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054044  lea     r12, WPP_GLOBAL_Control
0x18005404b  cmp     rcx, r12
0x18005404e  jz      short loc_180054069
0x180054050  test    byte ptr [rcx+44h], 1
0x180054054  jz      short loc_180054069
0x180054056  mov     rcx, [rcx+38h]
0x18005405a  lea     edx, [rbx+6Eh]
0x18005405d  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180054064  call    WPP_SF_
0x180054069  mov     edx, 6FEh; int
0x18005406e  lea     rcx, aMsmsecquerypee_0; "MSMSecQueryPeerState"
0x180054075  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x18005407a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054081  cmp     rcx, r12
0x180054084  jz      short loc_1800540A7
0x180054086  test    dword ptr [rcx+44h], 100h
0x18005408d  jz      short loc_1800540A7
0x18005408f  mov     rcx, [rcx+38h]
0x180054093  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x18005409a  mov     edx, 0CCh
0x18005409f  mov     r9d, ebx
0x1800540a2  call    WPP_SF_d
0x1800540a7  mov     eax, ebx
0x1800540a9  add     rsp, 78h
0x1800540ad  pop     r15
0x1800540af  pop     r14
0x1800540b1  pop     r13
0x1800540b3  pop     r12
0x1800540b5  pop     rdi
0x1800540b6  pop     rsi
0x1800540b7  pop     rbx
0x1800540b8  pop     rbp
0x1800540b9  retn
```
