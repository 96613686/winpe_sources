# ReadAllocCmapFormat12

- ea: `0x180013dac`
- end: `0x180013ea2`
- name: `ReadAllocCmapFormat12`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f298`
- `0x180017694`

## callees

- `0x1800134a0`
- `0x180013dac`
- `0x180015190`
- `0x1800164a0`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat12(__int64 *a1, unsigned int a2, __int64 a3, __int64 *a4)
{
  __int64 result; // rax
  unsigned int v9; // edi
  __int64 v10; // rax
  unsigned int v11; // ebx
  unsigned int i; // esi
  unsigned __int16 v13; // bp
  unsigned __int16 v14; // [rsp+68h] [rbp+10h] BYREF

  *a4 = 0;
  v14 = 0;
  result = ReadGeneric(a1, a3, 0x10u, (unsigned __int8 *)&CMAP_FORMAT12_CONTROL, a2, &v14);
  if ( !(_WORD)result )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( v9 <= 0x15555555 && (v10 = Mem_Alloc(12 * v9), (*a4 = v10) != 0) )
    {
      v11 = a2 + v14;
      for ( i = 0; ; ++i )
      {
        if ( i >= v9 )
          return 0;
        v13 = ReadGeneric(a1, *a4 + 12LL * i, 0xCu, (unsigned __int8 *)&FORMAT12_GROUPS_CONTROL, v11, &v14);
        if ( v13 )
          break;
        v11 += v14;
      }
      Mem_Free(*a4);
      result = v13;
      *a4 = 0;
    }
    else
    {
      return 1005;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013dac  mov     r11, rsp
0x180013daf  mov     [r11+8], rbx
0x180013db3  mov     [r11+18h], rbp
0x180013db7  push    rsi
0x180013db8  push    rdi
0x180013db9  push    r12
0x180013dbb  push    r14
0x180013dbd  push    r15
0x180013dbf  sub     rsp, 30h
0x180013dc3  xor     r12d, r12d
0x180013dc6  lea     rax, [r11+10h]
0x180013dca  mov     rdi, r8
0x180013dcd  mov     [r11-30h], rax
0x180013dd1  mov     r14, r9
0x180013dd4  mov     [r9], r12
0x180013dd7  mov     esi, edx
0x180013dd9  mov     [rsp+58h+var_38], edx
0x180013ddd  lea     r8d, [r12+10h]
0x180013de2  mov     [r11+10h], r12w
0x180013de7  lea     r9, CMAP_FORMAT12_CONTROL
0x180013dee  mov     rdx, rdi
0x180013df1  mov     r15, rcx
0x180013df4  call    ReadGeneric
0x180013df9  test    ax, ax
0x180013dfc  jnz     short loc_180013E74
0x180013dfe  mov     edi, [rdi+0Ch]
0x180013e01  cmp     edi, 15555555h
0x180013e07  ja      loc_180013E9B
0x180013e0d  lea     ecx, [rdi+rdi*2]
0x180013e10  shl     ecx, 2; Size
0x180013e13  call    Mem_Alloc
0x180013e18  mov     [r14], rax
0x180013e1b  test    rax, rax
0x180013e1e  jz      short loc_180013E9B
0x180013e20  movzx   ebx, [rsp+58h+arg_8]
0x180013e25  add     ebx, esi
0x180013e27  mov     esi, r12d
0x180013e2a  cmp     esi, edi
0x180013e2c  jnb     short loc_180013E71
0x180013e2e  mov     eax, esi
0x180013e30  lea     r9, FORMAT12_GROUPS_CONTROL
0x180013e37  mov     r8d, 0Ch
0x180013e3d  lea     rcx, [rax+rax*2]
0x180013e41  mov     rax, [r14]
0x180013e44  lea     rdx, [rax+rcx*4]
0x180013e48  mov     rcx, r15
0x180013e4b  lea     rax, [rsp+58h+arg_8]
0x180013e50  mov     [rsp+58h+var_30], rax
0x180013e55  mov     [rsp+58h+var_38], ebx
0x180013e59  call    ReadGeneric
0x180013e5e  movzx   ebp, ax
0x180013e61  test    ax, ax
0x180013e64  jnz     short loc_180013E8B
0x180013e66  movzx   eax, [rsp+58h+arg_8]
0x180013e6b  add     ebx, eax
0x180013e6d  inc     esi
0x180013e6f  jmp     short loc_180013E2A
0x180013e71  mov     eax, r12d
0x180013e74  mov     rbx, [rsp+58h+arg_0]
0x180013e79  mov     rbp, [rsp+58h+arg_10]
0x180013e7e  add     rsp, 30h
0x180013e82  pop     r15
0x180013e84  pop     r14
0x180013e86  pop     r12
0x180013e88  pop     rdi
0x180013e89  pop     rsi
0x180013e8a  retn
0x180013e8b  mov     rcx, [r14]
0x180013e8e  call    Mem_Free
0x180013e93  movzx   eax, bp
0x180013e96  mov     [r14], r12
0x180013e99  jmp     short loc_180013E74
0x180013e9b  mov     eax, 3EDh
0x180013ea0  jmp     short loc_180013E74
```
