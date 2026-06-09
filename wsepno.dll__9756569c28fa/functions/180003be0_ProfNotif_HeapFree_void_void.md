# ProfNotif_HeapFree(void *,void *)

- ea: `0x180003be0`
- end: `0x180003c3d`
- name: `?ProfNotif_HeapFree@@YAJPEAX0@Z`
- size: `93`
- prototype: `__int64 __fastcall(void *lpMem, void *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d50`
- `0x180004d60`
- `0x180004dac`
- `0x180006040`
- `0x180007768`
- `0x180007d30`
- `0x180007de0`
- `0x180007e90`
- `0x1800080a0`
- `0x1800081e0`
- `0x180008510`
- `0x180008648`
- `0x1800087a8`
- `0x18000890c`
- `0x18000b4e8`
- `0x18000c324`
- `0x18000c444`

## callees

- `0x180003be0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c1b`

## pseudocode

```c
__int64 __fastcall ProfNotif_HeapFree(void *lpMem, void *a2)
{
  unsigned int v2; // ebx
  HANDLE ProcessHeap; // rcx
  signed int LastError; // eax

  v2 = 0;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    v2 = -2147418113;
    if ( ProcessHeap )
    {
      v2 = 0;
      if ( !HeapFree(ProcessHeap, 0, lpMem) )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003be0  mov     [rsp+arg_0], rbx
0x180003be5  push    rdi
0x180003be6  sub     rsp, 20h
0x180003bea  xor     ebx, ebx
0x180003bec  mov     rdi, rcx
0x180003bef  test    rcx, rcx
0x180003bf2  jz      short loc_180003C30
0x180003bf4  call    cs:__imp_GetProcessHeap
0x180003bfa  mov     rcx, rax; hHeap
0x180003bfd  mov     ebx, 8000FFFFh
0x180003c02  xor     eax, eax
0x180003c04  test    rcx, rcx
0x180003c07  cmovnz  ebx, eax
0x180003c0a  jz      short loc_180003C30
0x180003c0c  mov     r8, rdi; lpMem
0x180003c0f  xor     edx, edx; dwFlags
0x180003c11  call    cs:__imp_HeapFree
0x180003c17  test    eax, eax
0x180003c19  jnz     short loc_180003C30
0x180003c1b  call    cs:__imp_GetLastError
0x180003c21  mov     ebx, eax
0x180003c23  test    eax, eax
0x180003c25  jle     short loc_180003C30
0x180003c27  movzx   ebx, ax
0x180003c2a  or      ebx, 80070000h
0x180003c30  mov     eax, ebx
0x180003c32  mov     rbx, [rsp+28h+arg_0]
0x180003c37  add     rsp, 20h
0x180003c3b  pop     rdi
0x180003c3c  retn
```
