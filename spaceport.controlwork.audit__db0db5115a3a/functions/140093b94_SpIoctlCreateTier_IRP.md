# SpIoctlCreateTier(_IRP *)

- ea: `0x140093b94`
- end: `0x140093f5f`
- name: `?SpIoctlCreateTier@@YAJPEAU_IRP@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400b57b0`

## callees

- `0x14001ab80`
- `0x14001d300`
- `0x140021df0`
- `0x14002ce90`
- `0x14002e43c`
- `0x14003401c`
- `0x1400345a0`
- `0x14003bfac`
- `0x14005c24c`
- `0x14005e7b0`
- `0x140068000`
- `0x140092340`
- `0x140093b94`
- `0x14009e3b8`
- `0x1400b55b0`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x140093cb6`
- `ntoskrnl!ExUuidCreate` at `0x140093cb6`

## pseudocode

```c
__int64 __fastcall SpIoctlCreateTier(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  unsigned int Options; // eax
  NTSTATUS v4; // ebx
  struct _IRP *MasterIrp; // rsi
  struct SP_POOL *PoolById; // rax
  struct SP_POOL *v7; // r15
  unsigned __int64 v8; // rcx
  SDB_OBJECT *v9; // rax
  SDB_OBJECT *v10; // rdi
  __int64 v11; // rdx
  unsigned int v12; // ecx
  struct _LIST_ENTRY **p_Blink; // r14
  __int64 v14; // r9
  GUID *v15; // r8
  GUID *v16; // rcx
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  ULONG DeviceType; // ecx
  const char *v20; // r9
  GUID v22; // [rsp+40h] [rbp-38h] BYREF
  __int128 v23; // [rsp+50h] [rbp-28h] BYREF
  GUID v24; // [rsp+60h] [rbp-18h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids);
  }
  SpAcquireResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options >= 0xAB0 )
  {
    MasterIrp = a1->AssociatedIrp.MasterIrp;
    if ( *(_DWORD *)&MasterIrp->Type != 2880 )
    {
      v4 = -1058602968;
      goto LABEL_40;
    }
    if ( Options != *(_DWORD *)(&MasterIrp->Size + 1) )
    {
      v4 = -1073741820;
      goto LABEL_40;
    }
    PoolById = SpFindPoolById((struct _GUID *)&MasterIrp->MdlAddress);
    v7 = PoolById;
    if ( !PoolById )
    {
      v4 = -1070071760;
      goto LABEL_40;
    }
    v4 = SpAccessCheckPool(PoolById, a1);
    if ( v4 < 0 )
      goto LABEL_40;
    if ( !*((_BYTE *)v7 + 65) )
    {
      v4 = -1070071728;
      goto LABEL_40;
    }
    v9 = (SDB_OBJECT *)SDB_TIER::operator new(v8);
    v10 = v9;
    if ( !v9 )
    {
      v4 = -1073741670;
      goto LABEL_40;
    }
    SDB_OBJECT::SDB_OBJECT(v9);
    *(_QWORD *)v10 = &SDB_TIER::`vftable';
    SDB_TIER::Initialize(v10);
    if ( MasterIrp->AssociatedIrp.MasterIrp == *(struct _IRP **)&GUID_NULL.Data1
      && MasterIrp->ThreadListEntry.Flink == *(struct _LIST_ENTRY **)GUID_NULL.Data4 )
    {
      v4 = ExUuidCreate((UUID *)v10 + 2);
      if ( v4 < 0 )
      {
LABEL_38:
        (**(void (__fastcall ***)(SDB_OBJECT *, __int64))v10)(v10, 1);
        goto LABEL_40;
      }
    }
    else
    {
      *((_OWORD *)v10 + 2) = *(_OWORD *)&MasterIrp->AssociatedIrp.MasterIrp;
    }
    v4 = SpStringCchCopyHelper(
           (unsigned __int16 *)&MasterIrp->IoStatus.Information,
           0x100u,
           (unsigned __int16 **)v10 + 6);
    if ( v4 >= 0 )
    {
      v4 = SpStringCchCopyHelper(
             (unsigned __int16 *)&MasterIrp[2].Tail.CompletionKey + 16,
             0x400u,
             (unsigned __int16 **)v10 + 7);
      if ( v4 >= 0 )
      {
        *((_DWORD *)v10 + 17) = MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
        *(_OWORD *)((char *)v10 + 72) = *((_OWORD *)&MasterIrp[12].Tail.CompletionKey + 2);
        *(_OWORD *)((char *)v10 + 88) = *((_OWORD *)&MasterIrp[12].Tail.CompletionKey + 3);
        *(_OWORD *)((char *)v10 + 104) = *(_OWORD *)((char *)&MasterIrp[12].Tail.CompletionKey + 76);
        *((_QWORD *)v10 + 15) = *(_QWORD *)(&MasterIrp[13].Size + 1);
        *((_DWORD *)v10 + 35) = MasterIrp[12].Tail.Overlay.PacketType;
        *((_DWORD *)v10 + 36) = *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 17);
        v11 = *((unsigned int *)&MasterIrp[12].Tail.CompletionKey + 18);
        v12 = v11 + 16 * *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 17);
        if ( v12 < (unsigned int)v11 )
        {
          v4 = -1073741675;
        }
        else if ( v12 <= *(_DWORD *)(&MasterIrp->Size + 1) )
        {
          v4 = SpIdsCopyHelper(
                 (struct _GUID *)((char *)MasterIrp + v11),
                 *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 17),
                 (struct _GUID **)v10 + 19);
          if ( v4 >= 0 )
          {
            p_Blink = &MasterIrp->ThreadListEntry.Blink;
            if ( MasterIrp->ThreadListEntry.Blink != *(struct _LIST_ENTRY **)&GUID_NULL.Data1
              || MasterIrp->IoStatus.Pointer != *(PVOID *)GUID_NULL.Data4 )
            {
              *((_QWORD *)v10 + 26) = MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
            }
            v4 = SP_POOL::ExecuteTransaction(v7, 28, v10);
            if ( v4 >= 0 )
            {
              if ( *p_Blink == *(struct _LIST_ENTRY **)&GUID_NULL.Data1
                && MasterIrp->IoStatus.Pointer == *(PVOID *)GUID_NULL.Data4 )
              {
                v14 = 1;
                v15 = &v22;
                v16 = &v24;
                v22 = GUID_NULL;
                v17 = *(_OWORD *)((char *)v7 + 108);
                v24 = GUID_SPACEPORT_POOL_NOTIFICATION;
                v23 = v17;
              }
              else
              {
                v14 = 10;
                v15 = &v24;
                v18 = *(_OWORD *)((char *)v7 + 108);
                v16 = &v22;
                v24 = *(GUID *)p_Blink;
                v23 = v18;
                v22 = GUID_SPACEPORT_SPACE_NOTIFICATION;
              }
              SpNotify(v16, &v23, v15, v14, 16, v7, 0);
            }
          }
        }
        else
        {
          v4 = -1073741811;
        }
      }
    }
    goto LABEL_38;
  }
  v4 = -1073741820;
LABEL_40:
  SpReleaseResourceExclusive((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  if ( v4 >= 0 || v4 == -2147483643 || v4 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v20 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v20 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      139,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v20,
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140093b94  push    rbp
0x140093b96  push    rbx
0x140093b97  push    rsi
0x140093b98  push    rdi
0x140093b99  push    r14
0x140093b9b  push    r15
0x140093b9d  mov     rbp, rsp
0x140093ba0  sub     rsp, 78h
0x140093ba4  mov     rdi, [rcx+0B8h]
0x140093bab  mov     rbx, rcx
0x140093bae  mov     rcx, cs:WPP_GLOBAL_Control
0x140093bb5  lea     rsi, WPP_GLOBAL_Control
0x140093bbc  cmp     rcx, rsi
0x140093bbf  jz      short loc_140093BE3
0x140093bc1  mov     eax, [rcx+2Ch]
0x140093bc4  test    al, 1
0x140093bc6  jz      short loc_140093BE3
0x140093bc8  cmp     byte ptr [rcx+29h], 3
0x140093bcc  jb      short loc_140093BE3
0x140093bce  mov     rcx, [rcx+18h]
0x140093bd2  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x140093bd9  mov     edx, 8Ah
0x140093bde  call    WPP_SF_
0x140093be3  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140093bea  add     rcx, 60h ; '`'; Resource
0x140093bee  call    ?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpAcquireResourceExclusive(_ERESOURCE *)
0x140093bf3  mov     eax, [rdi+10h]
0x140093bf6  cmp     eax, 0AB0h
0x140093bfb  jnb     short loc_140093C07
0x140093bfd  mov     ebx, 0C0000004h
0x140093c02  jmp     loc_140093EB9
0x140093c07  mov     rsi, [rbx+18h]
0x140093c0b  cmp     dword ptr [rsi], 0B40h
0x140093c11  jz      short loc_140093C1D
0x140093c13  mov     ebx, 0C0E70028h
0x140093c18  jmp     loc_140093EB2
0x140093c1d  cmp     eax, [rsi+4]
0x140093c20  jz      short loc_140093C2C
0x140093c22  mov     ebx, 0C0000004h
0x140093c27  jmp     loc_140093EB2
0x140093c2c  lea     rcx, [rsi+8]; struct _GUID *
0x140093c30  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x140093c35  mov     r15, rax
0x140093c38  test    rax, rax
0x140093c3b  jnz     short loc_140093C47
0x140093c3d  mov     ebx, 0C0380030h
0x140093c42  jmp     loc_140093EB2
0x140093c47  mov     rdx, rbx; struct _IRP *
0x140093c4a  mov     rcx, r15; struct SP_POOL *
0x140093c4d  call    ?SpAccessCheckPool@@YAJPEAVSP_POOL@@PEAU_IRP@@@Z; SpAccessCheckPool(SP_POOL *,_IRP *)
0x140093c52  mov     ebx, eax
0x140093c54  test    eax, eax
0x140093c56  js      loc_140093EB2
0x140093c5c  cmp     byte ptr [r15+41h], 0
0x140093c61  jnz     short loc_140093C6D
0x140093c63  mov     ebx, 0C0380050h
0x140093c68  jmp     loc_140093EB2
0x140093c6d  call    ??2SDB_TIER@@SAPEAX_K@Z; SDB_TIER::operator new(unsigned __int64)
0x140093c72  mov     rdi, rax
0x140093c75  test    rax, rax
0x140093c78  jz      loc_140093EAD
0x140093c7e  mov     rcx, rax; this
0x140093c81  call    ??0SDB_OBJECT@@QEAA@XZ; SDB_OBJECT::SDB_OBJECT(void)
0x140093c86  lea     rcx, ??_7SDB_TIER@@6B@; const SDB_TIER::`vftable'
0x140093c8d  mov     [rdi], rcx
0x140093c90  mov     rcx, rdi; this
0x140093c93  call    ?Initialize@SDB_TIER@@UEAAJXZ; SDB_TIER::Initialize(void)
0x140093c98  mov     rax, [rsi+18h]
0x140093c9c  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x140093ca3  jnz     short loc_140093CCD
0x140093ca5  mov     rax, [rsi+20h]
0x140093ca9  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x140093cb0  jnz     short loc_140093CCD
0x140093cb2  lea     rcx, [rdi+20h]; Uuid
0x140093cb6  call    cs:__imp_ExUuidCreate
0x140093cbd  nop     dword ptr [rax+rax+00h]
0x140093cc2  mov     ebx, eax
0x140093cc4  test    eax, eax
0x140093cc6  jns     short loc_140093CD6
0x140093cc8  jmp     loc_140093E98
0x140093ccd  movups  xmm0, xmmword ptr [rsi+18h]
0x140093cd1  movdqu  xmmword ptr [rdi+20h], xmm0
0x140093cd6  lea     r8, [rdi+30h]; unsigned __int16 **
0x140093cda  mov     edx, 100h; unsigned int
0x140093cdf  lea     rcx, [rsi+38h]; unsigned __int16 *
0x140093ce3  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x140093ce8  mov     ebx, eax
0x140093cea  test    eax, eax
0x140093cec  js      loc_140093E98
0x140093cf2  lea     r8, [rdi+38h]; unsigned __int16 **
0x140093cf6  mov     edx, 400h; unsigned int
0x140093cfb  lea     rcx, [rsi+238h]; unsigned __int16 *
0x140093d02  call    ?SpStringCchCopyHelper@@YAJPEAGKPEAPEAG@Z; SpStringCchCopyHelper(ushort *,ulong,ushort * *)
0x140093d07  mov     ebx, eax
0x140093d09  test    eax, eax
0x140093d0b  js      loc_140093E98
0x140093d11  mov     eax, [rsi+0A38h]
0x140093d17  mov     [rdi+44h], eax
0x140093d1a  movups  xmm0, xmmword ptr [rsi+0A58h]
0x140093d21  movups  xmmword ptr [rdi+48h], xmm0
0x140093d25  movups  xmm1, xmmword ptr [rsi+0A68h]
0x140093d2c  movups  xmmword ptr [rdi+58h], xmm1
0x140093d30  movups  xmm0, xmmword ptr [rsi+0A84h]
0x140093d37  movups  xmmword ptr [rdi+68h], xmm0
0x140093d3b  movsd   xmm1, qword ptr [rsi+0A94h]
0x140093d43  movsd   qword ptr [rdi+78h], xmm1
0x140093d48  mov     eax, [rsi+0A78h]
0x140093d4e  mov     [rdi+8Ch], eax
0x140093d54  mov     eax, [rsi+0A7Ch]
0x140093d5a  mov     [rdi+90h], eax
0x140093d60  mov     edx, [rsi+0A80h]
0x140093d66  mov     r9d, [rsi+0A7Ch]
0x140093d6d  mov     ecx, r9d
0x140093d70  shl     ecx, 4
0x140093d73  add     ecx, edx
0x140093d75  cmp     ecx, edx
0x140093d77  jb      loc_140093E93
0x140093d7d  cmp     ecx, [rsi+4]
0x140093d80  jbe     short loc_140093D8C
0x140093d82  mov     ebx, 0C000000Dh
0x140093d87  jmp     loc_140093E98
0x140093d8c  lea     rcx, [rsi+rdx]; Src
0x140093d90  mov     edx, r9d; unsigned int
0x140093d93  lea     r8, [rdi+98h]; struct _GUID **
0x140093d9a  call    ?SpIdsCopyHelper@@YAJPEAU_GUID@@KPEAPEAU1@@Z; SpIdsCopyHelper(_GUID *,ulong,_GUID * *)
0x140093d9f  mov     ebx, eax
0x140093da1  test    eax, eax
0x140093da3  js      loc_140093E98
0x140093da9  lea     r14, [rsi+28h]
0x140093dad  mov     rax, [r14]
0x140093db0  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x140093db7  jnz     short loc_140093DC6
0x140093db9  mov     rax, [r14+8]
0x140093dbd  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x140093dc4  jz      short loc_140093DD4
0x140093dc6  mov     rax, [rsi+0A40h]
0x140093dcd  mov     [rdi+0D0h], rax
0x140093dd4  mov     r9, r14
0x140093dd7  mov     [rsp+78h+var_58], 0
0x140093de0  mov     r8, rdi
0x140093de3  mov     edx, 1Ch
0x140093de8  mov     rcx, r15
0x140093deb  call    ?ExecuteTransaction@SP_POOL@@QEAAJW4TRANSACTION_CODE@@PEAX11@Z; SP_POOL::ExecuteTransaction(TRANSACTION_CODE,void *,void *,void *)
0x140093df0  mov     ebx, eax
0x140093df2  test    eax, eax
0x140093df4  js      loc_140093E98
0x140093dfa  mov     rax, [r14]
0x140093dfd  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x140093e04  jnz     short loc_140093E64
0x140093e06  mov     rax, [r14+8]
0x140093e0a  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x140093e11  jnz     short loc_140093E64
0x140093e13  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140093e1a  mov     r9d, 1
0x140093e20  lea     r8, [rbp+var_38]
0x140093e24  movups  xmm1, xmmword ptr cs:GUID_SPACEPORT_POOL_NOTIFICATION.Data1
0x140093e2b  lea     rcx, [rbp+var_18]
0x140093e2f  movdqu  [rbp+var_38], xmm0
0x140093e34  movups  xmm0, xmmword ptr [r15+6Ch]
0x140093e39  movdqu  [rbp+var_18], xmm1
0x140093e3e  movdqu  [rbp+var_28], xmm0
0x140093e43  mov     [rsp+78h+var_48], 0
0x140093e4c  lea     rdx, [rbp+var_28]
0x140093e50  mov     [rsp+78h+var_50], r15
0x140093e55  mov     dword ptr [rsp+78h+var_58], 10h
0x140093e5d  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x140093e62  jmp     short loc_140093E98
0x140093e64  movups  xmm0, xmmword ptr [r14]
0x140093e68  mov     r9d, 0Ah
0x140093e6e  lea     r8, [rbp+var_18]
0x140093e72  movups  xmm1, xmmword ptr [r15+6Ch]
0x140093e77  lea     rcx, [rbp+var_38]
0x140093e7b  movdqu  [rbp+var_18], xmm0
0x140093e80  movups  xmm0, xmmword ptr cs:GUID_SPACEPORT_SPACE_NOTIFICATION.Data1
0x140093e87  movdqu  [rbp+var_28], xmm1
0x140093e8c  movdqu  [rbp+var_38], xmm0
0x140093e91  jmp     short loc_140093E43
0x140093e93  mov     ebx, 0C0000095h
0x140093e98  mov     rax, [rdi]
0x140093e9b  mov     edx, 1
0x140093ea0  mov     rcx, rdi
0x140093ea3  mov     rax, [rax]
0x140093ea6  call    _guard_dispatch_icall
0x140093eab  jmp     short loc_140093EB2
0x140093ead  mov     ebx, 0C000009Ah
0x140093eb2  lea     rsi, WPP_GLOBAL_Control
0x140093eb9  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140093ec0  add     rcx, 60h ; '`'; Resource
0x140093ec4  call    ?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceExclusive(_ERESOURCE *)
0x140093ec9  test    ebx, ebx
0x140093ecb  jns     short loc_140093EFC
0x140093ecd  cmp     ebx, 80000005h
0x140093ed3  jz      short loc_140093EFC
0x140093ed5  cmp     ebx, 0C0000023h
0x140093edb  jz      short loc_140093EFC
0x140093edd  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140093ee3  cmp     ecx, 1
0x140093ee6  jz      short loc_140093EF3
0x140093ee8  mov     ecx, 1
0x140093eed  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140093ef3  lea     r9, aError; "Error"
0x140093efa  jmp     short loc_140093F19
0x140093efc  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x140093f02  cmp     ecx, 3
0x140093f05  jz      short loc_140093F12
0x140093f07  mov     ecx, 3
0x140093f0c  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x140093f12  lea     r9, aExit; "Exit "
0x140093f19  mov     r10, cs:WPP_GLOBAL_Control
0x140093f20  cmp     r10, rsi
0x140093f23  jz      short loc_140093F4F
0x140093f25  mov     eax, [r10+2Ch]
0x140093f29  test    al, 1
0x140093f2b  jz      short loc_140093F4F
0x140093f2d  movzx   eax, byte ptr [r10+29h]
0x140093f32  cmp     eax, ecx
0x140093f34  jb      short loc_140093F4F
0x140093f36  mov     rcx, [r10+18h]
0x140093f3a  lea     r8, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids
0x140093f41  mov     edx, 8Bh
0x140093f46  mov     dword ptr [rsp+78h+var_58], ebx
0x140093f4a  call    WPP_SF_sd
0x140093f4f  mov     eax, ebx
0x140093f51  add     rsp, 78h
0x140093f55  pop     r15
0x140093f57  pop     r14
0x140093f59  pop     rdi
0x140093f5a  pop     rsi
0x140093f5b  pop     rbx
0x140093f5c  pop     rbp
0x140093f5d  retn
```
