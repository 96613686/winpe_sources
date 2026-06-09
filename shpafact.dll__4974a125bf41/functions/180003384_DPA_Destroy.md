# DPA_Destroy

- ea: `0x180003384`
- end: `0x1800033f8`
- name: `DPA_Destroy`
- size: `116`
- prototype: `BOOL __stdcall(HDPA hdpa)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003400`

## callees

- `0x180003384`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033d1`

## pseudocode

```c
BOOL __stdcall DPA_Destroy(HDPA hdpa)
{
  void *v3; // r8
  signed int LastError; // eax

  if ( !hdpa )
    return 1;
  v3 = (void *)*((_QWORD *)hdpa + 1);
  if ( !v3 || HeapFree(*((HANDLE *)hdpa + 2), 0, v3) )
  {
    if ( HeapFree(*((HANDLE *)hdpa + 2), 0, hdpa) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
    return LastError >= 0;
  }
  else
  {
    GetLastError();
    return 0;
  }
}

```

## disassembly

```asm
0x180003384  push    rbx
0x180003386  sub     rsp, 20h
0x18000338a  mov     rbx, rcx
0x18000338d  test    rcx, rcx
0x180003390  jnz     short loc_180003397
0x180003392  lea     eax, [rcx+1]
0x180003395  jmp     short loc_1800033F2
0x180003397  mov     r8, [rcx+8]; lpMem
0x18000339b  test    r8, r8
0x18000339e  jz      short loc_1800033BA
0x1800033a0  mov     rcx, [rcx+10h]; hHeap
0x1800033a4  xor     edx, edx; dwFlags
0x1800033a6  call    cs:__imp_HeapFree
0x1800033ac  test    eax, eax
0x1800033ae  jnz     short loc_1800033BA
0x1800033b0  call    cs:__imp_GetLastError
0x1800033b6  xor     eax, eax
0x1800033b8  jmp     short loc_1800033F2
0x1800033ba  mov     rcx, [rbx+10h]; hHeap
0x1800033be  mov     r8, rbx; lpMem
0x1800033c1  xor     edx, edx; dwFlags
0x1800033c3  call    cs:__imp_HeapFree
0x1800033c9  test    eax, eax
0x1800033cb  jz      short loc_1800033D1
0x1800033cd  xor     eax, eax
0x1800033cf  jmp     short loc_1800033ED
0x1800033d1  call    cs:__imp_GetLastError
0x1800033d7  test    eax, eax
0x1800033d9  jle     short loc_1800033E3
0x1800033db  movzx   eax, ax
0x1800033de  or      eax, 80070000h
0x1800033e3  test    eax, eax
0x1800033e5  mov     ecx, 80004005h
0x1800033ea  cmovns  eax, ecx
0x1800033ed  not     eax
0x1800033ef  shr     eax, 1Fh
0x1800033f2  add     rsp, 20h
0x1800033f6  pop     rbx
0x1800033f7  retn
```
