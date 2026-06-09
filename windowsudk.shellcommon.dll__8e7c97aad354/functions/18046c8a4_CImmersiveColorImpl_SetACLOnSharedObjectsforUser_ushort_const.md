# CImmersiveColorImpl::SetACLOnSharedObjectsforUser(ushort const *)

- ea: `0x18046c8a4`
- end: `0x18046c9a9`
- name: `?SetACLOnSharedObjectsforUser@CImmersiveColorImpl@@SAJPEBG@Z`
- size: `261`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18046bee4`

## callees

- `0x18015cb00`
- `0x18033b018`
- `0x180469e00`
- `0x18046c8a4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18046c938`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18046c96e`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18046c938`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18046c96e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046c988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046c988`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18046c912`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18046c912`

## pseudocode

```c
__int64 __fastcall CImmersiveColorImpl::SetACLOnSharedObjectsforUser(const unsigned __int16 *a1)
{
  int Error; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-238h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !g_hColorPreferenceMapping )
    return (unsigned int)-2147024809;
  Error = StringCchPrintfW(StringSecurityDescriptor, 0x104u, L"D:(A;;GA;;;SY)(A;;GA;;;%s)(A;;GR;;;WD)", a1);
  if ( Error >= 0 )
  {
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( SetKernelObjectSecurity(g_hColorPreferenceMapping, 4u, SecurityDescriptor) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
LABEL_13:
          LocalFree(SecurityDescriptor);
          return (unsigned int)Error;
        }
      }
      if ( g_hColorPreferenceMappingMutex )
      {
        if ( SetKernelObjectSecurity(g_hColorPreferenceMappingMutex, 4u, SecurityDescriptor) )
          Error = 0;
        else
          Error = ResultFromKnownLastError();
      }
      goto LABEL_13;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18046c8a4  push    rbx
0x18046c8a6  sub     rsp, 250h
0x18046c8ad  mov     rax, cs:__security_cookie
0x18046c8b4  xor     rax, rsp
0x18046c8b7  mov     [rsp+258h+var_18], rax
0x18046c8bf  mov     rax, cs:?g_hColorPreferenceMapping@@3REAXEA; void * g_hColorPreferenceMapping
0x18046c8c6  test    rax, rax
0x18046c8c9  jnz     short loc_18046C8D5
0x18046c8cb  mov     ebx, 80070057h
0x18046c8d0  jmp     loc_18046C98E
0x18046c8d5  mov     r9, rcx
0x18046c8d8  lea     r8, aDAGaSyAGaSAGrW; "D:(A;;GA;;;SY)(A;;GA;;;%s)(A;;GR;;;WD)"
0x18046c8df  lea     rcx, [rsp+258h+StringSecurityDescriptor]; unsigned __int16 *
0x18046c8e4  mov     edx, 104h; unsigned __int64
0x18046c8e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18046c8ee  mov     ebx, eax
0x18046c8f0  test    eax, eax
0x18046c8f2  js      loc_18046C98E
0x18046c8f8  xor     r9d, r9d; SecurityDescriptorSize
0x18046c8fb  mov     [rsp+258h+SecurityDescriptor], 0
0x18046c904  lea     r8, [rsp+258h+SecurityDescriptor]; SecurityDescriptor
0x18046c909  lea     rcx, [rsp+258h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18046c90e  lea     edx, [r9+1]; StringSDRevision
0x18046c912  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18046c918  test    eax, eax
0x18046c91a  jnz     short loc_18046C927
0x18046c91c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18046c921  mov     ebx, eax
0x18046c923  test    eax, eax
0x18046c925  js      short loc_18046C98E
0x18046c927  mov     r8, [rsp+258h+SecurityDescriptor]; SecurityDescriptor
0x18046c92c  mov     edx, 4; SecurityInformation
0x18046c931  mov     rcx, cs:?g_hColorPreferenceMapping@@3REAXEA; Handle
0x18046c938  call    cs:__imp_SetKernelObjectSecurity
0x18046c93e  test    eax, eax
0x18046c940  jz      short loc_18046C946
0x18046c942  xor     ebx, ebx
0x18046c944  jmp     short loc_18046C951
0x18046c946  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18046c94b  mov     ebx, eax
0x18046c94d  test    eax, eax
0x18046c94f  js      short loc_18046C983
0x18046c951  mov     rax, cs:?g_hColorPreferenceMappingMutex@@3REAXEA; void * g_hColorPreferenceMappingMutex
0x18046c958  test    rax, rax
0x18046c95b  jz      short loc_18046C983
0x18046c95d  mov     r8, [rsp+258h+SecurityDescriptor]; SecurityDescriptor
0x18046c962  mov     edx, 4; SecurityInformation
0x18046c967  mov     rcx, cs:?g_hColorPreferenceMappingMutex@@3REAXEA; Handle
0x18046c96e  call    cs:__imp_SetKernelObjectSecurity
0x18046c974  test    eax, eax
0x18046c976  jz      short loc_18046C97C
0x18046c978  xor     ebx, ebx
0x18046c97a  jmp     short loc_18046C983
0x18046c97c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18046c981  mov     ebx, eax
0x18046c983  mov     rcx, [rsp+258h+SecurityDescriptor]; hMem
0x18046c988  call    cs:__imp_LocalFree
0x18046c98e  mov     eax, ebx
0x18046c990  mov     rcx, [rsp+258h+var_18]
0x18046c998  xor     rcx, rsp; StackCookie
0x18046c99b  call    __security_check_cookie
0x18046c9a0  add     rsp, 250h
0x18046c9a7  pop     rbx
0x18046c9a8  retn
```
