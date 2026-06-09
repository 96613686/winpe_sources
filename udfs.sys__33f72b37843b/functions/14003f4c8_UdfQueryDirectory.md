# UdfQueryDirectory

- ea: `0x14003f4c8`
- end: `0x140040198`
- name: `UdfQueryDirectory`
- size: `3280`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003f440`

## callees

- `0x1400030e0`
- `0x140008b0c`
- `0x14000a288`
- `0x14000c3e8`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cad4`
- `0x140015dd4`
- `0x14001bc30`
- `0x14001bc60`
- `0x14001bc80`
- `0x14001c080`
- `0x14002fe54`
- `0x14002feb8`
- `0x14002ff18`
- `0x14002ff60`
- `0x14002ffa8`
- `0x14003ebc0`
- `0x14003f360`
- `0x14003f4c8`
- `0x1400401a0`
- `0x140040820`
- `0x1400413f0`
- `0x140045f10`
- `0x1400543e0`
- `0x140055cd0`
- `0x1400567cc`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14003f698`
- `ntoskrnl!ExRaiseStatus` at `0x14003f698`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003f680`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003f680`
- `ntoskrnl!ExReleaseResourceLite` at `0x140040136`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059e79`
- `ntoskrnl!ExReleaseResourceLite` at `0x140040136`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059e79`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400400a0`
- `ntoskrnl!ExAcquireFastMutex` at `0x140059dc9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400400a0`
- `ntoskrnl!ExAcquireFastMutex` at `0x140059dc9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140040115`
- `ntoskrnl!ExReleaseFastMutex` at `0x140059e55`
- `ntoskrnl!ExReleaseFastMutex` at `0x140040115`
- `ntoskrnl!ExReleaseFastMutex` at `0x140059e55`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140059d3c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140059d3c`

## pseudocode

```c
__int64 __fastcall UdfQueryDirectory(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v8; // rbx
  __int64 v9; // r12
  int v11; // r13d
  unsigned int v12; // esi
  unsigned int v13; // r14d
  __int64 v14; // rcx
  BOOLEAN v15; // dl
  __int64 v16; // rcx
  int v17; // r15d
  int v18; // edx
  char *v19; // r12
  char *v20; // rcx
  __int64 v21; // r14
  int v22; // ecx
  unsigned int v23; // edx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  __int64 v28; // rsi
  __int64 v29; // rbx
  char *v30; // rdx
  char *v31; // rcx
  __int64 v32; // rdx
  char *v33; // rax
  char *v34; // rax
  unsigned int v35; // ebx
  _QWORD *v36; // rcx
  char v37; // dl
  char *v38; // rsi
  _QWORD *v39; // rcx
  _QWORD *v40; // rcx
  _QWORD *v41; // rcx
  unsigned __int64 *v42; // rax
  __int16 *v43; // rsi
  unsigned __int64 v44; // r14
  unsigned __int64 *v45; // r8
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rcx
  __int16 v48; // ax
  char *v49; // rsi
  _QWORD *v50; // rcx
  _QWORD *v51; // rcx
  _QWORD *v52; // rcx
  char *v53; // rbx
  _DWORD *v54; // rcx
  char v55; // dl
  __int64 v56; // rdx
  char *v57; // rcx
  unsigned int v58; // ebx
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rcx
  int v63; // eax
  unsigned int v64; // esi
  char *v65; // rcx
  char *v66; // r14
  void *v67; // rcx
  __int64 v68; // rdx
  char v69; // al
  __int64 v70; // rcx
  __int64 v71; // r8
  _BYTE *v72; // rcx
  __int64 v73; // rdx
  char *v74; // rcx
  __int64 v75; // r13
  __int64 v76; // rbx
  struct _KTHREAD *CurrentThread; // r14
  __int64 v78; // r14
  __int64 v79; // rcx
  char v80; // [rsp+40h] [rbp-2B8h] BYREF
  __int16 v81; // [rsp+41h] [rbp-2B7h] BYREF
  int v82; // [rsp+44h] [rbp-2B4h]
  char v83; // [rsp+48h] [rbp-2B0h]
  unsigned int v84; // [rsp+4Ch] [rbp-2ACh]
  unsigned int v85; // [rsp+50h] [rbp-2A8h]
  int v86; // [rsp+54h] [rbp-2A4h]
  int v87; // [rsp+58h] [rbp-2A0h]
  char *v88; // [rsp+60h] [rbp-298h]
  int v89; // [rsp+68h] [rbp-290h]
  char v90; // [rsp+6Ch] [rbp-28Ch]
  unsigned int v91; // [rsp+70h] [rbp-288h]
  unsigned int v92; // [rsp+74h] [rbp-284h]
  __int64 v93; // [rsp+78h] [rbp-280h]
  char *v94; // [rsp+80h] [rbp-278h]
  __int64 v95; // [rsp+88h] [rbp-270h]
  __int64 v96; // [rsp+90h] [rbp-268h]
  __int64 v97; // [rsp+98h] [rbp-260h]
  int v98; // [rsp+A0h] [rbp-258h]
  unsigned int v99; // [rsp+A4h] [rbp-254h]
  __int64 v100; // [rsp+A8h] [rbp-250h]
  __int64 v101; // [rsp+B0h] [rbp-248h]
  __int64 v102; // [rsp+B8h] [rbp-240h]
  __int64 v103; // [rsp+C0h] [rbp-238h]
  __int64 v104; // [rsp+C8h] [rbp-230h]
  __int64 v105; // [rsp+D0h] [rbp-228h]
  __int64 v106; // [rsp+D8h] [rbp-220h]
  __int64 v107; // [rsp+E0h] [rbp-218h]
  int v108; // [rsp+E8h] [rbp-210h]
  _DWORD Size[3]; // [rsp+ECh] [rbp-20Ch]
  _QWORD v110[5]; // [rsp+F8h] [rbp-200h] BYREF
  _QWORD v111[50]; // [rsp+120h] [rbp-1D8h] BYREF

  v103 = a4;
  *(_QWORD *)&Size[1] = a3;
  v96 = a2;
  v8 = a1;
  v95 = a1;
  v106 = a1;
  v93 = a2;
  v110[3] = a3;
  v107 = a4;
  v9 = a5;
  v105 = a5;
  memset(v111, 0, 0x188u);
  v80 = 0;
  v81 = 0;
  v89 = *(_DWORD *)(a3 + 24);
  v108 = v89;
  switch ( v89 )
  {
    case 1:
      v11 = 64;
      break;
    case 2:
      v11 = 68;
      break;
    case 3:
      v11 = 94;
      break;
    case 12:
      v11 = 12;
      break;
    case 37:
      v11 = 104;
      break;
    case 38:
      v11 = 80;
      break;
    default:
      UdfCompleteRequest(v8, a2, 3221225475LL);
      return 3221225475LL;
  }
  v86 = v11;
  v82 = 0;
  v12 = 0;
  v92 = 0;
  v99 = 0;
  v13 = 0;
  v85 = 0;
  v91 = 0;
  v94 = 0;
  v88 = (char *)UdfMapUserBuffer(v8, v96);
  UdfInitializeCompoundDirContext(v14, v111);
  v104 = a4 + 136;
  if ( !v8 || (v15 = 0, (*(_DWORD *)(v8 + 28) & 4) != 0) )
    v15 = 1;
  if ( !ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a4 + 136) + 80LL) + 8LL), v15) )
  {
    *(_DWORD *)(v8 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  UdfVerifyScbOperation(v8, a4, a5);
  v17 = UdfInitializeEnumeration(v8, v111, (__int64)&v80, (__int64)&v81, (__int64)&v81 + 1);
  v82 = v17;
  if ( v17 >= 0 )
  {
    while ( 1 )
    {
      if ( v13 && (_BYTE)v81 )
        goto LABEL_170;
      v110[4] = v111[35];
      v90 = UdfEnumerateIndex(v8);
      v80 = 1;
      if ( !v90 )
      {
        if ( !v13 )
        {
          v17 = -2147483642;
          v82 = -2147483642;
          if ( HIBYTE(v81) )
          {
            v17 = -1073741809;
            v82 = -1073741809;
          }
        }
        goto LABEL_170;
      }
      v100 = v111[4];
      v110[2] = v111[4];
      v18 = LOWORD(v111[8]);
      v84 = LOWORD(v111[8]);
      v98 = LOWORD(v111[8]);
      v16 = *(unsigned int *)(*(_QWORD *)&Size[1] + 8LL);
      if ( v13 > (unsigned int)v16 )
        goto LABEL_27;
      v16 = ((_DWORD)v16 - v13) & 0xFFFFFFFE;
      if ( (unsigned int)LOWORD(v111[8]) + v11 > (unsigned int)v16 )
      {
        if ( v13 )
        {
LABEL_27:
          v80 = 0;
          v17 = 0;
          v82 = 0;
          goto LABEL_170;
        }
        v18 = v16 - v11;
        v84 = v16 - v11;
        v98 = v16 - v11;
        v17 = -2147483643;
        v82 = -2147483643;
        LOBYTE(v81) = 1;
      }
      Size[0] = v18;
      v19 = (char *)(v96 + 64);
      v110[0] = v96 + 64;
      v20 = &v88[v12];
      if ( *(_BYTE *)(v96 + 64) )
        RtlSetUserMemory(v20);
      else
        RtlSetVolatileMemory(v20, 0, v13 + v11 - v12);
      v83 = 0;
      v21 = 0;
      v97 = 0;
      v22 = v89;
      if ( v89 == 12 )
      {
        v23 = v85;
      }
      else
      {
        UdfLookupFileEntryInEnumeration(v8, v103, v111);
        v21 = v111[21];
        v97 = v111[21];
        UdfUpdateTimestampsFromIcbContext(v8, &v111[19], &v111[31]);
        v23 = v85;
        v22 = v89;
      }
      v24 = v22 - 1;
      if ( !v24 || (v25 = v24 - 1) == 0 || (v26 = v25 - 1) == 0 )
      {
LABEL_54:
        v35 = 0;
        v87 = 0;
        v94 = &v88[v23];
        v36 = v94 + 8;
        v37 = *v19;
        if ( !v21 )
        {
          if ( v37 )
            RtlWriteULong64ToUser(v36, UdfCorruptFileTime);
          else
            *v36 = UdfCorruptFileTime;
          v49 = v94;
          v50 = v94 + 32;
          if ( *v19 )
            RtlWriteULong64ToUser(v50, UdfCorruptFileTime);
          else
            *v50 = UdfCorruptFileTime;
          v51 = v49 + 24;
          if ( *v19 )
            RtlWriteULong64ToUser(v51, UdfCorruptFileTime);
          else
            *v51 = UdfCorruptFileTime;
          v52 = v49 + 16;
          if ( *v19 )
            RtlWriteULong64ToUser(v52, UdfCorruptFileTime);
          else
            *v52 = UdfCorruptFileTime;
          goto LABEL_105;
        }
        if ( v37 )
          RtlWriteULong64ToUser(v36, v111[31]);
        else
          *v36 = v111[31];
        v38 = v94;
        v39 = v94 + 16;
        if ( *v19 )
          RtlWriteULong64ToUser(v39, v111[32]);
        else
          *v39 = v111[32];
        v40 = v38 + 24;
        if ( *v19 )
          RtlWriteULong64ToUser(v40, v111[33]);
        else
          *v40 = v111[33];
        v41 = v38 + 32;
        if ( *v19 )
          RtlWriteULong64ToUser(v41, v111[34]);
        else
          *v41 = v111[34];
        v42 = (unsigned __int64 *)(v38 + 40);
        if ( *(_BYTE *)(v21 + 27) == 4 )
        {
          if ( *v19 )
            RtlWriteULong64ToUser(v38 + 40, 0);
          else
            *v42 = 0;
          if ( *v19 )
            RtlWriteULong64ToUser(v38 + 48, 0);
          else
            *((_QWORD *)v38 + 6) = 0;
          v35 = 16;
          v87 = 16;
          v43 = (__int16 *)(v21 + 34);
LABEL_87:
          v48 = *v43;
          if ( (*v43 & 0x400) != 0 )
          {
            v35 |= 4u;
            v87 = v35;
          }
          if ( (v48 & 0x20) != 0 )
          {
            v35 |= 0x20u;
            v87 = v35;
          }
          if ( (*(_DWORD *)(v21 + 44) & 0x4210) == 0 || (*(_DWORD *)(v21 + 44) & 0x842) == 0 )
          {
            v35 |= 1u;
            v87 = v35;
          }
LABEL_105:
          v28 = v100;
          if ( v100 && (*(_BYTE *)(v100 + 18) & 1) != 0 )
          {
            v35 |= 2u;
            v87 = v35;
          }
          if ( !v35 )
            v35 = 128;
          v87 = v35;
          if ( *v19 )
            RtlWriteULongToUser(v94 + 56, v35);
          else
            *((_DWORD *)v94 + 14) = v35;
          v53 = v94;
          v54 = v94 + 4;
          v55 = *v19;
          if ( HIDWORD(v111[35]) )
          {
            if ( v55 )
            {
              v56 = 0;
LABEL_119:
              RtlWriteULongToUser(v54, v56);
            }
            else
            {
              *v54 = 0;
            }
          }
          else
          {
            if ( v55 )
            {
              v56 = LODWORD(v111[35]);
              goto LABEL_119;
            }
            *v54 = v111[35];
          }
          if ( *v19 )
            RtlWriteULongToUser(v53 + 60, v84);
          else
            *((_DWORD *)v53 + 15) = v84;
          goto LABEL_124;
        }
        v44 = *(_QWORD *)(v21 + 56);
        if ( *v19 )
          RtlWriteULong64ToUser(v38 + 40, v44);
        else
          *v42 = v44;
        v45 = (unsigned __int64 *)(v38 + 48);
        v43 = (__int16 *)(v97 + 34);
        if ( (*(_BYTE *)(v97 + 34) & 7) == 3 )
        {
          if ( *v19 )
          {
            v46 = v44;
            goto LABEL_81;
          }
          *v45 = v44;
        }
        else
        {
          v47 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v104 + 8LL) + 68LL) - 1);
          if ( *v19 )
          {
            v46 = v47 & (v44 + (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v104 + 8LL) + 68LL) - 1));
LABEL_81:
            RtlWriteULong64ToUser(v45, v46);
          }
          else
          {
            *v45 = v47 & (v44 + (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v104 + 8LL) + 68LL) - 1));
          }
        }
        v21 = v97;
        goto LABEL_87;
      }
      v27 = v26 - 9;
      if ( !v27 )
        break;
      if ( (unsigned int)(v27 - 25) < 2 )
        goto LABEL_54;
