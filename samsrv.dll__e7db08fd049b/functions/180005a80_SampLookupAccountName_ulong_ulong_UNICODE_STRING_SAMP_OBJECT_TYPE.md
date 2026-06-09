# SampLookupAccountName(ulong,ulong,_UNICODE_STRING *,_SAMP_OBJECT_TYPE *)

- ea: `0x180005a80`
- end: `0x180006163`
- name: `?SampLookupAccountName@@YAJKKPEAU_UNICODE_STRING@@PEAW4_SAMP_OBJECT_TYPE@@@Z`
- size: `1763`
- prototype: `int(unsigned int, unsigned int, struct _UNICODE_STRING *, enum _SAMP_OBJECT_TYPE *)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180012160`
- `0x180035610`
- `0x1800aa648`

## callees

- `0x180005a80`
- `0x180006170`
- `0x1800066f0`
- `0x180008590`
- `0x180012a28`
- `0x180018620`
- `0x1800198a0`
- `0x18001cfa0`
- `0x1800263d8`
- `0x180027e24`
- `0x18003c010`
- `0x18003c920`
- `0x18008ecd0`
- `0x1800bb788`

## import_xrefs

- `ntdll!NtCloseObjectAuditAlarm` at `0x18000606e`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18000606e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800060f1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800060f1`
- `ntdll!RtlEnterCriticalSection` at `0x1800060c1`
- `ntdll!RtlEnterCriticalSection` at `0x1800060c1`
- `ntdll!RtlCopyUnicodeString` at `0x180005b23`
- `ntdll!RtlCopyUnicodeString` at `0x180005b23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005b05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005b05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005e30`
- `RPCRT4!RpcRevertToSelf` at `0x18000609b`
- `RPCRT4!RpcRevertToSelf` at `0x18000609b`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18000608c`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18000608c`

## pseudocode

```c
__int64 __fastcall SampLookupAccountName(
        unsigned int a1,
        unsigned int a2,
        struct _UNICODE_STRING *a3,
        enum _SAMP_OBJECT_TYPE *a4)
{
  char *v5; // rcx
  __int64 v8; // r10
  int UnicodeStringAttribute; // edi
  unsigned int i; // edx
  __int64 v11; // r8
  const UNICODE_STRING *v12; // rbx
  WCHAR *v13; // rax
  PUNICODE_STRING v14; // rcx
  __int64 v15; // rdx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned int AccountContext2; // eax
  struct _SAMP_OBJECT *v20; // rbx
  unsigned int v21; // eax
  struct _SAMP_OBJECT *v22; // rbx
  unsigned int v23; // eax
  PUNICODE_STRING v24; // rcx
  _QWORD *v25; // rbx
  void *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // eax
  size_t v32; // rbp
  WCHAR *v33; // rax
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // rdx
  int v37; // esi
  bool v38; // zf
  int v39; // esi
  char v40; // al
  __int64 v41; // rcx
  _QWORD *v42; // rax
  unsigned int *v43; // [rsp+20h] [rbp-88h]
  PVOID HandleId[7]; // [rsp+70h] [rbp-38h] BYREF
  int v45; // [rsp+B0h] [rbp+8h] BYREF

