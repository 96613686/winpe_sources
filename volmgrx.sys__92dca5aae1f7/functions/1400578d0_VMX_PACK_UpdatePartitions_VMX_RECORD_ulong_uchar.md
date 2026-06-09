# VMX_PACK::UpdatePartitions(VMX_RECORD * *,ulong,uchar)

- ea: `0x1400578d0`
- end: `0x140057db7`
- name: `?UpdatePartitions@VMX_PACK@@QEAAJPEAPEAVVMX_RECORD@@KE@Z`
- size: `1255`
- prototype: `__int64 __fastcall(VMX_PACK *this, struct VMX_RECORD **, unsigned int, char)`
- caller_count: `7`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400302dc`
- `0x140035e3c`
- `0x1400362a8`
- `0x140036bac`
- `0x140036e70`
- `0x140037fe4`
- `0x14003bd90`

## callees

- `0x1400099d8`
- `0x14001b960`
- `0x14001be80`
- `0x14002d44c`
- `0x140033854`
- `0x1400342bc`
- `0x140044ac4`
- `0x1400578d0`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140057a6e`
- `ntoskrnl!ExAllocatePool2` at `0x140057ade`
- `ntoskrnl!ExAllocatePool2` at `0x140057a6e`
- `ntoskrnl!ExAllocatePool2` at `0x140057ade`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057a16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057d6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057d8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057da4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057a16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057d6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057d8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057da4`

## pseudocode

```c
__int64 __fastcall VMX_PACK::UpdatePartitions(VMX_PACK *this, struct VMX_RECORD **a2, unsigned int a3, char a4)
{
  __int64 v4; // rsi
  __int64 v6; // rdi
  struct VMX_RECORD *v7; // rbp
  VMX_PHYSICAL_DISK *v8; // r14
  VMX_DISK_DEVICE *v9; // r15
  int DriveGeometry; // eax
  VMX_NOTIFICATION_QUEUE *v11; // r10
  __int64 v12; // rdx
  struct _DISK_GEOMETRY *Pool2; // r12
  int DynamicPartitions; // edi
  struct _DRIVE_LAYOUT_INFORMATION_EX **v16; // rax
  struct _DRIVE_LAYOUT_INFORMATION_EX **v17; // r15
  __int64 v18; // r9
  VMX_NOTIFICATION_QUEUE *v19; // rcx
  __int64 v20; // rdx
  __int64 i; // rbx
  __int64 v22; // rcx
  VMX_DISK_DEVICE *v23; // rbp
  __int64 j; // rbp
  struct VMX_RECORD *v25; // rbx
  __int64 k; // rbx
  struct VMX_RECORD *v27; // r14
  __int64 v28; // r10
  struct _DRIVE_LAYOUT_INFORMATION_EX *v29; // rdx
  VMX_DISK_DEVICE *v30; // rcx
  __int64 v31; // r9
  __int64 m; // rbx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v33; // rcx
  PVOID P; // [rsp+20h] [rbp-68h] BYREF
  struct _DISK_GEOMETRY v35; // [rsp+28h] [rbp-60h] BYREF

  v4 = a3;
  P = 0;
  memset(&v35, 0, sizeof(v35));
  if ( !a3 )
    return 0;
  if ( a4 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = a2[v6];
      v8 = *(VMX_PHYSICAL_DISK **)(*((_QWORD *)v7 + (*((_WORD *)v7 + 32) & 1) + 5) + 128LL);
      if ( v8 )
      {
        v9 = (VMX_DISK_DEVICE *)*((_QWORD *)v8 + 2);
        DriveGeometry = VMX_DISK_DEVICE::GetDriveGeometry(v9, &v35);
        if ( DriveGeometry >= 0 )
        {
          DriveGeometry = VMX_DISK_DEVICE::GetDriveLayoutEx(v9, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P);
          if ( DriveGeometry >= 0 )
          {
            VMX_PHYSICAL_DISK::CreateDynamicPartitions(v8, v7, &v35, (struct _DRIVE_LAYOUT_INFORMATION_EX *)P);
            VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)Global + 36), 3, (__int64)v7, 0);
            ExFreePoolWithTag(P, 0);
            goto LABEL_17;
          }
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
          {
            goto LABEL_17;
          }
          v12 = 110;
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
          {
            goto LABEL_17;
          }
          v12 = 109;
        }
        WPP_SF_d(
          *((_QWORD *)v11 + 3),
          v12,
          WPP_b525482092043ba595507d12d78e6f73_Traceguids,
          (unsigned int)DriveGeometry);
      }
