# RaidAcquireNvmeIceKeyResources

- ea: `0x140095af0`
- end: `0x140096314`
- name: `RaidAcquireNvmeIceKeyResources`
- size: `2084`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x1400097d0`

## callees

- `0x14000befc`
- `0x14000d660`
- `0x1400290b0`
- `0x140070754`
- `0x140095af0`
- `0x140096ab8`
- `0x140097684`
- `0x1400d23c0`
- `0x1400dfda8`
- `0x14014b400`
- `0x14014b440`
- `0x14014b500`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140096004`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096004`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x140095b47`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x140095b47`
- `ntoskrnl!ExReleaseSpinLockSharedFromDpcLevel` at `0x140095c86`
- `ntoskrnl!ExReleaseSpinLockSharedFromDpcLevel` at `0x1400962d9`
- `ntoskrnl!ExReleaseSpinLockSharedFromDpcLevel` at `0x140095c86`
- `ntoskrnl!ExReleaseSpinLockSharedFromDpcLevel` at `0x1400962d9`
- `ntoskrnl!ExAcquireSpinLockSharedAtDpcLevel` at `0x140095c5c`
- `ntoskrnl!ExAcquireSpinLockSharedAtDpcLevel` at `0x140095c5c`
- `ntoskrnl!ExAcquireSpinLockExclusiveAtDpcLevel` at `0x140095c95`
- `ntoskrnl!ExAcquireSpinLockExclusiveAtDpcLevel` at `0x140095c95`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140095d50`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140096046`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140095d50`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140096046`
- `ntoskrnl!KeBugCheckEx` at `0x140095fd6`
- `ntoskrnl!KeBugCheckEx` at `0x140095fd6`
- `ntoskrnl!KeSweepLocalCaches` at `0x140095f47`
- `ntoskrnl!KeSweepLocalCaches` at `0x140095f47`

## string_xrefs

- `0x140095e6f`: `NVMe ICE ConfigureCapability returned a transient error.`
- `0x140095e87`: `Failed to configure NVMe ICE capability.`

## pseudocode

```c
__int64 __fastcall RaidAcquireNvmeIceKeyResources(__int64 a1, __int64 a2)
{
  int v2; // eax
  __int64 v4; // r15
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int AdapterCryptoEngineExtension; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  ULONG_PTR v12; // r14
  __int64 v13; // r13
  __int64 v14; // r8
  volatile LONG *v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r9
  volatile LONG *v18; // r12
  unsigned int NvmeIceKeyIndex; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r9
  unsigned __int64 v30; // r13
  __int64 v31; // r10
  __int64 v32; // rbx
  __int64 v33; // rcx
  unsigned int v34; // eax
  __int64 v35; // rdx
  const wchar_t *v36; // r9
  __int64 v37; // rcx
  __int64 (__fastcall *v38)(_QWORD, int *); // rax
  __int64 v39; // r8
  _QWORD *v40; // rdx
  const wchar_t *v41; // r9
  _QWORD *v42; // rdx
  const wchar_t *v43; // r9
  __int64 v44; // rdi
  __int64 v45; // rbx
  size_t v46; // r8
  const void *v47; // rdx
  _BYTE *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r14
  __int64 v51; // r9
  __int64 v52; // rax
  ULONG_PTR BugCheckParameter4; // rbx
  unsigned int v54; // eax
  void *v55; // rcx
  __int64 Pool; // rax
  __int64 v57; // rcx
  unsigned int v58; // eax
  __int64 v59; // rcx
  _BYTE *v60; // rax
  int v61; // edx
  _OWORD *v62; // rax
  __int64 v63; // rdi
  __int64 v64; // r14
  int v65; // edx
  __int64 v66; // r8
  int v67; // ecx
  __int64 v68; // rax
  __int64 v69; // rdi
  __int64 v70; // r14
  int v71; // edx
  __int64 v72; // r8
  int v73; // ecx
  __int64 v74; // rax
  unsigned int v76; // [rsp+30h] [rbp-49h] BYREF
  _QWORD *v77; // [rsp+38h] [rbp-41h]
  __int64 *v78; // [rsp+40h] [rbp-39h] BYREF
  __int64 v79; // [rsp+48h] [rbp-31h]
  int v80; // [rsp+50h] [rbp-29h] BYREF
  __int64 v81; // [rsp+58h] [rbp-21h]
  _BYTE *v82; // [rsp+60h] [rbp-19h]
  __int64 v83; // [rsp+68h] [rbp-11h]
  __int64 v84; // [rsp+70h] [rbp-9h]
  _OWORD *v85; // [rsp+78h] [rbp-1h]
  int v86; // [rsp+80h] [rbp+7h] BYREF
  __int16 v87; // [rsp+84h] [rbp+Bh]
  __int16 v88; // [rsp+86h] [rbp+Dh]
  int v89; // [rsp+88h] [rbp+Fh]
  __int64 v90; // [rsp+8Ch] [rbp+13h]

  v2 = *(_DWORD *)(a1 + 932);
  v4 = *(_QWORD *)(a1 + 24);
  v81 = a1;
  LODWORD(v82) = v2;
  v6 = *(_QWORD *)(a2 + 160);
  v78 = 0;
  v80 = 0;
  AdapterCryptoEngineExtension = IoGetAdapterCryptoEngineExtension(v6, &v78);
  if ( (AdapterCryptoEngineExtension & 0x80000000) != 0 )
    return 0;
  if ( !v78 )
    return 0;
  v12 = v78[1];
  if ( !v12 )
    return 0;
  if ( !*(_DWORD *)v12 || *(_DWORD *)(v12 + 4) < 0x48u )
    return (unsigned int)-1073741811;
  if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v8, v7, v10, v11) )
  {
    v13 = *(_QWORD *)(v4 + 6256);
    v14 = *(unsigned int *)(v12 + 20);
    v77 = (_QWORD *)v13;
    v15 = (volatile LONG *)(v13 + 64);
    v16 = *(unsigned int *)(v13 + 68);
    if ( (unsigned int)v14 > (unsigned int)v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qLL(WPP_GLOBAL_Control->AttachedDevice, v16, v14, v4, v14, *(_DWORD *)(v13 + 68));
      }
      return (unsigned int)-1073741811;
    }
