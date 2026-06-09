# CWnpConnector::OnMessage(uint,unsigned __int64,__int64)

- ea: `0x18005a080`
- end: `0x18005a930`
- name: `?OnMessage@CWnpConnector@@MEAA_JI_K_J@Z`
- size: `2224`
- prototype: `LRESULT __fastcall(CWnpConnector *this, UINT Msg, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `34`
- tags: ``

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x180010044`
- `0x18001344c`
- `0x180025ad4`
- `0x18002f27c`
- `0x18002f2d8`
- `0x18002f964`
- `0x18002fcdc`
- `0x18004f31c`
- `0x180051298`
- `0x180057104`
- `0x180057350`
- `0x180057648`
- `0x180057e2c`
- `0x180058458`
- `0x1800586dc`
- `0x180058d08`
- `0x180058e78`
- `0x1800593f4`
- `0x180059948`
- `0x180059b64`
- `0x180059c48`
- `0x180059d24`
- `0x180059de0`
- `0x18005a080`
- `0x18005aa00`
- `0x18005aacc`
- `0x18005af70`
- `0x18005b06c`
- `0x18005b478`
- `0x18005fc48`
- `0x18005feb0`
- `0x180060058`

## import_xrefs

- `WS2_32!__imp_WSAAsyncSelect` at `0x18005a3ed`
- `WS2_32!__imp_WSAAsyncSelect` at `0x18005a3ed`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a3f7`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a3f7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x18005a25b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x18005a25b`

## string_xrefs

