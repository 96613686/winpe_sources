# MyRtlAdjustPrivilege

- ea: `0x140031970`
- end: `0x140031a81`
- name: `MyRtlAdjustPrivilege`
- size: `273`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140034270`
- `0x1400877f0`
- `0x140089844`
- `0x14008b7bc`
- `0x1400934bc`

## callees

- `0x140031970`
- `0x140053720`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x140031a08`
- `ntdll!NtAdjustPrivilegesToken` at `0x140031a08`
- `ntdll!NtOpenThreadToken` at `0x140031a6a`
- `ntdll!NtOpenThreadToken` at `0x140031a6a`
- `ntdll!NtOpenProcessToken` at `0x1400319bc`
- `ntdll!NtOpenProcessToken` at `0x1400319bc`
- `ntdll!NtClose` at `0x140031a15`
- `ntdll!NtClose` at `0x140031a15`

## pseudocode

```c
NTSTATUS __fastcall MyRtlAdjustPrivilege(unsigned int a1, bool a2, char a3, bool *a4)
{
  LUID v4; // rbx
  NTSTATUS result; // eax
  NTSTATUS v8; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-40h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-28h] BYREF

  v4 = (LUID)a1;
  TokenHandle = 0;
  ReturnLength = 0;
  if ( a3 == 1 )
    result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 1u, &TokenHandle);
  else
    result = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, &TokenHandle);
  if ( result >= 0 )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = v4;
    NewState.Privileges[0].Attributes = a2 ? 2 : 0;
    v8 = NtAdjustPrivilegesToken(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
    NtClose(TokenHandle);
    if ( v8 == 262 )
      return -1073741727;
    if ( v8 >= 0 )
    {
      if ( PreviousState.PrivilegeCount )
        *a4 = (PreviousState.Privileges[0].Attributes & 2) != 0;
      else
        *a4 = a2;
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140031970  mov     [rsp+arg_0], rbx
0x140031975  mov     [rsp+arg_8], rsi
0x14003197a  push    rdi
0x14003197b  sub     rsp, 70h
0x14003197f  mov     rax, cs:__security_cookie
0x140031986  xor     rax, rsp
0x140031989  mov     [rsp+78h+var_18], rax
0x14003198e  xor     eax, eax
0x140031990  mov     ebx, ecx
0x140031992  mov     [rsp+78h+TokenHandle], rax
0x140031997  movzx   edi, dl
0x14003199a  mov     [rsp+78h+var_40], eax
0x14003199e  mov     rsi, r9
0x1400319a1  mov     edx, 28h ; '('; DesiredAccess
0x1400319a6  cmp     r8b, 1
0x1400319aa  jz      loc_140031A5B
0x1400319b0  lea     r8, [rsp+78h+TokenHandle]; TokenHandle
0x1400319b5  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400319bc  call    cs:__imp_NtOpenProcessToken
0x1400319c2  test    eax, eax
0x1400319c4  js      short loc_140031A29
0x1400319c6  movzx   eax, dil
0x1400319ca  mov     [rsp+78h+NewState.PrivilegeCount], 1
0x1400319d2  neg     al
0x1400319d4  mov     qword ptr [rsp+78h+NewState.Privileges.Luid.LowPart], rbx
0x1400319d9  lea     rax, [rsp+78h+var_40]
0x1400319de  mov     r9d, 10h; BufferLength
0x1400319e4  sbb     ecx, ecx
0x1400319e6  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1400319eb  and     ecx, 2
0x1400319ee  lea     rax, [rsp+78h+var_28]
0x1400319f3  mov     [rsp+78h+NewState.Privileges.Attributes], ecx
0x1400319f7  lea     r8, [rsp+78h+NewState]; NewState
0x1400319fc  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x140031a01  xor     edx, edx; DisableAllPrivileges
0x140031a03  mov     [rsp+78h+PreviousState], rax; PreviousState
0x140031a08  call    cs:__imp_NtAdjustPrivilegesToken
0x140031a0e  mov     rcx, [rsp+78h+TokenHandle]; Handle
0x140031a13  mov     ebx, eax
0x140031a15  call    cs:__imp_NtClose
0x140031a1b  cmp     ebx, 106h
0x140031a21  jz      short loc_140031A75
0x140031a23  test    ebx, ebx
0x140031a25  jns     short loc_140031A48
0x140031a27  mov     eax, ebx
0x140031a29  mov     rcx, [rsp+78h+var_18]
0x140031a2e  xor     rcx, rsp; StackCookie
0x140031a31  call    __security_check_cookie
0x140031a36  lea     r11, [rsp+78h+var_8]
0x140031a3b  mov     rbx, [r11+10h]
0x140031a3f  mov     rsi, [r11+18h]
0x140031a43  mov     rsp, r11
0x140031a46  pop     rdi
0x140031a47  retn
0x140031a48  cmp     [rsp+78h+var_28.PrivilegeCount], 0
0x140031a4d  jz      short loc_140031A7C
0x140031a4f  mov     eax, [rsp+78h+var_28.Privileges.Attributes]
0x140031a53  shr     eax, 1
0x140031a55  and     al, 1
0x140031a57  mov     [rsi], al
0x140031a59  jmp     short loc_140031A27
0x140031a5b  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x140031a60  mov     r8b, 1; OpenAsSelf
0x140031a63  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140031a6a  call    cs:__imp_NtOpenThreadToken
0x140031a70  jmp     loc_1400319C2
0x140031a75  mov     ebx, 0C0000061h
0x140031a7a  jmp     short loc_140031A27
0x140031a7c  mov     [rsi], dil
0x140031a7f  jmp     short loc_140031A27
```
