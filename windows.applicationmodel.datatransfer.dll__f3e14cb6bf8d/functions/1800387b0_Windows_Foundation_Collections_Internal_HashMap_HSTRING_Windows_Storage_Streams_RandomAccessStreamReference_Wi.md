# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>>::Insert(HSTRING__ *,Windows::Storage::Streams::IRandomAccessStreamReference *,uchar *)

- ea: `0x1800387b0`
- end: `0x1800389e0`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$00$00$0A@@7895@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIRandomAccessStreamReference@Streams@Storage@5@PEAE@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180038a10`

## callees

- `0x18000670c`
- `0x180008ae4`
- `0x180020e1c`
- `0x1800387b0`
- `0x18003b33c`
- `0x1800438e0`
- `0x18004ac44`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180038813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180038813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800389b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800389b6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800387f1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800388a8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800387f1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800388a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003895b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003895b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003886b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003886b`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  HSTRING string; // r14
  _DWORD *v7; // rsi
  int v8; // ebx
  _DWORD *v9; // r14
  __int64 v10; // r15
  __int128 v11; // xmm6
  __int128 v13; // [rsp+30h] [rbp-48h] BYREF
  __int128 v14; // [rsp+40h] [rbp-38h] BYREF
  int v15; // [rsp+50h] [rbp-28h] BYREF
  _DWORD *v16; // [rsp+58h] [rbp-20h]
  __int64 v17; // [rsp+C0h] [rbp+48h] BYREF
  HSTRING v18; // [rsp+C8h] [rbp+50h]
  __int64 v19; // [rsp+D0h] [rbp+58h] BYREF
  HSTRING newString; // [rsp+D8h] [rbp+60h] BYREF

  v19 = a3;
  v18 = a2;
  *a4 = 0;
  string = a2;
  if ( !*(_BYTE *)(a1 + 200) )
    RoOriginateError(2147549183LL, 0);
  v16 = 0;
  v15 = -2147483627;
  newString = 0;
  v7 = 0;
  LODWORD(v17) = WindowsDuplicateString(string, &newString);
  v8 = v17;
  if ( (int)v17 >= 0 )
  {
    XWinRT::AutoValue<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>>::AutoValue<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>>(
      &v13,
      &v19,
      &v17);
    v8 = v17;
    *(_QWORD *)&v14 = 0;
    BYTE8(v14) = 0;
    if ( (int)v17 < 0 )
    {
LABEL_28:
      XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v14);
      XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v13);
      goto LABEL_29;
    }
    v9 = (_DWORD *)(a1 + 184);
    if ( *(_DWORD *)(a1 + 176) == 1 )
    {
      if ( !*v9 )
        *v9 = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 184));
    }
    v7 = (_DWORD *)(a1 + 236);
    if ( *(_DWORD *)(a1 + 236) )
    {
      v8 = -2147483627;
    }
    else
    {
      v8 = 0;
      if ( *(int *)(a1 + 232) > 0 )
      {
        *v7 = 1;
        goto LABEL_14;
      }
    }
    v7 = 0;
LABEL_14:
    v16 = v7;
    v15 = v8;
    if ( v8 >= 0 )
    {
      XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 192));
      v17 = 0;
      v8 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(
             a1 + 88,
             &newString,
             &v17);
      if ( v8 >= 0 )
      {
        v10 = v17;
        if ( v17 )
        {
          v11 = *(_OWORD *)(v17 + 8);
          XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v14);
          v14 = v11;
          *(_OWORD *)(v10 + 8) = v13;
          *a4 = 1;
        }
        else
        {
          if ( *(_QWORD *)(a1 + 104) == 0x7FFFFFFF )
          {
            v8 = -2147024882;
            goto LABEL_24;
          }
          v8 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>>>::SetAt(
                 a1 + 88,
                 &newString,
                 &v13,
                 &v17);
          if ( v8 < 0 )
            goto LABEL_24;
          newString = 0;
        }
        BYTE8(v13) = 0;
        *(_QWORD *)&v13 = 0;
      }
    }
    else
    {
      RoOriginateError((unsigned int)v8, 0);
    }
LABEL_24:
    if ( *(_DWORD *)(a1 + 176) == 1 )
      *v9 += 0x10000000;
    else
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 184));
    string = v18;
    goto LABEL_28;
  }
