# CPxeRogueDetection::Initialize(void *)

- ea: `0x18000c494`
- end: `0x18000c633`
- name: `?Initialize@CPxeRogueDetection@@QEAAKPEAX@Z`
- size: `415`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002bc0`

## callees

- `0x18000c494`
- `0x18000c63c`
- `0x18000d13c`
- `0x18000f8b8`
- `0x180010f8c`
- `0x180011068`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c5b8`
- `KERNEL32!GetLastError` at `0x18000c5b8`
- `KERNEL32!EnterCriticalSection` at `0x18000c4a9`
- `KERNEL32!EnterCriticalSection` at `0x18000c4a9`
- `KERNEL32!LeaveCriticalSection` at `0x18000c614`
- `KERNEL32!LeaveCriticalSection` at `0x18000c614`
- `KERNEL32!CreateEventW` at `0x18000c510`
- `KERNEL32!CreateEventW` at `0x18000c544`
- `KERNEL32!CreateEventW` at `0x18000c510`
- `KERNEL32!CreateEventW` at `0x18000c544`
- `KERNEL32!CreateThread` at `0x18000c58e`
- `KERNEL32!CreateThread` at `0x18000c58e`
- `WdsCommonLib!?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z` at `0x18000c4de`
- `WdsCommonLib!?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z` at `0x18000c4de`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000c5ee`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000c5ee`

## pseudocode

