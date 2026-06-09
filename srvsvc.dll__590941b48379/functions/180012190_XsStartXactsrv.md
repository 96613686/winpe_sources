# XsStartXactsrv

- ea: `0x180012190`
- end: `0x18001272d`
- name: `XsStartXactsrv`
- size: `1437`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015500`

## callees

- `0x180012190`
- `0x180020dc0`
- `0x180020de8`
- `0x18002fc4c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001260b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800125ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001260b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800121e1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800121e1`
- `ntdll!NtCreateEvent` at `0x180012448`
- `ntdll!NtCreateEvent` at `0x180012448`
- `ntdll!NtOpenFile` at `0x1800123ec`
- `ntdll!NtOpenFile` at `0x1800123ec`
- `ntdll!RtlNtStatusToDosError` at `0x180012705`
- `ntdll!RtlNtStatusToDosError` at `0x180012713`
- `ntdll!RtlNtStatusToDosError` at `0x180012705`
- `ntdll!RtlNtStatusToDosError` at `0x180012713`
- `ntdll!NtWaitForSingleObject` at `0x18001254d`
- `ntdll!NtWaitForSingleObject` at `0x18001254d`
- `ntdll!RtlInitAnsiString` at `0x1800124bb`
- `ntdll!RtlInitAnsiString` at `0x1800124bb`
- `ntdll!NtFsControlFile` at `0x180012506`
- `ntdll!NtFsControlFile` at `0x180012506`
- `ntdll!RtlInitUnicodeString` at `0x18001238b`
- `ntdll!RtlInitUnicodeString` at `0x18001238b`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180012244`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180012244`
- `RPCRT4!RpcEpRegisterW` at `0x180012307`
- `RPCRT4!RpcEpRegisterW` at `0x180012307`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800126c5`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800126c5`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180012203`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180012203`
- `RPCRT4!RpcBindingVectorFree` at `0x180012632`
- `RPCRT4!RpcBindingVectorFree` at `0x1800126a5`
- `RPCRT4!RpcBindingVectorFree` at `0x180012632`
- `RPCRT4!RpcBindingVectorFree` at `0x1800126a5`
- `RPCRT4!RpcEpUnregister` at `0x18001268d`
- `RPCRT4!RpcEpUnregister` at `0x18001268d`
- `RPCRT4!RpcServerInqBindings` at `0x1800122ad`
- `RPCRT4!RpcServerInqBindings` at `0x1800122ad`

## string_xrefs

- `0x1800122ee`: `XactSrv service`

## pseudocode

```c
ULONG XsStartXactsrv()
{
  RPC_STATUS v0; // eax
  int Status; // ebx
  char v2; // r12
  unsigned int v3; // esi
  char v4; // r15
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  RPC_STATUS v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // r14d
  NTSTATUS v11; // eax
  unsigned int v13; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-98h] BYREF
  struct _STRING InputBuffer; // [rsp+60h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-68h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+F0h] [rbp+8h] BYREF
  void *EventHandle; // [rsp+F8h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+18h] BYREF

  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  InputBuffer = 0;
  BindingVector = 0;
  FileHandle = 0;
  EventHandle = 0;
  InitializeCriticalSection(&SpoolerMutex);
  dword_18005E4AC = 1;
  v0 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, 0, 0);
  Status = 0;
  v2 = 0;
  v3 = 0;
  if ( v0 != 1740 )
    v3 = v0;
  if ( !v3 )
  {
    v3 = RpcServerRegisterIfEx(qword_18004D420, 0, 0, 0xB1u, 0x4D2u, XactSrvRpcSecurityCallback);
    if ( !v3 )
    {
      v4 = 1;
      v8 = RpcServerInqBindings(&BindingVector);
      v3 = v8;
      if ( v8 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_60;
        }
        v6 = 18;
      }
      else
      {
        v8 = RpcEpRegisterW(qword_18004D420, BindingVector, 0, (RPC_WSTR)L"XactSrv service");
        v3 = v8;
        if ( v8 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            goto LABEL_60;
          }
          v6 = 19;
        }
        else
        {
          v3 = 0;
          v2 = 1;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids);
          }
          RtlInitUnicodeString(&DestinationString, L"\\Device\\SrvNet");
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = &DestinationString;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Status = NtOpenFile(&FileHandle, 1u, &ObjectAttributes, &IoStatusBlock, 0, 0);
          if ( Status >= 0 )
            Status = IoStatusBlock.Status;
          if ( Status < 0 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              v6 = 21;
              v7 = (unsigned int)Status;
              goto LABEL_9;
            }
            goto LABEL_60;
          }
          v8 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
          Status = v8;
          if ( v8 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids);
            }
            RtlInitAnsiString(&InputBuffer, "ncalrpc");
            v8 = NtFsControlFile(
                   FileHandle,
                   EventHandle,
                   0,
                   0,
                   &IoStatusBlock,
                   0x144014u,
                   InputBuffer.Buffer,
                   InputBuffer.Length,
                   0,
                   0);
            Status = v8;
            if ( v8 >= 0 )
            {
              v9 = NtWaitForSingleObject(EventHandle, 0, 0);
              v10 = v9;
              if ( v9 >= 0 )
              {
                v5 = WPP_GLOBAL_Control;
              }
              else
              {
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    25,
                    WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids,
                    (unsigned int)v9);
                  v5 = WPP_GLOBAL_Control;
                }
                Status = v10;
              }
              v11 = IoStatusBlock.Status;
              if ( IoStatusBlock.Status < 0 )
              {
                if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) )
                {
                  WPP_SF_d(
                    v5[2],
                    26,
                    WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids,
                    (unsigned int)IoStatusBlock.Status);
                  v11 = IoStatusBlock.Status;
                  v5 = WPP_GLOBAL_Control;
                }
                if ( Status >= 0 )
                  Status = v11;
              }
              goto LABEL_60;
            }
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              goto LABEL_60;
            }
            v6 = 24;
          }
          else
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              goto LABEL_60;
            }
            v6 = 22;
          }
        }
      }
      v7 = (unsigned int)v8;
      goto LABEL_9;
    }
  }
  v4 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v6 = 17;
    v7 = v3;
