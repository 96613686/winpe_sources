# MSMSecPerformCapabilityMatch

- ea: `0x1800115c0`
- end: `0x18001221d`
- name: `MSMSecPerformCapabilityMatch`
- size: `3165`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64, struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x18000431c`
- `0x180005e80`
- `0x18000892c`
- `0x180008998`
- `0x1800115c0`
- `0x180012224`
- `0x180012a20`
- `0x180013bc0`
- `0x1800169c0`
- `0x180036b98`
- `0x180038368`
- `0x180050da8`
- `0x180055a38`
- `0x180057f50`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800119ab`
- `MobileNetworking!ReleaseWriteLock` at `0x180011bd9`
- `MobileNetworking!ReleaseWriteLock` at `0x1800119ab`
- `MobileNetworking!ReleaseWriteLock` at `0x180011bd9`
- `MobileNetworking!AcquireWriteLock` at `0x180011845`
- `MobileNetworking!AcquireWriteLock` at `0x180011845`

## string_xrefs

- `0x180011834`: `SecMgrLockAndCheckAdapterDeleted`
- `0x180011bc8`: `SecMgrLockAndCheckAdapterDeleted`

## pseudocode

```c
__int64 MSMSecPerformCapabilityMatch(
        void *a1,
        struct MSMSEC_NW_DESC *a2,
        struct MSMSEC_HOST_DESC *a3,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a4,
        struct _DOT11_BSS_LIST *a5,
        ...)
{
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v5; // r10
  struct MSMSEC_INTF_CONTEXT *v8; // rbp
  struct MSMSEC_HOST_DESC *v9; // rax
  PVOID *v10; // rcx
  __int64 v11; // r9
  PVOID *v12; // rcx
  struct MSMSEC_INTF_CONTEXT *v13; // r14
  __int64 v14; // r9
  unsigned int v15; // ebx
  unsigned int v16; // edi
  __int64 uNumOfBytes; // r9
  int v18; // ebx
  unsigned int v19; // eax
  int v20; // r8d
  unsigned int v21; // ebx
  PVOID *v22; // rcx
  int v23; // r8d
  unsigned int matched; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r9
  bool v28; // zf
  int v29; // r8d
  PVOID *v30; // rbx
  unsigned __int32 v31; // ebx
  signed __int32 v32; // esi
  PVOID *v33; // rcx
  __int64 v35; // rdx
  PVOID *v36; // rcx
  unsigned int v37; // [rsp+60h] [rbp-48h] BYREF
  int v38; // [rsp+64h] [rbp-44h]
  struct MSMSEC_INTF_CONTEXT *v41; // [rsp+D8h] [rbp+30h] BYREF
  va_list va; // [rsp+D8h] [rbp+30h]
  va_list va1; // [rsp+E0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v41 = va_arg(va1, struct MSMSEC_INTF_CONTEXT *);
  v5 = a4;
  v37 = 327679;
  v38 = 0;
  v8 = 0;
  v9 = a3;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 37, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      v9 = a3;
      v5 = a4;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x400) != 0 )
    {
      WPP_SF_sd(
        (unsigned int)v10[7],
        22,
        (unsigned int)&WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
        (unsigned int)"MSMSecPerformCapabilityMatch",
        201);
      v9 = a3;
      v5 = a4;
    }
  }
  v11 = (unsigned int)_InterlockedIncrement(&dword_1800AEF94);
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v11);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v9 = a3;
    v5 = a4;
  }
  v13 = v41;
  if ( !g_MSMSecState )
  {
    v16 = 21;
    if ( v12 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v12 + 68) & 1) != 0 )
      {
        WPP_SF_(v12[7], 21, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 1) != 0 )
      {
        WPP_SF_d(v12[7], 38, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, 21);
        goto LABEL_121;
      }
    }
LABEL_83:
    if ( !v13 )
      goto LABEL_98;
    goto LABEL_84;
  }
  if ( !a1 && !v5 && !a5 || !v41 || !v9 )
  {
    v16 = 87;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 1) != 0 )
    {
      WPP_SF_(v12[7], 39, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
LABEL_121:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  if ( !a2 )
    goto LABEL_108;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
  {
    WPP_SF_(v12[2], 10, WPP_41974e13a072338369dd160d0525fcfd_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v9 = a3;
    v5 = a4;
  }
  v14 = *(unsigned int *)a2;
  if ( (unsigned int)v14 > 0x20 )
  {
    if ( v12 != &WPP_GLOBAL_Control )
    {
      v15 = 0;
      if ( (*((_BYTE *)v12 + 28) & 2) == 0 )
        goto LABEL_22;
      v35 = 11;
LABEL_137:
      WPP_SF_d(v12[2], v35, WPP_41974e13a072338369dd160d0525fcfd_Traceguids, v14);
      v12 = (PVOID *)WPP_GLOBAL_Control;
      v5 = a4;
      goto LABEL_21;
    }
LABEL_108:
    v16 = 87;
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 1) == 0 )
      goto LABEL_84;
    v25 = 40;
LABEL_111:
    WPP_SF_(v12[7], v25, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_84;
  }
  v14 = *((unsigned int *)a2 + 9);
  if ( (unsigned int)(v14 - 1) > 1 )
  {
    if ( v12 != &WPP_GLOBAL_Control )
    {
      v15 = 0;
      if ( (*((_BYTE *)v12 + 28) & 2) == 0 )
        goto LABEL_21;
      v35 = 12;
      goto LABEL_137;
    }
    goto LABEL_108;
  }
  v15 = 1;
LABEL_21:
  v9 = a3;
LABEL_22:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
  {
    WPP_SF_d(v12[2], 13, WPP_41974e13a072338369dd160d0525fcfd_Traceguids, v15);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v9 = a3;
    v5 = a4;
  }
  if ( !v15 )
    goto LABEL_108;
  v16 = 87;
  if ( !a5 )
    goto LABEL_37;
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
  {
    WPP_SF_(v12[7], 82, &WPP_12e458de31a934de740e4a85c92fcb51_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v9 = a3;
    v5 = a4;
  }
  uNumOfBytes = a5->uNumOfBytes;
  if ( !(_DWORD)uNumOfBytes || !a5->pucBuffer )
  {
    if ( v12 != &WPP_GLOBAL_Control )
    {
      v18 = 87;
      if ( (*((_BYTE *)v12 + 68) & 1) == 0 )
        goto LABEL_33;
      WPP_SF_(v12[7], 83, &WPP_12e458de31a934de740e4a85c92fcb51_Traceguids);
LABEL_147:
      v5 = a4;
      v9 = a3;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_33;
    }
LABEL_73:
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 1) == 0 )
      goto LABEL_84;
    v25 = 41;
    goto LABEL_111;
  }
  v18 = 0;
  if ( (unsigned int)uNumOfBytes < 0x40 )
  {
    if ( v12 != &WPP_GLOBAL_Control )
    {
      v18 = 122;
      if ( (*((_BYTE *)v12 + 68) & 1) == 0 )
        goto LABEL_33;
      WPP_SF_dd(v12[7], 84, &WPP_12e458de31a934de740e4a85c92fcb51_Traceguids, uNumOfBytes, 64);
      goto LABEL_147;
    }
    goto LABEL_73;
  }
LABEL_33:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
  {
    WPP_SF_d(v12[7], 85, &WPP_12e458de31a934de740e4a85c92fcb51_Traceguids, v18 == 0);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v9 = a3;
    v5 = a4;
  }
  if ( v18 )
    goto LABEL_73;
LABEL_37:
  if ( v12 != &WPP_GLOBAL_Control && *((char *)v12 + 68) < 0 )
  {
    WPP_SF_(v12[7], 42, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v9 = a3;
    v5 = a4;
  }
  if ( !a1 )
  {
LABEL_70:
    matched = PerformCapabilityMatchInternal(v8, a2, v9, v5, a5, 0, &v37);
    v16 = matched;
    if ( matched )
    {
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v26 = 44;
        v27 = matched;
        goto LABEL_117;
      }
    }
    goto LABEL_84;
  }
  v41 = 0;
  if ( v12 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    {
      WPP_SF_(v12[7], 31, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
      WPP_SF_(v12[7], 25, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  }
  v19 = SecMgrValidateAndDeleteOrRefAdapter(a1, 0, 1, (struct MSMSEC_INTF_CONTEXT **)va);
  v21 = v19;
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v19);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v21 )
  {
    v8 = v41;
    if ( v22 != &WPP_GLOBAL_Control && (*((_DWORD *)v22 + 17) & 0x100) != 0 )
    {
      WPP_SF_(v22[7], 27, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 )
    {
      if ( v22 != &WPP_GLOBAL_Control && (*((_DWORD *)v22 + 17) & 0x100) != 0 )
        WPP_SF_Ls((unsigned int)v22[7], 11, v20, *((_DWORD *)v8 + 624), (__int64)">>> Locking >>>");
      AcquireWriteLock(v8, (char *)v8 + 2512, "SecMgrLockAndCheckAdapterDeleted", 482);
      if ( *((_DWORD *)v8 + 654) )
      {
        v16 = 6;
        v36 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
            v36 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v36 != &WPP_GLOBAL_Control && (*((_DWORD *)v36 + 17) & 0x100) != 0 )
            WPP_SF_Ls((unsigned int)v36[7], 11, v23, *((_DWORD *)v8 + 624), (__int64)"<<< Unlocking <<<");
        }
        ReleaseWriteLock(v8, (char *)v8 + 2512, "SecMgrLockAndCheckAdapterDeleted", 496);
      }
      else
      {
        v16 = 0;
      }
    }
    else
    {
      if ( v22 == &WPP_GLOBAL_Control )
      {
LABEL_64:
        if ( v16 )
        {
          if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 68) & 1) != 0 )
            WPP_SF_d(v22[7], 34, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v16);
          TraceAdapterId(*((_DWORD *)v8 + 624), "<<< Derefing <<<");
          SecMgrDerefAdapterEx(v8, "SecMgrValidateRefAndLockAdapter", 535);
          v22 = (PVOID *)WPP_GLOBAL_Control;
          v8 = 0;
        }
        goto LABEL_65;
      }
      if ( (*((_BYTE *)v22 + 68) & 1) == 0 )
      {
LABEL_61:
        if ( v22 != &WPP_GLOBAL_Control && (*((_DWORD *)v22 + 17) & 0x100) != 0 )
        {
          WPP_SF_d(v22[7], 30, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v16);
          v22 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_64;
      }
      WPP_SF_(v22[7], 28, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    }
    v22 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  v16 = v21;
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 68) & 1) != 0 )
  {
    WPP_SF_d(v22[7], 33, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v21);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_65:
  if ( v22 != &WPP_GLOBAL_Control && (*((_DWORD *)v22 + 17) & 0x100) != 0 )
  {
    WPP_SF_d(v22[7], 35, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v16);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v16 )
  {
    v9 = a3;
    v5 = a4;
    v38 = 1;
    goto LABEL_70;
  }
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 68) & 1) != 0 )
  {
    v26 = 43;
    v27 = v16;
LABEL_117:
    WPP_SF_d(v22[7], v26, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v27);
  }
LABEL_84:
  v28 = v38 == 0;
  *(_DWORD *)v13 = v37;
  if ( v28 )
  {
LABEL_113:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_98;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      11,
      (unsigned int)"<<< Unlocking <<<",
      *((_DWORD *)v8 + 624),
      (__int64)"<<< Unlocking <<<");
  ReleaseWriteLock(v8, (char *)v8 + 2512, "MSMSecPerformCapabilityMatch", 253);
  v30 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v29, *((_DWORD *)v8 + 624), (__int64)"<<< Derefing <<<");
    v30 = (PVOID *)WPP_GLOBAL_Control;
  }
  v41 = v8;
  if ( v30 != &WPP_GLOBAL_Control && (*((_DWORD *)v30 + 17) & 0x400) != 0 )
    WPP_SF_sdqDDDDDD(
      (unsigned int)v30[7],
      14,
      (unsigned int)&WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids,
      (unsigned int)"MSMSecPerformCapabilityMatch",
      253,
      (char)v8,
      *((_BYTE *)v8 + 2360),
      *((_BYTE *)v8 + 2361),
      *((_BYTE *)v8 + 2362),
      *((_BYTE *)v8 + 2363),
      *((_BYTE *)v8 + 2364),
      *((_BYTE *)v8 + 2365));
  v31 = _InterlockedDecrement((volatile signed __int32 *)v8 + 4);
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v31);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v31 )
  {
    SecMgrMarkDeletedAndDerefAllPorts(v8, 1, v29);
    SecMgrRemoveAdapterFromDeletedList(v8);
    SecMgrDestroyAdapter((struct MSMSEC_INTF_CONTEXT **)va);
    goto LABEL_113;
  }
LABEL_98:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x400) != 0 )
    WPP_SF_sd(
      (unsigned int)v12[7],
      24,
      (unsigned int)&WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
      (unsigned int)"MSMSecPerformCapabilityMatch",
      255);
  v32 = _InterlockedExchangeAdd(&dword_1800AEF94, 0xFFFFFFFF);
  v33 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        25,
        &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
        (unsigned int)(v32 - 1));
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v33 != &WPP_GLOBAL_Control && (*((_DWORD *)v33 + 17) & 0x100) != 0 )
      WPP_SF_d(v33[7], 45, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v16);
  }
  return v16;
}

```

