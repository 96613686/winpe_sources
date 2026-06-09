# VMX_PACK::RemoveVolumesTransaction(VMX_RECORD *)

- ea: `0x140055f34`
- end: `0x1400561f5`
- name: `?RemoveVolumesTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z`
- size: `705`
- prototype: `int(VMX_PACK *__hidden this, struct VMX_RECORD *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x14002de54`
- `0x14002e230`
- `0x14002eb3c`
- `0x1400358f4`

## callees

- `0x1400099d8`
- `0x14001be80`
- `0x140033df4`
- `0x14004037c`
- `0x140050afc`
- `0x140055f34`
- `0x14005d644`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400561b4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400561b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400561cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400561cb`
- `ntoskrnl!ObfReferenceObject` at `0x140056113`
- `ntoskrnl!ObfReferenceObject` at `0x140056113`

## pseudocode

```c
__int64 __fastcall VMX_PACK::RemoveVolumesTransaction(VMX_PACK *this, struct VMX_RECORD *a2)
{
  struct _PARTMGR_PARTITIONS *v3; // rbx
  int v4; // eax
  unsigned int v5; // edi
  __int64 v7; // rbp
  __int64 v8; // r12
  unsigned int *v9; // r15
  int v10; // eax
  unsigned int v11; // ebx
  struct _DEVICE_OBJECT *v12; // r14
  NTSTATUS v13; // esi
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  __int64 v16; // r13
  __int64 v17; // rcx
  __int64 v18; // r12
  __int64 v19; // r15
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // r15
  bool v23; // zf
  VMX_NOTIFICATION_QUEUE *v24; // r10
  __int64 v25; // rdx
  __int64 i; // rdi
  __int64 v27; // [rsp+40h] [rbp-D8h]
  _QWORD v28[25]; // [rsp+50h] [rbp-C8h] BYREF
  struct _PARTMGR_PARTITIONS *v30; // [rsp+130h] [rbp+18h] BYREF
  unsigned int *v31; // [rsp+138h] [rbp+20h]

  v3 = 0;
  v30 = 0;
  memset(v28, 0, 0x90u);
  v4 = VMX_RECORD::PreTouch(a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        68,
        WPP_b525482092043ba595507d12d78e6f73_Traceguids,
        (unsigned int)v4);
    }
    return v5;
  }
  v7 = *((_QWORD *)a2 + 6);
  v8 = *(_QWORD *)(v7 + 128);
  v27 = v8;
  v9 = *(unsigned int **)(v8 + 16);
  v31 = v9;
  if ( *(_QWORD *)(v7 + 120) )
  {
    v10 = VMX_DISK_DEVICE::QueryPartitionDeviceObjects((VMX_DISK_DEVICE *)v9, &v30);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          69,
          WPP_b525482092043ba595507d12d78e6f73_Traceguids,
          (unsigned int)v10);
      }
      return v11;
    }
    v3 = v30;
  }
  v12 = 0;
  v13 = 0;
  while ( 1 )
  {
    v14 = *(_QWORD *)(v7 + 120);
    if ( !v14 )
      goto LABEL_35;
    v15 = *(_QWORD **)(v14 + 8LL * (*(_WORD *)(v14 + 64) & 1) + 40);
    v16 = *(_QWORD *)(*(_QWORD *)(v15[21] + 8LL * (*(_WORD *)(v15[21] + 64LL) & 1) + 40) + 136LL);
    v13 = VMX_PACK::DeleteVolumeTransaction(this, (struct VMX_RECORD *)v16);
    if ( v13 < 0 )
      break;
    *(_WORD *)(v16 + 64) |= 0x80u;
    v17 = *(_QWORD *)(v8 + 88);
    v18 = v15[12] << 9;
    v19 = *(_QWORD *)(v17 + 136) * v9[9];
    v20 = v15[10];
    v21 = 0;
    v22 = (v20 << 9) + v19;
    v23 = *(_DWORD *)v3 == 0;
    if ( *(_DWORD *)v3 )
    {
      do
      {
        v12 = (struct _DEVICE_OBJECT *)*((_QWORD *)v3 + v21 + 1);
        v13 = VmxpSendDeviceControl(v12, 0x70048u, 0, 0, v28, 0x90u, 0);
        if ( v13 >= 0 && v28[1] == v22 && v28[2] == v18 )
          break;
        v21 = (unsigned int)(v21 + 1);
      }
      while ( (unsigned int)v21 < *(_DWORD *)v3 );
      v23 = (_DWORD)v21 == *(_DWORD *)v3;
    }
    if ( v23 )
    {
      v13 = -1070071753;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v25 = 71;
LABEL_34:
        WPP_SF_d(*((_QWORD *)v24 + 3), v25, WPP_b525482092043ba595507d12d78e6f73_Traceguids, (unsigned int)v13);
        goto LABEL_35;
      }
      goto LABEL_35;
    }
    ObfReferenceObject(v12);
    v9 = v31;
    v8 = v27;
    *(_QWORD *)(*(_QWORD *)(v16 + 48) + 256LL) = v12;
  }
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v25 = 70;
    goto LABEL_34;
  }
