# OF_ReadUINT

- ea: `0x1800094e0`
- end: `0x180009576`
- name: `OF_ReadUINT`
- size: `150`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a1c`
- `0x180007f40`
- `0x1800080e0`
- `0x180008bc8`
- `0x180009b98`
- `0x18000b1f0`

## callees

- `0x1800093bc`
- `0x1800094e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009533`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000955c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009533`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000955c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000951f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009546`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000951f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009546`

## pseudocode

```c
__int64 __fastcall OF_ReadUINT(HANDLE *a1, _DWORD *a2)
{
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v6; // rax
  DWORD v7; // [rsp+40h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  lpMem = 0;
  if ( (unsigned int)OF_ReadBinaryData(a1, &lpMem, &v7) )
  {
    if ( v7 == 4 )
    {
      v3 = lpMem;
      *a2 = *(_DWORD *)lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      return 1;
    }
    v6 = GetProcessHeap();
    HeapFree(v6, 0, lpMem);
  }
  return 0;
}

```

## disassembly

```asm
0x1800094e0  mov     rax, rsp
0x1800094e3  mov     [rax+8], rbx
0x1800094e7  push    rdi
0x1800094e8  sub     rsp, 20h
0x1800094ec  mov     rdi, rdx
0x1800094ef  mov     dword ptr [rax+18h], 0
0x1800094f6  lea     rdx, [rax+20h]
0x1800094fa  mov     qword ptr [rax+20h], 0
0x180009502  lea     r8, [rax+18h]
0x180009506  call    OF_ReadBinaryData
0x18000950b  test    eax, eax
0x18000950d  jz      short loc_180009568
0x18000950f  cmp     [rsp+28h+arg_10], 4
0x180009514  jnz     short loc_180009546
0x180009516  mov     rbx, [rsp+28h+lpMem]
0x18000951b  mov     eax, [rbx]
0x18000951d  mov     [rdi], eax
0x18000951f  call    cs:__imp_GetProcessHeap
0x180009526  nop     dword ptr [rax+rax+00h]
0x18000952b  mov     r8, rbx; lpMem
0x18000952e  xor     edx, edx; dwFlags
0x180009530  mov     rcx, rax; hHeap
0x180009533  call    cs:__imp_HeapFree
0x18000953a  nop     dword ptr [rax+rax+00h]
0x18000953f  mov     eax, 1
0x180009544  jmp     short loc_18000956A
0x180009546  call    cs:__imp_GetProcessHeap
0x18000954d  nop     dword ptr [rax+rax+00h]
0x180009552  mov     r8, [rsp+28h+lpMem]; lpMem
0x180009557  xor     edx, edx; dwFlags
0x180009559  mov     rcx, rax; hHeap
0x18000955c  call    cs:__imp_HeapFree
0x180009563  nop     dword ptr [rax+rax+00h]
0x180009568  xor     eax, eax
0x18000956a  mov     rbx, [rsp+28h+arg_0]
0x18000956f  add     rsp, 20h
0x180009573  pop     rdi
0x180009574  retn
```
