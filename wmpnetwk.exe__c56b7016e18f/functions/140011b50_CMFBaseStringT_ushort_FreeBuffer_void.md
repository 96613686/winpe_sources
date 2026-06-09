# CMFBaseStringT<ushort>::_FreeBuffer(void)

- ea: `0x140011b50`
- end: `0x140011bae`
- name: `?_FreeBuffer@?$CMFBaseStringT@G@@IEAAXXZ`
- size: `94`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140011930`
- `0x140011bb4`
- `0x140012b30`
- `0x140013288`

## callees

- `0x140011b50`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140011b72`
- `KERNEL32!GetProcessHeap` at `0x140011b72`
- `KERNEL32!HeapFree` at `0x140011b80`
- `KERNEL32!HeapFree` at `0x140011b80`
- `ole32!CoTaskMemFree` at `0x140011ba6`
- `ole32!CoTaskMemFree` at `0x140011ba6`

## pseudocode

```c
__int64 __fastcall CMFBaseStringT<unsigned short>::_FreeBuffer(unsigned int *a1)
{
  __int64 result; // rax
  void *v3; // rdi
  int v4; // eax
  HANDLE ProcessHeap; // rax

  result = *a1;
  if ( (result & 1) == 0 )
  {
    v3 = (void *)*((_QWORD *)a1 + 2);
    if ( v3 )
    {
      v4 = *a1 & 6;
      if ( v4 )
      {
        if ( v4 == 2 )
          CoTaskMemFree(*((LPVOID *)a1 + 2));
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
      }
    }
    *a1 &= 0xFFFFFFF9;
    result = 0;
    *((_QWORD *)a1 + 2) = 0;
    *((_QWORD *)a1 + 1) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140011b50  push    rbx
0x140011b52  sub     rsp, 20h
0x140011b56  mov     eax, [rcx]
0x140011b58  mov     rbx, rcx
0x140011b5b  test    al, 1
0x140011b5d  jnz     short loc_140011B98
0x140011b5f  mov     [rsp+28h+arg_0], rdi
0x140011b64  mov     rdi, [rcx+10h]
0x140011b68  test    rdi, rdi
0x140011b6b  jz      short loc_140011B86
0x140011b6d  and     eax, 6
0x140011b70  jnz     short loc_140011B9E
0x140011b72  call    cs:__imp_GetProcessHeap
0x140011b78  mov     r8, rdi; lpMem
0x140011b7b  xor     edx, edx; dwFlags
0x140011b7d  mov     rcx, rax; hHeap
0x140011b80  call    cs:__imp_HeapFree
0x140011b86  and     dword ptr [rbx], 0FFFFFFF9h
0x140011b89  mov     rdi, [rsp+28h+arg_0]
0x140011b8e  xor     eax, eax
0x140011b90  mov     [rbx+10h], rax
0x140011b94  mov     [rbx+8], rax
0x140011b98  add     rsp, 20h
0x140011b9c  pop     rbx
0x140011b9d  retn
0x140011b9e  cmp     eax, 2
0x140011ba1  jnz     short loc_140011B86
0x140011ba3  mov     rcx, rdi; pv
0x140011ba6  call    cs:__imp_CoTaskMemFree
0x140011bac  jmp     short loc_140011B86
```
