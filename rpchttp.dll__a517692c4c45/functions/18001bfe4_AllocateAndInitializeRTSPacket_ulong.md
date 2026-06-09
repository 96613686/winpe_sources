# AllocateAndInitializeRTSPacket(ulong)

- ea: `0x18001bfe4`
- end: `0x18001c047`
- name: `?AllocateAndInitializeRTSPacket@@YAPEAVHTTP2SendContext@@K@Z`
- size: `99`
- prototype: `struct HTTP2SendContext *__fastcall(int)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a094`
- `0x18000a184`
- `0x18000dfe8`
- `0x180010864`
- `0x180012110`
- `0x180013920`
- `0x1800158e0`
- `0x1800168d0`
- `0x180018bec`
- `0x180019048`
- `0x180019490`
- `0x18001b9b4`
- `0x18001ba40`
- `0x18001bae0`
- `0x18001bbb4`
- `0x18001bcd8`
- `0x18001bd9c`
- `0x18001bddc`
- `0x18001be7c`
- `0x18001bf50`
- `0x18001bf7c`
- `0x18001bfb4`

## callees

- `0x18001bfe4`
- `0x180025010`

## pseudocode

```c
struct HTTP2SendContext *__fastcall AllocateAndInitializeRTSPacket(int a1)
{
  __int64 v2; // r8

  v2 = (*(__int64 (__fastcall **)(_QWORD))pRuntimeImportTable)((unsigned int)(a1 + 124));
  if ( v2 )
  {
    *(_QWORD *)(v2 + 88) = 1;
    *(_QWORD *)(v2 + 48) = v2 + 104;
    *(_DWORD *)(v2 + 56) = a1 + 20;
    *(_QWORD *)(v2 + 64) = 0;
    *(_DWORD *)(v2 + 96) = 0;
    *(_WORD *)(v2 + 120) = 0;
    *(_OWORD *)(v2 + 104) = xmmword_180028550;
    *(_WORD *)(v2 + 112) = a1 + 20;
  }
  return (struct HTTP2SendContext *)v2;
}

```

## disassembly

```asm
0x18001bfe4  push    rbx
0x18001bfe6  sub     rsp, 20h
0x18001bfea  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001bff1  mov     ebx, ecx
0x18001bff3  add     ecx, 7Ch ; '|'
0x18001bff6  mov     rax, [rax]
0x18001bff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bffe  mov     r8, rax
0x18001c001  xor     eax, eax
0x18001c003  test    r8, r8
0x18001c006  jz      short loc_18001C03E
0x18001c008  lea     rdx, [r8+68h]
0x18001c00c  mov     qword ptr [r8+58h], 1
0x18001c014  mov     [r8+30h], rdx
0x18001c018  lea     ecx, [rbx+14h]
0x18001c01b  mov     [r8+38h], ecx
0x18001c01f  add     bx, 14h
0x18001c023  mov     [r8+40h], rax
0x18001c027  mov     [r8+60h], eax
0x18001c02b  movups  xmm0, cs:xmmword_180028550
0x18001c032  mov     [rdx+10h], ax
0x18001c036  movdqu  xmmword ptr [rdx], xmm0
0x18001c03a  mov     [rdx+8], bx
0x18001c03e  mov     rax, r8
0x18001c041  add     rsp, 20h
0x18001c045  pop     rbx
0x18001c046  retn
```
