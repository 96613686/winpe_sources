# SclGenerateUniqueAccountDomainSid

- ea: `0x180001848`
- end: `0x180001961`
- name: `SclGenerateUniqueAccountDomainSid`
- size: `281`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800073c4`

## callees

- `0x1800016e4`
- `0x180001848`
- `0x18000a524`
- `0x180014da0`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180001915`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180001915`
- `ntdll!RtlFreeSid` at `0x180001938`
- `ntdll!RtlFreeSid` at `0x180001938`

## string_xrefs

- `0x180001890`: `Unable to generate new account domain SID`
- `0x1800018a3`: `SclGenerateUniqueAccountDomainSid`

## pseudocode

```c
__int64 __fastcall SclGenerateUniqueAccountDomainSid(_QWORD *a1)
{
  int v2; // ebx
  PSID Src; // [rsp+60h] [rbp+27h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp+2Fh] BYREF
  ULONG SubAuthority1[4]; // [rsp+70h] [rbp+37h] BYREF

  Src = 0;
  if ( GenerateRandomData(SubAuthority1, 0xCu) )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    v2 = RtlAllocateAndInitializeSid(
           &IdentifierAuthority,
           4u,
           0x15u,
           SubAuthority1[0],
           SubAuthority1[1],
           SubAuthority1[2],
           0,
           0,
           0,
           0,
           &Src);
    if ( v2 >= 0 )
      v2 = SclDuplicateSid(Src, a1);
  }
  else
  {
    v2 = -1073741823;
    SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 87, (__int64)"SclGenerateUniqueAccountDomainSid");
  }
  if ( Src )
    RtlFreeSid(Src);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001848  mov     [rsp-8+arg_8], rbx
0x18000184d  mov     [rsp-8+arg_10], rdi
0x180001852  push    rbp
0x180001853  lea     rbp, [rsp-57h]
0x180001858  sub     rsp, 90h
0x18000185f  mov     rax, cs:__security_cookie
0x180001866  xor     rax, rsp
0x180001869  mov     [rbp+57h+var_10], rax
0x18000186d  mov     rdi, rcx
0x180001870  mov     [rbp+57h+Src], 0
0x180001878  lea     rcx, [rbp+57h+SubAuthority1]; OutputBuffer
0x18000187c  mov     edx, 0Ch; OutputBufferLength
0x180001881  call    GenerateRandomData
0x180001886  test    eax, eax
0x180001888  jnz     short loc_1800018C1
0x18000188a  mov     r9d, 57h ; 'W'
0x180001890  lea     rax, aUnableToGenera; "Unable to generate new account domain S"...
0x180001897  mov     qword ptr [rsp+90h+SubAuthority3], rax
0x18000189c  lea     r8, SclEvent_Generic_Error
0x1800018a3  lea     rax, aSclgenerateuni; "SclGenerateUniqueAccountDomainSid"
0x1800018aa  xor     ecx, ecx
0x1800018ac  mov     ebx, 0C0000001h
0x1800018b1  mov     qword ptr [rsp+90h+SubAuthority2], rax
0x1800018b6  lea     edx, [r9-54h]
0x1800018ba  call    SclLogGenericMessage
0x1800018bf  jmp     short loc_18000192F
0x1800018c1  mov     r9d, [rbp+57h+SubAuthority1]; SubAuthority1
0x1800018c5  lea     rax, [rbp+57h+Src]
0x1800018c9  mov     [rsp+90h+Sid], rax; Sid
0x1800018ce  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800018d2  mov     eax, [rbp+57h+var_18]
0x1800018d5  mov     r8d, 15h; SubAuthority0
0x1800018db  mov     [rsp+90h+SubAuthority7], 0; SubAuthority7
0x1800018e3  mov     dl, 4; SubAuthorityCount
0x1800018e5  mov     [rsp+90h+SubAuthority6], 0; SubAuthority6
0x1800018ed  mov     [rsp+90h+SubAuthority5], 0; SubAuthority5
0x1800018f5  mov     [rsp+90h+SubAuthority4], 0; SubAuthority4
0x1800018fd  mov     [rsp+90h+SubAuthority3], eax; SubAuthority3
0x180001901  mov     eax, [rbp+57h+var_1C]
0x180001904  mov     [rsp+90h+SubAuthority2], eax; SubAuthority2
0x180001908  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x18000190f  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180001915  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000191b  mov     ebx, eax
0x18000191d  test    eax, eax
0x18000191f  js      short loc_18000192F
0x180001921  mov     rcx, [rbp+57h+Src]; Src
0x180001925  mov     rdx, rdi
0x180001928  call    SclDuplicateSid
0x18000192d  mov     ebx, eax
0x18000192f  mov     rcx, [rbp+57h+Src]; Sid
0x180001933  test    rcx, rcx
0x180001936  jz      short loc_18000193E
0x180001938  call    cs:__imp_RtlFreeSid
0x18000193e  mov     eax, ebx
0x180001940  mov     rcx, [rbp+57h+var_10]
0x180001944  xor     rcx, rsp; StackCookie
0x180001947  call    __security_check_cookie
0x18000194c  lea     r11, [rsp+90h+var_s0]
0x180001954  mov     rbx, [r11+18h]
0x180001958  mov     rdi, [r11+20h]
0x18000195c  mov     rsp, r11
0x18000195f  pop     rbp
0x180001960  retn
```
