# BfAdjustPrivilege(ulong,uchar,uchar *)

- ea: `0x18003cce0`
- end: `0x18003ce4a`
- name: `?BfAdjustPrivilege@@YAJKEPEAE@Z`
- size: `362`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003cae4`
- `0x18003cc38`

## callees

- `0x18000d030`
- `0x18003cce0`

## import_xrefs

- `ntdll!NtClose` at `0x18003ce21`
- `ntdll!NtClose` at `0x18003ce21`
- `ntdll!NtOpenThreadTokenEx` at `0x18003cd56`
- `ntdll!NtOpenThreadTokenEx` at `0x18003cd78`
- `ntdll!NtOpenThreadTokenEx` at `0x18003cd56`
- `ntdll!NtOpenThreadTokenEx` at `0x18003cd78`
- `ntdll!NtOpenProcessTokenEx` at `0x18003cd8e`
- `ntdll!NtOpenProcessTokenEx` at `0x18003cd8e`
- `ntdll!NtAdjustPrivilegesToken` at `0x18003cddf`
- `ntdll!NtAdjustPrivilegesToken` at `0x18003cddf`

## pseudocode

```c
__int64 __fastcall BfAdjustPrivilege(DWORD a1, char a2, bool *a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  HANDLE Handle; // [rsp+30h] [rbp-40h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  ReturnLength = 0;
  Handle = (HANDLE)-1LL;
  NewState = 0;
  PreviousState = 0;
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    v6 = NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, 0x200u, &Handle);
LABEL_5:
    v7 = v6;
    if ( v6 < 0 )
      return v7;
    goto LABEL_6;
  }
  if ( NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 1u, 0x200u, &Handle) < 0 )
  {
    v6 = NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, 0x200u, &Handle);
    goto LABEL_5;
  }
LABEL_6:
  *(_QWORD *)&NewState.Privileges[0].Luid.HighPart = 0;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid.LowPart = a1;
  if ( a2 )
    NewState.Privileges[0].Attributes = 2;
  v8 = NtAdjustPrivilegesToken(Handle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
  v7 = v8;
  if ( v8 == 262 )
  {
    v7 = -1073741727;
  }
  else if ( v8 >= 0 )
  {
    if ( PreviousState.PrivilegeCount )
      *a3 = (PreviousState.Privileges[0].Attributes & 2) != 0;
    else
      *a3 = a2 != 0;
  }
  if ( Handle != (HANDLE)-1LL )
    NtClose(Handle);
  return v7;
}

