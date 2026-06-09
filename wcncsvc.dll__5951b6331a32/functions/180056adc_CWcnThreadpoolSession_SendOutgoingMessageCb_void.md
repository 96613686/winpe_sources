# CWcnThreadpoolSession::SendOutgoingMessageCb(void)

- ea: `0x180056adc`
- end: `0x180056ccd`
- name: `?SendOutgoingMessageCb@CWcnThreadpoolSession@@AEAAXXZ`
- size: `497`
- prototype: `void __fastcall(CWcnThreadpoolSession *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180056ce0`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x18000a558`
- `0x18000a5ac`
- `0x1800157bc`
- `0x18001745c`
- `0x180018804`
- `0x180053004`
- `0x180056adc`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056c38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056c38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056c54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056c54`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180056c6a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180056c6a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180056b52`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180056b52`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWcnThreadpoolSession::SendOutgoingMessageCb(CWcnThreadpoolSession *this)
{
  char v2; // si
  const char *Indent; // rax
  __int64 v4; // r10
  HRESULT v5; // eax
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax
  const char *v12; // rax
  __int64 v13; // r10
  _BYTE v14[48]; // [rsp+20h] [rbp-58h] BYREF

  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v14);
  v2 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 19, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids, Indent);
  }
  v5 = CoInitializeEx(0, 4u);
  v6 = v5;
  if ( v5 < 0 )
  {
    v2 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 20;
LABEL_21:
      WPP_SF_d(v7[2], v8, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids, (unsigned int)v5);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v9 = *((_QWORD *)this + 8);
  v10 = (__int64 *)*((_QWORD *)this + 7);
  v11 = *v10;
  if ( !v9 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v11 + 16))(v10, v14);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 22;
        goto LABEL_21;
      }
      goto LABEL_22;
    }
LABEL_17:
    v5 = CWcnSession::DeliverIncomingMessage(
           *((CWcnSession **)this + 2),
           (const struct CSbMessageBuffer *)v14,
           *((_DWORD *)this + 6));
    v6 = v5;
    if ( v5 >= 0 )
    {
LABEL_23:
      CoUninitialize();
      goto LABEL_24;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 23;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64, _BYTE *))(v11 + 24))(v10, v9, v14);
  v6 = v5;
  if ( v5 >= 0 )
    goto LABEL_17;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 21;
    goto LABEL_21;
  }
LABEL_22:
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 2) + 1536LL));
  CWcnSession::SetFailureCode(*((CWcnSession **)this + 2), v6);
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 2) + 1536LL));
  CWcnSession::StartDisconnect(*((CWcnSession **)this + 2), 0);
  if ( v2 )
    goto LABEL_23;
LABEL_24:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v12 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v13 + 16), 24, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids, v12);
  }
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v14);
}

