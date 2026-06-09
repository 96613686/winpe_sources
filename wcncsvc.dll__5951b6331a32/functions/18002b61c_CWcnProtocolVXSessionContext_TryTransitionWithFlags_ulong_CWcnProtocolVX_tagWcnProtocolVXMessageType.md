# CWcnProtocolVXSessionContext::TryTransitionWithFlags(ulong,CWcnProtocolVX::tagWcnProtocolVXMessageType)

- ea: `0x18002b61c`
- end: `0x18002b82d`
- name: `?TryTransitionWithFlags@CWcnProtocolVXSessionContext@@QEAAJKW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002677c`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18001745c`
- `0x180018104`
- `0x180018a74`
- `0x18002aa60`
- `0x18002b3d8`
- `0x18002b61c`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b7ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002b7ac`

## pseudocode

```c
__int64 __fastcall CWcnProtocolVXSessionContext::TryTransitionWithFlags(CWcnSession **a1, int a2, unsigned int a3)
{
  _BYTE *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  unsigned int v9; // ebx
  const char *v10; // rax
  __int64 v11; // r10
  int v12; // eax
  _BYTE *v13; // r10
  int v14; // eax
  PTP_TIMER *v15; // rdi
  const char *v16; // rax
  __int64 v17; // r10
  const char *v18; // rax
  __int64 v19; // r10
  unsigned int v20; // eax
  __int64 v21; // r10

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 18, WPP_dfa615b9e67b3e2ae489af9303373651_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (a2 & 0x1000000) != 0 )
  {
    v9 = 0;
    if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && v6[25] >= 5u )
    {
      v10 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v11 + 16), 19, WPP_dfa615b9e67b3e2ae489af9303373651_Traceguids, v10);
    }
    CWcnSession::SetSessionResult(a1[1], 2);
    goto LABEL_29;
  }
  if ( (a2 & 0x20) != 0 && a3 == 3 && !*((_DWORD *)a1[1] + 68) )
  {
    v12 = CWcnProtocolVXSessionContext::CheckIfMessageIsType((CWcnProtocolVXSessionContext *)a1, WCN_VALUE_MT_M2D);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v9;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_30;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_dfa615b9e67b3e2ae489af9303373651_Traceguids,
        (unsigned int)v12);
      goto LABEL_29;
    }
    if ( v12 == 1 )
    {
LABEL_29:
      v13 = WPP_GLOBAL_Control;
      goto LABEL_30;
    }
  }
  v14 = CWcnProtocolVXSessionContext::StateMachineCallback(a1, a3);
  v9 = v14;
  if ( v14 < 0 )
  {
    CWcnSession::SetFailureCode(a1[1], v14);
    goto LABEL_29;
  }
  if ( (a2 & 0x2000000) != 0 )
    CWcnSession::SetSessionResult(a1[1], 2);
  v15 = (PTP_TIMER *)a1[1];
  if ( (a2 & 0x4000000) != 0 )
  {
    CWcnSession::StartRetransmitTimer((CWcnSession *)v15, 1);
    goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v16 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v17 + 16), 131, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v16);
  }
  SetThreadpoolTimer(v15[30], 0, 0, 0);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
LABEL_30:
      if ( v13 != (_BYTE *)&WPP_GLOBAL_Control && ((v9 & 0x80000000) != 0 || v13[25] >= 6u) )
      {
        v20 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v21 + 16), 21, (unsigned int)WPP_dfa615b9e67b3e2ae489af9303373651_Traceguids, v20, v9);
      }
      return v9;
    }
    v18 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v19 + 16), 132, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v18);
    goto LABEL_29;
  }
  return v9;
}

```

## disassembly

