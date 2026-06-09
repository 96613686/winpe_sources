# Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::SetAt(uint,HSTRING__ *)

- ea: `0x18004a9d0`
- end: `0x18004ab63`
- name: `?SetAt@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUHSTRING__@@@Z`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800033f2`
- `0x180043a2c`
- `0x18004a9d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004aa99`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004aa99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a9fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004a9fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004aad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004aafc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ab11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004aad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004aafc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ab11`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004aa49`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004aa49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004aaee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004aaee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004aa35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004aa35`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::SetAt(
        __int64 a1,
        unsigned int a2,
        HSTRING a3)
{
  __int64 v3; // rbp
  _DWORD *v5; // r14
  HSTRING v6; // rbx
  HRESULT v7; // edi
  __int64 v8; // r8
  _DWORD *v9; // r15
  __int64 v10; // rcx
  HSTRING *v11; // rdx
  int v13; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v14; // [rsp+38h] [rbp-40h]
  HSTRING string; // [rsp+90h] [rbp+18h] BYREF

  v3 = a2;
  v5 = 0;
  v13 = -2147483627;
  v14 = 0;
  v6 = 0;
  v7 = WindowsDuplicateString(a3, &string);
  if ( v7 < 0 )
  {
    string = 0;
    goto LABEL_22;
  }
  v9 = (_DWORD *)(a1 + 136);
  if ( *(_DWORD *)(a1 + 128) == 1 )
  {
    if ( !*v9 )
      *v9 = -268435456;
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
  }
  if ( (unsigned int)v3 >= *(_DWORD *)(a1 + 96) )
  {
    v7 = -2147483637;
LABEL_9:
    RoOriginateError((unsigned int)v7, 0);
    goto LABEL_19;
  }
  v10 = *(unsigned int *)(a1 + 176);
  v5 = (_DWORD *)(a1 + 180);
  if ( *(_DWORD *)(a1 + 180) )
  {
    v7 = -2147483627;
  }
  else
  {
    v7 = 0;
    if ( (int)v10 > 0 )
    {
      *v5 = 1;
      goto LABEL_15;
    }
  }
  v5 = 0;
LABEL_15:
  v14 = v5;
  v13 = v7;
  if ( v7 < 0 )
    goto LABEL_9;
  v11 = (HSTRING *)(*(_QWORD *)(a1 + 112) + 8 * v3);
  if ( !v11 )
  {
    *(_DWORD *)_o__errno(v10, 0, v8) = 22;
    invalid_parameter_noinfo();
    v7 = -2147418113;
    goto LABEL_9;
  }
  v6 = *v11;
  *v11 = string;
  ++*(_DWORD *)(a1 + 144);
  string = 0;
  WindowsDeleteString(0);
LABEL_19:
  if ( *(_DWORD *)(a1 + 128) == 1 )
    *v9 += 0x10000000;
  else
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 136));
LABEL_22:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v6);
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>::RaiseEvent(
           (unsigned int)&v13,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           3,
           v3);
  if ( v5 )
    *v5 = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004a9d0  mov     rax, rsp
