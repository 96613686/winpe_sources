# CWcnConnectionEngine::WaitForPbc(void)

- ea: `0x180020d60`
- end: `0x1800210c8`
- name: `?WaitForPbc@CWcnConnectionEngine@@AEAAJXZ`
- size: `872`
- prototype: `__int64 __fastcall(CWcnConnectionEngine *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x18000d630`
- `0x18000e0a0`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001fe2c`
- `0x180020ba0`
- `0x180020d60`
- `0x180021500`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180021070`
- `KERNEL32!ResetEvent` at `0x180021070`
- `KERNEL32!WaitForSingleObject` at `0x180020fba`
- `KERNEL32!WaitForSingleObject` at `0x180020fba`
- `wlanapi!WlanCloseHandle` at `0x180021066`
- `wlanapi!WlanCloseHandle` at `0x180021066`
- `wlanapi!WlanOpenHandle` at `0x180020dd2`
- `wlanapi!WlanOpenHandle` at `0x180020dd2`
- `wlanapi!WlanInternalScan` at `0x180020f11`
- `wlanapi!WlanInternalScan` at `0x180020f11`
- `wlanapi!WlanRegisterNotification` at `0x180020e57`
- `wlanapi!WlanRegisterNotification` at `0x180020e57`
- `wlanapi!WlanScan` at `0x180020ed9`
- `wlanapi!WlanScan` at `0x180020ed9`

## pseudocode

