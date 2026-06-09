# StateRepository::Cache::Entity::Package_NoThrow::GetEffectiveLocationByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)

- ea: `0x18001b894`
- end: `0x18001bb40`
- name: `?GetEffectiveLocationByUserAndPackage@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180037460`

## callees

- `0x18001ae24`
- `0x18001b388`
- `0x18001b894`
- `0x18001cc38`
- `0x18001d0d4`
- `0x18002b1d4`
- `0x18002b5bc`
- `0x18002bc68`
- `0x180037d54`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b930`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bad2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bb1c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b930`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bad2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bb1c`

## string_xrefs

- `0x18001b914`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001b9e6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001bae0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetEffectiveLocationByUserAndPackage(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void **a4)
{
  _WORD *v8; // rbx
  int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  unsigned __int64 v15; // rdi
  _WORD *i; // rax
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // r14
  const struct std::nothrow_t *v19; // rax
  const struct std::nothrow_t *v20; // rsi
  const struct std::nothrow_t *v21; // rdx
  unsigned __int64 v22; // rcx
  void *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int *v26; // [rsp+20h] [rbp-69h]
  int v27[4]; // [rsp+30h] [rbp-59h] BYREF
  __int128 v28; // [rsp+40h] [rbp-49h]
  __int128 v29; // [rsp+50h] [rbp-39h] BYREF
  __int64 v30; // [rsp+60h] [rbp-29h]
  __int128 v31; // [rsp+68h] [rbp-21h]
  __int64 v32; // [rsp+78h] [rbp-11h]
  __int64 v33; // [rsp+80h] [rbp-9h]
  _WORD *v34; // [rsp+88h] [rbp-1h]
  __int128 v35; // [rsp+90h] [rbp+7h]
  int v36; // [rsp+A0h] [rbp+17h]
  __int64 v37; // [rsp+A8h] [rbp+1Fh]
  __int64 v38; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  __int64 v40; // [rsp+F8h] [rbp+6Fh] BYREF

  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(a4);
  v8 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  if ( !a2 )
    goto LABEL_9;
  LOBYTE(v40) = 0;
  v26 = v27;
  v9 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(a1, a2, a3);
  if ( v9 < 0 )
  {
    v10 = 2297;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v9,
      (int)v27);
    v11 = *((_QWORD *)&v28 + 1);
    *((_QWORD *)&v28 + 1) = 0;
    if ( v11 )
      SRCache_Free();
    return (unsigned int)v9;
  }
  if ( !(_BYTE)v40 || (v8 = (_WORD *)*((_QWORD *)&v28 + 1)) == 0 )
  {
LABEL_9:
    LOBYTE(v40) = 0;
    v26 = v27;
    v9 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(a1, 0, a3);
    if ( v9 < 0 )
    {
      v10 = 2310;
      goto LABEL_4;
    }
    if ( (_BYTE)v40 )
      v8 = (_WORD *)*((_QWORD *)&v28 + 1);
  }
  v30 = 0;
  v29 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v31 = 0;
  if ( v8 )
    goto LABEL_19;
  LOBYTE(v40) = 0;
  v26 = (int *)&v40;
  v13 = StateRepository::Cache::Entity::Package_NoThrow::Get(a1, a3, 768, &v29);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x914,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v13,
      (int)&v40);
LABEL_35:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v29);
    v25 = *((_QWORD *)&v28 + 1);
    *((_QWORD *)&v28 + 1) = 0;
    if ( v25 )
      SRCache_Free();
    return v14;
  }
  if ( (_BYTE)v40 )
  {
    v8 = (_WORD *)v35;
    if ( (_QWORD)v35 || (v8 = v34) != 0 )
    {
LABEL_19:
      v15 = 0;
      for ( i = v8; *i; ++v15 )
      {
        if ( v15 >= 0x7FFFFFFF )
          break;
        ++i;
      }
      v17 = v15 + 1;
      v18 = 2 * v17;
      if ( !is_mul_ok(v17, 2u) )
        v18 = -1;
      v19 = (const struct std::nothrow_t *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
      v20 = v19;
      if ( !v19 )
      {
        v14 = -2147024882;
        v40 = 0;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x929,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
          (const char *)0x8007000ELL,
          (int)v26);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v40);
        goto LABEL_35;
      }
      memset_0(v19, 0, v18);
      v21 = v20;
      if ( v17 )
      {
        v22 = 0;
        do
        {
          ++v22;
          *(_WORD *)v20 = *v8;
          v20 = (const struct std::nothrow_t *)((char *)v20 + 2);
          ++v8;
        }
        while ( v22 < v17 );
      }
      v23 = *a4;
      v40 = 0;
      *a4 = v21;
      if ( v23 )
        operator delete(v23, v21);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v40);
    }
  }
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v29);
  v24 = *((_QWORD *)&v28 + 1);
  *((_QWORD *)&v28 + 1) = 0;
  if ( v24 )
    SRCache_Free();
  return 0;
}

```

