# RpcAutoImpersonate::GetClientUser(User &)

- ea: `0x18002e4e4`
- end: `0x18002e562`
- name: `?GetClientUser@RpcAutoImpersonate@@QEBAJAEAVUser@@@Z`
- size: `126`
- prototype: `int(RpcAutoImpersonate *__hidden this, struct User *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800213f8`
- `0x1800785f4`

## callees

- `0x18002e4e4`
- `0x18002f3e0`
- `0x180039d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e515`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e554`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e554`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e4f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002e4f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002e50b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002e50b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcAutoImpersonate::GetClientUser(RpcAutoImpersonate *this, struct User *a2)
{
  void *v3; // rdx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  TokenHandle = 0;
  if ( !*(_DWORD *)this )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
      return v6;
    }
    v3 = TokenHandle;
  }
  v6 = User::FromImpersonationToken(a2, v3);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18002e4e4  push    rbx
0x18002e4e6  sub     rsp, 20h
0x18002e4ea  mov     rbx, rdx
0x18002e4ed  xor     edx, edx
0x18002e4ef  mov     [rsp+28h+TokenHandle], rdx
0x18002e4f4  cmp     [rcx], edx
0x18002e4f6  jnz     short loc_18002E53B
0x18002e4f8  call    cs:__imp_GetCurrentProcess
0x18002e4fe  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18002e503  mov     edx, 20008h; DesiredAccess
0x18002e508  mov     rcx, rax; ProcessHandle
0x18002e50b  call    cs:__imp_OpenProcessToken
0x18002e511  test    eax, eax
0x18002e513  jnz     short loc_18002E536
0x18002e515  call    cs:__imp_GetLastError
0x18002e51b  mov     ebx, eax
0x18002e51d  test    eax, eax
0x18002e51f  jle     short loc_18002E52A
0x18002e521  movzx   ebx, ax
0x18002e524  or      ebx, 80070000h
0x18002e52a  lea     rcx, [rsp+28h+TokenHandle]; this
0x18002e52f  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18002e534  jmp     short loc_18002E55A
0x18002e536  mov     rdx, [rsp+28h+TokenHandle]; void *
0x18002e53b  mov     rcx, rbx; struct User *
0x18002e53e  call    ?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z; User::FromImpersonationToken(User &,void *)
0x18002e543  mov     ebx, eax
0x18002e545  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18002e54a  lea     rdx, [rcx-1]
0x18002e54e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002e552  ja      short loc_18002E55A
0x18002e554  call    cs:__imp_CloseHandle
0x18002e55a  mov     eax, ebx
0x18002e55c  add     rsp, 20h
0x18002e560  pop     rbx
0x18002e561  retn
```