LABEL_17:
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= (unsigned int)v4 )
        return 0;
    }
  }
  Pool2 = (struct _DISK_GEOMETRY *)ExAllocatePool2(258, 24LL * a3, 538996054);
  if ( Pool2 )
  {
    v16 = (struct _DRIVE_LAYOUT_INFORMATION_EX **)ExAllocatePool2(258, 8 * v4, 538996054);
    v17 = v16;
    if ( v16 )
    {
      DynamicPartitions = 0;
      if ( (_DWORD)v4 )
        memset(v16, 0, 8 * v4);
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= (unsigned int)v4 )
        {
          for ( j = 0; (unsigned int)j < (unsigned int)v4; j = (unsigned int)(j + 1) )
          {
            v25 = a2[j];
            DynamicPartitions = VMX_PHYSICAL_DISK::CreateDynamicPartitions(
                                  *(VMX_PHYSICAL_DISK **)(*((_QWORD *)v25 + (*((_WORD *)v25 + 32) & 1) + 5) + 128LL),
                                  v25,
                                  &Pool2[j],
                                  v17[j]);
            if ( DynamicPartitions < 0 )
            {
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  116,
                  WPP_b525482092043ba595507d12d78e6f73_Traceguids,
                  (unsigned int)DynamicPartitions);
              }
              for ( k = 0; (unsigned int)k < (unsigned int)j; k = (unsigned int)(k + 1) )
              {
                v27 = a2[k];
                v28 = 0;
                v29 = v17[k];
                v30 = *(VMX_DISK_DEVICE **)(*(_QWORD *)(*((_QWORD *)v27 + (*((_WORD *)v27 + 32) & 1) + 5) + 128LL) + 16LL);
                if ( v29->PartitionCount )
                {
                  do
                  {
                    v31 = v28;
                    v28 = (unsigned int)(v28 + 1);
                    v29->PartitionEntry[v31].RewritePartition = 1;
                  }
                  while ( (unsigned int)v28 < v29->PartitionCount );
                }
                VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(v30, v29);
                VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)Global + 36), 3, (__int64)v27, 0);
              }
              goto LABEL_64;
            }
            VMX_NOTIFICATION_QUEUE::AddTaskNotification(*((_QWORD *)Global + 36), 3, (__int64)v25, 0);
          }
          goto LABEL_64;
        }
        v22 = *(_QWORD *)(*((_QWORD *)a2[i] + (*((_WORD *)a2[i] + 32) & 1) + 5) + 128LL);
        if ( !v22 )
        {
          DynamicPartitions = -1070071791;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v20 = 113;
            goto LABEL_50;
          }
          goto LABEL_64;
        }
        v23 = *(VMX_DISK_DEVICE **)(v22 + 16);
        DynamicPartitions = VMX_DISK_DEVICE::GetDriveGeometry(v23, &Pool2[i]);
        if ( DynamicPartitions < 0 )
          break;
        DynamicPartitions = VMX_DISK_DEVICE::GetDriveLayoutEx(v23, &v17[i]);
        if ( DynamicPartitions < 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v20 = 115;
LABEL_50:
            v18 = (unsigned int)DynamicPartitions;
            goto LABEL_29;
          }
          goto LABEL_64;
        }
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v20 = 114;
        goto LABEL_50;
      }
    }
    else
    {
      v18 = 3221225626LL;
      DynamicPartitions = -1073741670;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v20 = 112;
LABEL_29:
        WPP_SF_d(*((_QWORD *)v19 + 3), v20, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v18);
      }
    }
