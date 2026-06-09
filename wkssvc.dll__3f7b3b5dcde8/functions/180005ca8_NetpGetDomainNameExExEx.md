# NetpGetDomainNameExExEx

- ea: `0x180005ca8`
- end: `0x180005de6`
- name: `NetpGetDomainNameExExEx`
- size: `318`
- prototype: `__int64 __fastcall(LPVOID *Buffer, __int64, __int64, __int64, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005ac0`
- `0x180005dec`

## callees

- `0x180005ca8`
- `0x180033159`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180005dd3`
- `netutils!NetApiBufferFree` at `0x180005dd3`
- `netutils!NetApiBufferAllocate` at `0x180005d48`
- `netutils!NetApiBufferAllocate` at `0x180005d48`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180005d12`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180005d12`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180005d2d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180005d2d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180005db3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180005db3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005dbe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180005dbe`

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
0x180005ca8  mov     rax, rsp
0x180005cab  mov     [rax+8], rbx
0x180005caf  mov     [rax+10h], rdi
0x180005cb3  mov     [rax+20h], r9
0x180005cb7  mov     [rax+18h], r8
0x180005cbb  push    rbp
0x180005cbc  mov     rbp, rsp
0x180005cbf  sub     rsp, 50h
0x180005cc3  xor     eax, eax
0x180005cc5  mov     [rbp+PolicyHandle], 0
0x180005ccd  mov     [rbp+Buffer], 0
0x180005cd5  mov     rdi, rcx
0x180005cd8  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x180005cdb  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x180005cde  test    rcx, rcx
0x180005ce1  jz      loc_180005DAC
0x180005ce7  mov     [rcx], rax
0x180005cea  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180005cee  xorps   xmm0, xmm0
0x180005cf1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180005cf8  xor     ecx, ecx; SystemName
0x180005cfa  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180005cfe  lea     r8d, [rax+1]; DesiredAccess
0x180005d02  mov     [rbp+ObjectAttributes.Attributes], eax
0x180005d05  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180005d09  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180005d0d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180005d12  call    cs:__imp_LsaOpenPolicy
0x180005d18  test    eax, eax
0x180005d1a  js      loc_180005DC6
0x180005d20  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180005d24  lea     r8, [rbp+Buffer]; Buffer
0x180005d28  mov     edx, 0Ch; InformationClass
0x180005d2d  call    cs:__imp_LsaQueryInformationPolicy
0x180005d33  test    eax, eax
0x180005d35  js      loc_180005DC6
0x180005d3b  mov     rax, [rbp+Buffer]
0x180005d3f  mov     rdx, rdi; Buffer
0x180005d42  movzx   ecx, word ptr [rax]
0x180005d45  add     ecx, 2; ByteCount
0x180005d48  call    cs:__imp_NetApiBufferAllocate
0x180005d4e  mov     ebx, eax
0x180005d50  test    eax, eax
0x180005d52  jnz     short loc_180005DCB
0x180005d54  mov     rdx, [rbp+Buffer]
0x180005d58  mov     rcx, [rdi]; void *
0x180005d5b  movzx   r8d, word ptr [rdx]; Size
0x180005d5f  mov     rdx, [rdx+8]; Src
0x180005d63  call    memcpy_0
0x180005d68  mov     rax, [rbp+Buffer]
0x180005d6c  mov     rcx, [rdi]
0x180005d6f  movzx   edx, word ptr [rax]
0x180005d72  xor     eax, eax
0x180005d74  shr     rdx, 1
0x180005d77  mov     [rcx+rdx*2], ax
0x180005d7b  mov     rdx, [rbp+Buffer]
0x180005d7f  cmp     [rdx+40h], rax
0x180005d83  mov     rax, [rbp+arg_20]
0x180005d87  setz    cl
0x180005d8a  mov     [rax], cl
0x180005d8c  test    rdx, rdx
0x180005d8f  jnz     short loc_180005DBB
0x180005d91  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180005d95  test    rcx, rcx
0x180005d98  jnz     short loc_180005DB3
0x180005d9a  mov     eax, ebx
0x180005d9c  mov     rbx, [rsp+50h+arg_0]
0x180005da1  mov     rdi, [rsp+50h+arg_8]
0x180005da6  add     rsp, 50h
0x180005daa  pop     rbp
0x180005dab  retn
0x180005dac  mov     eax, 57h ; 'W'
0x180005db1  jmp     short loc_180005D9C
0x180005db3  call    cs:__imp_LsaClose
0x180005db9  jmp     short loc_180005D9A
0x180005dbb  mov     rcx, rdx; Buffer
0x180005dbe  call    cs:__imp_LsaFreeMemory
0x180005dc4  jmp     short loc_180005D91
0x180005dc6  mov     ebx, 862h
0x180005dcb  mov     rcx, [rdi]; Buffer
0x180005dce  test    rcx, rcx
0x180005dd1  jz      short loc_180005DE0
0x180005dd3  call    cs:__imp_NetApiBufferFree
0x180005dd9  mov     qword ptr [rdi], 0
0x180005de0  mov     rdx, [rbp+Buffer]
0x180005de4  jmp     short loc_180005D8C
```
