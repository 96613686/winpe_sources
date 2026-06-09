# VMX_PACK::PreCommitDevices(ulong *,_VM_DEVICE_CHANGE * *)

- ea: `0x140053b8c`
- end: `0x14005431f`
- name: `?PreCommitDevices@VMX_PACK@@AEAAJPEAKPEAPEAU_VM_DEVICE_CHANGE@@@Z`
- size: `1939`
- prototype: `__int64 __fastcall(VMX_PACK *__hidden this, unsigned int *, struct _VM_DEVICE_CHANGE **)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14002a3f4`
- `0x14004e3ac`

## callees

- `0x1400099d8`
- `0x140009fcc`
- `0x14001b960`
- `0x14001b9a0`
- `0x14001ba60`
- `0x14001be80`
- `0x14003769c`
- `0x140046dec`
- `0x14004a5dc`
- `0x14004d1dc`
- `0x140053b8c`
- `0x14005d644`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140053c3a`
- `ntoskrnl!ExAllocatePool2` at `0x140053c3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400540c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054118`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054167`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400541bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005421d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005425d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400542b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400540c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054118`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054167`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400541bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005421d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005425d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400542b3`

## pseudocode

```c
__int64 __fastcall VMX_PACK::PreCommitDevices(VMX_PACK *this, unsigned int *a2, struct _VM_DEVICE_CHANGE **a3)
{
  unsigned int v6; // ecx
  _QWORD *v7; // r8
  _QWORD *v8; // rdx
  bool v9; // zf
  unsigned int v10; // eax
  VMX_GLOBAL_DATA *v11; // r12
  struct _VM_DEVICE_CHANGE *Pool2; // rbx
  unsigned int v14; // edx
  __int64 *i; // r15
  __int16 v16; // cx
  __int64 v17; // r13
  __int64 v18; // rdi
  __int64 v19; // rcx
  _QWORD *v20; // r10
  __int64 v21; // rax
  __int64 v22; // rax
  _QWORD *v23; // r12
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  VMX_PACK *v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  struct VMX_PHYSICAL_DISK *PhysicalDiskById; // rax
  struct _DEVICE_OBJECT *v33; // rcx
  NTSTATUS v34; // r12d
  int v35; // r12d
  struct VMX_PHYSICAL_DISK *v36; // rdx
  __int64 v37; // rcx
  int GptAttributes; // edi
  VMX_NOTIFICATION_QUEUE *v39; // rcx
  __int64 v40; // rdx
  __int16 v41; // r9
  struct VMX_VOLUME_DEVICE *v42; // r12
  int v43; // eax
  struct VMX_VOLUME_DEVICE *v44; // rdx
  VMX_NOTIFICATION_QUEUE *v45; // rcx
  __int64 v46; // rdx
  VMX_NOTIFICATION_QUEUE *v47; // rcx
  __int64 v48; // rdx
  unsigned int v49; // [rsp+40h] [rbp-C0h]
  VMX_GLOBAL_DATA *v50; // [rsp+48h] [rbp-B8h]
  struct VMX_VOLUME_DEVICE *v51; // [rsp+50h] [rbp-B0h] BYREF
  struct VMX_PHYSICAL_DISK *v52; // [rsp+58h] [rbp-A8h]
  unsigned int *v53; // [rsp+60h] [rbp-A0h]
  struct _VM_DEVICE_CHANGE **v54; // [rsp+68h] [rbp-98h]
  _OWORD v55[9]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+100h] [rbp+0h] BYREF
  int v57; // [rsp+108h] [rbp+8h]

  v54 = a3;
  v53 = a2;
  v56 = 0;
  v57 = 0;
  v51 = 0;
  memset(v55, 0, sizeof(v55));
  *a2 = 0;
  v6 = 0;
  *a3 = 0;
  v7 = (_QWORD *)(*((_QWORD *)this + 2) + 16LL);
  v8 = (_QWORD *)*v7;
  if ( (_QWORD *)*v7 == v7 )
    return 0;
  do
  {
    v9 = (v8[8] & 0x10) == 0;
    v10 = v6 + 1;
    v8 = (_QWORD *)*v8;
    if ( v9 )
      v10 = v6;
    v6 = v10;
  }
  while ( v8 != v7 );
  if ( !v10 )
    return 0;
  v11 = Global;
  v50 = Global;
  Pool2 = (struct _VM_DEVICE_CHANGE *)ExAllocatePool2(256, 112LL * v10, 1665428822);
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 235, WPP_b525482092043ba595507d12d78e6f73_Traceguids, 3221225626LL);
    }
    return 3221225626LL;
  }
  v14 = 0;
  v49 = 0;
  for ( i = *(__int64 **)(*((_QWORD *)this + 2) + 16LL); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)(*((_QWORD *)this + 2) + 16LL) )
    {
      *v53 = v14;
      *v54 = Pool2;
      return 0;
    }
    v16 = *((_WORD *)i + 32);
    if ( (v16 & 0x10) == 0 )
      continue;
    v17 = i[6];
    v18 = 112LL * v14;
    if ( (v16 & 0x40) != 0 )
      break;
    v24 = i[5];
    if ( v24 )
    {
      *(_QWORD *)((char *)Pool2 + v18 + 8) = *(_QWORD *)(v24 + 248);
      v25 = *(_QWORD **)(v24 + 248);
      if ( v25 )
      {
        v26 = 0;
LABEL_24:
        (*(void (__fastcall **)(_QWORD, VMX_PACK *))(*(_QWORD *)*v25 + 216LL))(*v25, v26);
      }
    }
    else
    {
      v27 = i[7];
      if ( v27 )
      {
        v28 = *(_QWORD *)(v27 + 8LL * (*(_WORD *)(v27 + 64) & 1) + 40);
        *(_QWORD *)((char *)Pool2 + v18 + 8) = *(_QWORD *)(v28 + 248);
        v25 = *(_QWORD **)(v28 + 248);
        if ( v25 )
        {
          v26 = this;
          goto LABEL_24;
        }
      }
    }
    v23 = (_QWORD *)((char *)Pool2 + v18 + 8);
    if ( *v23 )
    {
      v29 = (*((__int64 (__fastcall **)(_QWORD))v50 + 11))(*((_QWORD *)v50 + 1));
      *(_QWORD *)((char *)Pool2 + v18) = v29;
      if ( !v29 )
      {
        ExFreePoolWithTag(Pool2, 0);
        VMX_PACK::AbortDevices(this);
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 237, WPP_b525482092043ba595507d12d78e6f73_Traceguids);
        }
        return 3221225473LL;
      }
    }
