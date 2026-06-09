# CWcnWfdGoSession::StartDisconnect(void)

- ea: `0x18004fa00`
- end: `0x18004fbd9`
- name: `?StartDisconnect@CWcnWfdGoSession@@UEAAXXZ`
- size: `473`
- prototype: `void __fastcall(CWcnWfdGoSession *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000a994`
- `0x18003d6e8`
- `0x18003da64`
- `0x18003dbb4`
- `0x18004fa00`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fa41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fa41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb59`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004fb6b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004fb6b`
- `RPCRT4!UuidCreate` at `0x18004fb04`
- `RPCRT4!UuidCreate` at `0x18004fb04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWcnWfdGoSession::StartDisconnect(CWcnWfdGoSession *this)
{
  char v2; // si
  const char *Indent; // rax
  __int64 v4; // r10
  int v5; // ebx
  int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // r10
  unsigned __int8 v11[8]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v12[32]; // [rsp+38h] [rbp-50h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-30h] BYREF

  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v12);
  *(_DWORD *)v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  if ( !*((_BYTE *)this + 304) )
  {
    v5 = 0;
    v2 = 0;
    *((_BYTE *)this + 304) = 1;
    if ( !*((_QWORD *)this + 7) )
      goto LABEL_18;
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 20LL) != 1 )
    {
      v6 = CSbSafeBuffer::PushToBack((CSbSafeBuffer *)v12, v11, 4u);
      v5 = v6;
      if ( v6 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_18;
        v8 = 29;
        goto LABEL_12;
      }
      UuidCreate(&Uuid);
      v6 = CWcnMessageSinkSession::QueueOutgoingMessage(*((_QWORD *)this + 7), 2, v12);
      v5 = v6;
      if ( v6 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_18;
        v8 = 30;
LABEL_12:
        WPP_SF_d(v7[2], v8, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids, (unsigned int)v6);
        goto LABEL_18;
      }
    }
    CWcnMessageSinkSession::EndSessionAndPreventMoreMessages(*((CWcnMessageSinkSession **)this + 7));
    CWcnMessageSinkSession::Release(*((CWcnMessageSinkSession **)this + 7));
    *((_QWORD *)this + 7) = 0;
    goto LABEL_18;
  }
  v2 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    Indent = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 28, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids, Indent);
  }
  v5 = -2147467259;
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  if ( !v2 )
    SubmitThreadpoolWork(*((PTP_WORK *)this + 32));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v5 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v9 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v10 + 16), 31, (unsigned int)WPP_132dba730db930bf5e13527153a1eb3c_Traceguids, v9, v5);
  }
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v12);
}

```

## disassembly

