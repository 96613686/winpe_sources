# FreeFileRestoreEventInfo

- ea: `0x140071328`
- end: `0x140071431`
- name: `FreeFileRestoreEventInfo`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400736b0`

## callees

- `0x140071328`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140071355`
- `ole32!CoTaskMemFree` at `0x140071372`
- `ole32!CoTaskMemFree` at `0x140071389`
- `ole32!CoTaskMemFree` at `0x1400713a0`
- `ole32!CoTaskMemFree` at `0x1400713b7`
- `ole32!CoTaskMemFree` at `0x1400713ce`
- `ole32!CoTaskMemFree` at `0x1400713e5`
- `ole32!CoTaskMemFree` at `0x1400713fc`
- `ole32!CoTaskMemFree` at `0x140071413`
- `ole32!CoTaskMemFree` at `0x140071355`
- `ole32!CoTaskMemFree` at `0x140071372`
- `ole32!CoTaskMemFree` at `0x140071389`
- `ole32!CoTaskMemFree` at `0x1400713a0`
- `ole32!CoTaskMemFree` at `0x1400713b7`
- `ole32!CoTaskMemFree` at `0x1400713ce`
- `ole32!CoTaskMemFree` at `0x1400713e5`
- `ole32!CoTaskMemFree` at `0x1400713fc`
- `ole32!CoTaskMemFree` at `0x140071413`

## pseudocode

```c
void __fastcall FreeFileRestoreEventInfo(__int64 a1)
{
  __int64 i; // rdi
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  if ( *(_QWORD *)(a1 + 64) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 60); i = (unsigned int)(i + 1) )
    {
      v3 = *(void **)(*(_QWORD *)(a1 + 64) + 8 * i);
      if ( v3 )
      {
        CoTaskMemFree(v3);
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * i) = 0;
      }
    }
    CoTaskMemFree(*(LPVOID *)(a1 + 64));
    *(_QWORD *)(a1 + 64) = 0;
  }
  v4 = *(void **)(a1 + 72);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *(_QWORD *)(a1 + 72) = 0;
  }
  v5 = *(void **)(a1 + 80);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *(_QWORD *)(a1 + 80) = 0;
  }
  v6 = *(void **)(a1 + 88);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *(_QWORD *)(a1 + 88) = 0;
  }
  v7 = *(void **)(a1 + 96);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *(_QWORD *)(a1 + 96) = 0;
  }
  v8 = *(void **)(a1 + 104);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *(_QWORD *)(a1 + 104) = 0;
  }
  v9 = *(void **)(a1 + 112);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *(_QWORD *)(a1 + 112) = 0;
  }
  v10 = *(void **)(a1 + 120);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *(_QWORD *)(a1 + 120) = 0;
  }
}

```

## disassembly

```asm
0x140071328  mov     [rsp+arg_0], rbx
0x14007132d  mov     [rsp+arg_8], rsi
0x140071332  push    rdi
0x140071333  sub     rsp, 20h
0x140071337  cmp     qword ptr [rcx+40h], 0
0x14007133c  mov     rbx, rcx
0x14007133f  jz      short loc_140071380
0x140071341  xor     edi, edi
0x140071343  cmp     [rcx+3Ch], edi
0x140071346  jbe     short loc_14007136E
0x140071348  mov     rax, [rbx+40h]
0x14007134c  mov     rcx, [rax+rdi*8]; pv
0x140071350  test    rcx, rcx
0x140071353  jz      short loc_140071367
0x140071355  call    cs:__imp_CoTaskMemFree
0x14007135b  mov     rax, [rbx+40h]
0x14007135f  mov     qword ptr [rax+rdi*8], 0
0x140071367  inc     edi
0x140071369  cmp     edi, [rbx+3Ch]
0x14007136c  jb      short loc_140071348
0x14007136e  mov     rcx, [rbx+40h]; pv
0x140071372  call    cs:__imp_CoTaskMemFree
0x140071378  mov     qword ptr [rbx+40h], 0
0x140071380  mov     rcx, [rbx+48h]; pv
0x140071384  test    rcx, rcx
0x140071387  jz      short loc_140071397
0x140071389  call    cs:__imp_CoTaskMemFree
0x14007138f  mov     qword ptr [rbx+48h], 0
0x140071397  mov     rcx, [rbx+50h]; pv
0x14007139b  test    rcx, rcx
0x14007139e  jz      short loc_1400713AE
0x1400713a0  call    cs:__imp_CoTaskMemFree
0x1400713a6  mov     qword ptr [rbx+50h], 0
0x1400713ae  mov     rcx, [rbx+58h]; pv
0x1400713b2  test    rcx, rcx
0x1400713b5  jz      short loc_1400713C5
0x1400713b7  call    cs:__imp_CoTaskMemFree
0x1400713bd  mov     qword ptr [rbx+58h], 0
0x1400713c5  mov     rcx, [rbx+60h]; pv
0x1400713c9  test    rcx, rcx
0x1400713cc  jz      short loc_1400713DC
0x1400713ce  call    cs:__imp_CoTaskMemFree
0x1400713d4  mov     qword ptr [rbx+60h], 0
0x1400713dc  mov     rcx, [rbx+68h]; pv
0x1400713e0  test    rcx, rcx
0x1400713e3  jz      short loc_1400713F3
0x1400713e5  call    cs:__imp_CoTaskMemFree
0x1400713eb  mov     qword ptr [rbx+68h], 0
0x1400713f3  mov     rcx, [rbx+70h]; pv
0x1400713f7  test    rcx, rcx
0x1400713fa  jz      short loc_14007140A
0x1400713fc  call    cs:__imp_CoTaskMemFree
0x140071402  mov     qword ptr [rbx+70h], 0
0x14007140a  mov     rcx, [rbx+78h]; pv
0x14007140e  test    rcx, rcx
0x140071411  jz      short loc_140071421
0x140071413  call    cs:__imp_CoTaskMemFree
0x140071419  mov     qword ptr [rbx+78h], 0
0x140071421  mov     rbx, [rsp+28h+arg_0]
0x140071426  mov     rsi, [rsp+28h+arg_8]
0x14007142b  add     rsp, 20h
0x14007142f  pop     rdi
0x140071430  retn
```
