# StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::OpenByHostName(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x18000ad54`
- end: `0x18000b06b`
- name: `?OpenByHostName@DynamicAppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `791`
- prototype: `int(StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008db8`

## callees

- `0x18000ad54`
- `0x1800103b0`
- `0x180010c04`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000aee3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000af6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000af8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000aee3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000af6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000af8d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ad97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000adf4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aea5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aef8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000af80`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000afa2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ad97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000adf4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aea5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aef8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000af80`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000afa2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000ae81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000ae81`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000add0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000add0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000aec8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000aec8`

## string_xrefs

- `0x18000af48`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x18000afb6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x18000aff8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x18000b015`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x18000adb2`: `DynamicAppUriHandler\Index\HostName`
- `0x18000aec1`: `DynamicAppUriHandler\Index\HostName`
- `0x18000af2d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000afdd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000b044`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow::OpenByHostName(
        StateRepository::Cache::Entity::DynamicAppUriHandlerIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+248h] [rbp+148h]
  __int64 v28; // [rsp+250h] [rbp+150h]
  _BYTE *v29; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v4 )
    SRCacheContext_Close(v4);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = *(_QWORD *)a2;
  v22 = v21;
  *(_QWORD *)v21 = 0;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_Open(v7, L"DynamicAppUriHandler\\Index\\HostName", 0, &v23);
  if ( v24 )
  {
    v9 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
  }
  else
  {
    if ( !*(_QWORD *)v21 )
    {
      v12 = -2140733422;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
        (const char *)0x80670012LL,
        0);
LABEL_23:
      v17 = *(_QWORD *)v21;
      *(_QWORD *)v21 = 0;
      if ( v17 )
        SRCacheContext_Close(v17);
      return v12;
    }
    v25 = 0;
    memset_0(v26, 0, sizeof(v26));
    v27 = 0;
    v29 = v26;
    v28 = 256;
    v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a3);
    if ( v8 < 0 )
    {
      v20 = 699;
    }
    else
    {
      v22 = (int *)this;
      v23 = 0;
      v24 = 1;
      v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v29, 0, &v23);
      if ( v24 )
      {
        v10 = *(_QWORD *)v22;
        *(_QWORD *)v22 = v23;
        if ( v10 )
          SRCacheContext_Close(v10);
      }
      if ( v8 >= 0 )
      {
        if ( *(_QWORD *)this )
          *((_QWORD *)this + 2) = a2;
        v11 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"DynamicAppUriHandler\\Index\\HostName");
        v12 = v11;
        if ( v11 >= 0 )
        {
          v13 = v25;
          v25 = 0;
          if ( v13 )
            SRCache_Free(v13);
          v14 = *(_QWORD *)v21;
          *(_QWORD *)v21 = 0;
          if ( v14 )
            SRCacheContext_Close(v14);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
          (const char *)(unsigned int)v11,
          v21[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C4,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
          (const char *)v12,
          v21[0]);
        v16 = v25;
        v25 = 0;
        if ( v16 )
          SRCache_Free(v16);
        goto LABEL_23;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v8,
        v21[0]);
      v20 = 702;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
    v19 = v25;
    v25 = 0;
    if ( v19 )
      SRCache_Free(v19);
  }
  v18 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ad54  mov     [rsp-8+arg_18], rbx
0x18000ad59  push    rbp
0x18000ad5a  push    rsi
0x18000ad5b  push    rdi
0x18000ad5c  push    r14
0x18000ad5e  push    r15
0x18000ad60  lea     rbp, [rsp-170h]
0x18000ad68  sub     rsp, 270h
0x18000ad6f  mov     rax, cs:__security_cookie
0x18000ad76  xor     rax, rsp
0x18000ad79  mov     [rbp+190h+var_30], rax
0x18000ad80  mov     rbx, rcx
0x18000ad83  xor     r15d, r15d
0x18000ad86  mov     rcx, [rcx]
0x18000ad89  mov     r14, r8
0x18000ad8c  mov     rsi, rdx
0x18000ad8f  mov     [rbx], r15
0x18000ad92  test    rcx, rcx
0x18000ad95  jz      short loc_18000AD9D
0x18000ad97  call    cs:__imp_SRCacheContext_Close
0x18000ad9d  mov     [rbx+8], r15d
0x18000ada1  lea     rax, [rsp+290h+var_270]
0x18000ada6  mov     [rbx+10h], r15
0x18000adaa  lea     r9, [rsp+290h+var_260]
0x18000adaf  mov     rcx, [rsi]
0x18000adb2  lea     rdx, aDynamicappurih_5; "DynamicAppUriHandler\\Index\\HostName"
0x18000adb9  xor     r8d, r8d
0x18000adbc  mov     [rsp+290h+var_268], rax
0x18000adc1  mov     qword ptr [rsp+290h+var_270], r15; int
0x18000adc6  mov     [rsp+290h+var_260], r15
0x18000adcb  mov     [rsp+290h+var_258], 1
0x18000add0  call    cs:__imp_SRCacheContext_Open
0x18000add6  mov     edi, eax
0x18000add8  cmp     [rsp+290h+var_258], r15b
0x18000addd  jz      short loc_18000ADFA
0x18000addf  mov     r8, [rsp+290h+var_268]
0x18000ade4  mov     rdx, [rsp+290h+var_260]
0x18000ade9  mov     rcx, [r8]
0x18000adec  mov     [r8], rdx
0x18000adef  test    rcx, rcx
0x18000adf2  jz      short loc_18000ADFA
0x18000adf4  call    cs:__imp_SRCacheContext_Close
0x18000adfa  test    edi, edi
0x18000adfc  js      loc_18000AFD6
0x18000ae02  cmp     qword ptr [rsp+290h+var_270], r15
0x18000ae07  setnz   al
0x18000ae0a  test    al, al
0x18000ae0c  jz      loc_18000B00E
0x18000ae12  xor     edx, edx; Val
0x18000ae14  mov     [rsp+290h+var_250], r15
0x18000ae19  mov     r8d, 200h; Size
0x18000ae1f  lea     rcx, [rsp+290h+var_248]; void *
0x18000ae24  call    memset_0
0x18000ae29  lea     rax, [rsp+290h+var_248]
0x18000ae2e  mov     [rbp+190h+var_48], r15
0x18000ae35  mov     rdx, r14; unsigned __int16 *
0x18000ae38  mov     [rbp+190h+var_38], rax
0x18000ae3f  lea     rcx, [rsp+290h+var_250]; this
0x18000ae44  mov     [rbp+190h+var_40], 100h
0x18000ae4f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000ae54  mov     edi, eax
0x18000ae56  test    eax, eax
0x18000ae58  js      loc_18000B033
0x18000ae5e  mov     rdx, [rbp+190h+var_38]
0x18000ae65  lea     r9, [rsp+290h+var_260]
0x18000ae6a  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000ae6f  xor     r8d, r8d
0x18000ae72  mov     [rsp+290h+var_268], rbx
0x18000ae77  mov     [rsp+290h+var_260], r15
0x18000ae7c  mov     [rsp+290h+var_258], 1
0x18000ae81  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000ae87  mov     edi, eax
0x18000ae89  cmp     [rsp+290h+var_258], r15b
0x18000ae8e  jz      short loc_18000AEAB
0x18000ae90  mov     r8, [rsp+290h+var_268]
0x18000ae95  mov     rdx, [rsp+290h+var_260]
0x18000ae9a  mov     rcx, [r8]
0x18000ae9d  mov     [r8], rdx
0x18000aea0  test    rcx, rcx
0x18000aea3  jz      short loc_18000AEAB
0x18000aea5  call    cs:__imp_SRCacheContext_Close
0x18000aeab  test    edi, edi
0x18000aead  js      loc_18000B03D
0x18000aeb3  cmp     [rbx], r15
0x18000aeb6  jnz     loc_18000B062
0x18000aebc  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000aec1  lea     rdx, aDynamicappurih_5; "DynamicAppUriHandler\\Index\\HostName"
0x18000aec8  call    cs:__imp_SRCacheContext_AddToCache
0x18000aece  mov     ebx, eax
0x18000aed0  test    eax, eax
0x18000aed2  js      short loc_18000AF26
0x18000aed4  mov     rcx, [rsp+290h+var_250]
0x18000aed9  mov     [rsp+290h+var_250], r15
0x18000aede  test    rcx, rcx
0x18000aee1  jz      short loc_18000AEE9
0x18000aee3  call    cs:__imp_SRCache_Free
0x18000aee9  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000aeee  mov     qword ptr [rsp+290h+var_270], r15
0x18000aef3  test    rcx, rcx
0x18000aef6  jz      short loc_18000AEFE
0x18000aef8  call    cs:__imp_SRCacheContext_Close
0x18000aefe  xor     eax, eax
0x18000af00  mov     rcx, [rbp+190h+var_30]
0x18000af07  xor     rcx, rsp; StackCookie
0x18000af0a  call    __security_check_cookie
0x18000af0f  mov     rbx, [rsp+290h+arg_18]
0x18000af17  add     rsp, 270h
0x18000af1e  pop     r15
0x18000af20  pop     r14
0x18000af22  pop     rdi
0x18000af23  pop     rsi
0x18000af24  pop     rbp
0x18000af25  retn
0x18000af26  mov     rcx, [rbp+198h]; this
0x18000af2d  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000af34  mov     r9d, ebx; char *
0x18000af37  mov     edx, 1A6h; void *
0x18000af3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af41  mov     rcx, [rbp+198h]; this
0x18000af48  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000af4f  mov     r9d, ebx; char *
0x18000af52  mov     edx, 2C4h; void *
0x18000af57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af5c  mov     rcx, [rsp+290h+var_250]
0x18000af61  mov     [rsp+290h+var_250], r15
0x18000af66  test    rcx, rcx
0x18000af69  jz      short loc_18000AF71
0x18000af6b  call    cs:__imp_SRCache_Free
0x18000af71  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000af76  mov     qword ptr [rsp+290h+var_270], r15
0x18000af7b  test    rcx, rcx
0x18000af7e  jz      short loc_18000AF86
0x18000af80  call    cs:__imp_SRCacheContext_Close
0x18000af86  mov     eax, ebx
0x18000af88  jmp     loc_18000AF00
0x18000af8d  call    cs:__imp_SRCache_Free
0x18000af93  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000af98  mov     qword ptr [rsp+290h+var_270], r15
0x18000af9d  test    rcx, rcx
0x18000afa0  jz      short loc_18000AFA8
0x18000afa2  call    cs:__imp_SRCacheContext_Close
0x18000afa8  mov     eax, edi
0x18000afaa  jmp     loc_18000AF00
0x18000afaf  mov     rcx, [rbp+198h]; this
0x18000afb6  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000afbd  mov     r9d, edi; char *
0x18000afc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000afc5  mov     rcx, [rsp+290h+var_250]
0x18000afca  mov     [rsp+290h+var_250], r15
0x18000afcf  test    rcx, rcx
0x18000afd2  jz      short loc_18000AF93
0x18000afd4  jmp     short loc_18000AF8D
0x18000afd6  mov     rcx, [rbp+198h]; this
0x18000afdd  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000afe4  mov     r9d, edi; char *
0x18000afe7  mov     edx, 18Ch; void *
0x18000afec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aff1  mov     rcx, [rbp+198h]; this
0x18000aff8  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000afff  mov     r9d, edi; char *
0x18000b002  mov     edx, 2B7h; void *
0x18000b007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b00c  jmp     short loc_18000AF93
0x18000b00e  mov     rcx, [rbp+198h]; this
0x18000b015  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b01c  mov     ebx, 80670012h
0x18000b021  mov     edx, 2B8h; void *
0x18000b026  mov     r9d, ebx; char *
0x18000b029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b02e  jmp     loc_18000AF71
0x18000b033  mov     edx, 2BBh; void *
0x18000b038  jmp     loc_18000AFAF
0x18000b03d  mov     rcx, [rbp+198h]; this
0x18000b044  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b04b  mov     r9d, edi; char *
0x18000b04e  mov     edx, 1B0h; void *
0x18000b053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b058  mov     edx, 2BEh
0x18000b05d  jmp     loc_18000AFAF
0x18000b062  mov     [rbx+10h], rsi
0x18000b066  jmp     loc_18000AEBC
```
