# WcnpRpcPeerOpenSession

- ea: `0x180035c70`
- end: `0x180035eaf`
- name: `WcnpRpcPeerOpenSession`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x1800149ec`
- `0x180016994`
- `0x180017424`
- `0x180035c70`
- `0x18003aa08`
- `0x18003bdb0`
- `0x18003bddc`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180035e5c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180035e5c`

## pseudocode

```c
__int64 __fastcall WcnpRpcPeerOpenSession(__int64 a1, __int64 a2, CWcnRpcHandle **a3)
{
  _QWORD *v5; // r10
  const char *Indent; // rax
  __int64 v7; // r10
  int v9; // ebx
  int v10; // eax
  _BYTE *v11; // r10
  CWcnSession *v12; // rax
  CWcnSession *v13; // rax
  CWcnSession *v14; // rdi
  int v15; // eax
  CWcnRpcHandle *v16; // rax
  CWcnRpcHandle *v17; // rdi
  unsigned int v18; // eax
  __int64 v19; // r10
  CWcnRpcHandle *v20; // [rsp+50h] [rbp+8h] BYREF
  struct CWcnPeer *v21; // [rsp+68h] [rbp+20h] BYREF

  v21 = 0;
  v20 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 54, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, Indent);
    v5 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 2u )
      WPP_SF_s(v5[2], 55, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, "hPeer");
    return 2147500035LL;
  }
  *a3 = 0;
  if ( !(unsigned __int8)CWcnRpcHandle::ValidateHandle(a1, 1, &v21) )
  {
    v9 = -2147024890;
    goto LABEL_29;
  }
  v10 = CWcnRpcHandleTracker::CreateRpcHandle(*((_QWORD *)g_pWcnService + 7) + 1408LL, 2, &v20);
  v9 = v10;
  if ( v10 >= 0 )
  {
    v12 = (CWcnSession *)operator new(0x640u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v12 && (v13 = CWcnSession::CWcnSession(v12), (v14 = v13) != 0) )
    {
      v15 = CWcnSession::Init(v13, v21);
      v9 = v15;
      if ( v15 >= 0 )
      {
        v16 = v20;
        v20 = 0;
        *((_QWORD *)v16 + 1) = v14;
        *a3 = v16;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            WPP_b6f763267c4d324c721a67068f3e4818_Traceguids,
            (unsigned int)v15);
        CWcnSession::Release(v14);
      }
    }
    else
    {
      v9 = -2147024882;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_27;
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, "pNewSession");
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_27;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      WPP_b6f763267c4d324c721a67068f3e4818_Traceguids,
      (unsigned int)v10);
  }
  v11 = WPP_GLOBAL_Control;
LABEL_27:
  v17 = v20;
  if ( !v20 )
    goto LABEL_30;
  CWcnRpcHandle::~CWcnRpcHandle(v20);
  operator delete(v17);
LABEL_29:
  v11 = WPP_GLOBAL_Control;
LABEL_30:
  if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v9 < 0 || v11[25] >= 6u) )
  {
    v18 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 59, (unsigned int)WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v18, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180035c70  mov     rax, rsp
0x180035c73  mov     [rax+10h], rbx
0x180035c77  mov     [rax+18h], rsi
0x180035c7b  push    rdi
0x180035c7c  push    r14
0x180035c7e  push    r15
0x180035c80  sub     rsp, 30h
0x180035c84  mov     rsi, r8
0x180035c87  mov     qword ptr [rax+20h], 0
0x180035c8f  mov     rbx, rcx
0x180035c92  mov     qword ptr [rax+8], 0
0x180035c9a  mov     r10, cs:WPP_GLOBAL_Control
0x180035ca1  lea     r14, WPP_GLOBAL_Control
0x180035ca8  lea     r15, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids
0x180035caf  mov     edi, 1
0x180035cb4  cmp     r10, r14
0x180035cb7  jz      short loc_180035CE0
0x180035cb9  cmp     byte ptr [r10+19h], 6
0x180035cbe  jb      short loc_180035CE0
0x180035cc0  mov     ecx, edi; int
0x180035cc2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180035cc7  mov     rcx, [r10+10h]
0x180035ccb  lea     edx, [rdi+35h]
0x180035cce  mov     r9, rax
0x180035cd1  mov     r8, r15
0x180035cd4  call    WPP_SF_s
0x180035cd9  mov     r10, cs:WPP_GLOBAL_Control
0x180035ce0  test    rbx, rbx
0x180035ce3  jnz     short loc_180035D11
0x180035ce5  cmp     r10, r14
0x180035ce8  jz      short loc_180035D07
0x180035cea  cmp     byte ptr [r10+19h], 2
0x180035cef  jb      short loc_180035D07
0x180035cf1  mov     rcx, [r10+10h]
0x180035cf5  lea     edx, [rbx+37h]
0x180035cf8  lea     r9, aHpeer; "hPeer"
0x180035cff  mov     r8, r15
0x180035d02  call    WPP_SF_s
0x180035d07  mov     eax, 80004003h
0x180035d0c  jmp     loc_180035E9B
0x180035d11  lea     r8, [rsp+48h+arg_18]
0x180035d16  mov     qword ptr [rsi], 0
0x180035d1d  mov     edx, edi
0x180035d1f  mov     rcx, rbx
0x180035d22  call    ?ValidateHandle@CWcnRpcHandle@@SA_NPEAXW4tagWCNPRPC_HANDLE_TYPE@@PEAPEAX@Z; CWcnRpcHandle::ValidateHandle(void *,tagWCNPRPC_HANDLE_TYPE,void * *)
0x180035d27  test    al, al
0x180035d29  jnz     short loc_180035D35
0x180035d2b  mov     ebx, 80070006h
0x180035d30  jmp     loc_180035E62
0x180035d35  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x180035d3c  lea     r8, [rsp+48h+arg_0]
0x180035d41  mov     edx, 2
0x180035d46  mov     rcx, [rax+38h]
0x180035d4a  add     rcx, 580h
0x180035d51  call    ?CreateRpcHandle@CWcnRpcHandleTracker@@QEAAJW4tagWCNPRPC_HANDLE_TYPE@@PEAPEAVCWcnRpcHandle@@@Z; CWcnRpcHandleTracker::CreateRpcHandle(tagWCNPRPC_HANDLE_TYPE,CWcnRpcHandle * *)
0x180035d56  mov     ebx, eax
0x180035d58  test    eax, eax
0x180035d5a  jns     short loc_180035D90
0x180035d5c  mov     r10, cs:WPP_GLOBAL_Control
0x180035d63  cmp     r10, r14
0x180035d66  jz      loc_180035E47
0x180035d6c  cmp     byte ptr [r10+19h], 2
0x180035d71  jb      loc_180035E47
0x180035d77  mov     rcx, [r10+10h]
0x180035d7b  mov     edx, 38h ; '8'
0x180035d80  mov     r9d, eax
0x180035d83  mov     r8, r15
0x180035d86  call    WPP_SF_d
0x180035d8b  jmp     loc_180035E40
0x180035d90  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035d97  mov     ecx, 640h; unsigned __int64
0x180035d9c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035da1  test    rax, rax
0x180035da4  jz      short loc_180035E10
0x180035da6  mov     rcx, rax; this
0x180035da9  call    ??0CWcnSession@@QEAA@XZ; CWcnSession::CWcnSession(void)
0x180035dae  mov     rdi, rax
0x180035db1  test    rax, rax
0x180035db4  jz      short loc_180035E10
0x180035db6  mov     rdx, [rsp+48h+arg_18]; struct CWcnPeer *
0x180035dbb  mov     rcx, rax; this
0x180035dbe  call    ?Init@CWcnSession@@QEAAJPEAVCWcnPeer@@@Z; CWcnSession::Init(CWcnPeer *)
0x180035dc3  mov     ebx, eax
0x180035dc5  test    eax, eax
0x180035dc7  jns     short loc_180035DF9
0x180035dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180035dd0  cmp     rcx, r14
0x180035dd3  jz      short loc_180035DEF
0x180035dd5  cmp     byte ptr [rcx+19h], 2
0x180035dd9  jb      short loc_180035DEF
0x180035ddb  mov     rcx, [rcx+10h]
0x180035ddf  mov     edx, 3Ah ; ':'
0x180035de4  mov     r9d, eax
0x180035de7  mov     r8, r15
0x180035dea  call    WPP_SF_d
0x180035def  mov     rcx, rdi; this
0x180035df2  call    ?Release@CWcnSession@@QEAAXXZ; CWcnSession::Release(void)
0x180035df7  jmp     short loc_180035E40
0x180035df9  mov     rax, [rsp+48h+arg_0]
0x180035dfe  mov     [rsp+48h+arg_0], 0
0x180035e07  mov     [rax+8], rdi
0x180035e0b  mov     [rsi], rax
0x180035e0e  jmp     short loc_180035E40
0x180035e10  mov     ebx, 8007000Eh
0x180035e15  mov     r10, cs:WPP_GLOBAL_Control
0x180035e1c  cmp     r10, r14
0x180035e1f  jz      short loc_180035E47
0x180035e21  cmp     byte ptr [r10+19h], 2
0x180035e26  jb      short loc_180035E47
0x180035e28  mov     rcx, [r10+10h]
0x180035e2c  lea     r9, aPnewsession; "pNewSession"
0x180035e33  mov     edx, 39h ; '9'
0x180035e38  mov     r8, r15
0x180035e3b  call    WPP_SF_s
0x180035e40  mov     r10, cs:WPP_GLOBAL_Control
0x180035e47  mov     rdi, [rsp+48h+arg_0]
0x180035e4c  test    rdi, rdi
0x180035e4f  jz      short loc_180035E69
0x180035e51  mov     rcx, rdi; this
0x180035e54  call    ??1CWcnRpcHandle@@QEAA@XZ; CWcnRpcHandle::~CWcnRpcHandle(void)
0x180035e59  mov     rcx, rdi
0x180035e5c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180035e62  mov     r10, cs:WPP_GLOBAL_Control
0x180035e69  cmp     r10, r14
0x180035e6c  jz      short loc_180035E99
0x180035e6e  test    ebx, ebx
0x180035e70  js      short loc_180035E79
0x180035e72  cmp     byte ptr [r10+19h], 6
0x180035e77  jb      short loc_180035E99
0x180035e79  or      ecx, 0FFFFFFFFh; int
0x180035e7c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180035e81  mov     rcx, [r10+10h]
0x180035e85  mov     edx, 3Bh ; ';'
0x180035e8a  mov     r9, rax
0x180035e8d  mov     [rsp+48h+var_28], ebx
0x180035e91  mov     r8, r15
0x180035e94  call    WPP_SF_sd
0x180035e99  mov     eax, ebx
0x180035e9b  mov     rbx, [rsp+48h+arg_8]
0x180035ea0  mov     rsi, [rsp+48h+arg_10]
0x180035ea5  add     rsp, 30h
0x180035ea9  pop     r15
0x180035eab  pop     r14
0x180035ead  pop     rdi
0x180035eae  retn
```
