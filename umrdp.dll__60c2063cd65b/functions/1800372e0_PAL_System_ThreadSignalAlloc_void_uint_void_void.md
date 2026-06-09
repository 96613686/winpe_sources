# PAL_System_ThreadSignalAlloc(void * *,uint (*)(void *),void *)

- ea: `0x1800372e0`
- end: `0x1800374d0`
- name: `?PAL_System_ThreadSignalAlloc@@YAJPEAPEAXP6AIPEAX@Z1@Z`
- size: `496`
- prototype: `__int64 __fastcall(void **, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003e9d0`

## callees

- `0x1800010b0`
- `0x18000b458`
- `0x180036088`
- `0x1800372e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037421`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037421`

## string_xrefs

- `0x18003733c`: `PAL_System_ThreadSignalAlloc`
- `0x1800373b6`: `PAL_System_ThreadSignalAlloc`
- `0x180037452`: `PAL_System_ThreadSignalAlloc`
- `0x180037355`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x1800373cf`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x18003746b`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x180037360`: `Failed to allocated thread signal struct`
- `0x1800373e1`: `Failed to create thread signal window`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalAlloc(HWND **a1, unsigned int (*a2)(void *), HWND a3, int a4)
{
  __int64 v7; // rdx
  HWND *v8; // rbx
  int v9; // edi
  __int16 *v10; // rdx
  const char **v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  const char **v16; // [rsp+40h] [rbp-30h]
  const char *v17; // [rsp+50h] [rbp-20h] BYREF
  const char *v18; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v19[2]; // [rsp+60h] [rbp-10h] BYREF
  HWND v20; // [rsp+A0h] [rbp+30h] BYREF
  int v21; // [rsp+B8h] [rbp+48h] BYREF

  v20 = 0;
  if ( a1 && a2 )
  {
    v8 = (HWND *)PAL_System_MemAlloc(24);
    if ( v8 )
    {
      v9 = PAL_System_Win32_ThreadCreateWindow(&v20, v7, (int)a3, a4);
      if ( v9 >= 0 )
      {
        v9 = 0;
        *v8 = v20;
        v8[1] = (HWND)a2;
        v8[2] = a3;
        *a1 = v8;
      }
      else
      {
        if ( (unsigned int)dword_18005C008 > 2 )
        {
          LODWORD(v20) = 111;
          v19[0] = "PAL_System_ThreadSignalAlloc";
          v21 = -2147467259;
          v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
          v17 = "Failed to create thread signal window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)qword_180054AE8,
            v13,
            v14,
            (__int64)&v17,
            (__int64)&v21,
            (__int64)&v18,
            (__int64)&v20,
            (__int64)v19);
        }
        LocalFree(v8);
      }
    }
    else
    {
      v9 = -2147024882;
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        LODWORD(v20) = 102;
        v17 = "PAL_System_ThreadSignalAlloc";
        v10 = word_180054B72;
        v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
        v19[0] = "Failed to allocated thread signal struct";
        v16 = &v17;
        v11 = (const char **)v19;
LABEL_13:
        v21 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)a1,
          (_DWORD)v10,
          (_DWORD)a3,
          a4,
          (__int64)v11,
          (__int64)&v21,
          (__int64)&v18,
          (__int64)&v20,
          (__int64)v16);
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      LODWORD(v20) = 91;
      v19[0] = "PAL_System_ThreadSignalAlloc";
      v10 = (__int16 *)byte_180054B2D;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
      v17 = "NULL parameter passed";
      v16 = (const char **)v19;
      v11 = &v17;
      goto LABEL_13;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800372e0  mov     [rsp-28h+arg_8], rbx
