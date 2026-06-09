# CConnectedSearchShellService::GetAcceptLanguage(ushort * *)

- ea: `0x1801a2500`
- end: `0x1801a26b6`
- name: `?GetAcceptLanguage@CConnectedSearchShellService@@UEAAJPEAPEAG@Z`
- size: `438`
- prototype: `__int64 __fastcall(CConnectedSearchShellService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180027ee4`
- `0x180047224`
- `0x180052980`
- `0x1800900a8`
- `0x1800ae2cc`
- `0x1800b5e48`
- `0x1800ec758`
- `0x18013d330`
- `0x1801a2500`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801a265b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801a265b`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1801a2545`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1801a258f`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1801a2545`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1801a258f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a25c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a2619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a25c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a2619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a25fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a25fa`
- `Bcp47Langs!Bcp47Normalize` at `0x1801a25e8`
- `Bcp47Langs!Bcp47Normalize` at `0x1801a25e8`

## pseudocode

```c
__int64 __fastcall CConnectedSearchShellService::GetAcceptLanguage(
        CConnectedSearchShellService *this,
        unsigned __int16 **a2)
{
  __int64 v3; // rcx
  int Error; // edi
  PZZWSTR v5; // rbx
  __int64 v6; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  unsigned __int16 *i; // rsi
  ULONG pcchLanguagesBuffer; // [rsp+20h] [rbp-39h] BYREF
  ULONG pulNumLanguages; // [rsp+24h] [rbp-35h] BYREF
  HSTRING string; // [rsp+28h] [rbp-31h] BYREF
  PZZWSTR pwszLanguagesBuffer; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 *v16; // [rsp+38h] [rbp-21h] BYREF
  __int64 v17; // [rsp+40h] [rbp-19h]
  __int64 v18; // [rsp+48h] [rbp-11h]
  PZZWSTR v19; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-1h] BYREF

  *a2 = 0;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, 0, &pcchLanguagesBuffer)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    pwszLanguagesBuffer = 0;
    Error = _AllocArray<unsigned short,CTCoAllocPolicy>(v3, 1, pcchLanguagesBuffer, &pwszLanguagesBuffer);
    if ( Error >= 0 )
    {
      v5 = pwszLanguagesBuffer;
      Error = GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer)
            ? 0
            : ResultFromKnownLastError();
      if ( Error >= 0 )
      {
        v16 = 0;
        v17 = 0;
        v18 = 0;
        do
        {
          if ( !*v5 )
            break;
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          v19 = v5;
          v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, &v19);
          Error = Bcp47Normalize(*(_QWORD *)(v6 + 24), &string);
          if ( Error >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                      &v16,
                      L"%s, ",
                      StringRawBuffer);
          }
          WindowsDeleteString(string);
          v8 = -1;
          do
            ++v8;
          while ( v5[v8] );
          v5 += v8 + 1;
        }
        while ( Error >= 0 );
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v16);
        v9 = v17;
        for ( i = v16; v9; --v9 )
        {
          if ( !wcschr(L", ", i[v9 - 1]) )
            break;
        }
        if ( v9 != v17 )
          i[v9] = 0;
        v16 = 0;
        v18 = 0;
        v17 = 0;
        *a2 = i;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
      }
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pwszLanguagesBuffer);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1801a2500  push    rbp
0x1801a2502  push    rbx
0x1801a2503  push    rsi
0x1801a2504  push    rdi
0x1801a2505  push    r14
0x1801a2507  push    r15
0x1801a2509  lea     rbp, [rsp-2Fh]
0x1801a250e  sub     rsp, 88h
0x1801a2515  mov     rax, cs:__security_cookie
0x1801a251c  xor     rax, rsp
0x1801a251f  mov     [rbp+57h+var_38], rax
0x1801a2523  xor     r15d, r15d
0x1801a2526  lea     r9, [rbp+57h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1801a252a  mov     r14, rdx
0x1801a252d  mov     [rdx], r15
0x1801a2530  xor     r8d, r8d; pwszLanguagesBuffer
0x1801a2533  mov     [rbp+57h+pulNumLanguages], r15d
0x1801a2537  lea     rdx, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x1801a253b  mov     [rbp+57h+pcchLanguagesBuffer], r15d
0x1801a253f  lea     esi, [r15+38h]
0x1801a2543  mov     ecx, esi; dwFlags
0x1801a2545  call    cs:__imp_GetThreadPreferredUILanguages
0x1801a254b  test    eax, eax
0x1801a254d  jnz     short loc_1801A255E
0x1801a254f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801a2554  mov     edi, eax
0x1801a2556  test    eax, eax
0x1801a2558  js      loc_1801A2698
0x1801a255e  mov     r8d, [rbp+57h+pcchLanguagesBuffer]
0x1801a2562  lea     r9, [rbp+57h+pwszLanguagesBuffer]
0x1801a2566  mov     edx, 1
0x1801a256b  mov     [rbp+57h+pwszLanguagesBuffer], r15
0x1801a256f  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1801a2574  mov     edi, eax
0x1801a2576  test    eax, eax
0x1801a2578  js      loc_1801A268F
0x1801a257e  mov     rbx, [rbp+57h+pwszLanguagesBuffer]
0x1801a2582  lea     r9, [rbp+57h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1801a2586  mov     r8, rbx; pwszLanguagesBuffer
0x1801a2589  lea     rdx, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x1801a258d  mov     ecx, esi; dwFlags
0x1801a258f  call    cs:__imp_GetThreadPreferredUILanguages
0x1801a2595  test    eax, eax
0x1801a2597  jz      short loc_1801A259E
0x1801a2599  mov     edi, r15d
0x1801a259c  jmp     short loc_1801A25A5
0x1801a259e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801a25a3  mov     edi, eax
0x1801a25a5  test    edi, edi
0x1801a25a7  js      loc_1801A268F
0x1801a25ad  mov     [rbp+57h+var_78], r15
0x1801a25b1  mov     [rbp+57h+var_70], r15
0x1801a25b5  mov     [rbp+57h+var_68], r15
0x1801a25b9  cmp     [rbx], r15w
0x1801a25bd  jz      short loc_1801A2639
0x1801a25bf  xor     ecx, ecx; string
0x1801a25c1  mov     [rbp+57h+string], r15
0x1801a25c5  call    cs:__imp_WindowsDeleteString
0x1801a25cb  lea     rdx, [rbp+57h+var_60]
0x1801a25cf  mov     [rbp+57h+string], r15
0x1801a25d3  lea     rcx, [rbp+57h+var_58]
0x1801a25d7  mov     [rbp+57h+var_60], rbx
0x1801a25db  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801a25e0  lea     rdx, [rbp+57h+string]
0x1801a25e4  mov     rcx, [rax+18h]
0x1801a25e8  call    cs:__imp_Bcp47Normalize
0x1801a25ee  mov     edi, eax
0x1801a25f0  test    eax, eax
0x1801a25f2  js      short loc_1801A2615
0x1801a25f4  mov     rcx, [rbp+57h+string]; string
0x1801a25f8  xor     edx, edx; length
0x1801a25fa  call    cs:__imp_WindowsGetStringRawBuffer
0x1801a2600  mov     r8, rax
0x1801a2603  lea     rdx, aS_2; "%s, "
0x1801a260a  lea     rcx, [rbp+57h+var_78]
0x1801a260e  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1801a2613  mov     edi, eax
0x1801a2615  mov     rcx, [rbp+57h+string]; string
0x1801a2619  call    cs:__imp_WindowsDeleteString
0x1801a261f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a2623  inc     rax
0x1801a2626  cmp     [rbx+rax*2], r15w
0x1801a262b  jnz     short loc_1801A2623
0x1801a262d  lea     rbx, [rbx+rax*2]
0x1801a2631  add     rbx, 2
0x1801a2635  test    edi, edi
0x1801a2637  jns     short loc_1801A25B9
0x1801a2639  lea     rcx, [rbp+57h+var_78]
0x1801a263d  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x1801a2642  mov     rbx, [rbp+57h+var_70]
0x1801a2646  mov     rsi, [rbp+57h+var_78]
0x1801a264a  test    rbx, rbx
0x1801a264d  jz      short loc_1801A266C
0x1801a264f  movzx   edx, word ptr [rsi+rbx*2-2]; Ch
0x1801a2654  lea     rcx, asc_18040C374; ", "
0x1801a265b  call    cs:__imp_wcschr
0x1801a2661  test    rax, rax
0x1801a2664  jz      short loc_1801A266C
0x1801a2666  sub     rbx, 1
0x1801a266a  jnz     short loc_1801A264F
0x1801a266c  cmp     rbx, [rbp+57h+var_70]
0x1801a2670  jz      short loc_1801A2677
0x1801a2672  mov     [rsi+rbx*2], r15w
0x1801a2677  lea     rcx, [rbp+57h+var_78]
0x1801a267b  mov     [rbp+57h+var_78], r15
0x1801a267f  mov     [rbp+57h+var_68], r15
0x1801a2683  mov     [rbp+57h+var_70], r15
0x1801a2687  mov     [r14], rsi
0x1801a268a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801a268f  lea     rcx, [rbp+57h+pwszLanguagesBuffer]
0x1801a2693  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1801a2698  mov     eax, edi
0x1801a269a  mov     rcx, [rbp+57h+var_38]
0x1801a269e  xor     rcx, rsp; StackCookie
0x1801a26a1  call    __security_check_cookie
0x1801a26a6  add     rsp, 88h
0x1801a26ad  pop     r15
0x1801a26af  pop     r14
0x1801a26b1  pop     rdi
0x1801a26b2  pop     rsi
0x1801a26b3  pop     rbx
0x1801a26b4  pop     rbp
0x1801a26b5  retn
```
