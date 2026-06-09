# SrvNetProcessFsctlFsp

- ea: `0x140053eb0`
- end: `0x140054508`
- name: `SrvNetProcessFsctlFsp`
- size: `1624`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14001389c`
- `0x140013950`
- `0x14001acb4`
- `0x14001adbc`
- `0x140020448`
- `0x1400437d4`
- `0x1400439cc`
- `0x140047194`
- `0x140049090`
- `0x140049b8c`
- `0x140049e90`
- `0x140049fdc`
- `0x14004a114`
- `0x140053eb0`
- `0x140055490`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400540d6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400540d6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400540f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054154`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400540f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054154`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053f45`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053f74`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053fcf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400540c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005411a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053f45`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053f74`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053fcf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400540c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005411a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053f2c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053f5b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053fb6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400540ab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140054101`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053f2c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053f5b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053fb6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400540ab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140054101`
- `ntoskrnl!IofCompleteRequest` at `0x1400544ea`
- `ntoskrnl!IofCompleteRequest` at `0x1400544ea`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14005427d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14005427d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400544d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400544d2`
- `ntoskrnl!IoFreeWorkItem` at `0x140053ed1`
- `ntoskrnl!IoFreeWorkItem` at `0x140053ed1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400540e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054148`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400540e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054148`

## pseudocode

```c
void __fastcall SrvNetProcessFsctlFsp(PDEVICE_OBJECT DeviceObject, PIO_WORKITEM *Context)
{
  int v2; // ebx
  _DWORD *v4; // rsi
  const UNICODE_STRING *v5; // rdi
  unsigned __int64 v6; // rcx
  PWSTR Buffer; // rax
  char *v8; // rdx
  __int64 MaximumLength; // r8
  __int64 Length; // r9
  PIO_WORKITEM v11; // r11
  unsigned int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r11
  __int64 v15; // r11
  int v16; // eax
  int v17; // eax
  int v18; // eax
  PIO_WORKITEM v19; // rcx
  unsigned __int16 *v20; // rdx
  PVOID v21; // r14
  PVOID v22; // rax
  unsigned __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // r15d
  bool v26; // zf
  char *v27; // r8
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // r10
  char *v32; // rdi
  __int64 v33; // rax
  char *v34; // r8
  __int64 v35; // rbx
  __int64 v36; // r9
  unsigned __int16 v37; // ax
  PIO_WORKITEM v38; // rcx
  __int128 v39[5]; // [rsp+30h] [rbp-58h] BYREF

  v2 = 0;
  IoFreeWorkItem(Context[20]);
  v4 = Context[23];
  Context[20] = 0;
  if ( v4[6] == 1327131 )
  {
    v19 = Context[1];
    if ( !v19 )
      goto LABEL_105;
    v20 = (unsigned __int16 *)Context[3];
    if ( !v20 )
      goto LABEL_105;
    if ( (*((_BYTE *)v19 + 10) & 5) != 0 )
    {
      v21 = (PVOID)*((_QWORD *)v19 + 3);
    }
    else
    {
      v22 = MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000010u);
      v20 = (unsigned __int16 *)Context[3];
      v21 = v22;
    }
    if ( !v21 )
      goto LABEL_105;
    v23 = (unsigned int)v4[4];
    if ( (unsigned int)v23 < 0x60 )
      goto LABEL_105;
    v24 = *((_QWORD *)v20 + 1);
    v25 = v4[2];
    if ( v24 )
    {
      v26 = (unsigned __int16 *)((char *)v20 + v24) == 0;
      v27 = (char *)v20 + v24;
      *((_QWORD *)v20 + 1) = v27;
      if ( !v26 && (v27 <= (char *)v20 || v27 >= (char *)v20 + v23) )
        goto LABEL_64;
    }
    else
    {
      v27 = 0;
    }
    v30 = v20[1];
    v31 = *v20;
    if ( (unsigned __int16)v31 > (unsigned __int16)v30
      || v31 + (unsigned __int64)(unsigned int)(*((_DWORD *)v20 + 2) - (_DWORD)v20) > v23
      || (v32 = (char *)v20 + v23, &v27[v30] > (char *)v20 + v23) )
    {
LABEL_64:
      v2 = -1073741811;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_106;
      }
      v29 = 10;
      goto LABEL_68;
    }
    if ( (((unsigned __int16)v30 | (unsigned __int16)v31) & 1) != 0
      || (_WORD)v30 == 0xFFFF
      || !v27 && __PAIR32__(v30, v31) )
    {
      v2 = -1073741811;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_106;
      }
      v29 = 11;
    }
    else
    {
      v33 = *((_QWORD *)v20 + 3);
      if ( v33 )
      {
        v34 = (char *)v20 + v33;
        *((_QWORD *)v20 + 3) = (char *)v20 + v33;
        if ( (unsigned __int16 *)((char *)v20 + v33) && (v34 <= (char *)v20 || v34 >= v32) )
          goto LABEL_81;
      }
      else
      {
        v34 = 0;
      }
      v35 = v20[9];
      v36 = v20[8];
      if ( (unsigned __int16)v36 > (unsigned __int16)v35
        || v36 + (unsigned __int64)(unsigned int)(*((_DWORD *)v20 + 6) - (_DWORD)v20) > v23
        || &v34[v35] > v32 )
      {
LABEL_81:
        v2 = -1073741811;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_106;
        }
        v29 = 12;
        goto LABEL_68;
      }
      if ( (v36 & 1) == 0 )
      {
        v37 = v20[9];
        if ( (v37 & 1) == 0
          && (unsigned __int16)v36 <= v37
          && v37 != 0xFFFF
          && (*((_QWORD *)v20 + 3) || !(_WORD)v36 && !v37) )
        {
          v39[0] = *(_OWORD *)v20;
          v18 = SrvNetSendDatagram(v39, (unsigned __int64)(v20 + 8) & -(__int64)((_WORD)v36 != 0), v21, v25);
          goto LABEL_50;
        }
      }
      v2 = -1073741811;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_106;
      }
      v29 = 13;
    }
