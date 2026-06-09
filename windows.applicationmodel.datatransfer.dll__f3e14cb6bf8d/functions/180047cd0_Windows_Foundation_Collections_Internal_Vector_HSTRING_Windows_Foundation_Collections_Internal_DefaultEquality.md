# Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::ReplaceAll(uint,HSTRING__ * *)

- ea: `0x180047cd0`
- end: `0x180047e65`
- name: `?ReplaceAll@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUHSTRING__@@@Z`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180043a2c`
- `0x180047cd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047e11`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047e11`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180047d02`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180047d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180047d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180047d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047df8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047df8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180047da6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180047da6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047de1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047de1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047d67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047d67`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::ReplaceAll(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  _DWORD *v3; // rsi
  unsigned int v4; // r12d
  HSTRING *v7; // r15
  HRESULT v8; // edi
  __int64 v9; // r14
  _DWORD *v10; // rbx
  int v11; // eax
  HSTRING *v12; // rax
  __int64 i; // r12
  int v15; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v16; // [rsp+38h] [rbp-40h]

  v3 = 0;
  v4 = a2;
  v15 = -2147483627;
  v16 = 0;
  if ( !a2 )
  {
    LODWORD(v9) = 0;
    v7 = 0;
    v4 = 0;
LABEL_9:
    v10 = (_DWORD *)(a1 + 136);
    if ( *(_DWORD *)(a1 + 128) == 1 )
    {
      if ( !*v10 )
        *v10 = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 136));
    }
    v3 = (_DWORD *)(a1 + 180);
    if ( *(_DWORD *)(a1 + 180) )
    {
      v8 = -2147483627;
    }
    else
    {
      v8 = 0;
      if ( *(int *)(a1 + 176) > 0 )
      {
        *v3 = 1;
LABEL_18:
        v16 = v3;
        v15 = v8;
        if ( v8 >= 0 )
        {
          v11 = *(_DWORD *)(a1 + 96);
          ++*(_DWORD *)(a1 + 144);
          *(_DWORD *)(a1 + 96) = v9;
          LODWORD(v9) = v11;
          v12 = *(HSTRING **)(a1 + 112);
          *(_QWORD *)(a1 + 112) = v7;
          v7 = v12;
          *(_DWORD *)(a1 + 100) = v4;
        }
        else
        {
          RoOriginateError((unsigned int)v8, 0);
        }
        if ( *(_DWORD *)(a1 + 128) == 1 )
          *v10 += 0x10000000;
        else
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 136));
        goto LABEL_24;
      }
    }
    v3 = 0;
    goto LABEL_18;
  }
  v7 = (HSTRING *)malloc(8LL * a2);
  if ( !v7 )
    return (unsigned int)-2147024882;
  v9 = 0;
  while ( 1 )
  {
    v8 = WindowsDuplicateString(*(HSTRING *)(a3 + 8 * v9), &v7[v9]);
    if ( v8 < 0 )
      break;
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= v4 )
      goto LABEL_9;
  }
LABEL_24:
  if ( v7 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
    {
      WindowsDeleteString(v7[i]);
      v7[i] = 0;
    }
    free(v7);
  }
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>::RaiseEvent(
           (unsigned int)&v15,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           0,
           0);
  if ( v3 )
    *v3 = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180047cd0  push    rbx
