# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x18000c75c`
- end: `0x18000c7bb`
- name: `??1?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000c724`
- `0x18000ed10`

## callees

- `0x180009748`
- `0x18000c75c`
- `0x18000c7c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c784`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c784`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c792`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c792`

## pseudocode

```c
void __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  wil::details::shared_buffer::reset((wil::details::shared_buffer *)(a1 + 232));
  if ( *(_BYTE *)(a1 + 64) )
  {
    v2 = *(void **)(a1 + 56);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *(_BYTE *)(a1 + 64) = 0;
  }
  *(_QWORD *)(a1 + 56) = 0;
  _TlgActivityBase<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>,0,5>::~_TlgActivityBase<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>,0,5>((_DWORD *)a1);
}

```

## disassembly

```asm
0x18000c75c  mov     [rsp+arg_0], rbx
0x18000c761  mov     [rsp+arg_8], rsi
0x18000c766  push    rdi
0x18000c767  sub     rsp, 20h
0x18000c76b  mov     rdi, rcx
0x18000c76e  add     rcx, 0E8h; this
0x18000c775  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18000c77a  cmp     byte ptr [rdi+40h], 0
0x18000c77e  jz      short loc_18000C79C
0x18000c780  mov     rbx, [rdi+38h]
0x18000c784  call    cs:__imp_GetProcessHeap
0x18000c78a  mov     r8, rbx; lpMem
0x18000c78d  xor     edx, edx; dwFlags
0x18000c78f  mov     rcx, rax; hHeap
0x18000c792  call    cs:__imp_HeapFree
0x18000c798  mov     byte ptr [rdi+40h], 0
0x18000c79c  mov     rcx, rdi
0x18000c79f  mov     qword ptr [rdi+38h], 0
0x18000c7a7  mov     rbx, [rsp+28h+arg_0]
0x18000c7ac  mov     rsi, [rsp+28h+arg_8]
0x18000c7b1  add     rsp, 20h
0x18000c7b5  pop     rdi
0x18000c7b6  jmp     ??1?$_TlgActivityBase@V?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0A@$04@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>,0,5>::~_TlgActivityBase<wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>,0,5>(void)
```
