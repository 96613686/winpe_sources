# MSMSecRecvIndication

- ea: `0x180012df0`
- end: `0x1800135f8`
- name: `MSMSecRecvIndication`
- size: `2056`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, unsigned int, struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)`
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x18000431c`
- `0x1800073ec`
- `0x18000892c`
- `0x180008998`
- `0x180009c30`
- `0x18000a26c`
- `0x1800125b0`
- `0x180012df0`
- `0x180013600`
- `0x180013bc0`
- `0x180013cf4`
- `0x180014998`
- `0x180014b64`
- `0x180016a08`
- `0x18002abec`
- `0x18002b3f8`
- `0x180035824`
- `0x180043a30`
- `0x180050da8`
- `0x1800558c0`
- `0x180055a38`
- `0x180076758`
- `0x180076cb4`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180012fdc`
- `MobileNetworking!ReleaseWriteLock` at `0x18001304a`
- `MobileNetworking!ReleaseWriteLock` at `0x1800130e6`
- `MobileNetworking!ReleaseWriteLock` at `0x180012fdc`
- `MobileNetworking!ReleaseWriteLock` at `0x18001304a`
- `MobileNetworking!ReleaseWriteLock` at `0x1800130e6`

## pseudocode

```c
__int64 __fastcall MSMSecRecvIndication(
        void *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *a5)
{
  PVOID *v9; // rcx
  __int64 v10; // r9
  PVOID *v11; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  struct MSMSEC_INTF_CONTEXT *v14; // rdi
  __int64 v15; // rdx
  struct _DOT11_SAE_AUTH_PARAMS_NEEDED *v16; // r8
  __int64 v17; // r9
  PVOID *v18; // r11
  struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *v19; // rdx
  unsigned int v20; // eax
  struct MSMSEC_PORT_CONTEXT *v21; // rsi
  unsigned int v22; // eax
  int v23; // r8d
  unsigned int v24; // eax
  int v25; // r8d
  PVOID *v26; // rcx
  PVOID *v27; // rcx
  int v28; // r8d
  __int64 v29; // r9
  PVOID *v30; // rcx
  __int64 v32; // rax
  __int64 v33; // r11
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // rax
  unsigned int v38; // r10d
  __int64 v39; // rdx
  int v40; // eax
  __int64 v41; // r11
  __int64 v42; // r8
  char v43; // r10
  _OWORD *v44; // rax
  struct MSMSEC_INTF_CONTEXT *v45; // [rsp+40h] [rbp-A8h] BYREF
  struct MSMSEC_PORT_CONTEXT *v46; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v47[32]; // [rsp+50h] [rbp-98h] BYREF
  _OWORD v48[2]; // [rsp+70h] [rbp-78h] BYREF

  v45 = 0;
  v46 = 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 119, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x400) != 0 )
      WPP_SF_sd(
        (unsigned int)v9[7],
        22,
        (unsigned int)&WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
        (unsigned int)"MSMSecRecvIndication",
        105);
  }
  v10 = (unsigned int)_InterlockedIncrement(&dword_1800AEF94);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v10);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( g_MSMSecState )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 0x20) != 0 )
    {
      WPP_SF_(v11[7], 121, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !a1 || !a4 || !a5 )
    {
      v12 = 87;
      if ( v11 == &WPP_GLOBAL_Control )
        goto LABEL_62;
      if ( (*((_BYTE *)v11 + 68) & 1) == 0 )
        goto LABEL_58;
      WPP_SF_(v11[7], 122, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
      goto LABEL_57;
    }
    v13 = ValidateSecurityIndication(a4, a5, a2);
    v12 = v13;
    if ( v13 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_62;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_58;
      v34 = 123;
    }
    else
    {
      v13 = SecMgrValidateRefAndLockAdapter(a1, &v45);
      v12 = v13;
      if ( !v13 )
      {
        v14 = v45;
        if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v45 + 681), 10) )
        {
          v12 = 5023;
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_49;
            v37 = IntfActionStr(10, v15, v16, v17);
            v40 = IntfSecStateStr(v38, v39, v37);
            WPP_SF_SLSL(
              *(_QWORD *)(v41 + 56),
              125,
              (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
              v40,
              v43,
              v42,
              10);
            goto LABEL_48;
          }
          goto LABEL_52;
        }
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        {
          v32 = msmsec::string::ToString(a2);
          WPP_SF_LS(
            *(_QWORD *)(v33 + 56),
            126,
            (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            *((_DWORD *)v14 + 624),
            v32);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( a2 != 5 )
        {
          if ( a2 == 6 )
          {
            v20 = PmkCacheRecvPmkIdIndication(
                    (struct MSMSEC_INTF_CONTEXT *)((char *)v14 + 3000),
                    *((_DWORD *)v14 + 625),
                    (unsigned int)v16,
                    a4,
                    a5);
            v12 = v20;
            if ( !v20 )
            {
LABEL_48:
              v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
              if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 17) & 0x100) != 0 )
                WPP_SF_Ls((unsigned int)v18[7], 11, (_DWORD)v16, *((_DWORD *)v14 + 624), (__int64)"<<< Unlocking <<<");
              goto LABEL_52;
            }
            v18 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
                goto LABEL_49;
              v35 = 127;
LABEL_77:
              WPP_SF_d(v18[7], v35, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v20);
              goto LABEL_48;
            }
LABEL_52:
            ReleaseWriteLock(v14, (char *)v14 + 2512, "MSMSecRecvIndication", 1246);
LABEL_53:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
              WPP_SF_Ls(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                11,
                v28,
                *((_DWORD *)v14 + 624),
                (__int64)"<<< Derefing <<<");
            SecMgrDerefAdapterEx(v14, "MSMSecRecvIndication", 1258);
            goto LABEL_57;
          }
          if ( a2 != 10 && a2 != 11 && a2 != 12 )
          {
            if ( a2 == 46 )
            {
              msmsec::sae::ProcessSaeIndication(v14, (struct MSMSEC_INTF_CONTEXT *)a5, v16);
              goto LABEL_48;
            }
            if ( a2 == 47 )
            {
              v44 = (_OWORD *)msmsec::assoc::ProcessPeerAssocRequest(v47, v14, a5);
              v48[0] = *v44;
              *(_OWORD *)((char *)v48 + 12) = *(_OWORD *)((char *)v44 + 12);
              (*((void (__fastcall **)(_QWORD, _OWORD *))v14 + 280))(*((_QWORD *)v14 + 3), v48);
              v18 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
                  goto LABEL_49;
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 96, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
                goto LABEL_48;
              }
            }
            else
            {
              v12 = 87;
              if ( v18 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v18 + 68) & 1) == 0 )
                  goto LABEL_49;
                WPP_SF_dd(
                  v18[7],
                  131,
                  &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
                  *((unsigned int *)v14 + 624),
                  a2);
                goto LABEL_48;
              }
            }
            goto LABEL_52;
          }
        }
        v19 = a5 + 1;
        if ( a2 != 5 )
          v19 = a5;
        v20 = SecMgrValidateAndRefPort(v14, (unsigned __int8 (*)[6])v19, &v46);
        v12 = v20;
        if ( !v20 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
            WPP_SF_Ls(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              11,
              (_DWORD)v16,
              *((_DWORD *)v14 + 624),
              (__int64)"<<< Unlocking <<<");
          ReleaseWriteLock(v14, (char *)v14 + 2512, "MSMSecRecvIndication", 1208);
          v21 = v46;
          v22 = SecMgrLockAndCheckPortActive(v46);
          v12 = v22;
          if ( v22 )
          {
            v27 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            {
LABEL_46:
              SecMgrDerefPortEx(v21, "MSMSecRecvIndication", 1254);
              goto LABEL_53;
            }
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            {
LABEL_43:
              if ( v27 != &WPP_GLOBAL_Control && (*((_DWORD *)v27 + 17) & 0x100) != 0 )
                WPP_SF_Ls((unsigned int)v27[7], 12, v23, *((_DWORD *)v21 + 78), (__int64)"<<< Derefing <<<");
              goto LABEL_46;
            }
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 129, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v22);
LABEL_42:
            v27 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_43;
          }
          v24 = KeyMgrRecvIndication(v21, a2, a3, a5);
          v12 = v24;
          if ( v24 )
          {
            v26 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            {
LABEL_41:
              ReleaseWriteLock(v21, (char *)v21 + 320, "MSMSecRecvIndication", 1250);
              goto LABEL_42;
            }
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            {
LABEL_38:
              if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 17) & 0x100) != 0 )
                WPP_SF_Ls((unsigned int)v26[7], 12, v25, *((_DWORD *)v21 + 78), (__int64)"<<< Unlocking <<<");
              goto LABEL_41;
            }
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 130, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v24);
          }
          v26 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_38;
        }
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_49;
          v35 = 128;
          goto LABEL_77;
        }
        goto LABEL_52;
      }
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_62;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_58;
      v34 = 124;
    }
    v36 = v13;
