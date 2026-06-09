# CBthActiveConnector::_Run(void)

- ea: `0x180004620`
- end: `0x180004c3c`
- name: `?_Run@CBthActiveConnector@@AEAAJXZ`
- size: `1564`
- prototype: `__int64 __fastcall(CBthActiveConnector *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800066f0`

## callees

- `0x180004620`
- `0x180004c50`
- `0x180007880`
- `0x180007f28`
- `0x1800080e0`
- `0x18000dfd4`
- `0x18000e080`
- `0x18000e170`
- `0x18000e53c`
- `0x18000e8e4`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004a84`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004a84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800047c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800047c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000497b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000497b`
- `USER32!DispatchMessageW` at `0x180004736`
- `USER32!DispatchMessageW` at `0x180004b35`
- `USER32!DispatchMessageW` at `0x180004736`
- `USER32!DispatchMessageW` at `0x180004b35`
- `USER32!PeekMessageW` at `0x180004724`
- `USER32!PeekMessageW` at `0x180004750`
- `USER32!PeekMessageW` at `0x180004b23`
- `USER32!PeekMessageW` at `0x180004b4f`
- `USER32!PeekMessageW` at `0x180004724`
- `USER32!PeekMessageW` at `0x180004750`
- `USER32!PeekMessageW` at `0x180004b23`
- `USER32!PeekMessageW` at `0x180004b4f`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18000468a`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180004aac`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18000468a`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180004aac`

## pseudocode

```c
__int64 __fastcall CBthActiveConnector::_Run(CBthActiveConnector *this)
{
  unsigned int v2; // r14d
  void *v3; // rdi
  DWORD v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  DWORD v7; // ebx
  DWORD v8; // eax
  CPnPNotification *v9; // rcx
  CPnPNotification *v10; // rcx
  HRESULT v11; // eax
  unsigned int v12; // ebx
  _DWORD *v13; // rbx
  char *v14; // rdi
  char *v15; // rsi
  int v16; // r14d
  int v17; // eax
  CBthActiveConnector *v18; // rcx
  int v19; // eax
  CPnPNotification *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  int refreshed; // eax
  CPnPNotification *v24; // rcx
  DWORD v25; // ebx
  void *v26; // rdi
  DWORD v27; // eax
  DWORD v28; // eax
  LPVOID v29; // rcx
  tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF
  HANDLE pHandles; // [rsp+B0h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v34; // [rsp+C0h] [rbp+58h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp+60h] BYREF

  v2 = 0;
  while ( 1 )
  {
LABEL_2:
    if ( *((_DWORD *)this + 3) )
      return v2;
    v3 = (void *)*((_QWORD *)this + 3);
    pHandles = v3;
    while ( 1 )
    {
      v4 = MsgWaitForMultipleObjectsEx(1u, &pHandles, 0xFFFFFFFF, 0x1CFFu, 4u);
      v7 = v4;
      if ( !v4 )
        break;
      v8 = v4 - 1;
      if ( v8 )
      {
        if ( v8 == 257 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                61,
                &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
                0xFFFFFFFFLL);
              v9 = WPP_GLOBAL_Control;
            }
            if ( v9 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
              WPP_SF_L(*((_QWORD *)v9 + 2), v5, v6, v7);
          }
          goto LABEL_2;
        }
      }
      else
      {
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
          DispatchMessageW(&Msg);
      }
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v3);
      v10 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)this + 3) == 1 )
    {
      if ( v10 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x800) != 0 )
        WPP_SF_(*((_QWORD *)v10 + 2), 41, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids);
      return v2;
    }
    ppv = 0;
    v11 = CoCreateInstance(&CLSID_EnumBthMtpConnectors, 0, 1u, &GUID_bfdef549_9247_454f_bd82_06fe80853faa, &ppv);
    v12 = v11;
    if ( v11 < 0 )
      break;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids);
    }
    v13 = (_DWORD *)((char *)this + 4);
    v14 = (char *)this + 4;
    do
    {
      v15 = v14;
      if ( *((_DWORD *)this + 3) )
        break;
      v14 = (char *)this + 4;
      v15 = (char *)this + 4;
      if ( *((_DWORD *)this + 1) != 1 )
        break;
      LODWORD(pHandles) = 0;
      pv = 0;
      v34 = 0;
      v16 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *, HANDLE *))(*(_QWORD *)ppv + 24LL))(
              ppv,
              1,
              &v34,
              &pHandles);
      if ( !v16 && (_DWORD)pHandles == 1 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v34 + 64LL))(v34, &pv);
        if ( v17 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
              (unsigned int)v17);
          }
          goto LABEL_48;
        }
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, pv);
        }
        if ( CBthActiveConnector::_IsActiveConnectEnabled(v18, (const unsigned __int16 *)pv) )
        {
          v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v34 + 24LL))(v34, 0);
          if ( v19 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                (unsigned int)&WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
                (_DWORD)pv,
                v19);
            }
            goto LABEL_48;
          }
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            v21 = 46;
            goto LABEL_47;
          }
        }
        else
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            v21 = 48;
LABEL_47:
            WPP_SF_(*((_QWORD *)v20 + 2), v21, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids);
          }
        }
LABEL_48:
        CoTaskMemFree(pv);
        pv = 0;
        v22 = v34;
        if ( v34 )
        {
          v34 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
      }
      ATL::CComPtrBase<IEnumPortableDeviceConnectors>::~CComPtrBase<IEnumPortableDeviceConnectors>(&v34);
      v15 = (char *)this + 4;
    }
    while ( !v16 );
    refreshed = CBthActiveConnector::_RefreshWaitInterval(this);
    v2 = refreshed;
    if ( refreshed >= 0 )
    {
      v13 = v15;
      v24 = WPP_GLOBAL_Control;
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
          (unsigned int)refreshed);
        v24 = WPP_GLOBAL_Control;
      }
      v2 = 0;
    }
    if ( !*((_DWORD *)this + 3) && *v13 == 1 )
    {
      if ( *((_DWORD *)this + 10) )
      {
        v25 = *(_DWORD *)this;
        if ( !*(_DWORD *)this )
          v25 = -1;
      }
      else
      {
        if ( v24 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_DWORD *)v24 + 7) & 0x800) != 0 )
        {
          WPP_SF_(*((_QWORD *)v24 + 2), 58, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids);
          v24 = WPP_GLOBAL_Control;
        }
        v25 = -1;
      }
      if ( v24 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_DWORD *)v24 + 7) & 0x800) != 0 )
        WPP_SF_d(*((_QWORD *)v24 + 2), 59, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v25);
      ResetEvent(*((HANDLE *)this + 2));
      v26 = (void *)*((_QWORD *)this + 2);
      pHandles = v26;
      while ( 1 )
      {
        v27 = MsgWaitForMultipleObjectsEx(1u, &pHandles, v25, 0x1CFFu, 4u);
        if ( !v27 )
          break;
        v28 = v27 - 1;
        if ( v28 )
        {
          if ( v28 == 257 )
          {
            if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v25);
            }
            goto LABEL_82;
          }
        }
        else
        {
          memset(&Msg, 0, sizeof(Msg));
          while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
            DispatchMessageW(&Msg);
        }
      }
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v26);
      }
    }
LABEL_82:
    v29 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
      v29 = ppv;
    }
    if ( v29 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
  }
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
      (unsigned int)v11);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v12;
}

```