```c
__int64 __fastcall CWcnConnectionEngine::WaitForPbc(CWcnConnectionEngine *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int v6; // ebx
  _QWORD *v7; // r10
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int v10; // r14d
  signed int v11; // eax
  unsigned int v12; // ecx
  _QWORD *v13; // r8
  __int64 v14; // rdx
  int State; // eax
  int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // r10
  DWORD pdwNegotiatedVersion; // [rsp+68h] [rbp+10h] BYREF
  void *phClientHandle; // [rsp+70h] [rbp+18h] BYREF

  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 35, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, Indent);
  }
  v4 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    else
      v5 = v4;
    v6 = v5 | 0x80000000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_56;
    v8 = 36;
LABEL_11:
    WPP_SF_Dd(v7[2], v8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, (unsigned int)v4, v6);
LABEL_55:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  v4 = WlanRegisterNotification(phClientHandle, 8u, 0, CWcnConnectionEngine::WlanNotificationCallbackThunk, this, 0, 0);
  if ( v4 )
  {
    if ( v4 > 0 )
      v9 = (unsigned __int16)v4 | 0x80070000;
    else
      v9 = v4;
    v6 = v9 | 0x80000000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_56;
    v8 = 37;
    goto LABEL_11;
  }
  v10 = 0;
  (***((void (__fastcall ****)(_QWORD, __int64))this + 20))(*((_QWORD *)this + 20), 2);
  while ( 1 )
  {
    if ( (++v10 & 3) != 0 )
    {
      v11 = WlanScan(phClientHandle, (const GUID *)((char *)this + 44), (const PDOT11_SSID)((char *)this + 60), 0, 0);
      if ( v11 )
      {
        v12 = v11 > 0 ? (unsigned __int16)v11 | 0x80070000 : v11;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v14 = 38;
LABEL_35:
          WPP_SF__guid_Dd(v13[2], v14, v13, (char *)this + 44, v11, v12 | 0x80000000);
        }
      }
    }
    else
    {
      v11 = WlanInternalScan((char *)this + 44, 0);
      if ( v11 )
      {
        v12 = v11 > 0 ? (unsigned __int16)v11 | 0x80070000 : v11;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v14 = 39;
          goto LABEL_35;
        }
      }
    }
    State = CWcnConnectionEngine::WaitForNextState(this, 0x7530u);
    v6 = State;
    if ( State != -2147023436 && State < 0 )
      goto LABEL_55;
    v16 = CWcnConnectionEngine::CheckForNetworksWithPbc(this, phClientHandle, 0);
    v6 = v16;
    if ( v16 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 40;
        goto LABEL_54;
      }
      goto LABEL_56;
    }
    if ( !v16 )
      goto LABEL_47;
    v16 = CWcnConnectionEngine::CheckForNetworksWithPbc(this, phClientHandle, 1);
    v6 = v16;
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
LABEL_47:
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, const unsigned __int16 *))(**((_QWORD **)this + 14) + 24LL))(
              *((_QWORD *)this + 14),
              0,
              0,
              &word_18003746E);
      v6 = v16;
      if ( v16 >= 0 )
        goto LABEL_55;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 42;
        goto LABEL_54;
      }
      goto LABEL_56;
    }
    if ( !WaitForSingleObject(*((HANDLE *)this + 3), 0x1F4u) )
    {
      v6 = -2147023673;
      goto LABEL_55;
    }
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 41;
LABEL_54:
    WPP_SF_d(v7[2], v17, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, (unsigned int)v16);
    goto LABEL_55;
  }
LABEL_56:
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    ResetEvent(*((HANDLE *)this + 4));
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (v6 < 0 || *((_BYTE *)v7 + 25) >= 6u) )
  {
    v18 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v19 + 16), 43, (unsigned int)WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids, v18, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020d60  mov     rax, rsp
0x180020d63  mov     [rax+8], rbx
0x180020d67  mov     [rax+20h], rsi
0x180020d6b  push    r13
0x180020d6d  push    r14
0x180020d6f  push    r15
0x180020d71  sub     rsp, 40h
0x180020d75  mov     rsi, rcx
0x180020d78  mov     qword ptr [rax+18h], 0
0x180020d80  mov     dword ptr [rax+10h], 0
0x180020d87  mov     r10, cs:WPP_GLOBAL_Control
0x180020d8e  lea     r13, WPP_GLOBAL_Control
0x180020d95  cmp     r10, r13
0x180020d98  jz      short loc_180020DC3
0x180020d9a  cmp     byte ptr [r10+19h], 6
0x180020d9f  jb      short loc_180020DC3
0x180020da1  mov     ecx, 1; int
0x180020da6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180020dab  mov     rcx, [r10+10h]
0x180020daf  lea     r8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x180020db6  mov     edx, 23h ; '#'
0x180020dbb  mov     r9, rax
0x180020dbe  call    WPP_SF_s
0x180020dc3  xor     edx, edx; pReserved
0x180020dc5  lea     r9, [rsp+58h+phClientHandle]; phClientHandle
0x180020dca  lea     r8, [rsp+58h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180020dcf  lea     ecx, [rdx+2]; dwClientVersion
0x180020dd2  call    cs:__imp_WlanOpenHandle
0x180020dd8  test    eax, eax
0x180020dda  jz      short loc_180020E2D
0x180020ddc  jg      short loc_180020DE2
0x180020dde  mov     ebx, eax
0x180020de0  jmp     short loc_180020DEB
0x180020de2  movzx   ebx, ax
0x180020de5  or      ebx, 80070000h
0x180020deb  or      ebx, 80000000h
0x180020df1  mov     r10, cs:WPP_GLOBAL_Control
0x180020df8  cmp     r10, r13
0x180020dfb  jz      loc_18002105A
0x180020e01  cmp     byte ptr [r10+19h], 2
0x180020e06  jb      loc_18002105A
0x180020e0c  mov     edx, 24h ; '$'
0x180020e11  mov     rcx, [r10+10h]
0x180020e15  lea     r8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x180020e1c  mov     r9d, eax
0x180020e1f  mov     dword ptr [rsp+58h+pCallbackContext], ebx
0x180020e23  call    WPP_SF_Dd
0x180020e28  jmp     loc_180021053
0x180020e2d  mov     rcx, [rsp+58h+phClientHandle]; hClientHandle
0x180020e32  lea     r9, ?WlanNotificationCallbackThunk@CWcnConnectionEngine@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x180020e39  xor     r8d, r8d; bIgnoreDuplicate
0x180020e3c  mov     [rsp+58h+pdwPrevNotifSource], 0; pdwPrevNotifSource
0x180020e45  mov     [rsp+58h+pReserved], 0; pReserved
0x180020e4e  mov     [rsp+58h+pCallbackContext], rsi; pCallbackContext
0x180020e53  lea     edx, [r8+8]; dwNotifSource
0x180020e57  call    cs:__imp_WlanRegisterNotification
0x180020e5d  test    eax, eax
0x180020e5f  jz      short loc_180020E9B
0x180020e61  jg      short loc_180020E67
0x180020e63  mov     ebx, eax
0x180020e65  jmp     short loc_180020E70
0x180020e67  movzx   ebx, ax
0x180020e6a  or      ebx, 80070000h
0x180020e70  or      ebx, 80000000h
0x180020e76  mov     r10, cs:WPP_GLOBAL_Control
0x180020e7d  cmp     r10, r13
0x180020e80  jz      loc_18002105A
0x180020e86  cmp     byte ptr [r10+19h], 2
0x180020e8b  jb      loc_18002105A
0x180020e91  mov     edx, 25h ; '%'
0x180020e96  jmp     loc_180020E11
0x180020e9b  mov     rcx, [rsi+0A0h]
0x180020ea2  xor     r14d, r14d
0x180020ea5  mov     rax, [rcx]
0x180020ea8  lea     edx, [r14+2]
0x180020eac  mov     rax, [rax]
0x180020eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020eb4  lea     r15, [rsi+2Ch]
0x180020eb8  inc     r14d
0x180020ebb  test    r14b, 3
0x180020ebf  jz      short loc_180020F0C
0x180020ec1  mov     rcx, [rsp+58h+phClientHandle]; hClientHandle
0x180020ec6  lea     r8, [rsi+3Ch]; pDot11Ssid
0x180020eca  xor     r9d, r9d; pIeData
0x180020ecd  mov     [rsp+58h+pCallbackContext], 0; pReserved
0x180020ed6  mov     rdx, r15; pInterfaceGuid
0x180020ed9  call    cs:__imp_WlanScan
0x180020edf  test    eax, eax
0x180020ee1  jz      short loc_180020F5C
0x180020ee3  jg      short loc_180020EE9
0x180020ee5  mov     ecx, eax
0x180020ee7  jmp     short loc_180020EF2
0x180020ee9  movzx   ecx, ax
0x180020eec  or      ecx, 80070000h
0x180020ef2  mov     r8, cs:WPP_GLOBAL_Control
0x180020ef9  cmp     r8, r13
0x180020efc  jz      short loc_180020F5C
0x180020efe  cmp     byte ptr [r8+19h], 3
0x180020f03  jb      short loc_180020F5C
0x180020f05  mov     edx, 26h ; '&'
0x180020f0a  jmp     short loc_180020F42
0x180020f0c  xor     edx, edx
0x180020f0e  mov     rcx, r15
0x180020f11  call    cs:__imp_WlanInternalScan
0x180020f17  test    eax, eax
0x180020f19  jz      short loc_180020F5C
0x180020f1b  jg      short loc_180020F21
0x180020f1d  mov     ecx, eax
0x180020f1f  jmp     short loc_180020F2A
0x180020f21  movzx   ecx, ax
0x180020f24  or      ecx, 80070000h
0x180020f2a  mov     r8, cs:WPP_GLOBAL_Control
0x180020f31  cmp     r8, r13
0x180020f34  jz      short loc_180020F5C
0x180020f36  cmp     byte ptr [r8+19h], 3
0x180020f3b  jb      short loc_180020F5C
0x180020f3d  mov     edx, 27h ; '''
0x180020f42  or      ecx, 80000000h
0x180020f48  mov     r9, r15
0x180020f4b  mov     dword ptr [rsp+58h+pReserved], ecx
0x180020f4f  mov     rcx, [r8+10h]
0x180020f53  mov     dword ptr [rsp+58h+pCallbackContext], eax
0x180020f57  call    WPP_SF__guid_Dd
0x180020f5c  mov     edx, 7530h; unsigned int
0x180020f61  mov     rcx, rsi; this
0x180020f64  call    ?WaitForNextState@CWcnConnectionEngine@@AEAAJK@Z; CWcnConnectionEngine::WaitForNextState(ulong)
0x180020f69  mov     ebx, eax
0x180020f6b  cmp     eax, 800705B4h
0x180020f70  jz      short loc_180020F7A
0x180020f72  test    eax, eax
0x180020f74  js      loc_180021053
0x180020f7a  mov     rdx, [rsp+58h+phClientHandle]; void *
0x180020f7f  xor     r8d, r8d; int
0x180020f82  mov     rcx, rsi; this
0x180020f85  call    ?CheckForNetworksWithPbc@CWcnConnectionEngine@@AEAAJPEAXH@Z; CWcnConnectionEngine::CheckForNetworksWithPbc(void *,int)
0x180020f8a  mov     ebx, eax
0x180020f8c  test    eax, eax
0x180020f8e  js      loc_180021028
0x180020f94  jz      short loc_180020FEC
0x180020f96  mov     rdx, [rsp+58h+phClientHandle]; void *
0x180020f9b  mov     r8d, 1; int
0x180020fa1  mov     rcx, rsi; this
0x180020fa4  call    ?CheckForNetworksWithPbc@CWcnConnectionEngine@@AEAAJPEAXH@Z; CWcnConnectionEngine::CheckForNetworksWithPbc(void *,int)
0x180020fa9  mov     ebx, eax
0x180020fab  test    eax, eax
0x180020fad  js      short loc_180020FD2
0x180020faf  jz      short loc_180020FEC
0x180020fb1  mov     rcx, [rsi+18h]; hHandle
0x180020fb5  mov     edx, 1F4h; dwMilliseconds
0x180020fba  call    cs:__imp_WaitForSingleObject
0x180020fc0  test    eax, eax
0x180020fc2  jnz     loc_180020EB8
0x180020fc8  mov     ebx, 800704C7h
0x180020fcd  jmp     loc_180021053
0x180020fd2  mov     r10, cs:WPP_GLOBAL_Control
0x180020fd9  cmp     r10, r13
0x180020fdc  jz      short loc_18002105A
0x180020fde  cmp     byte ptr [r10+19h], 2
0x180020fe3  jb      short loc_18002105A
0x180020fe5  mov     edx, 29h ; ')'
0x180020fea  jmp     short loc_180021040
0x180020fec  mov     rcx, [rsi+70h]
0x180020ff0  lea     r9, word_18003746E
0x180020ff7  xor     r8d, r8d
0x180020ffa  xor     edx, edx
0x180020ffc  mov     rax, [rcx]
0x180020fff  mov     rax, [rax+18h]
0x180021003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021008  mov     ebx, eax
0x18002100a  test    eax, eax
0x18002100c  jns     short loc_180021053
0x18002100e  mov     r10, cs:WPP_GLOBAL_Control
0x180021015  cmp     r10, r13
0x180021018  jz      short loc_18002105A
0x18002101a  cmp     byte ptr [r10+19h], 2
0x18002101f  jb      short loc_18002105A
0x180021021  mov     edx, 2Ah ; '*'
0x180021026  jmp     short loc_180021040
0x180021028  mov     r10, cs:WPP_GLOBAL_Control
0x18002102f  cmp     r10, r13
0x180021032  jz      short loc_18002105A
0x180021034  cmp     byte ptr [r10+19h], 2
0x180021039  jb      short loc_18002105A
0x18002103b  mov     edx, 28h ; '('
0x180021040  mov     rcx, [r10+10h]
0x180021044  lea     r8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x18002104b  mov     r9d, eax
0x18002104e  call    WPP_SF_d
0x180021053  mov     r10, cs:WPP_GLOBAL_Control
0x18002105a  mov     rcx, [rsp+58h+phClientHandle]; hClientHandle
0x18002105f  test    rcx, rcx
0x180021062  jz      short loc_18002107D
0x180021064  xor     edx, edx; pReserved
0x180021066  call    cs:__imp_WlanCloseHandle
0x18002106c  mov     rcx, [rsi+20h]; hEvent
0x180021070  call    cs:__imp_ResetEvent
0x180021076  mov     r10, cs:WPP_GLOBAL_Control
0x18002107d  cmp     r10, r13
0x180021080  jz      short loc_1800210B1
0x180021082  test    ebx, ebx
0x180021084  js      short loc_18002108D
0x180021086  cmp     byte ptr [r10+19h], 6
0x18002108b  jb      short loc_1800210B1
0x18002108d  or      ecx, 0FFFFFFFFh; int
0x180021090  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180021095  mov     rcx, [r10+10h]
0x180021099  lea     r8, WPP_2ea1fd34665a3647954ba5ee5f2f60a4_Traceguids
0x1800210a0  mov     edx, 2Bh ; '+'
0x1800210a5  mov     dword ptr [rsp+58h+pCallbackContext], ebx
0x1800210a9  mov     r9, rax
0x1800210ac  call    WPP_SF_sd
0x1800210b1  mov     rsi, [rsp+58h+arg_18]
0x1800210b6  mov     eax, ebx
0x1800210b8  mov     rbx, [rsp+58h+arg_0]
0x1800210bd  add     rsp, 40h
0x1800210c1  pop     r15
0x1800210c3  pop     r14
0x1800210c5  pop     r13
0x1800210c7  retn
```
