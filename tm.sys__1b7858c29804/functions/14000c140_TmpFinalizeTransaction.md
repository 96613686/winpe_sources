# TmpFinalizeTransaction

- ea: `0x14000c140`
- end: `0x14000c30e`
- name: `TmpFinalizeTransaction`
- size: `462`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c010`
- `0x140010c70`
- `0x14001102c`
- `0x140011ab4`
- `0x14001a2e0`
- `0x14001b594`

## callees

- `0x14000c140`
- `0x140016584`

## import_xrefs

- `CLFS!CLFS_LSN_NULL` at `0x14000c21c`
- `CLFS!ClfsLsnContainer` at `0x14000c1d8`
- `CLFS!ClfsLsnContainer` at `0x14000c1ed`
- `CLFS!ClfsLsnContainer` at `0x14000c1d8`
- `CLFS!ClfsLsnContainer` at `0x14000c1ed`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c1a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c1a2`
- `ntoskrnl!KeReleaseMutex` at `0x14000c248`
- `ntoskrnl!KeReleaseMutex` at `0x14000c248`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c2af`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c2f2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c2af`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c2f2`
- `ntoskrnl!ZwClose` at `0x14000c295`
- `ntoskrnl!ZwClose` at `0x14000c295`

## pseudocode

```c
__int64 __fastcall TmpFinalizeTransaction(CLFS_LSN *Object)
{
  bool v2; // r14
  CLFS_LSN v3; // rbp
  char *v4; // rsi
  CLFS_CONTAINER_ID v5; // ebx
  __int64 v6; // rax
  char **ullOffset; // rcx
  CLFS_LSN *v8; // rbx
  CLFS_LSN *v9; // rbp
  void *v10; // rcx
  CLFS_LSN v11; // rcx

  if ( (Object[24].offset.cidContainer & 0x10000000) == 0 )
  {
    v2 = 0;
    _InterlockedOr((volatile signed __int32 *)&Object[24].offset.cidContainer, 0x10000000u);
    if ( (Object[24].offset.cidContainer & 0x800000) != 0 )
    {
      KeWaitForSingleObject((PVOID)(Object[64].ullOffset + 512), Executive, 0, 0, 0);
      if ( (Object[24].offset.cidContainer & 0x800000) != 0 )
      {
        v3 = Object[64];
        v4 = (char *)&Object[61];
        if ( *(CLFS_LSN **)(v3.ullOffset + 568) == &Object[61] )
        {
          v5 = ClfsLsnContainer(Object + 31);
          v2 = v5 > ClfsLsnContainer((const CLFS_LSN *)(v3.ullOffset + 648));
        }
        v6 = *(_QWORD *)v4;
        if ( *(char **)(*(_QWORD *)v4 + 8LL) != v4 || (ullOffset = (char **)Object[62].ullOffset, *ullOffset != v4) )
          __fastfail(3u);
        *ullOffset = (char *)v6;
        *(_QWORD *)(v6 + 8) = ullOffset;
        Object[31] = CLFS_LSN_NULL;
        _InterlockedAnd((volatile signed __int32 *)&Object[24].offset.cidContainer, 0xFF7FFFFF);
      }
      KeReleaseMutex((PRKMUTEX)(Object[64].ullOffset + 512), 0);
    }
    if ( (Object[24].offset.cidContainer & 0x100) != 0 && (Object[24].offset.cidContainer & 0x400) != 0 )
    {
      v8 = (CLFS_LSN *)Object[32].ullOffset;
      while ( v8 != &Object[32] )
      {
        v9 = v8 - 32;
        v8 = (CLFS_LSN *)v8->ullOffset;
        v10 = (void *)v9[86].ullOffset;
        if ( v10 )
        {
          ZwClose(v10);
          v9[86].ullOffset = 0;
        }
        ObfDereferenceObject(v9);
      }
    }
    v11 = Object[64];
    if ( v11.ullOffset )
      LOBYTE(Object[21].offset.idxRecord) = 1;
    LOBYTE(Object[16].offset.idxRecord) = 1;
    if ( v2 && v11.ullOffset )
      TmpQueueCheckpointTm();
    ObfDereferenceObject(Object);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c140  push    rbx
0x14000c142  push    rbp
0x14000c143  push    rsi
0x14000c144  push    rdi
0x14000c145  push    r14
0x14000c147  push    r15
0x14000c149  sub     rsp, 38h
0x14000c14d  mov     eax, [rcx+0C4h]
0x14000c153  mov     rdi, rcx
0x14000c156  mov     ecx, 10000000h
0x14000c15b  test    ecx, eax
0x14000c15d  jnz     loc_14000C2FE
0x14000c163  xor     r14b, r14b
0x14000c166  lock or [rdi+0C4h], ecx
0x14000c16d  mov     eax, [rdi+0C4h]
0x14000c173  mov     r15d, 1
0x14000c179  bt      eax, 17h
0x14000c17d  jnb     loc_14000C254
0x14000c183  mov     rcx, [rdi+200h]
0x14000c18a  xor     r9d, r9d; Alertable
0x14000c18d  add     rcx, 200h; Object
0x14000c194  mov     [rsp+68h+Timeout], 0; Timeout
0x14000c19d  xor     r8d, r8d; WaitMode
0x14000c1a0  xor     edx, edx; WaitReason
0x14000c1a2  call    cs:__imp_KeWaitForSingleObject
0x14000c1a9  nop     dword ptr [rax+rax+00h]
0x14000c1ae  mov     eax, [rdi+0C4h]
0x14000c1b4  bt      eax, 17h
0x14000c1b8  jnb     short loc_14000C238
0x14000c1ba  mov     rbp, [rdi+200h]
0x14000c1c1  lea     rsi, [rdi+1E8h]
0x14000c1c8  cmp     [rbp+238h], rsi
0x14000c1cf  jnz     short loc_14000C203
0x14000c1d1  lea     rcx, [rdi+0F8h]; plsn
0x14000c1d8  call    cs:__imp_ClfsLsnContainer
0x14000c1df  nop     dword ptr [rax+rax+00h]
0x14000c1e4  lea     rcx, [rbp+288h]; plsn
0x14000c1eb  mov     ebx, eax
0x14000c1ed  call    cs:__imp_ClfsLsnContainer
0x14000c1f4  nop     dword ptr [rax+rax+00h]
0x14000c1f9  cmp     ebx, eax
0x14000c1fb  movzx   r14d, r14b
0x14000c1ff  cmova   r14d, r15d
0x14000c203  mov     rax, [rsi]
0x14000c206  cmp     [rax+8], rsi
0x14000c20a  jnz     short loc_14000C278
0x14000c20c  mov     rcx, [rsi+8]
0x14000c210  cmp     [rcx], rsi
0x14000c213  jnz     short loc_14000C278
0x14000c215  mov     [rcx], rax
0x14000c218  mov     [rax+8], rcx
0x14000c21c  mov     rax, cs:__imp_CLFS_LSN_NULL
0x14000c223  mov     rcx, [rax]
0x14000c226  mov     [rdi+0F8h], rcx
0x14000c22d  lock and dword ptr [rdi+0C4h], 0FF7FFFFFh
0x14000c238  mov     rcx, [rdi+200h]
0x14000c23f  xor     edx, edx; Wait
0x14000c241  add     rcx, 200h; Mutex
0x14000c248  call    cs:__imp_KeReleaseMutex
0x14000c24f  nop     dword ptr [rax+rax+00h]
0x14000c254  mov     eax, [rdi+0C4h]
0x14000c25a  bt      eax, 8
0x14000c25e  jnb     short loc_14000C2C0
0x14000c260  mov     eax, [rdi+0C4h]
0x14000c266  bt      eax, 0Ah
0x14000c26a  jnb     short loc_14000C2C0
0x14000c26c  lea     rsi, [rdi+100h]
0x14000c273  mov     rbx, [rsi]
0x14000c276  jmp     short loc_14000C2BB
0x14000c278  mov     ecx, 3
0x14000c27d  int     29h; Win8: RtlFailFast(ecx)
0x14000c27f  lea     rbp, [rbx-100h]
0x14000c286  mov     rbx, [rbx]
0x14000c289  mov     rcx, [rbp+2B0h]; Handle
0x14000c290  test    rcx, rcx
0x14000c293  jz      short loc_14000C2AC
0x14000c295  call    cs:__imp_ZwClose
0x14000c29c  nop     dword ptr [rax+rax+00h]
0x14000c2a1  mov     qword ptr [rbp+2B0h], 0
0x14000c2ac  mov     rcx, rbp; Object
0x14000c2af  call    cs:__imp_ObfDereferenceObject
0x14000c2b6  nop     dword ptr [rax+rax+00h]
0x14000c2bb  cmp     rbx, rsi
0x14000c2be  jnz     short loc_14000C27F
0x14000c2c0  mov     eax, [rdi+0C4h]
0x14000c2c6  mov     rcx, [rdi+200h]
0x14000c2cd  test    rcx, rcx
0x14000c2d0  jz      short loc_14000C2D9
0x14000c2d2  mov     [rdi+0A8h], r15b
0x14000c2d9  mov     [rdi+80h], r15b
0x14000c2e0  test    r14b, r14b
0x14000c2e3  jz      short loc_14000C2EF
0x14000c2e5  test    rcx, rcx
0x14000c2e8  jz      short loc_14000C2EF
0x14000c2ea  call    TmpQueueCheckpointTm
0x14000c2ef  mov     rcx, rdi; Object
0x14000c2f2  call    cs:__imp_ObfDereferenceObject
0x14000c2f9  nop     dword ptr [rax+rax+00h]
0x14000c2fe  xor     eax, eax
0x14000c300  add     rsp, 38h
0x14000c304  pop     r15
0x14000c306  pop     r14
0x14000c308  pop     rdi
0x14000c309  pop     rsi
0x14000c30a  pop     rbp
0x14000c30b  pop     rbx
0x14000c30c  retn
```
