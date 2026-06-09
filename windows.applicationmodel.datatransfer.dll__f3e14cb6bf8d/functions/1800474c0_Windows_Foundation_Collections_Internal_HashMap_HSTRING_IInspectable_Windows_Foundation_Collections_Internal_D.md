# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)

- ea: `0x1800474c0`
- end: `0x180047687`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800478b0`

## callees

- `0x180008ae4`
- `0x1800130bc`
- `0x180020e1c`
- `0x18002b3a0`
- `0x18003b33c`
- `0x1800438c4`
- `0x1800474c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004759c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004759c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047639`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800474f7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004757a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800474f7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004757a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047627`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047627`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004752c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004752c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // edi
  HSTRING v4; // rbx
  RTL_SRWLOCK *v5; // r15
  bool v6; // zf
  __int64 v7; // r14
  __int128 v8; // xmm6
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int128 v14; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15; // [rsp+80h] [rbp+30h] BYREF
  __int64 v16; // [rsp+88h] [rbp+38h] BYREF

  v16 = a2;
  if ( *(_BYTE *)(a1 + 184) )
  {
    v4 = 0;
    v5 = (RTL_SRWLOCK *)(a1 + 168);
    v6 = *(_DWORD *)(a1 + 160) == 1;
    *(_QWORD *)&v14 = 0;
    BYTE8(v14) = 0;
    if ( v6 )
    {
      if ( !LODWORD(v5->Ptr) )
        LODWORD(v5->Ptr) = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 168));
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v15, *(unsigned __int8 *)(a1 + 186), a1 + 188);
    v15 = 0;
    v3 = XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(
           a1 + 72,
           &v16,
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
          v8 = *(_OWORD *)(v7 + 8);
          XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v14);
          v14 = v8;
          if ( v7 )
          {
            v9 = (unsigned int)(*(_DWORD *)(v7 + 32) % *(_DWORD *)(a1 + 96));
            v10 = *(_QWORD *)(a1 + 80);
            v11 = *(_QWORD *)(v10 + 8 * v9);
            if ( v7 == v11 )
            {
              v11 = 0;
            }
            else
            {
              while ( *(_QWORD *)(v11 + 24) != v7 )
                v11 = *(_QWORD *)(v11 + 24);
            }
            v12 = *(_QWORD *)(v7 + 24);
            if ( v11 )
              *(_QWORD *)(v11 + 24) = v12;
            else
              *(_QWORD *)(v10 + 8 * v9) = v12;
            XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::FreeNode(
              a1 + 72,
              v7);
            v3 = 0;
          }
          else
          {
            v4 = 0;
            v3 = -2147418113;
            *(_QWORD *)&v14 = 0;
            BYTE8(v14) = 0;
          }
        }
      }
      else
      {
        v3 = -2147483637;
        RoOriginateError(2147483659LL, 0);
      }
    }
    if ( *(_DWORD *)(a1 + 160) == 1 )
      LODWORD(v5->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v5);
    XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(&v14);
    WindowsDeleteString(v4);
    if ( v3 >= 0 )
      return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                             (unsigned __int8)v15,
                             *(unsigned __int8 *)(a1 + 185),
                             a1,
                             2,
                             v16);
  }
  else
  {
    v3 = -2147418113;
    RoOriginateError(2147549183LL, 0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800474c0  mov     rax, rsp
0x1800474c3  mov     [rax+18h], rbx
0x1800474c7  mov     [rax+20h], rsi
0x1800474cb  mov     [rax+10h], rdx
0x1800474cf  push    rbp
0x1800474d0  push    rdi
0x1800474d1  push    r13
0x1800474d3  push    r14
0x1800474d5  push    r15
0x1800474d7  mov     rbp, rsp
0x1800474da  sub     rsp, 50h
0x1800474de  cmp     byte ptr [rcx+0B8h], 0
0x1800474e5  mov     rsi, rcx
0x1800474e8  movaps  xmmword ptr [rax-38h], xmm6
0x1800474ec  jnz     short loc_180047502
0x1800474ee  mov     edi, 8000FFFFh
0x1800474f3  xor     edx, edx
0x1800474f5  mov     ecx, edi
0x1800474f7  call    cs:__imp_RoOriginateError
0x1800474fd  jmp     loc_180047667
0x180047502  xor     ebx, ebx
0x180047504  lea     r15, [rcx+0A8h]
0x18004750b  cmp     dword ptr [rcx+0A0h], 1
0x180047512  mov     qword ptr [rbp+var_20], rbx
0x180047516  mov     byte ptr [rbp+var_20+8], bl
0x180047519  jnz     short loc_180047529
0x18004751b  cmp     [r15], ebx
0x18004751e  jnz     short loc_180047532
0x180047520  mov     dword ptr [r15], 0F0000000h
0x180047527  jmp     short loc_180047532
0x180047529  mov     rcx, r15; SRWLock
0x18004752c  call    cs:__imp_AcquireSRWLockExclusive
0x180047532  movzx   edx, byte ptr [rsi+0BAh]
0x180047539  lea     r8, [rsi+0BCh]
0x180047540  lea     rcx, [rbp+arg_0]
0x180047544  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180047549  lea     r8, [rbp+arg_0]
0x18004754d  mov     [rbp+arg_0], rbx
0x180047551  lea     rdx, [rbp+arg_8]
0x180047555  lea     rcx, [rsi+48h]
0x180047559  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CPair * *)
0x18004755e  mov     edi, eax
0x180047560  test    eax, eax
0x180047562  js      loc_180047612
0x180047568  mov     r14, [rbp+arg_0]
0x18004756c  test    r14, r14
0x18004756f  jnz     short loc_180047585
0x180047571  mov     edi, 8000000Bh
0x180047576  xor     edx, edx
0x180047578  mov     ecx, edi
0x18004757a  call    cs:__imp_RoOriginateError
0x180047580  jmp     loc_180047612
0x180047585  lea     rcx, [rsi+0B0h]; this
0x18004758c  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180047591  mov     edi, eax
0x180047593  test    eax, eax
0x180047595  js      short loc_180047612
0x180047597  mov     rbx, [r14]
0x18004759a  xor     ecx, ecx; string
0x18004759c  call    cs:__imp_WindowsDeleteString
0x1800475a2  movups  xmm6, xmmword ptr [r14+8]
0x1800475a7  lea     rcx, [rbp+var_20]
0x1800475ab  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x1800475b0  movdqa  [rbp+var_20], xmm6
0x1800475b5  test    r14, r14
0x1800475b8  jz      short loc_180047604
0x1800475ba  mov     eax, [r14+20h]
0x1800475be  xor     edx, edx
0x1800475c0  div     dword ptr [rsi+60h]
0x1800475c3  mov     r8d, edx
0x1800475c6  mov     rdx, [rsi+50h]
0x1800475ca  mov     rax, [rdx+r8*8]
0x1800475ce  cmp     r14, rax
0x1800475d1  jnz     short loc_1800475DB
0x1800475d3  xor     eax, eax
0x1800475d5  jmp     short loc_1800475E1
0x1800475d7  mov     rax, [rax+18h]
0x1800475db  cmp     [rax+18h], r14
0x1800475df  jnz     short loc_1800475D7
0x1800475e1  mov     rcx, [r14+18h]
0x1800475e5  test    rax, rax
0x1800475e8  jnz     short loc_1800475F0
0x1800475ea  mov     [rdx+r8*8], rcx
0x1800475ee  jmp     short loc_1800475F4
0x1800475f0  mov     [rax+18h], rcx
0x1800475f4  mov     rdx, r14
0x1800475f7  lea     rcx, [rsi+48h]
0x1800475fb  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::CNode *)
0x180047600  xor     edi, edi
0x180047602  jmp     short loc_180047612
0x180047604  xor     ebx, ebx
0x180047606  mov     edi, 8000FFFFh
0x18004760b  mov     qword ptr [rbp+var_20], rbx
0x18004760f  mov     byte ptr [rbp+var_20+8], bl
0x180047612  cmp     dword ptr [rsi+0A0h], 1
0x180047619  jnz     short loc_180047624
0x18004761b  add     dword ptr [r15], 10000000h
0x180047622  jmp     short loc_18004762D
0x180047624  mov     rcx, r15; SRWLock
0x180047627  call    cs:__imp_ReleaseSRWLockExclusive
0x18004762d  lea     rcx, [rbp+var_20]
0x180047631  call    ??$Destroy@UIRandomAccessStreamReference@Streams@Storage@Windows@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAV?$GitStorageType@UIRandomAccessStreamReference@Streams@Storage@Windows@@@detail@1@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<Windows::Storage::Streams::IRandomAccessStreamReference>(XWinRT::detail::GitStorageType<Windows::Storage::Streams::IRandomAccessStreamReference> *)
0x180047636  mov     rcx, rbx; string
0x180047639  call    cs:__imp_WindowsDeleteString
0x18004763f  test    edi, edi
0x180047641  js      short loc_180047667
0x180047643  mov     rax, [rbp+arg_8]
0x180047647  mov     r9d, 2
0x18004764d  movzx   edx, byte ptr [rsi+0B9h]
0x180047654  mov     r8, rsi
0x180047657  movzx   ecx, byte ptr [rbp+arg_0]
0x18004765b  mov     [rsp+50h+var_30], rax
0x180047660  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180047665  mov     edi, eax
0x180047667  movaps  xmm6, [rsp+50h+var_10]
0x18004766c  lea     r11, [rsp+50h+var_s0]
0x180047671  mov     rbx, [r11+40h]
0x180047675  mov     eax, edi
0x180047677  mov     rsi, [r11+48h]
0x18004767b  mov     rsp, r11
0x18004767e  pop     r15
0x180047680  pop     r14
0x180047682  pop     r13
0x180047684  pop     rdi
0x180047685  pop     rbp
0x180047686  retn
```
