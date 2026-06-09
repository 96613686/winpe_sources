# ShutdownAdapter(void * &)

- ea: `0x1800066c0`
- end: `0x18000675d`
- name: `?ShutdownAdapter@@YAJAEAPEAX@Z`
- size: `157`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005c10`
- `0x1800066c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800066f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800066f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000671b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000671b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800066d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000670f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800066d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000670f`

## string_xrefs

- `0x180006708`: `Failed to signal the monitoring thread\n`

## pseudocode

```c
__int64 __fastcall ShutdownAdapter(void **a1)
{
  unsigned int v2; // ebx
  struct CompatibilityAdapter *Adapter; // rax
  void *v4; // rcx
  signed int LastError; // eax

  v2 = -2147418113;
  OutputDebugStringW(L"ShutdownAdapter called\n");
  Adapter = CompatibilityAdapter::GetAdapter();
  if ( Adapter )
  {
    v4 = (void *)*((_QWORD *)Adapter + 10);
    if ( !v4 || SetEvent(v4) )
    {
      v2 = 0;
    }
    else
    {
      OutputDebugStringW(L"Failed to signal the monitoring thread\n");
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (v2 & 0x80000000) != 0 )
      {
        *a1 = 0;
        return v2;
      }
    }
    *a1 = g_hMonitorThread;
  }
  return v2;
}

```

## disassembly

```asm
0x1800066c0  mov     [rsp+arg_0], rbx
0x1800066c5  push    rdi
0x1800066c6  sub     rsp, 20h
0x1800066ca  mov     rdi, rcx
0x1800066cd  mov     ebx, 8000FFFFh
0x1800066d2  lea     rcx, aShutdownadapte_0; "ShutdownAdapter called\n"
0x1800066d9  call    cs:__imp_OutputDebugStringW
0x1800066e0  nop     dword ptr [rax+rax+00h]
0x1800066e5  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x1800066ea  test    rax, rax
0x1800066ed  jz      short loc_18000674F
0x1800066ef  mov     rcx, [rax+50h]; hEvent
0x1800066f3  test    rcx, rcx
0x1800066f6  jz      short loc_180006743
0x1800066f8  call    cs:__imp_SetEvent
0x1800066ff  nop     dword ptr [rax+rax+00h]
0x180006704  test    eax, eax
0x180006706  jnz     short loc_180006743
0x180006708  lea     rcx, aFailedToSignal; "Failed to signal the monitoring thread"...
0x18000670f  call    cs:__imp_OutputDebugStringW
0x180006716  nop     dword ptr [rax+rax+00h]
0x18000671b  call    cs:__imp_GetLastError
0x180006722  nop     dword ptr [rax+rax+00h]
0x180006727  mov     ebx, eax
0x180006729  test    eax, eax
0x18000672b  jle     short loc_180006736
0x18000672d  movzx   ebx, ax
0x180006730  or      ebx, 80070000h
0x180006736  test    ebx, ebx
0x180006738  jns     short loc_180006745
0x18000673a  mov     qword ptr [rdi], 0
0x180006741  jmp     short loc_18000674F
0x180006743  xor     ebx, ebx
0x180006745  mov     rcx, cs:?g_hMonitorThread@@3PEAXEA; void * g_hMonitorThread
0x18000674c  mov     [rdi], rcx
0x18000674f  mov     eax, ebx
0x180006751  mov     rbx, [rsp+28h+arg_0]
0x180006756  add     rsp, 20h
0x18000675a  pop     rdi
0x18000675b  retn
```