0x180047cd2  push    rbp
0x180047cd3  push    rsi
0x180047cd4  push    rdi
0x180047cd5  push    r12
0x180047cd7  push    r14
0x180047cd9  push    r15
0x180047cdb  sub     rsp, 40h
0x180047cdf  xor     esi, esi
0x180047ce1  mov     r12d, edx
0x180047ce4  mov     [rsp+78h+var_48], 80000015h
0x180047cec  mov     rbx, r8
0x180047cef  mov     [rsp+78h+var_40], rsi
0x180047cf4  mov     rbp, rcx
0x180047cf7  test    edx, edx
0x180047cf9  jz      short loc_180047D3F
0x180047cfb  mov     ecx, r12d
0x180047cfe  shl     rcx, 3; Size
0x180047d02  call    cs:__imp_malloc
0x180047d08  mov     r15, rax
0x180047d0b  test    rax, rax
0x180047d0e  jnz     short loc_180047D1A
0x180047d10  mov     edi, 8007000Eh
0x180047d15  jmp     loc_180047E54
0x180047d1a  xor     r14d, r14d
0x180047d1d  mov     rcx, [rbx+r14*8]; string
0x180047d21  lea     rdx, [r15+r14*8]; newString
0x180047d25  call    cs:__imp_WindowsDuplicateString
0x180047d2b  mov     edi, eax
0x180047d2d  test    eax, eax
0x180047d2f  js      loc_180047DE7
0x180047d35  inc     r14d
0x180047d38  cmp     r14d, r12d
0x180047d3b  jb      short loc_180047D1D
0x180047d3d  jmp     short loc_180047D48
0x180047d3f  xor     r14d, r14d
0x180047d42  xor     r15d, r15d
0x180047d45  xor     r12d, r12d
0x180047d48  cmp     dword ptr [rbp+80h], 1
0x180047d4f  lea     rbx, [rbp+88h]
0x180047d56  jnz     short loc_180047D64
0x180047d58  cmp     [rbx], esi
0x180047d5a  jnz     short loc_180047D6D
0x180047d5c  mov     dword ptr [rbx], 0F0000000h
0x180047d62  jmp     short loc_180047D6D
0x180047d64  mov     rcx, rbx; SRWLock
0x180047d67  call    cs:__imp_AcquireSRWLockExclusive
0x180047d6d  mov     ecx, [rbp+0B0h]
0x180047d73  lea     rsi, [rbp+0B4h]
0x180047d7a  mov     eax, [rsi]
0x180047d7c  test    eax, eax
0x180047d7e  jnz     short loc_180047D8E
0x180047d80  xor     edi, edi
0x180047d82  test    ecx, ecx
0x180047d84  jle     short loc_180047D93
0x180047d86  mov     dword ptr [rsi], 1
0x180047d8c  jmp     short loc_180047D95
0x180047d8e  mov     edi, 80000015h
0x180047d93  xor     esi, esi
0x180047d95  mov     [rsp+78h+var_40], rsi
0x180047d9a  mov     [rsp+78h+var_48], edi
0x180047d9e  test    edi, edi
0x180047da0  jns     short loc_180047DAE
0x180047da2  xor     edx, edx
0x180047da4  mov     ecx, edi
0x180047da6  call    cs:__imp_RoOriginateError
0x180047dac  jmp     short loc_180047DCD
0x180047dae  mov     eax, [rbp+60h]
0x180047db1  inc     dword ptr [rbp+90h]
0x180047db7  mov     [rbp+60h], r14d
0x180047dbb  mov     r14d, eax
0x180047dbe  mov     rax, [rbp+70h]
0x180047dc2  mov     [rbp+70h], r15
0x180047dc6  mov     r15, rax
0x180047dc9  mov     [rbp+64h], r12d
0x180047dcd  cmp     dword ptr [rbp+80h], 1
0x180047dd4  jnz     short loc_180047DDE
0x180047dd6  add     dword ptr [rbx], 10000000h
0x180047ddc  jmp     short loc_180047DE7
0x180047dde  mov     rcx, rbx; SRWLock
0x180047de1  call    cs:__imp_ReleaseSRWLockExclusive
0x180047de7  test    r15, r15
0x180047dea  jz      short loc_180047E17
0x180047dec  xor     r12d, r12d
0x180047def  test    r14d, r14d
0x180047df2  jz      short loc_180047E0E
0x180047df4  mov     rcx, [r15+r12*8]; string
0x180047df8  call    cs:__imp_WindowsDeleteString
0x180047dfe  mov     qword ptr [r15+r12*8], 0
0x180047e06  inc     r12d
0x180047e09  cmp     r12d, r14d
0x180047e0c  jb      short loc_180047DF4
0x180047e0e  mov     rcx, r15; Block
0x180047e11  call    cs:__imp_free
0x180047e17  test    edi, edi
0x180047e19  js      short loc_180047E49
0x180047e1b  lea     rcx, [rbp+10h]
0x180047e1f  mov     [rsp+78h+var_58], 0
0x180047e27  mov     rax, rbp
0x180047e2a  lea     rdx, [rbp+98h]
0x180047e31  neg     rax
0x180047e34  sbb     r8, r8
0x180047e37  xor     r9d, r9d
0x180047e3a  and     r8, rcx
0x180047e3d  lea     rcx, [rsp+78h+var_48]
0x180047e42  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUHSTRING__@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUHSTRING__@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<HSTRING__ *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x180047e47  mov     edi, eax
0x180047e49  test    rsi, rsi
0x180047e4c  jz      short loc_180047E54
0x180047e4e  mov     dword ptr [rsi], 0
0x180047e54  mov     eax, edi
0x180047e56  add     rsp, 40h
0x180047e5a  pop     r15
0x180047e5c  pop     r14
0x180047e5e  pop     r12
0x180047e60  pop     rdi
0x180047e61  pop     rsi
0x180047e62  pop     rbp
0x180047e63  pop     rbx
0x180047e64  retn
```