LABEL_19:
    v18 = v15 + 6;
    ExAcquireSpinLockSharedAtDpcLevel(v15 + 6);
    v85 = (_OWORD *)(v12 + 24);
    NvmeIceKeyIndex = RaidGetNvmeIceKeyIndex(v15, v12 + 24);
    if ( NvmeIceKeyIndex != *v15 )
    {
      v69 = *((_QWORD *)v15 + 2);
      v70 = 9LL * NvmeIceKeyIndex;
      if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v21, v20, v22, v23) )
      {
        v71 = *(_DWORD *)(v69 + 8 * v70 + 64);
        v72 = *(_QWORD *)(v69 + 8 * v70 + 56);
      }
      else
      {
        v71 = -1;
        v72 = *(_QWORD *)(*(_QWORD *)(v69 + 8 * v70 + 48) + 8LL);
      }
      v73 = *(_DWORD *)(v69 + 8 * v70);
      v74 = *v78;
      *(_DWORD *)(a2 + 808) = 4718593;
      *(_QWORD *)(a2 + 824) = v72;
      *(_DWORD *)(a2 + 880) = v71;
      *(_QWORD *)(a2 + 832) = v74;
      *(_DWORD *)(a2 + 800) = v73;
      _InterlockedAdd((volatile signed __int32 *)(v69 + 8 * v70 + 36), 1u);
      ExReleaseSpinLockSharedFromDpcLevel(v18);
      return AdapterCryptoEngineExtension;
    }
    ExReleaseSpinLockSharedFromDpcLevel(v15 + 6);
    ExAcquireSpinLockExclusiveAtDpcLevel(v15 + 6);
    v24 = RaidGetNvmeIceKeyIndex(v15, v12 + 24);
    v28 = *(unsigned int *)v15;
    if ( v24 != (_DWORD)v28 )
    {
      v63 = *((_QWORD *)v15 + 2);
      v64 = 9LL * v24;
      if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v25, v28, v26, v27) )
      {
        v65 = *(_DWORD *)(v63 + 8 * v64 + 64);
        v66 = *(_QWORD *)(v63 + 8 * v64 + 56);
      }
      else
      {
        v65 = -1;
        v66 = *(_QWORD *)(*(_QWORD *)(v63 + 8 * v64 + 48) + 8LL);
      }
      v67 = *(_DWORD *)(v63 + 8 * v64);
      v68 = *v78;
      *(_DWORD *)(a2 + 808) = 4718593;
      *(_QWORD *)(a2 + 824) = v66;
      *(_DWORD *)(a2 + 880) = v65;
      *(_QWORD *)(a2 + 832) = v68;
      *(_DWORD *)(a2 + 800) = v67;
      _InterlockedAdd((volatile signed __int32 *)(v63 + 8 * v64 + 36), 1u);
      goto LABEL_61;
    }
    LOBYTE(v26) = *((_BYTE *)v15 + 8);
    v29 = 0;
    v76 = 0;
    if ( (v26 & 1) == 0 )
    {
      v30 = 0;
      LODWORD(v79) = 0;
      if ( (_DWORD)v28 )
      {
        v31 = *((_QWORD *)v15 + 2);
        while ( 1 )
        {
          v25 = 9 * v30;
          if ( (*(_BYTE *)(v31 + 72 * v30 + 68) & 1) == 0 )
            break;
          v30 = (unsigned int)(v30 + 1);
          LODWORD(v79) = v30;
          if ( (unsigned int)v30 >= (unsigned int)v28 )
            goto LABEL_26;
        }
LABEL_31:
        if ( (_DWORD)v30 == *v15 )
        {
          ++*((_DWORD *)v15 + 7);
          ExReleaseSpinLockExclusiveFromDpcLevel(v15 + 6);
          v32 = v81;
          StorpTelemetryNvmeIceKeySlotFull(v81, v15, v76);
          if ( *(_BYTE *)(v32 + 3368) && (g_QosFlags & 1) == 0
            || (v33 = *(_QWORD *)(*(_QWORD *)(a2 + 160) + 184LL),
                v34 = *(_DWORD *)(v32 + 1928),
                v35 = *(_QWORD *)(v33 + 24),
                (unsigned int)v35 >= v34)
            && v34 )
          {
            AdapterCryptoEngineExtension = -2147483631;
            v36 = L"NVMe ICE Key table is full. Can't program (v2) new capability.";
          }
          else
          {
            *(_QWORD *)(v33 + 24) = v35 + 1;
            *(_BYTE *)(*(_QWORD *)(a2 + 168) + 3LL) = 5;
            RaidUnitProcessBusyRequest(v32, a2, 0);
            v36 = L"NVMe ICE Key slot is full. Retry program (v2) new capability.";
            AdapterCryptoEngineExtension = 259;
          }
          StorEtwNVMeICEInterfaceEvent2(v4, v77[4], AdapterCryptoEngineExtension, (_DWORD)v36, 3);
          return AdapterCryptoEngineExtension;
        }
        if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                             v25,
                             v28,
                             v26,
                             v29) )
        {
          v42 = v77;
          v39 = v77[6];
          v51 = v77[7];
          v44 = *((_QWORD *)v15 + 2) + 72 * v30;
          v83 = v39;
          v84 = v51;
          if ( v39 || v51 )
          {
            v52 = v77[14];
            BugCheckParameter4 = *(unsigned int *)(v12 + 8);
            v76 = 0;
            v81 = v52;
            if ( (unsigned int)BugCheckParameter4 >= *(unsigned __int16 *)(v52 + 2) )
              KeBugCheckEx(0x176u, 2u, 6u, v12, BugCheckParameter4);
            v54 = *(_DWORD *)(v12 + 20) + 48;
            v76 = v54;
            if ( *(_DWORD *)(v44 + 40) < v54 )
            {
              v55 = *(void **)(v44 + 48);
              if ( v55 )
              {
                ExFreePoolWithTag(v55, 0x72436152u);
                v54 = v76;
                *(_QWORD *)(v44 + 48) = 0;
              }
              *(_DWORD *)(v44 + 40) = 0;
              Pool = RaidAllocatePool(64, v54, 1917018450, *(_QWORD *)(v4 + 8));
              *(_QWORD *)(v44 + 48) = Pool;
              if ( !Pool )
              {
                AdapterCryptoEngineExtension = -1073741670;
LABEL_61:
                ExReleaseSpinLockExclusiveFromDpcLevel(v18);
                return AdapterCryptoEngineExtension;
              }
              v54 = v76;
              *(_DWORD *)(v44 + 40) = v76;
            }
            v30 = *(_QWORD *)(v44 + 48);
            memset_0((void *)v30, 0, v54);
            *(_WORD *)v30 = *(_WORD *)(v81 + 16 * BugCheckParameter4 + 28);
            *(_WORD *)(v30 + 2) = *(_DWORD *)(v4 + 392) >> 10;
            *(_DWORD *)(v30 + 4) = (_DWORD)v82;
            *(_DWORD *)(v30 + 8) = 4096;
            *(_QWORD *)(v30 + 40) = *(_QWORD *)(v44 + 56);
            if ( *(_DWORD *)v12 < 2u )
            {
              *(_DWORD *)(v30 + 12) = 0;
            }
            else
            {
              *(_DWORD *)(v30 + 12) = *(_DWORD *)(v12 + 88);
              *(_OWORD *)(v30 + 20) = *(_OWORD *)(v12 + 72);
            }
            *(_WORD *)(v30 + 16) = *(_WORD *)(v12 + 20);
            memmove((void *)(v30 + 48), *(const void **)(v12 + 56), *(unsigned int *)(v12 + 20));
            v57 = v83;
            if ( !v83 )
              v57 = v84;
            v58 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, unsigned int *))(v57 + 40))(
                    *(_QWORD *)(v57 + 8),
                    v30,
                    &v76);
            v59 = *(unsigned int *)(v12 + 20);
            AdapterCryptoEngineExtension = v58;
            if ( *(_DWORD *)(v12 + 20) )
            {
              v60 = (_BYTE *)(v30 + 48);
              do
              {
                *v60++ = 0;
                --v59;
              }
              while ( v59 );
            }
            if ( AdapterCryptoEngineExtension == -1056964596 )
            {
              v40 = v77;
              v41 = L"NVMe ICE ProgramKeyV2 returned a transient error.";
              goto LABEL_73;
            }
            if ( AdapterCryptoEngineExtension )
            {
              v43 = L"Failed to program (v2) NVMe ICE capability.";
              LODWORD(v39) = AdapterCryptoEngineExtension;
LABEL_76:
              v42 = v77;
              goto LABEL_77;
            }
            v39 = *(_QWORD *)(v30 + 40);
            v61 = *(unsigned __int16 *)(v30 + 18);
            LODWORD(v30) = v79;
            *(_QWORD *)(v44 + 56) = v39;
            *(_DWORD *)(v44 + 64) = v61;
