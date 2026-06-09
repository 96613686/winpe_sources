# IsDomainJoined(int *)

- ea: `0x1800126e0`
- end: `0x180012799`
- name: `?IsDomainJoined@@YAKPEAH@Z`
- size: `185`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800126e0`

## import_xrefs

- `ADVAPI32!LsaClose` at `0x18001277a`
- `ADVAPI32!LsaClose` at `0x18001277a`
- `ADVAPI32!LsaFreeMemory` at `0x180012765`
- `ADVAPI32!LsaFreeMemory` at `0x180012765`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001273b`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001273b`
- `ADVAPI32!LsaOpenPolicy` at `0x18001271e`
- `ADVAPI32!LsaOpenPolicy` at `0x18001271e`

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
0x1800126e0  mov     [rsp-8+arg_0], rbx
0x1800126e5  mov     [rsp-8+arg_18], rdi
0x1800126ea  push    rbp
0x1800126eb  mov     rbp, rsp
0x1800126ee  sub     rsp, 50h
0x1800126f2  and     [rbp+PolicyHandle], 0
0x1800126f7  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800126fb  and     [rbp+Buffer], 0
0x180012700  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180012704  xorps   xmm0, xmm0
0x180012707  mov     rdi, rcx
0x18001270a  xor     ecx, ecx; SystemName
0x18001270c  mov     r8d, 1; DesiredAccess
0x180012712  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180012716  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001271a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001271e  call    cs:__imp_LsaOpenPolicy
0x180012725  nop     dword ptr [rax+rax+00h]
0x18001272a  mov     ebx, eax
0x18001272c  test    eax, eax
0x18001272e  jnz     short loc_18001275C
0x180012730  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180012734  lea     r8, [rbp+Buffer]; Buffer
0x180012738  lea     edx, [rax+0Ch]; InformationClass
0x18001273b  call    cs:__imp_LsaQueryInformationPolicy
0x180012742  nop     dword ptr [rax+rax+00h]
0x180012747  mov     ebx, eax
0x180012749  test    eax, eax
0x18001274b  jnz     short loc_18001275C
0x18001274d  mov     rcx, [rbp+Buffer]
0x180012751  cmp     [rcx+40h], rax
0x180012755  setnz   al
0x180012758  mov     [rdi], eax
0x18001275a  jmp     short loc_180012760
0x18001275c  mov     rcx, [rbp+Buffer]; Buffer
0x180012760  test    rcx, rcx
0x180012763  jz      short loc_180012771
0x180012765  call    cs:__imp_LsaFreeMemory
0x18001276c  nop     dword ptr [rax+rax+00h]
0x180012771  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180012775  test    rcx, rcx
0x180012778  jz      short loc_180012786
0x18001277a  call    cs:__imp_LsaClose
0x180012781  nop     dword ptr [rax+rax+00h]
0x180012786  mov     rdi, [rsp+50h+arg_18]
0x18001278b  mov     eax, ebx
0x18001278d  mov     rbx, [rsp+50h+arg_0]
0x180012792  add     rsp, 50h
0x180012796  pop     rbp
0x180012797  retn
```
