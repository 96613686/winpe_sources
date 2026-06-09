# NvmeAdapterFirmwareActivateIoctlCompletion

- ea: `0x140073320`
- end: `0x140073f8d`
- name: `NvmeAdapterFirmwareActivateIoctlCompletion`
- size: `3181`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140045c28`
- `0x14005285c`
- `0x14006d1c0`
- `0x14006d298`
- `0x140073320`
- `0x1400848c4`
- `0x1400f378c`
- `0x1400f8ed0`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140073c98`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140073c98`
- `ntoskrnl!IofCompleteRequest` at `0x140073f55`
- `ntoskrnl!IofCompleteRequest` at `0x140073f55`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140073c62`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140073c62`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140073725`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400737ab`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400739d3`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140073725`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400737ab`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400739d3`

## string_xrefs

- `0x140073a79`: `Controller requires conventional reset after firmware activation.  Device should be power cycled to complete update.`
- `0x1400738c4`: `Firmware activation without reset failed, attempting to re-active with reset.`
- `0x1400737b7`: `Queued identify update worker after firmware activation (1).`
- `0x140073731`: `Queued identify update worker after firmware activation.`

## pseudocode

```c
void __fastcall NvmeAdapterFirmwareActivateIoctlCompletion(char *Context, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebp
  __int64 v6; // r15
  __int64 v7; // rsi
  unsigned int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  bool v19; // zf
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ebx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  bool v35; // zf
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  bool v50; // zf
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // edx
  __int64 v63; // r10
  const wchar_t *v64; // r9
  struct _IO_WORKITEM *v65; // rcx
  const wchar_t *v66; // r9
  struct _IO_WORKITEM *v67; // rcx
  unsigned __int64 v68; // rcx
  __int64 v69; // rdx
  int *v70; // rax
  int v71; // ecx
  __int64 *v72; // rdx
  __int64 v73; // rdx
  unsigned int v74; // r14d
  unsigned __int8 v75; // r10
  char *v76; // r11
  char v77; // bl
  _BYTE *v78; // r9
  unsigned int v79; // ebp
  char v80; // r15
  unsigned __int64 v81; // rdi
  __int64 v82; // r8
  int v83; // ecx
  char v84; // cl
  char v85; // di
  char v86; // r11
  _BYTE *v87; // rax
  char v88; // r8
  char *v89; // r8
  unsigned int v90; // eax
  char v91; // al
  __int128 v92; // [rsp+A0h] [rbp-58h] BYREF

  LOBYTE(v5) = 1;
  v6 = *(_QWORD *)(*(_QWORD *)a2 + 4224LL);
  v7 = *(_QWORD *)(*(_QWORD *)a2 + 4184LL);
  if ( !a3 )
  {
    StorEtwNvmeControllerEvent(
      (_DWORD)Context,
      1,
      3,
      (unsigned int)L"Firmware activation caused null CQE.",
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0);
    *(_WORD *)(*(_QWORD *)a2 + 4260LL) = 0;
    *(_WORD *)(*(_QWORD *)a2 + 4260LL) &= 0xF1FFu;
    *(_WORD *)(*(_QWORD *)a2 + 4260LL) = *(_WORD *)(*(_QWORD *)a2 + 4260LL) & 0xFE01 | 0xC;
    v8 = *(unsigned __int16 *)(*(_QWORD *)a2 + 4260LL);
    if ( ((v8 >> 9) & 7) != 0 )
    {
      if ( ((*(unsigned __int16 *)(*(_QWORD *)a2 + 4260LL) >> 9) & 7) != 1 )
      {
        if ( ((*(unsigned __int16 *)(*(_QWORD *)a2 + 4260LL) >> 9) & 7) != 2 )
          goto LABEL_94;
        v9 = (unsigned __int8)(v8 >> 1) - 128;
        if ( !v9 )
          goto LABEL_94;
        v10 = v9 - 1;
        if ( !v10 )
          goto LABEL_94;
        v11 = v10 - 1;
        if ( !v11 )
          goto LABEL_94;
        v12 = v11 - 1;
        if ( !v12 )
          goto LABEL_94;
        v13 = v12 - 1;
        if ( !v13 )
          goto LABEL_94;
        v14 = v13 - 1;
        if ( !v14 )
          goto LABEL_94;
        goto LABEL_85;
      }
      v15 = (unsigned __int8)(v8 >> 1);
      if ( v15 <= 0x80 )
      {
        if ( v15 == 128 )
          goto LABEL_26;
        if ( v15 <= 0x11 )
        {
          if ( v15 == 17 )
            goto LABEL_35;
          if ( v15 <= 9 )
          {
            if ( v15 == 9 )
              goto LABEL_26;
            if ( !v15 )
              goto LABEL_26;
            v16 = v15 - 1;
            if ( !v16 )
              goto LABEL_26;
            v17 = v16 - 1;
            if ( !v17 )
              goto LABEL_26;
            v18 = v17 - 1;
            if ( !v18 )
              goto LABEL_26;
            v20 = v18 - 2;
            v19 = v20 == 0;
LABEL_23:
            if ( v19 )
              goto LABEL_26;
            v21 = v20 - 1;
            if ( !v21 )
              goto LABEL_26;
            v22 = v21 - 1;
            if ( !v22 )
              goto LABEL_26;
            goto LABEL_74;
          }
          v24 = v15 - 10;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( !v26 )
                goto LABEL_26;
              v27 = v26 - 1;
              if ( !v27 )
                goto LABEL_26;
              v28 = v27 - 1;
              if ( !v28 )
                goto LABEL_26;
              v29 = v28 - 1;
              if ( !v29 )
                goto LABEL_26;
              if ( v29 != 1 )
                goto LABEL_94;
            }
LABEL_35:
            v23 = -2147483210;
            goto LABEL_27;
          }
LABEL_26:
          v23 = -1073741808;
LABEL_27:
          *(_DWORD *)(v7 + 48) = v23;
          *(_QWORD *)(v7 + 56) = 0;
          goto LABEL_122;
        }
        if ( v15 <= 0x1A )
        {
          if ( v15 == 26 )
            goto LABEL_46;
          v30 = v15 - 18;
          if ( !v30 )
            goto LABEL_46;
          v31 = v30 - 1;
          if ( !v31 )
            goto LABEL_46;
          v32 = v31 - 1;
          if ( !v32 )
          {
            v23 = -1073741800;
            goto LABEL_27;
          }
          v33 = v32 - 1;
          if ( !v33 )
            goto LABEL_94;
          v34 = v33 - 1;
          if ( !v34 )
            goto LABEL_46;
          v36 = v34 - 2;
          v35 = v36 == 0;
          goto LABEL_44;
        }
        v37 = v15 - 27;
        if ( !v37 )
        {
          v23 = -1073741637;
          goto LABEL_27;
        }
        v38 = v37 - 1;
        if ( !v38 )
          goto LABEL_26;
        v39 = v38 - 2;
        if ( v39 )
        {
          v20 = v39 - 1;
          v19 = v20 == 0;
          goto LABEL_23;
        }
LABEL_86:
        v23 = -1073741790;
        goto LABEL_27;
      }
      v40 = v15 - 129;
      if ( !v40 )
        goto LABEL_26;
      v22 = v40 - 1;
      if ( !v22 )
        goto LABEL_86;
LABEL_74:
      v50 = v22 == 1;
LABEL_93:
      if ( !v50 )
        goto LABEL_94;
      goto LABEL_26;
    }
    v41 = (unsigned __int8)(v8 >> 1);
    if ( v41 > 0x80 )
    {
      v61 = v41 - 129;
      if ( !v61 )
        goto LABEL_26;
      v22 = v61 - 1;
      if ( !v22 )
      {
        v23 = -1073741661;
        goto LABEL_27;
      }
      goto LABEL_74;
    }
    if ( v41 == 128 )
      goto LABEL_26;
    if ( v41 > 0xE )
    {
      if ( v41 <= 0x16 )
      {
        if ( v41 == 22 )
          goto LABEL_26;
        v51 = v41 - 15;
        if ( !v51 )
          goto LABEL_26;
        v52 = v51 - 1;
        if ( !v52 )
          goto LABEL_26;
        v53 = v52 - 1;
        if ( !v53 )
          goto LABEL_26;
        v54 = v53 - 1;
        if ( !v54 )
          goto LABEL_26;
        v55 = v54 - 1;
        if ( !v55 )
          goto LABEL_26;
        v14 = v55 - 1;
        if ( v14 )
        {
LABEL_85:
          if ( v14 == 1 )
            goto LABEL_86;
LABEL_94:
          v23 = -1073741435;
          goto LABEL_27;
        }
LABEL_46:
        v23 = -1073741436;
        goto LABEL_27;
      }
      v56 = v41 - 24;
      if ( !v56 )
        goto LABEL_26;
      v57 = v56 - 1;
      if ( !v57 || (v58 = v57 - 1) == 0 )
      {
        v23 = -1073741643;
        goto LABEL_27;
      }
      v59 = v58 - 1;
      if ( v59 )
      {
        v60 = v59 - 1;
        if ( !v60 )
          goto LABEL_94;
        v50 = v60 == 2;
        goto LABEL_93;
      }
    }
    else
    {
      if ( v41 == 14 )
        goto LABEL_26;
      if ( v41 > 7 )
      {
        v46 = v41 - 8;
        if ( v46 )
        {
          v47 = v46 - 1;
          if ( v47 )
          {
            v48 = v47 - 1;
            if ( v48 )
            {
              v49 = v48 - 1;
              if ( !v49 )
                goto LABEL_26;
              v22 = v49 - 1;
              if ( !v22 )
              {
                v23 = -1073740758;
                goto LABEL_27;
              }
              goto LABEL_74;
            }
          }
        }
      }
      else if ( v41 != 7 )
      {
        if ( !v41 )
        {
          v23 = 0;
          goto LABEL_27;
        }
        v42 = v41 - 1;
        if ( !v42 )
          goto LABEL_26;
        v43 = v42 - 1;
        if ( !v43 )
          goto LABEL_26;
        v44 = v43 - 1;
        if ( !v44 )
          goto LABEL_94;
        v45 = v44 - 1;
        if ( !v45 )
          goto LABEL_94;
        v36 = v45 - 1;
        v35 = v36 == 0;
LABEL_44:
        if ( !v35 && v36 != 1 )
          goto LABEL_94;
        goto LABEL_46;
      }
    }
    v23 = -1073741248;
    goto LABEL_27;
  }
  v62 = *(unsigned __int16 *)(a3 + 14);
  if ( (v62 & 0xE00) == 0 )
  {
    if ( (v62 & 0x1FE) == 0 )
    {
      if ( (*((_QWORD *)Context + 121) & 0x10000LL) == 0 )
      {
        if ( !(unsigned __int8)IsNvmeFirmwareActivateWithoutResetEnabled(Context)
          || (*((_QWORD *)Context + 121) & 0x400LL) != 0 )
        {
          *((_QWORD *)Context + 121) |= v63;
          *((_QWORD *)Context + 121) &= ~0x400uLL;
          v65 = (struct _IO_WORKITEM *)*((_QWORD *)Context + 169);
          *((_QWORD *)Context + 121) |= 0x800000uLL;
          *((_QWORD *)Context + 166) = NvmeAdapterFirmwareActivateAfterResetCallback;
          *((_QWORD *)Context + 165) = a2;
          *((_QWORD *)Context + 167) = a2;
          Context[1344] = 0;
          IoQueueWorkItemEx(v65, NvmeAdapterFirmwareActivateResetWorker, DelayedWorkQueue, Context + 1320);
          v64 = L"Queued identify update worker after firmware activation (1).";
          LOBYTE(v5) = 0;
        }
        else
        {
          IoQueueWorkItemEx(
            *((PIO_WORKITEM *)Context + 169),
            NvmeAdapterFirmwareUpdateIdentifyWorker,
            DelayedWorkQueue,
            Context);
          v64 = L"Queued identify update worker after firmware activation.";
        }
        StorEtwNvmeControllerEvent(
          (_DWORD)Context,
          1,
          4,
          (_DWORD)v64,
          (__int64)&word_140155F3C,
          0,
          (__int64)&word_140155F3C,
          0,
          (__int64)&word_140155F3C,
          0,
          (__int64)&word_140155F3C,
          0,
          (__int64)&word_140155F3C,
          0,
          (__int64)&word_140155F3C,
          0,
          (__int64)&word_140155F3C,
          0,
          (__int64)&word_140155F3C,
          0);
      }
      v23 = 0;
      goto LABEL_122;
    }
LABEL_121:
    StorEtwNvmeControllerEvent(
      (_DWORD)Context,
      1,
      2,
      (unsigned int)L"Firmware activation failed (2).",
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0);
    v23 = -1073741435;
    goto LABEL_122;
  }
  if ( (v62 & 0xE00) != 0x200 )
    goto LABEL_121;
  if ( (unsigned __int8)(v62 >> 1) == 7 )
  {
    v66 = L"Controller reported invalid image on firmware activate.";
  }
  else
  {
    if ( (unsigned __int8)(v62 >> 1) == 11 )
    {
      StorEtwNvmeControllerEvent(
        (_DWORD)Context,
        1,
        3,
        (unsigned int)L"Controller requires conventional reset after firmware activation.  Device should be power cycled t"
                       "o complete update.",
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0);
      v23 = -2147483210;
      goto LABEL_122;
    }
    if ( (unsigned int)(unsigned __int8)(v62 >> 1) - 16 < 2 )
    {
      *((_QWORD *)Context + 121) |= 0x20uLL;
      v23 = 0;
      v67 = (struct _IO_WORKITEM *)*((_QWORD *)Context + 169);
      *((_QWORD *)Context + 121) |= 0x800000uLL;
      *((_QWORD *)Context + 166) = NvmeAdapterFirmwareActivateAfterResetCallback;
      *((_QWORD *)Context + 165) = a2;
      *((_QWORD *)Context + 167) = a2;
      Context[1344] = (v62 & 0x1FE) == 32;
      IoQueueWorkItemEx(v67, NvmeAdapterFirmwareActivateResetWorker, DelayedWorkQueue, Context + 1320);
      LOBYTE(v5) = 0;
      StorEtwNvmeControllerEvent(
        (_DWORD)Context,
        1,
        4,
        (unsigned int)L"Queued controller reset after firmware activation (2).",
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0);
      goto LABEL_122;
    }
    if ( (unsigned __int8)IsNvmeFirmwareActivateWithoutResetEnabled(Context)
      && (*((_QWORD *)Context + 121) & 0x400LL) == 0
      && (*((_QWORD *)Context + 121) & 0x10000LL) == 0 )
    {
      StorEtwNvmeControllerEvent(
        (_DWORD)Context,
        1,
        2,
        (unsigned int)L"Firmware activation without reset failed, attempting to re-active with reset.",
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0,
        (__int64)&word_140155F3C,
        0);
      *((_QWORD *)Context + 121) |= 0x400uLL;
      v23 = NvmeAdapterFirmwareActivateIoctl(v6, Context, v7, a2, 0);
      v5 = v23 >> 31;
      goto LABEL_122;
    }
    v66 = L"Firmware activation failed (1).";
  }
  StorEtwNvmeControllerEvent(
    (_DWORD)Context,
    1,
    2,
    (_DWORD)v66,
    (__int64)&word_140155F3C,
    0,
    (__int64)&word_140155F3C,
    0,
    (__int64)&word_140155F3C,
    0,
    (__int64)&word_140155F3C,
    0,
    (__int64)&word_140155F3C,
    0,
    (__int64)&word_140155F3C,
    0,
    (__int64)&word_140155F3C,
    0,
    (__int64)&word_140155F3C,
    0);
  v23 = -1073741808;
