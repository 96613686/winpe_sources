# TiAddDeviceToSession

- ea: `0x140002a7c`
- end: `0x140002c76`
- name: `TiAddDeviceToSession`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400015dc`

## callees

- `0x14000173c`
- `0x1400019a8`
- `0x140001a80`
- `0x140002a7c`
- `0x140002e78`
- `0x14000b78c`
- `0x14000b7b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140002af7`
- `ntoskrnl!ExAllocatePool2` at `0x140002af7`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x140002b15`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x140002b15`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140002be9`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140002be9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140002c23`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140002c23`

## pseudocode

```c
__int64 __fastcall TiAddDeviceToSession(int a1, _QWORD *a2, __int64 a3)
{
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  struct _DEVICE_OBJECT *i; // rax
  char *p_SecurityDescriptor; // rbx
  __int64 Pool2; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // edx
  int v14; // r8d
  _QWORD *SystemArgument1; // rax
  int v16; // edx
  int v17; // r8d
  struct _FAST_MUTEX *v18; // rdi
  char *v19; // rcx
  char **v20; // rdx
  unsigned int v21; // ebx
  int v23; // [rsp+20h] [rbp-58h]
  __int64 v24; // [rsp+28h] [rbp-50h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      (__int64)a2,
      a3,
      0x1Fu,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  TiLock();
  for ( i = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Dpc.DeferredContext; ; i = *(struct _DEVICE_OBJECT **)&i->Type )
  {
    if ( i == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DeferredContext )
    {
      Pool2 = ExAllocatePool2(64, 104, 1767142228);
      p_SecurityDescriptor = (char *)Pool2;
      if ( !Pool2 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_s(
            (__int64)WPP_GLOBAL_Control->DeviceExtension,
            v11,
            v12,
            0x21u,
            (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
        goto LABEL_15;
      }
      *(_DWORD *)Pool2 = a1;
      KeInitializeGuardedMutex((PKGUARDED_MUTEX)(Pool2 + 8));
      SystemArgument1 = WPP_MAIN_CB.Dpc.SystemArgument1;
      if ( *(struct _DEVICE_OBJECT **)WPP_MAIN_CB.Dpc.SystemArgument1 == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DeferredContext )
      {
        *((_QWORD *)p_SecurityDescriptor + 9) = WPP_MAIN_CB.Dpc.SystemArgument1;
        *((_QWORD *)p_SecurityDescriptor + 8) = &WPP_MAIN_CB.Dpc.DeferredContext;
        *SystemArgument1 = p_SecurityDescriptor + 64;
        WPP_MAIN_CB.Dpc.SystemArgument1 = p_SecurityDescriptor + 64;
        *((_QWORD *)p_SecurityDescriptor + 11) = p_SecurityDescriptor + 80;
        *((_QWORD *)p_SecurityDescriptor + 10) = p_SecurityDescriptor + 80;
        *((_DWORD *)p_SecurityDescriptor + 24) = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_sq(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            v14,
            32,
            (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
        goto LABEL_15;
      }
LABEL_17:
      __fastfail(3u);
    }
    p_SecurityDescriptor = (char *)&i[-1].SecurityDescriptor;
    if ( LODWORD(i[-1].SecurityDescriptor) == a1 )
      break;
  }
  ++*((_DWORD *)p_SecurityDescriptor + 24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sDq(WPP_GLOBAL_Control->DeviceExtension, v5, v6, v7, v23);
LABEL_15:
  TiUnlock();
  if ( p_SecurityDescriptor )
  {
    v18 = (struct _FAST_MUTEX *)(p_SecurityDescriptor + 8);
    a2[24] = p_SecurityDescriptor;
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(p_SecurityDescriptor + 8));
    v19 = p_SecurityDescriptor + 80;
    v20 = (char **)*((_QWORD *)p_SecurityDescriptor + 11);
    if ( *v20 != p_SecurityDescriptor + 80 )
      goto LABEL_17;
    v21 = 0;
    a2[25] = v19;
    a2[26] = v20;
    *v20 = (char *)(a2 + 25);
    *((_QWORD *)v19 + 1) = a2 + 25;
    KeReleaseGuardedMutex(v18);
  }
  else
  {
    v21 = -1073741670;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v16,
      v17,
      0x23u,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids,
      v24);
  return v21;
}

```

## disassembly

