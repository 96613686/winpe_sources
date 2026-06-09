# UserProcessImmersiveType(_WIN32_PROCESS_CALLOUT_PARAMETERS *,void *,_PROCESS_IMMERSIVE_TYPE *,ulong *,_PS_PKG_CLAIM *)

- ea: `0x14014ed3c`
- end: `0x14014eff3`
- name: `?UserProcessImmersiveType@@YAJPEAU_WIN32_PROCESS_CALLOUT_PARAMETERS@@PEAXPEAW4_PROCESS_IMMERSIVE_TYPE@@PEAKPEAU_PS_PKG_CLAIM@@@Z`
- size: `695`
- prototype: `int(struct _WIN32_PROCESS_CALLOUT_PARAMETERS *, void *, enum _PROCESS_IMMERSIVE_TYPE *, unsigned int *, struct _PS_PKG_CLAIM *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14014da60`
- `0x14014e0ec`

## callees

- `0x14014ed3c`
- `0x14014effc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14014ef3b`
- `ntoskrnl!ProbeForRead` at `0x14014ef3b`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14014eebb`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14014eebb`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ed8a`
- `ntoskrnl!SeQueryInformationToken` at `0x14014eda9`
- `ntoskrnl!SeQueryInformationToken` at `0x14014ed8a`
- `ntoskrnl!SeQueryInformationToken` at `0x14014eda9`
- `ntoskrnl!RtlCompareMemory` at `0x14014ef59`
- `ntoskrnl!RtlCompareMemory` at `0x14014ef59`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x14014ee0e`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x14014ee8f`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x14014ee0e`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x14014ee8f`
- `ntoskrnl!RtlImageNtHeader` at `0x14014eeca`
- `ntoskrnl!RtlImageNtHeader` at `0x14014eeca`
- `ntoskrnl!RtlQueryPackageClaims` at `0x14014ee43`
- `ntoskrnl!RtlQueryPackageClaims` at `0x14014ee43`

## pseudocode

```c
int __fastcall UserProcessImmersiveType(
        struct _WIN32_PROCESS_CALLOUT_PARAMETERS *a1,
        void *a2,
        enum _PROCESS_IMMERSIVE_TYPE *a3,
        PVOID *a4,
        struct _PS_PKG_CLAIM *a5)
{
  struct _PS_PKG_CLAIM *v9; // rbx
  int result; // eax
  __int64 v11; // rdx
  int v12; // eax
  bool v13; // bl
  bool v14; // r15
  void *ProcessSectionBaseAddress; // rax
  WORD NumberOfSections; // r13
  WORD i; // si
  PVOID TokenInformation; // [rsp+40h] [rbp-58h] BYREF
  PIMAGE_NT_HEADERS v19; // [rsp+48h] [rbp-50h]
  volatile void *Address[4]; // [rsp+50h] [rbp-48h] BYREF
  char v21; // [rsp+B0h] [rbp+18h] BYREF
  char v22; // [rsp+B8h] [rbp+20h] BYREF

