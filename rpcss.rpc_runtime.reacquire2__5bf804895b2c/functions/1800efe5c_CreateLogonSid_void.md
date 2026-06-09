# CreateLogonSid(void)

- ea: `0x1800efe5c`
- end: `0x1800eff92`
- name: `?CreateLogonSid@@YAPEAXXZ`
- size: `310`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004dee8`

## callees

- `0x180034260`
- `0x18008172c`
- `0x1800b7ac0`
- `0x1800efe5c`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x1800eff35`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff4f`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff69`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff35`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff4f`
- `ntdll!RtlSubAuthoritySid` at `0x1800eff69`
- `ntdll!RtlInitializeSid` at `0x1800eff24`
- `ntdll!RtlInitializeSid` at `0x1800eff24`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800efe8e`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800efe8e`
- `ntdll!RtlLengthRequiredSid` at `0x1800efef5`
- `ntdll!RtlLengthRequiredSid` at `0x1800efef5`
- `KERNELBASE!LocalAlloc` at `0x1800eff05`
- `KERNELBASE!LocalAlloc` at `0x1800eff05`

## string_xrefs

- `0x1800efedd`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x1800efed6`: `CreateLogonSid`

## pseudocode

```c
void *CreateLogonSid(void)
{
  NTSTATUS v0; // r8d
  ULONG v2; // eax
  HLOCAL v3; // rax
  void *v4; // rbx
  PULONG v5; // rax
  PULONG v6; // rax
  LUID LocallyUniqueId; // [rsp+30h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+38h] [rbp-20h] BYREF

  LocallyUniqueId = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v0 = NtAllocateLocallyUniqueId(&LocallyUniqueId);
  if ( v0 >= 0 )
  {
    v2 = RtlLengthRequiredSid(3u);
    v3 = LocalAlloc(0, v2);
    v4 = v3;
    if ( v3 )
    {
      RtlInitializeSid(v3, &IdentifierAuthority, 3u);
      *RtlSubAuthoritySid(v4, 0) = 5;
      v5 = RtlSubAuthoritySid(v4, 1u);
      *v5 = LocallyUniqueId.HighPart;
      v6 = RtlSubAuthoritySid(v4, 2u);
      *v6 = LocallyUniqueId.LowPart;
    }
    return v4;
  }
  else
  {
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
        (unsigned int)"CreateLogonSid",
        633,
        0,
        (__int64)L"%!STATUS!",
        v0);
    return 0;
  }
}

```

## disassembly

```asm
0x1800efe5c  push    rbx
0x1800efe5e  sub     rsp, 50h
0x1800efe62  mov     rax, cs:__security_cookie
0x1800efe69  xor     rax, rsp
0x1800efe6c  mov     [rsp+58h+var_18], rax
0x1800efe71  lea     rcx, [rsp+58h+LocallyUniqueId]; LocallyUniqueId
0x1800efe76  mov     qword ptr [rsp+58h+LocallyUniqueId.LowPart], 0
0x1800efe7f  mov     dword ptr [rsp+58h+IdentifierAuthority.Value], 0
0x1800efe87  mov     word ptr [rsp+58h+IdentifierAuthority.Value+4], 500h
0x1800efe8e  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800efe95  nop     dword ptr [rax+rax+00h]
0x1800efe9a  mov     r8d, eax
0x1800efe9d  test    eax, eax
0x1800efe9f  jns     short loc_1800EFEF0
0x1800efea1  mov     ecx, cs:dword_1801574B8
0x1800efea7  test    ecx, ecx
0x1800efea9  jnz     short loc_1800EFEBC
0x1800efeab  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800efeb1  jz      short loc_1800EFEE9
0x1800efeb3  call    IsWppLevelEnabled
0x1800efeb8  test    al, al
0x1800efeba  jz      short loc_1800EFEE9
0x1800efebc  mov     [rsp+58h+var_30], r8d
0x1800efec1  lea     rax, aStatus; "%!STATUS!"
0x1800efec8  mov     r8d, 279h
0x1800efece  mov     [rsp+58h+var_38], rax
0x1800efed3  xor     r9d, r9d
0x1800efed6  lea     rdx, aCreatelogonsid; "CreateLogonSid"
0x1800efedd  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800efee4  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800efee9  xor     eax, eax
0x1800efeeb  jmp     loc_1800EFF7E
0x1800efef0  mov     ecx, 3; SubAuthorityCount
0x1800efef5  call    cs:__imp_RtlLengthRequiredSid
0x1800efefc  nop     dword ptr [rax+rax+00h]
0x1800eff01  mov     edx, eax; uBytes
0x1800eff03  xor     ecx, ecx; uFlags
0x1800eff05  call    cs:__imp_LocalAlloc
0x1800eff0c  nop     dword ptr [rax+rax+00h]
0x1800eff11  mov     rbx, rax
0x1800eff14  test    rax, rax
0x1800eff17  jz      short loc_1800EFF7B
0x1800eff19  mov     r8b, 3; SubAuthorityCount
0x1800eff1c  lea     rdx, [rsp+58h+IdentifierAuthority]; IdentifierAuthority
0x1800eff21  mov     rcx, rax; Sid
0x1800eff24  call    cs:__imp_RtlInitializeSid
0x1800eff2b  nop     dword ptr [rax+rax+00h]
0x1800eff30  xor     edx, edx; SubAuthority
0x1800eff32  mov     rcx, rbx; Sid
0x1800eff35  call    cs:__imp_RtlSubAuthoritySid
0x1800eff3c  nop     dword ptr [rax+rax+00h]
0x1800eff41  mov     edx, 1; SubAuthority
0x1800eff46  mov     rcx, rbx; Sid
0x1800eff49  mov     dword ptr [rax], 5
0x1800eff4f  call    cs:__imp_RtlSubAuthoritySid
0x1800eff56  nop     dword ptr [rax+rax+00h]
0x1800eff5b  mov     ecx, [rsp+58h+LocallyUniqueId.HighPart]
0x1800eff5f  mov     edx, 2; SubAuthority
0x1800eff64  mov     [rax], ecx
0x1800eff66  mov     rcx, rbx; Sid
0x1800eff69  call    cs:__imp_RtlSubAuthoritySid
0x1800eff70  nop     dword ptr [rax+rax+00h]
0x1800eff75  mov     ecx, [rsp+58h+LocallyUniqueId.LowPart]
0x1800eff79  mov     [rax], ecx
0x1800eff7b  mov     rax, rbx
0x1800eff7e  mov     rcx, [rsp+58h+var_18]
0x1800eff83  xor     rcx, rsp; StackCookie
0x1800eff86  call    __security_check_cookie
0x1800eff8b  add     rsp, 50h
0x1800eff8f  pop     rbx
0x1800eff90  retn
```