  HandleId[0] = 0;
  v5 = (char *)SampDefinedDomains + 1360 * a1;
  v8 = *((_QWORD *)v5 + 168);
  if ( v8 )
  {
    UnicodeStringAttribute = 0;
    *(_DWORD *)a4 = 5;
    for ( i = 0; i < *(_DWORD *)v8; ++i )
    {
      v11 = *(_QWORD *)(v8 + 8) + 24LL * i;
      if ( *(_DWORD *)v11 == a2 )
      {
        *(_DWORD *)a4 = 3;
        if ( a3 )
        {
          v12 = (const UNICODE_STRING *)(v11 + 8);
          a3->Length = 0;
          v13 = (WCHAR *)LocalAlloc(0x40u, *(unsigned __int16 *)(v11 + 10));
          a3->Buffer = v13;
          if ( v13 )
          {
            a3->MaximumLength = v12->MaximumLength;
            RtlCopyUnicodeString(a3, v12);
          }
          else
          {
            UnicodeStringAttribute = -1073741801;
          }
        }
        break;
      }
    }
    v14 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)UnicodeStringAttribute;
    v15 = 110;
    goto LABEL_12;
  }
  if ( (*(_BYTE *)(*(_QWORD *)v5 + 192LL) & 2) != 0 )
  {
    v17 = SampLookupAccountNameDs(*((PSID *)v5 + 1), a2, a3, a4, v43);
    v18 = v17;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 111, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v17, v17);
    return v18;
  }
  AccountContext2 = SampCreateAccountContext2(0, 2u, a2, 0, 0, 1, 1u, 0, 0, 1, 0, 0, 0, (__int64 *)HandleId);
  UnicodeStringAttribute = AccountContext2;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      123,
      WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
      AccountContext2,
      AccountContext2);
  if ( UnicodeStringAttribute >= 0 )
  {
    v20 = (struct _SAMP_OBJECT *)HandleId[0];
    *(_DWORD *)a4 = 2;
    if ( a3 )
      UnicodeStringAttribute = SampGetUnicodeStringAttribute(v20);
    SampDeleteContext(v20);
    v14 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)UnicodeStringAttribute;
    v15 = 112;