LABEL_122:
  *((_QWORD *)Context + 121) &= ~0x10000uLL;
  if ( (_BYTE)v5 )
  {
    *(_DWORD *)(v7 + 48) = v23;
    *((_QWORD *)Context + 121) &= ~0x800uLL;
    *((_QWORD *)Context + 121) &= ~0x400uLL;
    *((_QWORD *)Context + 121) &= ~0x800000uLL;
    _interlockedbittestandreset((volatile signed __int32 *)(*(_QWORD *)a2 + 4256LL), 3u);
    NvmeControllerReclaimExtendedCommand(Context, a2);
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v6 + 160));
    v19 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(v7 + 141) = -84;
    if ( v19 )
      goto LABEL_188;
    v92 = 0;
    IoGetActivityIdIrp(v7, &v92);
    v69 = *(_QWORD *)(v7 + 184);
    if ( *(_BYTE *)v69 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_188;
      v72 = EventNonReadWriteRequestComplete;
      goto LABEL_187;
    }
    if ( *(_BYTE *)v69 != 15 )
    {
      if ( *(_BYTE *)v69 != 27 )
        goto LABEL_188;
      if ( *(_BYTE *)(v69 + 1) == 7 && !*(_DWORD *)(v69 + 8) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v70 = *(int **)(v7 + 56);
          if ( v70 )
            v71 = *v70;
          else
            v71 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v71, v69, (unsigned int)&v92, v7, v71, *(_DWORD *)(v7 + 48));
        }
        goto LABEL_188;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_188;
      v72 = EventPnpRequestComplete;
