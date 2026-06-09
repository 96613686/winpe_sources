# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x180047300`
- end: `0x1800474b2`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800130bc`
- `0x180020e1c`
- `0x18002b318`
- `0x18003b2d8`
- `0x1800438c4`
- `0x180047300`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800473d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800473d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047469`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180047330`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800473b3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180047330`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800473b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004744a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004744a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047360`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047360`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // esi
  HSTRING v4; // rdi
  __int64 v5; // rbx
  RTL_SRWLOCK *v6; // r15
  __int64 v7; // r14
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF

  v14 = a2;
  if ( *(_BYTE *)(a1 + 152) )
  {
    v4 = 0;
    v5 = 0;
    v6 = (RTL_SRWLOCK *)(a1 + 136);
    if ( *(_DWORD *)(a1 + 128) == 1 )
    {
      if ( !LODWORD(v6->Ptr) )
        LODWORD(v6->Ptr) = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v13, *(unsigned __int8 *)(a1 + 154), a1 + 156);
    v13 = 0;
    v3 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(
           a1 + 40,
           &v14,
           &v13);
    if ( v3 >= 0 )
    {
      v7 = v13;
      if ( v13 )
      {
        v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
        if ( v3 >= 0 )
        {
          v4 = *(HSTRING *)v7;
          WindowsDeleteString(0);
          if ( v7 )
          {
            v5 = *(_QWORD *)(v7 + 8);
            v8 = (unsigned int)(*(_DWORD *)(v7 + 24) % *(_DWORD *)(a1 + 64));
            v9 = *(_QWORD *)(a1 + 48);
            v10 = *(_QWORD *)(v9 + 8 * v8);
            if ( v7 == v10 )
            {
              v10 = 0;
            }
            else
            {
              while ( *(_QWORD *)(v10 + 16) != v7 )
                v10 = *(_QWORD *)(v10 + 16);
            }
            v11 = *(_QWORD *)(v7 + 16);
            if ( v10 )
              *(_QWORD *)(v10 + 16) = v11;
            else
              *(_QWORD *)(v9 + 8 * v8) = v11;
            XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(
              a1 + 40,
              v7);
            v3 = 0;
          }
          else
          {
            v3 = -2147418113;
            v4 = 0;
            v5 = 0;
          }
        }
      }
      else
      {
        v3 = -2147483637;
        RoOriginateError(2147483659LL, 0);
      }
    }
    if ( *(_DWORD *)(a1 + 128) == 1 )
      LODWORD(v6->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v6);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    WindowsDeleteString(v4);
    if ( v3 >= 0 )
      return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
                             (unsigned __int8)v13,
                             *(unsigned __int8 *)(a1 + 153),
                             a1,
                             2,
                             v14);
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
0x180047300  mov     [rsp+arg_10], rbx
0x180047305  mov     [rsp+arg_18], rbp
0x18004730a  mov     [rsp+arg_8], rdx
0x18004730f  push    rsi
0x180047310  push    rdi
0x180047311  push    r13
0x180047313  push    r14
0x180047315  push    r15
0x180047317  sub     rsp, 30h
0x18004731b  mov     rbp, rcx
0x18004731e  cmp     byte ptr [rcx+98h], 0
0x180047325  jnz     short loc_18004733B
0x180047327  xor     edx, edx
0x180047329  mov     esi, 8000FFFFh
0x18004732e  mov     ecx, esi
0x180047330  call    cs:__imp_RoOriginateError
0x180047336  jmp     loc_180047499
0x18004733b  xor     edi, edi
0x18004733d  xor     ebx, ebx
0x18004733f  lea     r15, [rcx+88h]
0x180047346  cmp     dword ptr [rcx+80h], 1
0x18004734d  jnz     short loc_18004735D
0x18004734f  cmp     [r15], ebx
0x180047352  jnz     short loc_180047366
0x180047354  mov     dword ptr [r15], 0F0000000h
0x18004735b  jmp     short loc_180047366
0x18004735d  mov     rcx, r15; SRWLock
0x180047360  call    cs:__imp_AcquireSRWLockExclusive
0x180047366  lea     r8, [rbp+9Ch]
0x18004736d  movzx   edx, byte ptr [rbp+9Ah]
0x180047374  lea     rcx, [rsp+58h+arg_0]
0x180047379  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18004737e  mov     [rsp+58h+arg_0], rbx
0x180047383  lea     r8, [rsp+58h+arg_0]
0x180047388  lea     rdx, [rsp+58h+arg_8]
0x18004738d  lea     rcx, [rbp+28h]
0x180047391  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x180047396  mov     esi, eax
0x180047398  test    eax, eax
0x18004739a  js      loc_180047435
0x1800473a0  mov     r14, [rsp+58h+arg_0]
0x1800473a5  test    r14, r14
0x1800473a8  jnz     short loc_1800473BB
0x1800473aa  xor     edx, edx
0x1800473ac  mov     esi, 8000000Bh
0x1800473b1  mov     ecx, esi
0x1800473b3  call    cs:__imp_RoOriginateError
0x1800473b9  jmp     short loc_180047435
0x1800473bb  lea     rcx, [rbp+90h]; this
0x1800473c2  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800473c7  mov     esi, eax
0x1800473c9  test    eax, eax
0x1800473cb  js      short loc_180047435
0x1800473cd  mov     rdi, [r14]
0x1800473d0  xor     ecx, ecx; string
0x1800473d2  call    cs:__imp_WindowsDeleteString
0x1800473d8  nop
0x1800473d9  test    r14, r14
0x1800473dc  jz      short loc_18004742C
0x1800473de  mov     rbx, [r14+8]
0x1800473e2  xor     edx, edx
0x1800473e4  mov     eax, [r14+18h]
0x1800473e8  div     dword ptr [rbp+40h]
0x1800473eb  mov     r8d, edx
0x1800473ee  mov     rdx, [rbp+30h]
0x1800473f2  mov     rax, [rdx+r8*8]
0x1800473f6  cmp     r14, rax
0x1800473f9  jnz     short loc_180047403
0x1800473fb  xor     eax, eax
0x1800473fd  jmp     short loc_180047409
0x1800473ff  mov     rax, [rax+10h]
0x180047403  cmp     [rax+10h], r14
0x180047407  jnz     short loc_1800473FF
0x180047409  mov     rcx, [r14+10h]
0x18004740d  test    rax, rax
0x180047410  jnz     short loc_180047418
0x180047412  mov     [rdx+r8*8], rcx
0x180047416  jmp     short loc_18004741C
0x180047418  mov     [rax+10h], rcx
0x18004741c  mov     rdx, r14
0x18004741f  lea     rcx, [rbp+28h]
0x180047423  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CNode *)
0x180047428  xor     esi, esi
0x18004742a  jmp     short loc_180047435
0x18004742c  mov     esi, 8000FFFFh
0x180047431  xor     edi, edi
0x180047433  xor     ebx, ebx
0x180047435  cmp     dword ptr [rbp+80h], 1
0x18004743c  jnz     short loc_180047447
0x18004743e  add     dword ptr [r15], 10000000h
0x180047445  jmp     short loc_180047451
0x180047447  mov     rcx, r15; SRWLock
0x18004744a  call    cs:__imp_ReleaseSRWLockExclusive
0x180047450  nop
0x180047451  test    rbx, rbx
0x180047454  jz      short loc_180047466
0x180047456  mov     rax, [rbx]
0x180047459  mov     rcx, rbx
0x18004745c  mov     rax, [rax+10h]
0x180047460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047465  nop
0x180047466  mov     rcx, rdi; string
0x180047469  call    cs:__imp_WindowsDeleteString
0x18004746f  test    esi, esi
0x180047471  js      short loc_180047499
0x180047473  mov     rax, [rsp+58h+arg_8]
0x180047478  mov     [rsp+58h+var_38], rax
0x18004747d  mov     r9d, 2
0x180047483  mov     r8, rbp
0x180047486  movzx   edx, byte ptr [rbp+99h]
0x18004748d  movzx   ecx, byte ptr [rsp+58h+arg_0]
0x180047492  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180047497  mov     esi, eax
0x180047499  mov     eax, esi
0x18004749b  mov     rbx, [rsp+58h+arg_10]
0x1800474a0  mov     rbp, [rsp+58h+arg_18]
0x1800474a5  add     rsp, 30h
0x1800474a9  pop     r15
0x1800474ab  pop     r14
0x1800474ad  pop     r13
0x1800474af  pop     rdi
0x1800474b0  pop     rsi
0x1800474b1  retn
```