LABEL_12:
    WPP_SF_Dd(
      v14[3].Buffer,
      v15,
      WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
      (unsigned int)UnicodeStringAttribute,
      UnicodeStringAttribute);
    return (unsigned int)UnicodeStringAttribute;
  }
  v21 = SampCreateAccountContext2(0, 3u, a2, 0, 0, 1, 1u, 0, 0, 1, 0, 0, 0, (__int64 *)HandleId);
  UnicodeStringAttribute = v21;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 123, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v21, v21);
  if ( UnicodeStringAttribute >= 0 )
  {
    v22 = (struct _SAMP_OBJECT *)HandleId[0];
    *(_DWORD *)a4 = 3;
    if ( a3 )
      UnicodeStringAttribute = SampGetUnicodeStringAttribute(v22);
    SampDeleteContext(v22);
    v14 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)UnicodeStringAttribute;
    v15 = 113;
    goto LABEL_12;
  }
  v23 = SampCreateAccountContext2(0, 4u, a2, 0, 0, 1, 1u, 0, 0, 1, 0, 0, 0, (__int64 *)HandleId);
  UnicodeStringAttribute = v23;
  v24 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 123, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v23, v23);
    v24 = WPP_GLOBAL_Control;
  }
  if ( UnicodeStringAttribute >= 0 )
  {
    v25 = HandleId[0];
    *(_DWORD *)a4 = 4;
    if ( !a3 )
    {
LABEL_68:
      *((_BYTE *)v25 + 20) |= 0x10u;
      v37 = 0;
      v38 = (*((_BYTE *)v25 + 20) & 0x20) == 0;
      v45 = 0;
      if ( v38 )
      {
        SampImpersonateClient(&v45);
        v37 = v45;
      }
      NtCloseObjectAuditAlarm(&SampSamSubsystem, v25, *((_BYTE *)v25 + 208));
      if ( v37 == 2 )
      {
        RpcRevertToSelf();
      }
      else
      {
        v39 = v37 - 1;
        if ( v39 )
        {
          if ( v39 == 2 && (int)SampShouldCallNtdsaApiSet() >= 0 )
            NtdsaExtUnImpersonateAnyClient();
        }
        else
        {
          SamIRevertNullSession();
        }
      }
      *((_BYTE *)v25 + 21) &= ~1u;
      v40 = *((_BYTE *)v25 + 28);
      if ( ((v40 & 1) == 0 || (v25[24] & 2) == 0) && v40 >= 0 )
      {
        RtlEnterCriticalSection(&SampContextListCritSect);
        v41 = *v25;
        if ( *v25 )
        {
          v42 = (_QWORD *)v25[1];
          if ( v42 )
          {
            if ( *(_QWORD **)(v41 + 8) != v25 || (_QWORD *)*v42 != v25 )
              __fastfail(3u);
            *v42 = v41;
            *(_QWORD *)(v41 + 8) = v42;
          }
        }
        RtlLeaveCriticalSection(&SampContextListCritSect);
      }
      SampDeReferenceContext(v25, 0);
      v14 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)UnicodeStringAttribute;
      v15 = 114;
      goto LABEL_12;
    }
    if ( !v25 )
    {
      UnicodeStringAttribute = -1073741811;
      goto LABEL_51;
    }
    if ( (v25[24] & 2) != 0 )
    {
      if ( v25[14] )
      {
        if ( _bittest64((const signed __int64 *)v25[8], 1u) )
        {
          v26 = (void *)v25[17];
          if ( v26 )
            LocalFree(v26);
          v27 = v25[14];
          *((_BYTE *)v25 + 20) &= 0xF0u;
          v25[17] = v27;
          v25[14] = 0;
          v25[15] = 0;
          *((_DWORD *)v25 + 32) = 0;
          UnicodeStringAttribute = SampValidateDsAttributes((struct _SAMP_OBJECT *)v25, 0);
          if ( UnicodeStringAttribute >= 0 )
          {
            UnicodeStringAttribute = SampValidateDsAttributes((struct _SAMP_OBJECT *)v25, 1u);
            if ( UnicodeStringAttribute >= 0 )
            {
              SampMarkPerAttributeInvalidFromWhichFields(v25, 0);
              *((_BYTE *)v25 + 29) &= ~1u;
            }
          }
          goto LABEL_49;
        }
      }
      else
      {
        UnicodeStringAttribute = SampValidateDsAttributes((struct _SAMP_OBJECT *)v25, 0);
        if ( UnicodeStringAttribute < 0 )
        {
LABEL_49:
          v24 = WPP_GLOBAL_Control;
LABEL_51:
          if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(
              v24[3].Buffer,
              110,
              WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
              (unsigned int)UnicodeStringAttribute,
              UnicodeStringAttribute);
            v24 = WPP_GLOBAL_Control;
          }
          if ( UnicodeStringAttribute >= 0 )
          {
            v29 = 88LL * *((int *)v25 + 4);
            if ( (v25[24] & 2) != 0 )
              v30 = *(unsigned int *)((char *)&SampObjectInformation + v29 + 76);
            else
              v30 = *(unsigned int *)((char *)&SampObjectInformation + v29 + 52);
            v31 = *(_DWORD *)(v25[14] + v30 + 16);
            a3->MaximumLength = v31;
            a3->Length = v31;
            v32 = v31;
            v33 = (WCHAR *)LocalAlloc(0x40u, v31);
            a3->Buffer = v33;
            if ( v33 )
            {
              v34 = v25[14];
              v35 = 88LL * *((int *)v25 + 4);
              if ( (v25[24] & 2) != 0 )
                v36 = (unsigned int)(*(_DWORD *)((char *)&SampObjectInformation + v35 + 72)
                                   + *(_DWORD *)(*(unsigned int *)((char *)&SampObjectInformation + v35 + 76) + v34 + 12));
              else
                v36 = (unsigned int)(*(_DWORD *)((char *)&SampObjectInformation + v35 + 56)
                                   + *(_DWORD *)(*(unsigned int *)((char *)&SampObjectInformation + v35 + 52) + v34 + 12));
              memcpy_0(v33, (const void *)(v34 + v36), v32);
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 32, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids, 0, 0);
              UnicodeStringAttribute = 0;
            }
            else
            {
              *(_DWORD *)&a3->Length = 0;
              UnicodeStringAttribute = -1073741801;
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                WPP_SF_Dd(
                  WPP_GLOBAL_Control[3].Buffer,
                  31,
                  WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                  3221225495LL,
                  -1073741801);
            }
          }
          else if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(
              v24[3].Buffer,
              29,
              WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
              (unsigned int)UnicodeStringAttribute,
              UnicodeStringAttribute);
          }
          goto LABEL_68;
        }
      }
      v28 = SampValidateDsAttributes((struct _SAMP_OBJECT *)v25, 1u);
    }
    else
    {
      v28 = SampValidateRegAttributes((struct _SAMP_OBJECT *)v25, 1u);
    }
    UnicodeStringAttribute = v28;
    goto LABEL_49;
  }
  *(_DWORD *)a4 = 5;
  if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v24[3].Buffer, 115, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180005a80  push    rbx
