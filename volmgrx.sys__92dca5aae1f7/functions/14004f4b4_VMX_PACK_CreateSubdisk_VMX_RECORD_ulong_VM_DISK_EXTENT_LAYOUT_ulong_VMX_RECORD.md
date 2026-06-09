# VMX_PACK::CreateSubdisk(VMX_RECORD *,ulong,_VM_DISK_EXTENT_LAYOUT *,ulong,VMX_RECORD * *)

- ea: `0x14004f4b4`
- end: `0x14004fe3a`
- name: `?CreateSubdisk@VMX_PACK@@AEAAJPEAVVMX_RECORD@@KPEAU_VM_DISK_EXTENT_LAYOUT@@KPEAPEAV2@@Z`
- size: `2438`
- prototype: `int(VMX_PACK *__hidden this, struct VMX_RECORD *, unsigned int, struct _VM_DISK_EXTENT_LAYOUT *, unsigned int, struct VMX_RECORD **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14004eb24`
- `0x140050c48`

## callees

- `0x1400099d8`
- `0x14001b9a0`
- `0x14002aed4`
- `0x14003f158`
- `0x1400401cc`
- `0x14004037c`
- `0x14004f4b4`
- `0x14005c600`
- `0x14005d734`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004f918`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f950`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f9a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f918`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f950`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f9a6`

## pseudocode

```c
__int64 __fastcall VMX_PACK::CreateSubdisk(
        VMX_CONFIG **this,
        struct VMX_RECORD *a2,
        unsigned int a3,
        struct _GUID *a4,
        unsigned int a5,
        struct VMX_RECORD **a6)
{
  VMX_RECORD *DiskById; // rax
  VMX_RECORD *v9; // r14
  VMX_NOTIFICATION_QUEUE *v10; // rcx
  unsigned int DriveLayout; // ebx
  __int64 v12; // rdx
  __int64 v13; // r13
  __int64 v14; // r12
  __int64 v15; // rcx
  unsigned int *v16; // rbp
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rsi
  struct VMX_RECORD *i; // rcx
  __int64 v20; // rax
  _QWORD *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rdi
  __int64 v24; // rax
  unsigned __int64 v25; // r9
  __int64 j; // rdx
  char v27; // al
  unsigned __int64 v28; // r10
  unsigned __int64 v29; // rcx
  __int64 k; // rcx
  unsigned __int64 v31; // r11
  VMX_NOTIFICATION_QUEUE *v32; // rcx
  __int64 v33; // rdx
  __int64 v35; // rbx
  __int64 v36; // r14
  unsigned __int64 v37; // rbp
  VMX_NOTIFICATION_QUEUE *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r15
  __int64 v41; // rcx
  VMX_RECORD *v42; // rbx
  int v43; // edi
  VMX_NOTIFICATION_QUEUE *v44; // rcx
  __int64 v45; // rdx
  unsigned int v46; // r9d
  VMX_RECORD *v47; // rsi
  __int64 v48; // rdi
  __int64 v49; // r9
  VMX_RECORD *v50; // rcx
  VMX_RECORD *v51; // rbp
  __int64 v52; // rdx
  __int64 v53; // rbx
  __int64 v54; // rcx
  VMX_RECORD *v55; // r14
  int v56; // ebp
  PVOID P; // [rsp+20h] [rbp-68h] BYREF
  __int64 v58; // [rsp+28h] [rbp-60h]
  VMX_RECORD *v59; // [rsp+30h] [rbp-58h] BYREF
  VMX_RECORD *v60; // [rsp+38h] [rbp-50h]
  __int64 v64; // [rsp+A8h] [rbp+20h]

