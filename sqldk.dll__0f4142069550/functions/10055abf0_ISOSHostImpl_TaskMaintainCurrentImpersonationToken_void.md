# ISOSHostImpl::TaskMaintainCurrentImpersonationToken(void)

- ea: `0x10055abf0`
- end: `0x10055aca9`
- name: `?TaskMaintainCurrentImpersonationToken@ISOSHostImpl@@UEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(ISOSHostImpl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callees

- `0x1004131c0`
- `0x100413250`
- `0x10055abf0`
- `0x100560ef0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x10055ac3a`
- `KERNEL32!GetCurrentThread` at `0x10055ac3a`
- `KERNEL32!GetLastError` at `0x10055ac59`
- `KERNEL32!GetLastError` at `0x10055ac59`
- `ADVAPI32!OpenThreadToken` at `0x10055ac4f`
- `ADVAPI32!OpenThreadToken` at `0x10055ac4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ISOSHostImpl::TaskMaintainCurrentImpersonationToken(ISOSHostImpl *this)
{
  unsigned int v1; // ebx
  _BYTE *v2; // rcx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v5; // rcx
  _BYTE v7[4]; // [rsp+28h] [rbp-20h] BYREF
  int v8; // [rsp+2Ch] [rbp-1Ch]
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v11; // [rsp+58h] [rbp+10h]

  TokenHandle = this;
  v1 = 0;
  v11 = v9;
  v8 = 0;
  v8 = ExtIntCodeProtector<0>::Pre(v7);
  v2 = v7;
  if ( v8 < 0 )
    v2 = 0;
  v9[0] = v2;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    v5 = TokenHandle;
  }
  else
  {
    LastError = GetLastError();
    v5 = 0;
    TokenHandle = 0;
    if ( LastError != 1008 && LastError != 1309 )
    {
      v1 = -2147221500;
      goto LABEL_9;
    }
  }
  SOS_Task::MaintainToken(v5);
LABEL_9:
  TokenHandle = v9;
  if ( v9[0] )
    SOS_Task::SetInExternalCode(*(_DWORD *)v9[0]);
  return v1;
}

```

## disassembly

```asm
0x10055abf0  mov     [rsp+TokenHandle], rcx
0x10055abf5  push    rbx
0x10055abf6  sub     rsp, 40h
0x10055abfa  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x10055ac03  xor     ebx, ebx
0x10055ac05  mov     [rsp+48h+var_1C], ebx
0x10055ac09  lea     rax, [rsp+48h+var_18]
0x10055ac0e  mov     [rsp+48h+arg_8], rax
0x10055ac13  mov     [rsp+48h+var_1C], ebx
0x10055ac17  lea     rcx, [rsp+48h+var_20]
0x10055ac1c  call    ?Pre@?$ExtIntCodeProtector@$0A@@@QEAAJXZ; ExtIntCodeProtector<0>::Pre(void)
0x10055ac21  mov     [rsp+48h+var_1C], eax
0x10055ac25  lea     rcx, [rsp+48h+var_20]
0x10055ac2a  test    eax, eax
0x10055ac2c  cmovs   rcx, rbx
0x10055ac30  mov     [rsp+48h+var_18], rcx
0x10055ac35  mov     [rsp+48h+TokenHandle], rbx
0x10055ac3a  call    cs:__imp_GetCurrentThread
0x10055ac40  mov     rcx, rax; ThreadHandle
0x10055ac43  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x10055ac48  lea     edx, [rbx+0Ch]; DesiredAccess
0x10055ac4b  lea     r8d, [rbx+1]; OpenAsSelf
0x10055ac4f  call    cs:__imp_OpenThreadToken
0x10055ac55  test    eax, eax
0x10055ac57  jnz     short loc_10055AC7B
0x10055ac59  call    cs:__imp_GetLastError
0x10055ac5f  mov     ecx, ebx
0x10055ac61  mov     [rsp+48h+TokenHandle], rbx
0x10055ac66  cmp     eax, 3F0h
0x10055ac6b  jz      short loc_10055AC80
0x10055ac6d  cmp     eax, 51Dh
0x10055ac72  jz      short loc_10055AC80
0x10055ac74  mov     ebx, 80040004h
0x10055ac79  jmp     short loc_10055AC86
0x10055ac7b  mov     rcx, [rsp+48h+TokenHandle]; void *
0x10055ac80  call    ?MaintainToken@SOS_Task@@SAXPEAX@Z; SOS_Task::MaintainToken(void *)
0x10055ac85  nop
0x10055ac86  lea     rax, [rsp+48h+var_18]
0x10055ac8b  mov     [rsp+48h+TokenHandle], rax
0x10055ac90  mov     rax, [rsp+48h+var_18]
0x10055ac95  test    rax, rax
0x10055ac98  jz      short loc_10055ACA1
0x10055ac9a  mov     ecx, [rax]; int
0x10055ac9c  call    ?SetInExternalCode@SOS_Task@@SAXH@Z; SOS_Task::SetInExternalCode(int)
0x10055aca1  mov     eax, ebx
0x10055aca3  add     rsp, 40h
0x10055aca7  pop     rbx
0x10055aca8  retn
```
