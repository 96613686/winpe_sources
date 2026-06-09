# SampCreateSupplementalCredentials(void *,_ATTRBLOCKSIMPLE *,_ATTRBLOCKSIMPLE *)

- ea: `0x18009d630`
- end: `0x18009da47`
- name: `?SampCreateSupplementalCredentials@@YAJPEAXPEAU_ATTRBLOCKSIMPLE@@1@Z`
- size: `1047`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _ATTRBLOCKSIMPLE *, struct _ATTRBLOCKSIMPLE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a38e0`

## callees

- `0x180012a28`
- `0x180021460`
- `0x180021e80`
- `0x1800243e0`
- `0x180027e24`
- `0x18004f408`
- `0x18004f894`
- `0x18009d630`
- `0x18009da50`
- `0x1800a51f0`
- `0x1800af3e0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18009d86f`
- `ntdll!RtlEqualSid` at `0x18009d86f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d980`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d9a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d9c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d9de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d980`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d9a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d9c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d9de`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction041` at `0x18009d810`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction041` at `0x18009d810`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtPrepareSupplementalCredentials` at `0x18009d950`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtPrepareSupplementalCredentials` at `0x18009d950`

## pseudocode

```c
__int64 __fastcall SampCreateSupplementalCredentials(
        unsigned __int16 *a1,
        struct _ATTRBLOCKSIMPLE *a2,
        struct _ATTRBLOCKSIMPLE *a3)
{
  struct _SAMP_SUPPLEMENTAL_CRED *v4; // r15
  __int64 Length; // r9
  PWSTR Buffer; // rdi
  struct _UNICODE_STRING *v7; // r12
  PSID v8; // r14
  unsigned int v9; // esi
  __int64 v10; // rdx
  USHORT *v11; // rax
  __int16 *v12; // rax
  __int16 v13; // cx
  NTSTATUS v14; // ebx
  void *v15; // rax
  ULONG v16; // edx
  unsigned int PrimaryDomainStart; // edi
  char v18; // si
  int v19; // eax
  int v20; // eax
  unsigned int v21; // edx
  unsigned int v22; // edi
  HLOCAL *v23; // rcx
  __int64 MaximumLength; // rcx
  _BYTE *v25; // rax
  unsigned int v27; // [rsp+40h] [rbp-79h] BYREF
  struct _UNICODE_STRING v28; // [rsp+48h] [rbp-71h] BYREF
  struct _SAMP_SUPPLEMENTAL_CRED *v29; // [rsp+58h] [rbp-61h] BYREF
  struct _UNICODE_STRING v30; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING v31; // [rsp+70h] [rbp-49h] BYREF
  void *Src; // [rsp+80h] [rbp-39h]
  PSID Sid2; // [rsp+88h] [rbp-31h]
  __int64 v34; // [rsp+90h] [rbp-29h] BYREF
  __int64 v35; // [rsp+98h] [rbp-21h]
  __int64 v36[2]; // [rsp+A0h] [rbp-19h] BYREF
  HLOCAL v37; // [rsp+B0h] [rbp-9h]
  __int128 v38; // [rsp+B8h] [rbp-1h] BYREF
  struct _ATTRBLOCKSIMPLE *v39; // [rsp+128h] [rbp+6Fh]
  __int16 v41; // [rsp+138h] [rbp+7Fh]

