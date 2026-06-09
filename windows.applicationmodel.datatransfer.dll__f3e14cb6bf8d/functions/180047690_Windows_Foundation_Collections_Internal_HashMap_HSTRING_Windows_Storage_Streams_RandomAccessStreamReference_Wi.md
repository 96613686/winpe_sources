# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>>::Remove(HSTRING__ *)

- ea: `0x180047690`
- end: `0x1800478a1`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$00$00$0A@@7895@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800478d0`

## callees

- `0x180008ae4`
- `0x180020e1c`
- `0x18002b3a0`
- `0x18003b33c`
- `0x1800438e0`
- `0x180047690`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004779c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004783a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004779c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004783a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800476cb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004777a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800476cb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004777a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047828`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047828`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047712`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047712`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Streams::RandomAccessStreamReference *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>>::Remove(
        __int64 a1,
        HSTRING a2)
{
  int v3; // eax
  _DWORD *v4; // r14
  int v5; // edi
  HSTRING v6; // rbx
  _DWORD *v7; // r12
  bool v8; // zf
  __int64 v9; // r15
  __int128 v10; // xmm6
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int128 v16; // [rsp+30h] [rbp-30h] BYREF
  int v17; // [rsp+40h] [rbp-20h] BYREF
  _DWORD *v18; // [rsp+48h] [rbp-18h]
  __int64 v19; // [rsp+90h] [rbp+30h] BYREF
  HSTRING string; // [rsp+98h] [rbp+38h] BYREF

  string = a2;
  if ( *(_BYTE *)(a1 + 200) )
  {
    v3 = 0;
  }
  else
  {
    RoOriginateError(2147549183LL, 0);
    v3 = -2147418113;
  }
  v4 = 0;
  v5 = -2147483627;
  v17 = -2147483627;
  if ( v3 < 0 )
    goto LABEL_34;
  v6 = 0;
  v7 = (_DWORD *)(a1 + 184);
  v8 = *(_DWORD *)(a1 + 176) == 1;
  *(_QWORD *)&v16 = 0;
  BYTE8(v16) = 0;
  if ( v8 )
  {
    if ( !*v7 )
      *v7 = -268435456;
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 184));
  }
  v4 = (_DWORD *)(a1 + 236);
  if ( *(_DWORD *)(a1 + 236) || (v5 = 0, *(int *)(a1 + 232) <= 0) )
    v4 = 0;
  else
    *v4 = 1;
  v18 = v4;
  v17 = v5;
  if ( v5 < 0 )
  {
LABEL_17:
    RoOriginateError((unsigned int)v5, 0);
    goto LABEL_29;
  }
  v19 = 0;
  v5 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(
         a1 + 88,
         &string,
         &v19);
  if ( v5 >= 0 )
  {
    v9 = v19;
    if ( v19 )
    {
      v5 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 192));
      if ( v5 >= 0 )
      {
        v6 = *(HSTRING *)v9;
        WindowsDeleteString(0);
        v10 = *(_OWORD *)(v9 + 8);
        XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v16);
        v16 = v10;
        if ( v9 )
        {
          v11 = (unsigned int)(*(_DWORD *)(v9 + 32) % *(_DWORD *)(a1 + 112));
          v12 = *(_QWORD *)(a1 + 96);
          v13 = *(_QWORD *)(v12 + 8 * v11);
          if ( v9 == v13 )
          {
            v13 = 0;
          }
          else
          {
            while ( *(_QWORD *)(v13 + 24) != v9 )
              v13 = *(_QWORD *)(v13 + 24);
          }
          v14 = *(_QWORD *)(v9 + 24);
          if ( v13 )
            *(_QWORD *)(v13 + 24) = v14;
          else
            *(_QWORD *)(v12 + 8 * v11) = v14;
          XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::FreeNode(
            a1 + 88,
            v9);
          v5 = 0;
        }
        else
        {
          v6 = 0;
          v5 = -2147418113;
          *(_QWORD *)&v16 = 0;
          BYTE8(v16) = 0;
        }
      }
      goto LABEL_29;
    }
    v5 = -2147483637;
    goto LABEL_17;
  }
LABEL_29:
  if ( *(_DWORD *)(a1 + 176) == 1 )
    *v7 += 0x10000000;
  else
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 184));
  XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v16);
  WindowsDeleteString(v6);
  if ( v5 < 0 )
    goto LABEL_35;
  v3 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>::RaiseEvent(
         (int)&v17,
         (int)a1 + 208,
         a1 != 0 ? a1 + 16 : 0,
         2,
         string);
LABEL_34:
  v5 = v3;
LABEL_35:
  if ( v4 )
    *v4 = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180047690  mov     rax, rsp
0x180047693  mov     [rax+18h], rbx
0x180047697  mov     [rax+20h], rsi
0x18004769b  mov     [rax+10h], rdx
0x18004769f  push    rbp
0x1800476a0  push    rdi
0x1800476a1  push    r12
0x1800476a3  push    r14
0x1800476a5  push    r15
0x1800476a7  mov     rbp, rsp
0x1800476aa  sub     rsp, 60h
0x1800476ae  cmp     byte ptr [rcx+0C8h], 0
0x1800476b5  mov     rsi, rcx
0x1800476b8  movaps  xmmword ptr [rax-38h], xmm6
0x1800476bc  mov     ebx, 8000FFFFh
0x1800476c1  jz      short loc_1800476C7
0x1800476c3  xor     eax, eax
0x1800476c5  jmp     short loc_1800476D3
0x1800476c7  xor     edx, edx
0x1800476c9  mov     ecx, ebx
0x1800476cb  call    cs:__imp_RoOriginateError
0x1800476d1  mov     eax, ebx
0x1800476d3  xor     r14d, r14d
0x1800476d6  mov     edi, 80000015h
0x1800476db  mov     [rbp+var_20], edi
0x1800476de  test    eax, eax
0x1800476e0  js      loc_180047873
0x1800476e6  xor     ebx, ebx
0x1800476e8  lea     r12, [rsi+0B8h]
0x1800476ef  cmp     dword ptr [rsi+0B0h], 1
0x1800476f6  mov     qword ptr [rbp+var_30], rbx
0x1800476fa  mov     byte ptr [rbp+var_30+8], bl
0x1800476fd  jnz     short loc_18004770F
0x1800476ff  cmp     [r12], ebx
0x180047703  jnz     short loc_180047718
0x180047705  mov     dword ptr [r12], 0F0000000h
0x18004770d  jmp     short loc_180047718
0x18004770f  mov     rcx, r12; SRWLock
0x180047712  call    cs:__imp_AcquireSRWLockExclusive
0x180047718  mov     ecx, [rsi+0E8h]
0x18004771e  lea     r14, [rsi+0ECh]
0x180047725  mov     eax, [r14]
0x180047728  test    eax, eax
0x18004772a  jnz     short loc_18004773B
0x18004772c  xor     edi, edi
0x18004772e  test    ecx, ecx
0x180047730  jle     short loc_18004773B
0x180047732  mov     dword ptr [r14], 1
0x180047739  jmp     short loc_18004773E
0x18004773b  xor     r14d, r14d
0x18004773e  mov     [rbp+var_18], r14
0x180047742  mov     [rbp+var_20], edi
0x180047745  test    edi, edi
0x180047747  js      short loc_180047776
0x180047749  lea     rcx, [rsi+58h]
0x18004774d  mov     [rbp+arg_0], rbx
0x180047751  lea     r8, [rbp+arg_0]
0x180047755  lea     rdx, [rbp+arg_8]
0x180047759  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x18004775e  mov     edi, eax
0x180047760  test    eax, eax
0x180047762  js      loc_180047812
0x180047768  mov     r15, [rbp+arg_0]
0x18004776c  test    r15, r15
0x18004776f  jnz     short loc_180047785
0x180047771  mov     edi, 8000000Bh
0x180047776  xor     edx, edx
0x180047778  mov     ecx, edi
0x18004777a  call    cs:__imp_RoOriginateError
0x180047780  jmp     loc_180047812
0x180047785  lea     rcx, [rsi+0C0h]; this
0x18004778c  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180047791  mov     edi, eax
0x180047793  test    eax, eax
0x180047795  js      short loc_180047812
0x180047797  mov     rbx, [r15]
0x18004779a  xor     ecx, ecx; string
0x18004779c  call    cs:__imp_WindowsDeleteString
0x1800477a2  movups  xmm6, xmmword ptr [r15+8]
0x1800477a7  lea     rcx, [rbp+var_30]
0x1800477ab  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x1800477b0  movdqa  [rbp+var_30], xmm6
0x1800477b5  test    r15, r15
0x1800477b8  jz      short loc_180047804
0x1800477ba  mov     eax, [r15+20h]
0x1800477be  xor     edx, edx
0x1800477c0  div     dword ptr [rsi+70h]
0x1800477c3  mov     r9d, edx
0x1800477c6  mov     rdx, [rsi+60h]
0x1800477ca  mov     rax, [rdx+r9*8]
0x1800477ce  cmp     r15, rax
0x1800477d1  jnz     short loc_1800477DB
0x1800477d3  xor     eax, eax
0x1800477d5  jmp     short loc_1800477E1
0x1800477d7  mov     rax, [rax+18h]
0x1800477db  cmp     [rax+18h], r15
0x1800477df  jnz     short loc_1800477D7
0x1800477e1  mov     rcx, [r15+18h]
0x1800477e5  test    rax, rax
0x1800477e8  jnz     short loc_1800477F0
0x1800477ea  mov     [rdx+r9*8], rcx
0x1800477ee  jmp     short loc_1800477F4
0x1800477f0  mov     [rax+18h], rcx
0x1800477f4  mov     rdx, r15
0x1800477f7  lea     rcx, [rsi+58h]
0x1800477fb  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CNode *)
0x180047800  xor     edi, edi
0x180047802  jmp     short loc_180047812
0x180047804  xor     ebx, ebx
0x180047806  mov     edi, 8000FFFFh
0x18004780b  mov     qword ptr [rbp+var_30], rbx
0x18004780f  mov     byte ptr [rbp+var_30+8], bl
0x180047812  cmp     dword ptr [rsi+0B0h], 1
0x180047819  jnz     short loc_180047825
0x18004781b  add     dword ptr [r12], 10000000h
0x180047823  jmp     short loc_18004782E
0x180047825  mov     rcx, r12; SRWLock
0x180047828  call    cs:__imp_ReleaseSRWLockExclusive
0x18004782e  lea     rcx, [rbp+var_30]
0x180047832  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x180047837  mov     rcx, rbx; string
0x18004783a  call    cs:__imp_WindowsDeleteString
0x180047840  test    edi, edi
0x180047842  js      short loc_180047875
0x180047844  lea     rcx, [rsi+10h]
0x180047848  mov     rax, rsi
0x18004784b  neg     rax
0x18004784e  lea     rdx, [rsi+0D0h]; int
0x180047855  mov     rax, [rbp+arg_8]
0x180047859  mov     r9d, 2; int
0x18004785f  sbb     r8, r8
0x180047862  mov     [rsp+60h+string], rax; string
0x180047867  and     r8, rcx; int
0x18004786a  lea     rcx, [rbp+var_20]; int
0x18004786e  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$MapChangedEventHandler@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableMap@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@345@W4CollectionChange@345@PEAUHSTRING__@@@Z; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *,Windows::Foundation::Collections::CollectionChange,HSTRING__ *)
0x180047873  mov     edi, eax
0x180047875  test    r14, r14
0x180047878  jz      short loc_180047881
0x18004787a  mov     dword ptr [r14], 0
0x180047881  movaps  xmm6, [rsp+60h+var_10]
0x180047886  lea     r11, [rsp+60h+var_s0]
0x18004788b  mov     rbx, [r11+40h]
0x18004788f  mov     eax, edi
0x180047891  mov     rsi, [r11+48h]
0x180047895  mov     rsp, r11
0x180047898  pop     r15
0x18004789a  pop     r14
0x18004789c  pop     r12
0x18004789e  pop     rdi
0x18004789f  pop     rbp
0x1800478a0  retn
```
