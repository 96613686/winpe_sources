# SampBuildAliasMembersKeyName

- ea: `0x1800aeafc`
- end: `0x1800aedfa`
- name: `SampBuildAliasMembersKeyName`
- size: `766`
- prototype: `__int64 __fastcall(PSID Sid, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180034204`
- `0x180034758`
- `0x180034b6c`
- `0x180034fa4`
- `0x180035494`
- `0x1800985f0`

## callees

- `0x180005980`
- `0x180020610`
- `0x1800213d0`
- `0x180021ca0`
- `0x180027e24`
- `0x1800aeafc`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800aedb9`
- `ntdll!RtlFreeUnicodeString` at `0x1800aedb9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800aec00`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800aec00`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800aeb42`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800aebda`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800aeb42`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800aebda`
- `ntdll!RtlSubAuthoritySid` at `0x1800aebed`
- `ntdll!RtlSubAuthoritySid` at `0x1800aebed`
- `ntdll!RtlCopyUnicodeString` at `0x1800aed7c`
- `ntdll!RtlCopyUnicodeString` at `0x1800aed7c`
- `ntdll!RtlCopySid` at `0x1800aebd1`
- `ntdll!RtlCopySid` at `0x1800aebd1`
- `ntdll!RtlLengthSid` at `0x1800aeb7e`
- `ntdll!RtlLengthSid` at `0x1800aebc3`
- `ntdll!RtlLengthSid` at `0x1800aeb7e`
- `ntdll!RtlLengthSid` at `0x1800aebc3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800aeb8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800aeb8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aec39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aec54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aed9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aeda8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aec39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aec54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aed9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aeda8`

## pseudocode

