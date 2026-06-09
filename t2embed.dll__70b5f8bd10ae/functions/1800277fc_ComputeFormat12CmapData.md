# ComputeFormat12CmapData

- ea: `0x1800277fc`
- end: `0x1800278d0`
- name: `ComputeFormat12CmapData`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d5f8`

## callees

- `0x180013230`
- `0x1800277fc`

## pseudocode

```c
__int64 __fastcall ComputeFormat12CmapData(_DWORD *a1, __int64 a2, _DWORD *a3, __int64 a4, unsigned int a5)
{
  unsigned int v5; // r10d
  __int64 v6; // rdi
  unsigned int v9; // ebp
  __int64 v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ebx
  __int64 result; // rax
  unsigned int v16; // ecx

  v5 = 0;
  v6 = 0;
  *a3 = 0;
  if ( a5 )
  {
    v9 = a5 - 1;
    do
    {
      v10 = v5;
      if ( v5 < v9 )
      {
        do
        {
          v11 = v5 + 1;
          if ( *(_DWORD *)(a4 + 8LL * v5) + 1 != *(_DWORD *)(a4 + 8 * v11) )
            break;
          if ( *(_DWORD *)(a4 + 8LL * v5 + 4) + 1 != *(_DWORD *)(a4 + 8 * v11 + 4) )
            break;
          ++v5;
        }
        while ( (unsigned int)v11 < v9 );
      }
      v12 = 3 * v6;
      *(_DWORD *)(a2 + 4 * v12) = *(_DWORD *)(a4 + 8 * v10);
      v13 = v5++;
      v6 = (unsigned int)(v6 + 1);
      *(_DWORD *)(a2 + 4 * v12 + 4) = *(_DWORD *)(a4 + 8 * v13);
      *(_DWORD *)(a2 + 4 * v12 + 8) = *(_DWORD *)(a4 + 8 * v10 + 4);
    }
    while ( v5 < a5 );
    *a3 = v6;
  }
  *a1 = 12;
  v14 = v6 * (unsigned __int16)GetGenericSize(&FORMAT12_GROUPS_CONTROL);
  result = GetGenericSize(&CMAP_FORMAT12_CONTROL);
  v16 = v14 + (unsigned __int16)result;
  a1[1] = v16;
  if ( v16 < (unsigned int)v6 )
  {
    a1[1] = 0;
    LODWORD(v6) = 0;
  }
  a1[3] = v6;
  return result;
}

```

## disassembly

```asm
0x1800277fc  push    rbx
0x1800277fe  push    rbp
0x1800277ff  push    rsi
0x180027800  push    rdi
0x180027801  push    r14
0x180027803  push    r15
0x180027805  sub     rsp, 28h
0x180027809  mov     r11d, [rsp+58h+arg_20]
0x180027811  xor     r10d, r10d
0x180027814  xor     edi, edi
0x180027816  mov     [r8], r10d
0x180027819  mov     r14, rdx
0x18002781c  mov     rsi, rcx
0x18002781f  test    r11d, r11d
0x180027822  jz      short loc_180027887
0x180027824  lea     ebp, [r11-1]
0x180027828  mov     r15d, r10d
0x18002782b  cmp     r10d, ebp
0x18002782e  jnb     short loc_180027858
0x180027830  mov     edx, r10d
0x180027833  lea     ecx, [r10+1]
0x180027837  mov     eax, [r9+rdx*8]
0x18002783b  inc     eax
0x18002783d  cmp     eax, [r9+rcx*8]
0x180027841  jnz     short loc_180027858
0x180027843  mov     eax, [r9+rdx*8+4]
0x180027848  inc     eax
0x18002784a  cmp     eax, [r9+rcx*8+4]
0x18002784f  jnz     short loc_180027858
0x180027851  mov     r10d, ecx
0x180027854  cmp     ecx, ebp
0x180027856  jb      short loc_180027830
0x180027858  mov     eax, [r9+r15*8]
0x18002785c  lea     rdx, [rdi+rdi*2]
0x180027860  mov     [r14+rdx*4], eax
0x180027864  mov     ecx, r10d
0x180027867  inc     r10d
0x18002786a  inc     edi
0x18002786c  mov     ecx, [r9+rcx*8]
0x180027870  mov     [r14+rdx*4+4], ecx
0x180027875  mov     eax, [r9+r15*8+4]
0x18002787a  mov     [r14+rdx*4+8], eax
0x18002787f  cmp     r10d, r11d
0x180027882  jb      short loc_180027828
0x180027884  mov     [r8], edi
0x180027887  lea     rcx, FORMAT12_GROUPS_CONTROL
0x18002788e  mov     dword ptr [rsi], 0Ch
0x180027894  call    GetGenericSize
0x180027899  movzx   ebx, ax
0x18002789c  lea     rcx, CMAP_FORMAT12_CONTROL
0x1800278a3  imul    ebx, edi
0x1800278a6  call    GetGenericSize
0x1800278ab  movzx   ecx, ax
0x1800278ae  add     ecx, ebx
0x1800278b0  mov     [rsi+4], ecx
0x1800278b3  cmp     ecx, edi
0x1800278b5  jnb     short loc_1800278C0
0x1800278b7  mov     dword ptr [rsi+4], 0
0x1800278be  xor     edi, edi
0x1800278c0  mov     [rsi+0Ch], edi
0x1800278c3  add     rsp, 28h
0x1800278c7  pop     r15
0x1800278c9  pop     r14
0x1800278cb  pop     rdi
0x1800278cc  pop     rsi
0x1800278cd  pop     rbp
0x1800278ce  pop     rbx
0x1800278cf  retn
```