LABEL_9:
    WPP_SF_d(v5[2], v6, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids, v7);
    v5 = WPP_GLOBAL_Control;
  }
LABEL_60:
  if ( EventHandle )
  {
    CloseHandle(EventHandle);
    v5 = WPP_GLOBAL_Control;
  }
  if ( FileHandle )
  {
    CloseHandle(FileHandle);
    v5 = WPP_GLOBAL_Control;
  }
  if ( Status < 0 || v3 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) )
      WPP_SF_Dd(v5[2], 27, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids, (unsigned int)Status, v3);
    if ( v2 )
      RpcEpUnregister(qword_18004D420, BindingVector, 0);
    if ( BindingVector )
    {
      RpcBindingVectorFree(&BindingVector);
      BindingVector = 0;
    }
    if ( v4 )
    {
      v13 = RpcServerUnregisterIf(qword_18004D420, 0, 1u);
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids, v13);
        }
      }
    }
    if ( Status >= 0 )
      return v3;
    else
      return RtlNtStatusToDosError(Status);
  }
  else
  {
    if ( BindingVector )
      RpcBindingVectorFree(&BindingVector);
    dword_18005E43C = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x180012190  mov     r11, rsp
0x180012193  push    rbx
0x180012194  push    rsi
0x180012195  push    rdi
0x180012196  push    r12
0x180012198  push    r13
0x18001219a  push    r14
0x18001219c  push    r15
0x18001219e  sub     rsp, 0B0h
0x1800121a5  xorps   xmm0, xmm0
0x1800121a8  movups  xmmword ptr [rsp+0E8h+IoStatusBlock], xmm0
0x1800121ad  xor     eax, eax
0x1800121af  movups  xmmword ptr [r11-68h], xmm0
0x1800121b4  movups  xmmword ptr [r11-58h], xmm0
0x1800121b9  movups  xmmword ptr [r11-4Ch], xmm0
0x1800121be  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1800121c3  xorps   xmm1, xmm1
0x1800121c6  movups  xmmword ptr [rsp+0E8h+var_88.Length], xmm1
0x1800121cb  xor     r13d, r13d
0x1800121ce  mov     [r11+8], r13
0x1800121d2  mov     [r11+18h], r13
0x1800121d6  mov     [r11+10h], r13
0x1800121da  lea     rcx, SpoolerMutex; lpCriticalSection
0x1800121e1  call    cs:__imp_InitializeCriticalSection
0x1800121e7  nop
0x1800121e8  mov     cs:dword_18005E4AC, 1
0x1800121f2  xor     r9d, r9d; SecurityDescriptor
0x1800121f5  xor     r8d, r8d; Endpoint
0x1800121f8  lea     edx, [r9+0Ah]; MaxCalls
0x1800121fc  lea     rcx, String2; "ncalrpc"
0x180012203  call    cs:__imp_RpcServerUseProtseqEpW
0x180012209  mov     ebx, r13d
0x18001220c  mov     r12b, r13b
0x18001220f  mov     esi, r13d
0x180012212  cmp     eax, 6CCh
0x180012217  cmovnz  esi, eax
0x18001221a  test    esi, esi
0x18001221c  jnz     short loc_180012250
0x18001221e  lea     rax, XactSrvRpcSecurityCallback
0x180012225  mov     [rsp+0E8h+IfCallback], rax; IfCallback
0x18001222a  mov     [rsp+0E8h+MaxCalls], 4D2h; MaxCalls
0x180012232  mov     r9d, 0B1h; Flags
0x180012238  xor     r8d, r8d; MgrEpv
0x18001223b  xor     edx, edx; MgrTypeUuid
0x18001223d  lea     rcx, qword_18004D420; IfSpec
0x180012244  call    cs:__imp_RpcServerRegisterIfEx
0x18001224a  mov     esi, eax
0x18001224c  test    eax, eax
0x18001224e  jz      short loc_1800122A2
0x180012250  mov     r15b, r13b
0x180012253  lea     rdi, WPP_GLOBAL_Control
0x18001225a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012261  cmp     rcx, rdi
0x180012264  jz      loc_1800125DE
0x18001226a  test    byte ptr [rcx+1Ch], 10h
0x18001226e  jz      loc_1800125DE
0x180012274  cmp     byte ptr [rcx+19h], 1
0x180012278  jb      loc_1800125DE
0x18001227e  mov     edx, 11h
0x180012283  mov     r9d, esi
0x180012286  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x18001228d  mov     rcx, [rcx+10h]
0x180012291  call    WPP_SF_d
0x180012296  mov     rcx, cs:WPP_GLOBAL_Control
0x18001229d  jmp     loc_1800125DE
0x1800122a2  mov     r15b, 1
0x1800122a5  lea     rcx, [rsp+0E8h+BindingVector]; BindingVector
0x1800122ad  call    cs:__imp_RpcServerInqBindings
0x1800122b3  mov     esi, eax
0x1800122b5  test    eax, eax
0x1800122b7  jz      short loc_1800122EE
0x1800122b9  lea     rdi, WPP_GLOBAL_Control
0x1800122c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122c7  cmp     rcx, rdi
0x1800122ca  jz      loc_1800125DE
0x1800122d0  test    byte ptr [rcx+1Ch], 10h
0x1800122d4  jz      loc_1800125DE
0x1800122da  cmp     [rcx+19h], r15b
0x1800122de  jb      loc_1800125DE
0x1800122e4  mov     edx, 12h
0x1800122e9  mov     r9d, eax
0x1800122ec  jmp     short loc_180012286
0x1800122ee  lea     r9, Annotation; "XactSrv service"
0x1800122f5  xor     r8d, r8d; UuidVector
0x1800122f8  mov     rdx, [rsp+0E8h+BindingVector]; BindingVector
0x180012300  lea     rcx, qword_18004D420; IfSpec
0x180012307  call    cs:__imp_RpcEpRegisterW
0x18001230d  mov     esi, eax
0x18001230f  test    eax, eax
0x180012311  jz      short loc_180012345
0x180012313  lea     rdi, WPP_GLOBAL_Control
0x18001231a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012321  cmp     rcx, rdi
0x180012324  jz      loc_1800125DE
0x18001232a  test    byte ptr [rcx+1Ch], 10h
0x18001232e  jz      loc_1800125DE
0x180012334  cmp     [rcx+19h], r15b
0x180012338  jb      loc_1800125DE
0x18001233e  mov     edx, 13h
0x180012343  jmp     short loc_1800122E9
0x180012345  mov     esi, r13d
0x180012348  mov     r12b, r15b
0x18001234b  lea     rdi, WPP_GLOBAL_Control
0x180012352  mov     rcx, cs:WPP_GLOBAL_Control
0x180012359  cmp     rcx, rdi
0x18001235c  jz      short loc_18001237F
0x18001235e  test    byte ptr [rcx+1Ch], 10h
0x180012362  jz      short loc_18001237F
0x180012364  cmp     byte ptr [rcx+19h], 2
0x180012368  jb      short loc_18001237F
0x18001236a  mov     edx, 14h
0x18001236f  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x180012376  mov     rcx, [rcx+10h]
0x18001237a  call    WPP_SF_
0x18001237f  lea     rdx, aDeviceSrvnet; "\\Device\\SrvNet"
0x180012386  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x18001238b  call    cs:__imp_RtlInitUnicodeString
0x180012391  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x18001239c  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], r13
0x1800123a4  mov     [rsp+0E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800123af  lea     rax, [rsp+0E8h+DestinationString]
0x1800123b4  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rax
0x1800123bc  xorps   xmm0, xmm0
0x1800123bf  movdqu  xmmword ptr [rsp+0E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800123c8  mov     dword ptr [rsp+0E8h+IfCallback], r13d; OpenOptions
0x1800123cd  mov     [rsp+0E8h+MaxCalls], r13d; ShareAccess
0x1800123d2  lea     r9, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x1800123d7  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x1800123df  mov     edx, 1; DesiredAccess
0x1800123e4  lea     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x1800123ec  call    cs:__imp_NtOpenFile
0x1800123f2  mov     ebx, eax
0x1800123f4  test    eax, eax
0x1800123f6  cmovns  ebx, dword ptr [rsp+0E8h+IoStatusBlock]
0x1800123fb  test    ebx, ebx
0x1800123fd  jns     short loc_180012430
0x1800123ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180012406  cmp     rcx, rdi
0x180012409  jz      loc_1800125DE
0x18001240f  test    byte ptr [rcx+1Ch], 10h
0x180012413  jz      loc_1800125DE
0x180012419  cmp     [rcx+19h], r15b
0x18001241d  jb      loc_1800125DE
0x180012423  mov     edx, 15h
0x180012428  mov     r9d, ebx
0x18001242b  jmp     loc_180012286
0x180012430  mov     byte ptr [rsp+0E8h+MaxCalls], r13b; InitialState
0x180012435  xor     r9d, r9d; EventType
0x180012438  xor     r8d, r8d; ObjectAttributes
0x18001243b  mov     edx, 1F0003h; DesiredAccess
0x180012440  lea     rcx, [rsp+0E8h+EventHandle]; EventHandle
0x180012448  call    cs:__imp_NtCreateEvent
0x18001244e  mov     ebx, eax
0x180012450  test    eax, eax
0x180012452  jns     short loc_180012482
0x180012454  mov     rcx, cs:WPP_GLOBAL_Control
0x18001245b  cmp     rcx, rdi
0x18001245e  jz      loc_1800125DE
0x180012464  test    byte ptr [rcx+1Ch], 10h
0x180012468  jz      loc_1800125DE
0x18001246e  cmp     [rcx+19h], r15b
0x180012472  jb      loc_1800125DE
0x180012478  mov     edx, 16h
0x18001247d  jmp     loc_1800122E9
0x180012482  mov     rcx, cs:WPP_GLOBAL_Control
0x180012489  cmp     rcx, rdi
0x18001248c  jz      short loc_1800124AF
0x18001248e  test    byte ptr [rcx+1Ch], 10h
0x180012492  jz      short loc_1800124AF
0x180012494  cmp     byte ptr [rcx+19h], 2
0x180012498  jb      short loc_1800124AF
0x18001249a  mov     edx, 17h
0x18001249f  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x1800124a6  mov     rcx, [rcx+10h]
0x1800124aa  call    WPP_SF_
0x1800124af  lea     rdx, aNcalrpc_0; "ncalrpc"
0x1800124b6  lea     rcx, [rsp+0E8h+var_88]; DestinationString
0x1800124bb  call    cs:__imp_RtlInitAnsiString
0x1800124c1  movzx   eax, [rsp+0E8h+var_88.Length]
0x1800124c6  mov     [rsp+0E8h+OutputBufferLength], r13d; OutputBufferLength
0x1800124cb  mov     [rsp+0E8h+OutputBuffer], r13; OutputBuffer
0x1800124d0  mov     [rsp+0E8h+InputBufferLength], eax; InputBufferLength
0x1800124d4  mov     rax, [rsp+0E8h+var_88.Buffer]
0x1800124d9  mov     [rsp+0E8h+InputBuffer], rax; InputBuffer
0x1800124de  mov     dword ptr [rsp+0E8h+IfCallback], 144014h; FsControlCode
0x1800124e6  lea     rax, [rsp+0E8h+IoStatusBlock]
0x1800124eb  mov     qword ptr [rsp+0E8h+MaxCalls], rax; IoStatusBlock
0x1800124f0  xor     r9d, r9d; ApcContext
0x1800124f3  xor     r8d, r8d; ApcRoutine
0x1800124f6  mov     rdx, [rsp+0E8h+EventHandle]; Event
0x1800124fe  mov     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x180012506  call    cs:__imp_NtFsControlFile
0x18001250c  mov     ebx, eax
0x18001250e  test    eax, eax
0x180012510  jns     short loc_180012540
0x180012512  mov     rcx, cs:WPP_GLOBAL_Control
0x180012519  cmp     rcx, rdi
0x18001251c  jz      loc_1800125DE
0x180012522  test    byte ptr [rcx+1Ch], 10h
0x180012526  jz      loc_1800125DE
0x18001252c  cmp     [rcx+19h], r15b
0x180012530  jb      loc_1800125DE
0x180012536  mov     edx, 18h
0x18001253b  jmp     loc_1800122E9
0x180012540  xor     r8d, r8d; Timeout
0x180012543  xor     edx, edx; Alertable
0x180012545  mov     rcx, [rsp+0E8h+EventHandle]; Handle
0x18001254d  call    cs:__imp_NtWaitForSingleObject
0x180012553  mov     r14d, eax
0x180012556  test    eax, eax
0x180012558  jns     short loc_180012596
0x18001255a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012561  cmp     rcx, rdi
0x180012564  jz      short loc_180012591
0x180012566  test    byte ptr [rcx+1Ch], 10h
0x18001256a  jz      short loc_180012591
0x18001256c  cmp     [rcx+19h], r15b
0x180012570  jb      short loc_180012591
0x180012572  mov     edx, 19h
0x180012577  mov     r9d, eax
0x18001257a  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x180012581  mov     rcx, [rcx+10h]
0x180012585  call    WPP_SF_d
0x18001258a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012591  mov     ebx, r14d
0x180012594  jmp     short loc_18001259D
0x180012596  mov     rcx, cs:WPP_GLOBAL_Control
0x18001259d  mov     eax, dword ptr [rsp+0E8h+IoStatusBlock]
0x1800125a1  test    eax, eax
0x1800125a3  jns     short loc_1800125DE
0x1800125a5  cmp     rcx, rdi
0x1800125a8  jz      short loc_1800125D9
0x1800125aa  test    byte ptr [rcx+1Ch], 10h
0x1800125ae  jz      short loc_1800125D9
0x1800125b0  cmp     [rcx+19h], r15b
0x1800125b4  jb      short loc_1800125D9
0x1800125b6  mov     edx, 1Ah
0x1800125bb  mov     r9d, eax
0x1800125be  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x1800125c5  mov     rcx, [rcx+10h]
0x1800125c9  call    WPP_SF_d
0x1800125ce  mov     eax, dword ptr [rsp+0E8h+IoStatusBlock]
0x1800125d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125d9  test    ebx, ebx
0x1800125db  cmovns  ebx, eax
0x1800125de  mov     rax, [rsp+0E8h+EventHandle]
0x1800125e6  test    rax, rax
0x1800125e9  jz      short loc_1800125FB
0x1800125eb  mov     rcx, rax; hObject
0x1800125ee  call    cs:__imp_CloseHandle
0x1800125f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125fb  mov     rax, [rsp+0E8h+FileHandle]
0x180012603  test    rax, rax
0x180012606  jz      short loc_180012618
0x180012608  mov     rcx, rax; hObject
0x18001260b  call    cs:__imp_CloseHandle
0x180012611  mov     rcx, cs:WPP_GLOBAL_Control
0x180012618  test    ebx, ebx
0x18001261a  js      short loc_180012649
0x18001261c  test    esi, esi
0x18001261e  jnz     short loc_180012649
0x180012620  cmp     [rsp+0E8h+BindingVector], r13
0x180012628  jz      short loc_180012638
0x18001262a  lea     rcx, [rsp+0E8h+BindingVector]; BindingVector
0x180012632  call    cs:__imp_RpcBindingVectorFree
0x180012638  mov     cs:dword_18005E43C, 1
0x180012642  xor     eax, eax
0x180012644  jmp     loc_18001271A
0x180012649  cmp     rcx, rdi
0x18001264c  jz      short loc_180012676
0x18001264e  test    byte ptr [rcx+1Ch], 10h
0x180012652  jz      short loc_180012676
0x180012654  cmp     byte ptr [rcx+19h], 1
0x180012658  jb      short loc_180012676
0x18001265a  mov     edx, 1Bh
0x18001265f  mov     [rsp+0E8h+MaxCalls], esi
0x180012663  mov     r9d, ebx
0x180012666  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x18001266d  mov     rcx, [rcx+10h]
0x180012671  call    WPP_SF_Dd
0x180012676  test    r12b, r12b
0x180012679  jz      short loc_180012693
0x18001267b  xor     r8d, r8d; UuidVector
0x18001267e  mov     rdx, [rsp+0E8h+BindingVector]; BindingVector
0x180012686  lea     rcx, qword_18004D420; IfSpec
0x18001268d  call    cs:__imp_RpcEpUnregister
0x180012693  cmp     [rsp+0E8h+BindingVector], r13
0x18001269b  jz      short loc_1800126B3
0x18001269d  lea     rcx, [rsp+0E8h+BindingVector]; BindingVector
0x1800126a5  call    cs:__imp_RpcBindingVectorFree
0x1800126ab  mov     [rsp+0E8h+BindingVector], r13
0x1800126b3  test    r15b, r15b
0x1800126b6  jz      short loc_1800126FF
0x1800126b8  xor     edx, edx; MgrTypeUuid
0x1800126ba  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x1800126be  lea     rcx, qword_18004D420; IfSpec
0x1800126c5  call    cs:__imp_RpcServerUnregisterIf
0x1800126cb  test    eax, eax
0x1800126cd  jz      short loc_1800126FF
0x1800126cf  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
