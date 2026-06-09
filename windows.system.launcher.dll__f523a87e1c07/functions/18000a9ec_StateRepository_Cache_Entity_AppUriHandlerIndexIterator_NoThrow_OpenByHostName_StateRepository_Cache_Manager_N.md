# StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::OpenByHostName(StateRepository::Cache::Manager_NoThrow &,ushort const *)

- ea: `0x18000a9ec`
- end: `0x18000ad03`
- name: `?OpenByHostName@AppUriHandlerIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z`
- size: `791`
- prototype: `int(StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009ad8`
- `0x18000ad0c`

## callees

- `0x18000a9ec`
- `0x1800103b0`
- `0x180010c04`
- `0x18008a030`
- `0x18008a9d8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ab7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000abe2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ac01`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ab7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000abe2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ac01`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aa2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aa8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ab3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ab90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000abf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ac16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aa2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000aa8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ab3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ab90`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000abf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ac16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000ab19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000ab19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000aa68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000aa68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000ab60`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000ab60`

## string_xrefs

- `0x18000abbf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x18000ac4b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x18000ac8d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x18000acad`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x18000aa4a`: `AppUriHandler\Index\HostName`
- `0x18000ab59`: `AppUriHandler\Index\HostName`
- `0x18000aba4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000ac72`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000acdc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow::OpenByHostName(
        StateRepository::Cache::Entity::AppUriHandlerIndexIterator_NoThrow *this,
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
  v8 = SRCacheContext_Open(v7, L"AppUriHandler\\Index\\HostName", 0, &v23);
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
      (void *)0x2C7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
        (void *)0x2C8,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
      v20 = 715;
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
        v11 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"AppUriHandler\\Index\\HostName");
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
          (void *)0x2D4,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
      v20 = 718;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
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
0x18000a9ec  mov     [rsp-8+arg_18], rbx
0x18000a9f1  push    rbp
0x18000a9f2  push    rsi
0x18000a9f3  push    rdi
0x18000a9f4  push    r14
0x18000a9f6  push    r15
0x18000a9f8  lea     rbp, [rsp-170h]
0x18000aa00  sub     rsp, 270h
0x18000aa07  mov     rax, cs:__security_cookie
0x18000aa0e  xor     rax, rsp
0x18000aa11  mov     [rbp+190h+var_30], rax
0x18000aa18  mov     rbx, rcx
0x18000aa1b  xor     r15d, r15d
0x18000aa1e  mov     rcx, [rcx]
0x18000aa21  mov     r14, r8
0x18000aa24  mov     rsi, rdx
0x18000aa27  mov     [rbx], r15
0x18000aa2a  test    rcx, rcx
0x18000aa2d  jz      short loc_18000AA35
0x18000aa2f  call    cs:__imp_SRCacheContext_Close
0x18000aa35  mov     [rbx+8], r15d
0x18000aa39  lea     rax, [rsp+290h+var_270]
0x18000aa3e  mov     [rbx+10h], r15
0x18000aa42  lea     r9, [rsp+290h+var_260]
0x18000aa47  mov     rcx, [rsi]
0x18000aa4a  lea     rdx, aAppurihandlerI_2; "AppUriHandler\\Index\\HostName"
0x18000aa51  xor     r8d, r8d
0x18000aa54  mov     [rsp+290h+var_268], rax
0x18000aa59  mov     qword ptr [rsp+290h+var_270], r15; int
0x18000aa5e  mov     [rsp+290h+var_260], r15
0x18000aa63  mov     [rsp+290h+var_258], 1
0x18000aa68  call    cs:__imp_SRCacheContext_Open
0x18000aa6e  mov     edi, eax
0x18000aa70  cmp     [rsp+290h+var_258], r15b
0x18000aa75  jz      short loc_18000AA92
0x18000aa77  mov     r8, [rsp+290h+var_268]
0x18000aa7c  mov     rdx, [rsp+290h+var_260]
0x18000aa81  mov     rcx, [r8]
0x18000aa84  mov     [r8], rdx
0x18000aa87  test    rcx, rcx
0x18000aa8a  jz      short loc_18000AA92
0x18000aa8c  call    cs:__imp_SRCacheContext_Close
0x18000aa92  test    edi, edi
0x18000aa94  js      loc_18000AC6B
0x18000aa9a  cmp     qword ptr [rsp+290h+var_270], r15
0x18000aa9f  setnz   al
0x18000aaa2  test    al, al
0x18000aaa4  jz      loc_18000ACA6
0x18000aaaa  xor     edx, edx; Val
0x18000aaac  mov     [rsp+290h+var_250], r15
0x18000aab1  mov     r8d, 200h; Size
0x18000aab7  lea     rcx, [rsp+290h+var_248]; void *
0x18000aabc  call    memset_0
0x18000aac1  lea     rax, [rsp+290h+var_248]
0x18000aac6  mov     [rbp+190h+var_48], r15
0x18000aacd  mov     rdx, r14; unsigned __int16 *
0x18000aad0  mov     [rbp+190h+var_38], rax
0x18000aad7  lea     rcx, [rsp+290h+var_250]; this
0x18000aadc  mov     [rbp+190h+var_40], 100h
0x18000aae7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000aaec  mov     edi, eax
0x18000aaee  test    eax, eax
0x18000aaf0  js      loc_18000ACCB
0x18000aaf6  mov     rdx, [rbp+190h+var_38]
0x18000aafd  lea     r9, [rsp+290h+var_260]
0x18000ab02  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000ab07  xor     r8d, r8d
0x18000ab0a  mov     [rsp+290h+var_268], rbx
0x18000ab0f  mov     [rsp+290h+var_260], r15
0x18000ab14  mov     [rsp+290h+var_258], 1
0x18000ab19  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000ab1f  mov     edi, eax
0x18000ab21  cmp     [rsp+290h+var_258], r15b
0x18000ab26  jz      short loc_18000AB43
0x18000ab28  mov     r8, [rsp+290h+var_268]
0x18000ab2d  mov     rdx, [rsp+290h+var_260]
0x18000ab32  mov     rcx, [r8]
0x18000ab35  mov     [r8], rdx
0x18000ab38  test    rcx, rcx
0x18000ab3b  jz      short loc_18000AB43
0x18000ab3d  call    cs:__imp_SRCacheContext_Close
0x18000ab43  test    edi, edi
0x18000ab45  js      loc_18000ACD5
0x18000ab4b  cmp     [rbx], r15
0x18000ab4e  jnz     loc_18000ACFA
0x18000ab54  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000ab59  lea     rdx, aAppurihandlerI_2; "AppUriHandler\\Index\\HostName"
0x18000ab60  call    cs:__imp_SRCacheContext_AddToCache
0x18000ab66  mov     ebx, eax
0x18000ab68  test    eax, eax
0x18000ab6a  js      short loc_18000AB9D
0x18000ab6c  mov     rcx, [rsp+290h+var_250]
0x18000ab71  mov     [rsp+290h+var_250], r15
0x18000ab76  test    rcx, rcx
0x18000ab79  jz      short loc_18000AB81
0x18000ab7b  call    cs:__imp_SRCache_Free
0x18000ab81  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000ab86  mov     qword ptr [rsp+290h+var_270], r15
0x18000ab8b  test    rcx, rcx
0x18000ab8e  jz      short loc_18000AB96
0x18000ab90  call    cs:__imp_SRCacheContext_Close
0x18000ab96  xor     eax, eax
0x18000ab98  jmp     loc_18000AC1E
0x18000ab9d  mov     rcx, [rbp+198h]; this
0x18000aba4  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000abab  mov     r9d, ebx; char *
0x18000abae  mov     edx, 1A6h; void *
0x18000abb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abb8  mov     rcx, [rbp+198h]; this
0x18000abbf  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000abc6  mov     r9d, ebx; char *
0x18000abc9  mov     edx, 2D4h; void *
0x18000abce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abd3  mov     rcx, [rsp+290h+var_250]
0x18000abd8  mov     [rsp+290h+var_250], r15
0x18000abdd  test    rcx, rcx
0x18000abe0  jz      short loc_18000ABE8
0x18000abe2  call    cs:__imp_SRCache_Free
0x18000abe8  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000abed  mov     qword ptr [rsp+290h+var_270], r15
0x18000abf2  test    rcx, rcx
0x18000abf5  jz      short loc_18000ABFD
0x18000abf7  call    cs:__imp_SRCacheContext_Close
0x18000abfd  mov     eax, ebx
0x18000abff  jmp     short loc_18000AC1E
0x18000ac01  call    cs:__imp_SRCache_Free
0x18000ac07  mov     rcx, qword ptr [rsp+290h+var_270]
0x18000ac0c  mov     qword ptr [rsp+290h+var_270], r15
0x18000ac11  test    rcx, rcx
0x18000ac14  jz      short loc_18000AC1C
0x18000ac16  call    cs:__imp_SRCacheContext_Close
0x18000ac1c  mov     eax, edi
0x18000ac1e  mov     rcx, [rbp+190h+var_30]
0x18000ac25  xor     rcx, rsp; StackCookie
0x18000ac28  call    __security_check_cookie
0x18000ac2d  mov     rbx, [rsp+290h+arg_18]
0x18000ac35  add     rsp, 270h
0x18000ac3c  pop     r15
0x18000ac3e  pop     r14
0x18000ac40  pop     rdi
0x18000ac41  pop     rsi
0x18000ac42  pop     rbp
0x18000ac43  retn
0x18000ac44  mov     rcx, [rbp+198h]; this
0x18000ac4b  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ac52  mov     r9d, edi; char *
0x18000ac55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac5a  mov     rcx, [rsp+290h+var_250]
0x18000ac5f  mov     [rsp+290h+var_250], r15
0x18000ac64  test    rcx, rcx
0x18000ac67  jz      short loc_18000AC07
0x18000ac69  jmp     short loc_18000AC01
0x18000ac6b  mov     rcx, [rbp+198h]; this
0x18000ac72  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ac79  mov     r9d, edi; char *
0x18000ac7c  mov     edx, 18Ch; void *
0x18000ac81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac86  mov     rcx, [rbp+198h]; this
0x18000ac8d  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ac94  mov     r9d, edi; char *
0x18000ac97  mov     edx, 2C7h; void *
0x18000ac9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aca1  jmp     loc_18000AC07
0x18000aca6  mov     rcx, [rbp+198h]; this
0x18000acad  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000acb4  mov     ebx, 80670012h
0x18000acb9  mov     edx, 2C8h; void *
0x18000acbe  mov     r9d, ebx; char *
0x18000acc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000acc6  jmp     loc_18000ABE8
0x18000accb  mov     edx, 2CBh; void *
0x18000acd0  jmp     loc_18000AC44
0x18000acd5  mov     rcx, [rbp+198h]; this
0x18000acdc  lea     r8, aOnecorePrivate_19; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ace3  mov     r9d, edi; char *
0x18000ace6  mov     edx, 1B0h; void *
0x18000aceb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000acf0  mov     edx, 2CEh
0x18000acf5  jmp     loc_18000AC44
0x18000acfa  mov     [rbx+10h], rsi
0x18000acfe  jmp     loc_18000AB54
```
