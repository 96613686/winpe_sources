# CanPackageUseAllowAnyClientBasedOnPackagedAppID(ushort const *,bool *)

- ea: `0x1800219c0`
- end: `0x180021c07`
- name: `?CanPackageUseAllowAnyClientBasedOnPackagedAppID@@YAJPEBGPEA_N@Z`
- size: `583`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021890`
- `0x180090a0c`

## callees

- `0x180020598`
- `0x180020b3c`
- `0x180020ed0`
- `0x180021454`
- `0x1800219c0`
- `0x18002ba28`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021b36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021bd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021b36`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180021bd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180021a00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180021a00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021a21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021a68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021b61`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021a21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021a68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180021b61`

## string_xrefs

- `0x180021a47`: `onecore\com\combase\catalog\services.cxx`
- `0x180021b8d`: `onecore\com\combase\catalog\services.cxx`
- `0x180021b73`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180021bb8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180021a2f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall CanPackageUseAllowAnyClientBasedOnPackagedAppID(const unsigned __int16 *a1, bool *a2)
{
  bool v4; // r14
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  bool v9; // si
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-69h] BYREF
  __int64 *v20; // [rsp+28h] [rbp-61h]
  __int64 v21; // [rsp+30h] [rbp-59h] BYREF
  char v22; // [rsp+38h] [rbp-51h]
  __int128 v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 v24; // [rsp+50h] [rbp-39h]
  __int64 v25; // [rsp+58h] [rbp-31h]
  __int64 v26; // [rsp+60h] [rbp-29h]
  __int64 v27; // [rsp+68h] [rbp-21h]
  __int64 v28; // [rsp+70h] [rbp-19h]
  __int64 v29; // [rsp+78h] [rbp-11h]
  __int128 v30; // [rsp+80h] [rbp-9h]
  int v31; // [rsp+90h] [rbp+7h]
  __int64 v32; // [rsp+98h] [rbp+Fh]
  __int64 v33; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  bool v35; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v36; // [rsp+100h] [rbp+77h] BYREF
  __int64 v37; // [rsp+108h] [rbp+7Fh] BYREF

  *a2 = 0;
  v37 = 0;
  v4 = 1;
  v20 = &v37;
  v21 = 0;
  v22 = 1;
  v5 = SRCacheManager_Open(0, &v21);
  if ( v22 )
  {
    v6 = *v20;
    *v20 = v21;
    if ( v6 )
      SRCacheManager_Close(v6);
  }
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)v5,
      v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD59,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)v5,
      v19);
LABEL_6:
    v7 = v37;
    v37 = 0;
    if ( v7 )
      SRCacheManager_Close(v7);
    return v5;
  }
  v24 = 0;
  v23 = 0;
  v30 = 0;
  v25 = 0;
  v26 = 0;
  v9 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v19 = 0;
  v5 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
         (struct StateRepository::Cache::Manager_NoThrow *)&v37,
         a1,
         &v19);
  if ( (v5 & 0x80000000) != 0 )
  {
    v15 = 1165;
    goto LABEL_22;
  }
  v10 = v19;
  if ( v19 )
  {
    v36 = 0;
    v11 = StateRepository::Cache::Entity::Package_NoThrow::Open(
            (struct StateRepository::Cache::Manager_NoThrow *)&v37,
            v19,
            (struct StateRepository::Cache::Context_NoThrow *)&v36,
            &v35);
    v5 = v11;
    if ( v11 < 0 )
    {
      v16 = 1110;
    }
    else
    {
      v9 = v35;
      if ( !v35
        || (v11 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v36, &v23, 0, v10),
            v5 = v11,
            v11 >= 0) )
      {
        v13 = v36;
        v36 = 0;
        if ( v13 )
          SRCacheContext_Close(v13, v12);
        goto LABEL_16;
      }
      v16 = 1115;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v11,
      v19);
    v18 = v36;
    v36 = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v17);
    v15 = 1168;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v5,
      v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5D,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)v5,
      v19);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v23);
    goto LABEL_6;
  }