LABEL_68:
    WPP_SF_d(v28->AttachedDevice, v29, WPP_6a4d2c8a1a8134e9dfbfd0e9f83a7911_Traceguids, 1327131);
    goto LABEL_106;
  }
  if ( v4[6] != 1335451 )
  {
    if ( v4[6] != 1336327 )
    {
      switch ( v4[6] )
      {
        case 0x14640B:
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 120), 1u);
          SrvNetTdiDetachPnpCallbacks();
          break;
        case 0x14640F:
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 120), 1u);
          if ( !BYTE1(SrvNetDeviceExtension[8].SystemResourcesList.Flink) )
          {
            v2 = SrvNetRegisterPnpCallbacks();
            if ( v2 >= 0 )
              BYTE1(SrvNetDeviceExtension[8].SystemResourcesList.Flink) = 1;
          }
          break;
        case 0x146413:
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 120), 1u);
          SrvNetDeregisterPnpCallbacks();
          break;
        default:
          goto LABEL_106;
      }
      goto LABEL_31;
    }
    v5 = (const UNICODE_STRING *)Context[3];
    if ( v5 )
    {
      v6 = (unsigned int)v4[4];
      if ( (unsigned int)v6 >= 0x60 )
      {
        if ( SrvNetDeviceExtension[2].OwnerTable )
          goto LABEL_29;
        Buffer = v5->Buffer;
        if ( Buffer )
        {
          v8 = (char *)v5 + (_QWORD)Buffer;
          v5->Buffer = (USHORT *)((char *)&v5->Length + (_QWORD)Buffer);
          if ( (const UNICODE_STRING *)((char *)v5 + (_QWORD)Buffer) && (v8 <= (char *)v5 || v8 >= (char *)v5 + v6) )
            goto LABEL_19;
        }
        else
        {
          v8 = 0;
        }
        MaximumLength = v5->MaximumLength;
        Length = v5->Length;
        if ( (unsigned __int16)Length > (unsigned __int16)MaximumLength
          || Length + (unsigned __int64)(unsigned int)(LODWORD(v5->Buffer) - (_DWORD)v5) > v6
          || &v8[MaximumLength] > (char *)v5 + v6 )
        {
LABEL_19:
          v2 = -1073741819;
          goto LABEL_106;
        }
        if ( (((unsigned __int16)MaximumLength | (unsigned __int16)Length) & 1) == 0
          && (_WORD)MaximumLength != 0xFFFF
          && (v8 || !__PAIR32__(MaximumLength, Length)) )
        {
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite(SrvNetDeviceExtension, 1u);
          RtlCopyUnicodeString(&RDMADomainName, v5);
          ExReleaseResourceLite(SrvNetDeviceExtension);
          KeLeaveCriticalRegion();
LABEL_29:
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 120), 1u);
          if ( !SrvNetDeviceExtension[2].OwnerTable )
            v2 = SrvNetTdiAttachPnpCallbacks();
LABEL_31:
          ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 120));
          KeLeaveCriticalRegion();
          goto LABEL_106;
        }
      }
    }
    goto LABEL_105;
  }
  v11 = Context[3];
  if ( !v11 )
    goto LABEL_105;
  v12 = *((_DWORD *)v11 + 34);
  if ( v12 + 140 < v12 )
  {
    v2 = -1073741675;
    goto LABEL_106;
  }
  v13 = v4[4];
  if ( v13 < v12 + 140 )
  {
    v2 = -2147483643;
    goto LABEL_106;
  }
  if ( RtlStringCchLengthA((STRSAFE_PCNZCH)v11 + 8, 0x80u, 0) < 0 )
  {
    v2 = -1073741562;
    goto LABEL_106;
  }
  if ( !(unsigned __int8)SmbValidateQuicCertificateStoreName(v14 + 8) )
    goto LABEL_105;
  v16 = *(_DWORD *)(v15 + 4);
  switch ( v16 )
  {
    case 0:
      v17 = SrvNetQUICAddCertificates(v15, v13);
      goto LABEL_42;
    case 1:
      v18 = SrvNetQUICRemoveConfiguration(v15, v13);
LABEL_50:
      v2 = v18;
      goto LABEL_106;
    case 3:
      v18 = SrvNetQUICUpdateConfigurationFlags(v15, v13);
      goto LABEL_50;
    case 2:
      v18 = SrvNetQUICUpdateConfiguration(v15, v13);
      goto LABEL_50;
  }
  if ( v16 != 4 )
  {
LABEL_105:
    v2 = -1073741811;
    goto LABEL_106;
  }
  v17 = SrvNetQUICUpdateOrAddCertificates(v15, v13);
