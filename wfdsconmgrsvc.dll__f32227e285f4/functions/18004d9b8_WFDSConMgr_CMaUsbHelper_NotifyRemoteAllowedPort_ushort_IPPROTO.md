# WFDSConMgr::CMaUsbHelper::NotifyRemoteAllowedPort(ushort,IPPROTO)

- ea: `0x18004d9b8`
- end: `0x18004db76`
- name: `?NotifyRemoteAllowedPort@CMaUsbHelper@WFDSConMgr@@QEAAXGW4IPPROTO@@@Z`
- size: `446`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper *__hidden this, unsigned __int16, enum IPPROTO)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003f490`

## callees

- `0x18000475c`
- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x180006eb0`
- `0x1800296f0`
- `0x18004d9b8`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dae3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dae3`
- `WS2_32!__imp_htons` at `0x18004dafc`
- `WS2_32!__imp_htons` at `0x18004dafc`

## string_xrefs

- `0x18004da06`: `UNKNOWN_PROTOCOL`
- `0x18004daa0`: `MA-USB driver handle not open`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::CMaUsbHelper::NotifyRemoteAllowedPort(
        WFDSConMgr::CMaUsbHelper *this,
        __int16 a2,
        enum IPPROTO a3)
{
  const wchar_t *v6; // rcx
  char v7; // bl
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, std::_Ref_count_base *, _QWORD, _QWORD, enum IPPROTO); // rbx
  u_short v10; // ax
  int v11; // eax
  std::_Ref_count_base *v12[2]; // [rsp+30h] [rbp-48h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( a3 == IPPROTO_TCP )
    {
      v6 = L"TCP";
    }
    else
    {
      v6 = L"UDP";
      if ( a3 != IPPROTO_UDP )
        v6 = L"UNKNOWN_PROTOCOL";
    }
    WPP_SF_qSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)&WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids,
      (_DWORD)this,
      (__int64)v6,
      a2);
  }
  *(_OWORD *)v12 = 0;
  v7 = 1;
  WFDSConMgr::CriticalSection::Lock((char *)this + 8, &lpCriticalSection);
  if ( !*((_BYTE *)this + 369) )
  {
    v7 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
    }
  }
  if ( !*((_QWORD *)this + 33) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMaUsbHelper::NotifyRemoteAllowedPort",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      240,
      L"MA-USB driver handle not open",
      this);
  std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(v12, (char *)this + 264);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( v7 )
  {
    v8 = *((_QWORD *)this + 6);
    v9 = *(__int64 (__fastcall **)(__int64, std::_Ref_count_base *, _QWORD, _QWORD, enum IPPROTO))(*(_QWORD *)v8 + 64LL);
    v10 = htons(a2);
    v11 = v9(v8, v12[0], *((_QWORD *)this + 43), v10, a3);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this, v11);
      }
    }
  }
  if ( v12[1] )
    std::_Ref_count_base::_Decref(v12[1]);
}

```

## disassembly

