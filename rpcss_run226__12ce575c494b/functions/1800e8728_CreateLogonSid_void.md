# CreateLogonSid(void)

- ea: `0x1800e8728`
- end: `0x1800e8830`
- name: `?CreateLogonSid@@YAPEAXXZ`
- size: `264`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800501cc`

## callees

- `0x180034540`
- `0x18007e3d4`
- `0x1800b27e0`
- `0x1800e8728`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x1800e87e6`
- `ntdll!RtlSubAuthoritySid` at `0x1800e87fa`
- `ntdll!RtlSubAuthoritySid` at `0x1800e880e`
- `ntdll!RtlSubAuthoritySid` at `0x1800e87e6`
- `ntdll!RtlSubAuthoritySid` at `0x1800e87fa`
- `ntdll!RtlSubAuthoritySid` at `0x1800e880e`
- `ntdll!RtlInitializeSid` at `0x1800e87db`
- `ntdll!RtlInitializeSid` at `0x1800e87db`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800e875a`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800e875a`
- `ntdll!RtlLengthRequiredSid` at `0x1800e87b8`
- `ntdll!RtlLengthRequiredSid` at `0x1800e87b8`
- `KERNELBASE!LocalAlloc` at `0x1800e87c2`
- `KERNELBASE!LocalAlloc` at `0x1800e87c2`

## string_xrefs

- `0x1800e87a3`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x1800e879c`: `CreateLogonSid`

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
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
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
0x1800e8728  push    rbx
0x1800e872a  sub     rsp, 50h
0x1800e872e  mov     rax, cs:__security_cookie
0x1800e8735  xor     rax, rsp
0x1800e8738  mov     [rsp+58h+var_18], rax
0x1800e873d  lea     rcx, [rsp+58h+LocallyUniqueId]; LocallyUniqueId
0x1800e8742  mov     qword ptr [rsp+58h+LocallyUniqueId.LowPart], 0
0x1800e874b  mov     dword ptr [rsp+58h+IdentifierAuthority.Value], 0
0x1800e8753  mov     word ptr [rsp+58h+IdentifierAuthority.Value+4], 500h
0x1800e875a  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800e8760  mov     r8d, eax
0x1800e8763  test    eax, eax
0x1800e8765  jns     short loc_1800E87B3
0x1800e8767  mov     ecx, cs:dword_18014E4B8
0x1800e876d  test    ecx, ecx
0x1800e876f  jnz     short loc_1800E8782
0x1800e8771  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800e8777  jz      short loc_1800E87AF
0x1800e8779  call    IsWppLevelEnabled
0x1800e877e  test    al, al
0x1800e8780  jz      short loc_1800E87AF
0x1800e8782  mov     [rsp+58h+var_30], r8d
0x1800e8787  lea     rax, aStatus; "%!STATUS!"
0x1800e878e  mov     r8d, 279h
0x1800e8794  mov     [rsp+58h+var_38], rax
0x1800e8799  xor     r9d, r9d
0x1800e879c  lea     rdx, aCreatelogonsid; "CreateLogonSid"
0x1800e87a3  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800e87aa  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800e87af  xor     eax, eax
0x1800e87b1  jmp     short loc_1800E881D
0x1800e87b3  mov     ecx, 3; SubAuthorityCount
0x1800e87b8  call    cs:__imp_RtlLengthRequiredSid
0x1800e87be  mov     edx, eax; uBytes
0x1800e87c0  xor     ecx, ecx; uFlags
0x1800e87c2  call    cs:__imp_LocalAlloc
0x1800e87c8  mov     rbx, rax
0x1800e87cb  test    rax, rax
0x1800e87ce  jz      short loc_1800E881A
0x1800e87d0  mov     r8b, 3; SubAuthorityCount
0x1800e87d3  lea     rdx, [rsp+58h+IdentifierAuthority]; IdentifierAuthority
0x1800e87d8  mov     rcx, rax; Sid
0x1800e87db  call    cs:__imp_RtlInitializeSid
0x1800e87e1  xor     edx, edx; SubAuthority
0x1800e87e3  mov     rcx, rbx; Sid
0x1800e87e6  call    cs:__imp_RtlSubAuthoritySid
0x1800e87ec  mov     edx, 1; SubAuthority
0x1800e87f1  mov     rcx, rbx; Sid
0x1800e87f4  mov     dword ptr [rax], 5
0x1800e87fa  call    cs:__imp_RtlSubAuthoritySid
0x1800e8800  mov     ecx, [rsp+58h+LocallyUniqueId.HighPart]
0x1800e8804  mov     edx, 2; SubAuthority
0x1800e8809  mov     [rax], ecx
0x1800e880b  mov     rcx, rbx; Sid
0x1800e880e  call    cs:__imp_RtlSubAuthoritySid
0x1800e8814  mov     ecx, [rsp+58h+LocallyUniqueId.LowPart]
0x1800e8818  mov     [rax], ecx
0x1800e881a  mov     rax, rbx
0x1800e881d  mov     rcx, [rsp+58h+var_18]
0x1800e8822  xor     rcx, rsp; StackCookie
0x1800e8825  call    __security_check_cookie
0x1800e882a  add     rsp, 50h
0x1800e882e  pop     rbx
0x1800e882f  retn
```
