# PipeCompleteIrpList

- ea: `0x140002e70`
- end: `0x140002ebc`
- name: `PipeCompleteIrpList`
- size: `76`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002000`
- `0x140002b60`
- `0x140002d20`
- `0x140015c50`
- `0x140015f50`

## callees

- `0x140002e70`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002ea0`
- `ntoskrnl!IofCompleteRequest` at `0x140002ea0`

## pseudocode

```c
void __fastcall PipeCompleteIrpList(_QWORD **a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rax

  while ( 1 )
  {
    v2 = *a1;
    if ( *a1 == a1 )
      break;
    if ( (_QWORD **)v2[1] != a1 || (v3 = (_QWORD *)*v2, *(_QWORD **)(*v2 + 8LL) != v2) )
      __fastfail(3u);
    *a1 = v3;
    v3[1] = a1;
    IofCompleteRequest((PIRP)(v2 - 17), 0);
  }
}

```

## disassembly

```asm
0x140002e70  push    rbx
0x140002e72  sub     rsp, 20h
0x140002e76  mov     rbx, rcx
0x140002e79  mov     rcx, [rbx]
0x140002e7c  cmp     rcx, rbx
0x140002e7f  jz      short loc_140002EB5
0x140002e81  cmp     [rcx+8], rbx
0x140002e85  jnz     short loc_140002EAE
0x140002e87  mov     rax, [rcx]
0x140002e8a  cmp     [rax+8], rcx
0x140002e8e  jnz     short loc_140002EAE
0x140002e90  mov     [rbx], rax
0x140002e93  add     rcx, 0FFFFFFFFFFFFFF78h; Irp
0x140002e9a  xor     edx, edx; PriorityBoost
0x140002e9c  mov     [rax+8], rbx
0x140002ea0  call    cs:__imp_IofCompleteRequest
0x140002ea7  nop     dword ptr [rax+rax+00h]
0x140002eac  jmp     short loc_140002E79
0x140002eae  mov     ecx, 3
0x140002eb3  int     29h; Win8: RtlFailFast(ecx)
0x140002eb5  add     rsp, 20h
0x140002eb9  pop     rbx
0x140002eba  retn
```
