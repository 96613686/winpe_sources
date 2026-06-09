# CWcnSession::Init(CWcnPeer *)

- ea: `0x180016994`
- end: `0x180016d17`
- name: `?Init@CWcnSession@@QEAAJPEAVCWcnPeer@@@Z`
- size: `899`
- prototype: `__int64 __fastcall(CWcnSession *__hidden this, struct CWcnPeer *)`
- caller_count: `4`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x18002c2bc`
- `0x180035c70`
- `0x1800408dc`
- `0x1800496c0`

## callees

- `0x180003840`
- `0x180004f2c`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000b080`
- `0x18000b1f8`
- `0x180016994`
- `0x180018f30`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016a56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016ac8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016a56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016ac8`
- `RPCRT4!UuidCreate` at `0x180016b20`
- `RPCRT4!UuidCreate` at `0x180016b20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWcnSession::Init(CWcnSession *this, struct CWcnPeer *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  HANDLE EventW; // rax
  signed int v9; // ebx
  unsigned int v10; // ebx
  _BYTE *v11; // r10
  unsigned int v12; // eax
  __int64 v13; // r10
  int v14; // edx
  HANDLE v15; // rax
  signed int v16; // ebx
  RPC_STATUS v17; // eax
  unsigned int v18; // ebx
  int Timer; // eax
  __int64 v20; // rdx
  int updated; // eax
  unsigned int v22; // eax
  __int64 v23; // r10

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 10, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *((_QWORD *)this + 4) = a2;
    _InterlockedAdd((volatile signed __int32 *)a2 + 66, 1u);
    *(_WORD *)((char *)this + 437) = 0;
    *((_QWORD *)this + 55) = 0;
    *((_QWORD *)this + 57) = 0;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 33) = EventW;
    if ( !EventW )
    {
      v9 = *((_DWORD *)this + 4);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = v9 | 0x80000000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v10;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_51;
      v12 = (unsigned int)GetIndent(0);
      v14 = 12;
LABEL_15:
      WPP_SF_sd(*(_QWORD *)(v13 + 16), v14, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v12, v10);
LABEL_50:
      v11 = WPP_GLOBAL_Control;
      goto LABEL_51;
    }
    v15 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 32) = v15;
    if ( !v15 )
    {
      v16 = *((_DWORD *)this + 4);
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v10 = v16 | 0x80000000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v10;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_51;
      v12 = (unsigned int)GetIndent(0);
      v14 = 13;
      goto LABEL_15;
    }
    v17 = UuidCreate((UUID *)((char *)this + 1576));
    if ( v17 )
    {
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      else
        v18 = v17;
      v10 = v18 | 0x80000000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_a137d119f5dc35a130051116e3170526_Traceguids,
            (unsigned int)v17,
            v10);
          goto LABEL_50;
        }
LABEL_51:
        if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && ((v10 & 0x80000000) != 0 || v11[25] >= 6u) )
        {
          v22 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v23 + 16), 20, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v22, v10);
        }
      }
      return v10;
    }
    Timer = CWcnService::InitializeSelfIdentityCopy(g_pWcnService, (CWcnSession *)((char *)this + 40));
    v10 = Timer;
    if ( Timer >= 0 )
    {
      updated = CWcnSession::UpdateSelfIdentityFromPeer(this);
      if ( updated < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_a137d119f5dc35a130051116e3170526_Traceguids,
          (unsigned int)updated);
      }
      Timer = CWcnScheduler::CreateTimer(
                (CWcnScheduler *)(*((_QWORD *)g_pWcnService + 7) + 320LL),
                (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER))WcnSessionStartTimeout,
                this,
                (struct _TP_TIMER **)this + 29);
      v10 = Timer;
      if ( Timer >= 0 )
      {
        Timer = CWcnScheduler::CreateTimer(
                  (CWcnScheduler *)(*((_QWORD *)g_pWcnService + 7) + 320LL),
                  (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER))WcnSessionRetransmitTimeout,
                  this,
                  (struct _TP_TIMER **)this + 30);
        v10 = Timer;
        if ( Timer >= 0 )
        {
          Timer = CWcnScheduler::CreateWorkItem(
                    (CWcnScheduler *)(*((_QWORD *)g_pWcnService + 7) + 320LL),
                    (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))WcnSessionFinishTimeout,
                    this,
                    (struct _TP_WORK **)this + 31);
          v10 = Timer;
          if ( Timer >= 0 )
            goto LABEL_50;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v10;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_51;
          v20 = 19;
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v10;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_51;
          v20 = 18;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v10;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_51;
        v20 = 17;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v10;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_51;
      v20 = 15;
    }
    WPP_SF_d(*((_QWORD *)v11 + 2), v20, WPP_a137d119f5dc35a130051116e3170526_Traceguids, (unsigned int)Timer);
    goto LABEL_50;
  }
  if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
    WPP_SF_s(v4[2], 11, WPP_a137d119f5dc35a130051116e3170526_Traceguids, "pPeer");
  return 2147500035LL;
}