LABEL_29:
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>::RaiseEvent(
           (int)&v15,
           (int)a1 + 208,
           a1 != 0 ? a1 + 16 : 0,
           *a4 != 0 ? 3 : 1,
           string);
  WindowsDeleteString(newString);
  newString = 0;
  if ( v7 )
    *v7 = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800387b0  mov     [rsp-40h+arg_10], r8
0x1800387b5  mov     [rsp-40h+arg_8], rdx
0x1800387ba  push    rbp
0x1800387bb  push    rbx
0x1800387bc  push    rsi
0x1800387bd  push    rdi
0x1800387be  push    r12
0x1800387c0  push    r13
0x1800387c2  push    r14
0x1800387c4  push    r15
0x1800387c6  mov     rbp, rsp
0x1800387c9  sub     rsp, 78h
0x1800387cd  xor     r15d, r15d
0x1800387d0  movaps  [rsp+78h+var_18], xmm6
0x1800387d5  mov     [r9], r15b
0x1800387d8  mov     r13, r9
0x1800387db  mov     r14, rdx
0x1800387de  mov     rdi, rcx
0x1800387e1  cmp     [rcx+0C8h], r15b
0x1800387e8  jnz     short loc_1800387F7
0x1800387ea  xor     edx, edx
0x1800387ec  mov     ecx, 8000FFFFh
0x1800387f1  call    cs:__imp_RoOriginateError
0x1800387f7  mov     r12d, 80000015h
0x1800387fd  mov     [rbp+var_20], r15
0x180038801  lea     rdx, [rbp+newString]; newString
0x180038805  mov     [rbp+var_28], r12d
0x180038809  mov     rcx, r14; string
0x18003880c  mov     [rbp+newString], r15
0x180038810  mov     rsi, r15
0x180038813  call    cs:__imp_WindowsDuplicateString
0x180038819  mov     dword ptr [rbp+arg_0], eax
0x18003881c  mov     ebx, eax
0x18003881e  test    eax, eax
0x180038820  js      loc_180038977
0x180038826  lea     r8, [rbp+arg_0]
0x18003882a  lea     rdx, [rbp+arg_10]
0x18003882e  lea     rcx, [rbp+var_48]
0x180038832  call    ??$?0PEAUIRandomAccessStreamReference@Streams@Storage@Windows@@@?$AutoValue@V?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@XWinRT@@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUIRandomAccessStreamReference@Streams@Storage@Windows@@PEAJ@Z; XWinRT::AutoValue<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>>::AutoValue<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>>(Windows::Storage::Streams::IRandomAccessStreamReference * const &,long *)
0x180038837  mov     ebx, dword ptr [rbp+arg_0]
0x18003883a  mov     qword ptr [rbp+var_38], r15
0x18003883e  mov     byte ptr [rbp+var_38+8], r15b
0x180038842  test    ebx, ebx
0x180038844  js      loc_180038965
0x18003884a  cmp     dword ptr [rdi+0B0h], 1
0x180038851  lea     r14, [rdi+0B8h]
0x180038858  jnz     short loc_180038868
0x18003885a  cmp     [r14], r15d
0x18003885d  jnz     short loc_180038871
0x18003885f  mov     dword ptr [r14], 0F0000000h
0x180038866  jmp     short loc_180038871
0x180038868  mov     rcx, r14; SRWLock
0x18003886b  call    cs:__imp_AcquireSRWLockExclusive
0x180038871  mov     ecx, [rdi+0E8h]
0x180038877  lea     rsi, [rdi+0ECh]
0x18003887e  mov     eax, [rsi]
0x180038880  test    eax, eax
0x180038882  jnz     short loc_180038893
0x180038884  mov     ebx, r15d
0x180038887  test    ecx, ecx
0x180038889  jle     short loc_180038896
0x18003888b  mov     dword ptr [rsi], 1
0x180038891  jmp     short loc_180038899
0x180038893  mov     ebx, r12d
0x180038896  mov     rsi, r15
0x180038899  mov     [rbp+var_20], rsi
0x18003889d  mov     [rbp+var_28], ebx
0x1800388a0  test    ebx, ebx
0x1800388a2  jns     short loc_1800388B3
0x1800388a4  xor     edx, edx
0x1800388a6  mov     ecx, ebx
0x1800388a8  call    cs:__imp_RoOriginateError
0x1800388ae  jmp     loc_180038946
0x1800388b3  lea     rcx, [rdi+0C0h]; this
0x1800388ba  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800388bf  lea     r8, [rbp+arg_0]
0x1800388c3  mov     [rbp+arg_0], r15
0x1800388c7  lea     rdx, [rbp+newString]
0x1800388cb  lea     rcx, [rdi+58h]
0x1800388cf  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x1800388d4  mov     ebx, eax
0x1800388d6  test    eax, eax
0x1800388d8  js      short loc_180038946
0x1800388da  mov     r15, [rbp+arg_0]
0x1800388de  test    r15, r15
0x1800388e1  jz      short loc_18003890A
0x1800388e3  movups  xmm6, xmmword ptr [r15+8]
0x1800388e8  lea     rcx, [rbp+var_38]
0x1800388ec  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x1800388f1  movups  xmm0, [rbp+var_48]
0x1800388f5  movdqa  [rbp+var_38], xmm6
0x1800388fa  movdqu  xmmword ptr [r15+8], xmm0
0x180038900  xor     r15d, r15d
0x180038903  mov     byte ptr [r13+0], 1
0x180038908  jmp     short loc_18003893E
0x18003890a  cmp     qword ptr [rdi+68h], 7FFFFFFFh
0x180038912  jnz     short loc_18003891B
0x180038914  mov     ebx, 8007000Eh
0x180038919  jmp     short loc_180038946
0x18003891b  lea     r9, [rbp+arg_0]
0x18003891f  mov     [rbp+arg_0], r15
0x180038923  lea     r8, [rbp+var_48]
0x180038927  lea     rdx, [rbp+newString]
0x18003892b  lea     rcx, [rdi+58h]
0x18003892f  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@2@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference>>>::SetAt(HSTRING__ * const &,XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> const &,XWinRT::TXPOSITION * *)
0x180038934  mov     ebx, eax
0x180038936  test    eax, eax
0x180038938  js      short loc_180038946
0x18003893a  mov     [rbp+newString], r15
0x18003893e  mov     byte ptr [rbp+var_48+8], r15b
0x180038942  mov     qword ptr [rbp+var_48], r15
0x180038946  cmp     dword ptr [rdi+0B0h], 1
0x18003894d  jnz     short loc_180038958
0x18003894f  add     dword ptr [r14], 10000000h
0x180038956  jmp     short loc_180038961
0x180038958  mov     rcx, r14; SRWLock
0x18003895b  call    cs:__imp_ReleaseSRWLockExclusive
0x180038961  mov     r14, [rbp+arg_8]
0x180038965  lea     rcx, [rbp+var_38]
0x180038969  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x18003896e  lea     rcx, [rbp+var_48]
0x180038972  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x180038977  test    ebx, ebx
0x180038979  js      short loc_1800389B2
0x18003897b  mov     al, [r13+0]
0x18003897f  lea     rcx, [rdi+10h]
0x180038983  neg     al
0x180038985  mov     [rsp+78h+string], r14; string
0x18003898a  mov     rax, rdi
0x18003898d  lea     rdx, [rdi+0D0h]; int
0x180038994  sbb     r9d, r9d
0x180038997  and     r9d, 2
0x18003899b  inc     r9d; int
0x18003899e  neg     rax
0x1800389a1  sbb     r8, r8
0x1800389a4  and     r8, rcx; int
0x1800389a7  lea     rcx, [rbp+var_28]; int
0x1800389ab  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$MapChangedEventHandler@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@345@W4CollectionChange@345@PEAUHSTRING__@@@Z; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *,Windows::Foundation::Collections::CollectionChange,HSTRING__ *)
0x1800389b0  mov     ebx, eax
0x1800389b2  mov     rcx, [rbp+newString]; string
0x1800389b6  call    cs:__imp_WindowsDeleteString
0x1800389bc  mov     [rbp+newString], r15
0x1800389c0  test    rsi, rsi
0x1800389c3  jz      short loc_1800389C8
0x1800389c5  mov     [rsi], r15d
0x1800389c8  movaps  xmm6, [rsp+78h+var_18]
0x1800389cd  mov     eax, ebx
0x1800389cf  add     rsp, 78h
0x1800389d3  pop     r15
0x1800389d5  pop     r14
0x1800389d7  pop     r13
0x1800389d9  pop     r12
0x1800389db  pop     rdi
0x1800389dc  pop     rsi
0x1800389dd  pop     rbx
0x1800389de  pop     rbp
0x1800389df  retn
```
