# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)

- ea: `0x180017750`
- end: `0x180017b5e`
- name: `?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1038`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010c30`
- `0x180014bd0`
- `0x1800170f0`
- `0x180017b70`

## callees

- `0x180010c04`
- `0x180017750`
- `0x1800326f0`
- `0x180034590`
- `0x18003506c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180017784`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800177a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180017784`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800177a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001789b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001789b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180017870`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180017870`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180017aa7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180017aa7`

## string_xrefs

- `0x180017813`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800178d4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180017abb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180017b37`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001782b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800178ad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800178ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180017952`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180017993`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800179f1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180017a4f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180017adc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180017b18`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001785d`: `CurrentDirectoryPath`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field_UInt32; // eax
  unsigned int v9; // esi
  int v10; // eax
  unsigned int v11; // esi
  __int64 v13; // rcx
  int Field_String; // eax
  int v15; // esi
  unsigned __int16 *v16; // rcx
  int v17; // esi
  int v18; // eax
  unsigned int v19; // esi
  int v20; // esi
  int v21; // esi
  __int64 v22; // rcx
  int Field_Binary; // eax
  unsigned int v24; // ebx
  int Field; // eax
  unsigned int v26; // esi
  unsigned __int16 **v27; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v28; // [rsp+28h] [rbp-20h] BYREF
  char v29; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_5;
  Field_UInt32 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Application", a2 + 8);
  v9 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v27);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CE,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)v9,
      (int)v27);
    return v9;
  }
  if ( a3 )
  {
LABEL_5:
    if ( (a3 & 2) == 0 )
      goto LABEL_8;
  }
  v10 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Index", a2 + 16);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      (int)v27);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)v11,
      (int)v27);
    return v11;
  }
  if ( a3 )
  {
LABEL_8:
    if ( (a3 & 4) == 0 )
      goto LABEL_9;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 20));
  v26 = Field;
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)Field,
      (int)v27);
    return v26;
  }
  if ( a3 )
  {
LABEL_9:
    if ( (a3 & 8) == 0 )
      goto LABEL_10;
  }
  v28 = 0;
  v27 = (unsigned __int16 **)(a2 + 24);
  v29 = 1;
  v17 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Category", &v28);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v27);
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DA,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v17,
      (int)v27);
    return (unsigned int)v17;
  }
  if ( a3 )
  {
LABEL_10:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_11;
  }
  v18 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Activation", (unsigned int *)(a2 + 32));
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DE,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v18,
      (int)v27);
    return v19;
  }
  if ( a3 )
  {
LABEL_11:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_12;
  }
  v28 = 0;
  v27 = (unsigned __int16 **)(a2 + 40);
  v29 = 1;
  v20 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"HostId", &v28);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v27);
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v20,
      (int)v27);
    return (unsigned int)v20;
  }
  if ( a3 )
  {
LABEL_12:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_13;
  }
  v28 = 0;
  v27 = (unsigned __int16 **)(a2 + 48);
  v29 = 1;
  v21 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Parameters", &v28);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v27);
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v21,
      (int)v27);
    return (unsigned int)v21;
  }
  if ( a3 )
  {
LABEL_13:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_14;
  }
  v13 = *(_QWORD *)a1;
  v27 = (unsigned __int16 **)(a2 + 56);
  v28 = 0;
  v29 = 1;
  Field_String = SRCacheContext_GetField_String(v13, L"CurrentDirectoryPath", &v28);
  v15 = Field_String;
  if ( Field_String < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v27);
  else
    v15 = 0;
  if ( v29 )
  {
    v16 = *v27;
    *v27 = v28;
    if ( v16 )
      SRCache_Free(v16);
  }
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3EA,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v15,
      (int)v27);
    return (unsigned int)v15;
  }
  if ( a3 )
  {
LABEL_14:
    if ( (a3 & 0x100) == 0 )
    {
LABEL_15:
      *(_QWORD *)a2 = a4;
      return 0;
    }
  }
  v22 = *(_QWORD *)a1;
  v27 = (unsigned __int16 **)(a2 + 64);
  v28 = 0;
  v29 = 1;
  Field_Binary = SRCacheContext_GetField_Binary(v22, L"_Dictionary", a2 + 72, &v28);
  v24 = Field_Binary;
  if ( Field_Binary >= 0 )
  {
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v27);
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x24F,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
    (const char *)(unsigned int)Field_Binary,
    (int)v27);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v27);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3EE,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
    (const char *)v24,
    (int)v27);
  return v24;
}

