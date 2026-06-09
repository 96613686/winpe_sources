# InitService(void)

- ea: `0x1800030b8`
- end: `0x18000343a`
- name: `?InitService@@YAJXZ`
- size: `898`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800034c0`

## callees

- `0x180001e04`
- `0x1800022c0`
- `0x18000248c`
- `0x180002620`
- `0x1800026e0`
- `0x1800030b8`
- `0x180003440`
- `0x1800038f8`
- `0x180003960`
- `0x180003be0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000340b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000340b`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180003153`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180003153`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800033cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800033cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003315`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800031cf`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800031cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003300`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003300`

## pseudocode

```c
__int64 InitService(void)
{
  int v0; // esi
  ULONG64 *v1; // rbx
  const GUID **v2; // rdi
  const GUID *v3; // r8
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // ebp
  signed int LastError; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  bool v10; // sf
  int inited; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // eax
  unsigned int v15; // eax
  int v16; // edi
  int v18; // [rsp+40h] [rbp-68h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+48h] [rbp-60h] BYREF
  int *v20; // [rsp+58h] [rbp-50h]
  __int64 v21; // [rsp+60h] [rbp-48h]

  v0 = 0;
  qword_1800086E0 = 0;
  qword_1800086E8 = 1;
  v1 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WepHostDebugTraceControlGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v2 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  do
  {
    v3 = *v2;
    TraceGuidReg.Guid = v3;
    ++v2;
    TraceGuidReg.RegHandle = 0;
    v1[4] = (ULONG64)v3;
    RegisterTraceGuidsW(WppControlCallback, v1, v3, 1u, &TraceGuidReg, 0, 0, v1 + 1);
    v1 = (ULONG64 *)*v1;
  }
  while ( v1 );
  McGenEventRegister_EventRegister();
  if ( (Microsoft_Windows_WEPHOSTSVCEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v4, ServiceStart, v5, 1, &TraceGuidReg);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids);
  qword_180008778 = (__int64)RegisterServiceCtrlHandlerExW(L"WEPHOSTSVC", WepHostServiceCtrlHandler, 0);
  if ( !qword_180008778 )
  {
    v6 = 0;
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v9 = 17;
    goto LABEL_12;
  }
  dword_180008758 = 16;
  dword_180008760 = 0;
  ReportSvcStatus(2, 0, 3000);
  inited = WepHostInitFuncTable();
  LastError = inited;
  if ( inited < 0 )
  {
    if ( (Microsoft_Windows_WEPHOSTSVCEnableBits & 1) != 0 )
    {
      v18 = inited;
      v21 = 4;
      v20 = &v18;
      McGenEventWrite_EventWriteTransfer(v12, DllLoadFailure, v13, 2, &TraceGuidReg);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids,
        (unsigned int)LastError);
    goto LABEL_45;
  }
  v14 = WepHostInitRPCServer();
  LastError = v14;
  if ( v14 >= 0 )
  {
    v6 = 1;
    v0 = 1;
    hObject = CreateEventW(0, 1, 0, 0);
    if ( hObject )
    {
      v15 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))(svcData + 192LL))(
              &qword_180008788,
              L"WEPHOSTSVC",
              hObject,
              WepHostStopCallback,
              0,
              24);
      v16 = v15;
      if ( !v15 )
        return (unsigned int)LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids, v15);
      if ( v16 <= 0 )
      {
        LastError = v16;
LABEL_37:
        v10 = LastError < 0;
LABEL_38:
        if ( !v10 )
          return (unsigned int)LastError;
        if ( !v6 )
          goto LABEL_43;
        goto LABEL_40;
      }
      LastError = (unsigned __int16)v16;
LABEL_36:
      LastError |= 0x80070000;
      goto LABEL_37;
    }
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_13:
      v10 = LastError < 0;
      if ( LastError <= 0 )
        goto LABEL_38;
      LastError = (unsigned __int16)LastError;
      goto LABEL_36;
    }
    v9 = 20;
