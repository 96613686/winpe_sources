# IsDomainJoined(int *)

- ea: `0x180013340`
- end: `0x1800133f9`
- name: `?IsDomainJoined@@YAKPEAH@Z`
- size: `185`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180013340`

## import_xrefs

- `ADVAPI32!LsaClose` at `0x1800133da`
- `ADVAPI32!LsaClose` at `0x1800133da`
- `ADVAPI32!LsaFreeMemory` at `0x1800133c5`
- `ADVAPI32!LsaFreeMemory` at `0x1800133c5`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001339b`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001339b`
- `ADVAPI32!LsaOpenPolicy` at `0x18001337e`
- `ADVAPI32!LsaOpenPolicy` at `0x18001337e`

## pseudocode

```c
__int64 __fastcall IsDomainJoined(int *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rax
  PVOID v4; // rcx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp+18h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v2
    || (LODWORD(v3) = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer), (v2 = v3) != 0) )
  {
    v4 = Buffer;
  }
  else
  {
    v4 = Buffer;
    *a1 = *((_QWORD *)Buffer + 8) != v3;
  }
  if ( v4 )
    LsaFreeMemory(v4);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v2;
}

```

## disassembly

```asm
0x180013340  mov     [rsp-8+arg_0], rbx
0x180013345  mov     [rsp-8+arg_18], rdi
0x18001334a  push    rbp
0x18001334b  mov     rbp, rsp
0x18001334e  sub     rsp, 50h
0x180013352  and     [rbp+PolicyHandle], 0
0x180013357  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18001335b  and     [rbp+Buffer], 0
0x180013360  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180013364  xorps   xmm0, xmm0
0x180013367  mov     rdi, rcx
0x18001336a  xor     ecx, ecx; SystemName
0x18001336c  mov     r8d, 1; DesiredAccess
0x180013372  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180013376  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001337a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001337e  call    cs:__imp_LsaOpenPolicy
0x180013385  nop     dword ptr [rax+rax+00h]
0x18001338a  mov     ebx, eax
0x18001338c  test    eax, eax
0x18001338e  jnz     short loc_1800133BC
0x180013390  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180013394  lea     r8, [rbp+Buffer]; Buffer
0x180013398  lea     edx, [rax+0Ch]; InformationClass
0x18001339b  call    cs:__imp_LsaQueryInformationPolicy
0x1800133a2  nop     dword ptr [rax+rax+00h]
0x1800133a7  mov     ebx, eax
0x1800133a9  test    eax, eax
0x1800133ab  jnz     short loc_1800133BC
0x1800133ad  mov     rcx, [rbp+Buffer]
0x1800133b1  cmp     [rcx+40h], rax
0x1800133b5  setnz   al
0x1800133b8  mov     [rdi], eax
0x1800133ba  jmp     short loc_1800133C0
0x1800133bc  mov     rcx, [rbp+Buffer]; Buffer
0x1800133c0  test    rcx, rcx
0x1800133c3  jz      short loc_1800133D1
0x1800133c5  call    cs:__imp_LsaFreeMemory
0x1800133cc  nop     dword ptr [rax+rax+00h]
0x1800133d1  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800133d5  test    rcx, rcx
0x1800133d8  jz      short loc_1800133E6
0x1800133da  call    cs:__imp_LsaClose
0x1800133e1  nop     dword ptr [rax+rax+00h]
0x1800133e6  mov     rdi, [rsp+50h+arg_18]
0x1800133eb  mov     eax, ebx
0x1800133ed  mov     rbx, [rsp+50h+arg_0]
0x1800133f2  add     rsp, 50h
0x1800133f6  pop     rbp
0x1800133f7  retn
```
