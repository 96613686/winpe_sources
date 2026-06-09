# GetDomainSid(void * *)

- ea: `0x180013190`
- end: `0x1800132ad`
- name: `?GetDomainSid@@YAKPEAPEAX@Z`
- size: `285`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x18000214c`
- `0x1800024b2`
- `0x180013190`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013289`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013289`
- `ADVAPI32!LsaClose` at `0x180013271`
- `ADVAPI32!LsaClose` at `0x180013271`
- `ADVAPI32!LsaFreeMemory` at `0x18001325c`
- `ADVAPI32!LsaFreeMemory` at `0x18001325c`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1800131ee`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1800131ee`
- `ADVAPI32!LsaOpenPolicy` at `0x1800131d1`
- `ADVAPI32!LsaOpenPolicy` at `0x1800131d1`
- `ADVAPI32!GetLengthSid` at `0x180013214`
- `ADVAPI32!GetLengthSid` at `0x180013214`

## pseudocode

```c
__int64 __fastcall GetDomainSid(void **a1)
{
  void *v2; // rdi
  unsigned int v3; // ebx
  void *v4; // rcx
  unsigned __int64 LengthSid; // rsi
  void *v6; // rax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+78h] [rbp+28h] BYREF
  PVOID PolicyHandle; // [rsp+80h] [rbp+30h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  v2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( !v3 )
  {
    v3 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( !v3 )
    {
      v4 = (void *)*((_QWORD *)Buffer + 8);
      if ( v4 )
      {
        LengthSid = GetLengthSid(v4);
        v6 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
        v2 = v6;
        if ( v6 )
        {
          memmove_0(v6, *((const void **)Buffer + 8), LengthSid);
          *a1 = v2;
        }
        else
        {
          v3 = 8;
        }
      }
      else
      {
        v3 = 1212;
      }
    }
  }
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v3 && v2 )
    operator delete(v2);
  return v3;
}

```

## disassembly

```asm
0x180013190  mov     [rsp-18h+arg_0], rbx
0x180013195  mov     [rsp-18h+arg_18], rsi
0x18001319a  push    rbp
0x18001319b  push    rdi
0x18001319c  push    r14
0x18001319e  mov     rbp, rsp
0x1800131a1  sub     rsp, 50h
0x1800131a5  and     [rbp+PolicyHandle], 0
0x1800131aa  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800131ae  and     [rbp+Buffer], 0
0x1800131b3  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800131b7  xorps   xmm0, xmm0
0x1800131ba  mov     r14, rcx
0x1800131bd  xor     edi, edi
0x1800131bf  xor     ecx, ecx; SystemName
0x1800131c1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800131c5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800131c9  lea     r8d, [rdi+1]; DesiredAccess
0x1800131cd  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800131d1  call    cs:__imp_LsaOpenPolicy
0x1800131d8  nop     dword ptr [rax+rax+00h]
0x1800131dd  mov     ebx, eax
0x1800131df  test    eax, eax
0x1800131e1  jnz     short loc_180013253
0x1800131e3  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800131e7  lea     r8, [rbp+Buffer]; Buffer
0x1800131eb  lea     edx, [rdi+0Ch]; InformationClass
0x1800131ee  call    cs:__imp_LsaQueryInformationPolicy
0x1800131f5  nop     dword ptr [rax+rax+00h]
0x1800131fa  mov     ebx, eax
0x1800131fc  test    eax, eax
0x1800131fe  jnz     short loc_180013253
0x180013200  mov     rax, [rbp+Buffer]
0x180013204  mov     rcx, [rax+40h]; pSid
0x180013208  test    rcx, rcx
0x18001320b  jnz     short loc_180013214
0x18001320d  mov     ebx, 4BCh
0x180013212  jmp     short loc_180013253
0x180013214  call    cs:__imp_GetLengthSid
0x18001321b  nop     dword ptr [rax+rax+00h]
0x180013220  mov     ecx, eax; unsigned __int64
0x180013222  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013229  mov     esi, eax
0x18001322b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013230  mov     rdi, rax
0x180013233  test    rax, rax
0x180013236  jnz     short loc_18001323D
0x180013238  lea     ebx, [rax+8]
0x18001323b  jmp     short loc_180013253
0x18001323d  mov     rdx, [rbp+Buffer]
0x180013241  mov     r8, rsi; Size
0x180013244  mov     rcx, rdi; void *
0x180013247  mov     rdx, [rdx+40h]; Src
0x18001324b  call    memmove_0
0x180013250  mov     [r14], rdi
0x180013253  mov     rcx, [rbp+Buffer]; Buffer
0x180013257  test    rcx, rcx
0x18001325a  jz      short loc_180013268
0x18001325c  call    cs:__imp_LsaFreeMemory
0x180013263  nop     dword ptr [rax+rax+00h]
0x180013268  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18001326c  test    rcx, rcx
0x18001326f  jz      short loc_18001327D
0x180013271  call    cs:__imp_LsaClose
0x180013278  nop     dword ptr [rax+rax+00h]
0x18001327d  test    ebx, ebx
0x18001327f  jz      short loc_180013295
0x180013281  test    rdi, rdi
0x180013284  jz      short loc_180013295
0x180013286  mov     rcx, rdi
0x180013289  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013290  nop     dword ptr [rax+rax+00h]
0x180013295  lea     r11, [rsp+50h+var_s0]
0x18001329a  mov     eax, ebx
0x18001329c  mov     rbx, [r11+20h]
0x1800132a0  mov     rsi, [r11+38h]
0x1800132a4  mov     rsp, r11
0x1800132a7  pop     r14
0x1800132a9  pop     rdi
0x1800132aa  pop     rbp
0x1800132ab  retn
```