  P = 0;
  v59 = 0;
  *a6 = 0;
  DiskById = VMX_CONFIG::FindDiskById(this[2], a4);
  v60 = DiskById;
  v9 = DiskById;
  if ( !DiskById )
  {
    v10 = WPP_GLOBAL_Control;
    DriveLayout = -1070071800;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveLayout;
    }
    v12 = 308;
    goto LABEL_152;
  }
  v13 = *((_QWORD *)a2 + 6);
  DriveLayout = VMX_RECORD::PreTouch(DiskById);
  if ( (DriveLayout & 0x80000000) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveLayout;
    }
    v12 = 309;
    goto LABEL_152;
  }
  v14 = *((_QWORD *)v9 + 6);
  DriveLayout = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 88LL))(v14);
  if ( (DriveLayout & 0x80000000) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveLayout;
    }
    v12 = 310;
    goto LABEL_152;
  }
  v15 = *(_QWORD *)(v14 + 128);
  v16 = *(unsigned int **)(v15 + 16);
  v17 = v16[9];
  if ( (_DWORD)v17 != a5 )
  {
    v10 = WPP_GLOBAL_Control;
    DriveLayout = -1070071730;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveLayout;
    }
    v12 = 311;
    goto LABEL_152;
  }
  v18 = v16[9];
  DriveLayout = -1070071779;
  if ( *(_QWORD *)&a4[1].Data1 % v17 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveLayout;
    }
    v12 = 312;
    goto LABEL_152;
  }
  if ( *(_QWORD *)a4[1].Data4 % v18 || !*(_QWORD *)a4[1].Data4 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveLayout;
    }
    v12 = 313;
    goto LABEL_152;
  }
  v64 = *(_QWORD *)(v15 + 88);
  v58 = *(_QWORD *)(*(_QWORD *)(v13 + 136) + 8LL * (*(_WORD *)(*(_QWORD *)(v13 + 136) + 64LL) & 1) + 40);
  for ( i = *(struct VMX_RECORD **)(v58 + 264); i; i = (struct VMX_RECORD *)v21[18] )
  {
    v20 = *((_WORD *)i + 32) & 1;
    v21 = (_QWORD *)*((_QWORD *)i + v20 + 5);
    if ( i != a2
      && (*(unsigned __int8 (__fastcall **)(_QWORD, VMX_RECORD *))(*v21 + 80LL))(*((_QWORD *)i + v20 + 5), v9) )
    {
      v10 = WPP_GLOBAL_Control;
      DriveLayout = -1070071784;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return DriveLayout;
      }
      v12 = 314;
      goto LABEL_152;
    }
  }
  v22 = *(_QWORD *)(v13 + 152);
  v23 = 0;
  while ( v22 )
  {
    v24 = *(_WORD *)(v22 + 64) & 1;
    v23 = *(_QWORD *)(v22 + 8 * v24 + 40);
    if ( a3 != *(_DWORD *)(v23 + 128)
      && (*(unsigned __int8 (__fastcall **)(_QWORD, VMX_RECORD *))(*(_QWORD *)v23 + 80LL))(
           *(_QWORD *)(v22 + 8 * v24 + 40),
           v9) )
    {
      v10 = WPP_GLOBAL_Control;
      DriveLayout = -1070071785;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v12 = 315;
        goto LABEL_152;
      }
      return DriveLayout;
    }
    v22 = *(_QWORD *)(v23 + 176);
  }
  v25 = *(_QWORD *)&a4[1].Data1;
  if ( v25 < v18 * *(_QWORD *)(v64 + 136)
    || v25 + *(_QWORD *)a4[1].Data4 > v18 * (*(_QWORD *)(v64 + 136) + *(_QWORD *)(v64 + 144)) )
  {
    v10 = WPP_GLOBAL_Control;
    DriveLayout = -1070071780;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveLayout;
    }
    v12 = 316;
    goto LABEL_152;
  }
  DriveLayout = VMX_DISK_DEVICE::GetDriveLayoutEx((VMX_DISK_DEVICE *)v16, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
  if ( (DriveLayout & 0x80000000) == 0 )
  {
    if ( !*(_DWORD *)P )
    {
      for ( j = 0; (unsigned int)j < *((_DWORD *)P + 1); j = (unsigned int)(j + 1) )
      {
        v27 = *((_BYTE *)P + 144 * j + 80);
        if ( v27 == 5 || v27 == 15 )
        {
          v28 = *((_QWORD *)P + 18 * j + 7);
          v29 = *(_QWORD *)&a4[1].Data1;
          if ( v29 < v28 + v18 && *(_QWORD *)a4[1].Data4 + v29 > v28 )
          {
            if ( (*(_DWORD *)(v58 + 156) & 0x800000) == 0 )
            {
              ExFreePoolWithTag(P, 0);
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                v33 = 318;
LABEL_76:
                WPP_SF_d(*((_QWORD *)v32 + 3), v33, WPP_b525482092043ba595507d12d78e6f73_Traceguids, 3224895518LL);
              }
              return 3224895518LL;
            }
            for ( k = *(_QWORD *)(v14 + 120); k; k = *(_QWORD *)(v23 + 160) )
            {
              v23 = *(_QWORD *)(k + 8LL * (*(_WORD *)(k + 64) & 1) + 40);
              v31 = (*(_QWORD *)(v23 + 80) << 9) + *(_QWORD *)(v64 + 136) * v18;
              if ( v31 < v28 + *((_QWORD *)P + 18 * j + 8)
                && v31 + (*(_QWORD *)(v23 + 96) << 9) > v28
                && (*(_DWORD *)(v23 + 72) & 0x40) != 0 )
              {
                ExFreePoolWithTag(P, 0);
                v32 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
                {
                  v33 = 319;
                  goto LABEL_76;
                }
                return 3224895518LL;
              }
            }
          }
        }
      }
    }
    ExFreePoolWithTag(P, 0);
    v35 = 0;
    v36 = *(_QWORD *)(v14 + 120);
    v37 = (*(_QWORD *)&a4[1].Data1 - *(_QWORD *)(v64 + 136) * v18) >> 9;
    if ( v36 )
    {
      do
      {
        v23 = *(_QWORD *)(v36 + 8LL * (*(_WORD *)(v36 + 64) & 1) + 40);
        if ( v37 < *(_QWORD *)(v23 + 80) )
          break;
        v36 = *(_QWORD *)(v23 + 160);
        v35 = v23;
      }
      while ( v36 );
      if ( v35 && v37 < *(_QWORD *)(v35 + 80) + *(_QWORD *)(v35 + 96) )
      {
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return 3224895514LL;
        }
        v39 = 320;
LABEL_93:
        WPP_SF_d(*((_QWORD *)v38 + 3), v39, WPP_b525482092043ba595507d12d78e6f73_Traceguids, 3224895514LL);
        return 3224895514LL;
      }
    }
    v40 = *(_QWORD *)a4[1].Data4 >> 9;
    if ( v36 && v40 + v37 > *(_QWORD *)(v23 + 80) )
    {
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3224895514LL;
      }
      v39 = 321;
      goto LABEL_93;
    }
    if ( v35 )
    {
      if ( v37 == *(_QWORD *)(v35 + 80) + *(_QWORD *)(v35 + 96)
        && *(struct VMX_RECORD **)(v35 + 168) == a2
        && *(_DWORD *)(v35 + 128) == a3 )
      {
        v41 = *(_QWORD *)(v35 + 176);
        if ( !v41 || *(_DWORD *)(*(_QWORD *)(v41 + 8LL * (*(_WORD *)(v41 + 64) & 1) + 40) + 128LL) != a3 )
        {
          v42 = *(VMX_RECORD **)(v35 + 48);
          v43 = VMX_RECORD::PreTouch(v42);
          if ( v43 < 0 )
          {
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
            {
              return (unsigned int)v43;
            }
            v45 = 322;
LABEL_106:
            WPP_SF_d(*((_QWORD *)v44 + 3), v45, WPP_b525482092043ba595507d12d78e6f73_Traceguids, (unsigned int)v43);
            return (unsigned int)v43;
          }
          *(_QWORD *)(*((_QWORD *)v42 + 6) + 96LL) += v40;
          VMX_RECORD::Touch(v42, this[6]);
          *a6 = v42;
          return 0;
        }
      }
    }
    if ( (*(_DWORD *)(v58 + 156) & 0x800000) != 0 && *(_DWORD *)(v13 + 92) )
    {
      v10 = WPP_GLOBAL_Control;
      DriveLayout = -1070071781;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return DriveLayout;
      }
      v12 = 323;
      goto LABEL_152;
    }
    v43 = VMX_CONFIG::CreateSubdiskRecord(this[2], &v59);
    if ( v43 < 0 )
    {
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return (unsigned int)v43;
      }
      v45 = 324;
      goto LABEL_106;
    }
    v47 = v59;
    v48 = *((_QWORD *)v59 + 6);
    VMX_CONFIG::NextSubdiskName(this[2], (char *)(v14 + 16), (char *)(v48 + 16), v46);
    VMX_RECORD::Touch(v47, this[6]);
    ++*(_DWORD *)(*(_QWORD *)(v49 + 48) + 16LL);
    v50 = v60;
    *(_QWORD *)(v48 + 80) = v37;
    *(_QWORD *)(v48 + 96) = v40;
    *(_QWORD *)(v48 + 112) = *((_QWORD *)v50 + 3);
    *(_QWORD *)(v48 + 152) = v50;
    if ( !v35 )
    {
      *(_QWORD *)(v14 + 120) = v47;
      goto LABEL_129;
    }
    v51 = *(VMX_RECORD **)(v35 + 48);
    DriveLayout = VMX_RECORD::PreTouch(v51);
    if ( (DriveLayout & 0x80000000) == 0 )
    {
      *(_QWORD *)(*((_QWORD *)v51 + 6) + 160LL) = v47;
LABEL_129:
      v52 = 0;
      *(_QWORD *)(v48 + 160) = v36;
      *(_QWORD *)(v48 + 104) = *((_QWORD *)a2 + 3);
      *(_QWORD *)(v48 + 168) = a2;
      *(_DWORD *)(v48 + 128) = a3;
      v53 = *(_QWORD *)(v13 + 152);
      if ( !v53 )
        goto LABEL_142;
      do
      {
        v54 = *(_QWORD *)(v53 + 8LL * (*(_WORD *)(v53 + 64) & 1) + 40);
        if ( a3 == *(_DWORD *)(v54 + 128) )
        {
          *(_QWORD *)(v48 + 88) += *(_QWORD *)(v54 + 96);
        }
        else if ( a3 < *(_DWORD *)(v54 + 128) )
        {
          break;
        }
        v53 = *(_QWORD *)(v54 + 176);
        v52 = v54;
      }
      while ( v53 );
      if ( v52 )
      {
        v55 = *(VMX_RECORD **)(v52 + 48);
        v56 = VMX_RECORD::PreTouch(v55);
        if ( v56 < 0 )
        {
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              326,
              WPP_b525482092043ba595507d12d78e6f73_Traceguids,
              (unsigned int)v56);
          }
          return (unsigned int)v56;
        }
        *(_QWORD *)(*((_QWORD *)v55 + 6) + 176LL) = v47;
      }
      else
      {
LABEL_142:
        *(_QWORD *)(v13 + 152) = v47;
      }
      *(_QWORD *)(v48 + 176) = v53;
      ++*(_DWORD *)(v13 + 92);
      *a6 = v47;
      return 0;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return DriveLayout;
    }
    v12 = 325;
