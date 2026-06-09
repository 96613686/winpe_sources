# CompressData

- ea: `0x180036ca0`
- end: `0x180036d36`
- name: `CompressData`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a59c`
- `0x1800318e8`

## callees

- `0x180004150`
- `0x180036ca0`

## pseudocode

```c
__int64 __fastcall CompressData(int a1, int a2, unsigned int *a3, __int64 a4)
{
  __int16 v4; // si
  unsigned int v5; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int v11; // [rsp+60h] [rbp+8h] BYREF

  v4 = a1;
  v5 = 0;
  v8 = (int)(float)((float)a1 * 1.001) + 17;
  v11 = v8;
  if ( a4 )
  {
    if ( *a3 >= v8 )
    {
      if ( (unsigned int)a1 > 0xFFFF || (unsigned int)compress2((int)a4 + 4, (unsigned int)&v11, a2, a1, 9) )
      {
        return 1359;
      }
      else
      {
        v9 = v11 + 4;
        *(_BYTE *)a4 = 1;
        *a3 = v9;
        *(_WORD *)(a4 + 2) = v4;
      }
    }
    else
    {
      *a3 = v8;
      return 234;
    }
  }
  else
  {
    *a3 = v8;
  }
  return v5;
}

```

## disassembly

```asm
0x180036ca0  push    rbx
0x180036ca2  push    rsi
0x180036ca3  push    rdi
0x180036ca4  push    r14
0x180036ca6  sub     rsp, 38h
0x180036caa  xorps   xmm0, xmm0
0x180036cad  mov     esi, ecx
0x180036caf  xor     ebx, ebx
0x180036cb1  mov     r14, r9
0x180036cb4  mov     rdi, r8
0x180036cb7  cvtsi2ss xmm0, rsi
0x180036cbc  mulss   xmm0, cs:__real@3f8020c5
0x180036cc4  cvttss2si rax, xmm0
0x180036cc9  add     eax, 11h
0x180036ccc  mov     [rsp+58h+arg_0], eax
0x180036cd0  test    r9, r9
0x180036cd3  jnz     short loc_180036CDA
0x180036cd5  mov     [r8], eax
0x180036cd8  jmp     short loc_180036D2A
0x180036cda  cmp     [r8], eax
0x180036cdd  jnb     short loc_180036CE9
0x180036cdf  mov     [r8], eax
0x180036ce2  mov     ebx, 0EAh
0x180036ce7  jmp     short loc_180036D2A
0x180036ce9  cmp     esi, 0FFFFh
0x180036cef  jbe     short loc_180036CF8
0x180036cf1  mov     ebx, 54Fh
0x180036cf6  jmp     short loc_180036D2A
0x180036cf8  lea     rcx, [r9+4]
0x180036cfc  mov     [rsp+58h+var_38], 9
0x180036d04  mov     r8, rdx
0x180036d07  mov     r9d, esi
0x180036d0a  lea     rdx, [rsp+58h+arg_0]
0x180036d0f  call    compress2
0x180036d14  test    eax, eax
0x180036d16  jnz     short loc_180036CF1
0x180036d18  mov     ecx, [rsp+58h+arg_0]
0x180036d1c  add     ecx, 4
0x180036d1f  mov     byte ptr [r14], 1
0x180036d23  mov     [rdi], ecx
0x180036d25  mov     [r14+2], si
0x180036d2a  mov     eax, ebx
0x180036d2c  add     rsp, 38h
0x180036d30  pop     r14
0x180036d32  pop     rdi
0x180036d33  pop     rsi
0x180036d34  pop     rbx
0x180036d35  retn
```
