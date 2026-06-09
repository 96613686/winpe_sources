# SkPreAllocatePageEncryptionResources

- ea: `0x1400bfa88`
- end: `0x1400bfc3b`
- name: `SkPreAllocatePageEncryptionResources`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400b86ec`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x1400bfa88`
- `0x1400c0574`
- `0x1400c0624`
- `0x1400c2614`
- `0x1400c2708`
- `0x1400c2800`
- `0x1400f9a80`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400bfb17`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400bfb17`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400bfba0`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400bfbba`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400bfbd4`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400bfbee`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400bfba0`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400bfbba`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400bfbd4`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400bfbee`

## pseudocode

```c
__int64 SkPreAllocatePageEncryptionResources()
{
  char v0; // di
  char v1; // r15
  char v2; // bp
  char v3; // r14
  __int64 v4; // rdx
  __int64 v5; // rcx
  int inited; // ebx
  __int64 v7; // r8
  __int64 v9; // rsi
  __m128i si128; // [rsp+20h] [rbp-58h]
  int v11; // [rsp+30h] [rbp-48h]
  int v12; // [rsp+34h] [rbp-44h]

  v11 = 6;
  v12 = 7;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v0 = 0;
  v1 = 0;
  v2 = 0;
  v3 = 0;
  memset_0(&qword_1401740B0, 0, 0x358u);
  inited = SkpOpenAesGcmProvider(&qword_1401740B0);
  if ( inited >= 0 )
  {
    v0 = 1;
    inited = SkpOpenKdfProvider(&qword_1401740B8);
    if ( inited >= 0 )
    {
      v1 = 1;
      inited = BCryptOpenAlgorithmProvider(&hAlgorithm, L"RSA", 0, 1u);
      if ( inited >= 0 )
      {
        v2 = 1;
        inited = SkpOpenAesXtsProvider(&qword_1401740C8);
        if ( inited >= 0 )
        {
          v3 = 1;
          qword_1401740D0 = SkAllocatePool(512, ObjectLengthSP800108);
          if ( qword_1401740D0 )
          {
            v9 = 0;
            while ( 1 )
            {
              inited = SkpInitPerDomainPageEncryptionState(si128.m128i_u32[v9], &qword_1401740D8[17 * (unsigned int)v9]);
              if ( inited < 0 )
                break;
              v9 = (unsigned int)(v9 + 1);
              if ( (unsigned int)v9 >= 6 )
                return (unsigned int)inited;
            }
          }
          else
          {
            inited = -1073741670;
          }
        }
      }
    }
  }
  SkpDeleteAllPerDomainPageEncryptionState(v5, v4, v7);
  if ( qword_1401740D0 )
  {
    SkFreePool(512, qword_1401740D0);
    qword_1401740D0 = 0;
  }
  if ( v2 )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( v1 )
    BCryptCloseAlgorithmProvider(qword_1401740B8, 0);
  if ( v0 )
    BCryptCloseAlgorithmProvider(qword_1401740B0, 0);
  if ( v3 )
    BCryptCloseAlgorithmProvider(qword_1401740C8, 0);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1400bfa88  push    rbx
0x1400bfa8a  push    rbp
0x1400bfa8b  push    rsi
0x1400bfa8c  push    rdi
0x1400bfa8d  push    r14
0x1400bfa8f  push    r15
0x1400bfa91  sub     rsp, 48h
0x1400bfa95  movdqa  xmm0, cs:__xmm@00000004000000030000000200000001
0x1400bfa9d  lea     rcx, qword_1401740B0; void *
0x1400bfaa4  xor     edx, edx; Val
0x1400bfaa6  mov     [rsp+78h+var_48], 6
0x1400bfaae  mov     r8d, 358h; Size
0x1400bfab4  mov     [rsp+78h+var_44], 7
0x1400bfabc  movdqu  [rsp+78h+var_58], xmm0
0x1400bfac2  xor     dil, dil
0x1400bfac5  xor     r15b, r15b
0x1400bfac8  xor     bpl, bpl
0x1400bfacb  xor     r14b, r14b
0x1400bface  call    memset_0
0x1400bfad3  lea     rcx, qword_1401740B0
0x1400bfada  call    SkpOpenAesGcmProvider
0x1400bfadf  mov     ebx, eax
0x1400bfae1  test    eax, eax
0x1400bfae3  js      loc_1400BFB6C
0x1400bfae9  lea     rcx, qword_1401740B8
0x1400bfaf0  mov     edi, 1
0x1400bfaf5  call    SkpOpenKdfProvider
0x1400bfafa  mov     ebx, eax
0x1400bfafc  test    eax, eax
0x1400bfafe  js      short loc_1400BFB6C
0x1400bfb00  mov     r9d, edi; dwFlags
0x1400bfb03  lea     rdx, aRsa; "RSA"
0x1400bfb0a  xor     r8d, r8d; pszImplementation
0x1400bfb0d  lea     rcx, hAlgorithm; phAlgorithm
0x1400bfb14  mov     r15b, dil
0x1400bfb17  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400bfb1e  nop     dword ptr [rax+rax+00h]
0x1400bfb23  mov     ebx, eax
0x1400bfb25  test    eax, eax
0x1400bfb27  js      short loc_1400BFB6C
0x1400bfb29  lea     rcx, qword_1401740C8
0x1400bfb30  mov     bpl, dil
0x1400bfb33  call    SkpOpenAesXtsProvider
0x1400bfb38  mov     ebx, eax
0x1400bfb3a  test    eax, eax
0x1400bfb3c  js      short loc_1400BFB6C
0x1400bfb3e  mov     edx, cs:ObjectLengthSP800108
0x1400bfb44  mov     ecx, 200h
0x1400bfb49  mov     r8d, 20534550h
0x1400bfb4f  mov     r14b, dil
0x1400bfb52  call    SkAllocatePool
0x1400bfb57  mov     cs:qword_1401740D0, rax
0x1400bfb5e  test    rax, rax
0x1400bfb61  jnz     loc_1400BFC0A
0x1400bfb67  mov     ebx, 0C000009Ah
0x1400bfb6c  call    SkpDeleteAllPerDomainPageEncryptionState
0x1400bfb71  mov     rdx, cs:qword_1401740D0
0x1400bfb78  test    rdx, rdx
0x1400bfb7b  jz      short loc_1400BFB92
0x1400bfb7d  mov     ecx, 200h
0x1400bfb82  call    SkFreePool
0x1400bfb87  mov     cs:qword_1401740D0, 0
0x1400bfb92  test    bpl, bpl
0x1400bfb95  jz      short loc_1400BFBAC
0x1400bfb97  mov     rcx, cs:hAlgorithm; hAlgorithm
0x1400bfb9e  xor     edx, edx; dwFlags
0x1400bfba0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400bfba7  nop     dword ptr [rax+rax+00h]
0x1400bfbac  test    r15b, r15b
0x1400bfbaf  jz      short loc_1400BFBC6
0x1400bfbb1  mov     rcx, cs:qword_1401740B8; hAlgorithm
0x1400bfbb8  xor     edx, edx; dwFlags
0x1400bfbba  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400bfbc1  nop     dword ptr [rax+rax+00h]
0x1400bfbc6  test    dil, dil
0x1400bfbc9  jz      short loc_1400BFBE0
0x1400bfbcb  mov     rcx, cs:qword_1401740B0; hAlgorithm
0x1400bfbd2  xor     edx, edx; dwFlags
0x1400bfbd4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400bfbdb  nop     dword ptr [rax+rax+00h]
0x1400bfbe0  test    r14b, r14b
0x1400bfbe3  jz      short loc_1400BFBFA
0x1400bfbe5  mov     rcx, cs:qword_1401740C8; hAlgorithm
0x1400bfbec  xor     edx, edx; dwFlags
0x1400bfbee  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400bfbf5  nop     dword ptr [rax+rax+00h]
0x1400bfbfa  mov     eax, ebx
0x1400bfbfc  add     rsp, 48h
0x1400bfc00  pop     r15
0x1400bfc02  pop     r14
0x1400bfc04  pop     rdi
0x1400bfc05  pop     rsi
0x1400bfc06  pop     rbp
0x1400bfc07  pop     rbx
0x1400bfc08  retn
0x1400bfc0a  xor     esi, esi
0x1400bfc0c  mov     ecx, esi
0x1400bfc0e  lea     rax, qword_1401740D8
0x1400bfc15  imul    rdx, rcx, 88h
0x1400bfc1c  mov     ecx, dword ptr [rsp+rsi*4+78h+var_58]
0x1400bfc20  add     rdx, rax
0x1400bfc23  call    SkpInitPerDomainPageEncryptionState
0x1400bfc28  mov     ebx, eax
0x1400bfc2a  test    eax, eax
0x1400bfc2c  js      loc_1400BFB6C
0x1400bfc32  add     esi, edi
0x1400bfc34  cmp     esi, 6
0x1400bfc37  jb      short loc_1400BFC0C
0x1400bfc39  jmp     short loc_1400BFBFA
```