LABEL_152:
    WPP_SF_d(*((_QWORD *)v10 + 3), v12, WPP_b525482092043ba595507d12d78e6f73_Traceguids, DriveLayout);
    return DriveLayout;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v12 = 317;
    goto LABEL_152;
  }
  return DriveLayout;
}

```

## disassembly

```asm
0x14004f4b4  mov     r11, rsp
0x14004f4b7  mov     [r11+18h], r8d
0x14004f4bb  mov     [r11+10h], rdx
0x14004f4bf  mov     [r11+8], rcx
0x14004f4c3  push    rbx
0x14004f4c4  push    rbp
0x14004f4c5  push    rsi
0x14004f4c6  push    rdi
0x14004f4c7  push    r12
0x14004f4c9  push    r13
0x14004f4cb  push    r14
0x14004f4cd  push    r15
0x14004f4cf  sub     rsp, 48h
0x14004f4d3  mov     rax, rcx
0x14004f4d6  xor     esi, esi
0x14004f4d8  mov     rcx, [rsp+88h+arg_28]
0x14004f4e0  mov     rdi, rdx
0x14004f4e3  mov     rdx, r9; struct _GUID *
0x14004f4e6  mov     [r11-68h], rsi
0x14004f4ea  mov     r15, r9
0x14004f4ed  mov     [r11-58h], rsi
0x14004f4f1  mov     [rcx], rsi
0x14004f4f4  mov     rcx, [rax+10h]; this
0x14004f4f8  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x14004f4fd  mov     [rsp+88h+var_50], rax
0x14004f502  mov     r14, rax
0x14004f505  test    rax, rax
0x14004f508  jnz     short loc_14004F545
0x14004f50a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f511  lea     rax, WPP_GLOBAL_Control
0x14004f518  mov     ebx, 0C0380008h
0x14004f51d  cmp     rcx, rax
0x14004f520  jz      loc_14004FE26
0x14004f526  mov     eax, [rcx+2Ch]
0x14004f529  test    al, 8
0x14004f52b  jz      loc_14004FE26
0x14004f531  cmp     byte ptr [rcx+29h], 2
0x14004f535  jb      loc_14004FE26
0x14004f53b  mov     edx, 134h
0x14004f540  jmp     loc_14004FE13
0x14004f545  mov     r13, [rdi+30h]
0x14004f549  mov     rcx, r14; this
0x14004f54c  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x14004f551  mov     ebx, eax
0x14004f553  test    eax, eax
0x14004f555  jns     short loc_14004F58E
0x14004f557  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f55e  lea     rax, WPP_GLOBAL_Control
0x14004f565  cmp     rcx, rax
0x14004f568  jz      loc_14004FE26
0x14004f56e  mov     edx, [rcx+2Ch]
0x14004f571  test    dl, 8
0x14004f574  jz      loc_14004FE26
0x14004f57a  cmp     byte ptr [rcx+29h], 2
0x14004f57e  jb      loc_14004FE26
0x14004f584  mov     edx, 135h
0x14004f589  jmp     loc_14004FE13
0x14004f58e  mov     r12, [r14+30h]
0x14004f592  mov     rcx, r12
0x14004f595  mov     rax, [r12]
0x14004f599  mov     rax, [rax+58h]
0x14004f59d  call    _guard_dispatch_icall
0x14004f5a2  mov     ebx, eax
0x14004f5a4  test    eax, eax
0x14004f5a6  jns     short loc_14004F5DF
0x14004f5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f5af  lea     rax, WPP_GLOBAL_Control
0x14004f5b6  cmp     rcx, rax
0x14004f5b9  jz      loc_14004FE26
0x14004f5bf  mov     edx, [rcx+2Ch]
0x14004f5c2  test    dl, 8
0x14004f5c5  jz      loc_14004FE26
0x14004f5cb  cmp     byte ptr [rcx+29h], 2
0x14004f5cf  jb      loc_14004FE26
0x14004f5d5  mov     edx, 136h
0x14004f5da  jmp     loc_14004FE13
0x14004f5df  mov     rcx, [r12+80h]
0x14004f5e7  mov     rbp, [rcx+10h]
0x14004f5eb  mov     eax, [rbp+24h]
0x14004f5ee  cmp     eax, [rsp+88h+arg_20]
0x14004f5f5  jz      short loc_14004F632
0x14004f5f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f5fe  lea     rax, WPP_GLOBAL_Control
0x14004f605  mov     ebx, 0C038004Eh
0x14004f60a  cmp     rcx, rax
0x14004f60d  jz      loc_14004FE26
0x14004f613  mov     eax, [rcx+2Ch]
0x14004f616  test    al, 8
0x14004f618  jz      loc_14004FE26
0x14004f61e  cmp     byte ptr [rcx+29h], 2
0x14004f622  jb      loc_14004FE26
0x14004f628  mov     edx, 137h
0x14004f62d  jmp     loc_14004FE13
0x14004f632  mov     rsi, rax
0x14004f635  xor     edx, edx
0x14004f637  mov     rax, [r15+10h]
0x14004f63b  mov     ebx, 0C038001Dh
0x14004f640  div     rsi
0x14004f643  test    rdx, rdx
0x14004f646  jz      short loc_14004F67E
0x14004f648  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f64f  lea     rax, WPP_GLOBAL_Control
0x14004f656  cmp     rcx, rax
0x14004f659  jz      loc_14004FE26
0x14004f65f  mov     eax, [rcx+2Ch]
0x14004f662  test    al, 8
0x14004f664  jz      loc_14004FE26
0x14004f66a  cmp     byte ptr [rcx+29h], 2
0x14004f66e  jb      loc_14004FE26
0x14004f674  mov     edx, 138h
0x14004f679  jmp     loc_14004FE13
0x14004f67e  mov     r8, [r15+18h]
0x14004f682  xor     edx, edx
0x14004f684  mov     rax, r8
0x14004f687  div     rsi
0x14004f68a  test    rdx, rdx
0x14004f68d  jnz     loc_14004FDEE
0x14004f693  test    r8, r8
0x14004f696  jz      loc_14004FDEE
0x14004f69c  mov     r8, [rcx+58h]
0x14004f6a0  mov     rcx, [r13+88h]
0x14004f6a7  mov     [rsp+88h+arg_18], r8
0x14004f6af  movzx   eax, word ptr [rcx+40h]
0x14004f6b3  and     eax, 1
0x14004f6b6  mov     rax, [rcx+rax*8+28h]
0x14004f6bb  mov     [rsp+88h+var_60], rax
0x14004f6c0  mov     rcx, [rax+108h]
0x14004f6c7  test    rcx, rcx
0x14004f6ca  jz      short loc_14004F737
0x14004f6cc  movzx   eax, word ptr [rcx+40h]
0x14004f6d0  and     eax, 1
0x14004f6d3  mov     rbx, [rcx+rax*8+28h]
0x14004f6d8  cmp     rcx, rdi
0x14004f6db  jz      short loc_14004F6F3
0x14004f6dd  mov     rax, [rbx]
0x14004f6e0  mov     rdx, r14
0x14004f6e3  mov     rcx, rbx
0x14004f6e6  mov     rax, [rax+50h]
0x14004f6ea  call    _guard_dispatch_icall
0x14004f6ef  test    al, al
0x14004f6f1  jnz     short loc_14004F6FC
0x14004f6f3  mov     rcx, [rbx+90h]
0x14004f6fa  jmp     short loc_14004F6C7
0x14004f6fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f703  lea     rax, WPP_GLOBAL_Control
0x14004f70a  mov     ebx, 0C0380018h
0x14004f70f  cmp     rcx, rax
0x14004f712  jz      loc_14004FE26
0x14004f718  mov     eax, [rcx+2Ch]
0x14004f71b  test    al, 8
0x14004f71d  jz      loc_14004FE26
0x14004f723  cmp     byte ptr [rcx+29h], 2
0x14004f727  jb      loc_14004FE26
0x14004f72d  mov     edx, 13Ah
0x14004f732  jmp     loc_14004FE13
0x14004f737  mov     rcx, [r13+98h]
0x14004f73e  xor     edi, edi
0x14004f740  mov     ebx, [rsp+88h+arg_10]
0x14004f747  test    rcx, rcx
0x14004f74a  jz      short loc_14004F7BA
0x14004f74c  movzx   eax, word ptr [rcx+40h]
0x14004f750  and     eax, 1
0x14004f753  mov     rdi, [rcx+rax*8+28h]
0x14004f758  cmp     ebx, [rdi+80h]
0x14004f75e  jz      short loc_14004F776
0x14004f760  mov     rax, [rdi]
0x14004f763  mov     rdx, r14
0x14004f766  mov     rcx, rdi
0x14004f769  mov     rax, [rax+50h]
0x14004f76d  call    _guard_dispatch_icall
0x14004f772  test    al, al
0x14004f774  jnz     short loc_14004F77F
0x14004f776  mov     rcx, [rdi+0B0h]
0x14004f77d  jmp     short loc_14004F747
0x14004f77f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f786  lea     rax, WPP_GLOBAL_Control
0x14004f78d  mov     ebx, 0C0380017h
0x14004f792  cmp     rcx, rax
0x14004f795  jz      loc_14004FE26
0x14004f79b  mov     eax, [rcx+2Ch]
0x14004f79e  test    al, 8
0x14004f7a0  jz      loc_14004FE26
0x14004f7a6  cmp     byte ptr [rcx+29h], 2
0x14004f7aa  jb      loc_14004FE26
0x14004f7b0  mov     edx, 13Bh
0x14004f7b5  jmp     loc_14004FE13
0x14004f7ba  mov     r8, [rsp+88h+arg_18]
0x14004f7c2  mov     r9, [r15+10h]
0x14004f7c6  mov     rdx, [r8+88h]
0x14004f7cd  mov     rax, rdx
0x14004f7d0  imul    rax, rsi
0x14004f7d4  cmp     r9, rax
0x14004f7d7  jb      loc_14004FDC2
0x14004f7dd  mov     r8, [r8+90h]
0x14004f7e4  add     r8, rdx
0x14004f7e7  mov     rdx, [r15+18h]
0x14004f7eb  imul    r8, rsi
0x14004f7ef  add     rdx, r9
0x14004f7f2  cmp     rdx, r8
0x14004f7f5  ja      loc_14004FDC2
0x14004f7fb  lea     rdx, [rsp+88h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14004f800  mov     rcx, rbp; this
0x14004f803  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14004f808  mov     ebx, eax
0x14004f80a  test    eax, eax
0x14004f80c  jns     short loc_14004F845
0x14004f80e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f815  lea     rax, WPP_GLOBAL_Control
0x14004f81c  cmp     rcx, rax
0x14004f81f  jz      loc_14004FE26
0x14004f825  mov     edx, [rcx+2Ch]
0x14004f828  test    dl, 8
0x14004f82b  jz      loc_14004FE26
0x14004f831  cmp     byte ptr [rcx+29h], 2
0x14004f835  jb      loc_14004FE26
0x14004f83b  mov     edx, 13Dh
0x14004f840  jmp     loc_14004FE13
0x14004f845  mov     r8, [rsp+88h+P]
0x14004f84a  mov     rbp, [rsp+88h+arg_18]
0x14004f852  cmp     dword ptr [r8], 0
0x14004f856  jnz     loc_14004F9A1
0x14004f85c  mov     ebx, [r8+4]
0x14004f860  xor     edx, edx
0x14004f862  mov     r14, [rsp+88h+var_60]
0x14004f867  cmp     edx, ebx
0x14004f869  jnb     loc_14004F9A1
0x14004f86f  lea     r9, [rdx+rdx*8]
0x14004f873  add     r9, r9
0x14004f876  mov     al, [r8+r9*8+50h]
0x14004f87b  cmp     al, 5
0x14004f87d  jz      short loc_14004F887
0x14004f87f  cmp     al, 0Fh
0x14004f881  jnz     loc_14004F90C
0x14004f887  mov     r10, [r8+r9*8+38h]
0x14004f88c  mov     rcx, [r15+10h]
0x14004f890  lea     rax, [r10+rsi]
0x14004f894  cmp     rcx, rax
0x14004f897  jnb     short loc_14004F90C
0x14004f899  add     rcx, [r15+18h]
0x14004f89d  cmp     rcx, r10
0x14004f8a0  jbe     short loc_14004F90C
0x14004f8a2  test    dword ptr [r14+9Ch], 800000h
0x14004f8ad  jz      loc_14004F94B
0x14004f8b3  mov     rcx, [r12+78h]
0x14004f8b8  test    rcx, rcx
0x14004f8bb  jz      short loc_14004F90C
0x14004f8bd  movzx   eax, word ptr [rcx+40h]
0x14004f8c1  mov     r11, rsi
0x14004f8c4  imul    r11, [rbp+88h]
0x14004f8cc  and     eax, 1
0x14004f8cf  mov     rdi, [rcx+rax*8+28h]
0x14004f8d4  mov     rcx, [r8+r9*8+40h]
0x14004f8d9  add     rcx, r10
0x14004f8dc  mov     rax, [rdi+50h]
0x14004f8e0  shl     rax, 9
0x14004f8e4  add     r11, rax
0x14004f8e7  cmp     r11, rcx
0x14004f8ea  jnb     short loc_14004F903
0x14004f8ec  mov     rax, [rdi+60h]
0x14004f8f0  shl     rax, 9
0x14004f8f4  add     rax, r11
0x14004f8f7  cmp     rax, r10
0x14004f8fa  jbe     short loc_14004F903
0x14004f8fc  mov     eax, [rdi+48h]
0x14004f8ff  test    al, 40h
0x14004f901  jnz     short loc_14004F913
0x14004f903  mov     rcx, [rdi+0A0h]
0x14004f90a  jmp     short loc_14004F8B8
0x14004f90c  inc     edx
0x14004f90e  jmp     loc_14004F867
0x14004f913  xor     edx, edx; Tag
0x14004f915  mov     rcx, r8; P
0x14004f918  call    cs:__imp_ExFreePoolWithTag
0x14004f91f  nop     dword ptr [rax+rax+00h]
0x14004f924  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f92b  lea     rax, WPP_GLOBAL_Control
0x14004f932  cmp     rcx, rax
0x14004f935  jz      short loc_14004F997
0x14004f937  mov     eax, [rcx+2Ch]
0x14004f93a  test    al, 8
0x14004f93c  jz      short loc_14004F997
0x14004f93e  cmp     byte ptr [rcx+29h], 2
0x14004f942  jb      short loc_14004F997
0x14004f944  mov     edx, 13Fh
0x14004f949  jmp     short loc_14004F981
0x14004f94b  xor     edx, edx; Tag
0x14004f94d  mov     rcx, r8; P
0x14004f950  call    cs:__imp_ExFreePoolWithTag
0x14004f957  nop     dword ptr [rax+rax+00h]
0x14004f95c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f963  lea     rax, WPP_GLOBAL_Control
0x14004f96a  cmp     rcx, rax
0x14004f96d  jz      short loc_14004F997
0x14004f96f  mov     eax, [rcx+2Ch]
0x14004f972  test    al, 8
0x14004f974  jz      short loc_14004F997
0x14004f976  cmp     byte ptr [rcx+29h], 2
0x14004f97a  jb      short loc_14004F997
0x14004f97c  mov     edx, 13Eh
0x14004f981  mov     rcx, [rcx+18h]
  ... truncated ...
```
