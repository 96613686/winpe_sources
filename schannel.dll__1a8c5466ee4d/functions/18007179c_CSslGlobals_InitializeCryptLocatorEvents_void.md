# CSslGlobals::InitializeCryptLocatorEvents(void)

- ea: `0x18007179c`
- end: `0x18007184e`
- name: `?InitializeCryptLocatorEvents@CSslGlobals@@SAKXZ`
- size: `178`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025c38`

## callees

- `0x180021da8`
- `0x18007164c`
- `0x18007179c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800717be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800717be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071804`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800717ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800717f2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800717ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800717f2`

## pseudocode

```c
__int64 CSslGlobals::InitializeCryptLocatorEvents(void)
{
  DWORD LastError; // ebx
  CCipherMill *v1; // rcx
  __int64 v2; // rdx

  CSslGlobals::m_hImplicitCertChangeEvent = CreateEventA(0, 0, 0, 0);
  if ( CSslGlobals::m_hImplicitCertChangeEvent )
  {
    LastError = 0;
    CSslGlobals::m_hImplicitIssersChangeEvent = CreateEventA(0, 0, 0, 0);
    if ( CSslGlobals::m_hImplicitIssersChangeEvent )
      return LastError;
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 12;
      goto LABEL_9;
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 11;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_44759acc45ff36e340102a6f38473a52_Traceguids, LastError);
    }
  }
  if ( LastError )
    CSslGlobals::CleanupCryptLocatorEvents();
  return LastError;
}

```

## disassembly

```asm
0x18007179c  push    rbx
0x18007179e  sub     rsp, 20h
0x1800717a2  xor     r9d, r9d; lpName
0x1800717a5  xor     r8d, r8d; bInitialState
0x1800717a8  xor     edx, edx; bManualReset
0x1800717aa  xor     ecx, ecx; lpEventAttributes
0x1800717ac  call    cs:__imp_CreateEventA
0x1800717b2  mov     cs:?m_hImplicitCertChangeEvent@CSslGlobals@@2PEAXEA, rax; void * CSslGlobals::m_hImplicitCertChangeEvent
0x1800717b9  test    rax, rax
0x1800717bc  jnz     short loc_1800717E6
0x1800717be  call    cs:__imp_GetLastError
0x1800717c4  mov     ebx, eax
0x1800717c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800717cd  lea     rax, WPP_GLOBAL_Control
0x1800717d4  cmp     rcx, rax
0x1800717d7  jz      short loc_18007183D
0x1800717d9  test    byte ptr [rcx+1Ch], 1
0x1800717dd  jz      short loc_18007183D
0x1800717df  mov     edx, 0Bh
0x1800717e4  jmp     short loc_18007182A
0x1800717e6  xor     r9d, r9d; lpName
0x1800717e9  xor     r8d, r8d; bInitialState
0x1800717ec  xor     edx, edx; bManualReset
0x1800717ee  xor     ecx, ecx; lpEventAttributes
0x1800717f0  xor     ebx, ebx
0x1800717f2  call    cs:__imp_CreateEventA
0x1800717f8  mov     cs:?m_hImplicitIssersChangeEvent@CSslGlobals@@2PEAXEA, rax; void * CSslGlobals::m_hImplicitIssersChangeEvent
0x1800717ff  test    rax, rax
0x180071802  jnz     short loc_180071846
0x180071804  call    cs:__imp_GetLastError
0x18007180a  mov     ebx, eax
0x18007180c  mov     rcx, cs:WPP_GLOBAL_Control
0x180071813  lea     rax, WPP_GLOBAL_Control
0x18007181a  cmp     rcx, rax
0x18007181d  jz      short loc_18007183D
0x18007181f  test    byte ptr [rcx+1Ch], 1
0x180071823  jz      short loc_18007183D
0x180071825  mov     edx, 0Ch
0x18007182a  mov     rcx, [rcx+10h]
0x18007182e  lea     r8, WPP_44759acc45ff36e340102a6f38473a52_Traceguids
0x180071835  mov     r9d, ebx
0x180071838  call    WPP_SF_d
0x18007183d  test    ebx, ebx
0x18007183f  jz      short loc_180071846
0x180071841  call    ?CleanupCryptLocatorEvents@CSslGlobals@@SAXXZ; CSslGlobals::CleanupCryptLocatorEvents(void)
0x180071846  mov     eax, ebx
0x180071848  add     rsp, 20h
0x18007184c  pop     rbx
0x18007184d  retn
```
