# CWcnSoftApSession::DeliverIncomingMessage(CSbMessageBuffer const *)

- ea: `0x180049f10`
- end: `0x18004a1c1`
- name: `?DeliverIncomingMessage@CWcnSoftApSession@@UEAAJPEBVCSbMessageBuffer@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(CWcnSoftApSession *this, const struct CSbMessageBuffer *)`
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
- `0x180049f10`
- `0x18004a450`
- `0x180051968`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a134`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a134`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a14c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a14c`

## string_xrefs

- `0x180049fa4`: `pIncomingMessage`

## pseudocode

```c
__int64 __fastcall CWcnSoftApSession::DeliverIncomingMessage(
        CWcnSoftApSession *this,
        const struct CSbMessageBuffer *a2)
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
    WPP_SF_s(*(_QWORD *)(v6 + 16), 27, WPP_547e2d81e4df314cfcd37421c8b4611e_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 28, WPP_547e2d81e4df314cfcd37421c8b4611e_Traceguids, "pIncomingMessage");
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
    v10 = 29;
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
        v10 = 31;
        goto LABEL_13;
      }
      break;
    case 2:
      Fragment = CWcnSoftApSession::SendNextFragment((CWcnSoftApSession *)((char *)this - 32));
      v7 = Fragment;
      if ( Fragment < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_36;
        v10 = 30;
        goto LABEL_13;
      }
      break;
    case 3:
      v7 = -2147176438;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v12 + 16), 32, WPP_547e2d81e4df314cfcd37421c8b4611e_Traceguids, v11);
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
      v10 = 33;
LABEL_13:
      WPP_SF_d(v9[2], v10, WPP_547e2d81e4df314cfcd37421c8b4611e_Traceguids, (unsigned int)Fragment);
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
    WPP_SF_sd(*(_QWORD *)(v14 + 16), 34, (unsigned int)WPP_547e2d81e4df314cfcd37421c8b4611e_Traceguids, v13, v7);
  }
