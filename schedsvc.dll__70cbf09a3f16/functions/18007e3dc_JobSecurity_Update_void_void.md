# JobSecurity::Update(void *,void *)

- ea: `0x18007e3dc`
- end: `0x18007e520`
- name: `?Update@JobSecurity@@QEAAJPEAX0@Z`
- size: `324`
- prototype: `int __fastcall(PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor, PSECURITY_DESCRIPTOR ModificationDescriptor, HANDLE Token)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029978`

## callees

- `0x18007e3dc`
- `0x18007e6d0`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18007e4fe`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18007e4fe`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18007e42a`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18007e42a`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18007e448`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18007e448`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18007e469`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18007e469`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18007e48c`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18007e48c`
- `ntdll!RtlSetSecurityObjectEx` at `0x18007e4ed`
- `ntdll!RtlSetSecurityObjectEx` at `0x18007e4ed`

## pseudocode

```c
int __fastcall JobSecurity::Update(
        PSECURITY_DESCRIPTOR *ObjectsSecurityDescriptor,
        PSECURITY_DESCRIPTOR ModificationDescriptor,
        HANDLE Token)
{
  NTSTATUS ControlSecurityDescriptor; // eax
  SECURITY_INFORMATION v8; // ebx
  unsigned __int8 OwnerDefaulted; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+31h] [rbp-3Fh] BYREF
  WORD Control; // [rsp+34h] [rbp-3Ch] BYREF
  PSID Owner; // [rsp+38h] [rbp-38h] BYREF
  ULONG Revision; // [rsp+40h] [rbp-30h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-28h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-20h] BYREF

  Control = 0;
  Revision = 0;
  DaclPresent[0] = 0;
  OwnerDefaulted = 0;
  Owner = 0;
  Dacl = 0;
  GenericMapping = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(ModificationDescriptor, &Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
    return ControlSecurityDescriptor | 0x10000000;
  ControlSecurityDescriptor = RtlGetOwnerSecurityDescriptor(ModificationDescriptor, &Owner, &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
    return ControlSecurityDescriptor | 0x10000000;
  v8 = Owner != 0;
  ControlSecurityDescriptor = RtlGetGroupSecurityDescriptor(ModificationDescriptor, &Owner, &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
    return ControlSecurityDescriptor | 0x10000000;
  if ( Owner )
    v8 |= 2u;
  ControlSecurityDescriptor = RtlGetDaclSecurityDescriptor(ModificationDescriptor, DaclPresent, &Dacl, &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
    return ControlSecurityDescriptor | 0x10000000;
  if ( DaclPresent[0] )
  {
    if ( (Control & 0x1000) != 0 )
      v8 |= 0x80000004;
    else
      v8 |= 0x20000004u;
  }
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  ControlSecurityDescriptor = RtlSetSecurityObjectEx(
                                v8,
                                ModificationDescriptor,
                                ObjectsSecurityDescriptor,
                                3u,
                                &GenericMapping,
                                Token);
  if ( ControlSecurityDescriptor < 0 )
    return ControlSecurityDescriptor | 0x10000000;
  *((_DWORD *)ObjectsSecurityDescriptor + 2) = RtlLengthSecurityDescriptor(*ObjectsSecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x18007e3dc  push    rbp
0x18007e3de  push    rbx
0x18007e3df  push    rsi
0x18007e3e0  push    rdi
0x18007e3e1  push    r14
0x18007e3e3  mov     rbp, rsp
0x18007e3e6  sub     rsp, 70h
0x18007e3ea  mov     rax, cs:__security_cookie
0x18007e3f1  xor     rax, rsp
0x18007e3f4  mov     [rbp+var_10], rax
0x18007e3f8  xor     eax, eax
0x18007e3fa  mov     rdi, rdx
0x18007e3fd  mov     r14, r8
0x18007e400  mov     [rbp+Control], ax
0x18007e404  mov     rsi, rcx
0x18007e407  mov     [rbp+Revision], eax
0x18007e40a  xorps   xmm0, xmm0
0x18007e40d  mov     [rbp+DaclPresent], al
0x18007e410  mov     rcx, rdi; SecurityDescriptor
0x18007e413  mov     [rbp+OwnerDefaulted], al
0x18007e416  lea     r8, [rbp+Revision]; Revision
0x18007e41a  mov     [rbp+Owner], rax
0x18007e41e  lea     rdx, [rbp+Control]; Control
0x18007e422  mov     [rbp+Dacl], rax
0x18007e426  movups  xmmword ptr [rbp+var_20.GenericRead], xmm0
0x18007e42a  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18007e430  test    eax, eax
0x18007e432  jns     short loc_18007E43D
0x18007e434  bts     eax, 1Ch
0x18007e438  jmp     loc_18007E509
0x18007e43d  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x18007e441  mov     rcx, rdi; SecurityDescriptor
0x18007e444  lea     rdx, [rbp+Owner]; Owner
0x18007e448  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18007e44e  test    eax, eax
0x18007e450  js      short loc_18007E434
0x18007e452  xor     ebx, ebx
0x18007e454  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x18007e458  cmp     [rbp+Owner], rbx
0x18007e45c  lea     rdx, [rbp+Owner]; Group
0x18007e460  mov     rcx, rdi; SecurityDescriptor
0x18007e463  lea     eax, [rbx+1]
0x18007e466  cmovnz  ebx, eax
0x18007e469  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18007e46f  test    eax, eax
0x18007e471  js      short loc_18007E434
0x18007e473  cmp     [rbp+Owner], 0
0x18007e478  jz      short loc_18007E47D
0x18007e47a  or      ebx, 2
0x18007e47d  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x18007e481  mov     rcx, rdi; SecurityDescriptor
0x18007e484  lea     r8, [rbp+Dacl]; Dacl
0x18007e488  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x18007e48c  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18007e492  test    eax, eax
0x18007e494  js      short loc_18007E434
0x18007e496  cmp     [rbp+DaclPresent], 0
0x18007e49a  jz      short loc_18007E4B5
0x18007e49c  mov     eax, 1000h
0x18007e4a1  test    [rbp+Control], ax
0x18007e4a5  jz      short loc_18007E4AF
0x18007e4a7  or      ebx, 80000004h
0x18007e4ad  jmp     short loc_18007E4B5
0x18007e4af  or      ebx, 20000004h
0x18007e4b5  lea     rax, [rbp+var_20]
0x18007e4b9  mov     [rsp+70h+Token], r14; Token
0x18007e4be  mov     r9d, 3; AutoInheritFlags
0x18007e4c4  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x18007e4c9  mov     r8, rsi; ObjectsSecurityDescriptor
0x18007e4cc  mov     [rbp+var_20.GenericRead], 120089h
0x18007e4d3  mov     rdx, rdi; ModificationDescriptor
0x18007e4d6  mov     [rbp+var_20.GenericWrite], 120116h
0x18007e4dd  mov     ecx, ebx; SecurityInformation
0x18007e4df  mov     [rbp+var_20.GenericExecute], 1200A0h
0x18007e4e6  mov     [rbp+var_20.GenericAll], 1F01FFh
0x18007e4ed  call    cs:__imp_RtlSetSecurityObjectEx
0x18007e4f3  test    eax, eax
0x18007e4f5  js      loc_18007E434
0x18007e4fb  mov     rcx, [rsi]; SecurityDescriptor
0x18007e4fe  call    cs:__imp_RtlLengthSecurityDescriptor
0x18007e504  mov     [rsi+8], eax
0x18007e507  xor     eax, eax
0x18007e509  mov     rcx, [rbp+var_10]
0x18007e50d  xor     rcx, rsp; StackCookie
0x18007e510  call    __security_check_cookie
0x18007e515  add     rsp, 70h
0x18007e519  pop     r14
0x18007e51b  pop     rdi
0x18007e51c  pop     rsi
0x18007e51d  pop     rbx
0x18007e51e  pop     rbp
0x18007e51f  retn
```