```

## disassembly

```asm
0x18003cce0  mov     [rsp-18h+arg_0], rbx
0x18003cce5  mov     [rsp-18h+arg_8], rsi
0x18003ccea  push    rbp
0x18003cceb  push    rdi
0x18003ccec  push    r14
0x18003ccee  mov     rbp, rsp
0x18003ccf1  sub     rsp, 70h
0x18003ccf5  mov     rax, cs:__security_cookie
0x18003ccfc  xor     rax, rsp
0x18003ccff  mov     [rbp+var_10], rax
0x18003cd03  xorps   xmm0, xmm0
0x18003cd06  mov     [rbp+var_38], 0
0x18003cd0d  xorps   xmm1, xmm1
0x18003cd10  mov     [rbp+Handle], 0FFFFFFFFFFFFFFFFh
0x18003cd18  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18003cd1c  mov     sil, dl
0x18003cd1f  mov     rdi, r8
0x18003cd22  movups  xmmword ptr [rbp+PreviousState.PrivilegeCount], xmm1
0x18003cd26  mov     eax, gs:179Ch
0x18003cd2e  mov     r14d, ecx
0x18003cd31  mov     edx, 28h ; '('; DesiredAccess
0x18003cd36  test    eax, eax
0x18003cd38  jz      short loc_18003CD80
0x18003cd3a  lea     rax, [rbp+Handle]
0x18003cd3e  mov     rbx, 0FFFFFFFFFFFFFFFEh
0x18003cd45  mov     rcx, rbx; ThreadHandle
0x18003cd48  mov     [rsp+70h+TokenHandle], rax; TokenHandle
0x18003cd4d  mov     r9d, 200h; HandleAttributes
0x18003cd53  mov     r8b, 1; OpenAsSelf
0x18003cd56  call    cs:__imp_NtOpenThreadTokenEx
0x18003cd5c  test    eax, eax
0x18003cd5e  jns     short loc_18003CD9E
0x18003cd60  lea     rax, [rbp+Handle]
0x18003cd64  mov     r9d, 200h; HandleAttributes
0x18003cd6a  xor     r8d, r8d; OpenAsSelf
0x18003cd6d  mov     [rsp+70h+TokenHandle], rax; TokenHandle
0x18003cd72  lea     edx, [rbx+2Ah]; DesiredAccess
0x18003cd75  mov     rcx, rbx; ThreadHandle
0x18003cd78  call    cs:__imp_NtOpenThreadTokenEx
0x18003cd7e  jmp     short loc_18003CD94
0x18003cd80  lea     r9, [rbp+Handle]; TokenHandle
0x18003cd84  mov     r8d, 200h; HandleAttributes
0x18003cd8a  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18003cd8e  call    cs:__imp_NtOpenProcessTokenEx
0x18003cd94  mov     ebx, eax
0x18003cd96  test    eax, eax
0x18003cd98  js      loc_18003CE27
0x18003cd9e  mov     qword ptr [rbp+NewState.Privileges.Luid.HighPart], 0
0x18003cda6  mov     [rbp+NewState.PrivilegeCount], 1
0x18003cdad  mov     [rbp+NewState.Privileges.Luid.LowPart], r14d
0x18003cdb1  test    sil, sil
0x18003cdb4  jz      short loc_18003CDBD
0x18003cdb6  mov     [rbp+NewState.Privileges.Attributes], 2
0x18003cdbd  mov     rcx, [rbp+Handle]; TokenHandle
0x18003cdc1  lea     rax, [rbp+var_38]
0x18003cdc5  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003cdca  lea     r8, [rbp+NewState]; NewState
0x18003cdce  lea     rax, [rbp+PreviousState]
0x18003cdd2  mov     r9d, 10h; BufferLength
0x18003cdd8  xor     edx, edx; DisableAllPrivileges
0x18003cdda  mov     [rsp+70h+TokenHandle], rax; PreviousState
0x18003cddf  call    cs:__imp_NtAdjustPrivilegesToken
0x18003cde5  mov     ebx, eax
0x18003cde7  cmp     eax, 106h
0x18003cdec  jnz     short loc_18003CDF5
0x18003cdee  mov     ebx, 0C0000061h
0x18003cdf3  jmp     short loc_18003CE17
0x18003cdf5  test    eax, eax
0x18003cdf7  js      short loc_18003CE17
0x18003cdf9  cmp     [rbp+PreviousState.PrivilegeCount], 0
0x18003cdfd  jnz     short loc_18003CE09
0x18003cdff  test    sil, sil
0x18003ce02  setnz   al
0x18003ce05  mov     [rdi], al
0x18003ce07  jmp     short loc_18003CE17
0x18003ce09  test    byte ptr [rbp+PreviousState.Privileges.Attributes], 2
0x18003ce0d  jz      short loc_18003CE14
0x18003ce0f  mov     byte ptr [rdi], 1
0x18003ce12  jmp     short loc_18003CE17
0x18003ce14  mov     byte ptr [rdi], 0
0x18003ce17  mov     rcx, [rbp+Handle]; Handle
0x18003ce1b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003ce1f  jz      short loc_18003CE27
0x18003ce21  call    cs:__imp_NtClose
0x18003ce27  mov     eax, ebx
0x18003ce29  mov     rcx, [rbp+var_10]
0x18003ce2d  xor     rcx, rsp; StackCookie
0x18003ce30  call    __security_check_cookie
0x18003ce35  lea     r11, [rsp+70h+var_s0]
0x18003ce3a  mov     rbx, [r11+20h]
0x18003ce3e  mov     rsi, [r11+28h]
0x18003ce42  mov     rsp, r11
0x18003ce45  pop     r14
0x18003ce47  pop     rdi
0x18003ce48  pop     rbp
0x18003ce49  retn
```
