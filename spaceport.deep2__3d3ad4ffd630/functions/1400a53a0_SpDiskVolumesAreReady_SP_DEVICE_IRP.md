# SpDiskVolumesAreReady(SP_DEVICE *,_IRP *)

- ea: `0x1400a53a0`
- end: `0x1400a563d`
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
- `0x14003bfac`
- `0x140042fc8`
- `0x140067fc0`
- `0x1400684c0`
- `0x1400a53a0`
- `0x1400b5720`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400a54ae`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a54ae`
- `ntoskrnl!IofCompleteRequest` at `0x1400a549b`
- `ntoskrnl!IofCompleteRequest` at `0x1400a549b`

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
0x1400a53a0  mov     [rsp+arg_10], rbx
0x1400a53a5  mov     [rsp+arg_18], rsi
0x1400a53aa  push    rdi
0x1400a53ab  sub     rsp, 100h
0x1400a53b2  mov     rax, cs:__security_cookie
0x1400a53b9  xor     rax, rsp
0x1400a53bc  mov     [rsp+108h+var_18], rax
0x1400a53c4  mov     rdi, rdx
0x1400a53c7  mov     [rsp+108h+var_98], 3
0x1400a53cf  xor     edx, edx; Val
0x1400a53d1  mov     rbx, rcx
0x1400a53d4  lea     rcx, [rsp+108h+var_94]; void *
0x1400a53d9  lea     r8d, [rdx+70h]; Size
0x1400a53dd  call    memset
0x1400a53e2  mov     rax, [rdi+0B8h]
0x1400a53e9  cmp     dword ptr [rax+10h], 4
0x1400a53ed  jnb     short loc_1400A5417
0x1400a53ef  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a53f5  mov     esi, 1
0x1400a53fa  mov     edi, 0C0000004h
0x1400a53ff  cmp     ecx, esi
0x1400a5401  jz      short loc_1400A540B
0x1400a5403  mov     ecx, esi
0x1400a5405  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a540b  lea     r9, aError; "Error"
0x1400a5412  jmp     loc_1400A55D7
0x1400a5417  mov     rcx, rbx; this
0x1400a541a  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x1400a541f  cmp     dword ptr [rbx+0C40h], 0FFFFFFFFh
0x1400a5426  mov     esi, 1
0x1400a542b  jnz     loc_1400A5527
0x1400a5431  mov     rax, [rdi+18h]
0x1400a5435  xor     dl, dl
0x1400a5437  lea     rdi, [rbx+0C10h]
0x1400a543e  mov     ecx, [rax]
0x1400a5440  mov     [rbx+0C40h], ecx
0x1400a5446  mov     rcx, [rdi]
0x1400a5449  cmp     rcx, rdi
0x1400a544c  jz      short loc_1400A546D
0x1400a544e  xor     eax, eax
0x1400a5450  movzx   edx, dl
0x1400a5453  xchg    rax, [rcx-40h]
0x1400a5457  mov     rcx, [rcx]
0x1400a545a  test    rax, rax
0x1400a545d  cmovz   edx, esi
0x1400a5460  cmp     rcx, rdi
0x1400a5463  jnz     short loc_1400A544E
0x1400a5465  test    dl, dl
0x1400a5467  jnz     loc_1400A5527
0x1400a546d  mov     rcx, [rdi]
0x1400a5470  cmp     rcx, rdi
0x1400a5473  jz      short loc_1400A54C3
0x1400a5475  cmp     [rcx+8], rdi
0x1400a5479  jnz     short loc_1400A54BC
0x1400a547b  mov     rax, [rcx]
0x1400a547e  cmp     [rax+8], rcx
0x1400a5482  jnz     short loc_1400A54BC
0x1400a5484  mov     [rdi], rax
0x1400a5487  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1400a548e  mov     [rax+8], rdi
0x1400a5492  xor     edx, edx; PriorityBoost
0x1400a5494  mov     dword ptr [rcx+30h], 0
0x1400a549b  call    cs:__imp_IofCompleteRequest
0x1400a54a2  nop     dword ptr [rax+rax+00h]
0x1400a54a7  mov     rcx, [rbx+0A0h]; Object
0x1400a54ae  call    cs:__imp_ObfDereferenceObject
0x1400a54b5  nop     dword ptr [rax+rax+00h]
0x1400a54ba  jmp     short loc_1400A546D
0x1400a54bc  mov     ecx, 3
0x1400a54c1  int     29h; Win8: RtlFailFast(ecx)
0x1400a54c3  mov     rax, [rbx+0C98h]
0x1400a54ca  test    rax, rax
0x1400a54cd  jz      short loc_1400A5527
0x1400a54cf  movups  xmm0, xmmword ptr [rax+18h]
0x1400a54d3  mov     [rsp+108h+var_D8], 0
0x1400a54dc  mov     r9d, 0Ah
0x1400a54e2  movups  xmm1, xmmword ptr [rax+8]
0x1400a54e6  mov     rax, [rax+488h]
0x1400a54ed  lea     r8, [rsp+108h+var_C8]
0x1400a54f2  movdqu  [rsp+108h+var_C8], xmm0
0x1400a54f8  mov     [rsp+108h+var_E0], rax
0x1400a54fd  lea     rdx, [rsp+108h+var_B8]
0x1400a5502  movups  xmm0, xmmword ptr cs:GUID_SPACEPORT_SPACE_NOTIFICATION.Data1
0x1400a5509  lea     rcx, [rsp+108h+var_A8]
0x1400a550e  mov     dword ptr [rsp+108h+var_E8], 4
0x1400a5516  movdqu  [rsp+108h+var_B8], xmm1
0x1400a551c  movdqu  [rsp+108h+var_A8], xmm0
0x1400a5522  call    ?SpNotify@@YAXU_GUID@@00W4_SP_NOTIFICATION_TYPE@@KPEAVSP_POOL@@PEAX@Z; SpNotify(_GUID,_GUID,_GUID,_SP_NOTIFICATION_TYPE,ulong,SP_POOL *,void *)
0x1400a5527  mov     rcx, [rbx+0C98h]; this
0x1400a552e  xor     edi, edi
0x1400a5530  test    rcx, rcx
0x1400a5533  jz      short loc_1400A557A
0x1400a5535  lea     rdx, [rsp+108h+var_98]; struct _SIO_HEALTH_CONTEXT *
0x1400a553a  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *)
0x1400a553f  mov     rcx, [rbx+0C98h]; this
0x1400a5546  call    ?IsSynchronizing@SIO_SPACE@@QEAAEXZ; SIO_SPACE::IsSynchronizing(void)
0x1400a554b  test    al, al
0x1400a554d  jz      short loc_1400A557A
0x1400a554f  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400a5556  xor     r9d, r9d; unsigned __int8
0x1400a5559  xor     r8d, r8d; unsigned int
0x1400a555c  xor     edx, edx; struct _LIST_ENTRY *
0x1400a555e  lock bts dword ptr [rax+648h], 0
0x1400a5567  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400a556e  add     rcx, 578h; Context
0x1400a5575  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x1400a557a  mov     rax, [rbx+0C98h]
0x1400a5581  test    rax, rax
0x1400a5584  jz      short loc_1400A558F
0x1400a5586  mov     r9, [rax+4D8h]
0x1400a558d  jmp     short loc_1400A5593
0x1400a558f  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400a5593  mov     r8, [rbx+0CD0h]
0x1400a559a  lea     rax, [rsp+108h+var_98]
0x1400a559f  lea     rdx, [rbx+18h]
0x1400a55a3  mov     [rsp+108h+var_E8], rax
0x1400a55a8  mov     ecx, 3FDh; unsigned int
0x1400a55ad  call    ?EventWrite@SC_ENV@@SAXKZZ; SC_ENV::EventWrite(ulong,...)
0x1400a55b2  mov     rcx, rbx; this
0x1400a55b5  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x1400a55ba  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a55c0  cmp     ecx, 3
0x1400a55c3  jz      short loc_1400A55D0
0x1400a55c5  mov     ecx, 3
0x1400a55ca  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a55d0  lea     r9, aExit; "Exit "
0x1400a55d7  mov     r10, cs:WPP_GLOBAL_Control
0x1400a55de  lea     rax, WPP_GLOBAL_Control
0x1400a55e5  cmp     r10, rax
0x1400a55e8  jz      short loc_1400A5615
0x1400a55ea  mov     eax, [r10+2Ch]
0x1400a55ee  test    sil, al
0x1400a55f1  jz      short loc_1400A5615
0x1400a55f3  movzx   edx, byte ptr [r10+29h]
0x1400a55f8  cmp     edx, ecx
0x1400a55fa  jb      short loc_1400A5615
0x1400a55fc  mov     rcx, [r10+18h]
0x1400a5600  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400a5607  mov     edx, 0Bh
0x1400a560c  mov     dword ptr [rsp+108h+var_E8], edi
0x1400a5610  call    WPP_SF_sd
0x1400a5615  mov     eax, edi
0x1400a5617  mov     rcx, [rsp+108h+var_18]
0x1400a561f  xor     rcx, rsp; StackCookie
0x1400a5622  call    __security_check_cookie
0x1400a5627  lea     r11, [rsp+108h+var_8]
0x1400a562f  mov     rbx, [r11+20h]
0x1400a5633  mov     rsi, [r11+28h]
0x1400a5637  mov     rsp, r11
0x1400a563a  pop     rdi
0x1400a563b  retn
```
