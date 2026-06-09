# VmxPartitionRemovedImmediate(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,uchar *)

- ea: `0x140034c20`
- end: `0x140034ee3`
- name: `?VmxPartitionRemovedImmediate@@YAJPEAU_DEVICE_OBJECT@@0PEAU_PARTITION_INFORMATION_EX@@PEAE@Z`
- size: `707`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, struct _PARTITION_INFORMATION_EX *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140030110`

## callees

- `0x14000774c`
- `0x140009a60`
- `0x14001b960`
- `0x140033750`
- `0x140033854`
- `0x1400341a8`
- `0x1400348d8`
- `0x140034c20`
- `0x140047134`
- `0x140047368`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140034e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034eca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034e95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034eca`

## pseudocode

```c
__int64 __fastcall VmxPartitionRemovedImmediate(
        struct _DEVICE_OBJECT *a1,
        struct _DEVICE_OBJECT *a2,
        struct _PARTITION_INFORMATION_EX *a3,
        unsigned __int8 *a4)
{
  struct VMX_DISK_DEVICE *DiskDeviceByPdo; // rax
  VMX_DISK_DEVICE *v7; // rsi
  PVOID v8; // rdi
  unsigned int v9; // r11d
  int v10; // r10d
  int v11; // r8d
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int v14; // edx
  int v15; // eax
  unsigned int v16; // r11d
  int v17; // r8d
  int v18; // r9d
  int v19; // edx
  __int64 v20; // r10
  struct _DISK_GEOMETRY *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // ebx
  PVOID P; // [rsp+30h] [rbp-40h] BYREF
  PVOID v28; // [rsp+38h] [rbp-38h] BYREF
  __int128 v29; // [rsp+40h] [rbp-30h] BYREF
  __int128 v30; // [rsp+50h] [rbp-20h] BYREF
  __int64 v31; // [rsp+60h] [rbp-10h]

  v31 = 0;
  v29 = 0;
  v28 = 0;
  v30 = 0;
  P = 0;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 3), 76, a2, a1, a2);
  }
  *a4 = 0;
  if ( a1 )
  {
    DiskDeviceByPdo = VmxpFindDiskDeviceByPdo(a1);
    v7 = DiskDeviceByPdo;
    if ( DiskDeviceByPdo )
    {
      if ( !*((_DWORD *)DiskDeviceByPdo + 10) )
      {
        if ( *((_BYTE *)DiskDeviceByPdo + 52) )
          goto LABEL_9;
        if ( (int)VMX_DISK_DEVICE::GetDriveGeometry(DiskDeviceByPdo, &v30) >= 0
          && (int)VMX_DISK_DEVICE::GetDriveLayoutEx(v7, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&v28) >= 0
          && (int)VMX_DISK_DEVICE::GetDiskAttributes(v7, &v29) >= 0 )
        {
          v8 = v28;
          if ( *(_DWORD *)v28 )
          {
            if ( *(_DWORD *)v28 == 1 )
            {
              v16 = *((_DWORD *)v28 + 1);
              v17 = 0;
              v18 = 0;
              v19 = 0;
              v20 = 0;
              if ( !v16 )
                goto LABEL_56;
              do
              {
                v21 = (struct _DISK_GEOMETRY *)(18 * v20);
                v22 = *((_QWORD *)v28 + 18 * v20 + 10) - *(_QWORD *)&PARTITION_LDM_METADATA_GUID.Data1;
                if ( !v22 )
                  v22 = *((_QWORD *)v28 + 18 * v20 + 11) - *(_QWORD *)PARTITION_LDM_METADATA_GUID.Data4;
                if ( v22 )
                {
                  v23 = *((_QWORD *)v28 + 18 * v20 + 10) - *(_QWORD *)&PARTITION_LDM_DATA_GUID.Data1;
                  if ( !v23 )
                    v23 = *((_QWORD *)v28 + 18 * v20 + 11) - *(_QWORD *)PARTITION_LDM_DATA_GUID.Data4;
                  if ( v23 )
                  {
                    v24 = *((_QWORD *)v28 + 18 * v20 + 10) - *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
                    if ( !v24 )
                      v24 = *((_QWORD *)v28 + 18 * v20 + 11) - *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
                    if ( !v24 )
                      ++v19;
                  }
                  else
                  {
                    ++v17;
                  }
                }
                else
                {
                  ++v18;
                }
                v20 = (unsigned int)(v20 + 1);
              }
              while ( (unsigned int)v20 < v16 );
              if ( !v17 )
                goto LABEL_56;
              if ( !v18 || v19 )
              {
                v15 = VmxpPrepareForDeleteDynamicPartitionsGpt(
                        v21,
                        (struct _DRIVE_LAYOUT_INFORMATION_EX *)v28,
                        (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
                goto LABEL_50;
              }
            }
            goto LABEL_54;
          }
          v9 = *((_DWORD *)v28 + 1);
          v10 = 0;
          v11 = 0;
          v12 = 0;
          if ( !v9 )
            goto LABEL_56;
          while ( 1 )
          {
            v13 = 18 * v12;
            v14 = *((unsigned __int8 *)v28 + 144 * v12 + 80);
            if ( (unsigned __int8)v14 <= 0xFu )
            {
              v13 = 32801;
              if ( _bittest((const int *)&v13, v14) )
                goto LABEL_27;
            }
            if ( (_BYTE)v14 == 0xA0
              || (_BYTE)v14 == 0x84
              || (_BYTE)v14 == 39
              || (_BYTE)v14 == 18
              || (unsigned __int8)(v14 + 34) <= 0x20u && (v13 = 0x100000201LL, _bittest64(&v13, v14 + 34)) )
            {
              if ( (unsigned int)v12 >= 4 )
LABEL_26:
                ++v11;
            }
            else
            {
              if ( (_BYTE)v14 != 66 )
                goto LABEL_26;
              ++v10;
            }
LABEL_27:
            v12 = (unsigned int)(v12 + 1);
            if ( (unsigned int)v12 >= v9 )
            {
              if ( !v10 )
                goto LABEL_56;
              if ( v11 )
              {
                v15 = VmxpPrepareForDeleteDynamicPartitionsMbr(
                        (struct _DISK_GEOMETRY *)v13,
                        (struct _DRIVE_LAYOUT_INFORMATION_EX *)v28,
                        (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
LABEL_50:
                if ( v15 < 0 || (v25 = VMX_DISK_DEVICE::SetDriveLayoutEx(v7, P), ExFreePoolWithTag(P, 0), v25 < 0) )
                {
LABEL_52:
                  ExFreePoolWithTag(v8, 0);
                  return 0;
                }
LABEL_56:
                ExFreePoolWithTag(v8, 0);
                VMX_DISK_DEVICE::Stop(v7);
LABEL_9:
                *a4 = 1;
                return 0;
              }
LABEL_54:
              if ( (BYTE8(v29) & 1) == 0 )
                goto LABEL_52;
              *((_BYTE *)v7 + 54) = 0;
              goto LABEL_56;
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140034c20  push    rbp
0x140034c22  push    rbx
0x140034c23  push    rsi
0x140034c24  push    rdi
0x140034c25  push    r14
0x140034c27  mov     rbp, rsp
0x140034c2a  sub     rsp, 70h
0x140034c2e  mov     rax, cs:__security_cookie
0x140034c35  xor     rax, rsp
0x140034c38  mov     [rbp+var_8], rax
0x140034c3c  xor     eax, eax
0x140034c3e  xorps   xmm0, xmm0
0x140034c41  xorps   xmm1, xmm1
0x140034c44  mov     [rbp+var_10], rax
0x140034c48  movups  [rbp+var_30], xmm0
0x140034c4c  mov     [rbp+var_38], rax
0x140034c50  mov     r14, r9
0x140034c53  movups  [rbp+var_20], xmm1
0x140034c57  mov     [rbp+P], rax
0x140034c5b  mov     r8, rdx
0x140034c5e  mov     rbx, rcx
0x140034c61  mov     rcx, cs:WPP_GLOBAL_Control
0x140034c68  lea     rax, WPP_GLOBAL_Control
0x140034c6f  cmp     rcx, rax
0x140034c72  jz      short loc_140034C97
0x140034c74  mov     eax, [rcx+2Ch]
0x140034c77  test    al, al
0x140034c79  jns     short loc_140034C97
0x140034c7b  cmp     byte ptr [rcx+29h], 4
0x140034c7f  jb      short loc_140034C97
0x140034c81  mov     rcx, [rcx+18h]
0x140034c85  mov     edx, 4Ch ; 'L'
0x140034c8a  mov     r9, rbx
0x140034c8d  mov     [rsp+70h+var_50], r8
0x140034c92  call    WPP_SF_qq
0x140034c97  mov     byte ptr [r14], 0
0x140034c9b  test    rbx, rbx
0x140034c9e  jz      loc_140034EA1
0x140034ca4  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x140034ca7  call    ?VmxpFindDiskDeviceByPdo@@YAPEAVVMX_DISK_DEVICE@@PEAU_DEVICE_OBJECT@@@Z; VmxpFindDiskDeviceByPdo(_DEVICE_OBJECT *)
0x140034cac  mov     rsi, rax
0x140034caf  test    rax, rax
0x140034cb2  jz      loc_140034EA1
0x140034cb8  cmp     dword ptr [rax+28h], 0
0x140034cbc  jnz     loc_140034EA1
0x140034cc2  cmp     byte ptr [rax+34h], 0
0x140034cc6  jz      short loc_140034CD1
0x140034cc8  mov     byte ptr [r14], 1
0x140034ccc  jmp     loc_140034EA1
0x140034cd1  lea     rdx, [rbp+var_20]; PVOID
0x140034cd5  mov     rcx, rsi; this
0x140034cd8  call    ?GetDriveGeometry@VMX_DISK_DEVICE@@QEAAJPEAU_DISK_GEOMETRY@@@Z; VMX_DISK_DEVICE::GetDriveGeometry(_DISK_GEOMETRY *)
0x140034cdd  test    eax, eax
0x140034cdf  js      loc_140034EA1
0x140034ce5  lea     rdx, [rbp+var_38]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140034ce9  mov     rcx, rsi; this
0x140034cec  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140034cf1  test    eax, eax
0x140034cf3  js      loc_140034EA1
0x140034cf9  lea     rdx, [rbp+var_30]; PVOID
0x140034cfd  mov     rcx, rsi; this
0x140034d00  call    ?GetDiskAttributes@VMX_DISK_DEVICE@@QEAAJPEAU_GET_DISK_ATTRIBUTES@@@Z; VMX_DISK_DEVICE::GetDiskAttributes(_GET_DISK_ATTRIBUTES *)
0x140034d05  test    eax, eax
0x140034d07  js      loc_140034EA1
0x140034d0d  mov     rdi, [rbp+var_38]
0x140034d11  mov     eax, [rdi]
0x140034d13  test    eax, eax
0x140034d15  jnz     loc_140034DB5
0x140034d1b  mov     r11d, [rdi+4]
0x140034d1f  xor     r10d, r10d
0x140034d22  xor     r8d, r8d
0x140034d25  xor     r9d, r9d
0x140034d28  test    r11d, r11d
0x140034d2b  jz      loc_140034EC5
0x140034d31  lea     rcx, [r9+r9*8]
0x140034d35  add     rcx, rcx
0x140034d38  movzx   edx, byte ptr [rdi+rcx*8+50h]
0x140034d3d  cmp     dl, 0Fh
0x140034d40  ja      short loc_140034D4C
0x140034d42  mov     ecx, 8021h; struct _DISK_GEOMETRY *
0x140034d47  bt      ecx, edx
0x140034d4a  jb      short loc_140034D8A
0x140034d4c  cmp     dl, 0A0h
0x140034d4f  jz      short loc_140034D81
0x140034d51  cmp     dl, 84h
0x140034d54  jz      short loc_140034D81
0x140034d56  cmp     dl, 27h ; '''
0x140034d59  jz      short loc_140034D81
0x140034d5b  cmp     dl, 12h
0x140034d5e  jz      short loc_140034D81
0x140034d60  lea     eax, [rdx+22h]
0x140034d63  cmp     al, 20h ; ' '
0x140034d65  ja      short loc_140034D77
0x140034d67  mov     rcx, 100000201h
0x140034d71  bt      rcx, rax
0x140034d75  jb      short loc_140034D81
0x140034d77  cmp     dl, 42h ; 'B'
0x140034d7a  jnz     short loc_140034D87
0x140034d7c  inc     r10d
0x140034d7f  jmp     short loc_140034D8A
0x140034d81  cmp     r9d, 4
0x140034d85  jb      short loc_140034D8A
0x140034d87  inc     r8d
0x140034d8a  inc     r9d
0x140034d8d  cmp     r9d, r11d
0x140034d90  jb      short loc_140034D31
0x140034d92  test    r10d, r10d
0x140034d95  jz      loc_140034EC5
0x140034d9b  test    r8d, r8d
0x140034d9e  jz      loc_140034EBB
0x140034da4  lea     r8, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140034da8  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140034dab  call    ?VmxpPrepareForDeleteDynamicPartitionsMbr@@YAJPEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU2@@Z; VmxpPrepareForDeleteDynamicPartitionsMbr(_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140034db0  jmp     loc_140034E68
0x140034db5  cmp     eax, 1
0x140034db8  jnz     loc_140034EBB
0x140034dbe  mov     r11d, [rdi+4]
0x140034dc2  xor     r8d, r8d
0x140034dc5  xor     r9d, r9d
0x140034dc8  xor     edx, edx
0x140034dca  xor     r10d, r10d
0x140034dcd  test    r11d, r11d
0x140034dd0  jz      loc_140034EC5
0x140034dd6  lea     rcx, [r10+r10*8]
0x140034dda  add     rcx, rcx; struct _DISK_GEOMETRY *
0x140034ddd  mov     rax, [rdi+rcx*8+50h]
0x140034de2  sub     rax, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data1
0x140034de9  jnz     short loc_140034DF7
0x140034deb  mov     rax, [rdi+rcx*8+58h]
0x140034df0  sub     rax, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data4
0x140034df7  test    rax, rax
0x140034dfa  jnz     short loc_140034E01
0x140034dfc  inc     r9d
0x140034dff  jmp     short loc_140034E46
0x140034e01  mov     rax, [rdi+rcx*8+50h]
0x140034e06  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data1
0x140034e0d  jnz     short loc_140034E1B
0x140034e0f  mov     rax, [rdi+rcx*8+58h]
0x140034e14  sub     rax, qword ptr cs:PARTITION_LDM_DATA_GUID.Data4
0x140034e1b  test    rax, rax
0x140034e1e  jnz     short loc_140034E25
0x140034e20  inc     r8d
0x140034e23  jmp     short loc_140034E46
0x140034e25  mov     rax, [rdi+rcx*8+50h]
0x140034e2a  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x140034e31  jnz     short loc_140034E3F
0x140034e33  mov     rax, [rdi+rcx*8+58h]
0x140034e38  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x140034e3f  test    rax, rax
0x140034e42  jnz     short loc_140034E46
0x140034e44  inc     edx
0x140034e46  inc     r10d
0x140034e49  cmp     r10d, r11d
0x140034e4c  jb      short loc_140034DD6
0x140034e4e  test    r8d, r8d
0x140034e51  jz      short loc_140034EC5
0x140034e53  test    r9d, r9d
0x140034e56  jz      short loc_140034E5C
0x140034e58  test    edx, edx
0x140034e5a  jz      short loc_140034EBB
0x140034e5c  lea     r8, [rbp+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140034e60  mov     rdx, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140034e63  call    ?VmxpPrepareForDeleteDynamicPartitionsGpt@@YAJPEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU2@@Z; VmxpPrepareForDeleteDynamicPartitionsGpt(_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140034e68  test    eax, eax
0x140034e6a  js      short loc_140034E90
0x140034e6c  mov     rdx, [rbp+P]; InputBuffer
0x140034e70  mov     rcx, rsi; this
0x140034e73  call    ?SetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::SetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140034e78  mov     rcx, [rbp+P]; P
0x140034e7c  xor     edx, edx; Tag
0x140034e7e  mov     ebx, eax
0x140034e80  call    cs:__imp_ExFreePoolWithTag
0x140034e87  nop     dword ptr [rax+rax+00h]
0x140034e8c  test    ebx, ebx
0x140034e8e  jns     short loc_140034EC5
0x140034e90  xor     edx, edx; Tag
0x140034e92  mov     rcx, rdi; P
0x140034e95  call    cs:__imp_ExFreePoolWithTag
0x140034e9c  nop     dword ptr [rax+rax+00h]
0x140034ea1  xor     eax, eax
0x140034ea3  mov     rcx, [rbp+var_8]
0x140034ea7  xor     rcx, rsp; StackCookie
0x140034eaa  call    __security_check_cookie
0x140034eaf  add     rsp, 70h
0x140034eb3  pop     r14
0x140034eb5  pop     rdi
0x140034eb6  pop     rsi
0x140034eb7  pop     rbx
0x140034eb8  pop     rbp
0x140034eb9  retn
0x140034ebb  test    byte ptr [rbp+var_30+8], 1
0x140034ebf  jz      short loc_140034E90
0x140034ec1  mov     byte ptr [rsi+36h], 0
0x140034ec5  xor     edx, edx; Tag
0x140034ec7  mov     rcx, rdi; P
0x140034eca  call    cs:__imp_ExFreePoolWithTag
0x140034ed1  nop     dword ptr [rax+rax+00h]
0x140034ed6  mov     rcx, rsi; this
0x140034ed9  call    ?Stop@VMX_DISK_DEVICE@@QEAAXXZ; VMX_DISK_DEVICE::Stop(void)
0x140034ede  jmp     loc_140034CC8
```
