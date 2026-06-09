# CFciPropertiesShellExt::GetSrmErrorMessage(long,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180009124`
- end: `0x180009460`
- name: `?GetSrmErrorMessage@CFciPropertiesShellExt@@AEAAXJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `828`
- prototype: `void __fastcall(__int64, signed int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000e6d4`

## callees

- `0x1800054cc`
- `0x180009124`
- `0x18000f424`
- `0x1800106fc`
- `0x180011714`
- `0x18001623c`
- `0x180016564`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800093f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800093f2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800092bc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800092bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000935f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000935f`

## string_xrefs

- `0x18000922d`: `srm.dll`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::GetSrmErrorMessage(__int64 a1, signed int a2, __int64 a3)
{
  __int64 v3; // rdi
  _WORD *v6; // rax
  DWORD v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int64 v14; // r8
  void *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  WCHAR Buffer[4]; // [rsp+48h] [rbp-1E0h] BYREF
  unsigned __int64 *v22; // [rsp+50h] [rbp-1D8h]
  unsigned int v23; // [rsp+58h] [rbp-1D0h] BYREF
  __int64 *v24; // [rsp+60h] [rbp-1C8h]
  _com_error *v25; // [rsp+68h] [rbp-1C0h] BYREF
  const exception *v26; // [rsp+70h] [rbp-1B8h] BYREF
  _QWORD v27[3]; // [rsp+78h] [rbp-1B0h] BYREF
  int v28; // [rsp+90h] [rbp-198h]
  int v29; // [rsp+94h] [rbp-194h]
  int v30; // [rsp+98h] [rbp-190h]
  _DWORD v31[26]; // [rsp+A0h] [rbp-188h] BYREF
  void *Src; // [rsp+108h] [rbp-120h] BYREF
  __int64 v33; // [rsp+110h] [rbp-118h]
  __int64 v34; // [rsp+118h] [rbp-110h]
  unsigned __int64 v35; // [rsp+120h] [rbp-108h]
  void **v36; // [rsp+130h] [rbp-F8h] BYREF
  int v37; // [rsp+138h] [rbp-F0h]
  unsigned int v38; // [rsp+15Ch] [rbp-CCh]
  unsigned __int16 v39[8]; // [rsp+1E0h] [rbp-48h] BYREF
  __int128 v40; // [rsp+1F0h] [rbp-38h]

  v3 = a3;
  v27[0] = L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp";
  v27[1] = L"CFciPropertiesShellExt::GetSrmErrorMessage";
  v27[2] = L"FCIPROPC";
  v28 = 4634;
  v29 = 17;
  v30 = 255;
  v31[24] = 0x1000000;
  memset_0(v31, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v36, (const struct CSrmDebugInfo *)v27, 0);
  v22 = (unsigned __int64 *)(v3 + 24);
  if ( *(_QWORD *)(v3 + 24) < 8u )
    v6 = (_WORD *)v3;
  else
    v6 = *(_WORD **)v3;
  v24 = (__int64 *)(v3 + 16);
  *(_QWORD *)(v3 + 16) = 0;
  *v6 = 0;
  if ( a2 >= 0 )
  {
    v36 = &CSrmFunctionTracer::`vftable';
    goto LABEL_23;
  }
  if ( !*(_QWORD *)(a1 + 224) )
    *(_QWORD *)(a1 + 224) = ((__int64 (__fastcall *)(LPCWSTR))IsolationAwareLoadLibraryExW)(L"srm.dll");
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v37 = StringCchPrintfW(v39, 0x10u, L"0x%08lX", (unsigned int)a2);
  *(_QWORD *)Buffer = 0;
  v35 = 7;
  v34 = 0;
  LOWORD(Src) = 0;
  v7 = FormatMessageW(0x1B00u, *(LPCVOID *)(a1 + 224), a2, 0, Buffer, 0, 0);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( v7 )
    {
      std::wstring::assign(&Src, *(char **)Buffer, v7);
      std::wstring::operator+=((char *)&Src, (char *)L" (", v8, v9);
      std::wstring::operator+=((char *)&Src, (char *)v39, v10, v11);
      std::wstring::operator+=((char *)&Src, (char *)L")", v12, v13);
    }
    else
    {
      *(_QWORD *)Buffer = 0;
      v14 = -1;
      do
        ++v14;
      while ( v39[v14] );
      std::wstring::assign(&Src, (char *)v39, v14);
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v23) )
    {
      CSrmFunctionTracer::HandleHresultException(
        (CSrmFunctionTracer *)&v36,
        v23,
        L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
        L"FCIPROPC",
        L"CFciPropertiesShellExt::GetSrmErrorMessage",
        0x1250u,
        v38);
      v3 = a3;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18000934E);
      goto LABEL_15;
    }
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v25) )
      CSrmFunctionTracer::HandleComException(
        (CSrmFunctionTracer *)&v36,
        v25,
        L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
        L"FCIPROPC",
        L"CFciPropertiesShellExt::GetSrmErrorMessage",
        0x1250u,
        v38);
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      CSrmFunctionTracer::HandleStdBadAllocException(
        (CSrmFunctionTracer *)&v36,
        L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
        L"FCIPROPC",
        L"CFciPropertiesShellExt::GetSrmErrorMessage",
        0x1250u,
        v38);
      v3 = a3;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000945A);
      goto LABEL_15;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', &v26) )
      CSrmFunctionTracer::HandleStdGenericException(
        (CSrmFunctionTracer *)&v36,
        v26,
        L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
        L"FCIPROPC",
        L"CFciPropertiesShellExt::GetSrmErrorMessage",
        0x1250u,
        v38);
  }
LABEL_15:
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  if ( v37 >= 0 && (void **)v3 != &Src )
  {
    v15 = *(void **)v3;
    v16 = *(_QWORD *)(v3 + 8);
    *(_QWORD *)v3 = Src;
    *(_QWORD *)(v3 + 8) = v33;
    Src = v15;
    v33 = v16;
    v17 = *v24;
    *v24 = v34;
    v34 = v17;
    v18 = *v22;
    *v22 = v35;
    v35 = v18;
  }
  if ( v35 >= 8 )
    operator delete(Src);
  v35 = 7;
  v34 = 0;
  LOWORD(Src) = 0;
  v36 = &CSrmFunctionTracer::`vftable';
LABEL_23:
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v36);
}

```

## disassembly

```asm
0x180009124  mov     r11, rsp
0x180009127  mov     [r11+20h], rbx
0x18000912b  push    rsi
0x18000912c  push    rdi
0x18000912d  push    r14
0x18000912f  sub     rsp, 210h
0x180009136  mov     rax, cs:__security_cookie
0x18000913d  xor     rax, rsp
0x180009140  mov     [rsp+228h+var_28], rax
0x180009148  mov     rdi, r8
0x18000914b  mov     r14d, edx
0x18000914e  mov     rsi, rcx
0x180009151  mov     [rsp+228h+var_1E8], r8
0x180009156  lea     rax, [rsp+228h+var_1B0]
0x18000915b  mov     [rsp+228h+var_1D8], rax
0x180009160  lea     rax, aBaseFsFsrmClie_1; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x180009167  mov     [rsp+228h+var_1B0], rax
0x18000916c  lea     rax, aCfciproperties_12; "CFciPropertiesShellExt::GetSrmErrorMess"...
0x180009173  mov     [r11-1A8h], rax
0x18000917a  lea     rax, aFcipropc; "FCIPROPC"
0x180009181  mov     [r11-1A0h], rax
0x180009188  mov     [rsp+228h+var_198], 121Ah
0x180009193  mov     [rsp+228h+var_194], 11h
0x18000919e  mov     [rsp+228h+var_190], 0FFh
0x1800091a9  xor     ebx, ebx
0x1800091ab  mov     [rsp+228h+var_128], 1000000h
0x1800091b6  xor     edx, edx; Val
0x1800091b8  lea     r8d, [rbx+60h]; Size
0x1800091bc  lea     rcx, [r11-188h]; void *
0x1800091c3  call    memset_0
0x1800091c8  nop
0x1800091c9  xor     r8d, r8d
0x1800091cc  lea     rdx, [rsp+228h+var_1B0]
0x1800091d1  lea     rcx, [rsp+228h+var_F8]
0x1800091d9  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800091de  nop
0x1800091df  lea     rdx, [rdi+18h]
0x1800091e3  mov     [rsp+228h+var_1D8], rdx
0x1800091e8  cmp     qword ptr [rdx], 8
0x1800091ec  jb      short loc_1800091F3
0x1800091ee  mov     rax, [rdi]
0x1800091f1  jmp     short loc_1800091F6
0x1800091f3  mov     rax, rdi
0x1800091f6  lea     rdx, [rdi+10h]
0x1800091fa  mov     [rsp+228h+var_1C8], rdx
0x1800091ff  mov     [rdx], rbx
0x180009202  mov     [rax], bx
0x180009205  test    r14d, r14d
0x180009208  js      short loc_18000921E
0x18000920a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180009211  mov     [rsp+228h+var_F8], rax
0x180009219  jmp     loc_180009423
0x18000921e  cmp     [rsi+0E0h], rbx
0x180009225  jnz     short loc_180009240
0x180009227  mov     r8d, 22h ; '"'
0x18000922d  lea     rcx, aSrmDll; "srm.dll"
0x180009234  call    IsolationAwareLoadLibraryExW
0x180009239  mov     [rsi+0E0h], rax
0x180009240  xorps   xmm0, xmm0
0x180009243  movups  xmmword ptr [rsp+228h+var_48], xmm0
0x18000924b  movups  [rsp+228h+var_38], xmm0
0x180009253  mov     r9d, r14d
0x180009256  lea     r8, a0x08lx_0; "0x%08lX"
0x18000925d  mov     edx, 10h; unsigned __int64
0x180009262  lea     rcx, [rsp+228h+var_48]; unsigned __int16 *
0x18000926a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000926f  mov     [rsp+228h+var_F0], eax
0x180009276  mov     qword ptr [rsp+228h+Buffer], rbx
0x18000927b  mov     [rsp+228h+var_108], 7
0x180009287  mov     [rsp+228h+var_110], rbx
0x18000928f  mov     word ptr [rsp+228h+Src], bx
0x180009297  mov     [rsp+228h+Arguments], rbx; Arguments
0x18000929c  mov     [rsp+228h+nSize], ebx; nSize
0x1800092a0  lea     rax, [rsp+228h+Buffer]
0x1800092a5  mov     [rsp+228h+lpBuffer], rax; lpBuffer
0x1800092aa  xor     r9d, r9d; dwLanguageId
0x1800092ad  mov     r8d, r14d; dwMessageId
0x1800092b0  mov     rdx, [rsi+0E0h]; lpSource
0x1800092b7  mov     ecx, 1B00h; dwFlags
0x1800092bc  call    cs:__imp_FormatMessageW
0x1800092c2  nop
0x1800092c3  test    eax, eax
0x1800092c5  jz      short loc_18000931B
0x1800092c7  mov     r8d, eax
0x1800092ca  mov     rdx, qword ptr [rsp+228h+Buffer]; void *
0x1800092cf  lea     rcx, [rsp+228h+Src]; Src
0x1800092d7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800092dc  lea     rdx, asc_1800228E8; " ("
0x1800092e3  lea     rcx, [rsp+228h+Src]; Src
0x1800092eb  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x1800092f0  lea     rdx, [rsp+228h+var_48]; void *
0x1800092f8  lea     rcx, [rsp+228h+Src]; Src
0x180009300  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180009305  lea     rdx, asc_1800228F0; ")"
0x18000930c  lea     rcx, [rsp+228h+Src]; Src
0x180009314  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180009319  jmp     short loc_18000934C
0x18000931b  mov     qword ptr [rsp+228h+Buffer], rbx
0x180009320  lea     rax, [rsp+228h+var_48]
0x180009328  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000932c  inc     r8
0x18000932f  cmp     [rax+r8*2], bx
0x180009334  jnz     short loc_18000932C
0x180009336  lea     rdx, [rsp+228h+var_48]; void *
0x18000933e  lea     rcx, [rsp+228h+Src]; Src
0x180009346  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000934b  nop
0x18000934c  jmp     short loc_180009355
0x18000934e  mov     rdi, [rsp+228h+var_1E8]
0x180009353  xor     ebx, ebx
0x180009355  mov     rcx, qword ptr [rsp+228h+Buffer]; hMem
0x18000935a  test    rcx, rcx
0x18000935d  jz      short loc_180009365
0x18000935f  call    cs:__imp_LocalFree
0x180009365  cmp     [rsp+228h+var_F0], ebx
0x18000936c  jl      short loc_1800093DF
0x18000936e  lea     rax, [rsp+228h+Src]
0x180009376  cmp     rdi, rax
0x180009379  jz      short loc_1800093DF
0x18000937b  mov     rdx, [rdi]
0x18000937e  mov     rax, [rdi+8]
0x180009382  mov     rcx, [rsp+228h+Src]
0x18000938a  mov     [rdi], rcx
0x18000938d  mov     rcx, [rsp+228h+var_118]
0x180009395  mov     [rdi+8], rcx
0x180009399  mov     [rsp+228h+Src], rdx
0x1800093a1  mov     [rsp+228h+var_118], rax
0x1800093a9  mov     rdx, [rsp+228h+var_1C8]
0x1800093ae  mov     rcx, [rdx]
0x1800093b1  mov     rax, [rsp+228h+var_110]
0x1800093b9  mov     [rdx], rax
0x1800093bc  mov     [rsp+228h+var_110], rcx
0x1800093c4  mov     rdx, [rsp+228h+var_1D8]
0x1800093c9  mov     rcx, [rdx]
0x1800093cc  mov     rax, [rsp+228h+var_108]
0x1800093d4  mov     [rdx], rax
0x1800093d7  mov     [rsp+228h+var_108], rcx
0x1800093df  cmp     [rsp+228h+var_108], 8
0x1800093e8  jb      short loc_1800093F8
0x1800093ea  mov     rcx, [rsp+228h+Src]
0x1800093f2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800093f8  mov     [rsp+228h+var_108], 7
0x180009404  mov     [rsp+228h+var_110], rbx
0x18000940c  mov     word ptr [rsp+228h+Src], bx
0x180009414  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000941b  mov     [rsp+228h+var_F8], rax
0x180009423  lea     rcx, [rsp+228h+var_F8]; this
0x18000942b  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180009430  nop
0x180009431  mov     rcx, [rsp+228h+var_28]
0x180009439  xor     rcx, rsp; StackCookie
0x18000943c  call    __security_check_cookie
0x180009441  mov     rbx, [rsp+228h+arg_18]
0x180009449  add     rsp, 210h
0x180009450  pop     r14
0x180009452  pop     rdi
0x180009453  pop     rsi
0x180009454  retn
0x180009455  jmp     loc_18000934E
0x18000945a  jmp     loc_18000934E
```
