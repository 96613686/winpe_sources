# GenerateStringCapabilityVector(_ISOLATION_CONTAINER *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>> &)

- ea: `0x18001b030`
- end: `0x18001b116`
- name: `?GenerateStringCapabilityVector@@YAJPEAU_ISOLATION_CONTAINER@@AEAV?$ComPtr@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800492d8`

## callees

- `0x18000e110`
- `0x18001b030`
- `0x18001b11c`
- `0x18004834c`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b0b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b0b8`

## string_xrefs

- `0x18001b0e4`: `Call: ConvertSidToStringSid`

## pseudocode

```c
__int64 __fastcall GenerateStringCapabilityVector(__int64 a1, __int64 *a2)
{
  unsigned int v2; // ebx
  unsigned int i; // esi
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD); // rbx
  __int64 v9; // rax
  const unsigned __int16 *v10; // rdx
  signed int LastError; // eax
  LPWSTR StringSid; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v14[32]; // [rsp+28h] [rbp-40h] BYREF

  v2 = 0;
  for ( i = 1; i < *(_DWORD *)(a1 + 32); ++i )
  {
    v6 = *(_QWORD *)(a1 + 24);
    StringSid = 0;
    if ( !ConvertSidToStringSidW(*(PSID *)(v6 + 16LL * i), &StringSid) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v10 = L"Call: ConvertSidToStringSid";
      goto LABEL_10;
    }
    v7 = *a2;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)*a2 + 104LL);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v14, &StringSid);
    v2 = v8(v7, *(_QWORD *)(v9 + 24));
    LocalFree(StringSid);
    if ( (v2 & 0x80000000) != 0 )
    {
      v10 = L"Call: Append";
LABEL_10:
      IsolationApi::TelemetryHelper::LogRestrictedAppContainerCreationFailure(v2, v10);
      return v2;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001b030  mov     [rsp+arg_10], rbx
0x18001b035  mov     [rsp+arg_18], rbp
0x18001b03a  push    rsi
0x18001b03b  push    rdi
0x18001b03c  push    r14
0x18001b03e  sub     rsp, 50h
0x18001b042  mov     rax, cs:__security_cookie
0x18001b049  xor     rax, rsp
0x18001b04c  mov     [rsp+68h+var_20], rax
0x18001b051  xor     ebx, ebx
0x18001b053  mov     r14, rdx
0x18001b056  mov     rbp, rcx
0x18001b059  lea     esi, [rbx+1]
0x18001b05c  cmp     esi, [rbp+20h]
0x18001b05f  jnb     loc_18001B0F2
0x18001b065  mov     rcx, [rbp+18h]
0x18001b069  lea     rdx, [rsp+68h+StringSid]; StringSid
0x18001b06e  mov     eax, esi
0x18001b070  add     rax, rax
0x18001b073  mov     [rsp+68h+StringSid], 0
0x18001b07c  mov     rcx, [rcx+rax*8]; Sid
0x18001b080  call    ConvertSidToStringSidW
0x18001b085  test    eax, eax
0x18001b087  jz      short loc_18001B0CF
0x18001b089  mov     rdi, [r14]
0x18001b08c  lea     rdx, [rsp+68h+StringSid]
0x18001b091  lea     rcx, [rsp+68h+var_40]
0x18001b096  mov     rax, [rdi]
0x18001b099  mov     rbx, [rax+68h]
0x18001b09d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001b0a2  mov     rcx, rdi
0x18001b0a5  mov     rdx, [rax+18h]
0x18001b0a9  mov     rax, rbx
0x18001b0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0b1  mov     rcx, [rsp+68h+StringSid]; hMem
0x18001b0b6  mov     ebx, eax
0x18001b0b8  call    cs:__imp_LocalFree
0x18001b0be  test    ebx, ebx
0x18001b0c0  js      short loc_18001B0C6
0x18001b0c2  inc     esi
0x18001b0c4  jmp     short loc_18001B05C
0x18001b0c6  lea     rdx, aCallAppend; "Call: Append"
0x18001b0cd  jmp     short loc_18001B0EB
0x18001b0cf  call    cs:__imp_GetLastError
0x18001b0d5  mov     ebx, eax
0x18001b0d7  test    eax, eax
0x18001b0d9  jle     short loc_18001B0E4
0x18001b0db  movzx   ebx, ax
0x18001b0de  or      ebx, 80070000h
0x18001b0e4  lea     rdx, aCallConvertsid; "Call: ConvertSidToStringSid"
0x18001b0eb  mov     ecx, ebx; int
0x18001b0ed  call    ?LogRestrictedAppContainerCreationFailure@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogRestrictedAppContainerCreationFailure(long,ushort const *)
0x18001b0f2  mov     eax, ebx
0x18001b0f4  mov     rcx, [rsp+68h+var_20]
0x18001b0f9  xor     rcx, rsp; StackCookie
0x18001b0fc  call    __security_check_cookie
0x18001b101  lea     r11, [rsp+68h+var_18]
0x18001b106  mov     rbx, [r11+30h]
0x18001b10a  mov     rbp, [r11+38h]
0x18001b10e  mov     rsp, r11
0x18001b111  pop     r14
0x18001b113  pop     rdi
0x18001b114  pop     rsi
0x18001b115  retn
```