0x180005a82  push    rsi
0x180005a83  push    rdi
0x180005a84  push    r12
0x180005a86  push    r14
0x180005a88  sub     rsp, 80h
0x180005a8f  mov     eax, ecx
0x180005a91  xor     r12d, r12d
0x180005a94  imul    rcx, rax, 550h
0x180005a9b  mov     rsi, r9
0x180005a9e  mov     [rsp+0A8h+HandleId], r12
0x180005aa3  add     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180005aaa  mov     r14, r8
0x180005aad  mov     ebx, edx
0x180005aaf  mov     r10, [rcx+540h]
0x180005ab6  test    r10, r10
0x180005ab9  jz      loc_180005B6D
0x180005abf  mov     edi, r12d
0x180005ac2  mov     dword ptr [r9], 5
0x180005ac9  mov     edx, r12d
0x180005acc  cmp     edx, [r10]
0x180005acf  jnb     short loc_180005B30
0x180005ad1  mov     eax, edx
0x180005ad3  lea     rcx, [rax+rax*2]
0x180005ad7  mov     rax, [r10+8]
0x180005adb  cmp     [rax+rcx*8], ebx
0x180005ade  lea     r8, [rax+rcx*8]
0x180005ae2  jz      short loc_180005AE8
0x180005ae4  inc     edx
0x180005ae6  jmp     short loc_180005ACC
0x180005ae8  mov     dword ptr [r9], 3
0x180005aef  test    r14, r14
0x180005af2  jz      short loc_180005B30
0x180005af4  lea     rbx, [r8+8]
0x180005af8  mov     [r14], r12w
0x180005afc  movzx   edx, word ptr [rbx+2]; uBytes
0x180005b00  mov     ecx, 40h ; '@'; uFlags
0x180005b05  call    cs:__imp_LocalAlloc
0x180005b0b  mov     [r14+8], rax
0x180005b0f  test    rax, rax
0x180005b12  jz      short loc_180005B2B
0x180005b14  movzx   eax, word ptr [rbx+2]
0x180005b18  mov     rdx, rbx; SourceString
0x180005b1b  mov     rcx, r14; DestinationString
0x180005b1e  mov     [r14+2], ax
0x180005b23  call    cs:__imp_RtlCopyUnicodeString
0x180005b29  jmp     short loc_180005B30
0x180005b2b  mov     edi, 0C0000017h
0x180005b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b37  test    dword ptr [rcx+44h], 20000h
0x180005b3e  jz      short loc_180005B5C
0x180005b40  mov     edx, 6Eh ; 'n'
0x180005b45  mov     rcx, [rcx+38h]
0x180005b49  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180005b50  mov     r9d, edi
0x180005b53  mov     dword ptr [rsp+0A8h+var_88], edi
0x180005b57  call    WPP_SF_Dd
0x180005b5c  mov     eax, edi
0x180005b5e  add     rsp, 80h
0x180005b65  pop     r14
0x180005b67  pop     r12
0x180005b69  pop     rdi
0x180005b6a  pop     rsi
0x180005b6b  pop     rbx
0x180005b6c  retn
0x180005b6d  mov     rax, [rcx]
0x180005b70  test    byte ptr [rax+0C0h], 2
0x180005b77  jz      short loc_180005BC1
0x180005b79  mov     rcx, [rcx+8]; SourceSid
0x180005b7d  call    ?SampLookupAccountNameDs@@YAJPEAXKPEAU_UNICODE_STRING@@PEAW4_SAMP_OBJECT_TYPE@@PEAK@Z; SampLookupAccountNameDs(void *,ulong,_UNICODE_STRING *,_SAMP_OBJECT_TYPE *,ulong *)
0x180005b82  mov     ebx, eax
0x180005b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b8b  test    dword ptr [rcx+44h], 20000h
0x180005b92  jz      short loc_180005BB0
0x180005b94  mov     rcx, [rcx+38h]
0x180005b98  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180005b9f  mov     edx, 6Fh ; 'o'
0x180005ba4  mov     dword ptr [rsp+0A8h+var_88], eax
0x180005ba8  mov     r9d, eax
0x180005bab  call    WPP_SF_Dd
0x180005bb0  mov     eax, ebx
0x180005bb2  add     rsp, 80h
0x180005bb9  pop     r14
0x180005bbb  pop     r12
0x180005bbd  pop     rdi
0x180005bbe  pop     rsi
0x180005bbf  pop     rbx
0x180005bc0  retn
0x180005bc1  lea     rax, [rsp+0A8h+HandleId]
0x180005bc6  xor     r9d, r9d
0x180005bc9  mov     [rsp+0A8h+var_40], rax
0x180005bce  mov     r8d, ebx
0x180005bd1  mov     [rsp+0A8h+var_48], r12
0x180005bd6  mov     edx, 2
0x180005bdb  mov     [rsp+0A8h+var_50], r12b
0x180005be0  xor     ecx, ecx
0x180005be2  mov     [rsp+0A8h+var_58], r12b
0x180005be7  mov     [rsp+0A8h+var_60], 1
0x180005bec  mov     [rsp+0A8h+var_68], r12b
0x180005bf1  mov     [rsp+0A8h+var_70], r12b
0x180005bf6  mov     [rsp+0A8h+var_78], 1
0x180005bfb  mov     [rsp+0A8h+var_80], 1
0x180005c03  mov     [rsp+0A8h+var_88], r12
0x180005c08  call    SampCreateAccountContext2
0x180005c0d  mov     edi, eax
0x180005c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c16  test    dword ptr [rcx+44h], 20000h
0x180005c1d  jz      short loc_180005C3B
0x180005c1f  mov     rcx, [rcx+38h]
0x180005c23  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180005c2a  mov     edx, 7Bh ; '{'
0x180005c2f  mov     dword ptr [rsp+0A8h+var_88], eax
0x180005c33  mov     r9d, eax
0x180005c36  call    WPP_SF_Dd
0x180005c3b  test    edi, edi
0x180005c3d  js      short loc_180005C8A
0x180005c3f  mov     rbx, [rsp+0A8h+HandleId]
0x180005c44  mov     dword ptr [rsi], 2
0x180005c4a  test    r14, r14
0x180005c4d  jz      short loc_180005C64
0x180005c4f  mov     r9, r14
0x180005c52  mov     r8b, 1
0x180005c55  mov     edx, 1
0x180005c5a  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180005c5d  call    SampGetUnicodeStringAttribute
0x180005c62  mov     edi, eax
0x180005c64  mov     rcx, rbx; HandleId
0x180005c67  call    SampDeleteContext
0x180005c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c73  test    dword ptr [rcx+44h], 20000h
0x180005c7a  jz      loc_180005B5C
0x180005c80  mov     edx, 70h ; 'p'
0x180005c85  jmp     loc_180005B45
0x180005c8a  lea     rax, [rsp+0A8h+HandleId]
0x180005c8f  xor     r9d, r9d
0x180005c92  mov     [rsp+0A8h+var_40], rax
0x180005c97  mov     r8d, ebx
0x180005c9a  mov     [rsp+0A8h+var_48], r12
0x180005c9f  mov     edx, 3
0x180005ca4  mov     [rsp+0A8h+var_50], r12b
0x180005ca9  xor     ecx, ecx
0x180005cab  mov     [rsp+0A8h+var_58], r12b
0x180005cb0  mov     [rsp+0A8h+var_60], 1
0x180005cb5  mov     [rsp+0A8h+var_68], r12b
0x180005cba  mov     [rsp+0A8h+var_70], r12b
0x180005cbf  mov     [rsp+0A8h+var_78], 1
0x180005cc4  mov     [rsp+0A8h+var_80], 1
0x180005ccc  mov     [rsp+0A8h+var_88], r12
0x180005cd1  call    SampCreateAccountContext2
0x180005cd6  mov     edi, eax
0x180005cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cdf  test    dword ptr [rcx+44h], 20000h
0x180005ce6  jz      short loc_180005D04
0x180005ce8  mov     rcx, [rcx+38h]
0x180005cec  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180005cf3  mov     edx, 7Bh ; '{'
0x180005cf8  mov     dword ptr [rsp+0A8h+var_88], eax
0x180005cfc  mov     r9d, eax
0x180005cff  call    WPP_SF_Dd
0x180005d04  test    edi, edi
0x180005d06  js      short loc_180005D53
0x180005d08  mov     rbx, [rsp+0A8h+HandleId]
0x180005d0d  mov     dword ptr [rsi], 3
0x180005d13  test    r14, r14
0x180005d16  jz      short loc_180005D2D
0x180005d18  mov     r9, r14
0x180005d1b  mov     r8b, 1
0x180005d1e  mov     edx, 1
0x180005d23  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180005d26  call    SampGetUnicodeStringAttribute
0x180005d2b  mov     edi, eax
0x180005d2d  mov     rcx, rbx; HandleId
0x180005d30  call    SampDeleteContext
0x180005d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d3c  test    dword ptr [rcx+44h], 20000h
0x180005d43  jz      loc_180005B5C
0x180005d49  mov     edx, 71h ; 'q'
0x180005d4e  jmp     loc_180005B45
0x180005d53  lea     rax, [rsp+0A8h+HandleId]
0x180005d58  xor     r9d, r9d
0x180005d5b  mov     [rsp+0A8h+var_40], rax
0x180005d60  mov     r8d, ebx
0x180005d63  mov     [rsp+0A8h+var_48], r12
0x180005d68  mov     edx, 4
0x180005d6d  mov     [rsp+0A8h+var_50], r12b
0x180005d72  xor     ecx, ecx
0x180005d74  mov     [rsp+0A8h+var_58], r12b
0x180005d79  mov     [rsp+0A8h+var_60], 1
0x180005d7e  mov     [rsp+0A8h+var_68], r12b
0x180005d83  mov     [rsp+0A8h+var_70], r12b
0x180005d88  mov     [rsp+0A8h+var_78], 1
0x180005d8d  mov     [rsp+0A8h+var_80], 1
0x180005d95  mov     [rsp+0A8h+var_88], r12
0x180005d9a  call    SampCreateAccountContext2
0x180005d9f  mov     edi, eax
0x180005da1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005da8  test    dword ptr [rcx+44h], 20000h
0x180005daf  jz      short loc_180005DD4
0x180005db1  mov     rcx, [rcx+38h]
0x180005db5  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180005dbc  mov     edx, 7Bh ; '{'
0x180005dc1  mov     dword ptr [rsp+0A8h+var_88], eax
0x180005dc5  mov     r9d, eax
0x180005dc8  call    WPP_SF_Dd
0x180005dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dd4  test    edi, edi
0x180005dd6  js      loc_180006126
0x180005ddc  mov     rbx, [rsp+0A8h+HandleId]
0x180005de1  mov     dword ptr [rsi], 4
0x180005de7  test    r14, r14
0x180005dea  jz      loc_180006033
0x180005df0  mov     [rsp+0A8h+arg_10], r15
0x180005df8  test    rbx, rbx
0x180005dfb  jz      loc_180005EBE
0x180005e01  test    byte ptr [rbx+0C0h], 2
0x180005e08  jz      loc_180005EA6
0x180005e0e  cmp     [rbx+70h], r12
0x180005e12  jz      short loc_180005E87
0x180005e14  mov     rax, [rbx+40h]
0x180005e18  bt      qword ptr [rax], 1
0x180005e1d  setb    al
0x180005e20  test    al, al
0x180005e22  jz      short loc_180005E97
0x180005e24  mov     rcx, [rbx+88h]; hMem
0x180005e2b  test    rcx, rcx
0x180005e2e  jz      short loc_180005E36
0x180005e30  call    cs:__imp_LocalFree
0x180005e36  mov     rax, [rbx+70h]
0x180005e3a  xor     edx, edx; unsigned int
0x180005e3c  and     byte ptr [rbx+14h], 0F0h
0x180005e40  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180005e43  mov     [rbx+88h], rax
0x180005e4a  mov     [rbx+70h], r12
0x180005e4e  mov     [rbx+78h], r12
0x180005e52  mov     [rbx+80h], r12d
0x180005e59  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180005e5e  mov     edi, eax
0x180005e60  test    eax, eax
0x180005e62  js      short loc_180005EB5
0x180005e64  mov     edx, 1; unsigned int
0x180005e69  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180005e6c  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180005e71  mov     edi, eax
0x180005e73  test    eax, eax
0x180005e75  js      short loc_180005EB5
0x180005e77  xor     edx, edx
0x180005e79  mov     rcx, rbx
0x180005e7c  call    SampMarkPerAttributeInvalidFromWhichFields
0x180005e81  and     byte ptr [rbx+1Dh], 0FEh
0x180005e85  jmp     short loc_180005EB5
0x180005e87  xor     edx, edx; unsigned int
0x180005e89  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180005e8c  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180005e91  mov     edi, eax
0x180005e93  test    eax, eax
0x180005e95  js      short loc_180005EB5
0x180005e97  mov     edx, 1; unsigned int
0x180005e9c  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180005e9f  call    ?SampValidateDsAttributes@@YAJPEAU_SAMP_OBJECT@@K@Z; SampValidateDsAttributes(_SAMP_OBJECT *,ulong)
0x180005ea4  jmp     short loc_180005EB3
0x180005ea6  mov     edx, 1; unsigned int
0x180005eab  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180005eae  call    SampValidateRegAttributes
0x180005eb3  mov     edi, eax
0x180005eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ebc  jmp     short loc_180005EC3
0x180005ebe  mov     edi, 0C000000Dh
0x180005ec3  test    dword ptr [rcx+44h], 20000h
0x180005eca  jz      short loc_180005EEF
0x180005ecc  mov     rcx, [rcx+38h]
0x180005ed0  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x180005ed7  mov     edx, 6Eh ; 'n'
0x180005edc  mov     dword ptr [rsp+0A8h+var_88], edi
0x180005ee0  mov     r9d, edi
0x180005ee3  call    WPP_SF_Dd
0x180005ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005eef  test    edi, edi
0x180005ef1  jns     short loc_180005F21
0x180005ef3  test    dword ptr [rcx+44h], 20000h
0x180005efa  jz      loc_18000602B
0x180005f00  mov     rcx, [rcx+38h]
0x180005f04  lea     r8, WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids
0x180005f0b  mov     edx, 1Dh
0x180005f10  mov     dword ptr [rsp+0A8h+var_88], edi
0x180005f14  mov     r9d, edi
0x180005f17  call    WPP_SF_Dd
0x180005f1c  jmp     loc_18000602B
0x180005f21  movsxd  rax, dword ptr [rbx+10h]
0x180005f25  lea     rdi, ?SampObjectInformation@@3PAU_SAMP_OBJECT_INFORMATION@@A; _SAMP_OBJECT_INFORMATION near * SampObjectInformation
0x180005f2c  imul    rcx, rax, 58h ; 'X'
0x180005f30  test    byte ptr [rbx+0C0h], 2
0x180005f37  mov     [rsp+0A8h+arg_8], rbp
0x180005f3f  jz      short loc_180005F47
0x180005f41  mov     eax, [rcx+rdi+4Ch]
0x180005f45  jmp     short loc_180005F4B
0x180005f47  mov     eax, [rcx+rdi+34h]
0x180005f4b  add     rax, [rbx+70h]
0x180005f4f  mov     ecx, 40h ; '@'; uFlags
0x180005f54  mov     eax, [rax+10h]
0x180005f57  mov     edx, eax; uBytes
  ... truncated ...
```
