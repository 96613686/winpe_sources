# WFDSConMgr::CMaUsbHelper::OnDatarateUpdate(_MI_NOTIFICATION_PARAMS const &)

- ea: `0x18004dc00`
- end: `0x18004de39`
- name: `?OnDatarateUpdate@CMaUsbHelper@WFDSConMgr@@UEAAXAEBU_MI_NOTIFICATION_PARAMS@@@Z`
- size: `569`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper *__hidden this, const struct _MI_NOTIFICATION_PARAMS *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x18000475c`
- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x180006eb0`
- `0x180009ba8`
- `0x18004dc00`
- `0x18005c800`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dcd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dcd9`

## string_xrefs

- `0x18004dc96`: `MA-USB driver handle not open`
- `0x18004dcaf`: `WFDSConMgr::CMaUsbHelper::OnDatarateUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::CMaUsbHelper::OnDatarateUpdate(
        WFDSConMgr::CMaUsbHelper *this,
        const struct _MI_NOTIFICATION_PARAMS *a2)
{
  int v4; // eax
  char v5; // bp
  __int64 v6; // rax
  __int64 v7; // r8
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  std::_Ref_count_base *v11[2]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v12[7]; // [rsp+40h] [rbp-38h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp+10h] BYREF

  v4 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 != 1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return;
    }
    v10 = 46;
LABEL_34:
    WPP_SF_qD(v9[2], v10, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this, v4);
    return;
  }
  v4 = *((_DWORD *)a2 + 2);
  if ( v4 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return;
    }
    v10 = 45;
    goto LABEL_34;
  }
  *(_OWORD *)v11 = 0;
  v5 = 1;
  WFDSConMgr::CriticalSection::Lock((char *)this + 8, &lpCriticalSection);
  if ( !*((_BYTE *)this + 369) )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
    }
  }
  if ( !*((_QWORD *)this + 33) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMaUsbHelper::OnDatarateUpdate",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      69,
      L"MA-USB driver handle not open",
      this);
  std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(v11, (char *)this + 264);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( v5 )
  {
    v6 = *((_QWORD *)a2 + 2);
    v12[0] = v6;
    v7 = *((_QWORD *)a2 + 3);
    v12[1] = v7;
    if ( *(_DWORD *)a2 != 1 )
      WFDSConMgr::CException::Throw(
        -2147024809,
        "WFDSConMgr::MaUsbDatarateInfo::MaUsbDatarateInfo",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
        22,
        L"Tried to convert Miracast notification to data rate stats, but had wrong notification type");
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids,
        this,
        v6,
        v7);
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base *, _QWORD, _QWORD *))(**((_QWORD **)this + 6) + 72LL))(
           *((_QWORD *)this + 6),
           v11[0],
           *((_QWORD *)this + 43),
           v12);
    if ( v8
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this, v8);
    }
  }
  if ( v11[1] )
    std::_Ref_count_base::_Decref(v11[1]);
}

