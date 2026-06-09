# WluiNotifyIsReadyForDesktopSwitch

- ea: `0x1400422c0`
- end: `0x14004235e`
- name: `WluiNotifyIsReadyForDesktopSwitch`
- size: `158`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400176f8`
- `0x14006e220`

## callees

- `0x140012220`
- `0x1400422c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140042342`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140042342`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400422ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400422ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400422db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400422db`
- `RPCRT4!NdrClientCall3` at `0x140042314`
- `RPCRT4!NdrClientCall3` at `0x140042314`
- `RPCRT4!I_RpcExceptionFilter` at `0x14009e879`
- `RPCRT4!I_RpcExceptionFilter` at `0x14009e879`

## string_xrefs

- `0x140042334`: `WluiReadyForDesktopSwitchEvent`

## pseudocode

```c
HANDLE WluiNotifyIsReadyForDesktopSwitch()
{
  unsigned int Pointer; // ebx
  int v1; // edi
  __int64 v2; // rsi

  Pointer = 21;
  EnterCriticalSection(&stru_1400D2DD0);
  v1 = WluiiWaitForServer();
  LeaveCriticalSection(&stru_1400D2DD0);
  v2 = 0;
  if ( v1 )
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xCu, 0, Binding).Pointer;
  if ( !Pointer )
    return OpenEventW(0x100000u, 0, L"WluiReadyForDesktopSwitchEvent");
  return (HANDLE)v2;
}

```

## disassembly

```asm
0x1400422c0  mov     [rsp+arg_8], rbx
0x1400422c5  mov     [rsp+arg_10], rsi
0x1400422ca  push    rdi
0x1400422cb  sub     rsp, 30h
0x1400422cf  mov     ebx, 15h
0x1400422d4  lea     rcx, stru_1400D2DD0; lpCriticalSection
0x1400422db  call    cs:__imp_EnterCriticalSection
0x1400422e1  call    WluiiWaitForServer
0x1400422e6  mov     edi, eax
0x1400422e8  lea     rcx, stru_1400D2DD0; lpCriticalSection
0x1400422ef  call    cs:__imp_LeaveCriticalSection
0x1400422f5  xor     esi, esi
0x1400422f7  test    edi, edi
0x1400422f9  jz      short loc_140042330
0x1400422fb  mov     [rsp+38h+arg_0], rsi
0x140042300  mov     r9, cs:Binding
0x140042307  xor     r8d, r8d; pReturnValue
0x14004230a  lea     edx, [rbx-9]; nProcNum
0x14004230d  lea     rcx, pProxyInfo; pProxyInfo
0x140042314  call    cs:__imp_NdrClientCall3
0x14004231a  mov     rbx, rax
0x14004231d  mov     [rsp+38h+arg_0], rax
0x140042322  mov     [rsp+38h+var_18], eax
0x140042326  jmp     short loc_140042330
0x140042328  mov     ebx, eax
0x14004232a  mov     [rsp+38h+var_18], eax
0x14004232e  xor     esi, esi
0x140042330  test    ebx, ebx
0x140042332  jnz     short loc_14004234B
0x140042334  lea     r8, aWluireadyforde; "WluiReadyForDesktopSwitchEvent"
0x14004233b  xor     edx, edx; bInheritHandle
0x14004233d  mov     ecx, 100000h; dwDesiredAccess
0x140042342  call    cs:__imp_OpenEventW
0x140042348  mov     rsi, rax
0x14004234b  mov     rax, rsi
0x14004234e  mov     rbx, [rsp+38h+arg_8]
0x140042353  mov     rsi, [rsp+38h+arg_10]
0x140042358  add     rsp, 30h
0x14004235c  pop     rdi
0x14004235d  retn
0x14009e86b  push    rbp
0x14009e86d  sub     rsp, 20h
0x14009e871  mov     rbp, rdx
0x14009e874  mov     rcx, [rcx]
0x14009e877  mov     ecx, [rcx]; ExceptionCode
0x14009e879  call    cs:__imp_I_RpcExceptionFilter
0x14009e87f  nop
0x14009e880  add     rsp, 20h
0x14009e884  pop     rbp
0x14009e885  retn
```