```c
__int64 __fastcall SampBuildAliasMembersKeyName(PSID Sid, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3)
{
  int v6; // r15d
  PUNICODE_STRING v7; // rcx
  NTSTATUS inited; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  ULONG v11; // eax
  HLOCAL v12; // r14
  ULONG v13; // eax
  ULONG v14; // r15d
  unsigned int v15; // edx
  unsigned int v16; // r8d
  PWSTR Buffer; // rcx
  PWSTR v18; // rcx
  unsigned __int16 v19; // dx
  unsigned __int16 v20; // r15
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING v23; // [rsp+40h] [rbp-18h] BYREF

  *(_QWORD *)&UnicodeString.Length = 0;
  *(_QWORD *)&v23.Length = 0;
  *a2 = 0;
  *a3 = 0;
  v23.Buffer = 0;
  UnicodeString.Buffer = 0;
  v6 = *RtlSubAuthorityCountSid(Sid);
  if ( !(_BYTE)v6 )
  {
    v7 = WPP_GLOBAL_Control;
    inited = -1073741704;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v9 = 74;
      v10 = 3221225592LL;
LABEL_23:
      WPP_SF_Dd(v7[3].Buffer, v9, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v10, inited);
      return (unsigned int)inited;
    }
    return (unsigned int)inited;
  }
  v11 = RtlLengthSid(Sid);
  v12 = LocalAlloc(0x40u, v11);
  if ( v12 )
  {
    v13 = RtlLengthSid(Sid);
    RtlCopySid(v13, v12, Sid);
    *RtlSubAuthorityCountSid(v12) = v6 - 1;
    v14 = *RtlSubAuthoritySid(Sid, v6 - 1);
    inited = RtlConvertSidToUnicodeString(&UnicodeString, v12, 1u);
    if ( inited >= 0 )
    {
      inited = SampRtlConvertUlongToUnicodeString(v14, v15, v16, 1u, &v23);
      if ( inited >= 0 )
      {
        v19 = UnicodeString.Length
            + SampNameDomains.Length
            + SampNameDomainAliases.Length
            + SampNameDomainAliasesMembers.Length
            + *((_WORD *)SampDefinedDomains + 680 * SampTransactionDomainIndexGlobal + 16)
            + 4 * SampBackSlash.Length
            + 18;
        v20 = v23.Length + SampBackSlash.Length + v19 + 6;
        inited = SampInitUnicodeString(a2, v19);
        if ( inited >= 0 )
        {
          inited = SampInitUnicodeString(a3, v20);
          if ( inited >= 0 )
          {
            SampAppendUnicodeString(a2, &SampNameDomains);
            SampAppendUnicodeString(a2, &SampBackSlash);
            SampAppendUnicodeString(
              a2,
              (struct _UNICODE_STRING *)SampDefinedDomains + 85 * SampTransactionDomainIndexGlobal + 2);
            SampAppendUnicodeString(a2, &SampBackSlash);
            SampAppendUnicodeString(a2, &SampNameDomainAliases);
            SampAppendUnicodeString(a2, &SampBackSlash);
            SampAppendUnicodeString(a2, &SampNameDomainAliasesMembers);
            SampAppendUnicodeString(a2, &SampBackSlash);
            SampAppendUnicodeString(a2, &UnicodeString);
            RtlCopyUnicodeString(a3, a2);
            SampAppendUnicodeString(a3, &SampBackSlash);
            inited = SampAppendUnicodeString(a3, &v23);
          }
          else
          {
            SampFreeUnicodeString(a2);
          }
        }
        LocalFree(v23.Buffer);
LABEL_19:
        LocalFree(v12);
        if ( UnicodeString.Buffer )
          RtlFreeUnicodeString(&UnicodeString);
        v7 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          v9 = 76;
          v10 = (unsigned int)inited;
          goto LABEL_23;
        }
        return (unsigned int)inited;
      }
    }
    else
    {
      UnicodeString.Buffer = 0;
    }
    Buffer = a3->Buffer;
    if ( Buffer )
    {
      LocalFree(Buffer);
      a3->Buffer = 0;
    }
    v18 = a2->Buffer;
    if ( v18 )
    {
      LocalFree(v18);
      a2->Buffer = 0;
    }
    goto LABEL_19;
  }
  v7 = WPP_GLOBAL_Control;
  inited = -1073741670;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v9 = 75;
    v10 = 3221225626LL;
    goto LABEL_23;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800aeafc  push    rbp
0x1800aeafe  push    rbx
0x1800aeaff  push    rsi
0x1800aeb00  push    rdi
0x1800aeb01  push    r14
0x1800aeb03  push    r15
0x1800aeb05  mov     rbp, rsp
0x1800aeb08  sub     rsp, 58h
0x1800aeb0c  xorps   xmm0, xmm0
0x1800aeb0f  mov     qword ptr [rbp+UnicodeString.Length], 0
0x1800aeb17  xorps   xmm1, xmm1
0x1800aeb1a  mov     qword ptr [rbp+var_18.Length], 0
0x1800aeb22  movups  xmmword ptr [rdx], xmm0
0x1800aeb25  mov     rsi, r8
0x1800aeb28  mov     rdi, rdx
0x1800aeb2b  movups  xmmword ptr [r8], xmm1
0x1800aeb2f  mov     rbx, rcx
0x1800aeb32  mov     [rbp+var_18.Buffer], 0
0x1800aeb3a  mov     [rbp+UnicodeString.Buffer], 0
0x1800aeb42  call    cs:__imp_RtlSubAuthorityCountSid
0x1800aeb48  movzx   r15d, byte ptr [rax]
0x1800aeb4c  cmp     r15b, 1
0x1800aeb50  jnb     short loc_1800AEB7B
0x1800aeb52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeb59  mov     ebx, 0C0000078h
0x1800aeb5e  test    dword ptr [rcx+44h], 20000h
0x1800aeb65  jz      loc_1800AEDEB
0x1800aeb6b  mov     edx, 4Ah ; 'J'
0x1800aeb70  mov     r9d, 0C0000078h
0x1800aeb76  jmp     loc_1800AEDD7
0x1800aeb7b  mov     rcx, rbx; Sid
0x1800aeb7e  call    cs:__imp_RtlLengthSid
0x1800aeb84  mov     edx, eax; uBytes
0x1800aeb86  mov     ecx, 40h ; '@'; uFlags
0x1800aeb8b  call    cs:__imp_LocalAlloc
0x1800aeb91  mov     r14, rax
0x1800aeb94  test    rax, rax
0x1800aeb97  jnz     short loc_1800AEBC0
0x1800aeb99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeba0  mov     ebx, 0C000009Ah
0x1800aeba5  test    dword ptr [rcx+44h], 20000h
0x1800aebac  jz      loc_1800AEDEB
0x1800aebb2  lea     edx, [rax+4Bh]
0x1800aebb5  mov     r9d, 0C000009Ah
0x1800aebbb  jmp     loc_1800AEDD7
0x1800aebc0  mov     rcx, rbx; Sid
0x1800aebc3  call    cs:__imp_RtlLengthSid
0x1800aebc9  mov     r8, rbx; SourceSid
0x1800aebcc  mov     rdx, r14; DestinationSid
0x1800aebcf  mov     ecx, eax; DestinationSidLength
0x1800aebd1  call    cs:__imp_RtlCopySid
0x1800aebd7  mov     rcx, r14; Sid
0x1800aebda  call    cs:__imp_RtlSubAuthorityCountSid
0x1800aebe0  lea     ecx, [r15-1]
0x1800aebe4  lea     edx, [r15-1]; SubAuthority
0x1800aebe8  mov     [rax], cl
0x1800aebea  mov     rcx, rbx; Sid
0x1800aebed  call    cs:__imp_RtlSubAuthoritySid
0x1800aebf3  mov     r8b, 1; AllocateDestinationString
0x1800aebf6  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800aebfa  mov     rdx, r14; Sid
0x1800aebfd  mov     r15d, [rax]
0x1800aec00  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800aec06  mov     ebx, eax
0x1800aec08  test    eax, eax
0x1800aec0a  jns     short loc_1800AEC16
0x1800aec0c  mov     [rbp+UnicodeString.Buffer], 0
0x1800aec14  jmp     short loc_1800AEC30
0x1800aec16  lea     rax, [rbp+var_18]
0x1800aec1a  mov     r9b, 1; unsigned __int8
0x1800aec1d  mov     ecx, r15d; Value
0x1800aec20  mov     [rsp+58h+var_38], rax; struct _UNICODE_STRING *
0x1800aec25  call    ?SampRtlConvertUlongToUnicodeString@@YAJKKKEPEAU_UNICODE_STRING@@@Z; SampRtlConvertUlongToUnicodeString(ulong,ulong,ulong,uchar,_UNICODE_STRING *)
0x1800aec2a  mov     ebx, eax
0x1800aec2c  test    eax, eax
0x1800aec2e  jns     short loc_1800AEC67
0x1800aec30  mov     rcx, [rsi+8]; hMem
0x1800aec34  test    rcx, rcx
0x1800aec37  jz      short loc_1800AEC47
0x1800aec39  call    cs:__imp_LocalFree
0x1800aec3f  mov     qword ptr [rsi+8], 0
0x1800aec47  mov     rcx, [rdi+8]; hMem
0x1800aec4b  test    rcx, rcx
0x1800aec4e  jz      loc_1800AEDA5
0x1800aec54  call    cs:__imp_LocalFree
0x1800aec5a  mov     qword ptr [rdi+8], 0
0x1800aec62  jmp     loc_1800AEDA5
0x1800aec67  mov     eax, cs:?SampTransactionDomainIndexGlobal@@3KA; ulong SampTransactionDomainIndexGlobal
0x1800aec6d  movzx   edx, cs:?SampBackSlash@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampBackSlash ...
0x1800aec74  shl     dx, 2
0x1800aec78  add     dx, 12h
0x1800aec7c  imul    rcx, rax, 550h
0x1800aec83  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800aec8a  add     dx, [rcx+rax+20h]
0x1800aec8f  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aec92  add     dx, cs:?SampNameDomainAliasesMembers@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampNameDomainAliasesMembers ...
0x1800aec99  add     dx, cs:?SampNameDomainAliases@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampNameDomainAliases ...
0x1800aeca0  add     dx, cs:?SampNameDomains@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampNameDomains ...
0x1800aeca7  add     dx, [rbp+UnicodeString.Length]; unsigned __int16
0x1800aecab  lea     r15d, [rdx+6]
0x1800aecaf  add     r15w, cs:?SampBackSlash@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING SampBackSlash ...
0x1800aecb7  add     r15w, [rbp+var_18.Length]
0x1800aecbc  call    ?SampInitUnicodeString@@YAJPEAU_UNICODE_STRING@@G@Z; SampInitUnicodeString(_UNICODE_STRING *,ushort)
0x1800aecc1  mov     ebx, eax
0x1800aecc3  test    eax, eax
0x1800aecc5  js      loc_1800AED9B
0x1800aeccb  movzx   edx, r15w; unsigned __int16
0x1800aeccf  mov     rcx, rsi; struct _UNICODE_STRING *
0x1800aecd2  call    ?SampInitUnicodeString@@YAJPEAU_UNICODE_STRING@@G@Z; SampInitUnicodeString(_UNICODE_STRING *,ushort)
0x1800aecd7  mov     ebx, eax
0x1800aecd9  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aecdc  test    eax, eax
0x1800aecde  jns     short loc_1800AECEA
0x1800aece0  call    SampFreeUnicodeString
0x1800aece5  jmp     loc_1800AED9B
0x1800aecea  lea     rdx, ?SampNameDomains@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800aecf1  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aecf6  lea     rbx, ?SampBackSlash@@3U_UNICODE_STRING@@A; _UNICODE_STRING SampBackSlash
0x1800aecfd  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aed00  mov     rdx, rbx; struct _UNICODE_STRING *
0x1800aed03  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed08  mov     eax, cs:?SampTransactionDomainIndexGlobal@@3KA; ulong SampTransactionDomainIndexGlobal
0x1800aed0e  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800aed15  imul    rcx, rax, 550h
0x1800aed1c  add     rdx, 20h ; ' '
0x1800aed20  add     rdx, rcx; struct _UNICODE_STRING *
0x1800aed23  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aed26  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed2b  mov     rdx, rbx; struct _UNICODE_STRING *
0x1800aed2e  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aed31  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed36  lea     rdx, ?SampNameDomainAliases@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800aed3d  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aed40  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed45  mov     rdx, rbx; struct _UNICODE_STRING *
0x1800aed48  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aed4b  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed50  lea     rdx, ?SampNameDomainAliasesMembers@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800aed57  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aed5a  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed5f  mov     rdx, rbx; struct _UNICODE_STRING *
0x1800aed62  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aed65  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed6a  lea     rdx, [rbp+UnicodeString]; struct _UNICODE_STRING *
0x1800aed6e  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800aed71  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed76  mov     rdx, rdi; SourceString
0x1800aed79  mov     rcx, rsi; DestinationString
0x1800aed7c  call    cs:__imp_RtlCopyUnicodeString
0x1800aed82  mov     rdx, rbx; struct _UNICODE_STRING *
0x1800aed85  mov     rcx, rsi; struct _UNICODE_STRING *
0x1800aed88  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed8d  lea     rdx, [rbp+var_18]; struct _UNICODE_STRING *
0x1800aed91  mov     rcx, rsi; struct _UNICODE_STRING *
0x1800aed94  call    ?SampAppendUnicodeString@@YAJPEAU_UNICODE_STRING@@0@Z; SampAppendUnicodeString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800aed99  mov     ebx, eax
0x1800aed9b  mov     rcx, [rbp+var_18.Buffer]; hMem
0x1800aed9f  call    cs:__imp_LocalFree
0x1800aeda5  mov     rcx, r14; hMem
0x1800aeda8  call    cs:__imp_LocalFree
0x1800aedae  cmp     [rbp+UnicodeString.Buffer], 0
0x1800aedb3  jz      short loc_1800AEDBF
0x1800aedb5  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800aedb9  call    cs:__imp_RtlFreeUnicodeString
0x1800aedbf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aedc6  test    dword ptr [rcx+44h], 20000h
0x1800aedcd  jz      short loc_1800AEDEB
0x1800aedcf  mov     edx, 4Ch ; 'L'
0x1800aedd4  mov     r9d, ebx
0x1800aedd7  mov     rcx, [rcx+38h]
0x1800aeddb  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800aede2  mov     dword ptr [rsp+58h+var_38], ebx
0x1800aede6  call    WPP_SF_Dd
0x1800aedeb  mov     eax, ebx
0x1800aeded  add     rsp, 58h
0x1800aedf1  pop     r15
0x1800aedf3  pop     r14
0x1800aedf5  pop     rdi
0x1800aedf6  pop     rsi
0x1800aedf7  pop     rbx
0x1800aedf8  pop     rbp
0x1800aedf9  retn
```
