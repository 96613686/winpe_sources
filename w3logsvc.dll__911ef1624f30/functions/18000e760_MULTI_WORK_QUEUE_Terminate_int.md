# MULTI_WORK_QUEUE::Terminate(int)

- ea: `0x18000e760`
- end: `0x18000e7c4`
- name: `?Terminate@MULTI_WORK_QUEUE@@QEAAXH@Z`
- size: `100`
- prototype: `void __fastcall(MULTI_WORK_QUEUE *this, BOOL)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b324`
- `0x18000d180`

## callees

- `0x18000e760`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000e7a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000e7a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000e78c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000e78c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000e782`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000e782`

## pseudocode

```c
void __fastcall MULTI_WORK_QUEUE::Terminate(MULTI_WORK_QUEUE *this, BOOL a2)
{
  struct _TP_CLEANUP_GROUP *v3; // rcx
  struct _TP_POOL *v4; // rcx

  if ( *((_DWORD *)this + 3) != 1 )
  {
    _InterlockedExchange((volatile __int32 *)this + 3, 1);
    v3 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 13);
    if ( v3 )
    {
      CloseThreadpoolCleanupGroupMembers(v3, a2, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 13));
      *((_QWORD *)this + 13) = 0;
    }
    v4 = (struct _TP_POOL *)*((_QWORD *)this + 12);
    if ( v4 )
    {
      CloseThreadpool(v4);
      *((_QWORD *)this + 12) = 0;
    }
    if ( *((_DWORD *)this + 22) )
      *((_DWORD *)this + 22) = 0;
  }
}

```

## disassembly

```asm
0x18000e760  push    rbx
0x18000e762  sub     rsp, 20h
0x18000e766  mov     eax, 1
0x18000e76b  mov     rbx, rcx
0x18000e76e  cmp     [rcx+0Ch], eax
0x18000e771  jz      short loc_18000E7BE
0x18000e773  xchg    eax, [rcx+0Ch]
0x18000e776  mov     rcx, [rcx+68h]; ptpcg
0x18000e77a  test    rcx, rcx
0x18000e77d  jz      short loc_18000E79A
0x18000e77f  xor     r8d, r8d; pvCleanupContext
0x18000e782  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000e788  mov     rcx, [rbx+68h]; ptpcg
0x18000e78c  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000e792  mov     qword ptr [rbx+68h], 0
0x18000e79a  mov     rcx, [rbx+60h]; ptpp
0x18000e79e  test    rcx, rcx
0x18000e7a1  jz      short loc_18000E7B1
0x18000e7a3  call    cs:__imp_CloseThreadpool
0x18000e7a9  mov     qword ptr [rbx+60h], 0
0x18000e7b1  cmp     dword ptr [rbx+58h], 0
0x18000e7b5  jz      short loc_18000E7BE
0x18000e7b7  mov     dword ptr [rbx+58h], 0
0x18000e7be  add     rsp, 20h
0x18000e7c2  pop     rbx
0x18000e7c3  retn
```