LABEL_187:
      McTemplateK0pd_EtwWriteTransfer(v68, v72, &v92, v7, *(_DWORD *)(v7 + 48));
      goto LABEL_188;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_188;
    v73 = *(_QWORD *)(v69 + 8);
    if ( *(_BYTE *)(v73 + 2) == 40 )
    {
      if ( *(_DWORD *)(v73 + 20) )
        goto LABEL_188;
      v74 = *(_DWORD *)(v73 + 56);
      if ( !v74 )
        goto LABEL_188;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      v79 = 0;
      v80 = 0;
      while ( 1 )
      {
        v68 = *(unsigned int *)(v73 + 4LL * v79 + 120);
        if ( (unsigned int)v68 >= 0x80 )
        {
          v81 = *(unsigned int *)(v73 + 16);
          if ( (unsigned int)v68 < (unsigned int)v81 )
          {
            v82 = (unsigned int)v68;
            v83 = *(_DWORD *)(v68 + v73) - 64;
            if ( v83 )
            {
              LODWORD(v68) = v83 - 1;
              if ( (_DWORD)v68 )
              {
                if ( (_DWORD)v68 == 1 )
                {
                  LODWORD(v68) = v82 + 40;
                  if ( v82 + 40 <= v81 )
                  {
                    if ( *(_DWORD *)(v82 + v73 + 12) )
                      v76 = (char *)(v82 + v73 + 32);
                    v78 = *(_BYTE **)(v82 + v73 + 24);
                    goto LABEL_161;
                  }
                }
              }
              else
              {
                LODWORD(v68) = v82 + 56;
                if ( v82 + 56 <= v81 )
                {
                  v80 = 1;
                  if ( *(_BYTE *)(v82 + v73 + 10) )
                    v76 = (char *)(v82 + v73 + 24);
                  v77 = *(_BYTE *)(v82 + v73 + 8);
                  v78 = *(_BYTE **)(v82 + v73 + 16);
                  v75 = *(_BYTE *)(v82 + v73 + 9);
                }
              }
            }
            else
            {
              LODWORD(v68) = v82 + 40;
              if ( v82 + 40 <= v81 )
              {
                if ( *(_BYTE *)(v82 + v73 + 10) )
                  v76 = (char *)(v82 + v73 + 24);
                v78 = *(_BYTE **)(v82 + v73 + 16);
LABEL_161:
                v75 = *(_BYTE *)(v82 + v73 + 9);
                v77 = *(_BYTE *)(v82 + v73 + 8);
LABEL_162:
                if ( v76 )
                {
                  v84 = *v76;
                  goto LABEL_165;
                }
                goto LABEL_188;
              }
            }
            if ( v80 )
              goto LABEL_162;
          }
        }
        if ( ++v79 >= v74 )
          goto LABEL_162;
      }
    }
    v84 = *(_BYTE *)(v73 + 72);
    v78 = *(_BYTE **)(v73 + 32);
    v75 = *(_BYTE *)(v73 + 11);
    v77 = *(_BYTE *)(v73 + 4);
    if ( *(_BYTE *)(v73 + 2) )
      goto LABEL_188;
