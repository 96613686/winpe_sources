# To_SECONDARYLOGONINFOW

- ea: `0x180001160`
- end: `0x180001466`
- name: `To_SECONDARYLOGONINFOW`
- size: `774`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180001160`
- `0x180002f70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000117c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000117c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800011ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800011d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800011ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800011d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001190`

## pseudocode

```c
__int64 __fastcall To_SECONDARYLOGONINFOW(__int64 a1, _QWORD *a2)
{
  HANDLE ProcessHeap; // rax
  void *v5; // r14
  char *v6; // rdi
  DWORD LastError; // ebx
  _DWORD *v8; // rax
  unsigned int i; // edx
  unsigned __int16 *v10; // rax
  _QWORD *v11; // r9
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v17; // edx
  __int64 v19; // [rsp+30h] [rbp-68h]
  _QWORD v20[9]; // [rsp+38h] [rbp-60h]

  ProcessHeap = GetProcessHeap();
  v5 = ProcessHeap;
  if ( !ProcessHeap )
  {
    v6 = 0;
    LastError = GetLastError();
    goto LABEL_26;
  }
  LastError = 8;
  v6 = (char *)HeapAlloc(ProcessHeap, 8u, 0x60u);
  if ( !v6 || (v8 = HeapAlloc(v5, 8u, 0x70u), (*(_QWORD *)v6 = v8) == 0) )
  {
LABEL_26:
    Free_SECONDARYLOGONINFOW(v6);
    return LastError;
  }
  v19 = a1;
  v20[0] = v6 + 8;
  v20[1] = a1 + 16;
  v20[2] = v6 + 16;
  v20[3] = a1 + 48;
  v20[4] = v6 + 24;
  v20[5] = a1 + 64;
  v20[6] = v6 + 32;
  v20[7] = a1 + 80;
  v20[8] = v6 + 48;
  *v8 = 112;
  *(_QWORD *)(*(_QWORD *)v6 + 8LL) = *(_QWORD *)(a1 + 104);
  *(_QWORD *)(*(_QWORD *)v6 + 16LL) = *(_QWORD *)(a1 + 112);
  *(_QWORD *)(*(_QWORD *)v6 + 24LL) = *(_QWORD *)(a1 + 120);
  *(_DWORD *)(*(_QWORD *)v6 + 32LL) = *(_DWORD *)(a1 + 128);
  *(_DWORD *)(*(_QWORD *)v6 + 36LL) = *(_DWORD *)(a1 + 132);
  *(_DWORD *)(*(_QWORD *)v6 + 40LL) = *(_DWORD *)(a1 + 136);
  *(_DWORD *)(*(_QWORD *)v6 + 44LL) = *(_DWORD *)(a1 + 140);
  *(_DWORD *)(*(_QWORD *)v6 + 48LL) = *(_DWORD *)(a1 + 144);
  *(_DWORD *)(*(_QWORD *)v6 + 52LL) = *(_DWORD *)(a1 + 148);
  *(_DWORD *)(*(_QWORD *)v6 + 56LL) = *(_DWORD *)(a1 + 152);
  *(_DWORD *)(*(_QWORD *)v6 + 60LL) = *(_DWORD *)(a1 + 156);
  *(_WORD *)(*(_QWORD *)v6 + 64LL) = *(_WORD *)(a1 + 160);
  *(_WORD *)(*(_QWORD *)v6 + 66LL) = *(_WORD *)(a1 + 162);
  *(_QWORD *)(*(_QWORD *)v6 + 72LL) = *(_QWORD *)(a1 + 168);
  *(_QWORD *)(*(_QWORD *)v6 + 80LL) = *(_QWORD *)(a1 + 176);
  *(_QWORD *)(*(_QWORD *)v6 + 88LL) = *(_QWORD *)(a1 + 184);
  *(_QWORD *)(*(_QWORD *)v6 + 96LL) = *(_QWORD *)(a1 + 192);
  *(_QWORD *)(*(_QWORD *)v6 + 104LL) = 0;
  for ( i = 0; i < 5; ++i )
  {
    v10 = (unsigned __int16 *)v20[2 * i - 1];
    if ( v10 )
    {
      v11 = (_QWORD *)v20[2 * i];
      v12 = *((_QWORD *)v10 + 1);
      if ( !v12 )
        goto LABEL_11;
      v13 = *v10;
      if ( v10[1] > (unsigned __int16)v13 )
      {
        *(_WORD *)(v12 + 2 * v13) = 0;
LABEL_11:
        *v11 = *((_QWORD *)v10 + 1);
        LastError = 0;
        goto LABEL_13;
      }
    }
    LastError = 87;
LABEL_13:
    if ( LastError )
      goto LABEL_26;
  }
  v14 = *(_QWORD *)(a1 + 40);
  *((_QWORD *)v6 + 8) = v14;
  *((_WORD *)v6 + 28) = *(_WORD *)(a1 + 32);
  v15 = *(unsigned __int16 *)(a1 + 34);
  *((_WORD *)v6 + 29) = v15;
  if ( v14 && (_WORD)v15 )
    *(_WORD *)(v14 + 2 * v15 - 2) = 0;
  v16 = *(_QWORD *)(a1 + 208);
  *((_QWORD *)v6 + 5) = v16;
  if ( v16 )
  {
    v17 = 4;
    if ( (*(_DWORD *)(a1 + 232) & 0x400) == 0 )
      v17 = 2;
    if ( *(_DWORD *)(a1 + 200) < v17 )
    {
      LastError = 87;
      goto LABEL_26;
    }
    while ( v17 )
      *(_BYTE *)(*(_DWORD *)(a1 + 200) - v17-- + *(_QWORD *)(a1 + 208)) = 0;
  }
  *((_DWORD *)v6 + 18) = *(_DWORD *)(a1 + 216);
  *((_DWORD *)v6 + 19) = *(_DWORD *)(a1 + 228);
  *((_DWORD *)v6 + 20) = *(_DWORD *)(a1 + 232);
  *((_DWORD *)v6 + 21) = *(_DWORD *)(a1 + 236);
  *((_QWORD *)v6 + 11) = *(_QWORD *)(a1 + 256);
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x180001160  mov     [rsp+arg_0], rbx
0x180001165  mov     [rsp+arg_8], rsi
0x18000116a  push    rdi
0x18000116b  push    r14
0x18000116d  push    r15
0x18000116f  sub     rsp, 80h
0x180001176  mov     r15, rdx
0x180001179  mov     rsi, rcx
0x18000117c  call    cs:__imp_GetProcessHeap
0x180001182  mov     r14, rax
0x180001185  test    rax, rax
0x180001188  jnz     short loc_18000119D
0x18000118a  xor     r10d, r10d
0x18000118d  mov     edi, r10d
0x180001190  call    cs:__imp_GetLastError
0x180001196  mov     ebx, eax
0x180001198  jmp     loc_180001443
0x18000119d  mov     ebx, 8
0x1800011a2  mov     r8d, 60h ; '`'; dwBytes
0x1800011a8  mov     edx, ebx; dwFlags
0x1800011aa  mov     rcx, r14; hHeap
0x1800011ad  call    cs:__imp_HeapAlloc
0x1800011b3  mov     rdi, rax
0x1800011b6  mov     [rsp+98h+arg_10], rax
0x1800011be  test    rax, rax
0x1800011c1  jz      loc_180001443
0x1800011c7  mov     r8d, 70h ; 'p'; dwBytes
0x1800011cd  mov     edx, ebx; dwFlags
0x1800011cf  mov     rcx, r14; hHeap
0x1800011d2  call    cs:__imp_HeapAlloc
0x1800011d8  mov     rdx, rax
0x1800011db  mov     [rdi], rax
0x1800011de  test    rax, rax
0x1800011e1  jz      loc_180001443
0x1800011e7  mov     [rsp+98h+var_68], rsi
0x1800011ec  lea     rcx, [rdi+8]
0x1800011f0  mov     [rsp+98h+var_60], rcx
0x1800011f5  lea     rcx, [rsi+10h]
0x1800011f9  mov     [rsp+98h+var_58], rcx
0x1800011fe  lea     rax, [rdi+10h]
0x180001202  mov     [rsp+98h+var_50], rax
0x180001207  lea     rax, [rsi+30h]
0x18000120b  mov     [rsp+98h+var_48], rax
0x180001210  lea     rax, [rdi+18h]
0x180001214  mov     [rsp+98h+var_40], rax
0x180001219  lea     rax, [rsi+40h]
0x18000121d  mov     [rsp+98h+var_38], rax
0x180001222  lea     rax, [rdi+20h]
0x180001226  mov     [rsp+98h+var_30], rax
0x18000122b  lea     rax, [rsi+50h]
0x18000122f  mov     [rsp+98h+var_28], rax
0x180001234  lea     rax, [rdi+30h]
0x180001238  mov     [rsp+98h+var_20], rax
0x18000123d  mov     dword ptr [rdx], 70h ; 'p'
0x180001243  mov     rcx, [rdi]
0x180001246  mov     rax, [rsi+68h]
0x18000124a  mov     [rcx+8], rax
0x18000124e  mov     rcx, [rdi]
0x180001251  mov     rax, [rsi+70h]
0x180001255  mov     [rcx+10h], rax
0x180001259  mov     rcx, [rdi]
0x18000125c  mov     rax, [rsi+78h]
0x180001260  mov     [rcx+18h], rax
0x180001264  mov     rcx, [rdi]
0x180001267  mov     eax, [rsi+80h]
0x18000126d  mov     [rcx+20h], eax
0x180001270  mov     rcx, [rdi]
0x180001273  mov     eax, [rsi+84h]
0x180001279  mov     [rcx+24h], eax
0x18000127c  mov     rcx, [rdi]
0x18000127f  mov     eax, [rsi+88h]
0x180001285  mov     [rcx+28h], eax
0x180001288  mov     rcx, [rdi]
0x18000128b  mov     eax, [rsi+8Ch]
0x180001291  mov     [rcx+2Ch], eax
0x180001294  mov     rcx, [rdi]
0x180001297  mov     eax, [rsi+90h]
0x18000129d  mov     [rcx+30h], eax
0x1800012a0  mov     rcx, [rdi]
0x1800012a3  mov     eax, [rsi+94h]
0x1800012a9  mov     [rcx+34h], eax
0x1800012ac  mov     rcx, [rdi]
0x1800012af  mov     eax, [rsi+98h]
0x1800012b5  mov     [rcx+38h], eax
0x1800012b8  mov     rcx, [rdi]
0x1800012bb  mov     eax, [rsi+9Ch]
0x1800012c1  mov     [rcx+3Ch], eax
0x1800012c4  mov     rcx, [rdi]
0x1800012c7  movzx   eax, word ptr [rsi+0A0h]
0x1800012ce  mov     [rcx+40h], ax
0x1800012d2  mov     rcx, [rdi]
0x1800012d5  movzx   eax, word ptr [rsi+0A2h]
0x1800012dc  mov     [rcx+42h], ax
0x1800012e0  mov     rcx, [rdi]
0x1800012e3  mov     rax, [rsi+0A8h]
0x1800012ea  mov     [rcx+48h], rax
0x1800012ee  mov     rcx, [rdi]
0x1800012f1  mov     rax, [rsi+0B0h]
0x1800012f8  mov     [rcx+50h], rax
0x1800012fc  mov     rcx, [rdi]
0x1800012ff  mov     rax, [rsi+0B8h]
0x180001306  mov     [rcx+58h], rax
0x18000130a  mov     rcx, [rdi]
0x18000130d  mov     rax, [rsi+0C0h]
0x180001314  mov     [rcx+60h], rax
0x180001318  mov     rax, [rdi]
0x18000131b  xor     r10d, r10d
0x18000131e  mov     [rax+68h], r10
0x180001322  mov     edx, r10d
0x180001325  mov     [rsp+98h+var_78], edx
0x180001329  cmp     edx, 5
0x18000132c  jnb     short loc_18000137A
0x18000132e  mov     ecx, edx
0x180001330  add     rcx, rcx
0x180001333  mov     rax, [rsp+rcx*8+98h+var_68]
0x180001338  test    rax, rax
0x18000133b  jz      short loc_180001365
0x18000133d  mov     r9, [rsp+rcx*8+98h+var_60]
0x180001342  mov     r8, [rax+8]
0x180001346  test    r8, r8
0x180001349  jz      short loc_180001359
0x18000134b  movzx   ecx, word ptr [rax]
0x18000134e  cmp     [rax+2], cx
0x180001352  jbe     short loc_180001365
0x180001354  mov     [r8+rcx*2], r10w
0x180001359  mov     rcx, [rax+8]
0x18000135d  mov     [r9], rcx
0x180001360  mov     ebx, r10d
0x180001363  jmp     short loc_18000136A
0x180001365  mov     ebx, 57h ; 'W'
0x18000136a  mov     [rsp+98h+var_70], ebx
0x18000136e  test    ebx, ebx
0x180001370  jnz     loc_180001443
0x180001376  inc     edx
0x180001378  jmp     short loc_180001325
0x18000137a  mov     rcx, [rsi+28h]
0x18000137e  mov     [rdi+40h], rcx
0x180001382  movzx   eax, word ptr [rsi+20h]
0x180001386  mov     [rdi+38h], ax
0x18000138a  movzx   eax, word ptr [rsi+22h]
0x18000138e  mov     [rdi+3Ah], ax
0x180001392  test    rcx, rcx
0x180001395  jz      short loc_1800013A2
0x180001397  test    ax, ax
0x18000139a  jz      short loc_1800013A2
0x18000139c  mov     [rcx+rax*2-2], r10w
0x1800013a2  mov     rax, [rsi+0D0h]
0x1800013a9  mov     [rdi+28h], rax
0x1800013ad  test    rax, rax
0x1800013b0  jz      short loc_1800013FB
0x1800013b2  test    dword ptr [rsi+0E8h], 400h
0x1800013bc  mov     edx, 4
0x1800013c1  mov     eax, 2
0x1800013c6  cmovz   edx, eax
0x1800013c9  mov     [rsp+98h+var_74], edx
0x1800013cd  cmp     [rsi+0C8h], edx
0x1800013d3  jnb     short loc_1800013DC
0x1800013d5  mov     ebx, 57h ; 'W'
0x1800013da  jmp     short loc_180001443
0x1800013dc  test    edx, edx
0x1800013de  jz      short loc_1800013FB
0x1800013e0  mov     ecx, [rsi+0C8h]
0x1800013e6  sub     ecx, edx
0x1800013e8  mov     rax, [rsi+0D0h]
0x1800013ef  mov     [rcx+rax], r10b
0x1800013f3  dec     edx
0x1800013f5  mov     [rsp+98h+var_74], edx
0x1800013f9  jmp     short loc_1800013DC
0x1800013fb  mov     eax, [rsi+0D8h]
0x180001401  mov     [rdi+48h], eax
0x180001404  mov     eax, [rsi+0E4h]
0x18000140a  mov     [rdi+4Ch], eax
0x18000140d  mov     eax, [rsi+0E8h]
0x180001413  mov     [rdi+50h], eax
0x180001416  mov     eax, [rsi+0ECh]
0x18000141c  mov     [rdi+54h], eax
0x18000141f  mov     rax, [rsi+100h]
0x180001426  mov     [rdi+58h], rax
0x18000142a  mov     [r15], rdi
0x18000142d  mov     ebx, r10d
0x180001430  jmp     short loc_18000144B
0x180001432  mov     ebx, 57h ; 'W'
0x180001437  mov     [rsp+98h+var_70], ebx
0x18000143b  mov     rdi, [rsp+98h+arg_10]
0x180001443  mov     rcx, rdi; lpMem
0x180001446  call    Free_SECONDARYLOGONINFOW
0x18000144b  mov     eax, ebx
0x18000144d  lea     r11, [rsp+98h+var_18]
0x180001455  mov     rbx, [r11+20h]
0x180001459  mov     rsi, [r11+28h]
0x18000145d  mov     rsp, r11
0x180001460  pop     r15
0x180001462  pop     r14
0x180001464  pop     rdi
0x180001465  retn
```