0x1800372e5  push    rbp
0x1800372e6  push    rsi
0x1800372e7  push    rdi
0x1800372e8  push    r14
0x1800372ea  push    r15
0x1800372ec  mov     rbp, rsp
0x1800372ef  sub     rsp, 70h
0x1800372f3  mov     [rbp+arg_0], 0
0x1800372fb  mov     r15, r8
0x1800372fe  mov     rsi, rdx
0x180037301  mov     r14, rcx
0x180037304  test    rcx, rcx
0x180037307  jz      loc_180037442
0x18003730d  test    rdx, rdx
0x180037310  jz      loc_180037442
0x180037316  mov     ecx, 18h
0x18003731b  call    PAL_System_MemAlloc
0x180037320  mov     rbx, rax
0x180037323  test    rax, rax
0x180037326  jnz     short loc_180037398
0x180037328  mov     eax, cs:dword_18005C008
0x18003732e  mov     edi, 8007000Eh
0x180037333  cmp     eax, 2
0x180037336  jbe     loc_1800374BA
0x18003733c  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x180037343  mov     dword ptr [rbp+arg_0], 66h ; 'f'
0x18003734a  mov     [rbp+var_20], rax
0x18003734e  lea     rdx, word_180054B72
0x180037355  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003735c  mov     [rbp+var_18], rax
0x180037360  lea     rax, aFailedToAlloca; "Failed to allocated thread signal struc"...
0x180037367  mov     [rbp+var_10], rax
0x18003736b  lea     rax, [rbp+var_20]
0x18003736f  mov     [rsp+70h+var_30], rax
0x180037374  lea     rax, [rbp+arg_0]
0x180037378  mov     [rsp+70h+var_38], rax
0x18003737d  lea     rax, [rbp+var_18]
0x180037381  mov     [rsp+70h+var_40], rax
0x180037386  lea     rax, [rbp+arg_18]
0x18003738a  mov     [rsp+70h+var_48], rax
0x18003738f  lea     rax, [rbp+var_10]
0x180037393  jmp     loc_1800374A9
0x180037398  lea     rcx, [rbp+arg_0]; HWND *
0x18003739c  call    ?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z; PAL_System_Win32_ThreadCreateWindow(HWND__ * *)
0x1800373a1  mov     edi, eax
0x1800373a3  test    eax, eax
0x1800373a5  jns     loc_18003742C
0x1800373ab  mov     eax, cs:dword_18005C008
0x1800373b1  cmp     eax, 2
0x1800373b4  jbe     short loc_18003741E
0x1800373b6  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x1800373bd  mov     dword ptr [rbp+arg_0], 6Fh ; 'o'
0x1800373c4  mov     [rbp+var_10], rax
0x1800373c8  lea     rdx, qword_180054AE8
0x1800373cf  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800373d6  mov     [rbp+arg_18], 80004005h
0x1800373dd  mov     [rbp+var_18], rax
0x1800373e1  lea     rax, aFailedToCreate_1; "Failed to create thread signal window"
0x1800373e8  mov     [rbp+var_20], rax
0x1800373ec  lea     rax, [rbp+var_10]
0x1800373f0  mov     [rsp+70h+var_30], rax
0x1800373f5  lea     rax, [rbp+arg_0]
0x1800373f9  mov     [rsp+70h+var_38], rax
0x1800373fe  lea     rax, [rbp+var_18]
0x180037402  mov     [rsp+70h+var_40], rax
0x180037407  lea     rax, [rbp+arg_18]
0x18003740b  mov     [rsp+70h+var_48], rax
0x180037410  lea     rax, [rbp+var_20]
0x180037414  mov     [rsp+70h+var_50], rax
0x180037419  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003741e  mov     rcx, rbx; hMem
0x180037421  call    cs:__imp_LocalFree
0x180037427  jmp     loc_1800374BA
0x18003742c  mov     rax, [rbp+arg_0]
0x180037430  xor     edi, edi
0x180037432  mov     [rbx], rax
0x180037435  mov     [rbx+8], rsi
0x180037439  mov     [rbx+10h], r15
0x18003743d  mov     [r14], rbx
0x180037440  jmp     short loc_1800374BA
0x180037442  mov     eax, cs:dword_18005C008
0x180037448  mov     edi, 80070057h
0x18003744d  cmp     eax, 2
0x180037450  jbe     short loc_1800374BA
0x180037452  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x180037459  mov     dword ptr [rbp+arg_0], 5Bh ; '['
0x180037460  mov     [rbp+var_10], rax
0x180037464  lea     rdx, byte_180054B2D
0x18003746b  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180037472  mov     [rbp+var_18], rax
0x180037476  lea     rax, aNullParameterP; "NULL parameter passed"
0x18003747d  mov     [rbp+var_20], rax
0x180037481  lea     rax, [rbp+var_10]
0x180037485  mov     [rsp+70h+var_30], rax
0x18003748a  lea     rax, [rbp+arg_0]
0x18003748e  mov     [rsp+70h+var_38], rax
0x180037493  lea     rax, [rbp+var_18]
0x180037497  mov     [rsp+70h+var_40], rax
0x18003749c  lea     rax, [rbp+arg_18]
0x1800374a0  mov     [rsp+70h+var_48], rax
0x1800374a5  lea     rax, [rbp+var_20]
0x1800374a9  mov     [rsp+70h+var_50], rax
0x1800374ae  mov     [rbp+arg_18], 80004005h
0x1800374b5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800374ba  mov     rbx, [rsp+70h+arg_8]
0x1800374c2  mov     eax, edi
0x1800374c4  add     rsp, 70h
0x1800374c8  pop     r15
0x1800374ca  pop     r14
0x1800374cc  pop     rdi
0x1800374cd  pop     rsi
0x1800374ce  pop     rbp
0x1800374cf  retn
```