LABEL_165:
    LOBYTE(v68) = v84 - 8;
    if ( (v68 & 0x5D) == 0 )
    {
      v85 = *(_BYTE *)(v73 + 3);
      if ( v85 == 1 || !v78 || !v75 )
        goto LABEL_183;
      LOBYTE(v73) = 0;
      v68 = (unsigned __int64)&v78[v75];
      v86 = 0;
      v87 = v78 + 8;
      v88 = 0;
      if ( (unsigned __int8)((*v78 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v87 <= v68 )
        {
          v86 = v78[2];
          LOBYTE(v73) = v78[1] & 0xF;
          v88 = v78[3];
LABEL_180:
          v91 = 1;
          goto LABEL_182;
        }
      }
      else if ( (unsigned __int64)v87 <= v68 )
      {
        v89 = v78 + 13;
        LOBYTE(v73) = v78[2] & 0xF;
        v90 = v75;
        if ( (unsigned int)(unsigned __int8)v78[7] + 8 <= v75 )
          v90 = (unsigned __int8)v78[7] + 8;
        v68 = (unsigned __int64)&v78[v90];
        if ( (unsigned __int64)v89 <= v68 )
          v86 = v78[12];
        if ( (unsigned __int64)(v78 + 14) > v68 )
          v88 = 0;
        else
          v88 = *v89;
        goto LABEL_180;
      }
      v91 = 0;
LABEL_182:
      if ( v91 )
      {
LABEL_184:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v68,
          v73,
          (unsigned int)&v92,
          v7,
          *(_DWORD *)(v7 + 48),
          v85,
          v77,
          v73,
          v86,
          v88,
          v7);
        goto LABEL_188;
      }
LABEL_183:
      LOBYTE(v73) = 0;
      v86 = 0;
      v88 = 0;
      goto LABEL_184;
    }