## disassembly

```asm
0x180004620  push    rbp
0x180004622  push    rbx
0x180004623  push    rsi
0x180004624  push    rdi
0x180004625  push    r12
0x180004627  push    r13
0x180004629  push    r14
0x18000462b  push    r15
0x18000462d  mov     rbp, rsp
0x180004630  sub     rsp, 68h
0x180004634  mov     r15, rcx
0x180004637  xor     esi, esi
0x180004639  mov     r14d, esi
0x18000463c  mov     r13d, 0FFFFFFFFh
0x180004642  lea     r12, WPP_GLOBAL_Control
0x180004649  nop     dword ptr [rax+00000000h]
0x180004650  cmp     dword ptr [r15+0Ch], 0
0x180004655  jnz     loc_180004C28
0x18000465b  mov     rdi, [r15+18h]
0x18000465f  mov     [rbp+pHandles], rdi
0x180004663  nop     dword ptr [rax+00h]
0x180004667  nop     word ptr [rax+rax+00000000h]
0x180004670  mov     [rsp+68h+dwFlags], 4; dwFlags
0x180004678  mov     r9d, 1CFFh; dwWakeMask
0x18000467e  mov     r8d, r13d; dwMilliseconds
0x180004681  lea     rdx, [rbp+pHandles]; pHandles
0x180004685  mov     ecx, 1; nCount
0x18000468a  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180004690  mov     ebx, eax
0x180004692  test    eax, eax
0x180004694  jz      loc_18000475F
0x18000469a  sub     eax, 1
0x18000469d  jz      short loc_180004701
0x18000469f  cmp     eax, 101h
0x1800046a4  jnz     short loc_180004670
0x1800046a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046ad  cmp     rcx, r12
0x1800046b0  jz      short loc_180004650
0x1800046b2  test    dword ptr [rcx+1Ch], 800h
0x1800046b9  jz      short loc_1800046DD
0x1800046bb  mov     edx, 3Dh ; '='
0x1800046c0  mov     r9d, 0FFFFFFFFh
0x1800046c6  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x1800046cd  mov     rcx, [rcx+10h]
0x1800046d1  call    WPP_SF_d
0x1800046d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046dd  cmp     rcx, r12
0x1800046e0  jz      loc_180004650
0x1800046e6  test    byte ptr [rcx+1Ch], 4
0x1800046ea  jz      loc_180004650
0x1800046f0  mov     r9d, ebx
0x1800046f3  mov     rcx, [rcx+10h]
0x1800046f7  call    WPP_SF_L
0x1800046fc  jmp     loc_180004650
0x180004701  xorps   xmm0, xmm0
0x180004704  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x180004708  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18000470c  movups  xmmword ptr [rbp+Msg.time], xmm0
0x180004710  mov     [rsp+68h+dwFlags], 1; wRemoveMsg
0x180004718  xor     r9d, r9d; wMsgFilterMax
0x18000471b  xor     r8d, r8d; wMsgFilterMin
0x18000471e  xor     edx, edx; hWnd
0x180004720  lea     rcx, [rbp+Msg]; lpMsg
0x180004724  call    cs:__imp_PeekMessageW
0x18000472a  test    eax, eax
0x18000472c  jz      loc_180004670
0x180004732  lea     rcx, [rbp+Msg]; lpMsg
0x180004736  call    cs:__imp_DispatchMessageW
0x18000473c  mov     [rsp+68h+dwFlags], 1; wRemoveMsg
0x180004744  xor     r9d, r9d; wMsgFilterMax
0x180004747  xor     r8d, r8d; wMsgFilterMin
0x18000474a  xor     edx, edx; hWnd
0x18000474c  lea     rcx, [rbp+Msg]; lpMsg
0x180004750  call    cs:__imp_PeekMessageW
0x180004756  test    eax, eax
0x180004758  jnz     short loc_180004732
0x18000475a  jmp     loc_180004670
0x18000475f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004766  cmp     rcx, r12
0x180004769  jz      short loc_180004793
0x18000476b  test    dword ptr [rcx+1Ch], 800h
0x180004772  jz      short loc_180004793
0x180004774  mov     edx, 3Ch ; '<'
0x180004779  mov     r9, rdi
0x18000477c  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004783  mov     rcx, [rcx+10h]
0x180004787  call    WPP_SF_q
0x18000478c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004793  cmp     dword ptr [r15+0Ch], 1
0x180004798  jz      loc_180004C05
0x18000479e  mov     [rbp+ppv], rsi
0x1800047a2  lea     rax, [rbp+ppv]
0x1800047a6  mov     qword ptr [rsp+68h+dwFlags], rax; ppv
0x1800047ab  lea     r9, _GUID_bfdef549_9247_454f_bd82_06fe80853faa; riid
0x1800047b2  xor     edx, edx; pUnkOuter
0x1800047b4  mov     r8d, 1; dwClsContext
0x1800047ba  lea     rcx, CLSID_EnumBthMtpConnectors; rclsid
0x1800047c1  call    cs:__imp_CoCreateInstance
0x1800047c7  mov     ebx, eax
0x1800047c9  test    eax, eax
0x1800047cb  js      loc_180004BC0
0x1800047d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047d8  cmp     rcx, r12
0x1800047db  jz      short loc_1800047FB
0x1800047dd  test    dword ptr [rcx+1Ch], 800h
0x1800047e4  jz      short loc_1800047FB
0x1800047e6  mov     edx, 2Bh ; '+'
0x1800047eb  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x1800047f2  mov     rcx, [rcx+10h]
0x1800047f6  call    WPP_SF_
0x1800047fb  lea     rbx, [r15+4]
0x1800047ff  mov     rdi, rbx
0x180004802  mov     rsi, rdi
0x180004805  cmp     dword ptr [r15+0Ch], 0
0x18000480a  jnz     loc_1800049B4
0x180004810  lea     rdi, [r15+4]
0x180004814  mov     rsi, rdi
0x180004817  cmp     dword ptr [rdi], 1
0x18000481a  jnz     loc_1800049B4
0x180004820  xor     esi, esi
0x180004822  mov     dword ptr [rbp+pHandles], esi
0x180004825  mov     [rbp+pv], rsi
0x180004829  mov     [rbp+arg_10], rsi
0x18000482d  mov     rcx, [rbp+ppv]
0x180004831  mov     rax, [rcx]
0x180004834  lea     r9, [rbp+pHandles]
0x180004838  lea     r8, [rbp+arg_10]
0x18000483c  mov     edx, 1
0x180004841  mov     rax, [rax+18h]
0x180004845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000484a  mov     r14d, eax
0x18000484d  test    eax, eax
0x18000484f  jnz     loc_18000499F
0x180004855  cmp     dword ptr [rbp+pHandles], 1
0x180004859  jnz     loc_18000499F
0x18000485f  mov     rcx, [rbp+arg_10]
0x180004863  mov     rax, [rcx]
0x180004866  lea     rdx, [rbp+pv]
0x18000486a  mov     rax, [rax+40h]
0x18000486e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004873  test    eax, eax
0x180004875  jns     short loc_1800048AE
0x180004877  mov     rcx, cs:WPP_GLOBAL_Control
0x18000487e  cmp     rcx, r12
0x180004881  jz      loc_180004977
0x180004887  test    byte ptr [rcx+1Ch], 2
0x18000488b  jz      loc_180004977
0x180004891  mov     edx, 2Ch ; ','
0x180004896  mov     r9d, eax
0x180004899  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x1800048a0  mov     rcx, [rcx+10h]
0x1800048a4  call    WPP_SF_d
0x1800048a9  jmp     loc_180004977
0x1800048ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048b5  cmp     rcx, r12
0x1800048b8  jz      short loc_1800048DC
0x1800048ba  test    dword ptr [rcx+1Ch], 800h
0x1800048c1  jz      short loc_1800048DC
0x1800048c3  mov     edx, 2Dh ; '-'
0x1800048c8  mov     r9, [rbp+pv]
0x1800048cc  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x1800048d3  mov     rcx, [rcx+10h]
0x1800048d7  call    WPP_SF_S
0x1800048dc  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800048e0  call    ?_IsActiveConnectEnabled@CBthActiveConnector@@AEAAHPEBG@Z; CBthActiveConnector::_IsActiveConnectEnabled(ushort const *)
0x1800048e5  cmp     eax, 1
0x1800048e8  jnz     short loc_18000494D
0x1800048ea  mov     rcx, [rbp+arg_10]
0x1800048ee  mov     rax, [rcx]
0x1800048f1  xor     edx, edx
0x1800048f3  mov     rax, [rax+18h]
0x1800048f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048fc  test    eax, eax
0x1800048fe  js      short loc_18000491C
0x180004900  mov     rcx, cs:WPP_GLOBAL_Control
0x180004907  cmp     rcx, r12
0x18000490a  jz      short loc_180004977
0x18000490c  test    dword ptr [rcx+1Ch], 800h
0x180004913  jz      short loc_180004977
0x180004915  mov     edx, 2Eh ; '.'
0x18000491a  jmp     short loc_180004967
0x18000491c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004923  cmp     rcx, r12
0x180004926  jz      short loc_180004977
0x180004928  test    byte ptr [rcx+1Ch], 2
0x18000492c  jz      short loc_180004977
0x18000492e  mov     edx, 2Fh ; '/'
0x180004933  mov     [rsp+68h+dwFlags], eax
0x180004937  mov     r9, [rbp+pv]
0x18000493b  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004942  mov     rcx, [rcx+10h]
0x180004946  call    WPP_SF_Sd
0x18000494b  jmp     short loc_180004977
0x18000494d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004954  cmp     rcx, r12
0x180004957  jz      short loc_180004977
0x180004959  test    dword ptr [rcx+1Ch], 800h
0x180004960  jz      short loc_180004977
0x180004962  mov     edx, 30h ; '0'
0x180004967  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x18000496e  mov     rcx, [rcx+10h]
0x180004972  call    WPP_SF_
0x180004977  mov     rcx, [rbp+pv]; pv
0x18000497b  call    cs:__imp_CoTaskMemFree
0x180004981  mov     [rbp+pv], rsi
0x180004985  mov     rcx, [rbp+arg_10]
0x180004989  test    rcx, rcx
0x18000498c  jz      short loc_18000499F
0x18000498e  mov     [rbp+arg_10], rsi
0x180004992  mov     rax, [rcx]
0x180004995  mov     rax, [rax+10h]
0x180004999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000499e  nop
0x18000499f  lea     rcx, [rbp+arg_10]
0x1800049a3  call    ??1?$CComPtrBase@UIEnumPortableDeviceConnectors@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumPortableDeviceConnectors>::~CComPtrBase<IEnumPortableDeviceConnectors>(void)
0x1800049a8  mov     rsi, rdi
0x1800049ab  test    r14d, r14d
0x1800049ae  jz      loc_180004802
0x1800049b4  mov     rcx, r15; this
0x1800049b7  call    ?_RefreshWaitInterval@CBthActiveConnector@@AEAAJXZ; CBthActiveConnector::_RefreshWaitInterval(void)
0x1800049bc  mov     r14d, eax
0x1800049bf  test    eax, eax
0x1800049c1  jns     short loc_1800049FB
0x1800049c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049ca  cmp     rcx, r12
0x1800049cd  jz      short loc_1800049F4
0x1800049cf  test    byte ptr [rcx+1Ch], 4
0x1800049d3  jz      short loc_1800049F4
0x1800049d5  mov     edx, 31h ; '1'
0x1800049da  mov     r9d, eax
0x1800049dd  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x1800049e4  mov     rcx, [rcx+10h]
0x1800049e8  call    WPP_SF_d
0x1800049ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049f4  xor     esi, esi
0x1800049f6  mov     r14d, esi
0x1800049f9  jmp     short loc_180004A07
0x1800049fb  mov     rbx, rsi
0x1800049fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a05  xor     esi, esi
0x180004a07  cmp     dword ptr [r15+0Ch], 0
0x180004a0c  jnz     loc_180004B8C
0x180004a12  cmp     dword ptr [rbx], 1
0x180004a15  jnz     loc_180004B8C
0x180004a1b  cmp     dword ptr [r15+28h], 0
0x180004a20  jnz     short loc_180004A51
0x180004a22  cmp     rcx, r12
0x180004a25  jz      short loc_180004A4C
0x180004a27  test    dword ptr [rcx+1Ch], 800h
0x180004a2e  jz      short loc_180004A4C
0x180004a30  mov     edx, 3Ah ; ':'
0x180004a35  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004a3c  mov     rcx, [rcx+10h]
0x180004a40  call    WPP_SF_
0x180004a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a4c  mov     ebx, r13d
0x180004a4f  jmp     short loc_180004A5A
0x180004a51  mov     ebx, [r15]
0x180004a54  test    ebx, ebx
0x180004a56  cmovz   ebx, r13d
0x180004a5a  cmp     rcx, r12
0x180004a5d  jz      short loc_180004A80
0x180004a5f  test    dword ptr [rcx+1Ch], 800h
0x180004a66  jz      short loc_180004A80
0x180004a68  mov     edx, 3Bh ; ';'
0x180004a6d  mov     r9d, ebx
0x180004a70  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004a77  mov     rcx, [rcx+10h]
0x180004a7b  call    WPP_SF_d
0x180004a80  mov     rcx, [r15+10h]; hEvent
0x180004a84  call    cs:__imp_ResetEvent
0x180004a8a  mov     rdi, [r15+10h]
0x180004a8e  mov     [rbp+pHandles], rdi
0x180004a92  mov     [rsp+68h+dwFlags], 4; dwFlags
0x180004a9a  mov     r9d, 1CFFh; dwWakeMask
0x180004aa0  mov     r8d, ebx; dwMilliseconds
0x180004aa3  lea     rdx, [rbp+pHandles]; pHandles
0x180004aa7  mov     ecx, 1; nCount
0x180004aac  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180004ab2  test    eax, eax
0x180004ab4  jz      loc_180004B5E
0x180004aba  sub     eax, 1
0x180004abd  jz      short loc_180004B00
0x180004abf  cmp     eax, 101h
0x180004ac4  jnz     short loc_180004A92
0x180004ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004acd  cmp     rcx, r12
0x180004ad0  jz      loc_180004B8C
0x180004ad6  test    dword ptr [rcx+1Ch], 800h
0x180004add  jz      loc_180004B8C
0x180004ae3  mov     edx, 3Dh ; '='
0x180004ae8  mov     r9d, ebx
0x180004aeb  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004af2  mov     rcx, [rcx+10h]
0x180004af6  call    WPP_SF_d
0x180004afb  jmp     loc_180004B8C
0x180004b00  xorps   xmm0, xmm0
0x180004b03  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x180004b07  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x180004b0b  movups  xmmword ptr [rbp+Msg.time], xmm0
  ... truncated ...
```
