# CWcnSession::DeliverIncomingMessage(CSbMessageBuffer const *,ulong)

- ea: `0x1800157bc`
- end: `0x180015b7e`
- name: `?DeliverIncomingMessage@CWcnSession@@QEAAJPEBVCSbMessageBuffer@@K@Z`
- size: `962`
- prototype: `__int64 __fastcall(CWcnSession *__hidden this, const struct CSbMessageBuffer *, unsigned int)`
- caller_count: `5`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800471a0`
- `0x180049f10`
- `0x18004be80`
- `0x18004f150`
- `0x180056adc`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x180015280`
- `0x1800157bc`
- `0x180015cd4`
- `0x180017054`
- `0x180017424`
- `0x180018804`
- `0x180019808`
- `0x180053004`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800158cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800158d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800158cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800158d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800158bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800158bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001590b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015af3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001590b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015af3`

## pseudocode

```c
__int64 __fastcall CWcnSession::DeliverIncomingMessage(
        CWcnSession *this,
        const struct CSbMessageBuffer *a2,
        unsigned int a3)
{
  _QWORD *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // r10
  char v12; // r15
  int v13; // r8d
  __int64 *v14; // rax
  __int64 v15; // rdx
  unsigned __int16 v16; // cx
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // r10
  unsigned __int16 v23; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v24[40]; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v25[16]; // [rsp+60h] [rbp-29h] BYREF
  char *v26; // [rsp+70h] [rbp-19h]
  __int64 v27; // [rsp+78h] [rbp-11h]
  char *v28; // [rsp+80h] [rbp-9h]
  __int64 v29; // [rsp+88h] [rbp-1h]
  __int16 *v30; // [rsp+90h] [rbp+7h]
  __int64 v31; // [rsp+98h] [rbp+Fh]
  __int64 v32; // [rsp+A0h] [rbp+17h]
  int v33; // [rsp+A8h] [rbp+1Fh]
  int v34; // [rsp+ACh] [rbp+23h]

  CSbSafeBuffer::CSbSafeBuffer((CSbSafeBuffer *)v24);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 114, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_s(v6[2], 115, WPP_a137d119f5dc35a130051116e3170526_Traceguids, "pRequestMessage");
    v9 = -2147467261;
    goto LABEL_50;
  }
  v9 = 0;
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 5u )
  {
    v10 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v11 + 16), 116, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v10, a3);
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 398);
  WaitForSingleObject(*((HANDLE *)this + 32), 0xFFFFFFFF);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
  if ( *((_DWORD *)this + 56) == 1 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    if ( *((_DWORD *)this + 56) != 2 )
      v9 = -2147022646;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
  if ( v9 >= 0 )
  {
    if ( (a3 & 0x4000) != 0 )
    {
      a3 &= ~0x4000u;
      if ( !*((_BYTE *)this + 432) )
      {
        a3 |= 0x8001u;
        *((_BYTE *)this + 435) = 1;
      }
    }
    *((_DWORD *)this + 68) = 0;
    *((_QWORD *)this + 36) = a2;
    *(_WORD *)((char *)this + 437) = 0;
    if ( (Microsoft_Windows_WCN_Config_RegistrarEnableBits & 1) != 0 )
    {
      v14 = (__int64 *)*((_QWORD *)a2 + 3);
      v15 = *v14;
      if ( v14 )
        v16 = v14[1] - v15;
      else
        v16 = 0;
      v23 = v16;
      v26 = (char *)this + 1576;
      v27 = 16;
      v28 = (char *)a2 + 32;
      v29 = 16;
      v30 = (__int16 *)&v23;
      v31 = 2;
      v32 = v15;
      v33 = v16;
      v34 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)WCN_ETW_EVENT_GUID_Context,
        (unsigned int)SessionReceive,
        v13,
        5,
        (__int64)v25);
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 16LL))(*((_QWORD *)this + 27))
      && (v17 = CWcnSession::AdjustProtocolVersion(this), v9 = v17, v17 < 0) )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_44;
      v19 = 117;
    }
    else
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 27) + 8LL))(*((_QWORD *)this + 27), a3);
      v9 = v17;
      if ( v17 >= 0 )
      {
        *((_QWORD *)this + 36) = 0;
        if ( v12 && !*((_BYTE *)this + 437) && *((_DWORD *)this + 56) == 1 )
          CWcnSession::FinishConnect(this);
        if ( *((_DWORD *)this + 56) != 2 )
          goto LABEL_44;
        v17 = CWcnSession::PrepareOutgoingMessage(this, a3);
        v9 = v17;
        if ( v17 >= 0 )
          goto LABEL_44;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_44;
        v19 = 119;
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_44;
        v19 = 118;
      }
    }
    WPP_SF_d(v18[2], v19, WPP_a137d119f5dc35a130051116e3170526_Traceguids, (unsigned int)v17);
  }
