# VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x1400342bc`
- end: `0x1400347ec`
- name: `?SetDriveLayoutExSynchronous@VMX_DISK_DEVICE@@QEAAJPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `1328`
- prototype: `__int64 __fastcall(VMX_DISK_DEVICE *this, unsigned int *InputBuffer)`
- caller_count: `9`
- callee_count: `8`
- tags: ``

## callers

- `0x14002af14`
- `0x140031bc8`
- `0x1400437c8`
- `0x140043e88`
- `0x140044b38`
- `0x1400452a4`
- `0x1400458e8`
- `0x1400459b4`
- `0x1400578d0`

## callees

- `0x140004550`
- `0x140007380`
- `0x1400099d8`
- `0x14001b9a0`
- `0x14001be80`
- `0x1400341a8`
- `0x1400342bc`
- `0x14005d644`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140034721`
- `ntoskrnl!KeDelayExecutionThread` at `0x140034721`
- `ntoskrnl!ObfDereferenceObject` at `0x1400346fc`
- `ntoskrnl!ObfDereferenceObject` at `0x1400346fc`
- `ntoskrnl!ExAllocatePool2` at `0x140034459`
- `ntoskrnl!ExAllocatePool2` at `0x140034555`
- `ntoskrnl!ExAllocatePool2` at `0x140034459`
- `ntoskrnl!ExAllocatePool2` at `0x140034555`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003453c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034743`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034774`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400347b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003453c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034743`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034774`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400347b3`

## pseudocode

```c
__int64 __fastcall VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(VMX_DISK_DEVICE *this, unsigned int *InputBuffer)
{
  VMX_GLOBAL_DATA *v2; // rbx
  VMX_DISK_DEVICE *v4; // r15
  void (__fastcall *v5)(__int64); // rax
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  VMX_NOTIFICATION_QUEUE *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // r13d
  unsigned int v13; // r8d
  __int64 j; // rdx
  unsigned int v15; // eax
  int v16; // ecx
  unsigned int v17; // r8d
  __int64 i; // rdx
  __int64 v19; // rax
  int v20; // eax
  _DWORD *Pool2; // r14
  unsigned int v22; // eax
  NTSTATUS v23; // eax
  unsigned int v24; // ebx
  __int64 k; // r15
  NTSTATUS v26; // eax
  unsigned int v27; // r9d
  __int64 v28; // r8
  __int64 v29; // rcx
  unsigned int v30; // eax
  bool v31; // zf
  __int64 v32; // rdx
  VMX_NOTIFICATION_QUEUE *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 m; // r15
  __int64 result; // rax
  union _LARGE_INTEGER Interval; // [rsp+40h] [rbp-D8h] BYREF
  VMX_GLOBAL_DATA *v39; // [rsp+48h] [rbp-D0h]
  _QWORD v40[25]; // [rsp+50h] [rbp-C8h] BYREF
  unsigned int v42; // [rsp+130h] [rbp+18h]
  ULONG v43; // [rsp+138h] [rbp+20h]

  v2 = Global;
  v4 = this;
  v39 = Global;
  memset(v40, 0, 0x90u);
  *((_BYTE *)v4 + 52) = 1;
  v5 = (void (__fastcall *)(__int64))*((_QWORD *)v2 + 4);
  v6 = *((_QWORD *)v2 + 1);
  Interval.QuadPart = 0;
  v5(v6);
  v7 = VMX_DISK_DEVICE::Reference(v4);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_89;
    }
    v10 = 32;
