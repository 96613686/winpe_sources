# NetpGetDomainNameExExEx

- ea: `0x180006068`
- end: `0x1800061cf`
- name: `NetpGetDomainNameExExEx`
- size: `359`
- prototype: `__int64 __usercall@<rax>(LPVOID *Buffer@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005e54`
- `0x1800061d8`

## callees

- `0x180006068`
- `0x180036191`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x1800061b6`
- `netutils!NetApiBufferFree` at `0x1800061b6`
- `netutils!NetApiBufferAllocate` at `0x180006114`
- `netutils!NetApiBufferAllocate` at `0x180006114`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800060d2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800060d2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800060f3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800060f3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000618a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000618a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000619b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000619b`

## pseudocode

```c
__int64 __fastcall NetpGetDomainNameExExEx(LPVOID *Buffer, __int64 a2, __int64 a3, __int64 a4, bool *a5)
{
  DWORD v6; // ebx
  PVOID v7; // rdx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF
  PVOID Buffera; // [rsp+78h] [rbp+28h] BYREF

  PolicyHandle = 0;
  Buffera = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( !Buffer )
    return 87;
  *Buffer = 0;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle) < 0
    || LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffera) < 0 )
  {
    v6 = 2146;
    goto LABEL_13;
  }
  v6 = NetApiBufferAllocate(*(unsigned __int16 *)Buffera + 2, Buffer);
  if ( v6 )
  {
LABEL_13:
    if ( *Buffer )
    {
      NetApiBufferFree(*Buffer);
      *Buffer = 0;
    }
    v7 = Buffera;
    goto LABEL_6;
  }
  memcpy_0(*Buffer, *((const void **)Buffera + 1), *(unsigned __int16 *)Buffera);
  *((_WORD *)*Buffer + ((unsigned __int64)*(unsigned __int16 *)Buffera >> 1)) = 0;
  v7 = Buffera;
  *a5 = *((_QWORD *)Buffera + 8) == 0;
LABEL_6:
  if ( v7 )
    LsaFreeMemory(v7);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v6;
}

```

## disassembly

```asm
0x180006068  mov     rax, rsp
0x18000606b  mov     [rax+8], rbx
0x18000606f  mov     [rax+10h], rdi
0x180006073  mov     [rax+20h], r9
0x180006077  mov     [rax+18h], r8
0x18000607b  push    rbp
0x18000607c  mov     rbp, rsp
0x18000607f  sub     rsp, 50h
0x180006083  xor     eax, eax
0x180006085  mov     [rbp+PolicyHandle], 0
0x18000608d  mov     [rbp+Buffer], 0
0x180006095  mov     rdi, rcx
0x180006098  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x18000609b  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x18000609e  test    rcx, rcx
0x1800060a1  jz      loc_180006183
0x1800060a7  mov     [rcx], rax
0x1800060aa  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800060ae  xorps   xmm0, xmm0
0x1800060b1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800060b8  xor     ecx, ecx; SystemName
0x1800060ba  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1800060be  lea     r8d, [rax+1]; DesiredAccess
0x1800060c2  mov     [rbp+ObjectAttributes.Attributes], eax
0x1800060c5  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800060c9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800060cd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800060d2  call    cs:__imp_LsaOpenPolicy
0x1800060d9  nop     dword ptr [rax+rax+00h]
0x1800060de  test    eax, eax
0x1800060e0  js      loc_1800061A9
0x1800060e6  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800060ea  lea     r8, [rbp+Buffer]; Buffer
0x1800060ee  mov     edx, 0Ch; InformationClass
0x1800060f3  call    cs:__imp_LsaQueryInformationPolicy
0x1800060fa  nop     dword ptr [rax+rax+00h]
0x1800060ff  test    eax, eax
0x180006101  js      loc_1800061A9
0x180006107  mov     rax, [rbp+Buffer]
0x18000610b  mov     rdx, rdi; Buffer
0x18000610e  movzx   ecx, word ptr [rax]
0x180006111  add     ecx, 2; ByteCount
0x180006114  call    cs:__imp_NetApiBufferAllocate
0x18000611b  nop     dword ptr [rax+rax+00h]
0x180006120  mov     ebx, eax
0x180006122  test    eax, eax
0x180006124  jnz     loc_1800061AE
0x18000612a  mov     rdx, [rbp+Buffer]
0x18000612e  mov     rcx, [rdi]; void *
0x180006131  movzx   r8d, word ptr [rdx]; Size
0x180006135  mov     rdx, [rdx+8]; Src
0x180006139  call    memcpy_0
0x18000613e  mov     rax, [rbp+Buffer]
0x180006142  mov     rcx, [rdi]
0x180006145  movzx   edx, word ptr [rax]
0x180006148  xor     eax, eax
0x18000614a  shr     rdx, 1
0x18000614d  mov     [rcx+rdx*2], ax
0x180006151  mov     rdx, [rbp+Buffer]
0x180006155  cmp     [rdx+40h], rax
0x180006159  mov     rax, [rbp+arg_20]
0x18000615d  setz    cl
0x180006160  mov     [rax], cl
0x180006162  test    rdx, rdx
0x180006165  jnz     short loc_180006198
0x180006167  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18000616b  test    rcx, rcx
0x18000616e  jnz     short loc_18000618A
0x180006170  mov     eax, ebx
0x180006172  mov     rbx, [rsp+50h+arg_0]
0x180006177  mov     rdi, [rsp+50h+arg_8]
0x18000617c  add     rsp, 50h
0x180006180  pop     rbp
0x180006181  retn
0x180006183  mov     eax, 57h ; 'W'
0x180006188  jmp     short loc_180006172
0x18000618a  call    cs:__imp_LsaClose
0x180006191  nop     dword ptr [rax+rax+00h]
0x180006196  jmp     short loc_180006170
0x180006198  mov     rcx, rdx; Buffer
0x18000619b  call    cs:__imp_LsaFreeMemory
0x1800061a2  nop     dword ptr [rax+rax+00h]
0x1800061a7  jmp     short loc_180006167
0x1800061a9  mov     ebx, 862h
0x1800061ae  mov     rcx, [rdi]; Buffer
0x1800061b1  test    rcx, rcx
0x1800061b4  jz      short loc_1800061C9
0x1800061b6  call    cs:__imp_NetApiBufferFree
0x1800061bd  nop     dword ptr [rax+rax+00h]
0x1800061c2  mov     qword ptr [rdi], 0
0x1800061c9  mov     rdx, [rbp+Buffer]
0x1800061cd  jmp     short loc_180006162
```
