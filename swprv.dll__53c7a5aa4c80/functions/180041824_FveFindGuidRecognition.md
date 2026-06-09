# FveFindGuidRecognition

- ea: `0x180041824`
- end: `0x18004187d`
- name: `FveFindGuidRecognition`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041608`

## callees

- `0x180041824`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x18004185c`
- `ntdll!RtlCompareMemory` at `0x18004185c`

## pseudocode

```c
__int64 __fastcall FveFindGuidRecognition(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  unsigned __int64 v5; // rsi

  v2 = 0;
  if ( a2 >= 0x28 )
  {
    v4 = 0;
    v5 = a2 - 40LL;
    while ( (unsigned int)v4 <= v5 )
    {
      if ( RtlCompareMemory(INFORMATION_OFFSET_GUID, (const void *)(v4 + a1), 0x10u) == 16 )
        return v4 + a1;
      v4 = (unsigned int)(v4 + 1);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180041824  push    rbx
0x180041826  push    rbp
0x180041827  push    rsi
0x180041828  push    rdi
0x180041829  push    r14
0x18004182b  sub     rsp, 20h
0x18004182f  xor     edi, edi
0x180041831  mov     r14, rcx
0x180041834  cmp     edx, 28h ; '('
0x180041837  jb      short loc_18004186F
0x180041839  xor     ebx, ebx
0x18004183b  mov     esi, edx
0x18004183d  sub     rsi, 28h ; '('
0x180041841  mov     eax, ebx
0x180041843  cmp     rax, rsi
0x180041846  ja      short loc_18004186F
0x180041848  lea     rbp, [rbx+r14]
0x18004184c  mov     r8d, 10h; Length
0x180041852  mov     rdx, rbp; Source2
0x180041855  lea     rcx, INFORMATION_OFFSET_GUID; Source1
0x18004185c  call    cs:__imp_RtlCompareMemory
0x180041862  cmp     rax, 10h
0x180041866  jz      short loc_18004186C
0x180041868  inc     ebx
0x18004186a  jmp     short loc_180041841
0x18004186c  mov     rdi, rbp
0x18004186f  mov     rax, rdi
0x180041872  add     rsp, 20h
0x180041876  pop     r14
0x180041878  pop     rdi
0x180041879  pop     rsi
0x18004187a  pop     rbp
0x18004187b  pop     rbx
0x18004187c  retn
```
