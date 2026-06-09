# Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,CCaseInsensitiveStringEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>>::RemoveAtInternal(uint,bool)

- ea: `0x1800569a0`
- end: `0x180056b14`
- name: `?RemoveAtInternal@?$Vector@PEAUHSTRING__@@VCCaseInsensitiveStringEqualityPredicate@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$VectorOptions@PEAUHSTRING__@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `372`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180056940`
- `0x180056960`
- `0x180056970`
- `0x180056990`

## callees

- `0x180049b64`
- `0x180055744`
- `0x1800569a0`
- `0x180056d84`
- `0x18005a32c`
- `0x18005bfec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056ace`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056ad7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056ad7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800569fb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180056a6c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800569fb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180056a6c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,CCaseInsensitiveStringEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>>::RemoveAtInternal(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  int v6; // ebx
  HSTRING v7; // r14
  unsigned int *v8; // rsi
  unsigned int v9; // r9d
  unsigned int v10; // r8d
  RTL_SRWLOCK *v11; // rcx
  int v13; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v14; // [rsp+78h] [rbp+20h] BYREF

  v13 = 0;
  XWinRT::SerializingLockPolicy::Write(&v14, a1 + 112, &v13);
  v6 = v13;
  v7 = 0;
  if ( v13 >= 0 )
  {
    v8 = (unsigned int *)(a1 + 80);
    if ( a3 )
      a2 = *v8 - 1;
    if ( a2 >= *v8 )
    {
      v6 = -2147483637;
      RoOriginateError(2147483659LL, 0);
    }
    if ( v6 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v13, *(unsigned __int8 *)(a1 + 133), a1 + 136);
      v6 = 0;
      v7 = *(HSTRING *)(*(_QWORD *)(a1 + 96) + 8LL * a2);
      WindowsDeleteString(0);
      if ( a2 < *v8 - 1
        && memmove_s(
             (void *const)(*(_QWORD *)(a1 + 96) + 8LL * a2),
             8LL * (*v8 - a2 - 1),
             (const void *const)(*(_QWORD *)(a1 + 96) + 8LL * (a2 + 1)),
             8LL * (*v8 - a2 - 1)) )
      {
        v6 = -2147418113;
        RoOriginateError(2147549183LL, 0);
      }
      else
      {
        v9 = *(_DWORD *)(a1 + 84);
        ++*(_DWORD *)(a1 + 128);
        if ( --*v8 < v9 / 3 )
        {
          v10 = 1;
          if ( v9 - 1 >= v9 - v9 / 3 )
            v10 = v9 / 3;
          v6 = Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,CCaseInsensitiveStringEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>>::ResizeStorage(
                 a1,
                 v9 - v10);
        }
      }
    }
  }
  if ( v14 )
  {
    v11 = v14 + 1;
    if ( LODWORD(v14->Ptr) == 1 )
      LODWORD(v11->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v11);
  }
  WindowsDeleteString(v7);
  if ( v6 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>::RaiseEvent(
                           (unsigned __int8)v13,
                           *(unsigned __int8 *)(a1 + 132),
                           a1,
                           2,
                           a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800569a0  mov     rax, rsp
0x1800569a3  mov     [rax+10h], rbx
0x1800569a7  push    rbp
0x1800569a8  push    rsi
0x1800569a9  push    rdi
0x1800569aa  push    r14
0x1800569ac  push    r15
0x1800569ae  sub     rsp, 30h
0x1800569b2  mov     ebp, edx
0x1800569b4  mov     dword ptr [rax+8], 0
0x1800569bb  lea     rdx, [rcx+70h]
0x1800569bf  mov     r15b, r8b
0x1800569c2  mov     rdi, rcx
0x1800569c5  lea     r8, [rax+8]
0x1800569c9  lea     rcx, [rax+20h]
0x1800569cd  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800569d2  mov     ebx, [rsp+58h+arg_0]
0x1800569d6  xor     r14d, r14d
0x1800569d9  test    ebx, ebx
0x1800569db  js      loc_180056AB3
0x1800569e1  lea     rsi, [rdi+50h]
0x1800569e5  test    r15b, r15b
0x1800569e8  jz      short loc_1800569EE
0x1800569ea  mov     ebp, [rsi]
0x1800569ec  dec     ebp
0x1800569ee  cmp     ebp, [rsi]
0x1800569f0  jb      short loc_180056A01
0x1800569f2  mov     ebx, 8000000Bh
0x1800569f7  xor     edx, edx
0x1800569f9  mov     ecx, ebx
0x1800569fb  call    cs:__imp_RoOriginateError
0x180056a01  test    ebx, ebx
0x180056a03  js      loc_180056AB3
0x180056a09  movzx   edx, byte ptr [rdi+85h]
0x180056a10  lea     r8, [rdi+88h]
0x180056a17  lea     rcx, [rsp+58h+arg_0]
0x180056a1c  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180056a21  mov     rax, [rdi+60h]
0x180056a25  xor     ecx, ecx; string
0x180056a27  mov     r15d, ebp
0x180056a2a  xor     ebx, ebx
0x180056a2c  mov     r14, [rax+r15*8]
0x180056a30  call    cs:__imp_WindowsDeleteString
0x180056a36  mov     ecx, [rsi]
0x180056a38  lea     eax, [rcx-1]
0x180056a3b  cmp     ebp, eax
0x180056a3d  jnb     short loc_180056A74
0x180056a3f  mov     r9, [rdi+60h]
0x180056a43  lea     eax, [rbp+1]
0x180056a46  sub     ecx, ebp
0x180056a48  lea     r8, [r9+rax*8]; Source
0x180056a4c  lea     edx, [rcx-1]
0x180056a4f  shl     rdx, 3; DestinationSize
0x180056a53  lea     rcx, [r9+r15*8]; Destination
0x180056a57  mov     r9, rdx; SourceSize
0x180056a5a  call    memmove_s
0x180056a5f  test    eax, eax
0x180056a61  jz      short loc_180056A74
0x180056a63  mov     ebx, 8000FFFFh
0x180056a68  xor     edx, edx
0x180056a6a  mov     ecx, ebx
0x180056a6c  call    cs:__imp_RoOriginateError
0x180056a72  jmp     short loc_180056AB3
0x180056a74  mov     r9d, [rdi+54h]
0x180056a78  mov     eax, 0AAAAAAABh
0x180056a7d  inc     dword ptr [rdi+80h]
0x180056a83  dec     dword ptr [rsi]
0x180056a85  mul     r9d
0x180056a88  shr     edx, 1
0x180056a8a  cmp     [rsi], edx
0x180056a8c  jnb     short loc_180056AB3
0x180056a8e  mov     ecx, r9d
0x180056a91  lea     eax, [r9-1]
0x180056a95  sub     ecx, edx
0x180056a97  mov     r8d, 1
0x180056a9d  cmp     eax, ecx
0x180056a9f  mov     rcx, rdi
0x180056aa2  cmovnb  r8d, edx
0x180056aa6  sub     r9d, r8d
0x180056aa9  mov     edx, r9d
0x180056aac  call    ?ResizeStorage@?$Vector@PEAUHSTRING__@@VCCaseInsensitiveStringEqualityPredicate@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$VectorOptions@PEAUHSTRING__@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,CCaseInsensitiveStringEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>>::ResizeStorage(uint)
0x180056ab1  mov     ebx, eax
0x180056ab3  mov     rax, [rsp+58h+arg_18]
0x180056ab8  test    rax, rax
0x180056abb  jz      short loc_180056AD4
0x180056abd  cmp     dword ptr [rax], 1
0x180056ac0  lea     rcx, [rax+8]; SRWLock
0x180056ac4  jnz     short loc_180056ACE
0x180056ac6  add     dword ptr [rcx], 10000000h
0x180056acc  jmp     short loc_180056AD4
0x180056ace  call    cs:__imp_ReleaseSRWLockExclusive
0x180056ad4  mov     rcx, r14; string
0x180056ad7  call    cs:__imp_WindowsDeleteString
0x180056add  test    ebx, ebx
0x180056adf  js      short loc_180056B01
0x180056ae1  movzx   edx, byte ptr [rdi+84h]
0x180056ae8  mov     r9d, 2
0x180056aee  movzx   ecx, byte ptr [rsp+58h+arg_0]
0x180056af3  mov     r8, rdi
0x180056af6  mov     [rsp+58h+var_38], ebp
0x180056afa  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>::RaiseEvent(...)
0x180056aff  mov     ebx, eax
0x180056b01  mov     eax, ebx
0x180056b03  mov     rbx, [rsp+58h+arg_8]
0x180056b08  add     rsp, 30h
0x180056b0c  pop     r15
0x180056b0e  pop     r14
0x180056b10  pop     rdi
0x180056b11  pop     rsi
0x180056b12  pop     rbp
0x180056b13  retn
```
