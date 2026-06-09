# CShareMediaCore::_OnNav(void)

- ea: `0x18000fbd0`
- end: `0x18000fd82`
- name: `?_OnNav@CShareMediaCore@@AEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f1cc`
- `0x18000fd88`

## callees

- `0x180001d60`
- `0x180003860`
- `0x180003888`
- `0x18000fbd0`
- `0x180012c58`
- `0x18001e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000fc7a`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000fc7a`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::_OnNav(CShareMediaCore *this, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  IUnknown *v5; // rcx
  __int64 v6; // rcx
  HRESULT v7; // ebx
  __int64 v8; // r8
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-30h] BYREF
  __int64 *v13; // [rsp+50h] [rbp-20h]
  __int64 v14; // [rsp+58h] [rbp-18h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    LODWORD(v10) = 0;
    v13 = &v10;
    v14 = 4;
    McGenEventWrite_EventWriteTransfer(
      (__int64)v4,
      (const EVENT_DESCRIPTOR *)ShareMediaCPL_NavigateAway_Start,
      a3,
      2u,
      &v12);
  }
  v5 = (IUnknown *)*((_QWORD *)this + 4);
  ppvOut = 0;
  v7 = IUnknown_QueryService(
         v5,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
         &ppvOut);
  if ( v7 >= 0 )
  {
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(void *, GUID *, GUID *, __int64 *))(*(_QWORD *)ppvOut + 24LL))(
           ppvOut,
           &IID_IWebBrowserApp,
           &GUID_0002df05_0000_0000_c000_000000000046,
           &v10);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 56LL))(v10);
      if ( v7 < 0 )
        v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 256LL))(v10);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    LODWORD(v10) = v7;
    v13 = &v10;
    v14 = 4;
    McGenEventWrite_EventWriteTransfer(v6, (const EVENT_DESCRIPTOR *)ShareMediaCPL_NavigateAway_Stop, v8, 2u, &v12);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fbd0  mov     [rsp-8+arg_8], rbx
0x18000fbd5  mov     [rsp-8+arg_10], rsi
0x18000fbda  push    rbp
0x18000fbdb  mov     rbp, rsp
0x18000fbde  sub     rsp, 70h
0x18000fbe2  mov     rax, cs:__security_cookie
0x18000fbe9  xor     rax, rsp
0x18000fbec  mov     [rbp+var_10], rax
0x18000fbf0  mov     rbx, rcx
0x18000fbf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbfa  lea     rsi, WPP_GLOBAL_Control
0x18000fc01  cmp     rcx, rsi
0x18000fc04  jz      short loc_18000FC21
0x18000fc06  test    byte ptr [rcx+1Ch], 20h
0x18000fc0a  jz      short loc_18000FC21
0x18000fc0c  mov     rcx, [rcx+10h]
0x18000fc10  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000fc17  mov     edx, 36h ; '6'
0x18000fc1c  call    WPP_SF_
0x18000fc21  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x18000fc28  jz      short loc_18000FC5C
0x18000fc2a  lea     rax, [rbp+var_40]
0x18000fc2e  mov     dword ptr [rbp+var_40], 0
0x18000fc35  mov     [rbp+var_20], rax
0x18000fc39  lea     rdx, ShareMediaCPL_NavigateAway_Start
0x18000fc40  lea     rax, [rbp+var_30]
0x18000fc44  mov     [rbp+var_18], 4
0x18000fc4c  mov     r9d, 2
0x18000fc52  mov     [rsp+70h+var_50], rax
0x18000fc57  call    McGenEventWrite_EventWriteTransfer
0x18000fc5c  mov     rcx, [rbx+20h]; punk
0x18000fc60  lea     r9, [rbp+ppvOut]; ppvOut
0x18000fc64  lea     r8, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18000fc6b  mov     [rbp+ppvOut], 0
0x18000fc73  lea     rdx, SID_STopLevelBrowser; guidService
0x18000fc7a  call    cs:__imp_IUnknown_QueryService
0x18000fc80  mov     ebx, eax
0x18000fc82  test    eax, eax
0x18000fc84  js      short loc_18000FD01
0x18000fc86  mov     rcx, [rbp+ppvOut]
0x18000fc8a  lea     r9, [rbp+var_40]
0x18000fc8e  mov     [rbp+var_40], 0
0x18000fc96  lea     r8, _GUID_0002df05_0000_0000_c000_000000000046
0x18000fc9d  lea     rdx, IID_IWebBrowserApp
0x18000fca4  mov     rax, [rcx]
0x18000fca7  mov     rax, [rax+18h]
0x18000fcab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcb0  mov     ebx, eax
0x18000fcb2  test    eax, eax
0x18000fcb4  js      short loc_18000FCF1
0x18000fcb6  mov     rcx, [rbp+var_40]
0x18000fcba  mov     rax, [rcx]
0x18000fcbd  mov     rax, [rax+38h]
0x18000fcc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcc6  mov     ebx, eax
0x18000fcc8  test    eax, eax
0x18000fcca  jns     short loc_18000FCE1
0x18000fccc  mov     rcx, [rbp+var_40]
0x18000fcd0  mov     rax, [rcx]
0x18000fcd3  mov     rax, [rax+100h]
0x18000fcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcdf  mov     ebx, eax
0x18000fce1  mov     rcx, [rbp+var_40]
0x18000fce5  mov     rax, [rcx]
0x18000fce8  mov     rax, [rax+10h]
0x18000fcec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcf1  mov     rcx, [rbp+ppvOut]
0x18000fcf5  mov     rax, [rcx]
0x18000fcf8  mov     rax, [rax+10h]
0x18000fcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd01  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x18000fd08  jz      short loc_18000FD38
0x18000fd0a  lea     rax, [rbp+var_40]
0x18000fd0e  mov     dword ptr [rbp+var_40], ebx
0x18000fd11  mov     [rbp+var_20], rax
0x18000fd15  lea     rdx, ShareMediaCPL_NavigateAway_Stop
0x18000fd1c  lea     rax, [rbp+var_30]
0x18000fd20  mov     [rbp+var_18], 4
0x18000fd28  mov     r9d, 2
0x18000fd2e  mov     [rsp+70h+var_50], rax
0x18000fd33  call    McGenEventWrite_EventWriteTransfer
0x18000fd38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd3f  cmp     rcx, rsi
0x18000fd42  jz      short loc_18000FD62
0x18000fd44  test    byte ptr [rcx+1Ch], 20h
0x18000fd48  jz      short loc_18000FD62
0x18000fd4a  mov     rcx, [rcx+10h]
0x18000fd4e  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000fd55  mov     edx, 37h ; '7'
0x18000fd5a  mov     r9d, ebx
0x18000fd5d  call    WPP_SF_d
0x18000fd62  mov     eax, ebx
0x18000fd64  mov     rcx, [rbp+var_10]
0x18000fd68  xor     rcx, rsp; StackCookie
0x18000fd6b  call    __security_check_cookie
0x18000fd70  lea     r11, [rsp+70h+var_s0]
0x18000fd75  mov     rbx, [r11+18h]
0x18000fd79  mov     rsi, [r11+20h]
0x18000fd7d  mov     rsp, r11
0x18000fd80  pop     rbp
0x18000fd81  retn
```
