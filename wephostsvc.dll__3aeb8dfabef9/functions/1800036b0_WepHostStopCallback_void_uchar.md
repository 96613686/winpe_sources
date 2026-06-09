# WepHostStopCallback(void *,uchar)

- ea: `0x1800036b0`
- end: `0x1800037e7`
- name: `?WepHostStopCallback@@YAXPEAXE@Z`
- size: `311`
- prototype: `void __fastcall(void *, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002620`
- `0x1800026e0`
- `0x1800036b0`
- `0x180003930`
- `0x180003960`
- `0x180003a70`
- `0x180003be0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003739`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800037b2`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800037b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003706`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003706`

## pseudocode

```c
void __fastcall WepHostStopCallback(void *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r8
  HANDLE v4; // rcx
  _QWORD *v5; // rbx
  TRACEHANDLE v6; // rcx
  _BYTE v7[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, (unsigned __int8)a2);
  WepHostTearDownRPCServer();
  if ( g_hInstance )
    FreeLibrary(g_hInstance);
  v4 = hObject;
  qword_180008738 = 0;
  g_Table = 0;
  xmmword_180008718 = 0;
  xmmword_180008728 = 0;
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( (Microsoft_Windows_WEPHOSTSVCEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v4, ServiceStop, v3, 1, v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids);
  McGenEventUnregister_EventUnregister();
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    while ( v5 )
    {
      v6 = v5[1];
      if ( v6 )
      {
        UnregisterTraceGuids(v6);
        v5[1] = 0;
      }
      v5 = (_QWORD *)*v5;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x1800036b0  mov     [rsp+arg_8], rbx
0x1800036b5  push    rdi
0x1800036b6  sub     rsp, 50h
0x1800036ba  mov     rax, cs:__security_cookie
0x1800036c1  xor     rax, rsp
0x1800036c4  mov     [rsp+58h+var_18], rax
0x1800036c9  mov     r9, rcx
0x1800036cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036d3  lea     rdi, WPP_GLOBAL_Control
0x1800036da  cmp     rcx, rdi
0x1800036dd  jz      short loc_1800036F5
0x1800036df  test    byte ptr [rcx+1Ch], 20h
0x1800036e3  jz      short loc_1800036F5
0x1800036e5  mov     rcx, [rcx+10h]
0x1800036e9  movzx   eax, dl
0x1800036ec  mov     dword ptr [rsp+58h+var_38], eax
0x1800036f0  call    WPP_SF_qd
0x1800036f5  call    ?WepHostTearDownRPCServer@@YAXXZ; WepHostTearDownRPCServer(void)
0x1800036fa  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hLibModule
0x180003701  test    rcx, rcx
0x180003704  jz      short loc_18000370C
0x180003706  call    cs:__imp_FreeLibrary
0x18000370c  mov     rcx, cs:hObject; hObject
0x180003713  xorps   xmm0, xmm0
0x180003716  xor     eax, eax
0x180003718  mov     cs:qword_180008738, rax
0x18000371f  movups  cs:?g_Table@@3U_tagPluginAPITable@@A, xmm0; _tagPluginAPITable g_Table
0x180003726  movups  cs:xmmword_180008718, xmm0
0x18000372d  movups  cs:xmmword_180008728, xmm0
0x180003734  test    rcx, rcx
0x180003737  jz      short loc_18000374A
0x180003739  call    cs:__imp_CloseHandle
0x18000373f  mov     cs:hObject, 0
0x18000374a  test    cs:Microsoft_Windows_WEPHOSTSVCEnableBits, 2
0x180003751  jz      short loc_18000376F
0x180003753  lea     rax, [rsp+58h+var_28]
0x180003758  mov     r9d, 1
0x18000375e  lea     rdx, ServiceStop
0x180003765  mov     [rsp+58h+var_38], rax
0x18000376a  call    McGenEventWrite_EventWriteTransfer
0x18000376f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003776  cmp     rcx, rdi
0x180003779  jz      short loc_180003796
0x18000377b  test    byte ptr [rcx+1Ch], 20h
0x18000377f  jz      short loc_180003796
0x180003781  mov     rcx, [rcx+10h]
0x180003785  lea     r8, WPP_3a1233b099da3452b07b65d2eb146164_Traceguids
0x18000378c  mov     edx, 0Fh
0x180003791  call    WPP_SF_
0x180003796  call    McGenEventUnregister_EventUnregister
0x18000379b  mov     rbx, cs:WPP_GLOBAL_Control
0x1800037a2  cmp     rbx, rdi
0x1800037a5  jz      short loc_1800037CF
0x1800037a7  jmp     short loc_1800037C3
0x1800037a9  mov     rcx, [rbx+8]; RegistrationHandle
0x1800037ad  test    rcx, rcx
0x1800037b0  jz      short loc_1800037C0
0x1800037b2  call    cs:__imp_UnregisterTraceGuids
0x1800037b8  mov     qword ptr [rbx+8], 0
0x1800037c0  mov     rbx, [rbx]
0x1800037c3  test    rbx, rbx
0x1800037c6  jnz     short loc_1800037A9
0x1800037c8  mov     cs:WPP_GLOBAL_Control, rdi
0x1800037cf  mov     rcx, [rsp+58h+var_18]
0x1800037d4  xor     rcx, rsp; StackCookie
0x1800037d7  call    __security_check_cookie
0x1800037dc  mov     rbx, [rsp+58h+arg_8]
0x1800037e1  add     rsp, 50h
0x1800037e5  pop     rdi
0x1800037e6  retn
```
