# WLGeneric_StartSecureLua_Execute(_StateMachineCallContext *)

- ea: `0x140003b60`
- end: `0x140003e96`
- name: `?WLGeneric_StartSecureLua_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `822`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140003b60`
- `0x140004f20`
- `0x1400057f4`
- `0x140005840`
- `0x140016850`
- `0x140016a30`
- `0x140016f60`
- `0x140041c34`
- `0x14004e714`
- `0x14005fb84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003d9e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003bd0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140003bbe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140003bbe`
- `RPCRT4!RpcAsyncAbortCall` at `0x140003c0d`
- `RPCRT4!RpcAsyncAbortCall` at `0x140003c0d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140003d3e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140003d3e`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x140003cc2`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x140003cc2`
- `ext-ms-win-ntuser-window-l1-1-0!EnumWindows` at `0x140003c70`
- `ext-ms-win-ntuser-window-l1-1-0!EnumWindows` at `0x140003c70`
- `ext-ms-win-ntuser-window-l1-1-0!FindWindowW` at `0x140003c7f`
- `ext-ms-win-ntuser-window-l1-1-0!FindWindowW` at `0x140003c7f`

## pseudocode

```c
__int64 __fastcall WLGeneric_StartSecureLua_Execute(
        struct _StateMachineCallContext *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r14
  DWORD v6; // esi
  struct _RPC_ASYNC_STATE *v7; // rdi
  HANDLE v8; // rax
  void *v9; // rsi
  DWORD LastError; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // r9
  HWND WindowW; // r15
  unsigned int v15; // eax
  unsigned int v16; // eax
  DWORD v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdi
  CUser *v20; // rcx
  __int64 result; // rax
  __int128 v22; // [rsp+30h] [rbp-58h] BYREF
  __int64 v23; // [rsp+40h] [rbp-48h]
  int v24; // [rsp+90h] [rbp+8h] BYREF

  v5 = *((_QWORD *)a1 + 1);
  v6 = *((_DWORD *)a1 + 12);
  v7 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a1 + 5);
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, a4);
  }
  v8 = OpenProcess(0x100011u, 0, v6);
  v9 = v8;
  if ( v8 )
  {
    WlStateMachine_Execute_SetContext(a1, v8);
    EnumWindows(ShowLogonUIWindowEnumWindowsCallbackProc, 0);
    WindowW = FindWindowW(0, L"$$$Secure UAP Background Window");
    if ( WindowW )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, v13);
      }
      ShowWindow(WindowW, 5);
    }
    v24 = 0;
    CSession::SwitchDesktop(*(_QWORD *)(v5 + 16), 0, &v24, 0, 0);
    if ( v24 )
    {
      v15 = WlAccessibilityOnDesktopSwitch((struct _WLSM_GLOBAL_CONTEXT *)v5, 1);
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v15);
        }
      }
    }
    v16 = RpcAsyncCompleteCall(v7, 0);
    if ( v16
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, v16);
    }
    v22 = 0;
    v23 = 0;
    ToSetTimeout(120000, &v22);
    while ( 1 )
    {
      v17 = WaitForSingleObject(v9, 0x7D0u);
      if ( !v17 )
        break;
      if ( v17 != 258 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, v17);
        }
        break;
      }
      v19 = *((_QWORD *)a1 + 2);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_ec24bf9d3a3f3b3e5391626512dbd62f_Traceguids,
          *((_QWORD *)a1 + 2));
        v20 = WPP_GLOBAL_Control;
      }
      if ( !v19 )
      {
        if ( v20 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
          WPP_SF_(*((_QWORD *)v20 + 2), 43, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, v18);
        break;
      }
    }
    ToResetTimeout();
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, LastError);
    }
    v12 = RpcAsyncAbortCall(v7, v11);
    if ( v12
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, v12);
    }
  }
  result = 13;
  if ( qword_1400D30C8 )
    return SignalManagerSetSignal(*(PRTL_CRITICAL_SECTION *)qword_1400D30C8);
  return result;
}

```

