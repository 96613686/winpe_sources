# ShutdownAdapter(void * &)

- ea: `0x1800062d0`
- end: `0x180006354`
- name: `?ShutdownAdapter@@YAJAEAPEAX@Z`
- size: `132`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800058f0`
- `0x1800062d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006302`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006319`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800062e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006313`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800062e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006313`

## string_xrefs

- `0x18000630c`: `Failed to signal the monitoring thread\n`

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
0x1800062d0  mov     [rsp+arg_0], rbx
0x1800062d5  push    rdi
0x1800062d6  sub     rsp, 20h
0x1800062da  mov     rdi, rcx
0x1800062dd  mov     ebx, 8000FFFFh
0x1800062e2  lea     rcx, aShutdownadapte_0; "ShutdownAdapter called\n"
0x1800062e9  call    cs:__imp_OutputDebugStringW
0x1800062ef  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x1800062f4  test    rax, rax
0x1800062f7  jz      short loc_180006347
0x1800062f9  mov     rcx, [rax+50h]; hEvent
0x1800062fd  test    rcx, rcx
0x180006300  jz      short loc_18000633B
0x180006302  call    cs:__imp_SetEvent
0x180006308  test    eax, eax
0x18000630a  jnz     short loc_18000633B
0x18000630c  lea     rcx, aFailedToSignal; "Failed to signal the monitoring thread"...
0x180006313  call    cs:__imp_OutputDebugStringW
0x180006319  call    cs:__imp_GetLastError
0x18000631f  mov     ebx, eax
0x180006321  test    eax, eax
0x180006323  jle     short loc_18000632E
0x180006325  movzx   ebx, ax
0x180006328  or      ebx, 80070000h
0x18000632e  test    ebx, ebx
0x180006330  jns     short loc_18000633D
0x180006332  mov     qword ptr [rdi], 0
0x180006339  jmp     short loc_180006347
0x18000633b  xor     ebx, ebx
0x18000633d  mov     rcx, cs:?g_hMonitorThread@@3PEAXEA; void * g_hMonitorThread
0x180006344  mov     [rdi], rcx
0x180006347  mov     eax, ebx
0x180006349  mov     rbx, [rsp+28h+arg_0]
0x18000634e  add     rsp, 20h
0x180006352  pop     rdi
0x180006353  retn
```
