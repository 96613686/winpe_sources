# VhdmpiCTLogDeleteBackingStore

- ea: `0x1400a7654`
- end: `0x1400a77db`
- name: `VhdmpiCTLogDeleteBackingStore`
- size: `391`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400a6fa4`
- `0x1400a7078`

## callees

- `0x140020874`
- `0x140023560`
- `0x140035e94`
- `0x1400a7654`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a77a8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a77a8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a76df`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a76df`
- `ntoskrnl!ZwClose` at `0x1400a76fc`
- `ntoskrnl!ZwClose` at `0x1400a76fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a76bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a77c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a76bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a77c3`

## string_xrefs

- `0x1400a769c`: `VhdmpiCTLogDeleteBackingStore`
- `0x1400a7735`: `VhdmpiCTLogDeleteBackingStore`
- `0x1400a7683`: `VhdmpiCTLogDeleteBackingStore called for %p.`
- `0x1400a774e`: `VhdmpiCTLogDeleteBackingStore: File handle closed for file %S. Status=0x%08x`

## pseudocode

```c
void __fastcall VhdmpiCTLogDeleteBackingStore(__int64 a1, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  int v7; // r10d
  __int64 v8; // rdx
  __int64 v9; // r8
  void *v10; // rcx

  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
    TraceEvents(
      "VhdmpiCTLogDeleteBackingStore",
      0x213u,
      4u,
      0x1000u,
      "VhdmpiCTLogDeleteBackingStore called for %p.",
      (const void *)a1);
  v4 = *(void **)(a1 + 4216);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0x68444856u);
    *(_QWORD *)(a1 + 4216) = 0;
  }
  v5 = *(void **)(a1 + 48);
  if ( v5 )
  {
    ObfDereferenceObject(v5);
    *(_QWORD *)(a1 + 48) = 0;
  }
  v6 = *(void **)(a1 + 40);
  if ( v6 )
  {
    ZwClose(v6);
    *(_QWORD *)(a1 + 40) = 0;
    a2 = (unsigned int)dword_140087708;
    if ( (unsigned int)dword_140087708 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
        TraceEvents(
          "VhdmpiCTLogDeleteBackingStore",
          0x22Bu,
          4u,
          0x1000u,
          "VhdmpiCTLogDeleteBackingStore: File handle closed for file %S. Status=0x%08x",
          *(const wchar_t **)(a1 + 32),
          v7);
    }
  }
  VhdmpiFreeFilePath(a1 + 16, a2, a3);
  VhdmpiFreeFilePath(a1, v8, v9);
  v10 = *(void **)(a1 + 32);
  if ( v10 )
  {
    ExFreePoolWithTag(v10, 0x7A444856u);
    *(_QWORD *)(a1 + 32) = 0;
  }
  if ( *(_BYTE *)(a1 + 4352) )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 4224));
    *(_BYTE *)(a1 + 4352) = 0;
  }
  ExFreePoolWithTag((PVOID)a1, 0x68444856u);
}