LABEL_188:
    IofCompleteRequest((PIRP)v7, 1);
  }
}

```

## disassembly

```asm
0x140073320  mov     r11, rsp
0x140073323  mov     [r11+18h], rbx
0x140073327  push    rbp
0x140073328  push    rsi
0x140073329  push    rdi
0x14007332a  push    r12
0x14007332c  push    r13
0x14007332e  push    r14
0x140073330  push    r15
0x140073332  sub     rsp, 0C0h
0x140073339  mov     rax, cs:__security_cookie
0x140073340  xor     rax, rsp
0x140073343  mov     [rsp+0F8h+var_48], rax
0x14007334b  mov     rax, [rdx]
0x14007334e  mov     r13d, 1
0x140073354  xor     r12d, r12d
0x140073357  mov     r14, rdx
0x14007335a  mov     rdi, rcx
0x14007335d  mov     bpl, r13b
0x140073360  mov     r15, [rax+1080h]
0x140073367  lea     ebx, [r13+7Fh]
0x14007336b  mov     rsi, [rax+1058h]
0x140073372  lea     r10d, [r13+1Fh]
0x140073376  test    r8, r8
0x140073379  jnz     loc_1400736C1
0x14007337f  mov     [r11-60h], r12
0x140073383  lea     rax, word_140155F3C
0x14007338a  mov     [r11-68h], rax
0x14007338e  lea     r9, aFirmwareActiva_0; "Firmware activation caused null CQE."
0x140073395  mov     [r11-70h], r12
0x140073399  lea     r8d, [r13+2]
0x14007339d  mov     [r11-78h], rax
0x1400733a1  mov     edx, r13d
0x1400733a4  mov     [r11-80h], r12
0x1400733a8  mov     [rsp+0F8h+var_88], rax
0x1400733ad  mov     [rsp+0F8h+var_90], r12
0x1400733b2  mov     [rsp+0F8h+var_98], rax
0x1400733b7  mov     [rsp+0F8h+var_A0], r12
0x1400733bc  mov     [rsp+0F8h+var_A8], rax
0x1400733c1  mov     [rsp+0F8h+var_B0], r12
0x1400733c6  mov     [rsp+0F8h+var_B8], rax
0x1400733cb  mov     [rsp+0F8h+var_C0], r12
0x1400733d0  mov     [rsp+0F8h+var_C8], rax
0x1400733d5  mov     [rsp+0F8h+var_D0], r12
0x1400733da  mov     [rsp+0F8h+var_D8], rax
0x1400733df  call    StorEtwNvmeControllerEvent
0x1400733e4  mov     rcx, [r14]
0x1400733e7  mov     edx, 0FE0Dh
0x1400733ec  mov     [rcx+10A4h], r12w
0x1400733f4  mov     ecx, 0F1FFh
0x1400733f9  mov     rax, [r14]
0x1400733fc  and     [rax+10A4h], cx
0x140073403  mov     rcx, [r14]
0x140073406  movzx   eax, word ptr [rcx+10A4h]
0x14007340d  and     ax, dx
0x140073410  or      ax, 0Ch
0x140073414  mov     [rcx+10A4h], ax
0x14007341b  mov     rax, [r14]
0x14007341e  movzx   ecx, word ptr [rax+10A4h]
0x140073425  mov     edx, ecx
0x140073427  shr     edx, 9
0x14007342a  and     edx, 7
0x14007342d  jz      loc_140073582
0x140073433  sub     edx, r13d
0x140073436  jz      short loc_140073480
0x140073438  sub     edx, r13d
0x14007343b  jnz     loc_14007368E
0x140073441  shr     ecx, 1
0x140073443  movzx   ecx, cl
0x140073446  sub     ecx, ebx
0x140073448  jz      loc_14007368E
0x14007344e  sub     ecx, r13d
0x140073451  jz      loc_14007368E
0x140073457  sub     ecx, r13d
0x14007345a  jz      loc_14007368E
0x140073460  sub     ecx, r13d
0x140073463  jz      loc_14007368E
0x140073469  sub     ecx, r13d
0x14007346c  jz      loc_14007368E
0x140073472  sub     ecx, r13d
0x140073475  jz      loc_14007368E
0x14007347b  jmp     loc_140073659
0x140073480  shr     ecx, 1
0x140073482  movzx   ecx, cl
0x140073485  cmp     ecx, ebx
0x140073487  ja      loc_14007356B
0x14007348d  jz      short loc_1400734C3
0x14007348f  cmp     ecx, 11h
0x140073492  ja      short loc_140073502
0x140073494  jz      short loc_1400734FB
0x140073496  cmp     ecx, 9
0x140073499  ja      short loc_1400734D4
0x14007349b  jz      short loc_1400734C3
0x14007349d  test    ecx, ecx
0x14007349f  jz      short loc_1400734C3
0x1400734a1  sub     ecx, r13d
0x1400734a4  jz      short loc_1400734C3
0x1400734a6  sub     ecx, r13d
0x1400734a9  jz      short loc_1400734C3
0x1400734ab  sub     ecx, r13d
0x1400734ae  jz      short loc_1400734C3
0x1400734b0  sub     ecx, 2
0x1400734b3  jz      short loc_1400734C3
0x1400734b5  sub     ecx, r13d
0x1400734b8  jz      short loc_1400734C3
0x1400734ba  sub     ecx, r13d
0x1400734bd  jnz     loc_1400735FC
0x1400734c3  mov     ebx, 0C0000010h
0x1400734c8  mov     [rsi+30h], ebx
0x1400734cb  mov     [rsi+38h], r12
0x1400734cf  jmp     loc_140073BEC
0x1400734d4  sub     ecx, 0Ah
0x1400734d7  jz      short loc_1400734C3
0x1400734d9  sub     ecx, r13d
0x1400734dc  jz      short loc_1400734FB
0x1400734de  sub     ecx, r13d
0x1400734e1  jz      short loc_1400734C3
0x1400734e3  sub     ecx, r13d
0x1400734e6  jz      short loc_1400734C3
0x1400734e8  sub     ecx, r13d
0x1400734eb  jz      short loc_1400734C3
0x1400734ed  sub     ecx, r13d
0x1400734f0  jz      short loc_1400734C3
0x1400734f2  cmp     ecx, r13d
0x1400734f5  jnz     loc_14007368E
0x1400734fb  mov     ebx, 800001B6h
0x140073500  jmp     short loc_1400734C8
0x140073502  cmp     ecx, 1Ah
0x140073505  ja      short loc_140073542
0x140073507  jz      short loc_140073534
0x140073509  sub     ecx, 12h
0x14007350c  jz      short loc_140073534
0x14007350e  sub     ecx, r13d
0x140073511  jz      short loc_140073534
0x140073513  sub     ecx, r13d
0x140073516  jz      short loc_14007353B
0x140073518  sub     ecx, r13d
0x14007351b  jz      loc_14007368E
0x140073521  sub     ecx, r13d
0x140073524  jz      short loc_140073534
0x140073526  sub     ecx, 2
0x140073529  jz      short loc_140073534
0x14007352b  cmp     ecx, r13d
0x14007352e  jnz     loc_14007368E
0x140073534  mov     ebx, 0C0000184h
0x140073539  jmp     short loc_1400734C8
0x14007353b  mov     ebx, 0C0000018h
0x140073540  jmp     short loc_1400734C8
0x140073542  sub     ecx, 1Bh
0x140073545  jz      short loc_140073561
0x140073547  sub     ecx, r13d
0x14007354a  jz      loc_1400734C3
0x140073550  sub     ecx, 2
0x140073553  jz      loc_14007365E
0x140073559  sub     ecx, r13d
0x14007355c  jmp     loc_1400734B3
0x140073561  mov     ebx, 0C00000BBh
0x140073566  jmp     loc_1400734C8
0x14007356b  sub     ecx, 81h
0x140073571  jz      loc_1400734C3
0x140073577  sub     ecx, r13d
0x14007357a  jz      loc_14007365E
0x140073580  jmp     short loc_1400735FC
0x140073582  shr     ecx, 1
0x140073584  movzx   ecx, cl
0x140073587  cmp     ecx, ebx
0x140073589  ja      loc_1400736A2
0x14007358f  jz      loc_1400734C3
0x140073595  cmp     ecx, 0Eh
0x140073598  ja      short loc_140073618
0x14007359a  jz      loc_1400734C3
0x1400735a0  cmp     ecx, 7
0x1400735a3  ja      short loc_1400735DF
0x1400735a5  jz      short loc_14007360E
0x1400735a7  test    ecx, ecx
0x1400735a9  jz      short loc_1400735D7
0x1400735ab  sub     ecx, r13d
0x1400735ae  jz      loc_1400734C3
0x1400735b4  sub     ecx, r13d
0x1400735b7  jz      loc_1400734C3
0x1400735bd  sub     ecx, r13d
0x1400735c0  jz      loc_14007368E
0x1400735c6  sub     ecx, r13d
0x1400735c9  jz      loc_14007368E
0x1400735cf  sub     ecx, r13d
0x1400735d2  jmp     loc_140073529
0x1400735d7  mov     ebx, r12d
0x1400735da  jmp     loc_1400734C8
0x1400735df  sub     ecx, 8
0x1400735e2  jz      short loc_14007360E
0x1400735e4  sub     ecx, r13d
0x1400735e7  jz      short loc_14007360E
0x1400735e9  sub     ecx, r13d
0x1400735ec  jz      short loc_14007360E
0x1400735ee  sub     ecx, r13d
0x1400735f1  jz      loc_1400734C3
0x1400735f7  sub     ecx, r13d
0x1400735fa  jz      short loc_140073604
0x1400735fc  cmp     ecx, r13d
0x1400735ff  jmp     loc_140073688
0x140073604  mov     ebx, 0C000042Ah
0x140073609  jmp     loc_1400734C8
0x14007360e  mov     ebx, 0C0000240h
0x140073613  jmp     loc_1400734C8
0x140073618  cmp     ecx, 16h
0x14007361b  ja      short loc_140073668
0x14007361d  jz      loc_1400734C3
0x140073623  sub     ecx, 0Fh
0x140073626  jz      loc_1400734C3
0x14007362c  sub     ecx, r13d
0x14007362f  jz      loc_1400734C3
0x140073635  sub     ecx, r13d
0x140073638  jz      loc_1400734C3
0x14007363e  sub     ecx, r13d
0x140073641  jz      loc_1400734C3
0x140073647  sub     ecx, r13d
0x14007364a  jz      loc_1400734C3
0x140073650  sub     ecx, r13d
0x140073653  jz      loc_140073534
0x140073659  cmp     ecx, r13d
0x14007365c  jnz     short loc_14007368E
0x14007365e  mov     ebx, 0C0000022h
0x140073663  jmp     loc_1400734C8
0x140073668  sub     ecx, 18h
0x14007366b  jz      loc_1400734C3
0x140073671  sub     ecx, r13d
0x140073674  jz      short loc_140073698
0x140073676  sub     ecx, r13d
0x140073679  jz      short loc_140073698
0x14007367b  sub     ecx, r13d
0x14007367e  jz      short loc_14007360E
0x140073680  sub     ecx, r13d
0x140073683  jz      short loc_14007368E
0x140073685  cmp     ecx, 2
0x140073688  jz      loc_1400734C3
0x14007368e  mov     ebx, 0C0000185h
0x140073693  jmp     loc_1400734C8
0x140073698  mov     ebx, 0C00000B5h
0x14007369d  jmp     loc_1400734C8
0x1400736a2  sub     ecx, 81h
0x1400736a8  jz      loc_1400734C3
0x1400736ae  sub     ecx, r13d
0x1400736b1  jnz     loc_1400735FC
0x1400736b7  mov     ebx, 0C00000A3h
0x1400736bc  jmp     loc_1400734C8
0x1400736c1  movzx   edx, word ptr [r8+0Eh]
0x1400736c6  mov     ecx, 0E00h
0x1400736cb  movzx   eax, dx
0x1400736ce  and     ax, cx
0x1400736d1  jnz     loc_14007383D
0x1400736d7  mov     eax, 1FEh
0x1400736dc  test    ax, dx
0x1400736df  jnz     loc_140073B6C
0x1400736e5  mov     rax, [rdi+3C8h]
0x1400736ec  bt      rax, 10h
0x1400736f1  jb      loc_140073835
0x1400736f7  mov     rcx, rdi
0x1400736fa  call    IsNvmeFirmwareActivateWithoutResetEnabled
0x1400736ff  test    al, al
0x140073701  jz      short loc_14007373D
0x140073703  mov     rax, [rdi+3C8h]
0x14007370a  bt      rax, 0Ah
0x14007370f  jb      short loc_14007373D
0x140073711  mov     rcx, [rdi+548h]; IoWorkItem
0x140073718  lea     rdx, NvmeAdapterFirmwareUpdateIdentifyWorker; WorkerRoutine
0x14007371f  mov     r9, rdi; Context
0x140073722  mov     r8d, r13d; QueueType
0x140073725  call    cs:__imp_IoQueueWorkItemEx
0x14007372c  nop     dword ptr [rax+rax+00h]
0x140073731  lea     r9, aQueuedIdentify; "Queued identify update worker after fir"...
0x140073738  jmp     loc_1400737C1
0x14007373d  mov     rax, [rdi+3C8h]
0x140073744  lea     r9, [rdi+528h]; Context
0x14007374b  or      rax, r10
0x14007374e  lea     rdx, NvmeAdapterFirmwareActivateResetWorker; WorkerRoutine
0x140073755  mov     [rdi+3C8h], rax
0x14007375c  mov     r8d, r13d; QueueType
0x14007375f  mov     rax, [rdi+3C8h]
0x140073766  btr     rax, 0Ah
0x14007376b  mov     [rdi+3C8h], rax
0x140073772  mov     rax, [rdi+3C8h]
0x140073779  mov     rcx, [rdi+548h]; IoWorkItem
0x140073780  bts     rax, 17h
0x140073785  mov     [rdi+3C8h], rax
0x14007378c  lea     rax, NvmeAdapterFirmwareActivateAfterResetCallback
0x140073793  mov     [rdi+530h], rax
0x14007379a  mov     [r9], r14
0x14007379d  mov     [rdi+538h], r14
0x1400737a4  mov     [rdi+540h], r12b
0x1400737ab  call    cs:__imp_IoQueueWorkItemEx
0x1400737b2  nop     dword ptr [rax+rax+00h]
0x1400737b7  lea     r9, aQueuedIdentify_0; "Queued identify update worker after fir"...
0x1400737be  mov     bpl, r12b
0x1400737c1  mov     [rsp+0F8h+var_60], r12
0x1400737c9  lea     rax, word_140155F3C
0x1400737d0  mov     [rsp+0F8h+var_68], rax
0x1400737d8  mov     r8d, 4
0x1400737de  mov     [rsp+0F8h+var_70], r12
0x1400737e6  mov     edx, r13d
0x1400737e9  mov     [rsp+0F8h+var_78], rax
  ... truncated ...
```