LABEL_80:
            if ( v39 )
            {
              v62 = v85;
              *(_DWORD *)v44 = v30;
              *(_OWORD *)(v44 + 4) = *v62;
              *(_OWORD *)(v44 + 20) = v62[1];
              *(_BYTE *)(v44 + 68) |= 1u;
              *(_QWORD *)(a2 + 832) = *v78;
              *(_DWORD *)(a2 + 808) = 4718593;
              *(_QWORD *)(a2 + 824) = v39;
              *(_DWORD *)(a2 + 880) = v61;
              *(_DWORD *)(a2 + 800) = v30;
              _InterlockedAdd((volatile signed __int32 *)(v44 + 36), 1u);
              goto LABEL_61;
            }
            v43 = L"Invalid key handle returned.";
            goto LABEL_76;
          }
        }
        else
        {
          v37 = *(_QWORD *)(*(_QWORD *)(v4 + 6256) + 40LL);
          v87 = *(_WORD *)(v12 + 8);
          v89 = (int)v82;
          v88 = *(_DWORD *)(v4 + 392) >> 10;
          v90 = 4096;
          v86 = 1310721;
          v38 = *(__int64 (__fastcall **)(_QWORD, int *))(v37 + 40);
          v81 = v37;
          LODWORD(v39) = v38(*(_QWORD *)(v37 + 8), &v86);
          if ( (_DWORD)v39 == -1056964596 )
          {
            v40 = *(_QWORD **)(v4 + 6256);
            v41 = L"NVMe ICE ConfigureCapability returned a transient error.";
LABEL_73:
            StorEtwNVMeICEInterfaceEvent2(v4, v40[4], -1056964596, (_DWORD)v41, 3);
            AdapterCryptoEngineExtension = -2147483631;
            goto LABEL_61;
          }
          if ( (_DWORD)v39 )
          {
            v42 = *(_QWORD **)(v4 + 6256);
            v43 = L"Failed to configure NVMe ICE capability.";
LABEL_77:
            StorEtwNVMeICEInterfaceEvent2(v4, v42[4], v39, (_DWORD)v43, 2);
            AdapterCryptoEngineExtension = -1073741823;
            goto LABEL_61;
          }
          v44 = *((_QWORD *)v15 + 2) + 72 * v30;
          v80 = *(_DWORD *)(v12 + 20) + 16;
          v45 = *(_QWORD *)(v44 + 48);
          v79 = v45;
          *(_DWORD *)v45 = 1572865;
          *(_WORD *)(v45 + 4) = *(_WORD *)(v12 + 20);
          *(_WORD *)(v45 + 6) = WORD2(v90);
          v46 = *(unsigned int *)(v12 + 20);
          v47 = *(const void **)(v12 + 56);
          v82 = (_BYTE *)(v45 + 16);
          memmove((void *)(v45 + 16), v47, v46);
          AdapterCryptoEngineExtension = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(v81 + 48))(
                                           *(_QWORD *)(v81 + 8),
                                           v45,
                                           &v80);
          if ( AdapterCryptoEngineExtension == -1056964596 )
          {
            v40 = *(_QWORD **)(v4 + 6256);
            v41 = L"NVMe ICE ProgramKey returned a transient error.";
            goto LABEL_73;
          }
          v49 = *(unsigned int *)(v12 + 20);
          if ( *(_DWORD *)(v12 + 20) )
          {
            v48 = v82;
            do
            {
              *v48++ = 0;
              --v49;
            }
            while ( v49 );
          }
          v50 = v79;
          *(_WORD *)(v79 + 4) = 0;
          KeSweepLocalCaches(v48);
          v39 = *(_QWORD *)(v50 + 8);
          v42 = v77;
        }
        if ( AdapterCryptoEngineExtension )
        {
          v43 = L"Failed to program NVMe ICE key.";
          LODWORD(v39) = AdapterCryptoEngineExtension;
          goto LABEL_77;
        }
        v61 = -1;
        goto LABEL_80;
      }