LABEL_44:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  if ( v9 < 0 )
    CWcnSession::StartDisconnect(this, 0);
  CWcnSession::Release(this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v9 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v20 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v21 + 16), 120, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v20, v9);
  }
LABEL_50:
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)v24);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800157bc  mov     [rsp-8+arg_8], rbx
0x1800157c1  mov     [rsp-8+arg_18], rsi
0x1800157c6  push    rbp
0x1800157c7  push    rdi
0x1800157c8  push    r12
0x1800157ca  push    r14
0x1800157cc  push    r15
0x1800157ce  lea     rbp, [rsp-37h]
0x1800157d3  sub     rsp, 0C0h
0x1800157da  mov     rax, cs:__security_cookie
0x1800157e1  xor     rax, rsp
0x1800157e4  mov     [rbp+57h+var_30], rax
0x1800157e8  mov     esi, r8d
0x1800157eb  mov     r14, rdx
0x1800157ee  mov     rdi, rcx
0x1800157f1  lea     rcx, [rbp+57h+var_A8]; this
0x1800157f5  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x1800157fa  nop
0x1800157fb  lea     rax, WPP_GLOBAL_Control
0x180015802  mov     r10, cs:WPP_GLOBAL_Control
0x180015809  cmp     r10, rax
0x18001580c  jz      short loc_180015845
0x18001580e  cmp     byte ptr [r10+19h], 6
0x180015813  jb      short loc_180015845
0x180015815  mov     ecx, 1; int
0x18001581a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001581f  mov     edx, 72h ; 'r'
0x180015824  mov     r9, rax
0x180015827  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x18001582e  mov     rcx, [r10+10h]
0x180015832  call    WPP_SF_s
0x180015837  mov     r10, cs:WPP_GLOBAL_Control
0x18001583e  lea     rax, WPP_GLOBAL_Control
0x180015845  test    r14, r14
0x180015848  jnz     short loc_18001587B
0x18001584a  cmp     r10, rax
0x18001584d  jz      short loc_180015871
0x18001584f  cmp     byte ptr [r10+19h], 2
0x180015854  jb      short loc_180015871
0x180015856  lea     edx, [r14+73h]
0x18001585a  lea     r9, aPrequestmessag; "pRequestMessage"
0x180015861  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015868  mov     rcx, [r10+10h]
0x18001586c  call    WPP_SF_s
0x180015871  mov     ebx, 80004003h
0x180015876  jmp     loc_180015B4B
0x18001587b  xor     ebx, ebx
0x18001587d  cmp     r10, rax
0x180015880  jz      short loc_1800158AA
0x180015882  cmp     byte ptr [r10+19h], 5
0x180015887  jb      short loc_1800158AA
0x180015889  xor     ecx, ecx; int
0x18001588b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015890  lea     edx, [rbx+74h]
0x180015893  mov     dword ptr [rsp+0E0h+var_C0], esi
0x180015897  mov     r9, rax
0x18001589a  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800158a1  mov     rcx, [r10+10h]
0x1800158a5  call    WPP_SF_sd
0x1800158aa  lock inc dword ptr [rdi+638h]
0x1800158b1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800158b4  mov     rcx, [rdi+100h]; hHandle
0x1800158bb  call    cs:__imp_WaitForSingleObject
0x1800158c1  lea     r12, [rdi+600h]
0x1800158c8  mov     rcx, r12; lpCriticalSection
0x1800158cb  call    cs:__imp_EnterCriticalSection
0x1800158d1  mov     rcx, [rdi+20h]
0x1800158d5  add     rcx, 10h; lpCriticalSection
0x1800158d9  call    cs:__imp_EnterCriticalSection
0x1800158df  mov     eax, [rdi+0E0h]
0x1800158e5  cmp     eax, 1
0x1800158e8  jnz     short loc_1800158EF
0x1800158ea  mov     r15b, al
0x1800158ed  jmp     short loc_180015903
0x1800158ef  xor     r15b, r15b
0x1800158f2  mov     eax, [rdi+0E0h]
0x1800158f8  mov     ecx, 800708CAh
0x1800158fd  cmp     eax, 2
0x180015900  cmovnz  ebx, ecx
0x180015903  mov     rcx, [rdi+20h]
0x180015907  add     rcx, 10h; lpCriticalSection
0x18001590b  call    cs:__imp_LeaveCriticalSection
0x180015911  test    ebx, ebx
0x180015913  js      loc_180015AE9
0x180015919  bt      esi, 0Eh
0x18001591d  jnb     short loc_180015939
0x18001591f  btr     esi, 0Eh
0x180015923  cmp     byte ptr [rdi+1B0h], 0
0x18001592a  jnz     short loc_180015939
0x18001592c  or      esi, 8001h
0x180015932  mov     byte ptr [rdi+1B3h], 1
0x180015939  mov     dword ptr [rdi+110h], 0
0x180015943  mov     [rdi+120h], r14
0x18001594a  mov     word ptr [rdi+1B5h], 0
0x180015953  test    byte ptr cs:Microsoft_Windows_WCN_Config_RegistrarEnableBits, 1
0x18001595a  jz      loc_1800159E1
0x180015960  mov     rax, [r14+18h]
0x180015964  mov     rdx, [rax]
0x180015967  test    rax, rax
0x18001596a  jz      short loc_180015975
0x18001596c  mov     rcx, [rax+8]
0x180015970  sub     rcx, rdx
0x180015973  jmp     short loc_180015977
0x180015975  xor     ecx, ecx
0x180015977  movzx   ecx, cx
0x18001597a  mov     [rbp+57h+var_B0], cx
0x18001597e  lea     rax, [rdi+628h]
0x180015985  mov     [rbp+57h+var_70], rax
0x180015989  mov     [rbp+57h+var_68], 10h
0x180015991  lea     rax, [r14+20h]
0x180015995  mov     [rbp+57h+var_60], rax
0x180015999  mov     [rbp+57h+var_58], 10h
0x1800159a1  lea     rax, [rbp+57h+var_B0]
0x1800159a5  mov     [rbp+57h+var_50], rax
0x1800159a9  mov     [rbp+57h+var_48], 2
0x1800159b1  mov     [rbp+57h+var_40], rdx
0x1800159b5  mov     [rbp+57h+var_38], ecx
0x1800159b8  mov     [rbp+57h+var_34], 0
0x1800159bf  lea     rax, [rbp+57h+var_80]
0x1800159c3  mov     [rsp+0E0h+var_C0], rax
0x1800159c8  mov     r9d, 5
0x1800159ce  lea     rdx, SessionReceive
0x1800159d5  lea     rcx, WCN_ETW_EVENT_GUID_Context
0x1800159dc  call    McGenEventWrite_EtwEventWriteTransfer
0x1800159e1  mov     rcx, [rdi+0D8h]
0x1800159e8  mov     rax, [rcx]
0x1800159eb  mov     rax, [rax+10h]
0x1800159ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159f4  test    al, al
0x1800159f6  jz      short loc_180015A44
0x1800159f8  mov     rcx, rdi; this
0x1800159fb  call    ?AdjustProtocolVersion@CWcnSession@@AEAAJXZ; CWcnSession::AdjustProtocolVersion(void)
0x180015a00  mov     ebx, eax
0x180015a02  test    eax, eax
0x180015a04  jns     short loc_180015A44
0x180015a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a0d  lea     rsi, WPP_GLOBAL_Control
0x180015a14  cmp     rcx, rsi
0x180015a17  jz      loc_180015AF0
0x180015a1d  cmp     byte ptr [rcx+19h], 2
0x180015a21  jb      loc_180015AF0
0x180015a27  mov     edx, 75h ; 'u'
0x180015a2c  mov     r9d, eax
0x180015a2f  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015a36  mov     rcx, [rcx+10h]
0x180015a3a  call    WPP_SF_d
0x180015a3f  jmp     loc_180015AF0
0x180015a44  mov     rcx, [rdi+0D8h]
0x180015a4b  mov     rax, [rcx]
0x180015a4e  mov     edx, esi
0x180015a50  mov     rax, [rax+8]
0x180015a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a59  mov     ebx, eax
0x180015a5b  test    eax, eax
0x180015a5d  jns     short loc_180015A7F
0x180015a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a66  lea     rsi, WPP_GLOBAL_Control
0x180015a6d  cmp     rcx, rsi
0x180015a70  jz      short loc_180015AF0
0x180015a72  cmp     byte ptr [rcx+19h], 2
0x180015a76  jb      short loc_180015AF0
0x180015a78  mov     edx, 76h ; 'v'
0x180015a7d  jmp     short loc_180015A2C
0x180015a7f  mov     qword ptr [rdi+120h], 0
0x180015a8a  test    r15b, r15b
0x180015a8d  jz      short loc_180015AAB
0x180015a8f  cmp     byte ptr [rdi+1B5h], 0
0x180015a96  jnz     short loc_180015AAB
0x180015a98  mov     eax, [rdi+0E0h]
0x180015a9e  cmp     eax, 1
0x180015aa1  jnz     short loc_180015AAB
0x180015aa3  mov     rcx, rdi; this
0x180015aa6  call    ?FinishConnect@CWcnSession@@QEAAXXZ; CWcnSession::FinishConnect(void)
0x180015aab  mov     eax, [rdi+0E0h]
0x180015ab1  cmp     eax, 2
0x180015ab4  jnz     short loc_180015AE9
0x180015ab6  mov     edx, esi; unsigned int
0x180015ab8  mov     rcx, rdi; this
0x180015abb  call    ?PrepareOutgoingMessage@CWcnSession@@QEAAJK@Z; CWcnSession::PrepareOutgoingMessage(ulong)
0x180015ac0  mov     ebx, eax
0x180015ac2  test    eax, eax
0x180015ac4  jns     short loc_180015AE9
0x180015ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015acd  lea     rsi, WPP_GLOBAL_Control
0x180015ad4  cmp     rcx, rsi
0x180015ad7  jz      short loc_180015AF0
0x180015ad9  cmp     byte ptr [rcx+19h], 2
0x180015add  jb      short loc_180015AF0
0x180015adf  mov     edx, 77h ; 'w'
0x180015ae4  jmp     loc_180015A2C
0x180015ae9  lea     rsi, WPP_GLOBAL_Control
0x180015af0  mov     rcx, r12; lpCriticalSection
0x180015af3  call    cs:__imp_LeaveCriticalSection
0x180015af9  test    ebx, ebx
0x180015afb  jns     short loc_180015B07
0x180015afd  xor     edx, edx; bool
0x180015aff  mov     rcx, rdi; this
0x180015b02  call    ?StartDisconnect@CWcnSession@@QEAAX_N@Z; CWcnSession::StartDisconnect(bool)
0x180015b07  mov     rcx, rdi; this
0x180015b0a  call    ?Release@CWcnSession@@QEAAXXZ; CWcnSession::Release(void)
0x180015b0f  mov     r10, cs:WPP_GLOBAL_Control
0x180015b16  cmp     r10, rsi
0x180015b19  jz      short loc_180015B4B
0x180015b1b  test    ebx, ebx
0x180015b1d  js      short loc_180015B26
0x180015b1f  cmp     byte ptr [r10+19h], 6
0x180015b24  jb      short loc_180015B4B
0x180015b26  or      ecx, 0FFFFFFFFh; int
0x180015b29  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015b2e  mov     edx, 78h ; 'x'
0x180015b33  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180015b37  mov     r9, rax
0x180015b3a  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015b41  mov     rcx, [r10+10h]
0x180015b45  call    WPP_SF_sd
0x180015b4a  nop
0x180015b4b  lea     rcx, [rbp+57h+var_A8]; this
0x180015b4f  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180015b54  mov     eax, ebx
0x180015b56  mov     rcx, [rbp+57h+var_30]
0x180015b5a  xor     rcx, rsp; StackCookie
0x180015b5d  call    __security_check_cookie
0x180015b62  lea     r11, [rsp+0E0h+var_20]
0x180015b6a  mov     rbx, [r11+38h]
0x180015b6e  mov     rsi, [r11+48h]
0x180015b72  mov     rsp, r11
0x180015b75  pop     r15
0x180015b77  pop     r14
0x180015b79  pop     r12
0x180015b7b  pop     rdi
0x180015b7c  pop     rbp
0x180015b7d  retn
```