LABEL_6:
    v11 = (unsigned int)v7;
    goto LABEL_7;
  }
  v8 = VMX_DISK_DEVICE::SetDriveLayoutEx(v4, InputBuffer);
  VMX_DISK_DEVICE::Dereference(v4);
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_89;
    }
    v10 = 33;
    goto LABEL_6;
  }
  v12 = 0;
  if ( *InputBuffer )
  {
    if ( *InputBuffer == 1 )
    {
      v17 = InputBuffer[1];
      for ( i = 0; (unsigned int)i < v17; v12 = v20 )
      {
        v19 = *(_QWORD *)&InputBuffer[36 * i + 20] - *(_QWORD *)&PARTITION_ENTRY_UNUSED_GUID.Data1;
        if ( !v19 )
          v19 = *(_QWORD *)&InputBuffer[36 * i + 22] - *(_QWORD *)PARTITION_ENTRY_UNUSED_GUID.Data4;
        v31 = v19 == 0;
        v20 = v12 + 1;
        if ( v31 )
          v20 = v12;
        i = (unsigned int)(i + 1);
      }
    }
  }
  else
  {
    v13 = InputBuffer[1];
    for ( j = 0; (unsigned int)j < v13; j = (unsigned int)(j + 1) )
    {
      v15 = LOBYTE(InputBuffer[36 * j + 20]);
      if ( (unsigned __int8)v15 <= 0xFu )
      {
        v16 = 32801;
        if ( _bittest(&v16, v15) )
          continue;
      }
      ++v12;
    }
  }
  v43 = 136;
  Pool2 = (_DWORD *)ExAllocatePool2(258, 136, 538996054);
  if ( !Pool2 )
  {
    v11 = 3221225626LL;
    v8 = -1073741670;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_89;
    }
    v10 = 34;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v9 + 3), v10, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v11);
    goto LABEL_89;
  }
  Interval.QuadPart = -100000;
  v22 = 0;
LABEL_33:
  v42 = v22;
  if ( v22 >= 0xA )
  {
LABEL_88:
    ExFreePoolWithTag(Pool2, 0);
    goto LABEL_89;
  }
  do
  {
    v8 = VMX_DISK_DEVICE::Reference(v4);
    if ( v8 < 0 )
    {
      ExFreePoolWithTag(Pool2, 0);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        goto LABEL_89;
      }
      v10 = 35;
LABEL_86:
      v11 = (unsigned int)v8;
      goto LABEL_7;
    }
    VMX_DISK_DEVICE::Dereference(v4);
    v23 = VmxpSendDeviceControl(*((PDEVICE_OBJECT *)v4 + 3), 0x704190u, 0, 0, Pool2, v43, 1u);
    v8 = v23;
    if ( v23 >= 0 )
    {
      if ( *Pool2 == v12 )
      {
        for ( k = 0; (unsigned int)k < *Pool2; k = (unsigned int)(k + 1) )
        {
          v26 = VmxpSendDeviceControl(*(PDEVICE_OBJECT *)&Pool2[2 * k + 2], 0x70048u, 0, 0, v40, 0x90u, 0);
          v8 = v26;
          if ( v26 < 0 )
          {
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
            {
              v34 = 38;
              v35 = (unsigned int)v26;
              goto LABEL_73;
            }
            break;
          }
          v27 = InputBuffer[1];
          v28 = 0;
          if ( v27 )
          {
            while ( 1 )
            {
              v29 = 36 * v28;
              if ( v40[1] == *(_QWORD *)&InputBuffer[36 * v28 + 14] && v40[2] == *(_QWORD *)&InputBuffer[v29 + 16] )
              {
                v30 = InputBuffer[v29 + 12];
                if ( LODWORD(v40[0]) == v30 )
                {
                  if ( v30 )
                  {
                    if ( v30 != 1 )
                      break;
                    v32 = v40[4] - *(_QWORD *)&InputBuffer[v29 + 20];
                    if ( v40[4] == *(_QWORD *)&InputBuffer[v29 + 20] )
                      v32 = v40[5] - *(_QWORD *)&InputBuffer[v29 + 22];
                    v31 = v32 == 0;
                  }
                  else
                  {
                    v31 = LOBYTE(v40[4]) == LOBYTE(InputBuffer[v29 + 20]);
                  }
                  if ( v31 )
                    break;
                }
              }
              v28 = (unsigned int)(v28 + 1);
              if ( (unsigned int)v28 >= v27 )
                goto LABEL_58;
            }
          }
          else
          {
LABEL_58:
            if ( (_DWORD)v28 == v27 )
            {
              v8 = -1070071753;
              v33 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                v34 = 39;
                goto LABEL_72;
              }
              break;
            }
          }
        }
      }
      else
      {
        v8 = -1070071753;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          v34 = 40;
LABEL_72:
          v35 = 3224895543LL;
LABEL_73:
          WPP_SF_d(*((_QWORD *)v33 + 3), v34, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v35);
        }
      }
      for ( m = 0; (unsigned int)m < *Pool2; m = (unsigned int)(m + 1) )
        ObfDereferenceObject(*(PVOID *)&Pool2[2 * m + 2]);
      if ( v8 < 0 )
      {
        KeDelayExecutionThread(0, 0, &Interval);
        v4 = this;
        v22 = v42 + 1;
        goto LABEL_33;
      }
      v4 = this;
      goto LABEL_88;
    }
    if ( v23 != -2147483643 )
    {
      ExFreePoolWithTag(Pool2, 0);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        goto LABEL_89;
      }
      v10 = 36;
      goto LABEL_86;
    }
    v24 = 8 * *Pool2 + 8;
    v43 = v24;
    ExFreePoolWithTag(Pool2, 0);
    Pool2 = (_DWORD *)ExAllocatePool2(258, v24, 538996054);
  }
  while ( Pool2 );
  v11 = 3221225626LL;
  v8 = -1073741670;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 8u)
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v10 = 37;
    goto LABEL_7;
  }
