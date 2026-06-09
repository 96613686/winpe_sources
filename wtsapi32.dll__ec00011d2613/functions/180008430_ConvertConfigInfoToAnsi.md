# ConvertConfigInfoToAnsi

- ea: `0x180008430`
- end: `0x180008535`
- name: `ConvertConfigInfoToAnsi`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180002b40`

## callees

- `0x180008430`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000844d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000844d`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000849e`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800084bb`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800084db`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800084fc`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000851d`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000849e`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800084bb`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800084db`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800084fc`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18000851d`

## pseudocode

```c
__int64 __fastcall ConvertConfigInfoToAnsi(__int64 a1, CHAR **a2, _DWORD *a3)
{
  __int64 result; // rax
  CHAR *v7; // rbx

  result = (__int64)LocalAlloc(0x40u, 0x350u);
  v7 = (CHAR *)result;
  if ( result )
  {
    *a3 = 848;
    *(_DWORD *)result = *(_DWORD *)a1;
    *(_DWORD *)(result + 4) = *(_DWORD *)(a1 + 4);
    *(_DWORD *)(result + 8) = *(_DWORD *)(a1 + 8);
    *(_DWORD *)(result + 12) = *(_DWORD *)(a1 + 12);
    *(_DWORD *)(result + 16) = *(_DWORD *)(a1 + 16);
    *(_DWORD *)(result + 20) = *(_DWORD *)(a1 + 20);
    RtlUnicodeToMultiByteN((PCHAR)(result + 24), 0x15u, 0, (PCWCH)(a1 + 24), 0x2Au);
    RtlUnicodeToMultiByteN(v7 + 45, 0x12u, 0, (PCWCH)(a1 + 66), 0x24u);
    RtlUnicodeToMultiByteN(v7 + 63, 0x105u, 0, (PCWCH)(a1 + 102), 0x20Au);
    RtlUnicodeToMultiByteN(v7 + 324, 0x105u, 0, (PCWCH)(a1 + 624), 0x20Au);
    RtlUnicodeToMultiByteN(v7 + 585, 0x105u, 0, (PCWCH)(a1 + 1146), 0x20Au);
    result = 1;
    *a2 = v7;
  }
  return result;
}

```

## disassembly

```asm
0x180008430  push    rbx
0x180008432  push    rsi
0x180008433  push    rdi
0x180008434  push    r14
0x180008436  sub     rsp, 38h
0x18000843a  mov     r14, rdx
0x18000843d  mov     rdi, rcx
0x180008440  mov     edx, 350h; uBytes
0x180008445  mov     ecx, 40h ; '@'; uFlags
0x18000844a  mov     rsi, r8
0x18000844d  call    cs:__imp_LocalAlloc
0x180008453  mov     rbx, rax
0x180008456  test    rax, rax
0x180008459  jz      loc_18000852B
0x18000845f  mov     dword ptr [rsi], 350h
0x180008465  lea     r9, [rdi+18h]; UnicodeString
0x180008469  mov     eax, [rdi]
0x18000846b  lea     rcx, [rbx+18h]; MbString
0x18000846f  mov     [rbx], eax
0x180008471  xor     r8d, r8d; ResultSize
0x180008474  mov     eax, [rdi+4]
0x180008477  mov     [rbx+4], eax
0x18000847a  mov     eax, [rdi+8]
0x18000847d  mov     [rbx+8], eax
0x180008480  lea     edx, [r8+15h]; MbSize
0x180008484  mov     eax, [rdi+0Ch]
0x180008487  mov     [rbx+0Ch], eax
0x18000848a  mov     eax, [rdi+10h]
0x18000848d  mov     [rbx+10h], eax
0x180008490  mov     eax, [rdi+14h]
0x180008493  mov     [rbx+14h], eax
0x180008496  mov     [rsp+58h+UnicodeSize], 2Ah ; '*'; UnicodeSize
0x18000849e  call    cs:__imp_RtlUnicodeToMultiByteN
0x1800084a4  xor     r8d, r8d; ResultSize
0x1800084a7  mov     [rsp+58h+UnicodeSize], 24h ; '$'; UnicodeSize
0x1800084af  lea     r9, [rdi+42h]; UnicodeString
0x1800084b3  lea     rcx, [rbx+2Dh]; MbString
0x1800084b7  lea     edx, [r8+12h]; MbSize
0x1800084bb  call    cs:__imp_RtlUnicodeToMultiByteN
0x1800084c1  mov     esi, 105h
0x1800084c6  mov     [rsp+58h+UnicodeSize], 20Ah; UnicodeSize
0x1800084ce  mov     edx, esi; MbSize
0x1800084d0  lea     r9, [rdi+66h]; UnicodeString
0x1800084d4  lea     rcx, [rbx+3Fh]; MbString
0x1800084d8  xor     r8d, r8d; ResultSize
0x1800084db  call    cs:__imp_RtlUnicodeToMultiByteN
0x1800084e1  lea     r9, [rdi+270h]; UnicodeString
0x1800084e8  mov     [rsp+58h+UnicodeSize], 20Ah; UnicodeSize
0x1800084f0  lea     rcx, [rbx+144h]; MbString
0x1800084f7  xor     r8d, r8d; ResultSize
0x1800084fa  mov     edx, esi; MbSize
0x1800084fc  call    cs:__imp_RtlUnicodeToMultiByteN
0x180008502  lea     r9, [rdi+47Ah]; UnicodeString
0x180008509  mov     [rsp+58h+UnicodeSize], 20Ah; UnicodeSize
0x180008511  lea     rcx, [rbx+249h]; MbString
0x180008518  xor     r8d, r8d; ResultSize
0x18000851b  mov     edx, esi; MbSize
0x18000851d  call    cs:__imp_RtlUnicodeToMultiByteN
0x180008523  mov     eax, 1
0x180008528  mov     [r14], rbx
0x18000852b  add     rsp, 38h
0x18000852f  pop     r14
0x180008531  pop     rdi
0x180008532  pop     rsi
0x180008533  pop     rbx
0x180008534  retn
```