LABEL_12:
    WPP_SF_D(v8[2], v9, &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids, (unsigned int)LastError);
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids,
      (unsigned int)v14);
LABEL_40:
  if ( g_hInstance )
    FreeLibrary(g_hInstance);
  g_Table = 0;
  qword_180008738 = 0;
  xmmword_180008718 = 0;
  xmmword_180008728 = 0;
LABEL_43:
  if ( v0 )
    WepHostTearDownRPCServer();
LABEL_45:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800030b8  push    rbx
0x1800030ba  push    rbp
0x1800030bb  push    rsi
0x1800030bc  push    rdi
0x1800030bd  push    r12
0x1800030bf  push    r13
0x1800030c1  push    r15
0x1800030c3  sub     rsp, 70h
0x1800030c7  mov     rax, cs:__security_cookie
0x1800030ce  xor     rax, rsp
0x1800030d1  mov     [rsp+0A8h+var_40], rax
0x1800030d6  xor     esi, esi
0x1800030d8  lea     r15d, [rsi+1]
0x1800030dc  mov     cs:qword_1800086E0, rsi
0x1800030e3  lea     rax, WPP_ThisDir_CTLGUID_WepHostDebugTraceControlGuid
0x1800030ea  mov     cs:qword_1800086E8, r15
0x1800030f1  lea     rbx, WPP_MAIN_CB
0x1800030f8  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1800030ff  mov     cs:WPP_GLOBAL_Control, rbx
0x180003106  lea     rdi, WPP_REGISTRATION_GUIDS
0x18000310d  mov     cs:WPP_MAIN_CB, rsi
0x180003114  mov     r8, [rdi]; ControlGuid
0x180003117  lea     rax, [rbx+8]
0x18000311b  mov     [rsp+0A8h+RegistrationHandle], rax; RegistrationHandle
0x180003120  lea     rcx, WppControlCallback; RequestAddress
0x180003127  mov     [rsp+0A8h+MofResourceName], rsi; MofResourceName
0x18000312c  lea     rax, [rsp+0A8h+var_60]
0x180003131  mov     [rsp+0A8h+var_60.Guid], r8
0x180003136  lea     rdi, [rdi+8]
0x18000313a  mov     [rsp+0A8h+var_60.RegHandle], rsi
0x18000313f  mov     r9d, r15d; GuidCount
0x180003142  mov     [rsp+0A8h+MofImagePath], rsi; MofImagePath
0x180003147  mov     rdx, rbx; RequestContext
0x18000314a  mov     [rsp+0A8h+TraceGuidReg], rax; TraceGuidReg
0x18000314f  mov     [rbx+20h], r8
0x180003153  call    cs:__imp_RegisterTraceGuidsW
0x180003159  mov     rbx, [rbx]
0x18000315c  test    rbx, rbx
0x18000315f  jnz     short loc_180003114
0x180003161  call    McGenEventRegister_EventRegister
0x180003166  lea     edi, [rbx+2]
0x180003169  test    cs:Microsoft_Windows_WEPHOSTSVCEnableBits, dil
0x180003170  jz      short loc_18000318B
0x180003172  lea     rax, [rsp+0A8h+var_60]
0x180003177  mov     r9d, r15d
0x18000317a  lea     rdx, ServiceStart
0x180003181  mov     [rsp+0A8h+TraceGuidReg], rax
0x180003186  call    McGenEventWrite_EventWriteTransfer
0x18000318b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003192  lea     r12, WPP_GLOBAL_Control
0x180003199  lea     r13, WPP_3a1233b099da3452b07b65d2eb146164_Traceguids
0x1800031a0  mov     ebx, 10h
0x1800031a5  cmp     rcx, r12
0x1800031a8  jz      short loc_1800031BE
0x1800031aa  test    byte ptr [rcx+1Ch], 20h
0x1800031ae  jz      short loc_1800031BE
0x1800031b0  mov     rcx, [rcx+10h]
0x1800031b4  mov     edx, ebx
0x1800031b6  mov     r8, r13
0x1800031b9  call    WPP_SF_
0x1800031be  xor     r8d, r8d; lpContext
0x1800031c1  lea     rdx, ?WepHostServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1800031c8  lea     rcx, ServiceName; "WEPHOSTSVC"
0x1800031cf  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800031d5  mov     cs:qword_180008778, rax
0x1800031dc  test    rax, rax
0x1800031df  jnz     short loc_18000321F
0x1800031e1  xor     ebp, ebp
0x1800031e3  call    cs:__imp_GetLastError
0x1800031e9  mov     ebx, eax
0x1800031eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031f2  cmp     rcx, r12
0x1800031f5  jz      short loc_18000320F
0x1800031f7  test    [rcx+1Ch], r15b
0x1800031fb  jz      short loc_18000320F
0x1800031fd  lea     edx, [rbp+11h]
0x180003200  mov     rcx, [rcx+10h]
0x180003204  mov     r9d, ebx
0x180003207  mov     r8, r13
0x18000320a  call    WPP_SF_D
0x18000320f  test    ebx, ebx
0x180003211  jle     loc_1800033BD
0x180003217  movzx   ebx, bx
0x18000321a  jmp     loc_1800033B5
0x18000321f  xor     edx, edx
0x180003221  mov     cs:dword_180008758, ebx
0x180003227  mov     r8d, 0BB8h
0x18000322d  mov     cs:dword_180008760, esi
0x180003233  mov     ecx, edi
0x180003235  call    ReportSvcStatus
0x18000323a  call    ?WepHostInitFuncTable@@YAJXZ; WepHostInitFuncTable(void)
0x18000323f  mov     ebx, eax
0x180003241  test    eax, eax
0x180003243  jns     short loc_1800032B1
0x180003245  test    cs:Microsoft_Windows_WEPHOSTSVCEnableBits, r15b
0x18000324c  jz      short loc_18000327E
0x18000324e  mov     [rsp+0A8h+var_68], eax
0x180003252  lea     rdx, DllLoadFailure
0x180003259  lea     rax, [rsp+0A8h+var_68]
0x18000325e  mov     [rsp+0A8h+var_48], 4
0x180003267  mov     [rsp+0A8h+var_50], rax
0x18000326c  mov     r9d, edi
0x18000326f  lea     rax, [rsp+0A8h+var_60]
0x180003274  mov     [rsp+0A8h+TraceGuidReg], rax
0x180003279  call    McGenEventWrite_EventWriteTransfer
0x18000327e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003285  cmp     rcx, r12
0x180003288  jz      loc_1800033FF
0x18000328e  test    [rcx+1Ch], r15b
0x180003292  jz      loc_1800033FF
0x180003298  mov     rcx, [rcx+10h]
0x18000329c  mov     edx, 12h
0x1800032a1  mov     r9d, ebx
0x1800032a4  mov     r8, r13
0x1800032a7  call    WPP_SF_D
0x1800032ac  jmp     loc_1800033FF
0x1800032b1  call    ?WepHostInitRPCServer@@YAJXZ; WepHostInitRPCServer(void)
0x1800032b6  mov     ebx, eax
0x1800032b8  test    eax, eax
0x1800032ba  jns     short loc_1800032EF
0x1800032bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032c3  cmp     rcx, r12
0x1800032c6  jz      loc_1800033C3
0x1800032cc  test    [rcx+1Ch], r15b
0x1800032d0  jz      loc_1800033C3
0x1800032d6  mov     rcx, [rcx+10h]
0x1800032da  mov     edx, 13h
0x1800032df  mov     r9d, eax
0x1800032e2  mov     r8, r13
0x1800032e5  call    WPP_SF_D
0x1800032ea  jmp     loc_1800033C3
0x1800032ef  xor     r9d, r9d; lpName
0x1800032f2  xor     r8d, r8d; bInitialState
0x1800032f5  mov     edx, r15d; bManualReset
0x1800032f8  xor     ecx, ecx; lpEventAttributes
0x1800032fa  mov     ebp, r15d
0x1800032fd  mov     esi, r15d
0x180003300  call    cs:__imp_CreateEventW
0x180003306  mov     cs:hObject, rax
0x18000330d  mov     r8, rax
0x180003310  test    rax, rax
0x180003313  jnz     short loc_180003341
0x180003315  call    cs:__imp_GetLastError
0x18000331b  mov     ebx, eax
0x18000331d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003324  cmp     rcx, r12
0x180003327  jz      loc_18000320F
0x18000332d  test    [rcx+1Ch], r15b
0x180003331  jz      loc_18000320F
0x180003337  mov     edx, 14h
0x18000333c  jmp     loc_180003200
0x180003341  mov     rax, cs:?svcData@@3U_WEPHOST_SERVICE_DATA@@A; _WEPHOST_SERVICE_DATA svcData
0x180003348  lea     r9, ?WepHostStopCallback@@YAXPEAXE@Z; WepHostStopCallback(void *,uchar)
0x18000334f  mov     dword ptr [rsp+0A8h+MofImagePath], 18h
0x180003357  lea     rdx, ServiceName; "WEPHOSTSVC"
0x18000335e  lea     rcx, qword_180008788
0x180003365  mov     [rsp+0A8h+TraceGuidReg], 0
0x18000336e  mov     rax, [rax+0C0h]
0x180003375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000337a  mov     edi, eax
0x18000337c  test    eax, eax
0x18000337e  jz      loc_18000341C
0x180003384  mov     rcx, cs:WPP_GLOBAL_Control
0x18000338b  cmp     rcx, r12
0x18000338e  jz      short loc_1800033AA
0x180003390  test    [rcx+1Ch], r15b
0x180003394  jz      short loc_1800033AA
0x180003396  mov     rcx, [rcx+10h]
0x18000339a  mov     edx, 15h
0x18000339f  mov     r9d, eax
0x1800033a2  mov     r8, r13
0x1800033a5  call    WPP_SF_D
0x1800033aa  test    edi, edi
0x1800033ac  jg      short loc_1800033B2
0x1800033ae  mov     ebx, edi
0x1800033b0  jmp     short loc_1800033BB
0x1800033b2  movzx   ebx, di
0x1800033b5  or      ebx, 80070000h
0x1800033bb  test    ebx, ebx
0x1800033bd  jns     short loc_18000341C
0x1800033bf  test    ebp, ebp
0x1800033c1  jz      short loc_1800033F6
0x1800033c3  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800033ca  test    rcx, rcx
0x1800033cd  jz      short loc_1800033D5
0x1800033cf  call    cs:__imp_FreeLibrary
0x1800033d5  xorps   xmm0, xmm0
0x1800033d8  xor     eax, eax
0x1800033da  movups  cs:?g_Table@@3U_tagPluginAPITable@@A, xmm0; _tagPluginAPITable g_Table
0x1800033e1  mov     cs:qword_180008738, rax
0x1800033e8  movups  cs:xmmword_180008718, xmm0
0x1800033ef  movups  cs:xmmword_180008728, xmm0
0x1800033f6  test    esi, esi
0x1800033f8  jz      short loc_1800033FF
0x1800033fa  call    ?WepHostTearDownRPCServer@@YAXXZ; WepHostTearDownRPCServer(void)
0x1800033ff  mov     rcx, cs:hObject; hObject
0x180003406  test    rcx, rcx
0x180003409  jz      short loc_18000341C
0x18000340b  call    cs:__imp_CloseHandle
0x180003411  mov     cs:hObject, 0
0x18000341c  mov     eax, ebx
0x18000341e  mov     rcx, [rsp+0A8h+var_40]
0x180003423  xor     rcx, rsp; StackCookie
0x180003426  call    __security_check_cookie
0x18000342b  add     rsp, 70h
0x18000342f  pop     r15
0x180003431  pop     r13
0x180003433  pop     r12
0x180003435  pop     rdi
0x180003436  pop     rsi
0x180003437  pop     rbp
0x180003438  pop     rbx
0x180003439  retn
```
