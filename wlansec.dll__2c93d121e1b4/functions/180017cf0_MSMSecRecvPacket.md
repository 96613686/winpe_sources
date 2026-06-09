# MSMSecRecvPacket

- ea: `0x180017cf0`
- end: `0x1800183bc`
- name: `MSMSecRecvPacket`
- size: `1740`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x1800125b0`
- `0x180013600`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x180016a08`
- `0x180017cf0`
- `0x180018774`
- `0x18002abec`
- `0x18002b3f8`
- `0x18003346c`
- `0x180035898`
- `0x180038034`
- `0x1800396e0`
- `0x18003d350`
- `0x1800558c0`
- `0x180055a38`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x180017d99`
- `WS2_32!__imp_ntohs` at `0x180017d99`
- `MobileNetworking!ReleaseWriteLock` at `0x180017ea4`
- `MobileNetworking!ReleaseWriteLock` at `0x180017f91`
- `MobileNetworking!ReleaseWriteLock` at `0x180018003`
- `MobileNetworking!ReleaseWriteLock` at `0x180017ea4`
- `MobileNetworking!ReleaseWriteLock` at `0x180017f91`
- `MobileNetworking!ReleaseWriteLock` at `0x180018003`

## pseudocode

```c
__int64 __fastcall MSMSecRecvPacket(void *a1, unsigned int a2, unsigned __int8 *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  struct _DOT11_SECURITY_PACKET_HEADER *v8; // rsi
  u_short v9; // ax
  unsigned int v10; // r15d
  int v11; // edx
  PVOID *v12; // rbp
  struct MSMSEC_INTF_CONTEXT *v13; // rdi
  unsigned int v14; // r12d
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // eax
  int v19; // r8d
  _QWORD *v20; // rcx
  struct MSMSEC_PORT_CONTEXT *v22; // rbp
  unsigned int v23; // eax
  int v24; // r8d
  unsigned int v25; // eax
  int v26; // r8d
  PVOID *v27; // rcx
  PVOID *v28; // rcx
  unsigned int v29; // ebx
  __int64 v30; // rdx
  unsigned int v31; // ecx
  __int64 v32; // rax
  unsigned int v33; // r10d
  __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // r11
  __int64 v37; // r8
  char v38; // r10
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  struct MSMSEC_INTF_CONTEXT *v41; // [rsp+60h] [rbp-58h] BYREF
  struct MSMSEC_PORT_CONTEXT *v42; // [rsp+68h] [rbp-50h] BYREF
  struct _DOT11_SECURITY_PACKET_HEADER *v43; // [rsp+D8h] [rbp+20h] BYREF

  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 104, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v6 = IncThreadCountAndCheckInitializedEx("MSMSecRecvPacket", 989);
  v7 = v6;
  if ( v6 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_26;
    v30 = 105;
    goto LABEL_49;
  }
  if ( a1 && a2 && a3 )
  {
    v6 = ValidateDot11SecurityPacket(a2, a3, &v43);
    v7 = v6;
    if ( v6 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_26;
      v30 = 107;
    }
    else
    {
      v8 = v43;
      v9 = ntohs(v43->usEtherType);
      v10 = v9;
      if ( v9 != 0x888E && v9 != 0x88C7 )
      {
        v7 = 87;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 108, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v9);
        goto LABEL_26;
      }
      v6 = SecMgrValidateRefAndLockAdapter(a1, &v41);
      v7 = v6;
      if ( !v6 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        v13 = v41;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
          {
            WPP_SF_Lq(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              110,
              &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
              *((unsigned int *)v41 + 624),
              a1);
            v12 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 0x10) != 0 )
          {
            v29 = a2 - 8;
            if ( a2 <= 8 )
              v29 = 0;
            WPP_SF_LDDDDDDDL(
              v12[7],
              v8->PeerMac[4],
              v8->PeerMac[3],
              *((unsigned int *)v13 + 624),
              v8->PeerMac[0],
              v8->PeerMac[1],
              v8->PeerMac[2],
              v8->PeerMac[3],
              v8->PeerMac[4],
              v8->PeerMac[5],
              v8->usEtherType,
              v29);
          }
        }
        v14 = a2 - 8;
        if ( (byte_1800AED45 & 8) != 0 )
        {
          v31 = a2 - 8;
          if ( a2 <= 8 )
            v31 = 0;
          McTemplateU0qjb6qqq_EventWriteTransfer(
            v31,
            v11,
            *((_DWORD *)v13 + 624),
            (_DWORD)v13 + 32,
            (__int64)v8,
            v8->usEtherType,
            v31);
        }
        if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v13 + 681), 6) )
        {
          v7 = 5023;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v32 = IntfActionStr(6, v15, v16, v17);
            v35 = IntfSecStateStr(v33, v34, v32);
            WPP_SF_SLSL(
              *(_QWORD *)(v36 + 56),
              112,
              (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
              v35,
              v38,
              v37,
              6);
          }
          goto LABEL_20;
        }
        if ( v10 != 34958 )
        {
          if ( v10 != 35015 )
          {
            v7 = 50;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 117, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v10);
            goto LABEL_20;
          }
          v18 = PreAuthValidateAndProcessEapolPacket(
                  (struct MSMSEC_INTF_CONTEXT *)((char *)v13 + 2912),
                  (unsigned __int8 (*)[6])v8,
                  v14,
                  v8->Data);
          v7 = v18;
          if ( !v18
            || (v39 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == &WPP_GLOBAL_Control)
            || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          {
LABEL_20:
            TraceAdapterId(*((_DWORD *)v13 + 624), "<<< Unlocking <<<");
            ReleaseWriteLock(v13, (char *)v13 + 2512, "MSMSecRecvPacket", 1095);
            goto LABEL_21;
          }
          v40 = 116;
LABEL_75:
          WPP_SF_d(v39[7], v40, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v18);
          goto LABEL_20;
        }
        v18 = SecMgrValidateAndRefPort(v13, (unsigned __int8 (*)[6])v8, &v42);
        v7 = v18;
        if ( v18 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_20;
          v40 = 113;
          goto LABEL_75;
        }
        TraceAdapterId(*((_DWORD *)v13 + 624), "<<< Unlocking <<<");
        ReleaseWriteLock(v13, (char *)v13 + 2512, "MSMSecRecvPacket", 1063);
        v22 = v42;
        v23 = SecMgrLockAndCheckPortActive(v42);
        v7 = v23;
        if ( v23 )
        {
          v28 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          {
LABEL_42:
            SecMgrDerefPortEx(v22, "MSMSecRecvPacket", 1103);
LABEL_21:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
              WPP_SF_Ls(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                11,
                v19,
                *((_DWORD *)v13 + 624),
                (__int64)"<<< Derefing <<<");
            SecMgrDerefAdapterEx(v13, "MSMSecRecvPacket", 1107);
            goto LABEL_26;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          {
LABEL_39:
            if ( v28 != &WPP_GLOBAL_Control && (*((_DWORD *)v28 + 17) & 0x100) != 0 )
              WPP_SF_Ls((unsigned int)v28[7], 12, v24, *((_DWORD *)v22 + 78), (__int64)"<<< Derefing <<<");
            goto LABEL_42;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 114, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v23);
LABEL_38:
          v28 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_39;
        }
        v25 = SecMgrValidateAndEnqueueEapolPacket(v22, v14, v8->Data);
        v7 = v25;
        if ( v25 )
        {
          v27 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          {
LABEL_37:
            ReleaseWriteLock(v22, (char *)v22 + 320, "MSMSecRecvPacket", 1099);
            goto LABEL_38;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          {
LABEL_34:
            if ( v27 != &WPP_GLOBAL_Control && (*((_DWORD *)v27 + 17) & 0x100) != 0 )
              WPP_SF_Ls((unsigned int)v27[7], 12, v26, *((_DWORD *)v22 + 78), (__int64)"<<< Unlocking <<<");
            goto LABEL_37;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 115, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v25);
        }
        v27 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_34;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_26;
      v30 = 109;
    }
LABEL_49:
    WPP_SF_d(v20[7], v30, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v6);
    goto LABEL_26;
  }
  v7 = 87;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 106, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
