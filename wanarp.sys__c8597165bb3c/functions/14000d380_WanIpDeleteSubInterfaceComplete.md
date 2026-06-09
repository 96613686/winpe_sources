# WanIpDeleteSubInterfaceComplete

- ea: `0x14000d380`
- end: `0x14000d3dc`
- name: `WanIpDeleteSubInterfaceComplete`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d380`
- `0x140015f60`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14000d3c2`
- `ntoskrnl!ExQueueWorkItem` at `0x14000d3c2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d389`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d389`

## pseudocode

```c
void __fastcall WanIpDeleteSubInterfaceComplete(__int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( KeGetCurrentIrql() )
  {
    *(_QWORD *)(v1 + 192) = v1;
    *(_QWORD *)(v1 + 184) = WanpIpDeleteSubInterfaceCompleteWorkItem;
    *(_QWORD *)(v1 + 168) = 0;
    ExQueueWorkItem((PWORK_QUEUE_ITEM)(v1 + 168), CriticalWorkQueue);
    *(_BYTE *)(v1 + 200) = 1;
  }
  else
  {
    WanpIpDeleteSubInterfaceCompleteWorkItem((_QWORD *)v1);
  }
}

```

## disassembly

```asm
0x14000d380  push    rbx
0x14000d382  sub     rsp, 20h
0x14000d386  mov     rbx, [rcx]
0x14000d389  call    cs:__imp_KeGetCurrentIrql
0x14000d390  nop     dword ptr [rax+rax+00h]
0x14000d395  test    al, al
0x14000d397  jnz     short loc_14000D3A3
0x14000d399  mov     rcx, rbx; Entry
0x14000d39c  call    WanpIpDeleteSubInterfaceCompleteWorkItem
0x14000d3a1  jmp     short loc_14000D3D5
0x14000d3a3  lea     rcx, [rbx+0A8h]; WorkItem
0x14000d3aa  xor     edx, edx; QueueType
0x14000d3ac  lea     rax, WanpIpDeleteSubInterfaceCompleteWorkItem
0x14000d3b3  mov     [rcx+18h], rbx
0x14000d3b7  mov     [rcx+10h], rax
0x14000d3bb  mov     qword ptr [rcx], 0
0x14000d3c2  call    cs:__imp_ExQueueWorkItem
0x14000d3c9  nop     dword ptr [rax+rax+00h]
0x14000d3ce  mov     byte ptr [rbx+0C8h], 1
0x14000d3d5  add     rsp, 20h
0x14000d3d9  pop     rbx
0x14000d3da  retn
```