```

## disassembly

```asm
0x18004dc00  mov     r11, rsp
0x18004dc03  push    rbx
0x18004dc04  push    rbp
0x18004dc05  push    rsi
0x18004dc06  push    rdi
0x18004dc07  sub     rsp, 58h
0x18004dc0b  mov     rsi, rdx
0x18004dc0e  mov     rbx, rcx
0x18004dc11  mov     eax, [rdx]
0x18004dc13  cmp     eax, 1
0x18004dc16  jnz     loc_18004DDF5
0x18004dc1c  mov     eax, [rdx+8]
0x18004dc1f  test    eax, eax
0x18004dc21  jnz     loc_18004DDCF
0x18004dc27  xorps   xmm0, xmm0
0x18004dc2a  movdqu  xmmword ptr [rsp+78h+var_48], xmm0
0x18004dc30  mov     bpl, 1
0x18004dc33  add     rcx, 8
0x18004dc37  lea     rdx, [r11+10h]
0x18004dc3b  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004dc40  nop
0x18004dc41  lea     rdi, WPP_GLOBAL_Control
0x18004dc48  cmp     byte ptr [rbx+171h], 0
0x18004dc4f  jnz     short loc_18004DC84
0x18004dc51  xor     bpl, bpl
0x18004dc54  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc5b  cmp     rcx, rdi
0x18004dc5e  jz      short loc_18004DC84
0x18004dc60  cmp     byte ptr [rcx+19h], 4
0x18004dc64  jb      short loc_18004DC84
0x18004dc66  test    byte ptr [rcx+1Ch], 1
0x18004dc6a  jz      short loc_18004DC84
0x18004dc6c  mov     edx, 2Ah ; '*'
0x18004dc71  mov     r9, rbx
0x18004dc74  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004dc7b  mov     rcx, [rcx+10h]
0x18004dc7f  call    WPP_SF_q
0x18004dc84  lea     rdx, [rbx+108h]
0x18004dc8b  cmp     qword ptr [rdx], 0
0x18004dc8f  jnz     short loc_18004DCC1
0x18004dc91  mov     [rsp+78h+var_50], rbx; void *
0x18004dc96  lea     rax, aMaUsbDriverHan; "MA-USB driver handle not open"
0x18004dc9d  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004dca2  mov     r9d, 445h; char
0x18004dca8  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004dcaf  lea     rdx, aWfdsconmgrCmau_6; "WFDSConMgr::CMaUsbHelper::OnDatarateUpd"...
0x18004dcb6  mov     ecx, 8007139Fh; char
0x18004dcbb  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004dcc1  lea     rcx, [rsp+78h+var_48]
0x18004dcc6  call    ??4?$shared_ptr@VCNotificationEvent@WFDSConMgr@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(std::shared_ptr<WFDSConMgr::CNotificationEvent> const &)
0x18004dccb  nop
0x18004dccc  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18004dcd4  test    rcx, rcx
0x18004dcd7  jz      short loc_18004DCDF
0x18004dcd9  call    cs:__imp_LeaveCriticalSection
0x18004dcdf  test    bpl, bpl
0x18004dce2  jz      loc_18004DDBE
0x18004dce8  mov     rax, [rsi+10h]
0x18004dcec  mov     [rsp+78h+var_38], rax
0x18004dcf1  mov     r8, [rsi+18h]
0x18004dcf5  mov     [rsp+78h+var_30], r8
0x18004dcfa  cmp     dword ptr [rsi], 1
0x18004dcfd  jz      short loc_18004DD2A
0x18004dcff  lea     rax, aTriedToConvert; "Tried to convert Miracast notification "...
0x18004dd06  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004dd0b  mov     r9d, 16h; char
0x18004dd11  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004dd18  lea     rdx, aWfdsconmgrMaus; "WFDSConMgr::MaUsbDatarateInfo::MaUsbDat"...
0x18004dd1f  mov     ecx, 80070057h; int
0x18004dd24  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18004dd2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dd31  cmp     rcx, rdi
0x18004dd34  jz      short loc_18004DD64
0x18004dd36  cmp     byte ptr [rcx+19h], 4
0x18004dd3a  jb      short loc_18004DD64
0x18004dd3c  test    byte ptr [rcx+1Ch], 1
0x18004dd40  jz      short loc_18004DD64
0x18004dd42  mov     edx, 2Bh ; '+'
0x18004dd47  mov     [rsp+78h+var_50], r8
0x18004dd4c  mov     [rsp+78h+var_58], rax
0x18004dd51  mov     r9, rbx
0x18004dd54  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004dd5b  mov     rcx, [rcx+10h]
0x18004dd5f  call    WPP_SF_qqq
0x18004dd64  mov     rcx, [rbx+30h]
0x18004dd68  mov     rax, [rcx]
0x18004dd6b  lea     r9, [rsp+78h+var_38]
0x18004dd70  mov     r8, [rbx+158h]
0x18004dd77  mov     rdx, [rsp+78h+var_48]
0x18004dd7c  mov     rax, [rax+48h]
0x18004dd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd85  test    eax, eax
0x18004dd87  jz      short loc_18004DDBE
0x18004dd89  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dd90  cmp     rcx, rdi
0x18004dd93  jz      short loc_18004DDBE
0x18004dd95  cmp     byte ptr [rcx+19h], 2
0x18004dd99  jb      short loc_18004DDBE
0x18004dd9b  test    byte ptr [rcx+1Ch], 1
0x18004dd9f  jz      short loc_18004DDBE
0x18004dda1  mov     edx, 2Ch ; ','
0x18004dda6  mov     dword ptr [rsp+78h+var_58], eax
0x18004ddaa  mov     r9, rbx
0x18004ddad  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004ddb4  mov     rcx, [rcx+10h]
0x18004ddb8  call    WPP_SF_qD
0x18004ddbd  nop
0x18004ddbe  mov     rcx, [rsp+78h+var_48+8]; this
0x18004ddc3  test    rcx, rcx
0x18004ddc6  jz      short loc_18004DE30
0x18004ddc8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004ddcd  jmp     short loc_18004DE30
0x18004ddcf  lea     rdi, WPP_GLOBAL_Control
0x18004ddd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dddd  cmp     rcx, rdi
0x18004dde0  jz      short loc_18004DE30
0x18004dde2  cmp     byte ptr [rcx+19h], 4
0x18004dde6  jb      short loc_18004DE30
0x18004dde8  test    byte ptr [rcx+1Ch], 1
0x18004ddec  jz      short loc_18004DE30
0x18004ddee  mov     edx, 2Dh ; '-'
0x18004ddf3  jmp     short loc_18004DE19
0x18004ddf5  lea     rdi, WPP_GLOBAL_Control
0x18004ddfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004de03  cmp     rcx, rdi
0x18004de06  jz      short loc_18004DE30
0x18004de08  cmp     byte ptr [rcx+19h], 4
0x18004de0c  jb      short loc_18004DE30
0x18004de0e  test    byte ptr [rcx+1Ch], 1
0x18004de12  jz      short loc_18004DE30
0x18004de14  mov     edx, 2Eh ; '.'
0x18004de19  mov     dword ptr [rsp+78h+var_58], eax
0x18004de1d  mov     r9, rbx
0x18004de20  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004de27  mov     rcx, [rcx+10h]
0x18004de2b  call    WPP_SF_qD
0x18004de30  add     rsp, 58h
0x18004de34  pop     rdi
0x18004de35  pop     rsi
0x18004de36  pop     rbp
0x18004de37  pop     rbx
0x18004de38  retn
```