## disassembly

```asm
0x1800115c0  mov     rax, rsp
0x1800115c3  mov     [rax+20h], r9
0x1800115c7  mov     [rax+18h], r8
0x1800115cb  push    rsi
0x1800115cc  push    rdi
0x1800115cd  push    r12
0x1800115cf  sub     rsp, 90h
0x1800115d6  mov     [rax-20h], rbp
0x1800115da  mov     r10, r9
0x1800115dd  mov     [rax-28h], r13
0x1800115e1  mov     r12, rcx
0x1800115e4  mov     r13, rdx
0x1800115e7  mov     [rax-30h], r14
0x1800115eb  xor     edx, edx
0x1800115ed  mov     [rsp+0A8h+var_48], 4FFFFh
0x1800115f5  mov     [rsp+0A8h+var_44], edx
0x1800115f9  mov     ebp, edx
0x1800115fb  mov     rax, r8
0x1800115fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180011605  lea     rdi, WPP_GLOBAL_Control
0x18001160c  cmp     rcx, rdi
0x18001160f  jz      short loc_180011630
0x180011611  test    dword ptr [rcx+44h], 100h
0x180011618  jnz     loc_180011BEA
0x18001161e  cmp     rcx, rdi
0x180011621  jz      short loc_180011630
0x180011623  test    dword ptr [rcx+44h], 400h
0x18001162a  jnz     loc_180011C1D
0x180011630  mov     r9d, 1
0x180011636  lock xadd cs:dword_1800AEF94, r9d
0x18001163f  inc     r9d
0x180011642  mov     rcx, cs:WPP_GLOBAL_Control
0x180011649  cmp     rcx, rdi
0x18001164c  jz      short loc_18001165B
0x18001164e  test    dword ptr [rcx+44h], 400h
0x180011655  jnz     loc_180011C58
0x18001165b  cmp     cs:?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A, ebp; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180011661  lea     r8, aUnlocking; "<<< Unlocking <<<"
0x180011668  mov     r14, [rsp+0A8h+arg_28]
0x180011670  mov     esi, 0FFFFFFFFh
0x180011675  mov     [rsp+0A8h+arg_0], rbx
0x18001167d  mov     [rsp+0A8h+var_38], r15
0x180011682  jz      loc_180011C8B
0x180011688  mov     r15, [rsp+0A8h+arg_20]
0x180011690  test    r12, r12
0x180011693  jz      loc_180011CF6
0x180011699  test    r14, r14
0x18001169c  jz      loc_180011B69
0x1800116a2  test    rax, rax
0x1800116a5  jz      loc_180011B69
0x1800116ab  test    r13, r13
0x1800116ae  jz      loc_180011AA0
0x1800116b4  cmp     rcx, rdi
0x1800116b7  jz      short loc_1800116C3
0x1800116b9  test    byte ptr [rcx+1Ch], 8
0x1800116bd  jnz     loc_180011D0D
0x1800116c3  mov     r9d, [r13+0]
0x1800116c7  cmp     r9d, 20h ; ' '
0x1800116cb  ja      loc_180011D47
0x1800116d1  mov     r9d, [r13+24h]
0x1800116d5  lea     eax, [r9-1]
0x1800116d9  cmp     eax, 1
0x1800116dc  ja      loc_180011D95
0x1800116e2  mov     ebx, 1
0x1800116e7  mov     rax, [rsp+0A8h+arg_10]
0x1800116ef  cmp     rcx, rdi
0x1800116f2  jz      short loc_1800116FE
0x1800116f4  test    byte ptr [rcx+1Ch], 8
0x1800116f8  jnz     loc_180011DAC
0x1800116fe  test    ebx, ebx
0x180011700  jz      loc_180011AA0
0x180011706  mov     edi, 57h ; 'W'
0x18001170b  test    r15, r15
0x18001170e  jz      short loc_18001176C
0x180011710  lea     rbx, WPP_GLOBAL_Control
0x180011717  cmp     rcx, rbx
0x18001171a  jz      short loc_180011729
0x18001171c  test    dword ptr [rcx+44h], 100h
0x180011723  jnz     loc_180011DE9
0x180011729  mov     r9d, [r15]
0x18001172c  test    r9d, r9d
0x18001172f  jz      loc_180011E5D
0x180011735  cmp     [r15+8], rbp
0x180011739  jz      loc_180011E5D
0x18001173f  mov     ebx, edx
0x180011741  cmp     r9d, 40h ; '@'
0x180011745  jb      loc_180011E23
0x18001174b  lea     r9, WPP_GLOBAL_Control
0x180011752  cmp     rcx, r9
0x180011755  jz      short loc_180011764
0x180011757  test    dword ptr [rcx+44h], 100h
0x18001175e  jnz     loc_180011EAC
0x180011764  test    ebx, ebx
0x180011766  jnz     loc_1800118F6
0x18001176c  lea     rbx, WPP_GLOBAL_Control
0x180011773  cmp     rcx, rbx
0x180011776  jz      short loc_180011782
0x180011778  test    byte ptr [rcx+44h], 80h
0x18001177c  jnz     loc_180011EEF
0x180011782  test    r12, r12
0x180011785  jz      loc_1800118ED
0x18001178b  mov     [rsp+0A8h+arg_28], rdx
0x180011793  cmp     rcx, rbx
0x180011796  jz      short loc_1800117B7
0x180011798  test    dword ptr [rcx+44h], 100h
0x18001179f  jnz     loc_180011F22
0x1800117a5  cmp     rcx, rbx
0x1800117a8  jz      short loc_1800117B7
0x1800117aa  test    dword ptr [rcx+44h], 100h
0x1800117b1  jnz     loc_180011F43
0x1800117b7  lea     r9, [rsp+0A8h+arg_28]; struct MSMSEC_INTF_CONTEXT **
0x1800117bf  xor     edx, edx; int
0x1800117c1  mov     r8d, 1; int
0x1800117c7  mov     rcx, r12; void *
0x1800117ca  call    ?SecMgrValidateAndDeleteOrRefAdapter@@YAKPEAXHHPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateAndDeleteOrRefAdapter(void *,int,int,MSMSEC_INTF_CONTEXT * *)
0x1800117cf  mov     ebx, eax
0x1800117d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117d8  lea     r12, WPP_GLOBAL_Control
0x1800117df  cmp     rcx, r12
0x1800117e2  jz      short loc_1800117F1
0x1800117e4  test    dword ptr [rcx+44h], 100h
0x1800117eb  jnz     loc_180011F5D
0x1800117f1  test    ebx, ebx
0x1800117f3  jnz     loc_180011F81
0x1800117f9  mov     rbp, [rsp+0A8h+arg_28]
0x180011801  cmp     rcx, r12
0x180011804  jz      short loc_180011813
0x180011806  test    dword ptr [rcx+44h], 100h
0x18001180d  jnz     loc_180011FBA
0x180011813  test    rbp, rbp
0x180011816  jz      loc_180011912
0x18001181c  cmp     rcx, r12
0x18001181f  jz      short loc_18001182E
0x180011821  test    dword ptr [rcx+44h], 100h
0x180011828  jnz     loc_180011FDB
0x18001182e  mov     r9d, 1E2h
0x180011834  lea     r8, aSecmgrlockandc; "SecMgrLockAndCheckAdapterDeleted"
0x18001183b  lea     rdx, [rbp+9D0h]
0x180011842  mov     rcx, rbp
0x180011845  call    cs:__imp_AcquireWriteLock
0x18001184c  nop     dword ptr [rax+rax+00h]
0x180011851  cmp     dword ptr [rbp+0A38h], 0
0x180011858  jnz     loc_180012001
0x18001185e  xor     edi, edi
0x180011860  mov     rcx, cs:WPP_GLOBAL_Control
0x180011867  cmp     rcx, r12
0x18001186a  jz      short loc_180011879
0x18001186c  test    dword ptr [rcx+44h], 100h
0x180011873  jnz     loc_180011B07
0x180011879  test    edi, edi
0x18001187b  jnz     loc_180012067
0x180011881  xor     edx, edx
0x180011883  cmp     rcx, r12
0x180011886  jz      short loc_180011895
0x180011888  test    dword ptr [rcx+44h], 100h
0x18001188f  jnz     loc_1800120C1
0x180011895  test    edi, edi
0x180011897  jnz     loc_18001193F
0x18001189d  mov     rax, [rsp+0A8h+arg_10]
0x1800118a5  mov     r10, [rsp+0A8h+arg_18]
0x1800118ad  mov     [rsp+0A8h+var_44], 1
0x1800118b5  lea     rcx, [rsp+0A8h+var_48]
0x1800118ba  mov     r9, r10; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x1800118bd  mov     [rsp+0A8h+var_78], rcx; unsigned int *
0x1800118c2  mov     r8, rax; struct MSMSEC_HOST_DESC *
0x1800118c5  mov     [rsp+0A8h+var_80], rdx; struct DOT11_MSMSEC_CONNECTION_PROFILE **
0x1800118ca  mov     rcx, rbp; struct MSMSEC_INTF_CONTEXT *
0x1800118cd  mov     rdx, r13; struct MSMSEC_NW_DESC *
0x1800118d0  mov     [rsp+0A8h+var_88], r15; struct _DOT11_BSS_LIST *
0x1800118d5  call    ?PerformCapabilityMatchInternal@@YAKAEAUMSMSEC_INTF_CONTEXT@@AEAUMSMSEC_NW_DESC@@AEAUMSMSEC_HOST_DESC@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAU_DOT11_BSS_LIST@@PEAPEAU4@PEAK@Z; PerformCapabilityMatchInternal(MSMSEC_INTF_CONTEXT &,MSMSEC_NW_DESC &,MSMSEC_HOST_DESC &,DOT11_MSMSEC_CONNECTION_PROFILE *,_DOT11_BSS_LIST *,DOT11_MSMSEC_CONNECTION_PROFILE * *,ulong *)
0x1800118da  mov     edi, eax
0x1800118dc  test    eax, eax
0x1800118de  jnz     loc_180011B2B
0x1800118e4  lea     r8, aUnlocking; "<<< Unlocking <<<"
0x1800118eb  jmp     short loc_180011969
0x1800118ed  lea     r12, WPP_GLOBAL_Control
0x1800118f4  jmp     short loc_1800118B5
0x1800118f6  lea     r12, WPP_GLOBAL_Control
0x1800118fd  cmp     rcx, r12
0x180011900  jz      short loc_180011969
0x180011902  test    byte ptr [rcx+44h], 1
0x180011906  jz      short loc_180011969
0x180011908  mov     edx, 29h ; ')'
0x18001190d  jmp     loc_180011AC4
0x180011912  cmp     rcx, r12
0x180011915  jz      loc_180011879
0x18001191b  test    byte ptr [rcx+44h], 1
0x18001191f  jz      loc_180011867
0x180011925  mov     rcx, [rcx+38h]
0x180011929  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180011930  mov     edx, 1Ch
0x180011935  call    WPP_SF_
0x18001193a  jmp     loc_180011860
0x18001193f  cmp     rcx, r12
0x180011942  jz      short loc_1800118E4
0x180011944  test    byte ptr [rcx+44h], 1
0x180011948  jz      short loc_1800118E4
0x18001194a  mov     edx, 2Bh ; '+'
0x18001194f  mov     r9d, edi
0x180011952  jmp     loc_180011B4D
0x180011957  cmp     rcx, r12
0x18001195a  jnz     loc_180011CCF
0x180011960  test    r14, r14
0x180011963  jz      loc_180011A14
0x180011969  cmp     [rsp+0A8h+var_44], 0
0x18001196e  mov     eax, [rsp+0A8h+var_48]
0x180011972  mov     [r14], eax
0x180011975  jz      loc_180011AFB
0x18001197b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011982  cmp     rcx, r12
0x180011985  jz      short loc_180011994
0x180011987  test    dword ptr [rcx+44h], 100h
0x18001198e  jnz     loc_1800120E7
0x180011994  lea     rdx, [rbp+9D0h]
0x18001199b  mov     r9d, 0FDh
0x1800119a1  lea     r8, aMsmsecperformc_0; "MSMSecPerformCapabilityMatch"
0x1800119a8  mov     rcx, rbp
0x1800119ab  call    cs:__imp_ReleaseWriteLock
0x1800119b2  nop     dword ptr [rax+rax+00h]
0x1800119b7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800119be  cmp     rbx, r12
0x1800119c1  jz      short loc_1800119D0
0x1800119c3  test    dword ptr [rbx+44h], 100h
0x1800119ca  jnz     loc_180012106
0x1800119d0  mov     [rsp+0A8h+arg_28], rbp
0x1800119d8  cmp     rbx, r12
0x1800119db  jz      short loc_1800119EA
0x1800119dd  test    dword ptr [rbx+44h], 400h
0x1800119e4  jnz     loc_180012133
0x1800119ea  mov     ebx, esi
0x1800119ec  lock xadd [rbp+10h], ebx
0x1800119f1  dec     ebx
0x1800119f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119fa  cmp     rcx, r12
0x1800119fd  jz      short loc_180011A0C
0x1800119ff  test    dword ptr [rcx+44h], 400h
0x180011a06  jnz     loc_1800121AB
0x180011a0c  test    ebx, ebx
0x180011a0e  jz      loc_180011AD9
0x180011a14  mov     r15, [rsp+0A8h+var_38]
0x180011a19  mov     r14, [rsp+0A8h+var_30]
0x180011a1e  mov     r13, [rsp+0A8h+var_28]
0x180011a26  mov     rbp, [rsp+0A8h+var_20]
0x180011a2e  mov     rbx, [rsp+0A8h+arg_0]
0x180011a36  cmp     rcx, r12
0x180011a39  jz      short loc_180011A48
0x180011a3b  test    dword ptr [rcx+44h], 400h
0x180011a42  jnz     loc_1800121CF
0x180011a48  lock xadd cs:dword_1800AEF94, esi
0x180011a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a57  cmp     rcx, r12
0x180011a5a  jz      short loc_180011A6E
0x180011a5c  test    dword ptr [rcx+44h], 400h
0x180011a63  jnz     loc_1800121F8
0x180011a69  cmp     rcx, r12
0x180011a6c  jnz     short loc_180011A7D
0x180011a6e  mov     eax, edi
0x180011a70  add     rsp, 90h
0x180011a77  pop     r12
0x180011a79  pop     rdi
0x180011a7a  pop     rsi
0x180011a7b  retn
0x180011a7d  test    dword ptr [rcx+44h], 100h
0x180011a84  jz      short loc_180011A6E
0x180011a86  mov     rcx, [rcx+38h]
0x180011a8a  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180011a91  mov     edx, 2Dh ; '-'
0x180011a96  mov     r9d, edi
0x180011a99  call    WPP_SF_d
0x180011a9e  jmp     short loc_180011A6E
0x180011aa0  mov     edi, 57h ; 'W'
0x180011aa5  lea     r12, WPP_GLOBAL_Control
0x180011aac  cmp     rcx, r12
0x180011aaf  jz      loc_180011969
0x180011ab5  test    byte ptr [rcx+44h], 1
0x180011ab9  jz      loc_180011969
0x180011abf  mov     edx, 28h ; '('
0x180011ac4  mov     rcx, [rcx+38h]
0x180011ac8  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180011acf  call    WPP_SF_
0x180011ad4  jmp     loc_1800118E4
0x180011ad9  mov     edx, 1; int
0x180011ade  mov     rcx, rbp; struct MSMSEC_INTF_CONTEXT *
0x180011ae1  call    ?SecMgrMarkDeletedAndDerefAllPorts@@YAKPEAUMSMSEC_INTF_CONTEXT@@H@Z; SecMgrMarkDeletedAndDerefAllPorts(MSMSEC_INTF_CONTEXT *,int)
0x180011ae6  mov     rcx, rbp; struct MSMSEC_INTF_CONTEXT *
0x180011ae9  call    ?SecMgrRemoveAdapterFromDeletedList@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrRemoveAdapterFromDeletedList(MSMSEC_INTF_CONTEXT *)
0x180011aee  lea     rcx, [rsp+0A8h+arg_28]; struct MSMSEC_INTF_CONTEXT **
0x180011af6  call    ?SecMgrDestroyAdapter@@YAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrDestroyAdapter(MSMSEC_INTF_CONTEXT * *)
0x180011afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b02  jmp     loc_180011A14
0x180011b07  mov     rcx, [rcx+38h]
0x180011b0b  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180011b12  mov     edx, 1Eh
0x180011b17  mov     r9d, edi
0x180011b1a  call    WPP_SF_d
0x180011b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b26  jmp     loc_180011879
0x180011b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b32  cmp     rcx, r12
0x180011b35  jz      loc_1800118E4
  ... truncated ...
```
