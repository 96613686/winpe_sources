# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x18006c8a0`
- end: `0x18006ca5c`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUIPropertyValue@Foundation@Windows@@@6734@U?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@6734@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callees

- `0x180064d44`
- `0x1800666d8`
- `0x180066f94`
- `0x180067d14`
- `0x18006ab94`
- `0x18006bf24`
- `0x18006c7f0`
- `0x18006c8a0`
- `0x18006d518`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18006c9e8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18006c9e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c963`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ca16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006c963`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ca16`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006c941`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006c941`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // edi
  HSTRING v4; // rbx
  void *v5; // r15
  char v6; // r12
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  RTL_SRWLOCK *v12; // rcx
  __int64 v14; // [rsp+78h] [rbp+48h] BYREF
  __int64 v15; // [rsp+80h] [rbp+50h] BYREF
  RTL_SRWLOCK *v16; // [rsp+88h] [rbp+58h] BYREF

  v14 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    v5 = 0;
    v6 = 0;
    LODWORD(v15) = 0;
    XWinRT::SerializingLockPolicy::Write(&v16, a1 + 160, &v15);
    v3 = v15;
    if ( (int)v15 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v15, *(unsigned __int8 *)(a1 + 186), a1 + 188);
      v15 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::Lookup(
             a1 + 72,
             &v14,
             &v15);
      if ( v3 >= 0 )
      {
        v7 = v15;
        if ( v15 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v7;
            WindowsDeleteString(0);
            if ( v7 )
            {
              v5 = *(void **)(v7 + 8);
              v6 = *(_BYTE *)(v7 + 16);
              v8 = (unsigned int)(*(_DWORD *)(v7 + 32) % *(_DWORD *)(a1 + 96));
              v9 = *(_QWORD *)(a1 + 80);
              v10 = *(_QWORD *)(v9 + 8 * v8);
              if ( v7 == v10 )
              {
                v10 = 0;
              }
              else
              {
                while ( *(_QWORD *)(v10 + 24) != v7 )
                  v10 = *(_QWORD *)(v10 + 24);
              }
              v11 = *(_QWORD *)(v7 + 24);
              if ( v10 )
                *(_QWORD *)(v10 + 24) = v11;
              else
                *(_QWORD *)(v9 + 8 * v8) = v11;
              XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::FreeNode(
                a1 + 72,
                v7);
              v3 = 0;
            }
            else
            {
              v3 = -2147418113;
              v4 = 0;
              v5 = 0;
              v6 = 0;
            }
          }
        }
        else
        {
          v3 = -2147483637;
          RoOriginateError(2147483659LL, 0);
        }
      }
    }
    if ( v16 )
    {
      v12 = v16 + 1;
      if ( LODWORD(v16->Ptr) == 1 )
        LODWORD(v12->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v12);
    }
    if ( v6 )
    {
      XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>::ReferencedGitCookie::Release(v5);
    }
    else if ( v5 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                           (unsigned __int8)v15,
                           *(unsigned __int8 *)(a1 + 185),
                           a1,
                           2,
                           v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006c8a0  mov     [rsp-38h+arg_0], rbx
0x18006c8a5  mov     [rsp-38h+arg_8], rdx
0x18006c8aa  push    rbp
0x18006c8ab  push    rsi
0x18006c8ac  push    rdi
0x18006c8ad  push    r12
0x18006c8af  push    r13
0x18006c8b1  push    r14
0x18006c8b3  push    r15
0x18006c8b5  mov     rbp, rsp
0x18006c8b8  sub     rsp, 30h
0x18006c8bc  mov     r14, rcx
0x18006c8bf  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUIPropertyValue@Foundation@Windows@@@6734@U?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@6734@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x18006c8c4  mov     edi, eax
0x18006c8c6  test    eax, eax
0x18006c8c8  js      loc_18006CA1C
0x18006c8ce  xor     ebx, ebx
0x18006c8d0  xor     r15d, r15d
0x18006c8d3  xor     r12b, r12b
0x18006c8d6  mov     dword ptr [rbp+arg_10], ebx
0x18006c8d9  lea     rdx, [r14+0A0h]
0x18006c8e0  lea     r8, [rbp+arg_10]
0x18006c8e4  lea     rcx, [rbp+arg_18]
0x18006c8e8  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18006c8ed  mov     edi, dword ptr [rbp+arg_10]
0x18006c8f0  test    edi, edi
0x18006c8f2  js      loc_18006C9CE
0x18006c8f8  lea     r8, [r14+0BCh]
0x18006c8ff  movzx   edx, byte ptr [r14+0BAh]
0x18006c907  lea     rcx, [rbp+arg_10]
0x18006c90b  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18006c910  mov     [rbp+arg_10], rbx
0x18006c914  lea     r8, [rbp+arg_10]
0x18006c918  lea     rdx, [rbp+arg_8]
0x18006c91c  lea     rcx, [r14+48h]
0x18006c920  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUIPropertyValue@Foundation@Windows@@@6734@U?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@6734@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::CPair * *)
0x18006c925  mov     edi, eax
0x18006c927  test    eax, eax
0x18006c929  js      loc_18006C9CE
0x18006c92f  mov     rsi, [rbp+arg_10]
0x18006c933  test    rsi, rsi
0x18006c936  jnz     short loc_18006C94C
0x18006c938  xor     edx, edx
0x18006c93a  mov     edi, 8000000Bh
0x18006c93f  mov     ecx, edi
0x18006c941  call    cs:__imp_RoOriginateError
0x18006c947  jmp     loc_18006C9CE
0x18006c94c  lea     rcx, [r14+0B0h]; this
0x18006c953  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18006c958  mov     edi, eax
0x18006c95a  test    eax, eax
0x18006c95c  js      short loc_18006C9CE
0x18006c95e  mov     rbx, [rsi]
0x18006c961  xor     ecx, ecx; string
0x18006c963  call    cs:__imp_WindowsDeleteString
0x18006c969  nop
0x18006c96a  test    rsi, rsi
0x18006c96d  jz      short loc_18006C9C1
0x18006c96f  mov     r15, [rsi+8]
0x18006c973  mov     r12b, [rsi+10h]
0x18006c977  xor     edx, edx
0x18006c979  mov     eax, [rsi+20h]
0x18006c97c  div     dword ptr [r14+60h]
0x18006c980  mov     r8d, edx
0x18006c983  mov     rdx, [r14+50h]
0x18006c987  mov     rax, [rdx+r8*8]
0x18006c98b  cmp     rsi, rax
0x18006c98e  jnz     short loc_18006C998
0x18006c990  xor     eax, eax
0x18006c992  jmp     short loc_18006C99E
0x18006c994  mov     rax, [rax+18h]
0x18006c998  cmp     [rax+18h], rsi
0x18006c99c  jnz     short loc_18006C994
0x18006c99e  mov     rcx, [rsi+18h]
0x18006c9a2  test    rax, rax
0x18006c9a5  jnz     short loc_18006C9AD
0x18006c9a7  mov     [rdx+r8*8], rcx
0x18006c9ab  jmp     short loc_18006C9B1
0x18006c9ad  mov     [rax+18h], rcx
0x18006c9b1  mov     rdx, rsi
0x18006c9b4  lea     rcx, [r14+48h]
0x18006c9b8  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUIPropertyValue@Foundation@Windows@@@6734@U?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@6734@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@@4@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::CNode *)
0x18006c9bd  xor     edi, edi
0x18006c9bf  jmp     short loc_18006C9CE
0x18006c9c1  mov     edi, 8000FFFFh
0x18006c9c6  xor     ebx, ebx
0x18006c9c8  xor     r15d, r15d
0x18006c9cb  xor     r12b, r12b
0x18006c9ce  mov     rax, [rbp+arg_18]
0x18006c9d2  test    rax, rax
0x18006c9d5  jz      short loc_18006C9EF
0x18006c9d7  lea     rcx, [rax+8]; SRWLock
0x18006c9db  cmp     dword ptr [rax], 1
0x18006c9de  jnz     short loc_18006C9E8
0x18006c9e0  add     dword ptr [rcx], 10000000h
0x18006c9e6  jmp     short loc_18006C9EF
0x18006c9e8  call    cs:__imp_ReleaseSRWLockExclusive
0x18006c9ee  nop
0x18006c9ef  test    r12b, r12b
0x18006c9f2  jz      short loc_18006C9FE
0x18006c9f4  mov     rcx, r15; Block
0x18006c9f7  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>::ReferencedGitCookie::Release(void)
0x18006c9fc  jmp     short loc_18006CA13
0x18006c9fe  test    r15, r15
0x18006ca01  jz      short loc_18006CA13
0x18006ca03  mov     rax, [r15]
0x18006ca06  mov     rcx, r15
0x18006ca09  mov     rax, [rax+10h]
0x18006ca0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca12  nop
0x18006ca13  mov     rcx, rbx; string
0x18006ca16  call    cs:__imp_WindowsDeleteString
0x18006ca1c  test    edi, edi
0x18006ca1e  js      short loc_18006CA45
0x18006ca20  mov     rax, [rbp+arg_8]
0x18006ca24  mov     [rsp+30h+var_10], rax
0x18006ca29  mov     r9d, 2
0x18006ca2f  mov     r8, r14
0x18006ca32  movzx   edx, byte ptr [r14+0B9h]
0x18006ca3a  movzx   ecx, byte ptr [rbp+arg_10]
0x18006ca3e  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18006ca43  mov     edi, eax
0x18006ca45  mov     eax, edi
0x18006ca47  mov     rbx, [rsp+30h+arg_0]
0x18006ca4c  add     rsp, 30h
0x18006ca50  pop     r15
0x18006ca52  pop     r14
0x18006ca54  pop     r13
0x18006ca56  pop     r12
0x18006ca58  pop     rdi
0x18006ca59  pop     rsi
0x18006ca5a  pop     rbp
0x18006ca5b  retn
```