LABEL_26:
      if ( (_DWORD)v30 != (_DWORD)v28 )
        goto LABEL_31;
    }
    LOBYTE(v26) = v26 | 1;
    v30 = 0;
    *((_BYTE *)v15 + 8) = v26;
    LODWORD(v79) = 0;
    if ( (_DWORD)v28 )
    {
      do
      {
        v28 = 9 * v30;
        v25 = *(unsigned int *)(*((_QWORD *)v15 + 2) + 72 * v30 + 36);
        if ( !(_DWORD)v25 )
          break;
        v30 = (unsigned int)(v30 + 1);
        v25 = *(unsigned int *)(*((_QWORD *)v15 + 2) + 8 * v28 + 36);
        v29 = (unsigned int)(v25 + v29);
      }
      while ( (unsigned int)v30 < *v15 );
      v76 = v29;
      LODWORD(v79) = v30;
    }
    goto LABEL_31;
  }
  v17 = *(_QWORD *)(a2 + 224);
  if ( *(_DWORD *)(v17 + 1048) )
  {
    v77 = *(_QWORD **)(a1 + 3608);
    v15 = (volatile LONG *)(v77 + 8);
    goto LABEL_19;
  }
  AdapterCryptoEngineExtension = -1073741436;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_d01163ced7ca35b3df36265f6b7e43c1_Traceguids, v17);
  }
  return AdapterCryptoEngineExtension;
}

