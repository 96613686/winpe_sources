# SHTranslateSIDToName

- ea: `0x1800092e8`
- end: `0x1800095dd`
- name: `SHTranslateSIDToName`
- size: `757`
- prototype: `__int64 __fastcall(void *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006730`
- `0x180006890`

## callees

- `0x1800092e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800093b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800093b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000959d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000959d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x180009368`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x180009368`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800095c6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800095c6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800095b2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800095bc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800095b2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800095bc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180009334`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180009334`

## pseudocode

```c
__int64 __fastcall SHTranslateSIDToName(void *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  unsigned int v6; // r8d
  unsigned __int64 v7; // rdi
  _WORD *v8; // r8
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // r9
  _WORD *v11; // r10
  PLSA_TRUST_INFORMATION Domains; // rcx
  PWSTR Buffer; // r11
  unsigned __int64 v14; // rax
  _WORD *v15; // rcx
  signed int v16; // edx
  unsigned __int64 v17; // rcx
  _WORD *v18; // rax
  __int64 v19; // rax
  const unsigned __int16 *v20; // r10
  _WORD *v21; // r9
  __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  _WORD *v24; // rcx
  unsigned __int64 v25; // rdx
  _WORD *v26; // rax
  __int64 v27; // rcx
  PWSTR v28; // r9
  _WORD *v29; // rax
  unsigned __int64 v30; // rdx
  unsigned __int64 i; // rdi
  _WORD *v32; // rcx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  PSID Sids; // [rsp+90h] [rbp+30h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+98h] [rbp+38h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+A0h] [rbp+40h] BYREF
  PVOID PolicyHandle; // [rsp+A8h] [rbp+48h] BYREF

  Sids = a1;
  *a2 = 0;
  v3 = -2147024809;
  if ( a1 )
  {
    PolicyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle) | 0x10000000;
    if ( v4 < 0 )
      return (unsigned int)v4;
    ReferencedDomains = 0;
    Names = 0;
    v5 = LsaLookupSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names) | 0x10000000;
    if ( v5 < 0 )
    {
      v3 = v5;
      goto LABEL_55;
    }
    if ( (unsigned int)(Names->Use - 7) <= 1 )
    {
      v3 = -2147467259;
      goto LABEL_55;
    }
    v6 = Names->Name.Length + 2;
    if ( Names->DomainIndex >= 0 )
      v6 = ReferencedDomains->Domains[Names->DomainIndex].Name.Length + Names->Name.Length + 4;
    v7 = v6;
    v8 = CoTaskMemAlloc(v6);
    if ( v8 )
    {
      v9 = v7 >> 1;
      if ( Names->DomainIndex < 0 )
      {
        *v8 = 0;
      }
      else
      {
        if ( v9 )
        {
          v10 = v9;
          v11 = v8;
          Domains = ReferencedDomains->Domains;
          Buffer = Domains[Names->DomainIndex].Name.Buffer;
          v14 = (unsigned __int64)Domains[Names->DomainIndex].Name.Length >> 1;
          do
          {
            if ( !v14 )
              break;
            if ( !*Buffer )
              break;
            *v11++ = *Buffer++;
            --v14;
            --v10;
          }
          while ( v10 );
          v15 = v11 - 1;
          v16 = v10 == 0 ? 0x8007007A : 0;
          if ( v10 )
            v15 = v11;
          *v15 = 0;
          if ( v10 )
          {
            v17 = v9;
            v18 = v8;
            do
            {
              if ( !*v18 )
                break;
              ++v18;
              --v17;
            }
            while ( v17 );
            v16 = v17 == 0 ? 0x80070057 : 0;
            v19 = v17 ? v9 - v17 : 0LL;
            if ( v17 )
            {
              v20 = L"\\";
              v21 = &v8[v19];
              v22 = 2147483646;
              v23 = v9 - v19;
              if ( v9 != v19 )
              {
                do
                {
                  if ( !v22 )
                    break;
                  if ( !*v20 )
                    break;
                  *v21++ = *v20++;
                  --v22;
                  --v23;
                }
                while ( v23 );
              }
              v24 = v21 - 1;
              if ( v23 )
                v24 = v21;
              v16 = v23 == 0 ? 0x8007007A : 0;
              *v24 = 0;
            }
          }
        }
        else
        {
          v16 = -2147024809;
        }
        if ( v16 < 0 )
        {
          v3 = v16;
LABEL_52:
          CoTaskMemFree(v8);
LABEL_55:
          LsaFreeMemory(ReferencedDomains);
          LsaFreeMemory(Names);
          LsaClose(PolicyHandle);
          return v3;
        }
      }
      if ( v9 )
      {
        v25 = v9;
        v26 = v8;
        do
        {
          if ( !*v26 )
            break;
          ++v26;
          --v25;
        }
        while ( v25 );
        v3 = v25 == 0 ? 0x80070057 : 0;
        v27 = v25 ? v9 - v25 : 0LL;
        if ( v25 )
        {
          v28 = Names->Name.Buffer;
          v29 = &v8[v27];
          v30 = (unsigned __int64)Names->Name.Length >> 1;
          for ( i = v9 - v27; i; --i )
          {
            if ( !v30 )
              break;
            if ( !*v28 )
              break;
            *v29++ = *v28++;
            --v30;
          }
          v32 = v29 - 1;
          if ( i )
            v32 = v29;
          *v32 = 0;
          v3 = i == 0 ? 0x8007007A : 0;
          if ( i )
          {
            *a2 = v8;
            v8 = 0;
          }
        }
      }
      goto LABEL_52;
    }
    v3 = -2147024882;
    goto LABEL_52;
  }
  return v3;
}

