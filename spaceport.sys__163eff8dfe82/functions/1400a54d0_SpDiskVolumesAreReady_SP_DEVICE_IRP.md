# SpDiskVolumesAreReady(SP_DEVICE *,_IRP *)

- ea: `0x1400a54d0`
- end: `0x1400a576d`
- name: `?SpDiskVolumesAreReady@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(struct SP_DEVICE *this, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001ad10`

## callees

- `0x1400044d0`
- `0x140011970`
- `0x1400216f0`
- `0x140021a90`
- `0x14002ce90`
- `0x14003c06c`
- `0x140043088`
- `0x140068110`
- `0x140068600`
- `0x1400a54d0`
- `0x1400b58c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400a55de`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a55de`
- `ntoskrnl!IofCompleteRequest` at `0x1400a55cb`
- `ntoskrnl!IofCompleteRequest` at `0x1400a55cb`

## pseudocode

```c
__int64 __fastcall SpDiskVolumesAreReady(struct SP_DEVICE *this, struct _IRP *a2)
{
  ULONG DeviceType; // ecx
  unsigned int v5; // edi
  const char *v6; // r9
  struct _IRP *MasterIrp; // rax
  char v8; // dl
  struct SP_DEVICE *v9; // rdi
  struct SP_DEVICE *v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  IRP *v14; // rcx
  __int64 v15; // rax
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int64 v18; // rax
  SP_SPACE *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r9
  __int64 v23; // [rsp+28h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D8h]
  __int64 v25; // [rsp+38h] [rbp-D0h]
  __int128 v26; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+50h] [rbp-B8h] BYREF
  GUID v28; // [rsp+60h] [rbp-A8h] BYREF
  int v29[32]; // [rsp+70h] [rbp-98h] BYREF

  v29[0] = 3;
  memset(&v29[1], 0, 0x70u);
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options >= 4 )
  {
    SP_DEVICE::AcquireMutex(this);
    if ( *((_DWORD *)this + 784) == -1 )
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      v8 = 0;
      v9 = (struct SP_DEVICE *)((char *)this + 3088);
      *((_DWORD *)this + 784) = *(_DWORD *)&MasterIrp->Type;
      v10 = (struct SP_DEVICE *)*((_QWORD *)this + 386);
      if ( v10 == (struct SP_DEVICE *)((char *)this + 3088) )
        goto LABEL_34;
      do
      {
        v11 = _InterlockedExchange64((volatile __int64 *)v10 - 8, 0);
        v10 = *(struct SP_DEVICE **)v10;
        if ( !v11 )
          v8 = 1;
      }
      while ( v10 != v9 );
      if ( !v8 )
      {
LABEL_34:
        while ( 1 )
        {
          v12 = *(_QWORD **)v9;
          if ( *(struct SP_DEVICE **)v9 == v9 )
            break;
          if ( (struct SP_DEVICE *)v12[1] != v9 || (v13 = (_QWORD *)*v12, *(_QWORD **)(*v12 + 8LL) != v12) )
            __fastfail(3u);
          *(_QWORD *)v9 = v13;
          v14 = (IRP *)(v12 - 21);
          v13[1] = v9;
          v14->IoStatus.Status = 0;
          IofCompleteRequest(v14, 0);
          ObfDereferenceObject(*((PVOID *)this + 20));
        }
        v15 = *((_QWORD *)this + 403);
        if ( v15 )
        {
          v16 = *(_OWORD *)(v15 + 24);
          v17 = *(_OWORD *)(v15 + 8);
          v18 = *(_QWORD *)(v15 + 1160);
          v26 = v16;
          v27 = v17;
          v28 = GUID_SPACEPORT_SPACE_NOTIFICATION;
          SpNotify(&v28, &v27, &v26, 10, 4, v18, 0);
        }
      }
    }
    v19 = (SP_SPACE *)*((_QWORD *)this + 403);
    v5 = 0;
    if ( v19 )
    {
      SP_SPACE::GetHealth(v19, (struct _SIO_HEALTH_CONTEXT *)v29);
      if ( SIO_SPACE::IsSynchronizing(*((SIO_SPACE **)this + 403)) )
      {
        _interlockedbittestandset((volatile signed __int32 *)WPP_MAIN_CB.DeviceExtension + 402, 0);
        SP_WORKITEM::Insert((char *)WPP_MAIN_CB.DeviceExtension + 1400, 0, 0, 0);
      }
    }
    v20 = *((_QWORD *)this + 403);
    if ( v20 )
      v21 = *(_QWORD *)(v20 + 1240);
    else
      v21 = -1;
    SC_ENV::EventWrite(
      0x3FDu,
      (__int64)this + 24,
      *((_QWORD *)this + 410),
      v21,
      v29,
      v23,
      v24,
      v25,
      v26,
      SBYTE8(v26),
      v27,
      SBYTE8(v27));
    SP_DEVICE::ReleaseMutex(this);
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v6 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    v5 = -1073741820;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v6 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v6,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1400a54d0  mov     [rsp+arg_10], rbx
0x1400a54d5  mov     [rsp+arg_18], rsi
0x1400a54da  push    rdi
0x1400a54db  sub     rsp, 100h
0x1400a54e2  mov     rax, cs:__security_cookie
0x1400a54e9  xor     rax, rsp
0x1400a54ec  mov     [rsp+108h+var_18], rax
0x1400a54f4  mov     rdi, rdx
0x1400a54f7  mov     [rsp+108h+var_98], 3
0x1400a54ff  xor     edx, edx; Val
0x1400a5501  mov     rbx, rcx
0x1400a5504  lea     rcx, [rsp+108h+var_94]; void *
0x1400a5509  lea     r8d, [rdx+70h]; Size
0x1400a550d  call    memset
0x1400a5512  mov     rax, [rdi+0B8h]
0x1400a5519  cmp     dword ptr [rax+10h], 4
0x1400a551d  jnb     short loc_1400A5547
0x1400a551f  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a5525  mov     esi, 1
0x1400a552a  mov     edi, 0C0000004h
0x1400a552f  cmp     ecx, esi
0x1400a5531  jz      short loc_1400A553B
0x1400a5533  mov     ecx, esi
0x1400a5535  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a553b  lea     r9, aError; "Error"
0x1400a5542  jmp     loc_1400A5707
0x1400a5547  mov     rcx, rbx; this
0x1400a554a  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x1400a554f  cmp     dword ptr [rbx+0C40h], 0FFFFFFFFh
0x1400a5556  mov     esi, 1
0x1400a555b  jnz     loc_1400A5657
0x1400a5561  mov     rax, [rdi+18h]
0x1400a5565  xor     dl, dl
0x1400a5567  lea     rdi, [rbx+0C10h]
0x1400a556e  mov     ecx, [rax]
0x1400a5570  mov     [rbx+0C40h], ecx
0x1400a5576  mov     rcx, [rdi]
0x1400a5579  cmp     rcx, rdi
0x1400a557c  jz      short loc_1400A559D
0x1400a557e  xor     eax, eax
0x1400a5580  movzx   edx, dl
0x1400a5583  xchg    rax, [rcx-40h]
0x1400a5587  mov     rcx, [rcx]
0x1400a558a  test    rax, rax
0x1400a558d  cmovz   edx, esi
0x1400a5590  cmp     rcx, rdi
0x1400a5593  jnz     short loc_1400A557E
0x1400a5595  test    dl, dl
0x1400a5597  jnz     loc_1400A5657
0x1400a559d  mov     rcx, [rdi]
0x1400a55a0  cmp     rcx, rdi
0x1400a55a3  jz      short loc_1400A55F3
0x1400a55a5  cmp     [rcx+8], rdi
0x1400a55a9  jnz     short loc_1400A55EC
0x1400a55ab  mov     rax, [rcx]
0x1400a55ae  cmp     [rax+8], rcx
0x1400a55b2  jnz     short loc_1400A55EC
0x1400a55b4  mov     [rdi], rax
0x1400a55b7  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1400a55be  mov     [rax+8], rdi
0x1400a55c2  xor     edx, edx; PriorityBoost
0x1400a55c4  mov     dword ptr [rcx+30h], 0
0x1400a55cb  call    cs:__imp_IofCompleteRequest
0x1400a55d2  nop     dword ptr [rax+rax+00h]
0x1400a55d7  mov     rcx, [rbx+0A0h]; Object
0x1400a55de  call    cs:__imp_ObfDereferenceObject
0x1400a55e5  nop     dword ptr [rax+rax+00h]
0x1400a55ea  jmp     short loc_1400A559D
0x1400a55ec  mov     ecx, 3
0x1400a55f1  int     29h; Win8: RtlFailFast(ecx)
0x1400a55f3  mov     rax, [rbx+0C98h]
0x1400a55fa  test    rax, rax
0x1400a55fd  jz      short loc_1400A5657
0x1400a55ff  movups  xmm0, xmmword ptr [rax+18h]
0x1400a5603  mov     [rsp+108h+var_D8], 0
0x1400a560c  mov     r9d, 0Ah
0x1400a5612  movups  xmm1, xmmword ptr [rax+8]
0x1400a5616  mov     rax, [rax+488h]
0x1400a561d  lea     r8, [rsp+108h+var_C8]
0x1400a5622  movdqu  [rsp+108h+var_C8], xmm0
0x1400a5628  mov     [rsp+108h+var_E0], rax
0x1400a562d  lea     rdx, [rsp+108h+var_B8]
0x1400a5632  movups  xmm0, xmmword ptr cs:GUID_SPACEPORT_SPACE_NOTIFICATION.Data1
0x1400a5639  lea     rcx, [rsp+108h+var_A8]
0x1400a563e  mov     dword ptr [rsp+108h+var_E8], 4
0x1400a5646  movdqu  [rsp+108h+var_B8], xmm1
0x1400a564c  movdqu  [rsp+108h+var_A8], xmm0
0x1400a5652  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x1400a5657  mov     rcx, [rbx+0C98h]; this
0x1400a565e  xor     edi, edi
0x1400a5660  test    rcx, rcx
0x1400a5663  jz      short loc_1400A56AA
0x1400a5665  lea     rdx, [rsp+108h+var_98]; struct _SIO_HEALTH_CONTEXT *
0x1400a566a  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *)
0x1400a566f  mov     rcx, [rbx+0C98h]; this
0x1400a5676  call    ?IsSynchronizing@SIO_SPACE@@QEAAEXZ; SIO_SPACE::IsSynchronizing(void)
0x1400a567b  test    al, al
0x1400a567d  jz      short loc_1400A56AA
0x1400a567f  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400a5686  xor     r9d, r9d; unsigned __int8
0x1400a5689  xor     r8d, r8d; unsigned int
0x1400a568c  xor     edx, edx; struct _LIST_ENTRY *
0x1400a568e  lock bts dword ptr [rax+648h], 0
0x1400a5697  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a569e  add     rcx, 578h; Context
0x1400a56a5  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400a56aa  mov     rax, [rbx+0C98h]
0x1400a56b1  test    rax, rax
0x1400a56b4  jz      short loc_1400A56BF
0x1400a56b6  mov     r9, [rax+4D8h]
0x1400a56bd  jmp     short loc_1400A56C3
0x1400a56bf  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400a56c3  mov     r8, [rbx+0CD0h]
0x1400a56ca  lea     rax, [rsp+108h+var_98]
0x1400a56cf  lea     rdx, [rbx+18h]
0x1400a56d3  mov     [rsp+108h+var_E8], rax
0x1400a56d8  mov     ecx, 3FDh; unsigned int
0x1400a56dd  call    ?EventWrite@SC_ENV@@SAXKZZ; SC_ENV::EventWrite(ulong,...)
0x1400a56e2  mov     rcx, rbx; this
0x1400a56e5  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x1400a56ea  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a56f0  cmp     ecx, 3
0x1400a56f3  jz      short loc_1400A5700
0x1400a56f5  mov     ecx, 3
0x1400a56fa  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a5700  lea     r9, aExit; "Exit "
0x1400a5707  mov     r10, cs:WPP_GLOBAL_Control
0x1400a570e  lea     rax, WPP_GLOBAL_Control
0x1400a5715  cmp     r10, rax
0x1400a5718  jz      short loc_1400A5745
0x1400a571a  mov     eax, [r10+2Ch]
0x1400a571e  test    sil, al
0x1400a5721  jz      short loc_1400A5745
0x1400a5723  movzx   edx, byte ptr [r10+29h]
0x1400a5728  cmp     edx, ecx
0x1400a572a  jb      short loc_1400A5745
0x1400a572c  mov     rcx, [r10+18h]
0x1400a5730  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400a5737  mov     edx, 0Bh
0x1400a573c  mov     dword ptr [rsp+108h+var_E8], edi
0x1400a5740  call    WPP_SF_sd
0x1400a5745  mov     eax, edi
0x1400a5747  mov     rcx, [rsp+108h+var_18]
0x1400a574f  xor     rcx, rsp; StackCookie
0x1400a5752  call    __security_check_cookie
0x1400a5757  lea     r11, [rsp+108h+var_8]
0x1400a575f  mov     rbx, [r11+20h]
0x1400a5763  mov     rsi, [r11+28h]
0x1400a5767  mov     rsp, r11
0x1400a576a  pop     rdi
0x1400a576b  retn
```