```

## disassembly

```asm
0x180056adc  mov     [rsp+arg_8], rbx
0x180056ae1  mov     [rsp+arg_10], rsi
0x180056ae6  push    rdi
0x180056ae7  push    r14
0x180056ae9  push    r15
0x180056aeb  sub     rsp, 60h
0x180056aef  mov     rax, cs:__security_cookie
0x180056af6  xor     rax, rsp
0x180056af9  mov     [rsp+78h+var_28], rax
0x180056afe  mov     rdi, rcx
0x180056b01  lea     rcx, [rsp+78h+var_58]; this
0x180056b06  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x180056b0b  nop
0x180056b0c  lea     r14, WPP_GLOBAL_Control
0x180056b13  mov     esi, 1
0x180056b18  lea     r15, WPP_404726790aff3681bc8dcdbed8ab165f_Traceguids
0x180056b1f  mov     r10, cs:WPP_GLOBAL_Control
0x180056b26  cmp     r10, r14
0x180056b29  jz      short loc_180056B4B
0x180056b2b  cmp     byte ptr [r10+19h], 6
0x180056b30  jb      short loc_180056B4B
0x180056b32  mov     ecx, esi; int
0x180056b34  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180056b39  lea     edx, [rsi+12h]
0x180056b3c  mov     r9, rax
0x180056b3f  mov     r8, r15
0x180056b42  mov     rcx, [r10+10h]
0x180056b46  call    WPP_SF_s
0x180056b4b  mov     edx, 4; dwCoInit
0x180056b50  xor     ecx, ecx; pvReserved
0x180056b52  call    cs:__imp_CoInitializeEx
0x180056b58  mov     ebx, eax
0x180056b5a  test    eax, eax
0x180056b5c  jns     short loc_180056B85
0x180056b5e  xor     sil, sil
0x180056b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b68  cmp     rcx, r14
0x180056b6b  jz      loc_180056C2D
0x180056b71  cmp     byte ptr [rcx+19h], 2
0x180056b75  jb      loc_180056C2D
0x180056b7b  mov     edx, 14h
0x180056b80  jmp     loc_180056C1E
0x180056b85  mov     rdx, [rdi+40h]
0x180056b89  mov     rcx, [rdi+38h]
0x180056b8d  mov     rax, [rcx]
0x180056b90  test    rdx, rdx
0x180056b93  jz      short loc_180056BC2
0x180056b95  lea     r8, [rsp+78h+var_58]
0x180056b9a  mov     rax, [rax+18h]
0x180056b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ba3  mov     ebx, eax
0x180056ba5  test    eax, eax
0x180056ba7  jns     short loc_180056BEF
0x180056ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180056bb0  cmp     rcx, r14
0x180056bb3  jz      short loc_180056C2D
0x180056bb5  cmp     byte ptr [rcx+19h], 2
0x180056bb9  jb      short loc_180056C2D
0x180056bbb  mov     edx, 15h
0x180056bc0  jmp     short loc_180056C1E
0x180056bc2  lea     rdx, [rsp+78h+var_58]
0x180056bc7  mov     rax, [rax+10h]
0x180056bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056bd0  mov     ebx, eax
0x180056bd2  test    eax, eax
0x180056bd4  jns     short loc_180056BEF
0x180056bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180056bdd  cmp     rcx, r14
0x180056be0  jz      short loc_180056C2D
0x180056be2  cmp     byte ptr [rcx+19h], 2
0x180056be6  jb      short loc_180056C2D
0x180056be8  mov     edx, 16h
0x180056bed  jmp     short loc_180056C1E
0x180056bef  mov     r8d, [rdi+18h]; unsigned int
0x180056bf3  lea     rdx, [rsp+78h+var_58]; struct CSbMessageBuffer *
0x180056bf8  mov     rcx, [rdi+10h]; this
0x180056bfc  call    ?DeliverIncomingMessage@CWcnSession@@QEAAJPEBVCSbMessageBuffer@@K@Z; CWcnSession::DeliverIncomingMessage(CSbMessageBuffer const *,ulong)
0x180056c01  mov     ebx, eax
0x180056c03  test    eax, eax
0x180056c05  jns     short loc_180056C6A
0x180056c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c0e  cmp     rcx, r14
0x180056c11  jz      short loc_180056C2D
0x180056c13  cmp     byte ptr [rcx+19h], 2
0x180056c17  jb      short loc_180056C2D
0x180056c19  mov     edx, 17h
0x180056c1e  mov     r9d, eax
0x180056c21  mov     r8, r15
0x180056c24  mov     rcx, [rcx+10h]
0x180056c28  call    WPP_SF_d
0x180056c2d  mov     rcx, [rdi+10h]
0x180056c31  add     rcx, 600h; lpCriticalSection
0x180056c38  call    cs:__imp_EnterCriticalSection
0x180056c3e  mov     edx, ebx; int
0x180056c40  mov     rcx, [rdi+10h]; this
0x180056c44  call    ?SetFailureCode@CWcnSession@@QEAAXJ@Z; CWcnSession::SetFailureCode(long)
0x180056c49  mov     rcx, [rdi+10h]
0x180056c4d  add     rcx, 600h; lpCriticalSection
0x180056c54  call    cs:__imp_LeaveCriticalSection
0x180056c5a  xor     edx, edx; bool
0x180056c5c  mov     rcx, [rdi+10h]; this
0x180056c60  call    ?StartDisconnect@CWcnSession@@QEAAX_N@Z; CWcnSession::StartDisconnect(bool)
0x180056c65  test    sil, sil
0x180056c68  jz      short loc_180056C70
0x180056c6a  call    cs:__imp_CoUninitialize
0x180056c70  mov     r10, cs:WPP_GLOBAL_Control
0x180056c77  cmp     r10, r14
0x180056c7a  jz      short loc_180056CA0
0x180056c7c  cmp     byte ptr [r10+19h], 6
0x180056c81  jb      short loc_180056CA0
0x180056c83  or      ecx, 0FFFFFFFFh; int
0x180056c86  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180056c8b  mov     edx, 18h
0x180056c90  mov     r9, rax
0x180056c93  mov     r8, r15
0x180056c96  mov     rcx, [r10+10h]
0x180056c9a  call    WPP_SF_s
0x180056c9f  nop
0x180056ca0  lea     rcx, [rsp+78h+var_58]; this
0x180056ca5  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180056caa  mov     rcx, [rsp+78h+var_28]
0x180056caf  xor     rcx, rsp; StackCookie
0x180056cb2  call    __security_check_cookie
0x180056cb7  lea     r11, [rsp+78h+var_18]
0x180056cbc  mov     rbx, [r11+28h]
0x180056cc0  mov     rsi, [r11+30h]
0x180056cc4  mov     rsp, r11
0x180056cc7  pop     r15
0x180056cc9  pop     r14
0x180056ccb  pop     rdi
0x180056ccc  retn
```
