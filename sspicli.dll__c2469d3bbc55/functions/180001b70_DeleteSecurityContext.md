# DeleteSecurityContext

- ea: `0x180001b70`
- end: `0x180001cca`
- name: `DeleteSecurityContext`
- size: `346`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800199c0`
- `0x180019eb0`
- `0x18001a060`

## callees

- `0x180001b70`
- `0x180001f90`
- `0x1800195c4`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180001c1e`
- `ntdll!RtlLeaveCriticalSection` at `0x180001ca6`
- `ntdll!RtlLeaveCriticalSection` at `0x180001c1e`
- `ntdll!RtlLeaveCriticalSection` at `0x180001ca6`
- `ntdll!RtlEnterCriticalSection` at `0x180001bfe`
- `ntdll!RtlEnterCriticalSection` at `0x180001bfe`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001bd4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001bd4`

## pseudocode

```c
SECURITY_STATUS __stdcall DeleteSecurityContext(PCtxtHandle phContext)
{
  struct _DLL_SECURITY_PACKAGE *v2; // rax
  struct _DLL_SECURITY_PACKAGE *v3; // rdi
  SECURITY_STATUS v4; // esi
  struct _SASL_CONTEXT *v5; // rcx
  struct _SASL_CONTEXT *v7; // rdi
  __int64 v8; // rax
  struct _SASL_CONTEXT **v9; // rdx
  struct _SecHandle v10; // [rsp+20h] [rbp-28h] BYREF

  v10 = 0;
  if ( phContext && phContext->dwLower <= (unsigned int)SecLsaPackageCount )
    return 0;
  v2 = SecpValidateHandle(1, phContext, &v10);
  v3 = v2;
  if ( !v2 )
    return -2146893055;
  if ( phContext->dwUpper != -2 )
  {
    TlsSetValue(SecTlsPackage, v2);
    v4 = (*(__int64 (__fastcall **)(struct _SecHandle *))(*((_QWORD *)v3 + 22) + 72LL))(&v10);
    if ( (*((_BYTE *)v3 + 36) & 8) != 0 )
    {
      RtlEnterCriticalSection(&SaslLock);
      v5 = SaslContextList;
      if ( SaslContextList == (struct _SASL_CONTEXT *)&SaslContextList )
        goto LABEL_6;
      do
      {
        if ( *((_QWORD *)v5 + 3) == phContext->dwUpper )
        {
          v7 = v5;
          if ( *((_QWORD *)v5 + 2) == phContext->dwLower )
            break;
        }
        v5 = *(struct _SASL_CONTEXT **)v5;
        v7 = 0;
      }
      while ( v5 != (struct _SASL_CONTEXT *)&SaslContextList );
      if ( !v7 )
      {
LABEL_6:
        RtlLeaveCriticalSection(&SaslLock);
      }
      else
      {
        v8 = *(_QWORD *)v7;
        if ( *(struct _SASL_CONTEXT **)(*(_QWORD *)v7 + 8LL) != v7
          || (v9 = (struct _SASL_CONTEXT **)*((_QWORD *)v7 + 1), *v9 != v7) )
        {
          __fastfail(3u);
        }
        *v9 = (struct _SASL_CONTEXT *)v8;
        *(_QWORD *)(v8 + 8) = v9;
        *(_QWORD *)v7 = 0;
        *((_QWORD *)v7 + 1) = 0;
        RtlLeaveCriticalSection(&SaslLock);
        SaslDeleteContext(v7);
      }
    }
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180001b70  mov     [rsp+arg_8], rbx
0x180001b75  mov     [rsp+arg_10], rsi
0x180001b7a  push    rdi
0x180001b7b  sub     rsp, 40h
0x180001b7f  mov     rax, cs:__security_cookie
0x180001b86  xor     rax, rsp
0x180001b89  mov     [rsp+48h+var_18], rax
0x180001b8e  xorps   xmm0, xmm0
0x180001b91  mov     rbx, rcx
0x180001b94  movups  xmmword ptr [rsp+48h+var_28.dwLower], xmm0
0x180001b99  test    rcx, rcx
0x180001b9c  jnz     loc_180001C43
0x180001ba2  lea     r8, [rsp+48h+var_28]; struct _SecHandle *
0x180001ba7  mov     rdx, rbx; struct _SecHandle *
0x180001baa  mov     ecx, 1; int
0x180001baf  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001bb4  mov     rdi, rax
0x180001bb7  test    rax, rax
0x180001bba  jz      loc_180001CC0
0x180001bc0  cmp     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFEh
0x180001bc5  jz      loc_180001C52
0x180001bcb  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001bd1  mov     rdx, rax; lpTlsValue
0x180001bd4  call    cs:__imp_TlsSetValue
0x180001bda  mov     rax, [rdi+0B0h]
0x180001be1  lea     rcx, [rsp+48h+var_28]
0x180001be6  mov     rax, [rax+48h]
0x180001bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bef  test    byte ptr [rdi+24h], 8
0x180001bf3  mov     esi, eax
0x180001bf5  jz      short loc_180001C24
0x180001bf7  lea     rcx, SaslLock; CriticalSection
0x180001bfe  call    cs:__imp_RtlEnterCriticalSection
0x180001c04  mov     rcx, cs:SaslContextList
0x180001c0b  lea     r8, SaslContextList
0x180001c12  cmp     rcx, r8
0x180001c15  jnz     short loc_180001C56
0x180001c17  lea     rcx, SaslLock; CriticalSection
0x180001c1e  call    cs:__imp_RtlLeaveCriticalSection
0x180001c24  mov     eax, esi
0x180001c26  mov     rcx, [rsp+48h+var_18]
0x180001c2b  xor     rcx, rsp; StackCookie
0x180001c2e  call    __security_check_cookie
0x180001c33  mov     rbx, [rsp+48h+arg_8]
0x180001c38  mov     rsi, [rsp+48h+arg_10]
0x180001c3d  add     rsp, 40h
0x180001c41  pop     rdi
0x180001c42  retn
0x180001c43  mov     eax, cs:SecLsaPackageCount
0x180001c49  cmp     [rcx], rax
0x180001c4c  ja      loc_180001BA2
0x180001c52  xor     eax, eax
0x180001c54  jmp     short loc_180001C26
0x180001c56  mov     rdx, [rbx+8]
0x180001c5a  xor     r9d, r9d
0x180001c5d  cmp     [rcx+18h], rdx
0x180001c61  jnz     short loc_180001C6F
0x180001c63  mov     rax, [rbx]
0x180001c66  mov     rdi, rcx
0x180001c69  cmp     [rcx+10h], rax
0x180001c6d  jz      short loc_180001C7A
0x180001c6f  mov     rcx, [rcx]
0x180001c72  mov     rdi, r9
0x180001c75  cmp     rcx, r8
0x180001c78  jnz     short loc_180001C5D
0x180001c7a  test    rdi, rdi
0x180001c7d  jz      short loc_180001C17
0x180001c7f  mov     rax, [rdi]
0x180001c82  cmp     [rax+8], rdi
0x180001c86  jnz     short loc_180001CB9
0x180001c88  mov     rdx, [rdi+8]
0x180001c8c  cmp     [rdx], rdi
0x180001c8f  jnz     short loc_180001CB9
0x180001c91  mov     [rdx], rax
0x180001c94  lea     rcx, SaslLock; CriticalSection
0x180001c9b  mov     [rax+8], rdx
0x180001c9f  mov     [rdi], r9
0x180001ca2  mov     [rdi+8], r9
0x180001ca6  call    cs:__imp_RtlLeaveCriticalSection
0x180001cac  mov     rcx, rdi; struct _SASL_CONTEXT *
0x180001caf  call    ?SaslDeleteContext@@YAXPEAU_SASL_CONTEXT@@@Z; SaslDeleteContext(_SASL_CONTEXT *)
0x180001cb4  jmp     loc_180001C24
0x180001cb9  mov     ecx, 3
0x180001cbe  int     29h; Win8: RtlFailFast(ecx)
0x180001cc0  mov     esi, 80090301h
0x180001cc5  jmp     loc_180001C24
```
