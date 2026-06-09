# GetDomainSid(void * *)

- ea: `0x180012540`
- end: `0x180012656`
- name: `?GetDomainSid@@YAKPEAPEAX@Z`
- size: `278`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x18000179c`
- `0x180012540`
- `0x18002e468`
- `0x18002f3ae`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1800125c4`
- `ADVAPI32!GetLengthSid` at `0x1800125c4`
- `ADVAPI32!LsaClose` at `0x180012621`
- `ADVAPI32!LsaClose` at `0x180012621`
- `ADVAPI32!LsaFreeMemory` at `0x18001260c`
- `ADVAPI32!LsaFreeMemory` at `0x18001260c`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001259e`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001259e`
- `ADVAPI32!LsaOpenPolicy` at `0x180012581`
- `ADVAPI32!LsaOpenPolicy` at `0x180012581`

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
0x180012540  mov     [rsp-18h+arg_0], rbx
0x180012545  mov     [rsp-18h+arg_18], rsi
0x18001254a  push    rbp
0x18001254b  push    rdi
0x18001254c  push    r14
0x18001254e  mov     rbp, rsp
0x180012551  sub     rsp, 50h
0x180012555  and     [rbp+PolicyHandle], 0
0x18001255a  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18001255e  and     [rbp+Buffer], 0
0x180012563  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180012567  xorps   xmm0, xmm0
0x18001256a  mov     r14, rcx
0x18001256d  xor     edi, edi
0x18001256f  xor     ecx, ecx; SystemName
0x180012571  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180012575  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180012579  lea     r8d, [rdi+1]; DesiredAccess
0x18001257d  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180012581  call    cs:__imp_LsaOpenPolicy
0x180012588  nop     dword ptr [rax+rax+00h]
0x18001258d  mov     ebx, eax
0x18001258f  test    eax, eax
0x180012591  jnz     short loc_180012603
0x180012593  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180012597  lea     r8, [rbp+Buffer]; Buffer
0x18001259b  lea     edx, [rdi+0Ch]; InformationClass
0x18001259e  call    cs:__imp_LsaQueryInformationPolicy
0x1800125a5  nop     dword ptr [rax+rax+00h]
0x1800125aa  mov     ebx, eax
0x1800125ac  test    eax, eax
0x1800125ae  jnz     short loc_180012603
0x1800125b0  mov     rax, [rbp+Buffer]
0x1800125b4  mov     rcx, [rax+40h]; pSid
0x1800125b8  test    rcx, rcx
0x1800125bb  jnz     short loc_1800125C4
0x1800125bd  mov     ebx, 4BCh
0x1800125c2  jmp     short loc_180012603
0x1800125c4  call    cs:__imp_GetLengthSid
0x1800125cb  nop     dword ptr [rax+rax+00h]
0x1800125d0  mov     ecx, eax; unsigned __int64
0x1800125d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800125d9  mov     esi, eax
0x1800125db  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800125e0  mov     rdi, rax
0x1800125e3  test    rax, rax
0x1800125e6  jnz     short loc_1800125ED
0x1800125e8  lea     ebx, [rax+8]
0x1800125eb  jmp     short loc_180012603
0x1800125ed  mov     rdx, [rbp+Buffer]
0x1800125f1  mov     r8, rsi; Size
0x1800125f4  mov     rcx, rdi; void *
0x1800125f7  mov     rdx, [rdx+40h]; Src
0x1800125fb  call    memmove_0
0x180012600  mov     [r14], rdi
0x180012603  mov     rcx, [rbp+Buffer]; Buffer
0x180012607  test    rcx, rcx
0x18001260a  jz      short loc_180012618
0x18001260c  call    cs:__imp_LsaFreeMemory
0x180012613  nop     dword ptr [rax+rax+00h]
0x180012618  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18001261c  test    rcx, rcx
0x18001261f  jz      short loc_18001262D
0x180012621  call    cs:__imp_LsaClose
0x180012628  nop     dword ptr [rax+rax+00h]
0x18001262d  test    ebx, ebx
0x18001262f  jz      short loc_18001263E
0x180012631  test    rdi, rdi
0x180012634  jz      short loc_18001263E
0x180012636  mov     rcx, rdi; lpMem
0x180012639  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001263e  lea     r11, [rsp+50h+var_s0]
0x180012643  mov     eax, ebx
0x180012645  mov     rbx, [r11+20h]
0x180012649  mov     rsi, [r11+38h]
0x18001264d  mov     rsp, r11
0x180012650  pop     r14
0x180012652  pop     rdi
0x180012653  pop     rbp
0x180012654  retn
```
