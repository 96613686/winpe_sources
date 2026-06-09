# PkGetSendBufferEx

- ea: `0x1400151a4`
- end: `0x140015213`
- name: `PkGetSendBufferEx`
- size: `111`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140014e78`
- `0x14001514c`
- `0x14001521c`
- `0x1400152dc`

## callees

- `0x1400151a4`
- `0x14001539c`

## pseudocode

```c
__int64 __fastcall PkGetSendBufferEx(__int64 a1, unsigned int a2, int a3, _QWORD *a4, _DWORD *a5)
{
  const void *v6; // rbx
  __int64 result; // rax
  _DWORD *v8; // rax
  int v9; // ecx
  int v10; // [rsp+48h] [rbp+10h] BYREF

  v6 = (const void *)(a2 + *(_QWORD *)(a1 + 8));
  v10 = 0;
  _m_prefetchw(v6);
  result = PkpCheckSendBufferFreeBytes(
             a1,
             ((a3 + 7) & 0xFFFFFFF8) + 8,
             a2,
             *(_DWORD *)(a1 + 132),
             *(_DWORD *)(a1 + 16),
             (__int64)&v10);
  if ( (int)result >= 0 )
  {
    v8 = a5;
    v9 = v10 - 8;
    *a4 = v6;
    *v8 = v9;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400151a4  mov     [rsp+arg_0], rbx
0x1400151a9  push    rdi
0x1400151aa  sub     rsp, 30h
0x1400151ae  mov     rbx, [rcx+8]
0x1400151b2  mov     rdi, r9
0x1400151b5  mov     r11d, edx
0x1400151b8  add     rbx, r11
0x1400151bb  mov     [rsp+38h+arg_8], 0
0x1400151c3  prefetchw byte ptr [rbx]
0x1400151c6  mov     r9d, [rcx+84h]
0x1400151cd  lea     edx, [r8+7]
0x1400151d1  lea     rax, [rsp+38h+arg_8]
0x1400151d6  and     edx, 0FFFFFFF8h
0x1400151d9  mov     [rsp+38h+var_10], rax
0x1400151de  add     edx, 8
0x1400151e1  mov     eax, [rcx+10h]
0x1400151e4  mov     r8d, r11d
0x1400151e7  mov     [rsp+38h+var_18], eax
0x1400151eb  call    PkpCheckSendBufferFreeBytes
0x1400151f0  test    eax, eax
0x1400151f2  js      short loc_140015207
0x1400151f4  mov     rax, [rsp+38h+arg_20]
0x1400151f9  mov     ecx, [rsp+38h+arg_8]
0x1400151fd  add     ecx, 0FFFFFFF8h
0x140015200  mov     [rdi], rbx
0x140015203  mov     [rax], ecx
0x140015205  xor     eax, eax
0x140015207  mov     rbx, [rsp+38h+arg_0]
0x14001520c  add     rsp, 30h
0x140015210  pop     rdi
0x140015211  retn
```