## disassembly

```asm
0x140003b60  push    rbx
0x140003b62  push    rsi
0x140003b63  push    rdi
0x140003b64  push    r12
0x140003b66  push    r14
0x140003b68  push    r15
0x140003b6a  sub     rsp, 58h
0x140003b6e  mov     rbx, rcx
0x140003b71  mov     r14, [rcx+8]
0x140003b75  mov     esi, [rcx+30h]
0x140003b78  mov     rdi, [rcx+28h]
0x140003b7c  lea     r12, WPP_GLOBAL_Control
0x140003b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b8a  cmp     rcx, r12
0x140003b8d  jz      short loc_140003BB4
0x140003b8f  test    dword ptr [rcx+1Ch], 100h
0x140003b96  jz      short loc_140003BB4
0x140003b98  cmp     byte ptr [rcx+19h], 4
0x140003b9c  jb      short loc_140003BB4
0x140003b9e  mov     edx, 26h ; '&'
0x140003ba3  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x140003baa  mov     rcx, [rcx+10h]
0x140003bae  call    WPP_SF_
0x140003bb3  nop
0x140003bb4  mov     r8d, esi; dwProcessId
0x140003bb7  xor     edx, edx; bInheritHandle
0x140003bb9  mov     ecx, 100011h; dwDesiredAccess
0x140003bbe  call    cs:__imp_OpenProcess
0x140003bc4  mov     rsi, rax
0x140003bc7  test    rax, rax
0x140003bca  jnz     loc_140003C5C
0x140003bd0  call    cs:__imp_GetLastError
0x140003bd6  mov     ebx, eax
0x140003bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bdf  cmp     rcx, r12
0x140003be2  jz      short loc_140003C08
0x140003be4  test    byte ptr [rcx+1Ch], 1
0x140003be8  jz      short loc_140003C08
0x140003bea  cmp     byte ptr [rcx+19h], 2
0x140003bee  jb      short loc_140003C08
0x140003bf0  mov     edx, 27h ; '''
0x140003bf5  mov     r9d, eax
0x140003bf8  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x140003bff  mov     rcx, [rcx+10h]
0x140003c03  call    WPP_SF_d
0x140003c08  mov     edx, ebx; ExceptionCode
0x140003c0a  mov     rcx, rdi; pAsync
0x140003c0d  call    cs:__imp_RpcAsyncAbortCall
0x140003c13  test    eax, eax
0x140003c15  jz      loc_140003E56
0x140003c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c22  cmp     rcx, r12
0x140003c25  jz      loc_140003E56
0x140003c2b  test    byte ptr [rcx+1Ch], 1
0x140003c2f  jz      loc_140003E56
0x140003c35  cmp     byte ptr [rcx+19h], 2
0x140003c39  jb      loc_140003E56
0x140003c3f  mov     edx, 28h ; '('
0x140003c44  mov     r9d, eax
0x140003c47  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x140003c4e  mov     rcx, [rcx+10h]
0x140003c52  call    WPP_SF_d
0x140003c57  jmp     loc_140003E56
0x140003c5c  mov     rdx, rsi; void *
0x140003c5f  mov     rcx, rbx; struct _StateMachineCallContext *
0x140003c62  call    ?WlStateMachine_Execute_SetContext@@YAXPEAU_StateMachineCallContext@@PEAX@Z; WlStateMachine_Execute_SetContext(_StateMachineCallContext *,void *)
0x140003c67  xor     edx, edx; lParam
0x140003c69  lea     rcx, ?ShowLogonUIWindowEnumWindowsCallbackProc@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x140003c70  call    cs:__imp_EnumWindows
0x140003c76  lea     rdx, WindowName; "$$$Secure UAP Background Window"
0x140003c7d  xor     ecx, ecx; lpClassName
0x140003c7f  call    cs:__imp_FindWindowW
0x140003c85  mov     r15, rax
0x140003c88  test    rax, rax
0x140003c8b  jz      short loc_140003CC8
0x140003c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c94  cmp     rcx, r12
0x140003c97  jz      short loc_140003CBA
0x140003c99  test    byte ptr [rcx+1Ch], 1
0x140003c9d  jz      short loc_140003CBA
0x140003c9f  cmp     byte ptr [rcx+19h], 4
0x140003ca3  jb      short loc_140003CBA
0x140003ca5  mov     edx, 29h ; ')'
0x140003caa  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x140003cb1  mov     rcx, [rcx+10h]
0x140003cb5  call    WPP_SF_
0x140003cba  mov     edx, 5; nCmdShow
0x140003cbf  mov     rcx, r15; hWnd
0x140003cc2  call    cs:__imp_ShowWindow
0x140003cc8  xor     eax, eax
0x140003cca  mov     [rsp+88h+arg_0], eax
0x140003cd1  mov     [rsp+88h+var_68], eax
0x140003cd5  xor     r9d, r9d
0x140003cd8  lea     r8, [rsp+88h+arg_0]
0x140003ce0  xor     edx, edx
0x140003ce2  mov     rcx, [r14+10h]
0x140003ce6  call    ?SwitchDesktop@CSession@@QEAAXW4_DESKTOPID@@PEAHKK@Z; CSession::SwitchDesktop(_DESKTOPID,int *,ulong,ulong)
0x140003ceb  cmp     [rsp+88h+arg_0], 0
0x140003cf3  jz      short loc_140003D39
0x140003cf5  mov     edx, 1; int
0x140003cfa  mov     rcx, r14; struct _WLSM_GLOBAL_CONTEXT *
0x140003cfd  call    ?WlAccessibilityOnDesktopSwitch@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z; WlAccessibilityOnDesktopSwitch(_WLSM_GLOBAL_CONTEXT *,int)
0x140003d02  test    eax, eax
0x140003d04  jz      short loc_140003D39
0x140003d06  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d0d  cmp     rcx, r12
0x140003d10  jz      short loc_140003D39
0x140003d12  test    dword ptr [rcx+1Ch], 40000h
0x140003d19  jz      short loc_140003D39
0x140003d1b  cmp     byte ptr [rcx+19h], 2
0x140003d1f  jb      short loc_140003D39
0x140003d21  mov     edx, 6Ch ; 'l'
0x140003d26  mov     r9d, eax
0x140003d29  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140003d30  mov     rcx, [rcx+10h]
0x140003d34  call    WPP_SF_d
0x140003d39  xor     edx, edx; Reply
0x140003d3b  mov     rcx, rdi; pAsync
0x140003d3e  call    cs:__imp_RpcAsyncCompleteCall
0x140003d44  test    eax, eax
0x140003d46  jz      short loc_140003D78
0x140003d48  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d4f  cmp     rcx, r12
0x140003d52  jz      short loc_140003D78
0x140003d54  test    byte ptr [rcx+1Ch], 1
0x140003d58  jz      short loc_140003D78
0x140003d5a  cmp     byte ptr [rcx+19h], 2
0x140003d5e  jb      short loc_140003D78
0x140003d60  mov     edx, 2Ah ; '*'
0x140003d65  mov     r9d, eax
0x140003d68  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x140003d6f  mov     rcx, [rcx+10h]
0x140003d73  call    WPP_SF_d
0x140003d78  xorps   xmm0, xmm0
0x140003d7b  xor     eax, eax
0x140003d7d  movaps  [rsp+88h+var_58], xmm0
0x140003d82  mov     [rsp+88h+var_48], rax
0x140003d87  lea     rdx, [rsp+88h+var_58]
0x140003d8c  mov     ecx, 1D4C0h
0x140003d91  call    ?ToSetTimeout@@YAKKU_StateMachineSignalData@@@Z; ToSetTimeout(ulong,_StateMachineSignalData)
0x140003d96  mov     edx, 7D0h; dwMilliseconds
0x140003d9b  mov     rcx, rsi; hHandle
0x140003d9e  call    cs:__imp_WaitForSingleObject
0x140003da4  test    eax, eax
0x140003da6  jz      loc_140003E50
0x140003dac  cmp     eax, 102h
0x140003db1  jnz     short loc_140003E20
0x140003db3  mov     rdi, [rbx+10h]
0x140003db7  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dbe  cmp     rcx, r12
0x140003dc1  jz      short loc_140003DEE
0x140003dc3  test    byte ptr [rcx+1Ch], 1
0x140003dc7  jz      short loc_140003DEE
0x140003dc9  cmp     byte ptr [rcx+19h], 5
0x140003dcd  jb      short loc_140003DEE
0x140003dcf  mov     edx, 0Bh
0x140003dd4  mov     r9, rdi
0x140003dd7  lea     r8, WPP_ec24bf9d3a3f3b3e5391626512dbd62f_Traceguids
0x140003dde  mov     rcx, [rcx+10h]
0x140003de2  call    WPP_SF_q
0x140003de7  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dee  test    rdi, rdi
0x140003df1  jnz     short loc_140003E1B
0x140003df3  cmp     rcx, r12
0x140003df6  jz      short loc_140003E50
0x140003df8  test    byte ptr [rcx+1Ch], 1
0x140003dfc  jz      short loc_140003E50
0x140003dfe  cmp     byte ptr [rcx+19h], 4
0x140003e02  jb      short loc_140003E50
0x140003e04  mov     edx, 2Bh ; '+'
0x140003e09  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x140003e10  mov     rcx, [rcx+10h]
0x140003e14  call    WPP_SF_
0x140003e19  jmp     short loc_140003E50
0x140003e1b  jmp     loc_140003D96
0x140003e20  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e27  cmp     rcx, r12
0x140003e2a  jz      short loc_140003E50
0x140003e2c  test    byte ptr [rcx+1Ch], 1
0x140003e30  jz      short loc_140003E50
0x140003e32  cmp     byte ptr [rcx+19h], 2
0x140003e36  jb      short loc_140003E50
0x140003e38  mov     edx, 2Ch ; ','
0x140003e3d  mov     r9d, eax
0x140003e40  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x140003e47  mov     rcx, [rcx+10h]
0x140003e4b  call    WPP_SF_d
0x140003e50  call    ?ToResetTimeout@@YAKXZ; ToResetTimeout(void)
0x140003e55  nop
0x140003e56  mov     eax, 0Dh
0x140003e5b  mov     rcx, cs:qword_1400D30C8
0x140003e62  test    rcx, rcx
0x140003e65  jz      short loc_140003E88
0x140003e67  mov     r8, [rcx+20h]
0x140003e6b  xor     r9d, r9d
0x140003e6e  mov     r8, [r8]
0x140003e71  xor     edx, edx
0x140003e73  mov     rcx, [rcx]; CriticalSection
0x140003e76  add     rsp, 58h
0x140003e7a  pop     r15
0x140003e7c  pop     r14
0x140003e7e  pop     r12
0x140003e80  pop     rdi
0x140003e81  pop     rsi
0x140003e82  pop     rbx
0x140003e83  jmp     SignalManagerSetSignal
0x140003e88  add     rsp, 58h
0x140003e8c  pop     r15
0x140003e8e  pop     r14
0x140003e90  pop     r12
0x140003e92  pop     rdi
0x140003e93  pop     rsi
0x140003e94  pop     rbx
0x140003e95  retn
0x14009cce0  push    rbp
0x14009cce2  sub     rsp, 30h
0x14009cce6  mov     rbp, rdx
0x14009cce9  add     rsp, 30h
0x14009cced  pop     rbp
0x14009ccee  retn
```
