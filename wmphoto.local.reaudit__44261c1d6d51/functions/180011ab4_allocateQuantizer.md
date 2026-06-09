# allocateQuantizer

- ea: `0x180011ab4`
- end: `0x180011b21`
- name: `allocateQuantizer`
- size: `109`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012bc`
- `0x18001128c`
- `0x18003146c`
- `0x180032cb4`
- `0x180032eb4`
- `0x180042878`
- `0x180042a84`

## callees

- `0x180011ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011ad7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180011ad7`

## pseudocode

```c
__int64 __fastcall allocateQuantizer(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  void *v5; // rax
  unsigned __int64 i; // rcx

  if ( a3 > 0x11 )
    return 0xFFFFFFFFLL;
  if ( a2 > 0x10 )
    return 0xFFFFFFFFLL;
  v5 = malloc(340 * a2);
  *a1 = v5;
  if ( !v5 )
    return 0xFFFFFFFFLL;
  for ( i = 1; i < a2; ++i )
    a1[i] = a1[i - 1] + 340LL;
  return 0;
}

```

## disassembly

```asm
0x180011ab4  mov     [rsp+arg_0], rbx
0x180011ab9  push    rdi
0x180011aba  sub     rsp, 20h
0x180011abe  mov     rbx, rdx
0x180011ac1  mov     rdi, rcx
0x180011ac4  cmp     r8, 11h
0x180011ac8  ja      short loc_180011B03
0x180011aca  cmp     rdx, 10h
0x180011ace  ja      short loc_180011B03
0x180011ad0  imul    rcx, rbx, 154h; Size
0x180011ad7  call    cs:__imp_malloc
0x180011ade  nop     dword ptr [rax+rax+00h]
0x180011ae3  mov     [rdi], rax
0x180011ae6  test    rax, rax
0x180011ae9  jz      short loc_180011B03
0x180011aeb  mov     ecx, 1
0x180011af0  cmp     rbx, rcx
0x180011af3  ja      short loc_180011B08
0x180011af5  xor     eax, eax
0x180011af7  mov     rbx, [rsp+28h+arg_0]
0x180011afc  add     rsp, 20h
0x180011b00  pop     rdi
0x180011b01  retn
0x180011b03  or      eax, 0FFFFFFFFh
0x180011b06  jmp     short loc_180011AF7
0x180011b08  mov     rax, [rdi+rcx*8-8]
0x180011b0d  add     rax, 154h
0x180011b13  mov     [rdi+rcx*8], rax
0x180011b17  inc     rcx
0x180011b1a  cmp     rcx, rbx
0x180011b1d  jb      short loc_180011B08
0x180011b1f  jmp     short loc_180011AF5
```