LABEL_42:
      v28 = v100;
LABEL_124:
      v30 = v88;
LABEL_125:
      v57 = (char *)(unsigned int)(v89 - 37);
      if ( v89 == 37 )
      {
        v58 = v85;
        if ( v28 )
        {
          v102 = 0;
          LODWORD(v102) = *(_DWORD *)(v28 + 24);
          v63 = *(unsigned __int16 *)(v28 + 28);
          HIDWORD(v102) = v63;
          if ( v21 && *(_BYTE *)(v21 + 27) == 4 )
            HIDWORD(v102) = v63 | 0x80000000;
          v57 = &v30[v85 + 96];
          if ( !*v19 )
          {
            v61 = v102;
            goto LABEL_142;
          }
          v60 = v102;
          goto LABEL_146;
        }
        v62 = v85 + 96LL;
        goto LABEL_144;
      }
      if ( v89 == 38 )
      {
        v58 = v85;
        if ( v28 )
        {
          v101 = 0;
          LODWORD(v101) = *(_DWORD *)(v28 + 24);
          v59 = *(unsigned __int16 *)(v28 + 28);
          HIDWORD(v101) = v59;
          if ( v21 && *(_BYTE *)(v21 + 27) == 4 )
            HIDWORD(v101) = v59 | 0x80000000;
          v57 = &v30[v85 + 72];
          if ( !*v19 )
          {
            v61 = v101;
LABEL_142:
            *(_QWORD *)v57 = v61;
            goto LABEL_148;
          }
          v60 = v101;
          goto LABEL_146;
        }
        v62 = v85 + 72LL;
LABEL_144:
        v57 = &v30[v62];
        v61 = *(_QWORD *)(v103 + 184);
        if ( !*v19 )
          goto LABEL_142;
        v60 = *(_QWORD *)(v103 + 184);
LABEL_146:
        RtlWriteULong64ToUser(v57, v60);
        goto LABEL_148;
      }
      v58 = v85;
