# WinHvConfigureTdComprehensiveScan

- ea: `0x140024330`
- end: `0x1400243c1`
- name: `WinHvConfigureTdComprehensiveScan`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140009d40`
- `0x14000b008`
- `0x14000b040`
- `0x14001fd40`
- `0x140024330`

## pseudocode

```c
__int64 __fastcall WinHvConfigureTdComprehensiveScan(__int64 a1, const void *a2, unsigned __int16 a3)
{
  __int64 v3; // rdi
  unsigned int v6; // ebx
  _WORD *Pool; // rsi

  v3 = a3;
  if ( a3 <= 0x1FFu )
  {
    Pool = (_WORD *)WinHvpAllocatePool(64, 8 * (unsigned int)a3 + 8, 1433815127);
    *Pool = v3;
    memmove(Pool + 4, a2, 8 * v3);
    v6 = WinHvSetPartitionPropertyEx(a1, 589842, 0, Pool, 8 * (int)v3 + 8);
    if ( Pool )
      WinHvpFreePoolWithTag(Pool, 1433815127);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v6;
}

```

## disassembly

```asm
0x140024330  push    rbx
0x140024332  push    rbp
0x140024333  push    rsi
0x140024334  push    rdi
0x140024335  push    r14
0x140024337  sub     rsp, 30h
0x14002433b  movzx   edi, r8w
0x14002433f  mov     eax, 1FFh
0x140024344  mov     rbp, rdx
0x140024347  mov     r14, rcx
0x14002434a  cmp     di, ax
0x14002434d  jbe     short loc_140024356
0x14002434f  mov     ebx, 0C000000Dh
0x140024354  jmp     short loc_1400243B3
0x140024356  lea     ebx, ds:8[rdi*8]
0x14002435d  mov     ecx, 40h ; '@'
0x140024362  mov     edx, ebx
0x140024364  mov     r8d, 55764857h
0x14002436a  call    WinHvpAllocatePool
0x14002436f  mov     r8, rdi
0x140024372  mov     rdx, rbp; Src
0x140024375  shl     r8, 3; Size
0x140024379  mov     rsi, rax
0x14002437c  lea     rcx, [rax+8]; void *
0x140024380  mov     [rax], di
0x140024383  call    memmove
0x140024388  mov     r9, rsi
0x14002438b  mov     [rsp+58h+var_38], ebx
0x14002438f  xor     r8d, r8d
0x140024392  mov     edx, 90012h
0x140024397  mov     rcx, r14
0x14002439a  call    WinHvSetPartitionPropertyEx
0x14002439f  mov     ebx, eax
0x1400243a1  test    rsi, rsi
0x1400243a4  jz      short loc_1400243B3
0x1400243a6  mov     edx, 55764857h
0x1400243ab  mov     rcx, rsi
0x1400243ae  call    WinHvpFreePoolWithTag
0x1400243b3  mov     eax, ebx
0x1400243b5  add     rsp, 30h
0x1400243b9  pop     r14
0x1400243bb  pop     rdi
0x1400243bc  pop     rsi
0x1400243bd  pop     rbp
0x1400243be  pop     rbx
0x1400243bf  retn
```
