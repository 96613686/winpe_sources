# CreatePerUserSecurityDescriptor

- ea: `0x1800237d8`
- end: `0x1800238e4`
- name: `CreatePerUserSecurityDescriptor`
- size: `268`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012100`

## callees

- `0x18000e110`
- `0x180010b40`
- `0x180012290`
- `0x1800125c8`
- `0x1800237d8`
- `0x180037284`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180023841`
- `ntdll!NtQueryInformationToken` at `0x180023841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238be`

## pseudocode

```c
__int64 __fastcall CreatePerUserSecurityDescriptor(__int64 a1, __int64 a2, PSECURITY_DESCRIPTOR *a3)
{
  LPCWSTR v3; // rdi
  PSID *v6; // r14
  NTSTATUS v7; // ebx
  int v8; // eax
  BOOL v9; // eax
  int v10; // ecx
  LPWSTR StringSid; // [rsp+30h] [rbp-48h] BYREF
  LPCWSTR StringSecurityDescriptor[8]; // [rsp+38h] [rbp-40h] BYREF
  ULONG ReturnLength; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  ReturnLength = 0;
  StringSid = 0;
  StringSecurityDescriptor[0] = 0;
  v6 = (PSID *)AccessHlprAlloc(84);
  if ( v6 )
  {
    v7 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, v6, 0x54u, &ReturnLength);
    if ( v7 >= 0 )
    {
      if ( ConvertSidToStringSidW(*v6, &StringSid) )
      {
        v8 = FormatSecurityDescriptor(a1, (__int64)StringSecurityDescriptor);
        v3 = StringSecurityDescriptor[0];
        v7 = v8;
        if ( v8 >= 0 )
        {
          v9 = ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor[0], 1u, a3, 0);
          v10 = v7;
          if ( !v9 )
            v10 = -1073741823;
          v7 = v10;
        }
      }
      else
      {
        v7 = -1073741823;
      }
      if ( StringSid )
        LocalFree(StringSid);
    }
  }
  else
  {
    v7 = -1073741801;
  }
  FreeTransientObjectSecurityDescriptor(v3);
  FreeTransientObjectSecurityDescriptor(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800237d8  mov     rax, rsp
0x1800237db  push    rbx
0x1800237dc  push    rbp
0x1800237dd  push    rdi
0x1800237de  push    r12
0x1800237e0  push    r14
0x1800237e2  push    r15
0x1800237e4  sub     rsp, 48h
0x1800237e8  xor     edi, edi
0x1800237ea  mov     dword ptr [rax+20h], 0
0x1800237f1  mov     r15, rcx
0x1800237f4  mov     qword ptr [rax-48h], 0
0x1800237fc  mov     r12, r8
0x1800237ff  mov     [rax-40h], rdi
0x180023803  mov     rbp, rdx
0x180023806  lea     ebx, [rdi+54h]
0x180023809  mov     ecx, ebx
0x18002380b  call    AccessHlprAlloc
0x180023810  mov     r14, rax
0x180023813  test    rax, rax
0x180023816  jnz     short loc_180023822
0x180023818  mov     ebx, 0C0000017h
0x18002381d  jmp     loc_1800238C4
0x180023822  lea     rax, [rsp+78h+arg_18]
0x18002382a  mov     r9d, ebx; TokenInformationLength
0x18002382d  mov     r8, r14; TokenInformation
0x180023830  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180023835  mov     edx, 1; TokenInformationClass
0x18002383a  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180023841  call    cs:__imp_NtQueryInformationToken
0x180023847  mov     ebx, eax
0x180023849  test    eax, eax
0x18002384b  js      short loc_1800238C4
0x18002384d  mov     rcx, [r14]; Sid
0x180023850  lea     rdx, [rsp+78h+StringSid]; StringSid
0x180023855  call    ConvertSidToStringSidW
0x18002385a  test    eax, eax
0x18002385c  jnz     short loc_180023865
0x18002385e  mov     ebx, 0C0000001h
0x180023863  jmp     short loc_1800238B1
0x180023865  mov     r9, [rsp+78h+StringSid]
0x18002386a  lea     rax, [rsp+78h+StringSecurityDescriptor]
0x18002386f  lea     r8, aS_0; "%s"
0x180023876  mov     [rsp+78h+ReturnLength], rax; __int64
0x18002387b  mov     rdx, rbp
0x18002387e  mov     rcx, r15; __int64
0x180023881  call    FormatSecurityDescriptor
0x180023886  mov     rdi, [rsp+78h+StringSecurityDescriptor]
0x18002388b  mov     ebx, eax
0x18002388d  test    eax, eax
0x18002388f  js      short loc_1800238B1
0x180023891  xor     r9d, r9d; SecurityDescriptorSize
0x180023894  mov     r8, r12; SecurityDescriptor
0x180023897  mov     rcx, rdi; StringSecurityDescriptor
0x18002389a  lea     edx, [r9+1]; StringSDRevision
0x18002389e  call    ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800238a3  mov     ecx, ebx
0x1800238a5  test    eax, eax
0x1800238a7  mov     ebx, 0C0000001h
0x1800238ac  cmovz   ecx, ebx
0x1800238af  mov     ebx, ecx
0x1800238b1  cmp     [rsp+78h+StringSid], 0
0x1800238b7  jz      short loc_1800238C4
0x1800238b9  mov     rcx, [rsp+78h+StringSid]; hMem
0x1800238be  call    cs:__imp_LocalFree
0x1800238c4  mov     rcx, rdi
0x1800238c7  call    FreeTransientObjectSecurityDescriptor
0x1800238cc  mov     rcx, r14
0x1800238cf  call    FreeTransientObjectSecurityDescriptor
0x1800238d4  mov     eax, ebx
0x1800238d6  add     rsp, 48h
0x1800238da  pop     r15
0x1800238dc  pop     r14
0x1800238de  pop     r12
0x1800238e0  pop     rdi
0x1800238e1  pop     rbp
0x1800238e2  pop     rbx
0x1800238e3  retn
```
