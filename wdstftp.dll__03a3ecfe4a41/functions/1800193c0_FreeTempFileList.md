# FreeTempFileList

- ea: `0x1800193c0`
- end: `0x18001944e`
- name: `FreeTempFileList`
- size: `142`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f278`
- `0x180019188`

## callees

- `0x1800193c0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001940a`
- `KERNEL32!HeapFree` at `0x18001942a`
- `KERNEL32!HeapFree` at `0x18001940a`
- `KERNEL32!HeapFree` at `0x18001942a`
- `KERNEL32!GetProcessHeap` at `0x1800193f6`
- `KERNEL32!GetProcessHeap` at `0x180019416`
- `KERNEL32!GetProcessHeap` at `0x1800193f6`
- `KERNEL32!GetProcessHeap` at `0x180019416`
- `KERNEL32!DeleteFileW` at `0x1800193ea`
- `KERNEL32!DeleteFileW` at `0x1800193ea`

## pseudocode

```c
void __fastcall FreeTempFileList(WCHAR **lpMem)
{
  WCHAR **v1; // rbx
  WCHAR *v2; // rdi
  WCHAR **v3; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax

  if ( lpMem )
  {
    v1 = lpMem;
    do
    {
      v2 = *v1;
      v3 = (WCHAR **)v1[1];
      if ( *v1 )
      {
        DeleteFileW(v2);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
      }
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v1);
      v1 = v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x1800193c0  test    rcx, rcx
0x1800193c3  jz      locret_18001944D
0x1800193c9  mov     [rsp+arg_0], rbx
0x1800193ce  mov     [rsp+arg_8], rsi
0x1800193d3  push    rdi
0x1800193d4  sub     rsp, 20h
0x1800193d8  mov     rbx, rcx
0x1800193db  mov     rdi, [rbx]
0x1800193de  mov     rsi, [rbx+8]
0x1800193e2  test    rdi, rdi
0x1800193e5  jz      short loc_180019416
0x1800193e7  mov     rcx, rdi; lpFileName
0x1800193ea  call    cs:__imp_DeleteFileW
0x1800193f1  nop     dword ptr [rax+rax+00h]
0x1800193f6  call    cs:__imp_GetProcessHeap
0x1800193fd  nop     dword ptr [rax+rax+00h]
0x180019402  mov     r8, rdi; lpMem
0x180019405  xor     edx, edx; dwFlags
0x180019407  mov     rcx, rax; hHeap
0x18001940a  call    cs:__imp_HeapFree
0x180019411  nop     dword ptr [rax+rax+00h]
0x180019416  call    cs:__imp_GetProcessHeap
0x18001941d  nop     dword ptr [rax+rax+00h]
0x180019422  mov     r8, rbx; lpMem
0x180019425  xor     edx, edx; dwFlags
0x180019427  mov     rcx, rax; hHeap
0x18001942a  call    cs:__imp_HeapFree
0x180019431  nop     dword ptr [rax+rax+00h]
0x180019436  mov     rbx, rsi
0x180019439  test    rsi, rsi
0x18001943c  jnz     short loc_1800193DB
0x18001943e  mov     rbx, [rsp+28h+arg_0]
0x180019443  mov     rsi, [rsp+28h+arg_8]
0x180019448  add     rsp, 20h
0x18001944c  pop     rdi
0x18001944d  retn
```