LABEL_27:
    v14 = ++v49;
    if ( *((char *)i + 64) < 0 )
    {
      v30 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v17 + 264) + 8LL * (*(_WORD *)(*(_QWORD *)(v17 + 264) + 64LL) & 1) + 40)
                      + 152LL);
      v31 = *(_QWORD *)(*(_QWORD *)(v30 + 8LL * (*(_WORD *)(v30 + 64) & 1) + 40) + 152LL);
      PhysicalDiskById = VmxpFindPhysicalDiskById((struct _GUID *)(*(_QWORD *)(v31
                                                                             + 8LL * (*(_WORD *)(v31 + 64) & 1)
                                                                             + 40)
                                                                 + 72LL));
      v33 = *(struct _DEVICE_OBJECT **)(v17 + 256);
      v52 = PhysicalDiskById;
      v34 = VmxpSendDeviceControl(v33, 0x2D1080u, 0, 0, &v56, 0xCu, 0);
      if ( v34 < 0 )
      {
        ExFreePoolWithTag(Pool2, 0);
        VMX_PACK::AbortDevices(this);
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v48 = 238;
          goto LABEL_80;
        }
        return (unsigned int)v34;
      }
      v34 = VmxpSendDeviceControl(*(PDEVICE_OBJECT *)(v17 + 256), 0x70048u, 0, 0, v55, 0x90u, 0);
      if ( v34 < 0 )
      {
        ExFreePoolWithTag(Pool2, 0);
        VMX_PACK::AbortDevices(this);
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v48 = 239;
          goto LABEL_80;
        }
        return (unsigned int)v34;
      }
      v35 = v55[0];
      if ( !LODWORD(v55[0]) && LOBYTE(v55[2]) == 66
        || LODWORD(v55[0]) == 1 && !memcmp(&v55[2], &PARTITION_LDM_DATA_GUID, 0x10u) )
      {
        ExFreePoolWithTag(Pool2, 0);
        VMX_PACK::AbortDevices(this);
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v46 = 240;
LABEL_70:
          WPP_SF_d(*((_QWORD *)v45 + 3), v46, WPP_b525482092043ba595507d12d78e6f73_Traceguids, 3224895556LL);
        }
        return 3224895556LL;
      }
      v36 = v52;
      *(_DWORD *)((char *)Pool2 + v18 + 20) = *(_DWORD *)(*((_QWORD *)v52 + 2) + 48LL);
      *((_BYTE *)Pool2 + v18 + 16) = 0;
      *(_QWORD *)((char *)Pool2 + v18 + 24) = *(_QWORD *)(v17 + 256);
      *(_QWORD *)((char *)Pool2 + v18 + 32) = *(_QWORD *)(*((_QWORD *)v36 + 2) + 16LL);
      v37 = *(_QWORD *)(*((_QWORD *)v36 + 2) + 24LL);
      *(_DWORD *)((char *)Pool2 + v18 + 48) = HIDWORD(v56);
      *(_DWORD *)((char *)Pool2 + v18 + 52) = v57;
      *(_QWORD *)((char *)Pool2 + v18 + 56) = *((_QWORD *)&v55[0] + 1);
      *(_QWORD *)((char *)Pool2 + v18 + 64) = *(_QWORD *)&v55[1];
      *(_QWORD *)((char *)Pool2 + v18 + 40) = v37;
      if ( v35 == 1 )
      {
        *(_OWORD *)((char *)Pool2 + v18 + 72) = v55[3];
        *((_BYTE *)Pool2 + v18 + 96) = 1;
      }
      else if ( !v35 )
      {
        GptAttributes = VmxpDiskGetGptAttributes(
                          *(struct _DEVICE_OBJECT **)(v17 + 256),
                          (unsigned __int64 *)((char *)Pool2 + v18 + 88));
        if ( GptAttributes < 0 )
        {
          ExFreePoolWithTag(Pool2, 0);
          VMX_PACK::AbortDevices(this);
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v40 = 241;
            goto LABEL_45;
          }
          return (unsigned int)GptAttributes;
        }
      }
      goto LABEL_36;
    }
    *((_BYTE *)Pool2 + v18 + 16) = 1;
    v41 = *((_WORD *)i + 32);
    if ( (v41 & 8) == 0 )
    {
      v34 = VMX_PACK::BuildVolumeDevice(
              this,
              (struct VMX_VOLUME_INFO *)v17,
              *v23 == 0,
              (v41 & 0x20) != 0,
              *((_BYTE *)this + 57),
              &v51);
      if ( v34 < 0 )
      {
        ExFreePoolWithTag(Pool2, 0);
        VMX_PACK::AbortDevices(this);
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v48 = 242;
LABEL_80:
          WPP_SF_d(*((_QWORD *)v47 + 3), v48, WPP_b525482092043ba595507d12d78e6f73_Traceguids, (unsigned int)v34);
        }
        return (unsigned int)v34;
      }
      v42 = v51;
      *(_QWORD *)(v17 + 248) = v51;
      *(_QWORD *)((char *)Pool2 + v18 + 104) = v42;
      if ( v42 )
      {
        v43 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v42 + 144LL))(*(_QWORD *)v42);
        v9 = *(_QWORD *)((char *)Pool2 + v18) == 0;
        *(_DWORD *)((char *)Pool2 + v18 + 20) = v43;
        if ( v9 )
        {
          v44 = v42;
          v11 = v50;
          GptAttributes = (*((__int64 (__fastcall **)(_QWORD, struct VMX_VOLUME_DEVICE *))v50 + 13))(
                            *((_QWORD *)v50 + 1),
                            v44);
          if ( GptAttributes < 0 )
          {
            ExFreePoolWithTag(Pool2, 0);
            VMX_PACK::AbortDevices(this);
            v39 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v40 = 243;
LABEL_45:
              WPP_SF_d(
                *((_QWORD *)v39 + 3),
                v40,
                WPP_b525482092043ba595507d12d78e6f73_Traceguids,
                (unsigned int)GptAttributes);
            }
            return (unsigned int)GptAttributes;
          }
          goto LABEL_37;
        }
      }
