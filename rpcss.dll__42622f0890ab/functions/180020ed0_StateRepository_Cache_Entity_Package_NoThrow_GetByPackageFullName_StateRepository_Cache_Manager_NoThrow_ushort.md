# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180020ed0`
- end: `0x1800211e4`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `788`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18002000c`
- `0x180020e38`
- `0x1800219c0`
- `0x180021c10`
- `0x1800722a0`
- `0x180094190`

## callees

- `0x180020ed0`
- `0x1800211f0`
- `0x18002ba28`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020f52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002100d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002108f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800210d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800210ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021119`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180020f52`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002100d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002108f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800210d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800210ef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021119`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180020f2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180020f2e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180021143`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180021143`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800210c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180021104`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800210c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180021104`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180020fe9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180020fe9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002103a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18002103a`

## string_xrefs

- `0x180021071`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002109e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180021189`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180021051`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002115a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800211a4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800211c9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int *v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+258h] [rbp+158h]
  __int64 v33; // [rsp+260h] [rbp+160h]
  _BYTE *v34; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v29 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v25 = 0;
  v27 = v25;
  v28 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v28);
  if ( v29 )
  {
    v7 = v28;
    v8 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v8 )
      SRCacheContext_Close(v8, v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v24 = 1128;
    goto LABEL_32;
  }
  if ( !*(_QWORD *)v25 )
  {
    v6 = -2140733422;
    v24 = 1129;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v25[0]);
LABEL_19:
    v18 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v15);
    return v6;
  }
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v32 = 0;
  v34 = v31;
  v33 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, a2);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v9,
      v25[0]);
LABEL_17:
    v17 = v30;
    v30 = 0;
    if ( v17 )
      SRCache_Free();
    goto LABEL_19;
  }
  v27 = (int *)&v26;
  v26 = 0;
  v28 = 0;
  v29 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v34, 0, &v28);
  if ( v29 )
  {
    v10 = v28;
    v11 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v11 )
      SRCacheContext_Close(v11, v10);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v14 = 1136;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v25[0]);
    v16 = v26;
    v26 = 0;
    if ( v16 )
      SRCacheContext_Close(v16, v15);
    goto LABEL_17;
  }
  if ( v26 )
  {
    v23 = SRCacheContext_EnumerateData(v26, 0, a3);
    v6 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v23,
        v25[0]);
      v14 = 1139;
      goto LABEL_14;
    }
  }
  v12 = SRCacheContext_AddToCache(*(_QWORD *)v25, L"Package\\Index\\PackageFullName");
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      v25[0]);
    v14 = 1142;
    goto LABEL_14;
  }
  v20 = v26;
  v26 = 0;
  if ( v20 )
    SRCacheContext_Close(v20, v13);
  v21 = v30;
  v30 = 0;
  if ( v21 )
    SRCache_Free();
  v22 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v22 )
    SRCacheContext_Close(v22, v13);
  return 0;
}

```

## disassembly