LABEL_148:
      v64 = v84;
      if ( v84 )
      {
        v65 = &v88[v58 + v11];
        if ( *v19 )
          RtlCopyToUser(v65, (void *)v111[9], Size[0]);
        else
          RtlCopyVolatileMemory(v65, (const void *)v111[9], Size[0]);
      }
      if ( !v17 && (v89 == 3 || v89 == 37) && (v111[7] & 1) != 0 )
      {
        if ( LOWORD(v111[14]) )
        {
          v66 = v94;
          v67 = v94 + 70;
          if ( *v19 )
            RtlCopyToUser(v67, (void *)v111[15], LOWORD(v111[14]));
          else
            RtlCopyVolatileMemory(v67, (const void *)v111[15], LOWORD(v111[14]));
          v69 = v111[14];
          goto LABEL_163;
        }
        if ( !(unsigned __int8)UdfIs8dot3Name(v57, &v111[8]) )
        {
          v110[0] = 1572864;
          v66 = v94;
          v110[1] = v94 + 70;
          LOBYTE(v71) = *v19;
          UdfGenerate8dot3Name(v70, &v111[12], v71, v110);
          v69 = v110[0];
LABEL_163:
          v72 = v66 + 68;
          if ( *v19 )
          {
            LOBYTE(v68) = v69;
            RtlWriteUCharToUser(v72, v68);
          }
          else
          {
            *v72 = v69;
          }
        }
      }
      v12 = v58 + v11 + v64;
      v92 = v12;
      v73 = v58 - v99;
      v74 = &v88[v99];
      if ( *v19 )
        RtlWriteULongToUser(v74, v73);
      else
        *(_DWORD *)v74 = v73;
      HIBYTE(v81) = 0;
      v99 = v58;
      v13 = (v12 + 7) & 0xFFFFFFF8;
      v85 = v13;
      v91 = v13;
      v8 = v95;
      UdfCleanupIcbContext(v95, &v111[19]);
      v9 = v105;
    }
    v29 = v23;
    v30 = v88;
    if ( HIDWORD(v111[35]) )
    {
      v33 = &v88[v29];
      if ( !*v19 )
      {
        *((_DWORD *)v33 + 1) = 0;
        goto LABEL_51;
      }
      v32 = 0;
      v31 = v33 + 4;
    }
    else
    {
      v31 = &v88[v29 + 4];
      if ( !*v19 )
      {
        *(_DWORD *)v31 = v111[35];
LABEL_51:
        v34 = &v30[v29];
        if ( !*v19 )
        {
          *((_DWORD *)v34 + 2) = v84;
          v28 = v100;
          goto LABEL_125;
        }
        RtlWriteULongToUser(v34 + 8, v84);
        goto LABEL_42;
      }
      v32 = LODWORD(v111[35]);
    }
    RtlWriteULongToUser(v31, v32);
    v30 = v88;
    goto LABEL_51;
  }