```

## disassembly

```asm
0x1400a7654  mov     [rsp+arg_0], rbx
0x1400a7659  push    rsi
0x1400a765a  sub     rsp, 40h
0x1400a765e  mov     eax, cs:dword_140087708
0x1400a7664  mov     rbx, rcx
0x1400a7667  mov     esi, 1000h
0x1400a766c  cmp     eax, 4
0x1400a766f  jbe     short loc_1400A76AE
0x1400a7671  mov     edx, esi
0x1400a7673  lea     rcx, dword_140087708
0x1400a767a  call    _tlgKeywordOn
0x1400a767f  test    al, al
0x1400a7681  jz      short loc_1400A76AE
0x1400a7683  lea     rax, aVhdmpictlogdel; "VhdmpiCTLogDeleteBackingStore called fo"...
0x1400a768a  mov     qword ptr [rsp+48h+var_20], rbx; char
0x1400a768f  mov     edx, 213h; int
0x1400a7694  mov     [rsp+48h+var_28], rax; char *
0x1400a7699  mov     r9d, esi; int
0x1400a769c  lea     rcx, aVhdmpictlogdel_1; "VhdmpiCTLogDeleteBackingStore"
0x1400a76a3  mov     r8d, 4; int
0x1400a76a9  call    TraceEvents
0x1400a76ae  mov     rcx, [rbx+1078h]; P
0x1400a76b5  test    rcx, rcx
0x1400a76b8  jz      short loc_1400A76D6
0x1400a76ba  mov     edx, 68444856h; Tag
0x1400a76bf  call    cs:__imp_ExFreePoolWithTag
0x1400a76c6  nop     dword ptr [rax+rax+00h]
0x1400a76cb  mov     qword ptr [rbx+1078h], 0
0x1400a76d6  mov     rcx, [rbx+30h]; Object
0x1400a76da  test    rcx, rcx
0x1400a76dd  jz      short loc_1400A76F3
0x1400a76df  call    cs:__imp_ObfDereferenceObject
0x1400a76e6  nop     dword ptr [rax+rax+00h]
0x1400a76eb  mov     qword ptr [rbx+30h], 0
0x1400a76f3  mov     rcx, [rbx+28h]; Handle
0x1400a76f7  test    rcx, rcx
0x1400a76fa  jz      short loc_1400A7765
0x1400a76fc  call    cs:__imp_ZwClose
0x1400a7703  nop     dword ptr [rax+rax+00h]
0x1400a7708  mov     qword ptr [rbx+28h], 0
0x1400a7710  mov     r10d, eax
0x1400a7713  mov     edx, cs:dword_140087708
0x1400a7719  cmp     edx, 4
0x1400a771c  jbe     short loc_1400A7765
0x1400a771e  mov     rdx, rsi
0x1400a7721  lea     rcx, dword_140087708
0x1400a7728  call    _tlgKeywordOn
0x1400a772d  test    al, al
0x1400a772f  jz      short loc_1400A7765
0x1400a7731  mov     rax, [rbx+20h]
0x1400a7735  lea     rcx, aVhdmpictlogdel_1; "VhdmpiCTLogDeleteBackingStore"
0x1400a773c  mov     [rsp+48h+var_18], r10d
0x1400a7741  mov     edx, 22Bh; int
0x1400a7746  mov     qword ptr [rsp+48h+var_20], rax; char
0x1400a774b  mov     r9d, esi; int
0x1400a774e  lea     rax, aVhdmpictlogdel_0; "VhdmpiCTLogDeleteBackingStore: File han"...
0x1400a7755  mov     r8d, 4; int
0x1400a775b  mov     [rsp+48h+var_28], rax; char *
0x1400a7760  call    TraceEvents
0x1400a7765  lea     rcx, [rbx+10h]
0x1400a7769  call    VhdmpiFreeFilePath
0x1400a776e  mov     rcx, rbx
0x1400a7771  call    VhdmpiFreeFilePath
0x1400a7776  mov     rcx, [rbx+20h]; P
0x1400a777a  test    rcx, rcx
0x1400a777d  jz      short loc_1400A7798
0x1400a777f  mov     edx, 7A444856h; Tag
0x1400a7784  call    cs:__imp_ExFreePoolWithTag
0x1400a778b  nop     dword ptr [rax+rax+00h]
0x1400a7790  mov     qword ptr [rbx+20h], 0
0x1400a7798  cmp     byte ptr [rbx+1100h], 0
0x1400a779f  jz      short loc_1400A77BB
0x1400a77a1  lea     rcx, [rbx+1080h]; Lookaside
0x1400a77a8  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a77af  nop     dword ptr [rax+rax+00h]
0x1400a77b4  mov     byte ptr [rbx+1100h], 0
0x1400a77bb  mov     edx, 68444856h; Tag
0x1400a77c0  mov     rcx, rbx; P
0x1400a77c3  call    cs:__imp_ExFreePoolWithTag
0x1400a77ca  nop     dword ptr [rax+rax+00h]
0x1400a77cf  mov     rbx, [rsp+48h+arg_0]
0x1400a77d4  add     rsp, 40h
0x1400a77d8  pop     rsi
0x1400a77d9  retn
```
