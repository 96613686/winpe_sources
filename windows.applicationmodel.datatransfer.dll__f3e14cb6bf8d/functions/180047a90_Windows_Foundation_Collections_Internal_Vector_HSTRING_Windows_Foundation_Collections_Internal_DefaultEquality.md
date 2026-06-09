# Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::RemoveAtInternal(uint,bool)

- ea: `0x180047a90`
- end: `0x180047c55`
- name: `?RemoveAtInternal@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `453`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180047a70`
- `0x180047a80`

## callees

- `0x1800033f2`
- `0x180005827`
- `0x180043a2c`
- `0x180047a90`
- `0x180048630`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180047b7f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180047b7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047b44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047c01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047b44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047c01`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180047af9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180047af9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047bf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047bf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047adb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047adb`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::RemoveAtInternal(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  _DWORD *v3; // r14
  RTL_SRWLOCK *v4; // r15
  HSTRING v5; // rbx
  bool v6; // zf
  int v7; // edi
  __int64 v11; // rcx
  size_t v12; // r8
  char *v13; // rdx
  char *v14; // r9
  unsigned int v15; // r9d
  unsigned int v16; // r8d
  int v18; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v19; // [rsp+38h] [rbp-40h]

  v3 = 0;
  v4 = (RTL_SRWLOCK *)(a1 + 136);
  v5 = 0;
  v19 = 0;
  v6 = *(_DWORD *)(a1 + 128) == 1;
  v7 = -2147483627;
  v18 = -2147483627;
  if ( v6 )
  {
    if ( !LODWORD(v4->Ptr) )
      LODWORD(v4->Ptr) = -268435456;
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
  }
  if ( a3 )
    a2 = *(_DWORD *)(a1 + 96) - 1;
  if ( a2 >= *(_DWORD *)(a1 + 96) )
  {
    v7 = -2147483637;
LABEL_9:
    RoOriginateError((unsigned int)v7, 0);
    goto LABEL_25;
  }
  v3 = (_DWORD *)(a1 + 180);
  if ( *(_DWORD *)(a1 + 180) || (v7 = 0, *(int *)(a1 + 176) <= 0) )
    v3 = 0;
  else
    *v3 = 1;
  v19 = v3;
  v18 = v7;
  if ( v7 < 0 )
    goto LABEL_9;
  v5 = *(HSTRING *)(*(_QWORD *)(a1 + 112) + 8LL * a2);
  WindowsDeleteString(0);
  v11 = *(unsigned int *)(a1 + 96);
  if ( a2 < (int)v11 - 1 )
  {
    v12 = 8LL * ((unsigned int)v11 + ~a2);
    if ( v12 )
    {
      v13 = *(char **)(a1 + 112);
      v14 = &v13[8 * a2];
      if ( !v14 || (v13 += 8 * a2 + 8) == 0 )
      {
        *(_DWORD *)_o__errno(v11, v13, v12) = 22;
        invalid_parameter_noinfo();
        v7 = -2147418113;
        goto LABEL_9;
      }
      memmove_0(v14, v13, v12);
    }
  }
  v15 = *(_DWORD *)(a1 + 100);
  ++*(_DWORD *)(a1 + 144);
  if ( --*(_DWORD *)(a1 + 96) < v15 / 3 )
  {
    v16 = 1;
    if ( v15 - 1 >= v15 - v15 / 3 )
      v16 = v15 / 3;
    v7 = Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::ResizeStorage(
           a1,
           v15 - v16);
  }
LABEL_25:
  if ( *(_DWORD *)(a1 + 128) == 1 )
    LODWORD(v4->Ptr) += 0x10000000;
  else
    ReleaseSRWLockExclusive(v4);
  WindowsDeleteString(v5);
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>::RaiseEvent(
           (unsigned int)&v18,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           2,
           a2);
  if ( v3 )
    *v3 = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180047a90  push    rbx
0x180047a92  push    rbp
0x180047a93  push    rsi
0x180047a94  push    rdi
0x180047a95  push    r12
0x180047a97  push    r14
0x180047a99  push    r15
0x180047a9b  sub     rsp, 40h
0x180047a9f  xor     r14d, r14d
0x180047aa2  lea     r15, [rcx+88h]
0x180047aa9  xor     ebx, ebx
0x180047aab  mov     [rsp+78h+var_40], r14
0x180047ab0  cmp     dword ptr [rcx+80h], 1
0x180047ab7  mov     edi, 80000015h
0x180047abc  mov     r12b, r8b
0x180047abf  mov     [rsp+78h+var_48], edi
0x180047ac3  mov     ebp, edx
0x180047ac5  mov     rsi, rcx
0x180047ac8  jnz     short loc_180047AD8
0x180047aca  cmp     [r15], ebx
0x180047acd  jnz     short loc_180047AE1
0x180047acf  mov     dword ptr [r15], 0F0000000h
0x180047ad6  jmp     short loc_180047AE1
0x180047ad8  mov     rcx, r15; SRWLock
0x180047adb  call    cs:__imp_AcquireSRWLockExclusive
0x180047ae1  test    r12b, r12b
0x180047ae4  jz      short loc_180047AEB
0x180047ae6  mov     ebp, [rsi+60h]
0x180047ae9  dec     ebp
0x180047aeb  cmp     ebp, [rsi+60h]
0x180047aee  jb      short loc_180047B04
0x180047af0  mov     edi, 8000000Bh
0x180047af5  xor     edx, edx
0x180047af7  mov     ecx, edi
0x180047af9  call    cs:__imp_RoOriginateError
0x180047aff  jmp     loc_180047BE3
0x180047b04  mov     ecx, [rsi+0B0h]
0x180047b0a  lea     r14, [rsi+0B4h]
0x180047b11  mov     eax, [r14]
0x180047b14  test    eax, eax
0x180047b16  jnz     short loc_180047B27
0x180047b18  xor     edi, edi
0x180047b1a  test    ecx, ecx
0x180047b1c  jle     short loc_180047B27
0x180047b1e  mov     dword ptr [r14], 1
0x180047b25  jmp     short loc_180047B2A
0x180047b27  xor     r14d, r14d
0x180047b2a  mov     [rsp+78h+var_40], r14
0x180047b2f  mov     [rsp+78h+var_48], edi
0x180047b33  test    edi, edi
0x180047b35  js      short loc_180047AF5
0x180047b37  mov     rbx, [rsi+70h]
0x180047b3b  xor     ecx, ecx; string
0x180047b3d  mov     r12d, ebp
0x180047b40  mov     rbx, [rbx+r12*8]
0x180047b44  call    cs:__imp_WindowsDeleteString
0x180047b4a  mov     ecx, [rsi+60h]
0x180047b4d  lea     eax, [rcx-1]
0x180047b50  cmp     ebp, eax
0x180047b52  jnb     short loc_180047BA2
0x180047b54  mov     r8d, ebp
0x180047b57  not     r8d
0x180047b5a  add     r8d, ecx
0x180047b5d  shl     r8, 3; Size
0x180047b61  test    r8, r8
0x180047b64  jz      short loc_180047BA2
0x180047b66  mov     rdx, [rsi+70h]
0x180047b6a  lea     r9, [rdx+r12*8]
0x180047b6e  test    r9, r9
0x180047b71  jz      short loc_180047B7F
0x180047b73  lea     eax, [rbp+1]
0x180047b76  lea     rdx, [rdx+rax*8]; Src
0x180047b7a  test    rdx, rdx
0x180047b7d  jnz     short loc_180047B9A
0x180047b7f  call    cs:__imp__o__errno
0x180047b85  mov     dword ptr [rax], 16h
0x180047b8b  call    _invalid_parameter_noinfo
0x180047b90  mov     edi, 8000FFFFh
0x180047b95  jmp     loc_180047AF5
0x180047b9a  mov     rcx, r9; void *
0x180047b9d  call    memmove_0
0x180047ba2  mov     r9d, [rsi+64h]
0x180047ba6  mov     eax, 0AAAAAAABh
0x180047bab  inc     dword ptr [rsi+90h]
0x180047bb1  dec     dword ptr [rsi+60h]
0x180047bb4  mul     r9d
0x180047bb7  shr     edx, 1
0x180047bb9  cmp     [rsi+60h], edx
0x180047bbc  jnb     short loc_180047BE3
0x180047bbe  mov     ecx, r9d
0x180047bc1  lea     eax, [r9-1]
0x180047bc5  sub     ecx, edx
0x180047bc7  mov     r8d, 1
0x180047bcd  cmp     eax, ecx
0x180047bcf  mov     rcx, rsi
0x180047bd2  cmovnb  r8d, edx
0x180047bd6  sub     r9d, r8d
0x180047bd9  mov     edx, r9d
0x180047bdc  call    ?ResizeStorage@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::ResizeStorage(uint)
0x180047be1  mov     edi, eax
0x180047be3  cmp     dword ptr [rsi+80h], 1
0x180047bea  jnz     short loc_180047BF5
0x180047bec  add     dword ptr [r15], 10000000h
0x180047bf3  jmp     short loc_180047BFE
0x180047bf5  mov     rcx, r15; SRWLock
0x180047bf8  call    cs:__imp_ReleaseSRWLockExclusive
0x180047bfe  mov     rcx, rbx; string
0x180047c01  call    cs:__imp_WindowsDeleteString
0x180047c07  test    edi, edi
0x180047c09  js      short loc_180047C38
0x180047c0b  lea     rcx, [rsi+10h]
0x180047c0f  mov     [rsp+78h+var_58], ebp
0x180047c13  mov     rax, rsi
0x180047c16  lea     rdx, [rsi+98h]
0x180047c1d  neg     rax
0x180047c20  mov     r9d, 2
0x180047c26  sbb     r8, r8
0x180047c29  and     r8, rcx
0x180047c2c  lea     rcx, [rsp+78h+var_48]
0x180047c31  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUHSTRING__@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUHSTRING__@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<HSTRING__ *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x180047c36  mov     edi, eax
0x180047c38  test    r14, r14
0x180047c3b  jz      short loc_180047C44
0x180047c3d  mov     dword ptr [r14], 0
0x180047c44  mov     eax, edi
0x180047c46  add     rsp, 40h
0x180047c4a  pop     r15
0x180047c4c  pop     r14
0x180047c4e  pop     r12
0x180047c50  pop     rdi
0x180047c51  pop     rsi
0x180047c52  pop     rbp
0x180047c53  pop     rbx
0x180047c54  retn
```
