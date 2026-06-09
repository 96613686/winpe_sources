# ATL::CAcl::GetLength(void)

- ea: `0x140001fb0`
- end: `0x14000202d`
- name: `?GetLength@CAcl@ATL@@QEBAIXZ`
- size: `125`
- prototype: `__int64 __fastcall(ATL::CAcl *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022d0`

## callees

- `0x140001fb0`
- `0x140002040`
- `0x140007298`
- `0x14000a2d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140002006`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140002006`

## pseudocode

```c
__int64 __fastcall ATL::CAcl::GetLength(ATL::CAcl *this)
{
  struct _ACL *PACL; // rax
  __int64 pAclInformation; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+28h] [rbp-20h]

  PACL = (struct _ACL *)ATL::CAcl::GetPACL(this);
  pAclInformation = 0;
  v5 = 0;
  if ( *((_BYTE *)this + 16) )
    return 0;
  if ( !GetAclInformation(PACL, &pAclInformation, 0xCu, AclSizeInformation) )
    ATL::AtlThrowLastWin32();
  return HIDWORD(pAclInformation);
}

```

## disassembly

```asm
0x140001fb0  push    rbx
0x140001fb2  sub     rsp, 40h
0x140001fb6  mov     rax, cs:__security_cookie
0x140001fbd  xor     rax, rsp
0x140001fc0  mov     [rsp+48h+var_18], rax
0x140001fc5  mov     rbx, rcx
0x140001fc8  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x140001fcd  xor     ecx, ecx
0x140001fcf  mov     [rsp+48h+pAclInformation], rcx
0x140001fd4  mov     [rsp+48h+var_20], ecx
0x140001fd8  cmp     [rbx+10h], cl
0x140001fdb  jz      short loc_140001FF2
0x140001fdd  xor     eax, eax
0x140001fdf  mov     rcx, [rsp+48h+var_18]
0x140001fe4  xor     rcx, rsp; StackCookie
0x140001fe7  call    __security_check_cookie
0x140001fec  add     rsp, 40h
0x140001ff0  pop     rbx
0x140001ff1  retn
0x140001ff2  mov     r9d, 2; dwAclInformationClass
0x140001ff8  lea     rdx, [rsp+48h+pAclInformation]; pAclInformation
0x140001ffd  mov     r8d, 0Ch; nAclInformationLength
0x140002003  mov     rcx, rax; pAcl
0x140002006  call    cs:__imp_GetAclInformation
0x14000200c  test    eax, eax
0x14000200e  jnz     short loc_140002016
0x140002010  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140002016  mov     eax, dword ptr [rsp+48h+pAclInformation+4]
0x14000201a  mov     rcx, [rsp+48h+var_18]
0x14000201f  xor     rcx, rsp; StackCookie
0x140002022  call    __security_check_cookie
0x140002027  add     rsp, 40h
0x14000202b  pop     rbx
0x14000202c  retn
```
