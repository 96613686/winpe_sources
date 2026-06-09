# CommonDllUnInit(long *)

- ea: `0x18000d864`
- end: `0x18000d8cd`
- name: `?CommonDllUnInit@@YAXPEAJ@Z`
- size: `105`
- prototype: `void __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a5b0`

## callees

- `0x18000d864`
- `0x18000db28`
- `0x18000ee9c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d887`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d887`

## pseudocode

```c
void __fastcall CommonDllUnInit(int *a1)
{
  CActiveThreadList *v1; // rbx
  int i; // edi

  v1 = g_pActiveThreadList;
  if ( g_pActiveThreadList )
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( *((_DWORD *)v1 + 1) <= 1u )
        break;
      Sleep(0x3E8u);
      v1 = g_pActiveThreadList;
    }
    if ( v1 )
    {
      CActiveThreadList::~CActiveThreadList(v1);
      operator delete(v1);
    }
  }
  g_pActiveThreadList = 0;
  _InterlockedDecrement(&g_ctrkwks);
}

```

## disassembly

```asm
0x18000d864  mov     [rsp+arg_0], rbx
0x18000d869  push    rdi
0x18000d86a  sub     rsp, 20h
0x18000d86e  mov     rbx, cs:g_pActiveThreadList
0x18000d875  test    rbx, rbx
0x18000d878  jz      short loc_18000D8B0
0x18000d87a  xor     edi, edi
0x18000d87c  cmp     dword ptr [rbx+4], 1
0x18000d880  jbe     short loc_18000D89B
0x18000d882  mov     ecx, 3E8h; dwMilliseconds
0x18000d887  call    cs:__imp_Sleep
0x18000d88d  mov     rbx, cs:g_pActiveThreadList
0x18000d894  inc     edi
0x18000d896  cmp     edi, 5
0x18000d899  jl      short loc_18000D87C
0x18000d89b  test    rbx, rbx
0x18000d89e  jz      short loc_18000D8B0
0x18000d8a0  mov     rcx, rbx; this
0x18000d8a3  call    ??1CActiveThreadList@@QEAA@XZ; CActiveThreadList::~CActiveThreadList(void)
0x18000d8a8  mov     rcx, rbx; Block
0x18000d8ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d8b0  mov     rbx, [rsp+28h+arg_0]
0x18000d8b5  mov     cs:g_pActiveThreadList, 0
0x18000d8c0  lock dec cs:?g_ctrkwks@@3JA; long g_ctrkwks
0x18000d8c7  add     rsp, 20h
0x18000d8cb  pop     rdi
0x18000d8cc  retn
```
