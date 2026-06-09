# CWerService::CheckIfValidPortMessage(_WERSVC_MSG *)

- ea: `0x180014c54`
- end: `0x180014e9c`
- name: `?CheckIfValidPortMessage@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014fa4`
- `0x18001d5cc`

## callees

- `0x180013df4`
- `0x180014c54`
- `0x18001caf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014e7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e6d`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180014cd5`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180014cd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWerService::CheckIfValidPortMessage(CWerService *this, struct _WERSVC_MSG *a2)
{
  int v3; // edi
  HANDLE v4; // rcx
  char *v5; // rax
  int v6; // ecx
  signed int LastError; // eax
  signed int v9; // ebx
  int v10; // ebx
  WINBOOL Wow64Process; // [rsp+68h] [rbp+28h] BYREF
  HANDLE hProcess; // [rsp+70h] [rbp+30h] BYREF

  v3 = (int)this;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((__int16 *)a2 + 2) < 0 && *(_DWORD *)a2 == 17826024 )
    return 0;
  if ( *((_WORD *)a2 + 1) == 1400 )
  {
LABEL_13:
    v6 = *((_DWORD *)a2 + 10);
    if ( v6 != 0x10000000 && v6 != 268435462 && v6 != 0x20000000 )
    {
      if ( v6 == 2 )
      {
        v10 = *((_DWORD *)a2 + 2);
        return GetCurrentProcessId() != v10 ? 0x80070005 : 0;
      }
      if ( v6 != 1342177280
        && v6 != 1610612736
        && v6 != 0x80000000
        && v6 != -1879048192
        && v6 != 805306368
        && v6 != 0x40000000
        && v6 != 268435463
        && v6 != -1342177280
        && (unsigned int)(v6 + 1073741822) > 2
        && v6 != -805306366
        && v6 != -536870910
        && v6 != -268435454
        && v6 != -268369918
        && v6 != -268304382
        && v6 != -268238846
        && v6 != -268173310
        && v6 != -268107774 )
      {
        return v6 != -268042238 ? 0xD000001C : 0;
      }
    }
    return 0;
  }
  if ( *((_WORD *)a2 + 1) > 0x578u )
    return 3489660963LL;
  Wow64Process = 0;
  hProcess = 0;
  if ( (int)CWerService::_OpenSenderProcessThread(v3, (_DWORD)a2, 1024, (unsigned int)&hProcess, 0, 0, 0) >= 0 )
  {
    if ( IsWow64Process(hProcess, &Wow64Process) && Wow64Process )
    {
      Wow64Process = 1;
      v4 = hProcess;
      v5 = (char *)hProcess + 1;
      if ( *((_WORD *)a2 + 1) == 1296 )
      {
        if ( (unsigned __int64)v5 > 1 )
          CloseHandle(hProcess);
        goto LABEL_13;
      }
    }
    else
    {
      Wow64Process = 0;
      v4 = hProcess;
      v5 = (char *)hProcess + 1;
    }
    if ( (unsigned __int64)v5 > 1 )
      CloseHandle(v4);
    return 3489660963LL;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 >= 0 )
    v9 = -2147467259;
  if ( (unsigned __int64)hProcess + 1 > 1 )
    CloseHandle(hProcess);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180014c54  mov     [rsp-18h+arg_0], rbx
0x180014c59  push    rbp
0x180014c5a  push    rsi
0x180014c5b  push    rdi
0x180014c5c  mov     rbp, rsp
0x180014c5f  sub     rsp, 40h
0x180014c63  mov     rbx, rdx
0x180014c66  mov     rdi, rcx
0x180014c69  xor     esi, esi
0x180014c6b  test    rdx, rdx
0x180014c6e  jnz     short loc_180014C75
0x180014c70  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014c75  cmp     [rbx+4], si
0x180014c79  jge     short loc_180014C87
0x180014c7b  cmp     dword ptr [rbx], 11000E8h
0x180014c81  jz      loc_180014E8D
0x180014c87  mov     eax, 578h
0x180014c8c  cmp     [rbx+2], ax
0x180014c90  jz      loc_180014D16
0x180014c96  ja      loc_180014E39
0x180014c9c  mov     [rbp+Wow64Process], esi
0x180014c9f  mov     [rbp+hProcess], rsi
0x180014ca3  mov     [rsp+40h+var_10], esi
0x180014ca7  mov     [rsp+40h+var_18], rsi
0x180014cac  mov     [rsp+40h+var_20], esi
0x180014cb0  lea     r9, [rbp+hProcess]
0x180014cb4  mov     r8d, 400h
0x180014cba  mov     rdx, rbx
0x180014cbd  mov     rcx, rdi
0x180014cc0  call    ?_OpenSenderProcessThread@CWerService@@AEAAJPEAU_WERSVC_MSG@@KPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K1K@Z; CWerService::_OpenSenderProcessThread(_WERSVC_MSG *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong,tlx::unique_any<tlx::file_handle_traits> *,ulong)
0x180014cc5  test    eax, eax
0x180014cc7  js      loc_180014E40
0x180014ccd  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x180014cd1  mov     rcx, [rbp+hProcess]; hProcess
0x180014cd5  call    cs:__imp_IsWow64Process
0x180014cdb  test    eax, eax
0x180014cdd  jz      loc_180014E22
0x180014ce3  cmp     [rbp+Wow64Process], esi
0x180014ce6  jz      loc_180014E22
0x180014cec  mov     [rbp+Wow64Process], 1
0x180014cf3  mov     eax, 510h
0x180014cf8  mov     rcx, [rbp+hProcess]; hObject
0x180014cfc  cmp     [rbx+2], ax
0x180014d00  lea     rax, [rcx+1]
0x180014d04  jnz     loc_180014E2D
0x180014d0a  cmp     rax, 1
0x180014d0e  jbe     short loc_180014D16
0x180014d10  call    cs:__imp_CloseHandle
0x180014d16  mov     ecx, [rbx+28h]
0x180014d19  cmp     ecx, 10000000h
0x180014d1f  jz      loc_180014E8D
0x180014d25  cmp     ecx, 10000006h
0x180014d2b  jz      loc_180014E8D
0x180014d31  cmp     ecx, 20000000h
0x180014d37  jz      loc_180014E8D
0x180014d3d  cmp     ecx, 2
0x180014d40  jz      loc_180014E77
0x180014d46  cmp     ecx, 50000000h
0x180014d4c  jz      loc_180014E8D
0x180014d52  cmp     ecx, 60000000h
0x180014d58  jz      loc_180014E8D
0x180014d5e  cmp     ecx, 80000000h
0x180014d64  jz      loc_180014E8D
0x180014d6a  cmp     ecx, 90000000h
0x180014d70  jz      loc_180014E8D
0x180014d76  cmp     ecx, 30000000h
0x180014d7c  jz      loc_180014E8D
0x180014d82  cmp     ecx, 40000000h
0x180014d88  jz      loc_180014E8D
0x180014d8e  cmp     ecx, 10000007h
0x180014d94  jz      loc_180014E8D
0x180014d9a  cmp     ecx, 0B0000000h
0x180014da0  jz      loc_180014E8D
0x180014da6  lea     eax, [rcx+3FFFFFFEh]
0x180014dac  cmp     eax, 2
0x180014daf  jbe     loc_180014E8D
0x180014db5  cmp     ecx, 0D0000002h
0x180014dbb  jz      loc_180014E8D
0x180014dc1  cmp     ecx, 0E0000002h
0x180014dc7  jz      loc_180014E8D
0x180014dcd  cmp     ecx, 0F0000002h
0x180014dd3  jz      loc_180014E8D
0x180014dd9  cmp     ecx, 0F0010002h
0x180014ddf  jz      loc_180014E8D
0x180014de5  cmp     ecx, 0F0020002h
0x180014deb  jz      loc_180014E8D
0x180014df1  cmp     ecx, 0F0030002h
0x180014df7  jz      loc_180014E8D
0x180014dfd  cmp     ecx, 0F0040002h
0x180014e03  jz      loc_180014E8D
0x180014e09  cmp     ecx, 0F0050002h
0x180014e0f  jz      short loc_180014E8D
0x180014e11  sub     ecx, 0F0060002h
0x180014e17  neg     ecx
0x180014e19  sbb     eax, eax
0x180014e1b  and     eax, 0D000001Ch
0x180014e20  jmp     short loc_180014E8F
0x180014e22  mov     [rbp+Wow64Process], esi
0x180014e25  mov     rcx, [rbp+hProcess]; hObject
0x180014e29  lea     rax, [rcx+1]
0x180014e2d  cmp     rax, 1
0x180014e31  jbe     short loc_180014E39
0x180014e33  call    cs:__imp_CloseHandle
0x180014e39  mov     eax, 0D0000023h
0x180014e3e  jmp     short loc_180014E8F
0x180014e40  call    cs:__imp_GetLastError
0x180014e46  mov     ebx, eax
0x180014e48  test    eax, eax
0x180014e4a  jle     short loc_180014E55
0x180014e4c  movzx   ebx, ax
0x180014e4f  or      ebx, 80070000h
0x180014e55  mov     eax, 80004005h
0x180014e5a  test    ebx, ebx
0x180014e5c  cmovns  ebx, eax
0x180014e5f  mov     rcx, [rbp+hProcess]; hObject
0x180014e63  lea     rdx, [rcx+1]
0x180014e67  cmp     rdx, 1
0x180014e6b  jbe     short loc_180014E73
0x180014e6d  call    cs:__imp_CloseHandle
0x180014e73  mov     eax, ebx
0x180014e75  jmp     short loc_180014E8F
0x180014e77  mov     ebx, [rbx+8]
0x180014e7a  call    cs:__imp_GetCurrentProcessId
0x180014e80  sub     ebx, eax
0x180014e82  neg     ebx
0x180014e84  sbb     eax, eax
0x180014e86  and     eax, 80070005h
0x180014e8b  jmp     short loc_180014E8F
0x180014e8d  xor     eax, eax
0x180014e8f  mov     rbx, [rsp+40h+arg_0]
0x180014e94  add     rsp, 40h
0x180014e98  pop     rdi
0x180014e99  pop     rsi
0x180014e9a  pop     rbp
0x180014e9b  retn
```