LABEL_170:
  v75 = v95;
  v76 = v111[35];
  v93 = v111[35];
  UdfCleanupDirContext(v16, v111);
  UdfCleanupIcbContext(v75, &v111[19]);
  if ( (v17 & 0xC0000000) == 0xC0000000 )
  {
    v78 = v104;
  }
  else
  {
    CurrentThread = KeGetCurrentThread();
    if ( CurrentThread != *(struct _KTHREAD **)(*(_QWORD *)v104 + 64LL) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)v104 + 80LL) + 216LL));
      *(_QWORD *)(*(_QWORD *)v104 + 64LL) = CurrentThread;
    }
    v78 = v104;
    ++*(_DWORD *)(*(_QWORD *)v104 + 72LL);
    *(_QWORD *)(v9 + 32) = v76;
    if ( !HIDWORD(v93) && (unsigned int)v76 > *(_DWORD *)(v9 + 56) )
      *(_DWORD *)(v9 + 56) = v76;
    *(_DWORD *)(v9 + 4) &= ~0x40000u;
    if ( v80 )
      *(_DWORD *)(v9 + 4) |= 0x40000u;
    if ( !--*(_DWORD *)(*(_QWORD *)v78 + 72LL) )
    {
      *(_QWORD *)(*(_QWORD *)v78 + 64LL) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)v78 + 80LL) + 216LL));
    }
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)v78 + 80LL) + 8LL));
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x80u) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 12, WPP_ebe251be81c330568a1711593312097c_Traceguids);
  }
  v79 = v96;
  *(_QWORD *)(v96 + 56) = v12;
  UdfCompleteRequest(v75, v79, (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14003f4c8  push    rbx
0x14003f4ca  push    rsi
0x14003f4cb  push    rdi
0x14003f4cc  push    r12
0x14003f4ce  push    r13
0x14003f4d0  push    r14
0x14003f4d2  push    r15
0x14003f4d4  sub     rsp, 2C0h
0x14003f4db  mov     rax, cs:__security_cookie
0x14003f4e2  xor     rax, rsp
0x14003f4e5  mov     [rsp+2F8h+var_48], rax
0x14003f4ed  mov     r15, r9
0x14003f4f0  mov     [rsp+2F8h+var_238], r9
0x14003f4f8  mov     r14, r8
0x14003f4fb  mov     qword ptr [rsp+2F8h+Size+4], r8
0x14003f503  mov     rsi, rdx
0x14003f506  mov     [rsp+2F8h+var_268], rdx
0x14003f50e  mov     rbx, rcx
0x14003f511  mov     [rsp+2F8h+var_270], rcx
0x14003f519  mov     [rsp+2F8h+var_220], rcx
0x14003f521  mov     [rsp+2F8h+var_280], rdx
0x14003f526  mov     [rsp+2F8h+var_1E8], r8
0x14003f52e  mov     [rsp+2F8h+var_218], r9
0x14003f536  mov     r12, [rsp+2F8h+arg_20]
0x14003f53e  mov     [rsp+2F8h+var_228], r12
0x14003f546  xor     edx, edx; Val
0x14003f548  mov     r8d, 188h; Size
0x14003f54e  lea     rcx, [rsp+2F8h+var_1D8]; void *
0x14003f556  call    memset
0x14003f55b  xor     edi, edi
0x14003f55d  mov     byte ptr [rsp+2F8h+var_2B8+2], dil
0x14003f562  mov     byte ptr [rsp+2F8h+var_2B8], dil
0x14003f567  mov     byte ptr [rsp+2F8h+var_2B8+1], dil
0x14003f56c  mov     ecx, [r14+18h]
0x14003f570  mov     [rsp+2F8h+var_290], ecx
0x14003f574  mov     [rsp+2F8h+var_210], ecx
0x14003f57b  mov     r8d, ecx
0x14003f57e  sub     r8d, 1
0x14003f582  jz      short loc_14003F603
0x14003f584  sub     r8d, 1
0x14003f588  jz      short loc_14003F5FB
0x14003f58a  sub     r8d, 1
0x14003f58e  jz      short loc_14003F5F3
0x14003f590  sub     r8d, 9
0x14003f594  jz      short loc_14003F5EB
0x14003f596  sub     r8d, 19h
0x14003f59a  jz      short loc_14003F5E3
0x14003f59c  cmp     r8d, 1
0x14003f5a0  jz      short loc_14003F5DB
0x14003f5a2  mov     edi, 0C0000003h
0x14003f5a7  mov     r8d, edi
0x14003f5aa  mov     rdx, rsi
0x14003f5ad  mov     rcx, rbx
0x14003f5b0  call    UdfCompleteRequest
0x14003f5b5  mov     eax, edi
0x14003f5b7  mov     rcx, [rsp+2F8h+var_48]
0x14003f5bf  xor     rcx, rsp; StackCookie
0x14003f5c2  call    __security_check_cookie
0x14003f5c7  add     rsp, 2C0h
0x14003f5ce  pop     r15
0x14003f5d0  pop     r14
0x14003f5d2  pop     r13
0x14003f5d4  pop     r12
0x14003f5d6  pop     rdi
0x14003f5d7  pop     rsi
0x14003f5d8  pop     rbx
0x14003f5d9  retn
0x14003f5db  mov     r13d, 50h ; 'P'
0x14003f5e1  jmp     short loc_14003F609
0x14003f5e3  mov     r13d, 68h ; 'h'
0x14003f5e9  jmp     short loc_14003F609
0x14003f5eb  mov     r13d, 0Ch
0x14003f5f1  jmp     short loc_14003F609
0x14003f5f3  mov     r13d, 5Eh ; '^'
0x14003f5f9  jmp     short loc_14003F609
0x14003f5fb  mov     r13d, 44h ; 'D'
0x14003f601  jmp     short loc_14003F609
0x14003f603  mov     r13d, 40h ; '@'
0x14003f609  mov     [rsp+2F8h+var_2A4], r13d
0x14003f60e  mov     dword ptr [rsp+2F8h+var_2B8+4], edi
0x14003f612  mov     esi, edi
0x14003f614  mov     [rsp+2F8h+var_284], edi
0x14003f618  mov     [rsp+2F8h+var_254], edi
0x14003f61f  mov     r14d, edi
0x14003f622  mov     [rsp+2F8h+var_2A8], edi
0x14003f626  mov     [rsp+2F8h+var_288], edi
0x14003f62a  mov     [rsp+2F8h+var_278], rdi
0x14003f632  mov     rdx, [rsp+2F8h+var_268]
0x14003f63a  mov     rcx, rbx
0x14003f63d  call    UdfMapUserBuffer
0x14003f642  mov     [rsp+2F8h+var_298], rax
0x14003f647  lea     rdx, [rsp+2F8h+var_1D8]
0x14003f64f  call    UdfInitializeCompoundDirContext
0x14003f654  lea     rax, [r15+88h]
0x14003f65b  mov     [rsp+2F8h+var_230], rax
0x14003f663  mov     rcx, [rax]
0x14003f666  mov     r8, [rcx+50h]
0x14003f66a  test    rbx, rbx
0x14003f66d  jz      short loc_14003F67A
0x14003f66f  mov     dl, dil
0x14003f672  mov     ecx, [rbx+1Ch]
0x14003f675  test    cl, 4
0x14003f678  jz      short loc_14003F67C
0x14003f67a  mov     dl, 1; Wait
0x14003f67c  lea     rcx, [r8+8]; Resource
0x14003f680  call    cs:__imp_ExAcquireResourceSharedLite
0x14003f687  nop     dword ptr [rax+rax+00h]
0x14003f68c  test    al, al
0x14003f68e  jnz     short loc_14003F6A5
0x14003f690  mov     ecx, 0C00000D8h; Status
0x14003f695  mov     [rbx+18h], ecx
0x14003f698  call    cs:__imp_ExRaiseStatus
0x14003f6a5  mov     r8, r12
0x14003f6a8  mov     rdx, r15
0x14003f6ab  mov     rcx, rbx
0x14003f6ae  call    UdfVerifyScbOperation
0x14003f6b3  lea     rax, [rsp+2F8h+var_2B8+2]
0x14003f6b8  mov     [rsp+2F8h+var_2C0], rax; __int64
0x14003f6bd  lea     rax, [rsp+2F8h+var_2B8+1]
0x14003f6c2  mov     [rsp+2F8h+var_2C8], rax; __int64
0x14003f6c7  lea     rax, [rsp+2F8h+var_2B8]
0x14003f6cc  mov     [rsp+2F8h+var_2D0], rax; __int64
0x14003f6d1  lea     rax, [rsp+2F8h+var_1D8]
0x14003f6d9  mov     [rsp+2F8h+var_2D8], rax; void *
0x14003f6de  mov     r9, r12
0x14003f6e1  mov     r8, r15
0x14003f6e4  mov     rdx, qword ptr [rsp+2F8h+Size+4]
0x14003f6ec  mov     rcx, rbx; int
0x14003f6ef  call    UdfInitializeEnumeration
0x14003f6f4  mov     r15d, eax
0x14003f6f7  mov     dword ptr [rsp+2F8h+var_2B8+4], eax
0x14003f6fb  test    eax, eax
0x14003f6fd  js      loc_140040037
0x14003f703  test    r14d, r14d
0x14003f706  jz      short loc_14003F713
0x14003f708  cmp     byte ptr [rsp+2F8h+var_2B8+1], dil
0x14003f70d  jnz     loc_140040037
0x14003f713  mov     rax, [rsp+2F8h+var_C0]
0x14003f71b  mov     [rsp+2F8h+var_1E0], rax
0x14003f723  mov     r9b, byte ptr [rsp+2F8h+var_2B8]
0x14003f728  lea     r8, [rsp+2F8h+var_1D8]
0x14003f730  mov     rdx, r12
0x14003f733  mov     rcx, rbx; int
0x14003f736  call    UdfEnumerateIndex
0x14003f73b  mov     [rsp+2F8h+var_28C], al
0x14003f73f  mov     byte ptr [rsp+2F8h+var_2B8], 1
0x14003f744  test    al, al
0x14003f746  jnz     short loc_14003F777
0x14003f748  test    r14d, r14d
0x14003f74b  jnz     loc_140040037
0x14003f751  mov     r15d, 80000006h
0x14003f757  mov     dword ptr [rsp+2F8h+var_2B8+4], r15d
0x14003f75c  cmp     byte ptr [rsp+2F8h+var_2B8+2], dil
0x14003f761  jz      loc_140040037
0x14003f767  mov     r15d, 0C000000Fh
0x14003f76d  mov     dword ptr [rsp+2F8h+var_2B8+4], r15d
0x14003f772  jmp     loc_140040037
0x14003f777  mov     rax, [rsp+2F8h+var_1B8]
0x14003f77f  mov     [rsp+2F8h+var_250], rax
0x14003f787  mov     [rsp+2F8h+var_1F0], rax
0x14003f78f  movzx   edx, [rsp+2F8h+var_198]
0x14003f797  mov     [rsp+2F8h+var_2AC], edx
0x14003f79b  mov     [rsp+2F8h+var_258], edx
0x14003f7a2  mov     rax, qword ptr [rsp+2F8h+Size+4]
0x14003f7aa  mov     ecx, [rax+8]
0x14003f7ad  cmp     r14d, ecx
0x14003f7b0  jbe     short loc_14003F7C3
0x14003f7b2  mov     byte ptr [rsp+2F8h+var_2B8], dil
0x14003f7b7  mov     r15d, edi
0x14003f7ba  mov     dword ptr [rsp+2F8h+var_2B8+4], edi
0x14003f7be  jmp     loc_140040037
0x14003f7c3  sub     ecx, r14d
0x14003f7c6  and     ecx, 0FFFFFFFEh
0x14003f7c9  lea     eax, [rdx+r13]
0x14003f7cd  cmp     eax, ecx
0x14003f7cf  jbe     short loc_14003F7F6
0x14003f7d1  test    r14d, r14d
0x14003f7d4  jnz     short loc_14003F7B2
0x14003f7d6  mov     edx, ecx
0x14003f7d8  sub     edx, r13d
0x14003f7db  mov     [rsp+2F8h+var_2AC], edx
0x14003f7df  mov     [rsp+2F8h+var_258], edx
0x14003f7e6  mov     r15d, 80000005h
0x14003f7ec  mov     dword ptr [rsp+2F8h+var_2B8+4], r15d
0x14003f7f1  mov     byte ptr [rsp+2F8h+var_2B8+1], 1
0x14003f7f6  mov     dword ptr [rsp+2F8h+Size], edx
0x14003f7fd  mov     r12, [rsp+2F8h+var_268]
0x14003f805  add     r12, 40h ; '@'
0x14003f809  mov     qword ptr [rsp+2F8h+var_200], r12
0x14003f811  mov     r8d, r13d
0x14003f814  sub     r8d, esi
0x14003f817  add     r8d, r14d; Size
0x14003f81a  mov     eax, esi
0x14003f81c  mov     rcx, [rsp+2F8h+var_298]
0x14003f821  add     rcx, rax; void *
0x14003f824  xor     edx, edx; Val
0x14003f826  cmp     [r12], dil
0x14003f82a  jz      short loc_14003F833
0x14003f82c  call    RtlSetUserMemory
0x14003f831  jmp     short loc_14003F838
0x14003f833  call    RtlSetVolatileMemory
0x14003f838  mov     sil, dil
0x14003f83b  mov     [rsp+2F8h+var_2B0], dil
0x14003f840  mov     r14, rdi
0x14003f843  mov     [rsp+2F8h+var_260], rdi
0x14003f84b  mov     ecx, [rsp+2F8h+var_290]
0x14003f84f  cmp     ecx, 0Ch
0x14003f852  jz      loc_14003F982
0x14003f858  lea     r8, [rsp+2F8h+var_1D8]
0x14003f860  mov     rdx, [rsp+2F8h+var_238]
0x14003f868  mov     rcx, rbx
0x14003f86b  call    UdfLookupFileEntryInEnumeration
0x14003f870  mov     r14, [rsp+2F8h+var_130]
0x14003f878  mov     [rsp+2F8h+var_260], r14
0x14003f880  lea     r8, [rsp+2F8h+var_E0]
0x14003f888  lea     rdx, [rsp+2F8h+var_140]
0x14003f890  mov     rcx, rbx
0x14003f893  call    UdfUpdateTimestampsFromIcbContext
0x14003f898  mov     edx, [rsp+2F8h+var_2A8]
0x14003f89c  mov     ecx, [rsp+2F8h+var_290]
0x14003f8a0  jmp     loc_14003F986
0x14003f8a5  lea     rax, WPP_GLOBAL_Control
0x14003f8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f8b3  cmp     rcx, rax
0x14003f8b6  jz      short loc_14003F8E9
0x14003f8b8  mov     eax, [rcx+2Ch]
0x14003f8bb  test    al, al
0x14003f8bd  jns     short loc_14003F8E9
0x14003f8bf  mov     edx, 0Bh
0x14003f8c4  mov     rbx, [rsp+2F8h+var_218]
0x14003f8cc  mov     [rsp+2F8h+var_238], rbx
0x14003f8d4  mov     r9, rbx
0x14003f8d7  lea     r8, WPP_ebe251be81c330568a1711593312097c_Traceguids
0x14003f8de  mov     rcx, [rcx+18h]
0x14003f8e2  call    WPP_SF_q
0x14003f8e7  jmp     short loc_14003F8F9
0x14003f8e9  mov     rax, [rsp+2F8h+var_218]
0x14003f8f1  mov     [rsp+2F8h+var_238], rax
0x14003f8f9  mov     r13, [rsp+2F8h+var_220]
0x14003f901  mov     [rsp+2F8h+var_270], r13
0x14003f909  mov     dword ptr [r13+18h], 0
0x14003f911  mov     sil, 1
0x14003f914  mov     [rsp+2F8h+var_2B0], sil
0x14003f919  xor     edi, edi
0x14003f91b  mov     r15d, dword ptr [rsp+2F8h+var_2B8+4]
0x14003f920  mov     edx, [rsp+2F8h+var_288]
0x14003f924  mov     [rsp+2F8h+var_2A8], edx
0x14003f928  mov     eax, [rsp+2F8h+var_258]
0x14003f92f  mov     [rsp+2F8h+var_2AC], eax
0x14003f933  mov     rax, [rsp+2F8h+var_1F0]
0x14003f93b  mov     [rsp+2F8h+var_250], rax
0x14003f943  mov     r13d, [rsp+2F8h+var_2A4]
0x14003f948  mov     ecx, [rsp+2F8h+var_210]
0x14003f94f  mov     [rsp+2F8h+var_290], ecx
0x14003f953  mov     r12, qword ptr [rsp+2F8h+var_200]
0x14003f95b  mov     rax, [rsp+2F8h+var_280]
0x14003f960  mov     [rsp+2F8h+var_268], rax
0x14003f968  mov     rax, [rsp+2F8h+var_1E8]
0x14003f970  mov     qword ptr [rsp+2F8h+Size+4], rax
0x14003f978  mov     r14, [rsp+2F8h+var_260]
0x14003f980  jmp     short loc_14003F986
0x14003f982  mov     edx, [rsp+2F8h+var_2A8]
0x14003f986  sub     ecx, 1
0x14003f989  jz      loc_14003FA3E
0x14003f98f  sub     ecx, 1
0x14003f992  jz      loc_14003FA3E
0x14003f998  sub     ecx, 1
0x14003f99b  jz      loc_14003FA3E
0x14003f9a1  sub     ecx, 9
0x14003f9a4  jz      short loc_14003F9C5
0x14003f9a6  sub     ecx, 19h
0x14003f9a9  jz      loc_14003FA3E
0x14003f9af  cmp     ecx, 1
0x14003f9b2  jz      loc_14003FA3E
0x14003f9b8  mov     rsi, [rsp+2F8h+var_250]
0x14003f9c0  jmp     loc_14003FD0C
0x14003f9c5  mov     ebx, edx
0x14003f9c7  mov     rdx, [rsp+2F8h+var_298]
0x14003f9cc  cmp     dword ptr [rsp+2F8h+var_C0+4], edi
0x14003f9d3  jnz     short loc_14003F9F2
0x14003f9d5  mov     rax, [rsp+2F8h+var_C0]
0x14003f9dd  lea     rcx, [rdx+4]
0x14003f9e1  add     rcx, rbx
0x14003f9e4  cmp     [r12], dil
0x14003f9e8  jz      short loc_14003F9EE
0x14003f9ea  mov     edx, eax
0x14003f9ec  jmp     short loc_14003FA02
0x14003f9ee  mov     [rcx], eax
0x14003f9f0  jmp     short loc_14003FA11
0x14003f9f2  lea     rax, [rbx+rdx]
0x14003f9f6  cmp     [r12], dil
0x14003f9fa  jz      short loc_14003FA0E
0x14003f9fc  xor     edx, edx
0x14003f9fe  lea     rcx, [rax+4]
0x14003fa02  call    RtlWriteULongToUser
0x14003fa07  mov     rdx, [rsp+2F8h+var_298]
0x14003fa0c  jmp     short loc_14003FA11
0x14003fa0e  mov     [rax+4], edi
0x14003fa11  lea     rax, [rbx+rdx]
0x14003fa15  cmp     [r12], dil
  ... truncated ...
```
