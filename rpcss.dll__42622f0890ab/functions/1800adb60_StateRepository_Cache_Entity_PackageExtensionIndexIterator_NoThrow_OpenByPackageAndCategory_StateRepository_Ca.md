# StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x1800adb60`
- end: `0x1800adf16`
- name: `?OpenByPackageAndCategory@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `950`
- prototype: `__int64 __fastcall(StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800722a0`

## callees

- `0x1800211f0`
- `0x1800217e4`
- `0x18002ba28`
- `0x180068bb0`
- `0x18006df78`
- `0x1800adb60`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800add0d`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800add0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800adbcf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800adc6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800adcb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800adee8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800adbcf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800adc6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800adcb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800adee8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800adc10`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800adc10`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800add7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800adeb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800aded3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800add7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800adeb9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800aded3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800ade2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800ade2e`

## string_xrefs

- `0x1800add1e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800addab`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800adc2f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800ade4d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800adba4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800adc4a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800adc8d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800add5c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800ade92`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800adbec`: `PackageExtension\Index\PackageAndCategory`
- `0x1800ade74`: `PackageExtension\Index\PackageAndCategory`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(
        StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  bool v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v27[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+238h] [rbp+138h]
  __int64 v29; // [rsp+240h] [rbp+140h]
  _BYTE *v30; // [rsp+248h] [rbp+148h]
  unsigned __int16 v31[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v32; // [rsp+258h] [rbp+158h] BYREF
  char v33; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)0x80070057LL,
      v25[0]);
    return v7;
  }
  v9 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v9 )
    SRCacheContext_Close(v9, a2);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v10 = *(_QWORD *)a2;
  *(_QWORD *)v31 = v25;
  *(_QWORD *)v25 = 0;
  v32 = 0;
  v33 = 1;
  v11 = SRCacheContext_Open(v10, L"PackageExtension\\Index\\PackageAndCategory", 0, &v32);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v31);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v25[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v11,
      v25[0]);
LABEL_8:
    v13 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v13 )
      SRCacheContext_Close(v13, v12);
    return (unsigned int)v11;
  }
  if ( !*(_QWORD *)v25 )
  {
    v7 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v15 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v15 )
      SRCacheContext_Close(v15, v14);
    return v7;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v29 = 256;
  v30 = v27;
  if ( (unsigned int)_o__ui64tow_s(a3, v31, 17) )
  {
    v11 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v25[0]);
LABEL_18:
    v17 = 735;
    goto LABEL_19;
  }
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, v31);
  if ( v11 < 0 )
    goto LABEL_18;
  v19 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v26, v28 + 2, v16);
  v11 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v19,
      v25[0]);
    v17 = 736;
    goto LABEL_19;
  }
  *(_DWORD *)&v30[2 * v28++] = 94;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, L"windows.hostRuntime");
  if ( v11 < 0 )
  {
    v17 = 737;
    goto LABEL_19;
  }
  *(_QWORD *)v31 = this;
  v32 = 0;
  v33 = 1;
  v11 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v30, 0, &v32);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v31);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v25[0]);
    v17 = 740;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v11,
      v25[0]);
    v18 = v26;
    v26 = 0;
    if ( v18 )
      SRCache_Free();
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v20 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v25,
          L"PackageExtension\\Index\\PackageAndCategory");
  v7 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EA,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v20,
      v25[0]);
    v22 = v26;
    v26 = 0;
    if ( v22 )
      SRCache_Free();
    goto LABEL_13;
  }
  v23 = v26;
  v26 = 0;
  if ( v23 )
    SRCache_Free();
  v24 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v24 )
    SRCacheContext_Close(v24, v21);
  return 0;
}

```

## disassembly

```asm
0x1800adb60  mov     [rsp-8+arg_18], rbx
0x1800adb65  push    rbp
0x1800adb66  push    rsi
0x1800adb67  push    rdi
0x1800adb68  push    r14
0x1800adb6a  push    r15
0x1800adb6c  lea     rbp, [rsp-180h]
0x1800adb74  sub     rsp, 280h
0x1800adb7b  mov     rax, cs:__security_cookie
0x1800adb82  xor     rax, rsp
0x1800adb85  mov     [rbp+1A0h+var_28], rax
0x1800adb8c  xor     r15d, r15d
0x1800adb8f  mov     r14, r8
0x1800adb92  mov     rsi, rdx
0x1800adb95  mov     rbx, rcx
0x1800adb98  test    r8, r8
0x1800adb9b  jnz     short loc_1800ADBC4
0x1800adb9d  mov     rcx, [rbp+1A8h]; this
0x1800adba4  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800adbab  mov     ebx, 80070057h
0x1800adbb0  mov     edx, 2D5h; void *
0x1800adbb5  mov     r9d, ebx; char *
0x1800adbb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adbbd  mov     eax, ebx
0x1800adbbf  jmp     loc_1800ADEF0
0x1800adbc4  mov     rcx, [rcx]
0x1800adbc7  mov     [rbx], r15
0x1800adbca  test    rcx, rcx
0x1800adbcd  jz      short loc_1800ADBD5
0x1800adbcf  call    cs:__imp_SRCacheContext_Close
0x1800adbd5  mov     [rbx+8], r15d
0x1800adbd9  lea     rax, [rsp+2A0h+var_280]
0x1800adbde  mov     [rbx+10h], r15
0x1800adbe2  lea     r9, [rbp+1A0h+var_48]
0x1800adbe9  mov     rcx, [rsi]
0x1800adbec  lea     rdx, aPackageextensi_0; "PackageExtension\\Index\\PackageAndCate"...
0x1800adbf3  xor     r8d, r8d
0x1800adbf6  mov     qword ptr [rbp+1A0h+var_50], rax
0x1800adbfd  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1800adc02  mov     [rbp+1A0h+var_48], r15
0x1800adc09  mov     [rbp+1A0h+var_40], 1
0x1800adc10  call    cs:__imp_SRCacheContext_Open
0x1800adc16  lea     rcx, [rbp+1A0h+var_50]
0x1800adc1d  mov     edi, eax
0x1800adc1f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800adc24  test    edi, edi
0x1800adc26  jns     short loc_1800ADC7A
0x1800adc28  mov     rcx, [rbp+1A8h]; this
0x1800adc2f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800adc36  mov     r9d, edi; char *
0x1800adc39  mov     edx, 18Ch; void *
0x1800adc3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adc43  mov     rcx, [rbp+1A8h]; this
0x1800adc4a  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800adc51  mov     r9d, edi; char *
0x1800adc54  mov     edx, 2DBh; void *
0x1800adc59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adc5e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800adc63  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800adc68  test    rcx, rcx
0x1800adc6b  jz      short loc_1800ADC73
0x1800adc6d  call    cs:__imp_SRCacheContext_Close
0x1800adc73  mov     eax, edi
0x1800adc75  jmp     loc_1800ADEF0
0x1800adc7a  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1800adc7f  setnz   al
0x1800adc82  test    al, al
0x1800adc84  jnz     short loc_1800ADCC4
0x1800adc86  mov     rcx, [rbp+1A8h]; this
0x1800adc8d  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800adc94  mov     ebx, 80670012h
0x1800adc99  mov     edx, 2DCh; void *
0x1800adc9e  mov     r9d, ebx; char *
0x1800adca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adca6  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800adcab  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800adcb0  test    rcx, rcx
0x1800adcb3  jz      loc_1800ADBBD
0x1800adcb9  call    cs:__imp_SRCacheContext_Close
0x1800adcbf  jmp     loc_1800ADBBD
0x1800adcc4  xor     edx, edx; Val
0x1800adcc6  mov     [rsp+2A0h+var_270], r15
0x1800adccb  mov     r8d, 200h; Size
0x1800adcd1  lea     rcx, [rsp+2A0h+var_268]; void *
0x1800adcd6  call    memset_0
0x1800adcdb  mov     r9d, 10h
0x1800adce1  mov     [rbp+1A0h+var_68], r15
0x1800adce8  lea     rax, [rsp+2A0h+var_268]
0x1800adced  mov     [rbp+1A0h+var_60], 100h
0x1800adcf8  lea     rdx, [rbp+1A0h+var_50]
0x1800adcff  mov     [rbp+1A0h+var_58], rax
0x1800add06  mov     rcx, r14
0x1800add09  lea     r8d, [r9+1]
0x1800add0d  call    cs:__imp__o__ui64tow_s
0x1800add13  test    eax, eax
0x1800add15  jz      short loc_1800ADD39
0x1800add17  mov     rcx, [rbp+1A8h]; this
0x1800add1e  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800add25  mov     edi, 8000FFFFh
0x1800add2a  mov     edx, 166h; void *
0x1800add2f  mov     r9d, edi; char *
0x1800add32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800add37  jmp     short loc_1800ADD50
0x1800add39  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x1800add40  lea     rcx, [rsp+2A0h+var_270]; this
0x1800add45  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800add4a  mov     edi, eax
0x1800add4c  test    eax, eax
0x1800add4e  jns     short loc_1800ADD89
0x1800add50  mov     edx, 2DFh; void *
0x1800add55  mov     rcx, [rbp+1A8h]; this
0x1800add5c  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800add63  mov     r9d, edi; char *
0x1800add66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800add6b  mov     rcx, [rsp+2A0h+var_270]
0x1800add70  mov     [rsp+2A0h+var_270], r15
0x1800add75  test    rcx, rcx
0x1800add78  jz      loc_1800ADC5E
0x1800add7e  call    cs:__imp_SRCache_Free
0x1800add84  jmp     loc_1800ADC5E
0x1800add89  mov     rdx, [rbp+1A0h+var_68]
0x1800add90  lea     rcx, [rsp+2A0h+var_270]; this
0x1800add95  add     rdx, 2; unsigned __int64
0x1800add99  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x1800add9e  mov     edi, eax
0x1800adda0  test    eax, eax
0x1800adda2  jns     short loc_1800ADDC6
0x1800adda4  mov     rcx, [rbp+1A8h]; this
0x1800addab  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800addb2  mov     r9d, eax; char *
0x1800addb5  mov     edx, 16Dh; void *
0x1800addba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800addbf  mov     edx, 2E0h
0x1800addc4  jmp     short loc_1800ADD55
0x1800addc6  mov     rdx, [rbp+1A0h+var_68]
0x1800addcd  mov     rcx, [rbp+1A0h+var_58]
0x1800addd4  mov     dword ptr [rcx+rdx*2], 5Eh ; '^'
0x1800adddb  lea     rdx, ?ExtensionCategoryHostRuntime@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.hostRuntime"
0x1800adde2  inc     [rbp+1A0h+var_68]
0x1800adde9  lea     rcx, [rsp+2A0h+var_270]; this
0x1800addee  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800addf3  mov     edi, eax
0x1800addf5  test    eax, eax
0x1800addf7  jns     short loc_1800ADE03
0x1800addf9  mov     edx, 2E1h
0x1800addfe  jmp     loc_1800ADD55
0x1800ade03  mov     rdx, [rbp+1A0h+var_58]
0x1800ade0a  lea     r9, [rbp+1A0h+var_48]
0x1800ade11  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800ade16  xor     r8d, r8d
0x1800ade19  mov     qword ptr [rbp+1A0h+var_50], rbx
0x1800ade20  mov     [rbp+1A0h+var_48], r15
0x1800ade27  mov     [rbp+1A0h+var_40], 1
0x1800ade2e  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800ade34  lea     rcx, [rbp+1A0h+var_50]
0x1800ade3b  mov     edi, eax
0x1800ade3d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800ade42  test    edi, edi
0x1800ade44  jns     short loc_1800ADE6B
0x1800ade46  mov     rcx, [rbp+1A8h]; this
0x1800ade4d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ade54  mov     r9d, edi; char *
0x1800ade57  mov     edx, 1B0h; void *
0x1800ade5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ade61  mov     edx, 2E4h
0x1800ade66  jmp     loc_1800ADD55
0x1800ade6b  cmp     [rbx], r15
0x1800ade6e  jz      short loc_1800ADE74
0x1800ade70  mov     [rbx+10h], rsi
0x1800ade74  lea     rdx, aPackageextensi_0; "PackageExtension\\Index\\PackageAndCate"...
0x1800ade7b  lea     rcx, [rsp+2A0h+var_280]; this
0x1800ade80  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800ade85  mov     ebx, eax
0x1800ade87  test    eax, eax
0x1800ade89  jns     short loc_1800ADEC4
0x1800ade8b  mov     rcx, [rbp+1A8h]; this
0x1800ade92  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ade99  mov     r9d, eax; char *
0x1800ade9c  mov     edx, 2EAh; void *
0x1800adea1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adea6  mov     rcx, [rsp+2A0h+var_270]
0x1800adeab  mov     [rsp+2A0h+var_270], r15
0x1800adeb0  test    rcx, rcx
0x1800adeb3  jz      loc_1800ADCA6
0x1800adeb9  call    cs:__imp_SRCache_Free
0x1800adebf  jmp     loc_1800ADCA6
0x1800adec4  mov     rcx, [rsp+2A0h+var_270]
0x1800adec9  mov     [rsp+2A0h+var_270], r15
0x1800adece  test    rcx, rcx
0x1800aded1  jz      short loc_1800ADED9
0x1800aded3  call    cs:__imp_SRCache_Free
0x1800aded9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800adede  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800adee3  test    rcx, rcx
0x1800adee6  jz      short loc_1800ADEEE
0x1800adee8  call    cs:__imp_SRCacheContext_Close
0x1800adeee  xor     eax, eax
0x1800adef0  mov     rcx, [rbp+1A0h+var_28]
0x1800adef7  xor     rcx, rsp; StackCookie
0x1800adefa  call    __security_check_cookie
0x1800adeff  mov     rbx, [rsp+2A0h+arg_18]
0x1800adf07  add     rsp, 280h
0x1800adf0e  pop     r15
0x1800adf10  pop     r14
0x1800adf12  pop     rdi
0x1800adf13  pop     rsi
0x1800adf14  pop     rbp
0x1800adf15  retn
```
