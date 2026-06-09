# IsDomainJoined

- ea: `0x140037060`
- end: `0x1400371c0`
- name: `IsDomainJoined`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140036ffc`

## callees

- `0x140037060`
- `0x1400371c8`
- `0x140053720`
- `0x1400967ac`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1400370ca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1400370ca`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140037137`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140037184`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140037137`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x140037184`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x14003715f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1400371ab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x14003715f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1400371ab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1400370f4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1400370f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool IsDomainJoined()
{
  NTSTATUS v0; // eax
  unsigned int v1; // r8d
  NTSTATUS v2; // eax
  unsigned int v3; // r8d
  PVOID v4; // rcx
  bool v5; // bl
  PVOID v7; // rcx
  PVOID Buffer; // [rsp+20h] [rbp-68h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+28h] [rbp-60h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES v10; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v11[4]; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v11[2] = 1;
  v11[0] = 12;
  v11[1] = 2;
  memset(&v10, 0, 40);
  v10.SecurityQualityOfService = v11;
  PolicyHandle = 0;
  v0 = LsaOpenPolicy(0, &v10, 1u, &PolicyHandle);
  if ( v0 < 0 )
  {
    wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x3B, v1, (const char *)(unsigned int)v0, (int)Buffer);
    if ( PolicyHandle )
      LsaClose(PolicyHandle);
    return 0;
  }
  else
  {
    Buffer = 0;
    v2 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( v2 < 0 )
    {
      wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x43, v3, (const char *)(unsigned int)v2, (int)Buffer);
      v7 = Buffer;
      Buffer = 0;
      if ( v7 )
        LsaFreeMemory(v7);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&PolicyHandle);
      return 0;
    }
    else
    {
      v4 = Buffer;
      v5 = *((_WORD *)Buffer + 8) || *((_WORD *)Buffer + 16) || *((_QWORD *)Buffer + 8);
      Buffer = 0;
      if ( v4 )
        LsaFreeMemory(v4);
      if ( PolicyHandle )
        LsaClose(PolicyHandle);
      return v5;
    }
  }
}

```

## disassembly

```asm
0x140037060  mov     r11, rsp
0x140037063  mov     [r11+8], rbx
0x140037067  push    rdi
0x140037068  sub     rsp, 80h
0x14003706f  mov     rax, cs:__security_cookie
0x140037076  xor     rax, rsp
0x140037079  mov     [rsp+88h+var_18], rax
0x14003707e  xor     edi, edi
0x140037080  mov     [rsp+88h+var_20], 1
0x140037088  mov     [rsp+88h+var_28], 0Ch
0x140037090  mov     [rsp+88h+var_24], 2
0x140037098  mov     [r11-58h], rdi
0x14003709c  xorps   xmm0, xmm0
0x14003709f  movdqu  [rsp+88h+var_50], xmm0
0x1400370a5  xorps   xmm1, xmm1
0x1400370a8  movdqu  [rsp+88h+var_40], xmm1
0x1400370ae  lea     rax, [r11-28h]
0x1400370b2  mov     [r11-30h], rax
0x1400370b6  mov     [r11-60h], rdi
0x1400370ba  lea     r9, [r11-60h]; PolicyHandle
0x1400370be  mov     r8d, 1; DesiredAccess
0x1400370c4  lea     rdx, [r11-58h]; ObjectAttributes
0x1400370c8  xor     ecx, ecx; SystemName
0x1400370ca  call    cs:__imp_LsaOpenPolicy
0x1400370d0  mov     rcx, [rsp+88h]; this
0x1400370d8  test    eax, eax
0x1400370da  js      loc_14003716C
0x1400370e0  mov     [rsp+88h+Buffer], rdi; int
0x1400370e5  lea     r8, [rsp+88h+Buffer]; Buffer
0x1400370ea  mov     edx, 0Ch; InformationClass
0x1400370ef  mov     rcx, [rsp+88h+PolicyHandle]; PolicyHandle
0x1400370f4  call    cs:__imp_LsaQueryInformationPolicy
0x1400370fa  mov     rcx, [rsp+88h]; this
0x140037102  test    eax, eax
0x140037104  js      loc_14003718F
0x14003710a  mov     rcx, [rsp+88h+Buffer]; Buffer
0x14003710f  cmp     [rcx+10h], di
0x140037113  jnz     short loc_140037168
0x140037115  cmp     [rcx+20h], di
0x140037119  jnz     short loc_140037168
0x14003711b  cmp     [rcx+40h], rdi
0x14003711f  jnz     short loc_140037168
0x140037121  xor     bl, bl
0x140037123  mov     [rsp+88h+Buffer], rdi
0x140037128  test    rcx, rcx
0x14003712b  jnz     short loc_14003715F
0x14003712d  mov     rcx, [rsp+88h+PolicyHandle]; ObjectHandle
0x140037132  test    rcx, rcx
0x140037135  jz      short loc_14003713E
0x140037137  call    cs:__imp_LsaClose
0x14003713d  nop
0x14003713e  movzx   eax, bl
0x140037141  mov     rcx, [rsp+88h+var_18]
0x140037146  xor     rcx, rsp; StackCookie
0x140037149  call    __security_check_cookie
0x14003714e  mov     rbx, [rsp+88h+arg_0]
0x140037156  add     rsp, 80h
0x14003715d  pop     rdi
0x14003715e  retn
0x14003715f  call    cs:__imp_LsaFreeMemory
0x140037165  nop
0x140037166  jmp     short loc_14003712D
0x140037168  mov     bl, 1
0x14003716a  jmp     short loc_140037123
0x14003716c  mov     r9d, eax; char *
0x14003716f  mov     edx, 3Bh ; ';'; void *
0x140037174  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x140037179  nop
0x14003717a  mov     rcx, [rsp+88h+PolicyHandle]; ObjectHandle
0x14003717f  test    rcx, rcx
0x140037182  jz      short loc_14003718B
0x140037184  call    cs:__imp_LsaClose
0x14003718a  nop
0x14003718b  xor     al, al
0x14003718d  jmp     short loc_140037141
0x14003718f  mov     r9d, eax; char *
0x140037192  mov     edx, 43h ; 'C'; void *
0x140037197  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x14003719c  mov     rcx, [rsp+88h+Buffer]; Buffer
0x1400371a1  mov     [rsp+88h+Buffer], rdi
0x1400371a6  test    rcx, rcx
0x1400371a9  jz      short loc_1400371B2
0x1400371ab  call    cs:__imp_LsaFreeMemory
0x1400371b1  nop
0x1400371b2  lea     rcx, [rsp+88h+PolicyHandle]
0x1400371b7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1400371bc  xor     al, al
0x1400371be  jmp     short loc_140037141
```
