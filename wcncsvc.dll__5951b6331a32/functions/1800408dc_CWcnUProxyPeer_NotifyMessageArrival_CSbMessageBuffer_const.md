# CWcnUProxyPeer::NotifyMessageArrival(CSbMessageBuffer const *)

- ea: `0x1800408dc`
- end: `0x180040c8f`
- name: `?NotifyMessageArrival@CWcnUProxyPeer@@QEAAXPEBVCSbMessageBuffer@@@Z`
- size: `947`
- prototype: `void __fastcall(CWcnUProxyPeer *this, const struct CSbMessageBuffer *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003e180`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a74c`
- `0x1800149ec`
- `0x180016994`
- `0x180017424`
- `0x180018204`
- `0x1800408dc`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040bbd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040bbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004093b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040b49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004093b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040b49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040bc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040bc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040c37`

## string_xrefs

- `0x180040b21`: `pIncomingMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CWcnUProxyPeer::NotifyMessageArrival(CWcnUProxyPeer *this, const struct CSbMessageBuffer *a2)
{
  int v4; // ebx
  const char *Indent; // rax
  __int64 v6; // r10
  const char *v7; // rax
  __int64 v8; // r10
  CWcnSession *v9; // rax
  CWcnSession *v10; // rdi
  _BYTE *v11; // r10
  int started; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r10
  __int64 v17; // rdx
  __int64 v18; // rdi
  const char *v19; // rax
  __int64 v20; // r10
  void (__fastcall ***v21)(_QWORD); // rcx
  int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // r10
  unsigned int v25; // eax
  __int64 v26; // r10

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 14, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, Indent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_QWORD *)this + 5) )
  {
    v11 = WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v7 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 21, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, v7);
  }
  v9 = (CWcnSession *)operator new(0x640u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
    v10 = CWcnSession::CWcnSession(v9);
  else
    v10 = 0;
  if ( v10 )
  {
    started = CWcnSession::Init(v10, *((struct CWcnPeer **)this + 2));
    v4 = started;
    if ( started >= 0 )
    {
      started = CWcnSession::StartConnect(v10, this, 3, 32773, 1);
      v4 = started;
      if ( started >= 0 )
        goto LABEL_24;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_24;
      v14 = 24;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_24;
      v14 = 23;
    }
    WPP_SF_d(v13[2], v14, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, (unsigned int)started);
LABEL_24:
    CWcnSession::Release(v10);
    goto LABEL_25;
  }
  v4 = -2147024882;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_30;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, "pNewSession");
LABEL_25:
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v4 < 0 || v11[25] >= 6u) )
  {
    v15 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v16 + 16), 25, (unsigned int)WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, v15, v4);
    v11 = WPP_GLOBAL_Control;
  }
LABEL_30:
  if ( v4 < 0 )
  {
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 2u )
    {
      v17 = 15;
LABEL_60:
      WPP_SF_d(*((_QWORD *)v11 + 2), v17, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, (unsigned int)v4);
      goto LABEL_61;
    }
    goto LABEL_61;
  }
LABEL_35:
  v18 = *((_QWORD *)this + 5);
  if ( !v18 )
    goto LABEL_61;
  if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 6u )
  {
    v19 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v20 + 16), 15, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v19);
    v11 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 88));
    if ( !*(_BYTE *)(v18 + 176) )
    {
      v21 = *(void (__fastcall ****)(_QWORD))(v18 + 168);
      if ( v21 )
      {
        (**v21)(v21);
        *(_BYTE *)(v18 + 176) = 1;
      }
    }
    *(_OWORD *)(v18 + 72) = *((_OWORD *)a2 + 2);
    v22 = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)(v18 + 40), a2);
    v4 = v22;
    if ( v22 >= 0 )
    {
      SetEvent(*(HANDLE *)(v18 + 24));
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids,
        (unsigned int)v22);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 88));
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v4 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
    {
      v23 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v24 + 16), 18, (unsigned int)WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, v23, v4);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v4 >= 0 )
      goto LABEL_61;
  }
  else
  {
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 2u )
    {
      WPP_SF_s(*((_QWORD *)v11 + 2), 16, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids, "pIncomingMessage");
      v11 = WPP_GLOBAL_Control;
    }
    v4 = -2147467261;
  }
  if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 2u )
  {
    v17 = 16;
    goto LABEL_60;
  }
LABEL_61:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v4 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v25 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v26 + 16), 17, (unsigned int)WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids, v25, v4);
  }
}

```

