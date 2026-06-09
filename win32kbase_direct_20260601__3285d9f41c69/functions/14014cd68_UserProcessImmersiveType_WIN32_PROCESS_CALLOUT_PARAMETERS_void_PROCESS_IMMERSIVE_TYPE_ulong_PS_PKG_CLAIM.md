# UserProcessImmersiveType(_WIN32_PROCESS_CALLOUT_PARAMETERS *,void *,_PROCESS_IMMERSIVE_TYPE *,ulong *,_PS_PKG_CLAIM *)

- ea: `0x14014cd68`
- end: `0x14014d01f`
- name: `?UserProcessImmersiveType@@YAJPEAU_WIN32_PROCESS_CALLOUT_PARAMETERS@@PEAXPEAW4_PROCESS_IMMERSIVE_TYPE@@PEAKPEAU_PS_PKG_CLAIM@@@Z`
- size: `695`
- prototype: `int(struct _WIN32_PROCESS_CALLOUT_PARAMETERS *, void *, enum _PROCESS_IMMERSIVE_TYPE *, unsigned int *, struct _PS_PKG_CLAIM *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14014bc30`
- `0x14014c2bc`

## callees

- `0x14014cd68`
- `0x14014d028`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14014cf67`
- `ntoskrnl!ProbeForRead` at `0x14014cf67`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14014cee7`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14014cee7`
- `ntoskrnl!SeQueryInformationToken` at `0x14014cdb6`
- `ntoskrnl!SeQueryInformationToken` at `0x14014cdd5`
- `ntoskrnl!SeQueryInformationToken` at `0x14014cdb6`
- `ntoskrnl!SeQueryInformationToken` at `0x14014cdd5`
- `ntoskrnl!RtlCompareMemory` at `0x14014cf85`
- `ntoskrnl!RtlCompareMemory` at `0x14014cf85`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x14014ce3a`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x14014cebb`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x14014ce3a`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x14014cebb`
- `ntoskrnl!RtlImageNtHeader` at `0x14014cef6`
- `ntoskrnl!RtlImageNtHeader` at `0x14014cef6`
- `ntoskrnl!RtlQueryPackageClaims` at `0x14014ce6f`
- `ntoskrnl!RtlQueryPackageClaims` at `0x14014ce6f`

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
0x14014cd68  mov     rax, rsp
0x14014cd6b  mov     [rax+8], rbx
0x14014cd6f  mov     [rax+10h], rsi
0x14014cd73  push    rdi
0x14014cd74  push    r12
0x14014cd76  push    r13
0x14014cd78  push    r14
0x14014cd7a  push    r15
0x14014cd7c  sub     rsp, 70h
0x14014cd80  mov     r12, r9
0x14014cd83  mov     r14, r8
0x14014cd86  mov     rsi, rdx
0x14014cd89  mov     r13, rcx
0x14014cd8c  xor     edi, edi
0x14014cd8e  mov     [rax+20h], dil
0x14014cd92  mov     [rax-58h], edi
0x14014cd95  mov     [rax-54h], edi
0x14014cd98  mov     [rax+18h], dil
0x14014cd9c  mov     [r8], edi
0x14014cd9f  mov     [r9], edi
0x14014cda2  mov     rbx, [rsp+98h+arg_20]
0x14014cdaa  mov     [rbx], rdi
0x14014cdad  mov     r8, r9; TokenInformation
0x14014cdb0  lea     edx, [rdi+20h]; TokenInformationClass
0x14014cdb3  mov     rcx, rsi; Token
0x14014cdb6  call    cs:__imp_SeQueryInformationToken
0x14014cdbd  nop     dword ptr [rax+rax+00h]
0x14014cdc2  test    eax, eax
0x14014cdc4  js      loc_14014D004
0x14014cdca  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x14014cdcf  lea     edx, [rdi+19h]; TokenInformationClass
0x14014cdd2  mov     rcx, rsi; Token
0x14014cdd5  call    cs:__imp_SeQueryInformationToken
0x14014cddc  nop     dword ptr [rax+rax+00h]
0x14014cde1  test    eax, eax
0x14014cde3  js      loc_14014D004
0x14014cde9  mov     [rsp+98h+arg_20], rdi
0x14014cdf1  mov     [rsp+98h+Address], rdi
0x14014cdf6  lea     rax, [rsp+98h+arg_20]
0x14014cdfe  mov     [rsp+98h+var_78], rax
0x14014ce03  lea     r9, [rsp+98h+Address]
0x14014ce08  lea     r8, [rsp+98h+TokenInformation+4]
0x14014ce0d  mov     rcx, rsi
0x14014ce10  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x14014ce15  movzx   eax, ax
0x14014ce18  mov     ecx, eax
0x14014ce1a  or      ecx, 0C0070000h
0x14014ce20  test    eax, eax
0x14014ce22  cmovnz  eax, ecx
0x14014ce25  test    eax, eax
0x14014ce27  js      loc_14014D004
0x14014ce2d  lea     r8, [rsp+98h+arg_10]
0x14014ce35  xor     edx, edx
0x14014ce37  mov     rcx, rsi
0x14014ce3a  call    cs:__imp_PsQueryProcessAttributesByToken
0x14014ce41  nop     dword ptr [rax+rax+00h]
0x14014ce46  cmp     [rsp+98h+arg_10], dil
0x14014ce4e  jz      short loc_14014CEA2
0x14014ce50  mov     [rsp+98h+var_60], rdi
0x14014ce55  mov     [rsp+98h+var_68], rbx
0x14014ce5a  mov     [rsp+98h+var_70], rdi
0x14014ce5f  mov     [rsp+98h+var_78], rdi
0x14014ce64  xor     r9d, r9d
0x14014ce67  xor     r8d, r8d
0x14014ce6a  xor     edx, edx
0x14014ce6c  mov     rcx, rsi
0x14014ce6f  call    cs:__imp_RtlQueryPackageClaims
0x14014ce76  nop     dword ptr [rax+rax+00h]
0x14014ce7b  test    eax, eax
0x14014ce7d  js      loc_14014D004
0x14014ce83  mov     eax, [rbx]
0x14014ce85  mov     ebx, eax
0x14014ce87  shr     ebx, 0Bh
0x14014ce8a  mov     edi, 1
0x14014ce8f  and     bl, dil
0x14014ce92  bt      eax, 9
0x14014ce96  jnb     short loc_14014CE9D
0x14014ce98  mov     r15b, dil
0x14014ce9b  jmp     short loc_14014CEAD
0x14014ce9d  xor     r15b, r15b
0x14014cea0  jmp     short loc_14014CEAD
0x14014cea2  mov     r15b, dil
0x14014cea5  mov     bl, dil
0x14014cea8  mov     edi, 1
0x14014cead  xor     r8d, r8d
0x14014ceb0  lea     rdx, [rsp+98h+arg_18]
0x14014ceb8  mov     rcx, rsi
0x14014cebb  call    cs:__imp_PsQueryProcessAttributesByToken
0x14014cec2  nop     dword ptr [rax+rax+00h]
0x14014cec7  cmp     [rsp+98h+arg_18], 0
0x14014cecf  setnz   byte ptr [rsp+98h+arg_20]
0x14014ced7  mov     eax, [r13+18h]
0x14014cedb  test    al, 2
0x14014cedd  jz      loc_14014CFDB
0x14014cee3  mov     rcx, [r13+10h]
0x14014cee7  call    cs:__imp_PsGetProcessSectionBaseAddress
0x14014ceee  nop     dword ptr [rax+rax+00h]
0x14014cef3  mov     rcx, rax; BaseAddress
0x14014cef6  call    cs:__imp_RtlImageNtHeader
0x14014cefd  nop     dword ptr [rax+rax+00h]
0x14014cf02  mov     [rsp+98h+var_50], rax
0x14014cf07  mov     rax, [rsp+98h+var_50]
0x14014cf0c  test    rax, rax
0x14014cf0f  jnz     short loc_14014CF1B
0x14014cf11  mov     eax, 0C0000001h
0x14014cf16  jmp     loc_14014D004
0x14014cf1b  mov     rdx, [rsp+98h+var_50]
0x14014cf20  mov     rax, [rsp+98h+var_50]
0x14014cf25  movzx   ecx, word ptr [rax+14h]
0x14014cf29  lea     rax, [rdx+18h]
0x14014cf2d  add     rax, rcx
0x14014cf30  mov     [rsp+98h+Address], rax
0x14014cf35  mov     rax, [rsp+98h+var_50]
0x14014cf3a  movzx   r13d, word ptr [rax+6]
0x14014cf3f  xor     esi, esi
0x14014cf41  cmp     si, r13w
0x14014cf45  jnb     loc_14014CFD7
0x14014cf4b  mov     [rsp+98h+var_40], 28h ; '('
0x14014cf54  mov     rcx, [rsp+98h+Address]; Address
0x14014cf59  mov     [rsp+98h+var_40], rdi
0x14014cf5e  mov     r8d, 4; Alignment
0x14014cf64  mov     rdx, rdi; Length
0x14014cf67  call    cs:__imp_ProbeForRead
0x14014cf6e  nop     dword ptr [rax+rax+00h]
0x14014cf73  mov     r8d, 8; Length
0x14014cf79  lea     rdx, aImrsiv; ".imrsiv"
0x14014cf80  mov     rcx, [rsp+98h+Address]; Source1
0x14014cf85  call    cs:__imp_RtlCompareMemory
0x14014cf8c  nop     dword ptr [rax+rax+00h]
0x14014cf91  cmp     rax, 8
0x14014cf95  jnz     short loc_14014CFC1
0x14014cf97  cmp     dword ptr [r12], 0
0x14014cf9c  jz      short loc_14014CFA5
0x14014cf9e  mov     [r14], edi
0x14014cfa1  xor     eax, eax
0x14014cfa3  jmp     short loc_14014D004
0x14014cfa5  cmp     dword ptr [rsp+98h+TokenInformation], 2000h
0x14014cfad  jnb     short loc_14014CFB6
0x14014cfaf  mov     eax, 0C0000001h
0x14014cfb4  jmp     short loc_14014D004
0x14014cfb6  mov     dword ptr [r14], 2
0x14014cfbd  xor     eax, eax
0x14014cfbf  jmp     short loc_14014D004
0x14014cfc1  mov     rax, [rsp+98h+Address]
0x14014cfc6  add     rax, 28h ; '('
0x14014cfca  mov     [rsp+98h+Address], rax
0x14014cfcf  add     si, di
0x14014cfd2  jmp     loc_14014CF41
0x14014cfd7  jmp     short loc_14014CFDB
0x14014cfd9  jmp     short loc_14014D004
0x14014cfdb  cmp     byte ptr [rsp+98h+arg_20], 0
0x14014cfe3  jz      short loc_14014D002
0x14014cfe5  test    bl, bl
0x14014cfe7  jnz     short loc_14014CFF0
0x14014cfe9  cmp     dword ptr [r12], 0
0x14014cfee  jz      short loc_14014D002
0x14014cff0  cmp     dword ptr [rsp+98h+TokenInformation+4], 30000h
0x14014cff8  jz      short loc_14014D002
0x14014cffa  test    r15b, r15b
0x14014cffd  jnz     short loc_14014D002
0x14014cfff  mov     [r14], edi
0x14014d002  xor     eax, eax
0x14014d004  lea     r11, [rsp+98h+var_28]
0x14014d009  mov     rbx, [r11+30h]
0x14014d00d  mov     rsi, [r11+38h]
0x14014d011  mov     rsp, r11
0x14014d014  pop     r15
0x14014d016  pop     r14
0x14014d018  pop     r13
0x14014d01a  pop     r12
0x14014d01c  pop     rdi
0x14014d01d  retn
0x14023957a  push    rbp
0x14023957c  sub     rsp, 40h
0x140239580  mov     rbp, rdx
0x140239583  mov     eax, 1
0x140239588  add     rsp, 40h
0x14023958c  pop     rbp
0x14023958d  retn
```
