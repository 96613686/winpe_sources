# NvmeNamespaceDeviceUsageNotificationIrp

- ea: `0x14011dcd8`
- end: `0x14011e3b2`
- name: `NvmeNamespaceDeviceUsageNotificationIrp`
- size: `1754`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140040b64`

## callees

- `0x1400232c0`
- `0x1400421f4`
- `0x140046454`
- `0x140046c60`
- `0x140054800`
- `0x140067e24`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400bb90c`
- `0x1400e6c00`
- `0x1400e7730`
- `0x14011dcd8`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14011e0d2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14011e0d2`
- `ntoskrnl!IofCompleteRequest` at `0x14011e37b`
- `ntoskrnl!IofCompleteRequest` at `0x14011e37b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14011e080`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14011e080`
- `ntoskrnl!IoFreeIrp` at `0x14011e091`
- `ntoskrnl!IoFreeIrp` at `0x14011e091`
- `ntoskrnl!IoAllocateIrp` at `0x14011dec5`
- `ntoskrnl!IoAllocateIrp` at `0x14011dec5`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14011dff1`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14011dff1`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceDeviceUsageNotificationIrp(__int64 a1, __int64 a2)
{
  int v2; // eax
  char v5; // r14
  __int64 v6; // r13
  __int64 v7; // r15
  _QWORD *v8; // rsi
  volatile signed __int32 *v9; // r12
  char v10; // dl
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  bool v16; // cf
  int v17; // r8d
  int v18; // r9d
  IRP *v19; // rax
  int Status; // r13d
  _IO_STACK_LOCATION *v21; // rdx
  PIRP v22; // rcx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v24; // eax
  int v25; // eax
  bool v26; // zf
  unsigned __int64 v27; // rcx
  _BYTE *v28; // rdx
  int *v29; // rax
  int v30; // ecx
  __int64 *v31; // rdx
  __int64 v32; // rdx
  unsigned int v33; // r12d
  char v34; // bl
  unsigned __int8 v35; // r10
  char *v36; // r11
  _BYTE *v37; // r9
  __int64 v38; // r15
  unsigned __int64 v39; // rsi
  __int64 v40; // r8
  int v41; // ecx
  char v42; // cl
  char v43; // si
  char v44; // r11
  char v45; // r8
  _BYTE *v46; // rax
  char *v47; // r8
  unsigned int v48; // eax
  char v50; // [rsp+60h] [rbp-A0h]
  char v51; // [rsp+60h] [rbp-A0h]
  char v52; // [rsp+61h] [rbp-9Fh] BYREF
  int v53; // [rsp+64h] [rbp-9Ch]
  PIRP Irp; // [rsp+68h] [rbp-98h] BYREF
  int v55; // [rsp+70h] [rbp-90h] BYREF
  int v56; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v57; // [rsp+78h] [rbp-88h]
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  __int128 v59; // [rsp+88h] [rbp-78h] BYREF
  __int64 v60[16]; // [rsp+A0h] [rbp-60h] BYREF
  char v61[16]; // [rsp+120h] [rbp+20h] BYREF
  char *v62; // [rsp+130h] [rbp+30h]
  __int64 v63; // [rsp+138h] [rbp+38h]
  char v64[16]; // [rsp+140h] [rbp+40h] BYREF

  v2 = *(_DWORD *)(a1 + 96);
  v5 = 1;
  if ( v2 )
  {
    if ( (unsigned int)(v2 - 5) > 1 )
    {
      v6 = *(_QWORD *)(a1 + 16);
      v57 = v6;
      if ( v6 )
      {
        v7 = *(_QWORD *)(v6 + 128);
        v8 = (_QWORD *)(a2 + 184);
        v9 = 0;
        *(_QWORD *)&v59 = *(_QWORD *)(a2 + 184);
        v10 = *(_BYTE *)(v59 + 8);
        v53 = *(_DWORD *)(v59 + 16);
        v50 = v10;
        if ( v53 == 1 )
        {
          v9 = (volatile signed __int32 *)(a1 + 272);
        }
        else if ( v53 == 2 )
        {
          v9 = (volatile signed __int32 *)(a1 + 280);
        }
        else
        {
          if ( v53 != 3 )
          {
            if ( v53 == 4 )
            {
              v11 = *(_QWORD *)(a1 + 112);
              if ( v10 )
              {
                *(_QWORD *)(a1 + 112) = v11 | 0x40;
                v12 = *(_QWORD *)(v7 + 1336);
                *(_QWORD *)(v7 + 152) |= 0x2000uLL;
                DlrmNotifyBootAdapterStatus(v12);
                if ( (unsigned int)dword_140176178 > 5 && (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL) )
                {
                  v14 = *(_QWORD *)(v7 + 1032);
                  v60[4] = (__int64)&v58;
                  v58 = 0x1000000;
                  v60[6] = v7 + 1048;
                  v60[8] = a1 + 160;
                  v55 = *(_DWORD *)(a1 + 56);
                  v60[10] = (__int64)&v55;
                  v56 = *(_DWORD *)(v7 + 56);
                  v60[12] = (__int64)&v56;
                  LODWORD(Irp) = *(unsigned __int16 *)(v6 + 4);
                  v60[14] = (__int64)&Irp;
                  v60[5] = 8;
                  v60[7] = 16;
                  v60[9] = 16;
                  v60[11] = 4;
                  v60[13] = 4;
                  v60[15] = 4;
                  tlgCreate1Sz_wchar_t(v61, v14);
                  v15 = *(_QWORD *)(v7 + 1040);
                  v16 = (*(_BYTE *)(v6 + 136) & 2) != 0;
                  v63 = 1;
                  v52 = v16 ? 20 : 17;
                  v62 = &v52;
                  tlgCreate1Sz_wchar_t(v64, v15);
                  tlgWriteTransfer_EtwWriteTransfer((int)v60, (int)&unk_140169408, v17, v18, 0xBu, (__int64)v60);
                }
              }
              else
              {
                *(_QWORD *)(a1 + 112) = v11 & 0xFFFFFFFFFFFFFFBFuLL;
                *(_QWORD *)(v7 + 152) &= ~0x2000uLL;
              }
            }
            goto LABEL_12;
          }
          v9 = (volatile signed __int32 *)(a1 + 276);
        }
        if ( v9 && !*v9 && !v10 )
        {
          Status = -1073741823;
          goto LABEL_50;
        }
LABEL_12:
        v19 = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v7 + 8) + 76LL) + 3, 0);
        Irp = v19;
        if ( !v19 )
        {
          Status = -1073741801;
          goto LABEL_50;
        }
        Status = NvmeNamespaceAcquireRemoveLock(a1, v19);
        if ( Status < 0 )
          goto LABEL_48;
        v21 = (_IO_STACK_LOCATION *)v59;
        v22 = Irp;
        Irp->Tail.Overlay.Thread = *(_ETHREAD **)(a2 + 152);
        CurrentStackLocation = v22->Tail.Overlay.CurrentStackLocation;
        v22->IoStatus.Status = -1073741637;
        CurrentStackLocation[-1] = *v21;
        Status = RaSendIrpSynchronous(*(PDEVICE_OBJECT *)(v7 + 8), v22);
        if ( Status >= 0 && (Status = Irp->IoStatus.Status, Status >= 0) )
        {
          v24 = v53;
        }
        else
        {
          if ( Status != -1073741637 )
            goto LABEL_47;
          v24 = v53;
          if ( v53 != 4 )
            goto LABEL_47;
          Status = 0;
        }
        if ( !v9 )
          goto LABEL_40;
        if ( v50 )
          _InterlockedAdd(v9, 1u);
        else
          _InterlockedDecrement(v9);
        IoInvalidateDeviceState(*(PDEVICE_OBJECT *)(a1 + 8));
        v24 = v53;
        if ( v53 == 1 )
        {
          RaidNotifyPoAboutSpecialDevice(*(_QWORD *)(a1 + 8), *(unsigned int *)v9);
          if ( v50 )
            StorPagingDeviceDumpRegister();
          goto LABEL_47;
        }
        if ( v53 != 2 )
        {
LABEL_40:
          if ( v24 == 3 )
          {
            v25 = *(_DWORD *)(a1 + 276);
            if ( v25 == 1 )
            {
              if ( !*(_QWORD *)(v7 + 104) )
              {
                *(_QWORD *)(v7 + 104) = a1;
                NvmeUpdateCrashDumpPowerReady(v7);
              }
            }
            else if ( !v25 && a1 == *(_QWORD *)(v7 + 104) )
            {
              *(_QWORD *)(v7 + 104) = 0;
            }
          }
          goto LABEL_47;
        }
        if ( v50 )
          _InterlockedAdd((volatile signed __int32 *)(v57 + 1692), 1u);
        else
          _InterlockedDecrement((volatile signed __int32 *)(v57 + 1692));
LABEL_47:
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 120));
LABEL_48:
        IoFreeIrp(Irp);
        goto LABEL_50;
      }
    }
  }
  Status = -1073741810;
  v8 = (_QWORD *)(a2 + 184);
