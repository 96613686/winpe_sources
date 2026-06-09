# DBLockManager::_ClaimLocks(CallerId const &,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *,DB_LOCK_TYPE const *,int *)

- ea: `0x180004fc0`
- end: `0x1800053de`
- name: `?_ClaimLocks@DBLockManager@@AEAAJAEBUCallerId@@KPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@PEBW4DB_LOCK_TYPE@@PEAH@Z`
- size: `1054`
- prototype: `int(DBLockManager *__hidden this, const struct CallerId *, unsigned int, const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *, const enum DB_LOCK_TYPE *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180027e7c`

## callees

- `0x180004910`
- `0x180004fc0`
- `0x1800053e4`
- `0x180005490`
- `0x1800054fc`
- `0x180005538`
- `0x18006f180`
- `0x1800729e0`
- `0x1800738f4`
- `0x1800ab2f4`
- `0x1800ab314`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005198`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005198`

## string_xrefs

- `0x180004ffc`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x1800050dd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x18000512e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x1800051c6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180005212`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180005237`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180005255`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180005359`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x1800053bd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180005281`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBLockManager.h`

## pseudocode

```c
__int64 __fastcall DBLockManager::_ClaimLocks(
        DBLockManager *this,
        const struct CallerId *a2,
        unsigned int a3,
        const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *a4,
        const enum DB_LOCK_TYPE *a5,
        int *a6)
{
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // edi
  unsigned int v13; // edx
  unsigned int v14; // ebx
  unsigned int i; // eax
  int v16; // r8d
  int v17; // eax
  _QWORD *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  int v21; // edi
  __int64 v22; // rbx
  int v23; // eax
  __int64 v24; // rcx
  bool v25; // zf
  int v26; // edi
  _DWORD *v28; // rbx
  int v29; // edi
  int v30; // eax
  int v31; // r8d
  unsigned int v32; // edi
  int v33; // r8d
  int v34; // r8d
  int v35; // r8d
  int v36; // [rsp+20h] [rbp-89h]
  int v37; // [rsp+20h] [rbp-89h]
  unsigned int v38; // [rsp+30h] [rbp-79h] BYREF
  int v39; // [rsp+34h] [rbp-75h] BYREF
  const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 **v40; // [rsp+38h] [rbp-71h]
  unsigned int *v41; // [rsp+40h] [rbp-69h]
  struct CallerId *v42; // [rsp+48h] [rbp-61h]
  DBLockManager *v43; // [rsp+50h] [rbp-59h]
  _QWORD v44[3]; // [rsp+58h] [rbp-51h] BYREF
  char v45; // [rsp+70h] [rbp-39h]
  _QWORD v46[4]; // [rsp+78h] [rbp-31h] BYREF
  char v47; // [rsp+98h] [rbp-11h]
  _BYTE v48[80]; // [rsp+A0h] [rbp-9h] BYREF
  unsigned int v49; // [rsp+100h] [rbp+57h] BYREF
  unsigned int v50; // [rsp+110h] [rbp+67h] BYREF
  const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *v51; // [rsp+118h] [rbp+6Fh] BYREF

  v51 = a4;
  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() )
    Log_AssertionEvent(
      v9,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
      863);
  v50 = 0;
  v10 = lambda_be838d8187f3b643c2cf9eb4129acdbb_::_lambda_be838d8187f3b643c2cf9eb4129acdbb_(
          (unsigned int)v44,
          (_DWORD)this,
          (_DWORD)a2,
          (unsigned int)&v50,
          (__int64)&v51);
  v47 = 1;
  v43 = *(DBLockManager **)v10;
  v46[0] = v43;
  v42 = *(struct CallerId **)(v10 + 8);
  v46[1] = v42;
  v11 = *(_QWORD *)(v10 + 16);
  v40 = *(const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 ***)(v10 + 24);
  v46[3] = v40;
  v41 = (unsigned int *)v11;
  v46[2] = v11;
  *a6 = 0;
  while ( 1 )
  {
    if ( v50 >= a3 )
      return 0;
    v12 = *((_DWORD *)this + 14);
    v13 = 0;
    v14 = 0;
    v38 = v12;
    v49 = 0;
    for ( i = v12; v13 < i; v14 = v13 )
    {
      if ( v14 >= i )
      {
        Log_AssertionEvent(
          v11,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
          408);
        v13 = v49;
        v12 = v38;
      }
      v11 = 56LL * v14;
      v16 = *(_DWORD *)(v11 + *((_QWORD *)this + 8));
      if ( v16 == 0x7FFFFFFF && v12 > v13 )
      {
        v12 = v13;
        v38 = v13;
      }
      else
      {
        v11 = v50;
        if ( *((_DWORD *)v51 + v50) == v16 )
          break;
      }
      i = *((_DWORD *)this + 14);
      v49 = ++v13;
    }
    v17 = *((_DWORD *)this + 14);
    if ( v13 == v17 )
      break;
LABEL_12:
    if ( v13 >= *((_DWORD *)this + 14) )
      Log_AssertionEvent(
        v11,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        908);
    v18 = (_QWORD *)lambda_938c91bc997241d0964ac66360921d1a_::_lambda_938c91bc997241d0964ac66360921d1a_(
                      v48,
                      &v49,
                      &v38,
                      this);
    v19 = v49;
    v45 = 1;
    v39 = 0;
    v44[0] = *v18;
    v20 = v18[1];
    v44[2] = v18[2];
    v44[1] = v20;
    if ( v49 >= *((_DWORD *)this + 14) )
      Log_AssertionEvent(
        v20,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        408);
    v21 = *((_DWORD *)a5 + v50);
    v22 = *((_QWORD *)this + 8) + 56 * v19;
    v23 = *(_DWORD *)(v22 + 4);
    if ( v23 )
    {
      if ( v23 == 1 )
      {
        if ( *(_DWORD *)a2 != *(_DWORD *)(v22 + 8) || *((_DWORD *)a2 + 1) != *(_DWORD *)(v22 + 12) )
        {
LABEL_45:
          Log_AssertionEvent(
            a5,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
            135);
          v32 = -2147418113;
          Log_UnistoreHREvent(-2147418113, 0, v35, 136, v36);
          goto LABEL_40;
        }
      }
      else if ( v23 != 2 || v21 )
      {
        goto LABEL_45;
      }
    }
    LockItem::_Validate((LockItem *)v22);
    if ( v21 == 1 )
    {
      if ( *(_DWORD *)(v22 + 4)
        && (*(_DWORD *)(v22 + 8) != *(_DWORD *)a2 || *(_DWORD *)(v22 + 12) != *((_DWORD *)a2 + 1)) )
      {
        Log_AssertionEvent(
          v24,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
          173);
      }
      v25 = ++*(_DWORD *)(v22 + 16) == 1;
      *(_QWORD *)(v22 + 8) = *(_QWORD *)a2;
      v26 = v25;
      *(_DWORD *)(v22 + 4) = 1;
    }
    else
    {
      v30 = LockItem::_AcquireLockShared((LockItem *)v22, a2, &v39);
      v32 = v30;
      if ( v30 < 0 )
      {
        Log_UnistoreHREvent(v30, 1, v31, 147, v36);
        LockItem::_Validate((LockItem *)v22);
LABEL_40:
        Log_UnistoreHREvent(v32, 1, v33, 918, v37);
        tlx::_UndoSolo__lambda_e140124145cc36afeff9d8ca68b1b919___::__UndoSolo__lambda_e140124145cc36afeff9d8ca68b1b919___(v44);
        tlx::_UndoSolo__lambda_55ec74b2a1a5e913bb6a0ee9940f9588___::__UndoSolo__lambda_55ec74b2a1a5e913bb6a0ee9940f9588___(v46);
        return v32;
      }
      v26 = v39;
    }
    if ( !*(_DWORD *)(v22 + 4) )
      Log_AssertionEvent(
        v24,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        150);
    if ( v26 )
      *(_QWORD *)(v22 + 48) = GetTickCount64();
    LockItem::_Validate((LockItem *)v22);
    if ( v26 )
      *a6 = 1;
    ++v50;
  }
  if ( v12 != v17 )
  {
LABEL_31:
    if ( v12 >= *((_DWORD *)this + 14) )
    {
      Log_AssertionEvent(
        v11,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        901);
      v12 = v38;
    }
    v49 = v12;
    if ( v12 >= *((_DWORD *)this + 14) )
      Log_AssertionEvent(
        v11,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        408);
    v11 = v50;
    v28 = (_DWORD *)(*((_QWORD *)this + 8) + 56LL * v12);
    v29 = *((_DWORD *)v51 + v50);
    if ( v28[1] )
      Log_AssertionEvent(
        v50,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBLockManager.h",
        34);
    *v28 = v29;
    v13 = v49;
    goto LABEL_12;
  }
  if ( (unsigned int)LockEntries::IncreaseSize((DBLockManager *)((char *)this + 56), v17 + 10) )
  {
    v12 = v38;
    goto LABEL_31;
  }
  Log_UnistoreHREvent(-2147024882, 0, v34, 898, v36);
  DBLockManager::_ReleaseLocksWithoutLock(v43, v42, *v41, *v40, 0);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004fc0  mov     [rsp-8+arg_8], rbx
0x180004fc5  mov     [rsp-8+arg_18], r9
0x180004fca  push    rbp
0x180004fcb  push    rsi
0x180004fcc  push    rdi
0x180004fcd  push    r12
0x180004fcf  push    r13
0x180004fd1  push    r14
0x180004fd3  push    r15
0x180004fd5  lea     rbp, [rsp-17h]
0x180004fda  sub     rsp, 0C0h
0x180004fe1  mov     r15d, r8d
0x180004fe4  mov     r12, rdx
0x180004fe7  mov     r13, rcx
0x180004fea  call    cs:__imp_GetCurrentThreadId
0x180004ff0  cmp     [r13+18h], eax
0x180004ff4  jz      short loc_180005008
0x180004ff6  mov     r8d, 35Fh
0x180004ffc  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005003  call    Log_AssertionEvent
0x180005008  lea     rax, [rbp+47h+arg_18]
0x18000500c  mov     [rbp+47h+arg_10], 0
0x180005013  lea     r9, [rbp+47h+arg_10]
0x180005017  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18000501c  mov     r8, r12
0x18000501f  lea     rcx, [rbp+47h+var_98]
0x180005023  mov     rdx, r13
0x180005026  call    _lambda_be838d8187f3b643c2cf9eb4129acdbb____lambda_be838d8187f3b643c2cf9eb4129acdbb_
0x18000502b  mov     [rbp+47h+var_58], 1
0x18000502f  mov     rcx, [rax]
0x180005032  mov     [rbp+47h+var_A0], rcx
0x180005036  mov     [rbp+47h+var_78], rcx
0x18000503a  mov     rcx, [rax+8]
0x18000503e  mov     [rbp+47h+var_A8], rcx
0x180005042  mov     [rbp+47h+var_70], rcx
0x180005046  mov     rcx, [rax+10h]
0x18000504a  mov     rax, [rax+18h]
0x18000504e  mov     [rbp+47h+var_B8], rax
0x180005052  mov     [rbp+47h+var_60], rax
0x180005056  mov     rax, [rbp+47h+arg_28]
0x18000505a  mov     [rbp+47h+var_B0], rcx
0x18000505e  mov     [rbp+47h+var_68], rcx
0x180005062  mov     dword ptr [rax], 0
0x180005068  cmp     [rbp+47h+arg_10], r15d
0x18000506c  jnb     loc_1800051EF
0x180005072  mov     edi, [r13+38h]
0x180005076  xor     edx, edx
0x180005078  xor     ebx, ebx
0x18000507a  mov     [rbp+47h+var_C0], edi
0x18000507d  mov     [rbp+47h+arg_0], edx
0x180005080  mov     eax, edi
0x180005082  test    edi, edi
0x180005084  jz      short loc_1800050C5
0x180005086  cmp     ebx, eax
0x180005088  jnb     loc_1800051C0
0x18000508e  mov     eax, ebx
0x180005090  imul    rcx, rax, 38h ; '8'
0x180005094  mov     rax, [r13+40h]
0x180005098  mov     r8d, [rcx+rax]
0x18000509c  cmp     r8d, 7FFFFFFFh
0x1800050a3  jz      loc_1800051DD
0x1800050a9  mov     ecx, [rbp+47h+arg_10]
0x1800050ac  mov     rax, [rbp+47h+arg_18]
0x1800050b0  cmp     [rax+rcx*4], r8d
0x1800050b4  jz      short loc_1800050C5
0x1800050b6  mov     eax, [r13+38h]
0x1800050ba  inc     edx
0x1800050bc  mov     [rbp+47h+arg_0], edx
0x1800050bf  mov     ebx, edx
0x1800050c1  cmp     edx, eax
0x1800050c3  jb      short loc_180005086
0x1800050c5  mov     eax, [r13+38h]
0x1800050c9  cmp     edx, eax
0x1800050cb  jz      loc_180005223
0x1800050d1  cmp     edx, [r13+38h]
0x1800050d5  jb      short loc_1800050E9
0x1800050d7  mov     r8d, 38Ch
0x1800050dd  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800050e4  call    Log_AssertionEvent
0x1800050e9  mov     r9, r13
0x1800050ec  lea     r8, [rbp+47h+var_C0]
0x1800050f0  lea     rdx, [rbp+47h+arg_0]
0x1800050f4  lea     rcx, [rbp+47h+var_50]
0x1800050f8  call    _lambda_938c91bc997241d0964ac66360921d1a____lambda_938c91bc997241d0964ac66360921d1a_
0x1800050fd  mov     ebx, [rbp+47h+arg_0]
0x180005100  mov     [rbp+47h+var_80], 1
0x180005104  mov     [rbp+47h+var_BC], 0
0x18000510b  mov     rcx, [rax]
0x18000510e  mov     [rbp+47h+var_98], rcx
0x180005112  mov     rcx, [rax+8]
0x180005116  mov     rax, [rax+10h]
0x18000511a  mov     [rbp+47h+var_88], rax
0x18000511e  mov     [rbp+47h+var_90], rcx
0x180005122  cmp     ebx, [r13+38h]
0x180005126  jb      short loc_18000513A
0x180005128  mov     r8d, 198h
0x18000512e  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005135  call    Log_AssertionEvent
0x18000513a  mov     eax, [rbp+47h+arg_10]
0x18000513d  mov     rcx, [rbp+47h+arg_20]
0x180005141  imul    rbx, 38h ; '8'
0x180005145  mov     edi, [rcx+rax*4]
0x180005148  add     rbx, [r13+40h]
0x18000514c  mov     eax, [rbx+4]
0x18000514f  test    eax, eax
0x180005151  jnz     loc_180005349
0x180005157  mov     rcx, rbx; this
0x18000515a  call    ?_Validate@LockItem@@AEBAXXZ; LockItem::_Validate(void)
0x18000515f  cmp     edi, 1
0x180005162  jnz     loc_180005297
0x180005168  cmp     dword ptr [rbx+4], 0
0x18000516c  jnz     loc_1800053A0
0x180005172  inc     dword ptr [rbx+10h]
0x180005175  xor     edi, edi
0x180005177  mov     rax, [r12]
0x18000517b  cmp     dword ptr [rbx+10h], 1
0x18000517f  mov     [rbx+8], rax
0x180005183  setz    dil
0x180005187  mov     dword ptr [rbx+4], 1
0x18000518e  cmp     dword ptr [rbx+4], 0
0x180005192  jz      short loc_18000520C
0x180005194  test    edi, edi
0x180005196  jz      short loc_1800051A2
0x180005198  call    cs:__imp_GetTickCount64
0x18000519e  mov     [rbx+30h], rax
0x1800051a2  mov     rcx, rbx; this
0x1800051a5  call    ?_Validate@LockItem@@AEBAXXZ; LockItem::_Validate(void)
0x1800051aa  test    edi, edi
0x1800051ac  jz      short loc_1800051B8
0x1800051ae  mov     rax, [rbp+47h+arg_28]
0x1800051b2  mov     dword ptr [rax], 1
0x1800051b8  inc     [rbp+47h+arg_10]
0x1800051bb  jmp     loc_180005068
0x1800051c0  mov     r8d, 198h
0x1800051c6  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800051cd  call    Log_AssertionEvent
0x1800051d2  mov     edx, [rbp+47h+arg_0]
0x1800051d5  mov     edi, [rbp+47h+var_C0]
0x1800051d8  jmp     loc_18000508E
0x1800051dd  cmp     edi, edx
0x1800051df  jbe     loc_1800050A9
0x1800051e5  mov     edi, edx
0x1800051e7  mov     [rbp+47h+var_C0], edx
0x1800051ea  jmp     loc_1800050B6
0x1800051ef  xor     eax, eax
0x1800051f1  mov     rbx, [rsp+0F0h+arg_8]
0x1800051f9  add     rsp, 0C0h
0x180005200  pop     r15
0x180005202  pop     r14
0x180005204  pop     r13
0x180005206  pop     r12
0x180005208  pop     rdi
0x180005209  pop     rsi
0x18000520a  pop     rbp
0x18000520b  retn
0x18000520c  mov     r8d, 96h
0x180005212  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005219  call    Log_AssertionEvent
0x18000521e  jmp     loc_180005194
0x180005223  cmp     edi, eax
0x180005225  jz      loc_1800052F5
0x18000522b  cmp     edi, [r13+38h]
0x18000522f  jb      short loc_180005246
0x180005231  mov     r8d, 385h
0x180005237  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000523e  call    Log_AssertionEvent
0x180005243  mov     edi, [rbp+47h+var_C0]
0x180005246  mov     [rbp+47h+arg_0], edi
0x180005249  cmp     edi, [r13+38h]
0x18000524d  jb      short loc_180005261
0x18000524f  mov     r8d, 198h
0x180005255  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000525c  call    Log_AssertionEvent
0x180005261  mov     ecx, [rbp+47h+arg_10]
0x180005264  mov     eax, edi
0x180005266  imul    rbx, rax, 38h ; '8'
0x18000526a  mov     rax, [rbp+47h+arg_18]
0x18000526e  add     rbx, [r13+40h]
0x180005272  mov     edi, [rax+rcx*4]
0x180005275  cmp     dword ptr [rbx+4], 0
0x180005279  jz      short loc_18000528D
0x18000527b  mov     r8d, 22h ; '"'
0x180005281  lea     rdx, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005288  call    Log_AssertionEvent
0x18000528d  mov     [rbx], edi
0x18000528f  mov     edx, [rbp+47h+arg_0]
0x180005292  jmp     loc_1800050D1
0x180005297  lea     r8, [rbp+47h+var_BC]; int *
0x18000529b  mov     rdx, r12; struct CallerId *
0x18000529e  mov     rcx, rbx; this
0x1800052a1  call    ?_AcquireLockShared@LockItem@@AEAAJAEBUCallerId@@PEAH@Z; LockItem::_AcquireLockShared(CallerId const &,int *)
0x1800052a6  mov     edi, eax
0x1800052a8  test    eax, eax
0x1800052aa  jns     loc_1800053D6
0x1800052b0  mov     edx, 1
0x1800052b5  mov     r9d, 93h
0x1800052bb  mov     ecx, eax
0x1800052bd  call    Log_UnistoreHREvent
0x1800052c2  mov     rcx, rbx; this
0x1800052c5  call    ?_Validate@LockItem@@AEBAXXZ; LockItem::_Validate(void)
0x1800052ca  mov     edx, 1
0x1800052cf  mov     r9d, 396h
0x1800052d5  mov     ecx, edi
0x1800052d7  call    Log_UnistoreHREvent
0x1800052dc  lea     rcx, [rbp+47h+var_98]
0x1800052e0  call    tlx___UndoSolo__lambda_e140124145cc36afeff9d8ca68b1b919_______UndoSolo__lambda_e140124145cc36afeff9d8ca68b1b919___
0x1800052e5  lea     rcx, [rbp+47h+var_78]
0x1800052e9  call    tlx___UndoSolo__lambda_55ec74b2a1a5e913bb6a0ee9940f9588_______UndoSolo__lambda_55ec74b2a1a5e913bb6a0ee9940f9588___
0x1800052ee  mov     eax, edi
0x1800052f0  jmp     loc_1800051F1
0x1800052f5  lea     edx, [rax+0Ah]; unsigned int
0x1800052f8  lea     rcx, [r13+38h]; this
0x1800052fc  call    ?IncreaseSize@LockEntries@@QEAAHK@Z; LockEntries::IncreaseSize(ulong)
0x180005301  test    eax, eax
0x180005303  jnz     loc_1800053CE
0x180005309  xor     edx, edx
0x18000530b  mov     ecx, 8007000Eh
0x180005310  mov     r9d, 382h
0x180005316  call    Log_UnistoreHREvent
0x18000531b  mov     r8, [rbp+47h+var_B0]
0x18000531f  mov     r9, [rbp+47h+var_B8]
0x180005323  mov     rdx, [rbp+47h+var_A8]; struct CallerId *
0x180005327  mov     rcx, [rbp+47h+var_A0]; this
0x18000532b  mov     r8d, [r8]; unsigned int
0x18000532e  mov     r9, [r9]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x180005331  mov     qword ptr [rsp+0F0h+var_D0], 0; int *
0x18000533a  call    ?_ReleaseLocksWithoutLock@DBLockManager@@AEAAXAEBUCallerId@@KPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@PEAH@Z; DBLockManager::_ReleaseLocksWithoutLock(CallerId const &,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *,int *)
0x18000533f  mov     eax, 8007000Eh
0x180005344  jmp     loc_1800051F1
0x180005349  cmp     eax, 1
0x18000534c  jz      short loc_18000537E
0x18000534e  cmp     eax, 2
0x180005351  jz      short loc_180005396
0x180005353  mov     r8d, 87h
0x180005359  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005360  call    Log_AssertionEvent
0x180005365  mov     edi, 8000FFFFh
0x18000536a  xor     edx, edx
0x18000536c  mov     ecx, edi
0x18000536e  mov     r9d, 88h
0x180005374  call    Log_UnistoreHREvent
0x180005379  jmp     loc_1800052CA
0x18000537e  mov     eax, [rbx+8]
0x180005381  cmp     [r12], eax
0x180005385  jnz     short loc_180005353
0x180005387  mov     eax, [rbx+0Ch]
0x18000538a  cmp     [r12+4], eax
0x18000538f  jnz     short loc_180005353
0x180005391  jmp     loc_180005157
0x180005396  test    edi, edi
0x180005398  jz      loc_180005157
0x18000539e  jmp     short loc_180005353
0x1800053a0  mov     eax, [r12]
0x1800053a4  cmp     [rbx+8], eax
0x1800053a7  jnz     short loc_1800053B7
0x1800053a9  mov     eax, [r12+4]
0x1800053ae  cmp     [rbx+0Ch], eax
0x1800053b1  jz      loc_180005172
0x1800053b7  mov     r8d, 0ADh
0x1800053bd  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800053c4  call    Log_AssertionEvent
0x1800053c9  jmp     loc_180005172
0x1800053ce  mov     edi, [rbp+47h+var_C0]
0x1800053d1  jmp     loc_18000522B
0x1800053d6  mov     edi, [rbp+47h+var_BC]
0x1800053d9  jmp     loc_18000518E
```
