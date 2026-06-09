# RaidAdapterPnpIrp

- ea: `0x1400234a0`
- end: `0x140023c61`
- name: `RaidAdapterPnpIrp`
- size: `1985`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140023370`

## callees

- `0x1400234a0`
- `0x140023c68`
- `0x1400240e0`
- `0x140024498`
- `0x140025144`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006f610`
- `0x14008482c`
- `0x1400848c4`
- `0x14008ad90`
- `0x14008ae24`
- `0x140093e14`
- `0x14014b400`
- `0x14018c900`
- `0x14018db40`
- `0x14018e5e4`
- `0x14018e688`
- `0x14018ed38`
- `0x1401be644`
- `0x1401c07f0`
- `0x1401c21a0`
- `0x1401c259c`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14002351f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140023641`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140023b5f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14002351f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140023641`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140023b5f`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400234de`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400234de`
- `ntoskrnl!IofCompleteRequest` at `0x14002367b`
- `ntoskrnl!IofCompleteRequest` at `0x14002367b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400235cf`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400237dc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400235cf`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400237dc`

## pseudocode

```c
__int64 __fastcall RaidAdapterPnpIrp(__int64 a1, __int64 a2)
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v3; // rcx
  int v5; // edx
  BOOLEAN v6; // si
  char v7; // r13
  unsigned int v8; // eax
  unsigned int v9; // r14d
  int v10; // ecx
  int v11; // eax
  char v12; // r15
  unsigned int InterfaceIrp; // eax
  unsigned int v14; // esi
  bool v16; // zf
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  int *v19; // rax
  int v20; // ecx
  char v21; // cl
  _BYTE *v22; // r9
  unsigned __int8 v23; // r10
  char v24; // r12
  char v25; // di
  __int64 v26; // rdx
  char v27; // r11
  _BYTE *v28; // rax
  char v29; // r8
  char *v30; // r8
  unsigned int v31; // eax
  __int64 v32; // r8
  int v33; // ecx
  unsigned int v34; // esi
  char *v35; // r11
  unsigned int v36; // r14d
  unsigned __int64 v37; // rdi
  char v38; // r15
  __int64 v39; // rcx
  unsigned int v40; // [rsp+60h] [rbp-9h]
  __int128 v41; // [rsp+68h] [rbp-1h] BYREF
  __int128 v42; // [rsp+78h] [rbp+Fh] BYREF

  v3 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 320);
  v42 = 0;
  v6 = ExAcquireRundownProtectionCacheAware(v3);
  v7 = 0;
  v8 = v6 == 0 ? 0xC0000056 : 0;
  v9 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL);
  v40 = v8;
  if ( StorEtwLoggingEnabled )
  {
    IoGetActivityIdIrp(a2, &v42);
    if ( v9 > 0x16 || (v11 = 4718720, !_bittest(&v11, v9)) )
    {
      if ( (byte_140177432 & 0x20) != 0 )
        McTemplateK0pddp_EtwWriteTransfer(v10, v5, (unsigned int)&v42, a2, v9, 0, *(_QWORD *)(a1 + 8));
    }
    v8 = v6 == 0 ? 0xC0000056 : 0;
  }
  if ( v6 )
  {
    v12 = 1;
    goto LABEL_9;
  }
  if ( v9 == 2 || v9 == 20 )
  {
    v12 = 0;
    if ( *(_DWORD *)(a1 + 88) == 5 )
    {
LABEL_9:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids, a1, a2, v9);
      }
      if ( v9 > 7 )
      {
        switch ( v9 )
        {
          case 8u:
            InterfaceIrp = RaidAdapterQueryInterfaceIrp((_QWORD *)a1, a2);
            break;
          case 9u:
            InterfaceIrp = RaidAdapterQueryCapabilitiesIrp(a1, a2);
            break;
          case 0xDu:
            InterfaceIrp = RaidAdapterFilterResourceRequirementsIrp(a1, a2);
            break;
          case 0x13u:
            if ( StorEtwLoggingEnabled && (byte_140177432 & 0x20) != 0 )
              McTemplateK0pddp_EtwWriteTransfer(
                *(_QWORD *)(a2 + 184),
                v5,
                (unsigned int)&v42,
                a2,
                v9,
                *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL),
                *(_QWORD *)(a1 + 8));
            InterfaceIrp = NvmeAdapterQueryIdIrp(a1, a2);
            break;
          case 0x14u:
            InterfaceIrp = RaidAdapterQueryPnpDeviceStateIrp(a1, a2);
            break;
          case 0x16u:
            if ( StorEtwLoggingEnabled && (byte_140177432 & 0x20) != 0 )
              McTemplateK0pddp_EtwWriteTransfer(
                *(_QWORD *)(a2 + 184),
                v5,
                (unsigned int)&v42,
                a2,
                v9,
                *(_DWORD *)(*(_QWORD *)(a2 + 184) + 16LL),
                *(_QWORD *)(a1 + 8));
            InterfaceIrp = RaidAdapterDeviceUsageNotificationIrp(a1, a2);
            break;
          case 0x17u:
            v12 = 0;
            InterfaceIrp = RaidAdapterSurpriseRemovalIrp(a1, a2);
            break;
          default:
            ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 320));
            v12 = 0;
            if ( StorEtwLoggingEnabled )
            {
              v41 = 0;
              IoGetActivityIdIrp(a2, &v41);
              if ( (byte_140177432 & 0x20) != 0 )
                McTemplateK0pd_EtwWriteTransfer(v39, EventPnpRequestComplete, &v41, a2, *(_DWORD *)(a2 + 48));
            }
            InterfaceIrp = RaForwardIrp(*(_QWORD *)(a1 + 24), a2);
            break;
        }
        goto LABEL_15;
      }
      switch ( v9 )
      {
        case 7u:
          if ( StorEtwLoggingEnabled && (byte_140177432 & 0x20) != 0 )
            McTemplateK0pddp_EtwWriteTransfer(
              *(_QWORD *)(a2 + 184),
              v5,
              (unsigned int)&v42,
              a2,
              7,
              *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL),
              *(_QWORD *)(a1 + 8));
          InterfaceIrp = RaidAdapterQueryDeviceRelationsIrp(a1, (PIRP)a2);
          break;
        case 0u:
          InterfaceIrp = RaidAdapterStartDeviceIrp((PVOID)a1, (PIRP)a2);
          break;
        case 1u:
          InterfaceIrp = RaidAdapterQueryRemoveDeviceIrp(a1, a2);
          break;
        case 2u:
          v12 = 0;
          InterfaceIrp = RaidAdapterRemoveDeviceIrp(a1, a2);
          break;
        case 3u:
          goto LABEL_114;
        case 4u:
          InterfaceIrp = RaidAdapterStopDeviceIrp(a1, a2);
          break;
        case 5u:
          InterfaceIrp = RaidAdapterQueryStopDeviceIrp(a1, a2);
          break;
        default:
