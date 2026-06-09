# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x18000e148`
- end: `0x18000e5b9`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `1137`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000dae4`

## callees

- `0x18000ceb0`
- `0x18000e148`
- `0x18000eccc`
- `0x18000f4d0`
- `0x1800210f8`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000e250`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000e2cf`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000e250`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000e2cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000e1c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000e1c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e410`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e439`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e410`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000e439`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000e333`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000e333`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18000e37e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18000e37e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000e3ad`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000e3ad`

## string_xrefs

- `0x18000e537`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000e55e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000e59e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000e3e6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18000e482`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18000e510`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18000e583`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18000e3c6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e49f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e4cb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000e4f0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        bool *a4)
{
  __int64 v7; // rcx
  int v8; // ebx
  bool v9; // r8
  int v10; // eax
  int IsEmpty; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+248h] [rbp+148h]
  __int64 v26; // [rsp+250h] [rbp+150h]
  _BYTE *v27; // [rsp+258h] [rbp+158h]
  unsigned __int16 v28[4]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v29; // [rsp+268h] [rbp+168h] BYREF
  char v30; // [rsp+270h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a4 = 0;
  if ( !a2 )
  {
    v17 = 153;
LABEL_29:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v20[0]);
    return (unsigned int)v8;
  }
  if ( !a3 )
  {
    v17 = 154;
    goto LABEL_29;
  }
  v7 = *(_QWORD *)a1;
  *(_QWORD *)v28 = v22;
  v22[0] = 0;
  v29 = 0;
  v30 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageUser\\Index\\UserAndPackage", 0, &v29);
  if ( v30 )
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(*(_QWORD *)v28, v29);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v18 = 158;
  }
  else
  {
    if ( v22[0] )
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
          v20[0]);
      }
      else
      {
        v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
        if ( v8 >= 0 )
        {
          v10 = StateRepository::Cache::Key_NoThrow::EnsureCapacity(
                  (StateRepository::Cache::Key_NoThrow *)&v23,
                  v25 + 2,
                  v9);
          v8 = v10;
          if ( v10 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x16D,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
              (const char *)(unsigned int)v10,
              v20[0]);
            v19 = 163;
          }
          else
          {
            *(_DWORD *)&v27[2 * v25++] = 94;
            if ( (unsigned int)_o__ui64tow_s(a3, v28, 17) )
            {
              v8 = -2147418113;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x166,
                (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
                (const char *)0x8000FFFFLL,
                v20[0]);
            }
            else
            {
              v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, v28);
              if ( v8 >= 0 )
              {
                *(_QWORD *)v28 = v20;
                *(_QWORD *)v20 = 0;
                v29 = 0;
                v30 = 1;
                v8 = SRCacheContext_OpenSubContext(v22[0], v27, 0, &v29);
                if ( v30 )
                  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(
                    *(_QWORD *)v28,
                    v29);
                if ( v8 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1B0,
                    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                    (const char *)(unsigned int)v8,
                    v20[0]);
                  v13 = 168;
                }
                else
                {
                  if ( !*(_QWORD *)v20 )
                  {
LABEL_18:
                    v12 = SRCacheContext_AddToCache(v22[0], L"PackageUser\\Index\\UserAndPackage");
                    v8 = v12;
                    if ( v12 >= 0 )
                    {
                      wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v20, 0);
                      v15 = v23;
                      v23 = 0;
                      if ( v15 )
                        SRCache_Free();
                      v8 = 0;
                      goto LABEL_26;
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1A6,
                      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                      (const char *)(unsigned int)v12,
                      v20[0]);
                    v13 = 176;
                    goto LABEL_20;
                  }
                  v21 = 0;
                  IsEmpty = SRCacheContext_IsEmpty(*(_QWORD *)v20, &v21);
                  v8 = IsEmpty;
                  if ( IsEmpty >= 0 )
                  {
                    *a4 = v21 == 0;
                    goto LABEL_18;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2B8,
                    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
                    (const char *)(unsigned int)IsEmpty,
                    v20[0]);
                  v13 = 172;
                }
LABEL_20:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
                  (const char *)(unsigned int)v8,
                  v20[0]);
                wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v20, 0);
                goto LABEL_21;
              }
            }
            v19 = 164;
          }
LABEL_40:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
            (const char *)(unsigned int)v8,
            v20[0]);
LABEL_21:
          v14 = v23;
          v23 = 0;
          if ( v14 )
            SRCache_Free();
          goto LABEL_26;
        }
      }
      v19 = 162;
      goto LABEL_40;
    }
    v8 = -2140733422;
    v18 = 159;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
    (const char *)(unsigned int)v8,
    v20[0]);
LABEL_26:
  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(v22, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000e148  push    rbp
0x18000e14a  push    rbx
0x18000e14b  push    rsi
0x18000e14c  push    rdi
0x18000e14d  push    r14
0x18000e14f  push    r15
0x18000e151  lea     rbp, [rsp-198h]
0x18000e159  sub     rsp, 298h
0x18000e160  mov     rax, cs:__security_cookie
0x18000e167  xor     rax, rsp
0x18000e16a  mov     [rbp+1C0h+var_38], rax
0x18000e171  xor     r15d, r15d
0x18000e174  mov     r14, r9
0x18000e177  mov     [r9], r15b
0x18000e17a  mov     rdi, r8
0x18000e17d  mov     rsi, rdx
0x18000e180  test    rdx, rdx
0x18000e183  jz      loc_18000E476
0x18000e189  test    r8, r8
0x18000e18c  jz      loc_18000E4BD
0x18000e192  mov     rcx, [rcx]
0x18000e195  lea     rax, [rsp+2C0h+var_290]
0x18000e19a  lea     r9, [rbp+1C0h+var_58]
0x18000e1a1  mov     qword ptr [rbp+1C0h+var_60], rax
0x18000e1a8  xor     r8d, r8d
0x18000e1ab  mov     [rsp+2C0h+var_290], r15
0x18000e1b0  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18000e1b7  mov     [rbp+1C0h+var_58], r15
0x18000e1be  mov     [rbp+1C0h+var_50], 1
0x18000e1c5  call    cs:__imp_SRCacheContext_Open
0x18000e1cc  nop     dword ptr [rax+rax+00h]
0x18000e1d1  mov     ebx, eax
0x18000e1d3  cmp     [rbp+1C0h+var_50], r15b
0x18000e1da  jz      short loc_18000E1EF
0x18000e1dc  mov     rdx, [rbp+1C0h+var_58]
0x18000e1e3  mov     rcx, qword ptr [rbp+1C0h+var_60]
0x18000e1ea  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e1ef  test    ebx, ebx
0x18000e1f1  js      loc_18000E4E9
0x18000e1f7  cmp     [rsp+2C0h+var_290], r15
0x18000e1fc  setnz   al
0x18000e1ff  test    al, al
0x18000e201  jz      loc_18000E524
0x18000e207  xor     edx, edx; Val
0x18000e209  mov     [rsp+2C0h+var_280], r15
0x18000e20e  mov     r8d, 200h; Size
0x18000e214  lea     rcx, [rsp+2C0h+var_278]; void *
0x18000e219  call    memset_0
0x18000e21e  mov     r9d, 10h
0x18000e224  mov     [rbp+1C0h+var_78], r15
0x18000e22b  lea     rax, [rsp+2C0h+var_278]
0x18000e230  mov     [rbp+1C0h+var_70], 100h
0x18000e23b  lea     rdx, [rbp+1C0h+var_60]
0x18000e242  mov     [rbp+1C0h+var_68], rax
0x18000e249  mov     rcx, rsi
0x18000e24c  lea     r8d, [r9+1]
0x18000e250  call    cs:__imp__o__ui64tow_s
0x18000e257  nop     dword ptr [rax+rax+00h]
0x18000e25c  test    eax, eax
0x18000e25e  jnz     loc_18000E530
0x18000e264  lea     rdx, [rbp+1C0h+var_60]; unsigned __int16 *
0x18000e26b  lea     rcx, [rsp+2C0h+var_280]; this
0x18000e270  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000e275  mov     ebx, eax
0x18000e277  test    eax, eax
0x18000e279  js      loc_18000E550
0x18000e27f  mov     rdx, [rbp+1C0h+var_78]
0x18000e286  lea     rcx, [rsp+2C0h+var_280]; this
0x18000e28b  add     rdx, 2; unsigned __int64
0x18000e28f  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x18000e294  mov     ebx, eax
0x18000e296  test    eax, eax
0x18000e298  js      loc_18000E597
0x18000e29e  mov     r10, [rbp+1C0h+var_78]
0x18000e2a5  mov     r9d, 10h
0x18000e2ab  mov     rdx, [rbp+1C0h+var_68]
0x18000e2b2  mov     rcx, rdi
0x18000e2b5  lea     r8d, [r9+1]
0x18000e2b9  mov     dword ptr [rdx+r10*2], 5Eh ; '^'
0x18000e2c1  lea     rdx, [rbp+1C0h+var_60]
0x18000e2c8  inc     [rbp+1C0h+var_78]
0x18000e2cf  call    cs:__imp__o__ui64tow_s
0x18000e2d6  nop     dword ptr [rax+rax+00h]
0x18000e2db  test    eax, eax
0x18000e2dd  jnz     loc_18000E557
0x18000e2e3  lea     rdx, [rbp+1C0h+var_60]; unsigned __int16 *
0x18000e2ea  lea     rcx, [rsp+2C0h+var_280]; this
0x18000e2ef  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000e2f4  mov     ebx, eax
0x18000e2f6  test    eax, eax
0x18000e2f8  js      loc_18000E577
0x18000e2fe  mov     rdx, [rbp+1C0h+var_68]
0x18000e305  lea     rax, [rsp+2C0h+var_2A0]
0x18000e30a  mov     rcx, [rsp+2C0h+var_290]
0x18000e30f  lea     r9, [rbp+1C0h+var_58]
0x18000e316  xor     r8d, r8d
0x18000e319  mov     qword ptr [rbp+1C0h+var_60], rax
0x18000e320  mov     qword ptr [rsp+2C0h+var_2A0], r15; int
0x18000e325  mov     [rbp+1C0h+var_58], r15
0x18000e32c  mov     [rbp+1C0h+var_50], 1
0x18000e333  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000e33a  nop     dword ptr [rax+rax+00h]
0x18000e33f  mov     ebx, eax
0x18000e341  cmp     [rbp+1C0h+var_50], r15b
0x18000e348  jz      short loc_18000E35D
0x18000e34a  mov     rdx, [rbp+1C0h+var_58]
0x18000e351  mov     rcx, qword ptr [rbp+1C0h+var_60]
0x18000e358  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e35d  test    ebx, ebx
0x18000e35f  js      loc_18000E4C4
0x18000e365  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18000e36a  test    rcx, rcx
0x18000e36d  setnz   al
0x18000e370  test    al, al
0x18000e372  jz      short loc_18000E3A1
0x18000e374  lea     rdx, [rsp+2C0h+var_298]
0x18000e379  mov     [rsp+2C0h+var_298], r15d
0x18000e37e  call    cs:__imp_SRCacheContext_IsEmpty
0x18000e385  nop     dword ptr [rax+rax+00h]
0x18000e38a  mov     ebx, eax
0x18000e38c  test    eax, eax
0x18000e38e  js      loc_18000E498
0x18000e394  cmp     [rsp+2C0h+var_298], r15d
0x18000e399  setnz   al
0x18000e39c  xor     al, 1
0x18000e39e  mov     [r14], al
0x18000e3a1  mov     rcx, [rsp+2C0h+var_290]
0x18000e3a6  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18000e3ad  call    cs:__imp_SRCacheContext_AddToCache
0x18000e3b4  nop     dword ptr [rax+rax+00h]
0x18000e3b9  mov     ebx, eax
0x18000e3bb  test    eax, eax
0x18000e3bd  jns     short loc_18000E41E
0x18000e3bf  mov     rcx, [rbp+1C8h]; this
0x18000e3c6  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e3cd  mov     r9d, eax; char *
0x18000e3d0  mov     edx, 1A6h; void *
0x18000e3d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3da  mov     edx, 0B0h; void *
0x18000e3df  mov     rcx, [rbp+1C8h]; this
0x18000e3e6  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e3ed  mov     r9d, ebx; char *
0x18000e3f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3f5  xor     edx, edx
0x18000e3f7  lea     rcx, [rsp+2C0h+var_2A0]
0x18000e3fc  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e401  mov     rcx, [rsp+2C0h+var_280]
0x18000e406  mov     [rsp+2C0h+var_280], r15
0x18000e40b  test    rcx, rcx
0x18000e40e  jz      short loc_18000E448
0x18000e410  call    cs:__imp_SRCache_Free
0x18000e417  nop     dword ptr [rax+rax+00h]
0x18000e41c  jmp     short loc_18000E448
0x18000e41e  xor     edx, edx
0x18000e420  lea     rcx, [rsp+2C0h+var_2A0]
0x18000e425  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e42a  mov     rcx, [rsp+2C0h+var_280]
0x18000e42f  mov     [rsp+2C0h+var_280], r15
0x18000e434  test    rcx, rcx
0x18000e437  jz      short loc_18000E445
0x18000e439  call    cs:__imp_SRCache_Free
0x18000e440  nop     dword ptr [rax+rax+00h]
0x18000e445  mov     ebx, r15d
0x18000e448  xor     edx, edx
0x18000e44a  lea     rcx, [rsp+2C0h+var_290]
0x18000e44f  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x18000e454  mov     eax, ebx
0x18000e456  mov     rcx, [rbp+1C0h+var_38]
0x18000e45d  xor     rcx, rsp; StackCookie
0x18000e460  call    __security_check_cookie
0x18000e465  add     rsp, 298h
0x18000e46c  pop     r15
0x18000e46e  pop     r14
0x18000e470  pop     rdi
0x18000e471  pop     rsi
0x18000e472  pop     rbx
0x18000e473  pop     rbp
0x18000e474  retn
0x18000e476  mov     edx, 99h; void *
0x18000e47b  mov     rcx, [rbp+1C8h]; this
0x18000e482  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e489  mov     ebx, 80070057h
0x18000e48e  mov     r9d, ebx; char *
0x18000e491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e496  jmp     short loc_18000E454
0x18000e498  mov     rcx, [rbp+1C8h]; this
0x18000e49f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e4a6  mov     r9d, ebx; char *
0x18000e4a9  mov     edx, 2B8h; void *
0x18000e4ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4b3  mov     edx, 0ACh
0x18000e4b8  jmp     loc_18000E3DF
0x18000e4bd  mov     edx, 9Ah
0x18000e4c2  jmp     short loc_18000E47B
0x18000e4c4  mov     rcx, [rbp+1C8h]; this
0x18000e4cb  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e4d2  mov     r9d, ebx; char *
0x18000e4d5  mov     edx, 1B0h; void *
0x18000e4da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4df  mov     edx, 0A8h
0x18000e4e4  jmp     loc_18000E3DF
0x18000e4e9  mov     rcx, [rbp+1C8h]; this
0x18000e4f0  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e4f7  mov     r9d, ebx; char *
0x18000e4fa  mov     edx, 18Ch; void *
0x18000e4ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e504  mov     edx, 9Eh; void *
0x18000e509  mov     rcx, [rbp+1C8h]; this
0x18000e510  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e517  mov     r9d, ebx; char *
0x18000e51a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e51f  jmp     loc_18000E448
0x18000e524  mov     ebx, 80670012h
0x18000e529  mov     edx, 9Fh
0x18000e52e  jmp     short loc_18000E509
0x18000e530  mov     rcx, [rbp+1C8h]; this
0x18000e537  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e53e  mov     ebx, 8000FFFFh
0x18000e543  mov     edx, 166h; void *
0x18000e548  mov     r9d, ebx; char *
0x18000e54b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e550  mov     edx, 0A2h
0x18000e555  jmp     short loc_18000E57C
0x18000e557  mov     rcx, [rbp+1C8h]; this
0x18000e55e  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e565  mov     ebx, 8000FFFFh
0x18000e56a  mov     edx, 166h; void *
0x18000e56f  mov     r9d, ebx; char *
0x18000e572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e577  mov     edx, 0A4h; void *
0x18000e57c  mov     rcx, [rbp+1C8h]; this
0x18000e583  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e58a  mov     r9d, ebx; char *
0x18000e58d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e592  jmp     loc_18000E401
0x18000e597  mov     rcx, [rbp+1C8h]; this
0x18000e59e  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e5a5  mov     r9d, ebx; char *
0x18000e5a8  mov     edx, 16Dh; void *
0x18000e5ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5b2  mov     edx, 0A3h
0x18000e5b7  jmp     short loc_18000E57C
```
