# Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,CCaseInsensitiveStringEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>>::SetAt(uint,HSTRING__ *)

- ea: `0x180057540`
- end: `0x180057699`
- name: `?SetAt@?$Vector@PEAUHSTRING__@@VCCaseInsensitiveStringEqualityPredicate@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$VectorOptions@PEAUHSTRING__@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUHSTRING__@@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800574e0`

## callees

- `0x1800458f8`
- `0x180049b64`
- `0x180055744`
- `0x180057540`
- `0x18005a32c`
- `0x18005bfec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005763f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005763f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005761b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005765a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005761b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057649`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005765a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800575b0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800575fb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800575b0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800575fb`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,CCaseInsensitiveStringEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>>::SetAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r14
  int v4; // ebx
  HSTRING v5; // rdi
  __int64 v6; // rax
  RTL_SRWLOCK *v7; // rcx
  HSTRING string; // [rsp+30h] [rbp-10h] BYREF
  RTL_SRWLOCK *v10; // [rsp+38h] [rbp-8h] BYREF
  HSTRING Destination; // [rsp+78h] [rbp+38h] BYREF

  v2 = a2;
  LODWORD(Destination) = 0;
  XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
  v4 = (int)Destination;
  v5 = 0;
  if ( (int)Destination >= 0 )
  {
    XWinRT::SerializingLockPolicy::Write(&v10, a1 + 112, &Destination);
    v4 = (int)Destination;
    if ( (int)Destination >= 0 )
    {
      if ( (unsigned int)v2 >= *(_DWORD *)(a1 + 80) )
      {
        v4 = -2147483637;
        RoOriginateError(2147483659LL, 0);
      }
      if ( v4 >= 0 )
      {
        XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&Destination, *(unsigned __int8 *)(a1 + 133), a1 + 136);
        v6 = *(_QWORD *)(a1 + 96);
        v4 = 0;
        Destination = 0;
        if ( memmove_s(&Destination, 8u, (const void *const)(v6 + 8 * v2), 8u) )
        {
          v4 = -2147418113;
          RoOriginateError(2147549183LL, 0);
        }
        else
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 96) + 8 * v2) = string;
          ++*(_DWORD *)(a1 + 128);
          string = 0;
          WindowsDeleteString(0);
          v5 = Destination;
        }
      }
    }
    if ( v10 )
    {
      v7 = v10 + 1;
      if ( LODWORD(v10->Ptr) == 1 )
        LODWORD(v7->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v7);
    }
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v5);
  if ( v4 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>::RaiseEvent(
                           (unsigned __int8)Destination,
                           *(unsigned __int8 *)(a1 + 132),
                           a1,
                           3,
                           v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180057540  mov     [rsp-18h+arg_0], rbx
0x180057545  mov     [rsp-18h+arg_8], rsi
0x18005754a  mov     [rsp-18h+arg_10], r8
0x18005754f  push    rbp
0x180057550  push    rdi
0x180057551  push    r14
0x180057553  mov     rbp, rsp
0x180057556  sub     rsp, 40h
0x18005755a  mov     r14d, edx
0x18005755d  lea     r8, [rbp+Destination]
0x180057561  mov     rsi, rcx
0x180057564  mov     dword ptr [rbp+Destination], 0
0x18005756b  lea     rdx, [rbp+arg_10]
0x18005756f  lea     rcx, [rbp+string]; newString
0x180057573  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x180057578  mov     ebx, dword ptr [rbp+Destination]
0x18005757b  xor     edi, edi
0x18005757d  test    ebx, ebx
0x18005757f  js      loc_180057645
0x180057585  lea     rdx, [rsi+70h]
0x180057589  lea     r8, [rbp+Destination]
0x18005758d  lea     rcx, [rbp+var_8]
0x180057591  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180057596  mov     ebx, dword ptr [rbp+Destination]
0x180057599  test    ebx, ebx
0x18005759b  js      loc_180057625
0x1800575a1  cmp     r14d, [rsi+50h]
0x1800575a5  jb      short loc_1800575B6
0x1800575a7  mov     ebx, 8000000Bh
0x1800575ac  xor     edx, edx
0x1800575ae  mov     ecx, ebx
0x1800575b0  call    cs:__imp_RoOriginateError
0x1800575b6  test    ebx, ebx
0x1800575b8  js      short loc_180057625
0x1800575ba  movzx   edx, byte ptr [rsi+85h]
0x1800575c1  lea     r8, [rsi+88h]
0x1800575c8  lea     rcx, [rbp+Destination]
0x1800575cc  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800575d1  mov     rax, [rsi+60h]
0x1800575d5  lea     rcx, [rbp+Destination]; Destination
0x1800575d9  xor     ebx, ebx
0x1800575db  mov     [rbp+Destination], rbx
0x1800575df  lea     r8, [rax+r14*8]; Source
0x1800575e3  lea     edx, [rbx+8]; DestinationSize
0x1800575e6  mov     r9d, edx; SourceSize
0x1800575e9  call    memmove_s
0x1800575ee  test    eax, eax
0x1800575f0  jz      short loc_180057603
0x1800575f2  mov     ebx, 8000FFFFh
0x1800575f7  xor     edx, edx
0x1800575f9  mov     ecx, ebx
0x1800575fb  call    cs:__imp_RoOriginateError
0x180057601  jmp     short loc_180057625
0x180057603  mov     rcx, [rsi+60h]
0x180057607  mov     rax, [rbp+string]
0x18005760b  mov     [rcx+r14*8], rax
0x18005760f  xor     ecx, ecx; string
0x180057611  inc     dword ptr [rsi+80h]
0x180057617  mov     [rbp+string], rbx
0x18005761b  call    cs:__imp_WindowsDeleteString
0x180057621  mov     rdi, [rbp+Destination]
0x180057625  mov     rax, [rbp+var_8]
0x180057629  test    rax, rax
0x18005762c  jz      short loc_180057645
0x18005762e  cmp     dword ptr [rax], 1
0x180057631  lea     rcx, [rax+8]; SRWLock
0x180057635  jnz     short loc_18005763F
0x180057637  add     dword ptr [rcx], 10000000h
0x18005763d  jmp     short loc_180057645
0x18005763f  call    cs:__imp_ReleaseSRWLockExclusive
0x180057645  mov     rcx, [rbp+string]; string
0x180057649  call    cs:__imp_WindowsDeleteString
0x18005764f  mov     rcx, rdi; string
0x180057652  mov     [rbp+string], 0
0x18005765a  call    cs:__imp_WindowsDeleteString
0x180057660  test    ebx, ebx
0x180057662  js      short loc_180057684
0x180057664  movzx   edx, byte ptr [rsi+84h]
0x18005766b  mov     r9d, 3
0x180057671  movzx   ecx, byte ptr [rbp+Destination]
0x180057675  mov     r8, rsi
0x180057678  mov     [rsp+40h+var_20], r14d
0x18005767d  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>::RaiseEvent(...)
0x180057682  mov     ebx, eax
0x180057684  mov     rsi, [rsp+40h+arg_8]
0x180057689  mov     eax, ebx
0x18005768b  mov     rbx, [rsp+40h+arg_0]
0x180057690  add     rsp, 40h
0x180057694  pop     r14
0x180057696  pop     rdi
0x180057697  pop     rbp
0x180057698  retn
```
