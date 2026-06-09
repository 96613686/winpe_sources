# FilterWaitForVariable

- ea: `0x1400057f8`
- end: `0x140005852`
- name: `FilterWaitForVariable`
- size: `90`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003fe8`
- `0x1400041a0`
- `0x140005630`
- `0x14000d690`

## callees

- `0x1400057f8`
- `0x14000cd98`

## import_xrefs

- `NDIS!NdisMSleep` at `0x14000583f`
- `NDIS!NdisMSleep` at `0x14000583f`

## pseudocode

```c
void __fastcall FilterWaitForVariable(_DWORD *a1)
{
  int v1; // ebx

  v1 = 0;
  while ( *a1 )
  {
    if ( (unsigned int)++v1 > 0xBB8 )
      TraceAssert((int)"FALSE", (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c", 180);
    NdisMSleep(0x2710u);
  }
}

```

## disassembly

```asm
0x1400057f8  mov     [rsp+arg_0], rbx
0x1400057fd  push    rdi
0x1400057fe  sub     rsp, 20h
0x140005802  xor     ebx, ebx
0x140005804  mov     rdi, rcx
0x140005807  cmp     [rcx], ebx
0x140005809  jnz     short loc_140005817
0x14000580b  mov     rbx, [rsp+28h+arg_0]
0x140005810  add     rsp, 20h
0x140005814  pop     rdi
0x140005815  retn
0x140005817  inc     ebx
0x140005819  cmp     ebx, 0BB8h
0x14000581f  jbe     short loc_14000583A
0x140005821  mov     r8d, 0B4h
0x140005827  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000582e  lea     rcx, aFalse; "FALSE"
0x140005835  call    TraceAssert
0x14000583a  mov     ecx, 2710h; MicrosecondsToSleep
0x14000583f  call    cs:__imp_NdisMSleep
0x140005846  nop     dword ptr [rax+rax+00h]
0x14000584b  cmp     dword ptr [rdi], 0
0x14000584e  jnz     short loc_140005817
0x140005850  jmp     short loc_14000580B
```
