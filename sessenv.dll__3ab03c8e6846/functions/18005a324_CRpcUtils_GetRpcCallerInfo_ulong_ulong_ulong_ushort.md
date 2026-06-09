# CRpcUtils::GetRpcCallerInfo(ulong *,ulong *,ulong,ushort *)

- ea: `0x18005a324`
- end: `0x18005a429`
- name: `?GetRpcCallerInfo@CRpcUtils@@SAJPEAK0KPEAG@Z`
- size: `261`
- prototype: `__int64 __fastcall(DWORD *pSessionId, unsigned int *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005a1cc`

## callees

- `0x180004e00`
- `0x18001a280`
- `0x18005a324`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005a3dc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18005a3dc`
- `ntdll!NtQueryInformationProcess` at `0x18005a3c2`
- `ntdll!NtQueryInformationProcess` at `0x18005a3c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a403`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a403`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18005a37b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18005a37b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005a398`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005a398`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18005a359`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18005a359`

## pseudocode

```c
__int64 __fastcall CRpcUtils::GetRpcCallerInfo(
        DWORD *pSessionId,
        unsigned int *a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  unsigned __int64 v4; // rbp
  RPC_STATUS v8; // eax
  int v9; // ebx
  HANDLE v10; // rax
  void *v11; // rdi
  NTSTATUS InformationProcess; // eax
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  _BYTE ProcessInformation[8]; // [rsp+30h] [rbp-148h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-140h]

  v4 = a3;
  *pSessionId = -1;
  *a2 = -1;
  v8 = I_RpcBindingInqLocalClientPID(0, a2);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    ProcessIdToSessionId(*a2, pSessionId);
    if ( (_DWORD)v4 )
    {
      if ( a4 )
      {
        v10 = OpenProcess(0x400u, 0, *a2);
        v11 = v10;
        if ( v10 )
        {
          InformationProcess = NtQueryInformationProcess(v10, ProcessImageFileName, ProcessInformation, 0x110u, 0);
          v9 = InformationProcess | 0x10000000;
          if ( InformationProcess >= 0 )
          {
            v13 = wcsrchr(Str, 0x5Cu);
            if ( v13 )
              v14 = v13 + 1;
            else
              v14 = Str;
            StringCchCopyW(a4, v4, v14);
          }
          CloseHandle(v11);
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005a324  push    rbx
0x18005a326  push    rbp
0x18005a327  push    rsi
0x18005a328  push    rdi
0x18005a329  push    r14
0x18005a32b  sub     rsp, 150h
0x18005a332  mov     rax, cs:__security_cookie
0x18005a339  xor     rax, rsp
0x18005a33c  mov     [rsp+178h+var_38], rax
0x18005a344  or      eax, 0FFFFFFFFh
0x18005a347  mov     ebp, r8d
0x18005a34a  mov     [rcx], eax
0x18005a34c  mov     r14, rcx
0x18005a34f  xor     ecx, ecx; Binding
0x18005a351  mov     [rdx], eax
0x18005a353  mov     rsi, r9
0x18005a356  mov     rdi, rdx
0x18005a359  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18005a35f  mov     ebx, eax
0x18005a361  test    eax, eax
0x18005a363  jle     short loc_18005A36E
0x18005a365  movzx   ebx, ax
0x18005a368  or      ebx, 80070000h
0x18005a36e  test    ebx, ebx
0x18005a370  js      loc_18005A409
0x18005a376  mov     ecx, [rdi]; dwProcessId
0x18005a378  mov     rdx, r14; pSessionId
0x18005a37b  call    cs:__imp_ProcessIdToSessionId
0x18005a381  test    ebp, ebp
0x18005a383  jz      loc_18005A409
0x18005a389  test    rsi, rsi
0x18005a38c  jz      short loc_18005A409
0x18005a38e  mov     r8d, [rdi]; dwProcessId
0x18005a391  xor     edx, edx; bInheritHandle
0x18005a393  mov     ecx, 400h; dwDesiredAccess
0x18005a398  call    cs:__imp_OpenProcess
0x18005a39e  mov     rdi, rax
0x18005a3a1  test    rax, rax
0x18005a3a4  jz      short loc_18005A409
0x18005a3a6  mov     r9d, 110h; ProcessInformationLength
0x18005a3ac  mov     [rsp+178h+ReturnLength], 0; ReturnLength
0x18005a3b5  lea     r8, [rsp+178h+ProcessInformation]; ProcessInformation
0x18005a3ba  mov     edx, 1Bh; ProcessInformationClass
0x18005a3bf  mov     rcx, rax; ProcessHandle
0x18005a3c2  call    cs:__imp_NtQueryInformationProcess
0x18005a3c8  mov     ebx, eax
0x18005a3ca  or      ebx, 10000000h
0x18005a3d0  jl      short loc_18005A400
0x18005a3d2  mov     rcx, [rsp+178h+Str]; Str
0x18005a3d7  mov     edx, 5Ch ; '\'; Ch
0x18005a3dc  call    cs:__imp_wcsrchr
0x18005a3e2  test    rax, rax
0x18005a3e5  jnz     short loc_18005A3EE
0x18005a3e7  mov     rax, [rsp+178h+Str]
0x18005a3ec  jmp     short loc_18005A3F2
0x18005a3ee  add     rax, 2
0x18005a3f2  mov     rdx, rbp; unsigned __int64
0x18005a3f5  mov     r8, rax; unsigned __int16 *
0x18005a3f8  mov     rcx, rsi; unsigned __int16 *
0x18005a3fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005a400  mov     rcx, rdi; hObject
0x18005a403  call    cs:__imp_CloseHandle
0x18005a409  mov     eax, ebx
0x18005a40b  mov     rcx, [rsp+178h+var_38]
0x18005a413  xor     rcx, rsp; StackCookie
0x18005a416  call    __security_check_cookie
0x18005a41b  add     rsp, 150h
0x18005a422  pop     r14
0x18005a424  pop     rdi
0x18005a425  pop     rsi
0x18005a426  pop     rbp
0x18005a427  pop     rbx
0x18005a428  retn
```
