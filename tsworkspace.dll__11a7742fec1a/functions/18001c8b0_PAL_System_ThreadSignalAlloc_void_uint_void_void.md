# PAL_System_ThreadSignalAlloc(void * *,uint (*)(void *),void *)

- ea: `0x18001c8b0`
- end: `0x18001caa0`
- name: `?PAL_System_ThreadSignalAlloc@@YAJPEAPEAXP6AIPEAX@Z1@Z`
- size: `496`
- prototype: `__int64 __fastcall(void **, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018280`

## callees

- `0x180001180`
- `0x18001ab9c`
- `0x18001c6e4`
- `0x18001c8b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9f1`

## string_xrefs

- `0x18001c90c`: `PAL_System_ThreadSignalAlloc`
- `0x18001c986`: `PAL_System_ThreadSignalAlloc`
- `0x18001ca22`: `PAL_System_ThreadSignalAlloc`
- `0x18001c925`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x18001c99f`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x18001ca3b`: `onecore\termsrv\rdpplatform\common\pal\wincommon\system\tssystempalwincommon.cpp`
- `0x18001c930`: `Failed to allocated thread signal struct`
- `0x18001c9b1`: `Failed to create thread signal window`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalAlloc(HWND **a1, unsigned int (*a2)(void *), HWND a3, int a4)
{
  __int64 v7; // rdx
  HWND *v8; // rbx
  int v9; // edi
  int *v10; // rdx
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
        if ( (unsigned int)dword_1800EB958 > 2 )
        {
          LODWORD(v20) = 111;
          v19[0] = "PAL_System_ThreadSignalAlloc";
          v21 = -2147467259;
          v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\system\\tssystempalwincommon.cpp";
          v17 = "Failed to create thread signal window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)word_1800CD902,
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
      if ( (unsigned int)dword_1800EB958 > 2 )
      {
        LODWORD(v20) = 102;
        v17 = "PAL_System_ThreadSignalAlloc";
        v10 = &dword_1800CD98C;
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
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      LODWORD(v20) = 91;
      v19[0] = "PAL_System_ThreadSignalAlloc";
      v10 = (int *)&byte_1800CD947;
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
0x18001c8b0  mov     [rsp-28h+arg_8], rbx
0x18001c8b5  push    rbp
0x18001c8b6  push    rsi
0x18001c8b7  push    rdi
0x18001c8b8  push    r14
0x18001c8ba  push    r15
0x18001c8bc  mov     rbp, rsp
0x18001c8bf  sub     rsp, 70h
0x18001c8c3  mov     [rbp+arg_0], 0
0x18001c8cb  mov     r15, r8
0x18001c8ce  mov     rsi, rdx
0x18001c8d1  mov     r14, rcx
0x18001c8d4  test    rcx, rcx
0x18001c8d7  jz      loc_18001CA12
0x18001c8dd  test    rdx, rdx
0x18001c8e0  jz      loc_18001CA12
0x18001c8e6  mov     ecx, 18h
0x18001c8eb  call    PAL_System_MemAlloc
0x18001c8f0  mov     rbx, rax
0x18001c8f3  test    rax, rax
0x18001c8f6  jnz     short loc_18001C968
0x18001c8f8  mov     eax, cs:dword_1800EB958
0x18001c8fe  mov     edi, 8007000Eh
0x18001c903  cmp     eax, 2
0x18001c906  jbe     loc_18001CA8A
0x18001c90c  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x18001c913  mov     dword ptr [rbp+arg_0], 66h ; 'f'
0x18001c91a  mov     [rbp+var_20], rax
0x18001c91e  lea     rdx, dword_1800CD98C
0x18001c925  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001c92c  mov     [rbp+var_18], rax
0x18001c930  lea     rax, aFailedToAlloca; "Failed to allocated thread signal struc"...
0x18001c937  mov     [rbp+var_10], rax
0x18001c93b  lea     rax, [rbp+var_20]
0x18001c93f  mov     [rsp+70h+var_30], rax
0x18001c944  lea     rax, [rbp+arg_0]
0x18001c948  mov     [rsp+70h+var_38], rax
0x18001c94d  lea     rax, [rbp+var_18]
0x18001c951  mov     [rsp+70h+var_40], rax
0x18001c956  lea     rax, [rbp+arg_18]
0x18001c95a  mov     [rsp+70h+var_48], rax
0x18001c95f  lea     rax, [rbp+var_10]
0x18001c963  jmp     loc_18001CA79
0x18001c968  lea     rcx, [rbp+arg_0]; HWND *
0x18001c96c  call    ?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z; PAL_System_Win32_ThreadCreateWindow(HWND__ * *)
0x18001c971  mov     edi, eax
0x18001c973  test    eax, eax
0x18001c975  jns     loc_18001C9FC
0x18001c97b  mov     eax, cs:dword_1800EB958
0x18001c981  cmp     eax, 2
0x18001c984  jbe     short loc_18001C9EE
0x18001c986  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x18001c98d  mov     dword ptr [rbp+arg_0], 6Fh ; 'o'
0x18001c994  mov     [rbp+var_10], rax
0x18001c998  lea     rdx, word_1800CD902
0x18001c99f  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001c9a6  mov     [rbp+arg_18], 80004005h
0x18001c9ad  mov     [rbp+var_18], rax
0x18001c9b1  lea     rax, aFailedToCreate_3; "Failed to create thread signal window"
0x18001c9b8  mov     [rbp+var_20], rax
0x18001c9bc  lea     rax, [rbp+var_10]
0x18001c9c0  mov     [rsp+70h+var_30], rax
0x18001c9c5  lea     rax, [rbp+arg_0]
0x18001c9c9  mov     [rsp+70h+var_38], rax
0x18001c9ce  lea     rax, [rbp+var_18]
0x18001c9d2  mov     [rsp+70h+var_40], rax
0x18001c9d7  lea     rax, [rbp+arg_18]
0x18001c9db  mov     [rsp+70h+var_48], rax
0x18001c9e0  lea     rax, [rbp+var_20]
0x18001c9e4  mov     [rsp+70h+var_50], rax
0x18001c9e9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001c9ee  mov     rcx, rbx; hMem
0x18001c9f1  call    cs:__imp_LocalFree
0x18001c9f7  jmp     loc_18001CA8A
0x18001c9fc  mov     rax, [rbp+arg_0]
0x18001ca00  xor     edi, edi
0x18001ca02  mov     [rbx], rax
0x18001ca05  mov     [rbx+8], rsi
0x18001ca09  mov     [rbx+10h], r15
0x18001ca0d  mov     [r14], rbx
0x18001ca10  jmp     short loc_18001CA8A
0x18001ca12  mov     eax, cs:dword_1800EB958
0x18001ca18  mov     edi, 80070057h
0x18001ca1d  cmp     eax, 2
0x18001ca20  jbe     short loc_18001CA8A
0x18001ca22  lea     rax, aPalSystemThrea_0; "PAL_System_ThreadSignalAlloc"
0x18001ca29  mov     dword ptr [rbp+arg_0], 5Bh ; '['
0x18001ca30  mov     [rbp+var_10], rax
0x18001ca34  lea     rdx, byte_1800CD947
0x18001ca3b  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ca42  mov     [rbp+var_18], rax
0x18001ca46  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001ca4d  mov     [rbp+var_20], rax
0x18001ca51  lea     rax, [rbp+var_10]
0x18001ca55  mov     [rsp+70h+var_30], rax
0x18001ca5a  lea     rax, [rbp+arg_0]
0x18001ca5e  mov     [rsp+70h+var_38], rax
0x18001ca63  lea     rax, [rbp+var_18]
0x18001ca67  mov     [rsp+70h+var_40], rax
0x18001ca6c  lea     rax, [rbp+arg_18]
0x18001ca70  mov     [rsp+70h+var_48], rax
0x18001ca75  lea     rax, [rbp+var_20]
0x18001ca79  mov     [rsp+70h+var_50], rax
0x18001ca7e  mov     [rbp+arg_18], 80004005h
0x18001ca85  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ca8a  mov     rbx, [rsp+70h+arg_8]
0x18001ca92  mov     eax, edi
0x18001ca94  add     rsp, 70h
0x18001ca98  pop     r15
0x18001ca9a  pop     r14
0x18001ca9c  pop     rdi
0x18001ca9d  pop     rsi
0x18001ca9e  pop     rbp
0x18001ca9f  retn
```
