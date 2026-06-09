# Vml::VmServiceModule<GuestComputeServiceModule>::OnStopService(uint,uint,void *)

- ea: `0x14003c6cc`
- end: `0x14003c765`
- name: `?OnStopService@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@QEAAXIIPEAX@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003cc20`

## callees

- `0x14000efd8`
- `0x14000f264`
- `0x14003c6cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c6e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c6e7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003c72d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003c72d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c71e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c71e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003c714`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003c714`

## string_xrefs

- `0x14003c745`: `Vml::VmExeModule<class GuestComputeServiceModule>::Quit`

## pseudocode

```c
int __fastcall Vml::VmServiceModule<GuestComputeServiceModule>::OnStopService(__int64 a1)
{
  SERVICE_STATUS_HANDLE v2; // rcx
  void *v3; // rcx
  int result; // eax

  if ( *(_QWORD *)(a1 + 136) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
    if ( *(_DWORD *)(a1 + 108) != 3 )
      *(_QWORD *)(a1 + 124) = 0;
    v2 = *(SERVICE_STATUS_HANDLE *)(a1 + 136);
    *(_DWORD *)(a1 + 108) = 3;
    *(_DWORD *)(a1 + 116) = 0;
    SetServiceStatus(v2, (LPSERVICE_STATUS)(a1 + 104));
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  }
  v3 = *(void **)(a1 + 88);
  if ( v3 )
    return SetEvent(v3);
  result = VmlIsDebugTraceEnabled(32770);
  if ( result )
    return VmlDebugTrace(
             32770,
             L"%hs calls with quit event NULL - call ignored.\n",
             "Vml::VmExeModule<class GuestComputeServiceModule>::Quit");
  return result;
}

```

## disassembly

```asm
0x14003c6cc  mov     [rsp+arg_8], rbx
0x14003c6d1  push    rdi
0x14003c6d2  sub     rsp, 20h
0x14003c6d6  cmp     qword ptr [rcx+88h], 0
0x14003c6de  mov     rbx, rcx
0x14003c6e1  jz      short loc_14003C724
0x14003c6e3  add     rcx, 28h ; '('; lpCriticalSection
0x14003c6e7  call    cs:__imp_EnterCriticalSection
0x14003c6ed  lea     rdx, [rbx+68h]; lpServiceStatus
0x14003c6f1  cmp     dword ptr [rdx+4], 3
0x14003c6f5  jz      short loc_14003C6FF
0x14003c6f7  mov     qword ptr [rbx+7Ch], 0
0x14003c6ff  mov     rcx, [rbx+88h]; hServiceStatus
0x14003c706  mov     dword ptr [rbx+6Ch], 3
0x14003c70d  mov     dword ptr [rbx+74h], 0
0x14003c714  call    cs:__imp_SetServiceStatus
0x14003c71a  lea     rcx, [rbx+28h]; lpCriticalSection
0x14003c71e  call    cs:__imp_LeaveCriticalSection
0x14003c724  mov     rcx, [rbx+58h]; hEvent
0x14003c728  test    rcx, rcx
0x14003c72b  jz      short loc_14003C735
0x14003c72d  call    cs:__imp_SetEvent
0x14003c733  jmp     short loc_14003C75A
0x14003c735  mov     ebx, 8002h
0x14003c73a  mov     ecx, ebx
0x14003c73c  call    VmlIsDebugTraceEnabled
0x14003c741  test    eax, eax
0x14003c743  jz      short loc_14003C75A
0x14003c745  lea     r8, aVmlVmexemodule; "Vml::VmExeModule<class GuestComputeServ"...
0x14003c74c  mov     ecx, ebx
0x14003c74e  lea     rdx, aHsCallsWithQui; "%hs calls with quit event NULL - call i"...
0x14003c755  call    VmlDebugTrace
0x14003c75a  mov     rbx, [rsp+28h+arg_8]
0x14003c75f  add     rsp, 20h
0x14003c763  pop     rdi
0x14003c764  retn
```