```

## disassembly

```asm
0x180016994  push    rbx
0x180016996  push    rbp
0x180016997  push    rdi
0x180016998  push    r14
0x18001699a  push    r15
0x18001699c  sub     rsp, 30h
0x1800169a0  mov     rbx, rdx
0x1800169a3  mov     rdi, rcx
0x1800169a6  mov     r10, cs:WPP_GLOBAL_Control
0x1800169ad  lea     rbp, WPP_GLOBAL_Control
0x1800169b4  lea     r14, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800169bb  mov     r15d, 1
0x1800169c1  cmp     r10, rbp
0x1800169c4  jz      short loc_1800169EF
0x1800169c6  cmp     byte ptr [r10+19h], 6
0x1800169cb  jb      short loc_1800169EF
0x1800169cd  mov     ecx, r15d; int
0x1800169d0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800169d5  mov     rcx, [r10+10h]
0x1800169d9  lea     edx, [r15+9]
0x1800169dd  mov     r9, rax
0x1800169e0  mov     r8, r14
0x1800169e3  call    WPP_SF_s
0x1800169e8  mov     r10, cs:WPP_GLOBAL_Control
0x1800169ef  test    rbx, rbx
0x1800169f2  jnz     short loc_180016A20
0x1800169f4  cmp     r10, rbp
0x1800169f7  jz      short loc_180016A16
0x1800169f9  cmp     byte ptr [r10+19h], 2
0x1800169fe  jb      short loc_180016A16
0x180016a00  mov     rcx, [r10+10h]
0x180016a04  lea     edx, [rbx+0Bh]
0x180016a07  lea     r9, aPpeer; "pPeer"
0x180016a0e  mov     r8, r14
0x180016a11  call    WPP_SF_s
0x180016a16  mov     eax, 80004003h
0x180016a1b  jmp     loc_180016D0B
0x180016a20  mov     [rdi+20h], rbx
0x180016a24  lock add [rbx+108h], r15d
0x180016a2c  xor     r9d, r9d; lpName
0x180016a2f  mov     word ptr [rdi+1B5h], 0
0x180016a38  xor     r8d, r8d; bInitialState
0x180016a3b  mov     qword ptr [rdi+1B8h], 0
0x180016a46  mov     edx, r15d; bManualReset
0x180016a49  mov     qword ptr [rdi+1C8h], 0
0x180016a54  xor     ecx, ecx; lpEventAttributes
0x180016a56  call    cs:__imp_CreateEventW
0x180016a5c  mov     [rdi+108h], rax
0x180016a63  test    rax, rax
0x180016a66  jnz     short loc_180016ABD
0x180016a68  mov     ebx, [rdi+10h]
0x180016a6b  test    ebx, ebx
0x180016a6d  jle     short loc_180016A78
0x180016a6f  movzx   ebx, bx
0x180016a72  or      ebx, 80070000h
0x180016a78  or      ebx, 80000000h
0x180016a7e  mov     r10, cs:WPP_GLOBAL_Control
0x180016a85  cmp     r10, rbp
0x180016a88  jz      loc_180016D09
0x180016a8e  cmp     byte ptr [r10+19h], 2
0x180016a93  jb      loc_180016CD9
0x180016a99  xor     ecx, ecx; int
0x180016a9b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016aa0  mov     edx, 0Ch
0x180016aa5  mov     rcx, [r10+10h]
0x180016aa9  mov     r9, rax
0x180016aac  mov     r8, r14
0x180016aaf  mov     [rsp+58h+var_38], ebx
0x180016ab3  call    WPP_SF_sd
0x180016ab8  jmp     loc_180016CD2
0x180016abd  xor     r9d, r9d; lpName
0x180016ac0  xor     r8d, r8d; bInitialState
0x180016ac3  mov     edx, r15d; bManualReset
0x180016ac6  xor     ecx, ecx; lpEventAttributes
0x180016ac8  call    cs:__imp_CreateEventW
0x180016ace  mov     [rdi+100h], rax
0x180016ad5  test    rax, rax
0x180016ad8  jnz     short loc_180016B19
0x180016ada  mov     ebx, [rdi+10h]
0x180016add  test    ebx, ebx
0x180016adf  jle     short loc_180016AEA
0x180016ae1  movzx   ebx, bx
0x180016ae4  or      ebx, 80070000h
0x180016aea  or      ebx, 80000000h
0x180016af0  mov     r10, cs:WPP_GLOBAL_Control
0x180016af7  cmp     r10, rbp
0x180016afa  jz      loc_180016D09
0x180016b00  cmp     byte ptr [r10+19h], 2
0x180016b05  jb      loc_180016CD9
0x180016b0b  xor     ecx, ecx; int
0x180016b0d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016b12  mov     edx, 0Dh
0x180016b17  jmp     short loc_180016AA5
0x180016b19  lea     rcx, [rdi+628h]; Uuid
0x180016b20  call    cs:__imp_UuidCreate
0x180016b26  test    eax, eax
0x180016b28  jz      short loc_180016B77
0x180016b2a  jg      short loc_180016B30
0x180016b2c  mov     ebx, eax
0x180016b2e  jmp     short loc_180016B39
0x180016b30  movzx   ebx, ax
0x180016b33  or      ebx, 80070000h
0x180016b39  or      ebx, 80000000h
0x180016b3f  mov     r10, cs:WPP_GLOBAL_Control
0x180016b46  cmp     r10, rbp
0x180016b49  jz      loc_180016D09
0x180016b4f  cmp     byte ptr [r10+19h], 2
0x180016b54  jb      loc_180016CD9
0x180016b5a  mov     rcx, [r10+10h]
0x180016b5e  mov     edx, 0Eh
0x180016b63  mov     r9d, eax
0x180016b66  mov     [rsp+58h+var_38], ebx
0x180016b6a  mov     r8, r14
0x180016b6d  call    WPP_SF_Dd
0x180016b72  jmp     loc_180016CD2
0x180016b77  mov     rcx, cs:?g_pWcnService@@3PEAVCWcnService@@EA; this
0x180016b7e  lea     rdx, [rdi+28h]; struct CWcnIdentity *
0x180016b82  call    ?InitializeSelfIdentityCopy@CWcnService@@QEAAJPEAVCWcnIdentity@@@Z; CWcnService::InitializeSelfIdentityCopy(CWcnIdentity *)
0x180016b87  mov     ebx, eax
0x180016b89  test    eax, eax
0x180016b8b  jns     short loc_180016BB2
0x180016b8d  mov     r10, cs:WPP_GLOBAL_Control
0x180016b94  cmp     r10, rbp
0x180016b97  jz      loc_180016D09
0x180016b9d  cmp     byte ptr [r10+19h], 2
0x180016ba2  jb      loc_180016CD9
0x180016ba8  mov     edx, 0Fh
0x180016bad  jmp     loc_180016CC3
0x180016bb2  mov     rcx, rdi; this
0x180016bb5  call    ?UpdateSelfIdentityFromPeer@CWcnSession@@AEAAJXZ; CWcnSession::UpdateSelfIdentityFromPeer(void)
0x180016bba  test    eax, eax
0x180016bbc  jns     short loc_180016BE4
0x180016bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bc5  cmp     rcx, rbp
0x180016bc8  jz      short loc_180016BE4
0x180016bca  cmp     byte ptr [rcx+19h], 3
0x180016bce  jb      short loc_180016BE4
0x180016bd0  mov     rcx, [rcx+10h]
0x180016bd4  mov     edx, 10h
0x180016bd9  mov     r9d, eax
0x180016bdc  mov     r8, r14
0x180016bdf  call    WPP_SF_d
0x180016be4  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x180016beb  lea     r9, [rdi+0E8h]; struct _TP_TIMER **
0x180016bf2  mov     r15d, 140h
0x180016bf8  lea     rdx, ?WcnSessionStartTimeout@@YAXPEAX00@Z; void (*)(void *, void *, void *)
0x180016bff  mov     r8, rdi; void *
0x180016c02  mov     rcx, [rax+38h]
0x180016c06  add     rcx, r15; this
0x180016c09  call    ?CreateTimer@CWcnScheduler@@QEAAJP6AXPEAX00@Z0PEAPEAU_TP_TIMER@@@Z; CWcnScheduler::CreateTimer(void (*)(void *,void *,void *),void *,_TP_TIMER * *)
0x180016c0e  mov     ebx, eax
0x180016c10  test    eax, eax
0x180016c12  jns     short loc_180016C39
0x180016c14  mov     r10, cs:WPP_GLOBAL_Control
0x180016c1b  cmp     r10, rbp
0x180016c1e  jz      loc_180016D09
0x180016c24  cmp     byte ptr [r10+19h], 2
0x180016c29  jb      loc_180016CD9
0x180016c2f  mov     edx, 11h
0x180016c34  jmp     loc_180016CC3
0x180016c39  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x180016c40  lea     r9, [rdi+0F0h]; struct _TP_TIMER **
0x180016c47  mov     r8, rdi; void *
0x180016c4a  lea     rdx, ?WcnSessionRetransmitTimeout@@YAXPEAX00@Z; void (*)(void *, void *, void *)
0x180016c51  mov     rcx, [rax+38h]
0x180016c55  add     rcx, r15; this
0x180016c58  call    ?CreateTimer@CWcnScheduler@@QEAAJP6AXPEAX00@Z0PEAPEAU_TP_TIMER@@@Z; CWcnScheduler::CreateTimer(void (*)(void *,void *,void *),void *,_TP_TIMER * *)
0x180016c5d  mov     ebx, eax
0x180016c5f  test    eax, eax
0x180016c61  jns     short loc_180016C81
0x180016c63  mov     r10, cs:WPP_GLOBAL_Control
0x180016c6a  cmp     r10, rbp
0x180016c6d  jz      loc_180016D09
0x180016c73  cmp     byte ptr [r10+19h], 2
0x180016c78  jb      short loc_180016CD9
0x180016c7a  mov     edx, 12h
0x180016c7f  jmp     short loc_180016CC3
0x180016c81  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x180016c88  lea     r9, [rdi+0F8h]; struct _TP_WORK **
0x180016c8f  mov     r8, rdi; void *
0x180016c92  lea     rdx, ?WcnSessionFinishTimeout@@YAXPEAX00@Z; void (*)(void *, void *, void *)
0x180016c99  mov     rcx, [rax+38h]
0x180016c9d  add     rcx, r15; this
0x180016ca0  call    ?CreateWorkItem@CWcnScheduler@@QEAAJP6AXPEAX00@Z0PEAPEAU_TP_WORK@@@Z; CWcnScheduler::CreateWorkItem(void (*)(void *,void *,void *),void *,_TP_WORK * *)
0x180016ca5  mov     ebx, eax
0x180016ca7  test    eax, eax
0x180016ca9  jns     short loc_180016CD2
0x180016cab  mov     r10, cs:WPP_GLOBAL_Control
0x180016cb2  cmp     r10, rbp
0x180016cb5  jz      short loc_180016D09
0x180016cb7  cmp     byte ptr [r10+19h], 2
0x180016cbc  jb      short loc_180016CD9
0x180016cbe  mov     edx, 13h
0x180016cc3  mov     rcx, [r10+10h]
0x180016cc7  mov     r9d, eax
0x180016cca  mov     r8, r14
0x180016ccd  call    WPP_SF_d
0x180016cd2  mov     r10, cs:WPP_GLOBAL_Control
0x180016cd9  cmp     r10, rbp
0x180016cdc  jz      short loc_180016D09
0x180016cde  test    ebx, ebx
0x180016ce0  js      short loc_180016CE9
0x180016ce2  cmp     byte ptr [r10+19h], 6
0x180016ce7  jb      short loc_180016D09
0x180016ce9  or      ecx, 0FFFFFFFFh; int
0x180016cec  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016cf1  mov     rcx, [r10+10h]
0x180016cf5  mov     edx, 14h
0x180016cfa  mov     r9, rax
0x180016cfd  mov     [rsp+58h+var_38], ebx
0x180016d01  mov     r8, r14
0x180016d04  call    WPP_SF_sd
0x180016d09  mov     eax, ebx
0x180016d0b  add     rsp, 30h
0x180016d0f  pop     r15
0x180016d11  pop     r14
0x180016d13  pop     rdi
0x180016d14  pop     rbp
0x180016d15  pop     rbx
0x180016d16  retn
```
