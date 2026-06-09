# QueryDomainInfo(ushort * *,ushort * *,int *)

- ea: `0x180013400`
- end: `0x18001362f`
- name: `?QueryDomainInfo@@YAKPEAPEAG0PEAH@Z`
- size: `559`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180015310`

## callees

- `0x18000214c`
- `0x180013400`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800135e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013604`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800135e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013604`
- `ADVAPI32!LsaClose` at `0x1800135cb`
- `ADVAPI32!LsaClose` at `0x1800135cb`
- `ADVAPI32!LsaFreeMemory` at `0x1800135b6`
- `ADVAPI32!LsaFreeMemory` at `0x1800135b6`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001347d`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001347d`
- `ADVAPI32!LsaOpenPolicy` at `0x18001345c`
- `ADVAPI32!LsaOpenPolicy` at `0x18001345c`

## pseudocode

```c
__int64 __fastcall QueryDomainInfo(unsigned __int16 **a1, unsigned __int16 **a2, int *a3)
{
  unsigned int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rcx
  __int64 v11; // r8
  unsigned __int16 v12; // ax
  unsigned __int16 *v13; // rax
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rax
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rcx
  __int64 v18; // r8
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // rax
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+80h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp+38h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v6 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( !v6 )
  {
    v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( !v6 )
    {
      if ( a2 && *(_WORD *)Buffer )
      {
        v7 = ((unsigned __int64)*(unsigned __int16 *)Buffer >> 1) + 1;
        v8 = 2 * v7;
        if ( !is_mul_ok(v7, 2u) )
          v8 = -1;
        v9 = (unsigned __int16 *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
        *a2 = v9;
        v10 = v9;
        if ( !v9 )
          goto LABEL_12;
        v11 = *((_QWORD *)Buffer + 1) - (_QWORD)v9;
        while ( v7 != 1 )
        {
          v12 = *(unsigned __int16 *)((char *)v10 + v11);
          if ( !v12 )
            break;
          *v10 = v12;
          --v7;
          ++v10;
        }
        v13 = v10 - 1;
        if ( v7 )
          v13 = v10;
        *v13 = 0;
      }
      if ( a1 && *((_WORD *)Buffer + 8) )
      {
        v14 = ((unsigned __int64)*((unsigned __int16 *)Buffer + 8) >> 1) + 1;
        v15 = 2 * v14;
        if ( !is_mul_ok(v14, 2u) )
          v15 = -1;
        v16 = (unsigned __int16 *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
        *a1 = v16;
        v17 = v16;
        if ( !v16 )
        {
LABEL_12:
          v6 = 8;
          goto LABEL_35;
        }
        v18 = *((_QWORD *)Buffer + 3) - (_QWORD)v16;
        while ( v14 != 1 )
        {
          v19 = *(unsigned __int16 *)((char *)v17 + v18);
          if ( !v19 )
            break;
          *v17 = v19;
          --v14;
          ++v17;
        }
        v20 = v17 - 1;
        if ( v14 )
          v20 = v17;
        *v20 = 0;
      }
      if ( a3 )
        *a3 = *((_QWORD *)Buffer + 8) == 0;
      v6 = 0;
    }
  }
LABEL_35:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v6 )
  {
    if ( a1 && *a1 )
    {
      operator delete(*a1);
      *a1 = 0;
    }
    if ( a2 && *a2 )
    {
      operator delete(*a2);
      *a2 = 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180013400  mov     [rsp-28h+arg_10], rbx
0x180013405  mov     [rsp-28h+arg_18], rsi
0x18001340a  push    rbp
0x18001340b  push    rdi
0x18001340c  push    r13
0x18001340e  push    r14
0x180013410  push    r15
0x180013412  mov     rbp, rsp
0x180013415  sub     rsp, 50h
0x180013419  xor     r15d, r15d
0x18001341c  mov     r14, r8
0x18001341f  mov     [rbp+PolicyHandle], r15
0x180013423  mov     rdi, rdx
0x180013426  mov     [rbp+Buffer], r15
0x18001342a  mov     rsi, rcx
0x18001342d  test    rcx, rcx
0x180013430  jz      short loc_180013435
0x180013432  mov     [rcx], r15
0x180013435  test    rdi, rdi
0x180013438  jz      short loc_18001343D
0x18001343a  mov     [rdx], r15
0x18001343d  xorps   xmm0, xmm0
0x180013440  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180013444  mov     r8d, 1; DesiredAccess
0x18001344a  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18001344e  xor     ecx, ecx; SystemName
0x180013450  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180013454  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180013458  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001345c  call    cs:__imp_LsaOpenPolicy
0x180013463  nop     dword ptr [rax+rax+00h]
0x180013468  mov     ebx, eax
0x18001346a  test    eax, eax
0x18001346c  jnz     loc_1800135AD
0x180013472  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180013476  lea     r8, [rbp+Buffer]; Buffer
0x18001347a  lea     edx, [rax+0Ch]; InformationClass
0x18001347d  call    cs:__imp_LsaQueryInformationPolicy
0x180013484  nop     dword ptr [rax+rax+00h]
0x180013489  mov     ebx, eax
0x18001348b  test    eax, eax
0x18001348d  jnz     loc_1800135AD
0x180013493  or      r13, 0FFFFFFFFFFFFFFFFh
0x180013497  test    rdi, rdi
0x18001349a  jz      short loc_180013517
0x18001349c  mov     rax, [rbp+Buffer]
0x1800134a0  cmp     [rax], r15w
0x1800134a4  jbe     short loc_180013517
0x1800134a6  movzx   ebx, word ptr [rax]
0x1800134a9  lea     eax, [r13+3]
0x1800134ad  shr     rbx, 1
0x1800134b0  inc     rbx
0x1800134b3  mul     rbx
0x1800134b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800134bd  cmovo   rax, r13
0x1800134c1  mov     rcx, rax; unsigned __int64
0x1800134c4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800134c9  mov     [rdi], rax
0x1800134cc  mov     rcx, rax
0x1800134cf  test    rax, rax
0x1800134d2  jnz     short loc_1800134DE
0x1800134d4  mov     ebx, 8
0x1800134d9  jmp     loc_1800135AD
0x1800134de  mov     rax, [rbp+Buffer]
0x1800134e2  mov     r8, [rax+8]
0x1800134e6  sub     r8, rcx
0x1800134e9  lea     rdx, [rbx-1]
0x1800134ed  test    rdx, rdx
0x1800134f0  jz      short loc_180013508
0x1800134f2  movzx   eax, word ptr [r8+rcx]
0x1800134f7  test    ax, ax
0x1800134fa  jz      short loc_180013508
0x1800134fc  mov     [rcx], ax
0x1800134ff  mov     rbx, rdx
0x180013502  add     rcx, 2
0x180013506  jmp     short loc_1800134E9
0x180013508  test    rbx, rbx
0x18001350b  lea     rax, [rcx-2]
0x18001350f  cmovnz  rax, rcx
0x180013513  mov     [rax], r15w
0x180013517  test    rsi, rsi
0x18001351a  jz      short loc_180013594
0x18001351c  mov     rax, [rbp+Buffer]
0x180013520  cmp     [rax+10h], r15w
0x180013525  jbe     short loc_180013594
0x180013527  movzx   ebx, word ptr [rax+10h]
0x18001352b  mov     eax, 2
0x180013530  shr     rbx, 1
0x180013533  inc     rbx
0x180013536  mul     rbx
0x180013539  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013540  cmovo   rax, r13
0x180013544  mov     rcx, rax; unsigned __int64
0x180013547  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001354c  mov     [rsi], rax
0x18001354f  mov     rcx, rax
0x180013552  test    rax, rax
0x180013555  jz      loc_1800134D4
0x18001355b  mov     rax, [rbp+Buffer]
0x18001355f  mov     r8, [rax+18h]
0x180013563  sub     r8, rcx
0x180013566  lea     rdx, [rbx-1]
0x18001356a  test    rdx, rdx
0x18001356d  jz      short loc_180013585
0x18001356f  movzx   eax, word ptr [r8+rcx]
0x180013574  test    ax, ax
0x180013577  jz      short loc_180013585
0x180013579  mov     [rcx], ax
0x18001357c  mov     rbx, rdx
0x18001357f  add     rcx, 2
0x180013583  jmp     short loc_180013566
0x180013585  test    rbx, rbx
0x180013588  lea     rax, [rcx-2]
0x18001358c  cmovnz  rax, rcx
0x180013590  mov     [rax], r15w
0x180013594  test    r14, r14
0x180013597  jz      short loc_1800135AA
0x180013599  mov     rax, [rbp+Buffer]
0x18001359d  mov     ecx, r15d
0x1800135a0  cmp     [rax+40h], r15
0x1800135a4  setz    cl
0x1800135a7  mov     [r14], ecx
0x1800135aa  mov     ebx, r15d
0x1800135ad  mov     rcx, [rbp+Buffer]; Buffer
0x1800135b1  test    rcx, rcx
0x1800135b4  jz      short loc_1800135C2
0x1800135b6  call    cs:__imp_LsaFreeMemory
0x1800135bd  nop     dword ptr [rax+rax+00h]
0x1800135c2  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800135c6  test    rcx, rcx
0x1800135c9  jz      short loc_1800135D7
0x1800135cb  call    cs:__imp_LsaClose
0x1800135d2  nop     dword ptr [rax+rax+00h]
0x1800135d7  test    ebx, ebx
0x1800135d9  jz      short loc_180013613
0x1800135db  test    rsi, rsi
0x1800135de  jz      short loc_1800135F7
0x1800135e0  mov     rcx, [rsi]
0x1800135e3  test    rcx, rcx
0x1800135e6  jz      short loc_1800135F7
0x1800135e8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800135ef  nop     dword ptr [rax+rax+00h]
0x1800135f4  mov     [rsi], r15
0x1800135f7  test    rdi, rdi
0x1800135fa  jz      short loc_180013613
0x1800135fc  mov     rcx, [rdi]
0x1800135ff  test    rcx, rcx
0x180013602  jz      short loc_180013613
0x180013604  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001360b  nop     dword ptr [rax+rax+00h]
0x180013610  mov     [rdi], r15
0x180013613  lea     r11, [rsp+50h+var_s0]
0x180013618  mov     eax, ebx
0x18001361a  mov     rbx, [r11+40h]
0x18001361e  mov     rsi, [r11+48h]
0x180013622  mov     rsp, r11
0x180013625  pop     r15
0x180013627  pop     r14
0x180013629  pop     r13
0x18001362b  pop     rdi
0x18001362c  pop     rbp
0x18001362d  retn
```
