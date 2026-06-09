# GeneratePMKID(uchar (*)[6],uchar (*)[6],uchar *,ulong,uchar (*)[16])

- ea: `0x18000bdfc`
- end: `0x18000c093`
- name: `?GeneratePMKID@@YAKPEAY05E0PEAEKPEAY0BA@E@Z`
- size: `663`
- prototype: `unsigned int(unsigned __int8 (*)[6], unsigned __int8 (*)[6], unsigned __int8 *, unsigned int, unsigned __int8 (*)[16])`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18003b368`
- `0x18003df58`
- `0x18006a91c`

## callees

- `0x1800063b0`
- `0x18000892c`
- `0x180008998`
- `0x18000bde0`
- `0x18000bdfc`
- `0x18000c730`
- `0x1800249c4`
- `0x180033650`
- `0x180043a30`
- `0x180096010`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18000bfb7`
- `bcrypt!BCryptFinishHash` at `0x18000bf9c`
- `bcrypt!BCryptFinishHash` at `0x18000bf9c`
- `bcrypt!BCryptHashData` at `0x18000bf78`
- `bcrypt!BCryptHashData` at `0x18000bf78`
- `bcrypt!BCryptCreateHash` at `0x18000bf4b`
- `bcrypt!BCryptCreateHash` at `0x18000bf4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GeneratePMKID(
        unsigned __int8 (*a1)[6],
        unsigned __int8 (*a2)[6],
        unsigned __int8 *a3,
        ULONG a4,
        unsigned __int8 (*a5)[16])
{
  unsigned int MSMSecMemory; // eax
  unsigned int v10; // ebx
  _DWORD *v11; // rdi
  PVOID *v12; // rcx
  NTSTATUS v14; // esi
  __int64 v15; // rdx
  __int64 v16; // r9
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-31h] BYREF
  BCRYPT_HASH_HANDLE *p_hHash; // [rsp+48h] [rbp-29h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-21h] BYREF
  char v20; // [rsp+58h] [rbp-19h]
  UCHAR pbOutput[16]; // [rsp+60h] [rbp-11h] BYREF
  int v22; // [rsp+70h] [rbp-1h]

  hHash = 0;
  *(_OWORD *)pbOutput = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
  MSMSecMemory = AllocateMSMSecMemory(0x14u);
  v10 = MSMSecMemory;
  v11 = hHash;
  if ( MSMSecMemory )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v15 = 22;
      v16 = MSMSecMemory;
LABEL_19:
      WPP_SF_d(v12[7], v15, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v16);
LABEL_16:
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    *(_QWORD *)hHash = g_ucPMKIDStr;
    v11[2] = *(_DWORD *)a1;
    *((_WORD *)v11 + 6) = *(_WORD *)&(*a1)[4];
    *(_DWORD *)((char *)v11 + 14) = *(_DWORD *)a2;
    *((_WORD *)v11 + 9) = *(_WORD *)&(*a2)[4];
    v10 = 0;
    hHash = 0;
    p_hHash = &hHash;
    phHash = 0;
    v20 = 1;
    v14 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0xA1, &phHash, 0, 0, a3, a4, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hHash);
    if ( v14 >= 0 )
    {
      v14 = BCryptHashData(hHash, (PUCHAR)v11, 0x14u, 0);
      if ( v14 >= 0 )
      {
        v14 = BCryptFinishHash(hHash, pbOutput, 0x14u, 0);
        if ( v14 >= 0 )
        {
          if ( hHash )
            ((void (*)(void))BCryptDestroyHash)();
          *(_OWORD *)a5 = *(_OWORD *)pbOutput;
          goto LABEL_16;
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    v10 = 1359;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v15 = 23;
      v16 = (unsigned int)v14;
      goto LABEL_19;
    }
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    WPP_SF_d(v12[7], 24, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000bdfc  push    rbp
0x18000bdfe  push    rbx
0x18000bdff  push    rsi
0x18000be00  push    rdi
0x18000be01  push    r12
0x18000be03  push    r13
0x18000be05  push    r14
0x18000be07  push    r15
0x18000be09  lea     rbp, [rsp-17h]
0x18000be0e  sub     rsp, 88h
0x18000be15  mov     rax, cs:__security_cookie
0x18000be1c  xor     rax, rsp
0x18000be1f  mov     [rbp+4Fh+var_48], rax
0x18000be23  mov     r12d, r9d
0x18000be26  mov     r13, r8
0x18000be29  mov     rsi, rdx
0x18000be2c  mov     r15, rcx
0x18000be2f  mov     r14, [rbp+4Fh+arg_20]
0x18000be33  mov     [rbp+4Fh+hHash], 0
0x18000be3b  xorps   xmm0, xmm0
0x18000be3e  xor     eax, eax
0x18000be40  movups  xmmword ptr [rbp+4Fh+pbOutput], xmm0
0x18000be44  mov     [rbp+4Fh+var_50], eax
0x18000be47  lea     rax, WPP_GLOBAL_Control
0x18000be4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be55  cmp     rcx, rax
0x18000be58  jz      short loc_18000BE67
0x18000be5a  test    dword ptr [rcx+44h], 100h
0x18000be61  jnz     loc_18000BFE0
0x18000be67  lea     rdx, [rbp+4Fh+hHash]
0x18000be6b  mov     ecx, 14h; dwBytes
0x18000be70  call    AllocateMSMSecMemory
0x18000be75  mov     ebx, eax
0x18000be77  mov     rdi, [rbp+4Fh+hHash]
0x18000be7b  test    eax, eax
0x18000be7d  jz      short loc_18000BEEE
0x18000be7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be86  lea     r14, WPP_GLOBAL_Control
0x18000be8d  cmp     rcx, r14
0x18000be90  jnz     loc_18000BFFA
0x18000be96  test    rdi, rdi
0x18000be99  jz      short loc_18000BEB9
0x18000be9b  cmp     rcx, r14
0x18000be9e  jz      short loc_18000BEAA
0x18000bea0  test    byte ptr [rcx+1Ch], 10h
0x18000bea4  jnz     loc_18000C059
0x18000beaa  mov     rcx, rdi
0x18000bead  call    FreeWLMemory
0x18000beb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000beb9  cmp     rcx, r14
0x18000bebc  jz      short loc_18000BECB
0x18000bebe  test    dword ptr [rcx+44h], 100h
0x18000bec5  jnz     loc_18000C076
0x18000becb  mov     eax, ebx
0x18000becd  mov     rcx, [rbp+4Fh+var_48]
0x18000bed1  xor     rcx, rsp; StackCookie
0x18000bed4  call    __security_check_cookie
0x18000bed9  add     rsp, 88h
0x18000bee0  pop     r15
0x18000bee2  pop     r14
0x18000bee4  pop     r13
0x18000bee6  pop     r12
0x18000bee8  pop     rdi
0x18000bee9  pop     rsi
0x18000beea  pop     rbx
0x18000beeb  pop     rbp
0x18000beec  retn
0x18000beee  mov     rax, cs:?g_ucPMKIDStr@@3PAEA; uchar near * g_ucPMKIDStr
0x18000bef5  mov     [rdi], rax
0x18000bef8  mov     eax, [r15]
0x18000befb  mov     [rdi+8], eax
0x18000befe  movzx   eax, word ptr [r15+4]
0x18000bf03  mov     [rdi+0Ch], ax
0x18000bf07  mov     eax, [rsi]
0x18000bf09  mov     [rdi+0Eh], eax
0x18000bf0c  movzx   eax, word ptr [rsi+4]
0x18000bf10  mov     [rdi+12h], ax
0x18000bf14  lea     r15, [rbp+4Fh+pbOutput]
0x18000bf18  xor     ebx, ebx
0x18000bf1a  mov     [rbp+4Fh+hHash], rbx
0x18000bf1e  lea     rax, [rbp+4Fh+hHash]
0x18000bf22  mov     [rbp+4Fh+var_78], rax
0x18000bf26  mov     [rbp+4Fh+phHash], rbx
0x18000bf2a  mov     [rbp+4Fh+var_68], 1
0x18000bf2e  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x18000bf32  mov     [rsp+0C0h+cbSecret], r12d; cbSecret
0x18000bf37  mov     [rsp+0C0h+pbSecret], r13; pbSecret
0x18000bf3c  xor     r9d, r9d; cbHashObject
0x18000bf3f  xor     r8d, r8d; pbHashObject
0x18000bf42  lea     rdx, [rbp+4Fh+phHash]; phHash
0x18000bf46  mov     ecx, 0A1h; hAlgorithm
0x18000bf4b  call    cs:__imp_BCryptCreateHash
0x18000bf52  nop     dword ptr [rax+rax+00h]
0x18000bf57  mov     esi, eax
0x18000bf59  lea     rcx, [rbp+4Fh+var_78]
0x18000bf5d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18000bf62  test    esi, esi
0x18000bf64  js      loc_18000C028
0x18000bf6a  xor     r9d, r9d; dwFlags
0x18000bf6d  lea     r8d, [rbx+14h]; cbInput
0x18000bf71  mov     rdx, rdi; pbInput
0x18000bf74  mov     rcx, [rbp+4Fh+hHash]; hHash
0x18000bf78  call    cs:__imp_BCryptHashData
0x18000bf7f  nop     dword ptr [rax+rax+00h]
0x18000bf84  mov     esi, eax
0x18000bf86  test    eax, eax
0x18000bf88  js      loc_18000C028
0x18000bf8e  xor     r9d, r9d; dwFlags
0x18000bf91  lea     r8d, [rbx+14h]; cbOutput
0x18000bf95  mov     rdx, r15; pbOutput
0x18000bf98  mov     rcx, [rbp+4Fh+hHash]; hHash
0x18000bf9c  call    cs:__imp_BCryptFinishHash
0x18000bfa3  nop     dword ptr [rax+rax+00h]
0x18000bfa8  mov     esi, eax
0x18000bfaa  test    eax, eax
0x18000bfac  js      short loc_18000C028
0x18000bfae  mov     rcx, [rbp+4Fh+hHash]
0x18000bfb2  test    rcx, rcx
0x18000bfb5  jz      short loc_18000BFC4
0x18000bfb7  mov     rax, cs:__imp_BCryptDestroyHash
0x18000bfbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc3  nop
0x18000bfc4  movups  xmm0, xmmword ptr [rbp+4Fh+pbOutput]
0x18000bfc8  movdqu  xmmword ptr [r14], xmm0
0x18000bfcd  lea     r14, WPP_GLOBAL_Control
0x18000bfd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfdb  jmp     loc_18000BE96
0x18000bfe0  mov     edx, 15h
0x18000bfe5  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18000bfec  mov     rcx, [rcx+38h]
0x18000bff0  call    WPP_SF_
0x18000bff5  jmp     loc_18000BE67
0x18000bffa  test    byte ptr [rcx+44h], 1
0x18000bffe  jz      loc_18000BE96
0x18000c004  mov     edx, 16h
0x18000c009  mov     r9d, eax
0x18000c00c  jmp     short loc_18000C016
0x18000c00e  mov     edx, 17h
0x18000c013  mov     r9d, esi
0x18000c016  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18000c01d  mov     rcx, [rcx+38h]
0x18000c021  call    WPP_SF_d
0x18000c026  jmp     short loc_18000BFD4
0x18000c028  lea     rcx, [rbp+4Fh+hHash]
0x18000c02c  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000c031  mov     ebx, 54Fh
0x18000c036  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c03d  lea     r14, WPP_GLOBAL_Control
0x18000c044  cmp     rcx, r14
0x18000c047  jz      loc_18000BE96
0x18000c04d  test    byte ptr [rcx+44h], 1
0x18000c051  jz      loc_18000BE96
0x18000c057  jmp     short loc_18000C00E
0x18000c059  mov     edx, 0Ch
0x18000c05e  mov     r9, rdi
0x18000c061  lea     r8, WPP_13d7b2876eef3b3479d595a943243812_Traceguids
0x18000c068  mov     rcx, [rcx+10h]
0x18000c06c  call    WPP_SF_q
0x18000c071  jmp     loc_18000BEAA
0x18000c076  mov     edx, 18h
0x18000c07b  mov     r9d, ebx
0x18000c07e  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18000c085  mov     rcx, [rcx+38h]
0x18000c089  call    WPP_SF_d
0x18000c08e  jmp     loc_18000BECB
```