LABEL_50:
  v26 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = Status;
  if ( v26 )
    goto LABEL_114;
  v59 = 0;
  IoGetActivityIdIrp(a2, &v59);
  v28 = (_BYTE *)*v8;
  if ( *(_BYTE *)*v8 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_114;
    v31 = EventNonReadWriteRequestComplete;
    goto LABEL_113;
  }
  if ( *(_BYTE *)*v8 != 15 )
  {
    if ( *(_BYTE *)*v8 != 27 )
      goto LABEL_114;
    if ( v28[1] == 7 && !*((_DWORD *)v28 + 2) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v29 = *(int **)(a2 + 56);
        if ( v29 )
          v30 = *v29;
        else
          v30 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v30, (_DWORD)v28, (unsigned int)&v59, a2, v30, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_114;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_114;
    v31 = EventPnpRequestComplete;
LABEL_113:
    McTemplateK0pd_EtwWriteTransfer(v27, v31, &v59, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_114;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_114;
  v32 = *((_QWORD *)v28 + 1);
  if ( *(_BYTE *)(v32 + 2) != 40 )
  {
    v42 = *(_BYTE *)(v32 + 72);
    v37 = *(_BYTE **)(v32 + 32);
    v35 = *(_BYTE *)(v32 + 11);
    v34 = *(_BYTE *)(v32 + 4);
    if ( *(_BYTE *)(v32 + 2) )
      goto LABEL_114;
LABEL_92:
    LOBYTE(v27) = v42 - 8;
    if ( (v27 & 0x5D) != 0 )
      goto LABEL_114;
    v43 = *(_BYTE *)(v32 + 3);
    if ( v43 == 1 || !v37 || !v35 )
      goto LABEL_109;
    LOBYTE(v32) = 0;
    v44 = 0;
    v45 = 0;
    v27 = (unsigned __int64)&v37[v35];
    v46 = v37 + 8;
    if ( (unsigned __int8)((*v37 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v46 <= v27 )
      {
        v44 = v37[2];
        LOBYTE(v32) = v37[1] & 0xF;
        v45 = v37[3];
        goto LABEL_108;
      }
    }
    else if ( (unsigned __int64)v46 <= v27 )
    {
      v47 = v37 + 13;
      LOBYTE(v32) = v37[2] & 0xF;
      v48 = v35;
      if ( (unsigned int)(unsigned __int8)v37[7] + 8 <= v35 )
        v48 = (unsigned __int8)v37[7] + 8;
      v27 = (unsigned __int64)&v37[v48];
      if ( (unsigned __int64)v47 <= v27 )
        v44 = v37[12];
      if ( (unsigned __int64)(v37 + 14) > v27 )
        v45 = 0;
      else
        v45 = *v47;
LABEL_108:
      if ( v5 )
      {
LABEL_110:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v27,
          v32,
          (unsigned int)&v59,
          a2,
          *(_DWORD *)(a2 + 48),
          v43,
          v34,
          v32,
          v44,
          v45,
          a2);
        goto LABEL_114;
      }
LABEL_109:
      LOBYTE(v32) = 0;
      v44 = 0;
      v45 = 0;
      goto LABEL_110;
    }
    v5 = 0;
    goto LABEL_108;
  }
  if ( *(_DWORD *)(v32 + 20) )
    goto LABEL_114;
  v33 = *(_DWORD *)(v32 + 56);
  if ( !v33 )
    goto LABEL_114;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v51 = 0;
  v37 = 0;
  v38 = 0;
  while ( 1 )
  {
    v27 = *(unsigned int *)(v32 + 4 * v38 + 120);
    if ( (unsigned int)v27 >= 0x80 )
    {
      v39 = *(unsigned int *)(v32 + 16);
      if ( (unsigned int)v27 < (unsigned int)v39 )
        break;
    }
LABEL_83:
    v38 = (unsigned int)(v38 + 1);
    if ( (unsigned int)v38 >= v33 )
      goto LABEL_89;
  }
  v40 = (unsigned int)v27;
  v41 = *(_DWORD *)(v27 + v32) - 64;
  if ( v41 )
  {
    LODWORD(v27) = v41 - 1;
    if ( (_DWORD)v27 )
    {
      if ( (_DWORD)v27 == 1 )
      {
        LODWORD(v27) = v40 + 40;
        if ( v40 + 40 <= v39 )
        {
          if ( *(_DWORD *)(v40 + v32 + 12) )
            v36 = (char *)(v40 + v32 + 32);
          v37 = *(_BYTE **)(v40 + v32 + 24);
          goto LABEL_88;
        }
      }
    }
    else
    {
      LODWORD(v27) = v40 + 56;
      if ( v40 + 56 <= v39 )
      {
        v51 = 1;
        if ( *(_BYTE *)(v40 + v32 + 10) )
          v36 = (char *)(v40 + v32 + 24);
        v34 = *(_BYTE *)(v40 + v32 + 8);
        v37 = *(_BYTE **)(v40 + v32 + 16);
        v35 = *(_BYTE *)(v40 + v32 + 9);
      }
    }
    goto LABEL_82;
  }
  LODWORD(v27) = v40 + 40;
  if ( v40 + 40 > v39 )
  {
LABEL_82:
    if ( v51 )
      goto LABEL_89;
    goto LABEL_83;
  }
  if ( *(_BYTE *)(v40 + v32 + 10) )
    v36 = (char *)(v40 + v32 + 24);
  v37 = *(_BYTE **)(v40 + v32 + 16);
LABEL_88:
  v35 = *(_BYTE *)(v40 + v32 + 9);
  v34 = *(_BYTE *)(v40 + v32 + 8);
LABEL_89:
  if ( v36 )
  {
    v42 = *v36;
    goto LABEL_92;
  }
LABEL_114:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14011dcd8  mov     [rsp-8+arg_10], rbx
0x14011dcdd  push    rbp
0x14011dcde  push    rsi
0x14011dcdf  push    rdi
0x14011dce0  push    r12
0x14011dce2  push    r13
0x14011dce4  push    r14
0x14011dce6  push    r15
0x14011dce8  lea     rbp, [rsp-60h]
0x14011dced  sub     rsp, 160h
0x14011dcf4  mov     rax, cs:__security_cookie
0x14011dcfb  xor     rax, rsp
0x14011dcfe  mov     [rbp+90h+var_40], rax
0x14011dd02  mov     eax, [rcx+60h]
0x14011dd05  mov     rdi, rdx
0x14011dd08  mov     rbx, rcx
0x14011dd0b  mov     r14d, 1
0x14011dd11  test    eax, eax
0x14011dd13  jz      loc_14011E09F
0x14011dd19  add     eax, 0FFFFFFFBh
0x14011dd1c  cmp     eax, r14d
0x14011dd1f  jbe     loc_14011E09F
0x14011dd25  mov     r13, [rcx+10h]
0x14011dd29  mov     [rsp+190h+var_118], r13
0x14011dd2e  test    r13, r13
0x14011dd31  jz      loc_14011E09F
0x14011dd37  mov     r15, [r13+80h]
0x14011dd3e  lea     rsi, [rdx+0B8h]
0x14011dd45  mov     rdx, [rsi]
0x14011dd48  xor     r12d, r12d
0x14011dd4b  mov     qword ptr [rbp+90h+var_108], rdx
0x14011dd4f  mov     ecx, [rdx+10h]
0x14011dd52  mov     dl, [rdx+8]
0x14011dd55  mov     [rsp+190h+var_12C], ecx
0x14011dd59  mov     [rsp+190h+var_130], dl
0x14011dd5d  sub     ecx, r14d
0x14011dd60  jz      loc_14011DF0B
0x14011dd66  sub     ecx, r14d
0x14011dd69  jz      loc_14011DF02
0x14011dd6f  sub     ecx, r14d
0x14011dd72  jz      loc_14011DEF9
0x14011dd78  cmp     ecx, r14d
0x14011dd7b  jnz     loc_14011DEB9
0x14011dd81  mov     rax, [rbx+70h]
0x14011dd85  test    dl, dl
0x14011dd87  jz      loc_14011DEE6
0x14011dd8d  or      rax, 40h
0x14011dd91  mov     [rbx+70h], rax
0x14011dd95  mov     rcx, [r15+538h]
0x14011dd9c  bts     qword ptr [r15+98h], 0Dh
0x14011dda5  call    DlrmNotifyBootAdapterStatus
0x14011ddaa  mov     eax, cs:dword_140176178
0x14011ddb0  cmp     eax, 5
0x14011ddb3  jbe     loc_14011DEB9
0x14011ddb9  mov     rdx, 400000000000h
0x14011ddc3  call    _tlgKeywordOn
0x14011ddc8  test    al, al
0x14011ddca  jz      loc_14011DEB9
0x14011ddd0  mov     rdx, [r15+408h]
0x14011ddd7  lea     rax, [rbp+90h+var_110]
0x14011dddb  mov     [rbp+90h+var_D0], rax
0x14011dddf  lea     rcx, [rbp+90h+var_70]
0x14011dde3  lea     rax, [r15+418h]
0x14011ddea  mov     [rbp+90h+var_110], 1000000h
0x14011ddf2  mov     [rbp+90h+var_C0], rax
0x14011ddf6  lea     rax, [rbx+0A0h]
0x14011ddfd  mov     [rbp+90h+var_B0], rax
0x14011de01  mov     eax, [rbx+38h]
0x14011de04  mov     [rsp+190h+var_120], eax
0x14011de08  lea     rax, [rsp+190h+var_120]
0x14011de0d  mov     [rbp+90h+var_A0], rax
0x14011de11  mov     eax, [r15+38h]
0x14011de15  mov     [rsp+190h+var_11C], eax
0x14011de19  lea     rax, [rsp+190h+var_11C]
0x14011de1e  mov     [rbp+90h+var_90], rax
0x14011de22  movzx   eax, word ptr [r13+4]
0x14011de27  mov     dword ptr [rsp+190h+Irp], eax
0x14011de2b  lea     rax, [rsp+190h+Irp]
0x14011de30  mov     [rbp+90h+var_80], rax
0x14011de34  mov     [rbp+90h+var_C8], 8
0x14011de3c  mov     [rbp+90h+var_B8], 10h
0x14011de44  mov     [rbp+90h+var_A8], 10h
0x14011de4c  mov     [rbp+90h+var_98], 4
0x14011de54  mov     [rbp+90h+var_88], 4
0x14011de5c  mov     [rbp+90h+var_78], 4
0x14011de64  call    _tlgCreate1Sz_wchar_t
0x14011de69  mov     cl, [r13+88h]
0x14011de70  mov     rdx, [r15+410h]
0x14011de77  and     cl, 2
0x14011de7a  neg     cl
0x14011de7c  mov     [rbp+90h+var_58], r14
0x14011de80  lea     rcx, [rbp+90h+var_50]
0x14011de84  sbb     al, al
0x14011de86  and     al, 3
0x14011de88  add     al, 11h
0x14011de8a  mov     [rsp+190h+var_12F], al
0x14011de8e  lea     rax, [rsp+190h+var_12F]
0x14011de93  mov     [rbp+90h+var_60], rax
0x14011de97  call    _tlgCreate1Sz_wchar_t
0x14011de9c  lea     rcx, [rbp+90h+var_F0]; int
0x14011dea0  mov     [rsp+190h+var_168], rcx; __int64
0x14011dea5  lea     rdx, unk_140169408; int
0x14011deac  mov     [rsp+190h+var_170], 0Bh; ULONG
0x14011deb4  call    _tlgWriteTransfer_EtwWriteTransfer
0x14011deb9  mov     rax, [r15+8]
0x14011debd  xor     edx, edx; ChargeQuota
0x14011debf  mov     cl, [rax+4Ch]
0x14011dec2  add     cl, 3; StackSize
0x14011dec5  call    cs:__imp_IoAllocateIrp
0x14011decc  nop     dword ptr [rax+rax+00h]
0x14011ded1  mov     [rsp+190h+Irp], rax
0x14011ded6  test    rax, rax
0x14011ded9  jnz     short loc_14011DF2D
0x14011dedb  mov     r13d, 0C0000017h
0x14011dee1  jmp     loc_14011E0AC
0x14011dee6  and     rax, 0FFFFFFFFFFFFFFBFh
0x14011deea  mov     [rbx+70h], rax
0x14011deee  btr     qword ptr [r15+98h], 0Dh
0x14011def7  jmp     short loc_14011DEB9
0x14011def9  lea     r12, [rbx+114h]
0x14011df00  jmp     short loc_14011DF12
0x14011df02  lea     r12, [rbx+118h]
0x14011df09  jmp     short loc_14011DF12
0x14011df0b  lea     r12, [rbx+110h]
0x14011df12  test    r12, r12
0x14011df15  jz      short loc_14011DEB9
0x14011df17  cmp     dword ptr [r12], 0
0x14011df1c  jnz     short loc_14011DEB9
0x14011df1e  test    dl, dl
0x14011df20  jnz     short loc_14011DEB9
0x14011df22  mov     r13d, 0C0000001h
0x14011df28  jmp     loc_14011E0AC
0x14011df2d  mov     rdx, rax
0x14011df30  mov     rcx, rbx
0x14011df33  call    NvmeNamespaceAcquireRemoveLock
0x14011df38  mov     r13d, eax
0x14011df3b  test    eax, eax
0x14011df3d  js      loc_14011E08C
0x14011df43  mov     rax, [rdi+98h]
0x14011df4a  mov     rdx, qword ptr [rbp+90h+var_108]
0x14011df4e  mov     rcx, [rsp+190h+Irp]
0x14011df53  mov     [rcx+98h], rax
0x14011df5a  mov     rax, [rcx+0B8h]
0x14011df61  mov     dword ptr [rcx+30h], 0C00000BBh
0x14011df68  movups  xmm0, xmmword ptr [rdx]
0x14011df6b  movups  xmmword ptr [rax-48h], xmm0
0x14011df6f  movups  xmm1, xmmword ptr [rdx+10h]
0x14011df73  movups  xmmword ptr [rax-38h], xmm1
0x14011df77  movups  xmm0, xmmword ptr [rdx+20h]
0x14011df7b  movups  xmmword ptr [rax-28h], xmm0
0x14011df7f  movups  xmm1, xmmword ptr [rdx+30h]
0x14011df83  movups  xmmword ptr [rax-18h], xmm1
0x14011df87  movsd   xmm0, qword ptr [rdx+40h]
0x14011df8c  mov     rdx, rcx; Irp
0x14011df8f  movsd   qword ptr [rax-8], xmm0
0x14011df94  mov     rcx, [r15+8]; DeviceObject
0x14011df98  call    RaSendIrpSynchronous
0x14011df9d  mov     r13d, eax
0x14011dfa0  test    eax, eax
0x14011dfa2  js      short loc_14011DFB2
0x14011dfa4  mov     r13, [rsp+190h+Irp]
0x14011dfa9  mov     r13d, [r13+30h]
0x14011dfad  test    r13d, r13d
0x14011dfb0  jns     short loc_14011DFD1
0x14011dfb2  cmp     r13d, 0C00000BBh
0x14011dfb9  jnz     loc_14011E07C
0x14011dfbf  mov     eax, [rsp+190h+var_12C]
0x14011dfc3  cmp     eax, 4
0x14011dfc6  jnz     loc_14011E07C
0x14011dfcc  xor     r13d, r13d
0x14011dfcf  jmp     short loc_14011DFD5
0x14011dfd1  mov     eax, [rsp+190h+var_12C]
0x14011dfd5  test    r12, r12
0x14011dfd8  jz      short loc_14011E045
0x14011dfda  cmp     [rsp+190h+var_130], 0
0x14011dfdf  jz      short loc_14011DFE8
0x14011dfe1  lock add [r12], r14d
0x14011dfe6  jmp     short loc_14011DFED
0x14011dfe8  lock dec dword ptr [r12]
0x14011dfed  mov     rcx, [rbx+8]; PhysicalDeviceObject
0x14011dff1  call    cs:__imp_IoInvalidateDeviceState
0x14011dff8  nop     dword ptr [rax+rax+00h]
0x14011dffd  mov     eax, [rsp+190h+var_12C]
0x14011e001  cmp     eax, r14d
0x14011e004  jnz     short loc_14011E021
0x14011e006  mov     edx, [r12]
0x14011e00a  mov     rcx, [rbx+8]
0x14011e00e  call    RaidNotifyPoAboutSpecialDevice
0x14011e013  cmp     [rsp+190h+var_130], 0
0x14011e018  jz      short loc_14011E07C
0x14011e01a  call    StorPagingDeviceDumpRegister
0x14011e01f  jmp     short loc_14011E07C
0x14011e021  cmp     eax, 2
0x14011e024  jnz     short loc_14011E045
0x14011e026  cmp     [rsp+190h+var_130], 0
0x14011e02b  mov     rax, [rsp+190h+var_118]
0x14011e030  jz      short loc_14011E03C
0x14011e032  lock add [rax+69Ch], r14d
0x14011e03a  jmp     short loc_14011E07C
0x14011e03c  lock dec dword ptr [rax+69Ch]
0x14011e043  jmp     short loc_14011E07C
0x14011e045  cmp     eax, 3
0x14011e048  jnz     short loc_14011E07C
0x14011e04a  mov     eax, [rbx+114h]
0x14011e050  cmp     eax, r14d
0x14011e053  jnz     short loc_14011E06A
0x14011e055  cmp     qword ptr [r15+68h], 0
0x14011e05a  jnz     short loc_14011E07C
0x14011e05c  mov     rcx, r15
0x14011e05f  mov     [r15+68h], rbx
0x14011e063  call    NvmeUpdateCrashDumpPowerReady
0x14011e068  jmp     short loc_14011E07C
0x14011e06a  test    eax, eax
0x14011e06c  jnz     short loc_14011E07C
0x14011e06e  cmp     rbx, [r15+68h]
0x14011e072  jnz     short loc_14011E07C
0x14011e074  mov     qword ptr [r15+68h], 0
0x14011e07c  mov     rcx, [rbx+78h]; RunRefCacheAware
0x14011e080  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14011e087  nop     dword ptr [rax+rax+00h]
0x14011e08c  mov     rcx, [rsp+190h+Irp]; Irp
0x14011e091  call    cs:__imp_IoFreeIrp
0x14011e098  nop     dword ptr [rax+rax+00h]
0x14011e09d  jmp     short loc_14011E0AC
0x14011e09f  mov     r13d, 0C000000Eh
0x14011e0a5  lea     rsi, [rdx+0B8h]
0x14011e0ac  cmp     cs:StorEtwLoggingEnabled, 0
0x14011e0b3  mov     byte ptr [rdi+8Dh], 0ACh
0x14011e0ba  mov     [rdi+30h], r13d
0x14011e0be  jz      loc_14011E376
0x14011e0c4  xorps   xmm0, xmm0
0x14011e0c7  lea     rdx, [rbp+90h+var_108]
0x14011e0cb  mov     rcx, rdi
0x14011e0ce  movups  [rbp+90h+var_108], xmm0
0x14011e0d2  call    cs:__imp_IoGetActivityIdIrp
0x14011e0d9  nop     dword ptr [rax+rax+00h]
0x14011e0de  mov     rdx, [rsi]
0x14011e0e1  movzx   eax, byte ptr [rdx]
0x14011e0e4  sub     eax, 0Eh
0x14011e0e7  jz      loc_14011E353
0x14011e0ed  sub     eax, r14d
0x14011e0f0  jz      short loc_14011E158
0x14011e0f2  cmp     eax, 0Ch
0x14011e0f5  jnz     loc_14011E376
0x14011e0fb  cmp     byte ptr [rdx+1], 7
0x14011e0ff  jnz     short loc_14011E13F
0x14011e101  cmp     dword ptr [rdx+8], 0
0x14011e105  jnz     short loc_14011E13F
0x14011e107  test    cs:byte_140177432, 40h
0x14011e10e  jz      loc_14011E376
0x14011e114  mov     rax, [rdi+38h]
0x14011e118  test    rax, rax
0x14011e11b  jz      short loc_14011E121
0x14011e11d  mov     ecx, [rax]
0x14011e11f  jmp     short loc_14011E123
0x14011e121  xor     ecx, ecx
0x14011e123  mov     eax, [rdi+30h]
0x14011e126  lea     r8, [rbp+90h+var_108]
0x14011e12a  mov     dword ptr [rsp+190h+var_168], eax
0x14011e12e  mov     r9, rdi
0x14011e131  mov     [rsp+190h+var_170], ecx
0x14011e135  call    McTemplateK0pqd_EtwWriteTransfer
0x14011e13a  jmp     loc_14011E376
0x14011e13f  test    cs:byte_140177432, 20h
0x14011e146  jz      loc_14011E376
0x14011e14c  lea     rdx, EventPnpRequestComplete
0x14011e153  jmp     loc_14011E363
0x14011e158  cmp     cs:byte_140177431, 0
0x14011e15f  jge     loc_14011E376
0x14011e165  mov     rdx, [rdx+8]
0x14011e169  movzx   eax, byte ptr [rdx+2]
0x14011e16d  cmp     al, 28h ; '('
0x14011e16f  jnz     loc_14011E25E
0x14011e175  cmp     dword ptr [rdx+14h], 0
0x14011e179  jnz     loc_14011E376
0x14011e17f  mov     r12d, [rdx+38h]
0x14011e183  test    r12d, r12d
0x14011e186  jz      loc_14011E376
0x14011e18c  xor     bl, bl
0x14011e18e  xor     r10b, r10b
0x14011e191  xor     r11d, r11d
0x14011e194  mov     [rsp+190h+var_130], bl
0x14011e198  xor     r9d, r9d
0x14011e19b  xor     r15d, r15d
0x14011e19e  mov     ecx, [rdx+r15*4+78h]
0x14011e1a3  cmp     ecx, 80h
0x14011e1a9  jb      short loc_14011E224
0x14011e1ab  mov     esi, [rdx+10h]
0x14011e1ae  cmp     ecx, esi
0x14011e1b0  jnb     short loc_14011E224
0x14011e1b2  mov     r8d, ecx
0x14011e1b5  mov     ecx, [rcx+rdx]
0x14011e1b8  sub     ecx, 40h ; '@'
0x14011e1bb  jz      short loc_14011E214
0x14011e1bd  sub     ecx, r14d
0x14011e1c0  jz      short loc_14011E1E6
0x14011e1c2  cmp     ecx, r14d
0x14011e1c5  jnz     short loc_14011E21D
0x14011e1c7  lea     rcx, [r8+28h]
0x14011e1cb  cmp     rcx, rsi
  ... truncated ...
```
