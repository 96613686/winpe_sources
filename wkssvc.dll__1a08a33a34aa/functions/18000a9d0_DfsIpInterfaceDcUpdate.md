# DfsIpInterfaceDcUpdate

- ea: `0x18000a9d0`
- end: `0x18000aba8`
- name: `DfsIpInterfaceDcUpdate`
- size: `472`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_IPINTERFACE_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000a9d0`
- `0x18000abb0`
- `0x18000b290`
- `0x18001fbd0`
- `0x1800204f6`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTable` at `0x18000ab97`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000ab97`
- `ntdll!RtlInsertElementGenericTable` at `0x18000ab45`
- `ntdll!RtlInsertElementGenericTable` at `0x18000ab45`
- `ntdll!RtlLookupElementGenericTable` at `0x18000aa99`
- `ntdll!RtlLookupElementGenericTable` at `0x18000aa99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aac7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aac7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ab01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000aa73`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000aa73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab72`
- `IPHLPAPI!GetIfEntry2` at `0x18000aa34`
- `IPHLPAPI!GetIfEntry2` at `0x18000aa34`

## pseudocode

```c
void __fastcall DfsIpInterfaceDcUpdate(
        PVOID CallerContext,
        PMIB_IPINTERFACE_ROW Row,
        MIB_NOTIFICATION_TYPE NotificationType)
{
  NET_LUID v5; // rax
  _DWORD *v6; // rax
  _DWORD *v7; // rcx
  int v8; // edx
  IF_OPER_STATUS OperStatus; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  NET_LUID Buffer; // [rsp+20h] [rbp-578h] BYREF
  __int64 v13; // [rsp+28h] [rbp-570h]
  _MIB_IF_ROW2 Rowa; // [rsp+30h] [rbp-568h] BYREF

  memset_0(&Rowa.InterfaceIndex, 0, 0x540u);
  v13 = 0;
  if ( Row )
  {
    v5.Value = (ULONG64)Row->InterfaceLuid;
    Buffer.Value = v5.Value;
    if ( NotificationType == MibParameterNotification )
    {
      Rowa.InterfaceLuid = v5;
      if ( GetIfEntry2(&Rowa) )
        return;
      EnterCriticalSection(&WsDfsNetLuidTableCriticalSection);
      if ( ((WsGlobalData.dwCurrentState - 1) & 0xFFFFFFFD) != 0
        && WaitForSingleObject(hHandle, 0)
        && !WsIsTerminationHandlerRunning )
      {
        v6 = RtlLookupElementGenericTable(WsDfsNetLuidTable, &Buffer);
        v7 = v6;
        if ( v6 )
        {
          v8 = v6[2];
          OperStatus = Rowa.OperStatus;
          if ( v8 != Rowa.OperStatus )
          {
            v7[2] = Rowa.OperStatus;
            OperStatus = Rowa.OperStatus;
          }
        }
        else
        {
          LODWORD(v13) = Rowa.OperStatus;
          RtlInsertElementGenericTable(WsDfsNetLuidTable, &Buffer, 0x10u, 0);
          OperStatus = Rowa.OperStatus;
          v8 = 2;
        }
        if ( v8 != 1 && OperStatus == IfOperStatusUp )
        {
          LeaveCriticalSection(&WsDfsNetLuidTableCriticalSection);
          DfsHandleServiceEvent(3);
          return;
        }
      }
      goto LABEL_11;
    }
    if ( NotificationType == MibDeleteInstance )
    {
      EnterCriticalSection(&WsDfsNetLuidTableCriticalSection);
      if ( !(unsigned int)WsIsTerminating(v11, v10) )
        RtlDeleteElementGenericTable(WsDfsNetLuidTable, &Buffer);
LABEL_11:
      LeaveCriticalSection(&WsDfsNetLuidTableCriticalSection);
    }
  }
}

```

## disassembly

