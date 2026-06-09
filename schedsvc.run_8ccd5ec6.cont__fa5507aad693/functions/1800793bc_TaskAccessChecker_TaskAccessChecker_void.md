# TaskAccessChecker::TaskAccessChecker(void)

- ea: `0x1800793bc`
- end: `0x18007950c`
- name: `??0TaskAccessChecker@@QEAA@XZ`
- size: `336`
- prototype: `TaskAccessChecker *__fastcall(TaskAccessChecker *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800535dc`
- `0x180079bfc`

## callees

- `0x180007b44`
- `0x180025de4`
- `0x180025e70`
- `0x180042200`
- `0x18005a2bc`
- `0x1800793bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079496`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007946a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007946a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079486`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079486`
- `RPCRT4!RpcRevertToSelf` at `0x1800794e6`
- `RPCRT4!RpcRevertToSelf` at `0x1800794e6`

## string_xrefs

- `0x1800793ee`: `TaskAccessChecker::TaskAccessChecker`

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
    v11 = &qword_1800A8718;
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
    v11 = &qword_1800A8718;
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
0x1800793bc  mov     [rsp-18h+arg_10], rbx
0x1800793c1  mov     [rsp-18h+arg_18], rsi
0x1800793c6  mov     [rsp-18h+arg_0], rcx
0x1800793cb  push    rbp
0x1800793cc  push    rdi
0x1800793cd  push    r14
0x1800793cf  mov     rbp, rsp
0x1800793d2  sub     rsp, 60h
0x1800793d6  mov     rbx, rcx
0x1800793d9  xor     r14d, r14d
0x1800793dc  mov     [rcx], r14b
0x1800793df  lea     rdi, [rcx+8]
0x1800793e3  mov     [rdi], r14
0x1800793e6  mov     [rcx+10h], r14
0x1800793ea  lea     r8d, [r14+1]; int
0x1800793ee  lea     rdx, aTaskaccesschec; "TaskAccessChecker::TaskAccessChecker"
0x1800793f5  lea     rcx, [rbp+arg_8]; this
0x1800793f9  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x1800793fe  nop
0x1800793ff  xor     edx, edx; void *
0x180079401  mov     rcx, rdi; struct User *
0x180079404  call    ?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z; User::FromImpersonationToken(User &,void *)
0x180079409  test    eax, eax
0x18007940b  jns     short loc_18007944E
0x18007940d  mov     [rbp+var_38], r14b
0x180079411  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180079418  mov     [rbp+pExceptionObject], rcx
0x18007941c  lea     rcx, qword_1800A8718
0x180079423  mov     [rbp+var_30], rcx
0x180079427  mov     [rbp+var_28], r14
0x18007942b  mov     [rbp+var_20], r14
0x18007942f  movzx   eax, ax
0x180079432  mov     [rbp+var_18], eax
0x180079435  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18007943d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180079444  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180079448  call    _CxxThrowException_0
0x18007944e  call    ?IsUserAdmin@tsched@@YAHXZ; tsched::IsUserAdmin(void)
0x180079453  test    eax, eax
0x180079455  jnz     short loc_180079466
0x180079457  mov     rcx, rdi; this
0x18007945a  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x18007945f  test    al, al
0x180079461  mov     al, r14b
0x180079464  jz      short loc_180079468
0x180079466  mov     al, 1
0x180079468  mov     [rbx], al
0x18007946a  call    cs:__imp_GetCurrentThread
0x180079471  nop     dword ptr [rax+rax+00h]
0x180079476  lea     r9, [rbx+10h]; TokenHandle
0x18007947a  mov     edx, 8; DesiredAccess
0x18007947f  lea     r8d, [rdx-7]; OpenAsSelf
0x180079483  mov     rcx, rax; ThreadHandle
0x180079486  call    cs:__imp_OpenThreadToken
0x18007948d  nop     dword ptr [rax+rax+00h]
0x180079492  test    eax, eax
0x180079494  jnz     short loc_1800794E0
0x180079496  call    cs:__imp_GetLastError
0x18007949d  nop     dword ptr [rax+rax+00h]
0x1800794a2  mov     [rbp+var_38], r14b
0x1800794a6  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800794ad  mov     [rbp+pExceptionObject], rcx
0x1800794b1  lea     rcx, qword_1800A8718
0x1800794b8  mov     [rbp+var_30], rcx
0x1800794bc  mov     [rbp+var_28], r14
0x1800794c0  mov     [rbp+var_20], r14
0x1800794c4  mov     [rbp+var_18], eax
0x1800794c7  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800794cf  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800794d6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800794da  call    _CxxThrowException_0
0x1800794e0  cmp     [rbp+arg_8], r14d
0x1800794e4  jz      short loc_1800794F3
0x1800794e6  call    cs:__imp_RpcRevertToSelf
0x1800794ed  nop     dword ptr [rax+rax+00h]
0x1800794f2  nop
0x1800794f3  mov     rax, rbx
0x1800794f6  lea     r11, [rsp+60h+var_s0]
0x1800794fb  mov     rbx, [r11+30h]
0x1800794ff  mov     rsi, [r11+38h]
0x180079503  mov     rsp, r11
0x180079506  pop     r14
0x180079508  pop     rdi
0x180079509  pop     rbp
0x18007950a  retn
```
