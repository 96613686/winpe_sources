# remove_phantom_zeroes

- ea: `0x18000f680`
- end: `0x18000f6dd`
- name: `remove_phantom_zeroes`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f680`

## pseudocode

```c
__int64 __fastcall remove_phantom_zeroes(__int64 a1, int a2, unsigned int *a3, _DWORD *a4)
{
  __int64 v4; // rsi
  int v6; // ebx
  int i; // r10d
  __int64 v9; // rcx
  int j; // r8d
  int k; // edx
  __int64 result; // rax

  if ( a2 > 0 )
  {
    v4 = *(_QWORD *)(a1 + 480);
    v6 = *(_DWORD *)(a1 + 476);
    for ( i = a2; i > 0; --i )
    {
      v9 = 0;
      for ( j = 1; (int)v9 < v6; v9 = (unsigned int)(v9 + 1) )
      {
        for ( k = *(_DWORD *)(v4 + 4 * v9); k > 0; --k )
        {
          if ( j )
          {
            result = *a3;
            *a4++ = result;
          }
          ++a3;
        }
        j ^= 1u;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f680  test    edx, edx
0x18000f682  jle     short locret_18000F6DC
0x18000f684  push    rbx
0x18000f685  push    rsi
0x18000f686  push    rdi
0x18000f687  mov     rsi, [rcx+1E0h]
0x18000f68e  mov     rdi, r9
0x18000f691  mov     ebx, [rcx+1DCh]
0x18000f697  mov     r11, r8
0x18000f69a  mov     r10d, edx
0x18000f69d  xor     ecx, ecx
0x18000f69f  lea     r8d, [rcx+1]
0x18000f6a3  test    ebx, ebx
0x18000f6a5  jle     short loc_18000F6D1
0x18000f6a7  mov     edx, [rsi+rcx*4]
0x18000f6aa  test    edx, edx
0x18000f6ac  jle     short loc_18000F6C7
0x18000f6ae  lea     r9, [r11+4]
0x18000f6b2  test    r8d, r8d
0x18000f6b5  jz      short loc_18000F6C0
0x18000f6b7  mov     eax, [r11]
0x18000f6ba  mov     [rdi], eax
0x18000f6bc  add     rdi, 4
0x18000f6c0  dec     edx
0x18000f6c2  mov     r11, r9
0x18000f6c5  jmp     short loc_18000F6AA
0x18000f6c7  xor     r8d, 1
0x18000f6cb  inc     ecx
0x18000f6cd  cmp     ecx, ebx
0x18000f6cf  jl      short loc_18000F6A7
0x18000f6d1  dec     r10d
0x18000f6d4  test    r10d, r10d
0x18000f6d7  jg      short loc_18000F69D
0x18000f6d9  pop     rdi
0x18000f6da  pop     rsi
0x18000f6db  pop     rbx
0x18000f6dc  retn
```
