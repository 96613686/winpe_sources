# MpMatchPerServiceSidByObj

- ea: `0x14006bfb0`
- end: `0x14006c0c2`
- name: `MpMatchPerServiceSidByObj`
- size: `274`
- prototype: `__int64 __fastcall(PEPROCESS Process, PSID Sid)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x140037928`
- `0x1400387f0`
- `0x14006eba0`

## callees

- `0x1400118d0`
- `0x14006bfb0`
- `0x14006c0c4`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14006c07c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14006c07c`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14006c098`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14006c098`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14006c03e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14006c03e`
- `ntoskrnl!SeTokenObjectType` at `0x14006c04a`
- `ntoskrnl!RtlValidSid` at `0x14006bff2`
- `ntoskrnl!RtlValidSid` at `0x14006bff2`
- `ntoskrnl!ZwClose` at `0x14006c00c`
- `ntoskrnl!ZwClose` at `0x14006c00c`

## pseudocode

```c
char __fastcall MpMatchPerServiceSidByObj(PEPROCESS Process, PSID Sid)
{
  char v2; // di
  PACCESS_TOKEN v6; // rsi
  _BYTE v7[8]; // [rsp+40h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-20h] BYREF

  v2 = 0;
  Handle = 0;
  v7[0] = 0;
  if ( Process && Sid )
  {
    if ( RtlValidSid(Sid) )
    {
      v6 = PsReferencePrimaryToken(Process);
      if ( ObOpenObjectByPointer(v6, 0x200u, 0, 8u, (POBJECT_TYPE)SeTokenObjectType, 0, &Handle) >= 0 )
      {
        MpCheckTokenMembership(Handle, Sid, v7);
        v2 = v7[0];
      }
      if ( v6 )
        PsDereferencePrimaryToken(v6);
    }
    if ( Handle )
      ZwClose(Handle);
  }
  return v2;
}

```

## disassembly

```asm
0x14006bfb0  mov     [rsp+arg_10], rbx
0x14006bfb5  mov     [rsp+arg_18], rsi
0x14006bfba  push    rdi
0x14006bfbb  sub     rsp, 60h
0x14006bfbf  mov     rax, cs:__security_cookie
0x14006bfc6  xor     rax, rsp
0x14006bfc9  mov     [rsp+68h+var_18], rax
0x14006bfce  xor     dil, dil
0x14006bfd1  mov     [rsp+68h+Handle], 0
0x14006bfda  mov     [rsp+68h+var_28], dil
0x14006bfdf  mov     rbx, rdx
0x14006bfe2  mov     rsi, rcx
0x14006bfe5  test    rcx, rcx
0x14006bfe8  jz      short loc_14006C018
0x14006bfea  test    rdx, rdx
0x14006bfed  jz      short loc_14006C018
0x14006bfef  mov     rcx, rdx; Sid
0x14006bff2  call    cs:__imp_RtlValidSid
0x14006bff9  nop     dword ptr [rax+rax+00h]
0x14006bffe  test    al, al
0x14006c000  jnz     short loc_14006C03B
0x14006c002  mov     rcx, [rsp+68h+Handle]; Handle
0x14006c007  test    rcx, rcx
0x14006c00a  jz      short loc_14006C018
0x14006c00c  call    cs:__imp_ZwClose
0x14006c013  nop     dword ptr [rax+rax+00h]
0x14006c018  mov     al, dil
0x14006c01b  mov     rcx, [rsp+68h+var_18]
0x14006c020  xor     rcx, rsp; StackCookie
0x14006c023  call    __security_check_cookie
0x14006c028  lea     r11, [rsp+68h+var_8]
0x14006c02d  mov     rbx, [r11+20h]
0x14006c031  mov     rsi, [r11+28h]
0x14006c035  mov     rsp, r11
0x14006c038  pop     rdi
0x14006c039  retn
0x14006c03b  mov     rcx, rsi; Process
0x14006c03e  call    cs:__imp_PsReferencePrimaryToken
0x14006c045  nop     dword ptr [rax+rax+00h]
0x14006c04a  mov     rcx, cs:__imp_SeTokenObjectType
0x14006c051  mov     r9d, 8; DesiredAccess
0x14006c057  mov     rsi, rax
0x14006c05a  mov     edx, 200h; HandleAttributes
0x14006c05f  lea     rax, [rsp+68h+Handle]
0x14006c064  mov     [rsp+68h+var_38], rax; Handle
0x14006c069  mov     r8, [rcx]
0x14006c06c  mov     rcx, rsi; Object
0x14006c06f  mov     [rsp+68h+AccessMode], dil; AccessMode
0x14006c074  mov     [rsp+68h+ObjectType], r8; ObjectType
0x14006c079  xor     r8d, r8d; PassedAccessState
0x14006c07c  call    cs:__imp_ObOpenObjectByPointer
0x14006c083  nop     dword ptr [rax+rax+00h]
0x14006c088  test    eax, eax
0x14006c08a  jns     short loc_14006C0A9
0x14006c08c  test    rsi, rsi
0x14006c08f  jz      loc_14006C002
0x14006c095  mov     rcx, rsi; PrimaryToken
0x14006c098  call    cs:__imp_PsDereferencePrimaryToken
0x14006c09f  nop     dword ptr [rax+rax+00h]
0x14006c0a4  jmp     loc_14006C002
0x14006c0a9  mov     rcx, [rsp+68h+Handle]; ExistingTokenHandle
0x14006c0ae  lea     r8, [rsp+68h+var_28]
0x14006c0b3  mov     rdx, rbx; Sid
0x14006c0b6  call    MpCheckTokenMembership
0x14006c0bb  mov     dil, [rsp+68h+var_28]
0x14006c0c0  jmp     short loc_14006C08C
```
