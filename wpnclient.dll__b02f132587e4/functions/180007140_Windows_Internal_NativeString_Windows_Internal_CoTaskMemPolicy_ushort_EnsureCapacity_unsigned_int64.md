# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180007140`
- end: `0x180007275`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005a00`
- `0x18000dca4`

## callees

- `0x180007140`
- `0x180013b80`
- `0x180025174`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007180`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r9
  _WORD *v5; // rdx
  __int64 result; // rax
  _QWORD *v7; // rcx
  __int64 v8; // r9
  unsigned int v9; // ebp
  unsigned __int64 v10; // rsi
  LPVOID v11; // rax
  unsigned __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return 2147942934LL;
  v4 = *(_QWORD *)(a1 + 16);
  if ( v4 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount();
    if ( *v7 )
      v4 = v7[1] + 1LL;
    else
      v4 = 0;
    v7[2] = v4;
  }
  if ( v4 )
  {
    result = 0;
    if ( v2 > v4 )
    {
      v12 = 0;
      result = ULongLongMult(v4, a2, &v12);
      v9 = result;
      if ( (int)result >= 0 )
      {
        v10 = v12;
        if ( v12 - v8 > 0x800 )
          v10 = v8 + 2048;
        if ( v2 > v10 )
          v10 = v2;
        v11 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v10);
        if ( v11 )
        {
          *(_QWORD *)a1 = v11;
          result = v9;
          *(_QWORD *)(a1 + 16) = v10;
        }
        else
        {
          return 2147942414LL;
        }
      }
    }
  }
  else if ( is_mul_ok(v2, 2u) )
  {
    v5 = CoTaskMemAlloc(2 * v2);
    if ( v5 )
    {
      *(_QWORD *)(a1 + 16) = v2;
      result = 0;
      *(_QWORD *)a1 = v5;
      *v5 = 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    return 2147942934LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007140  mov     [rsp+arg_18], rbx
0x180007145  push    rdi
0x180007146  sub     rsp, 20h
0x18000714a  lea     rdi, [rdx+1]
0x18000714e  mov     rbx, rcx
0x180007151  cmp     rdi, rdx
0x180007154  jb      short loc_1800071AA
0x180007156  mov     r9, [rcx+10h]
0x18000715a  mov     [rsp+28h+arg_10], rsi
0x18000715f  xor     esi, esi
0x180007161  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180007165  jz      short loc_1800071E4
0x180007167  test    r9, r9
0x18000716a  jnz     loc_180007203
0x180007170  mov     eax, 2
0x180007175  mul     rdi
0x180007178  test    rdx, rdx
0x18000717b  jnz     short loc_1800071BA
0x18000717d  mov     rcx, rax; cb
0x180007180  call    cs:__imp_CoTaskMemAlloc
0x180007186  mov     rdx, rax
0x180007189  test    rax, rax
0x18000718c  jz      short loc_1800071CF
0x18000718e  mov     [rbx+10h], rdi
0x180007192  mov     eax, esi
0x180007194  mov     [rbx], rdx
0x180007197  mov     [rdx], si
0x18000719a  mov     rsi, [rsp+28h+arg_10]
0x18000719f  mov     rbx, [rsp+28h+arg_18]
0x1800071a4  add     rsp, 20h
0x1800071a8  pop     rdi
0x1800071a9  retn
0x1800071aa  mov     eax, 80070216h
0x1800071af  mov     rbx, [rsp+28h+arg_18]
0x1800071b4  add     rsp, 20h
0x1800071b8  pop     rdi
0x1800071b9  retn
0x1800071ba  mov     rsi, [rsp+28h+arg_10]
0x1800071bf  mov     eax, 80070216h
0x1800071c4  mov     rbx, [rsp+28h+arg_18]
0x1800071c9  add     rsp, 20h
0x1800071cd  pop     rdi
0x1800071ce  retn
0x1800071cf  mov     rsi, [rsp+28h+arg_10]
0x1800071d4  mov     eax, 8007000Eh
0x1800071d9  mov     rbx, [rsp+28h+arg_18]
0x1800071de  add     rsp, 20h
0x1800071e2  pop     rdi
0x1800071e3  retn
0x1800071e4  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800071e9  cmp     [rcx], rsi
0x1800071ec  jz      short loc_1800071F7
0x1800071ee  mov     r9, [rcx+8]
0x1800071f2  inc     r9
0x1800071f5  jmp     short loc_1800071FA
0x1800071f7  mov     r9, rsi
0x1800071fa  mov     [rcx+10h], r9
0x1800071fe  jmp     loc_180007167
0x180007203  mov     eax, esi
0x180007205  cmp     rdi, r9
0x180007208  jbe     short loc_18000719A
0x18000720a  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x18000720f  mov     [rsp+28h+arg_0], rbp
0x180007214  mov     rcx, r9; unsigned __int64
0x180007217  mov     [rsp+28h+arg_8], rsi
0x18000721c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180007221  mov     ebp, eax
0x180007223  test    eax, eax
0x180007225  js      short loc_18000726B
0x180007227  mov     rsi, [rsp+28h+arg_8]
0x18000722c  mov     rcx, rsi
0x18000722f  sub     rcx, r9
0x180007232  cmp     rcx, 800h
0x180007239  jbe     short loc_180007242
0x18000723b  lea     rsi, [r9+800h]
0x180007242  mov     rcx, [rbx]; pv
0x180007245  cmp     rdi, rsi
0x180007248  cmova   rsi, rdi
0x18000724c  lea     rdx, [rsi+rsi]; cb
0x180007250  call    cs:__imp_CoTaskMemRealloc
0x180007256  test    rax, rax
0x180007259  jz      short loc_180007266
0x18000725b  mov     [rbx], rax
0x18000725e  mov     eax, ebp
0x180007260  mov     [rbx+10h], rsi
0x180007264  jmp     short loc_18000726B
0x180007266  mov     eax, 8007000Eh
0x18000726b  mov     rbp, [rsp+28h+arg_0]
0x180007270  jmp     loc_18000719A
```