```asm
0x18000a9d0  mov     [rsp+arg_0], rbx
0x18000a9d5  push    rdi
0x18000a9d6  sub     rsp, 590h
0x18000a9dd  mov     rax, cs:__security_cookie
0x18000a9e4  xor     rax, rsp
0x18000a9e7  mov     [rsp+598h+var_18], rax
0x18000a9ef  mov     edi, r8d
0x18000a9f2  lea     rcx, [rsp+598h+Row.InterfaceIndex]; void *
0x18000a9f7  mov     rbx, rdx
0x18000a9fa  mov     r8d, 540h; Size
0x18000aa00  xor     edx, edx; Val
0x18000aa02  call    memset_0
0x18000aa07  mov     [rsp+598h+var_570], 0
0x18000aa10  test    rbx, rbx
0x18000aa13  jz      loc_18000AAD3
0x18000aa19  mov     rax, [rbx+8]
0x18000aa1d  mov     [rsp+598h+Buffer], rax
0x18000aa22  test    edi, edi
0x18000aa24  jnz     loc_18000AB62
0x18000aa2a  lea     rcx, [rsp+598h+Row]; Row
0x18000aa2f  mov     qword ptr [rsp+598h+Row.InterfaceLuid], rax
0x18000aa34  call    cs:__imp_GetIfEntry2
0x18000aa3b  nop     dword ptr [rax+rax+00h]
0x18000aa40  test    eax, eax
0x18000aa42  jnz     loc_18000AAD3
0x18000aa48  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000aa4f  call    cs:__imp_EnterCriticalSection
0x18000aa56  nop     dword ptr [rax+rax+00h]
0x18000aa5b  mov     eax, cs:WsGlobalData.dwCurrentState
0x18000aa61  dec     eax
0x18000aa63  test    eax, 0FFFFFFFDh
0x18000aa68  jz      short loc_18000AAC0
0x18000aa6a  mov     rcx, cs:hHandle; hHandle
0x18000aa71  xor     edx, edx; dwMilliseconds
0x18000aa73  call    cs:__imp_WaitForSingleObject
0x18000aa7a  nop     dword ptr [rax+rax+00h]
0x18000aa7f  test    eax, eax
0x18000aa81  jz      short loc_18000AAC0
0x18000aa83  mov     eax, cs:WsIsTerminationHandlerRunning
0x18000aa89  test    eax, eax
0x18000aa8b  jnz     short loc_18000AAC0
0x18000aa8d  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18000aa94  lea     rdx, [rsp+598h+Buffer]; Buffer
0x18000aa99  call    cs:__imp_RtlLookupElementGenericTable
0x18000aaa0  nop     dword ptr [rax+rax+00h]
0x18000aaa5  mov     rcx, rax
0x18000aaa8  test    rax, rax
0x18000aaab  jz      short loc_18000AB25
0x18000aaad  mov     edx, [rax+8]
0x18000aab0  mov     eax, [rsp+598h+Row.OperStatus]
0x18000aab7  cmp     edx, eax
0x18000aab9  jnz     short loc_18000AB19
0x18000aabb  cmp     edx, 1
0x18000aabe  jnz     short loc_18000AAF5
0x18000aac0  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000aac7  call    cs:__imp_LeaveCriticalSection
0x18000aace  nop     dword ptr [rax+rax+00h]
0x18000aad3  mov     rcx, [rsp+598h+var_18]
0x18000aadb  xor     rcx, rsp; StackCookie
0x18000aade  call    __security_check_cookie
0x18000aae3  mov     rbx, [rsp+598h+arg_0]
0x18000aaeb  add     rsp, 590h
0x18000aaf2  pop     rdi
0x18000aaf3  retn
0x18000aaf5  cmp     eax, 1
0x18000aaf8  jnz     short loc_18000AAC0
0x18000aafa  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000ab01  call    cs:__imp_LeaveCriticalSection
0x18000ab08  nop     dword ptr [rax+rax+00h]
0x18000ab0d  mov     ecx, 3
0x18000ab12  call    DfsHandleServiceEvent
0x18000ab17  jmp     short loc_18000AAD3
0x18000ab19  mov     [rcx+8], eax
0x18000ab1c  mov     eax, [rsp+598h+Row.OperStatus]
0x18000ab23  jmp     short loc_18000AABB
0x18000ab25  mov     eax, [rsp+598h+Row.OperStatus]
0x18000ab2c  lea     rdx, [rsp+598h+Buffer]; Buffer
0x18000ab31  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18000ab38  xor     r9d, r9d; NewElement
0x18000ab3b  mov     r8d, 10h; BufferSize
0x18000ab41  mov     dword ptr [rsp+598h+var_570], eax
0x18000ab45  call    cs:__imp_RtlInsertElementGenericTable
0x18000ab4c  nop     dword ptr [rax+rax+00h]
0x18000ab51  mov     eax, [rsp+598h+Row.OperStatus]
0x18000ab58  mov     edx, 2
0x18000ab5d  jmp     loc_18000AABB
0x18000ab62  cmp     edi, 2
0x18000ab65  jnz     loc_18000AAD3
0x18000ab6b  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000ab72  call    cs:__imp_EnterCriticalSection
0x18000ab79  nop     dword ptr [rax+rax+00h]
0x18000ab7e  call    WsIsTerminating
0x18000ab83  test    eax, eax
0x18000ab85  jnz     loc_18000AAC0
0x18000ab8b  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18000ab92  lea     rdx, [rsp+598h+Buffer]; Buffer
0x18000ab97  call    cs:__imp_RtlDeleteElementGenericTable
0x18000ab9e  nop     dword ptr [rax+rax+00h]
0x18000aba3  jmp     loc_18000AAC0
```
