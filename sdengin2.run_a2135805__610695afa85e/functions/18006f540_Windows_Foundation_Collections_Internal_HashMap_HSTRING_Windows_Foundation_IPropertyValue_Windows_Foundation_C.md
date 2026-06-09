# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x18006f540`
- end: `0x18006f715`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUIPropertyValue@Foundation@Windows@@@6734@U?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@6734@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callees

- `0x180067700`
- `0x1800690d8`
- `0x180069a04`
- `0x18006a820`
- `0x18006d7c4`
- `0x18006ebb4`
- `0x18006f490`
- `0x18006f540`
- `0x1800701ec`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18006f694`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18006f694`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f6c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f6c8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006f5e1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006f5e1`

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
0x18006f540  mov     [rsp-38h+arg_0], rbx
0x18006f545  mov     [rsp-38h+arg_8], rdx
0x18006f54a  push    rbp
0x18006f54b  push    rsi
0x18006f54c  push    rdi
0x18006f54d  push    r12
0x18006f54f  push    r13
0x18006f551  push    r14
0x18006f553  push    r15
0x18006f555  mov     rbp, rsp
0x18006f558  sub     rsp, 30h
0x18006f55c  mov     r14, rcx
0x18006f55f  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUIPropertyValue@Foundation@Windows@@@6734@U?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@6734@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::EnsureInitialized(void)
0x18006f564  mov     edi, eax
0x18006f566  test    eax, eax
0x18006f568  js      loc_18006F6D4
0x18006f56e  xor     ebx, ebx
0x18006f570  xor     r15d, r15d
0x18006f573  xor     r12b, r12b
0x18006f576  mov     dword ptr [rbp+arg_10], ebx
0x18006f579  lea     rdx, [r14+0A0h]
0x18006f580  lea     r8, [rbp+arg_10]
0x18006f584  lea     rcx, [rbp+arg_18]
0x18006f588  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18006f58d  mov     edi, dword ptr [rbp+arg_10]
0x18006f590  test    edi, edi
0x18006f592  js      loc_18006F67A
0x18006f598  lea     r8, [r14+0BCh]
0x18006f59f  movzx   edx, byte ptr [r14+0BAh]
0x18006f5a7  lea     rcx, [rbp+arg_10]
0x18006f5ab  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18006f5b0  mov     [rbp+arg_10], rbx
0x18006f5b4  lea     r8, [rbp+arg_10]
0x18006f5b8  lea     rdx, [rbp+arg_8]
0x18006f5bc  lea     rcx, [r14+48h]
0x18006f5c0  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUIPropertyValue@Foundation@Windows@@@6734@U?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@6734@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::CPair * *)
0x18006f5c5  mov     edi, eax
0x18006f5c7  test    eax, eax
0x18006f5c9  js      loc_18006F67A
0x18006f5cf  mov     rsi, [rbp+arg_10]
0x18006f5d3  test    rsi, rsi
0x18006f5d6  jnz     short loc_18006F5F2
0x18006f5d8  xor     edx, edx
0x18006f5da  mov     edi, 8000000Bh
0x18006f5df  mov     ecx, edi
0x18006f5e1  call    cs:__imp_RoOriginateError
0x18006f5e8  nop     dword ptr [rax+rax+00h]
0x18006f5ed  jmp     loc_18006F67A
0x18006f5f2  lea     rcx, [r14+0B0h]; this
0x18006f5f9  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18006f5fe  mov     edi, eax
0x18006f600  test    eax, eax
0x18006f602  js      short loc_18006F67A
0x18006f604  mov     rbx, [rsi]
0x18006f607  xor     ecx, ecx; string
0x18006f609  call    cs:__imp_WindowsDeleteString
0x18006f610  nop     dword ptr [rax+rax+00h]
0x18006f615  nop
0x18006f616  test    rsi, rsi
0x18006f619  jz      short loc_18006F66D
0x18006f61b  mov     r15, [rsi+8]
0x18006f61f  mov     r12b, [rsi+10h]
0x18006f623  xor     edx, edx
0x18006f625  mov     eax, [rsi+20h]
0x18006f628  div     dword ptr [r14+60h]
0x18006f62c  mov     r8d, edx
0x18006f62f  mov     rdx, [r14+50h]
0x18006f633  mov     rax, [rdx+r8*8]
0x18006f637  cmp     rsi, rax
0x18006f63a  jnz     short loc_18006F644
0x18006f63c  xor     eax, eax
0x18006f63e  jmp     short loc_18006F64A
0x18006f640  mov     rax, [rax+18h]
0x18006f644  cmp     [rax+18h], rsi
0x18006f648  jnz     short loc_18006F640
0x18006f64a  mov     rcx, [rsi+18h]
0x18006f64e  test    rax, rax
0x18006f651  jnz     short loc_18006F659
0x18006f653  mov     [rdx+r8*8], rcx
0x18006f657  jmp     short loc_18006F65D
0x18006f659  mov     [rax+18h], rcx
0x18006f65d  mov     rdx, rsi
0x18006f660  lea     rcx, [r14+48h]
0x18006f664  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6734@U?$DefaultLifetimeTraits@PEAUIPropertyValue@Foundation@Windows@@@6734@U?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@6734@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@@4@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IPropertyValue *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>>>::CNode *)
0x18006f669  xor     edi, edi
0x18006f66b  jmp     short loc_18006F67A
0x18006f66d  mov     edi, 8000FFFFh
0x18006f672  xor     ebx, ebx
0x18006f674  xor     r15d, r15d
0x18006f677  xor     r12b, r12b
0x18006f67a  mov     rax, [rbp+arg_18]
0x18006f67e  test    rax, rax
0x18006f681  jz      short loc_18006F6A1
0x18006f683  lea     rcx, [rax+8]; SRWLock
0x18006f687  cmp     dword ptr [rax], 1
0x18006f68a  jnz     short loc_18006F694
0x18006f68c  add     dword ptr [rcx], 10000000h
0x18006f692  jmp     short loc_18006F6A1
0x18006f694  call    cs:__imp_ReleaseSRWLockExclusive
0x18006f69b  nop     dword ptr [rax+rax+00h]
0x18006f6a0  nop
0x18006f6a1  test    r12b, r12b
0x18006f6a4  jz      short loc_18006F6B0
0x18006f6a6  mov     rcx, r15; Block
0x18006f6a9  call    ?Release@ReferencedGitCookie@?$GitStorageType@UIPropertyValue@Foundation@Windows@@@detail@XWinRT@@QEAAKXZ; XWinRT::detail::GitStorageType<Windows::Foundation::IPropertyValue>::ReferencedGitCookie::Release(void)
0x18006f6ae  jmp     short loc_18006F6C5
0x18006f6b0  test    r15, r15
0x18006f6b3  jz      short loc_18006F6C5
0x18006f6b5  mov     rax, [r15]
0x18006f6b8  mov     rcx, r15
0x18006f6bb  mov     rax, [rax+10h]
0x18006f6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6c4  nop
0x18006f6c5  mov     rcx, rbx; string
0x18006f6c8  call    cs:__imp_WindowsDeleteString
0x18006f6cf  nop     dword ptr [rax+rax+00h]
0x18006f6d4  test    edi, edi
0x18006f6d6  js      short loc_18006F6FD
0x18006f6d8  mov     rax, [rbp+arg_8]
0x18006f6dc  mov     [rsp+30h+var_10], rax
0x18006f6e1  mov     r9d, 2
0x18006f6e7  mov     r8, r14
0x18006f6ea  movzx   edx, byte ptr [r14+0B9h]
0x18006f6f2  movzx   ecx, byte ptr [rbp+arg_10]
0x18006f6f6  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIPropertyValue@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Foundation::IPropertyValue *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x18006f6fb  mov     edi, eax
0x18006f6fd  mov     eax, edi
0x18006f6ff  mov     rbx, [rsp+30h+arg_0]
0x18006f704  add     rsp, 30h
0x18006f708  pop     r15
0x18006f70a  pop     r14
0x18006f70c  pop     r13
0x18006f70e  pop     r12
0x18006f710  pop     rdi
0x18006f711  pop     rsi
0x18006f712  pop     rbp
0x18006f713  retn
```