```

## disassembly

```asm
0x1800092e8  mov     [rsp-28h+Sids], rcx
0x1800092ed  push    rbp
0x1800092ee  push    rbx
0x1800092ef  push    rsi
0x1800092f0  push    rdi
0x1800092f1  push    r14
0x1800092f3  mov     rbp, rsp
0x1800092f6  sub     rsp, 60h
0x1800092fa  xor     r14d, r14d
0x1800092fd  mov     rsi, rdx
0x180009300  mov     [rdx], r14
0x180009303  mov     ebx, 80070057h
0x180009308  test    rcx, rcx
0x18000930b  jz      loc_1800095D0
0x180009311  xorps   xmm0, xmm0
0x180009314  mov     [rbp+PolicyHandle], r14
0x180009318  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18000931c  mov     r8d, 800h; DesiredAccess
0x180009322  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180009326  xor     ecx, ecx; SystemName
0x180009328  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000932c  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180009330  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180009334  call    cs:__imp_LsaOpenPolicy
0x18000933a  mov     edi, 10000000h
0x18000933f  or      eax, edi
0x180009341  jl      loc_1800095CE
0x180009347  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000934b  lea     rax, [rbp+arg_8]
0x18000934f  lea     r9, [rbp+ReferencedDomains]; ReferencedDomains
0x180009353  mov     [rsp+60h+Names], rax; Names
0x180009358  lea     r8, [rbp+Sids]; Sids
0x18000935c  mov     [rbp+ReferencedDomains], r14
0x180009360  lea     edx, [r14+1]; Count
0x180009364  mov     [rbp+arg_8], r14
0x180009368  call    cs:__imp_LsaLookupSids
0x18000936e  or      eax, edi
0x180009370  jl      loc_1800095AC
0x180009376  mov     rcx, [rbp+arg_8]
0x18000937a  mov     eax, [rcx]
0x18000937c  sub     eax, 7
0x18000937f  cmp     eax, 1
0x180009382  jbe     loc_1800095A5
0x180009388  movzx   r8d, word ptr [rcx+8]
0x18000938d  add     r8d, 2
0x180009391  cmp     [rcx+18h], r14d
0x180009395  jl      short loc_1800093B2
0x180009397  movsxd  rax, dword ptr [rcx+18h]
0x18000939b  add     r8d, 2
0x18000939f  lea     rdx, [rax+rax*2]
0x1800093a3  mov     rax, [rbp+ReferencedDomains]
0x1800093a7  mov     rcx, [rax+8]
0x1800093ab  movzx   eax, word ptr [rcx+rdx*8]
0x1800093af  add     r8d, eax
0x1800093b2  mov     ecx, r8d; cb
0x1800093b5  mov     edi, r8d
0x1800093b8  call    cs:__imp_CoTaskMemAlloc
0x1800093be  mov     r8, rax
0x1800093c1  test    rax, rax
0x1800093c4  jz      loc_180009595
0x1800093ca  mov     rax, [rbp+arg_8]
0x1800093ce  shr     rdi, 1
0x1800093d1  cmp     [rax+18h], r14d
0x1800093d5  jl      loc_1800094EB
0x1800093db  test    rdi, rdi
0x1800093de  jz      loc_1800094DE
0x1800093e4  movsxd  rax, dword ptr [rax+18h]
0x1800093e8  mov     r9, rdi
0x1800093eb  mov     r10, r8
0x1800093ee  lea     rdx, [rax+rax*2]
0x1800093f2  mov     rax, [rbp+ReferencedDomains]
0x1800093f6  mov     rcx, [rax+8]
0x1800093fa  movzx   eax, word ptr [rcx+rdx*8]
0x1800093fe  mov     r11, [rcx+rdx*8+8]
0x180009403  shr     rax, 1
0x180009406  test    rax, rax
0x180009409  jz      short loc_180009429
0x18000940b  movzx   ecx, word ptr [r11]
0x18000940f  test    cx, cx
0x180009412  jz      short loc_180009429
0x180009414  mov     [r10], cx
0x180009418  add     r11, 2
0x18000941c  add     r10, 2
0x180009420  dec     rax
0x180009423  sub     r9, 1
0x180009427  jnz     short loc_180009406
0x180009429  mov     rax, r9
0x18000942c  lea     rcx, [r10-2]
0x180009430  neg     rax
0x180009433  sbb     edx, edx
0x180009435  not     edx
0x180009437  and     edx, 8007007Ah
0x18000943d  test    r9, r9
0x180009440  cmovnz  rcx, r10
0x180009444  mov     [rcx], r14w
0x180009448  jz      loc_1800094E0
0x18000944e  mov     rcx, rdi
0x180009451  mov     rax, r8
0x180009454  cmp     [rax], r14w
0x180009458  jz      short loc_180009464
0x18000945a  add     rax, 2
0x18000945e  sub     rcx, 1
0x180009462  jnz     short loc_180009454
0x180009464  mov     rax, rcx
0x180009467  neg     rax
0x18000946a  sbb     edx, edx
0x18000946c  not     edx
0x18000946e  and     edx, ebx
0x180009470  test    rcx, rcx
0x180009473  jz      short loc_18000947D
0x180009475  mov     rax, rdi
0x180009478  sub     rax, rcx
0x18000947b  jmp     short loc_180009480
0x18000947d  mov     rax, r14
0x180009480  test    rcx, rcx
0x180009483  jz      short loc_1800094E0
0x180009485  mov     rdx, rdi
0x180009488  lea     r10, asc_18000BDF8; "\\"
0x18000948f  lea     r9, [r8+rax*2]
0x180009493  mov     ecx, 7FFFFFFEh
0x180009498  sub     rdx, rax
0x18000949b  jz      short loc_1800094C0
0x18000949d  test    rcx, rcx
0x1800094a0  jz      short loc_1800094C0
0x1800094a2  movzx   eax, word ptr [r10]
0x1800094a6  test    ax, ax
0x1800094a9  jz      short loc_1800094C0
0x1800094ab  mov     [r9], ax
0x1800094af  add     r10, 2
0x1800094b3  add     r9, 2
0x1800094b7  dec     rcx
0x1800094ba  sub     rdx, 1
0x1800094be  jnz     short loc_18000949D
0x1800094c0  test    rdx, rdx
0x1800094c3  lea     rcx, [r9-2]
0x1800094c7  cmovnz  rcx, r9
0x1800094cb  neg     rdx
0x1800094ce  sbb     edx, edx
0x1800094d0  not     edx
0x1800094d2  and     edx, 8007007Ah
0x1800094d8  mov     [rcx], r14w
0x1800094dc  jmp     short loc_1800094E0
0x1800094de  mov     edx, ebx
0x1800094e0  test    edx, edx
0x1800094e2  jns     short loc_1800094EF
0x1800094e4  mov     ebx, edx
0x1800094e6  jmp     loc_18000959A
0x1800094eb  mov     [r8], r14w
0x1800094ef  test    rdi, rdi
0x1800094f2  jz      loc_18000959A
0x1800094f8  mov     rdx, rdi
0x1800094fb  mov     rax, r8
0x1800094fe  cmp     [rax], r14w
0x180009502  jz      short loc_18000950E
0x180009504  add     rax, 2
0x180009508  sub     rdx, 1
0x18000950c  jnz     short loc_1800094FE
0x18000950e  mov     rax, rdx
0x180009511  neg     rax
0x180009514  sbb     ecx, ecx
0x180009516  not     ecx
0x180009518  and     ebx, ecx
0x18000951a  test    rdx, rdx
0x18000951d  jz      short loc_180009527
0x18000951f  mov     rcx, rdi
0x180009522  sub     rcx, rdx
0x180009525  jmp     short loc_18000952A
0x180009527  mov     rcx, r14
0x18000952a  test    rdx, rdx
0x18000952d  jz      short loc_18000959A
0x18000952f  mov     rax, [rbp+arg_8]
0x180009533  movzx   edx, word ptr [rax+8]
0x180009537  mov     r9, [rax+10h]
0x18000953b  lea     rax, [r8+rcx*2]
0x18000953f  shr     rdx, 1
0x180009542  sub     rdi, rcx
0x180009545  jz      short loc_180009569
0x180009547  test    rdx, rdx
0x18000954a  jz      short loc_180009569
0x18000954c  movzx   ecx, word ptr [r9]
0x180009550  test    cx, cx
0x180009553  jz      short loc_180009569
0x180009555  mov     [rax], cx
0x180009558  add     r9, 2
0x18000955c  add     rax, 2
0x180009560  dec     rdx
0x180009563  sub     rdi, 1
0x180009567  jnz     short loc_180009547
0x180009569  test    rdi, rdi
0x18000956c  lea     rcx, [rax-2]
0x180009570  cmovnz  rcx, rax
0x180009574  mov     rax, rdi
0x180009577  neg     rax
0x18000957a  sbb     ebx, ebx
0x18000957c  not     ebx
0x18000957e  mov     [rcx], r14w
0x180009582  and     ebx, 8007007Ah
0x180009588  test    rdi, rdi
0x18000958b  jz      short loc_18000959A
0x18000958d  mov     [rsi], r8
0x180009590  mov     r8, r14
0x180009593  jmp     short loc_18000959A
0x180009595  mov     ebx, 8007000Eh
0x18000959a  mov     rcx, r8; pv
0x18000959d  call    cs:__imp_CoTaskMemFree
0x1800095a3  jmp     short loc_1800095AE
0x1800095a5  mov     ebx, 80004005h
0x1800095aa  jmp     short loc_1800095AE
0x1800095ac  mov     ebx, eax
0x1800095ae  mov     rcx, [rbp+ReferencedDomains]; Buffer
0x1800095b2  call    cs:__imp_LsaFreeMemory
0x1800095b8  mov     rcx, [rbp+arg_8]; Buffer
0x1800095bc  call    cs:__imp_LsaFreeMemory
0x1800095c2  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800095c6  call    cs:__imp_LsaClose
0x1800095cc  jmp     short loc_1800095D0
0x1800095ce  mov     ebx, eax
0x1800095d0  mov     eax, ebx
0x1800095d2  add     rsp, 60h
0x1800095d6  pop     r14
0x1800095d8  pop     rdi
0x1800095d9  pop     rsi
0x1800095da  pop     rbx
0x1800095db  pop     rbp
0x1800095dc  retn
```