```

## disassembly

```asm
0x180017750  push    rbp
0x180017752  push    rbx
0x180017753  push    rsi
0x180017754  push    rdi
0x180017755  push    r14
0x180017757  push    r15
0x180017759  mov     rbp, rsp
0x18001775c  sub     rsp, 48h
0x180017760  mov     r14, r9
0x180017763  mov     rbx, r8
0x180017766  mov     rdi, rdx
0x180017769  mov     r15, rcx
0x18001776c  test    r8, r8
0x18001776f  jz      short loc_180017776
0x180017771  test    bl, 1
0x180017774  jz      short loc_180017795
0x180017776  mov     rcx, [rcx]
0x180017779  lea     r8, [rdx+8]
0x18001777d  lea     rdx, aApplication_0; "Application"
0x180017784  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18001778a  mov     esi, eax
0x18001778c  test    eax, eax
0x18001778e  js      short loc_18001780F
0x180017790  test    rbx, rbx
0x180017793  jz      short loc_18001779A
0x180017795  test    bl, 2
0x180017798  jz      short loc_1800177C1
0x18001779a  mov     rcx, [r15]
0x18001779d  lea     r8, [rdi+10h]
0x1800177a1  lea     rdx, aIndex; "Index"
0x1800177a8  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800177ae  mov     esi, eax
0x1800177b0  test    eax, eax
0x1800177b2  js      loc_1800178D0
0x1800177b8  test    rbx, rbx
0x1800177bb  jz      loc_180017AF7
0x1800177c1  test    bl, 4
0x1800177c4  jnz     loc_180017AF7
0x1800177ca  test    bl, 8
0x1800177cd  jnz     loc_180017918
0x1800177d3  test    bl, 10h
0x1800177d6  jnz     loc_180017976
0x1800177dc  test    bl, 20h
0x1800177df  jnz     loc_1800179B7
0x1800177e5  test    bl, 40h
0x1800177e8  jnz     loc_180017A15
0x1800177ee  test    bl, bl
0x1800177f0  js      short loc_18001784E
0x1800177f2  bt      rbx, 8
0x1800177f7  jb      loc_180017A81
0x1800177fd  mov     [rdi], r14
0x180017800  xor     eax, eax
0x180017802  add     rsp, 48h
0x180017806  pop     r15
0x180017808  pop     r14
0x18001780a  pop     rdi
0x18001780b  pop     rsi
0x18001780c  pop     rbx
0x18001780d  pop     rbp
0x18001780e  retn
0x18001780f  mov     rcx, [rbp+30h]; this
0x180017813  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001781a  mov     r9d, esi; char *
0x18001781d  mov     edx, 221h; void *
0x180017822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017827  mov     rcx, [rbp+30h]; this
0x18001782b  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017832  mov     r9d, esi; char *
0x180017835  mov     edx, 3CEh; void *
0x18001783a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001783f  mov     eax, esi
0x180017841  add     rsp, 48h
0x180017845  pop     r15
0x180017847  pop     r14
0x180017849  pop     rdi
0x18001784a  pop     rsi
0x18001784b  pop     rbx
0x18001784c  pop     rbp
0x18001784d  retn
0x18001784e  mov     rcx, [r15]
0x180017851  lea     rax, [rdi+38h]
0x180017855  lea     r8, [rbp+var_20]
0x180017859  mov     [rbp+var_28], rax
0x18001785d  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x180017864  mov     [rbp+var_20], 0
0x18001786c  mov     [rbp+var_18], 1
0x180017870  call    cs:__imp_SRCacheContext_GetField_String
0x180017876  mov     esi, eax
0x180017878  test    eax, eax
0x18001787a  js      loc_180017B33
0x180017880  xor     esi, esi
0x180017882  cmp     [rbp+var_18], 0
0x180017886  jz      short loc_1800178A1
0x180017888  mov     rdx, [rbp+var_28]
0x18001788c  mov     rax, [rbp+var_20]
0x180017890  mov     rcx, [rdx]
0x180017893  mov     [rdx], rax
0x180017896  test    rcx, rcx
0x180017899  jz      short loc_1800178A1
0x18001789b  call    cs:__imp_SRCache_Free
0x1800178a1  test    esi, esi
0x1800178a3  jns     loc_180017A78
0x1800178a9  mov     rcx, [rbp+30h]; this
0x1800178ad  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800178b4  mov     r9d, esi; char *
0x1800178b7  mov     edx, 3EAh; void *
0x1800178bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800178c1  mov     eax, esi
0x1800178c3  add     rsp, 48h
0x1800178c7  pop     r15
0x1800178c9  pop     r14
0x1800178cb  pop     rdi
0x1800178cc  pop     rsi
0x1800178cd  pop     rbx
0x1800178ce  pop     rbp
0x1800178cf  retn
0x1800178d0  mov     rcx, [rbp+30h]; this
0x1800178d4  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800178db  mov     r9d, esi; char *
0x1800178de  mov     edx, 221h; void *
0x1800178e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800178e8  mov     rcx, [rbp+30h]; this
0x1800178ec  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800178f3  mov     r9d, esi; char *
0x1800178f6  mov     edx, 3D2h; void *
0x1800178fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017900  mov     eax, esi
0x180017902  add     rsp, 48h
0x180017906  pop     r15
0x180017908  pop     r14
0x18001790a  pop     rdi
0x18001790b  pop     rsi
0x18001790c  pop     rbx
0x18001790d  pop     rbp
0x18001790e  retn
0x18001790f  test    rbx, rbx
0x180017912  jnz     loc_1800177CA
0x180017918  lea     rax, [rdi+18h]
0x18001791c  mov     [rbp+var_20], 0
0x180017924  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180017928  mov     [rbp+var_28], rax
0x18001792c  lea     rdx, aCategory; "Category"
0x180017933  mov     [rbp+var_18], 1
0x180017937  mov     rcx, r15; this
0x18001793a  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001793f  lea     rcx, [rbp+var_28]
0x180017943  mov     esi, eax
0x180017945  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18001794a  test    esi, esi
0x18001794c  jns     short loc_18001796D
0x18001794e  mov     rcx, [rbp+30h]; this
0x180017952  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017959  mov     r9d, esi; char *
0x18001795c  mov     edx, 3DAh; void *
0x180017961  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017966  mov     eax, esi
0x180017968  jmp     loc_180017802
0x18001796d  test    rbx, rbx
0x180017970  jnz     loc_1800177D3
0x180017976  lea     r8, [rdi+20h]; unsigned int *
0x18001797a  mov     rcx, r15; this
0x18001797d  lea     rdx, aActivation; "Activation"
0x180017984  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180017989  mov     esi, eax
0x18001798b  test    eax, eax
0x18001798d  jns     short loc_1800179AE
0x18001798f  mov     rcx, [rbp+30h]; this
0x180017993  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001799a  mov     r9d, eax; char *
0x18001799d  mov     edx, 3DEh; void *
0x1800179a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800179a7  mov     eax, esi
0x1800179a9  jmp     loc_180017802
0x1800179ae  test    rbx, rbx
0x1800179b1  jnz     loc_1800177DC
0x1800179b7  lea     rax, [rdi+28h]
0x1800179bb  mov     [rbp+var_20], 0
0x1800179c3  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800179c7  mov     [rbp+var_28], rax
0x1800179cb  lea     rdx, aHostid; "HostId"
0x1800179d2  mov     [rbp+var_18], 1
0x1800179d6  mov     rcx, r15; this
0x1800179d9  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800179de  lea     rcx, [rbp+var_28]
0x1800179e2  mov     esi, eax
0x1800179e4  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800179e9  test    esi, esi
0x1800179eb  jns     short loc_180017A0C
0x1800179ed  mov     rcx, [rbp+30h]; this
0x1800179f1  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800179f8  mov     r9d, esi; char *
0x1800179fb  mov     edx, 3E2h; void *
0x180017a00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017a05  mov     eax, esi
0x180017a07  jmp     loc_180017802
0x180017a0c  test    rbx, rbx
0x180017a0f  jnz     loc_1800177E5
0x180017a15  lea     rax, [rdi+30h]
0x180017a19  mov     [rbp+var_20], 0
0x180017a21  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180017a25  mov     [rbp+var_28], rax
0x180017a29  lea     rdx, aParameters; "Parameters"
0x180017a30  mov     [rbp+var_18], 1
0x180017a34  mov     rcx, r15; this
0x180017a37  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180017a3c  lea     rcx, [rbp+var_28]
0x180017a40  mov     esi, eax
0x180017a42  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180017a47  test    esi, esi
0x180017a49  jns     short loc_180017A6A
0x180017a4b  mov     rcx, [rbp+30h]; this
0x180017a4f  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017a56  mov     r9d, esi; char *
0x180017a59  mov     edx, 3E6h; void *
0x180017a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017a63  mov     eax, esi
0x180017a65  jmp     loc_180017802
0x180017a6a  test    rbx, rbx
0x180017a6d  jnz     loc_1800177EE
0x180017a73  jmp     loc_18001784E
0x180017a78  test    rbx, rbx
0x180017a7b  jnz     loc_1800177F2
0x180017a81  mov     rcx, [r15]
0x180017a84  lea     rax, [rdi+40h]
0x180017a88  lea     r8, [rdi+48h]
0x180017a8c  mov     [rbp+var_28], rax
0x180017a90  lea     r9, [rbp+var_20]
0x180017a94  mov     [rbp+var_20], 0
0x180017a9c  lea     rdx, aDictionary; "_Dictionary"
0x180017aa3  mov     [rbp+var_18], 1
0x180017aa7  call    cs:__imp_SRCacheContext_GetField_Binary
0x180017aad  mov     ebx, eax
0x180017aaf  test    eax, eax
0x180017ab1  jns     loc_180017B50
0x180017ab7  mov     rcx, [rbp+30h]; this
0x180017abb  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017ac2  mov     r9d, eax; char *
0x180017ac5  mov     edx, 24Fh; void *
0x180017aca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017acf  lea     rcx, [rbp+var_28]
0x180017ad3  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180017ad8  mov     rcx, [rbp+30h]; this
0x180017adc  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017ae3  mov     r9d, ebx; char *
0x180017ae6  mov     edx, 3EEh; void *
0x180017aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017af0  mov     eax, ebx
0x180017af2  jmp     loc_180017802
0x180017af7  lea     r8, [rdi+14h]; unsigned int *
0x180017afb  mov     rcx, r15; this
0x180017afe  lea     rdx, aFlags; "Flags"
0x180017b05  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180017b0a  mov     esi, eax
0x180017b0c  test    eax, eax
0x180017b0e  jns     loc_18001790F
0x180017b14  mov     rcx, [rbp+30h]; this
0x180017b18  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017b1f  mov     r9d, eax; char *
0x180017b22  mov     edx, 3D6h; void *
0x180017b27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b2c  mov     eax, esi
0x180017b2e  jmp     loc_180017802
0x180017b33  mov     rcx, [rbp+30h]; this
0x180017b37  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x180017b3e  mov     r9d, eax; char *
0x180017b41  mov     edx, 246h; void *
0x180017b46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b4b  jmp     loc_180017882
0x180017b50  lea     rcx, [rbp+var_28]
0x180017b54  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180017b59  jmp     loc_1800177FD
```
