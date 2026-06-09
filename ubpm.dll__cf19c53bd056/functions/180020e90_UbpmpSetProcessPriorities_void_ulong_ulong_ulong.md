# UbpmpSetProcessPriorities(void *,ulong,ulong,ulong)

- ea: `0x180020e90`
- end: `0x18002104b`
- name: `?UbpmpSetProcessPriorities@@YAXPEAXKKK@Z`
- size: `443`
- prototype: `void __fastcall(HANDLE Process, DWORD dwPriorityClass, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180021060`

## callees

- `0x180020e90`
- `0x18003c764`
- `0x18003c830`

## import_xrefs

- `ntdll!NtSetInformationProcess` at `0x180020ec7`
- `ntdll!NtSetInformationProcess` at `0x180020f78`
- `ntdll!NtSetInformationProcess` at `0x180020ec7`
- `ntdll!NtSetInformationProcess` at `0x180020f78`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020f39`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020fa5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020fed`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002101b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020f39`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020fa5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020fed`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002101b`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180020f12`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180020f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f2e`

## pseudocode

```c
void __fastcall UbpmpSetProcessPriorities(HANDLE Process, DWORD dwPriorityClass, unsigned int a3, unsigned int a4)
{
  NTSTATUS v8; // ebx
  DWORD LastError; // ebx
  DWORD v10; // eax
  __int64 v11; // r8
  NTSTATUS v12; // ebx
  DWORD v13; // eax
  __int64 v14; // r8
  DWORD ProcessId; // eax
  __int64 v16; // r8
  DWORD v17; // eax
  __int64 v18; // r8
  __int64 v19; // [rsp+28h] [rbp-40h]
  NTSTATUS v20; // [rsp+28h] [rbp-40h]
  unsigned int ProcessInformation; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v22; // [rsp+80h] [rbp+18h] BYREF

  v22 = a3;
  ProcessInformation = 0;
  v8 = NtSetInformationProcess(Process, ProcessIoPriority, &v22, 4u);
  if ( v8 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    ProcessId = GetProcessId(Process);
    v20 = v8;
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, v16, a3, ProcessId, v20);
  }
  if ( a4 )
  {
    ProcessInformation = a4;
    v12 = NtSetInformationProcess(Process, ProcessPagePriority, &ProcessInformation, 4u);
    if ( v12 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = GetProcessId(Process);
      LODWORD(v19) = v12;
      WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, v14, a4, v13, v19);
    }
  }
  if ( dwPriorityClass && !SetPriorityClass(Process, dwPriorityClass) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v10 = GetProcessId(Process);
      LODWORD(v19) = LastError;
      WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, v11, a4, v10, v19);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v17 = GetProcessId(Process);
    WPP_SF_dddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, v18, v17, dwPriorityClass, a3, a4);
  }
}

