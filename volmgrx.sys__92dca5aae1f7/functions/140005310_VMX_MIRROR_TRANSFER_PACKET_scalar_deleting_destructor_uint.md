# VMX_MIRROR_TRANSFER_PACKET::`scalar deleting destructor'(uint)

- ea: `0x140005310`
- end: `0x140005387`
- name: `??_GVMX_MIRROR_TRANSFER_PACKET@@UEAAPEAXI@Z`
- size: `119`
- prototype: `void *__fastcall(PVOID P, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140005310`
- `0x140005390`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005379`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005379`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000533f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000533f`

## pseudocode

```c
VMX_OVERLAP_TRANSFER_PACKET *__fastcall VMX_MIRROR_TRANSFER_PACKET::`scalar deleting destructor'(
        VMX_OVERLAP_TRANSFER_PACKET *P,
        char a2)
{
  char v4; // al
  struct _NPAGED_LOOKASIDE_LIST *DeviceExtension; // rcx

  VMX_OVERLAP_TRANSFER_PACKET::~VMX_OVERLAP_TRANSFER_PACKET(P);
  if ( (a2 & 1) != 0 && P )
  {
    v4 = *((_BYTE *)P + 80);
    switch ( v4 )
    {
      case 1:
        DeviceExtension = (struct _NPAGED_LOOKASIDE_LIST *)WPP_MAIN_CB.DeviceExtension;
        break;
      case 2:
        DeviceExtension = (struct _NPAGED_LOOKASIDE_LIST *)WPP_MAIN_CB.Queue.ListEntry.Flink;
        break;
      case 3:
        DeviceExtension = *(struct _NPAGED_LOOKASIDE_LIST **)&WPP_MAIN_CB.DeviceType;
        break;
      default:
        ExFreePoolWithTag(P, 0);
        return P;
    }
    ExFreeToNPagedLookasideList(DeviceExtension, P);
  }
  return P;
}

```

## disassembly

```asm
0x140005310  mov     [rsp+arg_0], rbx
0x140005315  push    rdi
0x140005316  sub     rsp, 20h
0x14000531a  mov     ebx, edx
0x14000531c  mov     rdi, rcx
0x14000531f  call    ??1VMX_OVERLAP_TRANSFER_PACKET@@UEAA@XZ; VMX_OVERLAP_TRANSFER_PACKET::~VMX_OVERLAP_TRANSFER_PACKET(void)
0x140005324  test    bl, 1
0x140005327  jz      short loc_14000534B
0x140005329  test    rdi, rdi
0x14000532c  jz      short loc_14000534B
0x14000532e  mov     al, [rdi+50h]
0x140005331  cmp     al, 1
0x140005333  jnz     short loc_14000535A
0x140005335  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; Lookaside
0x14000533c  mov     rdx, rdi; Entry
0x14000533f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140005346  nop     dword ptr [rax+rax+00h]
0x14000534b  mov     rbx, [rsp+28h+arg_0]
0x140005350  mov     rax, rdi
0x140005353  add     rsp, 20h
0x140005357  pop     rdi
0x140005358  retn
0x14000535a  cmp     al, 2
0x14000535c  jnz     short loc_140005367
0x14000535e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140005365  jmp     short loc_14000533C
0x140005367  cmp     al, 3
0x140005369  jnz     short loc_140005374
0x14000536b  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType
0x140005372  jmp     short loc_14000533C
0x140005374  xor     edx, edx; Tag
0x140005376  mov     rcx, rdi; P
0x140005379  call    cs:__imp_ExFreePoolWithTag
0x140005380  nop     dword ptr [rax+rax+00h]
0x140005385  jmp     short loc_14000534B
```
