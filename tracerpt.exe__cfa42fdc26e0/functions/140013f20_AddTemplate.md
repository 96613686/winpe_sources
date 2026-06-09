# AddTemplate

- ea: `0x140013f20`
- end: `0x1400140ef`
- name: `AddTemplate`
- size: `463`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015974`

## callees

- `0x140013f20`
- `0x140015e84`
- `0x1400400b2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014081`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014093`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014093`

## pseudocode

```c
__int64 __fastcall AddTemplate(__int64 a1, __int64 a2)
{
  _DWORD *v2; // r14
  _DWORD *i; // rbx
  _DWORD *v6; // r9
  unsigned int v7; // r12d
  __int64 v8; // r11
  int v9; // r15d
  unsigned __int16 *v10; // rax
  __int64 v11; // r8
  int v12; // edx
  int v13; // r10d
  unsigned __int16 v14; // ax
  bool v15; // zf
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  int v18; // r8d
  int v19; // r10d
  unsigned int v20; // eax
  HANDLE ProcessHeap; // rax
  _DWORD *v22; // rax
  int v23; // ecx
  _QWORD *v24; // rax

  v2 = (_DWORD *)(a1 + 152);
  for ( i = *(_DWORD **)(a1 + 152); i != v2; i = *(_DWORD **)i )
  {
    v6 = (_DWORD *)*((_QWORD *)i + 3);
    v7 = v6[25];
    if ( *(_QWORD *)(v6 + 25) == *(_QWORD *)(a2 + 100) )
    {
      v8 = 0;
      if ( v7 )
      {
        while ( 1 )
        {
          v9 = v6[6 * v8 + 28];
          if ( v9 != *(_DWORD *)(a2 + 24 * v8 + 112) )
            break;
          v10 = (unsigned __int16 *)((char *)v6 + (unsigned int)v6[6 * v8 + 29]);
          v11 = a2 + *(unsigned int *)(a2 + 24 * v8 + 116) - (_QWORD)v10;
          do
          {
            v12 = *(unsigned __int16 *)((char *)v10 + v11);
            v13 = *v10 - v12;
            if ( v13 )
              break;
            ++v10;
          }
          while ( v12 );
          if ( v13 || LOWORD(v6[6 * v8 + 30]) != *(_WORD *)(a2 + 24 * v8 + 120) )
            break;
          v14 = *(_WORD *)(a2 + 24 * v8 + 122);
          if ( (v9 & 1) != 0 )
          {
            v15 = HIWORD(v6[6 * v8 + 30]) == v14;
          }
          else
          {
            if ( HIWORD(v6[6 * v8 + 30]) != v14 )
              break;
            v16 = (unsigned __int16 *)((char *)v6 + (unsigned int)v6[6 * v8 + 31]);
            v17 = a2 + *(unsigned int *)(a2 + 24 * v8 + 124) - (_QWORD)v16;
            do
            {
              v18 = *(unsigned __int16 *)((char *)v16 + v17);
              v19 = *v16 - v18;
              if ( v19 )
                break;
              ++v16;
            }
            while ( v18 );
            v15 = v19 == 0;
          }
          if ( !v15
            || LOWORD(v6[6 * v8 + 32]) != *(_WORD *)(a2 + 24 * v8 + 128)
            || HIWORD(v6[6 * v8 + 32]) != *(_WORD *)(a2 + 24 * v8 + 130) )
          {
            break;
          }
          v8 = (unsigned int)(v8 + 1);
          if ( (unsigned int)v8 >= v7 )
            goto LABEL_21;
        }
      }
      else
      {
LABEL_21:
        if ( !v6[21]
          || (v20 = v6[22], v20 == *(_DWORD *)(a2 + 88))
          && !memcmp_0((char *)v6 + (unsigned int)v6[21], (const void *)(a2 + *(unsigned int *)(a2 + 84)), v20) )
        {
          if ( i )
            return (unsigned int)i[4];
          break;
        }
      }
    }
  }
  ProcessHeap = GetProcessHeap();
  v22 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  i = v22;
  if ( v22 )
  {
    v23 = *(_DWORD *)(a1 + 144);
    *(_DWORD *)(a1 + 144) = v23 + 1;
    v22[4] = v23;
    v22[5] = *(_DWORD *)(a2 + 100);
    *((_QWORD *)v22 + 3) = a2;
    v24 = *(_QWORD **)(a1 + 160);
    *(_QWORD *)i = a1 + 152;
    *((_QWORD *)i + 1) = v24;
    *v24 = i;
    *(_QWORD *)(a1 + 160) = i;
  }
  else
  {
    RaiseAllocationFailure();
  }
  return (unsigned int)i[4];
}

