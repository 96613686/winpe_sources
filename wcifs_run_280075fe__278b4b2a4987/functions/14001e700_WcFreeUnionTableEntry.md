# WcFreeUnionTableEntry

- ea: `0x14001e700`
- end: `0x14001e806`
- name: `WcFreeUnionTableEntry`
- size: `262`
- prototype: `RTL_AVL_FREE_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140001c44`
- `0x14001e700`
- `0x14002ee54`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e7ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e7ee`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e72e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001e72e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e781`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001e781`
- `FLTMGR!FltDeleteContext` at `0x14001e766`
- `FLTMGR!FltDeleteContext` at `0x14001e766`

## pseudocode

```c
void __fastcall WcFreeUnionTableEntry(struct _RTL_AVL_TABLE *Table, _QWORD *Buffer)
{
  __int64 v2; // rdi
  char v4; // r14
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  int v8; // edx

  v2 = Buffer[4];
  if ( (unsigned int)(*(_DWORD *)(v2 + 28) - 2) <= 1 )
  {
    v4 = 0;
    ExAcquireFastMutex((PFAST_MUTEX)(v2 + 200));
    v5 = (_QWORD *)(v2 + 184);
    while ( (_QWORD *)*v5 != v5 )
    {
      v6 = *(_QWORD **)(v2 + 192);
      if ( (_QWORD *)*v6 != v5 || (v7 = (_QWORD *)v6[1], (_QWORD *)*v7 != v6) )
        __fastfail(3u);
      *(_QWORD *)(v2 + 192) = v7;
      *v7 = v5;
      v6[1] = v6;
      *v6 = v6;
      FltDeleteContext(v6);
      ++v4;
    }
    ExReleaseFastMutex((PFAST_MUTEX)(v2 + 200));
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_sDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        9,
        10,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        104,
        v4);
    }
  }
  WcReleaseUnionContext(v2);
  ExFreePoolWithTag(Buffer, 0x63754357u);
}

```

## disassembly

```asm
0x14001e700  push    rbx
0x14001e702  push    rbp
0x14001e703  push    rsi
0x14001e704  push    rdi
0x14001e705  push    r14
0x14001e707  sub     rsp, 40h
0x14001e70b  mov     rdi, [rdx+20h]
0x14001e70f  mov     rsi, rdx
0x14001e712  mov     eax, [rdi+1Ch]
0x14001e715  sub     eax, 2
0x14001e718  cmp     eax, 1
0x14001e71b  ja      loc_14001E7DE
0x14001e721  lea     rbp, [rdi+0C8h]
0x14001e728  xor     r14d, r14d
0x14001e72b  mov     rcx, rbp; FastMutex
0x14001e72e  call    cs:__imp_ExAcquireFastMutex
0x14001e735  nop     dword ptr [rax+rax+00h]
0x14001e73a  lea     rbx, [rdi+0B8h]
0x14001e741  cmp     [rbx], rbx
0x14001e744  jz      short loc_14001E77E
0x14001e746  mov     rcx, [rbx+8]; Context
0x14001e74a  cmp     [rcx], rbx
0x14001e74d  jnz     short loc_14001E777
0x14001e74f  mov     rax, [rcx+8]
0x14001e753  cmp     [rax], rcx
0x14001e756  jnz     short loc_14001E777
0x14001e758  mov     [rbx+8], rax
0x14001e75c  mov     [rax], rbx
0x14001e75f  mov     [rcx+8], rcx
0x14001e763  mov     [rcx], rcx
0x14001e766  call    cs:__imp_FltDeleteContext
0x14001e76d  nop     dword ptr [rax+rax+00h]
0x14001e772  inc     r14d
0x14001e775  jmp     short loc_14001E741
0x14001e777  mov     ecx, 3
0x14001e77c  int     29h; Win8: RtlFailFast(ecx)
0x14001e77e  mov     rcx, rbp; FastMutex
0x14001e781  call    cs:__imp_ExReleaseFastMutex
0x14001e788  nop     dword ptr [rax+rax+00h]
0x14001e78d  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e794  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e79b  jz      short loc_14001E7DE
0x14001e79d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e7a4  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001e7ab  mov     [rsp+68h+var_30], r14d
0x14001e7b0  mov     r9d, 0Ah
0x14001e7b6  mov     [rsp+68h+var_38], 168h
0x14001e7be  mov     dl, 4
0x14001e7c0  mov     [rsp+68h+var_40], rax
0x14001e7c5  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001e7cc  mov     rcx, [rcx+40h]
0x14001e7d0  lea     r8d, [r9-1]
0x14001e7d4  mov     [rsp+68h+var_48], rax
0x14001e7d9  call    WPP_RECORDER_SF_sDD
0x14001e7de  mov     rcx, rdi
0x14001e7e1  call    WcReleaseUnionContext
0x14001e7e6  mov     edx, 63754357h; Tag
0x14001e7eb  mov     rcx, rsi; P
0x14001e7ee  call    cs:__imp_ExFreePoolWithTag
0x14001e7f5  nop     dword ptr [rax+rax+00h]
0x14001e7fa  add     rsp, 40h
0x14001e7fe  pop     r14
0x14001e800  pop     rdi
0x14001e801  pop     rsi
0x14001e802  pop     rbp
0x14001e803  pop     rbx
0x14001e804  retn
```