LABEL_42:
  v2 = v17;
  if ( v17 >= 0 )
    SrvNetDisableDeferSmbQuicInitialization();
LABEL_106:
  v38 = Context[3];
  if ( v38 )
  {
    ExFreePoolWithTag(v38, 0);
    Context[3] = 0;
  }
  *((_DWORD *)Context + 12) = v2;
  IofCompleteRequest((PIRP)Context, 2);
}

```

## disassembly

```asm
0x140053eb0  push    rbx
0x140053eb2  push    rbp
0x140053eb3  push    rsi
0x140053eb4  push    rdi
0x140053eb5  push    r12
0x140053eb7  push    r13
0x140053eb9  push    r14
0x140053ebb  push    r15
0x140053ebd  sub     rsp, 48h
0x140053ec1  mov     rcx, [rdx+0A0h]; IoWorkItem
0x140053ec8  xor     r12d, r12d
0x140053ecb  mov     ebx, r12d
0x140053ece  mov     rbp, rdx
0x140053ed1  call    cs:__imp_IoFreeWorkItem
0x140053ed8  nop     dword ptr [rax+rax+00h]
0x140053edd  mov     rsi, [rbp+0B8h]
0x140053ee4  mov     r13d, 14401Bh
0x140053eea  mov     [rbp+0A0h], r12
0x140053ef1  mov     ecx, [rsi+18h]
0x140053ef4  sub     ecx, r13d
0x140053ef7  jz      loc_140054241
0x140053efd  sub     ecx, 2080h
0x140053f03  jz      loc_140054165
0x140053f09  sub     ecx, 36Ch
0x140053f0f  jz      loc_140053FE5
0x140053f15  sub     ecx, 4
0x140053f18  jz      loc_140053FB6
0x140053f1e  sub     ecx, 4
0x140053f21  jz      short loc_140053F5B
0x140053f23  cmp     ecx, 4
0x140053f26  jnz     loc_1400544C7
0x140053f2c  call    cs:__imp_KeEnterCriticalRegion
0x140053f33  nop     dword ptr [rax+rax+00h]
0x140053f38  mov     rcx, cs:SrvNetDeviceExtension
0x140053f3f  mov     dl, 1; Wait
0x140053f41  add     rcx, 78h ; 'x'; Resource
0x140053f45  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140053f4c  nop     dword ptr [rax+rax+00h]
0x140053f51  call    SrvNetDeregisterPnpCallbacks
0x140053f56  jmp     loc_14005413D
0x140053f5b  call    cs:__imp_KeEnterCriticalRegion
0x140053f62  nop     dword ptr [rax+rax+00h]
0x140053f67  mov     rcx, cs:SrvNetDeviceExtension
0x140053f6e  mov     dl, 1; Wait
0x140053f70  add     rcx, 78h ; 'x'; Resource
0x140053f74  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140053f7b  nop     dword ptr [rax+rax+00h]
0x140053f80  mov     rax, cs:SrvNetDeviceExtension
0x140053f87  cmp     [rax+341h], r12b
0x140053f8e  jnz     loc_14005413D
0x140053f94  call    SrvNetRegisterPnpCallbacks
0x140053f99  mov     ebx, eax
0x140053f9b  test    eax, eax
0x140053f9d  js      loc_14005413D
0x140053fa3  mov     rcx, cs:SrvNetDeviceExtension
0x140053faa  mov     byte ptr [rcx+341h], 1
0x140053fb1  jmp     loc_14005413D
0x140053fb6  call    cs:__imp_KeEnterCriticalRegion
0x140053fbd  nop     dword ptr [rax+rax+00h]
0x140053fc2  mov     rcx, cs:SrvNetDeviceExtension
0x140053fc9  mov     dl, 1; Wait
0x140053fcb  add     rcx, 78h ; 'x'; Resource
0x140053fcf  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140053fd6  nop     dword ptr [rax+rax+00h]
0x140053fdb  call    SrvNetTdiDetachPnpCallbacks
0x140053fe0  jmp     loc_14005413D
0x140053fe5  mov     rdi, [rbp+18h]
0x140053fe9  test    rdi, rdi
0x140053fec  jz      loc_1400544C2
0x140053ff2  mov     ecx, [rsi+10h]
0x140053ff5  cmp     ecx, 60h ; '`'
0x140053ff8  jb      loc_1400544C2
0x140053ffe  mov     rax, cs:SrvNetDeviceExtension
0x140054005  cmp     [rax+0E0h], r12
0x14005400c  jnz     loc_140054101
0x140054012  mov     rax, [rdi+8]
0x140054016  test    rax, rax
0x140054019  jz      short loc_140054040
0x14005401b  lea     rdx, [rax+rdi]
0x14005401f  mov     [rdi+8], rdx
0x140054023  test    rdx, rdx
0x140054026  jz      short loc_140054043
0x140054028  cmp     rdx, rdi
0x14005402b  jbe     short loc_140054036
0x14005402d  lea     rax, [rdi+rcx]
0x140054031  cmp     rdx, rax
0x140054034  jb      short loc_140054043
0x140054036  mov     ebx, 0C0000005h
0x14005403b  jmp     loc_1400544C7
0x140054040  mov     rdx, r12
0x140054043  movzx   r8d, word ptr [rdi+2]
0x140054048  movzx   r9d, word ptr [rdi]
0x14005404c  cmp     r9w, r8w
0x140054050  ja      short loc_140054036
0x140054052  mov     r10, rcx
0x140054055  mov     ecx, [rdi+8]
0x140054058  sub     ecx, edi
0x14005405a  add     rcx, r9
0x14005405d  cmp     rcx, r10
0x140054060  ja      short loc_140054036
0x140054062  lea     rcx, [rdx+r8]
0x140054066  lea     rax, [r10+rdi]
0x14005406a  cmp     rcx, rax
0x14005406d  ja      short loc_140054036
0x14005406f  movzx   ecx, r9w
0x140054073  or      cx, r8w
0x140054077  bt      cx, r12w
0x14005407c  jb      loc_1400544C2
0x140054082  mov     r11d, 0FFFEh
0x140054088  cmp     r8w, r11w
0x14005408c  ja      loc_1400544C2
0x140054092  test    rdx, rdx
0x140054095  jnz     short loc_1400540AB
0x140054097  test    r9w, r9w
0x14005409b  jnz     loc_1400544C2
0x1400540a1  test    r8w, r8w
0x1400540a5  jnz     loc_1400544C2
0x1400540ab  call    cs:__imp_KeEnterCriticalRegion
0x1400540b2  nop     dword ptr [rax+rax+00h]
0x1400540b7  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x1400540be  mov     dl, 1; Wait
0x1400540c0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400540c7  nop     dword ptr [rax+rax+00h]
0x1400540cc  mov     rdx, rdi; SourceString
0x1400540cf  lea     rcx, RDMADomainName; DestinationString
0x1400540d6  call    cs:__imp_RtlCopyUnicodeString
0x1400540dd  nop     dword ptr [rax+rax+00h]
0x1400540e2  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x1400540e9  call    cs:__imp_ExReleaseResourceLite
0x1400540f0  nop     dword ptr [rax+rax+00h]
0x1400540f5  call    cs:__imp_KeLeaveCriticalRegion
0x1400540fc  nop     dword ptr [rax+rax+00h]
0x140054101  call    cs:__imp_KeEnterCriticalRegion
0x140054108  nop     dword ptr [rax+rax+00h]
0x14005410d  mov     rcx, cs:SrvNetDeviceExtension
0x140054114  mov     dl, 1; Wait
0x140054116  add     rcx, 78h ; 'x'; Resource
0x14005411a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140054121  nop     dword ptr [rax+rax+00h]
0x140054126  mov     rax, cs:SrvNetDeviceExtension
0x14005412d  cmp     [rax+0E0h], r12
0x140054134  jnz     short loc_14005413D
0x140054136  call    SrvNetTdiAttachPnpCallbacks
0x14005413b  mov     ebx, eax
0x14005413d  mov     rcx, cs:SrvNetDeviceExtension
0x140054144  add     rcx, 78h ; 'x'; Resource
0x140054148  call    cs:__imp_ExReleaseResourceLite
0x14005414f  nop     dword ptr [rax+rax+00h]
0x140054154  call    cs:__imp_KeLeaveCriticalRegion
0x14005415b  nop     dword ptr [rax+rax+00h]
0x140054160  jmp     loc_1400544C7
0x140054165  mov     r11, [rbp+18h]
0x140054169  test    r11, r11
0x14005416c  jz      loc_1400544C2
0x140054172  mov     eax, [r11+88h]
0x140054179  lea     ecx, [rax+8Ch]
0x14005417f  cmp     ecx, eax
0x140054181  jnb     short loc_14005418D
0x140054183  mov     ebx, 0C0000095h
0x140054188  jmp     loc_1400544C7
0x14005418d  mov     ebx, [rsi+10h]
0x140054190  cmp     ebx, ecx
0x140054192  jnb     short loc_14005419E
0x140054194  mov     ebx, 80000005h
0x140054199  jmp     loc_1400544C7
0x14005419e  xor     r8d, r8d; pcchLength
0x1400541a1  lea     rcx, [r11+8]; psz
0x1400541a5  mov     edx, 80h; cchMax
0x1400541aa  call    RtlStringCchLengthA
0x1400541af  test    eax, eax
0x1400541b1  jns     short loc_1400541BD
0x1400541b3  mov     ebx, 0C0000106h
0x1400541b8  jmp     loc_1400544C7
0x1400541bd  lea     rcx, [r11+8]
0x1400541c1  call    SmbValidateQuicCertificateStoreName
0x1400541c6  test    al, al
0x1400541c8  jz      loc_1400544C2
0x1400541ce  mov     eax, [r11+4]
0x1400541d2  test    eax, eax
0x1400541d4  jnz     short loc_1400541F4
0x1400541d6  mov     edx, ebx
0x1400541d8  mov     rcx, r11
0x1400541db  call    SrvNetQUICAddCertificates
0x1400541e0  mov     ebx, eax
0x1400541e2  test    eax, eax
0x1400541e4  js      loc_1400544C7
0x1400541ea  call    SrvNetDisableDeferSmbQuicInitialization
0x1400541ef  jmp     loc_1400544C7
0x1400541f4  cmp     eax, 1
0x1400541f7  jnz     short loc_140054205
0x1400541f9  mov     edx, ebx
0x1400541fb  mov     rcx, r11
0x1400541fe  call    SrvNetQUICRemoveConfiguration
0x140054203  jmp     short loc_140054225
0x140054205  cmp     eax, 3
0x140054208  jnz     short loc_140054216
0x14005420a  mov     edx, ebx
0x14005420c  mov     rcx, r11
0x14005420f  call    SrvNetQUICUpdateConfigurationFlags
0x140054214  jmp     short loc_140054225
0x140054216  cmp     eax, 2
0x140054219  jnz     short loc_14005422C
0x14005421b  mov     edx, ebx
0x14005421d  mov     rcx, r11
0x140054220  call    SrvNetQUICUpdateConfiguration
0x140054225  mov     ebx, eax
0x140054227  jmp     loc_1400544C7
0x14005422c  cmp     eax, 4
0x14005422f  jnz     loc_1400544C2
0x140054235  mov     edx, ebx
0x140054237  mov     rcx, r11
0x14005423a  call    SrvNetQUICUpdateOrAddCertificates
0x14005423f  jmp     short loc_1400541E0
0x140054241  mov     rcx, [rbp+8]; MemoryDescriptorList
0x140054245  test    rcx, rcx
0x140054248  jz      loc_1400544C2
0x14005424e  mov     rdx, [rbp+18h]
0x140054252  test    rdx, rdx
0x140054255  jz      loc_1400544C2
0x14005425b  test    byte ptr [rcx+0Ah], 5
0x14005425f  jz      short loc_140054267
0x140054261  mov     r14, [rcx+18h]
0x140054265  jmp     short loc_140054290
0x140054267  xor     r9d, r9d; RequestedAddress
0x14005426a  mov     [rsp+88h+Priority], 40000010h; Priority
0x140054272  xor     edx, edx; AccessMode
0x140054274  mov     [rsp+88h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140054279  lea     r8d, [r9+1]; CacheType
0x14005427d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140054284  nop     dword ptr [rax+rax+00h]
0x140054289  mov     rdx, [rbp+18h]
0x14005428d  mov     r14, rax
0x140054290  test    r14, r14
0x140054293  jz      loc_1400544C2
0x140054299  mov     ecx, [rsi+10h]
0x14005429c  cmp     ecx, 60h ; '`'
0x14005429f  jb      loc_1400544C2
0x1400542a5  mov     r8, [rdx+8]
0x1400542a9  mov     r15d, [rsi+8]
0x1400542ad  test    r8, r8
0x1400542b0  jz      short loc_140054319
0x1400542b2  add     r8, rdx
0x1400542b5  mov     [rdx+8], r8
0x1400542b9  jz      short loc_14005431C
0x1400542bb  cmp     r8, rdx
0x1400542be  jbe     short loc_1400542C9
0x1400542c0  lea     rax, [rdx+rcx]
0x1400542c4  cmp     r8, rax
0x1400542c7  jb      short loc_14005431C
0x1400542c9  mov     ebx, 0C000000Dh
0x1400542ce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400542d5  lea     rax, WPP_GLOBAL_Control
0x1400542dc  cmp     rcx, rax
0x1400542df  jz      loc_1400544C7
0x1400542e5  test    dword ptr [rcx+2Ch], 4000h
0x1400542ec  jz      loc_1400544C7
0x1400542f2  cmp     byte ptr [rcx+29h], 2
0x1400542f6  jb      loc_1400544C7
0x1400542fc  mov     edx, 0Ah
0x140054301  mov     rcx, [rcx+18h]
0x140054305  lea     r8, WPP_6a4d2c8a1a8134e9dfbfd0e9f83a7911_Traceguids
0x14005430c  mov     r9d, r13d
0x14005430f  call    WPP_SF_d
0x140054314  jmp     loc_1400544C7
0x140054319  mov     r8, r12
0x14005431c  movzx   r9d, word ptr [rdx+2]
0x140054321  movzx   r10d, word ptr [rdx]
0x140054325  cmp     r10w, r9w
0x140054329  ja      short loc_1400542C9
0x14005432b  mov     rsi, rcx
0x14005432e  mov     ecx, [rdx+8]
0x140054331  sub     ecx, edx
0x140054333  add     rcx, r10
0x140054336  cmp     rcx, rsi
0x140054339  ja      short loc_1400542C9
0x14005433b  lea     rdi, [rsi+rdx]
0x14005433f  lea     rax, [r8+r9]
0x140054343  cmp     rax, rdi
0x140054346  ja      short loc_1400542C9
0x140054348  movzx   ecx, r10w
0x14005434c  or      cx, r9w
0x140054350  bt      cx, r12w
0x140054355  jb      loc_140054491
0x14005435b  mov     r11d, 0FFFEh
0x140054361  cmp     r9w, r11w
0x140054365  ja      loc_140054491
0x14005436b  test    r8, r8
0x14005436e  jnz     short loc_140054384
0x140054370  test    r10w, r10w
0x140054374  jnz     loc_140054491
0x14005437a  test    r9w, r9w
0x14005437e  jnz     loc_140054491
0x140054384  mov     rax, [rdx+18h]
0x140054388  test    rax, rax
0x14005438b  jz      short loc_1400543E1
0x14005438d  lea     r8, [rdx+rax]
0x140054391  mov     [rdx+18h], r8
0x140054395  test    r8, r8
0x140054398  jz      short loc_1400543E4
0x14005439a  cmp     r8, rdx
  ... truncated ...
```
