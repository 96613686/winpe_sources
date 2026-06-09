# SP_ATTRIBUTES::~SP_ATTRIBUTES(void)

- ea: `0x1400aa638`
- end: `0x1400aa69a`
- name: `??1SP_ATTRIBUTES@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400a1bd8`

## callees

- `0x1400aa638`
- `0x1400b9bc0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400aa67b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400aa67b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400aa649`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400aa649`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400aa666`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400aa666`

## pseudocode

```c
void __fastcall SP_ATTRIBUTES::~SP_ATTRIBUTES(PRTL_AVL_TABLE Table)
{
  PRTL_AVL_TABLE i; // rbx
  PVOID v2; // rax
  PVOID RestartKey; // [rsp+30h] [rbp+8h] BYREF

  for ( i = Table; ; Table = i )
  {
    RestartKey = 0;
    v2 = RtlEnumerateGenericTableWithoutSplayingAvl(Table, &RestartKey);
    if ( !v2 )
      break;
    RtlDeleteElementGenericTableAvl(i, v2);
  }
  ExDeleteResourceLite((PERESOURCE)&i[1]);
  SP_WORKITEM::~SP_WORKITEM((SP_WORKITEM *)&i[2]);
}

```

## disassembly

```asm
0x1400aa638  push    rbx
0x1400aa63a  sub     rsp, 20h
0x1400aa63e  mov     rbx, rcx
0x1400aa641  jmp     short loc_1400AA658
0x1400aa643  mov     rdx, rax; Buffer
0x1400aa646  mov     rcx, rbx; Table
0x1400aa649  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400aa650  nop     dword ptr [rax+rax+00h]
0x1400aa655  mov     rcx, rbx; Table
0x1400aa658  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x1400aa65d  mov     [rsp+28h+RestartKey], 0
0x1400aa666  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400aa66d  nop     dword ptr [rax+rax+00h]
0x1400aa672  test    rax, rax
0x1400aa675  jnz     short loc_1400AA643
0x1400aa677  lea     rcx, [rbx+68h]; Resource
0x1400aa67b  call    cs:__imp_ExDeleteResourceLite
0x1400aa682  nop     dword ptr [rax+rax+00h]
0x1400aa687  lea     rcx, [rbx+0D0h]; this
0x1400aa68e  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400aa693  add     rsp, 20h
0x1400aa697  pop     rbx
0x1400aa698  retn
```