LABEL_86:
    WPP_SF_d(v11[7], v34, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v36);
LABEL_57:
    v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_58:
    if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x400) != 0 )
      WPP_SF_sd(
        (unsigned int)v11[7],
        24,
        (unsigned int)&WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
        (unsigned int)"MSMSecRecvIndication",
        236);
    goto LABEL_62;
  }
  v12 = 21;
  if ( v11 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v11 + 68) & 1) != 0 )
    {
      WPP_SF_(v11[7], 21, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v11 + 68) & 1) == 0 )
        goto LABEL_58;
      v34 = 120;
      v36 = 21;
      goto LABEL_86;
    }
  }
LABEL_62:
  v29 = (unsigned int)_InterlockedDecrement(&dword_1800AEF94);
  v30 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v29);
      v30 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v30 != &WPP_GLOBAL_Control && (*((_DWORD *)v30 + 17) & 0x100) != 0 )
      WPP_SF_d(v30[7], 132, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180012df0  push    rbx
0x180012df2  push    rbp
0x180012df3  push    rsi
0x180012df4  push    rdi
0x180012df5  push    r12
0x180012df7  push    r13
0x180012df9  push    r14
0x180012dfb  push    r15
0x180012dfd  sub     rsp, 0A8h
0x180012e04  mov     rax, cs:__security_cookie
0x180012e0b  xor     rax, rsp
0x180012e0e  mov     [rsp+0E8h+var_58], rax
0x180012e16  mov     r14, [rsp+0E8h+arg_20]
0x180012e1e  xor     ebx, ebx
0x180012e20  mov     [rsp+0E8h+var_A8], rbx
0x180012e25  mov     esi, r9d
0x180012e28  mov     [rsp+0E8h+var_A0], rbx
0x180012e2d  mov     r12d, r8d
0x180012e30  mov     r15d, edx
0x180012e33  mov     rdi, rcx
0x180012e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e3d  lea     r13, WPP_GLOBAL_Control
0x180012e44  cmp     rcx, r13
0x180012e47  jz      short loc_180012E68
0x180012e49  test    dword ptr [rcx+44h], 100h
0x180012e50  jnz     loc_1800132A5
0x180012e56  cmp     rcx, r13
0x180012e59  jz      short loc_180012E68
0x180012e5b  test    dword ptr [rcx+44h], 400h
0x180012e62  jnz     loc_1800132C6
0x180012e68  mov     ebp, 1
0x180012e6d  mov     r9d, ebp
0x180012e70  lock xadd cs:dword_1800AEF94, r9d
0x180012e79  add     r9d, ebp
0x180012e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e83  cmp     rcx, r13
0x180012e86  jz      short loc_180012E95
0x180012e88  test    dword ptr [rcx+44h], 400h
0x180012e8f  jnz     loc_1800132EF
0x180012e95  cmp     cs:?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A, ebx; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180012e9b  jz      loc_180013310
0x180012ea1  cmp     rcx, r13
0x180012ea4  jnz     short loc_180012EDB
0x180012ea6  test    rdi, rdi
0x180012ea9  jnz     short loc_180012EFF
0x180012eab  mov     ebx, 57h ; 'W'
0x180012eb0  cmp     rcx, r13
0x180012eb3  jz      loc_18001316B
0x180012eb9  test    [rcx+44h], bpl
0x180012ebd  jz      loc_18001312E
0x180012ec3  mov     rcx, [rcx+38h]
0x180012ec7  lea     edx, [rbx+23h]
0x180012eca  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180012ed1  call    WPP_SF_
0x180012ed6  jmp     loc_180013127
0x180012edb  test    byte ptr [rcx+44h], 20h
0x180012edf  jz      short loc_180012EA6
0x180012ee1  mov     rcx, [rcx+38h]
0x180012ee5  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180012eec  mov     edx, 79h ; 'y'
0x180012ef1  call    WPP_SF_
0x180012ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012efd  jmp     short loc_180012EA6
0x180012eff  test    esi, esi
0x180012f01  jz      short loc_180012EAB
0x180012f03  test    r14, r14
0x180012f06  jz      short loc_180012EAB
0x180012f08  mov     r8d, r15d; unsigned int
0x180012f0b  mov     rdx, r14; void *
0x180012f0e  mov     ecx, esi; unsigned int
0x180012f10  call    ?ValidateSecurityIndication@@YAKKPEAXK@Z; ValidateSecurityIndication(ulong,void *,ulong)
0x180012f15  mov     ebx, eax
0x180012f17  test    eax, eax
0x180012f19  jnz     loc_180013377
0x180012f1f  lea     rdx, [rsp+0E8h+var_A8]; struct MSMSEC_INTF_CONTEXT **
0x180012f24  mov     rcx, rdi; void *
0x180012f27  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180012f2c  mov     ebx, eax
0x180012f2e  test    eax, eax
0x180012f30  jnz     loc_180013223
0x180012f36  mov     rdi, [rsp+0E8h+var_A8]
0x180012f3b  lea     edx, [rax+0Ah]
0x180012f3e  mov     ecx, [rdi+0AA4h]
0x180012f44  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180012f49  test    eax, eax
0x180012f4b  jz      loc_180013393
0x180012f51  mov     r11, cs:WPP_GLOBAL_Control
0x180012f58  cmp     r11, r13
0x180012f5b  jnz     loc_1800131E3
0x180012f61  mov     eax, r15d
0x180012f64  sub     eax, 5
0x180012f67  jz      short loc_180012F82
0x180012f69  sub     eax, ebp
0x180012f6b  jz      loc_180013091
0x180012f71  sub     eax, 4
0x180012f74  jz      short loc_180012F82
0x180012f76  sub     eax, ebp
0x180012f78  jz      short loc_180012F82
0x180012f7a  sub     eax, ebp
0x180012f7c  jnz     loc_1800133F9
0x180012f82  cmp     r15d, 5
0x180012f86  lea     rdx, [r14+0Ch]
0x180012f8a  lea     r8, [rsp+0E8h+var_A0]; struct MSMSEC_PORT_CONTEXT **
0x180012f8f  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180012f92  cmovnz  rdx, r14; unsigned __int8 (*)[6]
0x180012f96  call    ?SecMgrValidateAndRefPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrValidateAndRefPort(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x180012f9b  mov     ebx, eax
0x180012f9d  test    eax, eax
0x180012f9f  jnz     loc_180013247
0x180012fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fac  lea     rbp, aUnlocking; "<<< Unlocking <<<"
0x180012fb3  cmp     rcx, r13
0x180012fb6  jz      short loc_180012FC5
0x180012fb8  test    dword ptr [rcx+44h], 100h
0x180012fbf  jnz     loc_180013507
0x180012fc5  lea     rdx, [rdi+9D0h]
0x180012fcc  mov     r9d, 4B8h
0x180012fd2  lea     r8, aMsmsecrecvindi_0; "MSMSecRecvIndication"
0x180012fd9  mov     rcx, rdi
0x180012fdc  call    cs:__imp_ReleaseWriteLock
0x180012fe3  nop     dword ptr [rax+rax+00h]
0x180012fe8  mov     rsi, [rsp+0E8h+var_A0]
0x180012fed  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x180012ff0  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x180012ff5  mov     ebx, eax
0x180012ff7  test    eax, eax
0x180012ff9  jnz     loc_180013526
0x180012fff  mov     r9, r14; void *
0x180013002  mov     r8d, r12d; unsigned int
0x180013005  mov     edx, r15d; unsigned int
0x180013008  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x18001300b  call    ?KeyMgrRecvIndication@@YAKPEAUMSMSEC_PORT_CONTEXT@@KKPEAX@Z; KeyMgrRecvIndication(MSMSEC_PORT_CONTEXT *,ulong,ulong,void *)
0x180013010  mov     ebx, eax
0x180013012  test    eax, eax
0x180013014  jnz     loc_180013559
0x18001301a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013021  cmp     rcx, r13
0x180013024  jz      short loc_180013033
0x180013026  test    dword ptr [rcx+44h], 100h
0x18001302d  jnz     loc_18001356E
0x180013033  lea     rdx, [rsi+140h]
0x18001303a  mov     r9d, 4E2h
0x180013040  lea     r8, aMsmsecrecvindi_0; "MSMSecRecvIndication"
0x180013047  mov     rcx, rsi
0x18001304a  call    cs:__imp_ReleaseWriteLock
0x180013051  nop     dword ptr [rax+rax+00h]
0x180013056  mov     rcx, cs:WPP_GLOBAL_Control
0x18001305d  cmp     rcx, r13
0x180013060  jz      loc_1800135AC
0x180013066  test    dword ptr [rcx+44h], 100h
0x18001306d  lea     rbp, aDerefing; "<<< Derefing <<<"
0x180013074  jnz     loc_18001358D
0x18001307a  mov     r8d, 4E6h; int
0x180013080  lea     rdx, aMsmsecrecvindi_0; "MSMSecRecvIndication"
0x180013087  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x18001308a  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x18001308f  jmp     short loc_1800130F9
0x180013091  mov     edx, [rdi+9C4h]; unsigned int
0x180013097  lea     rcx, [rdi+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x18001309e  mov     r9d, esi; unsigned int
0x1800130a1  mov     [rsp+0E8h+var_C8], r14; struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *
0x1800130a6  call    ?PmkCacheRecvPmkIdIndication@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@KKKPEAUDOT11_PMKID_CANDIDATE_LIST_PARAMETERS@@@Z; PmkCacheRecvPmkIdIndication(MSMSEC_PMKCACHE_CONTEXT *,ulong,ulong,ulong,DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)
0x1800130ab  mov     ebx, eax
0x1800130ad  test    eax, eax
0x1800130af  jnz     loc_1800134BD
0x1800130b5  mov     r11, cs:WPP_GLOBAL_Control
0x1800130bc  cmp     r11, r13
0x1800130bf  jz      short loc_1800130CF
0x1800130c1  test    dword ptr [r11+44h], 100h
0x1800130c9  jnz     loc_1800134E1
0x1800130cf  lea     rdx, [rdi+9D0h]
0x1800130d6  mov     r9d, 4DEh
0x1800130dc  lea     r8, aMsmsecrecvindi_0; "MSMSecRecvIndication"
0x1800130e3  mov     rcx, rdi
0x1800130e6  call    cs:__imp_ReleaseWriteLock
0x1800130ed  nop     dword ptr [rax+rax+00h]
0x1800130f2  lea     rbp, aDerefing; "<<< Derefing <<<"
0x1800130f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013100  cmp     rcx, r13
0x180013103  jz      short loc_180013112
0x180013105  test    dword ptr [rcx+44h], 100h
0x18001310c  jnz     loc_1800135B8
0x180013112  mov     r8d, 4EAh; int
0x180013118  lea     rdx, aMsmsecrecvindi_0; "MSMSecRecvIndication"
0x18001311f  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180013122  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180013127  mov     rcx, cs:WPP_GLOBAL_Control
0x18001312e  cmp     rcx, r13
0x180013131  jz      short loc_18001316B
0x180013133  test    dword ptr [rcx+44h], 400h
0x18001313a  jz      short loc_18001316B
0x18001313c  mov     rcx, [rcx+38h]
0x180013140  lea     r9, aMsmsecrecvindi_0; "MSMSecRecvIndication"
0x180013147  mov     edx, 18h
0x18001314c  mov     dword ptr [rsp+0E8h+var_C8], 4ECh
0x180013154  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x18001315b  call    WPP_SF_sd
0x180013160  jmp     short loc_18001316B
0x180013162  cmp     rcx, r13
0x180013165  jnz     loc_180013346
0x18001316b  or      r9d, 0FFFFFFFFh
0x18001316f  lock xadd cs:dword_1800AEF94, r9d
0x180013178  dec     r9d
0x18001317b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013182  cmp     rcx, r13
0x180013185  jz      short loc_180013199
0x180013187  test    dword ptr [rcx+44h], 400h
0x18001318e  jnz     loc_1800135D7
0x180013194  cmp     rcx, r13
0x180013197  jnz     short loc_1800131C0
0x180013199  mov     eax, ebx
0x18001319b  mov     rcx, [rsp+0E8h+var_58]
0x1800131a3  xor     rcx, rsp; StackCookie
0x1800131a6  call    __security_check_cookie
0x1800131ab  add     rsp, 0A8h
0x1800131b2  pop     r15
0x1800131b4  pop     r14
0x1800131b6  pop     r13
0x1800131b8  pop     r12
0x1800131ba  pop     rdi
0x1800131bb  pop     rsi
0x1800131bc  pop     rbp
0x1800131bd  pop     rbx
0x1800131be  retn
0x1800131c0  test    dword ptr [rcx+44h], 100h
0x1800131c7  jz      short loc_180013199
0x1800131c9  mov     rcx, [rcx+38h]
0x1800131cd  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800131d4  mov     edx, 84h
0x1800131d9  mov     r9d, ebx
0x1800131dc  call    WPP_SF_d
0x1800131e1  jmp     short loc_180013199
0x1800131e3  test    byte ptr [r11+44h], 20h
0x1800131e8  jz      loc_180012F61
0x1800131ee  mov     ecx, r15d
0x1800131f1  call    ?ToString@string@msmsec@@YAPEBGW4DOT11_AUTH_UPCALL_TYPE@@@Z; msmsec::string::ToString(DOT11_AUTH_UPCALL_TYPE)
0x1800131f6  mov     rcx, [r11+38h]
0x1800131fa  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180013201  mov     r9d, [rdi+9C0h]
0x180013208  mov     edx, 7Eh ; '~'
0x18001320d  mov     [rsp+0E8h+var_C8], rax
0x180013212  call    WPP_SF_LS
0x180013217  mov     r11, cs:WPP_GLOBAL_Control
0x18001321e  jmp     loc_180012F61
0x180013223  mov     rcx, cs:WPP_GLOBAL_Control
0x18001322a  cmp     rcx, r13
0x18001322d  jz      loc_18001316B
0x180013233  test    [rcx+44h], bpl
0x180013237  jz      loc_18001312E
0x18001323d  mov     edx, 7Ch ; '|'
0x180013242  jmp     loc_18001335F
0x180013247  mov     r11, cs:WPP_GLOBAL_Control
0x18001324e  cmp     r11, r13
0x180013251  jz      loc_1800130CF
0x180013257  test    [r11+44h], bpl
0x18001325b  jz      loc_1800130BC
0x180013261  mov     edx, 80h
0x180013266  mov     rcx, [r11+38h]
0x18001326a  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180013271  mov     r9d, eax
0x180013274  call    WPP_SF_d
0x180013279  jmp     loc_1800130B5
0x18001327e  test    byte ptr [rcx+44h], 1
0x180013282  jz      loc_180013021
0x180013288  mov     rcx, [rcx+38h]
0x18001328c  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180013293  mov     edx, 82h
0x180013298  mov     r9d, eax
0x18001329b  call    WPP_SF_d
0x1800132a0  jmp     loc_18001301A
0x1800132a5  mov     rcx, [rcx+38h]
0x1800132a9  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800132b0  mov     edx, 77h ; 'w'
0x1800132b5  call    WPP_SF_
0x1800132ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132c1  jmp     loc_180012E56
0x1800132c6  mov     rcx, [rcx+38h]
0x1800132ca  lea     r9, aMsmsecrecvindi_0; "MSMSecRecvIndication"
0x1800132d1  mov     edx, 16h
0x1800132d6  mov     dword ptr [rsp+0E8h+var_C8], 469h
0x1800132de  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x1800132e5  call    WPP_SF_sd
0x1800132ea  jmp     loc_180012E68
0x1800132ef  mov     rcx, [rcx+38h]
0x1800132f3  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x1800132fa  mov     edx, 17h
0x1800132ff  call    WPP_SF_d
0x180013304  mov     rcx, cs:WPP_GLOBAL_Control
0x18001330b  jmp     loc_180012E95
0x180013310  mov     ebx, 15h
0x180013315  cmp     rcx, r13
0x180013318  jz      loc_18001316B
0x18001331e  test    [rcx+44h], bpl
0x180013322  jz      loc_180013162
0x180013328  mov     rcx, [rcx+38h]
0x18001332c  lea     r8, WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids
0x180013333  mov     edx, ebx
0x180013335  call    WPP_SF_
0x18001333a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013341  jmp     loc_180013162
  ... truncated ...
```
