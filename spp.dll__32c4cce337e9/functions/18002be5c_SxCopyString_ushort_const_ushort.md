# SxCopyString(ushort const *,ushort * *)

- ea: `0x18002be5c`
- end: `0x18002bede`
- name: `?SxCopyString@@YAJPEBGPEAPEAG@Z`
- size: `130`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002f88`
- `0x180018f10`
- `0x1800192a8`
- `0x180019bb4`
- `0x18002849c`
- `0x180028b7c`

## callees

- `0x18002be5c`
- `0x180035b82`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002becb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002becb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002be99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002be99`

## pseudocode

```c
__int64 __fastcall SxCopyString(const unsigned __int16 *Src, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rdi
  __int64 v5; // rax
  SIZE_T v6; // rbp
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx

  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_10;
  }
  *a2 = 0;
  v4 = 0;
  if ( !Src )
    goto LABEL_8;
  v5 = -1;
  do
    ++v5;
  while ( Src[v5] );
  v6 = 2 * v5 + 2;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(v6);
  v4 = v7;
  if ( v7 )
  {
    memcpy_0(v7, Src, v6);
LABEL_8:
    v8 = 0;
    *a2 = v4;
    goto LABEL_10;
  }
  v8 = -2147024882;
LABEL_10:
  CoTaskMemFree(0);
  return v8;
}

```

## disassembly

```asm
0x18002be5c  push    rbx
0x18002be5e  push    rbp
0x18002be5f  push    rsi
0x18002be60  push    rdi
0x18002be61  push    r14
0x18002be63  sub     rsp, 20h
0x18002be67  xor     r14d, r14d
0x18002be6a  mov     rsi, rdx
0x18002be6d  mov     rbx, rcx
0x18002be70  test    rdx, rdx
0x18002be73  jz      short loc_18002BEC4
0x18002be75  mov     [rdx], r14
0x18002be78  mov     edi, r14d
0x18002be7b  test    rcx, rcx
0x18002be7e  jz      short loc_18002BEBC
0x18002be80  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002be84  inc     rax
0x18002be87  cmp     [rcx+rax*2], r14w
0x18002be8c  jnz     short loc_18002BE84
0x18002be8e  lea     rbp, ds:2[rax*2]
0x18002be96  mov     rcx, rbp; cb
0x18002be99  call    cs:__imp_CoTaskMemAlloc
0x18002be9f  mov     rdi, rax
0x18002bea2  test    rax, rax
0x18002bea5  jnz     short loc_18002BEAE
0x18002bea7  mov     ebx, 8007000Eh
0x18002beac  jmp     short loc_18002BEC9
0x18002beae  mov     r8, rbp; Size
0x18002beb1  mov     rdx, rbx; Src
0x18002beb4  mov     rcx, rax; void *
0x18002beb7  call    memcpy_0
0x18002bebc  mov     ebx, r14d
0x18002bebf  mov     [rsi], rdi
0x18002bec2  jmp     short loc_18002BEC9
0x18002bec4  mov     ebx, 80070057h
0x18002bec9  xor     ecx, ecx; pv
0x18002becb  call    cs:__imp_CoTaskMemFree
0x18002bed1  mov     eax, ebx
0x18002bed3  add     rsp, 20h
0x18002bed7  pop     r14
0x18002bed9  pop     rdi
0x18002beda  pop     rsi
0x18002bedb  pop     rbp
0x18002bedc  pop     rbx
0x18002bedd  retn
```
