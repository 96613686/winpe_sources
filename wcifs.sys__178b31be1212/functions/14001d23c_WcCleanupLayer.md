# WcCleanupLayer

- ea: `0x14001d23c`
- end: `0x14001d34c`
- name: `WcCleanupLayer`
- size: `272`
- prototype: `void __fastcall(char *P)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000696c`
- `0x14001e6c0`
- `0x140020e60`

## callees

- `0x14001d23c`
- `0x14001d42c`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14001d286`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001d286`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d2ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d31e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d332`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d2ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d31e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d332`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001d296`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001d296`
- `FLTMGR!FltObjectDereference` at `0x14001d2f6`
- `FLTMGR!FltObjectDereference` at `0x14001d2f6`
- `FLTMGR!FltReleaseContext` at `0x14001d2e6`
- `FLTMGR!FltReleaseContext` at `0x14001d2e6`
- `FLTMGR!FltGetInstanceContext` at `0x14001d2cc`
- `FLTMGR!FltGetInstanceContext` at `0x14001d2cc`

## pseudocode

```c
void __fastcall WcCleanupLayer(char *P)
{
  char *v1; // rax
  __int64 v2; // rdx
  char **v4; // rcx
  struct _FLT_INSTANCE *v5; // rcx
  void *v6; // rcx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  v1 = P + 48;
  Context = 0;
  v2 = *((_QWORD *)P + 6);
  if ( *(char **)(v2 + 8) != P + 48 || (v4 = (char **)*((_QWORD *)P + 7), *v4 != v1) )
    __fastfail(3u);
  *v4 = (char *)v2;
  *(_QWORD *)(v2 + 8) = v4;
  if ( *((_QWORD *)P + 8) )
  {
    WcClearDirectoryTable(P);
    RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(P + 72));
    ExDeleteResourceLite(*((PERESOURCE *)P + 8));
    ExFreePoolWithTag(*((PVOID *)P + 8), 0x796C4357u);
  }
  v5 = (struct _FLT_INSTANCE *)*((_QWORD *)P + 5);
  if ( v5 )
  {
    if ( (*((_DWORD *)P + 4) & 8) != 0 )
    {
      FltGetInstanceContext(v5, &Context);
      _InterlockedDecrement((volatile signed __int32 *)Context + 5);
      FltReleaseContext(Context);
      FltObjectDereference(*((PVOID *)P + 5));
    }
    *((_QWORD *)P + 5) = 0;
  }
  v6 = (void *)*((_QWORD *)P + 4);
  if ( v6 && P[20] )
    ExFreePoolWithTag(v6, 0x796C4357u);
  ExFreePoolWithTag(P, 0x796C4357u);
}

```

## disassembly

```asm
0x14001d23c  push    rbx
0x14001d23e  sub     rsp, 20h
0x14001d242  lea     rax, [rcx+30h]
0x14001d246  mov     [rsp+28h+Context], 0
0x14001d24f  mov     rdx, [rax]
0x14001d252  mov     rbx, rcx
0x14001d255  cmp     [rdx+8], rax
0x14001d259  jnz     loc_14001D345
0x14001d25f  mov     rcx, [rax+8]
0x14001d263  cmp     [rcx], rax
0x14001d266  jnz     loc_14001D345
0x14001d26c  mov     [rcx], rdx
0x14001d26f  mov     [rdx+8], rcx
0x14001d273  cmp     qword ptr [rbx+40h], 0
0x14001d278  jz      short loc_14001D2B7
0x14001d27a  mov     rcx, rbx
0x14001d27d  call    WcClearDirectoryTable
0x14001d282  lea     rcx, [rbx+48h]; HashTable
0x14001d286  call    cs:__imp_RtlDeleteHashTable
0x14001d28d  nop     dword ptr [rax+rax+00h]
0x14001d292  mov     rcx, [rbx+40h]; Resource
0x14001d296  call    cs:__imp_ExDeleteResourceLite
0x14001d29d  nop     dword ptr [rax+rax+00h]
0x14001d2a2  mov     rcx, [rbx+40h]; P
0x14001d2a6  mov     edx, 796C4357h; Tag
0x14001d2ab  call    cs:__imp_ExFreePoolWithTag
0x14001d2b2  nop     dword ptr [rax+rax+00h]
0x14001d2b7  mov     rcx, [rbx+28h]; Instance
0x14001d2bb  test    rcx, rcx
0x14001d2be  jz      short loc_14001D30A
0x14001d2c0  mov     eax, [rbx+10h]
0x14001d2c3  test    al, 8
0x14001d2c5  jz      short loc_14001D302
0x14001d2c7  lea     rdx, [rsp+28h+Context]; Context
0x14001d2cc  call    cs:__imp_FltGetInstanceContext
0x14001d2d3  nop     dword ptr [rax+rax+00h]
0x14001d2d8  mov     rax, [rsp+28h+Context]
0x14001d2dd  lock dec dword ptr [rax+14h]
0x14001d2e1  mov     rcx, [rsp+28h+Context]; Context
0x14001d2e6  call    cs:__imp_FltReleaseContext
0x14001d2ed  nop     dword ptr [rax+rax+00h]
0x14001d2f2  mov     rcx, [rbx+28h]; FltObject
0x14001d2f6  call    cs:__imp_FltObjectDereference
0x14001d2fd  nop     dword ptr [rax+rax+00h]
0x14001d302  mov     qword ptr [rbx+28h], 0
0x14001d30a  mov     rcx, [rbx+20h]; P
0x14001d30e  test    rcx, rcx
0x14001d311  jz      short loc_14001D32A
0x14001d313  cmp     byte ptr [rbx+14h], 0
0x14001d317  jz      short loc_14001D32A
0x14001d319  mov     edx, 796C4357h; Tag
0x14001d31e  call    cs:__imp_ExFreePoolWithTag
0x14001d325  nop     dword ptr [rax+rax+00h]
0x14001d32a  mov     edx, 796C4357h; Tag
0x14001d32f  mov     rcx, rbx; P
0x14001d332  call    cs:__imp_ExFreePoolWithTag
0x14001d339  nop     dword ptr [rax+rax+00h]
0x14001d33e  add     rsp, 20h
0x14001d342  pop     rbx
0x14001d343  retn
0x14001d345  mov     ecx, 3
0x14001d34a  int     29h; Win8: RtlFailFast(ecx)
```