```asm
0x18004fa00  mov     [rsp+arg_8], rbx
0x18004fa05  mov     [rsp+arg_10], rbp
0x18004fa0a  push    rsi
0x18004fa0b  push    rdi
0x18004fa0c  push    r15
0x18004fa0e  sub     rsp, 70h
0x18004fa12  mov     rax, cs:__security_cookie
0x18004fa19  xor     rax, rsp
0x18004fa1c  mov     [rsp+88h+var_20], rax
0x18004fa21  mov     rdi, rcx
0x18004fa24  lea     rcx, [rsp+88h+var_50]; this
0x18004fa29  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004fa2e  nop
0x18004fa2f  mov     dword ptr [rsp+88h+var_58], 0
0x18004fa37  lea     rbp, [rdi+108h]
0x18004fa3e  mov     rcx, rbp; lpCriticalSection
0x18004fa41  call    cs:__imp_EnterCriticalSection
0x18004fa47  lea     r15, WPP_GLOBAL_Control
0x18004fa4e  cmp     byte ptr [rdi+130h], 0
0x18004fa55  jz      short loc_18004FA96
0x18004fa57  mov     sil, 1
0x18004fa5a  mov     r10, cs:WPP_GLOBAL_Control
0x18004fa61  cmp     r10, r15
0x18004fa64  jz      short loc_18004FA8C
0x18004fa66  cmp     byte ptr [r10+19h], 2
0x18004fa6b  jb      short loc_18004FA8C
0x18004fa6d  xor     ecx, ecx; int
0x18004fa6f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004fa74  mov     edx, 1Ch
0x18004fa79  mov     r9, rax
0x18004fa7c  lea     r8, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids
0x18004fa83  mov     rcx, [r10+10h]
0x18004fa87  call    WPP_SF_s
0x18004fa8c  mov     ebx, 80004005h
0x18004fa91  jmp     loc_18004FB56
0x18004fa96  xor     ebx, ebx
0x18004fa98  xor     sil, sil
0x18004fa9b  mov     byte ptr [rdi+130h], 1
0x18004faa2  cmp     [rdi+38h], rbx
0x18004faa6  jz      loc_18004FB56
0x18004faac  mov     rax, [rdi+10h]
0x18004fab0  cmp     dword ptr [rax+14h], 1
0x18004fab4  jz      loc_18004FB3C
0x18004faba  lea     r8d, [rbx+4]; unsigned __int64
0x18004fabe  lea     rdx, [rsp+88h+var_58]; unsigned __int8 *
0x18004fac3  lea     rcx, [rsp+88h+var_50]; this
0x18004fac8  call    ?PushToBack@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::PushToBack(uchar const *,unsigned __int64)
0x18004facd  mov     ebx, eax
0x18004facf  test    eax, eax
0x18004fad1  jns     short loc_18004FAFF
0x18004fad3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fada  cmp     rcx, r15
0x18004fadd  jz      short loc_18004FB56
0x18004fadf  cmp     byte ptr [rcx+19h], 2
0x18004fae3  jb      short loc_18004FB56
0x18004fae5  mov     edx, 1Dh
0x18004faea  mov     r9d, eax
0x18004faed  lea     r8, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids
0x18004faf4  mov     rcx, [rcx+10h]
0x18004faf8  call    WPP_SF_d
0x18004fafd  jmp     short loc_18004FB56
0x18004faff  lea     rcx, [rsp+88h+Uuid]; Uuid
0x18004fb04  call    cs:__imp_UuidCreate
0x18004fb0a  lea     r8, [rsp+88h+var_50]
0x18004fb0f  mov     edx, 2
0x18004fb14  mov     rcx, [rdi+38h]
0x18004fb18  call    ?QueueOutgoingMessage@CWcnMessageSinkSession@@QEAAJW4tagWCN_ACTION@@PEBVCSbMessageBuffer@@@Z; CWcnMessageSinkSession::QueueOutgoingMessage(tagWCN_ACTION,CSbMessageBuffer const *)
0x18004fb1d  mov     ebx, eax
0x18004fb1f  test    eax, eax
0x18004fb21  jns     short loc_18004FB3C
0x18004fb23  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fb2a  cmp     rcx, r15
0x18004fb2d  jz      short loc_18004FB56
0x18004fb2f  cmp     byte ptr [rcx+19h], 2
0x18004fb33  jb      short loc_18004FB56
0x18004fb35  mov     edx, 1Eh
0x18004fb3a  jmp     short loc_18004FAEA
0x18004fb3c  mov     rcx, [rdi+38h]; this
0x18004fb40  call    ?EndSessionAndPreventMoreMessages@CWcnMessageSinkSession@@QEAAXXZ; CWcnMessageSinkSession::EndSessionAndPreventMoreMessages(void)
0x18004fb45  mov     rcx, [rdi+38h]; this
0x18004fb49  call    ?Release@CWcnMessageSinkSession@@QEAAXXZ; CWcnMessageSinkSession::Release(void)
0x18004fb4e  mov     qword ptr [rdi+38h], 0
0x18004fb56  mov     rcx, rbp; lpCriticalSection
0x18004fb59  call    cs:__imp_LeaveCriticalSection
0x18004fb5f  test    sil, sil
0x18004fb62  jnz     short loc_18004FB71
0x18004fb64  mov     rcx, [rdi+100h]; pwk
0x18004fb6b  call    cs:__imp_SubmitThreadpoolWork
0x18004fb71  mov     r10, cs:WPP_GLOBAL_Control
0x18004fb78  cmp     r10, r15
0x18004fb7b  jz      short loc_18004FBAD
0x18004fb7d  test    ebx, ebx
0x18004fb7f  js      short loc_18004FB88
0x18004fb81  cmp     byte ptr [r10+19h], 6
0x18004fb86  jb      short loc_18004FBAD
0x18004fb88  or      ecx, 0FFFFFFFFh; int
0x18004fb8b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004fb90  mov     edx, 1Fh
0x18004fb95  mov     [rsp+88h+var_68], ebx
0x18004fb99  mov     r9, rax
0x18004fb9c  lea     r8, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids
0x18004fba3  mov     rcx, [r10+10h]
0x18004fba7  call    WPP_SF_sd
0x18004fbac  nop
0x18004fbad  lea     rcx, [rsp+88h+var_50]; this
0x18004fbb2  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004fbb7  mov     rcx, [rsp+88h+var_20]
0x18004fbbc  xor     rcx, rsp; StackCookie
0x18004fbbf  call    __security_check_cookie
0x18004fbc4  lea     r11, [rsp+88h+var_18]
0x18004fbc9  mov     rbx, [r11+28h]
0x18004fbcd  mov     rbp, [r11+30h]
0x18004fbd1  mov     rsp, r11
0x18004fbd4  pop     r15
0x18004fbd6  pop     rdi
0x18004fbd7  pop     rsi
0x18004fbd8  retn
```