LABEL_114:
          InterfaceIrp = RaidAdapterCancelRemoveDeviceIrp(a1, a2);
          break;
      }
LABEL_15:
      v14 = InterfaceIrp;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqDD(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids,
          a1,
          a2,
          v9,
          InterfaceIrp);
      }
      if ( v12 )
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 320));
      return v14;
    }
  }
  v16 = StorEtwLoggingEnabled == 0;
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v8;
  if ( v16 )
    goto LABEL_26;
  v41 = 0;
  IoGetActivityIdIrp(a2, &v41);
  v18 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v18 == 14 )
  {
    if ( (byte_140177432 & 8) != 0 )
      McTemplateK0pd_EtwWriteTransfer(v17, EventNonReadWriteRequestComplete, &v41, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_26;
  }
  if ( *(_BYTE *)v18 != 15 )
  {
    if ( *(_BYTE *)v18 == 27 )
    {
      if ( *(_BYTE *)(v18 + 1) != 7 || *(_DWORD *)(v18 + 8) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v17, EventPnpRequestComplete, &v41, a2, *(_DWORD *)(a2 + 48));
      }
      else if ( (byte_140177432 & 0x40) != 0 )
      {
        v19 = *(int **)(a2 + 56);
        if ( v19 )
          v20 = *v19;
        else
          v20 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v20, v18, (unsigned int)&v41, a2, v20, *(_DWORD *)(a2 + 48));
      }
    }
    goto LABEL_26;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_26;
  v26 = *(_QWORD *)(v18 + 8);
  v38 = 1;
  if ( *(_BYTE *)(v26 + 2) != 40 )
  {
    v21 = *(_BYTE *)(v26 + 72);
    v22 = *(_BYTE **)(v26 + 32);
    v23 = *(_BYTE *)(v26 + 11);
    v24 = *(_BYTE *)(v26 + 4);
    if ( !*(_BYTE *)(v26 + 2) )
      goto LABEL_62;
    goto LABEL_26;
  }
  if ( *(_DWORD *)(v26 + 20) )
    goto LABEL_26;
  v36 = *(_DWORD *)(v26 + 56);
  if ( !v36 )
    goto LABEL_26;
  v23 = 0;
  v35 = 0;
  v24 = 0;
  v22 = 0;
  v34 = 0;
  while ( 1 )
  {
    v17 = *(unsigned int *)(v26 + 4LL * v34 + 120);
    if ( (unsigned int)v17 >= 0x80 )
    {
      v37 = *(unsigned int *)(v26 + 16);
      if ( (unsigned int)v17 < (unsigned int)v37 )
        break;
    }
LABEL_79:
    if ( ++v34 >= v36 )
      goto LABEL_80;
  }
  v32 = *(unsigned int *)(v26 + 4LL * v34 + 120);
  v33 = *(_DWORD *)(v17 + v26) - 64;
  if ( v33 )
  {
    LODWORD(v17) = v33 - 1;
    if ( (_DWORD)v17 )
    {
      if ( (_DWORD)v17 == 1 )
      {
        LODWORD(v17) = v32 + 40;
        if ( v32 + 40 <= v37 )
        {
          if ( *(_DWORD *)(v32 + v26 + 12) )
            v35 = (char *)(v32 + v26 + 32);
          v22 = *(_BYTE **)(v32 + v26 + 24);
          goto LABEL_90;
        }
      }
    }
    else
    {
      LODWORD(v17) = v32 + 56;
      if ( v32 + 56 <= v37 )
      {
        v7 = 1;
        if ( *(_BYTE *)(v32 + v26 + 10) )
          v35 = (char *)(v32 + v26 + 24);
        v24 = *(_BYTE *)(v32 + v26 + 8);
        v22 = *(_BYTE **)(v32 + v26 + 16);
        v23 = *(_BYTE *)(v32 + v26 + 9);
      }
    }
    goto LABEL_78;
  }
  LODWORD(v17) = v32 + 40;
  if ( v32 + 40 > v37 )
  {
LABEL_78:
    if ( v7 )
      goto LABEL_80;
    goto LABEL_79;
  }
  if ( *(_BYTE *)(v32 + v26 + 10) )
    v35 = (char *)(v32 + v26 + 24);
  v22 = *(_BYTE **)(v32 + v26 + 16);
