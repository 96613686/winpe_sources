# IsTokenUserGrantedCapability

- ea: `0x1800377ac`
- end: `0x1800378ef`
- name: `IsTokenUserGrantedCapability`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180012ca0`

## callees

- `0x1800377ac`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800377f3`
- `ntdll!RtlInitializeSid` at `0x180037845`
- `ntdll!RtlInitializeSid` at `0x1800377f3`
- `ntdll!RtlInitializeSid` at `0x180037845`
- `ntdll!RtlSubAuthoritySid` at `0x1800377ff`
- `ntdll!RtlSubAuthoritySid` at `0x180037851`
- `ntdll!RtlSubAuthoritySid` at `0x180037866`
- `ntdll!RtlSubAuthoritySid` at `0x18003787b`
- `ntdll!RtlSubAuthoritySid` at `0x180037890`
- `ntdll!RtlSubAuthoritySid` at `0x1800378a5`
- `ntdll!RtlSubAuthoritySid` at `0x1800377ff`
- `ntdll!RtlSubAuthoritySid` at `0x180037851`
- `ntdll!RtlSubAuthoritySid` at `0x180037866`
- `ntdll!RtlSubAuthoritySid` at `0x18003787b`
- `ntdll!RtlSubAuthoritySid` at `0x180037890`
- `ntdll!RtlSubAuthoritySid` at `0x1800378a5`
- `ntdll!RtlCheckTokenMembershipEx` at `0x180037821`
- `ntdll!RtlCheckTokenMembershipEx` at `0x1800378bf`
- `ntdll!RtlCheckTokenMembershipEx` at `0x180037821`
- `ntdll!RtlCheckTokenMembershipEx` at `0x1800378bf`

## pseudocode

```c
__int64 __fastcall IsTokenUserGrantedCapability(__int64 a1, char a2, _BYTE *a3)
{
  __int64 result; // rax
  char v7; // cl
  _BYTE v8[4]; // [rsp+20h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+24h] [rbp-3Ch] BYREF
  _BYTE Sid[32]; // [rsp+30h] [rbp-30h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v8[0] = 0;
  RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(Sid, 0) = 18;
  result = RtlCheckTokenMembershipEx(a1, Sid, a2 != 0, v8);
  if ( (int)result >= 0 )
  {
    v7 = v8[0];
    if ( !v8[0] )
    {
      RtlInitializeSid(Sid, &IdentifierAuthority, 5u);
      *RtlSubAuthoritySid(Sid, 0) = 21;
      *RtlSubAuthoritySid(Sid, 1u) = -1592088623;
      *RtlSubAuthoritySid(Sid, 2u) = 795188819;
      *RtlSubAuthoritySid(Sid, 3u) = 444038987;
      *RtlSubAuthoritySid(Sid, 4u) = 1030;
      result = RtlCheckTokenMembershipEx(a1, Sid, a2 != 0, v8);
      if ( (int)result < 0 )
        return result;
      v7 = v8[0];
    }
    *a3 = v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800377ac  mov     [rsp-18h+arg_8], rbx
0x1800377b1  mov     [rsp-18h+arg_18], rsi
0x1800377b6  push    rbp
0x1800377b7  push    rdi
0x1800377b8  push    r14
0x1800377ba  mov     rbp, rsp
0x1800377bd  sub     rsp, 60h
0x1800377c1  mov     rax, cs:__security_cookie
0x1800377c8  xor     rax, rsp
0x1800377cb  mov     [rbp+var_10], rax
0x1800377cf  mov     rdi, r8
0x1800377d2  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x1800377d9  mov     bl, dl
0x1800377db  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1800377e1  mov     r14, rcx
0x1800377e4  mov     [rbp+var_40], 0
0x1800377e8  mov     r8b, 1; SubAuthorityCount
0x1800377eb  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1800377ef  lea     rcx, [rbp+Sid]; Sid
0x1800377f3  call    cs:__imp_RtlInitializeSid
0x1800377f9  xor     edx, edx; SubAuthority
0x1800377fb  lea     rcx, [rbp+Sid]; Sid
0x1800377ff  call    cs:__imp_RtlSubAuthoritySid
0x180037805  xor     esi, esi
0x180037807  lea     r9, [rbp+var_40]
0x18003780b  test    bl, bl
0x18003780d  lea     rdx, [rbp+Sid]
0x180037811  mov     rcx, r14
0x180037814  setnz   sil
0x180037818  mov     dword ptr [rax], 12h
0x18003781e  mov     r8d, esi
0x180037821  call    cs:__imp_RtlCheckTokenMembershipEx
0x180037827  test    eax, eax
0x180037829  js      loc_1800378CE
0x18003782f  mov     cl, [rbp+var_40]
0x180037832  test    cl, cl
0x180037834  jnz     loc_1800378CC
0x18003783a  mov     r8b, 5; SubAuthorityCount
0x18003783d  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180037841  lea     rcx, [rbp+Sid]; Sid
0x180037845  call    cs:__imp_RtlInitializeSid
0x18003784b  xor     edx, edx; SubAuthority
0x18003784d  lea     rcx, [rbp+Sid]; Sid
0x180037851  call    cs:__imp_RtlSubAuthoritySid
0x180037857  mov     edx, 1; SubAuthority
0x18003785c  lea     rcx, [rbp+Sid]; Sid
0x180037860  mov     dword ptr [rax], 15h
0x180037866  call    cs:__imp_RtlSubAuthoritySid
0x18003786c  mov     edx, 2; SubAuthority
0x180037871  lea     rcx, [rbp+Sid]; Sid
0x180037875  mov     dword ptr [rax], 0A11AA7D1h
0x18003787b  call    cs:__imp_RtlSubAuthoritySid
0x180037881  mov     edx, 3; SubAuthority
0x180037886  lea     rcx, [rbp+Sid]; Sid
0x18003788a  mov     dword ptr [rax], 2F659E53h
0x180037890  call    cs:__imp_RtlSubAuthoritySid
0x180037896  mov     edx, 4; SubAuthority
0x18003789b  lea     rcx, [rbp+Sid]; Sid
0x18003789f  mov     dword ptr [rax], 1A777F4Bh
0x1800378a5  call    cs:__imp_RtlSubAuthoritySid
0x1800378ab  lea     r9, [rbp+var_40]
0x1800378af  mov     r8d, esi
0x1800378b2  lea     rdx, [rbp+Sid]
0x1800378b6  mov     rcx, r14
0x1800378b9  mov     dword ptr [rax], 406h
0x1800378bf  call    cs:__imp_RtlCheckTokenMembershipEx
0x1800378c5  test    eax, eax
0x1800378c7  js      short loc_1800378CE
0x1800378c9  mov     cl, [rbp+var_40]
0x1800378cc  mov     [rdi], cl
0x1800378ce  mov     rcx, [rbp+var_10]
0x1800378d2  xor     rcx, rsp; StackCookie
0x1800378d5  call    __security_check_cookie
0x1800378da  lea     r11, [rsp+60h+var_s0]
0x1800378df  mov     rbx, [r11+28h]
0x1800378e3  mov     rsi, [r11+38h]
0x1800378e7  mov     rsp, r11
0x1800378ea  pop     r14
0x1800378ec  pop     rdi
0x1800378ed  pop     rbp
0x1800378ee  retn
```
