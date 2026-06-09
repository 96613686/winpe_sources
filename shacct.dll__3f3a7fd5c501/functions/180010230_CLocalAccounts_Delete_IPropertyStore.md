# CLocalAccounts::Delete(IPropertyStore *)

- ea: `0x180010230`
- end: `0x180010664`
- name: `?Delete@CLocalAccounts@@UEAAJPEAUIPropertyStore@@@Z`
- size: `1076`
- prototype: `__int64 __fastcall(CLocalAccounts *__hidden this, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003660`
- `0x1800037e0`
- `0x180009190`
- `0x18000b9e0`
- `0x18000cb84`
- `0x180010230`
- `0x1800119fc`
- `0x180012f18`
- `0x1800131b0`
- `0x180013534`
- `0x180017010`

## import_xrefs

- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180010295`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x180010295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001034a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001054d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001034a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001054d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001064d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001064d`
- `SAMLIB!SamCloseHandle` at `0x180010402`
- `SAMLIB!SamCloseHandle` at `0x18001040c`
- `SAMLIB!SamCloseHandle` at `0x1800105f3`
- `SAMLIB!SamCloseHandle` at `0x1800105fd`
- `SAMLIB!SamCloseHandle` at `0x180010402`
- `SAMLIB!SamCloseHandle` at `0x18001040c`
- `SAMLIB!SamCloseHandle` at `0x1800105f3`
- `SAMLIB!SamCloseHandle` at `0x1800105fd`
- `SAMLIB!SamLookupIdsInDomain` at `0x180010310`
- `SAMLIB!SamLookupIdsInDomain` at `0x180010513`
- `SAMLIB!SamLookupIdsInDomain` at `0x180010310`
- `SAMLIB!SamLookupIdsInDomain` at `0x180010513`
- `SAMLIB!SamFreeMemory` at `0x1800103ab`
- `SAMLIB!SamFreeMemory` at `0x1800103b5`
- `SAMLIB!SamFreeMemory` at `0x18001059c`
- `SAMLIB!SamFreeMemory` at `0x1800105a6`
- `SAMLIB!SamFreeMemory` at `0x1800103ab`
- `SAMLIB!SamFreeMemory` at `0x1800103b5`
- `SAMLIB!SamFreeMemory` at `0x18001059c`
- `SAMLIB!SamFreeMemory` at `0x1800105a6`

## pseudocode

