# UserProcessImmersiveType(_WIN32_PROCESS_CALLOUT_PARAMETERS *,void *,_PROCESS_IMMERSIVE_TYPE *,ulong *,_PS_PKG_CLAIM *)

- ea: `0x1400b4f98`
- end: `0x1400b524f`
- name: `?UserProcessImmersiveType@@YAJPEAU_WIN32_PROCESS_CALLOUT_PARAMETERS@@PEAXPEAW4_PROCESS_IMMERSIVE_TYPE@@PEAKPEAU_PS_PKG_CLAIM@@@Z`
- size: `695`
- prototype: `int(struct _WIN32_PROCESS_CALLOUT_PARAMETERS *, void *, enum _PROCESS_IMMERSIVE_TYPE *, unsigned int *, struct _PS_PKG_CLAIM *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400b30d0`
- `0x1400b375c`

## callees

- `0x1400b4f98`
- `0x1400b5258`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400b5197`
- `ntoskrnl!ProbeForRead` at `0x1400b5197`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400b5117`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400b5117`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b4fe6`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b5005`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b4fe6`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b5005`
- `ntoskrnl!RtlCompareMemory` at `0x1400b51b5`
- `ntoskrnl!RtlCompareMemory` at `0x1400b51b5`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1400b506a`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1400b50eb`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1400b506a`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1400b50eb`
- `ntoskrnl!RtlImageNtHeader` at `0x1400b5126`
- `ntoskrnl!RtlImageNtHeader` at `0x1400b5126`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1400b509f`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1400b509f`

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
0x1400b4f98  mov     rax, rsp
0x1400b4f9b  mov     [rax+8], rbx
0x1400b4f9f  mov     [rax+10h], rsi
0x1400b4fa3  push    rdi
0x1400b4fa4  push    r12
0x1400b4fa6  push    r13
0x1400b4fa8  push    r14
0x1400b4faa  push    r15
0x1400b4fac  sub     rsp, 70h
0x1400b4fb0  mov     r12, r9
0x1400b4fb3  mov     r14, r8
0x1400b4fb6  mov     rsi, rdx
0x1400b4fb9  mov     r13, rcx
0x1400b4fbc  xor     edi, edi
0x1400b4fbe  mov     [rax+20h], dil
0x1400b4fc2  mov     [rax-58h], edi
0x1400b4fc5  mov     [rax-54h], edi
0x1400b4fc8  mov     [rax+18h], dil
0x1400b4fcc  mov     [r8], edi
0x1400b4fcf  mov     [r9], edi
0x1400b4fd2  mov     rbx, [rsp+98h+arg_20]
0x1400b4fda  mov     [rbx], rdi
0x1400b4fdd  mov     r8, r9; TokenInformation
0x1400b4fe0  lea     edx, [rdi+20h]; TokenInformationClass
0x1400b4fe3  mov     rcx, rsi; Token
0x1400b4fe6  call    cs:__imp_SeQueryInformationToken
0x1400b4fed  nop     dword ptr [rax+rax+00h]
0x1400b4ff2  test    eax, eax
0x1400b4ff4  js      loc_1400B5234
0x1400b4ffa  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x1400b4fff  lea     edx, [rdi+19h]; TokenInformationClass
0x1400b5002  mov     rcx, rsi; Token
0x1400b5005  call    cs:__imp_SeQueryInformationToken
0x1400b500c  nop     dword ptr [rax+rax+00h]
0x1400b5011  test    eax, eax
0x1400b5013  js      loc_1400B5234
0x1400b5019  mov     [rsp+98h+arg_20], rdi
0x1400b5021  mov     [rsp+98h+Address], rdi
0x1400b5026  lea     rax, [rsp+98h+arg_20]
0x1400b502e  mov     [rsp+98h+var_78], rax
0x1400b5033  lea     r9, [rsp+98h+Address]
0x1400b5038  lea     r8, [rsp+98h+TokenInformation+4]
0x1400b503d  mov     rcx, rsi
0x1400b5040  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x1400b5045  movzx   eax, ax
0x1400b5048  mov     ecx, eax
0x1400b504a  or      ecx, 0C0070000h
0x1400b5050  test    eax, eax
0x1400b5052  cmovnz  eax, ecx
0x1400b5055  test    eax, eax
0x1400b5057  js      loc_1400B5234
0x1400b505d  lea     r8, [rsp+98h+arg_10]
0x1400b5065  xor     edx, edx
0x1400b5067  mov     rcx, rsi
0x1400b506a  call    cs:__imp_PsQueryProcessAttributesByToken
0x1400b5071  nop     dword ptr [rax+rax+00h]
0x1400b5076  cmp     [rsp+98h+arg_10], dil
0x1400b507e  jz      short loc_1400B50D2
0x1400b5080  mov     [rsp+98h+var_60], rdi
0x1400b5085  mov     [rsp+98h+var_68], rbx
0x1400b508a  mov     [rsp+98h+var_70], rdi
0x1400b508f  mov     [rsp+98h+var_78], rdi
0x1400b5094  xor     r9d, r9d
0x1400b5097  xor     r8d, r8d
0x1400b509a  xor     edx, edx
0x1400b509c  mov     rcx, rsi
0x1400b509f  call    cs:__imp_RtlQueryPackageClaims
0x1400b50a6  nop     dword ptr [rax+rax+00h]
0x1400b50ab  test    eax, eax
0x1400b50ad  js      loc_1400B5234
0x1400b50b3  mov     eax, [rbx]
0x1400b50b5  mov     ebx, eax
0x1400b50b7  shr     ebx, 0Bh
0x1400b50ba  mov     edi, 1
0x1400b50bf  and     bl, dil
0x1400b50c2  bt      eax, 9
0x1400b50c6  jnb     short loc_1400B50CD
0x1400b50c8  mov     r15b, dil
0x1400b50cb  jmp     short loc_1400B50DD
0x1400b50cd  xor     r15b, r15b
0x1400b50d0  jmp     short loc_1400B50DD
0x1400b50d2  mov     r15b, dil
0x1400b50d5  mov     bl, dil
0x1400b50d8  mov     edi, 1
0x1400b50dd  xor     r8d, r8d
0x1400b50e0  lea     rdx, [rsp+98h+arg_18]
0x1400b50e8  mov     rcx, rsi
0x1400b50eb  call    cs:__imp_PsQueryProcessAttributesByToken
0x1400b50f2  nop     dword ptr [rax+rax+00h]
0x1400b50f7  cmp     [rsp+98h+arg_18], 0
0x1400b50ff  setnz   byte ptr [rsp+98h+arg_20]
0x1400b5107  mov     eax, [r13+18h]
0x1400b510b  test    al, 2
0x1400b510d  jz      loc_1400B520B
0x1400b5113  mov     rcx, [r13+10h]
0x1400b5117  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1400b511e  nop     dword ptr [rax+rax+00h]
0x1400b5123  mov     rcx, rax; BaseAddress
0x1400b5126  call    cs:__imp_RtlImageNtHeader
0x1400b512d  nop     dword ptr [rax+rax+00h]
0x1400b5132  mov     [rsp+98h+var_50], rax
0x1400b5137  mov     rax, [rsp+98h+var_50]
0x1400b513c  test    rax, rax
0x1400b513f  jnz     short loc_1400B514B
0x1400b5141  mov     eax, 0C0000001h
0x1400b5146  jmp     loc_1400B5234
0x1400b514b  mov     rdx, [rsp+98h+var_50]
0x1400b5150  mov     rax, [rsp+98h+var_50]
0x1400b5155  movzx   ecx, word ptr [rax+14h]
0x1400b5159  lea     rax, [rdx+18h]
0x1400b515d  add     rax, rcx
0x1400b5160  mov     [rsp+98h+Address], rax
0x1400b5165  mov     rax, [rsp+98h+var_50]
0x1400b516a  movzx   r13d, word ptr [rax+6]
0x1400b516f  xor     esi, esi
0x1400b5171  cmp     si, r13w
0x1400b5175  jnb     loc_1400B5207
0x1400b517b  mov     [rsp+98h+var_40], 28h ; '('
0x1400b5184  mov     rcx, [rsp+98h+Address]; Address
0x1400b5189  mov     [rsp+98h+var_40], rdi
0x1400b518e  mov     r8d, 4; Alignment
0x1400b5194  mov     rdx, rdi; Length
0x1400b5197  call    cs:__imp_ProbeForRead
0x1400b519e  nop     dword ptr [rax+rax+00h]
0x1400b51a3  mov     r8d, 8; Length
0x1400b51a9  lea     rdx, aImrsiv; ".imrsiv"
0x1400b51b0  mov     rcx, [rsp+98h+Address]; Source1
0x1400b51b5  call    cs:__imp_RtlCompareMemory
0x1400b51bc  nop     dword ptr [rax+rax+00h]
0x1400b51c1  cmp     rax, 8
0x1400b51c5  jnz     short loc_1400B51F1
0x1400b51c7  cmp     dword ptr [r12], 0
0x1400b51cc  jz      short loc_1400B51D5
0x1400b51ce  mov     [r14], edi
0x1400b51d1  xor     eax, eax
0x1400b51d3  jmp     short loc_1400B5234
0x1400b51d5  cmp     dword ptr [rsp+98h+TokenInformation], 2000h
0x1400b51dd  jnb     short loc_1400B51E6
0x1400b51df  mov     eax, 0C0000001h
0x1400b51e4  jmp     short loc_1400B5234
0x1400b51e6  mov     dword ptr [r14], 2
0x1400b51ed  xor     eax, eax
0x1400b51ef  jmp     short loc_1400B5234
0x1400b51f1  mov     rax, [rsp+98h+Address]
0x1400b51f6  add     rax, 28h ; '('
0x1400b51fa  mov     [rsp+98h+Address], rax
0x1400b51ff  add     si, di
0x1400b5202  jmp     loc_1400B5171
0x1400b5207  jmp     short loc_1400B520B
0x1400b5209  jmp     short loc_1400B5234
0x1400b520b  cmp     byte ptr [rsp+98h+arg_20], 0
0x1400b5213  jz      short loc_1400B5232
0x1400b5215  test    bl, bl
0x1400b5217  jnz     short loc_1400B5220
0x1400b5219  cmp     dword ptr [r12], 0
0x1400b521e  jz      short loc_1400B5232
0x1400b5220  cmp     dword ptr [rsp+98h+TokenInformation+4], 30000h
0x1400b5228  jz      short loc_1400B5232
0x1400b522a  test    r15b, r15b
0x1400b522d  jnz     short loc_1400B5232
0x1400b522f  mov     [r14], edi
0x1400b5232  xor     eax, eax
0x1400b5234  lea     r11, [rsp+98h+var_28]
0x1400b5239  mov     rbx, [r11+30h]
0x1400b523d  mov     rsi, [r11+38h]
0x1400b5241  mov     rsp, r11
0x1400b5244  pop     r15
0x1400b5246  pop     r14
0x1400b5248  pop     r13
0x1400b524a  pop     r12
0x1400b524c  pop     rdi
0x1400b524d  retn
0x140239aa7  push    rbp
0x140239aa9  sub     rsp, 40h
0x140239aad  mov     rbp, rdx
0x140239ab0  mov     eax, 1
0x140239ab5  add     rsp, 40h
0x140239ab9  pop     rbp
0x140239aba  retn
```
