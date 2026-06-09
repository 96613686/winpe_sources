# Free_StringArray(ulong *,ushort * * *)

- ea: `0x14000d2f0`
- end: `0x14000d348`
- name: `?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z`
- size: `88`
- prototype: `void __fastcall(unsigned int *, LPVOID *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000d12c`
- `0x14000d1a4`
- `0x14000d2a4`

## callees

- `0x14000d2f0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d312`
- `ole32!CoTaskMemFree` at `0x14000d32c`
- `ole32!CoTaskMemFree` at `0x14000d312`
- `ole32!CoTaskMemFree` at `0x14000d32c`

## pseudocode

```c
void __fastcall Free_StringArray(unsigned int *a1, LPVOID *a2)
{
  __int64 i; // rbp

  if ( *a2 )
  {
    for ( i = 0; (unsigned int)i < *a1; i = (unsigned int)(i + 1) )
    {
      CoTaskMemFree(*((LPVOID *)*a2 + i));
      *((_QWORD *)*a2 + i) = 0;
    }
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x14000d2f0  push    rbx
0x14000d2f2  push    rbp
0x14000d2f3  push    rsi
0x14000d2f4  push    rdi
0x14000d2f5  sub     rsp, 28h
0x14000d2f9  cmp     qword ptr [rdx], 0
0x14000d2fd  mov     rdi, rdx
0x14000d300  mov     rsi, rcx
0x14000d303  jz      short loc_14000D339
0x14000d305  xor     ebp, ebp
0x14000d307  cmp     [rcx], ebp
0x14000d309  jbe     short loc_14000D329
0x14000d30b  mov     rcx, [rdi]
0x14000d30e  mov     rcx, [rcx+rbp*8]; pv
0x14000d312  call    cs:__imp_CoTaskMemFree
0x14000d318  mov     rax, [rdi]
0x14000d31b  mov     qword ptr [rax+rbp*8], 0
0x14000d323  inc     ebp
0x14000d325  cmp     ebp, [rsi]
0x14000d327  jb      short loc_14000D30B
0x14000d329  mov     rcx, [rdi]; pv
0x14000d32c  call    cs:__imp_CoTaskMemFree
0x14000d332  mov     qword ptr [rdi], 0
0x14000d339  mov     dword ptr [rsi], 0
0x14000d33f  add     rsp, 28h
0x14000d343  pop     rdi
0x14000d344  pop     rsi
0x14000d345  pop     rbp
0x14000d346  pop     rbx
0x14000d347  retn
```
