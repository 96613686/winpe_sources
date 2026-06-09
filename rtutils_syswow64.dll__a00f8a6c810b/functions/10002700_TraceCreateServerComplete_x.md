# TraceCreateServerComplete(x)

- ea: `0x10002700`
- end: `0x100027d5`
- name: `_TraceCreateServerComplete@4`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10002470`
- `0x100030b0`

## callees

- `0x10002700`
- `0x10002de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1000271c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10002735`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1000271c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10002735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000562a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000563e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000562a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000563e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100055d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100055e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100055d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100055e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002791`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x10002791`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100027b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10005653`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100027b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10005653`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10005613`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10005613`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10002765`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x10002765`

## pseudocode

```c
DWORD __thiscall TraceCreateServerComplete(int this)
{
  HANDLE EventA; // eax
  HANDLE v3; // eax
  HANDLE *v4; // edi
  DWORD LastError; // ebx
  DWORD dwDisposition; // [esp+Ch] [ebp-14h] BYREF
  DWORD cbData; // [esp+10h] [ebp-10h] BYREF
  DWORD Type; // [esp+14h] [ebp-Ch] BYREF
  BYTE Data[4]; // [esp+18h] [ebp-8h] BYREF
  HKEY phkResult; // [esp+1Ch] [ebp-4h] BYREF

  phkResult = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  *(_DWORD *)(this + 52) = EventA;
  if ( EventA )
  {
    v3 = CreateEventA(0, 0, 0, 0);
    *(_DWORD *)(this + 56) = v3;
    v4 = (HANDLE *)(this + 56);
    if ( v3 )
    {
      LastError = RegCreateKeyExA(
                    HKEY_LOCAL_MACHINE,
                    "Software\\Microsoft\\Tracing",
                    0,
                    0,
                    0,
                    3u,
                    0,
                    &phkResult,
                    &dwDisposition);
      if ( !LastError )
      {
        if ( (cbData = 4, !RegQueryValueExA(phkResult, "EnableConsoleTracing", 0, &Type, Data, &cbData)) && Type == 4
          || (Type = 4,
              cbData = 4,
              *(_DWORD *)Data = 0,
              (LastError = RegSetValueExA(phkResult, "EnableConsoleTracing", 0, 4u, Data, 4u)) == 0) )
        {
          if ( *(_DWORD *)Data )
            *(_DWORD *)(this + 32) |= 4u;
          RegCloseKey(phkResult);
          phkResult = 0;
          SetWaitArray(this);
          return 0;
        }
      }
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = (HANDLE *)(this + 56);
  }
  if ( *v4 )
  {
    CloseHandle(*v4);
    *v4 = 0;
  }
  if ( *(_DWORD *)(this + 52) )
  {
    CloseHandle(*(HANDLE *)(this + 52));
    *(_DWORD *)(this + 52) = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return LastError;
}

```

## disassembly

```asm
0x10002700  mov     edi, edi
0x10002702  push    ebp
0x10002703  mov     ebp, esp
0x10002705  sub     esp, 14h
0x10002708  push    ebx
0x10002709  push    esi
0x1000270a  push    edi
0x1000270b  push    0; lpName
0x1000270d  push    0; bInitialState
0x1000270f  push    0; bManualReset
0x10002711  push    0; lpEventAttributes
0x10002713  mov     esi, ecx
0x10002715  mov     [ebp+phkResult], 0
0x1000271c  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x10002722  mov     [esi+34h], eax
0x10002725  test    eax, eax
0x10002727  jz      loc_100055D5
0x1000272d  push    0; lpName
0x1000272f  push    0; bInitialState
0x10002731  push    0; bManualReset
0x10002733  push    0; lpEventAttributes
0x10002735  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x1000273b  mov     [esi+38h], eax
0x1000273e  lea     edi, [esi+38h]
0x10002741  test    eax, eax
0x10002743  jz      loc_100055E2
0x10002749  lea     eax, [ebp+dwDisposition]
0x1000274c  push    eax; lpdwDisposition
0x1000274d  lea     eax, [ebp+phkResult]
0x10002750  push    eax; phkResult
0x10002751  push    0; lpSecurityAttributes
0x10002753  push    3; samDesired
0x10002755  push    0; dwOptions
0x10002757  push    0; lpClass
0x10002759  push    0; Reserved
0x1000275b  push    offset SubKey; "Software\\Microsoft\\Tracing"
0x10002760  push    80000002h; hKey
0x10002765  call    ds:__imp__RegCreateKeyExA@36; RegCreateKeyExA(x,x,x,x,x,x,x,x,x)
0x1000276b  mov     ebx, eax
0x1000276d  test    ebx, ebx
0x1000276f  jnz     loc_10005623
0x10002775  lea     eax, [ebp+cbData]
0x10002778  mov     [ebp+cbData], 4
0x1000277f  push    eax; lpcbData
0x10002780  lea     eax, [ebp+Data]
0x10002783  push    eax; lpData
0x10002784  lea     eax, [ebp+Type]
0x10002787  push    eax; lpType
0x10002788  push    ebx; lpReserved
0x10002789  push    offset ValueName; "EnableConsoleTracing"
0x1000278e  push    [ebp+phkResult]; hKey
0x10002791  call    ds:__imp__RegQueryValueExA@24; RegQueryValueExA(x,x,x,x,x,x)
0x10002797  test    eax, eax
0x10002799  jnz     loc_100055EC
0x1000279f  cmp     [ebp+Type], 4
0x100027a3  jnz     loc_100055EC
0x100027a9  cmp     dword ptr [ebp+Data], 0
0x100027ad  jnz     short loc_100027CF
0x100027af  push    [ebp+phkResult]; hKey
0x100027b2  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100027b8  mov     ecx, esi
0x100027ba  mov     [ebp+phkResult], 0
0x100027c1  call    _SetWaitArray@4; SetWaitArray(x)
0x100027c6  xor     eax, eax
0x100027c8  pop     edi
0x100027c9  pop     esi
0x100027ca  pop     ebx
0x100027cb  mov     esp, ebp
0x100027cd  pop     ebp
0x100027ce  retn
0x100027cf  or      dword ptr [esi+20h], 4
0x100027d3  jmp     short loc_100027AF
0x100055d5  call    ds:__imp__GetLastError@0; GetLastError()
0x100055db  mov     ebx, eax
0x100055dd  lea     edi, [esi+38h]
0x100055e0  jmp     short loc_10005623
0x100055e2  call    ds:__imp__GetLastError@0; GetLastError()
0x100055e8  mov     ebx, eax
0x100055ea  jmp     short loc_10005623
0x100055ec  push    4; cbData
0x100055ee  lea     eax, [ebp+Data]
0x100055f1  mov     [ebp+Type], 4
0x100055f8  push    eax; lpData
0x100055f9  push    4; dwType
0x100055fb  push    0; Reserved
0x100055fd  push    offset ValueName; "EnableConsoleTracing"
0x10005602  push    [ebp+phkResult]; hKey
0x10005605  mov     [ebp+cbData], 4
0x1000560c  mov     dword ptr [ebp+Data], 0
0x10005613  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10005619  mov     ebx, eax
0x1000561b  test    ebx, ebx
0x1000561d  jz      loc_100027A9
0x10005623  mov     eax, [edi]
0x10005625  test    eax, eax
0x10005627  jz      short loc_10005636
0x10005629  push    eax; hObject
0x1000562a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10005630  mov     dword ptr [edi], 0
0x10005636  mov     eax, [esi+34h]
0x10005639  test    eax, eax
0x1000563b  jz      short loc_1000564B
0x1000563d  push    eax; hObject
0x1000563e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10005644  mov     dword ptr [esi+34h], 0
0x1000564b  mov     eax, [ebp+phkResult]
0x1000564e  test    eax, eax
0x10005650  jz      short loc_10005659
0x10005652  push    eax; hKey
0x10005653  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10005659  mov     eax, ebx
0x1000565b  jmp     loc_100027C8
```