LABEL_64:
    ExFreePoolWithTag(Pool2, 0);
    if ( v17 )
    {
      for ( m = 0; (unsigned int)m < (unsigned int)v4; m = (unsigned int)(m + 1) )
      {
        v33 = v17[m];
        if ( v33 )
          ExFreePoolWithTag(v33, 0);
      }
      ExFreePoolWithTag(v17, 0);
    }
  }
  else
  {
    DynamicPartitions = -1073741670;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 111, WPP_b525482092043ba595507d12d78e6f73_Traceguids, 3221225626LL);
    }
  }
  return (unsigned int)DynamicPartitions;
}

```

## disassembly

```asm
0x1400578d0  mov     [rsp+arg_0], rbx
0x1400578d5  push    rbp
0x1400578d6  push    rsi
0x1400578d7  push    rdi
0x1400578d8  push    r12
0x1400578da  push    r13
0x1400578dc  push    r14
0x1400578de  push    r15
0x1400578e0  sub     rsp, 50h
0x1400578e4  mov     rax, cs:__security_cookie
0x1400578eb  xor     rax, rsp
0x1400578ee  mov     [rsp+88h+var_48], rax
0x1400578f3  xor     eax, eax
0x1400578f5  mov     esi, r8d
0x1400578f8  mov     qword ptr [rsp+88h+var_60.SectorsPerTrack], rax
0x1400578fd  xorps   xmm0, xmm0
0x140057900  mov     [rsp+88h+P], rax
0x140057905  mov     r13, rdx
0x140057908  movups  xmmword ptr [rsp+88h+var_60.Cylinders], xmm0
0x14005790d  test    r8d, r8d
0x140057910  jz      loc_140057A2C
0x140057916  test    r9b, r9b
0x140057919  jz      loc_140057A54
0x14005791f  xor     edi, edi
0x140057921  test    r8d, r8d
0x140057924  jz      loc_140057A2C
0x14005792a  lea     rbx, WPP_GLOBAL_Control
0x140057931  mov     rbp, [r13+rdi*8+0]
0x140057936  movzx   eax, word ptr [rbp+40h]
0x14005793a  and     eax, 1
0x14005793d  mov     rax, [rbp+rax*8+28h]
0x140057942  mov     r14, [rax+80h]
0x140057949  test    r14, r14
0x14005794c  jz      loc_140057A22
0x140057952  mov     r15, [r14+10h]
0x140057956  lea     rdx, [rsp+88h+var_60]; PVOID
0x14005795b  mov     rcx, r15; this
0x14005795e  call    ?GetDriveGeometry@VMX_DISK_DEVICE@@QEAAJPEAU_DISK_GEOMETRY@@@Z; VMX_DISK_DEVICE::GetDriveGeometry(_DISK_GEOMETRY *)
0x140057963  test    eax, eax
0x140057965  jns     short loc_1400579A9
0x140057967  mov     r10, cs:WPP_GLOBAL_Control
0x14005796e  cmp     r10, rbx
0x140057971  jz      loc_140057A22
0x140057977  mov     ecx, [r10+2Ch]
0x14005797b  test    cl, 8
0x14005797e  jz      loc_140057A22
0x140057984  cmp     byte ptr [r10+29h], 2
0x140057989  jb      loc_140057A22
0x14005798f  mov     edx, 6Dh ; 'm'
0x140057994  mov     rcx, [r10+18h]
0x140057998  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14005799f  mov     r9d, eax
0x1400579a2  call    WPP_SF_d
0x1400579a7  jmp     short loc_140057A22
0x1400579a9  lea     rdx, [rsp+88h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x1400579ae  mov     rcx, r15; this
0x1400579b1  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x1400579b6  test    eax, eax
0x1400579b8  jns     short loc_1400579DD
0x1400579ba  mov     r10, cs:WPP_GLOBAL_Control
0x1400579c1  cmp     r10, rbx
0x1400579c4  jz      short loc_140057A22
0x1400579c6  mov     ecx, [r10+2Ch]
0x1400579ca  test    cl, 8
0x1400579cd  jz      short loc_140057A22
0x1400579cf  cmp     byte ptr [r10+29h], 2
0x1400579d4  jb      short loc_140057A22
0x1400579d6  mov     edx, 6Eh ; 'n'
0x1400579db  jmp     short loc_140057994
0x1400579dd  mov     r9, [rsp+88h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x1400579e2  lea     r8, [rsp+88h+var_60]; struct _DISK_GEOMETRY *
0x1400579e7  mov     rdx, rbp; struct VMX_RECORD *
0x1400579ea  mov     rcx, r14; this
0x1400579ed  call    ?CreateDynamicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateDynamicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x1400579f2  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400579f9  xor     r9d, r9d
0x1400579fc  mov     r8, rbp
0x1400579ff  mov     rcx, [rcx+120h]
0x140057a06  lea     edx, [r9+3]
0x140057a0a  call    ?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)
0x140057a0f  mov     rcx, [rsp+88h+P]; P
0x140057a14  xor     edx, edx; Tag
0x140057a16  call    cs:__imp_ExFreePoolWithTag
0x140057a1d  nop     dword ptr [rax+rax+00h]
0x140057a22  inc     edi
0x140057a24  cmp     edi, esi
0x140057a26  jb      loc_140057931
0x140057a2c  xor     eax, eax
0x140057a2e  mov     rcx, [rsp+88h+var_48]
0x140057a33  xor     rcx, rsp; StackCookie
0x140057a36  call    __security_check_cookie
0x140057a3b  mov     rbx, [rsp+88h+arg_0]
0x140057a43  add     rsp, 50h
0x140057a47  pop     r15
0x140057a49  pop     r14
0x140057a4b  pop     r13
0x140057a4d  pop     r12
0x140057a4f  pop     rdi
0x140057a50  pop     rsi
0x140057a51  pop     rbp
0x140057a52  retn
0x140057a54  lea     rdx, [rsi+rsi*2]
0x140057a58  mov     edi, 20206D56h
0x140057a5d  mov     ebp, 102h
0x140057a62  shl     rdx, 3
0x140057a66  mov     r8d, edi
0x140057a69  mov     ecx, ebp
0x140057a6b  mov     rbx, rsi
0x140057a6e  call    cs:__imp_ExAllocatePool2
0x140057a75  nop     dword ptr [rax+rax+00h]
0x140057a7a  mov     r12, rax
0x140057a7d  test    rax, rax
0x140057a80  jnz     short loc_140057AD1
0x140057a82  mov     r9d, 0C000009Ah
0x140057a88  mov     edi, r9d
0x140057a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140057a92  lea     rbx, WPP_GLOBAL_Control
0x140057a99  cmp     rcx, rbx
0x140057a9c  jz      loc_140057DB0
0x140057aa2  mov     eax, [rcx+2Ch]
0x140057aa5  test    al, 8
0x140057aa7  jz      loc_140057DB0
0x140057aad  cmp     byte ptr [rcx+29h], 2
0x140057ab1  jb      loc_140057DB0
0x140057ab7  mov     rcx, [rcx+18h]
0x140057abb  lea     edx, [r12+6Fh]
0x140057ac0  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140057ac7  call    WPP_SF_d
0x140057acc  jmp     loc_140057DB0
0x140057ad1  shl     rbx, 3
0x140057ad5  mov     r8d, edi
0x140057ad8  mov     rdx, rbx
0x140057adb  mov     rcx, rbp
0x140057ade  call    cs:__imp_ExAllocatePool2
0x140057ae5  nop     dword ptr [rax+rax+00h]
0x140057aea  mov     r15, rax
0x140057aed  test    rax, rax
0x140057af0  jnz     short loc_140057B40
0x140057af2  mov     r9d, 0C000009Ah
0x140057af8  mov     edi, r9d
0x140057afb  mov     rcx, cs:WPP_GLOBAL_Control
0x140057b02  lea     rbx, WPP_GLOBAL_Control
0x140057b09  cmp     rcx, rbx
0x140057b0c  jz      loc_140057D66
0x140057b12  mov     eax, [rcx+2Ch]
0x140057b15  test    al, 8
0x140057b17  jz      loc_140057D66
0x140057b1d  cmp     byte ptr [rcx+29h], 2
0x140057b21  jb      loc_140057D66
0x140057b27  lea     edx, [r15+70h]
0x140057b2b  mov     rcx, [rcx+18h]
0x140057b2f  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140057b36  call    WPP_SF_d
0x140057b3b  jmp     loc_140057D66
0x140057b40  xor     edi, edi
0x140057b42  test    esi, esi
0x140057b44  jz      short loc_140057B57
0x140057b46  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140057b4a  xor     edx, edx; Val
0x140057b4c  mov     r8, rbx; Size
0x140057b4f  mov     rcx, r15; void *
0x140057b52  call    memset
0x140057b57  xor     ebx, ebx
0x140057b59  cmp     ebx, esi
0x140057b5b  jnb     loc_140057C56
0x140057b61  mov     rcx, [r13+rbx*8+0]
0x140057b66  movzx   eax, word ptr [rcx+40h]
0x140057b6a  and     eax, 1
0x140057b6d  mov     rax, [rcx+rax*8+28h]
0x140057b72  mov     rcx, [rax+80h]
0x140057b79  test    rcx, rcx
0x140057b7c  jz      loc_140057C18
0x140057b82  mov     rbp, [rcx+10h]
0x140057b86  lea     rax, [rbx+rbx*2]
0x140057b8a  lea     rdx, [r12+rax*8]; PVOID
0x140057b8e  mov     rcx, rbp; this
0x140057b91  call    ?GetDriveGeometry@VMX_DISK_DEVICE@@QEAAJPEAU_DISK_GEOMETRY@@@Z; VMX_DISK_DEVICE::GetDriveGeometry(_DISK_GEOMETRY *)
0x140057b96  mov     edi, eax
0x140057b98  test    eax, eax
0x140057b9a  js      short loc_140057BE5
0x140057b9c  lea     rdx, [r15+rbx*8]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140057ba0  mov     rcx, rbp; this
0x140057ba3  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140057ba8  mov     edi, eax
0x140057baa  test    eax, eax
0x140057bac  js      short loc_140057BB2
0x140057bae  inc     ebx
0x140057bb0  jmp     short loc_140057B59
0x140057bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140057bb9  lea     rbx, WPP_GLOBAL_Control
0x140057bc0  cmp     rcx, rbx
0x140057bc3  jz      loc_140057D66
0x140057bc9  mov     eax, [rcx+2Ch]
0x140057bcc  test    al, 8
0x140057bce  jz      loc_140057D66
0x140057bd4  cmp     byte ptr [rcx+29h], 2
0x140057bd8  jb      loc_140057D66
0x140057bde  mov     edx, 73h ; 's'
0x140057be3  jmp     short loc_140057C4E
0x140057be5  mov     rcx, cs:WPP_GLOBAL_Control
0x140057bec  lea     rbx, WPP_GLOBAL_Control
0x140057bf3  cmp     rcx, rbx
0x140057bf6  jz      loc_140057D66
0x140057bfc  mov     eax, [rcx+2Ch]
0x140057bff  test    al, 8
0x140057c01  jz      loc_140057D66
0x140057c07  cmp     byte ptr [rcx+29h], 2
0x140057c0b  jb      loc_140057D66
0x140057c11  mov     edx, 72h ; 'r'
0x140057c16  jmp     short loc_140057C4E
0x140057c18  mov     edi, 0C0380011h
0x140057c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c24  lea     rbx, WPP_GLOBAL_Control
0x140057c2b  cmp     rcx, rbx
0x140057c2e  jz      loc_140057D66
0x140057c34  mov     eax, [rcx+2Ch]
0x140057c37  test    al, 8
0x140057c39  jz      loc_140057D66
0x140057c3f  cmp     byte ptr [rcx+29h], 2
0x140057c43  jb      loc_140057D66
0x140057c49  mov     edx, 71h ; 'q'
0x140057c4e  mov     r9d, edi
0x140057c51  jmp     loc_140057B2B
0x140057c56  xor     ebp, ebp
0x140057c58  cmp     ebp, esi
0x140057c5a  jnb     loc_140057CF4
0x140057c60  mov     rbx, [r13+rbp*8+0]
0x140057c65  lea     rax, ds:0[rbp*2]
0x140057c6d  mov     r9, [r15+rbp*8]; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140057c71  add     rax, rbp
0x140057c74  mov     rdx, rbx; struct VMX_RECORD *
0x140057c77  lea     r8, [r12+rax*8]; struct _DISK_GEOMETRY *
0x140057c7b  movzx   eax, word ptr [rbx+40h]
0x140057c7f  and     eax, 1
0x140057c82  mov     rcx, [rbx+rax*8+28h]
0x140057c87  mov     rcx, [rcx+80h]; this
0x140057c8e  call    ?CreateDynamicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateDynamicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140057c93  mov     edi, eax
0x140057c95  test    eax, eax
0x140057c97  js      short loc_140057CBA
0x140057c99  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140057ca0  xor     r9d, r9d
0x140057ca3  mov     r8, rbx
0x140057ca6  mov     rcx, [rcx+120h]
0x140057cad  lea     edx, [r9+3]
0x140057cb1  call    ?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)
0x140057cb6  inc     ebp
0x140057cb8  jmp     short loc_140057C58
0x140057cba  mov     rcx, cs:WPP_GLOBAL_Control
0x140057cc1  lea     rbx, WPP_GLOBAL_Control
0x140057cc8  cmp     rcx, rbx
0x140057ccb  jz      short loc_140057CF8
0x140057ccd  mov     eax, [rcx+2Ch]
0x140057cd0  test    al, 8
0x140057cd2  jz      short loc_140057CF8
0x140057cd4  cmp     byte ptr [rcx+29h], 2
0x140057cd8  jb      short loc_140057CF8
0x140057cda  mov     rcx, [rcx+18h]
0x140057cde  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x140057ce5  mov     edx, 74h ; 't'
0x140057cea  mov     r9d, edi
0x140057ced  call    WPP_SF_d
0x140057cf2  jmp     short loc_140057CF8
0x140057cf4  test    edi, edi
0x140057cf6  jns     short loc_140057D66
0x140057cf8  xor     ebx, ebx
0x140057cfa  test    ebp, ebp
0x140057cfc  jz      short loc_140057D66
0x140057cfe  mov     r14, [r13+rbx*8+0]
0x140057d03  xor     r10d, r10d
0x140057d06  mov     rdx, [r15+rbx*8]; InputBuffer
0x140057d0a  movzx   eax, word ptr [r14+40h]
0x140057d0f  and     eax, 1
0x140057d12  mov     rax, [r14+rax*8+28h]
0x140057d17  mov     rcx, [rax+80h]
0x140057d1e  mov     rcx, [rcx+10h]; this
0x140057d22  cmp     [rdx+4], r10d
0x140057d26  jbe     short loc_140057D3E
0x140057d28  lea     r9, [r10+r10*8]
0x140057d2c  inc     r10d
0x140057d2f  add     r9, r9
0x140057d32  mov     byte ptr [rdx+r9*8+4Ch], 1
0x140057d38  cmp     r10d, [rdx+4]
0x140057d3c  jb      short loc_140057D28
0x140057d3e  call    ?SetDriveLayoutExSynchronous@VMX_DISK_DEVICE@@QEAAJPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140057d43  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140057d4a  xor     r9d, r9d
0x140057d4d  mov     r8, r14
0x140057d50  mov     rcx, [rcx+120h]
0x140057d57  lea     edx, [r9+3]
0x140057d5b  call    ?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)
0x140057d60  inc     ebx
0x140057d62  cmp     ebx, ebp
0x140057d64  jb      short loc_140057CFE
0x140057d66  xor     edx, edx; Tag
0x140057d68  mov     rcx, r12; P
0x140057d6b  call    cs:__imp_ExFreePoolWithTag
0x140057d72  nop     dword ptr [rax+rax+00h]
0x140057d77  test    r15, r15
0x140057d7a  jz      short loc_140057DB0
  ... truncated ...
```