- `0x18005a62b`: `FD_READ`
- `0x18005a639`: `FD_WRITE`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
LRESULT __fastcall CWnpConnector::OnMessage(CWnpConnector *this, UINT Msg, WPARAM a3, LPARAM a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  PVOID *v11; // rcx
  __int64 v12; // rdx
  PVOID *v14; // rcx
  int v15; // r9d
  int Error; // eax
  char v17; // bp
  signed int v18; // esi
  __int64 v19; // rdx
  unsigned int v20; // esi
  PVOID *v21; // rcx
  const char *v22; // rax
  unsigned int v23; // edx
  bool v24; // al
  bool v25; // zf
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  unsigned int v29; // edx
  __int64 v30; // rdx
  bool v31; // si
  __int64 v32; // r9
  int v33; // [rsp+20h] [rbp-68h]
  int v34; // [rsp+20h] [rbp-68h]
  int v35; // [rsp+28h] [rbp-60h]
  bool v36; // [rsp+40h] [rbp-48h] BYREF
  bool v37; // [rsp+41h] [rbp-47h] BYREF
  int v38; // [rsp+44h] [rbp-44h] BYREF
  int v39; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v40; // [rsp+4Ch] [rbp-3Ch] BYREF

  if ( CMsgrWndBase::IsShuttingDown(this) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
    }
    return DefWindowProcW(*((HWND *)this + 3), Msg, a3, a4);
  }
  if ( Msg != 1056 )
  {
    if ( Msg == 1057 )
    {
      *((_QWORD *)this + 20) = -1;
      CWnpConnector::LogDnsLookupEnd(this, a3);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_dLc(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          228,
          &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
          *((unsigned int *)this + 16),
          a3,
          (*((_BYTE *)this + 108) & 8) != 0);
      }
      if ( (a3 & 0x80000000) != 0LL )
      {
        CWnpConnector::OnError(this, (unsigned int)a3);
        CWnpConnector::LogTelemetry(this, a3);
        CWnpConnector::HandleDnsLookupRetryLogic(this, a3);
      }
      else
      {
        CWnpConnector::OnGetAddrInfo(this, *((struct addrinfoexW **)this + 25));
      }
      return 0;
    }
    if ( Msg != 1058 )
    {
      if ( Msg == 1059 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dc(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            236,
            &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
            *((unsigned int *)this + 16),
            (*((_BYTE *)this + 108) & 8) != 0);
        }
        CWnpConnector::OnDnsLookupRetry(this);
      }
      else if ( Msg == 1060 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dc(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            237,
            &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
            *((unsigned int *)this + 16),
            (*((_BYTE *)this + 108) & 8) != 0);
        }
        CWnpConnector::OnDirectConnectRetry(this);
      }
      else
      {
        if ( Msg != 1061 )
        {
          if ( Msg == 1062 )
          {
            if ( (byte_1800AFD83 & 0x20) != 0 )
              McTemplateU0q_EventWriteTransfer(
                v9,
                WPNPRV_TRANS_PROXY_NEGOTIATION_END,
                (*((_BYTE *)this + 108) & 8) != 0);
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_dc(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                229,
                &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
                *((unsigned int *)this + 16),
                (*((_BYTE *)this + 108) & 8) != 0);
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( *((_DWORD *)this + 22) == 4 )
            {
              CWnpConnector::LogConnectToProxyEnd(this, -2147177293);
              v12 = 2147790003LL;
            }
            else
            {
              if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 2u )
                WPP_SF_Dd(v11[2], 230, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
              CWnpConnector::LogConnectToProxyEnd(this, -2147177304);
              v12 = 2147789992LL;
            }
            CWnpConnector::OnError(this, v12);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_dLc(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              239,
              &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
              Msg,
              *((_DWORD *)this + 16),
              (*((_BYTE *)this + 108) & 8) != 0);
          }
          return DefWindowProcW(*((HWND *)this + 3), Msg, a3, a4);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dc(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            238,
            &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
            *((unsigned int *)this + 16),
            (*((_BYTE *)this + 108) & 8) != 0);
        }
        CWnpConnector::OnConnectorFailed(this, (unsigned int)a3);
      }
      return 0;
    }
    if ( (byte_1800AFD83 & 0x20) != 0 )
      McTemplateU0q_EventWriteTransfer(v9, WPNPRV_TRANS_PROXY_NEGOTIATION_END, (*((_BYTE *)this + 108) & 8) != 0);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dDc(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        v10,
        *((unsigned int *)this + 16),
        a3,
        (*((_BYTE *)this + 108) & 8) != 0);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( a3 == -1 )
    {
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 && *((_BYTE *)v14 + 25) >= 2u )
      {
        LOBYTE(v33) = (*((_BYTE *)this + 108) & 8) != 0;
        WPP_SF_dc(v14[2], 235, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, (unsigned int)a4, v33);
      }
      CWnpConnector::LogConnectToProxyEnd(this, a4);
      v19 = (unsigned int)a4;
    }
    else
    {
      v15 = *((_DWORD *)this + 22);
      *((_QWORD *)this + 10) = a3;
      if ( v15 == 4 )
      {
        if ( WSAAsyncSelect(a3, *((HWND *)this + 3), 0x420u, 35) )
        {
          Error = WSAGetLastError();
          v17 = Error;
          if ( Error > 0 )
            v18 = (unsigned __int16)Error | 0x80070000;
          else
            v18 = Error;
          if ( v18 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              232,
              &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
              (unsigned int)v18);
          }
          CWnpConnector::OnSocketError(this, v17, 0x23u, 1, 0x422u);
          CWnpConnector::LogConnectToProxyEnd(this, v18);
          return 0;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
        }
LABEL_69:
        CWnpConnector::OnSocketConnect(this);
        return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
      }
      CWnpConnector::LogConnectToProxyEnd(this, -2147177304);
      v19 = 2147789992LL;
    }
    CWnpConnector::OnError(this, v19);
    return 0;
  }
  v20 = (unsigned __int16)a4;
  v39 = (unsigned __int16)a4;
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    switch ( (unsigned __int16)a4 )
    {
      case 0x10u:
        v22 = "FD_CONNECT";
        break;
      case 1u:
        v22 = "FD_READ";
        break;
      case 2u:
        v22 = "FD_WRITE";
        break;
      case 8u:
        v22 = "FD_ACCEPT";
        break;
      default:
        v22 = "FD_CLOSE";
        if ( (unsigned __int16)a4 != 32 )
          v22 = (const char *)&byte_18009A357;
        break;
    }
    v23 = WORD1(a4);
    if ( WORD1(a4) )
      v23 = WORD1(a4) | 0x80070000;
    LOBYTE(v10) = (*((_BYTE *)this + 108) & 8) != 0;
    WPP_SF_dDdsc(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v10, *((_DWORD *)this + 16), a3, v23, (__int64)v22, v10);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 532) )
  {
    v38 = *((_DWORD *)this + 132);
    v24 = a3 != *((_QWORD *)this + 10) || *((_QWORD *)this + 10) == -1 || !*((_QWORD *)this + 9);
    v25 = (*((_BYTE *)this + 108) & 8) == 0;
    v36 = v24;
    v26 = WORD1(a4);
    v37 = !v25;
    if ( WORD1(a4) )
      v26 = WORD1(a4) | 0x80070000;
    v40 = v26;
    WpnVerboseTelemetry::WnpConnectorSocketMessage<long,long &,bool,bool,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0008>(
      (unsigned int)&v40,
      (unsigned int)&v39,
      (unsigned int)&v37,
      (unsigned int)&v36,
      (__int64)&v38);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 != *((_QWORD *)this + 10) || *((_QWORD *)this + 10) == -1 || !*((_QWORD *)this + 9) )
  {
    if ( v21 == &WPP_GLOBAL_Control || (*((_BYTE *)v21 + 28) & 4) == 0 || *((_BYTE *)v21 + 25) < 5u )
      return 0;
    v30 = 224;
    goto LABEL_152;
  }
  if ( WORD1(a4) )
  {
    if ( (byte_1800AFD84 & 1) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        v21,
        WPNPRV_TRANS_ASYNC_CONNECT_FAILURE,
        (*((_BYTE *)this + 108) & 8) != 0,
        WORD1(a4));
    CWnpConnector::LogDirectConnectEnd(this, WORD1(a4) | 0x80070000);
    CWnpConnector::LogWnpSocketOperation(this, (unsigned __int16)a4, 1, 0x420u, SBYTE2(a4));
    LOBYTE(a4) = CWnpConnector::HandleAsyncConnectFailure(this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      LOBYTE(v35) = (*((_BYTE *)this + 108) & 8) != 0;
      LOBYTE(v34) = a4;
      WPP_SF_dcc(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, WORD1(a4) | 0x80070000, v34, v35);
    }
    if ( (_BYTE)a4 )
      return 0;
    if ( *((_DWORD *)this + 22) == 7 || (*((_BYTE *)this + 108) & 1) == 0 )
    {
      CWnpConnector::OnSocketError(this, SBYTE2(a4), v20, 1, 0x420u);
      if ( v20 != 16 )
        return 0;
      v29 = WORD1(a4) | 0x80070000;
    }
    else
    {
      CWnpConnector::ChangeConnectorState(this, 3);
      v29 = -2147177294;
    }
    CWnpConnector::HandleConnectRetryLogic(this, v29);
    return 0;
  }
  switch ( (unsigned __int16)a4 )
  {
    case 1u:
      CWnpConnector::OnSocketRead(this);
      return 0;
    case 2u:
      CWnpConnector::OnSocketWrite(this);
      return 0;
    case 0x10u:
      goto LABEL_69;
    case 0x20u:
      if ( (byte_1800AFD84 & 1) != 0 )
        McTemplateU0qq_EventWriteTransfer(v21, WPNPRV_TRANS_ASYNC_CONNECT_FAILURE, (*((_BYTE *)this + 108) & 8) != 0, 0);
      CWnpConnector::LogSocketClose(this);
      v31 = CWnpConnector::HandleAsyncConnectFailure(this);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LOBYTE(v32) = v31;
        LOBYTE(v33) = (*((_BYTE *)this + 108) & 8) != 0;
        WPP_SF_cc(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, v32, v33);
      }
      if ( !v31 )
        CWnpConnector::OnSocketClose(this, -2147177297);
      return 0;
  }
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 && *((_BYTE *)v21 + 25) >= 2u )
  {
    v30 = 227;
LABEL_152:
    WPP_SF_(v21[2], v30, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18005a080  push    rbx
0x18005a082  push    rbp
0x18005a083  push    rsi
0x18005a084  push    rdi
0x18005a085  push    r14
0x18005a087  push    r15
0x18005a089  sub     rsp, 58h
0x18005a08d  mov     r14, r9
0x18005a090  mov     rbp, r8
0x18005a093  mov     r15d, edx
0x18005a096  mov     rbx, rcx
0x18005a099  call    ?IsShuttingDown@CMsgrWndBase@@IEAA_NXZ; CMsgrWndBase::IsShuttingDown(void)
0x18005a09e  test    al, al
0x18005a0a0  jz      short loc_18005A0E7
0x18005a0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a0a9  lea     rdi, WPP_GLOBAL_Control
0x18005a0b0  cmp     rcx, rdi
0x18005a0b3  jz      loc_18005A24E
0x18005a0b9  test    byte ptr [rcx+1Ch], 4
0x18005a0bd  jz      loc_18005A24E
0x18005a0c3  cmp     byte ptr [rcx+19h], 5
0x18005a0c7  jb      loc_18005A24E
0x18005a0cd  mov     rcx, [rcx+10h]
0x18005a0d1  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a0d8  mov     edx, 0DEh
0x18005a0dd  call    WPP_SF_
0x18005a0e2  jmp     loc_18005A24E
0x18005a0e7  mov     eax, r15d
0x18005a0ea  sub     eax, 420h
0x18005a0ef  jz      loc_18005A5CC
0x18005a0f5  sub     eax, 1
0x18005a0f8  jz      loc_18005A538
0x18005a0fe  sub     eax, 1
0x18005a101  jz      loc_18005A358
0x18005a107  sub     eax, 1
0x18005a10a  jz      loc_18005A308
0x18005a110  sub     eax, 1
0x18005a113  jz      loc_18005A2B8
0x18005a119  sub     eax, 1
0x18005a11c  jz      loc_18005A266
0x18005a122  cmp     eax, 1
0x18005a125  jz      short loc_18005A181
0x18005a127  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a12e  lea     rdi, WPP_GLOBAL_Control
0x18005a135  cmp     rcx, rdi
0x18005a138  jz      loc_18005A24E
0x18005a13e  test    byte ptr [rcx+1Ch], 4
0x18005a142  jz      loc_18005A24E
0x18005a148  cmp     byte ptr [rcx+19h], 5
0x18005a14c  jb      loc_18005A24E
0x18005a152  test    byte ptr [rbx+6Ch], 8
0x18005a156  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a15d  mov     rcx, [rcx+10h]
0x18005a161  mov     edx, 0EFh
0x18005a166  setnbe  al
0x18005a169  mov     r9d, r15d
0x18005a16c  mov     byte ptr [rsp+88h+var_60], al
0x18005a170  mov     eax, [rbx+40h]
0x18005a173  mov     dword ptr [rsp+88h+var_68], eax
0x18005a177  call    WPP_SF_dLc
0x18005a17c  jmp     loc_18005A24E
0x18005a181  test    cs:byte_1800AFD83, 20h
0x18005a188  jz      short loc_18005A1A4
0x18005a18a  test    byte ptr [rbx+6Ch], 8
0x18005a18e  lea     rdx, WPNPRV_TRANS_PROXY_NEGOTIATION_END
0x18005a195  mov     r8d, 0
0x18005a19b  setnbe  r8b
0x18005a19f  call    McTemplateU0q_EventWriteTransfer
0x18005a1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a1ab  lea     rdi, WPP_GLOBAL_Control
0x18005a1b2  cmp     rcx, rdi
0x18005a1b5  jz      short loc_18005A1EE
0x18005a1b7  test    byte ptr [rcx+1Ch], 4
0x18005a1bb  jz      short loc_18005A1EE
0x18005a1bd  cmp     byte ptr [rcx+19h], 5
0x18005a1c1  jb      short loc_18005A1EE
0x18005a1c3  test    byte ptr [rbx+6Ch], 8
0x18005a1c7  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a1ce  mov     r9d, [rbx+40h]
0x18005a1d2  mov     edx, 0E5h
0x18005a1d7  mov     rcx, [rcx+10h]
0x18005a1db  setnbe  al
0x18005a1de  mov     [rsp+88h+var_68], al
0x18005a1e2  call    WPP_SF_dc
0x18005a1e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a1ee  mov     r9d, [rbx+58h]
0x18005a1f2  cmp     r9d, 4
0x18005a1f6  jnz     short loc_18005A20B
0x18005a1f8  mov     edi, 8004ACB3h
0x18005a1fd  mov     rcx, rbx; this
0x18005a200  mov     edx, edi; int
0x18005a202  call    ?LogConnectToProxyEnd@CWnpConnector@@AEAAXJ@Z; CWnpConnector::LogConnectToProxyEnd(long)
0x18005a207  mov     edx, edi
0x18005a209  jmp     short loc_18005A246
0x18005a20b  mov     esi, 8004ACA8h
0x18005a210  cmp     rcx, rdi
0x18005a213  jz      short loc_18005A23A
0x18005a215  test    byte ptr [rcx+1Ch], 4
0x18005a219  jz      short loc_18005A23A
0x18005a21b  cmp     byte ptr [rcx+19h], 2
0x18005a21f  jb      short loc_18005A23A
0x18005a221  mov     rcx, [rcx+10h]
0x18005a225  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a22c  mov     edx, 0E6h
0x18005a231  mov     dword ptr [rsp+88h+var_68], esi
0x18005a235  call    WPP_SF_Dd
0x18005a23a  mov     edx, esi; int
0x18005a23c  mov     rcx, rbx; this
0x18005a23f  call    ?LogConnectToProxyEnd@CWnpConnector@@AEAAXJ@Z; CWnpConnector::LogConnectToProxyEnd(long)
0x18005a244  mov     edx, esi
0x18005a246  mov     rcx, rbx
0x18005a249  call    ?OnError@CWnpConnector@@AEAAXJW4LogCommandFailureContext@@@Z; CWnpConnector::OnError(long,LogCommandFailureContext)
0x18005a24e  mov     rcx, [rbx+18h]; hWnd
0x18005a252  mov     r9, r14; lParam
0x18005a255  mov     r8, rbp; wParam
0x18005a258  mov     edx, r15d; Msg
0x18005a25b  call    cs:__imp_DefWindowProcW
0x18005a261  jmp     loc_18005A923
0x18005a266  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a26d  lea     rdi, WPP_GLOBAL_Control
0x18005a274  cmp     rcx, rdi
0x18005a277  jz      short loc_18005A2A9
0x18005a279  test    byte ptr [rcx+1Ch], 4
0x18005a27d  jz      short loc_18005A2A9
0x18005a27f  cmp     byte ptr [rcx+19h], 5
0x18005a283  jb      short loc_18005A2A9
0x18005a285  test    byte ptr [rbx+6Ch], 8
0x18005a289  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a290  mov     r9d, [rbx+40h]
0x18005a294  mov     edx, 0EEh
0x18005a299  mov     rcx, [rcx+10h]
0x18005a29d  setnbe  al
0x18005a2a0  mov     [rsp+88h+var_68], al
0x18005a2a4  call    WPP_SF_dc
0x18005a2a9  mov     edx, ebp
0x18005a2ab  mov     rcx, rbx
0x18005a2ae  call    ?OnConnectorFailed@CWnpConnector@@AEAAJJW4LogCommandFailureContext@@@Z; CWnpConnector::OnConnectorFailed(long,LogCommandFailureContext)
0x18005a2b3  jmp     loc_18005A921
0x18005a2b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a2bf  lea     rdi, WPP_GLOBAL_Control
0x18005a2c6  cmp     rcx, rdi
0x18005a2c9  jz      short loc_18005A2FB
0x18005a2cb  test    byte ptr [rcx+1Ch], 4
0x18005a2cf  jz      short loc_18005A2FB
0x18005a2d1  cmp     byte ptr [rcx+19h], 5
0x18005a2d5  jb      short loc_18005A2FB
0x18005a2d7  test    byte ptr [rbx+6Ch], 8
0x18005a2db  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a2e2  mov     r9d, [rbx+40h]
0x18005a2e6  mov     edx, 0EDh
0x18005a2eb  mov     rcx, [rcx+10h]
0x18005a2ef  setnbe  al
0x18005a2f2  mov     [rsp+88h+var_68], al
0x18005a2f6  call    WPP_SF_dc
0x18005a2fb  mov     rcx, rbx; this
0x18005a2fe  call    ?OnDirectConnectRetry@CWnpConnector@@AEAAXXZ; CWnpConnector::OnDirectConnectRetry(void)
0x18005a303  jmp     loc_18005A921
0x18005a308  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a30f  lea     rdi, WPP_GLOBAL_Control
0x18005a316  cmp     rcx, rdi
0x18005a319  jz      short loc_18005A34B
0x18005a31b  test    byte ptr [rcx+1Ch], 4
0x18005a31f  jz      short loc_18005A34B
0x18005a321  cmp     byte ptr [rcx+19h], 5
0x18005a325  jb      short loc_18005A34B
0x18005a327  test    byte ptr [rbx+6Ch], 8
0x18005a32b  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a332  mov     r9d, [rbx+40h]
0x18005a336  mov     edx, 0ECh
0x18005a33b  mov     rcx, [rcx+10h]
0x18005a33f  setnbe  al
0x18005a342  mov     [rsp+88h+var_68], al
0x18005a346  call    WPP_SF_dc
0x18005a34b  mov     rcx, rbx; this
0x18005a34e  call    ?OnDnsLookupRetry@CWnpConnector@@AEAAXXZ; CWnpConnector::OnDnsLookupRetry(void)
0x18005a353  jmp     loc_18005A921
0x18005a358  test    cs:byte_1800AFD83, 20h
0x18005a35f  jz      short loc_18005A37B
0x18005a361  test    byte ptr [rbx+6Ch], 8
0x18005a365  lea     rdx, WPNPRV_TRANS_PROXY_NEGOTIATION_END
0x18005a36c  mov     r8d, 0
0x18005a372  setnbe  r8b
0x18005a376  call    McTemplateU0q_EventWriteTransfer
0x18005a37b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a382  lea     rdi, WPP_GLOBAL_Control
0x18005a389  cmp     rcx, rdi
0x18005a38c  jz      short loc_18005A3BD
0x18005a38e  test    byte ptr [rcx+1Ch], 4
0x18005a392  jz      short loc_18005A3BD
0x18005a394  cmp     byte ptr [rcx+19h], 5
0x18005a398  jb      short loc_18005A3BD
0x18005a39a  test    byte ptr [rbx+6Ch], 8
0x18005a39e  mov     r9d, [rbx+40h]
0x18005a3a2  mov     rcx, [rcx+10h]
0x18005a3a6  setnbe  al
0x18005a3a9  mov     byte ptr [rsp+88h+var_60], al
0x18005a3ad  mov     dword ptr [rsp+88h+var_68], ebp
0x18005a3b1  call    WPP_SF_dDc
0x18005a3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a3bd  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18005a3c1  jz      loc_18005A4E9
0x18005a3c7  mov     r9d, [rbx+58h]
0x18005a3cb  mov     [rbx+50h], rbp
0x18005a3cf  cmp     r9d, 4
0x18005a3d3  jnz     loc_18005A4A5
0x18005a3d9  mov     rdx, [rbx+18h]; hWnd
0x18005a3dd  lea     r15d, [r9+1Fh]
0x18005a3e1  mov     r9d, r15d; lEvent
0x18005a3e4  mov     r8d, 420h; wMsg
0x18005a3ea  mov     rcx, rbp; s
0x18005a3ed  call    cs:__imp_WSAAsyncSelect
0x18005a3f3  test    eax, eax
0x18005a3f5  jz      short loc_18005A46B
0x18005a3f7  call    cs:__imp_WSAGetLastError
0x18005a3fd  mov     ebp, eax
0x18005a3ff  test    eax, eax
0x18005a401  jg      short loc_18005A407
0x18005a403  mov     esi, eax
0x18005a405  jmp     short loc_18005A410
0x18005a407  movzx   esi, bp
0x18005a40a  or      esi, 80070000h
0x18005a410  test    esi, esi
0x18005a412  jns     short loc_18005A444
0x18005a414  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a41b  cmp     rcx, rdi
0x18005a41e  jz      short loc_18005A444
0x18005a420  test    byte ptr [rcx+1Ch], 4
0x18005a424  jz      short loc_18005A444
0x18005a426  cmp     byte ptr [rcx+19h], 2
0x18005a42a  jb      short loc_18005A444
0x18005a42c  mov     rcx, [rcx+10h]
0x18005a430  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a437  mov     edx, 0E8h
0x18005a43c  mov     r9d, esi
0x18005a43f  call    WPP_SF_d
0x18005a444  mov     r9b, 1; bool
0x18005a447  mov     dword ptr [rsp+88h+var_68], 422h; unsigned int
0x18005a44f  mov     r8d, r15d; unsigned int
0x18005a452  mov     edx, ebp; char
0x18005a454  mov     rcx, rbx; this
0x18005a457  call    ?OnSocketError@CWnpConnector@@AEAAXHJ_NI@Z; CWnpConnector::OnSocketError(int,long,bool,uint)
0x18005a45c  mov     edx, esi; int
0x18005a45e  mov     rcx, rbx; this
0x18005a461  call    ?LogConnectToProxyEnd@CWnpConnector@@AEAAXJ@Z; CWnpConnector::LogConnectToProxyEnd(long)
0x18005a466  jmp     loc_18005A921
0x18005a46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a472  cmp     rcx, rdi
0x18005a475  jz      short loc_18005A498
0x18005a477  test    byte ptr [rcx+1Ch], 4
0x18005a47b  jz      short loc_18005A498
0x18005a47d  cmp     byte ptr [rcx+19h], 5
0x18005a481  jb      short loc_18005A498
0x18005a483  mov     rcx, [rcx+10h]
0x18005a487  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a48e  mov     edx, 0E9h
0x18005a493  call    WPP_SF_
0x18005a498  mov     rcx, rbx; this
0x18005a49b  call    ?OnSocketConnect@CWnpConnector@@AEAAXXZ; CWnpConnector::OnSocketConnect(void)
0x18005a4a0  jmp     loc_18005A921
0x18005a4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a4ac  mov     esi, 8004ACA8h
0x18005a4b1  cmp     rcx, rdi
0x18005a4b4  jz      short loc_18005A4DB
0x18005a4b6  test    byte ptr [rcx+1Ch], 4
0x18005a4ba  jz      short loc_18005A4DB
0x18005a4bc  cmp     byte ptr [rcx+19h], 2
0x18005a4c0  jb      short loc_18005A4DB
0x18005a4c2  mov     rcx, [rcx+10h]
0x18005a4c6  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a4cd  mov     edx, 0EAh
0x18005a4d2  mov     dword ptr [rsp+88h+var_68], esi
0x18005a4d6  call    WPP_SF_Dd
0x18005a4db  mov     edx, esi; int
0x18005a4dd  mov     rcx, rbx; this
0x18005a4e0  call    ?LogConnectToProxyEnd@CWnpConnector@@AEAAXJ@Z; CWnpConnector::LogConnectToProxyEnd(long)
0x18005a4e5  mov     edx, esi
0x18005a4e7  jmp     short loc_18005A52B
0x18005a4e9  cmp     rcx, rdi
0x18005a4ec  jz      short loc_18005A51D
0x18005a4ee  test    byte ptr [rcx+1Ch], 4
0x18005a4f2  jz      short loc_18005A51D
0x18005a4f4  cmp     byte ptr [rcx+19h], 2
0x18005a4f8  jb      short loc_18005A51D
0x18005a4fa  test    byte ptr [rbx+6Ch], 8
0x18005a4fe  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005a505  mov     rcx, [rcx+10h]
0x18005a509  mov     r9d, r14d
0x18005a50c  setnbe  al
0x18005a50f  mov     edx, 0EBh
0x18005a514  mov     [rsp+88h+var_68], al
0x18005a518  call    WPP_SF_dc
0x18005a51d  mov     edx, r14d; int
0x18005a520  mov     rcx, rbx; this
0x18005a523  call    ?LogConnectToProxyEnd@CWnpConnector@@AEAAXJ@Z; CWnpConnector::LogConnectToProxyEnd(long)
0x18005a528  mov     edx, r14d
0x18005a52b  mov     rcx, rbx
0x18005a52e  call    ?OnError@CWnpConnector@@AEAAXJW4LogCommandFailureContext@@@Z; CWnpConnector::OnError(long,LogCommandFailureContext)
0x18005a533  jmp     loc_18005A921
0x18005a538  mov     edx, ebp; int
0x18005a53a  mov     qword ptr [rbx+0A0h], 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
