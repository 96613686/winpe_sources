# StateRepository::Cache::Entity::Application_NoThrow::GetByPackageAndPackageRelativeApplicationId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)

- ea: `0x18000e8b0`
- end: `0x18000ecc5`
- name: `?GetByPackageAndPackageRelativeApplicationId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z`
- size: `1045`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18009979c`

## callees

- `0x18000ceb0`
- `0x18000e8b0`
- `0x18000eccc`
- `0x18000f4d0`
- `0x1800210f8`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000e9af`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000e9af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000e924`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000e924`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000eb85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000eb85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000eb1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000eb43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000eb1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000eb43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000ea66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000ea66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000eab7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000eab7`

## string_xrefs

- `0x18000ec82`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000eca7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000eaf0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000ebcf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000ebe7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000ec5b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000ead0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000eba2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000ec16`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000ec3b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::GetByPackageAndPackageRelativeApplicationId(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  __int64 v7; // rcx
  unsigned int v8; // ebx
  bool v9; // r8
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+238h] [rbp+138h]
  __int64 v26; // [rsp+240h] [rbp+140h]
  _BYTE *v27; // [rsp+248h] [rbp+148h]
  unsigned __int16 v28[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v29; // [rsp+258h] [rbp+158h] BYREF
  char v30; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v21[0]);
    return v8;
  }
  v7 = *(_QWORD *)a1;
  *(_QWORD *)v28 = &v22;
  v22 = 0;
  v29 = 0;
  v30 = 1;
  v8 = SRCacheContext_Open(v7, L"Application\\Index\\PackageAndPackageRelativeApplicationId", 0, &v29);
  if ( v30 )
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(*(_QWORD *)v28, v29);
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v8,
      v21[0]);
    v20 = 363;
  }
  else
  {
    if ( v22 )
    {
      v23 = 0;
      memset_0(v24, 0, sizeof(v24));
      v25 = 0;
      v26 = 256;
      v27 = v24;
      if ( (unsigned int)_o__ui64tow_s(a2, v28, 17) )
      {
        v8 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x166,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8000FFFFLL,
          v21[0]);
      }
      else
      {
        v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
        if ( (v8 & 0x80000000) == 0 )
        {
          v10 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(
                  (StateRepository::Cache::Key_NoThrow *)&v23,
                  v25 + 2,
                  v9);
          v8 = v10;
          if ( v10 >= 0 )
          {
            *(_DWORD *)&v27[2 * v25++] = 94;
            v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a3);
            v8 = v11;
            if ( v11 >= 0 )
            {
              *(_QWORD *)v28 = v21;
              *(_QWORD *)v21 = 0;
              v29 = 0;
              v30 = 1;
              v8 = SRCacheContext_OpenSubContext(v22, v27, 0, &v29);
              if ( v30 )
                wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(
                  *(_QWORD *)v28,
                  v29);
              if ( (v8 & 0x80000000) != 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1B0,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                  (const char *)v8,
                  v21[0]);
                v13 = 373;
              }
              else if ( *(_QWORD *)v21 && (v17 = SRCacheContext_EnumerateData(*(_QWORD *)v21, 0, a4), v8 = v17, v17 < 0) )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2A6,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                  (const char *)(unsigned int)v17,
                  v21[0]);
                v13 = 376;
              }
              else
              {
                v12 = SRCacheContext_AddToCache(v22, L"Application\\Index\\PackageAndPackageRelativeApplicationId");
                v8 = v12;
                if ( v12 >= 0 )
                {
                  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v21, 0);
                  v15 = v23;
                  v23 = 0;
                  if ( v15 )
                    SRCache_Free();
                  v8 = 0;
                  goto LABEL_22;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1A6,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                  (const char *)(unsigned int)v12,
                  v21[0]);
                v13 = 379;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v13,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
                (const char *)v8,
                v21[0]);
              wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v21, 0);
              goto LABEL_17;
            }
            v18 = (unsigned int)v11;
            v19 = 369;
LABEL_27:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v19,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
              (const char *)v18,
              v21[0]);