```asm
0x140002a7c  push    rbx
0x140002a7e  push    rbp
0x140002a7f  push    rsi
0x140002a80  push    rdi
0x140002a81  push    r14
0x140002a83  push    r15
0x140002a85  sub     rsp, 48h
0x140002a89  mov     rsi, rdx
0x140002a8c  mov     edi, ecx
0x140002a8e  lea     rbp, WPP_RECORDER_INITIALIZED
0x140002a95  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002a9c  lea     r15, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x140002aa3  jz      short loc_140002AC0
0x140002aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140002aac  mov     r9d, 1Fh
0x140002ab2  mov     [rsp+78h+var_58], r15
0x140002ab7  mov     rcx, [rcx+40h]
0x140002abb  call    WPP_RECORDER_SF_s
0x140002ac0  call    TiLock
0x140002ac5  mov     rax, cs:WPP_MAIN_CB.Dpc.DeferredContext
0x140002acc  lea     r14, WPP_MAIN_CB.Dpc.DeferredContext
0x140002ad3  jmp     short loc_140002AE4
0x140002ad5  lea     rbx, [rax-40h]
0x140002ad9  cmp     [rbx], edi
0x140002adb  jz      loc_140002B83
0x140002ae1  mov     rax, [rax]
0x140002ae4  cmp     rax, r14
0x140002ae7  jnz     short loc_140002AD5
0x140002ae9  mov     edx, 68h ; 'h'
0x140002aee  mov     r8d, 69547354h
0x140002af4  lea     ecx, [rdx-28h]
0x140002af7  call    cs:__imp_ExAllocatePool2
0x140002afe  nop     dword ptr [rax+rax+00h]
0x140002b03  mov     rbx, rax
0x140002b06  test    rax, rax
0x140002b09  jz      loc_140002BAD
0x140002b0f  lea     rcx, [rax+8]; Mutex
0x140002b13  mov     [rax], edi
0x140002b15  call    cs:__imp_KeInitializeGuardedMutex
0x140002b1c  nop     dword ptr [rax+rax+00h]
0x140002b21  mov     rax, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x140002b28  cmp     [rax], r14
0x140002b2b  jnz     loc_140002C02
0x140002b31  lea     rcx, [rbx+40h]
0x140002b35  mov     [rcx+8], rax
0x140002b39  mov     [rcx], r14
0x140002b3c  mov     [rax], rcx
0x140002b3f  lea     rax, [rbx+50h]
0x140002b43  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument1, rcx
0x140002b4a  mov     [rax+8], rax
0x140002b4e  mov     [rax], rax
0x140002b51  mov     dword ptr [rbx+60h], 1
0x140002b58  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002b5f  jz      short loc_140002BD1
0x140002b61  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b68  mov     r9d, 20h ; ' '
0x140002b6e  mov     [rsp+78h+var_48], rbx
0x140002b73  mov     [rsp+78h+var_58], r15
0x140002b78  mov     rcx, [rcx+40h]
0x140002b7c  call    WPP_RECORDER_SF_sq
0x140002b81  jmp     short loc_140002BD1
0x140002b83  inc     dword ptr [rbx+60h]
0x140002b86  mov     eax, [rbx+60h]
0x140002b89  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002b90  jz      short loc_140002BD1
0x140002b92  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b99  mov     [rsp+78h+var_40], rbx
0x140002b9e  mov     dword ptr [rsp+78h+var_48], eax
0x140002ba2  mov     rcx, [rcx+40h]
0x140002ba6  call    WPP_RECORDER_SF_sDq
0x140002bab  jmp     short loc_140002BD1
0x140002bad  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002bb4  jz      short loc_140002BD1
0x140002bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140002bbd  mov     r9d, 21h ; '!'
0x140002bc3  mov     [rsp+78h+var_58], r15
0x140002bc8  mov     rcx, [rcx+40h]
0x140002bcc  call    WPP_RECORDER_SF_s
0x140002bd1  call    TiUnlock
0x140002bd6  test    rbx, rbx
0x140002bd9  jz      short loc_140002C31
0x140002bdb  lea     rdi, [rbx+8]
0x140002bdf  mov     [rsi+0C0h], rbx
0x140002be6  mov     rcx, rdi; Mutex
0x140002be9  call    cs:__imp_KeAcquireGuardedMutex
0x140002bf0  nop     dword ptr [rax+rax+00h]
0x140002bf5  lea     rcx, [rbx+50h]
0x140002bf9  mov     rdx, [rcx+8]
0x140002bfd  cmp     [rdx], rcx
0x140002c00  jz      short loc_140002C09
0x140002c02  mov     ecx, 3
0x140002c07  int     29h; Win8: RtlFailFast(ecx)
0x140002c09  lea     rax, [rsi+0C8h]
0x140002c10  xor     ebx, ebx
0x140002c12  mov     [rax], rcx
0x140002c15  mov     [rax+8], rdx
0x140002c19  mov     [rdx], rax
0x140002c1c  mov     [rcx+8], rax
0x140002c20  mov     rcx, rdi; Mutex
0x140002c23  call    cs:__imp_KeReleaseGuardedMutex
0x140002c2a  nop     dword ptr [rax+rax+00h]
0x140002c2f  jmp     short loc_140002C36
0x140002c31  mov     ebx, 0C000009Ah
0x140002c36  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140002c3d  jz      short loc_140002C66
0x140002c3f  mov     rcx, [rsi]
0x140002c42  mov     r9d, 23h ; '#'
0x140002c48  mov     dword ptr [rsp+78h+var_40], ebx
0x140002c4c  mov     [rsp+78h+var_48], rcx
0x140002c51  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c58  mov     [rsp+78h+var_58], r15
0x140002c5d  mov     rcx, [rcx+40h]
0x140002c61  call    WPP_RECORDER_SF_sqd
0x140002c66  mov     eax, ebx
0x140002c68  add     rsp, 48h
0x140002c6c  pop     r15
0x140002c6e  pop     r14
0x140002c70  pop     rdi
0x140002c71  pop     rsi
0x140002c72  pop     rbp
0x140002c73  pop     rbx
0x140002c74  retn
```
