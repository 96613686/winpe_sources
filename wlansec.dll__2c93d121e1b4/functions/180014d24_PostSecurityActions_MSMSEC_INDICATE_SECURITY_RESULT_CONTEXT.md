# PostSecurityActions(MSMSEC_INDICATE_SECURITY_RESULT_CONTEXT *)

- ea: `0x180014d24`
- end: `0x1800152ec`
- name: `?PostSecurityActions@@YAKPEAUMSMSEC_INDICATE_SECURITY_RESULT_CONTEXT@@@Z`
- size: `1480`
- prototype: `unsigned int __fastcall(struct MSMSEC_INDICATE_SECURITY_RESULT_CONTEXT *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180015ff0`

## callees

- `0x18000764c`
- `0x18000892c`
- `0x180008998`
- `0x1800092dc`
- `0x18000a26c`
- `0x18000a824`
- `0x1800125b0`
- `0x180013600`
- `0x180013bc0`
- `0x180014998`
- `0x180014d24`
- `0x180016a08`
- `0x18002abec`
- `0x18002b3f8`
- `0x1800328b0`
- `0x180036f38`
- `0x1800558c0`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180014e45`
- `MobileNetworking!ReleaseWriteLock` at `0x180014f4e`
- `MobileNetworking!ReleaseWriteLock` at `0x180014f91`
- `MobileNetworking!ReleaseWriteLock` at `0x180014e45`
- `MobileNetworking!ReleaseWriteLock` at `0x180014f4e`
- `MobileNetworking!ReleaseWriteLock` at `0x180014f91`
- `MobileNetworking!AcquireWriteLock` at `0x180014e93`
- `MobileNetworking!AcquireWriteLock` at `0x180014e93`

## string_xrefs

- `0x180014e3b`: `PostSecurityActions`
- `0x180014e86`: `PostSecurityActions`
- `0x180014f44`: `PostSecurityActions`
- `0x180014f87`: `PostSecurityActions`
- `0x180014fc8`: `PostSecurityActions`
- `0x180014ff6`: `PostSecurityActions`

## pseudocode

```c
__int64 __fastcall PostSecurityActions(struct MSMSEC_INDICATE_SECURITY_RESULT_CONTEXT *a1)
{
  unsigned int v1; // ebx
  PVOID *v3; // rcx
  unsigned int v5; // eax
  struct MSMSEC_INTF_CONTEXT *v6; // rdi
  unsigned int v7; // eax
  int v8; // r8d
  struct MSMSEC_PORT_CONTEXT *v9; // rbp
  unsigned int v10; // eax
  int v11; // r8d
  int v12; // r12d
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r9
  PVOID *v16; // r11
  PVOID *v17; // rcx
  PVOID *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned int v21; // r10d
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // r11
  __int64 v25; // r8
  char v26; // r10
  int v27; // eax
  __int64 v28; // r11
  char v29; // r8
  struct MSMSEC_INTF_CONTEXT *v30; // [rsp+80h] [rbp+8h] BYREF
  struct MSMSEC_PORT_CONTEXT *v31; // [rsp+88h] [rbp+10h] BYREF

  v1 = 0;
  v30 = 0;
  v31 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a1 + 8) )
    goto LABEL_5;
  v5 = SecMgrValidateRefAndLockAdapter(*((void **)a1 + 6), &v30);
  v1 = v5;
  if ( !v5 )
  {
    v6 = v30;
    v7 = SecMgrValidateAndRefPort(v30, (unsigned __int8 (*)[6])((unsigned __int8 *)a1 + 4), &v31);
    v9 = v31;
    v1 = v7;
    if ( v7 )
    {
      v12 = 0;
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_34;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_31:
        if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 17) & 0x100) != 0 )
          WPP_SF_Ls((unsigned int)v17[7], 11, v8, *((_DWORD *)v6 + 624), (__int64)"<<< Unlocking <<<");