```c
__int64 __fastcall CPxeRogueDetection::Initialize(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _RTL_CRITICAL_SECTION_DEBUG *a2)
{
  unsigned int Parameters; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  DWORD LastError; // ebx
  unsigned int HostName; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  HANDLE EventW; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  HANDLE v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  HANDLE Thread; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  int v21; // [rsp+20h] [rbp-18h]

  EnterCriticalSection(lpCriticalSection);
  Parameters = CPxeRogueDetection::ReadParameters(lpCriticalSection);
  LastError = ElValidateWin32_4(Parameters, v5, v6, 185);
  if ( !LastError )
  {
    HostName = GetHostName(ComputerNameDnsFullyQualified, (unsigned __int16 **)&lpCriticalSection[6]);
    LastError = ElValidateWin32_4(HostName, v9, v10, 193);
    if ( !LastError )
    {
      lpCriticalSection[1].DebugInfo = a2;
      EventW = CreateEventW(0, 1, 0, 0);
      lpCriticalSection[6].OwningThread = EventW;
      if ( (unsigned int)ElValidateGleTrue_0(EventW == 0, v12, v13, 206)
        || (v14 = CreateEventW(0, 0, 0, 0),
            lpCriticalSection[6].LockSemaphore = v14,
            (unsigned int)ElValidateGleTrue_0(v14 == 0, v15, v16, 216))
        || (CPxeRogueDetection::InitializeDhcpApiAvailability((CPxeRogueDetection *)lpCriticalSection),
            Thread = CreateThread(0, 0, CPxeRogueDetection::_RogueThread, lpCriticalSection, LastError & v21, 0),
            *(_QWORD *)&lpCriticalSection[6].LockCount = Thread,
            (unsigned int)ElValidateGleTrue_0(Thread == 0, v18, v19, 236)) )
      {
        LastError = GetLastError();
      }
    }
  }
  lpCriticalSection[1].LockCount = LastError != 0;
  if ( LastError )
  {
    CEventLog::Log((CEventLog *)qword_18001CC40, 0xC1070300, 1);
  }
  else
  {
    if ( LODWORD(lpCriticalSection[1].LockSemaphore) )
      CPxeRogueDetection::SetAuthState((CPxeRogueDetection *)lpCriticalSection, 1);
    LastError = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x18000c494  mov     [rsp+arg_0], rbx
0x18000c499  mov     [rsp+arg_8], rsi
0x18000c49e  push    rdi
0x18000c49f  sub     rsp, 30h
0x18000c4a3  mov     rsi, rdx
0x18000c4a6  mov     rdi, rcx
0x18000c4a9  call    cs:__imp_EnterCriticalSection
0x18000c4b0  nop     dword ptr [rax+rax+00h]
0x18000c4b5  mov     rcx, rdi; lpCriticalSection
0x18000c4b8  call    ?ReadParameters@CPxeRogueDetection@@AEAAKXZ; CPxeRogueDetection::ReadParameters(void)
0x18000c4bd  mov     ecx, eax
0x18000c4bf  mov     r9d, 0B9h
0x18000c4c5  call    ElValidateWin32_4
0x18000c4ca  mov     ebx, eax
0x18000c4cc  test    eax, eax
0x18000c4ce  jnz     loc_18000C5C6
0x18000c4d4  lea     rdx, [rdi+0F0h]
0x18000c4db  lea     ecx, [rax+3]
0x18000c4de  call    cs:__imp_?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18000c4e5  nop     dword ptr [rax+rax+00h]
0x18000c4ea  mov     ecx, eax
0x18000c4ec  mov     r9d, 0C1h
0x18000c4f2  call    ElValidateWin32_4
0x18000c4f7  mov     ebx, eax
0x18000c4f9  test    eax, eax
0x18000c4fb  jnz     loc_18000C5C6
0x18000c501  xor     r9d, r9d; lpName
0x18000c504  mov     [rdi+28h], rsi
0x18000c508  xor     r8d, r8d; bInitialState
0x18000c50b  lea     edx, [rax+1]; bManualReset
0x18000c50e  xor     ecx, ecx; lpEventAttributes
0x18000c510  call    cs:__imp_CreateEventW
0x18000c517  nop     dword ptr [rax+rax+00h]
0x18000c51c  xor     ecx, ecx
0x18000c51e  mov     r9d, 0CEh
0x18000c524  test    rax, rax
0x18000c527  mov     [rdi+100h], rax
0x18000c52e  setz    cl
0x18000c531  call    ElValidateGleTrue_0
0x18000c536  test    eax, eax
0x18000c538  jnz     short loc_18000C5B8
0x18000c53a  xor     r9d, r9d; lpName
0x18000c53d  xor     r8d, r8d; bInitialState
0x18000c540  xor     edx, edx; bManualReset
0x18000c542  xor     ecx, ecx; lpEventAttributes
0x18000c544  call    cs:__imp_CreateEventW
0x18000c54b  nop     dword ptr [rax+rax+00h]
0x18000c550  xor     ecx, ecx
0x18000c552  mov     r9d, 0D8h
0x18000c558  test    rax, rax
0x18000c55b  mov     [rdi+108h], rax
0x18000c562  setz    cl
0x18000c565  call    ElValidateGleTrue_0
0x18000c56a  test    eax, eax
0x18000c56c  jnz     short loc_18000C5B8
0x18000c56e  mov     rcx, rdi; this
0x18000c571  call    ?InitializeDhcpApiAvailability@CPxeRogueDetection@@AEAAXXZ; CPxeRogueDetection::InitializeDhcpApiAvailability(void)
0x18000c576  and     [rsp+38h+var_10], 0
0x18000c57c  lea     r8, ?_RogueThread@CPxeRogueDetection@@SAKPEAX@Z; lpStartAddress
0x18000c583  and     [rsp+38h+var_18], ebx
0x18000c587  mov     r9, rdi; lpParameter
0x18000c58a  xor     edx, edx; dwStackSize
0x18000c58c  xor     ecx, ecx; lpThreadAttributes
0x18000c58e  call    cs:__imp_CreateThread
0x18000c595  nop     dword ptr [rax+rax+00h]
0x18000c59a  xor     ecx, ecx
0x18000c59c  mov     r9d, 0ECh
0x18000c5a2  test    rax, rax
0x18000c5a5  mov     [rdi+0F8h], rax
0x18000c5ac  setz    cl
0x18000c5af  call    ElValidateGleTrue_0
0x18000c5b4  test    eax, eax
0x18000c5b6  jz      short loc_18000C5C6
0x18000c5b8  call    cs:__imp_GetLastError
0x18000c5bf  nop     dword ptr [rax+rax+00h]
0x18000c5c4  mov     ebx, eax
0x18000c5c6  xor     eax, eax
0x18000c5c8  test    ebx, ebx
0x18000c5ca  setnz   al
0x18000c5cd  mov     [rdi+30h], eax
0x18000c5d0  test    ebx, ebx
0x18000c5d2  jz      short loc_18000C5FC
0x18000c5d4  mov     r9d, 5
0x18000c5da  mov     [rsp+38h+var_18], ebx
0x18000c5de  mov     edx, 0C1070300h
0x18000c5e3  lea     rcx, qword_18001CC40
0x18000c5ea  lea     r8d, [r9-4]
0x18000c5ee  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000c5f5  nop     dword ptr [rax+rax+00h]
0x18000c5fa  jmp     short loc_18000C611
0x18000c5fc  cmp     dword ptr [rdi+40h], 0
0x18000c600  jz      short loc_18000C60F
0x18000c602  mov     edx, 1; int
0x18000c607  mov     rcx, rdi; this
0x18000c60a  call    ?SetAuthState@CPxeRogueDetection@@AEAAXH@Z; CPxeRogueDetection::SetAuthState(int)
0x18000c60f  xor     ebx, ebx
0x18000c611  mov     rcx, rdi; lpCriticalSection
0x18000c614  call    cs:__imp_LeaveCriticalSection
0x18000c61b  nop     dword ptr [rax+rax+00h]
0x18000c620  mov     rsi, [rsp+38h+arg_8]
0x18000c625  mov     eax, ebx
0x18000c627  mov     rbx, [rsp+38h+arg_0]
0x18000c62c  add     rsp, 30h
0x18000c630  pop     rdi
0x18000c631  retn
```
