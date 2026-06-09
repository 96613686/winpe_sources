# EnablePrivilegeEx2

- ea: `0x180040cb4`
- end: `0x180040d97`
- name: `EnablePrivilegeEx2`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003eddc`

## callees

- `0x180040cb4`
- `0x1800607b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180040d3a`
- `KERNEL32!GetLastError` at `0x180040d3a`
- `KERNEL32!CloseHandle` at `0x180040d68`
- `KERNEL32!CloseHandle` at `0x180040d68`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180040d2a`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180040d2a`

## pseudocode

```c
__int64 __fastcall EnablePrivilegeEx2(int a1, DWORD a2, DWORD *a3, void **a4)
{
  void *v4; // r14
  unsigned int v5; // ebx
  DWORD v9; // [rsp+30h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES v10; // [rsp+38h] [rbp-28h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF

  v4 = *a4;
  v5 = 1;
  v9 = 0;
  *(_QWORD *)&v10.PrivilegeCount = a1;
  NewState.Privileges[0].Luid = (LUID)a1;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0;
  if ( !AdjustTokenPrivileges(v4, 0, &NewState, 0x10u, &v10, &v9) || GetLastError() )
  {
    v5 = 0;
  }
  else if ( a3 )
  {
    if ( v10.PrivilegeCount )
      *a3 = (v10.Privileges[0].Attributes >> 1) & 1;
    else
      *a3 = a2;
  }
  CloseHandle(v4);
  return v5;
}

```

## disassembly

```asm
0x180040cb4  mov     r11, rsp
0x180040cb7  mov     [r11+8], rbx
0x180040cbb  mov     [r11+10h], rsi
0x180040cbf  push    rbp
0x180040cc0  push    rdi
0x180040cc1  push    r14
0x180040cc3  mov     rbp, rsp
0x180040cc6  sub     rsp, 60h
0x180040cca  mov     rax, cs:__security_cookie
0x180040cd1  xor     rax, rsp
0x180040cd4  mov     [rbp+var_8], rax
0x180040cd8  mov     r14, [r9]
0x180040cdb  mov     ebx, 1
0x180040ce0  and     [rbp+var_30], 0
0x180040ce4  mov     rdi, r8
0x180040ce7  movsxd  rax, ecx
0x180040cea  lea     r8, [rbp+NewState]; NewState
0x180040cee  mov     dword ptr [rbp+var_28], eax
0x180040cf1  mov     esi, edx
0x180040cf3  shr     rax, 20h
0x180040cf7  lea     r9d, [rbx+0Fh]; BufferLength
0x180040cfb  mov     dword ptr [rbp+var_28+4], eax
0x180040cfe  mov     rax, [rbp+var_28]
0x180040d02  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x180040d06  mov     eax, edx
0x180040d08  neg     eax
0x180040d0a  mov     [rbp+NewState.PrivilegeCount], ebx
0x180040d0d  lea     rax, [rbp+var_30]
0x180040d11  sbb     ecx, ecx
0x180040d13  mov     [r11-50h], rax
0x180040d17  and     ecx, 2
0x180040d1a  lea     rax, [rbp+var_28]
0x180040d1e  mov     [rbp+NewState.Privileges.Attributes], ecx
0x180040d21  xor     edx, edx; DisableAllPrivileges
0x180040d23  mov     rcx, r14; TokenHandle
0x180040d26  mov     [r11-58h], rax
0x180040d2a  call    cs:__imp_AdjustTokenPrivileges
0x180040d31  nop     dword ptr [rax+rax+00h]
0x180040d36  test    eax, eax
0x180040d38  jz      short loc_180040D63
0x180040d3a  call    cs:__imp_GetLastError
0x180040d41  nop     dword ptr [rax+rax+00h]
0x180040d46  test    eax, eax
0x180040d48  jnz     short loc_180040D63
0x180040d4a  test    rdi, rdi
0x180040d4d  jz      short loc_180040D65
0x180040d4f  cmp     dword ptr [rbp+var_28], eax
0x180040d52  jnz     short loc_180040D58
0x180040d54  mov     [rdi], esi
0x180040d56  jmp     short loc_180040D65
0x180040d58  mov     eax, [rbp+var_1C]
0x180040d5b  shr     eax, 1
0x180040d5d  and     eax, ebx
0x180040d5f  mov     [rdi], eax
0x180040d61  jmp     short loc_180040D65
0x180040d63  xor     ebx, ebx
0x180040d65  mov     rcx, r14; hObject
0x180040d68  call    cs:__imp_CloseHandle
0x180040d6f  nop     dword ptr [rax+rax+00h]
0x180040d74  mov     eax, ebx
0x180040d76  mov     rcx, [rbp+var_8]
0x180040d7a  xor     rcx, rsp; StackCookie
0x180040d7d  call    __security_check_cookie
0x180040d82  lea     r11, [rsp+60h+var_s0]
0x180040d87  mov     rbx, [r11+20h]
0x180040d8b  mov     rsi, [r11+28h]
0x180040d8f  mov     rsp, r11
0x180040d92  pop     r14
0x180040d94  pop     rdi
0x180040d95  pop     rbp
0x180040d96  retn
```
