# CreatePerSessionWin32kCall

- ea: `0x14000b828`
- end: `0x14000b8ec`
- name: `CreatePerSessionWin32kCall`
- size: `196`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400ba080`

## callees

- `0x14000b828`
- `0x14000b8f4`
- `0x140018ea0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b8b3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b8b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b8bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b8bf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b855`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b855`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b86a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b86a`
- `ntoskrnl!PsQueryCurrentApiSetSchema` at `0x14000b837`
- `ntoskrnl!PsQueryCurrentApiSetSchema` at `0x14000b837`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000b8d3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000b8d3`

## pseudocode

```c
__int64 __fastcall CreatePerSessionWin32kCall(__int64 *a1)
{
  __int64 v1; // r14
  int v2; // edi
  struct _EJOB *v3; // rsi
  int v4; // ebx
  void *CurrentApiSetSchema; // [rsp+50h] [rbp+8h] BYREF

  v1 = *a1;
  v2 = 0;
  CurrentApiSetSchema = (void *)PsQueryCurrentApiSetSchema();
  v3 = SetWin32kSilo(&CurrentApiSetSchema);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&gSessionApiSetHostRefCountLock, 0);
  v4 = 0;
  if ( *(_QWORD *)(v1 + 8) )
  {
    do
    {
      v2 = ResolveApiSetHost((struct _Win32kApiSet *)(v1 + 24LL * v4), CurrentApiSetSchema);
      if ( v2 < 0 )
        break;
      ++v4;
    }
    while ( *(_QWORD *)(v1 + 24LL * v4 + 8) );
  }
  ExReleasePushLockExclusiveEx(&gSessionApiSetHostRefCountLock, 0);
  KeLeaveCriticalRegion();
  if ( v3 )
    PsDetachSiloFromCurrentThread(v3);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000b828  push    rbx
0x14000b82a  push    rsi
0x14000b82b  push    rdi
0x14000b82c  push    r14
0x14000b82e  sub     rsp, 28h
0x14000b832  mov     r14, [rcx]
0x14000b835  xor     edi, edi
0x14000b837  call    cs:__imp_PsQueryCurrentApiSetSchema
0x14000b83e  nop     dword ptr [rax+rax+00h]
0x14000b843  lea     rcx, [rsp+48h+arg_0]; void **
0x14000b848  mov     [rsp+48h+arg_0], rax
0x14000b84d  call    ?SetWin32kSilo@@YAPEAU_EJOB@@AEAPEAX@Z; SetWin32kSilo(void * &)
0x14000b852  mov     rsi, rax
0x14000b855  call    cs:__imp_KeEnterCriticalRegion
0x14000b85c  nop     dword ptr [rax+rax+00h]
0x14000b861  xor     edx, edx
0x14000b863  lea     rcx, gSessionApiSetHostRefCountLock
0x14000b86a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b871  nop     dword ptr [rax+rax+00h]
0x14000b876  xor     ebx, ebx
0x14000b878  cmp     [r14+8], rbx
0x14000b87c  jz      short loc_14000B8AA
0x14000b87e  mov     rdx, [rsp+48h+arg_0]; void *
0x14000b883  movsxd  rax, ebx
0x14000b886  lea     rcx, [rax+rax*2]
0x14000b88a  lea     rcx, [r14+rcx*8]; struct _Win32kApiSet *
0x14000b88e  call    ?ResolveApiSetHost@@YAJPEAU_Win32kApiSet@@PEAX@Z; ResolveApiSetHost(_Win32kApiSet *,void *)
0x14000b893  mov     edi, eax
0x14000b895  test    eax, eax
0x14000b897  js      short loc_14000B8AA
0x14000b899  inc     ebx
0x14000b89b  movsxd  rdx, ebx
0x14000b89e  lea     r8, [rdx+rdx*2]
0x14000b8a2  cmp     qword ptr [r14+r8*8+8], 0
0x14000b8a8  jnz     short loc_14000B87E
0x14000b8aa  xor     edx, edx
0x14000b8ac  lea     rcx, gSessionApiSetHostRefCountLock
0x14000b8b3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b8ba  nop     dword ptr [rax+rax+00h]
0x14000b8bf  call    cs:__imp_KeLeaveCriticalRegion
0x14000b8c6  nop     dword ptr [rax+rax+00h]
0x14000b8cb  test    rsi, rsi
0x14000b8ce  jz      short loc_14000B8DF
0x14000b8d0  mov     rcx, rsi
0x14000b8d3  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14000b8da  nop     dword ptr [rax+rax+00h]
0x14000b8df  mov     eax, edi
0x14000b8e1  add     rsp, 28h
0x14000b8e5  pop     r14
0x14000b8e7  pop     rdi
0x14000b8e8  pop     rsi
0x14000b8e9  pop     rbx
0x14000b8ea  retn
```