LABEL_36:
      v11 = v50;
LABEL_37:
      v14 = v49;
      continue;
    }
    v11 = v50;
    *((_BYTE *)Pool2 + v18 + 17) = 1;
    *(_QWORD *)(v17 + 248) = 0;
  }
  v19 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v17 + 264) + 8LL * (*(_WORD *)(*(_QWORD *)(v17 + 264) + 64LL) & 1) + 40)
                  + 152LL);
  v20 = *(_QWORD **)(v19 + 8LL * (*(_WORD *)(v19 + 64) & 1) + 40);
  v21 = *(_QWORD *)(*(_QWORD *)(v20[19] + 8LL * (*(_WORD *)(v20[19] + 64LL) & 1) + 40) + 128LL);
  v22 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v11 + 10))(
          *((_QWORD *)v11 + 1),
          *(unsigned int *)(*(_QWORD *)(v21 + 16) + 32LL),
          (v20[10] << 9) + *(_QWORD *)(*(_QWORD *)(v21 + 88) + 136LL) * *(unsigned int *)(*(_QWORD *)(v21 + 16) + 36LL),
          v20[12] << 9,
          0);
  *(_QWORD *)((char *)Pool2 + v18) = v22;
  if ( v22 )
  {
    v23 = (_QWORD *)((char *)Pool2 + v18 + 8);
    goto LABEL_27;
  }
  ExFreePoolWithTag(Pool2, 0);
  VMX_PACK::AbortDevices(this);
  v45 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v46 = 236;
    goto LABEL_70;
  }
  return 3224895556LL;
}