LABEL_16:
  if ( !v9 || (v25 & 0x800000000LL) == 0 || (v26 & 0x100) == 0 )
    v4 = 0;
  *a2 = v4;
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v23);
  v14 = v37;
  v37 = 0;
  if ( v14 )
    SRCacheManager_Close(v14);
  return 0;
}

```

## disassembly

```asm
0x1800219c0  push    rbp
0x1800219c2  push    rbx
0x1800219c3  push    rsi
0x1800219c4  push    rdi
0x1800219c5  push    r12
0x1800219c7  push    r14
0x1800219c9  push    r15
0x1800219cb  lea     rbp, [rsp-27h]
0x1800219d0  sub     rsp, 0B0h
0x1800219d7  xor     r12d, r12d
0x1800219da  lea     rax, [rbp+57h+arg_18]
0x1800219de  mov     [rdx], r12b
0x1800219e1  mov     r15, rdx
0x1800219e4  mov     rdi, rcx
0x1800219e7  mov     [rbp+57h+arg_18], r12
0x1800219eb  mov     r14b, 1
0x1800219ee  mov     [rbp+57h+var_B8], rax
0x1800219f2  lea     rdx, [rbp+57h+var_B0]
0x1800219f6  mov     [rbp+57h+var_B0], r12
0x1800219fa  xor     ecx, ecx
0x1800219fc  mov     [rbp+57h+var_A8], r14b
0x180021a00  call    cs:__imp_SRCacheManager_Open
0x180021a06  mov     ebx, eax
0x180021a08  cmp     [rbp+57h+var_A8], r12b
0x180021a0c  jz      short loc_180021A27
0x180021a0e  mov     r8, [rbp+57h+var_B8]
0x180021a12  mov     rdx, [rbp+57h+var_B0]
0x180021a16  mov     rcx, [r8]
0x180021a19  mov     [r8], rdx
0x180021a1c  test    rcx, rcx
0x180021a1f  jz      short loc_180021A27
0x180021a21  call    cs:__imp_SRCacheManager_Close
0x180021a27  test    ebx, ebx
0x180021a29  jns     short loc_180021A82
0x180021a2b  mov     rcx, [rbp+5Fh]; this
0x180021a2f  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021a36  mov     r9d, ebx; char *
0x180021a39  mov     edx, 0A5h; void *
0x180021a3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021a43  mov     rcx, [rbp+5Fh]; this
0x180021a47  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180021a4e  mov     r9d, ebx; char *
0x180021a51  mov     edx, 0D59h; void *
0x180021a56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021a5b  mov     rcx, [rbp+57h+arg_18]
0x180021a5f  mov     [rbp+57h+arg_18], r12
0x180021a63  test    rcx, rcx
0x180021a66  jz      short loc_180021A6E
0x180021a68  call    cs:__imp_SRCacheManager_Close
0x180021a6e  mov     eax, ebx
0x180021a70  add     rsp, 0B0h
0x180021a77  pop     r15
0x180021a79  pop     r14
0x180021a7b  pop     r12
0x180021a7d  pop     rdi
0x180021a7e  pop     rsi
0x180021a7f  pop     rbx
0x180021a80  pop     rbp
0x180021a81  retn
0x180021a82  xorps   xmm0, xmm0
0x180021a85  mov     [rbp+57h+var_90], r12
0x180021a89  lea     r8, [rbp+57h+var_C0]; __int64 *
0x180021a8d  movdqa  [rbp+57h+var_A0], xmm0
0x180021a92  mov     rdx, rdi; unsigned __int16 *
0x180021a95  movdqa  [rbp+57h+var_60], xmm0
0x180021a9a  lea     rcx, [rbp+57h+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x180021a9e  mov     [rbp+57h+var_88], r12
0x180021aa2  mov     [rbp+57h+var_80], r12
0x180021aa6  mov     sil, r12b
0x180021aa9  mov     [rbp+57h+var_78], r12
0x180021aad  mov     [rbp+57h+var_70], r12
0x180021ab1  mov     [rbp+57h+var_68], r12
0x180021ab5  mov     [rbp+57h+var_50], r12d
0x180021ab9  mov     [rbp+57h+var_48], r12
0x180021abd  mov     [rbp+57h+var_40], r12
0x180021ac1  mov     [rbp+57h+arg_8], r12b
0x180021ac5  mov     [rbp+57h+var_C0], r12
0x180021ac9  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180021ace  mov     ebx, eax
0x180021ad0  test    eax, eax
0x180021ad2  js      loc_180021B6E
0x180021ad8  mov     rdi, [rbp+57h+var_C0]
0x180021adc  test    rdi, rdi
0x180021adf  jz      short loc_180021B3C
0x180021ae1  lea     r9, [rbp+57h+arg_8]; bool *
0x180021ae5  mov     [rbp+57h+arg_10], r12
0x180021ae9  lea     r8, [rbp+57h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180021aed  mov     rdx, rdi; __int64
0x180021af0  lea     rcx, [rbp+57h+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x180021af4  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180021af9  mov     ebx, eax
0x180021afb  test    eax, eax
0x180021afd  js      loc_180021BAF
0x180021b03  mov     sil, [rbp+57h+arg_8]
0x180021b07  test    sil, sil
0x180021b0a  jz      short loc_180021B29
0x180021b0c  mov     r9, rdi
0x180021b0f  lea     rdx, [rbp+57h+var_A0]
0x180021b13  xor     r8d, r8d
0x180021b16  lea     rcx, [rbp+57h+arg_10]
0x180021b1a  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180021b1f  mov     ebx, eax
0x180021b21  test    eax, eax
0x180021b23  js      loc_180021C00
0x180021b29  mov     rcx, [rbp+57h+arg_10]
0x180021b2d  mov     [rbp+57h+arg_10], r12
0x180021b31  test    rcx, rcx
0x180021b34  jz      short loc_180021B3C
0x180021b36  call    cs:__imp_SRCacheContext_Close
0x180021b3c  test    sil, sil
0x180021b3f  jnz     loc_180021BE4
0x180021b45  mov     r14b, r12b
0x180021b48  lea     rcx, [rbp+57h+var_A0]; this
0x180021b4c  mov     [r15], r14b
0x180021b4f  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180021b54  mov     rcx, [rbp+57h+arg_18]
0x180021b58  mov     [rbp+57h+arg_18], r12
0x180021b5c  test    rcx, rcx
0x180021b5f  jz      short loc_180021B67
0x180021b61  call    cs:__imp_SRCacheManager_Close
0x180021b67  xor     eax, eax
0x180021b69  jmp     loc_180021A70
0x180021b6e  mov     edx, 48Dh; void *
0x180021b73  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021b7a  mov     rcx, [rbp+5Fh]; this
0x180021b7e  mov     r9d, ebx; char *
0x180021b81  mov     r8, rdi; unsigned int
0x180021b84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b89  mov     rcx, [rbp+5Fh]; this
0x180021b8d  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180021b94  mov     r9d, ebx; char *
0x180021b97  mov     edx, 0D5Dh; void *
0x180021b9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ba1  lea     rcx, [rbp+57h+var_A0]; this
0x180021ba5  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180021baa  jmp     loc_180021A5B
0x180021baf  mov     edx, 456h; void *
0x180021bb4  mov     rcx, [rbp+5Fh]; this
0x180021bb8  lea     rdi, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180021bbf  mov     r8, rdi; unsigned int
0x180021bc2  mov     r9d, eax; char *
0x180021bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021bca  mov     rcx, [rbp+57h+arg_10]
0x180021bce  mov     [rbp+57h+arg_10], r12
0x180021bd2  test    rcx, rcx
0x180021bd5  jz      short loc_180021BDD
0x180021bd7  call    cs:__imp_SRCacheContext_Close
0x180021bdd  mov     edx, 490h
0x180021be2  jmp     short loc_180021B7A
0x180021be4  test    byte ptr [rbp+57h+var_88+4], 8
0x180021be8  jz      loc_180021B45
0x180021bee  test    dword ptr [rbp+57h+var_80], 100h
0x180021bf5  jz      loc_180021B45
0x180021bfb  jmp     loc_180021B48
0x180021c00  mov     edx, 45Bh
0x180021c05  jmp     short loc_180021BB4
```