```asm
0x180020ed0  push    rbp
0x180020ed2  push    rbx
0x180020ed3  push    rsi
0x180020ed4  push    rdi
0x180020ed5  push    r14
0x180020ed7  lea     rbp, [rsp-180h]
0x180020edf  sub     rsp, 280h
0x180020ee6  mov     rax, cs:__security_cookie
0x180020eed  xor     rax, rsp
0x180020ef0  mov     [rbp+1A0h+var_30], rax
0x180020ef7  xor     r14d, r14d
0x180020efa  mov     [rsp+2A0h+var_260], 1
0x180020eff  mov     [r8], r14
0x180020f02  lea     rax, [rsp+2A0h+var_280]
0x180020f07  mov     rcx, [rcx]
0x180020f0a  lea     r9, [rsp+2A0h+var_268]
0x180020f0f  mov     rdi, r8
0x180020f12  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x180020f17  mov     rsi, rdx
0x180020f1a  mov     [rsp+2A0h+var_270], rax
0x180020f1f  xor     r8d, r8d
0x180020f22  mov     [rsp+2A0h+var_268], r14
0x180020f27  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x180020f2e  call    cs:__imp_SRCacheContext_Open
0x180020f34  mov     ebx, eax
0x180020f36  cmp     [rsp+2A0h+var_260], r14b
0x180020f3b  jz      short loc_180020F58
0x180020f3d  mov     r8, [rsp+2A0h+var_270]
0x180020f42  mov     rdx, [rsp+2A0h+var_268]
0x180020f47  mov     rcx, [r8]
0x180020f4a  mov     [r8], rdx
0x180020f4d  test    rcx, rcx
0x180020f50  jz      short loc_180020F58
0x180020f52  call    cs:__imp_SRCacheContext_Close
0x180020f58  test    ebx, ebx
0x180020f5a  js      loc_1800211C2
0x180020f60  cmp     qword ptr [rsp+2A0h+var_280], r14
0x180020f65  setnz   al
0x180020f68  test    al, al
0x180020f6a  jz      loc_180021178
0x180020f70  xor     edx, edx; Val
0x180020f72  mov     [rsp+2A0h+var_250], r14
0x180020f77  mov     r8d, 200h; Size
0x180020f7d  lea     rcx, [rsp+2A0h+var_248]; void *
0x180020f82  call    memset_0
0x180020f87  lea     rax, [rsp+2A0h+var_248]
0x180020f8c  mov     [rbp+1A0h+var_48], r14
0x180020f93  mov     rdx, rsi; unsigned __int16 *
0x180020f96  mov     [rbp+1A0h+var_38], rax
0x180020f9d  lea     rcx, [rsp+2A0h+var_250]; this
0x180020fa2  mov     [rbp+1A0h+var_40], 100h
0x180020fad  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180020fb2  mov     ebx, eax
0x180020fb4  test    eax, eax
0x180020fb6  js      loc_180021097
0x180020fbc  mov     rdx, [rbp+1A0h+var_38]
0x180020fc3  lea     rax, [rsp+2A0h+var_278]
0x180020fc8  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180020fcd  lea     r9, [rsp+2A0h+var_268]
0x180020fd2  xor     r8d, r8d
0x180020fd5  mov     [rsp+2A0h+var_270], rax
0x180020fda  mov     [rsp+2A0h+var_278], r14
0x180020fdf  mov     [rsp+2A0h+var_268], r14
0x180020fe4  mov     [rsp+2A0h+var_260], 1
0x180020fe9  call    cs:__imp_SRCacheContext_OpenSubContext
0x180020fef  mov     ebx, eax
0x180020ff1  cmp     [rsp+2A0h+var_260], r14b
0x180020ff6  jz      short loc_180021013
0x180020ff8  mov     r8, [rsp+2A0h+var_270]
0x180020ffd  mov     rdx, [rsp+2A0h+var_268]
0x180021002  mov     rcx, [r8]
0x180021005  mov     [r8], rdx
0x180021008  test    rcx, rcx
0x18002100b  jz      short loc_180021013
0x18002100d  call    cs:__imp_SRCacheContext_Close
0x180021013  test    ebx, ebx
0x180021015  js      loc_18002119D
0x18002101b  mov     rcx, [rsp+2A0h+var_278]
0x180021020  test    rcx, rcx
0x180021023  setnz   al
0x180021026  test    al, al
0x180021028  jnz     loc_18002113E
0x18002102e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180021033  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18002103a  call    cs:__imp_SRCacheContext_AddToCache
0x180021040  mov     ebx, eax
0x180021042  test    eax, eax
0x180021044  jns     loc_1800210E0
0x18002104a  mov     rcx, [rbp+1A8h]; this
0x180021051  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021058  mov     r9d, eax; char *
0x18002105b  mov     edx, 1A6h; void *
0x180021060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021065  mov     edx, 476h; void *
0x18002106a  mov     rcx, [rbp+1A8h]; this
0x180021071  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021078  mov     r9d, ebx; char *
0x18002107b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021080  mov     rcx, [rsp+2A0h+var_278]
0x180021085  mov     [rsp+2A0h+var_278], r14
0x18002108a  test    rcx, rcx
0x18002108d  jz      short loc_1800210B2
0x18002108f  call    cs:__imp_SRCacheContext_Close
0x180021095  jmp     short loc_1800210B2
0x180021097  mov     rcx, [rbp+1A8h]; this
0x18002109e  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800210a5  mov     r9d, ebx; char *
0x1800210a8  mov     edx, 46Ch; void *
0x1800210ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800210b2  mov     rcx, [rsp+2A0h+var_250]
0x1800210b7  mov     [rsp+2A0h+var_250], r14
0x1800210bc  test    rcx, rcx
0x1800210bf  jz      short loc_1800210C7
0x1800210c1  call    cs:__imp_SRCache_Free
0x1800210c7  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800210cc  mov     qword ptr [rsp+2A0h+var_280], r14
0x1800210d1  test    rcx, rcx
0x1800210d4  jz      short loc_1800210DC
0x1800210d6  call    cs:__imp_SRCacheContext_Close
0x1800210dc  mov     eax, ebx
0x1800210de  jmp     short loc_180021121
0x1800210e0  mov     rcx, [rsp+2A0h+var_278]
0x1800210e5  mov     [rsp+2A0h+var_278], r14
0x1800210ea  test    rcx, rcx
0x1800210ed  jz      short loc_1800210F5
0x1800210ef  call    cs:__imp_SRCacheContext_Close
0x1800210f5  mov     rcx, [rsp+2A0h+var_250]
0x1800210fa  mov     [rsp+2A0h+var_250], r14
0x1800210ff  test    rcx, rcx
0x180021102  jz      short loc_18002110A
0x180021104  call    cs:__imp_SRCache_Free
0x18002110a  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18002110f  mov     qword ptr [rsp+2A0h+var_280], r14
0x180021114  test    rcx, rcx
0x180021117  jz      short loc_18002111F
0x180021119  call    cs:__imp_SRCacheContext_Close
0x18002111f  xor     eax, eax
0x180021121  mov     rcx, [rbp+1A0h+var_30]
0x180021128  xor     rcx, rsp; StackCookie
0x18002112b  call    __security_check_cookie
0x180021130  add     rsp, 280h
0x180021137  pop     r14
0x180021139  pop     rdi
0x18002113a  pop     rsi
0x18002113b  pop     rbx
0x18002113c  pop     rbp
0x18002113d  retn
0x18002113e  mov     r8, rdi
0x180021141  xor     edx, edx
0x180021143  call    cs:__imp_SRCacheContext_EnumerateData
0x180021149  mov     ebx, eax
0x18002114b  test    eax, eax
0x18002114d  jns     loc_18002102E
0x180021153  mov     rcx, [rbp+1A8h]; this
0x18002115a  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021161  mov     r9d, eax; char *
0x180021164  mov     edx, 2A6h; void *
0x180021169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002116e  mov     edx, 473h
0x180021173  jmp     loc_18002106A
0x180021178  mov     ebx, 80670012h
0x18002117d  mov     edx, 469h; void *
0x180021182  mov     rcx, [rbp+1A8h]; this
0x180021189  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021190  mov     r9d, ebx; char *
0x180021193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021198  jmp     loc_1800210C7
0x18002119d  mov     rcx, [rbp+1A8h]; this
0x1800211a4  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800211ab  mov     r9d, ebx; char *
0x1800211ae  mov     edx, 1B0h; void *
0x1800211b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800211b8  mov     edx, 470h
0x1800211bd  jmp     loc_18002106A
0x1800211c2  mov     rcx, [rbp+1A8h]; this
0x1800211c9  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800211d0  mov     r9d, ebx; char *
0x1800211d3  mov     edx, 18Ch; void *
0x1800211d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800211dd  mov     edx, 468h
0x1800211e2  jmp     short loc_180021182
```
