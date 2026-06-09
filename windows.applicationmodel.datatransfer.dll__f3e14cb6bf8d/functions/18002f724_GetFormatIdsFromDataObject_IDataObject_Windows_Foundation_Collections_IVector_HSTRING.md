# GetFormatIdsFromDataObject(IDataObject *,Windows::Foundation::Collections::IVector<HSTRING__ *> *)

- ea: `0x18002f724`
- end: `0x18002f941`
- name: `?GetFormatIdsFromDataObject@@YAJPEAUIDataObject@@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002f53c`

## callees

- `0x180002ad0`
- `0x180006ca0`
- `0x18002e910`
- `0x18002f724`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f8c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f811`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f8c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f7fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f8ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f7fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f8ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetFormatIdsFromDataObject(__int64 a1, __int64 a2)
{
  int DataObjectFormatName; // ebx
  unsigned int v4; // r8d
  unsigned __int64 v5; // rbx
  unsigned int v6; // r8d
  unsigned __int16 v7; // cx
  unsigned __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v12; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h]
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  WCHAR sourceString[256]; // [rsp+80h] [rbp-80h] BYREF

  v11 = 0;
  DataObjectFormatName = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)a1 + 64LL))(a1, 1, &v11);
  if ( DataObjectFormatName < 0 )
  {
LABEL_25:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
    goto LABEL_26;
  }
  while ( 1 )
  {
    v13 = 0;
    v14 = 0;
    DataObjectFormatName = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v11 + 24LL))(
                             v11,
                             1,
                             &v13);
    if ( DataObjectFormatName )
      break;
    if ( (BYTE8(v14) & 0x5D) != 0 )
    {
      DataObjectFormatName = GetDataObjectFormatName(v13, sourceString, v4);
      if ( DataObjectFormatName < 0 )
        goto LABEL_23;
      v5 = -1;
      do
        ++v5;
      while ( sourceString[v5] );
      if ( v5 > 0xFFFFFFFF )
      {
        LODWORD(v5) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(sourceString, v5, &hstringHeader, &string);
      v12 = string;
      DataObjectFormatName = AppendNoDup<HSTRING__ *>(a2, &v12);
      if ( DataObjectFormatName < 0 )
        goto LABEL_23;
      if ( (_WORD)v13 == 15 || (_WORD)v13 == word_1800AA616 || (_WORD)v13 == word_1800AA62A )
      {
        v7 = word_1800AA61E;
        if ( word_1800AA61E )
          goto LABEL_17;
      }
      else if ( (_WORD)v13 == 8 || (_WORD)v13 == 17 )
      {
        v7 = 2;
LABEL_17:
        DataObjectFormatName = GetDataObjectFormatName(v7, sourceString, v6);
        if ( DataObjectFormatName >= 0 )
        {
          v8 = -1;
          do
            ++v8;
          while ( sourceString[v8] );
          if ( v8 > 0xFFFFFFFF )
          {
            LODWORD(v8) = -1;
            RaiseException(0xC000000D, 1u, 0, 0);
          }
          WindowsCreateStringReference(sourceString, v8, &hstringHeader, &string);
          v12 = string;
          DataObjectFormatName = AppendNoDup<HSTRING__ *>(a2, &v12);
        }
      }
LABEL_23:
      if ( DataObjectFormatName )
        break;
    }
  }
  if ( DataObjectFormatName < 0 )
    goto LABEL_25;
LABEL_26:
  v9 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)DataObjectFormatName;
}

```

## disassembly

