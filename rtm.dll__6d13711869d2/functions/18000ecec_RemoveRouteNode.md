# RemoveRouteNode

- ea: `0x18000ecec`
- end: `0x18000ee97`
- name: `RemoveRouteNode`
- size: `427`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000ea20`
- `0x18000f780`
- `0x18000fa20`
- `0x1800102d0`

## callees

- `0x18000ecec`
- `0x18001163c`
- `0x180011800`

## import_xrefs

- `ntdll!RtlQueueWorkItem` at `0x18000ee78`
- `ntdll!RtlQueueWorkItem` at `0x18000ee78`
- `KERNEL32!GlobalFree` at `0x18000ede3`
- `KERNEL32!GlobalFree` at `0x18000ede3`

## pseudocode

```c
__int64 __fastcall RemoveRouteNode(char *Context, __int64 *a2)
{
  __int64 v4; // rbp
  char v6; // al
  char *v7; // rcx
  __int64 *v8; // rax
  __int64 **v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rdx
  __int64 **v12; // rax
  __int64 *v13; // rax
  __int64 *v14; // rcx
  __int64 **v15; // rdx
  __int64 *v16; // rcx
  __int64 **v17; // rax
  __int64 **v18; // rax
  __int64 v19; // rcx

  v4 = *((_QWORD *)Context + 33) + 32LL * (*((_DWORD *)a2 + 24) % 0x1Fu);
  if ( !DoEnterSyncList((__int64)Context, v4, 1) )
    return 1450;
  v6 = DoEnterSyncList((__int64)Context, (__int64)(Context + 160), 1);
  v7 = Context;
  if ( !v6 )
  {
LABEL_4:
    LeaveSyncList(v7, v4);
    return 1450;
  }
  if ( !DoEnterSyncList((__int64)Context, (__int64)(Context + 128), 1) )
  {
    LeaveSyncList(Context, Context + 160);
    v7 = Context;
    goto LABEL_4;
  }
  v8 = (__int64 *)a2[2];
  if ( (__int64 *)v8[1] != a2 + 2 )
    goto LABEL_24;
  v9 = (__int64 **)a2[3];
  if ( *v9 != a2 + 2 )
    goto LABEL_24;
  *v9 = v8;
  v8[1] = (__int64)v9;
  if ( (__int64 *)*v8 == v8 )
  {
    v10 = v8 - 2;
    v11 = *(v8 - 2);
    if ( *(__int64 **)(v11 + 8) != v8 - 2 )
      goto LABEL_24;
    v12 = (__int64 **)v10[1];
    if ( *v12 != v10 )
      goto LABEL_24;
    *v12 = (__int64 *)v11;
    *(_QWORD *)(v11 + 8) = v12;
    GlobalFree(v10);
  }
  LeaveSyncList(Context, v4);
  v13 = a2 + 6;
  v14 = (__int64 *)a2[6];
  if ( v14 != a2 + 6 )
  {
    if ( (__int64 *)v14[1] == v13 )
    {
      v15 = (__int64 **)a2[7];
      if ( *v15 == v13 )
      {
        *v15 = v14;
        v14[1] = (__int64)v15;
        goto LABEL_17;
      }
    }
LABEL_24:
    __fastfail(3u);
  }
LABEL_17:
  LeaveSyncList(Context, Context + 160);
  v16 = (__int64 *)*a2;
  if ( *(__int64 **)(*a2 + 8) != a2 )
    goto LABEL_24;
  v17 = (__int64 **)a2[1];
  if ( *v17 != a2 )
    goto LABEL_24;
  *v17 = v16;
  v16[1] = (__int64)v17;
  v18 = (__int64 **)(Context + 144);
  v19 = *((_QWORD *)Context + 18);
  if ( *(char **)(v19 + 8) != Context + 144 )
    goto LABEL_24;
  *a2 = v19;
  a2[1] = (__int64)v18;
  *(_QWORD *)(v19 + 8) = a2;
  *v18 = a2;
  if ( ++*((_DWORD *)Context + 11) == 16 && !_InterlockedIncrement((volatile signed __int32 *)Context + 12) )
    RtlQueueWorkItem(ConsolidateNetNumberListsWI, Context, 0);
  LeaveSyncList(Context, Context + 128);
  return 0;
}