LABEL_34:
        ReleaseWriteLock(v6, (char *)v6 + 2512, "PostSecurityActions", 578);
        if ( !v12 )
          goto LABEL_40;
        goto LABEL_35;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v7);
LABEL_30:
      v17 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
      WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v8, *((_DWORD *)v6 + 624), (__int64)"<<< Unlocking <<<");
    ReleaseWriteLock(v6, (char *)v6 + 2512, "PostSecurityActions", 497);
    v10 = SecMgrLockAndCheckPortActive(v9);
    v1 = v10;
    if ( v10 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_39:
        SecMgrDerefPortEx(v9, "PostSecurityActions", 582);
LABEL_40:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
          WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v11, *((_DWORD *)v6 + 624), (__int64)"<<< Derefing <<<");
        SecMgrDerefAdapterEx(v6, "PostSecurityActions", 586);
        goto LABEL_44;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_36:
        if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 17) & 0x100) != 0 )
          WPP_SF_Ls((unsigned int)v18[7], 12, v11, *((_DWORD *)v9 + 78), (__int64)"<<< Derefing <<<");
        goto LABEL_39;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v10);
LABEL_35:
      v18 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_36;
    }
    v12 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
      WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v11, *((_DWORD *)v6 + 624), (__int64)">>> Locking >>>");
    AcquireWriteLock(v6, (char *)v6 + 2512, "PostSecurityActions", 504);
    if ( *((_DWORD *)v6 + 654) )
    {
      v1 = 303;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_26;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
        goto LABEL_25;
      }
      goto LABEL_29;
    }
    if ( *((_QWORD *)v6 + 328) == *((_QWORD *)a1 + 7) )
    {
      if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v6 + 681), 5) )
      {
        v1 = 5023;
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_26;
          v20 = IntfActionStr(5, v14, v13, v15);
          v23 = IntfSecStateStr(v21, v22, v20);
          WPP_SF_SLSL(
            *(_QWORD *)(v24 + 56),
            58,
            (unsigned int)&WPP_b56916f94f50376d7382066de30fa1b3_Traceguids,
            v23,
            v26,
            v25,
            5);
          goto LABEL_25;
        }
        goto LABEL_29;
      }
      if ( *((_QWORD *)v9 + 53) == *((_QWORD *)a1 + 8) )
      {
        LODWORD(v13) = *((_DWORD *)v9 + 110);
        if ( (_DWORD)v13 == 8 )
        {
          PreAuthActivate(
            (struct MSMSEC_INTF_CONTEXT *)((char *)v6 + 2912),
            (unsigned __int8 (*)[6])((unsigned __int8 *)a1 + 4));
          PmkCacheTrigger((struct MSMSEC_INTF_CONTEXT *)((char *)v6 + 3000));
LABEL_25:
          v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
          if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 17) & 0x100) != 0 )
            WPP_SF_Ls((unsigned int)v16[7], 12, v13, *((_DWORD *)v9 + 78), (__int64)"<<< Unlocking <<<");
          goto LABEL_29;
        }
        v1 = 5023;
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_26;
          v27 = PortSecStateStr((unsigned int)v13);
          WPP_SF_SL(*(_QWORD *)(v28 + 56), 60, (unsigned int)&WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v27, v29);
          goto LABEL_25;
        }
LABEL_29:
        ReleaseWriteLock(v9, (char *)v9 + 320, "PostSecurityActions", 574);
        goto LABEL_30;
      }
      v1 = 5023;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_29;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_26;
      v19 = 59;
    }
    else
    {
      v1 = 5023;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_29;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_26;
      v19 = 57;
    }
    WPP_SF_qq(v16[7], v19, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
    goto LABEL_25;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v5);
