# PtDeviceControl

- ea: `0x140009b60`
- end: `0x140009d41`
- name: `PtDeviceControl`
- size: `481`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b2d0`

## callees

- `0x14000173c`
- `0x1400017e8`
- `0x140001a80`
- `0x140009b60`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140009bcb`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140009bcb`
- `ntoskrnl!IofCompleteRequest` at `0x140009bed`
- `ntoskrnl!IofCompleteRequest` at `0x140009c6b`
- `ntoskrnl!IofCompleteRequest` at `0x140009bed`
- `ntoskrnl!IofCompleteRequest` at `0x140009c6b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140009c88`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140009c88`

## pseudocode

```c
__int64 __fastcall PtDeviceControl(__int64 a1, __int64 a2, int a3)
{
  __int64 v5; // rsi
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // r8d
  unsigned int v9; // ebx
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      16,
      (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
  v5 = *(_QWORD *)(a1 + 64);
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 24), PtDeviceControl, File, 1u, 0x20u);
  *(_QWORD *)(a2 + 56) = 0;
  v9 = v6;
  if ( v6 < 0 )
  {
    *(_DWORD *)(a2 + 48) = v6;
    IofCompleteRequest((PIRP)a2, 0);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = 17;
LABEL_14:
      WPP_RECORDER_SF_sqd(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        v12,
        (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
      return v9;
    }
    return v9;
  }
  if ( !*(_BYTE *)(v5 + 184) || !*(_BYTE *)(v5 + 88) )
    goto LABEL_11;
  v13 = *(_QWORD *)(a2 + 184);
  if ( *(_DWORD *)(v13 + 24) != 2703680 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v8,
        20,
        (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
LABEL_11:
    v9 = -1073741808;
    goto LABEL_12;
  }
  if ( *(_DWORD *)(v13 + 8) >= 4u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v8,
        19,
        (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
    v9 = 0;
    **(_DWORD **)(a2 + 24) = 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v8,
        18,
        (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
    v9 = -1073741306;
  }
  *(_QWORD *)(a2 + 56) = 4;
LABEL_12:
  *(_DWORD *)(a2 + 48) = v9;
  IofCompleteRequest((PIRP)a2, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 24), PtDeviceControl, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = 21;
    goto LABEL_14;
  }
  return v9;
}

```

## disassembly

```asm
0x140009b60  push    rbx
0x140009b62  push    rbp
0x140009b63  push    rsi
0x140009b64  push    rdi
0x140009b65  push    r12
0x140009b67  push    r14
0x140009b69  push    r15
0x140009b6b  sub     rsp, 40h
0x140009b6f  mov     rdi, rdx
0x140009b72  mov     rbp, rcx
0x140009b75  lea     r15, WPP_RECORDER_INITIALIZED
0x140009b7c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009b83  lea     r12, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x140009b8a  jz      short loc_140009BA7
0x140009b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009b93  mov     r9d, 10h
0x140009b99  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009b9e  mov     rcx, [rcx+40h]
0x140009ba2  call    WPP_RECORDER_SF_s
0x140009ba7  mov     rsi, [rbp+40h]
0x140009bab  lea     r8, File; File
0x140009bb2  mov     r9d, 1; Line
0x140009bb8  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140009bc0  lea     rdx, PtDeviceControl; Tag
0x140009bc7  lea     rcx, [rsi+18h]; RemoveLock
0x140009bcb  call    cs:__imp_IoAcquireRemoveLockEx
0x140009bd2  nop     dword ptr [rax+rax+00h]
0x140009bd7  mov     qword ptr [rdi+38h], 0
0x140009bdf  mov     ebx, eax
0x140009be1  test    eax, eax
0x140009be3  jns     short loc_140009C11
0x140009be5  xor     edx, edx; PriorityBoost
0x140009be7  mov     [rdi+30h], eax
0x140009bea  mov     rcx, rdi; Irp
0x140009bed  call    cs:__imp_IofCompleteRequest
0x140009bf4  nop     dword ptr [rax+rax+00h]
0x140009bf9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009c00  jz      loc_140009CC1
0x140009c06  mov     r9d, 11h
0x140009c0c  jmp     loc_140009CA3
0x140009c11  cmp     byte ptr [rsi+0B8h], 0
0x140009c18  jz      short loc_140009C5E
0x140009c1a  cmp     byte ptr [rsi+58h], 0
0x140009c1e  jz      short loc_140009C5E
0x140009c20  mov     rax, [rdi+0B8h]
0x140009c27  mov     ecx, [rax+18h]
0x140009c2a  cmp     ecx, 294140h
0x140009c30  jz      loc_140009CD3
0x140009c36  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009c3d  jz      short loc_140009C5E
0x140009c3f  mov     dword ptr [rsp+78h+var_48], ecx
0x140009c43  mov     r9d, 14h
0x140009c49  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c50  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009c55  mov     rcx, [rcx+40h]
0x140009c59  call    WPP_RECORDER_SF_sD
0x140009c5e  mov     ebx, 0C0000010h
0x140009c63  xor     edx, edx; PriorityBoost
0x140009c65  mov     [rdi+30h], ebx
0x140009c68  mov     rcx, rdi; Irp
0x140009c6b  call    cs:__imp_IofCompleteRequest
0x140009c72  nop     dword ptr [rax+rax+00h]
0x140009c77  mov     r8d, 20h ; ' '; RemlockSize
0x140009c7d  lea     rdx, PtDeviceControl; Tag
0x140009c84  lea     rcx, [rsi+18h]; RemoveLock
0x140009c88  call    cs:__imp_IoReleaseRemoveLockEx
0x140009c8f  nop     dword ptr [rax+rax+00h]
0x140009c94  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009c9b  jz      short loc_140009CC1
0x140009c9d  mov     r9d, 15h
0x140009ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x140009caa  mov     [rsp+78h+var_40], ebx
0x140009cae  mov     [rsp+78h+var_48], rbp
0x140009cb3  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009cb8  mov     rcx, [rcx+40h]
0x140009cbc  call    WPP_RECORDER_SF_sqd
0x140009cc1  mov     eax, ebx
0x140009cc3  add     rsp, 40h
0x140009cc7  pop     r15
0x140009cc9  pop     r14
0x140009ccb  pop     r12
0x140009ccd  pop     rdi
0x140009cce  pop     rsi
0x140009ccf  pop     rbp
0x140009cd0  pop     rbx
0x140009cd1  retn
0x140009cd3  cmp     dword ptr [rax+8], 4
0x140009cd7  jnb     short loc_140009D04
0x140009cd9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009ce0  jz      short loc_140009CFD
0x140009ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ce9  mov     r9d, 12h
0x140009cef  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009cf4  mov     rcx, [rcx+40h]
0x140009cf8  call    WPP_RECORDER_SF_s
0x140009cfd  mov     ebx, 0C0000206h
0x140009d02  jmp     short loc_140009D34
0x140009d04  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009d0b  jz      short loc_140009D28
0x140009d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d14  mov     r9d, 13h
0x140009d1a  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009d1f  mov     rcx, [rcx+40h]
0x140009d23  call    WPP_RECORDER_SF_s
0x140009d28  mov     rax, [rdi+18h]
0x140009d2c  xor     ebx, ebx
0x140009d2e  mov     dword ptr [rax], 0
0x140009d34  mov     qword ptr [rdi+38h], 4
0x140009d3c  jmp     loc_140009C63
```
