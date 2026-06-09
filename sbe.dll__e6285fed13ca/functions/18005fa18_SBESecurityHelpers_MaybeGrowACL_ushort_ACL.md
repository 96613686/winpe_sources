# SBESecurityHelpers::MaybeGrowACL(ushort,_ACL * *)

- ea: `0x18005fa18`
- end: `0x18005fae4`
- name: `?MaybeGrowACL@SBESecurityHelpers@@SAKGPEAPEAU_ACL@@@Z`
- size: `204`
- prototype: `unsigned int __fastcall(unsigned __int16, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f394`

## callees

- `0x180001c00`
- `0x18005f468`
- `0x18005fa18`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005fa60`
- `KERNEL32!GetLastError` at `0x18005fa60`
- `KERNEL32!LocalFree` at `0x18005fa71`
- `KERNEL32!LocalFree` at `0x18005fad9`
- `KERNEL32!LocalFree` at `0x18005fa71`
- `KERNEL32!LocalFree` at `0x18005fad9`
- `KERNEL32!LocalAlloc` at `0x18005faad`
- `KERNEL32!LocalAlloc` at `0x18005faad`
- `ADVAPI32!GetAclInformation` at `0x18005fa56`
- `ADVAPI32!GetAclInformation` at `0x18005fa56`

## pseudocode

```c
__int64 __fastcall SBESecurityHelpers::MaybeGrowACL(unsigned __int16 a1, struct _ACL **a2)
{
  unsigned int v2; // edi
  unsigned int LastError; // ebx
  struct _ACL *v5; // rdi
  ACL *v7; // rax
  unsigned int v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v10; // [rsp+30h] [rbp-18h]

  v2 = a1;
  v9 = 0;
  v10 = 0;
  if ( GetAclInformation(*a2, &v9, 0xCu, AclSizeInformation) )
  {
    LastError = 0;
    if ( v10 >= v2 )
      return LastError;
    v8 = HIDWORD(v9) + v2;
    v7 = (ACL *)LocalAlloc(0x40u, HIDWORD(v9) + v2);
    v5 = v7;
    if ( v7 )
    {
      LastError = SBESecurityHelpers::CopyACL(*a2, v7, &v8);
      if ( !LastError )
      {
        LocalFree(*a2);
        *a2 = v5;
        return LastError;
      }
    }
    else
    {
      LastError = 8;
    }
    goto LABEL_3;
  }
  LastError = GetLastError();
  v5 = 0;
  if ( LastError )
LABEL_3:
    LocalFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x18005fa18  mov     r11, rsp
0x18005fa1b  mov     [r11+18h], rbx
0x18005fa1f  mov     [r11+20h], rsi
0x18005fa23  push    rdi
0x18005fa24  sub     rsp, 40h
0x18005fa28  mov     rax, cs:__security_cookie
0x18005fa2f  xor     rax, rsp
0x18005fa32  mov     [rsp+48h+var_10], rax
0x18005fa37  xor     eax, eax
0x18005fa39  movzx   edi, cx
0x18005fa3c  mov     rsi, rdx
0x18005fa3f  mov     [r11-20h], rax
0x18005fa43  lea     rdx, [r11-20h]; pAclInformation
0x18005fa47  mov     [rsp+48h+var_18], eax
0x18005fa4b  lea     r9d, [rax+2]; dwAclInformationClass
0x18005fa4f  mov     rcx, [rsi]; pAcl
0x18005fa52  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18005fa56  call    cs:__imp_GetAclInformation
0x18005fa5c  test    eax, eax
0x18005fa5e  jnz     short loc_18005FA96
0x18005fa60  call    cs:__imp_GetLastError
0x18005fa66  mov     ebx, eax
0x18005fa68  xor     edi, edi
0x18005fa6a  test    eax, eax
0x18005fa6c  jz      short loc_18005FA77
0x18005fa6e  mov     rcx, rdi; hMem
0x18005fa71  call    cs:__imp_LocalFree
0x18005fa77  mov     eax, ebx
0x18005fa79  mov     rcx, [rsp+48h+var_10]
0x18005fa7e  xor     rcx, rsp; StackCookie
0x18005fa81  call    __security_check_cookie
0x18005fa86  mov     rbx, [rsp+48h+arg_10]
0x18005fa8b  mov     rsi, [rsp+48h+arg_18]
0x18005fa90  add     rsp, 40h
0x18005fa94  pop     rdi
0x18005fa95  retn
0x18005fa96  xor     ebx, ebx
0x18005fa98  mov     ecx, edi
0x18005fa9a  cmp     [rsp+48h+var_18], edi
0x18005fa9e  jnb     short loc_18005FA77
0x18005faa0  add     ecx, [rsp+48h+var_1C]
0x18005faa4  mov     [rsp+48h+var_28], ecx
0x18005faa8  mov     edx, ecx; uBytes
0x18005faaa  lea     ecx, [rbx+40h]; uFlags
0x18005faad  call    cs:__imp_LocalAlloc
0x18005fab3  mov     rdi, rax
0x18005fab6  test    rax, rax
0x18005fab9  jnz     short loc_18005FAC0
0x18005fabb  lea     ebx, [rax+8]
0x18005fabe  jmp     short loc_18005FA6E
0x18005fac0  mov     rcx, [rsi]; pAcl
0x18005fac3  lea     r8, [rsp+48h+var_28]; unsigned int *
0x18005fac8  mov     rdx, rdi; PACL
0x18005facb  call    ?CopyACL@SBESecurityHelpers@@SAKPEAU_ACL@@0PEAK@Z; SBESecurityHelpers::CopyACL(_ACL *,_ACL *,ulong *)
0x18005fad0  mov     ebx, eax
0x18005fad2  test    eax, eax
0x18005fad4  jnz     short loc_18005FA6E
0x18005fad6  mov     rcx, [rsi]; hMem
0x18005fad9  call    cs:__imp_LocalFree
0x18005fadf  mov     [rsi], rdi
0x18005fae2  jmp     short loc_18005FA77
```