LABEL_17:
            v14 = v23;
            v23 = 0;
            if ( v14 )
              SRCache_Free();
            goto LABEL_22;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16D,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
            (const char *)(unsigned int)v10,
            v21[0]);
          v19 = 368;
LABEL_30:
          v18 = v8;
          goto LABEL_27;
        }
      }
      v19 = 367;
      goto LABEL_30;
    }
    v8 = -2140733422;
    v20 = 364;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
    (const char *)v8,
    v21[0]);
LABEL_22:
  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v22, 0);
  return v8;
}

```

## disassembly

```asm
0x18000e8b0  push    rbp
0x18000e8b2  push    rbx
0x18000e8b3  push    rsi
0x18000e8b4  push    rdi
0x18000e8b5  push    r14
0x18000e8b7  push    r15
0x18000e8b9  lea     rbp, [rsp-188h]
0x18000e8c1  sub     rsp, 288h
0x18000e8c8  mov     rax, cs:__security_cookie
0x18000e8cf  xor     rax, rsp
0x18000e8d2  mov     [rbp+1B0h+var_38], rax
0x18000e8d9  xor     r15d, r15d
0x18000e8dc  mov     rsi, r9
0x18000e8df  mov     [r9], r15
0x18000e8e2  mov     r14, r8
0x18000e8e5  mov     rdi, rdx
0x18000e8e8  test    rdx, rdx
0x18000e8eb  jz      loc_18000EBE0
0x18000e8f1  mov     rcx, [rcx]
0x18000e8f4  lea     rax, [rsp+2B0h+var_288]
0x18000e8f9  lea     r9, [rbp+1B0h+var_58]
0x18000e900  mov     qword ptr [rbp+1B0h+var_60], rax
0x18000e907  xor     r8d, r8d
0x18000e90a  mov     [rsp+2B0h+var_288], r15
0x18000e90f  lea     rdx, aApplicationInd; "Application\\Index\\PackageAndPackageRe"...
0x18000e916  mov     [rbp+1B0h+var_58], r15
0x18000e91d  mov     [rbp+1B0h+var_50], 1
0x18000e924  call    cs:__imp_SRCacheContext_Open
0x18000e92b  nop     dword ptr [rax+rax+00h]
0x18000e930  mov     ebx, eax
0x18000e932  cmp     [rbp+1B0h+var_50], r15b
0x18000e939  jz      short loc_18000E94E
0x18000e93b  mov     rdx, [rbp+1B0h+var_58]
0x18000e942  mov     rcx, qword ptr [rbp+1B0h+var_60]
0x18000e949  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e94e  test    ebx, ebx
0x18000e950  js      loc_18000EC34
0x18000e956  cmp     [rsp+2B0h+var_288], r15
0x18000e95b  setnz   al
0x18000e95e  test    al, al
0x18000e960  jz      loc_18000EC6F
0x18000e966  xor     edx, edx; Val
0x18000e968  mov     [rsp+2B0h+var_280], r15
0x18000e96d  mov     r8d, 200h; Size
0x18000e973  lea     rcx, [rsp+2B0h+var_278]; void *
0x18000e978  call    memset_0
0x18000e97d  mov     r9d, 10h
0x18000e983  mov     [rbp+1B0h+var_78], r15
0x18000e98a  lea     rax, [rsp+2B0h+var_278]
0x18000e98f  mov     [rbp+1B0h+var_70], 100h
0x18000e99a  lea     rdx, [rbp+1B0h+var_60]
0x18000e9a1  mov     [rbp+1B0h+var_68], rax
0x18000e9a8  mov     rcx, rdi
0x18000e9ab  lea     r8d, [r9+1]
0x18000e9af  call    cs:__imp__o__ui64tow_s
0x18000e9b6  nop     dword ptr [rax+rax+00h]
0x18000e9bb  test    eax, eax
0x18000e9bd  jnz     loc_18000EC7B
0x18000e9c3  lea     rdx, [rbp+1B0h+var_60]; unsigned __int16 *
0x18000e9ca  lea     rcx, [rsp+2B0h+var_280]; this
0x18000e9cf  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000e9d4  mov     ebx, eax
0x18000e9d6  test    eax, eax
0x18000e9d8  js      loc_18000EC05
0x18000e9de  mov     rdx, [rbp+1B0h+var_78]
0x18000e9e5  lea     rcx, [rsp+2B0h+var_280]; this
0x18000e9ea  add     rdx, 2; unsigned __int64
0x18000e9ee  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x18000e9f3  mov     ebx, eax
0x18000e9f5  test    eax, eax
0x18000e9f7  js      loc_18000ECA0
0x18000e9fd  mov     r8, [rbp+1B0h+var_78]
0x18000ea04  mov     rdx, r14; unsigned __int16 *
0x18000ea07  mov     rcx, [rbp+1B0h+var_68]
0x18000ea0e  mov     dword ptr [rcx+r8*2], 5Eh ; '^'
0x18000ea16  lea     rcx, [rsp+2B0h+var_280]; this
0x18000ea1b  inc     [rbp+1B0h+var_78]
0x18000ea22  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000ea27  mov     ebx, eax
0x18000ea29  test    eax, eax
0x18000ea2b  js      loc_18000EBC0
0x18000ea31  mov     rdx, [rbp+1B0h+var_68]
0x18000ea38  lea     rax, [rsp+2B0h+var_290]
0x18000ea3d  mov     rcx, [rsp+2B0h+var_288]
0x18000ea42  lea     r9, [rbp+1B0h+var_58]
0x18000ea49  xor     r8d, r8d
0x18000ea4c  mov     qword ptr [rbp+1B0h+var_60], rax
0x18000ea53  mov     qword ptr [rsp+2B0h+var_290], r15; int
0x18000ea58  mov     [rbp+1B0h+var_58], r15
0x18000ea5f  mov     [rbp+1B0h+var_50], 1
0x18000ea66  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000ea6d  nop     dword ptr [rax+rax+00h]
0x18000ea72  mov     ebx, eax
0x18000ea74  cmp     [rbp+1B0h+var_50], r15b
0x18000ea7b  jz      short loc_18000EA90
0x18000ea7d  mov     rdx, [rbp+1B0h+var_58]
0x18000ea84  mov     rcx, qword ptr [rbp+1B0h+var_60]
0x18000ea8b  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000ea90  test    ebx, ebx
0x18000ea92  js      loc_18000EC0F
0x18000ea98  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x18000ea9d  test    rcx, rcx
0x18000eaa0  setnz   al
0x18000eaa3  test    al, al
0x18000eaa5  jnz     loc_18000EB80
0x18000eaab  mov     rcx, [rsp+2B0h+var_288]
0x18000eab0  lea     rdx, aApplicationInd; "Application\\Index\\PackageAndPackageRe"...
0x18000eab7  call    cs:__imp_SRCacheContext_AddToCache
0x18000eabe  nop     dword ptr [rax+rax+00h]
0x18000eac3  mov     ebx, eax
0x18000eac5  test    eax, eax
0x18000eac7  jns     short loc_18000EB28
0x18000eac9  mov     rcx, [rbp+1B8h]; this
0x18000ead0  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ead7  mov     r9d, eax; char *
0x18000eada  mov     edx, 1A6h; void *
0x18000eadf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eae4  mov     edx, 17Bh; void *
0x18000eae9  mov     rcx, [rbp+1B8h]; this
0x18000eaf0  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000eaf7  mov     r9d, ebx; char *
0x18000eafa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eaff  xor     edx, edx
0x18000eb01  lea     rcx, [rsp+2B0h+var_290]
0x18000eb06  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000eb0b  mov     rcx, [rsp+2B0h+var_280]
0x18000eb10  mov     [rsp+2B0h+var_280], r15
0x18000eb15  test    rcx, rcx
0x18000eb18  jz      short loc_18000EB52
0x18000eb1a  call    cs:__imp_SRCache_Free
0x18000eb21  nop     dword ptr [rax+rax+00h]
0x18000eb26  jmp     short loc_18000EB52
0x18000eb28  xor     edx, edx
0x18000eb2a  lea     rcx, [rsp+2B0h+var_290]
0x18000eb2f  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000eb34  mov     rcx, [rsp+2B0h+var_280]
0x18000eb39  mov     [rsp+2B0h+var_280], r15
0x18000eb3e  test    rcx, rcx
0x18000eb41  jz      short loc_18000EB4F
0x18000eb43  call    cs:__imp_SRCache_Free
0x18000eb4a  nop     dword ptr [rax+rax+00h]
0x18000eb4f  mov     ebx, r15d
0x18000eb52  xor     edx, edx
0x18000eb54  lea     rcx, [rsp+2B0h+var_288]
0x18000eb59  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000eb5e  mov     eax, ebx
0x18000eb60  mov     rcx, [rbp+1B0h+var_38]
0x18000eb67  xor     rcx, rsp; StackCookie
0x18000eb6a  call    __security_check_cookie
0x18000eb6f  add     rsp, 288h
0x18000eb76  pop     r15
0x18000eb78  pop     r14
0x18000eb7a  pop     rdi
0x18000eb7b  pop     rsi
0x18000eb7c  pop     rbx
0x18000eb7d  pop     rbp
0x18000eb7e  retn
0x18000eb80  mov     r8, rsi
0x18000eb83  xor     edx, edx
0x18000eb85  call    cs:__imp_SRCacheContext_EnumerateData
0x18000eb8c  nop     dword ptr [rax+rax+00h]
0x18000eb91  mov     ebx, eax
0x18000eb93  test    eax, eax
0x18000eb95  jns     loc_18000EAAB
0x18000eb9b  mov     rcx, [rbp+1B8h]; this
0x18000eba2  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000eba9  mov     r9d, eax; char *
0x18000ebac  mov     edx, 2A6h; void *
0x18000ebb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebb6  mov     edx, 178h
0x18000ebbb  jmp     loc_18000EAE9
0x18000ebc0  mov     r9d, eax; char *
0x18000ebc3  mov     edx, 171h; void *
0x18000ebc8  mov     rcx, [rbp+1B8h]; this
0x18000ebcf  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ebd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ebdb  jmp     loc_18000EB0B
0x18000ebe0  mov     rcx, [rbp+1B8h]; this
0x18000ebe7  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ebee  mov     ebx, 80070057h
0x18000ebf3  mov     edx, 167h; void *
0x18000ebf8  mov     r9d, ebx; char *
0x18000ebfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec00  jmp     loc_18000EB5E
0x18000ec05  mov     edx, 16Fh
0x18000ec0a  mov     r9d, ebx
0x18000ec0d  jmp     short loc_18000EBC8
0x18000ec0f  mov     rcx, [rbp+1B8h]; this
0x18000ec16  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ec1d  mov     r9d, ebx; char *
0x18000ec20  mov     edx, 1B0h; void *
0x18000ec25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec2a  mov     edx, 175h
0x18000ec2f  jmp     loc_18000EAE9
0x18000ec34  mov     rcx, [rbp+1B8h]; this
0x18000ec3b  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ec42  mov     r9d, ebx; char *
0x18000ec45  mov     edx, 18Ch; void *
0x18000ec4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec4f  mov     edx, 16Bh; void *
0x18000ec54  mov     rcx, [rbp+1B8h]; this
0x18000ec5b  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ec62  mov     r9d, ebx; char *
0x18000ec65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec6a  jmp     loc_18000EB52
0x18000ec6f  mov     ebx, 80670012h
0x18000ec74  mov     edx, 16Ch
0x18000ec79  jmp     short loc_18000EC54
0x18000ec7b  mov     rcx, [rbp+1B8h]; this
0x18000ec82  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ec89  mov     ebx, 8000FFFFh
0x18000ec8e  mov     edx, 166h; void *
0x18000ec93  mov     r9d, ebx; char *
0x18000ec96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec9b  jmp     loc_18000EC05
0x18000eca0  mov     rcx, [rbp+1B8h]; this
0x18000eca7  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ecae  mov     r9d, ebx; char *
0x18000ecb1  mov     edx, 16Dh; void *
0x18000ecb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ecbb  mov     edx, 170h
0x18000ecc0  jmp     loc_18000EC0A
```
