# CWcnWfdGoSession::DeliverIncomingMessage(CSbMessageBuffer const *)

- ea: `0x18004f150`
- end: `0x18004f401`
- name: `?DeliverIncomingMessage@CWcnWfdGoSession@@UEAAJPEBVCSbMessageBuffer@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(CWcnWfdGoSession *this, const struct CSbMessageBuffer *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x1800157bc`
- `0x180017424`
- `0x18001745c`
- `0x18003da64`
- `0x18004f150`
- `0x18004f594`
- `0x180051968`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f374`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f38c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f38c`

## string_xrefs

- `0x18004f1e4`: `pIncomingMessage`

## pseudocode

```c
__int64 __fastcall CWcnWfdGoSession::DeliverIncomingMessage(CWcnWfdGoSession *this, const struct CSbMessageBuffer *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  int v7; // ebx
  int Fragment; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  const char *v11; // rax
  __int64 v12; // r10
  unsigned int v13; // eax
  __int64 v14; // r10
  int v16; // [rsp+30h] [rbp-58h] BYREF
  UUID v17[3]; // [rsp+38h] [rbp-50h] BYREF

  v16 = 0;
  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v17);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 32, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 33, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids, "pIncomingMessage");
    v7 = -2147467261;
    goto LABEL_41;
  }
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this - 2) + 1592LL));
  Fragment = CWcnEapReassembler::DeliverFragment(
               (UUID *)this + 3,
               a2,
               (enum CWcnEapReassembler::ReassembleResponse *)&v16,
               v17);
  v7 = Fragment;
  if ( Fragment < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_36;
    v10 = 34;
    goto LABEL_13;
  }
  switch ( v16 )
  {
    case 0:
      v7 = -2147019873;
      goto LABEL_36;
    case 1:
      Fragment = CWcnMessageSinkSession::QueueOutgoingMessage(*((_QWORD *)this + 3), 0, v17);
      v7 = Fragment;
      if ( Fragment < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_36;
        v10 = 36;
        goto LABEL_13;
      }
      break;
    case 2:
      Fragment = CWcnWfdGoSession::SendNextFragment((CWcnWfdGoSession *)((char *)this - 32));
      v7 = Fragment;
      if ( Fragment < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_36;
        v10 = 35;
        goto LABEL_13;
      }
      break;
    case 3:
      v7 = -2147176438;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v12 + 16), 37, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids, v11);
      }
      goto LABEL_36;
    case 4:
      Fragment = CWcnSession::DeliverIncomingMessage(
                   *((CWcnSession **)this - 2),
                   (const struct CSbMessageBuffer *)v17,
                   *((_DWORD *)this - 2));
      v7 = Fragment;
      if ( Fragment >= 0 )
        break;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_36;
      v10 = 38;
LABEL_13:
      WPP_SF_d(v9[2], v10, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids, (unsigned int)Fragment);
LABEL_36:
      EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this - 2) + 1536LL));
      CWcnSession::SetFailureCode(*((CWcnSession **)this - 2), v7);
      LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this - 2) + 1536LL));
      break;
    default:
      v7 = -2147418113;
      goto LABEL_41;
  }
  CWcnSession::Release(*((CWcnSession **)this - 2));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v7 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v13 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v14 + 16), 39, (unsigned int)WPP_132dba730db930bf5e13527153a1eb3c_Traceguids, v13, v7);
  }
LABEL_41:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004f150  mov     [rsp+arg_10], rbx
0x18004f155  mov     [rsp+arg_18], rbp
0x18004f15a  push    rsi
0x18004f15b  push    rdi
0x18004f15c  push    r14
0x18004f15e  sub     rsp, 70h
0x18004f162  mov     rax, cs:__security_cookie
0x18004f169  xor     rax, rsp
0x18004f16c  mov     [rsp+88h+var_20], rax
0x18004f171  mov     rbx, rdx
0x18004f174  mov     rdi, rcx
0x18004f177  mov     [rsp+88h+var_58], 0
0x18004f17f  lea     rcx, [rsp+88h+var_50]; this
0x18004f184  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18004f189  nop
0x18004f18a  lea     rbp, WPP_GLOBAL_Control
0x18004f191  lea     r14, WPP_132dba730db930bf5e13527153a1eb3c_Traceguids
0x18004f198  mov     r10, cs:WPP_GLOBAL_Control
0x18004f19f  cmp     r10, rbp
0x18004f1a2  jz      short loc_18004F1D0
0x18004f1a4  cmp     byte ptr [r10+19h], 6
0x18004f1a9  jb      short loc_18004F1D0
0x18004f1ab  mov     ecx, 1; int
0x18004f1b0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004f1b5  mov     edx, 20h ; ' '
0x18004f1ba  mov     r9, rax
0x18004f1bd  mov     r8, r14
0x18004f1c0  mov     rcx, [r10+10h]
0x18004f1c4  call    WPP_SF_s
0x18004f1c9  mov     r10, cs:WPP_GLOBAL_Control
0x18004f1d0  test    rbx, rbx
0x18004f1d3  jnz     short loc_18004F201
0x18004f1d5  cmp     r10, rbp
0x18004f1d8  jz      short loc_18004F1F7
0x18004f1da  cmp     byte ptr [r10+19h], 2
0x18004f1df  jb      short loc_18004F1F7
0x18004f1e1  lea     edx, [rbx+21h]
0x18004f1e4  lea     r9, aPincomingmessa; "pIncomingMessage"
0x18004f1eb  mov     r8, r14
0x18004f1ee  mov     rcx, [r10+10h]
0x18004f1f2  call    WPP_SF_s
0x18004f1f7  mov     ebx, 80004003h
0x18004f1fc  jmp     loc_18004F3D3
0x18004f201  mov     rax, [rdi-10h]
0x18004f205  lock inc dword ptr [rax+638h]
0x18004f20c  lea     rcx, [rdi+30h]; this
0x18004f210  lea     r9, [rsp+88h+var_50]; struct CSbMessageBuffer *
0x18004f215  lea     r8, [rsp+88h+var_58]; enum CWcnEapReassembler::ReassembleResponse *
0x18004f21a  mov     rdx, rbx; struct CSbMessageBuffer *
0x18004f21d  call    ?DeliverFragment@CWcnEapReassembler@@QEAAJPEBVCSbMessageBuffer@@PEAW4ReassembleResponse@1@PEAV2@@Z; CWcnEapReassembler::DeliverFragment(CSbMessageBuffer const *,CWcnEapReassembler::ReassembleResponse *,CSbMessageBuffer *)
0x18004f222  mov     ebx, eax
0x18004f224  test    eax, eax
0x18004f226  jns     short loc_18004F25B
0x18004f228  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f22f  cmp     rcx, rbp
0x18004f232  jz      loc_18004F368
0x18004f238  cmp     byte ptr [rcx+19h], 2
0x18004f23c  jb      loc_18004F368
0x18004f242  mov     edx, 22h ; '"'
0x18004f247  mov     r9d, eax
0x18004f24a  mov     r8, r14
0x18004f24d  mov     rcx, [rcx+10h]
0x18004f251  call    WPP_SF_d
0x18004f256  jmp     loc_18004F368
0x18004f25b  mov     ecx, [rsp+88h+var_58]
0x18004f25f  test    ecx, ecx
0x18004f261  jz      loc_18004F363
0x18004f267  sub     ecx, 1
0x18004f26a  jz      loc_18004F331
0x18004f270  sub     ecx, 1
0x18004f273  jz      loc_18004F306
0x18004f279  sub     ecx, 1
0x18004f27c  jz      short loc_18004F2CD
0x18004f27e  cmp     ecx, 1
0x18004f281  jz      short loc_18004F28D
0x18004f283  mov     ebx, 8000FFFFh
0x18004f288  jmp     loc_18004F3D3
0x18004f28d  mov     r8d, [rdi-8]; unsigned int
0x18004f291  lea     rdx, [rsp+88h+var_50]; struct CSbMessageBuffer *
0x18004f296  mov     rcx, [rdi-10h]; this
0x18004f29a  call    ?DeliverIncomingMessage@CWcnSession@@QEAAJPEBVCSbMessageBuffer@@K@Z; CWcnSession::DeliverIncomingMessage(CSbMessageBuffer const *,ulong)
0x18004f29f  mov     ebx, eax
0x18004f2a1  test    eax, eax
0x18004f2a3  jns     loc_18004F392
0x18004f2a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f2b0  cmp     rcx, rbp
0x18004f2b3  jz      loc_18004F368
0x18004f2b9  cmp     byte ptr [rcx+19h], 2
0x18004f2bd  jb      loc_18004F368
0x18004f2c3  mov     edx, 26h ; '&'
0x18004f2c8  jmp     loc_18004F247
0x18004f2cd  mov     ebx, 8004B00Ah
0x18004f2d2  mov     r10, cs:WPP_GLOBAL_Control
0x18004f2d9  cmp     r10, rbp
0x18004f2dc  jz      loc_18004F368
0x18004f2e2  cmp     byte ptr [r10+19h], 2
0x18004f2e7  jb      short loc_18004F368
0x18004f2e9  xor     ecx, ecx; int
0x18004f2eb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004f2f0  mov     edx, 25h ; '%'
0x18004f2f5  mov     r9, rax
0x18004f2f8  mov     r8, r14
0x18004f2fb  mov     rcx, [r10+10h]
0x18004f2ff  call    WPP_SF_s
0x18004f304  jmp     short loc_18004F368
0x18004f306  lea     rcx, [rdi-20h]; this
0x18004f30a  call    ?SendNextFragment@CWcnWfdGoSession@@AEAAJXZ; CWcnWfdGoSession::SendNextFragment(void)
0x18004f30f  mov     ebx, eax
0x18004f311  test    eax, eax
0x18004f313  jns     short loc_18004F392
0x18004f315  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f31c  cmp     rcx, rbp
0x18004f31f  jz      short loc_18004F368
0x18004f321  cmp     byte ptr [rcx+19h], 2
0x18004f325  jb      short loc_18004F368
0x18004f327  mov     edx, 23h ; '#'
0x18004f32c  jmp     loc_18004F247
0x18004f331  lea     r8, [rsp+88h+var_50]
0x18004f336  xor     edx, edx
0x18004f338  mov     rcx, [rdi+18h]
0x18004f33c  call    ?QueueOutgoingMessage@CWcnMessageSinkSession@@QEAAJW4tagWCN_ACTION@@PEBVCSbMessageBuffer@@@Z; CWcnMessageSinkSession::QueueOutgoingMessage(tagWCN_ACTION,CSbMessageBuffer const *)
0x18004f341  mov     ebx, eax
0x18004f343  test    eax, eax
0x18004f345  jns     short loc_18004F392
0x18004f347  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f34e  cmp     rcx, rbp
0x18004f351  jz      short loc_18004F368
0x18004f353  cmp     byte ptr [rcx+19h], 2
0x18004f357  jb      short loc_18004F368
0x18004f359  mov     edx, 24h ; '$'
0x18004f35e  jmp     loc_18004F247
0x18004f363  mov     ebx, 8007139Fh
0x18004f368  mov     rcx, [rdi-10h]
0x18004f36c  mov     esi, 600h
0x18004f371  add     rcx, rsi; lpCriticalSection
0x18004f374  call    cs:__imp_EnterCriticalSection
0x18004f37a  mov     edx, ebx; int
0x18004f37c  mov     rcx, [rdi-10h]; this
0x18004f380  call    ?SetFailureCode@CWcnSession@@QEAAXJ@Z; CWcnSession::SetFailureCode(long)
0x18004f385  mov     rcx, [rdi-10h]
0x18004f389  add     rcx, rsi; lpCriticalSection
0x18004f38c  call    cs:__imp_LeaveCriticalSection
0x18004f392  mov     rcx, [rdi-10h]; this
0x18004f396  call    ?Release@CWcnSession@@QEAAXXZ; CWcnSession::Release(void)
0x18004f39b  mov     r10, cs:WPP_GLOBAL_Control
0x18004f3a2  cmp     r10, rbp
0x18004f3a5  jz      short loc_18004F3D3
0x18004f3a7  test    ebx, ebx
0x18004f3a9  js      short loc_18004F3B2
0x18004f3ab  cmp     byte ptr [r10+19h], 6
0x18004f3b0  jb      short loc_18004F3D3
0x18004f3b2  or      ecx, 0FFFFFFFFh; int
0x18004f3b5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004f3ba  mov     edx, 27h ; '''
0x18004f3bf  mov     [rsp+88h+var_68], ebx
0x18004f3c3  mov     r9, rax
0x18004f3c6  mov     r8, r14
0x18004f3c9  mov     rcx, [r10+10h]
0x18004f3cd  call    WPP_SF_sd
0x18004f3d2  nop
0x18004f3d3  lea     rcx, [rsp+88h+var_50]; this
0x18004f3d8  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004f3dd  mov     eax, ebx
0x18004f3df  mov     rcx, [rsp+88h+var_20]
0x18004f3e4  xor     rcx, rsp; StackCookie
0x18004f3e7  call    __security_check_cookie
0x18004f3ec  lea     r11, [rsp+88h+var_18]
0x18004f3f1  mov     rbx, [r11+30h]
0x18004f3f5  mov     rbp, [r11+38h]
0x18004f3f9  mov     rsp, r11
0x18004f3fc  pop     r14
0x18004f3fe  pop     rdi
0x18004f3ff  pop     rsi
0x18004f400  retn
```
