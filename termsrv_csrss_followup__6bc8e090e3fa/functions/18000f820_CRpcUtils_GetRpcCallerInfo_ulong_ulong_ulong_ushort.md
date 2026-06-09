# CRpcUtils::GetRpcCallerInfo(ulong *,ulong *,ulong,ushort *)

- ea: `0x18000f820`
- end: `0x18000f94c`
- name: `?GetRpcCallerInfo@CRpcUtils@@SAJPEAK0KPEAG@Z`
- size: `300`
- prototype: `__int64 __fastcall(DWORD *pSessionId, unsigned int *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800500a0`

## callees

- `0x18000f820`
- `0x180012d10`
- `0x180033f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f90e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f90e`
- `ntdll!NtQueryInformationProcess` at `0x18000f8ee`
- `ntdll!NtQueryInformationProcess` at `0x18000f8ee`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000f87e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000f87e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f93b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f93b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000f85a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000f85a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f8be`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f8be`

## pseudocode

```c
__int64 __fastcall CRpcUtils::GetRpcCallerInfo(
        DWORD *pSessionId,
        unsigned int *a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  unsigned __int64 v5; // rbp
  RPC_STATUS v8; // eax
  int v9; // ebx
  HANDLE v11; // rax
  void *v12; // rdi
  NTSTATUS InformationProcess; // eax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  _BYTE ProcessInformation[8]; // [rsp+30h] [rbp-148h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-140h]

  *pSessionId = -1;
  v5 = a3;
  *a2 = -1;
  v8 = I_RpcBindingInqLocalClientPID(0, a2);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    ProcessIdToSessionId(*a2, pSessionId);
    if ( (_DWORD)v5 )
    {
      if ( a4 )
      {
        v11 = OpenProcess(0x400u, 0, *a2);
        v12 = v11;
        if ( v11 )
        {
          InformationProcess = NtQueryInformationProcess(v11, ProcessImageFileName, ProcessInformation, 0x110u, 0);
          v9 = InformationProcess | 0x10000000;
          if ( InformationProcess >= 0 )
          {
            v14 = wcsrchr(Str, 0x5Cu);
            if ( v14 )
              v15 = v14 + 1;
            else
              v15 = Str;
            StringCchCopyW(a4, v5, v15);
          }
          CloseHandle(v12);
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f820  push    rbx
0x18000f822  push    rbp
0x18000f823  push    rsi
0x18000f824  push    rdi
0x18000f825  push    r14
0x18000f827  sub     rsp, 150h
0x18000f82e  mov     rax, cs:__security_cookie
0x18000f835  xor     rax, rsp
0x18000f838  mov     [rsp+178h+var_38], rax
0x18000f840  mov     dword ptr [rcx], 0FFFFFFFFh
0x18000f846  mov     rsi, rcx
0x18000f849  xor     ecx, ecx; Binding
0x18000f84b  mov     ebp, r8d
0x18000f84e  mov     r14, r9
0x18000f851  mov     dword ptr [rdx], 0FFFFFFFFh
0x18000f857  mov     rdi, rdx
0x18000f85a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000f861  nop     dword ptr [rax+rax+00h]
0x18000f866  mov     ebx, eax
0x18000f868  test    eax, eax
0x18000f86a  jle     short loc_18000F875
0x18000f86c  movzx   ebx, ax
0x18000f86f  or      ebx, 80070000h
0x18000f875  test    ebx, ebx
0x18000f877  js      short loc_18000F88E
0x18000f879  mov     ecx, [rdi]; dwProcessId
0x18000f87b  mov     rdx, rsi; pSessionId
0x18000f87e  call    cs:__imp_ProcessIdToSessionId
0x18000f885  nop     dword ptr [rax+rax+00h]
0x18000f88a  test    ebp, ebp
0x18000f88c  jnz     short loc_18000F8AF
0x18000f88e  mov     eax, ebx
0x18000f890  mov     rcx, [rsp+178h+var_38]
0x18000f898  xor     rcx, rsp; StackCookie
0x18000f89b  call    __security_check_cookie
0x18000f8a0  add     rsp, 150h
0x18000f8a7  pop     r14
0x18000f8a9  pop     rdi
0x18000f8aa  pop     rsi
0x18000f8ab  pop     rbp
0x18000f8ac  pop     rbx
0x18000f8ad  retn
0x18000f8af  test    r14, r14
0x18000f8b2  jz      short loc_18000F88E
0x18000f8b4  mov     r8d, [rdi]; dwProcessId
0x18000f8b7  xor     edx, edx; bInheritHandle
0x18000f8b9  mov     ecx, 400h; dwDesiredAccess
0x18000f8be  call    cs:__imp_OpenProcess
0x18000f8c5  nop     dword ptr [rax+rax+00h]
0x18000f8ca  mov     rdi, rax
0x18000f8cd  test    rax, rax
0x18000f8d0  jz      short loc_18000F88E
0x18000f8d2  mov     r9d, 110h; ProcessInformationLength
0x18000f8d8  mov     [rsp+178h+ReturnLength], 0; ReturnLength
0x18000f8e1  lea     r8, [rsp+178h+ProcessInformation]; ProcessInformation
0x18000f8e6  mov     edx, 1Bh; ProcessInformationClass
0x18000f8eb  mov     rcx, rax; ProcessHandle
0x18000f8ee  call    cs:__imp_NtQueryInformationProcess
0x18000f8f5  nop     dword ptr [rax+rax+00h]
0x18000f8fa  mov     ebx, eax
0x18000f8fc  or      ebx, 10000000h
0x18000f902  jl      short loc_18000F938
0x18000f904  mov     rcx, [rsp+178h+Str]; Str
0x18000f909  mov     edx, 5Ch ; '\'; Ch
0x18000f90e  call    cs:__imp_wcsrchr
0x18000f915  nop     dword ptr [rax+rax+00h]
0x18000f91a  test    rax, rax
0x18000f91d  jnz     short loc_18000F926
0x18000f91f  mov     rax, [rsp+178h+Str]
0x18000f924  jmp     short loc_18000F92A
0x18000f926  add     rax, 2
0x18000f92a  mov     rdx, rbp; unsigned __int64
0x18000f92d  mov     r8, rax; unsigned __int16 *
0x18000f930  mov     rcx, r14; unsigned __int16 *
0x18000f933  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f938  mov     rcx, rdi; hObject
0x18000f93b  call    cs:__imp_CloseHandle
0x18000f942  nop     dword ptr [rax+rax+00h]
0x18000f947  jmp     loc_18000F88E
```