```

## disassembly

```asm
0x140095af0  mov     [rsp-8+arg_10], rbx
0x140095af5  push    rbp
0x140095af6  push    rsi
0x140095af7  push    rdi
0x140095af8  push    r12
0x140095afa  push    r13
0x140095afc  push    r14
0x140095afe  push    r15
0x140095b00  lea     rbp, [rsp-27h]
0x140095b05  sub     rsp, 0A0h
0x140095b0c  mov     rax, cs:__security_cookie
0x140095b13  xor     rax, rsp
0x140095b16  mov     [rbp+57h+var_38], rax
0x140095b1a  mov     eax, [rcx+3A4h]
0x140095b20  mov     rsi, rdx
0x140095b23  mov     r15, [rcx+18h]
0x140095b27  lea     rdx, [rbp+57h+var_90]
0x140095b2b  mov     rdi, rcx
0x140095b2e  mov     [rbp+57h+var_78], rcx
0x140095b32  xor     r12d, r12d
0x140095b35  mov     dword ptr [rbp+57h+var_70], eax
0x140095b38  mov     rcx, [rsi+0A0h]
0x140095b3f  mov     [rbp+57h+var_90], r12
0x140095b43  mov     [rbp+57h+var_80], r12d
0x140095b47  call    cs:__imp_IoGetAdapterCryptoEngineExtension
0x140095b4e  nop     dword ptr [rax+rax+00h]
0x140095b53  mov     ebx, eax
0x140095b55  test    eax, eax
0x140095b57  js      loc_1400962E7
0x140095b5d  mov     r14, [rbp+57h+var_90]
0x140095b61  test    r14, r14
0x140095b64  jz      loc_1400962E7
0x140095b6a  mov     r14, [r14+8]
0x140095b6e  test    r14, r14
0x140095b71  jz      loc_1400962E7
0x140095b77  cmp     dword ptr [r14], 1
0x140095b7b  jb      short loc_140095BE1
0x140095b7d  cmp     dword ptr [r14+4], 48h ; 'H'
0x140095b82  jb      short loc_140095BE1
0x140095b84  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x140095b89  test    eax, eax
0x140095b8b  jnz     short loc_140095BEB
0x140095b8d  mov     r13, [r15+1870h]
0x140095b94  mov     r8d, [r14+14h]
0x140095b98  mov     [rbp+57h+var_98], r13
0x140095b9c  lea     rdi, [r13+40h]
0x140095ba0  mov     edx, [rdi+4]
0x140095ba3  cmp     r8d, edx
0x140095ba6  jbe     loc_140095C55
0x140095bac  mov     rcx, cs:WPP_GLOBAL_Control
0x140095bb3  lea     rax, WPP_GLOBAL_Control
0x140095bba  cmp     rcx, rax
0x140095bbd  jz      short loc_140095BE1
0x140095bbf  mov     eax, [rcx+2Ch]
0x140095bc2  test    al, 2
0x140095bc4  jz      short loc_140095BE1
0x140095bc6  cmp     byte ptr [rcx+29h], 2
0x140095bca  jb      short loc_140095BE1
0x140095bcc  mov     rcx, [rcx+18h]
0x140095bd0  mov     r9, r15
0x140095bd3  mov     [rsp+0D0h+var_A8], edx
0x140095bd7  mov     dword ptr [rsp+0D0h+BugCheckParameter4], r8d
0x140095bdc  call    WPP_SF_qLL
0x140095be1  mov     ebx, 0C000000Dh
0x140095be6  jmp     loc_1400962EA
0x140095beb  mov     r9, [rsi+0E0h]
0x140095bf2  cmp     [r9+418h], r12d
0x140095bf9  jnz     short loc_140095C46
0x140095bfb  mov     ebx, 0C0000184h
0x140095c00  mov     rcx, cs:WPP_GLOBAL_Control
0x140095c07  lea     rax, WPP_GLOBAL_Control
0x140095c0e  cmp     rcx, rax
0x140095c11  jz      loc_1400962EA
0x140095c17  mov     eax, [rcx+2Ch]
0x140095c1a  test    al, 2
0x140095c1c  jz      loc_1400962EA
0x140095c22  cmp     byte ptr [rcx+29h], 2
0x140095c26  jb      loc_1400962EA
0x140095c2c  mov     rcx, [rcx+18h]
0x140095c30  lea     r8, WPP_d01163ced7ca35b3df36265f6b7e43c1_Traceguids
0x140095c37  mov     edx, 15h
0x140095c3c  call    WPP_SF_q
0x140095c41  jmp     loc_1400962EA
0x140095c46  mov     rax, [rdi+0E18h]
0x140095c4d  mov     [rbp+57h+var_98], rax
0x140095c51  lea     rdi, [rax+40h]
0x140095c55  lea     r12, [rdi+18h]
0x140095c59  mov     rcx, r12; SpinLock
0x140095c5c  call    cs:__imp_ExAcquireSpinLockSharedAtDpcLevel
0x140095c63  nop     dword ptr [rax+rax+00h]
0x140095c68  lea     r13, [r14+18h]
0x140095c6c  mov     rcx, rdi
0x140095c6f  mov     rdx, r13
0x140095c72  mov     [rbp+57h+var_58], r13
0x140095c76  call    RaidGetNvmeIceKeyIndex
0x140095c7b  cmp     eax, [rdi]
0x140095c7d  jnz     loc_140096270
0x140095c83  mov     rcx, r12; SpinLock
0x140095c86  call    cs:__imp_ExReleaseSpinLockSharedFromDpcLevel
0x140095c8d  nop     dword ptr [rax+rax+00h]
0x140095c92  mov     rcx, r12; SpinLock
0x140095c95  call    cs:__imp_ExAcquireSpinLockExclusiveAtDpcLevel
0x140095c9c  nop     dword ptr [rax+rax+00h]
0x140095ca1  mov     rdx, r13
0x140095ca4  mov     rcx, rdi
0x140095ca7  call    RaidGetNvmeIceKeyIndex
0x140095cac  mov     edx, [rdi]
0x140095cae  cmp     eax, edx
0x140095cb0  jnz     loc_140096205
0x140095cb6  mov     r8b, [rdi+8]
0x140095cba  xor     r9d, r9d
0x140095cbd  mov     [rbp+57h+var_A0], r9d
0x140095cc1  lea     r11d, [r9+1]
0x140095cc5  test    r11b, r8b
0x140095cc8  jnz     short loc_140095CFC
0x140095cca  xor     r13d, r13d
0x140095ccd  mov     dword ptr [rbp+57h+var_88], r13d
0x140095cd1  test    edx, edx
0x140095cd3  jz      short loc_140095CF7
0x140095cd5  mov     r10, [rdi+10h]
0x140095cd9  lea     rcx, ds:0[r13*8]
0x140095ce1  add     rcx, r13
0x140095ce4  test    [r10+rcx*8+44h], r11b
0x140095ce9  jz      short loc_140095D40
0x140095ceb  add     r13d, r11d
0x140095cee  mov     dword ptr [rbp+57h+var_88], r13d
0x140095cf2  cmp     r13d, edx
0x140095cf5  jb      short loc_140095CD9
0x140095cf7  cmp     r13d, edx
0x140095cfa  jnz     short loc_140095D40
0x140095cfc  or      r8b, r11b
0x140095cff  xor     r13d, r13d
0x140095d02  mov     [rdi+8], r8b
0x140095d06  mov     dword ptr [rbp+57h+var_88], r13d
0x140095d0a  test    edx, edx
0x140095d0c  jz      short loc_140095D40
0x140095d0e  mov     rax, [rdi+10h]
0x140095d12  lea     rdx, ds:0[r13*8]
0x140095d1a  add     rdx, r13
0x140095d1d  mov     ecx, [rax+rdx*8+24h]
0x140095d21  test    ecx, ecx
0x140095d23  jz      short loc_140095D38
0x140095d25  mov     rax, [rdi+10h]
0x140095d29  add     r13d, r11d
0x140095d2c  mov     ecx, [rax+rdx*8+24h]
0x140095d30  add     r9d, ecx
0x140095d33  cmp     r13d, [rdi]
0x140095d36  jb      short loc_140095D0E
0x140095d38  mov     [rbp+57h+var_A0], r9d
0x140095d3c  mov     dword ptr [rbp+57h+var_88], r13d
0x140095d40  cmp     r13d, [rdi]
0x140095d43  jnz     loc_140095E02
0x140095d49  add     [rdi+1Ch], r11d
0x140095d4d  mov     rcx, r12; SpinLock
0x140095d50  call    cs:__imp_ExReleaseSpinLockExclusiveFromDpcLevel
0x140095d57  nop     dword ptr [rax+rax+00h]
0x140095d5c  mov     rbx, [rbp+57h+var_78]
0x140095d60  mov     rdx, rdi
0x140095d63  mov     r8d, [rbp+57h+var_A0]
0x140095d67  mov     rcx, rbx
0x140095d6a  call    StorpTelemetryNvmeIceKeySlotFull
0x140095d6f  cmp     byte ptr [rbx+0D28h], 0
0x140095d76  jz      short loc_140095D87
0x140095d78  mov     eax, cs:g_QosFlags
0x140095d7e  mov     edx, 1
0x140095d83  test    dl, al
0x140095d85  jz      short loc_140095DA7
0x140095d87  mov     rax, [rsi+0A0h]
0x140095d8e  mov     rcx, [rax+0B8h]
0x140095d95  mov     eax, [rbx+788h]
0x140095d9b  mov     rdx, [rcx+18h]
0x140095d9f  cmp     edx, eax
0x140095da1  jb      short loc_140095DB5
0x140095da3  test    eax, eax
0x140095da5  jz      short loc_140095DB5
0x140095da7  mov     ebx, 80000011h
0x140095dac  lea     r9, aNvmeIceKeyTabl; "NVMe ICE Key table is full. Can't progr"...
0x140095db3  jmp     short loc_140095DE2
0x140095db5  lea     rax, [rdx+1]
0x140095db9  xor     r8d, r8d
0x140095dbc  mov     [rcx+18h], rax
0x140095dc0  mov     rdx, rsi
0x140095dc3  mov     rax, [rsi+0A8h]
0x140095dca  mov     rcx, rbx
0x140095dcd  mov     byte ptr [rax+3], 5
0x140095dd1  call    RaidUnitProcessBusyRequest
0x140095dd6  lea     r9, aNvmeIceKeySlot; "NVMe ICE Key slot is full. Retry progra"...
0x140095ddd  mov     ebx, 103h
0x140095de2  mov     rdx, [rbp+57h+var_98]
0x140095de6  mov     r8d, ebx
0x140095de9  mov     rcx, r15
0x140095dec  mov     dword ptr [rsp+0D0h+BugCheckParameter4], 3
0x140095df4  mov     rdx, [rdx+20h]
0x140095df8  call    StorEtwNVMeICEInterfaceEvent2
0x140095dfd  jmp     loc_1400962EA
0x140095e02  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x140095e07  test    eax, eax
0x140095e09  jnz     loc_140095F5D
0x140095e0f  mov     rax, [r15+1870h]
0x140095e16  lea     rdx, [rbp+57h+var_50]
0x140095e1a  mov     rcx, [rax+28h]
0x140095e1e  movzx   eax, word ptr [r14+8]
0x140095e23  mov     [rbp+57h+var_4C], ax
0x140095e27  mov     eax, dword ptr [rbp+57h+var_70]
0x140095e2a  mov     [rbp+57h+var_48], eax
0x140095e2d  mov     eax, [r15+188h]
0x140095e34  shr     eax, 0Ah
0x140095e37  mov     [rbp+57h+var_4A], ax
0x140095e3b  mov     [rbp+57h+var_44], 1000h
0x140095e43  mov     [rbp+57h+var_50], 140001h
0x140095e4a  mov     rax, [rcx+28h]
0x140095e4e  mov     [rbp+57h+var_78], rcx
0x140095e52  mov     rcx, [rcx+8]
0x140095e56  call    _guard_dispatch_icall
0x140095e5b  mov     r8d, eax
0x140095e5e  mov     eax, 0C100000Ch
0x140095e63  cmp     r8d, eax
0x140095e66  jnz     short loc_140095E7B
0x140095e68  mov     rdx, [r15+1870h]
0x140095e6f  lea     r9, aNvmeIceConfigu; "NVMe ICE ConfigureCapability returned a"...
0x140095e76  jmp     loc_140096137
0x140095e7b  test    r8d, r8d
0x140095e7e  jz      short loc_140095E93
0x140095e80  mov     rdx, [r15+1870h]
0x140095e87  lea     r9, aFailedToConfig; "Failed to configure NVMe ICE capability"...
0x140095e8e  jmp     loc_14009616A
0x140095e93  mov     rax, [rdi+10h]
0x140095e97  lea     rcx, ds:0[r13*8]
0x140095e9f  add     rcx, r13
0x140095ea2  lea     rdi, [rax+rcx*8]
0x140095ea6  mov     eax, [r14+14h]
0x140095eaa  add     eax, 10h
0x140095ead  mov     [rbp+57h+var_80], eax
0x140095eb0  mov     rbx, [rdi+30h]
0x140095eb4  mov     [rbp+57h+var_88], rbx
0x140095eb8  mov     dword ptr [rbx], 180001h
0x140095ebe  movzx   eax, word ptr [r14+14h]
0x140095ec3  mov     [rbx+4], ax
0x140095ec7  movzx   eax, word ptr [rbp+57h+var_44+4]
0x140095ecb  mov     [rbx+6], ax
0x140095ecf  lea     rax, [rbx+10h]
0x140095ed3  mov     r8d, [r14+14h]; Size
0x140095ed7  mov     rcx, rax; void *
0x140095eda  mov     rdx, [r14+38h]; Src
0x140095ede  mov     [rbp+57h+var_70], rax
0x140095ee2  call    memmove
0x140095ee7  mov     rcx, [rbp+57h+var_78]
0x140095eeb  lea     r8, [rbp+57h+var_80]
0x140095eef  mov     rdx, rbx
0x140095ef2  mov     rax, [rcx+30h]
0x140095ef6  mov     rcx, [rcx+8]
0x140095efa  call    _guard_dispatch_icall
0x140095eff  mov     r8d, 0C100000Ch
0x140095f05  mov     ebx, eax
0x140095f07  cmp     eax, r8d
0x140095f0a  jnz     short loc_140095F1F
0x140095f0c  mov     rdx, [r15+1870h]
0x140095f13  lea     r9, aNvmeIceProgram_0; "NVMe ICE ProgramKey returned a transien"...
0x140095f1a  jmp     loc_14009613A
0x140095f1f  mov     eax, [r14+14h]
0x140095f23  test    rax, rax
0x140095f26  jz      short loc_140095F3C
0x140095f28  mov     rcx, [rbp+57h+var_70]
0x140095f2c  mov     edx, 1
0x140095f31  mov     byte ptr [rcx], 0
0x140095f34  add     rcx, rdx
0x140095f37  sub     rax, rdx
0x140095f3a  jnz     short loc_140095F31
0x140095f3c  mov     r14, [rbp+57h+var_88]
0x140095f40  xor     eax, eax
0x140095f42  mov     [r14+4], ax
0x140095f47  call    cs:__imp_KeSweepLocalCaches
0x140095f4e  nop     dword ptr [rax+rax+00h]
0x140095f53  mov     r8, [r14+8]
0x140095f57  mov     rdx, [rbp+57h+var_98]
0x140095f5b  jmp     short loc_140095F8E
0x140095f5d  mov     rdx, [rbp+57h+var_98]
0x140095f61  lea     rcx, ds:0[r13*8]
0x140095f69  mov     rax, [rdi+10h]
0x140095f6d  add     rcx, r13
0x140095f70  mov     r8, [rdx+30h]
0x140095f74  mov     r9, [rdx+38h]
0x140095f78  lea     rdi, [rax+rcx*8]
0x140095f7c  mov     [rbp+57h+var_68], r8
0x140095f80  mov     [rbp+57h+var_60], r9
0x140095f84  test    r8, r8
0x140095f87  jnz     short loc_140095FA5
0x140095f89  test    r9, r9
0x140095f8c  jnz     short loc_140095FA5
0x140095f8e  test    ebx, ebx
0x140095f90  jz      loc_14009619E
0x140095f96  lea     r9, aFailedToProgra_0; "Failed to program NVMe ICE key."
0x140095f9d  mov     r8d, ebx
0x140095fa0  jmp     loc_14009616A
0x140095fa5  mov     rax, [rdx+70h]
0x140095fa9  mov     ebx, [r14+8]
0x140095fad  mov     [rbp+57h+var_A0], 0
0x140095fb4  mov     [rbp+57h+var_78], rax
0x140095fb8  movzx   eax, word ptr [rax+2]
0x140095fbc  cmp     ebx, eax
  ... truncated ...
```