LABEL_89:
  (*((void (__fastcall **)(_QWORD))v39 + 3))(*((_QWORD *)v39 + 1));
  result = (unsigned int)v8;
  *((_BYTE *)v4 + 52) = 0;
  return result;
}

```

## disassembly

```asm
0x1400342bc  mov     [rsp+arg_0], rcx
0x1400342c1  push    rbx
0x1400342c2  push    rbp
0x1400342c3  push    rsi
0x1400342c4  push    r12
0x1400342c6  push    r13
0x1400342c8  push    r14
0x1400342ca  push    r15
0x1400342cc  sub     rsp, 0E0h
0x1400342d3  mov     rbx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400342da  mov     r12, rdx
0x1400342dd  mov     r15, rcx
0x1400342e0  mov     [rsp+118h+var_D0], rbx
0x1400342e5  xor     edx, edx; Val
0x1400342e7  lea     rcx, [rsp+118h+var_C8]; void *
0x1400342ec  mov     r8d, 90h; Size
0x1400342f2  call    memset
0x1400342f7  mov     byte ptr [r15+34h], 1
0x1400342fc  mov     rax, [rbx+20h]
0x140034300  mov     rcx, [rbx+8]
0x140034304  mov     qword ptr [rsp+118h+Interval], 0
0x14003430d  call    _guard_dispatch_icall
0x140034312  mov     rcx, r15; this
0x140034315  call    ?Reference@VMX_DISK_DEVICE@@QEAAJXZ; VMX_DISK_DEVICE::Reference(void)
0x14003431a  mov     ebx, eax
0x14003431c  test    eax, eax
0x14003431e  jns     short loc_140034369
0x140034320  mov     rcx, cs:WPP_GLOBAL_Control
0x140034327  lea     rbp, WPP_GLOBAL_Control
0x14003432e  cmp     rcx, rbp
0x140034331  jz      loc_1400347BF
0x140034337  bt      dword ptr [rcx+2Ch], 8
0x14003433c  jnb     loc_1400347BF
0x140034342  cmp     byte ptr [rcx+29h], 2
0x140034346  jb      loc_1400347BF
0x14003434c  mov     edx, 20h ; ' '
0x140034351  mov     r9d, eax
0x140034354  mov     rcx, [rcx+18h]
0x140034358  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003435f  call    WPP_SF_d
0x140034364  jmp     loc_1400347BF
0x140034369  mov     rdx, r12; InputBuffer
0x14003436c  mov     rcx, r15; this
0x14003436f  call    ?SetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::SetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX *)
0x140034374  mov     rcx, r15; this
0x140034377  mov     ebx, eax
0x140034379  call    ?Dereference@VMX_DISK_DEVICE@@QEAAXXZ; VMX_DISK_DEVICE::Dereference(void)
0x14003437e  test    eax, eax
0x140034380  jns     short loc_1400343B5
0x140034382  mov     rcx, cs:WPP_GLOBAL_Control
0x140034389  lea     rbp, WPP_GLOBAL_Control
0x140034390  cmp     rcx, rbp
0x140034393  jz      loc_1400347BF
0x140034399  bt      dword ptr [rcx+2Ch], 8
0x14003439e  jnb     loc_1400347BF
0x1400343a4  cmp     byte ptr [rcx+29h], 2
0x1400343a8  jb      loc_1400347BF
0x1400343ae  mov     edx, 21h ; '!'
0x1400343b3  jmp     short loc_140034351
0x1400343b5  mov     eax, [r12]
0x1400343b9  xor     r13d, r13d
0x1400343bc  test    eax, eax
0x1400343be  jnz     short loc_1400343F3
0x1400343c0  mov     r8d, [r12+4]
0x1400343c5  xor     edx, edx
0x1400343c7  test    r8d, r8d
0x1400343ca  jz      short loc_140034441
0x1400343cc  lea     rcx, [rdx+rdx*8]
0x1400343d0  add     rcx, rcx
0x1400343d3  movzx   eax, byte ptr [r12+rcx*8+50h]
0x1400343d9  cmp     al, 0Fh
0x1400343db  ja      short loc_1400343E7
0x1400343dd  mov     ecx, 8021h
0x1400343e2  bt      ecx, eax
0x1400343e5  jb      short loc_1400343EA
0x1400343e7  inc     r13d
0x1400343ea  inc     edx
0x1400343ec  cmp     edx, r8d
0x1400343ef  jb      short loc_1400343CC
0x1400343f1  jmp     short loc_140034441
0x1400343f3  cmp     eax, 1
0x1400343f6  jnz     short loc_140034441
0x1400343f8  mov     r8d, [r12+4]
0x1400343fd  xor     edx, edx
0x1400343ff  test    r8d, r8d
0x140034402  jz      short loc_140034441
0x140034404  lea     rcx, [rdx+rdx*8]
0x140034408  add     rcx, rcx
0x14003440b  mov     rax, [r12+rcx*8+50h]
0x140034410  sub     rax, qword ptr cs:PARTITION_ENTRY_UNUSED_GUID.Data1
0x140034417  jnz     short loc_140034425
0x140034419  mov     rax, [r12+rcx*8+58h]
0x14003441e  sub     rax, qword ptr cs:PARTITION_ENTRY_UNUSED_GUID.Data4
0x140034425  xor     ecx, ecx
0x140034427  test    rax, rax
0x14003442a  lea     eax, [r13+1]
0x14003442e  setz    cl
0x140034431  test    ecx, ecx
0x140034433  cmovnz  eax, r13d
0x140034437  inc     edx
0x140034439  mov     r13d, eax
0x14003443c  cmp     edx, r8d
0x14003443f  jb      short loc_140034404
0x140034441  mov     eax, 88h
0x140034446  mov     r8d, 20206D56h
0x14003444c  mov     edx, eax
0x14003444e  mov     qword ptr [rsp+118h+arg_18], rax
0x140034456  lea     ecx, [rax+7Ah]
0x140034459  call    cs:__imp_ExAllocatePool2
0x140034460  nop     dword ptr [rax+rax+00h]
0x140034465  mov     r14, rax
0x140034468  test    rax, rax
0x14003446b  jnz     short loc_1400344AA
0x14003446d  mov     r9d, 0C000009Ah
0x140034473  mov     ebx, r9d
0x140034476  mov     rcx, cs:WPP_GLOBAL_Control
0x14003447d  lea     rbp, WPP_GLOBAL_Control
0x140034484  cmp     rcx, rbp
0x140034487  jz      loc_1400347BF
0x14003448d  bt      dword ptr [rcx+2Ch], 8
0x140034492  jnb     loc_1400347BF
0x140034498  cmp     byte ptr [rcx+29h], 2
0x14003449c  jb      loc_1400347BF
0x1400344a2  lea     edx, [rax+22h]
0x1400344a5  jmp     loc_140034354
0x1400344aa  mov     qword ptr [rsp+118h+Interval], 0FFFFFFFFFFFE7960h
0x1400344b3  lea     rbp, WPP_GLOBAL_Control
0x1400344ba  xor     eax, eax
0x1400344bc  mov     [rsp+118h+arg_10], eax
0x1400344c3  cmp     eax, 0Ah
0x1400344c6  jnb     loc_1400347AE
0x1400344cc  mov     rcx, r15; this
0x1400344cf  call    ?Reference@VMX_DISK_DEVICE@@QEAAJXZ; VMX_DISK_DEVICE::Reference(void)
0x1400344d4  mov     ebx, eax
0x1400344d6  test    eax, eax
0x1400344d8  js      loc_14003476F
0x1400344de  mov     rcx, r15; this
0x1400344e1  call    ?Dereference@VMX_DISK_DEVICE@@QEAAXXZ; VMX_DISK_DEVICE::Dereference(void)
0x1400344e6  mov     rax, qword ptr [rsp+118h+arg_18]
0x1400344ee  xor     r9d, r9d; InputBufferLength
0x1400344f1  mov     rcx, [r15+18h]; DeviceObject
0x1400344f5  xor     r8d, r8d; InputBuffer
0x1400344f8  mov     [rsp+118h+var_E8], 1; BOOLEAN
0x1400344fd  mov     edx, 704190h; IoControlCode
0x140034502  mov     [rsp+118h+var_F0], eax; ULONG
0x140034506  mov     [rsp+118h+var_F8], r14; PVOID
0x14003450b  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140034510  mov     ebx, eax
0x140034512  test    eax, eax
0x140034514  jns     loc_1400345A3
0x14003451a  xor     edx, edx; Tag
0x14003451c  mov     rcx, r14; P
0x14003451f  cmp     eax, 80000005h
0x140034524  jnz     loc_140034743
0x14003452a  mov     eax, [r14]
0x14003452d  lea     ebx, ds:8[rax*8]
0x140034534  mov     qword ptr [rsp+118h+arg_18], rbx
0x14003453c  call    cs:__imp_ExFreePoolWithTag
0x140034543  nop     dword ptr [rax+rax+00h]
0x140034548  mov     edx, ebx
0x14003454a  mov     ecx, 102h
0x14003454f  mov     r8d, 20206D56h
0x140034555  call    cs:__imp_ExAllocatePool2
0x14003455c  nop     dword ptr [rax+rax+00h]
0x140034561  mov     r14, rax
0x140034564  test    rax, rax
0x140034567  jnz     loc_1400344CC
0x14003456d  mov     r9d, 0C000009Ah
0x140034573  mov     ebx, r9d
0x140034576  mov     rcx, cs:WPP_GLOBAL_Control
0x14003457d  cmp     rcx, rbp
0x140034580  jz      loc_1400347BF
0x140034586  bt      dword ptr [rcx+2Ch], 8
0x14003458b  jnb     loc_1400347BF
0x140034591  cmp     byte ptr [rcx+29h], 2
0x140034595  jb      loc_1400347BF
0x14003459b  lea     edx, [rax+25h]
0x14003459e  jmp     loc_140034354
0x1400345a3  cmp     [r14], r13d
0x1400345a6  jnz     loc_1400346B5
0x1400345ac  xor     r15d, r15d
0x1400345af  cmp     r15d, [r14]
0x1400345b2  jnb     loc_1400346EF
0x1400345b8  mov     rcx, [r14+r15*8+8]; DeviceObject
0x1400345bd  lea     rax, [rsp+118h+var_C8]
0x1400345c2  mov     [rsp+118h+var_E8], 0; BOOLEAN
0x1400345c7  xor     r9d, r9d; InputBufferLength
0x1400345ca  mov     [rsp+118h+var_F0], 90h; ULONG
0x1400345d2  xor     r8d, r8d; InputBuffer
0x1400345d5  mov     edx, 70048h; IoControlCode
0x1400345da  mov     [rsp+118h+var_F8], rax; PVOID
0x1400345df  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x1400345e4  mov     ebx, eax
0x1400345e6  test    eax, eax
0x1400345e8  js      loc_140034692
0x1400345ee  mov     r9d, [r12+4]
0x1400345f3  xor     r8d, r8d
0x1400345f6  test    r9d, r9d
0x1400345f9  jz      short loc_14003465C
0x1400345fb  mov     r10, [rsp+118h+var_A8]
0x140034600  mov     r11, [rsp+118h+var_B8]
0x140034605  mov     rax, [rsp+118h+var_C0]
0x14003460a  lea     rcx, [r8+r8*8]
0x14003460e  shl     rcx, 4
0x140034612  cmp     rax, [rcx+r12+38h]
0x140034617  jnz     short loc_140034654
0x140034619  cmp     r11, [rcx+r12+40h]
0x14003461e  jnz     short loc_140034654
0x140034620  mov     eax, [rcx+r12+30h]
0x140034625  cmp     [rsp+118h+var_C8], eax
0x140034629  jnz     short loc_140034654
0x14003462b  test    eax, eax
0x14003462d  jnz     short loc_140034636
0x14003462f  cmp     r10b, [rcx+r12+50h]
0x140034634  jmp     short loc_140034652
0x140034636  cmp     eax, 1
0x140034639  jnz     short loc_140034661
0x14003463b  mov     rdx, r10
0x14003463e  sub     rdx, [rcx+r12+50h]
0x140034643  jnz     short loc_14003464F
0x140034645  mov     rdx, [rsp+118h+var_A0]
0x14003464a  sub     rdx, [rcx+r12+58h]
0x14003464f  test    rdx, rdx
0x140034652  jz      short loc_140034661
0x140034654  inc     r8d
0x140034657  cmp     r8d, r9d
0x14003465a  jb      short loc_140034605
0x14003465c  cmp     r8d, r9d
0x14003465f  jz      short loc_140034669
0x140034661  inc     r15d
0x140034664  jmp     loc_1400345AF
0x140034669  mov     r8d, 0C0380037h
0x14003466f  mov     ebx, r8d
0x140034672  mov     rcx, cs:WPP_GLOBAL_Control
0x140034679  cmp     rcx, rbp
0x14003467c  jz      short loc_1400346EF
0x14003467e  bt      dword ptr [rcx+2Ch], 8
0x140034683  jnb     short loc_1400346EF
0x140034685  cmp     byte ptr [rcx+29h], 2
0x140034689  jb      short loc_1400346EF
0x14003468b  mov     edx, 27h ; '''
0x140034690  jmp     short loc_1400346DC
0x140034692  mov     rcx, cs:WPP_GLOBAL_Control
0x140034699  cmp     rcx, rbp
0x14003469c  jz      short loc_1400346EF
0x14003469e  bt      dword ptr [rcx+2Ch], 8
0x1400346a3  jnb     short loc_1400346EF
0x1400346a5  cmp     byte ptr [rcx+29h], 2
0x1400346a9  jb      short loc_1400346EF
0x1400346ab  mov     edx, 26h ; '&'
0x1400346b0  mov     r9d, eax
0x1400346b3  jmp     short loc_1400346DF
0x1400346b5  mov     r8d, 0C0380037h
0x1400346bb  mov     ebx, r8d
0x1400346be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400346c5  cmp     rcx, rbp
0x1400346c8  jz      short loc_1400346EF
0x1400346ca  bt      dword ptr [rcx+2Ch], 8
0x1400346cf  jnb     short loc_1400346EF
0x1400346d1  cmp     byte ptr [rcx+29h], 2
0x1400346d5  jb      short loc_1400346EF
0x1400346d7  mov     edx, 28h ; '('
0x1400346dc  mov     r9d, r8d
0x1400346df  mov     rcx, [rcx+18h]
0x1400346e3  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x1400346ea  call    WPP_SF_d
0x1400346ef  xor     r15d, r15d
0x1400346f2  cmp     [r14], r15d
0x1400346f5  jbe     short loc_140034710
0x1400346f7  mov     rcx, [r14+r15*8+8]; Object
0x1400346fc  call    cs:__imp_ObfDereferenceObject
0x140034703  nop     dword ptr [rax+rax+00h]
0x140034708  inc     r15d
0x14003470b  cmp     r15d, [r14]
0x14003470e  jb      short loc_1400346F7
0x140034710  test    ebx, ebx
0x140034712  jns     loc_1400347A6
0x140034718  lea     r8, [rsp+118h+Interval]; Interval
0x14003471d  xor     edx, edx; Alertable
0x14003471f  xor     ecx, ecx; WaitMode
0x140034721  call    cs:__imp_KeDelayExecutionThread
0x140034728  nop     dword ptr [rax+rax+00h]
0x14003472d  mov     eax, [rsp+118h+arg_10]
0x140034734  mov     r15, [rsp+118h+arg_0]
0x14003473c  inc     eax
0x14003473e  jmp     loc_1400344BC
0x140034743  call    cs:__imp_ExFreePoolWithTag
0x14003474a  nop     dword ptr [rax+rax+00h]
0x14003474f  mov     rcx, cs:WPP_GLOBAL_Control
0x140034756  cmp     rcx, rbp
0x140034759  jz      short loc_1400347BF
0x14003475b  bt      dword ptr [rcx+2Ch], 8
0x140034760  jnb     short loc_1400347BF
0x140034762  cmp     byte ptr [rcx+29h], 2
0x140034766  jb      short loc_1400347BF
0x140034768  mov     edx, 24h ; '$'
0x14003476d  jmp     short loc_14003479E
0x14003476f  xor     edx, edx; Tag
0x140034771  mov     rcx, r14; P
0x140034774  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
