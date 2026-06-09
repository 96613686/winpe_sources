# StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)

- ea: `0x1800867cc`
- end: `0x180086ae5`
- name: `?OpenByPackageAndCategory@PackageExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z`
- size: `793`
- prototype: `int(StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18007bbe8`

## callees

- `0x180004cf0`
- `0x180005150`
- `0x1800103b0`
- `0x180010c04`
- `0x180030640`
- `0x180034c24`
- `0x1800867cc`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18008699c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180086a88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180086aa2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18008699c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180086a88`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180086aa2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008683b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800868cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008691b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180086ab7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008683b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800868cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008691b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180086ab7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800869ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800869ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180086874`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180086874`

## string_xrefs

- `0x180086891`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180086a1c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180086810`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800868ac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x1800868ef`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x18008697a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180086a61`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExtension.hpp`
- `0x180086856`: `PackageExtension\Index\PackageAndCategory`
- `0x180086a43`: `PackageExtension\Index\PackageAndCategory`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow::OpenByPackageAndCategory(
        StateRepository::Cache::Entity::PackageExtensionIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 v14; // dx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v22; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+248h] [rbp+148h]
  __int64 v28; // [rsp+250h] [rbp+150h]
  _BYTE *v29; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return v7;
  }
  v9 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v9 )
    SRCacheContext_Close(v9);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v10 = *(_QWORD *)a2;
  v22 = v21;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v24 = 1;
  v11 = SRCacheContext_Open(v10, L"PackageExtension\\Index\\PackageAndCategory", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
LABEL_8:
    v12 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)v11;
  }
  if ( !*(_QWORD *)v21 )
  {
    v7 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)0x80670012LL,
      0);
LABEL_13:
    v13 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    return v7;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
  if ( v11 < 0 )
  {
    v15 = 735;
    goto LABEL_17;
  }
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, v14);
  if ( v11 < 0 )
  {
    v15 = 736;
    goto LABEL_17;
  }
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, L"windows.hostRuntime");
  if ( v11 < 0 )
  {
    v15 = 737;
    goto LABEL_17;
  }
  v22 = (int *)this;
  v23 = 0;
  v24 = 1;
  v11 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v29, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
    v15 = 740;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
    v16 = v25;
    v25 = 0;
    if ( v16 )
      SRCache_Free(v16);
    goto LABEL_8;
  }
  if ( *(_QWORD *)this )
    *((_QWORD *)this + 2) = a2;
  v17 = StateRepository::Cache::Context_NoThrow::AddToCache(
          (StateRepository::Cache::Context_NoThrow *)v21,
          L"PackageExtension\\Index\\PackageAndCategory");
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EA,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v17,
      v21[0]);
    v18 = v25;
    v25 = 0;
    if ( v18 )
      SRCache_Free(v18);
    goto LABEL_13;
  }
  v19 = v25;
  v25 = 0;
  if ( v19 )
    SRCache_Free(v19);
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x1800867cc  mov     [rsp-8+arg_18], rbx
0x1800867d1  push    rbp
0x1800867d2  push    rsi
0x1800867d3  push    rdi
0x1800867d4  push    r14
0x1800867d6  push    r15
0x1800867d8  lea     rbp, [rsp-170h]
0x1800867e0  sub     rsp, 270h
0x1800867e7  mov     rax, cs:__security_cookie
0x1800867ee  xor     rax, rsp
0x1800867f1  mov     [rbp+190h+var_30], rax
0x1800867f8  xor     r15d, r15d
0x1800867fb  mov     r14, r8
0x1800867fe  mov     rsi, rdx
0x180086801  mov     rbx, rcx
0x180086804  test    r8, r8
0x180086807  jnz     short loc_180086830
0x180086809  mov     rcx, [rbp+198h]; this
0x180086810  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180086817  mov     ebx, 80070057h
0x18008681c  mov     edx, 2D5h; void *
0x180086821  mov     r9d, ebx; char *
0x180086824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086829  mov     eax, ebx
0x18008682b  jmp     loc_180086ABF
0x180086830  mov     rcx, [rcx]
0x180086833  mov     [rbx], r15
0x180086836  test    rcx, rcx
0x180086839  jz      short loc_180086841
0x18008683b  call    cs:__imp_SRCacheContext_Close
0x180086841  mov     [rbx+8], r15d
0x180086845  lea     rax, [rsp+290h+var_270]
0x18008684a  mov     [rbx+10h], r15
0x18008684e  lea     r9, [rsp+290h+var_260]
0x180086853  mov     rcx, [rsi]
0x180086856  lea     rdx, aPackageextensi_0; "PackageExtension\\Index\\PackageAndCate"...
0x18008685d  xor     r8d, r8d
0x180086860  mov     [rsp+290h+var_268], rax
0x180086865  mov     qword ptr [rsp+290h+var_270], r15; int
0x18008686a  mov     [rsp+290h+var_260], r15
0x18008686f  mov     [rsp+290h+var_258], 1
0x180086874  call    cs:__imp_SRCacheContext_Open
0x18008687a  lea     rcx, [rsp+290h+var_268]
0x18008687f  mov     edi, eax
0x180086881  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180086886  test    edi, edi
0x180086888  jns     short loc_1800868DC
0x18008688a  mov     rcx, [rbp+198h]; this
0x180086891  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180086898  mov     r9d, edi; char *
0x18008689b  mov     edx, 18Ch; void *
0x1800868a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800868a5  mov     rcx, [rbp+198h]; this
0x1800868ac  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800868b3  mov     r9d, edi; char *
0x1800868b6  mov     edx, 2DBh; void *
0x1800868bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800868c0  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800868c5  mov     qword ptr [rsp+290h+var_270], r15
0x1800868ca  test    rcx, rcx
0x1800868cd  jz      short loc_1800868D5
0x1800868cf  call    cs:__imp_SRCacheContext_Close
0x1800868d5  mov     eax, edi
0x1800868d7  jmp     loc_180086ABF
0x1800868dc  cmp     qword ptr [rsp+290h+var_270], r15
0x1800868e1  setnz   al
0x1800868e4  test    al, al
0x1800868e6  jnz     short loc_180086926
0x1800868e8  mov     rcx, [rbp+198h]; this
0x1800868ef  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800868f6  mov     ebx, 80670012h
0x1800868fb  mov     edx, 2DCh; void *
0x180086900  mov     r9d, ebx; char *
0x180086903  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086908  mov     rcx, qword ptr [rsp+290h+var_270]
0x18008690d  mov     qword ptr [rsp+290h+var_270], r15
0x180086912  test    rcx, rcx
0x180086915  jz      loc_180086829
0x18008691b  call    cs:__imp_SRCacheContext_Close
0x180086921  jmp     loc_180086829
0x180086926  xor     edx, edx; Val
0x180086928  mov     [rsp+290h+var_250], r15
0x18008692d  mov     r8d, 200h; Size
0x180086933  lea     rcx, [rsp+290h+var_248]; void *
0x180086938  call    memset_0
0x18008693d  lea     rax, [rsp+290h+var_248]
0x180086942  mov     [rbp+190h+var_48], r15
0x180086949  mov     rdx, r14; unsigned __int64
0x18008694c  mov     [rbp+190h+var_38], rax
0x180086953  lea     rcx, [rsp+290h+var_250]; this
0x180086958  mov     [rbp+190h+var_40], 100h
0x180086963  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180086968  mov     edi, eax
0x18008696a  test    eax, eax
0x18008696c  jns     short loc_1800869A7
0x18008696e  mov     edx, 2DFh; void *
0x180086973  mov     rcx, [rbp+198h]; this
0x18008697a  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180086981  mov     r9d, edi; char *
0x180086984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086989  mov     rcx, [rsp+290h+var_250]
0x18008698e  mov     [rsp+290h+var_250], r15
0x180086993  test    rcx, rcx
0x180086996  jz      loc_1800868C0
0x18008699c  call    cs:__imp_SRCache_Free
0x1800869a2  jmp     loc_1800868C0
0x1800869a7  lea     rcx, [rsp+290h+var_250]; this
0x1800869ac  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort)
0x1800869b1  mov     edi, eax
0x1800869b3  test    eax, eax
0x1800869b5  jns     short loc_1800869BE
0x1800869b7  mov     edx, 2E0h
0x1800869bc  jmp     short loc_180086973
0x1800869be  lea     rdx, aWindowsHostrun; "windows.hostRuntime"
0x1800869c5  lea     rcx, [rsp+290h+var_250]; this
0x1800869ca  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800869cf  mov     edi, eax
0x1800869d1  test    eax, eax
0x1800869d3  jns     short loc_1800869DC
0x1800869d5  mov     edx, 2E1h
0x1800869da  jmp     short loc_180086973
0x1800869dc  mov     rdx, [rbp+190h+var_38]
0x1800869e3  lea     r9, [rsp+290h+var_260]
0x1800869e8  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800869ed  xor     r8d, r8d
0x1800869f0  mov     [rsp+290h+var_268], rbx
0x1800869f5  mov     [rsp+290h+var_260], r15
0x1800869fa  mov     [rsp+290h+var_258], 1
0x1800869ff  call    cs:__imp_SRCacheContext_OpenSubContext
0x180086a05  lea     rcx, [rsp+290h+var_268]
0x180086a0a  mov     edi, eax
0x180086a0c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180086a11  test    edi, edi
0x180086a13  jns     short loc_180086A3A
0x180086a15  mov     rcx, [rbp+198h]; this
0x180086a1c  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180086a23  mov     r9d, edi; char *
0x180086a26  mov     edx, 1B0h; void *
0x180086a2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086a30  mov     edx, 2E4h
0x180086a35  jmp     loc_180086973
0x180086a3a  cmp     [rbx], r15
0x180086a3d  jz      short loc_180086A43
0x180086a3f  mov     [rbx+10h], rsi
0x180086a43  lea     rdx, aPackageextensi_0; "PackageExtension\\Index\\PackageAndCate"...
0x180086a4a  lea     rcx, [rsp+290h+var_270]; this
0x180086a4f  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180086a54  mov     ebx, eax
0x180086a56  test    eax, eax
0x180086a58  jns     short loc_180086A93
0x180086a5a  mov     rcx, [rbp+198h]; this
0x180086a61  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180086a68  mov     r9d, eax; char *
0x180086a6b  mov     edx, 2EAh; void *
0x180086a70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086a75  mov     rcx, [rsp+290h+var_250]
0x180086a7a  mov     [rsp+290h+var_250], r15
0x180086a7f  test    rcx, rcx
0x180086a82  jz      loc_180086908
0x180086a88  call    cs:__imp_SRCache_Free
0x180086a8e  jmp     loc_180086908
0x180086a93  mov     rcx, [rsp+290h+var_250]
0x180086a98  mov     [rsp+290h+var_250], r15
0x180086a9d  test    rcx, rcx
0x180086aa0  jz      short loc_180086AA8
0x180086aa2  call    cs:__imp_SRCache_Free
0x180086aa8  mov     rcx, qword ptr [rsp+290h+var_270]
0x180086aad  mov     qword ptr [rsp+290h+var_270], r15
0x180086ab2  test    rcx, rcx
0x180086ab5  jz      short loc_180086ABD
0x180086ab7  call    cs:__imp_SRCacheContext_Close
0x180086abd  xor     eax, eax
0x180086abf  mov     rcx, [rbp+190h+var_30]
0x180086ac6  xor     rcx, rsp; StackCookie
0x180086ac9  call    __security_check_cookie
0x180086ace  mov     rbx, [rsp+290h+arg_18]
0x180086ad6  add     rsp, 270h
0x180086add  pop     r15
0x180086adf  pop     r14
0x180086ae1  pop     rdi
0x180086ae2  pop     rsi
0x180086ae3  pop     rbp
0x180086ae4  retn
```
