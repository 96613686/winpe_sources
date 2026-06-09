# SP_MEM<ulong>::operator=(CTypeWrapper<ulong *>)

- ea: `0x18003ad90`
- end: `0x18003ade4`
- name: `??4?$SP_MEM@K@@QEAAAEAV0@V?$CTypeWrapper@PEAK@@@Z`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## callees

- `0x18003ad90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003adad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003adad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003adc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003adc1`

## pseudocode

```c
void **__fastcall SP_MEM<unsigned long>::operator=(void **a1, void *a2)
{
  void *v2; // rsi
  HANDLE ProcessHeap; // rax
  void **result; // rax

  v2 = *a1;
  if ( *a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  result = a1;
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x18003ad90  mov     [rsp+arg_0], rbx
0x18003ad95  mov     [rsp+arg_8], rsi
0x18003ad9a  push    rdi
0x18003ad9b  sub     rsp, 20h
0x18003ad9f  mov     rsi, [rcx]
0x18003ada2  mov     rbx, rdx
0x18003ada5  mov     rdi, rcx
0x18003ada8  test    rsi, rsi
0x18003adab  jz      short loc_18003ADCD
0x18003adad  call    cs:__imp_GetProcessHeap
0x18003adb4  nop     dword ptr [rax+rax+00h]
0x18003adb9  mov     r8, rsi; lpMem
0x18003adbc  xor     edx, edx; dwFlags
0x18003adbe  mov     rcx, rax; hHeap
0x18003adc1  call    cs:__imp_HeapFree
0x18003adc8  nop     dword ptr [rax+rax+00h]
0x18003adcd  mov     rsi, [rsp+28h+arg_8]
0x18003add2  mov     rax, rdi
0x18003add5  mov     [rdi], rbx
0x18003add8  mov     rbx, [rsp+28h+arg_0]
0x18003addd  add     rsp, 20h
0x18003ade1  pop     rdi
0x18003ade2  retn
```
