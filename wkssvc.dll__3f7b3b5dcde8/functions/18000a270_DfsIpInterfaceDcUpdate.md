# DfsIpInterfaceDcUpdate

- ea: `0x18000a270`
- end: `0x18000a40d`
- name: `DfsIpInterfaceDcUpdate`
- size: `413`
- prototype: `void __fastcall(PVOID CallerContext, PMIB_IPINTERFACE_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000a270`
- `0x18000a420`
- `0x18000a600`
- `0x18001e420`
- `0x18001ed46`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTable` at `0x18000a402`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000a402`
- `ntdll!RtlInsertElementGenericTable` at `0x18000a3bc`
- `ntdll!RtlInsertElementGenericTable` at `0x18000a3bc`
- `ntdll!RtlLookupElementGenericTable` at `0x18000a323`
- `ntdll!RtlLookupElementGenericTable` at `0x18000a323`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a34b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a37e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a34b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a37e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a303`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a303`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a2e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a3e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a2e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a3e3`
- `IPHLPAPI!GetIfEntry2` at `0x18000a2d4`
- `IPHLPAPI!GetIfEntry2` at `0x18000a2d4`

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
0x18000a270  mov     [rsp+arg_0], rbx
0x18000a275  push    rdi
0x18000a276  sub     rsp, 590h
0x18000a27d  mov     rax, cs:__security_cookie
0x18000a284  xor     rax, rsp
0x18000a287  mov     [rsp+598h+var_18], rax
0x18000a28f  mov     edi, r8d
0x18000a292  lea     rcx, [rsp+598h+Row.InterfaceIndex]; void *
0x18000a297  mov     rbx, rdx
0x18000a29a  mov     r8d, 540h; Size
0x18000a2a0  xor     edx, edx; Val
0x18000a2a2  call    memset_0
0x18000a2a7  mov     [rsp+598h+var_570], 0
0x18000a2b0  test    rbx, rbx
0x18000a2b3  jz      loc_18000A351
0x18000a2b9  mov     rax, [rbx+8]
0x18000a2bd  mov     [rsp+598h+Buffer], rax
0x18000a2c2  test    edi, edi
0x18000a2c4  jnz     loc_18000A3D3
0x18000a2ca  lea     rcx, [rsp+598h+Row]; Row
0x18000a2cf  mov     qword ptr [rsp+598h+Row.InterfaceLuid], rax
0x18000a2d4  call    cs:__imp_GetIfEntry2
0x18000a2da  test    eax, eax
0x18000a2dc  jnz     short loc_18000A351
0x18000a2de  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000a2e5  call    cs:__imp_EnterCriticalSection
0x18000a2eb  mov     eax, cs:WsGlobalData.dwCurrentState
0x18000a2f1  dec     eax
0x18000a2f3  test    eax, 0FFFFFFFDh
0x18000a2f8  jz      short loc_18000A344
0x18000a2fa  mov     rcx, cs:hHandle; hHandle
0x18000a301  xor     edx, edx; dwMilliseconds
0x18000a303  call    cs:__imp_WaitForSingleObject
0x18000a309  test    eax, eax
0x18000a30b  jz      short loc_18000A344
0x18000a30d  mov     eax, cs:WsIsTerminationHandlerRunning
0x18000a313  test    eax, eax
0x18000a315  jnz     short loc_18000A344
0x18000a317  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18000a31e  lea     rdx, [rsp+598h+Buffer]; Buffer
0x18000a323  call    cs:__imp_RtlLookupElementGenericTable
0x18000a329  mov     rcx, rax
0x18000a32c  test    rax, rax
0x18000a32f  jz      short loc_18000A39C
0x18000a331  mov     edx, [rax+8]
0x18000a334  mov     eax, [rsp+598h+Row.OperStatus]
0x18000a33b  cmp     edx, eax
0x18000a33d  jnz     short loc_18000A390
0x18000a33f  cmp     edx, 1
0x18000a342  jnz     short loc_18000A372
0x18000a344  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000a34b  call    cs:__imp_LeaveCriticalSection
0x18000a351  mov     rcx, [rsp+598h+var_18]
0x18000a359  xor     rcx, rsp; StackCookie
0x18000a35c  call    __security_check_cookie
0x18000a361  mov     rbx, [rsp+598h+arg_0]
0x18000a369  add     rsp, 590h
0x18000a370  pop     rdi
0x18000a371  retn
0x18000a372  cmp     eax, 1
0x18000a375  jnz     short loc_18000A344
0x18000a377  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000a37e  call    cs:__imp_LeaveCriticalSection
0x18000a384  mov     ecx, 3
0x18000a389  call    DfsHandleServiceEvent
0x18000a38e  jmp     short loc_18000A351
0x18000a390  mov     [rcx+8], eax
0x18000a393  mov     eax, [rsp+598h+Row.OperStatus]
0x18000a39a  jmp     short loc_18000A33F
0x18000a39c  mov     eax, [rsp+598h+Row.OperStatus]
0x18000a3a3  lea     rdx, [rsp+598h+Buffer]; Buffer
0x18000a3a8  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18000a3af  xor     r9d, r9d; NewElement
0x18000a3b2  mov     r8d, 10h; BufferSize
0x18000a3b8  mov     dword ptr [rsp+598h+var_570], eax
0x18000a3bc  call    cs:__imp_RtlInsertElementGenericTable
0x18000a3c2  mov     eax, [rsp+598h+Row.OperStatus]
0x18000a3c9  mov     edx, 2
0x18000a3ce  jmp     loc_18000A33F
0x18000a3d3  cmp     edi, 2
0x18000a3d6  jnz     loc_18000A351
0x18000a3dc  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18000a3e3  call    cs:__imp_EnterCriticalSection
0x18000a3e9  call    WsIsTerminating
0x18000a3ee  test    eax, eax
0x18000a3f0  jnz     loc_18000A344
0x18000a3f6  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18000a3fd  lea     rdx, [rsp+598h+Buffer]; Buffer
0x18000a402  call    cs:__imp_RtlDeleteElementGenericTable
0x18000a408  jmp     loc_18000A344
```
