# Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,CCaseInsensitiveStringEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>>::ReplaceAll(uint,HSTRING__ * *)

- ea: `0x180056ba0`
- end: `0x180056cf2`
- name: `?ReplaceAll@?$Vector@PEAUHSTRING__@@VCCaseInsensitiveStringEqualityPredicate@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$VectorOptions@PEAUHSTRING__@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUHSTRING__@@@Z`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180056b20`

## callees

- `0x180049b64`
- `0x180055744`
- `0x180056ba0`
- `0x18005a32c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056cb4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056cb4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180056bc8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180056bc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056c85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056c9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056c9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180056bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180056bea`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,CCaseInsensitiveStringEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>>::ReplaceAll(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  unsigned int v3; // ebx
  HSTRING *v6; // r14
  int v7; // edi
  __int64 v8; // rsi
  int v9; // eax
  HSTRING *v10; // rax
  RTL_SRWLOCK *v11; // rcx
  __int64 i; // r15
  RTL_SRWLOCK *v14; // [rsp+30h] [rbp-48h] BYREF
  HRESULT v15; // [rsp+98h] [rbp+20h] BYREF

  v3 = a2;
  v15 = 0;
  if ( a2 )
  {
    v6 = (HSTRING *)malloc(8LL * a2);
    if ( !v6 )
    {
      v7 = -2147024882;
      goto LABEL_19;
    }
    v8 = 0;
    while ( 1 )
    {
      v15 = WindowsDuplicateString(*(HSTRING *)(a3 + 8 * v8), &v6[v8]);
      v7 = v15;
      if ( v15 < 0 )
        break;
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= v3 )
        goto LABEL_9;
    }
  }
  else
  {
    LODWORD(v8) = 0;
    v6 = 0;
    v3 = 0;
LABEL_9:
    XWinRT::SerializingLockPolicy::Write(&v14, a1 + 112, &v15);
    v7 = v15;
    if ( v15 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v15, *(unsigned __int8 *)(a1 + 133), a1 + 136);
      v9 = *(_DWORD *)(a1 + 80);
      v7 = 0;
      *(_DWORD *)(a1 + 80) = v8;
      LODWORD(v8) = v9;
      *(_DWORD *)(a1 + 84) = v3;
      v10 = *(HSTRING **)(a1 + 96);
      *(_QWORD *)(a1 + 96) = v6;
      v6 = v10;
      ++*(_DWORD *)(a1 + 128);
    }
    if ( v14 )
    {
      v11 = v14 + 1;
      if ( LODWORD(v14->Ptr) == 1 )
        LODWORD(v11->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v11);
    }
  }
  if ( v6 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v8; i = (unsigned int)(i + 1) )
    {
      WindowsDeleteString(v6[i]);
      v6[i] = 0;
    }
    free(v6);
  }
LABEL_19:
  if ( v7 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>::RaiseEvent(
                           (unsigned __int8)v15,
                           *(unsigned __int8 *)(a1 + 132),
                           a1,
                           0,
                           0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180056ba0  mov     rax, rsp
0x180056ba3  push    rbx
0x180056ba4  push    rbp
0x180056ba5  push    rsi
0x180056ba6  push    rdi
0x180056ba7  push    r14
0x180056ba9  push    r15
0x180056bab  sub     rsp, 48h
0x180056baf  mov     ebx, edx
0x180056bb1  mov     r15, r8
0x180056bb4  mov     dword ptr [rax+20h], 0
0x180056bbb  mov     rbp, rcx
0x180056bbe  test    edx, edx
0x180056bc0  jz      short loc_180056C09
0x180056bc2  mov     ecx, ebx
0x180056bc4  shl     rcx, 3; Size
0x180056bc8  call    cs:__imp_malloc
0x180056bce  mov     r14, rax
0x180056bd1  test    rax, rax
0x180056bd4  jnz     short loc_180056BE0
0x180056bd6  mov     edi, 8007000Eh
0x180056bdb  jmp     loc_180056CBA
0x180056be0  xor     esi, esi
0x180056be2  mov     rcx, [r15+rsi*8]; string
0x180056be6  lea     rdx, [r14+rsi*8]; newString
0x180056bea  call    cs:__imp_WindowsDuplicateString
0x180056bf0  mov     [rsp+78h+arg_18], eax
0x180056bf7  mov     edi, eax
0x180056bf9  test    eax, eax
0x180056bfb  js      loc_180056C8B
0x180056c01  inc     esi
0x180056c03  cmp     esi, ebx
0x180056c05  jb      short loc_180056BE2
0x180056c07  jmp     short loc_180056C10
0x180056c09  xor     esi, esi
0x180056c0b  xor     r14d, r14d
0x180056c0e  xor     ebx, ebx
0x180056c10  lea     rdx, [rbp+70h]
0x180056c14  lea     r8, [rsp+78h+arg_18]
0x180056c1c  lea     rcx, [rsp+78h+var_48]
0x180056c21  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180056c26  mov     edi, [rsp+78h+arg_18]
0x180056c2d  test    edi, edi
0x180056c2f  js      short loc_180056C6A
0x180056c31  movzx   edx, byte ptr [rbp+85h]
0x180056c38  lea     r8, [rbp+88h]
0x180056c3f  lea     rcx, [rsp+78h+arg_18]
0x180056c47  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180056c4c  mov     eax, [rbp+50h]
0x180056c4f  xor     edi, edi
0x180056c51  mov     [rbp+50h], esi
0x180056c54  mov     esi, eax
0x180056c56  mov     [rbp+54h], ebx
0x180056c59  mov     rax, [rbp+60h]
0x180056c5d  mov     [rbp+60h], r14
0x180056c61  mov     r14, rax
0x180056c64  inc     dword ptr [rbp+80h]
0x180056c6a  mov     rax, [rsp+78h+var_48]
0x180056c6f  test    rax, rax
0x180056c72  jz      short loc_180056C8B
0x180056c74  cmp     dword ptr [rax], 1
0x180056c77  lea     rcx, [rax+8]; SRWLock
0x180056c7b  jnz     short loc_180056C85
0x180056c7d  add     dword ptr [rcx], 10000000h
0x180056c83  jmp     short loc_180056C8B
0x180056c85  call    cs:__imp_ReleaseSRWLockExclusive
0x180056c8b  test    r14, r14
0x180056c8e  jz      short loc_180056CBA
0x180056c90  xor     r15d, r15d
0x180056c93  test    esi, esi
0x180056c95  jz      short loc_180056CB1
0x180056c97  mov     rcx, [r14+r15*8]; string
0x180056c9b  call    cs:__imp_WindowsDeleteString
0x180056ca1  mov     qword ptr [r14+r15*8], 0
0x180056ca9  inc     r15d
0x180056cac  cmp     r15d, esi
0x180056caf  jb      short loc_180056C97
0x180056cb1  mov     rcx, r14; Block
0x180056cb4  call    cs:__imp_free
0x180056cba  test    edi, edi
0x180056cbc  js      short loc_180056CE3
0x180056cbe  movzx   edx, byte ptr [rbp+84h]
0x180056cc5  xor     r9d, r9d
0x180056cc8  movzx   ecx, byte ptr [rsp+78h+arg_18]
0x180056cd0  mov     r8, rbp
0x180056cd3  mov     [rsp+78h+var_58], 0
0x180056cdc  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,1,0>::RaiseEvent(...)
0x180056ce1  mov     edi, eax
0x180056ce3  mov     eax, edi
0x180056ce5  add     rsp, 48h
0x180056ce9  pop     r15
0x180056ceb  pop     r14
0x180056ced  pop     rdi
0x180056cee  pop     rsi
0x180056cef  pop     rbp
0x180056cf0  pop     rbx
0x180056cf1  retn
```