```c
__int64 __fastcall CLocalAccounts::Delete(CLocalAccounts *this, struct IPropertyStore *a2)
{
  int v3; // ebx
  struct IPropertyStoreVtbl *lpVtbl; // rax
  ULONG v5; // r12d
  unsigned __int16 *v6; // r14
  int v7; // ebx
  int v8; // ebx
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  char v12; // al
  int v13; // r8d
  int v14; // ebx
  unsigned __int64 v15; // rbx
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rdi
  void *v19; // [rsp+30h] [rbp-30h] BYREF
  void *v20; // [rsp+38h] [rbp-28h] BYREF
  void *v21; // [rsp+40h] [rbp-20h] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+58h] [rbp-8h]
  ULONG v24; // [rsp+A8h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+50h] BYREF
  const unsigned __int16 **v26; // [rsp+B8h] [rbp+58h] BYREF

  if ( a2 )
  {
    v23 = 0;
    lpVtbl = a2->lpVtbl;
    *(_OWORD *)propvarIn = 0;
    v3 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int128 *, PROPVARIANT *))lpVtbl->GetValue)(
           a2,
           &PKEY_SAM_ResidualID,
           propvarIn);
    if ( v3 >= 0 )
    {
      pv = 0;
      v5 = PropVariantToUInt32WithDefault(propvarIn, 0);
      if ( (int)CSGetAccountDomainSid(&pv) >= 0 )
      {
        v21 = 0;
        v20 = 0;
        if ( (int)SamHandleForDomain(pv, 0x20021u, 0x20385u, &v21, &v20) >= 0 )
        {
          v26 = 0;
          v19 = 0;
          v6 = 0;
          v24 = v5;
          v7 = SamLookupIdsInDomain(v20, 1, &v24, &v26, &v19);
          if ( v7 < 0 )
          {
            if ( v7 == -1073741709 )
            {
              v8 = -2147023728;
            }
            else
            {
              v8 = v7 | 0x10000000;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_dD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  67,
                  WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
                  v5,
                  v8);
              }
            }
          }
          else
          {
            if ( *(_DWORD *)v19 == 4 || *(_DWORD *)v19 == 1 )
            {
              v9 = ((unsigned __int64)*(unsigned __int16 *)v26 + 2) >> 1;
              v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9);
              v11 = v10;
              if ( v10 )
              {
                memset_0(v10, 0, 2 * v9);
                v8 = StringCchCopyNW(v11, v9, v26[1], (unsigned __int64)*(unsigned __int16 *)v26 >> 1);
                if ( v8 >= 0 )
                  v6 = v11;
                else
                  CoTaskMemFree(v11);
              }
              else
              {
                v8 = -2147024882;
              }
            }
            else
            {
              v8 = -805306230;
            }
            SamFreeMemory(v19);
            SamFreeMemory(v26);
          }
          SamCloseHandle(v20);
          SamCloseHandle(v21);
          if ( v8 >= 0 )
          {
            (*(void (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this);
            v3 = CSDeleteAccount(pv);
            if ( v3 < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = (*(__int64 (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 136LL))(this);
              WPP_SF_SdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v13, (_DWORD)v6, v12, v3);
            }
            CoTaskMemFree(pv);
            CoTaskMemFree(v6);
            goto LABEL_50;
          }
        }
        CoTaskMemFree(pv);
      }
      v3 = CSGetBuiltInDomainSid(&pv);
      if ( v3 >= 0 )
      {
        v21 = 0;
        v19 = 0;
        v3 = SamHandleForDomain(pv, 0x20021u, 0x20385u, &v21, &v19);
        if ( v3 < 0 )
          goto LABEL_46;
        v26 = 0;
        v20 = 0;
        v24 = v5;
        v14 = SamLookupIdsInDomain(v19, 1, &v24, &v26, &v20);
        if ( v14 < 0 )
        {
          if ( v14 == -1073741709 )
          {
            v3 = -2147023728;
          }
          else
          {
            v3 = v14 | 0x10000000;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_dD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
                v5,
                v3);
          }
        }
        else
        {
          if ( *(_DWORD *)v20 == 4 || *(_DWORD *)v20 == 1 )
          {
            v15 = ((unsigned __int64)*(unsigned __int16 *)v26 + 2) >> 1;
            v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15);
            v17 = v16;
            if ( v16 )
            {
              memset_0(v16, 0, 2 * v15);
              v3 = StringCchCopyNW(v17, v15, v26[1], (unsigned __int64)*(unsigned __int16 *)v26 >> 1);
              if ( v3 < 0 )
                CoTaskMemFree(v17);
            }
            else
            {
              v3 = -2147024882;
            }
          }
          else
          {
            v3 = -805306230;
          }
          SamFreeMemory(v20);
          SamFreeMemory(v26);
        }
        SamCloseHandle(v19);
        SamCloseHandle(v21);
        if ( v3 < 0 )
LABEL_46:
          CoTaskMemFree(pv);
        else
          v3 = -2147024891;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v5);
    }
LABEL_50:
    PropVariantClear(propvarIn);
    return (unsigned int)v3;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x180010230  push    rbp
0x180010232  push    rbx
0x180010233  push    rsi
0x180010234  push    rdi
0x180010235  push    r12
0x180010237  push    r13
0x180010239  push    r14
0x18001023b  mov     rbp, rsp
0x18001023e  sub     rsp, 60h
0x180010242  xor     r13d, r13d
0x180010245  mov     r9, rdx
0x180010248  mov     rsi, rcx
0x18001024b  test    rdx, rdx
0x18001024e  jnz     short loc_18001025A
0x180010250  mov     ebx, 80004003h
0x180010255  jmp     loc_180010653
0x18001025a  xor     eax, eax
0x18001025c  lea     r8, [rbp+propvarIn]
0x180010260  mov     [rbp+var_8], rax
0x180010264  xorps   xmm0, xmm0
0x180010267  mov     rax, [rdx]
0x18001026a  mov     rcx, r9
0x18001026d  lea     rdx, PKEY_SAM_ResidualID
0x180010274  movups  xmmword ptr [rbp+propvarIn], xmm0
0x180010278  mov     rax, [rax+28h]
0x18001027c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010281  mov     ebx, eax
0x180010283  test    eax, eax
0x180010285  js      loc_180010649
0x18001028b  xor     edx, edx; ulDefault
0x18001028d  mov     [rbp+pv], r13
0x180010291  lea     rcx, [rbp+propvarIn]; propvarIn
0x180010295  call    cs:__imp_PropVariantToUInt32WithDefault
0x18001029b  lea     rcx, [rbp+pv]
0x18001029f  mov     r12d, eax
0x1800102a2  call    CSGetAccountDomainSid
0x1800102a7  lea     rdi, WPP_GLOBAL_Control
0x1800102ae  test    eax, eax
0x1800102b0  js      loc_1800104A7
0x1800102b6  mov     rcx, [rbp+pv]; void *
0x1800102ba  lea     rax, [rbp+var_28]
0x1800102be  lea     r9, [rbp+var_20]; void **
0x1800102c2  mov     [rsp+60h+var_40], rax; void **
0x1800102c7  mov     edx, 20021h; unsigned int
0x1800102cc  mov     [rbp+var_20], r13
0x1800102d0  mov     r8d, 20385h; unsigned int
0x1800102d6  mov     [rbp+var_28], r13
0x1800102da  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x1800102df  test    eax, eax
0x1800102e1  js      loc_18001049D
0x1800102e7  mov     rcx, [rbp+var_28]
0x1800102eb  lea     rax, [rbp+var_30]
0x1800102ef  lea     r9, [rbp+arg_18]
0x1800102f3  mov     [rsp+60h+var_40], rax
0x1800102f8  lea     r8, [rbp+arg_8]
0x1800102fc  mov     [rbp+arg_18], r13
0x180010300  mov     edx, 1
0x180010305  mov     [rbp+var_30], r13
0x180010309  mov     r14, r13
0x18001030c  mov     [rbp+arg_8], r12d
0x180010310  call    cs:__imp_SamLookupIdsInDomain
0x180010316  mov     ebx, eax
0x180010318  test    eax, eax
0x18001031a  js      loc_1800103BD
0x180010320  mov     rax, [rbp+var_30]
0x180010324  cmp     dword ptr [rax], 4
0x180010327  jz      short loc_180010335
0x180010329  cmp     dword ptr [rax], 1
0x18001032c  jz      short loc_180010335
0x18001032e  mov     ebx, 0D000008Ah
0x180010333  jmp     short loc_1800103A7
0x180010335  mov     rax, [rbp+arg_18]
0x180010339  movzx   ebx, word ptr [rax]
0x18001033c  add     rbx, 2
0x180010340  shr     rbx, 1
0x180010343  lea     r13, [rbx+rbx]
0x180010347  mov     rcx, r13; cb
0x18001034a  call    cs:__imp_CoTaskMemAlloc
0x180010350  mov     rdi, rax
0x180010353  test    rax, rax
0x180010356  jnz     short loc_180010362
0x180010358  mov     ebx, 8007000Eh
0x18001035d  xor     r13d, r13d
0x180010360  jmp     short loc_1800103A0
0x180010362  mov     r8, r13; Size
0x180010365  xor     edx, edx; Val
0x180010367  mov     rcx, rdi; void *
0x18001036a  call    memset_0
0x18001036f  mov     r8, [rbp+arg_18]
0x180010373  mov     rdx, rbx; unsigned __int64
0x180010376  mov     rcx, rdi; unsigned __int16 *
0x180010379  movzx   r9d, word ptr [r8]
0x18001037d  mov     r8, [r8+8]; unsigned __int16 *
0x180010381  shr     r9, 1; unsigned __int64
0x180010384  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180010389  xor     r13d, r13d
0x18001038c  mov     ebx, eax
0x18001038e  test    eax, eax
0x180010390  jns     short loc_18001039D
0x180010392  mov     rcx, rdi; pv
0x180010395  call    cs:__imp_CoTaskMemFree
0x18001039b  jmp     short loc_1800103A0
0x18001039d  mov     r14, rdi
0x1800103a0  lea     rdi, WPP_GLOBAL_Control
0x1800103a7  mov     rcx, [rbp+var_30]
0x1800103ab  call    cs:__imp_SamFreeMemory
0x1800103b1  mov     rcx, [rbp+arg_18]
0x1800103b5  call    cs:__imp_SamFreeMemory
0x1800103bb  jmp     short loc_1800103FE
0x1800103bd  cmp     ebx, 0C0000073h
0x1800103c3  jnz     short loc_1800103CC
0x1800103c5  mov     ebx, 80070490h
0x1800103ca  jmp     short loc_1800103FE
0x1800103cc  bts     ebx, 1Ch
0x1800103d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103d7  cmp     rcx, rdi
0x1800103da  jz      short loc_1800103FE
0x1800103dc  test    byte ptr [rcx+1Ch], 2
0x1800103e0  jz      short loc_1800103FE
0x1800103e2  mov     rcx, [rcx+10h]
0x1800103e6  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x1800103ed  mov     edx, 43h ; 'C'
0x1800103f2  mov     dword ptr [rsp+60h+var_40], ebx
0x1800103f6  mov     r9d, r12d
0x1800103f9  call    WPP_SF_dD
0x1800103fe  mov     rcx, [rbp+var_28]
0x180010402  call    cs:__imp_SamCloseHandle
0x180010408  mov     rcx, [rbp+var_20]
0x18001040c  call    cs:__imp_SamCloseHandle
0x180010412  test    ebx, ebx
0x180010414  js      loc_18001049D
0x18001041a  mov     rax, [rsi]
0x18001041d  mov     rcx, rsi
0x180010420  mov     rax, [rax+88h]
0x180010427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001042c  mov     rcx, [rbp+pv]; void *
0x180010430  mov     r8d, eax
0x180010433  mov     rdx, r14
0x180010436  call    CSDeleteAccount
0x18001043b  mov     ebx, eax
0x18001043d  test    eax, eax
0x18001043f  jns     short loc_180010485
0x180010441  mov     rax, cs:WPP_GLOBAL_Control
0x180010448  cmp     rax, rdi
0x18001044b  jz      short loc_180010485
0x18001044d  test    byte ptr [rax+1Ch], 2
0x180010451  jz      short loc_180010485
0x180010453  mov     rax, [rsi]
0x180010456  mov     rcx, rsi
0x180010459  mov     rax, [rax+88h]
0x180010460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010465  mov     rcx, cs:WPP_GLOBAL_Control
0x18001046c  mov     edx, 0Eh
0x180010471  mov     [rsp+60h+var_38], ebx
0x180010475  mov     r9, r14
0x180010478  mov     dword ptr [rsp+60h+var_40], eax
0x18001047c  mov     rcx, [rcx+10h]
0x180010480  call    WPP_SF_SdD
0x180010485  mov     rcx, [rbp+pv]; pv
0x180010489  call    cs:__imp_CoTaskMemFree
0x18001048f  mov     rcx, r14; pv
0x180010492  call    cs:__imp_CoTaskMemFree
0x180010498  jmp     loc_180010649
0x18001049d  mov     rcx, [rbp+pv]; pv
0x1800104a1  call    cs:__imp_CoTaskMemFree
0x1800104a7  lea     rcx, [rbp+pv]
0x1800104ab  call    CSGetBuiltInDomainSid
0x1800104b0  mov     ebx, eax
0x1800104b2  test    eax, eax
0x1800104b4  js      loc_180010618
0x1800104ba  mov     rcx, [rbp+pv]; void *
0x1800104be  lea     rax, [rbp+var_30]
0x1800104c2  lea     r9, [rbp+var_20]; void **
0x1800104c6  mov     [rsp+60h+var_40], rax; void **
0x1800104cb  mov     edx, 20021h; unsigned int
0x1800104d0  mov     [rbp+var_20], r13
0x1800104d4  mov     r8d, 20385h; unsigned int
0x1800104da  mov     [rbp+var_30], r13
0x1800104de  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x1800104e3  mov     ebx, eax
0x1800104e5  test    eax, eax
0x1800104e7  js      loc_18001060E
0x1800104ed  mov     rcx, [rbp+var_30]
0x1800104f1  lea     rax, [rbp+var_28]
0x1800104f5  lea     r9, [rbp+arg_18]
0x1800104f9  mov     [rsp+60h+var_40], rax
0x1800104fe  lea     r8, [rbp+arg_8]
0x180010502  mov     [rbp+arg_18], r13
0x180010506  mov     edx, 1
0x18001050b  mov     [rbp+var_28], r13
0x18001050f  mov     [rbp+arg_8], r12d
0x180010513  call    cs:__imp_SamLookupIdsInDomain
0x180010519  mov     ebx, eax
0x18001051b  test    eax, eax
0x18001051d  js      loc_1800105AE
0x180010523  mov     rax, [rbp+var_28]
0x180010527  cmp     dword ptr [rax], 4
0x18001052a  jz      short loc_180010538
0x18001052c  cmp     dword ptr [rax], 1
0x18001052f  jz      short loc_180010538
0x180010531  mov     ebx, 0D000008Ah
0x180010536  jmp     short loc_180010598
0x180010538  mov     rax, [rbp+arg_18]
0x18001053c  movzx   ebx, word ptr [rax]
0x18001053f  add     rbx, 2
0x180010543  shr     rbx, 1
0x180010546  lea     rsi, [rbx+rbx]
0x18001054a  mov     rcx, rsi; cb
0x18001054d  call    cs:__imp_CoTaskMemAlloc
0x180010553  mov     rdi, rax
0x180010556  test    rax, rax
0x180010559  jnz     short loc_180010562
0x18001055b  mov     ebx, 8007000Eh
0x180010560  jmp     short loc_180010598
0x180010562  mov     r8, rsi; Size
0x180010565  xor     edx, edx; Val
0x180010567  mov     rcx, rdi; void *
0x18001056a  call    memset_0
0x18001056f  mov     r8, [rbp+arg_18]
0x180010573  mov     rdx, rbx; unsigned __int64
0x180010576  mov     rcx, rdi; unsigned __int16 *
0x180010579  movzx   r9d, word ptr [r8]
0x18001057d  mov     r8, [r8+8]; unsigned __int16 *
0x180010581  shr     r9, 1; unsigned __int64
0x180010584  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180010589  mov     ebx, eax
0x18001058b  test    eax, eax
0x18001058d  jns     short loc_180010598
0x18001058f  mov     rcx, rdi; pv
0x180010592  call    cs:__imp_CoTaskMemFree
0x180010598  mov     rcx, [rbp+var_28]
0x18001059c  call    cs:__imp_SamFreeMemory
0x1800105a2  mov     rcx, [rbp+arg_18]
0x1800105a6  call    cs:__imp_SamFreeMemory
0x1800105ac  jmp     short loc_1800105EF
0x1800105ae  cmp     ebx, 0C0000073h
0x1800105b4  jnz     short loc_1800105BD
0x1800105b6  mov     ebx, 80070490h
0x1800105bb  jmp     short loc_1800105EF
0x1800105bd  bts     ebx, 1Ch
0x1800105c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105c8  cmp     rcx, rdi
0x1800105cb  jz      short loc_1800105EF
0x1800105cd  test    byte ptr [rcx+1Ch], 2
0x1800105d1  jz      short loc_1800105EF
0x1800105d3  mov     rcx, [rcx+10h]
0x1800105d7  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x1800105de  mov     edx, 43h ; 'C'
0x1800105e3  mov     dword ptr [rsp+60h+var_40], ebx
0x1800105e7  mov     r9d, r12d
0x1800105ea  call    WPP_SF_dD
0x1800105ef  mov     rcx, [rbp+var_30]
0x1800105f3  call    cs:__imp_SamCloseHandle
0x1800105f9  mov     rcx, [rbp+var_20]
0x1800105fd  call    cs:__imp_SamCloseHandle
0x180010603  test    ebx, ebx
0x180010605  js      short loc_18001060E
0x180010607  mov     ebx, 80070005h
0x18001060c  jmp     short loc_180010618
0x18001060e  mov     rcx, [rbp+pv]; pv
0x180010612  call    cs:__imp_CoTaskMemFree
0x180010618  mov     rcx, cs:WPP_GLOBAL_Control
0x18001061f  lea     rax, WPP_GLOBAL_Control
0x180010626  cmp     rcx, rax
0x180010629  jz      short loc_180010649
0x18001062b  test    byte ptr [rcx+1Ch], 2
0x18001062f  jz      short loc_180010649
0x180010631  mov     rcx, [rcx+10h]
0x180010635  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18001063c  mov     edx, 0Fh
0x180010641  mov     r9d, r12d
0x180010644  call    WPP_SF_d
0x180010649  lea     rcx, [rbp+propvarIn]; pvar
0x18001064d  call    cs:__imp_PropVariantClear
0x180010653  mov     eax, ebx
0x180010655  add     rsp, 60h
0x180010659  pop     r14
0x18001065b  pop     r13
0x18001065d  pop     r12
0x18001065f  pop     rdi
0x180010660  pop     rsi
0x180010661  pop     rbx
0x180010662  pop     rbp
0x180010663  retn
```