## disassembly

```asm
0x18001b894  mov     [rsp-8+arg_0], rbx
0x18001b899  mov     [rsp-8+arg_10], rsi
0x18001b89e  push    rbp
0x18001b89f  push    rdi
0x18001b8a0  push    r12
0x18001b8a2  push    r14
0x18001b8a4  push    r15
0x18001b8a6  lea     rbp, [rsp-37h]
0x18001b8ab  sub     rsp, 0C0h
0x18001b8b2  mov     r14, rcx
0x18001b8b5  mov     r15, r9
0x18001b8b8  mov     rcx, r9
0x18001b8bb  mov     rsi, r8
0x18001b8be  mov     rdi, rdx
0x18001b8c1  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18001b8c6  xor     r12d, r12d
0x18001b8c9  xorps   xmm0, xmm0
0x18001b8cc  xorps   xmm1, xmm1
0x18001b8cf  mov     ebx, r12d
0x18001b8d2  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x18001b8d7  movdqu  [rbp+57h+var_A0], xmm1
0x18001b8dc  test    rdi, rdi
0x18001b8df  jz      short loc_18001B94C
0x18001b8e1  lea     rax, [rbp+57h+arg_8]
0x18001b8e5  mov     byte ptr [rbp+57h+arg_8], r12b
0x18001b8e9  mov     [rsp+0E0h+var_B8], rax
0x18001b8ee  mov     r8, rsi
0x18001b8f1  lea     rax, [rbp+57h+var_B0]
0x18001b8f5  mov     rdx, rdi
0x18001b8f8  mov     rcx, r14
0x18001b8fb  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001b900  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18001b905  mov     edi, eax
0x18001b907  test    eax, eax
0x18001b909  jns     short loc_18001B93D
0x18001b90b  mov     edx, 8F9h; void *
0x18001b910  mov     rcx, [rbp+5Fh]; this
0x18001b914  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b91b  mov     r9d, edi; char *
0x18001b91e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b923  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x18001b927  mov     qword ptr [rbp+57h+var_A0+8], r12
0x18001b92b  test    rcx, rcx
0x18001b92e  jz      short loc_18001B936
0x18001b930  call    cs:__imp_SRCache_Free
0x18001b936  mov     eax, edi
0x18001b938  jmp     loc_18001BB24
0x18001b93d  cmp     byte ptr [rbp+57h+arg_8], r12b
0x18001b941  jz      short loc_18001B94C
0x18001b943  mov     rbx, qword ptr [rbp+57h+var_A0+8]
0x18001b947  test    rbx, rbx
0x18001b94a  jnz     short loc_18001B985
0x18001b94c  lea     rax, [rbp+57h+arg_8]
0x18001b950  mov     byte ptr [rbp+57h+arg_8], r12b
0x18001b954  mov     [rsp+0E0h+var_B8], rax
0x18001b959  mov     r8, rsi
0x18001b95c  lea     rax, [rbp+57h+var_B0]
0x18001b960  xor     edx, edx
0x18001b962  mov     rcx, r14
0x18001b965  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001b96a  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18001b96f  mov     edi, eax
0x18001b971  test    eax, eax
0x18001b973  jns     short loc_18001B97C
0x18001b975  mov     edx, 906h
0x18001b97a  jmp     short loc_18001B910
0x18001b97c  cmp     byte ptr [rbp+57h+arg_8], r12b
0x18001b980  cmovnz  rbx, qword ptr [rbp+57h+var_A0+8]
0x18001b985  mov     [rbp+57h+var_80], r12
0x18001b989  xorps   xmm0, xmm0
0x18001b98c  movdqa  [rbp+57h+var_90], xmm0
0x18001b991  xorps   xmm1, xmm1
0x18001b994  movdqa  [rbp+57h+var_50], xmm0
0x18001b999  mov     [rbp+57h+var_68], r12
0x18001b99d  mov     [rbp+57h+var_60], r12
0x18001b9a1  mov     [rbp+57h+var_58], r12
0x18001b9a5  mov     [rbp+57h+var_40], r12d
0x18001b9a9  mov     [rbp+57h+var_38], r12
0x18001b9ad  mov     [rbp+57h+var_30], r12
0x18001b9b1  movups  [rbp+57h+var_78], xmm1
0x18001b9b5  test    rbx, rbx
0x18001b9b8  jnz     short loc_18001BA1F
0x18001b9ba  lea     rax, [rbp+57h+arg_8]
0x18001b9be  mov     byte ptr [rbp+57h+arg_8], r12b
0x18001b9c2  lea     r9, [rbp+57h+var_90]
0x18001b9c6  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001b9cb  mov     r8d, 300h
0x18001b9d1  mov     rdx, rsi
0x18001b9d4  mov     rcx, r14
0x18001b9d7  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18001b9dc  mov     ebx, eax
0x18001b9de  test    eax, eax
0x18001b9e0  jns     short loc_18001B9FF
0x18001b9e2  mov     rcx, [rbp+5Fh]; this
0x18001b9e6  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b9ed  mov     r9d, eax; char *
0x18001b9f0  mov     edx, 914h; void *
0x18001b9f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b9fa  jmp     loc_18001BB06
0x18001b9ff  cmp     byte ptr [rbp+57h+arg_8], r12b
0x18001ba03  jz      loc_18001BABC
0x18001ba09  mov     rbx, qword ptr [rbp+57h+var_50]
0x18001ba0d  test    rbx, rbx
0x18001ba10  jnz     short loc_18001BA1F
0x18001ba12  mov     rbx, [rbp+57h+var_58]
0x18001ba16  test    rbx, rbx
0x18001ba19  jz      loc_18001BABC
0x18001ba1f  mov     rdi, r12
0x18001ba22  mov     rax, rbx
0x18001ba25  cmp     [rbx], r12w
0x18001ba29  jz      short loc_18001BA41
0x18001ba2b  cmp     rdi, 7FFFFFFFh
0x18001ba32  jnb     short loc_18001BA41
0x18001ba34  add     rax, 2
0x18001ba38  inc     rdi
0x18001ba3b  cmp     [rax], r12w
0x18001ba3f  jnz     short loc_18001BA2B
0x18001ba41  inc     rdi
0x18001ba44  mov     eax, 2
0x18001ba49  mul     rdi
0x18001ba4c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ba53  mov     r14, rax
0x18001ba56  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001ba5d  cmovb   r14, rax
0x18001ba61  mov     rcx, r14; unsigned __int64
0x18001ba64  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ba69  mov     rsi, rax
0x18001ba6c  test    rax, rax
0x18001ba6f  jz      short loc_18001BADC
0x18001ba71  mov     r8, r14; Size
0x18001ba74  xor     edx, edx; Val
0x18001ba76  mov     rcx, rax; void *
0x18001ba79  call    memset_0
0x18001ba7e  mov     rdx, rsi; struct std::nothrow_t *
0x18001ba81  test    rdi, rdi
0x18001ba84  jz      short loc_18001BA9F
0x18001ba86  mov     rcx, r12
0x18001ba89  movzx   eax, word ptr [rbx]
0x18001ba8c  inc     rcx
0x18001ba8f  mov     [rsi], ax
0x18001ba92  lea     rsi, [rsi+2]
0x18001ba96  lea     rbx, [rbx+2]
0x18001ba9a  cmp     rcx, rdi
0x18001ba9d  jb      short loc_18001BA89
0x18001ba9f  mov     rcx, [r15]; void *
0x18001baa2  mov     [rbp+57h+arg_8], r12
0x18001baa6  mov     [r15], rdx
0x18001baa9  test    rcx, rcx
0x18001baac  jz      short loc_18001BAB3
0x18001baae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bab3  lea     rcx, [rbp+57h+arg_8]
0x18001bab7  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18001babc  lea     rcx, [rbp+57h+var_90]; this
0x18001bac0  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18001bac5  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x18001bac9  mov     qword ptr [rbp+57h+var_A0+8], r12
0x18001bacd  test    rcx, rcx
0x18001bad0  jz      short loc_18001BAD8
0x18001bad2  call    cs:__imp_SRCache_Free
0x18001bad8  xor     eax, eax
0x18001bada  jmp     short loc_18001BB24
0x18001badc  mov     rcx, [rbp+5Fh]; this
0x18001bae0  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bae7  mov     ebx, 8007000Eh
0x18001baec  mov     [rbp+57h+arg_8], r12
0x18001baf0  mov     r9d, ebx; char *
0x18001baf3  mov     edx, 929h; void *
0x18001baf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bafd  lea     rcx, [rbp+57h+arg_8]
0x18001bb01  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18001bb06  lea     rcx, [rbp+57h+var_90]; this
0x18001bb0a  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18001bb0f  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x18001bb13  mov     qword ptr [rbp+57h+var_A0+8], r12
0x18001bb17  test    rcx, rcx
0x18001bb1a  jz      short loc_18001BB22
0x18001bb1c  call    cs:__imp_SRCache_Free
0x18001bb22  mov     eax, ebx
0x18001bb24  lea     r11, [rsp+0E0h+var_20]
0x18001bb2c  mov     rbx, [r11+30h]
0x18001bb30  mov     rsi, [r11+40h]
0x18001bb34  mov     rsp, r11
0x18001bb37  pop     r15
0x18001bb39  pop     r14
0x18001bb3b  pop     r12
0x18001bb3d  pop     rdi
0x18001bb3e  pop     rbp
0x18001bb3f  retn
```