LABEL_90:
  v24 = *(_BYTE *)(v32 + v26 + 8);
  v23 = *(_BYTE *)(v32 + v26 + 9);
LABEL_80:
  if ( !v35 )
    goto LABEL_26;
  v21 = *v35;
LABEL_62:
  LOBYTE(v17) = v21 - 8;
  if ( (v17 & 0x5D) != 0 )
    goto LABEL_26;
  v25 = *(_BYTE *)(v26 + 3);
  if ( v25 == 1 || !v22 || !v23 )
    goto LABEL_100;
  LOBYTE(v26) = 0;
  v17 = (unsigned __int64)&v22[v23];
  v27 = 0;
  v28 = v22 + 8;
  v29 = 0;
  if ( (unsigned __int8)((*v22 & 0x7F) - 114) <= 1u )
  {
    if ( (unsigned __int64)v28 <= v17 )
    {
      v27 = v22[2];
      LOBYTE(v26) = v22[1] & 0xF;
      v29 = v22[3];
      goto LABEL_110;
    }
    goto LABEL_109;
  }
  if ( (unsigned __int64)v28 > v17 )
  {
LABEL_109:
    v38 = 0;
    goto LABEL_110;
  }
  v30 = v22 + 13;
  LOBYTE(v26) = v22[2] & 0xF;
  v31 = v23;
  if ( (unsigned int)(unsigned __int8)v22[7] + 8 <= v23 )
    v31 = (unsigned __int8)v22[7] + 8;
  v17 = (unsigned __int64)&v22[v31];
  if ( (unsigned __int64)v30 <= v17 )
    v27 = v22[12];
  if ( (unsigned __int64)(v22 + 14) > v17 )
    v29 = 0;
  else
    v29 = *v30;