LABEL_26:
  DecThreadCountEx("MSMSecRecvPacket", 1109);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 118, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180017cf0  mov     rax, rsp
0x180017cf3  push    rbx
0x180017cf4  push    rbp
0x180017cf5  push    rsi
0x180017cf6  push    rdi
0x180017cf7  push    r12
0x180017cf9  push    r13
0x180017cfb  push    r14
0x180017cfd  push    r15
0x180017cff  sub     rsp, 78h
0x180017d03  xor     ebp, ebp
0x180017d05  mov     rdi, r8
0x180017d08  mov     [rax-58h], rbp
0x180017d0c  mov     r14d, edx
0x180017d0f  mov     [rax-50h], rbp
0x180017d13  mov     r12, rcx
0x180017d16  mov     [rax+20h], rbp
0x180017d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d21  lea     r13, WPP_GLOBAL_Control
0x180017d28  cmp     rcx, r13
0x180017d2b  jz      short loc_180017D3A
0x180017d2d  test    dword ptr [rcx+44h], 100h
0x180017d34  jnz     loc_1800180BC
0x180017d3a  mov     edx, 3DDh; int
0x180017d3f  lea     rcx, aMsmsecrecvpack_0; "MSMSecRecvPacket"
0x180017d46  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180017d4b  mov     ebx, eax
0x180017d4d  test    eax, eax
0x180017d4f  jnz     loc_180017EE7
0x180017d55  test    r12, r12
0x180017d58  jz      loc_180018385
0x180017d5e  test    r14d, r14d
0x180017d61  jz      loc_180018385
0x180017d67  test    rdi, rdi
0x180017d6a  jz      loc_180018385
0x180017d70  lea     r8, [rsp+0B8h+arg_18]; struct _DOT11_SECURITY_PACKET_HEADER **
0x180017d78  mov     rdx, rdi; unsigned __int8 *
0x180017d7b  mov     ecx, r14d; unsigned int
0x180017d7e  call    ?ValidateDot11SecurityPacket@@YAKKPEAEPEAPEAU_DOT11_SECURITY_PACKET_HEADER@@@Z; ValidateDot11SecurityPacket(ulong,uchar *,_DOT11_SECURITY_PACKET_HEADER * *)
0x180017d83  mov     ebx, eax
0x180017d85  test    eax, eax
0x180017d87  jnz     loc_180018104
0x180017d8d  mov     rsi, [rsp+0B8h+arg_18]
0x180017d95  movzx   ecx, word ptr [rsi+6]; netshort
0x180017d99  call    cs:__imp_ntohs
0x180017da0  nop     dword ptr [rax+rax+00h]
0x180017da5  movzx   r15d, ax
0x180017da9  mov     eax, 888Eh
0x180017dae  cmp     r15w, ax
0x180017db2  jnz     loc_180018125
0x180017db8  lea     rdx, [rsp+0B8h+var_58]; struct MSMSEC_INTF_CONTEXT **
0x180017dbd  mov     rcx, r12; void *
0x180017dc0  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180017dc5  mov     ebx, eax
0x180017dc7  test    eax, eax
0x180017dc9  jnz     loc_18001816E
0x180017dcf  mov     rbp, cs:WPP_GLOBAL_Control
0x180017dd6  mov     rdi, [rsp+0B8h+var_58]
0x180017ddb  cmp     rbp, r13
0x180017dde  jz      short loc_180017E15
0x180017de0  test    byte ptr [rbp+44h], 10h
0x180017de4  jz      short loc_180017E0C
0x180017de6  mov     r9d, [rdi+9C0h]
0x180017ded  lea     edx, [rax+6Eh]
0x180017df0  mov     rcx, [rbp+38h]
0x180017df4  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180017dfb  mov     [rsp+0B8h+var_98], r12
0x180017e00  call    WPP_SF_Lq
0x180017e05  mov     rbp, cs:WPP_GLOBAL_Control
0x180017e0c  cmp     rbp, r13
0x180017e0f  jnz     loc_18001804D
0x180017e15  test    cs:byte_1800AED45, 8
0x180017e1c  lea     r12d, [r14-8]
0x180017e20  jnz     loc_18001818D
0x180017e26  mov     ecx, [rdi+0AA4h]
0x180017e2c  mov     ebp, 6
0x180017e31  mov     edx, ebp
0x180017e33  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180017e38  test    eax, eax
0x180017e3a  jz      loc_1800181BF
0x180017e40  mov     ecx, r15d
0x180017e43  mov     r9d, r15d
0x180017e46  sub     ecx, 888Eh
0x180017e4c  jz      loc_180017F4B
0x180017e52  cmp     ecx, 39h ; '9'
0x180017e55  jnz     loc_180018223
0x180017e5b  lea     r9, [rsi+8]; unsigned __int8 *
0x180017e5f  mov     r8d, r12d; unsigned int
0x180017e62  lea     rcx, [rdi+0B60h]; struct MSMSEC_PREAUTH_CONTEXT *
0x180017e69  mov     rdx, rsi; unsigned __int8 (*)[6]
0x180017e6c  call    ?PreAuthValidateAndProcessEapolPacket@@YAKPEAUMSMSEC_PREAUTH_CONTEXT@@PEAY05EKPEAE@Z; PreAuthValidateAndProcessEapolPacket(MSMSEC_PREAUTH_CONTEXT *,uchar (*)[6],ulong,uchar *)
0x180017e71  mov     ebx, eax
0x180017e73  test    eax, eax
0x180017e75  jnz     loc_18001825A
0x180017e7b  mov     ecx, [rdi+9C0h]; unsigned int
0x180017e81  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180017e88  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180017e8d  lea     rdx, [rdi+9D0h]
0x180017e94  mov     r9d, 447h
0x180017e9a  lea     r8, aMsmsecrecvpack_0; "MSMSecRecvPacket"
0x180017ea1  mov     rcx, rdi
0x180017ea4  call    cs:__imp_ReleaseWriteLock
0x180017eab  nop     dword ptr [rax+rax+00h]
0x180017eb0  lea     rsi, aDerefing; "<<< Derefing <<<"
0x180017eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ebe  cmp     rcx, r13
0x180017ec1  jz      short loc_180017ED0
0x180017ec3  test    dword ptr [rcx+44h], 100h
0x180017eca  jnz     loc_180018366
0x180017ed0  mov     r8d, 453h; int
0x180017ed6  lea     rdx, aMsmsecrecvpack_0; "MSMSecRecvPacket"
0x180017edd  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180017ee0  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180017ee5  jmp     short loc_180017EF7
0x180017ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180017eee  cmp     rcx, r13
0x180017ef1  jnz     loc_1800180D6
0x180017ef7  mov     edx, 455h; int
0x180017efc  lea     rcx, aMsmsecrecvpack_0; "MSMSecRecvPacket"
0x180017f03  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180017f08  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f0f  cmp     rcx, r13
0x180017f12  jnz     short loc_180017F28
0x180017f14  mov     eax, ebx
0x180017f16  add     rsp, 78h
0x180017f1a  pop     r15
0x180017f1c  pop     r14
0x180017f1e  pop     r13
0x180017f20  pop     r12
0x180017f22  pop     rdi
0x180017f23  pop     rsi
0x180017f24  pop     rbp
0x180017f25  pop     rbx
0x180017f26  retn
0x180017f28  test    dword ptr [rcx+44h], 100h
0x180017f2f  jz      short loc_180017F14
0x180017f31  mov     rcx, [rcx+38h]
0x180017f35  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180017f3c  mov     edx, 76h ; 'v'
0x180017f41  mov     r9d, ebx
0x180017f44  call    WPP_SF_d
0x180017f49  jmp     short loc_180017F14
0x180017f4b  lea     r8, [rsp+0B8h+var_50]; struct MSMSEC_PORT_CONTEXT **
0x180017f50  mov     rdx, rsi; unsigned __int8 (*)[6]
0x180017f53  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180017f56  call    ?SecMgrValidateAndRefPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrValidateAndRefPort(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x180017f5b  mov     ebx, eax
0x180017f5d  test    eax, eax
0x180017f5f  jnz     loc_18001827B
0x180017f65  mov     ecx, [rdi+9C0h]; unsigned int
0x180017f6b  lea     r14, aUnlocking; "<<< Unlocking <<<"
0x180017f72  mov     rdx, r14; char *
0x180017f75  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180017f7a  lea     rdx, [rdi+9D0h]
0x180017f81  mov     r9d, 427h
0x180017f87  lea     r8, aMsmsecrecvpack_0; "MSMSecRecvPacket"
0x180017f8e  mov     rcx, rdi
0x180017f91  call    cs:__imp_ReleaseWriteLock
0x180017f98  nop     dword ptr [rax+rax+00h]
0x180017f9d  mov     rbp, [rsp+0B8h+var_50]
0x180017fa2  mov     rcx, rbp; struct MSMSEC_PORT_CONTEXT *
0x180017fa5  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x180017faa  mov     ebx, eax
0x180017fac  mov     r15d, 0Ch
0x180017fb2  test    eax, eax
0x180017fb4  jnz     loc_1800182B2
0x180017fba  lea     r8, [rsi+8]; unsigned __int8 *
0x180017fbe  mov     edx, r12d; unsigned int
0x180017fc1  mov     rcx, rbp; struct MSMSEC_PORT_CONTEXT *
0x180017fc4  call    ?SecMgrValidateAndEnqueueEapolPacket@@YAKPEAUMSMSEC_PORT_CONTEXT@@KPEAE@Z; SecMgrValidateAndEnqueueEapolPacket(MSMSEC_PORT_CONTEXT *,ulong,uchar *)
0x180017fc9  mov     ebx, eax
0x180017fcb  test    eax, eax
0x180017fcd  jnz     loc_1800182E9
0x180017fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fda  cmp     rcx, r13
0x180017fdd  jz      short loc_180017FEC
0x180017fdf  test    dword ptr [rcx+44h], 100h
0x180017fe6  jnz     loc_180018320
0x180017fec  lea     rdx, [rbp+140h]
0x180017ff3  mov     r9d, 44Bh
0x180017ff9  lea     r8, aMsmsecrecvpack_0; "MSMSecRecvPacket"
0x180018000  mov     rcx, rbp
0x180018003  call    cs:__imp_ReleaseWriteLock
0x18001800a  nop     dword ptr [rax+rax+00h]
0x18001800f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018016  cmp     rcx, r13
0x180018019  jz      loc_18001835A
0x18001801f  test    dword ptr [rcx+44h], 100h
0x180018026  lea     rsi, aDerefing; "<<< Derefing <<<"
0x18001802d  jnz     loc_18001833D
0x180018033  mov     r8d, 44Fh; int
0x180018039  lea     rdx, aMsmsecrecvpack_0; "MSMSecRecvPacket"
0x180018040  mov     rcx, rbp; struct MSMSEC_PORT_CONTEXT *
0x180018043  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180018048  jmp     loc_180017EB7
0x18001804d  test    byte ptr [rbp+44h], 10h
0x180018051  jz      loc_180017E15
0x180018057  movzx   ecx, byte ptr [rsi+5]
0x18001805b  lea     ebx, [r14-8]
0x18001805f  movzx   r9d, byte ptr [rsi+2]
0x180018064  xor     eax, eax
0x180018066  movzx   edx, byte ptr [rsi+4]
0x18001806a  cmp     r14d, 8
0x18001806e  movzx   r8d, byte ptr [rsi+3]
0x180018073  movzx   r10d, byte ptr [rsi+1]
0x180018078  cmovbe  ebx, eax
0x18001807b  movzx   eax, word ptr [rsi+6]
0x18001807f  movzx   r11d, byte ptr [rsi]
0x180018083  mov     [rsp+0B8h+var_60], ebx
0x180018087  mov     [rsp+0B8h+var_68], eax
0x18001808b  mov     [rsp+0B8h+var_70], ecx
0x18001808f  mov     rcx, [rbp+38h]
0x180018093  mov     [rsp+0B8h+var_78], edx
0x180018097  mov     [rsp+0B8h+var_80], r8d
0x18001809c  mov     [rsp+0B8h+var_88], r9d
0x1800180a1  mov     r9d, [rdi+9C0h]
0x1800180a8  mov     dword ptr [rsp+0B8h+var_90], r10d
0x1800180ad  mov     dword ptr [rsp+0B8h+var_98], r11d
0x1800180b2  call    WPP_SF_LDDDDDDDL
0x1800180b7  jmp     loc_180017E15
0x1800180bc  mov     rcx, [rcx+38h]
0x1800180c0  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800180c7  mov     edx, 68h ; 'h'
0x1800180cc  call    WPP_SF_
0x1800180d1  jmp     loc_180017D3A
0x1800180d6  test    byte ptr [rcx+44h], 1
0x1800180da  jz      loc_180017EF7
0x1800180e0  mov     edx, 69h ; 'i'
0x1800180e5  jmp     short loc_1800180EC
0x1800180e7  mov     edx, 6Dh ; 'm'
0x1800180ec  mov     rcx, [rcx+38h]
0x1800180f0  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800180f7  mov     r9d, eax
0x1800180fa  call    WPP_SF_d
0x1800180ff  jmp     loc_180017EF7
0x180018104  mov     rcx, cs:WPP_GLOBAL_Control
0x18001810b  cmp     rcx, r13
0x18001810e  jz      loc_180017EF7
0x180018114  test    byte ptr [rcx+44h], 1
0x180018118  jz      loc_180017EF7
0x18001811e  mov     edx, 6Bh ; 'k'
0x180018123  jmp     short loc_1800180EC
0x180018125  mov     eax, 88C7h
0x18001812a  cmp     r15w, ax
0x18001812e  jz      loc_180017DB8
0x180018134  mov     ebx, 57h ; 'W'
0x180018139  mov     rcx, cs:WPP_GLOBAL_Control
0x180018140  cmp     rcx, r13
0x180018143  jz      loc_180017EF7
0x180018149  test    byte ptr [rcx+44h], 1
0x18001814d  jz      loc_180017EF7
0x180018153  mov     rcx, [rcx+38h]
0x180018157  lea     edx, [rbx+15h]
0x18001815a  mov     r9d, r15d
0x18001815d  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180018164  call    WPP_SF_d
0x180018169  jmp     loc_180017EF7
0x18001816e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018175  cmp     rcx, r13
0x180018178  jz      loc_180017EF7
0x18001817e  test    byte ptr [rcx+44h], 1
0x180018182  jz      loc_180017EF7
0x180018188  jmp     loc_1800180E7
0x18001818d  mov     r8d, [rdi+9C0h]
0x180018194  lea     r9, [rdi+20h]
0x180018198  xor     eax, eax
0x18001819a  mov     ecx, r12d
0x18001819d  cmp     r14d, 8
0x1800181a1  cmovbe  ecx, eax
0x1800181a4  movzx   eax, word ptr [rsi+6]
0x1800181a8  mov     [rsp+0B8h+var_88], ecx
0x1800181ac  mov     dword ptr [rsp+0B8h+var_90], eax
0x1800181b0  mov     [rsp+0B8h+var_98], rsi
0x1800181b5  call    McTemplateU0qjb6qqq_EventWriteTransfer
0x1800181ba  jmp     loc_180017E26
0x1800181bf  mov     ebx, 139Fh
0x1800181c4  mov     r11, cs:WPP_GLOBAL_Control
0x1800181cb  cmp     r11, r13
0x1800181ce  jz      loc_180017E7B
0x1800181d4  test    byte ptr [r11+44h], 1
0x1800181d9  jz      loc_180017E7B
0x1800181df  mov     r10d, [rdi+0AA4h]
0x1800181e6  mov     ecx, ebp
0x1800181e8  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x1800181ed  mov     ecx, r10d
0x1800181f0  mov     r8, rax
0x1800181f3  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800181f8  mov     rcx, [r11+38h]
0x1800181fc  mov     r9, rax
0x1800181ff  mov     [rsp+0B8h+var_88], ebp
0x180018203  mov     edx, 70h ; 'p'
0x180018208  mov     [rsp+0B8h+var_90], r8
0x18001820d  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180018214  mov     dword ptr [rsp+0B8h+var_98], r10d
0x180018219  call    WPP_SF_SLSL
0x18001821e  jmp     loc_180017E7B
0x180018223  mov     ebx, 32h ; '2'
0x180018228  mov     rcx, cs:WPP_GLOBAL_Control
0x18001822f  cmp     rcx, r13
0x180018232  jz      loc_180017E7B
  ... truncated ...
```
