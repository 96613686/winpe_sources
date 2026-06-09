# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,Windows::Storage::Streams::IRandomAccessStreamReference *,uchar *)

- ea: `0x180062590`
- end: `0x18006276c`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIRandomAccessStreamReference@Streams@Storage@5@PEAE@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000670c`
- `0x180008ae4`
- `0x1800130bc`
- `0x180020e1c`
- `0x18003b33c`
- `0x1800438c4`
- `0x18004ac44`
- `0x180062590`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800625e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800625e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062747`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800625d0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800625d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800626fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800626fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062638`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062638`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  int v7; // ebx
  _DWORD *v8; // rsi
  __int64 v9; // r14
  __int128 v10; // xmm6
  __int128 v12; // [rsp+30h] [rbp-30h] BYREF
  __int128 v13; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+50h] BYREF
  HSTRING newString; // [rsp+B8h] [rbp+58h] BYREF

  v15 = a3;
  *a4 = 0;
  if ( !*(_BYTE *)(a1 + 184) )
    RoOriginateError(2147549183LL, 0);
  newString = 0;
  LODWORD(v14) = WindowsDuplicateString(a2, &newString);
  v7 = v14;
  if ( (int)v14 >= 0 )
  {
    XWinRT::AutoValue<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>>::AutoValue<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>>(
      &v12,
      &v15,
      &v14);
    v7 = v14;
    *(_QWORD *)&v13 = 0;
    BYTE8(v13) = 0;
    if ( (int)v14 < 0 )
    {
LABEL_20:
      XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v13);
      XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v12);
      goto LABEL_21;
    }
    v8 = (_DWORD *)(a1 + 168);
    if ( *(_DWORD *)(a1 + 160) == 1 )
    {
      if ( !*v8 )
        *v8 = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 168));
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v14, *(unsigned __int8 *)(a1 + 186), a1 + 188);
    XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 176));
    v14 = 0;
    v7 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(
           a1 + 72,
           &newString,
           &v14);
    if ( v7 >= 0 )
    {
      v9 = v14;
      if ( v14 )
      {
        v10 = *(_OWORD *)(v14 + 8);
        XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v13);
        v13 = v10;
        *(_OWORD *)(v9 + 8) = v12;
        *a4 = 1;
LABEL_16:
        BYTE8(v12) = 0;
        *(_QWORD *)&v12 = 0;
        goto LABEL_17;
      }
      if ( *(_QWORD *)(a1 + 88) == 0x7FFFFFFF )
      {
        v7 = -2147024882;
        goto LABEL_17;
      }
      v14 = 0;
      v7 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>>>::SetAt(
             a1 + 72,
             &newString,
             &v12,
             &v14);
      if ( v7 >= 0 )
      {
        newString = 0;
        goto LABEL_16;
      }
    }
LABEL_17:
    if ( *(_DWORD *)(a1 + 160) == 1 )
      *v8 += 0x10000000;
    else
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 168));
    goto LABEL_20;
  }
