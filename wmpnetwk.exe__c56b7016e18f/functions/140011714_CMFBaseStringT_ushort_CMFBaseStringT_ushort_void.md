# CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)

- ea: `0x140011714`
- end: `0x140011777`
- name: `??1?$CMFBaseStringT@G@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140011d70`
- `0x1400124d0`
- `0x1400357b4`
- `0x14006982c`
- `0x14009c907`

## callees

- `0x140011714`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140011735`
- `KERNEL32!GetProcessHeap` at `0x140011735`
- `KERNEL32!HeapFree` at `0x140011743`
- `KERNEL32!HeapFree` at `0x140011743`
- `ole32!CoTaskMemFree` at `0x14001176f`
- `ole32!CoTaskMemFree` at `0x14001176f`

## pseudocode

```c
void __fastcall CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(__int64 a1)
{
  void *v1; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax

  v1 = *(void **)(a1 + 16);
  if ( v1 && (*(_DWORD *)a1 & 1) == 0 )
  {
    v3 = *(_DWORD *)a1 & 6;
    if ( v3 )
    {
      if ( v3 == 2 )
        CoTaskMemFree(*(LPVOID *)(a1 + 16));
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    *(_DWORD *)a1 &= 0xFFFFFFF9;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x140011714  mov     [rsp+arg_0], rbx
0x140011719  push    rdi
0x14001171a  sub     rsp, 20h
0x14001171e  mov     rdi, [rcx+10h]
0x140011722  mov     rbx, rcx
0x140011725  test    rdi, rdi
0x140011728  jz      short loc_14001175C
0x14001172a  mov     eax, [rcx]
0x14001172c  test    al, 1
0x14001172e  jnz     short loc_14001175C
0x140011730  and     eax, 6
0x140011733  jnz     short loc_140011767
0x140011735  call    cs:__imp_GetProcessHeap
0x14001173b  mov     r8, rdi; lpMem
0x14001173e  xor     edx, edx; dwFlags
0x140011740  mov     rcx, rax; hHeap
0x140011743  call    cs:__imp_HeapFree
0x140011749  and     dword ptr [rbx], 0FFFFFFF9h
0x14001174c  mov     qword ptr [rbx+10h], 0
0x140011754  mov     qword ptr [rbx+8], 0
0x14001175c  mov     rbx, [rsp+28h+arg_0]
0x140011761  add     rsp, 20h
0x140011765  pop     rdi
0x140011766  retn
0x140011767  cmp     eax, 2
0x14001176a  jnz     short loc_140011749
0x14001176c  mov     rcx, rdi; pv
0x14001176f  call    cs:__imp_CoTaskMemFree
0x140011775  jmp     short loc_140011749
```
