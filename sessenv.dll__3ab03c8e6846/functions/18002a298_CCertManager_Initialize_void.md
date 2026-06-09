# CCertManager::Initialize(void)

- ea: `0x18002a298`
- end: `0x18002a40c`
- name: `?Initialize@CCertManager@@QEAAJXZ`
- size: `372`
- prototype: `__int64 __fastcall(CCertManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028780`

## callees

- `0x18000196c`
- `0x180003f30`
- `0x1800135a0`
- `0x180029d60`
- `0x18002a298`
- `0x18002abe4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002a38e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002a38e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a2bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a2f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a2bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a2f7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002a3c3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002a3c3`
- `USERENV!RegisterGPNotification` at `0x18002a34b`
- `USERENV!RegisterGPNotification` at `0x18002a34b`

## string_xrefs

- `0x18002a322`: `GetComputerFQDN failed: 0x%x in %s`
- `0x18002a3f1`: `StartCertUpdateThread failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CCertManager::Initialize(CCertManager *this)
{
  HANDLE EventW; // rax
  signed int v3; // eax
  unsigned int v4; // ebx
  HANDLE v5; // rax
  int ComputerFQDN; // eax
  DWORD LastError; // eax
  HANDLE Thread; // rax
  signed int v9; // eax

  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180084250);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 199) = EventW;
  if ( !EventW )
    goto LABEL_2;
  v5 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 203) = v5;
  if ( !v5 )
    goto LABEL_2;
  CCertManager::CreateCertUpdateEvent(this);
  ComputerFQDN = CCertManager::GetComputerFQDN(this);
  v4 = ComputerFQDN;
  if ( ComputerFQDN < 0 )
  {
    _DbgPrintMessage(8, "GetComputerFQDN failed: 0x%x in %s", (unsigned int)ComputerFQDN, "CCertManager::Initialize");
    return v4;
  }
  if ( RegisterGPNotification(*((HANDLE *)this + 203), 1) )
  {
    *((_DWORD *)this + 408) = 1;
  }
  else
  {
    LastError = GetLastError();
    _DbgPrintMessage(8, "RegisterGPNotification() failed: %d", LastError);
  }
  if ( GetModuleHandleExW(6u, (LPCWSTR)CCertManager::staticCertUpdateThread, (HMODULE *)this + 208) )
  {
    CCertManager::ReadDCConnectTimeoutFromReg(this);
    Thread = CreateThread(0, 0, CCertManager::staticCertUpdateThread, this, 0, 0);
    *((_QWORD *)this + 201) = Thread;
    if ( Thread )
    {
      return 0;
    }
    else
    {
      v9 = GetLastError();
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      if ( (v4 & 0x80000000) != 0 )
        _DbgPrintMessage(8, "StartCertUpdateThread failed: 0x%x in %s", v4, "CCertManager::Initialize");
    }
  }
  else
  {
LABEL_2:
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x18002a298  mov     [rsp+arg_0], rbx
0x18002a29d  push    rdi
0x18002a29e  sub     rsp, 30h
0x18002a2a2  mov     rdi, rcx
0x18002a2a5  lea     rcx, dword_180084250; CallbackContext
0x18002a2ac  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002a2b1  xor     r9d, r9d; lpName
0x18002a2b4  xor     r8d, r8d; bInitialState
0x18002a2b7  xor     edx, edx; bManualReset
0x18002a2b9  xor     ecx, ecx; lpEventAttributes
0x18002a2bb  call    cs:__imp_CreateEventW
0x18002a2c1  mov     [rdi+638h], rax
0x18002a2c8  test    rax, rax
0x18002a2cb  jnz     short loc_18002A2EB
0x18002a2cd  call    cs:__imp_GetLastError
0x18002a2d3  mov     ebx, eax
0x18002a2d5  test    eax, eax
0x18002a2d7  jle     loc_18002A3FF
0x18002a2dd  movzx   ebx, ax
0x18002a2e0  or      ebx, 80070000h
0x18002a2e6  jmp     loc_18002A3FF
0x18002a2eb  xor     r9d, r9d; lpName
0x18002a2ee  xor     r8d, r8d; bInitialState
0x18002a2f1  xor     ecx, ecx; lpEventAttributes
0x18002a2f3  lea     edx, [r9+1]; bManualReset
0x18002a2f7  call    cs:__imp_CreateEventW
0x18002a2fd  mov     [rdi+658h], rax
0x18002a304  test    rax, rax
0x18002a307  jz      short loc_18002A2CD
0x18002a309  mov     rcx, rdi; this
0x18002a30c  call    ?CreateCertUpdateEvent@CCertManager@@AEAAJXZ; CCertManager::CreateCertUpdateEvent(void)
0x18002a311  mov     rcx, rdi; this
0x18002a314  call    ?GetComputerFQDN@CCertManager@@AEAAJXZ; CCertManager::GetComputerFQDN(void)
0x18002a319  mov     ebx, eax
0x18002a31b  test    eax, eax
0x18002a31d  jns     short loc_18002A33F
0x18002a31f  mov     r8d, eax
0x18002a322  lea     rdx, aGetcomputerfqd; "GetComputerFQDN failed: 0x%x in %s"
0x18002a329  lea     r9, aCcertmanagerIn; "CCertManager::Initialize"
0x18002a330  mov     ecx, 8; int
0x18002a335  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a33a  jmp     loc_18002A3FF
0x18002a33f  mov     rcx, [rdi+658h]; hEvent
0x18002a346  mov     edx, 1; bMachine
0x18002a34b  call    cs:__imp_RegisterGPNotification
0x18002a351  test    eax, eax
0x18002a353  jz      short loc_18002A361
0x18002a355  mov     dword ptr [rdi+660h], 1
0x18002a35f  jmp     short loc_18002A37B
0x18002a361  call    cs:__imp_GetLastError
0x18002a367  lea     rdx, aRegistergpnoti_2; "RegisterGPNotification() failed: %d"
0x18002a36e  mov     ecx, 8; int
0x18002a373  mov     r8d, eax
0x18002a376  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a37b  lea     r8, [rdi+680h]; phModule
0x18002a382  mov     ecx, 6; dwFlags
0x18002a387  lea     rdx, ?staticCertUpdateThread@CCertManager@@CAKPEAX@Z; lpModuleName
0x18002a38e  call    cs:__imp_GetModuleHandleExW
0x18002a394  test    eax, eax
0x18002a396  jz      loc_18002A2CD
0x18002a39c  mov     rcx, rdi; this
0x18002a39f  call    ?ReadDCConnectTimeoutFromReg@CCertManager@@AEAAXXZ; CCertManager::ReadDCConnectTimeoutFromReg(void)
0x18002a3a4  mov     r9, rdi; lpParameter
0x18002a3a7  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18002a3b0  lea     r8, ?staticCertUpdateThread@CCertManager@@CAKPEAX@Z; lpStartAddress
0x18002a3b7  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18002a3bf  xor     edx, edx; dwStackSize
0x18002a3c1  xor     ecx, ecx; lpThreadAttributes
0x18002a3c3  call    cs:__imp_CreateThread
0x18002a3c9  mov     [rdi+648h], rax
0x18002a3d0  test    rax, rax
0x18002a3d3  jnz     short loc_18002A3FD
0x18002a3d5  call    cs:__imp_GetLastError
0x18002a3db  mov     ebx, eax
0x18002a3dd  test    eax, eax
0x18002a3df  jle     short loc_18002A3EA
0x18002a3e1  movzx   ebx, ax
0x18002a3e4  or      ebx, 80070000h
0x18002a3ea  test    ebx, ebx
0x18002a3ec  jns     short loc_18002A3FF
0x18002a3ee  mov     r8d, ebx
0x18002a3f1  lea     rdx, aStartcertupdat; "StartCertUpdateThread failed: 0x%x in %"...
0x18002a3f8  jmp     loc_18002A329
0x18002a3fd  xor     ebx, ebx
0x18002a3ff  mov     eax, ebx
0x18002a401  mov     rbx, [rsp+38h+arg_0]
0x18002a406  add     rsp, 30h
0x18002a40a  pop     rdi
0x18002a40b  retn
```
