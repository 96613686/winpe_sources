# CacheDomainAndDnsDomainSids

- ea: `0x18000cbf8`
- end: `0x18000cd59`
- name: `CacheDomainAndDnsDomainSids`
- size: `353`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180004f20`
- `0x180005730`

## callees

- `0x18000cbf8`
- `0x18000cd60`
- `0x18000dbb0`
- `0x18000dc40`
- `0x18004f902`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000cce7`
- `ntdll!RtlLengthSid` at `0x18000cd27`
- `ntdll!RtlLengthSid` at `0x18000cce7`
- `ntdll!RtlLengthSid` at `0x18000cd27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccce`

## pseudocode

```c
char CacheDomainAndDnsDomainSids()
{
  NTSTATUS v1; // eax
  const void **v2; // rbx
  NTSTATUS v3; // eax
  const void **v4; // rdi
  void *v5; // rcx
  ULONG v6; // eax
  void *v7; // rcx
  ULONG v8; // eax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF
  PVOID DomainInfo; // [rsp+78h] [rbp+28h] BYREF
  PVOID hMem; // [rsp+80h] [rbp+30h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  PolicyHandle = 0;
  hMem = 0;
  DomainInfo = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  if ( LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle) >= 0 )
  {
    gbLsaLookupSucceeded = 1;
    v1 = LsaLookupGetDomainInfo(PolicyHandle, DnsDomainInformation, &DomainInfo);
    v2 = (const void **)DomainInfo;
    if ( v1 >= 0 )
    {
      if ( DomainInfo )
      {
        v5 = (void *)*((_QWORD *)DomainInfo + 8);
        if ( v5 )
        {
          v6 = RtlLengthSid(v5);
          memcpy_0(qword_18007C720, v2[8], v6);
          Sid = qword_18007C720;
          gbDnsDomainSidCached = 1;
        }
      }
    }
    else
    {
      gbLsaLookupSucceeded = 0;
    }
    v3 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &hMem);
    v4 = (const void **)hMem;
    if ( v3 >= 0 )
    {
      if ( hMem )
      {
        v7 = (void *)*((_QWORD *)hMem + 2);
        if ( v7 )
        {
          v8 = RtlLengthSid(v7);
          memcpy_0(qword_18007C800, v4[2], v8);
          Src = qword_18007C800;
          gbDomainSidCached = 1;
        }
      }
    }
    else
    {
      gbLsaLookupSucceeded = 0;
    }
    LsaLookupClose(PolicyHandle);
    if ( v4 )
      LocalFree(v4);
    if ( v2 )
      LocalFree(v2);
  }
  return 1;
}

```

## disassembly

```asm
0x18000cbf8  mov     [rsp-18h+arg_18], rbx
0x18000cbfd  push    rbp
0x18000cbfe  push    rdi
0x18000cbff  push    r14
0x18000cc01  mov     rbp, rsp
0x18000cc04  sub     rsp, 50h
0x18000cc08  xor     eax, eax
0x18000cc0a  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000cc12  xorps   xmm0, xmm0
0x18000cc15  mov     qword ptr [rbp+ObjectAttributes.Attributes], rax
0x18000cc19  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x18000cc1d  mov     [rbp+PolicyHandle], rax
0x18000cc21  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x18000cc25  mov     [rbp+hMem], rax
0x18000cc29  lea     edx, [rax+1]; AccessMask
0x18000cc2c  mov     [rbp+DomainInfo], rax
0x18000cc30  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18000cc34  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000cc38  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000cc3d  call    LsaLookupOpenLocalPolicy
0x18000cc42  test    eax, eax
0x18000cc44  jns     short loc_18000CC59
0x18000cc46  mov     rbx, [rsp+50h+arg_18]
0x18000cc4e  mov     al, 1
0x18000cc50  add     rsp, 50h
0x18000cc54  pop     r14
0x18000cc56  pop     rdi
0x18000cc57  pop     rbp
0x18000cc58  retn
0x18000cc59  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000cc5d  lea     r8, [rbp+DomainInfo]; DomainInfo
0x18000cc61  mov     edx, 0Ch; DomainInfoClass
0x18000cc66  mov     cs:gbLsaLookupSucceeded, 1
0x18000cc70  call    LsaLookupGetDomainInfo
0x18000cc75  mov     rbx, [rbp+DomainInfo]
0x18000cc79  test    eax, eax
0x18000cc7b  jns     short loc_18000CCD9
0x18000cc7d  mov     cs:gbLsaLookupSucceeded, 0
0x18000cc87  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000cc8b  lea     r8, [rbp+hMem]; DomainInfo
0x18000cc8f  mov     edx, 5; DomainInfoClass
0x18000cc94  call    LsaLookupGetDomainInfo
0x18000cc99  mov     rdi, [rbp+hMem]
0x18000cc9d  test    eax, eax
0x18000cc9f  jns     short loc_18000CD19
0x18000cca1  mov     cs:gbLsaLookupSucceeded, 0
0x18000ccab  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18000ccaf  call    LsaLookupClose
0x18000ccb4  test    rdi, rdi
0x18000ccb7  jz      short loc_18000CCC2
0x18000ccb9  mov     rcx, rdi; hMem
0x18000ccbc  call    cs:__imp_LocalFree
0x18000ccc2  test    rbx, rbx
0x18000ccc5  jz      loc_18000CC46
0x18000cccb  mov     rcx, rbx; hMem
0x18000ccce  call    cs:__imp_LocalFree
0x18000ccd4  jmp     loc_18000CC46
0x18000ccd9  test    rbx, rbx
0x18000ccdc  jz      short loc_18000CC87
0x18000ccde  mov     rcx, [rbx+40h]; Sid
0x18000cce2  test    rcx, rcx
0x18000cce5  jz      short loc_18000CC87
0x18000cce7  call    cs:__imp_RtlLengthSid
0x18000cced  mov     rdx, [rbx+40h]; Src
0x18000ccf1  lea     rdi, qword_18007C720
0x18000ccf8  mov     r8d, eax; Size
0x18000ccfb  mov     rcx, rdi; void *
0x18000ccfe  call    memcpy_0
0x18000cd03  mov     cs:Sid, rdi
0x18000cd0a  mov     cs:gbDnsDomainSidCached, 1
0x18000cd14  jmp     loc_18000CC87
0x18000cd19  test    rdi, rdi
0x18000cd1c  jz      short loc_18000CCAB
0x18000cd1e  mov     rcx, [rdi+10h]; Sid
0x18000cd22  test    rcx, rcx
0x18000cd25  jz      short loc_18000CCAB
0x18000cd27  call    cs:__imp_RtlLengthSid
0x18000cd2d  mov     rdx, [rdi+10h]; Src
0x18000cd31  lea     r14, qword_18007C800
0x18000cd38  mov     r8d, eax; Size
0x18000cd3b  mov     rcx, r14; void *
0x18000cd3e  call    memcpy_0
0x18000cd43  mov     cs:Src, r14
0x18000cd4a  mov     cs:gbDomainSidCached, 1
0x18000cd54  jmp     loc_18000CCAB
```
