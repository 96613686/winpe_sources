# TraceCreateServerComplete

- ea: `0x180002910`
- end: `0x180002ada`
- name: `TraceCreateServerComplete`
- size: `458`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001100`
- `0x180005450`

## callees

- `0x1800027b0`
- `0x180002910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000293a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000299e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000293a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000299e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000295d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000296f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000295d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000296f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002a43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180002a43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800029f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800029f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180002a9e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180002a9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002983`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002ac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002983`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002ac0`

## pseudocode

```c
__int64 __fastcall TraceCreateServerComplete(__int64 a1)
{
  HANDLE EventA; // rax
  DWORD LastError; // edi
  HANDLE *v4; // rsi
  void *v5; // rcx
  HANDLE v7; // rax
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  int Data; // [rsp+90h] [rbp+8h] BYREF
  DWORD Type; // [rsp+98h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+18h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+20h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  dwDisposition = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  *(_QWORD *)(a1 + 80) = EventA;
  if ( !EventA )
  {
    LastError = GetLastError();
    v4 = (HANDLE *)(a1 + 88);
LABEL_3:
    if ( *v4 )
    {
      CloseHandle(*v4);
      *v4 = 0;
    }
    v5 = *(void **)(a1 + 80);
    if ( v5 )
    {
      CloseHandle(v5);
      *(_QWORD *)(a1 + 80) = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    return LastError;
  }
  v7 = CreateEventA(0, 0, 0, 0);
  *(_QWORD *)(a1 + 88) = v7;
  v4 = (HANDLE *)(a1 + 88);
  if ( !v7 )
  {
    LastError = GetLastError();
    goto LABEL_3;
  }
  LastError = RegCreateKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Tracing", 0, 0, 0, 3u, 0, &hKey, &dwDisposition);
  if ( LastError )
    goto LABEL_3;
  cbData = 4;
  if ( RegQueryValueExA(hKey, "EnableConsoleTracing", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
  {
    Type = 4;
    cbData = 4;
    Data = 0;
    LastError = RegSetValueExA(hKey, "EnableConsoleTracing", 0, 4u, (const BYTE *)&Data, 4u);
    if ( LastError )
      goto LABEL_3;
  }
  if ( Data )
    *(_DWORD *)(a1 + 56) |= 4u;
  RegCloseKey(hKey);
  hKey = 0;
  SetWaitArray(a1);
  return 0;
}

```

## disassembly

```asm
0x180002910  mov     rax, rsp
0x180002913  push    rbx
0x180002914  push    rbp
0x180002915  push    rsi
0x180002916  push    rdi
0x180002917  sub     rsp, 68h
0x18000291b  xor     ebp, ebp
0x18000291d  mov     rbx, rcx
0x180002920  xor     ecx, ecx; lpEventAttributes
0x180002922  mov     [rax-38h], rbp
0x180002926  xor     r9d, r9d; lpName
0x180002929  mov     [rax+10h], ebp
0x18000292c  xor     r8d, r8d; bInitialState
0x18000292f  mov     [rax+18h], ebp
0x180002932  xor     edx, edx; bManualReset
0x180002934  mov     [rax+8], ebp
0x180002937  mov     [rax+20h], ebp
0x18000293a  call    cs:__imp_CreateEventA
0x180002940  mov     [rbx+50h], rax
0x180002944  test    rax, rax
0x180002947  jnz     short loc_180002994
0x180002949  call    cs:__imp_GetLastError
0x18000294f  mov     edi, eax
0x180002951  lea     rsi, [rbx+58h]
0x180002955  mov     rcx, [rsi]; hObject
0x180002958  test    rcx, rcx
0x18000295b  jz      short loc_180002966
0x18000295d  call    cs:__imp_CloseHandle
0x180002963  mov     [rsi], rbp
0x180002966  mov     rcx, [rbx+50h]; hObject
0x18000296a  test    rcx, rcx
0x18000296d  jz      short loc_180002979
0x18000296f  call    cs:__imp_CloseHandle
0x180002975  mov     [rbx+50h], rbp
0x180002979  mov     rcx, [rsp+88h+hKey]; hKey
0x18000297e  test    rcx, rcx
0x180002981  jz      short loc_180002989
0x180002983  call    cs:__imp_RegCloseKey
0x180002989  mov     eax, edi
0x18000298b  add     rsp, 68h
0x18000298f  pop     rdi
0x180002990  pop     rsi
0x180002991  pop     rbp
0x180002992  pop     rbx
0x180002993  retn
0x180002994  xor     r9d, r9d; lpName
0x180002997  xor     r8d, r8d; bInitialState
0x18000299a  xor     edx, edx; bManualReset
0x18000299c  xor     ecx, ecx; lpEventAttributes
0x18000299e  call    cs:__imp_CreateEventA
0x1800029a4  mov     [rbx+58h], rax
0x1800029a8  lea     rsi, [rbx+58h]
0x1800029ac  test    rax, rax
0x1800029af  jnz     short loc_1800029BB
0x1800029b1  call    cs:__imp_GetLastError
0x1800029b7  mov     edi, eax
0x1800029b9  jmp     short loc_180002955
0x1800029bb  lea     rax, [rsp+88h+dwDisposition]
0x1800029c3  xor     r9d, r9d; lpClass
0x1800029c6  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x1800029cb  lea     rdx, SubKey; "Software\\Microsoft\\Tracing"
0x1800029d2  lea     rax, [rsp+88h+hKey]
0x1800029d7  xor     r8d, r8d; Reserved
0x1800029da  mov     [rsp+88h+phkResult], rax; phkResult
0x1800029df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800029e6  mov     [rsp+88h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1800029eb  mov     [rsp+88h+samDesired], 3; samDesired
0x1800029f3  mov     [rsp+88h+dwOptions], ebp; dwOptions
0x1800029f7  call    cs:__imp_RegCreateKeyExA
0x1800029fd  mov     edi, eax
0x1800029ff  test    eax, eax
0x180002a01  jnz     loc_180002955
0x180002a07  mov     rcx, [rsp+88h+hKey]; hKey
0x180002a0c  lea     rax, [rsp+88h+cbData]
0x180002a14  mov     qword ptr [rsp+88h+samDesired], rax; lpcbData
0x180002a19  lea     r9, [rsp+88h+Type]; lpType
0x180002a21  lea     rax, [rsp+88h+Data]
0x180002a29  mov     [rsp+88h+cbData], 4
0x180002a34  xor     r8d, r8d; lpReserved
0x180002a37  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180002a3c  lea     rdx, aEnableconsolet_0; "EnableConsoleTracing"
0x180002a43  call    cs:__imp_RegQueryValueExA
0x180002a49  test    eax, eax
0x180002a4b  jnz     short loc_180002A57
0x180002a4d  cmp     [rsp+88h+Type], 4
0x180002a55  jz      short loc_180002AAE
0x180002a57  mov     rcx, [rsp+88h+hKey]; hKey
0x180002a5c  lea     rax, [rsp+88h+Data]
0x180002a64  mov     [rsp+88h+samDesired], 4; cbData
0x180002a6c  lea     rdx, aEnableconsolet_0; "EnableConsoleTracing"
0x180002a73  mov     r9d, 4; dwType
0x180002a79  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180002a7e  xor     r8d, r8d; Reserved
0x180002a81  mov     [rsp+88h+Type], 4
0x180002a8c  mov     [rsp+88h+cbData], 4
0x180002a97  mov     [rsp+88h+Data], ebp
0x180002a9e  call    cs:__imp_RegSetValueExA
0x180002aa4  mov     edi, eax
0x180002aa6  test    eax, eax
0x180002aa8  jnz     loc_180002955
0x180002aae  cmp     [rsp+88h+Data], ebp
0x180002ab5  jz      short loc_180002ABB
0x180002ab7  or      dword ptr [rbx+38h], 4
0x180002abb  mov     rcx, [rsp+88h+hKey]; hKey
0x180002ac0  call    cs:__imp_RegCloseKey
0x180002ac6  mov     rcx, rbx
0x180002ac9  mov     [rsp+88h+hKey], rbp
0x180002ace  call    SetWaitArray
0x180002ad3  xor     eax, eax
0x180002ad5  jmp     loc_18000298B
```
