# NetpGetDomainNameExExEx

- ea: `0x18001cff4`
- end: `0x18001d19c`
- name: `NetpGetDomainNameExExEx`
- size: `424`
- prototype: `__int64 __usercall@<rax>(LPVOID *Buffer@<rcx>, LPVOID *@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001cb8`
- `0x180012938`

## callees

- `0x18001cff4`
- `0x1800435f8`

## import_xrefs

- `netutils!NetApiBufferAllocate` at `0x18001d0fb`
- `netutils!NetApiBufferAllocate` at `0x18001d14b`
- `netutils!NetApiBufferAllocate` at `0x18001d0fb`
- `netutils!NetApiBufferAllocate` at `0x18001d14b`
- `netutils!NetApiBufferFree` at `0x18001d085`
- `netutils!NetApiBufferFree` at `0x18001d09b`
- `netutils!NetApiBufferFree` at `0x18001d085`
- `netutils!NetApiBufferFree` at `0x18001d09b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001d0e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001d0e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001d0ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001d0ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001d06e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001d06e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001d0bc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001d0bc`

## pseudocode

```c
__int64 __fastcall NetpGetDomainNameExExEx(LPVOID *Buffer, LPVOID *a2, __int64 a3, __int64 a4, bool *a5)
{
  DWORD v8; // ebx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+80h] [rbp+30h] BYREF
  PVOID Buffera; // [rsp+88h] [rbp+38h] BYREF

  PolicyHandle = 0;
  Buffera = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( !Buffer )
    return 87;
  *Buffer = 0;
  if ( a2 )
    *a2 = 0;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle) < 0
    || LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffera) < 0 )
  {
    v8 = 2146;
    goto LABEL_7;
  }
  v8 = NetApiBufferAllocate(*(unsigned __int16 *)Buffera + 2, Buffer);
  if ( v8 )
    goto LABEL_7;
  memcpy_0(*Buffer, *((const void **)Buffera + 1), *(unsigned __int16 *)Buffera);
  *((_WORD *)*Buffer + ((unsigned __int64)*(unsigned __int16 *)Buffera >> 1)) = 0;
  if ( !a2 || !*((_WORD *)Buffera + 8) )
    goto LABEL_23;
  v8 = NetApiBufferAllocate(*((unsigned __int16 *)Buffera + 8) + 2, a2);
  if ( v8 )
  {
LABEL_7:
    if ( *Buffer )
    {
      NetApiBufferFree(*Buffer);
      *Buffer = 0;
    }
    if ( a2 && *a2 )
    {
      NetApiBufferFree(*a2);
      *a2 = 0;
    }
    goto LABEL_12;
  }
  memcpy_0(*a2, *((const void **)Buffera + 3), *((unsigned __int16 *)Buffera + 8));
  *((_WORD *)*a2 + ((unsigned __int64)*((unsigned __int16 *)Buffera + 8) >> 1)) = 0;
LABEL_23:
  v8 = 0;
  *a5 = *((_QWORD *)Buffera + 8) == 0;
LABEL_12:
  if ( Buffera )
    LsaFreeMemory(Buffera);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v8;
}

```

## disassembly

