# ServiceHandler

- ea: `0x180002fd0`
- end: `0x1800030ba`
- name: `ServiceHandler`
- size: `234`
- prototype: `DWORD __fastcall(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180002fd0`
- `0x1800030c0`
- `0x180003450`
- `0x1800041e0`
- `0x18000427c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800030a1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800030a1`

## pseudocode

```c
DWORD __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, LPVOID lpContext)
{
  DWORD dwCurrentState; // ebx
  DWORD v6; // ecx
  DWORD v7; // ecx
  DWORD v8; // ecx
  int started; // edi

  dwCurrentState = g_state.dwCurrentState;
  if ( dwControl == 14 )
  {
    if ( dwEventType == 6 )
    {
      started = SessionLogoffCallback(lpEventData[1]);
      if ( started )
        goto LABEL_10;
    }
    return 0;
  }
  if ( dwControl == 4 )
    return 0;
  v6 = dwControl - 1;
  if ( !v6 )
  {
    g_fShutdown = 0;
    goto LABEL_22;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    started = MySetServiceStatus(6u, 0);
    if ( started )
      goto LABEL_10;
    started = SeclStopRpcServer();
    if ( started )
      goto LABEL_10;
    dwCurrentState = 7;
LABEL_20:
    started = 0;
    goto LABEL_10;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    started = MySetServiceStatus(5u, 0);
    if ( started )
      goto LABEL_10;
    started = SeclStartRpcServer();
    if ( started )
      goto LABEL_10;
    dwCurrentState = 4;
    goto LABEL_20;
  }
  if ( v8 != 2 )
  {
    started = 120;
LABEL_10:
    MySetServiceStatus(dwCurrentState, 0);
    return started;
  }
  g_fShutdown = 1;
LABEL_22:
  if ( SetEvent(g_stopServiceEvent) )
    return 0;
  return GetLastError();
}

```

## disassembly

```asm
0x180002fd0  mov     [rsp+arg_0], rbx
0x180002fd5  push    rdi
0x180002fd6  sub     rsp, 20h
0x180002fda  mov     ebx, cs:g_state.dwCurrentState
0x180002fe0  cmp     ecx, 0Eh
0x180002fe3  jnz     short loc_180002FF7
0x180002fe5  sub     edx, 5
0x180002fe8  jnz     short loc_180003026
0x180002fea  xor     eax, eax
0x180002fec  mov     rbx, [rsp+28h+arg_0]
0x180002ff1  add     rsp, 20h
0x180002ff5  pop     rdi
0x180002ff6  retn
0x180002ff7  cmp     ecx, 4
0x180002ffa  jz      short loc_180002FEA
0x180002ffc  sub     ecx, 1
0x180002fff  jz      loc_180003092
0x180003005  sub     ecx, 1
0x180003008  jz      short loc_18000306C
0x18000300a  sub     ecx, 1
0x18000300d  jz      short loc_180003048
0x18000300f  cmp     ecx, 2
0x180003012  jz      short loc_18000303C
0x180003014  mov     edi, 78h ; 'x'
0x180003019  xor     edx, edx
0x18000301b  mov     ecx, ebx
0x18000301d  call    MySetServiceStatus
0x180003022  mov     eax, edi
0x180003024  jmp     short loc_180002FEC
0x180003026  cmp     edx, 1
0x180003029  jnz     short loc_180002FEA
0x18000302b  mov     ecx, [r8+4]
0x18000302f  call    SessionLogoffCallback
0x180003034  mov     edi, eax
0x180003036  test    eax, eax
0x180003038  jz      short loc_180002FEA
0x18000303a  jmp     short loc_180003019
0x18000303c  mov     cs:g_fShutdown, 1
0x180003046  jmp     short loc_18000309A
0x180003048  xor     edx, edx
0x18000304a  mov     ecx, 5
0x18000304f  call    MySetServiceStatus
0x180003054  mov     edi, eax
0x180003056  test    eax, eax
0x180003058  jnz     short loc_180003019
0x18000305a  call    SeclStartRpcServer
0x18000305f  mov     edi, eax
0x180003061  test    eax, eax
0x180003063  jnz     short loc_180003019
0x180003065  mov     ebx, 4
0x18000306a  jmp     short loc_18000308E
0x18000306c  xor     edx, edx
0x18000306e  mov     ecx, 6
0x180003073  call    MySetServiceStatus
0x180003078  mov     edi, eax
0x18000307a  test    eax, eax
0x18000307c  jnz     short loc_180003019
0x18000307e  call    SeclStopRpcServer
0x180003083  mov     edi, eax
0x180003085  test    eax, eax
0x180003087  jnz     short loc_180003019
0x180003089  mov     ebx, 7
0x18000308e  xor     edi, edi
0x180003090  jmp     short loc_180003019
0x180003092  xor     edi, edi
0x180003094  mov     cs:g_fShutdown, edi
0x18000309a  mov     rcx, cs:g_stopServiceEvent; hEvent
0x1800030a1  call    cs:__imp_SetEvent
0x1800030a7  test    eax, eax
0x1800030a9  jnz     loc_180002FEA
0x1800030af  call    cs:__imp_GetLastError
0x1800030b5  jmp     loc_180002FEC
```
