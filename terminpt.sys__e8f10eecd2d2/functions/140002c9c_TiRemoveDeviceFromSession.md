# TiRemoveDeviceFromSession

- ea: `0x140002c9c`
- end: `0x140002e50`
- name: `TiRemoveDeviceFromSession`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140001724`

## callees

- `0x14000173c`
- `0x1400019a8`
- `0x140002c9c`
- `0x14000b78c`
- `0x14000b7b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002dfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002dfe`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140002cf2`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140002cf2`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140002d94`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140002d94`

## pseudocode

```c
void __fastcall TiRemoveDeviceFromSession(_QWORD *a1, int a2, int a3)
{
  __int64 v3; // rbx
  int v5; // edx
  int v6; // r8d
  char v7; // si
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  int v10; // edx
  int v11; // r8d
  __int64 v13; // rcx
  _QWORD *v14; // rdx

  v3 = a1[24];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      36,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  if ( v3 )
  {
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v3 + 8));
    if ( a1[24] )
    {
      a1[24] = 0;
      v8 = a1[25];
      if ( *(_QWORD **)(v8 + 8) != a1 + 25 )
        goto LABEL_22;
      v9 = (_QWORD *)a1[26];
      if ( (_QWORD *)*v9 != a1 + 25 )
        goto LABEL_22;
      *v9 = v8;
      v7 = 1;
      *(_QWORD *)(v8 + 8) = v9;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sq(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          v6,
          37,
          (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    }
    else
    {
      v7 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_s(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          v6,
          38,
          (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    }
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v3 + 8));
    if ( !v7 )
      goto LABEL_19;
    TiLock();
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sq(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        39,
        (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
    if ( (*(_DWORD *)(v3 + 96))-- != 1 )
      goto LABEL_18;
    v13 = *(_QWORD *)(v3 + 64);
    if ( *(_QWORD *)(v13 + 8) == v3 + 64 )
    {
      v14 = *(_QWORD **)(v3 + 72);
      if ( *v14 == v3 + 64 )
      {
        *v14 = v13;
        *(_QWORD *)(v13 + 8) = v14;
        ExFreePoolWithTag((PVOID)v3, 0x69547354u);
LABEL_18:
        TiUnlock();
        goto LABEL_19;
      }
    }
LABEL_22:
    __fastfail(3u);
  }
LABEL_19:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      40,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
}

```

## disassembly

```asm
0x140002c9c  push    rbx
0x140002c9e  push    rbp
0x140002c9f  push    rsi
0x140002ca0  push    rdi
0x140002ca1  push    r14
0x140002ca3  push    r15
0x140002ca5  sub     rsp, 48h
0x140002ca9  mov     rbx, [rcx+0C0h]
0x140002cb0  mov     rdi, rcx
0x140002cb3  lea     r14, WPP_RECORDER_INITIALIZED
0x140002cba  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002cc1  lea     r15, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x140002cc8  jz      short loc_140002CE5
0x140002cca  mov     rcx, cs:WPP_GLOBAL_Control
0x140002cd1  mov     r9d, 24h ; '$'
0x140002cd7  mov     [rsp+78h+var_58], r15
0x140002cdc  mov     rcx, [rcx+40h]
0x140002ce0  call    WPP_RECORDER_SF_s
0x140002ce5  test    rbx, rbx
0x140002ce8  jz      loc_140002E0F
0x140002cee  lea     rcx, [rbx+8]; Mutex
0x140002cf2  call    cs:__imp_KeAcquireGuardedMutex
0x140002cf9  nop     dword ptr [rax+rax+00h]
0x140002cfe  cmp     qword ptr [rdi+0C0h], 0
0x140002d06  jnz     short loc_140002D31
0x140002d08  xor     sil, sil
0x140002d0b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002d12  jz      short loc_140002D90
0x140002d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d1b  mov     r9d, 26h ; '&'
0x140002d21  mov     [rsp+78h+var_58], r15
0x140002d26  mov     rcx, [rcx+40h]
0x140002d2a  call    WPP_RECORDER_SF_s
0x140002d2f  jmp     short loc_140002D90
0x140002d31  lea     rax, [rdi+0C8h]
0x140002d38  mov     qword ptr [rdi+0C0h], 0
0x140002d43  mov     rdx, [rax]
0x140002d46  cmp     [rdx+8], rax
0x140002d4a  jnz     loc_140002E49
0x140002d50  mov     rcx, [rax+8]
0x140002d54  cmp     [rcx], rax
0x140002d57  jnz     loc_140002E49
0x140002d5d  mov     [rcx], rdx
0x140002d60  mov     sil, 1
0x140002d63  mov     [rdx+8], rcx
0x140002d67  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002d6e  jz      short loc_140002D90
0x140002d70  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d77  mov     r9d, 25h ; '%'
0x140002d7d  mov     [rsp+78h+var_48], rbx
0x140002d82  mov     [rsp+78h+var_58], r15
0x140002d87  mov     rcx, [rcx+40h]
0x140002d8b  call    WPP_RECORDER_SF_sq
0x140002d90  lea     rcx, [rbx+8]; Mutex
0x140002d94  call    cs:__imp_KeReleaseGuardedMutex
0x140002d9b  nop     dword ptr [rax+rax+00h]
0x140002da0  test    sil, sil
0x140002da3  jz      short loc_140002E0F
0x140002da5  call    TiLock
0x140002daa  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002db1  jz      short loc_140002DD3
0x140002db3  mov     rcx, cs:WPP_GLOBAL_Control
0x140002dba  mov     r9d, 27h ; '''
0x140002dc0  mov     [rsp+78h+var_48], rbx
0x140002dc5  mov     [rsp+78h+var_58], r15
0x140002dca  mov     rcx, [rcx+40h]
0x140002dce  call    WPP_RECORDER_SF_sq
0x140002dd3  add     dword ptr [rbx+60h], 0FFFFFFFFh
0x140002dd7  jnz     short loc_140002E0A
0x140002dd9  lea     rax, [rbx+40h]
0x140002ddd  mov     rcx, [rax]
0x140002de0  cmp     [rcx+8], rax
0x140002de4  jnz     short loc_140002E49
0x140002de6  mov     rdx, [rax+8]
0x140002dea  cmp     [rdx], rax
0x140002ded  jnz     short loc_140002E49
0x140002def  mov     [rdx], rcx
0x140002df2  mov     [rcx+8], rdx
0x140002df6  mov     edx, 69547354h; Tag
0x140002dfb  mov     rcx, rbx; P
0x140002dfe  call    cs:__imp_ExFreePoolWithTag
0x140002e05  nop     dword ptr [rax+rax+00h]
0x140002e0a  call    TiUnlock
0x140002e0f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002e16  jz      short loc_140002E3B
0x140002e18  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e1f  mov     r9d, 28h ; '('
0x140002e25  mov     rax, [rdi]
0x140002e28  mov     [rsp+78h+var_48], rax
0x140002e2d  mov     [rsp+78h+var_58], r15
0x140002e32  mov     rcx, [rcx+40h]
0x140002e36  call    WPP_RECORDER_SF_sq
0x140002e3b  add     rsp, 48h
0x140002e3f  pop     r15
0x140002e41  pop     r14
0x140002e43  pop     rdi
0x140002e44  pop     rsi
0x140002e45  pop     rbp
0x140002e46  pop     rbx
0x140002e47  retn
0x140002e49  mov     ecx, 3
0x140002e4e  int     29h; Win8: RtlFailFast(ecx)
```
