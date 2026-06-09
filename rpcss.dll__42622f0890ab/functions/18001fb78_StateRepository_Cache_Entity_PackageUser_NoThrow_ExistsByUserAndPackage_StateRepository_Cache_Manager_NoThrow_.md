# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x18001fb78`
- end: `0x180020006`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `1166`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002000c`

## callees

- `0x18001fb78`
- `0x1800211f0`
- `0x1800217e4`
- `0x18002ba28`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001fc86`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001fcff`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001fc86`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18001fcff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fc1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fd87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fe2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fe56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fe91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001febb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fc1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fd87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fe2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fe56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001fe91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001febb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001fbf5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001fbf5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001fe41`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001fea6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001fe41`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001fea6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001fd5d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001fd5d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18001fdae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-2!SRCacheContext_IsEmpty` at `0x18001fdae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001fdd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001fdd7`

## string_xrefs

- `0x18001ff84`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001ffab`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001ffeb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18001fe0e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18001fe6a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18001ff5d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18001ffd0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x18001fdee`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001fee9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001ff18`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001ff3d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
  __int64 v9; // rcx
  bool v10; // r8
  int v11; // eax
  __int64 v12; // rcx
  int IsEmpty; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  int v28[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD v30[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+248h] [rbp+148h]
  __int64 v34; // [rsp+250h] [rbp+150h]
  _BYTE *v35; // [rsp+258h] [rbp+158h]
  unsigned __int16 v36[4]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v37; // [rsp+268h] [rbp+168h] BYREF
  char v38; // [rsp+270h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a4 = 0;
  if ( !a2 )
  {
    v21 = 153;
LABEL_29:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v28[0]);
    return (unsigned int)v8;
  }
  if ( !a3 )
  {
    v21 = 154;
    goto LABEL_29;
  }
  v7 = *(_QWORD *)a1;
  *(_QWORD *)v36 = v28;
  *(_QWORD *)v28 = 0;
  v37 = 0;
  v38 = 1;
  v8 = SRCacheContext_Open(v7, L"PackageUser\\Index\\UserAndPackage", 0, &v37);
  if ( v38 )
  {
    v9 = **(_QWORD **)v36;
    **(_QWORD **)v36 = v37;
    if ( v9 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v26 = 158;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
LABEL_26:
    v20 = *(_QWORD *)v28;
    *(_QWORD *)v28 = 0;
    if ( v20 )
      SRCacheContext_Close(v20, v17);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v28 )
  {
    v8 = -2140733422;
    v26 = 159;
    goto LABEL_42;
  }
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v33 = 0;
  v34 = 256;
  v35 = v32;
  if ( (unsigned int)_o__ui64tow_s(a2, v36, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v28[0]);
    goto LABEL_45;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, v36);
  if ( v8 < 0 )
  {
LABEL_45:
    v27 = 162;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
LABEL_24:
    v19 = v31;
    v31 = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_26;
  }
  v11 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v31, v33 + 2, v10);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v11,
      v28[0]);
    v27 = 163;
    goto LABEL_48;
  }
  *(_DWORD *)&v35[2 * v33++] = 94;
  if ( (unsigned int)_o__ui64tow_s(a3, v36, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v28[0]);
    goto LABEL_47;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v31, v36);
  if ( v8 < 0 )
  {
LABEL_47:
    v27 = 164;
    goto LABEL_48;
  }
  *(_QWORD *)v36 = &v29;
  v29 = 0;
  v37 = 0;
  v38 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v28, v35, 0, &v37);
  if ( v38 )
  {
    v12 = **(_QWORD **)v36;
    **(_QWORD **)v36 = v37;
    if ( v12 )
      ((void (*)(void))SRCacheContext_Close)();
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v16 = 168;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)v8,
      v28[0]);
    v18 = v29;
    v29 = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v17);
    goto LABEL_24;
  }
  if ( !v29 )
    goto LABEL_20;
  v30[0] = 0;
  IsEmpty = SRCacheContext_IsEmpty(v29, v30);
  v8 = IsEmpty;
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v28[0]);
    v16 = 172;
    goto LABEL_22;
  }
  *a4 = v30[0] == 0;
LABEL_20:
  v14 = SRCacheContext_AddToCache(*(_QWORD *)v28, L"PackageUser\\Index\\UserAndPackage");
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v14,
      v28[0]);
    v16 = 176;
    goto LABEL_22;
  }
  v23 = v29;
  v29 = 0;
  if ( v23 )
    ((void (*)(void))SRCacheContext_Close)();
  v24 = v31;
  v31 = 0;
  if ( v24 )
    SRCache_Free();
  v25 = *(_QWORD *)v28;
  *(_QWORD *)v28 = 0;
  if ( v25 )
    SRCacheContext_Close(v25, v15);
  return 0;
}

