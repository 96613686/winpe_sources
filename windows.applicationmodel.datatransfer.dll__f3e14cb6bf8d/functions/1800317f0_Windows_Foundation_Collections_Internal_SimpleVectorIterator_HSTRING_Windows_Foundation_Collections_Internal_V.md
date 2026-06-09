# Windows::Foundation::Collections::Internal::SimpleVectorIterator<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,XWinRT::IntVersionTag,1>::GetMany(uint,HSTRING__ * *,uint *)

- ea: `0x1800317f0`
- end: `0x180031918`
- name: `?GetMany@?$SimpleVectorIterator@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUHSTRING__@@PEAI@Z`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000346c`
- `0x1800317f0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031889`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800318e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031889`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800318e0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180031832`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800318ce`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180031832`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800318ce`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800318fc`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800318fc`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorIterator<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,XWinRT::IntVersionTag,1>::GetMany(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int *a4)
{
  unsigned int v4; // ebp
  int v9; // ebx
  __int64 v10; // r13
  unsigned __int32 v11; // r12d
  bool v12; // zf
  signed __int32 v13; // eax
  __int64 v14; // rbx
  unsigned int i; // esi
  __int64 v16; // rbx

  v4 = 0;
  *a4 = 0;
  if ( a2 )
    memset_0(a3, 0, 8LL * a2);
  v9 = *(_DWORD *)(a1 + 80);
  if ( v9 >= 0 )
  {
    v10 = *(_QWORD *)(a1 + 64);
    v11 = *(_DWORD *)(a1 + 72);
    while ( 1 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *, unsigned int *))(**(_QWORD **)(a1 + 64) + 128LL))(
             *(_QWORD *)(a1 + 64),
             v11,
             a2,
             a3,
             a4);
      if ( v9 < 0 )
        break;
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 72), v11 + *a4, v11);
      v12 = v11 == v13;
      v11 = v13;
      if ( v12 )
        break;
      if ( *a4 )
      {
        do
        {
          v14 = v4;
          WindowsDeleteString(*((HSTRING *)a3 + v4++));
          *((_QWORD *)a3 + v14) = 0;
        }
        while ( v4 < *a4 );
      }
      v4 = 0;
      *a4 = 0;
    }
    if ( *(_DWORD *)(a1 + 84) != (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(v10 + 40) + 24LL))(v10 + 40) )
    {
      *(_DWORD *)(a1 + 80) = -2147483636;
      if ( v9 < 0 )
      {
        RoTransformError((unsigned int)v9, 2147483660LL, 0);
      }
      else
      {
        RoOriginateError(2147483660LL, 0);
        for ( i = 0; i < *a4; *((_QWORD *)a3 + v16) = 0 )
        {
          v16 = i;
          WindowsDeleteString(*((HSTRING *)a3 + i++));
        }
        *a4 = 0;
      }
      return (unsigned int)-2147483636;
    }
  }
  else
  {
    RoOriginateError((unsigned int)v9, 0);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800317f0  push    rbx
0x1800317f2  push    rbp
0x1800317f3  push    rsi
0x1800317f4  push    rdi
0x1800317f5  push    r12
0x1800317f7  push    r13
0x1800317f9  push    r14
0x1800317fb  push    r15
0x1800317fd  sub     rsp, 38h
0x180031801  xor     ebp, ebp
0x180031803  mov     r15d, edx
0x180031806  mov     [r9], ebp
0x180031809  mov     rdi, r9
0x18003180c  mov     r14, r8
0x18003180f  mov     rsi, rcx
0x180031812  test    edx, edx
0x180031814  jz      short loc_180031827
0x180031816  mov     r8d, r15d
0x180031819  xor     edx, edx; Val
0x18003181b  shl     r8, 3; Size
0x18003181f  mov     rcx, r14; void *
0x180031822  call    memset_0
0x180031827  mov     ebx, [rsi+50h]
0x18003182a  test    ebx, ebx
0x18003182c  jns     short loc_18003183D
0x18003182e  xor     edx, edx
0x180031830  mov     ecx, ebx
0x180031832  call    cs:__imp_RoOriginateError
0x180031838  jmp     loc_180031905
0x18003183d  mov     r13, [rsi+40h]
0x180031841  mov     r12d, [rsi+48h]
0x180031845  mov     rcx, [rsi+40h]
0x180031849  mov     r9, r14
0x18003184c  mov     r8d, r15d
0x18003184f  mov     [rsp+78h+var_58], rdi
0x180031854  mov     edx, r12d
0x180031857  mov     rax, [rcx]
0x18003185a  mov     rax, [rax+80h]
0x180031861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031866  mov     ebx, eax
0x180031868  test    eax, eax
0x18003186a  js      short loc_1800318A6
0x18003186c  mov     ecx, [rdi]
0x18003186e  mov     eax, r12d
0x180031871  add     ecx, r12d
0x180031874  lock cmpxchg [rsi+48h], ecx
0x180031879  mov     r12d, eax
0x18003187c  jz      short loc_1800318A6
0x18003187e  cmp     dword ptr [rdi], 0
0x180031881  jbe     short loc_18003189D
0x180031883  mov     ebx, ebp
0x180031885  mov     rcx, [r14+rbx*8]; string
0x180031889  call    cs:__imp_WindowsDeleteString
0x18003188f  inc     ebp
0x180031891  mov     qword ptr [r14+rbx*8], 0
0x180031899  cmp     ebp, [rdi]
0x18003189b  jb      short loc_180031883
0x18003189d  mov     rax, rdi
0x1800318a0  xor     ebp, ebp
0x1800318a2  mov     [rax], ebp
0x1800318a4  jmp     short loc_180031845
0x1800318a6  lea     rcx, [r13+28h]
0x1800318aa  mov     rax, [rcx]
0x1800318ad  mov     rax, [rax+18h]
0x1800318b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318b6  cmp     [rsi+54h], eax
0x1800318b9  jz      short loc_180031905
0x1800318bb  mov     r15d, 8000000Ch
0x1800318c1  mov     [rsi+50h], r15d
0x1800318c5  test    ebx, ebx
0x1800318c7  js      short loc_1800318F4
0x1800318c9  xor     edx, edx
0x1800318cb  mov     ecx, r15d
0x1800318ce  call    cs:__imp_RoOriginateError
0x1800318d4  mov     esi, ebp
0x1800318d6  cmp     [rdi], ebp
0x1800318d8  jbe     short loc_1800318F0
0x1800318da  mov     ebx, esi
0x1800318dc  mov     rcx, [r14+rbx*8]; string
0x1800318e0  call    cs:__imp_WindowsDeleteString
0x1800318e6  inc     esi
0x1800318e8  mov     [r14+rbx*8], rbp
0x1800318ec  cmp     esi, [rdi]
0x1800318ee  jb      short loc_1800318DA
0x1800318f0  mov     [rdi], ebp
0x1800318f2  jmp     short loc_180031902
0x1800318f4  xor     r8d, r8d
0x1800318f7  mov     edx, r15d
0x1800318fa  mov     ecx, ebx
0x1800318fc  call    cs:__imp_RoTransformError
0x180031902  mov     ebx, r15d
0x180031905  mov     eax, ebx
0x180031907  add     rsp, 38h
0x18003190b  pop     r15
0x18003190d  pop     r14
0x18003190f  pop     r13
0x180031911  pop     r12
0x180031913  pop     rdi
0x180031914  pop     rsi
0x180031915  pop     rbp
0x180031916  pop     rbx
0x180031917  retn
```