```

## disassembly

```asm
0x140053b8c  push    rbp
0x140053b8e  push    rbx
0x140053b8f  push    rdi
0x140053b90  push    r12
0x140053b92  push    r13
0x140053b94  push    r14
0x140053b96  push    r15
0x140053b98  lea     rbp, [rsp-20h]
0x140053b9d  sub     rsp, 120h
0x140053ba4  mov     rax, cs:__security_cookie
0x140053bab  xor     rax, rsp
0x140053bae  mov     [rbp+50h+var_40], rax
0x140053bb2  xor     eax, eax
0x140053bb4  mov     [rsp+150h+var_E8], r8
0x140053bb9  mov     r13, r8
0x140053bbc  mov     [rsp+150h+var_F0], rdx
0x140053bc1  mov     rdi, rdx
0x140053bc4  mov     [rbp+50h+var_50], rax
0x140053bc8  mov     r14, rcx
0x140053bcb  mov     [rbp+50h+var_48], eax
0x140053bce  xor     ebx, ebx
0x140053bd0  lea     rcx, [rsp+150h+var_E0]; void *
0x140053bd5  xor     edx, edx; Val
0x140053bd7  mov     [rsp+150h+var_100], rbx
0x140053bdc  mov     r8d, 90h; Size
0x140053be2  call    memset
0x140053be7  mov     [rdi], ebx
0x140053be9  mov     ecx, ebx
0x140053beb  mov     [r13+0], rbx
0x140053bef  mov     r8, [r14+10h]
0x140053bf3  add     r8, 10h
0x140053bf7  mov     rdx, [r8]
0x140053bfa  cmp     rdx, r8
0x140053bfd  jz      loc_1400542FD
0x140053c03  test    byte ptr [rdx+40h], 10h
0x140053c07  lea     eax, [rcx+1]
0x140053c0a  mov     rdx, [rdx]
0x140053c0d  cmovz   eax, ecx
0x140053c10  mov     ecx, eax
0x140053c12  cmp     rdx, r8
0x140053c15  jnz     short loc_140053C03
0x140053c17  test    eax, eax
0x140053c19  jz      loc_1400542FD
0x140053c1f  mov     r12, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140053c26  mov     r8d, 63446D56h
0x140053c2c  imul    rdx, rcx, 70h ; 'p'
0x140053c30  mov     ecx, 100h
0x140053c35  mov     [rsp+150h+var_108], r12
0x140053c3a  call    cs:__imp_ExAllocatePool2
0x140053c41  nop     dword ptr [rax+rax+00h]
0x140053c46  mov     rbx, rax
0x140053c49  test    rax, rax
0x140053c4c  jnz     short loc_140053C92
0x140053c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140053c55  lea     rax, WPP_GLOBAL_Control
0x140053c5c  mov     ebx, 0C000009Ah
0x140053c61  cmp     rcx, rax
0x140053c64  jz      short loc_140053C8B
0x140053c66  mov     eax, [rcx+2Ch]
0x140053c69  test    al, 8
0x140053c6b  jz      short loc_140053C8B
0x140053c6d  cmp     byte ptr [rcx+29h], 2
0x140053c71  jb      short loc_140053C8B
0x140053c73  mov     rcx, [rcx+18h]
0x140053c77  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140053c7e  mov     edx, 0EBh
0x140053c83  mov     r9d, ebx
0x140053c86  call    WPP_SF_d
0x140053c8b  mov     eax, ebx
0x140053c8d  jmp     loc_1400542FF
0x140053c92  mov     rax, [r14+10h]
0x140053c96  xor     edx, edx
0x140053c98  mov     [rsp+150h+var_110], edx
0x140053c9c  mov     r15, [rax+10h]
0x140053ca0  mov     rax, [r14+10h]
0x140053ca4  add     rax, 10h
0x140053ca8  cmp     r15, rax
0x140053cab  jz      loc_1400542EE
0x140053cb1  movzx   ecx, word ptr [r15+40h]
0x140053cb6  test    cl, 10h
0x140053cb9  jz      loc_140053F82
0x140053cbf  mov     r13, [r15+30h]
0x140053cc3  mov     eax, edx
0x140053cc5  imul    rdi, rax, 70h ; 'p'
0x140053cc9  test    cl, 40h
0x140053ccc  jz      loc_140053D6D
0x140053cd2  mov     rcx, [r13+108h]
0x140053cd9  mov     [rsp+150h+var_130], 0
0x140053ce2  movzx   eax, word ptr [rcx+40h]
0x140053ce6  and     eax, 1
0x140053ce9  mov     rax, [rcx+rax*8+28h]
0x140053cee  mov     rcx, [rax+98h]
0x140053cf5  movzx   eax, word ptr [rcx+40h]
0x140053cf9  and     eax, 1
0x140053cfc  mov     r10, [rcx+rax*8+28h]
0x140053d01  mov     rcx, [r10+98h]
0x140053d08  mov     r9, [r10+60h]
0x140053d0c  shl     r9, 9
0x140053d10  movzx   eax, word ptr [rcx+40h]
0x140053d14  and     eax, 1
0x140053d17  mov     rax, [rcx+rax*8+28h]
0x140053d1c  mov     rcx, [r12+8]
0x140053d21  mov     rax, [rax+80h]
0x140053d28  mov     rdx, [rax+10h]
0x140053d2c  mov     rax, [rax+58h]
0x140053d30  mov     r8d, [rdx+24h]
0x140053d34  imul    r8, [rax+88h]
0x140053d3c  mov     rax, [r10+50h]
0x140053d40  mov     edx, [rdx+20h]
0x140053d43  shl     rax, 9
0x140053d47  add     r8, rax
0x140053d4a  mov     rax, [r12+50h]
0x140053d4f  call    _guard_dispatch_icall
0x140053d54  mov     [rdi+rbx], rax
0x140053d58  test    rax, rax
0x140053d5b  jz      loc_140054113
0x140053d61  lea     r12, [rbx+8]
0x140053d65  add     r12, rdi
0x140053d68  jmp     loc_140053E03
0x140053d6d  mov     rcx, [r15+28h]
0x140053d71  test    rcx, rcx
0x140053d74  jz      short loc_140053D92
0x140053d76  mov     rax, [rcx+0F8h]
0x140053d7d  mov     [rdi+rbx+8], rax
0x140053d82  mov     rcx, [rcx+0F8h]
0x140053d89  test    rcx, rcx
0x140053d8c  jz      short loc_140053DD4
0x140053d8e  xor     edx, edx
0x140053d90  jmp     short loc_140053DC2
0x140053d92  mov     rcx, [r15+38h]
0x140053d96  test    rcx, rcx
0x140053d99  jz      short loc_140053DD4
0x140053d9b  movzx   eax, word ptr [rcx+40h]
0x140053d9f  and     eax, 1
0x140053da2  mov     rcx, [rcx+rax*8+28h]
0x140053da7  mov     rax, [rcx+0F8h]
0x140053dae  mov     [rdi+rbx+8], rax
0x140053db3  mov     rcx, [rcx+0F8h]
0x140053dba  test    rcx, rcx
0x140053dbd  jz      short loc_140053DD4
0x140053dbf  mov     rdx, r14
0x140053dc2  mov     rcx, [rcx]
0x140053dc5  mov     rax, [rcx]
0x140053dc8  mov     rax, [rax+0D8h]
0x140053dcf  call    _guard_dispatch_icall
0x140053dd4  lea     r12, [rbx+8]
0x140053dd8  add     r12, rdi
0x140053ddb  mov     rdx, [r12]
0x140053ddf  test    rdx, rdx
0x140053de2  jz      short loc_140053E03
0x140053de4  mov     rcx, [rsp+150h+var_108]
0x140053de9  mov     rax, [rcx+58h]
0x140053ded  mov     rcx, [rcx+8]
0x140053df1  call    _guard_dispatch_icall
0x140053df6  mov     [rdi+rbx], rax
0x140053dfa  test    rax, rax
0x140053dfd  jz      loc_140054162
0x140053e03  mov     edx, [rsp+150h+var_110]
0x140053e07  mov     al, [r15+40h]
0x140053e0b  inc     edx
0x140053e0d  mov     [rsp+150h+var_110], edx
0x140053e11  test    al, al
0x140053e13  jns     loc_140054000
0x140053e19  mov     rcx, [r13+108h]
0x140053e20  movzx   eax, word ptr [rcx+40h]
0x140053e24  and     eax, 1
0x140053e27  mov     rax, [rcx+rax*8+28h]
0x140053e2c  mov     rcx, [rax+98h]
0x140053e33  movzx   eax, word ptr [rcx+40h]
0x140053e37  and     eax, 1
0x140053e3a  mov     rax, [rcx+rax*8+28h]
0x140053e3f  mov     rcx, [rax+98h]
0x140053e46  movzx   eax, word ptr [rcx+40h]
0x140053e4a  and     eax, 1
0x140053e4d  mov     rcx, [rcx+rax*8+28h]
0x140053e52  add     rcx, 48h ; 'H'; struct _GUID *
0x140053e56  call    ?VmxpFindPhysicalDiskById@@YAPEAVVMX_PHYSICAL_DISK@@PEAU_GUID@@@Z; VmxpFindPhysicalDiskById(_GUID *)
0x140053e5b  mov     rcx, [r13+100h]; DeviceObject
0x140053e62  xor     r9d, r9d; InputBufferLength
0x140053e65  mov     [rsp+150h+var_F8], rax
0x140053e6a  xor     r8d, r8d; InputBuffer
0x140053e6d  lea     rax, [rbp+50h+var_50]
0x140053e71  mov     [rsp+150h+var_120], 0; BOOLEAN
0x140053e76  mov     [rsp+150h+var_128], 0Ch; ULONG
0x140053e7e  mov     edx, 2D1080h; IoControlCode
0x140053e83  mov     [rsp+150h+var_130], rax; PVOID
0x140053e88  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140053e8d  mov     r12d, eax
0x140053e90  test    eax, eax
0x140053e92  js      loc_140054258
0x140053e98  mov     rcx, [r13+100h]; DeviceObject
0x140053e9f  lea     rax, [rsp+150h+var_E0]
0x140053ea4  mov     [rsp+150h+var_120], 0; BOOLEAN
0x140053ea9  xor     r9d, r9d; InputBufferLength
0x140053eac  mov     [rsp+150h+var_128], 90h; ULONG
0x140053eb4  xor     r8d, r8d; InputBuffer
0x140053eb7  mov     edx, 70048h; IoControlCode
0x140053ebc  mov     [rsp+150h+var_130], rax; PVOID
0x140053ec1  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140053ec6  mov     r12d, eax
0x140053ec9  test    eax, eax
0x140053ecb  js      loc_140054218
0x140053ed1  mov     r12d, [rsp+150h+var_E0]
0x140053ed6  test    r12d, r12d
0x140053ed9  jnz     short loc_140053EE5
0x140053edb  cmp     [rbp+50h+Buf1], 42h ; 'B'
0x140053edf  jz      loc_1400541BA
0x140053ee5  cmp     r12d, 1
0x140053ee9  jnz     short loc_140053F08
0x140053eeb  lea     r8d, [r12+0Fh]; Size
0x140053ef0  lea     rdx, PARTITION_LDM_DATA_GUID; Buf2
0x140053ef7  lea     rcx, [rbp+50h+Buf1]; Buf1
0x140053efb  call    memcmp
0x140053f00  test    eax, eax
0x140053f02  jz      loc_1400541BA
0x140053f08  mov     rdx, [rsp+150h+var_F8]
0x140053f0d  mov     rax, [rdx+10h]
0x140053f11  mov     ecx, [rax+30h]
0x140053f14  mov     [rdi+rbx+14h], ecx
0x140053f18  mov     byte ptr [rdi+rbx+10h], 0
0x140053f1d  mov     rax, [r13+100h]
0x140053f24  mov     [rdi+rbx+18h], rax
0x140053f29  mov     rax, [rdx+10h]
0x140053f2d  mov     rcx, [rax+10h]
0x140053f31  mov     [rdi+rbx+20h], rcx
0x140053f36  mov     rax, [rdx+10h]
0x140053f3a  mov     rcx, [rax+18h]
0x140053f3e  mov     eax, dword ptr [rbp+50h+var_50+4]
0x140053f41  mov     [rdi+rbx+30h], eax
0x140053f45  mov     eax, [rbp+50h+var_48]
0x140053f48  mov     [rdi+rbx+34h], eax
0x140053f4c  mov     rax, [rsp+150h+var_D8]
0x140053f51  mov     [rdi+rbx+38h], rax
0x140053f56  mov     rax, [rbp+50h+var_D0]
0x140053f5a  mov     [rdi+rbx+40h], rax
0x140053f5f  mov     [rdi+rbx+28h], rcx
0x140053f64  cmp     r12d, 1
0x140053f68  jnz     short loc_140053F8A
0x140053f6a  movaps  xmm0, [rbp+50h+var_B0]
0x140053f6e  movdqu  xmmword ptr [rdi+rbx+48h], xmm0
0x140053f74  mov     [rdi+rbx+60h], r12b
0x140053f79  mov     r12, [rsp+150h+var_108]
0x140053f7e  mov     edx, [rsp+150h+var_110]
0x140053f82  mov     r15, [r15]
0x140053f85  jmp     loc_140053CA0
0x140053f8a  test    r12d, r12d
0x140053f8d  jnz     short loc_140053F79
0x140053f8f  mov     rcx, [r13+100h]; struct _DEVICE_OBJECT *
0x140053f96  lea     rdx, [rbx+58h]
0x140053f9a  add     rdx, rdi; unsigned __int64 *
0x140053f9d  call    ?VmxpDiskGetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@PEA_K@Z; VmxpDiskGetGptAttributes(_DEVICE_OBJECT *,unsigned __int64 *)
0x140053fa2  mov     edi, eax
0x140053fa4  test    eax, eax
0x140053fa6  jns     short loc_140053F79
0x140053fa8  xor     edx, edx; Tag
0x140053faa  mov     rcx, rbx; P
0x140053fad  call    cs:__imp_ExFreePoolWithTag
0x140053fb4  nop     dword ptr [rax+rax+00h]
0x140053fb9  mov     rcx, r14; this
0x140053fbc  call    ?AbortDevices@VMX_PACK@@AEAAXXZ; VMX_PACK::AbortDevices(void)
0x140053fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140053fc8  lea     rax, WPP_GLOBAL_Control
0x140053fcf  cmp     rcx, rax
0x140053fd2  jz      short loc_140053FF9
0x140053fd4  mov     eax, [rcx+2Ch]
0x140053fd7  test    al, 8
0x140053fd9  jz      short loc_140053FF9
0x140053fdb  cmp     byte ptr [rcx+29h], 2
0x140053fdf  jb      short loc_140053FF9
0x140053fe1  mov     edx, 0F1h
0x140053fe6  mov     rcx, [rcx+18h]
0x140053fea  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140053ff1  mov     r9d, edi
0x140053ff4  call    WPP_SF_d
0x140053ff9  mov     eax, edi
0x140053ffb  jmp     loc_1400542FF
0x140054000  mov     byte ptr [rdi+rbx+10h], 1
0x140054005  movzx   r9d, word ptr [r15+40h]
0x14005400a  test    r9b, 8
0x14005400e  jz      short loc_14005402A
0x140054010  mov     r12, [rsp+150h+var_108]
0x140054015  mov     byte ptr [rdi+rbx+11h], 1
0x14005401a  mov     qword ptr [r13+0F8h], 0
0x140054025  jmp     loc_140053F82
0x14005402a  shr     r9b, 5
0x14005402e  lea     rax, [rsp+150h+var_100]
0x140054033  mov     qword ptr [rsp+150h+var_128], rax; struct VMX_VOLUME_DEVICE **
0x140054038  and     r9b, 1; unsigned __int8
0x14005403c  cmp     qword ptr [r12], 0
0x140054041  mov     rdx, r13; struct VMX_VOLUME_INFO *
0x140054044  mov     al, [r14+39h]
0x140054048  mov     rcx, r14; this
0x14005404b  setz    r8b; unsigned __int8
0x14005404f  mov     byte ptr [rsp+150h+var_130], al; unsigned __int8
0x140054053  call    ?BuildVolumeDevice@VMX_PACK@@AEAAJPEAVVMX_VOLUME_INFO@@EEEPEAPEAVVMX_VOLUME_DEVICE@@@Z; VMX_PACK::BuildVolumeDevice(VMX_VOLUME_INFO *,uchar,uchar,uchar,VMX_VOLUME_DEVICE * *)
0x140054058  mov     r12d, eax
0x14005405b  test    eax, eax
0x14005405d  js      loc_1400542AE
0x140054063  mov     r12, [rsp+150h+var_100]
0x140054068  mov     [r13+0F8h], r12
  ... truncated ...
```