```asm
0x18002f724  mov     [rsp-8+arg_10], rbx
0x18002f729  mov     [rsp-8+arg_18], rsi
0x18002f72e  push    rbp
0x18002f72f  push    rdi
0x18002f730  push    r14
0x18002f732  lea     rbp, [rsp-190h]
0x18002f73a  sub     rsp, 290h
0x18002f741  mov     rax, cs:__security_cookie
0x18002f748  xor     rax, rsp
0x18002f74b  mov     [rbp+1A0h+var_20], rax
0x18002f752  mov     rdi, rdx
0x18002f755  xor     esi, esi
0x18002f757  mov     [rsp+2A0h+var_270], rsi
0x18002f75c  mov     rax, [rcx]
0x18002f75f  lea     r8, [rsp+2A0h+var_270]
0x18002f764  lea     edx, [rsi+1]
0x18002f767  mov     rax, [rax+40h]
0x18002f76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f770  mov     ebx, eax
0x18002f772  test    eax, eax
0x18002f774  js      loc_18002F8EC
0x18002f77a  mov     r14d, 0FFFFFFFFh
0x18002f780  xorps   xmm0, xmm0
0x18002f783  movups  [rsp+2A0h+var_260], xmm0
0x18002f788  movups  [rsp+2A0h+var_250], xmm0
0x18002f78d  mov     rcx, [rsp+2A0h+var_270]
0x18002f792  mov     rax, [rcx]
0x18002f795  xor     r9d, r9d
0x18002f798  lea     r8, [rsp+2A0h+var_260]
0x18002f79d  lea     edx, [r9+1]
0x18002f7a1  mov     rax, [rax+18h]
0x18002f7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7aa  mov     ebx, eax
0x18002f7ac  test    eax, eax
0x18002f7ae  jnz     loc_18002F8E8
0x18002f7b4  test    byte ptr [rsp+2A0h+var_250+8], 5Dh
0x18002f7b9  jz      short loc_18002F780
0x18002f7bb  lea     rdx, [rbp+1A0h+sourceString]; unsigned __int16 *
0x18002f7bf  movzx   ecx, word ptr [rsp+2A0h+var_260]; unsigned __int16
0x18002f7c4  call    ?GetDataObjectFormatName@@YAJGPEAGI@Z; GetDataObjectFormatName(ushort,ushort *,uint)
0x18002f7c9  mov     ebx, eax
0x18002f7cb  test    eax, eax
0x18002f7cd  js      loc_18002F8E0
0x18002f7d3  lea     rax, [rbp+1A0h+sourceString]
0x18002f7d7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f7db  inc     rbx
0x18002f7de  cmp     [rax+rbx*2], si
0x18002f7e2  jnz     short loc_18002F7DB
0x18002f7e4  cmp     rbx, r14
0x18002f7e7  jbe     short loc_18002F801
0x18002f7e9  mov     ebx, r14d
0x18002f7ec  xor     r9d, r9d; lpArguments
0x18002f7ef  xor     r8d, r8d; nNumberOfArguments
0x18002f7f2  lea     edx, [r9+1]; dwExceptionFlags
0x18002f7f6  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002f7fb  call    cs:__imp_RaiseException
0x18002f801  lea     r9, [rsp+2A0h+string]; string
0x18002f806  lea     r8, [rsp+2A0h+hstringHeader]; hstringHeader
0x18002f80b  mov     edx, ebx; length
0x18002f80d  lea     rcx, [rbp+1A0h+sourceString]; sourceString
0x18002f811  call    cs:__imp_WindowsCreateStringReference
0x18002f817  mov     rax, [rsp+2A0h+string]
0x18002f81c  mov     [rsp+2A0h+var_268], rax
0x18002f821  lea     rdx, [rsp+2A0h+var_268]
0x18002f826  mov     rcx, rdi
0x18002f829  call    ??$AppendNoDup@PEAUHSTRING__@@@@YAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@AEBQEAUHSTRING__@@@Z; AppendNoDup<HSTRING__ *>(Windows::Foundation::Collections::IVector<HSTRING__ *> *,HSTRING__ * const &)
0x18002f82e  mov     ebx, eax
0x18002f830  test    eax, eax
0x18002f832  js      loc_18002F8E0
0x18002f838  movzx   eax, word ptr [rsp+2A0h+var_260]
0x18002f83d  cmp     ax, 0Fh
0x18002f841  jz      short loc_18002F868
0x18002f843  cmp     ax, cs:word_1800AA616
0x18002f84a  jz      short loc_18002F868
0x18002f84c  cmp     ax, cs:word_1800AA62A
0x18002f853  jz      short loc_18002F868
0x18002f855  cmp     ax, 8
0x18002f859  jz      short loc_18002F861
0x18002f85b  cmp     ax, 11h
0x18002f85f  jnz     short loc_18002F8E0
0x18002f861  mov     ecx, 2
0x18002f866  jmp     short loc_18002F874
0x18002f868  movzx   ecx, cs:word_1800AA61E; unsigned __int16
0x18002f86f  test    cx, cx
0x18002f872  jz      short loc_18002F8E0
0x18002f874  lea     rdx, [rbp+1A0h+sourceString]; unsigned __int16 *
0x18002f878  call    ?GetDataObjectFormatName@@YAJGPEAGI@Z; GetDataObjectFormatName(ushort,ushort *,uint)
0x18002f87d  mov     ebx, eax
0x18002f87f  test    eax, eax
0x18002f881  js      short loc_18002F8E0
0x18002f883  lea     rax, [rbp+1A0h+sourceString]
0x18002f887  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f88b  inc     rbx
0x18002f88e  cmp     [rax+rbx*2], si
0x18002f892  jnz     short loc_18002F88B
0x18002f894  cmp     rbx, r14
0x18002f897  jbe     short loc_18002F8B1
0x18002f899  mov     ebx, r14d
0x18002f89c  xor     r9d, r9d; lpArguments
0x18002f89f  xor     r8d, r8d; nNumberOfArguments
0x18002f8a2  lea     edx, [r9+1]; dwExceptionFlags
0x18002f8a6  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002f8ab  call    cs:__imp_RaiseException
0x18002f8b1  lea     r9, [rsp+2A0h+string]; string
0x18002f8b6  lea     r8, [rsp+2A0h+hstringHeader]; hstringHeader
0x18002f8bb  mov     edx, ebx; length
0x18002f8bd  lea     rcx, [rbp+1A0h+sourceString]; sourceString
0x18002f8c1  call    cs:__imp_WindowsCreateStringReference
0x18002f8c7  mov     rax, [rsp+2A0h+string]
0x18002f8cc  mov     [rsp+2A0h+var_268], rax
0x18002f8d1  lea     rdx, [rsp+2A0h+var_268]
0x18002f8d6  mov     rcx, rdi
0x18002f8d9  call    ??$AppendNoDup@PEAUHSTRING__@@@@YAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@AEBQEAUHSTRING__@@@Z; AppendNoDup<HSTRING__ *>(Windows::Foundation::Collections::IVector<HSTRING__ *> *,HSTRING__ * const &)
0x18002f8de  mov     ebx, eax
0x18002f8e0  test    ebx, ebx
0x18002f8e2  jz      loc_18002F780
0x18002f8e8  test    ebx, ebx
0x18002f8ea  jns     short loc_18002F8FC
0x18002f8ec  mov     rax, [rdi]
0x18002f8ef  mov     rcx, rdi
0x18002f8f2  mov     rax, [rax+78h]
0x18002f8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8fb  nop
0x18002f8fc  mov     rcx, [rsp+2A0h+var_270]
0x18002f901  test    rcx, rcx
0x18002f904  jz      short loc_18002F918
0x18002f906  mov     [rsp+2A0h+var_270], rsi
0x18002f90b  mov     rax, [rcx]
0x18002f90e  mov     rax, [rax+10h]
0x18002f912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f917  nop
0x18002f918  mov     eax, ebx
0x18002f91a  mov     rcx, [rbp+1A0h+var_20]
0x18002f921  xor     rcx, rsp; StackCookie
0x18002f924  call    __security_check_cookie
0x18002f929  lea     r11, [rsp+2A0h+var_10]
0x18002f931  mov     rbx, [r11+30h]
0x18002f935  mov     rsi, [r11+38h]
0x18002f939  mov     rsp, r11
0x18002f93c  pop     r14
0x18002f93e  pop     rdi
0x18002f93f  pop     rbp
0x18002f940  retn
```