  v22 = 0;
  TokenInformation = 0;
  v21 = 0;
  *(_DWORD *)a3 = 0;
  *(_DWORD *)a4 = 0;
  v9 = a5;
  *(_QWORD *)a5 = 0;
  result = SeQueryInformationToken(a2, TokenAppContainerNumber, a4);
  if ( result >= 0 )
  {
    result = SeQueryInformationToken(a2, TokenIntegrityLevel, &TokenInformation);
    if ( result >= 0 )
    {
      a5 = 0;
      Address[0] = 0;
      result = (unsigned __int16)AppModelPolicy_GetPolicy_Internal(a2, v11, (char *)&TokenInformation + 4, Address, &a5);
      if ( (_WORD)result )
        result = (unsigned __int16)result | 0xC0070000;
      if ( result >= 0 )
      {
        PsQueryProcessAttributesByToken(a2, 0, &v21);
        if ( v21 )
        {
          result = RtlQueryPackageClaims(a2, 0, 0, 0, 0, 0, v9, 0);
          if ( result < 0 )
            return result;
          v12 = *(_DWORD *)v9;
          v13 = (*(_DWORD *)v9 & 0x800) != 0;
          v14 = (v12 & 0x200) != 0;
        }
        else
        {
          v14 = 0;
          v13 = 0;
        }
        PsQueryProcessAttributesByToken(a2, &v22, 0);
        LOBYTE(a5) = v22 != 0;
        if ( (*((_DWORD *)a1 + 6) & 2) != 0 )
        {
          ProcessSectionBaseAddress = (void *)PsGetProcessSectionBaseAddress(*((_QWORD *)a1 + 2));
          v19 = RtlImageNtHeader(ProcessSectionBaseAddress);
          if ( !v19 )
            return -1073741823;
          Address[0] = (char *)&v19->OptionalHeader + v19->FileHeader.SizeOfOptionalHeader;
          NumberOfSections = v19->FileHeader.NumberOfSections;
          for ( i = 0; i < NumberOfSections; ++i )
          {
            Address[1] = (volatile void *)1;
            ProbeForRead(Address[0], 1u, 4u);
            if ( RtlCompareMemory((const void *)Address[0], ".imrsiv", 8u) == 8 )
            {
              if ( *(_DWORD *)a4 )
              {
                *(_DWORD *)a3 = 1;
                return 0;
              }
              else if ( (unsigned int)TokenInformation >= 0x2000 )
              {
                *(_DWORD *)a3 = 2;
                return 0;
              }
              else
              {
                return -1073741823;
              }
            }
            Address[0] = (char *)Address[0] + 40;
          }
        }
        if ( (_BYTE)a5 && (v13 || *(_DWORD *)a4) && HIDWORD(TokenInformation) != 196608 && !v14 )
          *(_DWORD *)a3 = 1;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14014ed3c  mov     rax, rsp
0x14014ed3f  mov     [rax+8], rbx
0x14014ed43  mov     [rax+10h], rsi
0x14014ed47  push    rdi
0x14014ed48  push    r12
0x14014ed4a  push    r13
0x14014ed4c  push    r14
0x14014ed4e  push    r15
0x14014ed50  sub     rsp, 70h
0x14014ed54  mov     r12, r9
0x14014ed57  mov     r14, r8
0x14014ed5a  mov     rsi, rdx
0x14014ed5d  mov     r13, rcx
0x14014ed60  xor     edi, edi
0x14014ed62  mov     [rax+20h], dil
0x14014ed66  mov     [rax-58h], edi
0x14014ed69  mov     [rax-54h], edi
0x14014ed6c  mov     [rax+18h], dil
0x14014ed70  mov     [r8], edi
0x14014ed73  mov     [r9], edi
0x14014ed76  mov     rbx, [rsp+98h+arg_20]
0x14014ed7e  mov     [rbx], rdi
0x14014ed81  mov     r8, r9; TokenInformation
0x14014ed84  lea     edx, [rdi+20h]; TokenInformationClass
0x14014ed87  mov     rcx, rsi; Token
0x14014ed8a  call    cs:__imp_SeQueryInformationToken
0x14014ed91  nop     dword ptr [rax+rax+00h]
0x14014ed96  test    eax, eax
0x14014ed98  js      loc_14014EFD8
0x14014ed9e  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x14014eda3  lea     edx, [rdi+19h]; TokenInformationClass
0x14014eda6  mov     rcx, rsi; Token
0x14014eda9  call    cs:__imp_SeQueryInformationToken
0x14014edb0  nop     dword ptr [rax+rax+00h]
0x14014edb5  test    eax, eax
0x14014edb7  js      loc_14014EFD8
0x14014edbd  mov     [rsp+98h+arg_20], rdi
0x14014edc5  mov     [rsp+98h+Address], rdi
0x14014edca  lea     rax, [rsp+98h+arg_20]
0x14014edd2  mov     [rsp+98h+var_78], rax
0x14014edd7  lea     r9, [rsp+98h+Address]
0x14014eddc  lea     r8, [rsp+98h+TokenInformation+4]
0x14014ede1  mov     rcx, rsi
0x14014ede4  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x14014ede9  movzx   eax, ax
0x14014edec  mov     ecx, eax
0x14014edee  or      ecx, 0C0070000h
0x14014edf4  test    eax, eax
0x14014edf6  cmovnz  eax, ecx
0x14014edf9  test    eax, eax
0x14014edfb  js      loc_14014EFD8
0x14014ee01  lea     r8, [rsp+98h+arg_10]
0x14014ee09  xor     edx, edx
0x14014ee0b  mov     rcx, rsi
0x14014ee0e  call    cs:__imp_PsQueryProcessAttributesByToken
0x14014ee15  nop     dword ptr [rax+rax+00h]
0x14014ee1a  cmp     [rsp+98h+arg_10], dil
0x14014ee22  jz      short loc_14014EE76
0x14014ee24  mov     [rsp+98h+var_60], rdi
0x14014ee29  mov     [rsp+98h+var_68], rbx
0x14014ee2e  mov     [rsp+98h+var_70], rdi
0x14014ee33  mov     [rsp+98h+var_78], rdi
0x14014ee38  xor     r9d, r9d
0x14014ee3b  xor     r8d, r8d
0x14014ee3e  xor     edx, edx
0x14014ee40  mov     rcx, rsi
0x14014ee43  call    cs:__imp_RtlQueryPackageClaims
0x14014ee4a  nop     dword ptr [rax+rax+00h]
0x14014ee4f  test    eax, eax
0x14014ee51  js      loc_14014EFD8
0x14014ee57  mov     eax, [rbx]
0x14014ee59  mov     ebx, eax
0x14014ee5b  shr     ebx, 0Bh
0x14014ee5e  mov     edi, 1
0x14014ee63  and     bl, dil
0x14014ee66  bt      eax, 9
0x14014ee6a  jnb     short loc_14014EE71
0x14014ee6c  mov     r15b, dil
0x14014ee6f  jmp     short loc_14014EE81
0x14014ee71  xor     r15b, r15b
0x14014ee74  jmp     short loc_14014EE81
0x14014ee76  mov     r15b, dil
0x14014ee79  mov     bl, dil
0x14014ee7c  mov     edi, 1
0x14014ee81  xor     r8d, r8d
0x14014ee84  lea     rdx, [rsp+98h+arg_18]
0x14014ee8c  mov     rcx, rsi
0x14014ee8f  call    cs:__imp_PsQueryProcessAttributesByToken
0x14014ee96  nop     dword ptr [rax+rax+00h]
0x14014ee9b  cmp     [rsp+98h+arg_18], 0
0x14014eea3  setnz   byte ptr [rsp+98h+arg_20]
0x14014eeab  mov     eax, [r13+18h]
0x14014eeaf  test    al, 2
0x14014eeb1  jz      loc_14014EFAF
0x14014eeb7  mov     rcx, [r13+10h]
0x14014eebb  call    cs:__imp_PsGetProcessSectionBaseAddress
0x14014eec2  nop     dword ptr [rax+rax+00h]
0x14014eec7  mov     rcx, rax; BaseAddress
0x14014eeca  call    cs:__imp_RtlImageNtHeader
0x14014eed1  nop     dword ptr [rax+rax+00h]
0x14014eed6  mov     [rsp+98h+var_50], rax
0x14014eedb  mov     rax, [rsp+98h+var_50]
0x14014eee0  test    rax, rax
0x14014eee3  jnz     short loc_14014EEEF
0x14014eee5  mov     eax, 0C0000001h
0x14014eeea  jmp     loc_14014EFD8
0x14014eeef  mov     rdx, [rsp+98h+var_50]
0x14014eef4  mov     rax, [rsp+98h+var_50]
0x14014eef9  movzx   ecx, word ptr [rax+14h]
0x14014eefd  lea     rax, [rdx+18h]
0x14014ef01  add     rax, rcx
0x14014ef04  mov     [rsp+98h+Address], rax
0x14014ef09  mov     rax, [rsp+98h+var_50]
0x14014ef0e  movzx   r13d, word ptr [rax+6]
0x14014ef13  xor     esi, esi
0x14014ef15  cmp     si, r13w
0x14014ef19  jnb     loc_14014EFAB
0x14014ef1f  mov     [rsp+98h+var_40], 28h ; '('
0x14014ef28  mov     rcx, [rsp+98h+Address]; Address
0x14014ef2d  mov     [rsp+98h+var_40], rdi
0x14014ef32  mov     r8d, 4; Alignment
0x14014ef38  mov     rdx, rdi; Length
0x14014ef3b  call    cs:__imp_ProbeForRead
0x14014ef42  nop     dword ptr [rax+rax+00h]
0x14014ef47  mov     r8d, 8; Length
0x14014ef4d  lea     rdx, aImrsiv; ".imrsiv"
0x14014ef54  mov     rcx, [rsp+98h+Address]; Source1
0x14014ef59  call    cs:__imp_RtlCompareMemory
0x14014ef60  nop     dword ptr [rax+rax+00h]
0x14014ef65  cmp     rax, 8
0x14014ef69  jnz     short loc_14014EF95
0x14014ef6b  cmp     dword ptr [r12], 0
0x14014ef70  jz      short loc_14014EF79
0x14014ef72  mov     [r14], edi
0x14014ef75  xor     eax, eax
0x14014ef77  jmp     short loc_14014EFD8
0x14014ef79  cmp     dword ptr [rsp+98h+TokenInformation], 2000h
0x14014ef81  jnb     short loc_14014EF8A
0x14014ef83  mov     eax, 0C0000001h
0x14014ef88  jmp     short loc_14014EFD8
0x14014ef8a  mov     dword ptr [r14], 2
0x14014ef91  xor     eax, eax
0x14014ef93  jmp     short loc_14014EFD8
0x14014ef95  mov     rax, [rsp+98h+Address]
0x14014ef9a  add     rax, 28h ; '('
0x14014ef9e  mov     [rsp+98h+Address], rax
0x14014efa3  add     si, di
0x14014efa6  jmp     loc_14014EF15
0x14014efab  jmp     short loc_14014EFAF
0x14014efad  jmp     short loc_14014EFD8
0x14014efaf  cmp     byte ptr [rsp+98h+arg_20], 0
0x14014efb7  jz      short loc_14014EFD6
0x14014efb9  test    bl, bl
0x14014efbb  jnz     short loc_14014EFC4
0x14014efbd  cmp     dword ptr [r12], 0
0x14014efc2  jz      short loc_14014EFD6
0x14014efc4  cmp     dword ptr [rsp+98h+TokenInformation+4], 30000h
0x14014efcc  jz      short loc_14014EFD6
0x14014efce  test    r15b, r15b
0x14014efd1  jnz     short loc_14014EFD6
0x14014efd3  mov     [r14], edi
0x14014efd6  xor     eax, eax
0x14014efd8  lea     r11, [rsp+98h+var_28]
0x14014efdd  mov     rbx, [r11+30h]
0x14014efe1  mov     rsi, [r11+38h]
0x14014efe5  mov     rsp, r11
0x14014efe8  pop     r15
0x14014efea  pop     r14
0x14014efec  pop     r13
0x14014efee  pop     r12
0x14014eff0  pop     rdi
0x14014eff1  retn
0x140239cd2  push    rbp
0x140239cd4  sub     rsp, 40h
0x140239cd8  mov     rbp, rdx
0x140239cdb  mov     eax, 1
0x140239ce0  add     rsp, 40h
0x140239ce4  pop     rbp
0x140239ce5  retn
```
