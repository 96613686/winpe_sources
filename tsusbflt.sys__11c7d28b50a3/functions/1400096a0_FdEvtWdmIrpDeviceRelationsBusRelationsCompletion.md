# FdEvtWdmIrpDeviceRelationsBusRelationsCompletion

- ea: `0x1400096a0`
- end: `0x140009754`
- name: `FdEvtWdmIrpDeviceRelationsBusRelationsCompletion`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400096a0`
- `0x14000aa30`

## pseudocode

```c
__int64 __fastcall FdEvtWdmIrpDeviceRelationsBusRelationsCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rdi
  __int64 result; // rax
  _QWORD *v6; // rax

  v4 = (_QWORD *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                   WPP_MAIN_CB.Queue.ListEntry.Blink,
                   a3,
                   off_14000F1A0);
  result = 0;
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  if ( *(int *)(a2 + 48) >= 0 )
  {
    if ( *(_QWORD *)(a2 + 56) )
    {
      v6 = (_QWORD *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                       WPP_MAIN_CB.Queue.ListEntry.Blink,
                       v4[2],
                       off_14000F0E0);
      *v6 = a2;
      v6[1] = *v4;
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[190].Flink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        v4[2]);
      return 3221225494LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400096a0  mov     [rsp+arg_0], rbx
0x1400096a5  push    rdi
0x1400096a6  sub     rsp, 20h
0x1400096aa  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400096b1  mov     r9, r8
0x1400096b4  mov     r8, cs:off_14000F1A0
0x1400096bb  mov     rbx, rdx
0x1400096be  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400096c5  mov     rdx, r9
0x1400096c8  mov     rax, [rax+650h]
0x1400096cf  call    _guard_dispatch_icall
0x1400096d4  xor     edx, edx
0x1400096d6  mov     rdi, rax
0x1400096d9  mov     eax, edx
0x1400096db  cmp     [rbx+41h], dl
0x1400096de  jz      short loc_1400096EB
0x1400096e0  mov     rcx, [rbx+0B8h]
0x1400096e7  or      byte ptr [rcx+3], 1
0x1400096eb  cmp     [rbx+30h], edx
0x1400096ee  jl      short loc_140009748
0x1400096f0  cmp     [rbx+38h], rdx
0x1400096f4  jz      short loc_140009748
0x1400096f6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400096fd  mov     r8, cs:off_14000F0E0
0x140009704  mov     rdx, [rdi+10h]
0x140009708  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000970f  mov     rax, [rax+650h]
0x140009716  call    _guard_dispatch_icall
0x14000971b  mov     [rax], rbx
0x14000971e  mov     rcx, [rdi]
0x140009721  mov     [rax+8], rcx
0x140009725  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000972c  mov     rdx, [rdi+10h]
0x140009730  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140009737  mov     rax, [rax+0BE0h]
0x14000973e  call    _guard_dispatch_icall
0x140009743  mov     eax, 0C0000016h
0x140009748  mov     rbx, [rsp+28h+arg_0]
0x14000974d  add     rsp, 20h
0x140009751  pop     rdi
0x140009752  retn
```
