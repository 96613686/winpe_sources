# WheapWmiExecutePluginCtlMethod

- ea: `0x140692d84`
- end: `0x140692e60`
- name: `WheapWmiExecutePluginCtlMethod`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140692ae4`

## callees

- `0x140692d84`
- `0x1406f6f80`

## import_xrefs

- `PSHED!PshedAllocateMemory` at `0x140692de2`
- `PSHED!PshedAllocateMemory` at `0x140692de2`
- `PSHED!PshedDoPluginCtl` at `0x140692e20`
- `PSHED!PshedDoPluginCtl` at `0x140692e20`
- `PSHED!PshedFreeMemory` at `0x140692e31`
- `PSHED!PshedFreeMemory` at `0x140692e31`

## pseudocode

```c
__int64 __fastcall WheapWmiExecutePluginCtlMethod(
        int a1,
        unsigned int a2,
        unsigned int *a3,
        __int64 a4,
        unsigned int *a5)
{
  unsigned int v5; // ebx
  __int64 result; // rax
  size_t v9; // rsi
  PVOID Memory; // rax
  void *v11; // r15

  v5 = 0;
  *a5 = 0;
  if ( a1 == 1 )
  {
    if ( a2 < 4 || !a3 || (v9 = *a3, (unsigned int)v9 < 4) )
    {
      result = 3221225485LL;
      goto LABEL_13;
    }
    v5 = 8;
    if ( a2 >= 8 )
    {
      Memory = PshedAllocateMemory(v9);
      v11 = Memory;
      if ( !Memory )
      {
        result = 3221225626LL;
        goto LABEL_13;
      }
      memmove(Memory, a3 + 1, v9);
      a3[1] = a2 - 8;
      *a3 = PshedDoPluginCtl((unsigned int)v9, v11, a3 + 1, a3 + 2);
      PshedFreeMemory(v11);
      v5 = a3[1] + 8;
      if ( a2 >= v5 )
      {
        result = *a3;
        goto LABEL_13;
      }
    }
    result = 3221225507LL;
  }
  else
  {
    result = 3221226135LL;
  }
LABEL_13:
  *a5 = v5;
  return result;
}

```

## disassembly

```asm
0x140692d84  push    rbx
0x140692d86  push    rbp
0x140692d87  push    rsi
0x140692d88  push    rdi
0x140692d89  push    r14
0x140692d8b  push    r15
0x140692d8d  sub     rsp, 28h
0x140692d91  mov     r14, [rsp+58h+arg_20]
0x140692d99  xor     ebx, ebx
0x140692d9b  mov     rdi, r8
0x140692d9e  mov     ebp, edx
0x140692da0  mov     dword ptr [r14], 0
0x140692da7  cmp     ecx, 1
0x140692daa  jz      short loc_140692DB6
0x140692dac  mov     eax, 0C0000297h
0x140692db1  jmp     loc_140692E4F
0x140692db6  cmp     ebp, 4
0x140692db9  jb      loc_140692E4A
0x140692dbf  test    rdi, rdi
0x140692dc2  jz      loc_140692E4A
0x140692dc8  mov     esi, [r8]
0x140692dcb  cmp     esi, 4
0x140692dce  jb      short loc_140692E4A
0x140692dd0  mov     ebx, 8
0x140692dd5  cmp     ebp, ebx
0x140692dd7  jnb     short loc_140692DE0
0x140692dd9  mov     eax, 0C0000023h
0x140692dde  jmp     short loc_140692E4F
0x140692de0  mov     ecx, esi; Size
0x140692de2  call    cs:__imp_PshedAllocateMemory
0x140692de9  nop     dword ptr [rax+rax+00h]
0x140692dee  mov     r15, rax
0x140692df1  test    rax, rax
0x140692df4  jnz     short loc_140692DFD
0x140692df6  mov     eax, 0C000009Ah
0x140692dfb  jmp     short loc_140692E4F
0x140692dfd  lea     rbx, [rdi+4]
0x140692e01  mov     r8, rsi; Size
0x140692e04  mov     rdx, rbx; Src
0x140692e07  mov     rcx, r15; void *
0x140692e0a  call    memmove
0x140692e0f  lea     eax, [rbp-8]
0x140692e12  mov     r8, rbx
0x140692e15  lea     r9, [rbx+4]
0x140692e19  mov     [rbx], eax
0x140692e1b  mov     rdx, r15
0x140692e1e  mov     ecx, esi
0x140692e20  call    cs:__imp_PshedDoPluginCtl
0x140692e27  nop     dword ptr [rax+rax+00h]
0x140692e2c  mov     rcx, r15; Address
0x140692e2f  mov     [rdi], eax
0x140692e31  call    cs:__imp_PshedFreeMemory
0x140692e38  nop     dword ptr [rax+rax+00h]
0x140692e3d  mov     ebx, [rbx]
0x140692e3f  add     ebx, 8
0x140692e42  cmp     ebp, ebx
0x140692e44  jb      short loc_140692DD9
0x140692e46  mov     eax, [rdi]
0x140692e48  jmp     short loc_140692E4F
0x140692e4a  mov     eax, 0C000000Dh
0x140692e4f  mov     [r14], ebx
0x140692e52  add     rsp, 28h
0x140692e56  pop     r15
0x140692e58  pop     r14
0x140692e5a  pop     rdi
0x140692e5b  pop     rsi
0x140692e5c  pop     rbp
0x140692e5d  pop     rbx
0x140692e5e  retn
```