LABEL_41:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180049f10  mov     [rsp+arg_10], rbx
0x180049f15  mov     [rsp+arg_18], rbp
0x180049f1a  push    rsi
0x180049f1b  push    rdi
0x180049f1c  push    r14
0x180049f1e  sub     rsp, 70h
0x180049f22  mov     rax, cs:__security_cookie
0x180049f29  xor     rax, rsp
0x180049f2c  mov     [rsp+88h+var_20], rax
0x180049f31  mov     rbx, rdx
0x180049f34  mov     rdi, rcx
0x180049f37  mov     [rsp+88h+var_58], 0
0x180049f3f  lea     rcx, [rsp+88h+var_50]; this
0x180049f44  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x180049f49  nop
0x180049f4a  lea     rbp, WPP_GLOBAL_Control
0x180049f51  lea     r14, WPP_547e2d81e4df314cfcd37421c8b4611e_Traceguids
0x180049f58  mov     r10, cs:WPP_GLOBAL_Control
0x180049f5f  cmp     r10, rbp
0x180049f62  jz      short loc_180049F90
0x180049f64  cmp     byte ptr [r10+19h], 6
0x180049f69  jb      short loc_180049F90
0x180049f6b  mov     ecx, 1; int
0x180049f70  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180049f75  mov     edx, 1Bh
0x180049f7a  mov     r9, rax
0x180049f7d  mov     r8, r14
0x180049f80  mov     rcx, [r10+10h]
0x180049f84  call    WPP_SF_s
0x180049f89  mov     r10, cs:WPP_GLOBAL_Control
0x180049f90  test    rbx, rbx
0x180049f93  jnz     short loc_180049FC1
0x180049f95  cmp     r10, rbp
0x180049f98  jz      short loc_180049FB7
0x180049f9a  cmp     byte ptr [r10+19h], 2
0x180049f9f  jb      short loc_180049FB7
0x180049fa1  lea     edx, [rbx+1Ch]
0x180049fa4  lea     r9, aPincomingmessa; "pIncomingMessage"
0x180049fab  mov     r8, r14
0x180049fae  mov     rcx, [r10+10h]
0x180049fb2  call    WPP_SF_s
0x180049fb7  mov     ebx, 80004003h
0x180049fbc  jmp     loc_18004A193
0x180049fc1  mov     rax, [rdi-10h]
0x180049fc5  lock inc dword ptr [rax+638h]
0x180049fcc  lea     rcx, [rdi+30h]; this
0x180049fd0  lea     r9, [rsp+88h+var_50]; struct CSbMessageBuffer *
0x180049fd5  lea     r8, [rsp+88h+var_58]; enum CWcnEapReassembler::ReassembleResponse *
0x180049fda  mov     rdx, rbx; struct CSbMessageBuffer *
0x180049fdd  call    ?DeliverFragment@CWcnEapReassembler@@QEAAJPEBVCSbMessageBuffer@@PEAW4ReassembleResponse@1@PEAV2@@Z; CWcnEapReassembler::DeliverFragment(CSbMessageBuffer const *,CWcnEapReassembler::ReassembleResponse *,CSbMessageBuffer *)
0x180049fe2  mov     ebx, eax
0x180049fe4  test    eax, eax
0x180049fe6  jns     short loc_18004A01B
0x180049fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fef  cmp     rcx, rbp
0x180049ff2  jz      loc_18004A128
0x180049ff8  cmp     byte ptr [rcx+19h], 2
0x180049ffc  jb      loc_18004A128
0x18004a002  mov     edx, 1Dh
0x18004a007  mov     r9d, eax
0x18004a00a  mov     r8, r14
0x18004a00d  mov     rcx, [rcx+10h]
0x18004a011  call    WPP_SF_d
0x18004a016  jmp     loc_18004A128
0x18004a01b  mov     ecx, [rsp+88h+var_58]
0x18004a01f  test    ecx, ecx
0x18004a021  jz      loc_18004A123
0x18004a027  sub     ecx, 1
0x18004a02a  jz      loc_18004A0F1
0x18004a030  sub     ecx, 1
0x18004a033  jz      loc_18004A0C6
0x18004a039  sub     ecx, 1
0x18004a03c  jz      short loc_18004A08D
0x18004a03e  cmp     ecx, 1
0x18004a041  jz      short loc_18004A04D
0x18004a043  mov     ebx, 8000FFFFh
0x18004a048  jmp     loc_18004A193
0x18004a04d  mov     r8d, [rdi-8]; unsigned int
0x18004a051  lea     rdx, [rsp+88h+var_50]; struct CSbMessageBuffer *
0x18004a056  mov     rcx, [rdi-10h]; this
0x18004a05a  call    ?DeliverIncomingMessage@CWcnSession@@QEAAJPEBVCSbMessageBuffer@@K@Z; CWcnSession::DeliverIncomingMessage(CSbMessageBuffer const *,ulong)
0x18004a05f  mov     ebx, eax
0x18004a061  test    eax, eax
0x18004a063  jns     loc_18004A152
0x18004a069  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a070  cmp     rcx, rbp
0x18004a073  jz      loc_18004A128
0x18004a079  cmp     byte ptr [rcx+19h], 2
0x18004a07d  jb      loc_18004A128
0x18004a083  mov     edx, 21h ; '!'
0x18004a088  jmp     loc_18004A007
0x18004a08d  mov     ebx, 8004B00Ah
0x18004a092  mov     r10, cs:WPP_GLOBAL_Control
0x18004a099  cmp     r10, rbp
0x18004a09c  jz      loc_18004A128
0x18004a0a2  cmp     byte ptr [r10+19h], 2
0x18004a0a7  jb      short loc_18004A128
0x18004a0a9  xor     ecx, ecx; int
0x18004a0ab  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004a0b0  mov     edx, 20h ; ' '
0x18004a0b5  mov     r9, rax
0x18004a0b8  mov     r8, r14
0x18004a0bb  mov     rcx, [r10+10h]
0x18004a0bf  call    WPP_SF_s
0x18004a0c4  jmp     short loc_18004A128
0x18004a0c6  lea     rcx, [rdi-20h]; this
0x18004a0ca  call    ?SendNextFragment@CWcnSoftApSession@@AEAAJXZ; CWcnSoftApSession::SendNextFragment(void)
0x18004a0cf  mov     ebx, eax
0x18004a0d1  test    eax, eax
0x18004a0d3  jns     short loc_18004A152
0x18004a0d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0dc  cmp     rcx, rbp
0x18004a0df  jz      short loc_18004A128
0x18004a0e1  cmp     byte ptr [rcx+19h], 2
0x18004a0e5  jb      short loc_18004A128
0x18004a0e7  mov     edx, 1Eh
0x18004a0ec  jmp     loc_18004A007
0x18004a0f1  lea     r8, [rsp+88h+var_50]
0x18004a0f6  xor     edx, edx
0x18004a0f8  mov     rcx, [rdi+18h]
0x18004a0fc  call    ?QueueOutgoingMessage@CWcnMessageSinkSession@@QEAAJW4tagWCN_ACTION@@PEBVCSbMessageBuffer@@@Z; CWcnMessageSinkSession::QueueOutgoingMessage(tagWCN_ACTION,CSbMessageBuffer const *)
0x18004a101  mov     ebx, eax
0x18004a103  test    eax, eax
0x18004a105  jns     short loc_18004A152
0x18004a107  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a10e  cmp     rcx, rbp
0x18004a111  jz      short loc_18004A128
0x18004a113  cmp     byte ptr [rcx+19h], 2
0x18004a117  jb      short loc_18004A128
0x18004a119  mov     edx, 1Fh
0x18004a11e  jmp     loc_18004A007
0x18004a123  mov     ebx, 8007139Fh
0x18004a128  mov     rcx, [rdi-10h]
0x18004a12c  mov     esi, 600h
0x18004a131  add     rcx, rsi; lpCriticalSection
0x18004a134  call    cs:__imp_EnterCriticalSection
0x18004a13a  mov     edx, ebx; int
0x18004a13c  mov     rcx, [rdi-10h]; this
0x18004a140  call    ?SetFailureCode@CWcnSession@@QEAAXJ@Z; CWcnSession::SetFailureCode(long)
0x18004a145  mov     rcx, [rdi-10h]
0x18004a149  add     rcx, rsi; lpCriticalSection
0x18004a14c  call    cs:__imp_LeaveCriticalSection
0x18004a152  mov     rcx, [rdi-10h]; this
0x18004a156  call    ?Release@CWcnSession@@QEAAXXZ; CWcnSession::Release(void)
0x18004a15b  mov     r10, cs:WPP_GLOBAL_Control
0x18004a162  cmp     r10, rbp
0x18004a165  jz      short loc_18004A193
0x18004a167  test    ebx, ebx
0x18004a169  js      short loc_18004A172
0x18004a16b  cmp     byte ptr [r10+19h], 6
0x18004a170  jb      short loc_18004A193
0x18004a172  or      ecx, 0FFFFFFFFh; int
0x18004a175  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004a17a  mov     edx, 22h ; '"'
0x18004a17f  mov     [rsp+88h+var_68], ebx
0x18004a183  mov     r9, rax
0x18004a186  mov     r8, r14
0x18004a189  mov     rcx, [r10+10h]
0x18004a18d  call    WPP_SF_sd
0x18004a192  nop
0x18004a193  lea     rcx, [rsp+88h+var_50]; this
0x18004a198  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18004a19d  mov     eax, ebx
0x18004a19f  mov     rcx, [rsp+88h+var_20]
0x18004a1a4  xor     rcx, rsp; StackCookie
0x18004a1a7  call    __security_check_cookie
0x18004a1ac  lea     r11, [rsp+88h+var_18]
0x18004a1b1  mov     rbx, [r11+30h]
0x18004a1b5  mov     rbp, [r11+38h]
0x18004a1b9  mov     rsp, r11
0x18004a1bc  pop     r14
0x18004a1be  pop     rdi
0x18004a1bf  pop     rsi
0x18004a1c0  retn
```
