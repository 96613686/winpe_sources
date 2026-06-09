# ServiceMain(ulong,ushort * *)

- ea: `0x180029bf0`
- end: `0x180029d6a`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `378`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18000c078`
- `0x180029bf0`
- `0x180029df0`
- `0x180029ebc`
- `0x18002f900`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x180029cac`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerExA` at `0x180029cac`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180029cfd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180029cfd`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  int v3; // ebx
  struct ServiceContext *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  qword_180044518 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_GLOBAL_Control = (LPCSTR)&WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  qword_180044520 = 1;
  WppInitUm(a1, a2);
  ServiceStatus.dwServiceType = 48;
  *(_OWORD *)&ServiceStatus.dwControlsAccepted = 0;
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwWaitHint = 20000;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids);
  v2 = RegisterServiceCtrlHandlerExA("ssdpsrv", ServiceCtrlHandler, 0);
  hServiceStatus = v2;
  if ( v2 )
  {
    if ( !SetServiceStatus(v2, &ServiceStatus) )
      goto LABEL_13;
    v3 = SsdpMain(hServiceStatus, &ServiceStatus, &v4);
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids);
    if ( v3 )
LABEL_13:
      SsdpMainStop(v4);
  }
  else if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids);
  }
}

```

## disassembly

```asm
0x180029bf0  mov     [rsp+arg_0], rbx
0x180029bf5  push    rbp
0x180029bf6  sub     rsp, 20h
0x180029bfa  mov     [rsp+28h+arg_10], 0
0x180029c03  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180029c0a  mov     cs:qword_180044518, 0
0x180029c15  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180029c1c  lea     rax, WPP_MAIN_CB
0x180029c23  mov     cs:WPP_GLOBAL_Control, rax
0x180029c2a  mov     cs:WPP_MAIN_CB, 0
0x180029c35  mov     cs:qword_180044520, 1
0x180029c40  call    WppInitUm
0x180029c45  xorps   xmm0, xmm0
0x180029c48  mov     cs:ServiceStatus.dwServiceType, 30h ; '0'
0x180029c52  movups  xmmword ptr cs:ServiceStatus.dwControlsAccepted, xmm0
0x180029c59  mov     cs:ServiceStatus.dwCurrentState, 2
0x180029c63  mov     cs:ServiceStatus.dwWaitHint, 4E20h
0x180029c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c74  lea     rbp, WPP_GLOBAL_Control
0x180029c7b  cmp     rcx, rbp
0x180029c7e  jz      short loc_180029C9B
0x180029c80  test    byte ptr [rcx+1Ch], 8
0x180029c84  jz      short loc_180029C9B
0x180029c86  mov     rcx, [rcx+10h]
0x180029c8a  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x180029c91  mov     edx, 0Ah
0x180029c96  call    WPP_SF_
0x180029c9b  xor     r8d, r8d; lpContext
0x180029c9e  lea     rdx, ?ServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180029ca5  lea     rcx, ServiceName; "ssdpsrv"
0x180029cac  call    cs:__imp_RegisterServiceCtrlHandlerExA
0x180029cb3  nop     dword ptr [rax+rax+00h]
0x180029cb8  mov     cs:hServiceStatus, rax
0x180029cbf  test    rax, rax
0x180029cc2  jnz     short loc_180029CF3
0x180029cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ccb  cmp     rcx, rbp
0x180029cce  jz      loc_180029D5E
0x180029cd4  test    byte ptr [rcx+1Ch], 1
0x180029cd8  jz      loc_180029D5E
0x180029cde  mov     rcx, [rcx+10h]
0x180029ce2  lea     edx, [rax+0Bh]
0x180029ce5  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x180029cec  call    WPP_SF_
0x180029cf1  jmp     short loc_180029D5E
0x180029cf3  lea     rdx, ServiceStatus; lpServiceStatus
0x180029cfa  mov     rcx, rax; hServiceStatus
0x180029cfd  call    cs:__imp_SetServiceStatus
0x180029d04  nop     dword ptr [rax+rax+00h]
0x180029d09  test    eax, eax
0x180029d0b  jz      short loc_180029D52
0x180029d0d  mov     rcx, cs:hServiceStatus; struct SERVICE_STATUS_HANDLE__ *
0x180029d14  lea     r8, [rsp+28h+arg_10]; void **
0x180029d19  lea     rdx, ServiceStatus; struct _SERVICE_STATUS *
0x180029d20  call    ?SsdpMain@@YAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@PEAPEAX@Z; SsdpMain(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *,void * *)
0x180029d25  mov     ebx, eax
0x180029d27  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d2e  cmp     rcx, rbp
0x180029d31  jz      short loc_180029D4E
0x180029d33  test    byte ptr [rcx+1Ch], 8
0x180029d37  jz      short loc_180029D4E
0x180029d39  mov     rcx, [rcx+10h]
0x180029d3d  lea     r8, WPP_fc287fcc3a7730a9a5469c38641149bf_Traceguids
0x180029d44  mov     edx, 0Ch
0x180029d49  call    WPP_SF_
0x180029d4e  test    ebx, ebx
0x180029d50  jz      short loc_180029D5E
0x180029d52  mov     rcx, [rsp+28h+arg_10]; struct ServiceContext *
0x180029d57  xor     edx, edx; int
0x180029d59  call    ?SsdpMainStop@@YAXPEAXH@Z; SsdpMainStop(void *,int)
0x180029d5e  mov     rbx, [rsp+28h+arg_0]
0x180029d63  add     rsp, 20h
0x180029d67  pop     rbp
0x180029d68  retn
```