  v39 = a2;
  v29 = 0;
  v37 = 0;
  *(_QWORD *)&v30.Length = 0;
  v4 = 0;
  v30.Buffer = 0;
  Length = 0;
  *(_QWORD *)&v28.Length = 0;
  v28.Buffer = 0;
  Buffer = 0;
  *(_QWORD *)&v31.Length = 0;
  v7 = 0;
  v31.Buffer = 0;
  v8 = 0;
  v41 = 0;
  v9 = 0;
  v34 = 0;
  v35 = 0;
  v27 = 0;
  v38 = 0;
  Src = 0;
  *(_OWORD *)v36 = 0;
  Sid2 = 0;
  while ( v9 < *(_DWORD *)a2 )
  {
    v10 = *((_QWORD *)a2 + 1);
    switch ( *(_DWORD *)(v10 + 24LL * v9) )
    {
      case 0x90008:
        if ( *(_DWORD *)(v10 + 24LL * v9 + 8) )
        {
          v14 = SampFlagsToAccountControl(
                  **(unsigned int **)(*(_QWORD *)(v10 + 24LL * v9 + 16) + 8LL),
                  &v27,
                  (unsigned int)(*(_DWORD *)(v10 + 24LL * v9) - 589832),
                  Length);
          if ( v14 < 0 )
            goto LABEL_50;
          Length = v30.Length;
        }
        break;
      case 0x9007D:
        if ( *(_DWORD *)(v10 + 24LL * v9 + 8) )
        {
          v12 = *(__int16 **)(v10 + 24LL * v9 + 16);
          v13 = *v12;
          v35 = *((_QWORD *)v12 + 1);
          v41 = v13;
          LOWORD(v34) = v13;
          WORD1(v34) = v13;
        }
        break;
      case 0x90092:
        if ( *(_DWORD *)(v10 + 24LL * v9 + 8) )
          Src = *(void **)(*(_QWORD *)(v10 + 24LL * v9 + 16) + 8LL);
        break;
      case 0x900DD:
        if ( *(_DWORD *)(v10 + 24LL * v9 + 8) )
        {
          Length = **(unsigned __int16 **)(v10 + 24LL * v9 + 16);
          v30.Length = Length;
          v30.MaximumLength = Length;
          v30.Buffer = *(PWSTR *)(*(_QWORD *)(v10 + 24LL * v9 + 16) + 8LL);
        }
        break;
      case 0x90290:
        if ( *(_DWORD *)(v10 + 24LL * v9 + 8) )
        {
          v11 = *(USHORT **)(v10 + 24LL * v9 + 16);
          if ( *(_DWORD *)v11 > 0xFFFFu )
            goto LABEL_21;
          v28.Length = *v11;
          v28.MaximumLength = v28.Length;
          v28.Buffer = *(PWSTR *)(*(_QWORD *)(v10 + 24LL * v9 + 16) + 8LL);
        }
        break;
      default:
        goto LABEL_21;
    }
    a2 = v39;
    ++v9;
  }
  if ( (_WORD)Length && (v15 = Src) != 0 )
  {
    if ( *(_BYTE *)a1 )
    {
      v16 = a1[4];
      v7 = (struct _UNICODE_STRING *)&v38;
      LOWORD(v38) = a1[2];
      WORD1(v38) = v16;
      *((_QWORD *)&v38 + 1) = a1 + 6;
      v14 = SystemFunction041(a1 + 6, v16, 0);
      if ( v14 < 0 )
        goto LABEL_50;
      v15 = Src;
    }
    v14 = SampSplitSid(v15);
    if ( v14 < 0 )
    {
      v8 = Sid2;
      goto LABEL_50;
    }
    PrimaryDomainStart = SampDsGetPrimaryDomainStart();
    v8 = Sid2;
    if ( PrimaryDomainStart >= SampDefinedDomainsCount )
      goto LABEL_21;
    do
    {
      if ( RtlEqualSid(*((PSID *)SampDefinedDomains + 170 * PrimaryDomainStart + 1), v8) )
        break;
      ++PrimaryDomainStart;
    }
    while ( PrimaryDomainStart < SampDefinedDomainsCount );
    if ( PrimaryDomainStart >= SampDefinedDomainsCount )
    {
LABEL_21:
      v14 = -1073741811;
      goto LABEL_50;
    }
    v18 = 0;
    if ( !v28.Length )
    {
      v14 = SampCreateDefaultUPN(&v30, PrimaryDomainStart, &v28);
      if ( v14 < 0 )
        goto LABEL_50;
      v18 = 1;
    }
    if ( !v41 || (v14 = SampDecryptSupplementalCredentials(&v34, 0, &v31), v14 >= 0) )
    {
      v19 = SampCreateSupplementalCredentialsHelper(
              PrimaryDomainStart,
              &v30,
              v27,
              &v28,
              &v31,
              v7,
              *((_BYTE *)a1 + 1),
              &v29);
      v4 = v29;
      v14 = v19;
      if ( v19 >= 0 )
      {
        v14 = SampConvertCredentialsFromListToAttr(&v31, (__int64)v36);
        if ( v14 >= 0 )
        {
          v20 = SampShouldCallNtdsaApiSet();
          v14 = v20;
          if ( v20 == -1073741637 )
          {
            v14 = 0;
          }
          else if ( v20 >= 0 )
          {
            v14 = NtdsaExtPrepareSupplementalCredentials(v36, a3);
          }
        }
      }
    }
    if ( v18 )
      LocalFree(v28.Buffer);
    Buffer = v31.Buffer;
  }
  else
  {
    v14 = -1073741811;
  }
  if ( Buffer )
    LocalFree(Buffer);
LABEL_50:
  v21 = v36[1];
  v22 = 0;
  v23 = (HLOCAL *)v37;
  if ( LODWORD(v36[1]) )
  {
    do
    {
      if ( v23[2 * v22 + 1] )
      {
        LocalFree(v23[2 * v22 + 1]);
        v23 = (HLOCAL *)v37;
        v21 = v36[1];
      }
      ++v22;
    }
    while ( v22 < v21 );
    v4 = v29;
  }
  if ( v23 )
    LocalFree(v23);
  if ( v4 )
    SampFreeSupplementalCredentialList(v4);
  if ( v8 )
    LocalFree(v8);
  if ( v7 )
  {
    MaximumLength = v7->MaximumLength;
    v25 = v7->Buffer;
    if ( v7->MaximumLength )
    {
      do
      {
        *v25++ = 0;
        --MaximumLength;
      }
      while ( MaximumLength );
    }
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      331,
      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
      (unsigned int)v14,
      v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18009d630  mov     [rsp-8+arg_10], r8
0x18009d635  mov     [rsp-8+arg_8], rdx
0x18009d63a  push    rbp
0x18009d63b  push    rbx
0x18009d63c  push    rsi
0x18009d63d  push    rdi
0x18009d63e  push    r12
0x18009d640  push    r13
0x18009d642  push    r14
0x18009d644  push    r15
0x18009d646  lea     rbp, [rsp-1Fh]
0x18009d64b  sub     rsp, 0D8h
0x18009d652  xor     ebx, ebx
0x18009d654  xorps   xmm0, xmm0
0x18009d657  xor     eax, eax
0x18009d659  mov     [rbp+57h+var_B8], rbx
0x18009d65d  xorps   xmm1, xmm1
0x18009d660  mov     [rbp+57h+var_60], rax
0x18009d664  mov     r13, rcx
0x18009d667  mov     qword ptr [rbp+57h+var_B0.Length], rbx
0x18009d66b  mov     r15d, ebx
0x18009d66e  mov     [rbp+57h+var_B0.Buffer], rbx
0x18009d672  mov     r9d, ebx
0x18009d675  mov     qword ptr [rbp+57h+var_C8.Length], rbx
0x18009d679  mov     [rbp+57h+var_C8.Buffer], rbx
0x18009d67d  mov     edi, ebx
0x18009d67f  mov     qword ptr [rbp+57h+var_A0.Length], rbx
0x18009d683  mov     r12d, ebx
0x18009d686  mov     [rbp+57h+var_A0.Buffer], rbx
0x18009d68a  mov     r14d, ebx
0x18009d68d  mov     [rbp+57h+arg_18], ebx
0x18009d690  mov     esi, ebx
0x18009d692  mov     [rbp+57h+var_80], rbx
0x18009d696  mov     [rbp+57h+var_78], rbx
0x18009d69a  mov     [rbp+57h+var_D0], ebx
0x18009d69d  mov     [rbp+57h+arg_0], ebx
0x18009d6a0  movups  [rbp+57h+var_58], xmm0
0x18009d6a4  mov     [rbp+57h+Src], rbx
0x18009d6a8  movups  xmmword ptr [rbp+57h+var_70], xmm1
0x18009d6ac  mov     [rbp+57h+Sid2], rbx
0x18009d6b0  cmp     esi, [rdx]
0x18009d6b2  jnb     loc_18009D7D2
0x18009d6b8  mov     rdx, [rdx+8]
0x18009d6bc  mov     eax, esi
0x18009d6be  lea     rcx, [rax+rax*2]
0x18009d6c2  mov     r8d, [rdx+rcx*8]
0x18009d6c6  sub     r8d, 90008h
0x18009d6cd  jz      loc_18009D792
0x18009d6d3  sub     r8d, 75h ; 'u'
0x18009d6d7  jz      loc_18009D76F
0x18009d6dd  sub     r8d, 15h
0x18009d6e1  jz      short loc_18009D75A
0x18009d6e3  sub     r8d, 4Bh ; 'K'
0x18009d6e7  jz      short loc_18009D72E
0x18009d6e9  cmp     r8d, 1B3h
0x18009d6f0  jnz     loc_18009D7C8
0x18009d6f6  cmp     [rdx+rcx*8+8], ebx
0x18009d6fa  jbe     loc_18009D7BD
0x18009d700  mov     rax, [rdx+rcx*8+10h]
0x18009d705  cmp     dword ptr [rax], 0FFFFh
0x18009d70b  ja      loc_18009D7C8
0x18009d711  movzx   eax, word ptr [rax]
0x18009d714  mov     [rbp+57h+var_C8.Length], ax
0x18009d718  mov     [rbp+57h+var_C8.MaximumLength], ax
0x18009d71c  mov     rax, [rdx+rcx*8+10h]
0x18009d721  mov     rcx, [rax+8]
0x18009d725  mov     [rbp+57h+var_C8.Buffer], rcx
0x18009d729  jmp     loc_18009D7BD
0x18009d72e  cmp     [rdx+rcx*8+8], ebx
0x18009d732  jbe     loc_18009D7BD
0x18009d738  mov     rax, [rdx+rcx*8+10h]
0x18009d73d  movzx   r9d, word ptr [rax]
0x18009d741  mov     [rbp+57h+var_B0.Length], r9w
0x18009d746  mov     [rbp+57h+var_B0.MaximumLength], r9w
0x18009d74b  mov     rax, [rdx+rcx*8+10h]
0x18009d750  mov     rcx, [rax+8]
0x18009d754  mov     [rbp+57h+var_B0.Buffer], rcx
0x18009d758  jmp     short loc_18009D7BD
0x18009d75a  cmp     [rdx+rcx*8+8], ebx
0x18009d75e  jbe     short loc_18009D7BD
0x18009d760  mov     rax, [rdx+rcx*8+10h]
0x18009d765  mov     rcx, [rax+8]
0x18009d769  mov     [rbp+57h+Src], rcx
0x18009d76d  jmp     short loc_18009D7BD
0x18009d76f  cmp     [rdx+rcx*8+8], ebx
0x18009d773  jbe     short loc_18009D7BD
0x18009d775  mov     rax, [rdx+rcx*8+10h]
0x18009d77a  movzx   ecx, word ptr [rax]
0x18009d77d  mov     rax, [rax+8]
0x18009d781  mov     [rbp+57h+var_78], rax
0x18009d785  mov     [rbp+57h+arg_18], ecx
0x18009d788  mov     word ptr [rbp+57h+var_80], cx
0x18009d78c  mov     word ptr [rbp+57h+var_80+2], cx
0x18009d790  jmp     short loc_18009D7BD
0x18009d792  cmp     [rdx+rcx*8+8], ebx
0x18009d796  jbe     short loc_18009D7BD
0x18009d798  mov     rax, [rdx+rcx*8+10h]
0x18009d79d  lea     rdx, [rbp+57h+var_D0]
0x18009d7a1  mov     rcx, [rax+8]
0x18009d7a5  mov     ecx, [rcx]
0x18009d7a7  call    SampFlagsToAccountControl
0x18009d7ac  mov     ebx, eax
0x18009d7ae  test    eax, eax
0x18009d7b0  js      loc_18009D986
0x18009d7b6  movzx   r9d, [rbp+57h+var_B0.Length]
0x18009d7bb  xor     ebx, ebx
0x18009d7bd  mov     rdx, [rbp+57h+arg_8]
0x18009d7c1  inc     esi
0x18009d7c3  jmp     loc_18009D6B0
0x18009d7c8  mov     ebx, 0C000000Dh
0x18009d7cd  jmp     loc_18009D986
0x18009d7d2  test    r9w, r9w
0x18009d7d6  jz      loc_18009D973
0x18009d7dc  mov     rax, [rbp+57h+Src]
0x18009d7e0  test    rax, rax
0x18009d7e3  jz      loc_18009D973
0x18009d7e9  cmp     [r13+0], bl
0x18009d7ed  jz      short loc_18009D824
0x18009d7ef  movzx   eax, word ptr [r13+4]
0x18009d7f4  lea     rcx, [r13+0Ch]; Memory
0x18009d7f8  movzx   edx, word ptr [r13+8]; MemorySize
0x18009d7fd  lea     r12, [rbp+57h+var_58]
0x18009d801  xor     r8d, r8d; OptionFlags
0x18009d804  mov     word ptr [rbp+57h+var_58], ax
0x18009d808  mov     word ptr [rbp+57h+var_58+2], dx
0x18009d80c  mov     qword ptr [rbp+57h+var_58+8], rcx
0x18009d810  call    cs:__imp_SystemFunction041
0x18009d816  mov     ebx, eax
0x18009d818  test    eax, eax
0x18009d81a  js      loc_18009D986
0x18009d820  mov     rax, [rbp+57h+Src]
0x18009d824  lea     r8, [rbp+57h+arg_0]
0x18009d828  mov     rcx, rax; Src
0x18009d82b  lea     rdx, [rbp+57h+Sid2]
0x18009d82f  call    SampSplitSid
0x18009d834  mov     ebx, eax
0x18009d836  test    eax, eax
0x18009d838  js      loc_18009D96D
0x18009d83e  call    SampDsGetPrimaryDomainStart
0x18009d843  cmp     eax, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x18009d849  mov     edi, eax
0x18009d84b  mov     r14, [rbp+57h+Sid2]
0x18009d84f  jnb     loc_18009D7C8
0x18009d855  xor     ebx, ebx
0x18009d857  mov     ecx, edi
0x18009d859  mov     rdx, r14; Sid2
0x18009d85c  imul    r8, rcx, 550h
0x18009d863  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18009d86a  mov     rcx, [r8+rcx+8]; Sid1
0x18009d86f  call    cs:__imp_RtlEqualSid
0x18009d875  mov     ecx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x18009d87b  test    al, al
0x18009d87d  jnz     short loc_18009D885
0x18009d87f  inc     edi
0x18009d881  cmp     edi, ecx
0x18009d883  jb      short loc_18009D857
0x18009d885  cmp     edi, ecx
0x18009d887  jnb     loc_18009D7C8
0x18009d88d  mov     sil, bl
0x18009d890  cmp     [rbp+57h+var_C8.Length], bx
0x18009d894  jnz     short loc_18009D8B2
0x18009d896  lea     r8, [rbp+57h+var_C8]
0x18009d89a  mov     edx, edi
0x18009d89c  lea     rcx, [rbp+57h+var_B0]
0x18009d8a0  call    SampCreateDefaultUPN
0x18009d8a5  mov     ebx, eax
0x18009d8a7  test    eax, eax
0x18009d8a9  js      loc_18009D986
0x18009d8af  mov     sil, 1
0x18009d8b2  cmp     word ptr [rbp+57h+arg_18], r15w
0x18009d8b7  jz      short loc_18009D8D3
0x18009d8b9  mov     edx, [rbp+57h+arg_0]
0x18009d8bc  lea     r8, [rbp+57h+var_A0]
0x18009d8c0  lea     rcx, [rbp+57h+var_80]
0x18009d8c4  call    SampDecryptSupplementalCredentials
0x18009d8c9  mov     ebx, eax
0x18009d8cb  test    eax, eax
0x18009d8cd  js      loc_18009D958
0x18009d8d3  mov     r8d, [rbp+57h+var_D0]; unsigned int
0x18009d8d7  lea     rax, [rbp+57h+var_B8]
0x18009d8db  mov     [rsp+110h+var_D8], rax; struct _SAMP_SUPPLEMENTAL_CRED **
0x18009d8e0  lea     r9, [rbp+57h+var_C8]; struct _UNICODE_STRING *
0x18009d8e4  mov     al, [r13+1]
0x18009d8e8  lea     rdx, [rbp+57h+var_B0]; struct _UNICODE_STRING *
0x18009d8ec  mov     [rsp+110h+var_E0], al; char
0x18009d8f0  mov     ecx, edi; unsigned int
0x18009d8f2  lea     rax, [rbp+57h+var_A0]
0x18009d8f6  mov     [rsp+110h+var_E8], r12; struct _UNICODE_STRING *
0x18009d8fb  mov     [rsp+110h+var_F0], rax; struct _UNICODE_STRING *
0x18009d900  call    ?SampCreateSupplementalCredentialsHelper@@YAJKPEAU_UNICODE_STRING@@K000EPEAPEAU_SAMP_SUPPLEMENTAL_CRED@@@Z; SampCreateSupplementalCredentialsHelper(ulong,_UNICODE_STRING *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,uchar,_SAMP_SUPPLEMENTAL_CRED * *)
0x18009d905  mov     r15, [rbp+57h+var_B8]
0x18009d909  xor     edi, edi
0x18009d90b  mov     ebx, eax
0x18009d90d  test    eax, eax
0x18009d90f  js      short loc_18009D958
0x18009d911  mov     r8d, [rbp+57h+arg_0]
0x18009d915  lea     rax, [rbp+57h+var_70]
0x18009d919  mov     r9, r15
0x18009d91c  mov     [rsp+110h+var_F0], rax; __int64
0x18009d921  xor     edx, edx
0x18009d923  lea     rcx, [rbp+57h+var_A0]; struct _UNICODE_STRING *
0x18009d927  call    SampConvertCredentialsFromListToAttr
0x18009d92c  mov     ebx, eax
0x18009d92e  test    eax, eax
0x18009d930  js      short loc_18009D958
0x18009d932  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18009d937  mov     ebx, eax
0x18009d939  cmp     eax, 0C00000BBh
0x18009d93e  jnz     short loc_18009D944
0x18009d940  mov     ebx, edi
0x18009d942  jmp     short loc_18009D958
0x18009d944  test    eax, eax
0x18009d946  js      short loc_18009D958
0x18009d948  mov     rdx, [rbp+57h+arg_10]
0x18009d94c  lea     rcx, [rbp+57h+var_70]
0x18009d950  call    cs:__imp_NtdsaExtPrepareSupplementalCredentials
0x18009d956  mov     ebx, eax
0x18009d958  test    sil, sil
0x18009d95b  jz      short loc_18009D967
0x18009d95d  mov     rcx, [rbp+57h+var_C8.Buffer]; hMem
0x18009d961  call    cs:__imp_LocalFree
0x18009d967  mov     rdi, [rbp+57h+var_A0.Buffer]
0x18009d96b  jmp     short loc_18009D978
0x18009d96d  mov     r14, [rbp+57h+Sid2]
0x18009d971  jmp     short loc_18009D986
0x18009d973  mov     ebx, 0C000000Dh
0x18009d978  test    rdi, rdi
0x18009d97b  jz      short loc_18009D986
0x18009d97d  mov     rcx, rdi; hMem
0x18009d980  call    cs:__imp_LocalFree
0x18009d986  mov     edx, dword ptr [rbp+57h+var_70+8]
0x18009d989  xor     edi, edi
0x18009d98b  mov     rcx, [rbp+57h+var_60]
0x18009d98f  test    edx, edx
0x18009d991  jz      short loc_18009D9BC
0x18009d993  mov     eax, edi
0x18009d995  add     rax, rax
0x18009d998  mov     r8, [rcx+rax*8+8]
0x18009d99d  test    r8, r8
0x18009d9a0  jz      short loc_18009D9B2
0x18009d9a2  mov     rcx, r8; hMem
0x18009d9a5  call    cs:__imp_LocalFree
0x18009d9ab  mov     rcx, [rbp+57h+var_60]; hMem
0x18009d9af  mov     edx, dword ptr [rbp+57h+var_70+8]
0x18009d9b2  inc     edi
0x18009d9b4  cmp     edi, edx
0x18009d9b6  jb      short loc_18009D993
0x18009d9b8  mov     r15, [rbp+57h+var_B8]
0x18009d9bc  xor     edi, edi
0x18009d9be  test    rcx, rcx
0x18009d9c1  jz      short loc_18009D9C9
0x18009d9c3  call    cs:__imp_LocalFree
0x18009d9c9  test    r15, r15
0x18009d9cc  jz      short loc_18009D9D6
0x18009d9ce  mov     rcx, r15; hMem
0x18009d9d1  call    ?SampFreeSupplementalCredentialList@@YAXPEAU_SAMP_SUPPLEMENTAL_CRED@@@Z; SampFreeSupplementalCredentialList(_SAMP_SUPPLEMENTAL_CRED *)
0x18009d9d6  test    r14, r14
0x18009d9d9  jz      short loc_18009D9E4
0x18009d9db  mov     rcx, r14; hMem
0x18009d9de  call    cs:__imp_LocalFree
0x18009d9e4  test    r12, r12
0x18009d9e7  jz      short loc_18009DA05
0x18009d9e9  movzx   ecx, word ptr [r12+2]
0x18009d9ef  mov     rax, [r12+8]
0x18009d9f4  test    rcx, rcx
0x18009d9f7  jz      short loc_18009DA05
0x18009d9f9  mov     [rax], dil
0x18009d9fc  inc     rax
0x18009d9ff  sub     rcx, 1
0x18009da03  jnz     short loc_18009D9F9
0x18009da05  mov     rcx, cs:WPP_GLOBAL_Control
0x18009da0c  test    dword ptr [rcx+44h], 20000h
0x18009da13  jz      short loc_18009DA31
0x18009da15  mov     rcx, [rcx+38h]
0x18009da19  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x18009da20  mov     edx, 14Bh
0x18009da25  mov     dword ptr [rsp+110h+var_F0], ebx
0x18009da29  mov     r9d, ebx
0x18009da2c  call    WPP_SF_Dd
0x18009da31  mov     eax, ebx
0x18009da33  add     rsp, 0D8h
0x18009da3a  pop     r15
0x18009da3c  pop     r14
0x18009da3e  pop     r13
0x18009da40  pop     r12
0x18009da42  pop     rdi
0x18009da43  pop     rsi
0x18009da44  pop     rbx
0x18009da45  pop     rbp
0x18009da46  retn
```