```

## disassembly

```asm
0x18000ecec  push    rbx
0x18000ecee  push    rbp
0x18000ecef  push    rsi
0x18000ecf0  push    rdi
0x18000ecf1  push    r14
0x18000ecf3  sub     rsp, 20h
0x18000ecf7  mov     r8d, [rdx+60h]
0x18000ecfb  mov     rdi, rdx
0x18000ecfe  mov     eax, 8421085h
0x18000ed03  mov     rbx, rcx
0x18000ed06  mul     r8d
0x18000ed09  mov     eax, r8d
0x18000ed0c  sub     eax, edx
0x18000ed0e  shr     eax, 1
0x18000ed10  add     eax, edx
0x18000ed12  shr     eax, 4
0x18000ed15  imul    eax, 1Fh
0x18000ed18  sub     r8d, eax
0x18000ed1b  mov     ebp, r8d
0x18000ed1e  mov     r8b, 1
0x18000ed21  shl     rbp, 5
0x18000ed25  add     rbp, [rcx+108h]
0x18000ed2c  mov     rdx, rbp
0x18000ed2f  call    DoEnterSyncList
0x18000ed34  test    al, al
0x18000ed36  jnz     short loc_18000ED48
0x18000ed38  mov     eax, 5AAh
0x18000ed3d  add     rsp, 20h
0x18000ed41  pop     r14
0x18000ed43  pop     rdi
0x18000ed44  pop     rsi
0x18000ed45  pop     rbp
0x18000ed46  pop     rbx
0x18000ed47  retn
0x18000ed48  lea     rsi, [rbx+0A0h]
0x18000ed4f  mov     r8b, 1
0x18000ed52  mov     rdx, rsi
0x18000ed55  mov     rcx, rbx
0x18000ed58  call    DoEnterSyncList
0x18000ed5d  mov     rcx, rbx
0x18000ed60  test    al, al
0x18000ed62  jnz     short loc_18000ED6E
0x18000ed64  mov     rdx, rbp
0x18000ed67  call    LeaveSyncList
0x18000ed6c  jmp     short loc_18000ED38
0x18000ed6e  lea     r14, [rbx+80h]
0x18000ed75  mov     r8b, 1
0x18000ed78  mov     rdx, r14
0x18000ed7b  call    DoEnterSyncList
0x18000ed80  test    al, al
0x18000ed82  jnz     short loc_18000ED94
0x18000ed84  mov     rdx, rsi
0x18000ed87  mov     rcx, rbx
0x18000ed8a  call    LeaveSyncList
0x18000ed8f  mov     rcx, rbx
0x18000ed92  jmp     short loc_18000ED64
0x18000ed94  lea     rcx, [rdi+10h]
0x18000ed98  mov     rax, [rcx]
0x18000ed9b  cmp     [rax+8], rcx
0x18000ed9f  jnz     loc_18000EE90
0x18000eda5  mov     rdx, [rcx+8]
0x18000eda9  cmp     [rdx], rcx
0x18000edac  jnz     loc_18000EE90
0x18000edb2  mov     [rdx], rax
0x18000edb5  mov     [rax+8], rdx
0x18000edb9  cmp     [rax], rax
0x18000edbc  jnz     short loc_18000EDE9
0x18000edbe  lea     rcx, [rax-10h]; hMem
0x18000edc2  mov     rdx, [rcx]
0x18000edc5  cmp     [rdx+8], rcx
0x18000edc9  jnz     loc_18000EE90
0x18000edcf  mov     rax, [rcx+8]
0x18000edd3  cmp     [rax], rcx
0x18000edd6  jnz     loc_18000EE90
0x18000eddc  mov     [rax], rdx
0x18000eddf  mov     [rdx+8], rax
0x18000ede3  call    cs:__imp_GlobalFree
0x18000ede9  mov     rdx, rbp
0x18000edec  mov     rcx, rbx
0x18000edef  call    LeaveSyncList
0x18000edf4  lea     rax, [rdi+30h]
0x18000edf8  mov     rcx, [rax]
0x18000edfb  cmp     rcx, rax
0x18000edfe  jz      short loc_18000EE1A
0x18000ee00  cmp     [rcx+8], rax
0x18000ee04  jnz     loc_18000EE90
0x18000ee0a  mov     rdx, [rax+8]
0x18000ee0e  cmp     [rdx], rax
0x18000ee11  jnz     short loc_18000EE90
0x18000ee13  mov     [rdx], rcx
0x18000ee16  mov     [rcx+8], rdx
0x18000ee1a  mov     rdx, rsi
0x18000ee1d  mov     rcx, rbx
0x18000ee20  call    LeaveSyncList
0x18000ee25  mov     rcx, [rdi]
0x18000ee28  cmp     [rcx+8], rdi
0x18000ee2c  jnz     short loc_18000EE90
0x18000ee2e  mov     rax, [rdi+8]
0x18000ee32  cmp     [rax], rdi
0x18000ee35  jnz     short loc_18000EE90
0x18000ee37  mov     [rax], rcx
0x18000ee3a  mov     [rcx+8], rax
0x18000ee3e  lea     rax, [rbx+90h]
0x18000ee45  mov     rcx, [rax]
0x18000ee48  cmp     [rcx+8], rax
0x18000ee4c  jnz     short loc_18000EE90
0x18000ee4e  mov     [rdi], rcx
0x18000ee51  mov     [rdi+8], rax
0x18000ee55  mov     [rcx+8], rdi
0x18000ee59  mov     [rax], rdi
0x18000ee5c  inc     dword ptr [rbx+2Ch]
0x18000ee5f  cmp     dword ptr [rbx+2Ch], 10h
0x18000ee63  jnz     short loc_18000EE7E
0x18000ee65  lock inc dword ptr [rbx+30h]
0x18000ee69  jnz     short loc_18000EE7E
0x18000ee6b  xor     r8d, r8d; Flags
0x18000ee6e  lea     rcx, ConsolidateNetNumberListsWI; Function
0x18000ee75  mov     rdx, rbx; Context
0x18000ee78  call    cs:__imp_RtlQueueWorkItem
0x18000ee7e  mov     rdx, r14
0x18000ee81  mov     rcx, rbx
0x18000ee84  call    LeaveSyncList
0x18000ee89  xor     eax, eax
0x18000ee8b  jmp     loc_18000ED3D
0x18000ee90  mov     ecx, 3
0x18000ee95  int     29h; Win8: RtlFailFast(ecx)
```
