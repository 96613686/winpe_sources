# ServiceMain(ulong,ushort * *)

- ea: `0x180027e20`
- end: `0x180027f89`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `361`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18000a768`
- `0x180027e20`
- `0x180028000`
- `0x1800280b8`
- `0x18002d870`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x180027edc`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x180027edc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180027f23`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180027f23`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  int v3; // ebx
  struct ServiceContext *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  qword_180041418 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_GLOBAL_Control = (LPCSTR)&WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  qword_180041420 = 1;
  WppInitUm(a1, a2);
  ServiceStatus.dwServiceType = 48;
  *(_OWORD *)&ServiceStatus.dwControlsAccepted = 0;
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwWaitHint = 20000;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids);
  v2 = RegisterServiceCtrlHandlerExA("ssdpsrv", (LPHANDLER_FUNCTION_EX)ServiceCtrlHandler, 0);
  hServiceStatus = v2;
  if ( v2 )
  {
    if ( !SetServiceStatus(v2, &ServiceStatus) )
      goto LABEL_13;
    v3 = SsdpMain(hServiceStatus, &ServiceStatus, (void **)&v4);
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids);
    if ( v3 )
LABEL_13:
      SsdpMainStop(v4, 0);
  }
  else if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids);
  }
}

```

## disassembly

```asm
0x180027e20  mov     [rsp+arg_0], rbx
0x180027e25  push    rbp
0x180027e26  sub     rsp, 20h
0x180027e2a  mov     [rsp+28h+arg_10], 0
0x180027e33  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180027e3a  mov     cs:qword_180041418, 0
0x180027e45  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180027e4c  lea     rax, WPP_MAIN_CB
0x180027e53  mov     cs:WPP_GLOBAL_Control, rax
0x180027e5a  mov     cs:WPP_MAIN_CB, 0
0x180027e65  mov     cs:qword_180041420, 1
0x180027e70  call    WppInitUm
0x180027e75  xorps   xmm0, xmm0
0x180027e78  mov     cs:ServiceStatus.dwServiceType, 30h ; '0'
0x180027e82  movups  xmmword ptr cs:ServiceStatus.dwControlsAccepted, xmm0
0x180027e89  mov     cs:ServiceStatus.dwCurrentState, 2
0x180027e93  mov     cs:ServiceStatus.dwWaitHint, 4E20h
0x180027e9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ea4  lea     rbp, WPP_GLOBAL_Control
0x180027eab  cmp     rcx, rbp
0x180027eae  jz      short loc_180027ECB
0x180027eb0  test    byte ptr [rcx+1Ch], 8
0x180027eb4  jz      short loc_180027ECB
0x180027eb6  mov     rcx, [rcx+10h]
0x180027eba  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x180027ec1  mov     edx, 0Ah
0x180027ec6  call    WPP_SF_
0x180027ecb  xor     r8d, r8d; lpContext
0x180027ece  lea     rdx, ?ServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180027ed5  lea     rcx, ServiceName; "ssdpsrv"
0x180027edc  call    cs:__imp_RegisterServiceCtrlHandlerExA
0x180027ee2  mov     cs:hServiceStatus, rax
0x180027ee9  test    rax, rax
0x180027eec  jnz     short loc_180027F19
0x180027eee  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ef5  cmp     rcx, rbp
0x180027ef8  jz      loc_180027F7E
0x180027efe  test    byte ptr [rcx+1Ch], 1
0x180027f02  jz      short loc_180027F7E
0x180027f04  mov     rcx, [rcx+10h]
0x180027f08  lea     edx, [rax+0Bh]
0x180027f0b  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x180027f12  call    WPP_SF_
0x180027f17  jmp     short loc_180027F7E
0x180027f19  lea     rdx, ServiceStatus; lpServiceStatus
0x180027f20  mov     rcx, rax; hServiceStatus
0x180027f23  call    cs:__imp_SetServiceStatus
0x180027f29  test    eax, eax
0x180027f2b  jz      short loc_180027F72
0x180027f2d  mov     rcx, cs:hServiceStatus; struct SERVICE_STATUS_HANDLE__ *
0x180027f34  lea     r8, [rsp+28h+arg_10]; void **
0x180027f39  lea     rdx, ServiceStatus; struct _SERVICE_STATUS *
0x180027f40  call    ?SsdpMain@@YAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@PEAPEAX@Z; SsdpMain(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *,void * *)
0x180027f45  mov     ebx, eax
0x180027f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f4e  cmp     rcx, rbp
0x180027f51  jz      short loc_180027F6E
0x180027f53  test    byte ptr [rcx+1Ch], 8
0x180027f57  jz      short loc_180027F6E
0x180027f59  mov     rcx, [rcx+10h]
0x180027f5d  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x180027f64  mov     edx, 0Ch
0x180027f69  call    WPP_SF_
0x180027f6e  test    ebx, ebx
0x180027f70  jz      short loc_180027F7E
0x180027f72  mov     rcx, [rsp+28h+arg_10]; struct ServiceContext *
0x180027f77  xor     edx, edx; int
0x180027f79  call    ?SsdpMainStop@@YAXPEAXH@Z; SsdpMainStop(void *,int)
0x180027f7e  mov     rbx, [rsp+28h+arg_0]
0x180027f83  add     rsp, 20h
0x180027f87  pop     rbp
0x180027f88  retn
```
