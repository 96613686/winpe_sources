# DPA_Destroy

- ea: `0x180007ab0`
- end: `0x180007b24`
- name: `DPA_Destroy`
- size: `116`
- prototype: `BOOL __stdcall(HDPA hdpa)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800060a8`
- `0x180007b30`

## callees

- `0x180007ab0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ad2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ad2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007afd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007afd`

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
0x180007ab0  push    rbx
0x180007ab2  sub     rsp, 20h
0x180007ab6  mov     rbx, rcx
0x180007ab9  test    rcx, rcx
0x180007abc  jnz     short loc_180007AC3
0x180007abe  lea     eax, [rcx+1]
0x180007ac1  jmp     short loc_180007B1E
0x180007ac3  mov     r8, [rcx+8]; lpMem
0x180007ac7  test    r8, r8
0x180007aca  jz      short loc_180007AE6
0x180007acc  mov     rcx, [rcx+10h]; hHeap
0x180007ad0  xor     edx, edx; dwFlags
0x180007ad2  call    cs:__imp_HeapFree
0x180007ad8  test    eax, eax
0x180007ada  jnz     short loc_180007AE6
0x180007adc  call    cs:__imp_GetLastError
0x180007ae2  xor     eax, eax
0x180007ae4  jmp     short loc_180007B1E
0x180007ae6  mov     rcx, [rbx+10h]; hHeap
0x180007aea  mov     r8, rbx; lpMem
0x180007aed  xor     edx, edx; dwFlags
0x180007aef  call    cs:__imp_HeapFree
0x180007af5  test    eax, eax
0x180007af7  jz      short loc_180007AFD
0x180007af9  xor     eax, eax
0x180007afb  jmp     short loc_180007B19
0x180007afd  call    cs:__imp_GetLastError
0x180007b03  test    eax, eax
0x180007b05  jle     short loc_180007B0F
0x180007b07  movzx   eax, ax
0x180007b0a  or      eax, 80070000h
0x180007b0f  test    eax, eax
0x180007b11  mov     ecx, 80004005h
0x180007b16  cmovns  eax, ecx
0x180007b19  not     eax
0x180007b1b  shr     eax, 1Fh
0x180007b1e  add     rsp, 20h
0x180007b22  pop     rbx
0x180007b23  retn
```