0x18004a9d3  push    rbx
0x18004a9d4  push    rbp
0x18004a9d5  push    rsi
0x18004a9d6  push    rdi
0x18004a9d7  push    r14
0x18004a9d9  push    r15
0x18004a9db  sub     rsp, 48h
0x18004a9df  mov     ebp, edx
0x18004a9e1  mov     rsi, rcx
0x18004a9e4  xor     r14d, r14d
0x18004a9e7  mov     dword ptr [rax-48h], 80000015h
0x18004a9ee  lea     rdx, [rax+18h]; newString
0x18004a9f2  mov     [rax-40h], r14
0x18004a9f6  mov     rcx, r8; string
0x18004a9f9  xor     ebx, ebx
0x18004a9fb  call    cs:__imp_WindowsDuplicateString
0x18004aa01  mov     edi, eax
0x18004aa03  test    eax, eax
0x18004aa05  jns     short loc_18004AA14
0x18004aa07  mov     [rsp+78h+string], rbx
0x18004aa0f  jmp     loc_18004AAF4
0x18004aa14  cmp     dword ptr [rsi+80h], 1
0x18004aa1b  lea     r15, [rsi+88h]
0x18004aa22  jnz     short loc_18004AA32
0x18004aa24  cmp     [r15], ebx
0x18004aa27  jnz     short loc_18004AA3B
0x18004aa29  mov     dword ptr [r15], 0F0000000h
0x18004aa30  jmp     short loc_18004AA3B
0x18004aa32  mov     rcx, r15; SRWLock
0x18004aa35  call    cs:__imp_AcquireSRWLockExclusive
0x18004aa3b  cmp     ebp, [rsi+60h]
0x18004aa3e  jb      short loc_18004AA54
0x18004aa40  mov     edi, 8000000Bh
0x18004aa45  xor     edx, edx
0x18004aa47  mov     ecx, edi
0x18004aa49  call    cs:__imp_RoOriginateError
0x18004aa4f  jmp     loc_18004AAD9
0x18004aa54  mov     ecx, [rsi+0B0h]
0x18004aa5a  lea     r14, [rsi+0B4h]
0x18004aa61  mov     eax, [r14]
0x18004aa64  test    eax, eax
0x18004aa66  jnz     short loc_18004AA77
0x18004aa68  xor     edi, edi
0x18004aa6a  test    ecx, ecx
0x18004aa6c  jle     short loc_18004AA7C
0x18004aa6e  mov     dword ptr [r14], 1
0x18004aa75  jmp     short loc_18004AA7F
0x18004aa77  mov     edi, 80000015h
0x18004aa7c  xor     r14d, r14d
0x18004aa7f  mov     [rsp+78h+var_40], r14
0x18004aa84  mov     [rsp+78h+var_48], edi
0x18004aa88  test    edi, edi
0x18004aa8a  js      short loc_18004AA45
0x18004aa8c  mov     rax, [rsi+70h]
0x18004aa90  lea     rdx, [rax+rbp*8]
0x18004aa94  test    rdx, rdx
0x18004aa97  jnz     short loc_18004AAB1
0x18004aa99  call    cs:__imp__o__errno
0x18004aa9f  mov     dword ptr [rax], 16h
0x18004aaa5  call    _invalid_parameter_noinfo
0x18004aaaa  mov     edi, 8000FFFFh
0x18004aaaf  jmp     short loc_18004AA45
0x18004aab1  mov     rbx, [rdx]
0x18004aab4  xor     ecx, ecx; string
0x18004aab6  mov     rax, [rsp+78h+string]
0x18004aabe  mov     [rdx], rax
0x18004aac1  inc     dword ptr [rsi+90h]
0x18004aac7  mov     [rsp+78h+string], 0
0x18004aad3  call    cs:__imp_WindowsDeleteString
0x18004aad9  cmp     dword ptr [rsi+80h], 1
0x18004aae0  jnz     short loc_18004AAEB
0x18004aae2  add     dword ptr [r15], 10000000h
0x18004aae9  jmp     short loc_18004AAF4
0x18004aaeb  mov     rcx, r15; SRWLock
0x18004aaee  call    cs:__imp_ReleaseSRWLockExclusive
0x18004aaf4  mov     rcx, [rsp+78h+string]; string
0x18004aafc  call    cs:__imp_WindowsDeleteString
0x18004ab02  mov     rcx, rbx; string
0x18004ab05  mov     [rsp+78h+string], 0
0x18004ab11  call    cs:__imp_WindowsDeleteString
0x18004ab17  test    edi, edi
0x18004ab19  js      short loc_18004AB48
0x18004ab1b  lea     rcx, [rsi+10h]
0x18004ab1f  mov     [rsp+78h+var_58], ebp
0x18004ab23  mov     rax, rsi
0x18004ab26  lea     rdx, [rsi+98h]
0x18004ab2d  neg     rax
0x18004ab30  mov     r9d, 3
0x18004ab36  sbb     r8, r8
0x18004ab39  and     r8, rcx
0x18004ab3c  lea     rcx, [rsp+78h+var_48]
0x18004ab41  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUHSTRING__@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUHSTRING__@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<HSTRING__ *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x18004ab46  mov     edi, eax
0x18004ab48  test    r14, r14
0x18004ab4b  jz      short loc_18004AB54
0x18004ab4d  mov     dword ptr [r14], 0
0x18004ab54  mov     eax, edi
0x18004ab56  add     rsp, 48h
0x18004ab5a  pop     r15
0x18004ab5c  pop     r14
0x18004ab5e  pop     rdi
0x18004ab5f  pop     rsi
0x18004ab60  pop     rbp
0x18004ab61  pop     rbx
0x18004ab62  retn
```
