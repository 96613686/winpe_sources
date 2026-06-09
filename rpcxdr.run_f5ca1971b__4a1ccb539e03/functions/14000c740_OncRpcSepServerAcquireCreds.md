# OncRpcSepServerAcquireCreds

- ea: `0x14000c740`
- end: `0x14000c7ed`
- name: `OncRpcSepServerAcquireCreds`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a2d0`

## callees

- `0x1400020c0`
- `0x14000a1ec`
- `0x14000c740`

## import_xrefs

- `ksecdd!MapSecurityError` at `0x14000c79f`
- `ksecdd!MapSecurityError` at `0x14000c79f`
- `ksecdd!AcquireCredentialsHandleW` at `0x14000c78a`
- `ksecdd!AcquireCredentialsHandleW` at `0x14000c78a`

## pseudocode

```c
__int64 __fastcall OncRpcSepServerAcquireCreds(_DWORD *a1, struct _SecHandle *a2, SECURITY_INTEGER *a3)
{
  unsigned int v4; // eax
  SECURITY_STATUS v5; // ecx
  unsigned int v6; // ebx
  UNICODE_STRING v8; // [rsp+50h] [rbp-18h] BYREF

  v8.Buffer = L"Kerberos";
  *(_QWORD *)&v8.Length = 1179664;
  v4 = AcquireCredentialsHandleW(0, &v8, 1u, 0, 0, 0, 0, a2, a3);
  *a1 = OncRpcSeSecStatusToGssMajor(v4);
  v6 = MapSecurityError(v5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x14000c740  mov     r11, rsp
0x14000c743  mov     [r11+8], rbx
0x14000c747  push    rdi
0x14000c748  sub     rsp, 60h
0x14000c74c  mov     [r11-28h], r8
0x14000c750  lea     rax, aKerberos; "Kerberos"
0x14000c757  mov     [r11-30h], rdx
0x14000c75b  mov     rbx, rcx
0x14000c75e  mov     [r11-10h], rax
0x14000c762  lea     rdx, [r11-18h]; pPackage
0x14000c766  xor     eax, eax
0x14000c768  mov     qword ptr [r11-18h], 120010h
0x14000c770  mov     [r11-38h], rax
0x14000c774  mov     edi, 12h
0x14000c779  mov     [r11-40h], rax
0x14000c77d  xor     r9d, r9d; pvLogonId
0x14000c780  xor     ecx, ecx; pPrincipal
0x14000c782  mov     [r11-48h], rax
0x14000c786  lea     r8d, [rdi-11h]; fCredentialUse
0x14000c78a  call    cs:__imp_AcquireCredentialsHandleW
0x14000c791  nop     dword ptr [rax+rax+00h]
0x14000c796  mov     ecx, eax
0x14000c798  call    OncRpcSeSecStatusToGssMajor
0x14000c79d  mov     [rbx], eax
0x14000c79f  call    cs:__imp_MapSecurityError
0x14000c7a6  nop     dword ptr [rax+rax+00h]
0x14000c7ab  mov     ebx, eax
0x14000c7ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c7b4  lea     rax, WPP_GLOBAL_Control
0x14000c7bb  cmp     rcx, rax
0x14000c7be  jz      short loc_14000C7DF
0x14000c7c0  mov     r8d, [rcx+2Ch]
0x14000c7c4  test    r8b, 1
0x14000c7c8  jz      short loc_14000C7DF
0x14000c7ca  mov     rcx, [rcx+18h]
0x14000c7ce  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000c7d5  mov     edx, edi
0x14000c7d7  mov     r9d, ebx
0x14000c7da  call    WPP_SF_d
0x14000c7df  mov     eax, ebx
0x14000c7e1  mov     rbx, [rsp+68h+arg_0]
0x14000c7e6  add     rsp, 60h
0x14000c7ea  pop     rdi
0x14000c7eb  retn
```
