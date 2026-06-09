# TaskAccessChecker::TaskAccessChecker(void)

- ea: `0x18007545c`
- end: `0x180075593`
- name: `??0TaskAccessChecker@@QEAA@XZ`
- size: `311`
- prototype: `TaskAccessChecker *__fastcall(TaskAccessChecker *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x18005105c`
- `0x180075c4c`

## callees

- `0x18001351c`
- `0x18002f35c`
- `0x18002f3e0`
- `0x180040590`
- `0x18005790c`
- `0x18007545c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007552a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007552a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007550a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007550a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180075520`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180075520`
- `RPCRT4!RpcRevertToSelf` at `0x180075574`
- `RPCRT4!RpcRevertToSelf` at `0x180075574`

## string_xrefs

- `0x18007548e`: `TaskAccessChecker::TaskAccessChecker`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
TaskAccessChecker *__fastcall TaskAccessChecker::TaskAccessChecker(TaskAccessChecker *this)
{
  struct User *v2; // rdi
  int v3; // eax
  tsched *v4; // rcx
  bool v5; // zf
  char v6; // al
  HANDLE CurrentThread; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v10; // [rsp+28h] [rbp-38h]
  const unsigned __int16 *v11; // [rsp+30h] [rbp-30h]
  __int64 v12; // [rsp+38h] [rbp-28h]
  __int64 v13; // [rsp+40h] [rbp-20h]
  DWORD LastError; // [rsp+48h] [rbp-18h]
  __int64 v15; // [rsp+4Ch] [rbp-14h]
  int v16; // [rsp+88h] [rbp+28h] BYREF

  *(_BYTE *)this = 0;
  v2 = (TaskAccessChecker *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v16, L"TaskAccessChecker::TaskAccessChecker", 1);
  v3 = User::FromImpersonationToken(v2, 0);
  if ( v3 < 0 )
  {
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = &qword_1800A4718;
    v12 = 0;
    v13 = 0;
    LastError = (unsigned __int16)v3;
    v15 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( (unsigned int)tsched::IsUserAdmin(v4) || (v5 = !User::IsLocalSystem(v2), v6 = 0, !v5) )
    v6 = 1;
  *(_BYTE *)this = v6;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)this + 2) )
  {
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = &qword_1800A4718;
    v12 = 0;
    v13 = 0;
    LastError = GetLastError();
    v15 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( v16 )
    RpcRevertToSelf();
  return this;
}

```

## disassembly

```asm
0x18007545c  mov     [rsp-18h+arg_10], rbx
0x180075461  mov     [rsp-18h+arg_18], rsi
0x180075466  mov     [rsp-18h+arg_0], rcx
0x18007546b  push    rbp
0x18007546c  push    rdi
0x18007546d  push    r14
0x18007546f  mov     rbp, rsp
0x180075472  sub     rsp, 60h
0x180075476  mov     rbx, rcx
0x180075479  xor     r14d, r14d
0x18007547c  mov     [rcx], r14b
0x18007547f  lea     rdi, [rcx+8]
0x180075483  mov     [rdi], r14
0x180075486  mov     [rcx+10h], r14
0x18007548a  lea     r8d, [r14+1]; int
0x18007548e  lea     rdx, aTaskaccesschec; "TaskAccessChecker::TaskAccessChecker"
0x180075495  lea     rcx, [rbp+arg_8]; this
0x180075499  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18007549e  nop
0x18007549f  xor     edx, edx; void *
0x1800754a1  mov     rcx, rdi; struct User *
0x1800754a4  call    ?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z; User::FromImpersonationToken(User &,void *)
0x1800754a9  test    eax, eax
0x1800754ab  jns     short loc_1800754EE
0x1800754ad  mov     [rbp+var_38], r14b
0x1800754b1  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800754b8  mov     [rbp+pExceptionObject], rcx
0x1800754bc  lea     rcx, qword_1800A4718
0x1800754c3  mov     [rbp+var_30], rcx
0x1800754c7  mov     [rbp+var_28], r14
0x1800754cb  mov     [rbp+var_20], r14
0x1800754cf  movzx   eax, ax
0x1800754d2  mov     [rbp+var_18], eax
0x1800754d5  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800754dd  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800754e4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800754e8  call    _CxxThrowException_0
0x1800754ee  call    ?IsUserAdmin@tsched@@YAHXZ; tsched::IsUserAdmin(void)
0x1800754f3  test    eax, eax
0x1800754f5  jnz     short loc_180075506
0x1800754f7  mov     rcx, rdi; this
0x1800754fa  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x1800754ff  test    al, al
0x180075501  mov     al, r14b
0x180075504  jz      short loc_180075508
0x180075506  mov     al, 1
0x180075508  mov     [rbx], al
0x18007550a  call    cs:__imp_GetCurrentThread
0x180075510  lea     r9, [rbx+10h]; TokenHandle
0x180075514  mov     edx, 8; DesiredAccess
0x180075519  lea     r8d, [rdx-7]; OpenAsSelf
0x18007551d  mov     rcx, rax; ThreadHandle
0x180075520  call    cs:__imp_OpenThreadToken
0x180075526  test    eax, eax
0x180075528  jnz     short loc_18007556E
0x18007552a  call    cs:__imp_GetLastError
0x180075530  mov     [rbp+var_38], r14b
0x180075534  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18007553b  mov     [rbp+pExceptionObject], rcx
0x18007553f  lea     rcx, qword_1800A4718
0x180075546  mov     [rbp+var_30], rcx
0x18007554a  mov     [rbp+var_28], r14
0x18007554e  mov     [rbp+var_20], r14
0x180075552  mov     [rbp+var_18], eax
0x180075555  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18007555d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180075564  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180075568  call    _CxxThrowException_0
0x18007556e  cmp     [rbp+arg_8], r14d
0x180075572  jz      short loc_18007557B
0x180075574  call    cs:__imp_RpcRevertToSelf
0x18007557a  nop
0x18007557b  mov     rax, rbx
0x18007557e  lea     r11, [rsp+60h+var_s0]
0x180075583  mov     rbx, [r11+30h]
0x180075587  mov     rsi, [r11+38h]
0x18007558b  mov     rsp, r11
0x18007558e  pop     r14
0x180075590  pop     rdi
0x180075591  pop     rbp
0x180075592  retn
```