LABEL_35:
  if ( v3 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)v3; i = (unsigned int)(i + 1) )
      ObfDereferenceObject(*((PVOID *)v3 + i + 1));
    ExFreePoolWithTag(v3, 0);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140055f34  mov     rax, rsp
0x140055f37  mov     [rax+10h], rbx
0x140055f3b  mov     [rax+8], rcx
0x140055f3f  push    rbp
0x140055f40  push    rsi
0x140055f41  push    rdi
0x140055f42  push    r12
0x140055f44  push    r13
0x140055f46  push    r14
0x140055f48  push    r15
0x140055f4a  sub     rsp, 0E0h
0x140055f51  mov     rsi, rdx
0x140055f54  lea     rcx, [rsp+118h+var_C8]; void *
0x140055f59  xor     ebx, ebx
0x140055f5b  xor     edx, edx; Val
0x140055f5d  mov     r8d, 90h; Size
0x140055f63  mov     [rax+18h], rbx
0x140055f67  call    memset
0x140055f6c  mov     rcx, rsi; this
0x140055f6f  call    ?PreTouch@VMX_RECORD@@QEAAJXZ; VMX_RECORD::PreTouch(void)
0x140055f74  mov     edi, eax
0x140055f76  test    eax, eax
0x140055f78  jns     short loc_140055FBA
0x140055f7a  mov     r10, cs:WPP_GLOBAL_Control
0x140055f81  lea     rcx, WPP_GLOBAL_Control
0x140055f88  cmp     r10, rcx
0x140055f8b  jz      short loc_140055FB3
0x140055f8d  mov     edx, [r10+2Ch]
0x140055f91  test    dl, 8
0x140055f94  jz      short loc_140055FB3
0x140055f96  cmp     byte ptr [r10+29h], 2
0x140055f9b  jb      short loc_140055FB3
0x140055f9d  mov     rcx, [r10+18h]
0x140055fa1  lea     edx, [rbx+44h]
0x140055fa4  mov     r9d, eax
0x140055fa7  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140055fae  call    WPP_SF_d
0x140055fb3  mov     eax, edi
0x140055fb5  jmp     loc_1400561D9
0x140055fba  mov     rbp, [rsi+30h]
0x140055fbe  mov     r12, [rbp+80h]
0x140055fc5  mov     [rsp+118h+var_D8], r12
0x140055fca  mov     r15, [r12+10h]
0x140055fcf  mov     [rsp+118h+arg_18], r15
0x140055fd7  cmp     [rbp+78h], rbx
0x140055fdb  jz      short loc_14005603D
0x140055fdd  lea     rdx, [rsp+118h+arg_10]; struct _PARTMGR_PARTITIONS **
0x140055fe5  mov     rcx, r15; this
0x140055fe8  call    ?QueryPartitionDeviceObjects@VMX_DISK_DEVICE@@QEAAJPEAPEAU_PARTMGR_PARTITIONS@@@Z; VMX_DISK_DEVICE::QueryPartitionDeviceObjects(_PARTMGR_PARTITIONS * *)
0x140055fed  mov     ebx, eax
0x140055fef  test    eax, eax
0x140055ff1  jns     short loc_140056035
0x140055ff3  mov     r10, cs:WPP_GLOBAL_Control
0x140055ffa  lea     rcx, WPP_GLOBAL_Control
0x140056001  cmp     r10, rcx
0x140056004  jz      short loc_14005602E
0x140056006  mov     edx, [r10+2Ch]
0x14005600a  test    dl, 8
0x14005600d  jz      short loc_14005602E
0x14005600f  cmp     byte ptr [r10+29h], 2
0x140056014  jb      short loc_14005602E
0x140056016  mov     rcx, [r10+18h]
0x14005601a  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140056021  mov     edx, 45h ; 'E'
0x140056026  mov     r9d, eax
0x140056029  call    WPP_SF_d
0x14005602e  mov     eax, ebx
0x140056030  jmp     loc_1400561D9
0x140056035  mov     rbx, [rsp+118h+arg_10]
0x14005603d  xor     r14d, r14d
0x140056040  xor     esi, esi
0x140056042  mov     rcx, [rbp+78h]
0x140056046  test    rcx, rcx
0x140056049  jz      loc_1400561A4
0x14005604f  movzx   eax, word ptr [rcx+40h]
0x140056053  and     eax, 1
0x140056056  mov     rdi, [rcx+rax*8+28h]
0x14005605b  mov     rcx, [rdi+0A8h]
0x140056062  movzx   eax, word ptr [rcx+40h]
0x140056066  and     eax, 1
0x140056069  mov     rax, [rcx+rax*8+28h]
0x14005606e  mov     rcx, [rsp+118h+arg_0]; this
0x140056076  mov     r13, [rax+88h]
0x14005607d  mov     rdx, r13; struct VMX_RECORD *
0x140056080  call    ?DeleteVolumeTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::DeleteVolumeTransaction(VMX_RECORD *)
0x140056085  mov     esi, eax
0x140056087  test    eax, eax
0x140056089  js      loc_14005616A
0x14005608f  mov     eax, 80h
0x140056094  or      [r13+40h], ax
0x140056099  mov     rcx, [r12+58h]
0x14005609e  mov     r15d, [r15+24h]
0x1400560a2  mov     r12, [rdi+60h]
0x1400560a6  shl     r12, 9
0x1400560aa  imul    r15, [rcx+88h]
0x1400560b2  mov     rcx, [rdi+50h]
0x1400560b6  xor     edi, edi
0x1400560b8  shl     rcx, 9
0x1400560bc  add     r15, rcx
0x1400560bf  cmp     edi, [rbx]
0x1400560c1  jnb     short loc_14005610E
0x1400560c3  mov     r14, [rbx+rdi*8+8]
0x1400560c8  lea     rax, [rsp+118h+var_C8]
0x1400560cd  mov     [rsp+118h+var_E8], 0; BOOLEAN
0x1400560d2  mov     rcx, r14; DeviceObject
0x1400560d5  mov     [rsp+118h+var_F0], 90h; ULONG
0x1400560dd  xor     r9d, r9d; InputBufferLength
0x1400560e0  xor     r8d, r8d; InputBuffer
0x1400560e3  mov     [rsp+118h+var_F8], rax; PVOID
0x1400560e8  mov     edx, 70048h; IoControlCode
0x1400560ed  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x1400560f2  mov     esi, eax
0x1400560f4  test    eax, eax
0x1400560f6  js      short loc_140056106
0x1400560f8  cmp     [rsp+118h+var_C0], r15
0x1400560fd  jnz     short loc_140056106
0x1400560ff  cmp     [rsp+118h+var_B8], r12
0x140056104  jz      short loc_14005610C
0x140056106  inc     edi
0x140056108  cmp     edi, [rbx]
0x14005610a  jb      short loc_1400560C3
0x14005610c  cmp     edi, [rbx]
0x14005610e  jz      short loc_14005613C
0x140056110  mov     rcx, r14; Object
0x140056113  call    cs:__imp_ObfReferenceObject
0x14005611a  nop     dword ptr [rax+rax+00h]
0x14005611f  mov     rax, [r13+30h]
0x140056123  mov     r15, [rsp+118h+arg_18]
0x14005612b  mov     r12, [rsp+118h+var_D8]
0x140056130  mov     [rax+100h], r14
0x140056137  jmp     loc_140056042
0x14005613c  mov     esi, 0C0380037h
0x140056141  mov     r10, cs:WPP_GLOBAL_Control
0x140056148  lea     rcx, WPP_GLOBAL_Control
0x14005614f  cmp     r10, rcx
0x140056152  jz      short loc_1400561A4
0x140056154  mov     eax, [r10+2Ch]
0x140056158  test    al, 8
0x14005615a  jz      short loc_1400561A4
0x14005615c  cmp     byte ptr [r10+29h], 2
0x140056161  jb      short loc_1400561A4
0x140056163  mov     edx, 47h ; 'G'
0x140056168  jmp     short loc_140056191
0x14005616a  mov     r10, cs:WPP_GLOBAL_Control
0x140056171  lea     rcx, WPP_GLOBAL_Control
0x140056178  cmp     r10, rcx
0x14005617b  jz      short loc_1400561A4
0x14005617d  mov     eax, [r10+2Ch]
0x140056181  test    al, 8
0x140056183  jz      short loc_1400561A4
0x140056185  cmp     byte ptr [r10+29h], 2
0x14005618a  jb      short loc_1400561A4
0x14005618c  mov     edx, 46h ; 'F'
0x140056191  mov     rcx, [r10+18h]
0x140056195  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14005619c  mov     r9d, esi
0x14005619f  call    WPP_SF_d
0x1400561a4  test    rbx, rbx
0x1400561a7  jz      short loc_1400561D7
0x1400561a9  xor     edi, edi
0x1400561ab  cmp     [rbx], edi
0x1400561ad  jbe     short loc_1400561C6
0x1400561af  mov     rcx, [rbx+rdi*8+8]; Object
0x1400561b4  call    cs:__imp_ObfDereferenceObject
0x1400561bb  nop     dword ptr [rax+rax+00h]
0x1400561c0  inc     edi
0x1400561c2  cmp     edi, [rbx]
0x1400561c4  jb      short loc_1400561AF
0x1400561c6  xor     edx, edx; Tag
0x1400561c8  mov     rcx, rbx; P
0x1400561cb  call    cs:__imp_ExFreePoolWithTag
0x1400561d2  nop     dword ptr [rax+rax+00h]
0x1400561d7  mov     eax, esi
0x1400561d9  mov     rbx, [rsp+118h+arg_8]
0x1400561e1  add     rsp, 0E0h
0x1400561e8  pop     r15
0x1400561ea  pop     r14
0x1400561ec  pop     r13
0x1400561ee  pop     r12
0x1400561f0  pop     rdi
0x1400561f1  pop     rsi
0x1400561f2  pop     rbp
0x1400561f3  retn
```
