# UbpmEnableTaskHostChannelRpcInterface

- ea: `0x18002af50`
- end: `0x18002b0d8`
- name: `UbpmEnableTaskHostChannelRpcInterface`
- size: `392`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a7f0`

## callees

- `0x18002af50`
- `0x180032e38`
- `0x1800347bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002afb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002afb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002af5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002af5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afca`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002b073`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002b073`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002b00f`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002b00f`

## string_xrefs

- `0x18002af56`: `rpcrt4.dll`
- `0x18002afae`: `I_RpcOpenClientProcess`
- `0x18002affd`: `ubpmtaskhostchannel`

## pseudocode

```c
__int64 UbpmEnableTaskHostChannelRpcInterface()
{
  HMODULE ModuleHandleW; // rax
  DWORD LastError; // eax
  DWORD v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx

  ModuleHandleW = GetModuleHandleW(L"rpcrt4.dll");
  if ( ModuleHandleW )
  {
    s_pfnI_RpcOpenClientProcess = (int (*)(void *, unsigned int, void **))GetProcAddress(
                                                                            ModuleHandleW,
                                                                            "I_RpcOpenClientProcess");
    if ( s_pfnI_RpcOpenClientProcess )
    {
      LastError = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"ubpmtaskhostchannel", 0);
      v2 = LastError;
      if ( !LastError || LastError == 1740 )
      {
        LastError = RpcServerRegisterIfEx(
                      qword_18003F2C0,
                      0,
                      0,
                      0x21u,
                      0x4D2u,
                      (RPC_IF_CALLBACK_FN *)UbpmpTaskHostChannelInterfaceSecurityCb);
        v2 = LastError;
        if ( LastError )
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v4 = 15;
            goto LABEL_5;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids);
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = 14;
          goto LABEL_5;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 13;
        goto LABEL_5;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 12;
LABEL_5:
      WPP_SF_d(v3[2], v4, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002af50  push    rbx
0x18002af52  sub     rsp, 30h
0x18002af56  lea     rcx, ModuleName; "rpcrt4.dll"
0x18002af5d  call    cs:__imp_GetModuleHandleW
0x18002af63  test    rax, rax
0x18002af66  jnz     short loc_18002AFAE
0x18002af68  call    cs:__imp_GetLastError
0x18002af6e  mov     ebx, eax
0x18002af70  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af77  lea     rdx, WPP_GLOBAL_Control
0x18002af7e  cmp     rcx, rdx
0x18002af81  jz      loc_18002B0D0
0x18002af87  test    byte ptr [rcx+1Ch], 1
0x18002af8b  jz      loc_18002B0D0
0x18002af91  mov     edx, 0Ch
0x18002af96  mov     rcx, [rcx+10h]
0x18002af9a  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002afa1  mov     r9d, eax
0x18002afa4  call    WPP_SF_d
0x18002afa9  jmp     loc_18002B0D0
0x18002afae  lea     rdx, ProcName; "I_RpcOpenClientProcess"
0x18002afb5  mov     rcx, rax; hModule
0x18002afb8  call    cs:__imp_GetProcAddress
0x18002afbe  mov     cs:?s_pfnI_RpcOpenClientProcess@@3P6AJPEAXKPEAPEAX@ZEA, rax; long (*s_pfnI_RpcOpenClientProcess)(void *,ulong,void * *)
0x18002afc5  test    rax, rax
0x18002afc8  jnz     short loc_18002AFFA
0x18002afca  call    cs:__imp_GetLastError
0x18002afd0  mov     ebx, eax
0x18002afd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afd9  lea     rdx, WPP_GLOBAL_Control
0x18002afe0  cmp     rcx, rdx
0x18002afe3  jz      loc_18002B0D0
0x18002afe9  test    byte ptr [rcx+1Ch], 1
0x18002afed  jz      loc_18002B0D0
0x18002aff3  mov     edx, 0Dh
0x18002aff8  jmp     short loc_18002AF96
0x18002affa  xor     r9d, r9d; SecurityDescriptor
0x18002affd  lea     r8, Endpoint; "ubpmtaskhostchannel"
0x18002b004  lea     rcx, Protseq; "ncalrpc"
0x18002b00b  lea     edx, [r9+0Ah]; MaxCalls
0x18002b00f  call    cs:__imp_RpcServerUseProtseqEpW
0x18002b015  mov     ebx, eax
0x18002b017  test    eax, eax
0x18002b019  jz      short loc_18002B04D
0x18002b01b  cmp     eax, 6CCh
0x18002b020  jz      short loc_18002B04D
0x18002b022  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b029  lea     rdx, WPP_GLOBAL_Control
0x18002b030  cmp     rcx, rdx
0x18002b033  jz      loc_18002B0D0
0x18002b039  test    byte ptr [rcx+1Ch], 1
0x18002b03d  jz      loc_18002B0D0
0x18002b043  mov     edx, 0Eh
0x18002b048  jmp     loc_18002AF96
0x18002b04d  lea     rax, UbpmpTaskHostChannelInterfaceSecurityCb
0x18002b054  mov     r9d, 21h ; '!'; Flags
0x18002b05a  mov     [rsp+38h+IfCallback], rax; IfCallback
0x18002b05f  lea     rcx, qword_18003F2C0; IfSpec
0x18002b066  xor     r8d, r8d; MgrEpv
0x18002b069  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x18002b071  xor     edx, edx; MgrTypeUuid
0x18002b073  call    cs:__imp_RpcServerRegisterIfEx
0x18002b079  mov     ebx, eax
0x18002b07b  test    eax, eax
0x18002b07d  jz      short loc_18002B0A2
0x18002b07f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b086  lea     rdx, WPP_GLOBAL_Control
0x18002b08d  cmp     rcx, rdx
0x18002b090  jz      short loc_18002B0D0
0x18002b092  test    byte ptr [rcx+1Ch], 1
0x18002b096  jz      short loc_18002B0D0
0x18002b098  mov     edx, 0Fh
0x18002b09d  jmp     loc_18002AF96
0x18002b0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0a9  lea     rdx, WPP_GLOBAL_Control
0x18002b0b0  cmp     rcx, rdx
0x18002b0b3  jz      short loc_18002B0D0
0x18002b0b5  test    byte ptr [rcx+1Ch], 80h
0x18002b0b9  jz      short loc_18002B0D0
0x18002b0bb  mov     rcx, [rcx+10h]
0x18002b0bf  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002b0c6  mov     edx, 10h
0x18002b0cb  call    WPP_SF_
0x18002b0d0  mov     eax, ebx
0x18002b0d2  add     rsp, 30h
0x18002b0d6  pop     rbx
0x18002b0d7  retn
```