```asm
0x18002b61c  push    rbx
0x18002b61e  push    rbp
0x18002b61f  push    rsi
0x18002b620  push    rdi
0x18002b621  push    r14
0x18002b623  sub     rsp, 30h
0x18002b627  mov     ebp, r8d
0x18002b62a  mov     esi, edx
0x18002b62c  mov     rdi, rcx
0x18002b62f  mov     r10, cs:WPP_GLOBAL_Control
0x18002b636  lea     r14, WPP_GLOBAL_Control
0x18002b63d  cmp     r10, r14
0x18002b640  jz      short loc_18002B672
0x18002b642  cmp     byte ptr [r10+19h], 6
0x18002b647  jb      short loc_18002B672
0x18002b649  mov     ecx, 1; int
0x18002b64e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002b653  mov     rcx, [r10+10h]
0x18002b657  lea     r8, WPP_dfa615b9e67b3e2ae489af9303373651_Traceguids
0x18002b65e  mov     edx, 12h
0x18002b663  mov     r9, rax
0x18002b666  call    WPP_SF_s
0x18002b66b  mov     r10, cs:WPP_GLOBAL_Control
0x18002b672  bt      esi, 18h
0x18002b676  jnb     short loc_18002B6B6
0x18002b678  xor     ebx, ebx
0x18002b67a  cmp     r10, r14
0x18002b67d  jz      short loc_18002B6A3
0x18002b67f  cmp     byte ptr [r10+19h], 5
0x18002b684  jb      short loc_18002B6A3
0x18002b686  xor     ecx, ecx; int
0x18002b688  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002b68d  mov     rcx, [r10+10h]
0x18002b691  lea     edx, [rbx+13h]
0x18002b694  mov     r9, rax
0x18002b697  lea     r8, WPP_dfa615b9e67b3e2ae489af9303373651_Traceguids
0x18002b69e  call    WPP_SF_s
0x18002b6a3  mov     rcx, [rdi+8]
0x18002b6a7  mov     edx, 2
0x18002b6ac  call    ?SetSessionResult@CWcnSession@@QEAAXW4tagWCNPRPC_SESSION_NOTIFICATION_TYPE@@@Z; CWcnSession::SetSessionResult(tagWCNPRPC_SESSION_NOTIFICATION_TYPE)
0x18002b6b1  jmp     loc_18002B7E5
0x18002b6b6  test    sil, 20h
0x18002b6ba  jz      short loc_18002B71E
0x18002b6bc  cmp     ebp, 3
0x18002b6bf  jnz     short loc_18002B71E
0x18002b6c1  mov     rax, [rdi+8]
0x18002b6c5  cmp     dword ptr [rax+110h], 0
0x18002b6cc  jnz     short loc_18002B71E
0x18002b6ce  lea     edx, [rbp+3]; enum tagWCN_VALUE_TYPE_MESSAGE_TYPE
0x18002b6d1  mov     rcx, rdi; this
0x18002b6d4  call    ?CheckIfMessageIsType@CWcnProtocolVXSessionContext@@QEAAJW4tagWCN_VALUE_TYPE_MESSAGE_TYPE@@@Z; CWcnProtocolVXSessionContext::CheckIfMessageIsType(tagWCN_VALUE_TYPE_MESSAGE_TYPE)
0x18002b6d9  mov     ebx, eax
0x18002b6db  test    eax, eax
0x18002b6dd  jns     short loc_18002B715
0x18002b6df  mov     r10, cs:WPP_GLOBAL_Control
0x18002b6e6  cmp     r10, r14
0x18002b6e9  jz      loc_18002B820
0x18002b6ef  cmp     byte ptr [r10+19h], 2
0x18002b6f4  jb      loc_18002B7EC
0x18002b6fa  mov     rcx, [r10+10h]
0x18002b6fe  lea     edx, [rbp+11h]
0x18002b701  mov     r9d, eax
0x18002b704  lea     r8, WPP_dfa615b9e67b3e2ae489af9303373651_Traceguids
0x18002b70b  call    WPP_SF_d
0x18002b710  jmp     loc_18002B7E5
0x18002b715  cmp     eax, 1
0x18002b718  jz      loc_18002B7E5
0x18002b71e  mov     edx, ebp
0x18002b720  mov     rcx, rdi
0x18002b723  call    ?StateMachineCallback@CWcnProtocolVXSessionContext@@AEAAJW4tagWcnProtocolVXMessageType@CWcnProtocolVX@@@Z; CWcnProtocolVXSessionContext::StateMachineCallback(CWcnProtocolVX::tagWcnProtocolVXMessageType)
0x18002b728  mov     ebx, eax
0x18002b72a  test    eax, eax
0x18002b72c  jns     short loc_18002B73E
0x18002b72e  mov     rcx, [rdi+8]; this
0x18002b732  mov     edx, eax; int
0x18002b734  call    ?SetFailureCode@CWcnSession@@QEAAXJ@Z; CWcnSession::SetFailureCode(long)
0x18002b739  jmp     loc_18002B7E5
0x18002b73e  bt      esi, 19h
0x18002b742  jnb     short loc_18002B752
0x18002b744  mov     rcx, [rdi+8]
0x18002b748  mov     edx, 2
0x18002b74d  call    ?SetSessionResult@CWcnSession@@QEAAXW4tagWCNPRPC_SESSION_NOTIFICATION_TYPE@@@Z; CWcnSession::SetSessionResult(tagWCNPRPC_SESSION_NOTIFICATION_TYPE)
0x18002b752  mov     rdi, [rdi+8]
0x18002b756  bt      esi, 1Ah
0x18002b75a  jnb     short loc_18002B768
0x18002b75c  mov     dl, 1; bool
0x18002b75e  mov     rcx, rdi; this
0x18002b761  call    ?StartRetransmitTimer@CWcnSession@@QEAAX_N@Z; CWcnSession::StartRetransmitTimer(bool)
0x18002b766  jmp     short loc_18002B7E5
0x18002b768  mov     r10, cs:WPP_GLOBAL_Control
0x18002b76f  cmp     r10, r14
0x18002b772  jz      short loc_18002B79D
0x18002b774  cmp     byte ptr [r10+19h], 6
0x18002b779  jb      short loc_18002B79D
0x18002b77b  mov     ecx, 1; int
0x18002b780  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002b785  mov     rcx, [r10+10h]
0x18002b789  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18002b790  mov     edx, 83h
0x18002b795  mov     r9, rax
0x18002b798  call    WPP_SF_s
0x18002b79d  mov     rcx, [rdi+0F0h]; pti
0x18002b7a4  xor     r9d, r9d; msWindowLength
0x18002b7a7  xor     r8d, r8d; msPeriod
0x18002b7aa  xor     edx, edx; pftDueTime
0x18002b7ac  call    cs:__imp_SetThreadpoolTimer
0x18002b7b2  mov     r10, cs:WPP_GLOBAL_Control
0x18002b7b9  cmp     r10, r14
0x18002b7bc  jz      short loc_18002B820
0x18002b7be  cmp     byte ptr [r10+19h], 6
0x18002b7c3  jb      short loc_18002B7EC
0x18002b7c5  or      ecx, 0FFFFFFFFh; int
0x18002b7c8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002b7cd  mov     rcx, [r10+10h]
0x18002b7d1  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18002b7d8  mov     edx, 84h
0x18002b7dd  mov     r9, rax
0x18002b7e0  call    WPP_SF_s
0x18002b7e5  mov     r10, cs:WPP_GLOBAL_Control
0x18002b7ec  cmp     r10, r14
0x18002b7ef  jz      short loc_18002B820
0x18002b7f1  test    ebx, ebx
0x18002b7f3  js      short loc_18002B7FC
0x18002b7f5  cmp     byte ptr [r10+19h], 6
0x18002b7fa  jb      short loc_18002B820
0x18002b7fc  or      ecx, 0FFFFFFFFh; int
0x18002b7ff  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002b804  mov     rcx, [r10+10h]
0x18002b808  lea     r8, WPP_dfa615b9e67b3e2ae489af9303373651_Traceguids
0x18002b80f  mov     edx, 15h
0x18002b814  mov     [rsp+58h+var_38], ebx
0x18002b818  mov     r9, rax
0x18002b81b  call    WPP_SF_sd
0x18002b820  mov     eax, ebx
0x18002b822  add     rsp, 30h
0x18002b826  pop     r14
0x18002b828  pop     rdi
0x18002b829  pop     rsi
0x18002b82a  pop     rbp
0x18002b82b  pop     rbx
0x18002b82c  retn
```
