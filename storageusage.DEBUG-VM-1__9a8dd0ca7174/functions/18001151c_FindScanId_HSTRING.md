# FindScanId(HSTRING__ *)

- ea: `0x18001151c`
- end: `0x1800115fa`
- name: `?FindScanId@@YA?AW4SCAN_ID@@PEAUHSTRING__@@@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014550`

## callees

- `0x1800050f0`
- `0x180011438`
- `0x18001151c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800115c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800115da`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800115c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800115da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180011598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180011598`

## pseudocode

```c
__int64 __fastcall FindScanId(HSTRING a1)
{
  int i; // ebx
  unsigned __int64 v3; // r9
  const WCHAR *v4; // rdx
  HRESULT v5; // eax
  INT32 result; // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-50h] BYREF
  HSTRING string2; // [rsp+40h] [rbp-38h]

  for ( i = 0; i < 19; ++i )
  {
    v3 = -1;
    string2 = 0;
    v4 = *(const WCHAR **)(STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 72LL * i + 8);
    do
      ++v3;
    while ( v4[v3] );
    if ( v3 > 0xFFFFFFFF || (int)v3 + 1 < (unsigned int)v3 )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v4, v3 + 1, v3);
    result = 0;
    v5 = WindowsCompareStringOrdinal(a1, string2, &result);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      __debugbreak();
    }
    if ( !result )
      return *(unsigned int *)(STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings + 72LL * i);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18001151c  push    rbx
0x18001151e  push    rbp
0x18001151f  push    rsi
0x180011520  push    rdi
0x180011521  sub     rsp, 58h
0x180011525  mov     rax, cs:__security_cookie
0x18001152c  xor     rax, rsp
0x18001152f  mov     [rsp+78h+var_30], rax
0x180011534  xor     ebp, ebp
0x180011536  mov     rsi, rcx
0x180011539  mov     ebx, ebp
0x18001153b  cmp     ebx, 13h
0x18001153e  jge     loc_1800115E1
0x180011544  movsxd  rax, ebx
0x180011547  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001154b  mov     [rsp+78h+string2], rbp
0x180011550  lea     rdi, [rax+rax*8]
0x180011554  mov     rax, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x18001155b  mov     rdx, [rax+rdi*8+8]; sourceString
0x180011560  inc     r9; unsigned int
0x180011563  cmp     [rdx+r9*2], bp
0x180011568  jnz     short loc_180011560
0x18001156a  mov     eax, 0FFFFFFFFh
0x18001156f  cmp     r9, rax
0x180011572  ja      short loc_1800115CB
0x180011574  lea     r8d, [r9+1]; unsigned int
0x180011578  cmp     r8d, r9d
0x18001157b  jb      short loc_1800115CB
0x18001157d  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x180011582  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011587  mov     rdx, [rsp+78h+string2]; string2
0x18001158c  lea     r8, [rsp+78h+result]; result
0x180011591  mov     rcx, rsi; string1
0x180011594  mov     [rsp+78h+result], ebp
0x180011598  call    cs:__imp_WindowsCompareStringOrdinal
0x18001159e  test    eax, eax
0x1800115a0  js      short loc_1800115B8
0x1800115a2  cmp     [rsp+78h+result], ebp
0x1800115a6  jz      short loc_1800115AC
0x1800115a8  inc     ebx
0x1800115aa  jmp     short loc_18001153B
0x1800115ac  mov     rax, qword ptr cs:?HardcodedDefaultSettings@STORAGE_USAGE_SCAN_CONFIG@@2V?$vector@VSTORAGE_USAGE_SCAN_CONFIG@@V?$allocator@VSTORAGE_USAGE_SCAN_CONFIG@@@std@@@std@@A; std::vector<STORAGE_USAGE_SCAN_CONFIG> STORAGE_USAGE_SCAN_CONFIG::HardcodedDefaultSettings
0x1800115b3  mov     eax, [rax+rdi*8]
0x1800115b6  jmp     short loc_1800115E4
0x1800115b8  xor     r9d, r9d; lpArguments
0x1800115bb  xor     r8d, r8d; nNumberOfArguments
0x1800115be  mov     ecx, eax; dwExceptionCode
0x1800115c0  lea     edx, [r9+1]; dwExceptionFlags
0x1800115c4  call    cs:__imp_RaiseException
0x1800115ca  int     3; Trap to Debugger
0x1800115cb  xor     r9d, r9d; lpArguments
0x1800115ce  xor     r8d, r8d; nNumberOfArguments
0x1800115d1  mov     ecx, 80070216h; dwExceptionCode
0x1800115d6  lea     edx, [r9+1]; dwExceptionFlags
0x1800115da  call    cs:__imp_RaiseException
0x1800115e0  int     3; Trap to Debugger
0x1800115e1  or      eax, 0FFFFFFFFh
0x1800115e4  mov     rcx, [rsp+78h+var_30]
0x1800115e9  xor     rcx, rsp; StackCookie
0x1800115ec  call    __security_check_cookie
0x1800115f1  add     rsp, 58h
0x1800115f5  pop     rdi
0x1800115f6  pop     rsi
0x1800115f7  pop     rbp
0x1800115f8  pop     rbx
0x1800115f9  retn
```
