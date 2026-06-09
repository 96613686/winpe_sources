# CVaultGenericPropertyCollection<EVaultPropertyId,0>::CreateProperties(void)

- ea: `0x1800062a8`
- end: `0x18000631e`
- name: `?CreateProperties@?$CVaultGenericPropertyCollection@W4EVaultPropertyId@@$0A@@@AEAAKXZ`
- size: `118`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005df0`
- `0x18001aa28`
- `0x18001cc1c`
- `0x180028e3c`
- `0x180038e44`
- `0x180041524`

## callees

- `0x1800062a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800062c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800062e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800062c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800062e0`

## pseudocode

```c
__int64 __fastcall CVaultGenericPropertyCollection<enum EVaultPropertyId,0>::CreateProperties(__int64 a1)
{
  HLOCAL v2; // rax
  __int64 i; // rbx
  char *v4; // rax

  v2 = LocalAlloc(0x40u, 8LL * (unsigned int)(8 * *(_DWORD *)a1));
  *(_QWORD *)(a1 + 8) = v2;
  if ( !v2 )
    return 14;
  for ( i = 0; (unsigned int)i < *(_DWORD *)a1; i = (unsigned int)(i + 1) )
  {
    v4 = (char *)LocalAlloc(0x40u, 0x20u);
    if ( !v4 )
      return 14;
    *(_DWORD *)v4 = -1;
    *(_OWORD *)(v4 + 8) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * i) = v4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800062a8  mov     [rsp+arg_0], rbx
0x1800062ad  push    rdi
0x1800062ae  sub     rsp, 20h
0x1800062b2  mov     edx, [rcx]
0x1800062b4  mov     rdi, rcx
0x1800062b7  shl     edx, 3
0x1800062ba  mov     ecx, 40h ; '@'; uFlags
0x1800062bf  shl     rdx, 3; uBytes
0x1800062c3  call    cs:__imp_LocalAlloc
0x1800062c9  mov     [rdi+8], rax
0x1800062cd  test    rax, rax
0x1800062d0  jz      short loc_180006317
0x1800062d2  xor     ebx, ebx
0x1800062d4  cmp     ebx, [rdi]
0x1800062d6  jnb     short loc_18000630A
0x1800062d8  mov     edx, 20h ; ' '; uBytes
0x1800062dd  lea     ecx, [rdx+20h]; uFlags
0x1800062e0  call    cs:__imp_LocalAlloc
0x1800062e6  test    rax, rax
0x1800062e9  jz      short loc_180006317
0x1800062eb  mov     dword ptr [rax], 0FFFFFFFFh
0x1800062f1  xor     ecx, ecx
0x1800062f3  xorps   xmm0, xmm0
0x1800062f6  movups  xmmword ptr [rax+8], xmm0
0x1800062fa  mov     [rax+18h], rcx
0x1800062fe  mov     rcx, [rdi+8]
0x180006302  mov     [rcx+rbx*8], rax
0x180006306  inc     ebx
0x180006308  jmp     short loc_1800062D4
0x18000630a  xor     eax, eax
0x18000630c  mov     rbx, [rsp+28h+arg_0]
0x180006311  add     rsp, 20h
0x180006315  pop     rdi
0x180006316  retn
0x180006317  mov     eax, 0Eh
0x18000631c  jmp     short loc_18000630C
```
