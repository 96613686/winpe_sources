# CRpcUtils::GetRpcCallerInfo(ulong *,ulong *,ulong,ushort *)

- ea: `0x18000f250`
- end: `0x18000f357`
- name: `?GetRpcCallerInfo@CRpcUtils@@SAJPEAK0KPEAG@Z`
- size: `263`
- prototype: `__int64 __fastcall(DWORD *pSessionId, unsigned int *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004da60`

## callees

- `0x18000f250`
- `0x1800127b0`
- `0x1800321f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f325`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f325`
- `ntdll!NtQueryInformationProcess` at `0x18000f30b`
- `ntdll!NtQueryInformationProcess` at `0x18000f30b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000f2a8`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000f2a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f34c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f34c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000f28a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000f28a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f2e1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f2e1`

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
0x18000f250  push    rbx
0x18000f252  push    rbp
0x18000f253  push    rsi
0x18000f254  push    rdi
0x18000f255  push    r14
0x18000f257  sub     rsp, 150h
0x18000f25e  mov     rax, cs:__security_cookie
0x18000f265  xor     rax, rsp
0x18000f268  mov     [rsp+178h+var_38], rax
0x18000f270  mov     dword ptr [rcx], 0FFFFFFFFh
0x18000f276  mov     rsi, rcx
0x18000f279  xor     ecx, ecx; Binding
0x18000f27b  mov     ebp, r8d
0x18000f27e  mov     r14, r9
0x18000f281  mov     dword ptr [rdx], 0FFFFFFFFh
0x18000f287  mov     rdi, rdx
0x18000f28a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000f290  mov     ebx, eax
0x18000f292  test    eax, eax
0x18000f294  jle     short loc_18000F29F
0x18000f296  movzx   ebx, ax
0x18000f299  or      ebx, 80070000h
0x18000f29f  test    ebx, ebx
0x18000f2a1  js      short loc_18000F2B2
0x18000f2a3  mov     ecx, [rdi]; dwProcessId
0x18000f2a5  mov     rdx, rsi; pSessionId
0x18000f2a8  call    cs:__imp_ProcessIdToSessionId
0x18000f2ae  test    ebp, ebp
0x18000f2b0  jnz     short loc_18000F2D2
0x18000f2b2  mov     eax, ebx
0x18000f2b4  mov     rcx, [rsp+178h+var_38]
0x18000f2bc  xor     rcx, rsp; StackCookie
0x18000f2bf  call    __security_check_cookie
0x18000f2c4  add     rsp, 150h
0x18000f2cb  pop     r14
0x18000f2cd  pop     rdi
0x18000f2ce  pop     rsi
0x18000f2cf  pop     rbp
0x18000f2d0  pop     rbx
0x18000f2d1  retn
0x18000f2d2  test    r14, r14
0x18000f2d5  jz      short loc_18000F2B2
0x18000f2d7  mov     r8d, [rdi]; dwProcessId
0x18000f2da  xor     edx, edx; bInheritHandle
0x18000f2dc  mov     ecx, 400h; dwDesiredAccess
0x18000f2e1  call    cs:__imp_OpenProcess
0x18000f2e7  mov     rdi, rax
0x18000f2ea  test    rax, rax
0x18000f2ed  jz      short loc_18000F2B2
0x18000f2ef  mov     r9d, 110h; ProcessInformationLength
0x18000f2f5  mov     [rsp+178h+ReturnLength], 0; ReturnLength
0x18000f2fe  lea     r8, [rsp+178h+ProcessInformation]; ProcessInformation
0x18000f303  mov     edx, 1Bh; ProcessInformationClass
0x18000f308  mov     rcx, rax; ProcessHandle
0x18000f30b  call    cs:__imp_NtQueryInformationProcess
0x18000f311  mov     ebx, eax
0x18000f313  or      ebx, 10000000h
0x18000f319  jl      short loc_18000F349
0x18000f31b  mov     rcx, [rsp+178h+Str]; Str
0x18000f320  mov     edx, 5Ch ; '\'; Ch
0x18000f325  call    cs:__imp_wcsrchr
0x18000f32b  test    rax, rax
0x18000f32e  jnz     short loc_18000F337
0x18000f330  mov     rax, [rsp+178h+Str]
0x18000f335  jmp     short loc_18000F33B
0x18000f337  add     rax, 2
0x18000f33b  mov     rdx, rbp; unsigned __int64
0x18000f33e  mov     r8, rax; unsigned __int16 *
0x18000f341  mov     rcx, r14; unsigned __int16 *
0x18000f344  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f349  mov     rcx, rdi; hObject
0x18000f34c  call    cs:__imp_CloseHandle
0x18000f352  jmp     loc_18000F2B2
```
