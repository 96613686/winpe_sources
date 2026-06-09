# TSGetRedirectedLogonSid(void *,void * *)

- ea: `0x18001acf0`
- end: `0x18001ae3c`
- name: `?TSGetRedirectedLogonSid@@YAJPEAXPEAPEAX@Z`
- size: `332`
- prototype: `__int64 __fastcall(_BYTE *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800032c0`
- `0x180005ed0`
- `0x18001acf0`
- `0x18001b77c`
- `0x18001d010`

## import_xrefs

- `SspiCli!QueryContextAttributesW` at `0x18001ad59`
- `SspiCli!QueryContextAttributesW` at `0x18001ad59`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001ae09`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001ae09`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001add8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001add8`
- `ntdll!NtQueryInformationToken` at `0x18001ad82`
- `ntdll!NtQueryInformationToken` at `0x18001adc9`
- `ntdll!NtQueryInformationToken` at `0x18001ad82`
- `ntdll!NtQueryInformationToken` at `0x18001adc9`

## pseudocode

```c
__int64 __fastcall TSGetRedirectedLogonSid(_BYTE *a1, void **a2)
{
  struct _TS_CONTEXT *v4; // rcx
  SECURITY_STATUS v5; // ebx
  PSID *v6; // rdi
  __int64 LengthSid; // rbx
  void *v8; // rax
  ULONG TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE pBuffer; // [rsp+48h] [rbp+10h] BYREF

  pBuffer = 0;
  TokenInformationLength = 0;
  *a2 = 0;
  if ( a1 && (v4 = *(struct _TS_CONTEXT **)a1) != 0 && TSContextIsValid(v4) && a1[24] )
  {
    v5 = QueryContextAttributesW((PCtxtHandle)(*(_QWORD *)a1 + 24LL), 0x12u, &pBuffer);
    if ( v5 >= 0 )
    {
      v5 = NtQueryInformationToken(pBuffer, TokenUser, 0, 0, &TokenInformationLength);
      if ( v5 == -1073741789 )
      {
        v6 = (PSID *)TSAllocate(TokenInformationLength);
        if ( v6 )
        {
          v5 = NtQueryInformationToken(pBuffer, TokenUser, v6, TokenInformationLength, &TokenInformationLength);
          if ( v5 >= 0 )
          {
            LengthSid = GetLengthSid(*v6);
            v8 = (void *)((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocateLsaHeap)(LengthSid);
            *a2 = v8;
            if ( v8 )
              v5 = !CopySid(LengthSid, v8, *v6) ? 0xC00000E5 : 0;
            else
              v5 = -1073741801;
          }
          TSFree(v6);
        }
        else
        {
          return (unsigned int)-1073741801;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001acf0  mov     rax, rsp
0x18001acf3  mov     [rax+18h], rbx
0x18001acf7  mov     [rax+20h], rsi
0x18001acfb  push    rdi
0x18001acfc  sub     rsp, 30h
0x18001ad00  mov     qword ptr [rax+10h], 0
0x18001ad08  mov     rsi, rdx
0x18001ad0b  mov     dword ptr [rax+8], 0
0x18001ad12  mov     rbx, rcx
0x18001ad15  mov     qword ptr [rdx], 0
0x18001ad1c  test    rcx, rcx
0x18001ad1f  jz      loc_18001AE25
0x18001ad25  mov     rcx, [rcx]; struct _TS_CONTEXT *
0x18001ad28  test    rcx, rcx
0x18001ad2b  jz      loc_18001AE25
0x18001ad31  call    ?TSContextIsValid@@YAEPEAU_TS_CONTEXT@@@Z; TSContextIsValid(_TS_CONTEXT *)
0x18001ad36  test    al, al
0x18001ad38  jz      loc_18001AE25
0x18001ad3e  cmp     byte ptr [rbx+18h], 0
0x18001ad42  jz      loc_18001AE25
0x18001ad48  mov     rcx, [rbx]
0x18001ad4b  lea     r8, [rsp+38h+pBuffer]; pBuffer
0x18001ad50  add     rcx, 18h; phContext
0x18001ad54  mov     edx, 12h; ulAttribute
0x18001ad59  call    cs:__imp_QueryContextAttributesW
0x18001ad5f  mov     ebx, eax
0x18001ad61  test    eax, eax
0x18001ad63  js      loc_18001AE2A
0x18001ad69  mov     rcx, [rsp+38h+pBuffer]; TokenHandle
0x18001ad6e  lea     rax, [rsp+38h+TokenInformationLength]
0x18001ad73  xor     r9d, r9d; TokenInformationLength
0x18001ad76  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001ad7b  xor     r8d, r8d; TokenInformation
0x18001ad7e  lea     edx, [r9+1]; TokenInformationClass
0x18001ad82  call    cs:__imp_NtQueryInformationToken
0x18001ad88  mov     ebx, eax
0x18001ad8a  cmp     eax, 0C0000023h
0x18001ad8f  jnz     loc_18001AE2A
0x18001ad95  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x18001ad99  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x18001ad9e  mov     rdi, rax
0x18001ada1  test    rax, rax
0x18001ada4  jnz     short loc_18001ADAD
0x18001ada6  mov     ebx, 0C0000017h
0x18001adab  jmp     short loc_18001AE2A
0x18001adad  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18001adb2  lea     rax, [rsp+38h+TokenInformationLength]
0x18001adb7  mov     rcx, [rsp+38h+pBuffer]; TokenHandle
0x18001adbc  mov     r8, rdi; TokenInformation
0x18001adbf  mov     edx, 1; TokenInformationClass
0x18001adc4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001adc9  call    cs:__imp_NtQueryInformationToken
0x18001adcf  mov     ebx, eax
0x18001add1  test    eax, eax
0x18001add3  js      short loc_18001AE1B
0x18001add5  mov     rcx, [rdi]; pSid
0x18001add8  call    cs:__imp_GetLengthSid
0x18001adde  mov     rcx, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18001ade5  mov     ebx, eax
0x18001ade7  mov     rax, [rcx+28h]
0x18001adeb  mov     ecx, ebx
0x18001aded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adf2  mov     [rsi], rax
0x18001adf5  test    rax, rax
0x18001adf8  jnz     short loc_18001AE01
0x18001adfa  mov     ebx, 0C0000017h
0x18001adff  jmp     short loc_18001AE1B
0x18001ae01  mov     r8, [rdi]; pSourceSid
0x18001ae04  mov     rdx, rax; pDestinationSid
0x18001ae07  mov     ecx, ebx; nDestinationSidLength
0x18001ae09  call    cs:__imp_CopySid
0x18001ae0f  neg     eax
0x18001ae11  sbb     ebx, ebx
0x18001ae13  not     ebx
0x18001ae15  and     ebx, 0C00000E5h
0x18001ae1b  mov     rcx, rdi; void *
0x18001ae1e  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x18001ae23  jmp     short loc_18001AE2A
0x18001ae25  mov     ebx, 0C000000Dh
0x18001ae2a  mov     rsi, [rsp+38h+arg_18]
0x18001ae2f  mov     eax, ebx
0x18001ae31  mov     rbx, [rsp+38h+arg_10]
0x18001ae36  add     rsp, 30h
0x18001ae3a  pop     rdi
0x18001ae3b  retn
```