## disassembly

```asm
0x1800408dc  mov     [rsp+arg_8], rbx
0x1800408e1  mov     [rsp+arg_10], rbp
0x1800408e6  push    rsi
0x1800408e7  push    rdi
0x1800408e8  push    r12
0x1800408ea  push    r14
0x1800408ec  push    r15
0x1800408ee  sub     rsp, 30h
0x1800408f2  mov     rbp, rdx
0x1800408f5  mov     rsi, rcx
0x1800408f8  xor     ebx, ebx
0x1800408fa  lea     r15, WPP_GLOBAL_Control
0x180040901  lea     edi, [rbx+1]
0x180040904  lea     r12, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x18004090b  mov     r10, cs:WPP_GLOBAL_Control
0x180040912  cmp     r10, r15
0x180040915  jz      short loc_180040937
0x180040917  cmp     byte ptr [r10+19h], 6
0x18004091c  jb      short loc_180040937
0x18004091e  mov     ecx, edi; int
0x180040920  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040925  lea     edx, [rbx+0Eh]
0x180040928  mov     r9, rax
0x18004092b  mov     r8, r12
0x18004092e  mov     rcx, [r10+10h]
0x180040932  call    WPP_SF_s
0x180040937  lea     rcx, [rsi+30h]; lpCriticalSection
0x18004093b  call    cs:__imp_EnterCriticalSection
0x180040941  cmp     [rsi+28h], rbx
0x180040945  jnz     loc_180040AC1
0x18004094b  mov     r10, cs:WPP_GLOBAL_Control
0x180040952  cmp     r10, r15
0x180040955  jz      short loc_180040979
0x180040957  cmp     byte ptr [r10+19h], 6
0x18004095c  jb      short loc_180040979
0x18004095e  mov     ecx, edi; int
0x180040960  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040965  mov     edx, 15h
0x18004096a  mov     r9, rax
0x18004096d  mov     r8, r12
0x180040970  mov     rcx, [r10+10h]
0x180040974  call    WPP_SF_s
0x180040979  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180040980  mov     ecx, 640h; unsigned __int64
0x180040985  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004098a  mov     [rsp+58h+arg_0], rax
0x18004098f  test    rax, rax
0x180040992  jz      short loc_1800409A1
0x180040994  mov     rcx, rax; this
0x180040997  call    ??0CWcnSession@@QEAA@XZ; CWcnSession::CWcnSession(void)
0x18004099c  mov     rdi, rax
0x18004099f  jmp     short loc_1800409A3
0x1800409a1  xor     edi, edi
0x1800409a3  test    rdi, rdi
0x1800409a6  jnz     short loc_1800409E0
0x1800409a8  mov     ebx, 8007000Eh
0x1800409ad  mov     r10, cs:WPP_GLOBAL_Control
0x1800409b4  cmp     r10, r15
0x1800409b7  jz      loc_180040A9C
0x1800409bd  cmp     byte ptr [r10+19h], 2
0x1800409c2  jb      loc_180040A65
0x1800409c8  lea     edx, [rdi+16h]
0x1800409cb  lea     r9, aPnewsession; "pNewSession"
0x1800409d2  mov     r8, r12
0x1800409d5  mov     rcx, [r10+10h]
0x1800409d9  call    WPP_SF_s
0x1800409de  jmp     short loc_180040A5E
0x1800409e0  mov     rdx, [rsi+10h]; struct CWcnPeer *
0x1800409e4  mov     rcx, rdi; this
0x1800409e7  call    ?Init@CWcnSession@@QEAAJPEAVCWcnPeer@@@Z; CWcnSession::Init(CWcnPeer *)
0x1800409ec  mov     ebx, eax
0x1800409ee  test    eax, eax
0x1800409f0  jns     short loc_180040A0B
0x1800409f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800409f9  cmp     rcx, r15
0x1800409fc  jz      short loc_180040A56
0x1800409fe  cmp     byte ptr [rcx+19h], 2
0x180040a02  jb      short loc_180040A56
0x180040a04  mov     edx, 17h
0x180040a09  jmp     short loc_180040A47
0x180040a0b  mov     [rsp+58h+var_38], 1
0x180040a13  mov     r9d, 8005h
0x180040a19  mov     r8d, 3
0x180040a1f  mov     rdx, rsi
0x180040a22  mov     rcx, rdi
0x180040a25  call    ?StartConnect@CWcnSession@@QEAAJPEAVIWcnTransportPeer@@W4tagWcnTransportId@@KW4tagWCN_SESSION_CONNECT_REASON@1@@Z; CWcnSession::StartConnect(IWcnTransportPeer *,tagWcnTransportId,ulong,CWcnSession::tagWCN_SESSION_CONNECT_REASON)
0x180040a2a  mov     ebx, eax
0x180040a2c  test    eax, eax
0x180040a2e  jns     short loc_180040A56
0x180040a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a37  cmp     rcx, r15
0x180040a3a  jz      short loc_180040A56
0x180040a3c  cmp     byte ptr [rcx+19h], 2
0x180040a40  jb      short loc_180040A56
0x180040a42  mov     edx, 18h
0x180040a47  mov     r9d, eax
0x180040a4a  mov     r8, r12
0x180040a4d  mov     rcx, [rcx+10h]
0x180040a51  call    WPP_SF_d
0x180040a56  mov     rcx, rdi; this
0x180040a59  call    ?Release@CWcnSession@@QEAAXXZ; CWcnSession::Release(void)
0x180040a5e  mov     r10, cs:WPP_GLOBAL_Control
0x180040a65  cmp     r10, r15
0x180040a68  jz      short loc_180040A9C
0x180040a6a  test    ebx, ebx
0x180040a6c  js      short loc_180040A75
0x180040a6e  cmp     byte ptr [r10+19h], 6
0x180040a73  jb      short loc_180040A9C
0x180040a75  or      ecx, 0FFFFFFFFh; int
0x180040a78  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040a7d  mov     edx, 19h
0x180040a82  mov     [rsp+58h+var_38], ebx
0x180040a86  mov     r9, rax
0x180040a89  mov     r8, r12
0x180040a8c  mov     rcx, [r10+10h]
0x180040a90  call    WPP_SF_sd
0x180040a95  mov     r10, cs:WPP_GLOBAL_Control
0x180040a9c  test    ebx, ebx
0x180040a9e  jns     short loc_180040AC8
0x180040aa0  cmp     r10, r15
0x180040aa3  jz      loc_180040C33
0x180040aa9  cmp     byte ptr [r10+19h], 2
0x180040aae  jb      loc_180040C33
0x180040ab4  mov     edx, 0Fh
0x180040ab9  mov     r8, r12
0x180040abc  jmp     loc_180040C27
0x180040ac1  mov     r10, cs:WPP_GLOBAL_Control
0x180040ac8  mov     rdi, [rsi+28h]
0x180040acc  test    rdi, rdi
0x180040acf  jz      loc_180040C33
0x180040ad5  lea     r12, WPP_5fa190baff5c39c65fabd2932d857ffc_Traceguids
0x180040adc  cmp     r10, r15
0x180040adf  jz      short loc_180040B0D
0x180040ae1  cmp     byte ptr [r10+19h], 6
0x180040ae6  jb      short loc_180040B0D
0x180040ae8  mov     ecx, 1; int
0x180040aed  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040af2  mov     edx, 0Fh
0x180040af7  mov     r9, rax
0x180040afa  mov     r8, r12
0x180040afd  mov     rcx, [r10+10h]
0x180040b01  call    WPP_SF_s
0x180040b06  mov     r10, cs:WPP_GLOBAL_Control
0x180040b0d  test    rbp, rbp
0x180040b10  jnz     short loc_180040B45
0x180040b12  cmp     r10, r15
0x180040b15  jz      short loc_180040B3B
0x180040b17  cmp     byte ptr [r10+19h], 2
0x180040b1c  jb      short loc_180040B3B
0x180040b1e  lea     edx, [rbp+10h]
0x180040b21  lea     r9, aPincomingmessa; "pIncomingMessage"
0x180040b28  mov     r8, r12
0x180040b2b  mov     rcx, [r10+10h]
0x180040b2f  call    WPP_SF_s
0x180040b34  mov     r10, cs:WPP_GLOBAL_Control
0x180040b3b  mov     ebx, 80004003h
0x180040b40  jmp     loc_180040C0F
0x180040b45  lea     rcx, [rdi+58h]; lpCriticalSection
0x180040b49  call    cs:__imp_EnterCriticalSection
0x180040b4f  cmp     byte ptr [rdi+0B0h], 0
0x180040b56  jnz     short loc_180040B76
0x180040b58  mov     rcx, [rdi+0A8h]
0x180040b5f  test    rcx, rcx
0x180040b62  jz      short loc_180040B76
0x180040b64  mov     rax, [rcx]
0x180040b67  mov     rax, [rax]
0x180040b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b6f  mov     byte ptr [rdi+0B0h], 1
0x180040b76  lea     rcx, [rdi+28h]; this
0x180040b7a  movups  xmm0, xmmword ptr [rbp+20h]
0x180040b7e  movdqu  xmmword ptr [rcx+20h], xmm0
0x180040b83  mov     rdx, rbp; struct CSbSafeBuffer *
0x180040b86  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBV1@@Z; CSbSafeBuffer::CopyFromBuffer(CSbSafeBuffer const *)
0x180040b8b  mov     ebx, eax
0x180040b8d  test    eax, eax
0x180040b8f  jns     short loc_180040BB9
0x180040b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b98  cmp     rcx, r15
0x180040b9b  jz      short loc_180040BC3
0x180040b9d  cmp     byte ptr [rcx+19h], 2
0x180040ba1  jb      short loc_180040BC3
0x180040ba3  mov     edx, 11h
0x180040ba8  mov     r9d, eax
0x180040bab  mov     r8, r12
0x180040bae  mov     rcx, [rcx+10h]
0x180040bb2  call    WPP_SF_d
0x180040bb7  jmp     short loc_180040BC3
0x180040bb9  mov     rcx, [rdi+18h]; hEvent
0x180040bbd  call    cs:__imp_SetEvent
0x180040bc3  lea     rcx, [rdi+58h]; lpCriticalSection
0x180040bc7  call    cs:__imp_LeaveCriticalSection
0x180040bcd  mov     r10, cs:WPP_GLOBAL_Control
0x180040bd4  cmp     r10, r15
0x180040bd7  jz      short loc_180040C0B
0x180040bd9  test    ebx, ebx
0x180040bdb  js      short loc_180040BE4
0x180040bdd  cmp     byte ptr [r10+19h], 6
0x180040be2  jb      short loc_180040C0B
0x180040be4  or      ecx, 0FFFFFFFFh; int
0x180040be7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040bec  mov     edx, 12h
0x180040bf1  mov     [rsp+58h+var_38], ebx
0x180040bf5  mov     r9, rax
0x180040bf8  mov     r8, r12
0x180040bfb  mov     rcx, [r10+10h]
0x180040bff  call    WPP_SF_sd
0x180040c04  mov     r10, cs:WPP_GLOBAL_Control
0x180040c0b  test    ebx, ebx
0x180040c0d  jns     short loc_180040C33
0x180040c0f  cmp     r10, r15
0x180040c12  jz      short loc_180040C33
0x180040c14  cmp     byte ptr [r10+19h], 2
0x180040c19  jb      short loc_180040C33
0x180040c1b  mov     edx, 10h
0x180040c20  lea     r8, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x180040c27  mov     r9d, ebx
0x180040c2a  mov     rcx, [r10+10h]
0x180040c2e  call    WPP_SF_d
0x180040c33  lea     rcx, [rsi+30h]; lpCriticalSection
0x180040c37  call    cs:__imp_LeaveCriticalSection
0x180040c3d  mov     r10, cs:WPP_GLOBAL_Control
0x180040c44  cmp     r10, r15
0x180040c47  jz      short loc_180040C78
0x180040c49  test    ebx, ebx
0x180040c4b  js      short loc_180040C54
0x180040c4d  cmp     byte ptr [r10+19h], 6
0x180040c52  jb      short loc_180040C78
0x180040c54  or      ecx, 0FFFFFFFFh; int
0x180040c57  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180040c5c  mov     edx, 11h
0x180040c61  mov     [rsp+58h+var_38], ebx
0x180040c65  mov     r9, rax
0x180040c68  lea     r8, WPP_af767cd661eb3cc5404dbe8478e6939c_Traceguids
0x180040c6f  mov     rcx, [r10+10h]
0x180040c73  call    WPP_SF_sd
0x180040c78  mov     rbx, [rsp+58h+arg_8]
0x180040c7d  mov     rbp, [rsp+58h+arg_10]
0x180040c82  add     rsp, 30h
0x180040c86  pop     r15
0x180040c88  pop     r14
0x180040c8a  pop     r12
0x180040c8c  pop     rdi
0x180040c8d  pop     rsi
0x180040c8e  retn
```
