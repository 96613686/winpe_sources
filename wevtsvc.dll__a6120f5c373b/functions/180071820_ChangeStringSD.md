# ChangeStringSD

- ea: `0x180071820`
- end: `0x18007196d`
- name: `ChangeStringSD`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004c74`

## callees

- `0x180004a3c`
- `0x18003d2f8`
- `0x180047fd8`
- `0x180071820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800718e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800718e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071935`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007189c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800718d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007189c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800718d5`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180071857`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180071857`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180071848`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180071848`

## pseudocode

```c
__int64 __fastcall ChangeStringSD(__int64 a1, LPCWSTR *a2)
{
  void *v4; // rcx
  PSECURITY_DESCRIPTOR v5; // rax
  char LastError; // al
  char v8; // al
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp+10h] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(*a2, 1u, &SecurityDescriptor, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids,
        (unsigned int)*a2,
        LastError);
    }
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return 3221225506LL;
  }
  if ( !IsValidSecurityDescriptor(SecurityDescriptor) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids,
        (unsigned int)*a2,
        v8);
    }
    tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&SecurityDescriptor);
    return 3221225506LL;
  }
  v4 = *(void **)(a1 + 8);
  v5 = SecurityDescriptor;
  SecurityDescriptor = 0;
  *(_QWORD *)(a1 + 8) = v5;
  if ( v4 )
    LocalFree(v4);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a1 + 16, a2);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x180071820  mov     [rsp+arg_0], rbx
0x180071825  push    rdi
0x180071826  sub     rsp, 30h
0x18007182a  mov     rdi, rdx
0x18007182d  mov     [rsp+38h+SecurityDescriptor], 0
0x180071836  xor     r9d, r9d; SecurityDescriptorSize
0x180071839  lea     r8, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x18007183e  mov     rbx, rcx
0x180071841  mov     rcx, [rdi]; StringSecurityDescriptor
0x180071844  lea     edx, [r9+1]; StringSDRevision
0x180071848  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18007184e  test    eax, eax
0x180071850  jz      short loc_1800718AF
0x180071852  mov     rcx, [rsp+38h+SecurityDescriptor]; pSecurityDescriptor
0x180071857  call    cs:__imp_IsValidSecurityDescriptor
0x18007185d  test    eax, eax
0x18007185f  jz      loc_180071913
0x180071865  mov     rcx, [rbx+8]; hMem
0x180071869  mov     rax, [rsp+38h+SecurityDescriptor]
0x18007186e  mov     [rsp+38h+SecurityDescriptor], 0
0x180071877  mov     [rbx+8], rax
0x18007187b  test    rcx, rcx
0x18007187e  jz      short loc_180071886
0x180071880  call    cs:__imp_LocalFree
0x180071886  lea     rcx, [rbx+10h]
0x18007188a  mov     rdx, rdi
0x18007188d  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180071892  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x180071897  test    rcx, rcx
0x18007189a  jz      short loc_1800718A2
0x18007189c  call    cs:__imp_LocalFree
0x1800718a2  xor     eax, eax
0x1800718a4  mov     rbx, [rsp+38h+arg_0]
0x1800718a9  add     rsp, 30h
0x1800718ad  pop     rdi
0x1800718ae  retn
0x1800718af  mov     rax, cs:WPP_GLOBAL_Control
0x1800718b6  lea     rcx, WPP_GLOBAL_Control
0x1800718bd  cmp     rax, rcx
0x1800718c0  jz      short loc_1800718CB
0x1800718c2  test    dword ptr [rax+1Ch], 1000h
0x1800718c9  jnz     short loc_1800718E2
0x1800718cb  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x1800718d0  test    rcx, rcx
0x1800718d3  jz      short loc_1800718DB
0x1800718d5  call    cs:__imp_LocalFree
0x1800718db  mov     eax, 0C0000022h
0x1800718e0  jmp     short loc_1800718A4
0x1800718e2  cmp     byte ptr [rax+19h], 2
0x1800718e6  jb      short loc_1800718CB
0x1800718e8  call    cs:__imp_GetLastError
0x1800718ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800718f5  lea     r8, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids
0x1800718fc  mov     r9, [rdi]
0x1800718ff  mov     edx, 0Ah
0x180071904  mov     [rsp+38h+var_18], eax
0x180071908  mov     rcx, [rcx+10h]
0x18007190c  call    WPP_SF_Sd
0x180071911  jmp     short loc_1800718CB
0x180071913  mov     rax, cs:WPP_GLOBAL_Control
0x18007191a  lea     rcx, WPP_GLOBAL_Control
0x180071921  cmp     rax, rcx
0x180071924  jz      short loc_18007195E
0x180071926  test    dword ptr [rax+1Ch], 1000h
0x18007192d  jz      short loc_18007195E
0x18007192f  cmp     byte ptr [rax+19h], 2
0x180071933  jb      short loc_18007195E
0x180071935  call    cs:__imp_GetLastError
0x18007193b  mov     rcx, cs:WPP_GLOBAL_Control
0x180071942  lea     r8, WPP_ea75b5403a3133fdaefc7675f4848d19_Traceguids
0x180071949  mov     r9, [rdi]
0x18007194c  mov     edx, 0Bh
0x180071951  mov     [rsp+38h+var_18], eax
0x180071955  mov     rcx, [rcx+10h]
0x180071959  call    WPP_SF_Sd
0x18007195e  lea     rcx, [rsp+38h+SecurityDescriptor]
0x180071963  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(void)
0x180071968  jmp     loc_1800718DB
```
