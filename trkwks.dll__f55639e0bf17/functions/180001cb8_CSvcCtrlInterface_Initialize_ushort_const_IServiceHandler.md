# CSvcCtrlInterface::Initialize(ushort const *,IServiceHandler *)

- ea: `0x180001cb8`
- end: `0x180001d44`
- name: `?Initialize@CSvcCtrlInterface@@QEAAXPEBGPEAVIServiceHandler@@@Z`
- size: `140`
- prototype: `void __fastcall(CSvcCtrlInterface *__hidden this, const unsigned __int16 *, struct IServiceHandler *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180001e28`

## callees

- `0x180001940`
- `0x180001cb8`
- `0x18000d038`
- `0x18000feb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d22`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180001cea`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180001cea`

## pseudocode

```c
void __fastcall CSvcCtrlInterface::Initialize(
        CSvcCtrlInterface *this,
        const unsigned __int16 *a2,
        struct IServiceHandler *a3)
{
  SERVICE_STATUS_HANDLE v4; // rax
  unsigned int v5; // r9d
  signed int LastError; // eax
  DWORD v7; // eax

  *(_DWORD *)this |= 1u;
  *((_QWORD *)this + 1) = a3;
  CSvcCtrlInterface::_fStoppedOrStopping = 0;
  *((_DWORD *)this + 5) = 0;
  v4 = RegisterServiceCtrlHandlerExW(L"TrkWks", CSvcCtrlInterface::ServiceHandler, this);
  *((_QWORD *)this + 4) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    TrkReportInternalError(0xCu, 0x3Du, LastError, L"TrkWks");
    v7 = GetLastError();
    TrkRaiseWin32Error(v7);
  }
  CSvcCtrlInterface::SetServiceStatus(this, 2u, 0, v5);
}

```

## disassembly

```asm
0x180001cb8  push    rbx
0x180001cba  sub     rsp, 20h
0x180001cbe  or      dword ptr [rcx], 1
0x180001cc1  lea     rdx, ?ServiceHandler@CSvcCtrlInterface@@CAKKKPEAX0@Z; lpHandlerProc
0x180001cc8  mov     [rcx+8], r8
0x180001ccc  mov     rbx, rcx
0x180001ccf  mov     cs:?_fStoppedOrStopping@CSvcCtrlInterface@@0HA, 0; int CSvcCtrlInterface::_fStoppedOrStopping
0x180001cd9  mov     r8, rcx; lpContext
0x180001cdc  mov     dword ptr [rcx+14h], 0
0x180001ce3  lea     rcx, ServiceName; "TrkWks"
0x180001cea  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180001cf0  mov     [rbx+20h], rax
0x180001cf4  test    rax, rax
0x180001cf7  jnz     short loc_180001D30
0x180001cf9  call    cs:__imp_GetLastError
0x180001cff  test    eax, eax
0x180001d01  jle     short loc_180001D0B
0x180001d03  movzx   eax, ax
0x180001d06  or      eax, 80070000h
0x180001d0b  mov     edx, 3Dh ; '='; unsigned int
0x180001d10  lea     r9, ServiceName; "TrkWks"
0x180001d17  mov     r8d, eax; int
0x180001d1a  lea     ecx, [rdx-31h]; unsigned int
0x180001d1d  call    ?TrkReportInternalError@@YAJKKJPEBG@Z; TrkReportInternalError(ulong,ulong,long,ushort const *)
0x180001d22  call    cs:__imp_GetLastError
0x180001d28  mov     ecx, eax; int
0x180001d2a  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180001d30  xor     r8d, r8d; unsigned int
0x180001d33  mov     rcx, rbx; this
0x180001d36  lea     edx, [r8+2]; unsigned int
0x180001d3a  add     rsp, 20h
0x180001d3e  pop     rbx
0x180001d3f  jmp     ?SetServiceStatus@CSvcCtrlInterface@@QEAAXKKK@Z; CSvcCtrlInterface::SetServiceStatus(ulong,ulong,ulong)
```
