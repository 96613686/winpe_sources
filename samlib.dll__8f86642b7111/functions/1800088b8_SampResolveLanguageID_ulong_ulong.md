# SampResolveLanguageID(ulong,ulong *)

- ea: `0x1800088b8`
- end: `0x1800089d2`
- name: `?SampResolveLanguageID@@YAHKPEAK@Z`
- size: `282`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008c40`

## callees

- `0x180006ed0`
- `0x1800088b8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800088fc`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18000896b`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800088fc`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18000896b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008938`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008938`
- `ntdll!RtlInitUnicodeString` at `0x18000899b`
- `ntdll!RtlInitUnicodeString` at `0x18000899b`
- `ntdll!RtlUnicodeStringToInteger` at `0x1800089ae`
- `ntdll!RtlUnicodeStringToInteger` at `0x1800089ae`

## pseudocode

```c
__int64 __fastcall SampResolveLanguageID(unsigned int a1, unsigned int *a2)
{
  WCHAR *v4; // rax
  WCHAR *v5; // rbx
  unsigned int v6; // esi
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+58h] [rbp+28h] BYREF
  ULONG pulNumLanguages; // [rsp+60h] [rbp+30h] BYREF
  ULONG Value; // [rsp+68h] [rbp+38h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  Value = 0;
  DestinationString = 0;
  if ( !a2 )
    return 0;
  *a2 = a1;
  if ( !GetSystemPreferredUILanguages(4u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
  {
    if ( SamMuiLogFile )
      fwprintf(SamMuiLogFile, L"Failed to get the buffer size for the System Preferred UI Languages list\n");
    return 0;
  }
  v4 = (WCHAR *)LocalAlloc(0x40u, 2LL * pcchLanguagesBuffer);
  v5 = v4;
  if ( !v4 )
  {
    if ( SamMuiLogFile )
      fwprintf(SamMuiLogFile, L"Failed to allocate buffer for the System Preferred UI Languages list\n");
    return 0;
  }
  v6 = 0;
  if ( GetSystemPreferredUILanguages(4u, &pulNumLanguages, v4, &pcchLanguagesBuffer) )
  {
    if ( pulNumLanguages )
    {
      RtlInitUnicodeString(&DestinationString, v5);
      if ( RtlUnicodeStringToInteger(&DestinationString, 0x10u, &Value) >= 0 )
      {
        v6 = 1;
        *a2 = Value;
      }
    }
  }
  else if ( SamMuiLogFile )
  {
    fwprintf(SamMuiLogFile, L"Failed to get the System Preferred UI Language list\n");
  }
  LocalFree(v5);
  return v6;
}

```

## disassembly

```asm
0x1800088b8  mov     [rsp-18h+arg_0], rbx
0x1800088bd  push    rbp
0x1800088be  push    rsi
0x1800088bf  push    rdi
0x1800088c0  mov     rbp, rsp
0x1800088c3  sub     rsp, 30h
0x1800088c7  mov     [rbp+pulNumLanguages], 0
0x1800088ce  xorps   xmm0, xmm0
0x1800088d1  mov     [rbp+pcchLanguagesBuffer], 0
0x1800088d8  mov     rdi, rdx
0x1800088db  mov     [rbp+Value], 0
0x1800088e2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800088e6  test    rdx, rdx
0x1800088e9  jz      short loc_18000891E
0x1800088eb  mov     [rdx], ecx
0x1800088ed  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800088f1  xor     r8d, r8d; pwszLanguagesBuffer
0x1800088f4  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x1800088f8  lea     ecx, [r8+4]; dwFlags
0x1800088fc  call    cs:__imp_GetSystemPreferredUILanguages
0x180008902  test    eax, eax
0x180008904  jnz     short loc_18000892D
0x180008906  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x18000890d  test    rcx, rcx
0x180008910  jz      short loc_18000891E
0x180008912  lea     rdx, aFailedToGetThe; "Failed to get the buffer size for the S"...
0x180008919  call    fwprintf
0x18000891e  xor     eax, eax
0x180008920  mov     rbx, [rsp+30h+arg_0]
0x180008925  add     rsp, 30h
0x180008929  pop     rdi
0x18000892a  pop     rsi
0x18000892b  pop     rbp
0x18000892c  retn
0x18000892d  mov     edx, [rbp+pcchLanguagesBuffer]
0x180008930  mov     ecx, 40h ; '@'; uFlags
0x180008935  add     rdx, rdx; uBytes
0x180008938  call    cs:__imp_LocalAlloc
0x18000893e  mov     rbx, rax
0x180008941  test    rax, rax
0x180008944  jnz     short loc_18000895B
0x180008946  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; _iobuf * SamMuiLogFile
0x18000894d  test    rcx, rcx
0x180008950  jz      short loc_18000891E
0x180008952  lea     rdx, aFailedToAlloca; "Failed to allocate buffer for the Syste"...
0x180008959  jmp     short loc_180008919
0x18000895b  xor     esi, esi
0x18000895d  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180008961  mov     r8, rbx; pwszLanguagesBuffer
0x180008964  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x180008968  lea     ecx, [rsi+4]; dwFlags
0x18000896b  call    cs:__imp_GetSystemPreferredUILanguages
0x180008971  test    eax, eax
0x180008973  jnz     short loc_18000898F
0x180008975  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x18000897c  test    rcx, rcx
0x18000897f  jz      short loc_1800089C2
0x180008981  lea     rdx, aFailedToGetThe_0; "Failed to get the System Preferred UI L"...
0x180008988  call    fwprintf
0x18000898d  jmp     short loc_1800089C2
0x18000898f  cmp     [rbp+pulNumLanguages], esi
0x180008992  jbe     short loc_1800089C2
0x180008994  mov     rdx, rbx; SourceString
0x180008997  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000899b  call    cs:__imp_RtlInitUnicodeString
0x1800089a1  lea     r8, [rbp+Value]; Value
0x1800089a5  mov     edx, 10h; Base
0x1800089aa  lea     rcx, [rbp+DestinationString]; String
0x1800089ae  call    cs:__imp_RtlUnicodeStringToInteger
0x1800089b4  test    eax, eax
0x1800089b6  js      short loc_1800089C2
0x1800089b8  mov     eax, [rbp+Value]
0x1800089bb  mov     esi, 1
0x1800089c0  mov     [rdi], eax
0x1800089c2  mov     rcx, rbx; hMem
0x1800089c5  call    cs:__imp_LocalFree
0x1800089cb  mov     eax, esi
0x1800089cd  jmp     loc_180008920
```
