# SrvLibGetSelfSid

- ea: `0x14004e900`
- end: `0x14004ea1a`
- name: `SrvLibGetSelfSid`
- size: `282`
- prototype: `__int64 __fastcall(PSID DestinationSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140029030`

## callees

- `0x14002a3e0`
- `0x14004e900`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x14004e9ea`
- `ntoskrnl!RtlCopySid` at `0x14004e9ea`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14004e961`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14004e961`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14004e98a`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14004e98a`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004e9ba`
- `ntoskrnl!ZwQueryInformationToken` at `0x14004e9ba`
- `ntoskrnl!ZwClose` at `0x14004e9cd`
- `ntoskrnl!ZwClose` at `0x14004e9cd`

## pseudocode

```c
__int64 __fastcall SrvLibGetSelfSid(PSID DestinationSid)
{
  NTSTATUS v2; // ebx
  HANDLE Handle; // [rsp+30h] [rbp-88h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  Handle = 0;
  ReturnLength = 0;
  if ( DestinationSid )
  {
    v2 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x20008u, 1u, 0x200u, &Handle);
    if ( v2 == -1073741700 )
      v2 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20008u, 0x200u, &Handle);
    if ( v2 >= 0 )
    {
      v2 = ZwQueryInformationToken(Handle, TokenUser, TokenInformation, 0x58u, &ReturnLength);
      ZwClose(Handle);
      if ( v2 >= 0 )
        RtlCopySid(0x44u, DestinationSid, TokenInformation[0]);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14004e900  mov     [rsp+arg_8], rbx
0x14004e905  push    rdi
0x14004e906  sub     rsp, 0B0h
0x14004e90d  mov     rax, cs:__security_cookie
0x14004e914  xor     rax, rsp
0x14004e917  mov     [rsp+0B8h+var_18], rax
0x14004e91f  mov     [rsp+0B8h+Handle], 0
0x14004e928  mov     rdi, rcx
0x14004e92b  mov     [rsp+0B8h+ReturnLength], 0
0x14004e933  test    rcx, rcx
0x14004e936  jnz     short loc_14004E942
0x14004e938  mov     ebx, 0C000000Dh
0x14004e93d  jmp     loc_14004E9F6
0x14004e942  lea     rax, [rsp+0B8h+Handle]
0x14004e947  mov     r9d, 200h; HandleAttributes
0x14004e94d  mov     r8b, 1; OpenAsSelf
0x14004e950  mov     [rsp+0B8h+TokenHandle], rax; TokenHandle
0x14004e955  mov     edx, 20008h; DesiredAccess
0x14004e95a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14004e961  call    cs:__imp_ZwOpenThreadTokenEx
0x14004e968  nop     dword ptr [rax+rax+00h]
0x14004e96d  mov     ebx, eax
0x14004e96f  cmp     eax, 0C000007Ch
0x14004e974  jnz     short loc_14004E998
0x14004e976  lea     r9, [rsp+0B8h+Handle]; TokenHandle
0x14004e97b  mov     edx, 20008h; DesiredAccess
0x14004e980  mov     r8d, 200h; HandleAttributes
0x14004e986  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14004e98a  call    cs:__imp_ZwOpenProcessTokenEx
0x14004e991  nop     dword ptr [rax+rax+00h]
0x14004e996  mov     ebx, eax
0x14004e998  test    ebx, ebx
0x14004e99a  js      short loc_14004E9F6
0x14004e99c  mov     rcx, [rsp+0B8h+Handle]; TokenHandle
0x14004e9a1  lea     rax, [rsp+0B8h+ReturnLength]
0x14004e9a6  mov     r9d, 58h ; 'X'; TokenInformationLength
0x14004e9ac  mov     [rsp+0B8h+TokenHandle], rax; ReturnLength
0x14004e9b1  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x14004e9b6  lea     edx, [r9-57h]; TokenInformationClass
0x14004e9ba  call    cs:__imp_ZwQueryInformationToken
0x14004e9c1  nop     dword ptr [rax+rax+00h]
0x14004e9c6  mov     rcx, [rsp+0B8h+Handle]; Handle
0x14004e9cb  mov     ebx, eax
0x14004e9cd  call    cs:__imp_ZwClose
0x14004e9d4  nop     dword ptr [rax+rax+00h]
0x14004e9d9  test    ebx, ebx
0x14004e9db  js      short loc_14004E9F6
0x14004e9dd  mov     r8, [rsp+0B8h+TokenInformation]; SourceSid
0x14004e9e2  mov     rdx, rdi; DestinationSid
0x14004e9e5  mov     ecx, 44h ; 'D'; DestinationSidLength
0x14004e9ea  call    cs:__imp_RtlCopySid
0x14004e9f1  nop     dword ptr [rax+rax+00h]
0x14004e9f6  mov     eax, ebx
0x14004e9f8  mov     rcx, [rsp+0B8h+var_18]
0x14004ea00  xor     rcx, rsp; StackCookie
0x14004ea03  call    __security_check_cookie
0x14004ea08  mov     rbx, [rsp+0B8h+arg_8]
0x14004ea10  add     rsp, 0B0h
0x14004ea17  pop     rdi
0x14004ea18  retn
```
