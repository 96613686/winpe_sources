# WcGetEnumEntry

- ea: `0x140014198`
- end: `0x1400142c8`
- name: `WcGetEnumEntry`
- size: `304`
- prototype: `int *__fastcall(__int64, unsigned int, _DWORD *, _DWORD *, int *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140028f74`
- `0x14002b71c`
- `0x14002b77c`
- `0x14002b7d8`
- `0x14002e898`

## callees

- `0x140014198`

## pseudocode

```c
int *__fastcall WcGetEnumEntry(__int64 a1, unsigned int a2, _DWORD *a3, _DWORD *a4, int *a5)
{
  unsigned int v5; // r10d
  int *v9; // r8
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // edx

  v5 = *(_DWORD *)(a1 + 60);
  if ( a2 >= v5 )
    return 0;
  v9 = 0;
  v10 = *(_DWORD *)(a1 + 52) - 12;
  if ( !v10 )
  {
    if ( a2 + 12 < v5 )
    {
      v9 = (int *)(a2 + *(_QWORD *)(a1 + 72));
      *a3 = 12;
      v18 = *v9;
      *a4 = v9[2];
      *a5 = v18;
    }
    return v9;
  }
  v11 = v10 - 21;
  if ( v11 )
  {
    v12 = v11 - 27;
    if ( v12 )
    {
      v13 = v12 - 3;
      if ( v13 )
      {
        v14 = v13 - 15;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              if ( v16 != 1 || a2 + 122 >= v5 )
                return v9;
              *a3 = 122;
              goto LABEL_23;
            }
            if ( a2 + 96 < v5 )
            {
              *a3 = 96;
LABEL_23:
              v9 = (int *)(a2 + *(_QWORD *)(a1 + 72));
              v17 = *v9;
              *a4 = v9[15];
LABEL_26:
              *a5 = v17;
            }
          }
          else if ( a2 + 106 < v5 )
          {
            *a3 = 106;
            goto LABEL_23;
          }
        }
        else if ( a2 + 80 < v5 )
        {
          *a3 = 80;
          goto LABEL_23;
        }
      }
      else if ( a2 + 114 < v5 )
      {
        *a3 = 114;
        goto LABEL_23;
      }
    }
    else if ( a2 + 88 < v5 )
    {
      *a3 = 88;
      goto LABEL_23;
    }
  }
  else if ( a2 + 16 <= v5 )
  {
    v17 = 16;
    v9 = (int *)(*(_QWORD *)(a1 + 72) + a2);
    *a3 = 16;
    *a4 = 0;
    goto LABEL_26;
  }
  return v9;
}

```

## disassembly

```asm
0x140014198  mov     [rsp+arg_0], rbx
0x14001419d  mov     r10d, [rcx+3Ch]
0x1400141a1  mov     rbx, r8
0x1400141a4  mov     r11, rcx
0x1400141a7  cmp     edx, r10d
0x1400141aa  jb      short loc_1400141B3
0x1400141ac  xor     eax, eax
0x1400141ae  jmp     loc_1400142C1
0x1400141b3  mov     ecx, [rcx+34h]
0x1400141b6  xor     r8d, r8d
0x1400141b9  sub     ecx, 0Ch
0x1400141bc  jz      loc_140014296
0x1400141c2  sub     ecx, 15h
0x1400141c5  jz      loc_140014270
0x1400141cb  sub     ecx, 1Bh
0x1400141ce  jz      short loc_14001424D
0x1400141d0  sub     ecx, 3
0x1400141d3  jz      short loc_14001423D
0x1400141d5  sub     ecx, 0Fh
0x1400141d8  jz      short loc_140014229
0x1400141da  sub     ecx, 1
0x1400141dd  jz      short loc_140014215
0x1400141df  sub     ecx, 1
0x1400141e2  jz      short loc_140014201
0x1400141e4  cmp     ecx, 1
0x1400141e7  jnz     loc_1400142BE
0x1400141ed  lea     eax, [rdx+7Ah]
0x1400141f0  cmp     eax, r10d
0x1400141f3  jnb     loc_1400142BE
0x1400141f9  mov     dword ptr [rbx], 7Ah ; 'z'
0x1400141ff  jmp     short loc_14001425B
0x140014201  lea     eax, [rdx+60h]
0x140014204  cmp     eax, r10d
0x140014207  jnb     loc_1400142BE
0x14001420d  mov     dword ptr [rbx], 60h ; '`'
0x140014213  jmp     short loc_14001425B
0x140014215  lea     eax, [rdx+6Ah]
0x140014218  cmp     eax, r10d
0x14001421b  jnb     loc_1400142BE
0x140014221  mov     dword ptr [rbx], 6Ah ; 'j'
0x140014227  jmp     short loc_14001425B
0x140014229  lea     eax, [rdx+50h]
0x14001422c  cmp     eax, r10d
0x14001422f  jnb     loc_1400142BE
0x140014235  mov     dword ptr [rbx], 50h ; 'P'
0x14001423b  jmp     short loc_14001425B
0x14001423d  lea     eax, [rdx+72h]
0x140014240  cmp     eax, r10d
0x140014243  jnb     short loc_1400142BE
0x140014245  mov     dword ptr [rbx], 72h ; 'r'
0x14001424b  jmp     short loc_14001425B
0x14001424d  lea     eax, [rdx+58h]
0x140014250  cmp     eax, r10d
0x140014253  jnb     short loc_1400142BE
0x140014255  mov     dword ptr [rbx], 58h ; 'X'
0x14001425b  mov     r8, [r11+48h]
0x14001425f  mov     ecx, edx
0x140014261  add     r8, rcx
0x140014264  mov     eax, [r8+3Ch]
0x140014268  mov     ecx, [r8]
0x14001426b  mov     [r9], eax
0x14001426e  jmp     short loc_14001428D
0x140014270  lea     eax, [rdx+10h]
0x140014273  cmp     eax, r10d
0x140014276  ja      short loc_1400142BE
0x140014278  mov     ecx, 10h
0x14001427d  mov     r8d, edx
0x140014280  add     r8, [r11+48h]
0x140014284  mov     [rbx], ecx
0x140014286  mov     dword ptr [r9], 0
0x14001428d  mov     rax, [rsp+arg_20]
0x140014292  mov     [rax], ecx
0x140014294  jmp     short loc_1400142BE
0x140014296  lea     eax, [rdx+0Ch]
0x140014299  cmp     eax, r10d
0x14001429c  jnb     short loc_1400142BE
0x14001429e  mov     r8, [r11+48h]
0x1400142a2  mov     ecx, edx
0x1400142a4  add     r8, rcx
0x1400142a7  mov     dword ptr [rbx], 0Ch
0x1400142ad  mov     ecx, [r8+8]
0x1400142b1  mov     edx, [r8]
0x1400142b4  mov     [r9], ecx
0x1400142b7  mov     rcx, [rsp+arg_20]
0x1400142bc  mov     [rcx], edx
0x1400142be  mov     rax, r8
0x1400142c1  mov     rbx, [rsp+arg_0]
0x1400142c6  retn
```
