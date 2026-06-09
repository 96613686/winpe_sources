# SdpRemoveFileFromList(_LIST_ENTRY *,ushort const *)

- ea: `0x1800076a4`
- end: `0x180007797`
- name: `?SdpRemoveFileFromList@@YAJPEAU_LIST_ENTRY@@PEBG@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000787c`

## callees

- `0x1800012a4`
- `0x1800076a4`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800076fd`
- `msvcrt!_wcsicmp` at `0x1800076fd`
- `KERNEL32!GetProcessHeap` at `0x18000776d`
- `KERNEL32!GetProcessHeap` at `0x18000776d`
- `KERNEL32!HeapFree` at `0x18000777b`
- `KERNEL32!HeapFree` at `0x18000777b`

## string_xrefs

- `0x180007720`: `SdpRemoveFileFromList`

## pseudocode

```c
__int64 __fastcall SdpRemoveFileFromList(struct _LIST_ENTRY *a1, const unsigned __int16 *a2)
{
  int v4; // r9d
  unsigned int v5; // r8d
  unsigned int v6; // edi
  struct _LIST_ENTRY *Flink; // rbx
  int v8; // eax
  struct _LIST_ENTRY *v9; // rcx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v12; // rcx
  HANDLE ProcessHeap; // rax

  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = 1329;
    v6 = -2147024809;
LABEL_11:
    SdpDebugTrace(1u, L"SdpRemoveFileFromList", v5, v4);
    return v6;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 1330;
    v6 = -2147024809;
    goto LABEL_11;
  }
  Flink = a1->Flink;
  if ( a1->Flink == a1 )
  {
LABEL_9:
    v6 = -2143551225;
    v5 = 1355;
LABEL_10:
    v4 = v6;
    goto LABEL_11;
  }
  while ( 1 )
  {
    if ( !Flink )
    {
      v6 = -2147467261;
      v5 = 1338;
      goto LABEL_10;
    }
    v8 = _wcsicmp(a2, (const wchar_t *)Flink[1].Flink);
    v9 = Flink->Flink;
    if ( !v8 )
      break;
    Flink = Flink->Flink;
    if ( v9 == a1 )
      goto LABEL_9;
  }
  if ( v9->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
    __fastfail(3u);
  Blink->Flink = v9;
  v6 = 0;
  v9->Blink = Blink;
  v12 = Flink[1].Flink;
  if ( v12 )
  {
    operator delete(v12);
    Flink[1].Flink = 0;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, Flink);
  return v6;
}

```

## disassembly

```asm
0x1800076a4  mov     [rsp+arg_0], rbx
0x1800076a9  mov     [rsp+arg_8], rsi
0x1800076ae  push    rdi
0x1800076af  sub     rsp, 20h
0x1800076b3  mov     rsi, rdx
0x1800076b6  mov     rdi, rcx
0x1800076b9  test    rcx, rcx
0x1800076bc  jnz     short loc_1800076CF
0x1800076be  mov     r9d, 80070057h
0x1800076c4  mov     r8d, 531h
0x1800076ca  mov     edi, r9d
0x1800076cd  jmp     short loc_180007720
0x1800076cf  test    rsi, rsi
0x1800076d2  jnz     short loc_1800076E5
0x1800076d4  mov     r9d, 80070057h
0x1800076da  mov     r8d, 532h
0x1800076e0  mov     edi, r9d
0x1800076e3  jmp     short loc_180007720
0x1800076e5  mov     rbx, [rcx]
0x1800076e8  cmp     rbx, rdi
0x1800076eb  jz      short loc_180007712
0x1800076ed  test    rbx, rbx
0x1800076f0  jz      loc_18000778A
0x1800076f6  mov     rdx, [rbx+10h]; String2
0x1800076fa  mov     rcx, rsi; String1
0x1800076fd  call    cs:__imp__wcsicmp
0x180007703  mov     rcx, [rbx]
0x180007706  test    eax, eax
0x180007708  jz      short loc_180007743
0x18000770a  mov     rbx, rcx
0x18000770d  cmp     rcx, rdi
0x180007710  jnz     short loc_1800076ED
0x180007712  mov     edi, 803C0107h
0x180007717  mov     r8d, 54Bh; int
0x18000771d  mov     r9d, edi; int
0x180007720  lea     rdx, aSdpremovefilef; "SdpRemoveFileFromList"
0x180007727  mov     ecx, 1; Level
0x18000772c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007731  mov     rbx, [rsp+28h+arg_0]
0x180007736  mov     eax, edi
0x180007738  mov     rsi, [rsp+28h+arg_8]
0x18000773d  add     rsp, 20h
0x180007741  pop     rdi
0x180007742  retn
0x180007743  cmp     [rcx+8], rbx
0x180007747  jnz     short loc_180007783
0x180007749  mov     rax, [rbx+8]
0x18000774d  cmp     [rax], rbx
0x180007750  jnz     short loc_180007783
0x180007752  mov     [rax], rcx
0x180007755  xor     edi, edi
0x180007757  mov     [rcx+8], rax
0x18000775b  mov     rcx, [rbx+10h]; Block
0x18000775f  test    rcx, rcx
0x180007762  jz      short loc_18000776D
0x180007764  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007769  mov     [rbx+10h], rdi
0x18000776d  call    cs:__imp_GetProcessHeap
0x180007773  mov     r8, rbx; lpMem
0x180007776  xor     edx, edx; dwFlags
0x180007778  mov     rcx, rax; hHeap
0x18000777b  call    cs:__imp_HeapFree
0x180007781  jmp     short loc_180007731
0x180007783  mov     ecx, 3
0x180007788  int     29h; Win8: RtlFailFast(ecx)
0x18000778a  mov     edi, 80004003h
0x18000778f  mov     r8d, 53Ah
0x180007795  jmp     short loc_18000771D
```