```asm
0x18004d9b8  push    rbx
0x18004d9ba  push    rbp
0x18004d9bb  push    rsi
0x18004d9bc  push    rdi
0x18004d9bd  push    r12
0x18004d9bf  push    r14
0x18004d9c1  sub     rsp, 48h
0x18004d9c5  mov     ebp, r8d
0x18004d9c8  movzx   r14d, dx
0x18004d9cc  mov     rsi, rcx
0x18004d9cf  lea     r12, WPP_GLOBAL_Control
0x18004d9d6  mov     r10, cs:WPP_GLOBAL_Control
0x18004d9dd  cmp     r10, r12
0x18004d9e0  jz      short loc_18004DA36
0x18004d9e2  cmp     byte ptr [r10+19h], 3
0x18004d9e7  jb      short loc_18004DA36
0x18004d9e9  test    byte ptr [r10+1Ch], 1
0x18004d9ee  jz      short loc_18004DA36
0x18004d9f0  cmp     r8d, 6
0x18004d9f4  jnz     short loc_18004D9FF
0x18004d9f6  lea     rcx, aTcp; "TCP"
0x18004d9fd  jmp     short loc_18004DA14
0x18004d9ff  lea     rcx, aUdp; "UDP"
0x18004da06  lea     rax, aUnknownProtoco; "UNKNOWN_PROTOCOL"
0x18004da0d  cmp     ebp, 11h
0x18004da10  cmovnz  rcx, rax
0x18004da14  mov     edx, 25h ; '%'
0x18004da19  mov     dword ptr [rsp+78h+var_50], r14d
0x18004da1e  mov     [rsp+78h+var_58], rcx
0x18004da23  mov     r9, rsi
0x18004da26  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004da2d  mov     rcx, [r10+10h]
0x18004da31  call    WPP_SF_qSD
0x18004da36  xorps   xmm0, xmm0
0x18004da39  movdqu  xmmword ptr [rsp+78h+var_48], xmm0
0x18004da3f  mov     bl, 1
0x18004da41  lea     rcx, [rsi+8]
0x18004da45  lea     rdx, [rsp+78h+lpCriticalSection]
0x18004da4d  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004da52  nop
0x18004da53  cmp     byte ptr [rsi+171h], 0
0x18004da5a  jnz     short loc_18004DA8E
0x18004da5c  xor     bl, bl
0x18004da5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da65  cmp     rcx, r12
0x18004da68  jz      short loc_18004DA8E
0x18004da6a  cmp     byte ptr [rcx+19h], 4
0x18004da6e  jb      short loc_18004DA8E
0x18004da70  test    byte ptr [rcx+1Ch], 1
0x18004da74  jz      short loc_18004DA8E
0x18004da76  mov     edx, 26h ; '&'
0x18004da7b  mov     r9, rsi
0x18004da7e  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004da85  mov     rcx, [rcx+10h]
0x18004da89  call    WPP_SF_q
0x18004da8e  lea     rdx, [rsi+108h]
0x18004da95  cmp     qword ptr [rdx], 0
0x18004da99  jnz     short loc_18004DACB
0x18004da9b  mov     [rsp+78h+var_50], rsi; void *
0x18004daa0  lea     rax, aMaUsbDriverHan; "MA-USB driver handle not open"
0x18004daa7  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004daac  mov     r9d, 3F0h; char
0x18004dab2  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004dab9  lea     rdx, aWfdsconmgrCmau_9; "WFDSConMgr::CMaUsbHelper::NotifyRemoteA"...
0x18004dac0  mov     ecx, 8007139Fh; char
0x18004dac5  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004dacb  lea     rcx, [rsp+78h+var_48]
0x18004dad0  call    ??4?$shared_ptr@VCNotificationEvent@WFDSConMgr@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(std::shared_ptr<WFDSConMgr::CNotificationEvent> const &)
0x18004dad5  nop
0x18004dad6  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18004dade  test    rcx, rcx
0x18004dae1  jz      short loc_18004DAE9
0x18004dae3  call    cs:__imp_LeaveCriticalSection
0x18004dae9  test    bl, bl
0x18004daeb  jz      short loc_18004DB5A
0x18004daed  mov     rdi, [rsi+30h]
0x18004daf1  mov     rax, [rdi]
0x18004daf4  mov     rbx, [rax+40h]
0x18004daf8  movzx   ecx, r14w; hostshort
0x18004dafc  call    cs:__imp_htons
0x18004db02  mov     dword ptr [rsp+78h+var_58], ebp
0x18004db06  movzx   r9d, ax
0x18004db0a  mov     r8, [rsi+158h]
0x18004db11  mov     rdx, [rsp+78h+var_48]
0x18004db16  mov     rcx, rdi
0x18004db19  mov     rax, rbx
0x18004db1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db21  test    eax, eax
0x18004db23  jz      short loc_18004DB5A
0x18004db25  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db2c  cmp     rcx, r12
0x18004db2f  jz      short loc_18004DB5A
0x18004db31  cmp     byte ptr [rcx+19h], 1
0x18004db35  jb      short loc_18004DB5A
0x18004db37  test    byte ptr [rcx+1Ch], 1
0x18004db3b  jz      short loc_18004DB5A
0x18004db3d  mov     edx, 27h ; '''
0x18004db42  mov     dword ptr [rsp+78h+var_58], eax
0x18004db46  mov     r9, rsi
0x18004db49  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004db50  mov     rcx, [rcx+10h]
0x18004db54  call    WPP_SF_qD
0x18004db59  nop
0x18004db5a  mov     rcx, [rsp+78h+var_48+8]; this
0x18004db5f  test    rcx, rcx
0x18004db62  jz      short loc_18004DB69
0x18004db64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004db69  add     rsp, 48h
0x18004db6d  pop     r14
0x18004db6f  pop     r12
0x18004db71  pop     rdi
0x18004db72  pop     rsi
0x18004db73  pop     rbp
0x18004db74  pop     rbx
0x18004db75  retn
```