```

## disassembly

```asm
0x180020e90  mov     rax, rsp
0x180020e93  mov     [rax+8], rbx
0x180020e97  push    rbp
0x180020e98  push    rsi
0x180020e99  push    rdi
0x180020e9a  push    r14
0x180020e9c  push    r15
0x180020e9e  sub     rsp, 40h
0x180020ea2  mov     esi, r9d
0x180020ea5  mov     [rax+18h], r8d
0x180020ea9  mov     r14d, r8d
0x180020eac  mov     dword ptr [rax+10h], 0
0x180020eb3  mov     edi, edx
0x180020eb5  lea     r8, [rax+18h]; ProcessInformation
0x180020eb9  mov     r9d, 4; ProcessInformationLength
0x180020ebf  mov     edx, 21h ; '!'; ProcessInformationClass
0x180020ec4  mov     rbp, rcx
0x180020ec7  call    cs:__imp_NtSetInformationProcess
0x180020ecd  lea     r15, WPP_GLOBAL_Control
0x180020ed4  mov     ebx, eax
0x180020ed6  test    eax, eax
0x180020ed8  js      loc_180020FD0
0x180020ede  test    esi, esi
0x180020ee0  jnz     short loc_180020F61
0x180020ee2  test    edi, edi
0x180020ee4  jnz     short loc_180020F0D
0x180020ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180020eed  cmp     rcx, r15
0x180020ef0  jz      short loc_180020EFC
0x180020ef2  test    byte ptr [rcx+1Ch], 80h
0x180020ef6  jnz     loc_180021018
0x180020efc  mov     rbx, [rsp+68h+arg_0]
0x180020f01  add     rsp, 40h
0x180020f05  pop     r15
0x180020f07  pop     r14
0x180020f09  pop     rdi
0x180020f0a  pop     rsi
0x180020f0b  pop     rbp
0x180020f0c  retn
0x180020f0d  mov     edx, edi; dwPriorityClass
0x180020f0f  mov     rcx, rbp; hProcess
0x180020f12  call    cs:__imp_SetPriorityClass
0x180020f18  test    eax, eax
0x180020f1a  jnz     short loc_180020EE6
0x180020f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f23  cmp     rcx, r15
0x180020f26  jz      short loc_180020EFC
0x180020f28  test    byte ptr [rcx+1Ch], 1
0x180020f2c  jz      short loc_180020EE6
0x180020f2e  call    cs:__imp_GetLastError
0x180020f34  mov     rcx, rbp; Process
0x180020f37  mov     ebx, eax
0x180020f39  call    cs:__imp_GetProcessId
0x180020f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f46  mov     edx, 0C7h
0x180020f4b  mov     dword ptr [rsp+68h+var_40], ebx
0x180020f4f  mov     r9d, esi
0x180020f52  mov     [rsp+68h+var_48], eax
0x180020f56  mov     rcx, [rcx+10h]
0x180020f5a  call    WPP_SF_ddd
0x180020f5f  jmp     short loc_180020EE6
0x180020f61  mov     r9d, 4; ProcessInformationLength
0x180020f67  mov     [rsp+68h+ProcessInformation], esi
0x180020f6b  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x180020f70  mov     edx, 27h ; '''; ProcessInformationClass
0x180020f75  mov     rcx, rbp; ProcessHandle
0x180020f78  call    cs:__imp_NtSetInformationProcess
0x180020f7e  mov     ebx, eax
0x180020f80  test    eax, eax
0x180020f82  jns     loc_180020EE2
0x180020f88  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f8f  cmp     rcx, r15
0x180020f92  jz      loc_180020EE2
0x180020f98  test    byte ptr [rcx+1Ch], 1
0x180020f9c  jz      loc_180020EE2
0x180020fa2  mov     rcx, rbp; Process
0x180020fa5  call    cs:__imp_GetProcessId
0x180020fab  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fb2  mov     edx, 0C6h
0x180020fb7  mov     dword ptr [rsp+68h+var_40], ebx
0x180020fbb  mov     r9d, esi
0x180020fbe  mov     [rsp+68h+var_48], eax
0x180020fc2  mov     rcx, [rcx+10h]
0x180020fc6  call    WPP_SF_ddd
0x180020fcb  jmp     loc_180020EE2
0x180020fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fd7  cmp     rcx, r15
0x180020fda  jz      loc_180020EDE
0x180020fe0  test    byte ptr [rcx+1Ch], 1
0x180020fe4  jz      loc_180020EDE
0x180020fea  mov     rcx, rbp; Process
0x180020fed  call    cs:__imp_GetProcessId
0x180020ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ffa  mov     edx, 0C5h
0x180020fff  mov     dword ptr [rsp+68h+var_40], ebx
0x180021003  mov     r9d, r14d
0x180021006  mov     [rsp+68h+var_48], eax
0x18002100a  mov     rcx, [rcx+10h]
0x18002100e  call    WPP_SF_ddd
0x180021013  jmp     loc_180020EDE
0x180021018  mov     rcx, rbp; Process
0x18002101b  call    cs:__imp_GetProcessId
0x180021021  mov     rcx, cs:WPP_GLOBAL_Control
0x180021028  mov     edx, 0C8h
0x18002102d  mov     [rsp+68h+var_38], esi
0x180021031  mov     r9d, eax
0x180021034  mov     dword ptr [rsp+68h+var_40], r14d
0x180021039  mov     [rsp+68h+var_48], edi
0x18002103d  mov     rcx, [rcx+10h]
0x180021041  call    WPP_SF_dddd
0x180021046  jmp     loc_180020EFC
```