```

## disassembly

```asm
0x18001fb78  push    rbp
0x18001fb7a  push    rbx
0x18001fb7b  push    rsi
0x18001fb7c  push    rdi
0x18001fb7d  push    r14
0x18001fb7f  push    r15
0x18001fb81  lea     rbp, [rsp-198h]
0x18001fb89  sub     rsp, 298h
0x18001fb90  mov     rax, cs:__security_cookie
0x18001fb97  xor     rax, rsp
0x18001fb9a  mov     [rbp+1C0h+var_38], rax
0x18001fba1  xor     r15d, r15d
0x18001fba4  mov     r14, r9
0x18001fba7  mov     [r9], r15b
0x18001fbaa  mov     rdi, r8
0x18001fbad  mov     rsi, rdx
0x18001fbb0  test    rdx, rdx
0x18001fbb3  jz      loc_18001FE5E
0x18001fbb9  test    r8, r8
0x18001fbbc  jz      loc_18001FF07
0x18001fbc2  mov     rcx, [rcx]
0x18001fbc5  lea     rax, [rsp+2C0h+var_2A0]
0x18001fbca  lea     r9, [rbp+1C0h+var_58]
0x18001fbd1  mov     qword ptr [rbp+1C0h+var_60], rax
0x18001fbd8  xor     r8d, r8d
0x18001fbdb  mov     qword ptr [rsp+2C0h+var_2A0], r15; int
0x18001fbe0  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18001fbe7  mov     [rbp+1C0h+var_58], r15
0x18001fbee  mov     [rbp+1C0h+var_50], 1
0x18001fbf5  call    cs:__imp_SRCacheContext_Open
0x18001fbfb  mov     ebx, eax
0x18001fbfd  cmp     [rbp+1C0h+var_50], r15b
0x18001fc04  jz      short loc_18001FC25
0x18001fc06  mov     r8, qword ptr [rbp+1C0h+var_60]
0x18001fc0d  mov     rdx, [rbp+1C0h+var_58]
0x18001fc14  mov     rcx, [r8]
0x18001fc17  mov     [r8], rdx
0x18001fc1a  test    rcx, rcx
0x18001fc1d  jz      short loc_18001FC25
0x18001fc1f  call    cs:__imp_SRCacheContext_Close
0x18001fc25  test    ebx, ebx
0x18001fc27  js      loc_18001FF36
0x18001fc2d  cmp     qword ptr [rsp+2C0h+var_2A0], r15
0x18001fc32  setnz   al
0x18001fc35  test    al, al
0x18001fc37  jz      loc_18001FF71
0x18001fc3d  xor     edx, edx; Val
0x18001fc3f  mov     [rsp+2C0h+var_280], r15
0x18001fc44  mov     r8d, 200h; Size
0x18001fc4a  lea     rcx, [rsp+2C0h+var_278]; void *
0x18001fc4f  call    memset_0
0x18001fc54  mov     r9d, 10h
0x18001fc5a  mov     [rbp+1C0h+var_78], r15
0x18001fc61  lea     rax, [rsp+2C0h+var_278]
0x18001fc66  mov     [rbp+1C0h+var_70], 100h
0x18001fc71  lea     rdx, [rbp+1C0h+var_60]
0x18001fc78  mov     [rbp+1C0h+var_68], rax
0x18001fc7f  mov     rcx, rsi
0x18001fc82  lea     r8d, [r9+1]
0x18001fc86  call    cs:__imp__o__ui64tow_s
0x18001fc8c  test    eax, eax
0x18001fc8e  jnz     loc_18001FF7D
0x18001fc94  lea     rdx, [rbp+1C0h+var_60]; unsigned __int16 *
0x18001fc9b  lea     rcx, [rsp+2C0h+var_280]; this
0x18001fca0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001fca5  mov     ebx, eax
0x18001fca7  test    eax, eax
0x18001fca9  js      loc_18001FF9D
0x18001fcaf  mov     rdx, [rbp+1C0h+var_78]
0x18001fcb6  lea     rcx, [rsp+2C0h+var_280]; this
0x18001fcbb  add     rdx, 2; unsigned __int64
0x18001fcbf  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x18001fcc4  mov     ebx, eax
0x18001fcc6  test    eax, eax
0x18001fcc8  js      loc_18001FFE4
0x18001fcce  mov     r10, [rbp+1C0h+var_78]
0x18001fcd5  mov     r9d, 10h
0x18001fcdb  mov     rdx, [rbp+1C0h+var_68]
0x18001fce2  mov     rcx, rdi
0x18001fce5  lea     r8d, [r9+1]
0x18001fce9  mov     dword ptr [rdx+r10*2], 5Eh ; '^'
0x18001fcf1  lea     rdx, [rbp+1C0h+var_60]
0x18001fcf8  inc     [rbp+1C0h+var_78]
0x18001fcff  call    cs:__imp__o__ui64tow_s
0x18001fd05  test    eax, eax
0x18001fd07  jnz     loc_18001FFA4
0x18001fd0d  lea     rdx, [rbp+1C0h+var_60]; unsigned __int16 *
0x18001fd14  lea     rcx, [rsp+2C0h+var_280]; this
0x18001fd19  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001fd1e  mov     ebx, eax
0x18001fd20  test    eax, eax
0x18001fd22  js      loc_18001FFC4
0x18001fd28  mov     rdx, [rbp+1C0h+var_68]
0x18001fd2f  lea     rax, [rsp+2C0h+var_298]
0x18001fd34  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18001fd39  lea     r9, [rbp+1C0h+var_58]
0x18001fd40  xor     r8d, r8d
0x18001fd43  mov     qword ptr [rbp+1C0h+var_60], rax
0x18001fd4a  mov     [rsp+2C0h+var_298], r15
0x18001fd4f  mov     [rbp+1C0h+var_58], r15
0x18001fd56  mov     [rbp+1C0h+var_50], 1
0x18001fd5d  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001fd63  mov     ebx, eax
0x18001fd65  cmp     [rbp+1C0h+var_50], r15b
0x18001fd6c  jz      short loc_18001FD8D
0x18001fd6e  mov     r8, qword ptr [rbp+1C0h+var_60]
0x18001fd75  mov     rdx, [rbp+1C0h+var_58]
0x18001fd7c  mov     rcx, [r8]
0x18001fd7f  mov     [r8], rdx
0x18001fd82  test    rcx, rcx
0x18001fd85  jz      short loc_18001FD8D
0x18001fd87  call    cs:__imp_SRCacheContext_Close
0x18001fd8d  test    ebx, ebx
0x18001fd8f  js      loc_18001FF11
0x18001fd95  mov     rcx, [rsp+2C0h+var_298]
0x18001fd9a  test    rcx, rcx
0x18001fd9d  setnz   al
0x18001fda0  test    al, al
0x18001fda2  jz      short loc_18001FDCB
0x18001fda4  lea     rdx, [rsp+2C0h+var_290]
0x18001fda9  mov     [rsp+2C0h+var_290], r15d
0x18001fdae  call    cs:__imp_SRCacheContext_IsEmpty
0x18001fdb4  mov     ebx, eax
0x18001fdb6  test    eax, eax
0x18001fdb8  js      loc_18001FEE2
0x18001fdbe  cmp     [rsp+2C0h+var_290], r15d
0x18001fdc3  setnz   al
0x18001fdc6  xor     al, 1
0x18001fdc8  mov     [r14], al
0x18001fdcb  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18001fdd0  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x18001fdd7  call    cs:__imp_SRCacheContext_AddToCache
0x18001fddd  mov     ebx, eax
0x18001fddf  test    eax, eax
0x18001fde1  jns     loc_18001FE82
0x18001fde7  mov     rcx, [rbp+1C8h]; this
0x18001fdee  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fdf5  mov     r9d, eax; char *
0x18001fdf8  mov     edx, 1A6h; void *
0x18001fdfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe02  mov     edx, 0B0h; void *
0x18001fe07  mov     rcx, [rbp+1C8h]; this
0x18001fe0e  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fe15  mov     r9d, ebx; char *
0x18001fe18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe1d  mov     rcx, [rsp+2C0h+var_298]
0x18001fe22  mov     [rsp+2C0h+var_298], r15
0x18001fe27  test    rcx, rcx
0x18001fe2a  jz      short loc_18001FE32
0x18001fe2c  call    cs:__imp_SRCacheContext_Close
0x18001fe32  mov     rcx, [rsp+2C0h+var_280]
0x18001fe37  mov     [rsp+2C0h+var_280], r15
0x18001fe3c  test    rcx, rcx
0x18001fe3f  jz      short loc_18001FE47
0x18001fe41  call    cs:__imp_SRCache_Free
0x18001fe47  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18001fe4c  mov     qword ptr [rsp+2C0h+var_2A0], r15
0x18001fe51  test    rcx, rcx
0x18001fe54  jz      short loc_18001FE7E
0x18001fe56  call    cs:__imp_SRCacheContext_Close
0x18001fe5c  jmp     short loc_18001FE7E
0x18001fe5e  mov     edx, 99h; void *
0x18001fe63  mov     rcx, [rbp+1C8h]; this
0x18001fe6a  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fe71  mov     ebx, 80070057h
0x18001fe76  mov     r9d, ebx; char *
0x18001fe79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe7e  mov     eax, ebx
0x18001fe80  jmp     short loc_18001FEC3
0x18001fe82  mov     rcx, [rsp+2C0h+var_298]
0x18001fe87  mov     [rsp+2C0h+var_298], r15
0x18001fe8c  test    rcx, rcx
0x18001fe8f  jz      short loc_18001FE97
0x18001fe91  call    cs:__imp_SRCacheContext_Close
0x18001fe97  mov     rcx, [rsp+2C0h+var_280]
0x18001fe9c  mov     [rsp+2C0h+var_280], r15
0x18001fea1  test    rcx, rcx
0x18001fea4  jz      short loc_18001FEAC
0x18001fea6  call    cs:__imp_SRCache_Free
0x18001feac  mov     rcx, qword ptr [rsp+2C0h+var_2A0]
0x18001feb1  mov     qword ptr [rsp+2C0h+var_2A0], r15
0x18001feb6  test    rcx, rcx
0x18001feb9  jz      short loc_18001FEC1
0x18001febb  call    cs:__imp_SRCacheContext_Close
0x18001fec1  xor     eax, eax
0x18001fec3  mov     rcx, [rbp+1C0h+var_38]
0x18001feca  xor     rcx, rsp; StackCookie
0x18001fecd  call    __security_check_cookie
0x18001fed2  add     rsp, 298h
0x18001fed9  pop     r15
0x18001fedb  pop     r14
0x18001fedd  pop     rdi
0x18001fede  pop     rsi
0x18001fedf  pop     rbx
0x18001fee0  pop     rbp
0x18001fee1  retn
0x18001fee2  mov     rcx, [rbp+1C8h]; this
0x18001fee9  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fef0  mov     r9d, ebx; char *
0x18001fef3  mov     edx, 2B8h; void *
0x18001fef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fefd  mov     edx, 0ACh
0x18001ff02  jmp     loc_18001FE07
0x18001ff07  mov     edx, 9Ah
0x18001ff0c  jmp     loc_18001FE63
0x18001ff11  mov     rcx, [rbp+1C8h]; this
0x18001ff18  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ff1f  mov     r9d, ebx; char *
0x18001ff22  mov     edx, 1B0h; void *
0x18001ff27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff2c  mov     edx, 0A8h
0x18001ff31  jmp     loc_18001FE07
0x18001ff36  mov     rcx, [rbp+1C8h]; this
0x18001ff3d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ff44  mov     r9d, ebx; char *
0x18001ff47  mov     edx, 18Ch; void *
0x18001ff4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff51  mov     edx, 9Eh; void *
0x18001ff56  mov     rcx, [rbp+1C8h]; this
0x18001ff5d  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ff64  mov     r9d, ebx; char *
0x18001ff67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff6c  jmp     loc_18001FE47
0x18001ff71  mov     ebx, 80670012h
0x18001ff76  mov     edx, 9Fh
0x18001ff7b  jmp     short loc_18001FF56
0x18001ff7d  mov     rcx, [rbp+1C8h]; this
0x18001ff84  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ff8b  mov     ebx, 8000FFFFh
0x18001ff90  mov     edx, 166h; void *
0x18001ff95  mov     r9d, ebx; char *
0x18001ff98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff9d  mov     edx, 0A2h
0x18001ffa2  jmp     short loc_18001FFC9
0x18001ffa4  mov     rcx, [rbp+1C8h]; this
0x18001ffab  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ffb2  mov     ebx, 8000FFFFh
0x18001ffb7  mov     edx, 166h; void *
0x18001ffbc  mov     r9d, ebx; char *
0x18001ffbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffc4  mov     edx, 0A4h; void *
0x18001ffc9  mov     rcx, [rbp+1C8h]; this
0x18001ffd0  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ffd7  mov     r9d, ebx; char *
0x18001ffda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffdf  jmp     loc_18001FE32
0x18001ffe4  mov     rcx, [rbp+1C8h]; this
0x18001ffeb  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001fff2  mov     r9d, ebx; char *
0x18001fff5  mov     edx, 16Dh; void *
0x18001fffa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffff  mov     edx, 0A3h
0x180020004  jmp     short loc_18001FFC9
```