```

## disassembly

```asm
0x140013f20  push    rbx
0x140013f22  push    rbp
0x140013f23  push    rsi
0x140013f24  push    rdi
0x140013f25  push    r12
0x140013f27  push    r14
0x140013f29  push    r15
0x140013f2b  sub     rsp, 20h
0x140013f2f  lea     r14, [rcx+98h]
0x140013f36  mov     rdi, rdx
0x140013f39  mov     rbx, [r14]
0x140013f3c  mov     rbp, rcx
0x140013f3f  jmp     loc_140014071
0x140013f44  mov     r9, [rbx+18h]
0x140013f48  mov     r12d, [r9+64h]
0x140013f4c  cmp     r12d, [rdi+64h]
0x140013f50  jnz     loc_14001406E
0x140013f56  mov     eax, [rdi+68h]
0x140013f59  cmp     [r9+68h], eax
0x140013f5d  jnz     loc_14001406E
0x140013f63  xor     r11d, r11d
0x140013f66  test    r12d, r12d
0x140013f69  jz      loc_140014045
0x140013f6f  lea     rcx, [r11+r11*2]
0x140013f73  mov     r15d, [r9+rcx*8+70h]
0x140013f78  cmp     r15d, [rdi+rcx*8+70h]
0x140013f7d  jnz     loc_14001406E
0x140013f83  mov     r8d, [rdi+rcx*8+74h]
0x140013f88  mov     eax, [r9+rcx*8+74h]
0x140013f8d  add     r8, rdi
0x140013f90  add     rax, r9
0x140013f93  sub     r8, rax
0x140013f96  movzx   r10d, word ptr [rax]
0x140013f9a  movzx   edx, word ptr [rax+r8]
0x140013f9f  sub     r10d, edx
0x140013fa2  jnz     short loc_140013FAC
0x140013fa4  add     rax, 2
0x140013fa8  test    edx, edx
0x140013faa  jnz     short loc_140013F96
0x140013fac  test    r10d, r10d
0x140013faf  jnz     loc_14001406E
0x140013fb5  movzx   eax, word ptr [rdi+rcx*8+78h]
0x140013fba  cmp     [r9+rcx*8+78h], ax
0x140013fc0  jnz     loc_14001406E
0x140013fc6  movzx   eax, word ptr [rdi+rcx*8+7Ah]
0x140013fcb  test    r15b, 1
0x140013fcf  jz      short loc_140013FD9
0x140013fd1  cmp     [r9+rcx*8+7Ah], ax
0x140013fd7  jmp     short loc_140014011
0x140013fd9  cmp     [r9+rcx*8+7Ah], ax
0x140013fdf  jnz     loc_14001406E
0x140013fe5  mov     edx, [rdi+rcx*8+7Ch]
0x140013fe9  mov     eax, [r9+rcx*8+7Ch]
0x140013fee  add     rdx, rdi
0x140013ff1  add     rax, r9
0x140013ff4  sub     rdx, rax
0x140013ff7  movzx   r10d, word ptr [rax]
0x140013ffb  movzx   r8d, word ptr [rax+rdx]
0x140014000  sub     r10d, r8d
0x140014003  jnz     short loc_14001400E
0x140014005  add     rax, 2
0x140014009  test    r8d, r8d
0x14001400c  jnz     short loc_140013FF7
0x14001400e  test    r10d, r10d
0x140014011  jnz     short loc_14001406E
0x140014013  movzx   eax, word ptr [rdi+rcx*8+80h]
0x14001401b  cmp     [r9+rcx*8+80h], ax
0x140014024  jnz     short loc_14001406E
0x140014026  movzx   eax, word ptr [rdi+rcx*8+82h]
0x14001402e  cmp     [r9+rcx*8+82h], ax
0x140014037  jnz     short loc_14001406E
0x140014039  inc     r11d
0x14001403c  cmp     r11d, r12d
0x14001403f  jb      loc_140013F6F
0x140014045  cmp     dword ptr [r9+54h], 0
0x14001404a  jz      short loc_14001407C
0x14001404c  mov     eax, [r9+58h]
0x140014050  cmp     eax, [rdi+58h]
0x140014053  jnz     short loc_14001406E
0x140014055  mov     ecx, [r9+54h]
0x140014059  mov     r8d, eax; Size
0x14001405c  mov     edx, [rdi+54h]
0x14001405f  add     rcx, r9; Buf1
0x140014062  add     rdx, rdi; Buf2
0x140014065  call    memcmp_0
0x14001406a  test    eax, eax
0x14001406c  jz      short loc_14001407C
0x14001406e  mov     rbx, [rbx]
0x140014071  cmp     rbx, r14
0x140014074  jnz     loc_140013F44
0x14001407a  jmp     short loc_140014081
0x14001407c  test    rbx, rbx
0x14001407f  jnz     short loc_1400140DD
0x140014081  call    cs:__imp_GetProcessHeap
0x140014087  mov     edx, 8; dwFlags
0x14001408c  mov     rcx, rax; hHeap
0x14001408f  lea     r8d, [rdx+18h]; dwBytes
0x140014093  call    cs:__imp_HeapAlloc
0x140014099  mov     rbx, rax
0x14001409c  test    rax, rax
0x14001409f  jz      short loc_1400140D8
0x1400140a1  mov     ecx, [rbp+90h]
0x1400140a7  lea     eax, [rcx+1]
0x1400140aa  mov     [rbp+90h], eax
0x1400140b0  mov     [rbx+10h], ecx
0x1400140b3  lea     rcx, [rbp+98h]
0x1400140ba  mov     eax, [rdi+64h]
0x1400140bd  mov     [rbx+14h], eax
0x1400140c0  mov     [rbx+18h], rdi
0x1400140c4  mov     rax, [rcx+8]
0x1400140c8  mov     [rbx], rcx
0x1400140cb  mov     [rbx+8], rax
0x1400140cf  mov     [rax], rbx
0x1400140d2  mov     [rcx+8], rbx
0x1400140d6  jmp     short loc_1400140DD
0x1400140d8  call    RaiseAllocationFailure
0x1400140dd  mov     eax, [rbx+10h]
0x1400140e0  add     rsp, 20h
0x1400140e4  pop     r15
0x1400140e6  pop     r14
0x1400140e8  pop     r12
0x1400140ea  pop     rdi
0x1400140eb  pop     rsi
0x1400140ec  pop     rbp
0x1400140ed  pop     rbx
0x1400140ee  retn
```