LABEL_110:
  if ( !v38 )
  {
LABEL_100:
    LOBYTE(v26) = 0;
    v27 = 0;
    v29 = 0;
  }
  McTemplateK0pduuuuup_EtwWriteTransfer(
    v17,
    v26,
    (unsigned int)&v41,
    a2,
    *(_DWORD *)(a2 + 48),
    v25,
    v24,
    v26,
    v27,
    v29,
    a2);
LABEL_26:
  IofCompleteRequest((PIRP)a2, 0);
  return v40;
}

```

## disassembly

```asm
0x1400234a0  mov     [rsp-8+arg_10], rbx
0x1400234a5  push    rbp
0x1400234a6  push    rsi
0x1400234a7  push    rdi
0x1400234a8  push    r12
0x1400234aa  push    r13
0x1400234ac  push    r14
0x1400234ae  push    r15
0x1400234b0  lea     rbp, [rsp-27h]
0x1400234b5  sub     rsp, 90h
0x1400234bc  mov     rax, cs:__security_cookie
0x1400234c3  xor     rax, rsp
0x1400234c6  mov     [rbp+57h+var_38], rax
0x1400234ca  mov     rdi, rcx
0x1400234cd  xorps   xmm0, xmm0
0x1400234d0  mov     rcx, [rcx+140h]; RunRefCacheAware
0x1400234d7  mov     rbx, rdx
0x1400234da  movups  [rbp+57h+var_48], xmm0
0x1400234de  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400234e5  nop     dword ptr [rax+rax+00h]
0x1400234ea  mov     cl, al
0x1400234ec  mov     sil, al
0x1400234ef  neg     cl
0x1400234f1  mov     r12b, 20h ; ' '
0x1400234f4  mov     rcx, [rbx+0B8h]
0x1400234fb  sbb     eax, eax
0x1400234fd  xor     r13d, r13d
0x140023500  not     eax
0x140023502  and     eax, 0C0000056h
0x140023507  cmp     cs:StorEtwLoggingEnabled, r13b
0x14002350e  movzx   r14d, byte ptr [rcx+1]
0x140023513  mov     [rbp+57h+var_60], eax
0x140023516  jz      short loc_14002354C
0x140023518  lea     rdx, [rbp+57h+var_48]
0x14002351c  mov     rcx, rbx
0x14002351f  call    cs:__imp_IoGetActivityIdIrp
0x140023526  nop     dword ptr [rax+rax+00h]
0x14002352b  cmp     r14d, 16h
0x14002352f  ja      short loc_14002353C
0x140023531  mov     eax, 480080h
0x140023536  bt      eax, r14d
0x14002353a  jb      short loc_140023549
0x14002353c  test    cs:byte_140177432, r12b
0x140023543  jnz     loc_140023A09
0x140023549  mov     eax, [rbp+57h+var_60]
0x14002354c  test    sil, sil
0x14002354f  jz      loc_140023605
0x140023555  mov     r15d, 1
0x14002355b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023562  lea     rax, WPP_GLOBAL_Control
0x140023569  cmp     rcx, rax
0x14002356c  jz      short loc_140023579
0x14002356e  mov     eax, [rcx+2Ch]
0x140023571  test    al, 2
0x140023573  jnz     loc_140023A83
0x140023579  cmp     r14d, 7
0x14002357d  jbe     loc_1400236B6
0x140023583  mov     eax, r14d
0x140023586  sub     eax, 8
0x140023589  jz      loc_140023C1C
0x14002358f  sub     eax, 1
0x140023592  jnz     loc_14002368F
0x140023598  mov     rdx, rbx
0x14002359b  mov     rcx, rdi
0x14002359e  call    RaidAdapterQueryCapabilitiesIrp
0x1400235a3  mov     esi, eax
0x1400235a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400235ac  lea     rax, WPP_GLOBAL_Control
0x1400235b3  cmp     rcx, rax
0x1400235b6  jz      short loc_1400235C3
0x1400235b8  mov     eax, [rcx+2Ch]
0x1400235bb  test    al, 2
0x1400235bd  jnz     loc_140023C2C
0x1400235c3  test    r15b, r15b
0x1400235c6  jz      short loc_1400235DB
0x1400235c8  mov     rcx, [rdi+140h]; RunRefCacheAware
0x1400235cf  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400235d6  nop     dword ptr [rax+rax+00h]
0x1400235db  mov     eax, esi
0x1400235dd  mov     rcx, [rbp+57h+var_38]
0x1400235e1  xor     rcx, rsp; StackCookie
0x1400235e4  call    __security_check_cookie
0x1400235e9  mov     rbx, [rsp+0C0h+arg_10]
0x1400235f1  add     rsp, 90h
0x1400235f8  pop     r15
0x1400235fa  pop     r14
0x1400235fc  pop     r13
0x1400235fe  pop     r12
0x140023600  pop     rdi
0x140023601  pop     rsi
0x140023602  pop     rbp
0x140023603  retn
0x140023605  cmp     r14d, 2
0x140023609  jnz     loc_140023A2D
0x14002360f  cmp     dword ptr [rdi+58h], 5
0x140023613  mov     r15b, r13b
0x140023616  jz      loc_14002355B
0x14002361c  cmp     cs:StorEtwLoggingEnabled, r13b
0x140023623  mov     [rbx+38h], r13
0x140023627  mov     byte ptr [rbx+8Dh], 0ACh
0x14002362e  mov     [rbx+30h], eax
0x140023631  jz      short loc_140023676
0x140023633  xorps   xmm0, xmm0
0x140023636  lea     rdx, [rbp+57h+var_58]
0x14002363a  mov     rcx, rbx
0x14002363d  movups  [rbp+57h+var_58], xmm0
0x140023641  call    cs:__imp_IoGetActivityIdIrp
0x140023648  nop     dword ptr [rax+rax+00h]
0x14002364d  mov     rdx, [rbx+0B8h]
0x140023654  movzx   eax, byte ptr [rdx]
0x140023657  sub     eax, 0Eh
0x14002365a  jz      loc_140023720
0x140023660  sub     eax, 1
0x140023663  jnz     loc_14002374C
0x140023669  cmp     cs:byte_140177431, r13b
0x140023670  jl      loc_140023A3C
0x140023676  xor     edx, edx; PriorityBoost
0x140023678  mov     rcx, rbx; Irp
0x14002367b  call    cs:__imp_IofCompleteRequest
0x140023682  nop     dword ptr [rax+rax+00h]
0x140023687  mov     eax, [rbp+57h+var_60]
0x14002368a  jmp     loc_1400235DD
0x14002368f  sub     eax, 4
0x140023692  jz      loc_140023C0C
0x140023698  sub     eax, 6
0x14002369b  jz      loc_140023BC4
0x1400236a1  sub     eax, 1
0x1400236a4  jnz     short loc_1400236D4
0x1400236a6  mov     rdx, rbx
0x1400236a9  mov     rcx, rdi
0x1400236ac  call    RaidAdapterQueryPnpDeviceStateIrp
0x1400236b1  jmp     loc_1400235A3
0x1400236b6  jz      short loc_140023703
0x1400236b8  mov     eax, r14d
0x1400236bb  test    r14d, r14d
0x1400236be  jnz     loc_14002379F
0x1400236c4  mov     rdx, rbx
0x1400236c7  mov     rcx, rdi
0x1400236ca  call    RaidAdapterStartDeviceIrp
0x1400236cf  jmp     loc_1400235A3
0x1400236d4  sub     eax, 2
0x1400236d7  jnz     loc_140023809
0x1400236dd  cmp     cs:StorEtwLoggingEnabled, r13b
0x1400236e4  jz      short loc_1400236F3
0x1400236e6  test    cs:byte_140177432, r12b
0x1400236ed  jnz     loc_140023B97
0x1400236f3  mov     rdx, rbx
0x1400236f6  mov     rcx, rdi
0x1400236f9  call    RaidAdapterDeviceUsageNotificationIrp
0x1400236fe  jmp     loc_1400235A3
0x140023703  cmp     cs:StorEtwLoggingEnabled, r13b
0x14002370a  jnz     loc_140023B17
0x140023710  mov     rdx, rbx
0x140023713  mov     rcx, rdi
0x140023716  call    RaidAdapterQueryDeviceRelationsIrp
0x14002371b  jmp     loc_1400235A3
0x140023720  test    cs:byte_140177432, 8
0x140023727  jz      loc_140023676
0x14002372d  mov     edx, [rbx+30h]
0x140023730  mov     dword ptr [rsp+0C0h+var_A0], edx
0x140023734  lea     rdx, EventNonReadWriteRequestComplete
0x14002373b  mov     r9, rbx
0x14002373e  lea     r8, [rbp+57h+var_58]
0x140023742  call    McTemplateK0pd_EtwWriteTransfer
0x140023747  jmp     loc_140023676
0x14002374c  cmp     eax, 0Ch
0x14002374f  jnz     loc_140023676
0x140023755  cmp     byte ptr [rdx+1], 7
0x140023759  jz      short loc_140023778
0x14002375b  test    cs:byte_140177432, r12b
0x140023762  jz      loc_140023676
0x140023768  mov     eax, [rbx+30h]
0x14002376b  lea     rdx, EventPnpRequestComplete
0x140023772  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140023776  jmp     short loc_14002373B
0x140023778  cmp     [rdx+8], r13d
0x14002377c  jnz     short loc_14002375B
0x14002377e  test    cs:byte_140177432, 40h
0x140023785  jz      loc_140023676
0x14002378b  mov     rax, [rbx+38h]
0x14002378f  test    rax, rax
0x140023792  jz      loc_14014EA0E
0x140023798  mov     ecx, [rax]
0x14002379a  jmp     loc_14014EA11
0x14002379f  sub     eax, 1
0x1400237a2  jz      loc_140023B07
0x1400237a8  sub     eax, 1
0x1400237ab  jz      loc_140023AF4
0x1400237b1  sub     eax, 1
0x1400237b4  jz      loc_140023AE4
0x1400237ba  sub     eax, 1
0x1400237bd  jz      loc_140023AD4
0x1400237c3  sub     eax, 1
0x1400237c6  jz      loc_140023AC4
0x1400237cc  cmp     eax, 1
0x1400237cf  jz      loc_140023AB4
0x1400237d5  mov     rcx, [rdi+140h]; RunRefCacheAware
0x1400237dc  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400237e3  nop     dword ptr [rax+rax+00h]
0x1400237e8  cmp     cs:StorEtwLoggingEnabled, r13b
0x1400237ef  mov     r15b, r13b
0x1400237f2  jnz     loc_140023B51
0x1400237f8  mov     rcx, [rdi+18h]
0x1400237fc  mov     rdx, rbx
0x1400237ff  call    RaForwardIrp
0x140023804  jmp     loc_1400235A3
0x140023809  cmp     eax, 1
0x14002380c  jnz     short loc_1400237D5
0x14002380e  mov     rdx, rbx
0x140023811  mov     rcx, rdi
0x140023814  mov     r15b, r13b
0x140023817  call    RaidAdapterSurpriseRemovalIrp
0x14002381c  jmp     loc_1400235A3
0x140023821  mov     cl, [rdx+48h]
0x140023824  mov     r9, [rdx+20h]
0x140023828  mov     r10b, [rdx+0Bh]
0x14002382c  mov     r12b, [rdx+4]
0x140023830  test    eax, eax
0x140023832  jnz     loc_140023676
0x140023838  sub     cl, 8
0x14002383b  test    cl, 5Dh
0x14002383e  jnz     loc_140023676
0x140023844  mov     dil, [rdx+3]
0x140023848  cmp     dil, r15b
0x14002384b  jz      loc_1400239CB
0x140023851  test    r9, r9
0x140023854  jz      loc_1400239CB
0x14002385a  test    r10b, r10b
0x14002385d  jz      loc_1400239CB
0x140023863  mov     al, [r9]
0x140023866  mov     dl, r13b
0x140023869  and     al, 7Fh
0x14002386b  movzx   ecx, r10b
0x14002386f  sub     al, 72h ; 'r'
0x140023871  add     rcx, r9
0x140023874  cmp     al, r15b
0x140023877  mov     r11b, r13b
0x14002387a  lea     rax, [r9+8]
0x14002387e  mov     r8b, r13b
0x140023881  jbe     loc_140023A5C
0x140023887  cmp     rax, rcx
0x14002388a  ja      loc_140023A72
0x140023890  movzx   ecx, byte ptr [r9+7]
0x140023895  lea     r8, [r9+0Dh]
0x140023899  mov     dl, [r9+2]
0x14002389d  add     ecx, 8
0x1400238a0  and     dl, 0Fh
0x1400238a3  movzx   eax, r10b
0x1400238a7  cmp     ecx, eax
0x1400238a9  cmovbe  eax, ecx
0x1400238ac  mov     ecx, eax
0x1400238ae  add     rcx, r9
0x1400238b1  cmp     r8, rcx
0x1400238b4  ja      short loc_1400238BA
0x1400238b6  mov     r11b, [r9+0Ch]
0x1400238ba  lea     rax, [r9+0Eh]
0x1400238be  cmp     rax, rcx
0x1400238c1  ja      loc_140023A57
0x1400238c7  mov     r8b, [r8]
0x1400238ca  jmp     loc_140023A75
0x1400238cf  mov     r8, rcx
0x1400238d2  mov     ecx, [rcx+rdx]
0x1400238d5  sub     ecx, 40h ; '@'
0x1400238d8  jz      short loc_14002393E
0x1400238da  sub     ecx, r15d
0x1400238dd  jz      short loc_140023912
0x1400238df  cmp     ecx, r15d
0x1400238e2  jnz     short loc_1400238ED
0x1400238e4  lea     rcx, [r8+28h]
0x1400238e8  cmp     rcx, rdi
0x1400238eb  jbe     short loc_140023962
0x1400238ed  test    r13b, r13b
0x1400238f0  jnz     short loc_1400238FE
0x1400238f2  add     esi, r15d
0x1400238f5  cmp     esi, r14d
0x1400238f8  jb      loc_1400239A9
0x1400238fe  xor     r13d, r13d
0x140023901  test    r11, r11
0x140023904  jz      loc_140023676
0x14002390a  mov     cl, [r11]
0x14002390d  jmp     loc_140023838
0x140023912  lea     rcx, [r8+38h]
0x140023916  cmp     rcx, rdi
0x140023919  ja      short loc_1400238ED
0x14002391b  cmp     byte ptr [r8+rdx+0Ah], 0
0x140023921  mov     r13b, r15b
0x140023924  jbe     short loc_14002392D
0x140023926  lea     r11, [rdx+18h]
0x14002392a  add     r11, r8
0x14002392d  mov     r12b, [r8+rdx+8]
0x140023932  mov     r9, [r8+rdx+10h]
0x140023937  mov     r10b, [r8+rdx+9]
0x14002393c  jmp     short loc_1400238ED
0x14002393e  lea     rcx, [r8+28h]
0x140023942  cmp     rcx, rdi
0x140023945  ja      short loc_1400238ED
0x140023947  xor     r13d, r13d
0x14002394a  cmp     [r8+rdx+0Ah], r13b
0x14002394f  ja      short loc_14002397A
0x140023951  mov     r9, [r8+rdx+10h]
  ... truncated ...
```