LABEL_44:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_5:
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x100) != 0 )
    WPP_SF_d(v3[7], 61, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180014d24  mov     rax, rsp
0x180014d27  mov     [rax+18h], rbx
0x180014d2b  push    rbp
0x180014d2c  push    rsi
0x180014d2d  push    rdi
0x180014d2e  push    r12
0x180014d30  push    r13
0x180014d32  push    r14
0x180014d34  push    r15
0x180014d36  sub     rsp, 40h
0x180014d3a  xor     ebx, ebx
0x180014d3c  mov     rsi, rcx
0x180014d3f  mov     [rax+8], rbx
0x180014d43  mov     [rax+10h], rbx
0x180014d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d4e  lea     r13, WPP_GLOBAL_Control
0x180014d55  cmp     rcx, r13
0x180014d58  jz      short loc_180014D67
0x180014d5a  test    dword ptr [rcx+44h], 100h
0x180014d61  jnz     loc_1800150AB
0x180014d67  cmp     [rsi+20h], ebx
0x180014d6a  jz      short loc_180014DBF
0x180014d6c  cmp     rcx, r13
0x180014d6f  jz      short loc_180014DA4
0x180014d71  test    dword ptr [rcx+44h], 100h
0x180014d78  jz      short loc_180014DA4
0x180014d7a  mov     rcx, [rcx+38h]
0x180014d7e  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180014d85  mov     edx, 3Dh ; '='
0x180014d8a  mov     r9d, ebx
0x180014d8d  call    WPP_SF_d
0x180014d92  jmp     short loc_180014DA4
0x180014d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d9b  cmp     rcx, r13
0x180014d9e  jnz     loc_1800150CC
0x180014da4  mov     eax, ebx
0x180014da6  mov     rbx, [rsp+78h+arg_10]
0x180014dae  add     rsp, 40h
0x180014db2  pop     r15
0x180014db4  pop     r14
0x180014db6  pop     r13
0x180014db8  pop     r12
0x180014dba  pop     rdi
0x180014dbb  pop     rsi
0x180014dbc  pop     rbp
0x180014dbd  retn
0x180014dbf  mov     rcx, [rsi+30h]; void *
0x180014dc3  lea     rdx, [rsp+78h+arg_0]; struct MSMSEC_INTF_CONTEXT **
0x180014dcb  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180014dd0  mov     ebx, eax
0x180014dd2  test    eax, eax
0x180014dd4  jnz     short loc_180014D94
0x180014dd6  mov     rdi, [rsp+78h+arg_0]
0x180014dde  lea     r8, [rsp+78h+arg_8]; struct MSMSEC_PORT_CONTEXT **
0x180014de6  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180014de9  lea     rdx, [rsi+18h]; unsigned __int8 (*)[6]
0x180014ded  call    ?SecMgrValidateAndRefPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrValidateAndRefPort(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x180014df2  mov     rbp, [rsp+78h+arg_8]
0x180014dfa  lea     r12, aDerefing; "<<< Derefing <<<"
0x180014e01  mov     ebx, eax
0x180014e03  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x180014e0a  test    ebx, ebx
0x180014e0c  jnz     loc_180015071
0x180014e12  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e19  cmp     rcx, r13
0x180014e1c  jz      short loc_180014E2B
0x180014e1e  test    dword ptr [rcx+44h], 100h
0x180014e25  jnz     loc_1800150F3
0x180014e2b  lea     r14, [rdi+9D0h]
0x180014e32  mov     r9d, 1F1h
0x180014e38  mov     rdx, r14
0x180014e3b  lea     r8, aPostsecurityac; "PostSecurityActions"
0x180014e42  mov     rcx, rdi
0x180014e45  call    cs:__imp_ReleaseWriteLock
0x180014e4c  nop     dword ptr [rax+rax+00h]
0x180014e51  mov     rcx, rbp; struct MSMSEC_PORT_CONTEXT *
0x180014e54  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x180014e59  mov     ebx, eax
0x180014e5b  test    eax, eax
0x180014e5d  jnz     loc_18001503A
0x180014e63  lea     r12d, [rax+1]
0x180014e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e6e  cmp     rcx, r13
0x180014e71  jz      short loc_180014E80
0x180014e73  test    dword ptr [rcx+44h], 100h
0x180014e7a  jnz     loc_180015112
0x180014e80  mov     r9d, 1F8h
0x180014e86  lea     r8, aPostsecurityac; "PostSecurityActions"
0x180014e8d  mov     rdx, r14
0x180014e90  mov     rcx, rdi
0x180014e93  call    cs:__imp_AcquireWriteLock
0x180014e9a  nop     dword ptr [rax+rax+00h]
0x180014e9f  cmp     dword ptr [rdi+0A38h], 0
0x180014ea6  jnz     loc_180015138
0x180014eac  mov     r9, [rsi+38h]
0x180014eb0  mov     rax, [rdi+0A40h]
0x180014eb7  cmp     rax, r9
0x180014eba  jnz     loc_180015011
0x180014ec0  mov     ecx, [rdi+0AA4h]
0x180014ec6  mov     r14d, 5
0x180014ecc  mov     edx, r14d
0x180014ecf  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180014ed4  test    eax, eax
0x180014ed6  jz      loc_180015190
0x180014edc  mov     rax, [rsi+40h]
0x180014ee0  mov     r9, [rbp+1A8h]
0x180014ee7  cmp     r9, rax
0x180014eea  jnz     loc_1800151F5
0x180014ef0  mov     r8d, [rbp+1B8h]
0x180014ef7  cmp     r8d, 8
0x180014efb  jnz     loc_180015219
0x180014f01  lea     rcx, [rdi+0B60h]; struct MSMSEC_PREAUTH_CONTEXT *
0x180014f08  lea     rdx, [rsi+18h]; unsigned __int8 (*)[6]
0x180014f0c  call    ?PreAuthActivate@@YAKPEAUMSMSEC_PREAUTH_CONTEXT@@PEAY05E@Z; PreAuthActivate(MSMSEC_PREAUTH_CONTEXT *,uchar (*)[6])
0x180014f11  lea     rcx, [rdi+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x180014f18  call    ?PmkCacheTrigger@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; PmkCacheTrigger(MSMSEC_PMKCACHE_CONTEXT *)
0x180014f1d  mov     r11, cs:WPP_GLOBAL_Control
0x180014f24  cmp     r11, r13
0x180014f27  jz      short loc_180014F37
0x180014f29  test    dword ptr [r11+44h], 100h
0x180014f31  jnz     loc_180015262
0x180014f37  lea     rdx, [rbp+140h]
0x180014f3e  mov     r9d, 23Eh
0x180014f44  lea     r8, aPostsecurityac; "PostSecurityActions"
0x180014f4b  mov     rcx, rbp
0x180014f4e  call    cs:__imp_ReleaseWriteLock
0x180014f55  nop     dword ptr [rax+rax+00h]
0x180014f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f61  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x180014f68  cmp     rcx, r13
0x180014f6b  jz      short loc_180014F7A
0x180014f6d  test    dword ptr [rcx+44h], 100h
0x180014f74  jnz     loc_180015288
0x180014f7a  lea     rdx, [rdi+9D0h]
0x180014f81  mov     r9d, 242h
0x180014f87  lea     r8, aPostsecurityac; "PostSecurityActions"
0x180014f8e  mov     rcx, rdi
0x180014f91  call    cs:__imp_ReleaseWriteLock
0x180014f98  nop     dword ptr [rax+rax+00h]
0x180014f9d  test    r12d, r12d
0x180014fa0  jz      short loc_180014FD7
0x180014fa2  lea     r12, aDerefing; "<<< Derefing <<<"
0x180014fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fb0  cmp     rcx, r13
0x180014fb3  jz      short loc_180014FC2
0x180014fb5  test    dword ptr [rcx+44h], 100h
0x180014fbc  jnz     loc_1800152A7
0x180014fc2  mov     r8d, 246h; int
0x180014fc8  lea     rdx, aPostsecurityac; "PostSecurityActions"
0x180014fcf  mov     rcx, rbp; struct MSMSEC_PORT_CONTEXT *
0x180014fd2  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180014fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fde  cmp     rcx, r13
0x180014fe1  jz      short loc_180014FF0
0x180014fe3  test    dword ptr [rcx+44h], 100h
0x180014fea  jnz     loc_1800152C6
0x180014ff0  mov     r8d, 24Ah; int
0x180014ff6  lea     rdx, aPostsecurityac; "PostSecurityActions"
0x180014ffd  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180015000  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180015005  mov     rcx, cs:WPP_GLOBAL_Control
0x18001500c  jmp     loc_180014D6C
0x180015011  mov     ebx, 139Fh
0x180015016  mov     r11, cs:WPP_GLOBAL_Control
0x18001501d  cmp     r11, r13
0x180015020  jz      loc_180014F37
0x180015026  test    [r11+44h], r12b
0x18001502a  jz      loc_180014F24
0x180015030  mov     edx, 39h ; '9'
0x180015035  jmp     loc_180015176
0x18001503a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015041  cmp     rcx, r13
0x180015044  jz      loc_180014FC2
0x18001504a  test    byte ptr [rcx+44h], 1
0x18001504e  jz      loc_180014FB0
0x180015054  mov     rcx, [rcx+38h]
0x180015058  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18001505f  mov     edx, 37h ; '7'
0x180015064  mov     r9d, eax
0x180015067  call    WPP_SF_d
0x18001506c  jmp     loc_180014FA9
0x180015071  xor     r12d, r12d
0x180015074  mov     rcx, cs:WPP_GLOBAL_Control
0x18001507b  cmp     rcx, r13
0x18001507e  jz      loc_180014F7A
0x180015084  test    byte ptr [rcx+44h], 1
0x180015088  jz      loc_180014F68
0x18001508e  mov     rcx, [rcx+38h]
0x180015092  lea     edx, [r12+36h]
0x180015097  mov     r9d, ebx
0x18001509a  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x1800150a1  call    WPP_SF_d
0x1800150a6  jmp     loc_180014F5A
0x1800150ab  mov     rcx, [rcx+38h]
0x1800150af  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x1800150b6  mov     edx, 34h ; '4'
0x1800150bb  call    WPP_SF_
0x1800150c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150c7  jmp     loc_180014D67
0x1800150cc  test    byte ptr [rcx+44h], 1
0x1800150d0  jz      loc_180014D6C
0x1800150d6  mov     rcx, [rcx+38h]
0x1800150da  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x1800150e1  mov     edx, 35h ; '5'
0x1800150e6  mov     r9d, eax
0x1800150e9  call    WPP_SF_d
0x1800150ee  jmp     loc_180015005
0x1800150f3  mov     r9d, [rdi+9C0h]
0x1800150fa  mov     edx, 0Bh
0x1800150ff  mov     rcx, [rcx+38h]
0x180015103  mov     [rsp+78h+var_58], rax
0x180015108  call    WPP_SF_Ls
0x18001510d  jmp     loc_180014E2B
0x180015112  mov     r9d, [rdi+9C0h]
0x180015119  lea     rax, aLocking; ">>> Locking >>>"
0x180015120  mov     rcx, [rcx+38h]
0x180015124  mov     edx, 0Bh
0x180015129  mov     [rsp+78h+var_58], rax
0x18001512e  call    WPP_SF_Ls
0x180015133  jmp     loc_180014E80
0x180015138  mov     ebx, 12Fh
0x18001513d  mov     r11, cs:WPP_GLOBAL_Control
0x180015144  cmp     r11, r13
0x180015147  jz      loc_180014F37
0x18001514d  test    [r11+44h], r12b
0x180015151  jz      loc_180014F24
0x180015157  mov     rcx, [r11+38h]
0x18001515b  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180015162  mov     edx, 38h ; '8'
0x180015167  call    WPP_SF_
0x18001516c  jmp     loc_180014F1D
0x180015171  mov     edx, 3Bh ; ';'
0x180015176  mov     rcx, [r11+38h]
0x18001517a  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180015181  mov     [rsp+78h+var_58], rax
0x180015186  call    WPP_SF_qq
0x18001518b  jmp     loc_180014F1D
0x180015190  mov     ebx, 139Fh
0x180015195  mov     r11, cs:WPP_GLOBAL_Control
0x18001519c  cmp     r11, r13
0x18001519f  jz      loc_180014F37
0x1800151a5  test    [r11+44h], r12b
0x1800151a9  jz      loc_180014F24
0x1800151af  mov     r10d, [rdi+0AA4h]
0x1800151b6  mov     ecx, r14d
0x1800151b9  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x1800151be  mov     ecx, r10d
0x1800151c1  mov     r8, rax
0x1800151c4  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x1800151c9  mov     rcx, [r11+38h]
0x1800151cd  mov     r9, rax
0x1800151d0  mov     [rsp+78h+var_48], r14d
0x1800151d5  mov     edx, 3Ah ; ':'
0x1800151da  mov     [rsp+78h+var_50], r8
0x1800151df  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x1800151e6  mov     dword ptr [rsp+78h+var_58], r10d
0x1800151eb  call    WPP_SF_SLSL
0x1800151f0  jmp     loc_180014F1D
0x1800151f5  mov     ebx, 139Fh
0x1800151fa  mov     r11, cs:WPP_GLOBAL_Control
0x180015201  cmp     r11, r13
0x180015204  jz      loc_180014F37
0x18001520a  test    [r11+44h], r12b
0x18001520e  jz      loc_180014F24
0x180015214  jmp     loc_180015171
0x180015219  mov     ebx, 139Fh
0x18001521e  mov     r11, cs:WPP_GLOBAL_Control
0x180015225  cmp     r11, r13
0x180015228  jz      loc_180014F37
0x18001522e  test    [r11+44h], r12b
0x180015232  jz      loc_180014F24
0x180015238  mov     ecx, r8d
0x18001523b  call    ?PortSecStateStr@@YAPEBGW4MSMSEC_PORT_SEC_STATE@@@Z; PortSecStateStr(MSMSEC_PORT_SEC_STATE)
0x180015240  mov     rcx, [r11+38h]
0x180015244  mov     r9, rax
0x180015247  mov     dword ptr [rsp+78h+var_58], r8d
0x18001524c  mov     edx, 3Ch ; '<'
0x180015251  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180015258  call    WPP_SF_SL
0x18001525d  jmp     loc_180014F1D
0x180015262  mov     r9d, [rbp+138h]
0x180015269  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x180015270  mov     rcx, [r11+38h]
0x180015274  mov     edx, 0Ch
0x180015279  mov     [rsp+78h+var_58], rax
0x18001527e  call    WPP_SF_Ls
0x180015283  jmp     loc_180014F37
0x180015288  mov     r9d, [rdi+9C0h]
0x18001528f  mov     edx, 0Bh
0x180015294  mov     rcx, [rcx+38h]
0x180015298  mov     [rsp+78h+var_58], rax
0x18001529d  call    WPP_SF_Ls
0x1800152a2  jmp     loc_180014F7A
0x1800152a7  mov     r9d, [rbp+138h]
0x1800152ae  mov     edx, 0Ch
0x1800152b3  mov     rcx, [rcx+38h]
0x1800152b7  mov     [rsp+78h+var_58], r12
0x1800152bc  call    WPP_SF_Ls
0x1800152c1  jmp     loc_180014FC2
0x1800152c6  mov     r9d, [rdi+9C0h]
  ... truncated ...
```
