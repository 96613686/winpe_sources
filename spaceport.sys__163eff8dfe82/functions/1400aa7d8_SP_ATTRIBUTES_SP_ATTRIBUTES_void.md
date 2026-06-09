# SP_ATTRIBUTES::~SP_ATTRIBUTES(void)

- ea: `0x1400aa7d8`
- end: `0x1400aa83a`
- name: `??1SP_ATTRIBUTES@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400a1d08`

## callees

- `0x1400aa7d8`
- `0x1400b9d60`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400aa81b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400aa81b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400aa7e9`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400aa7e9`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400aa806`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400aa806`

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
0x1400aa7d8  push    rbx
0x1400aa7da  sub     rsp, 20h
0x1400aa7de  mov     rbx, rcx
0x1400aa7e1  jmp     short loc_1400AA7F8
0x1400aa7e3  mov     rdx, rax; Buffer
0x1400aa7e6  mov     rcx, rbx; Table
0x1400aa7e9  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400aa7f0  nop     dword ptr [rax+rax+00h]
0x1400aa7f5  mov     rcx, rbx; Table
0x1400aa7f8  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x1400aa7fd  mov     [rsp+28h+RestartKey], 0
0x1400aa806  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400aa80d  nop     dword ptr [rax+rax+00h]
0x1400aa812  test    rax, rax
0x1400aa815  jnz     short loc_1400AA7E3
0x1400aa817  lea     rcx, [rbx+68h]; Resource
0x1400aa81b  call    cs:__imp_ExDeleteResourceLite
0x1400aa822  nop     dword ptr [rax+rax+00h]
0x1400aa827  lea     rcx, [rbx+0D0h]; this
0x1400aa82e  call    ??1SP_WORKITEM@@QEAA@XZ; SP_WORKITEM::~SP_WORKITEM(void)
0x1400aa833  add     rsp, 20h
0x1400aa837  pop     rbx
0x1400aa838  retn
```