```asm
0x18001cff4  mov     rax, rsp
0x18001cff7  mov     [rax+8], rbx
0x18001cffb  mov     [rax+10h], rsi
0x18001cfff  mov     [rax+20h], r9
0x18001d003  mov     [rax+18h], r8
0x18001d007  push    rbp
0x18001d008  push    rdi
0x18001d009  push    r14
0x18001d00b  mov     rbp, rsp
0x18001d00e  sub     rsp, 50h
0x18001d012  xor     r14d, r14d
0x18001d015  mov     rdi, rdx
0x18001d018  mov     [rbp+PolicyHandle], r14
0x18001d01c  mov     rsi, rcx
0x18001d01f  mov     [rbp+Buffer], r14
0x18001d023  mov     dword ptr [rbp+ObjectAttributes+4], r14d
0x18001d027  mov     dword ptr [rbp+ObjectAttributes+1Ch], r14d
0x18001d02b  test    rcx, rcx
0x18001d02e  jnz     short loc_18001D038
0x18001d030  lea     eax, [rcx+57h]
0x18001d033  jmp     loc_18001D0C4
0x18001d038  mov     [rcx], r14
0x18001d03b  test    rdi, rdi
0x18001d03e  jz      short loc_18001D043
0x18001d040  mov     [rdx], r14
0x18001d043  xorps   xmm0, xmm0
0x18001d046  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001d04d  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18001d051  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x18001d055  mov     r8d, 1; DesiredAccess
0x18001d05b  mov     [rbp+ObjectAttributes.Attributes], r14d
0x18001d05f  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18001d063  mov     [rbp+ObjectAttributes.ObjectName], r14
0x18001d067  xor     ecx, ecx; SystemName
0x18001d069  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001d06e  call    cs:__imp_LsaOpenPolicy
0x18001d074  test    eax, eax
0x18001d076  jns     short loc_18001D0D7
0x18001d078  mov     ebx, 862h
0x18001d07d  mov     rcx, [rsi]; Buffer
0x18001d080  test    rcx, rcx
0x18001d083  jz      short loc_18001D08E
0x18001d085  call    cs:__imp_NetApiBufferFree
0x18001d08b  mov     [rsi], r14
0x18001d08e  test    rdi, rdi
0x18001d091  jz      short loc_18001D0A4
0x18001d093  mov     rcx, [rdi]; Buffer
0x18001d096  test    rcx, rcx
0x18001d099  jz      short loc_18001D0A4
0x18001d09b  call    cs:__imp_NetApiBufferFree
0x18001d0a1  mov     [rdi], r14
0x18001d0a4  mov     rcx, [rbp+Buffer]; Buffer
0x18001d0a8  test    rcx, rcx
0x18001d0ab  jz      short loc_18001D0B3
0x18001d0ad  call    cs:__imp_LsaFreeMemory
0x18001d0b3  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18001d0b7  test    rcx, rcx
0x18001d0ba  jz      short loc_18001D0C2
0x18001d0bc  call    cs:__imp_LsaClose
0x18001d0c2  mov     eax, ebx
0x18001d0c4  mov     rbx, [rsp+50h+arg_0]
0x18001d0c9  mov     rsi, [rsp+50h+arg_8]
0x18001d0ce  add     rsp, 50h
0x18001d0d2  pop     r14
0x18001d0d4  pop     rdi
0x18001d0d5  pop     rbp
0x18001d0d6  retn
0x18001d0d7  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18001d0db  lea     r8, [rbp+Buffer]; Buffer
0x18001d0df  mov     edx, 0Ch; InformationClass
0x18001d0e4  call    cs:__imp_LsaQueryInformationPolicy
0x18001d0ea  test    eax, eax
0x18001d0ec  js      short loc_18001D078
0x18001d0ee  mov     rax, [rbp+Buffer]
0x18001d0f2  mov     rdx, rsi; Buffer
0x18001d0f5  movzx   ecx, word ptr [rax]
0x18001d0f8  add     ecx, 2; ByteCount
0x18001d0fb  call    cs:__imp_NetApiBufferAllocate
0x18001d101  mov     ebx, eax
0x18001d103  test    eax, eax
0x18001d105  jnz     loc_18001D07D
0x18001d10b  mov     rdx, [rbp+Buffer]
0x18001d10f  mov     rcx, [rsi]; void *
0x18001d112  movzx   r8d, word ptr [rdx]; Size
0x18001d116  mov     rdx, [rdx+8]; Src
0x18001d11a  call    memcpy_0
0x18001d11f  mov     rax, [rbp+Buffer]
0x18001d123  mov     rcx, [rsi]
0x18001d126  movzx   edx, word ptr [rax]
0x18001d129  shr     rdx, 1
0x18001d12c  mov     [rcx+rdx*2], r14w
0x18001d131  test    rdi, rdi
0x18001d134  jz      short loc_18001D183
0x18001d136  mov     rax, [rbp+Buffer]
0x18001d13a  cmp     [rax+10h], r14w
0x18001d13f  jz      short loc_18001D183
0x18001d141  movzx   ecx, word ptr [rax+10h]
0x18001d145  mov     rdx, rdi; Buffer
0x18001d148  add     ecx, 2; ByteCount
0x18001d14b  call    cs:__imp_NetApiBufferAllocate
0x18001d151  mov     ebx, eax
0x18001d153  test    eax, eax
0x18001d155  jnz     loc_18001D07D
0x18001d15b  mov     rdx, [rbp+Buffer]
0x18001d15f  mov     rcx, [rdi]; void *
0x18001d162  movzx   r8d, word ptr [rdx+10h]; Size
0x18001d167  mov     rdx, [rdx+18h]; Src
0x18001d16b  call    memcpy_0
0x18001d170  mov     rax, [rbp+Buffer]
0x18001d174  mov     rcx, [rdi]
0x18001d177  movzx   edx, word ptr [rax+10h]
0x18001d17b  shr     rdx, 1
0x18001d17e  mov     [rcx+rdx*2], r14w
0x18001d183  mov     rax, [rbp+Buffer]
0x18001d187  mov     ebx, r14d
0x18001d18a  cmp     [rax+40h], r14
0x18001d18e  mov     rax, [rbp+arg_20]
0x18001d192  setz    cl
0x18001d195  mov     [rax], cl
0x18001d197  jmp     loc_18001D0A4
```
