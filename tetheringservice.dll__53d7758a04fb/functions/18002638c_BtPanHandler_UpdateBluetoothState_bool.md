# BtPanHandler::UpdateBluetoothState(bool)

- ea: `0x18002638c`
- end: `0x180026504`
- name: `?UpdateBluetoothState@BtPanHandler@@AEAAJ_N@Z`
- size: `376`
- prototype: `__int64 __fastcall(BtPanHandler *__hidden this, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180025c88`

## callees

- `0x180005e98`
- `0x18000a21c`
- `0x18000bf4c`
- `0x18000bf74`
- `0x180024a40`
- `0x180024b04`
- `0x18002638c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002646c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002646c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026445`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002647f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002647f`

## pseudocode

```c
__int64 __fastcall BtPanHandler::UpdateBluetoothState(BtPanHandler *this, char a2)
{
  TetheringServiceTelemetry *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  const char *v8; // r9
  unsigned int v9; // ebx
  DWORD v10; // eax
  __int64 v11; // r8
  const char *v12; // r9
  signed int LastError; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v16; // [rsp+30h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( this == (BtPanHandler *)-48LL )
  {
    if ( v4 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 1) == 0 )
      goto LABEL_14;
    v5 = (unsigned int)((_DWORD)this + 59);
    goto LABEL_8;
  }
  v6 = *((_QWORD *)this + 6);
  v16 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 72LL))(v6, &v16) < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_14;
    }
    v5 = 12;
LABEL_8:
    WPP_SF_(*((_QWORD *)v4 + 2), v5, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids);
    goto LABEL_14;
  }
  if ( v16 == 1 )
  {
    v9 = BtPanHandler::BtInitializeHelper(this);
    goto LABEL_24;
  }
LABEL_14:
  if ( !a2 )
    return 0;
  if ( !ResetEvent(*(HANDLE *)this) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v7, v8);
  v9 = BtPanHandler::BtTurnOnRadio(this);
  if ( (v9 & 0x80000000) != 0 )
    goto LABEL_25;
  v10 = WaitForSingleObjectEx(*(HANDLE *)this, 0x1D4C0u, 0);
  if ( v10 != 258 )
  {
    if ( v10 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v11, v12);
    return v9;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_24:
  if ( (v9 & 0x80000000) == 0 )
    return v9;
LABEL_25:
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18002638c  mov     [rsp+arg_8], rbx
0x180026391  mov     [rsp+arg_10], rsi
0x180026396  push    rdi
0x180026397  sub     rsp, 20h
0x18002639b  mov     bl, dl
0x18002639d  mov     rdi, rcx
0x1800263a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263a7  lea     rsi, WPP_GLOBAL_Control
0x1800263ae  cmp     rcx, rsi
0x1800263b1  jz      short loc_1800263D5
0x1800263b3  test    byte ptr [rcx+1Ch], 4
0x1800263b7  jz      short loc_1800263D5
0x1800263b9  mov     rcx, [rcx+10h]
0x1800263bd  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x1800263c4  mov     edx, 0Ah
0x1800263c9  call    WPP_SF_
0x1800263ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263d5  lea     rax, [rdi+30h]
0x1800263d9  test    rax, rax
0x1800263dc  jnz     short loc_1800263FE
0x1800263de  cmp     rcx, rsi
0x1800263e1  jz      short loc_18002643E
0x1800263e3  test    byte ptr [rcx+1Ch], 1
0x1800263e7  jz      short loc_18002643E
0x1800263e9  lea     edx, [rax+0Bh]
0x1800263ec  mov     rcx, [rcx+10h]
0x1800263f0  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x1800263f7  call    WPP_SF_
0x1800263fc  jmp     short loc_18002643E
0x1800263fe  mov     rcx, [rax]
0x180026401  lea     rdx, [rsp+28h+arg_0]
0x180026406  mov     [rsp+28h+arg_0], 0
0x18002640e  mov     rax, [rcx]
0x180026411  mov     rax, [rax+48h]
0x180026415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002641a  test    eax, eax
0x18002641c  jns     short loc_180026437
0x18002641e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026425  cmp     rcx, rsi
0x180026428  jz      short loc_18002643E
0x18002642a  test    byte ptr [rcx+1Ch], 1
0x18002642e  jz      short loc_18002643E
0x180026430  mov     edx, 0Ch
0x180026435  jmp     short loc_1800263EC
0x180026437  cmp     [rsp+28h+arg_0], 1
0x18002643c  jz      short loc_18002649A
0x18002643e  test    bl, bl
0x180026440  jz      short loc_180026496
0x180026442  mov     rcx, [rdi]; hEvent
0x180026445  call    cs:__imp_ResetEvent
0x18002644b  test    eax, eax
0x18002644d  jz      loc_1800264E4
0x180026453  mov     rcx, rdi; this
0x180026456  call    ?BtTurnOnRadio@BtPanHandler@@AEAAJXZ; BtPanHandler::BtTurnOnRadio(void)
0x18002645b  mov     ebx, eax
0x18002645d  test    eax, eax
0x18002645f  js      short loc_1800264A8
0x180026461  mov     rcx, [rdi]; hHandle
0x180026464  xor     r8d, r8d; bAlertable
0x180026467  mov     edx, 1D4C0h; dwMilliseconds
0x18002646c  call    cs:__imp_WaitForSingleObjectEx
0x180026472  cmp     eax, 102h
0x180026477  jz      short loc_18002647F
0x180026479  test    eax, eax
0x18002647b  jnz     short loc_1800264F4
0x18002647d  jmp     short loc_1800264D2
0x18002647f  call    cs:__imp_GetLastError
0x180026485  mov     ebx, eax
0x180026487  test    eax, eax
0x180026489  jle     short loc_1800264A4
0x18002648b  movzx   ebx, ax
0x18002648e  or      ebx, 80070000h
0x180026494  jmp     short loc_1800264A4
0x180026496  xor     ebx, ebx
0x180026498  jmp     short loc_1800264D2
0x18002649a  mov     rcx, rdi; this
0x18002649d  call    ?BtInitializeHelper@BtPanHandler@@AEAAJXZ; BtPanHandler::BtInitializeHelper(void)
0x1800264a2  mov     ebx, eax
0x1800264a4  test    ebx, ebx
0x1800264a6  jns     short loc_1800264D2
0x1800264a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264af  cmp     rcx, rsi
0x1800264b2  jz      short loc_1800264D2
0x1800264b4  test    byte ptr [rcx+1Ch], 1
0x1800264b8  jz      short loc_1800264D2
0x1800264ba  mov     rcx, [rcx+10h]
0x1800264be  lea     r8, WPP_0b53a71487193501cbc3cdc44df626ed_Traceguids
0x1800264c5  mov     edx, 1Ch
0x1800264ca  mov     r9d, ebx
0x1800264cd  call    WPP_SF_d
0x1800264d2  mov     rsi, [rsp+28h+arg_10]
0x1800264d7  mov     eax, ebx
0x1800264d9  mov     rbx, [rsp+28h+arg_8]
0x1800264de  add     rsp, 20h
0x1800264e2  pop     rdi
0x1800264e3  retn
0x1800264e4  mov     rcx, [rsp+28h]; this
0x1800264e9  mov     edx, 0A06h; void *
0x1800264ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800264f4  mov     rcx, [rsp+28h]; this
0x1800264f9  mov     edx, 0B0Fh; void *
0x1800264fe  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