LABEL_21:
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
           (unsigned __int8)v14,
           *(unsigned __int8 *)(a1 + 185),
           a1,
           *a4 != 0 ? 3 : 1,
           a2);
  WindowsDeleteString(newString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180062590  mov     [rsp-38h+arg_8], rbx
0x180062595  mov     [rsp-38h+arg_10], r8
0x18006259a  push    rbp
0x18006259b  push    rsi
0x18006259c  push    rdi
0x18006259d  push    r12
0x18006259f  push    r13
0x1800625a1  push    r14
0x1800625a3  push    r15
0x1800625a5  mov     rbp, rsp
0x1800625a8  sub     rsp, 60h
0x1800625ac  xor     r14d, r14d
0x1800625af  movaps  [rsp+60h+var_10], xmm6
0x1800625b4  mov     [r9], r14b
0x1800625b7  mov     r15, r9
0x1800625ba  mov     r12, rdx
0x1800625bd  mov     rdi, rcx
0x1800625c0  cmp     [rcx+0B8h], r14b
0x1800625c7  jnz     short loc_1800625D6
0x1800625c9  xor     edx, edx
0x1800625cb  mov     ecx, 8000FFFFh
0x1800625d0  call    cs:__imp_RoOriginateError
0x1800625d6  lea     rdx, [rbp+newString]; newString
0x1800625da  mov     [rbp+newString], r14
0x1800625de  mov     rcx, r12; string
0x1800625e1  call    cs:__imp_WindowsDuplicateString
0x1800625e7  mov     dword ptr [rbp+arg_0], eax
0x1800625ea  mov     ebx, eax
0x1800625ec  test    eax, eax
0x1800625ee  js      loc_180062716
0x1800625f4  lea     r8, [rbp+arg_0]
0x1800625f8  lea     rdx, [rbp+arg_10]
0x1800625fc  lea     rcx, [rbp+var_30]
0x180062600  call    ??$?0PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@@?$AutoValue@V?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@XWinRT@@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUIRandomAccessStreamReference@Streams@Storage@Windows@@PEAJ@Z; XWinRT::AutoValue<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>>::AutoValue<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>>(Windows::Storage::Streams::IRandomAccessStreamReference * const &,long *)
0x180062605  mov     ebx, dword ptr [rbp+arg_0]
0x180062608  mov     qword ptr [rbp+var_20], r14
0x18006260c  mov     byte ptr [rbp+var_20+8], r14b
0x180062610  test    ebx, ebx
0x180062612  js      loc_180062704
0x180062618  cmp     dword ptr [rdi+0A0h], 1
0x18006261f  lea     rsi, [rdi+0A8h]
0x180062626  jnz     short loc_180062635
0x180062628  cmp     [rsi], r14d
0x18006262b  jnz     short loc_18006263E
0x18006262d  mov     dword ptr [rsi], 0F0000000h
0x180062633  jmp     short loc_18006263E
0x180062635  mov     rcx, rsi; SRWLock
0x180062638  call    cs:__imp_AcquireSRWLockExclusive
0x18006263e  movzx   edx, byte ptr [rdi+0BAh]
0x180062645  lea     r8, [rdi+0BCh]
0x18006264c  lea     rcx, [rbp+arg_0]
0x180062650  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180062655  lea     rcx, [rdi+0B0h]; this
0x18006265c  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180062661  lea     r8, [rbp+arg_0]
0x180062665  mov     [rbp+arg_0], r14
0x180062669  lea     rdx, [rbp+newString]
0x18006266d  lea     rcx, [rdi+48h]
0x180062671  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x180062676  mov     ebx, eax
0x180062678  test    eax, eax
0x18006267a  js      short loc_1800626EA
0x18006267c  mov     r14, [rbp+arg_0]
0x180062680  test    r14, r14
0x180062683  jz      short loc_1800626AB
0x180062685  movups  xmm6, xmmword ptr [r14+8]
0x18006268a  lea     rcx, [rbp+var_20]
0x18006268e  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x180062693  movups  xmm0, [rbp+var_30]
0x180062697  movdqa  [rbp+var_20], xmm6
0x18006269c  movdqu  xmmword ptr [r14+8], xmm0
0x1800626a2  xor     r14d, r14d
0x1800626a5  mov     byte ptr [r15], 1
0x1800626a9  jmp     short loc_1800626E2
0x1800626ab  cmp     qword ptr [rdi+58h], 7FFFFFFFh
0x1800626b3  jnz     short loc_1800626BC
0x1800626b5  mov     ebx, 8007000Eh
0x1800626ba  jmp     short loc_1800626EA
0x1800626bc  xor     r14d, r14d
0x1800626bf  lea     r9, [rbp+arg_0]
0x1800626c3  lea     r8, [rbp+var_30]
0x1800626c7  mov     [rbp+arg_0], r14
0x1800626cb  lea     rdx, [rbp+newString]
0x1800626cf  lea     rcx, [rdi+48h]
0x1800626d3  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@2@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>>>::SetAt(HSTRING__ * const &,XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> const &,XWinRT::TXPOSITION * *)
0x1800626d8  mov     ebx, eax
0x1800626da  test    eax, eax
0x1800626dc  js      short loc_1800626EA
0x1800626de  mov     [rbp+newString], r14
0x1800626e2  mov     byte ptr [rbp+var_30+8], r14b
0x1800626e6  mov     qword ptr [rbp+var_30], r14
0x1800626ea  cmp     dword ptr [rdi+0A0h], 1
0x1800626f1  jnz     short loc_1800626FB
0x1800626f3  add     dword ptr [rsi], 10000000h
0x1800626f9  jmp     short loc_180062704
0x1800626fb  mov     rcx, rsi; SRWLock
0x1800626fe  call    cs:__imp_ReleaseSRWLockExclusive
0x180062704  lea     rcx, [rbp+var_20]
0x180062708  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x18006270d  lea     rcx, [rbp+var_30]
0x180062711  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x180062716  test    ebx, ebx
0x180062718  js      short loc_180062743
0x18006271a  mov     al, [r15]
0x18006271d  mov     r8, rdi
0x180062720  movzx   edx, byte ptr [rdi+0B9h]
0x180062727  neg     al
0x180062729  movzx   ecx, byte ptr [rbp+arg_0]
0x18006272d  sbb     r9d, r9d
0x180062730  mov     [rsp+60h+var_40], r12
0x180062735  and     r9d, 2
0x180062739  inc     r9d
0x18006273c  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180062741  mov     ebx, eax
0x180062743  mov     rcx, [rbp+newString]; string
0x180062747  call    cs:__imp_WindowsDeleteString
0x18006274d  movaps  xmm6, [rsp+60h+var_10]
0x180062752  mov     eax, ebx
0x180062754  mov     rbx, [rsp+60h+arg_8]
0x18006275c  add     rsp, 60h
0x180062760  pop     r15
0x180062762  pop     r14
0x180062764  pop     r13
0x180062766  pop     r12
0x180062768  pop     rdi
0x180062769  pop     rsi
0x18006276a  pop     rbp
0x18006276b  retn
```
