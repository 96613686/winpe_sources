# MTX_AHUFF_ReadSymbol

- ea: `0x180009580`
- end: `0x180009760`
- name: `MTX_AHUFF_ReadSymbol`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800088a0`

## callees

- `0x180009580`
- `0x180009770`
- `0x18001c9ec`

## import_xrefs

- `msvcrt!longjmp` at `0x18000974f`
- `msvcrt!longjmp` at `0x18000974f`

## pseudocode

```c
__int64 __fastcall MTX_AHUFF_ReadSymbol(__int64 *a1)
{
  __int64 v1; // r9
  __int64 v3; // r8
  __int64 v4; // rbx
  __int16 v5; // cx
  __int64 v6; // rdx
  __int16 v7; // r15
  __int64 v8; // r14
  __int16 v9; // di
  __int64 v10; // rax
  int v11; // esi
  bool v12; // zf
  __int64 v13; // rbp
  __int64 v14; // rcx
  __int64 v16; // rdx
  __int16 v17; // cx
  __int16 v18; // bp

  v1 = *a1;
  v3 = a1[4];
  LOWORD(v4) = 1;
  do
  {
    v5 = *(_WORD *)(v3 + 16);
    *(_WORD *)(v3 + 16) = v5 - 1;
    if ( !v5 )
    {
      v16 = *(int *)(v3 + 8);
      if ( (int)v16 >= *(_DWORD *)(v3 + 12) )
        longjmp((_JBTYPE *)(*(_QWORD *)(v3 + 40) + 48LL), 3304);
      v17 = *(unsigned __int8 *)(v16 + *(_QWORD *)v3);
      ++*(_DWORD *)(v3 + 20);
      *(_DWORD *)(v3 + 8) = v16 + 1;
      *(_WORD *)(v3 + 18) = v17;
      *(_WORD *)(v3 + 16) = 7;
    }
    *(_WORD *)(v3 + 18) *= 2;
    v6 = 4;
    if ( (*(_WORD *)(v3 + 18) & 0x100) == 0 )
      v6 = 2;
    v4 = *(__int16 *)(v1 + v6 + 12LL * (__int16)v4);
    v7 = *(_WORD *)(v1 + 12 * v4 + 6);
  }
  while ( v7 < 0 );
  v8 = *a1;
  if ( (_DWORD)v4 != 1 )
  {
    do
    {
      v9 = v4 - 1;
      v10 = (__int16)(v4 - 1);
      v11 = *(_DWORD *)(v8 + 12LL * (__int16)v4 + 8);
      v12 = *(_DWORD *)(v8 + 12 * v10 + 8) == v11;
      v13 = v8 + 12 * v10;
      if ( *(_DWORD *)(v13 + 8) < v11 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v12 = *(_DWORD *)(v13 + 8) == v11;
      }
      if ( v12 )
      {
        do
          v18 = v9--;
        while ( *(_DWORD *)(v8 + 12LL * v9 + 8) == v11 );
        if ( v18 >= 1 )
        {
          if ( v18 > 1 )
          {
            SwapNodes(a1, (unsigned __int16)v4, (unsigned __int16)v18);
            LOWORD(v4) = v18;
          }
        }
        else
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
      }
      v14 = 3LL * (__int16)v4;
      LOWORD(v4) = *(_WORD *)(v8 + 12LL * (__int16)v4);
      *(_DWORD *)(v8 + 4 * v14 + 8) = v11 + 1;
    }
    while ( (_WORD)v4 != 1 );
  }
  if ( ++*(_DWORD *)(v8 + 12LL * (unsigned __int16)v4 + 8) != *(_DWORD *)(v8
                                                                        + 12LL
                                                                        * *(__int16 *)(v8
                                                                                     + 12LL * (unsigned __int16)v4
                                                                                     + 2)
                                                                        + 8)
                                                            + *(_DWORD *)(v8
                                                                        + 12LL
                                                                        * *(__int16 *)(v8
                                                                                     + 12LL * (unsigned __int16)v4
                                                                                     + 4)
                                                                        + 8) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return (unsigned __int16)v7;
}

```

## disassembly

```asm
0x180009580  push    rbx
0x180009582  push    rdi
0x180009583  push    r12
0x180009585  sub     rsp, 20h
0x180009589  mov     r9, [rcx]
0x18000958c  mov     r12, rcx
0x18000958f  mov     r8, [rcx+20h]
0x180009593  mov     ebx, 1
0x180009598  mov     r10d, 100h
0x18000959e  mov     [rsp+38h+arg_18], r15
0x1800095a3  mov     r11d, 2
0x1800095a9  nop     dword ptr [rax+00000000h]
0x1800095b0  movzx   ecx, word ptr [r8+10h]
0x1800095b5  lea     eax, [rcx-1]
0x1800095b8  mov     [r8+10h], ax
0x1800095bd  test    cx, cx
0x1800095c0  jz      loc_1800096C7
0x1800095c6  shl     word ptr [r8+12h], 1
0x1800095cb  mov     edx, 4
0x1800095d0  test    [r8+12h], r10w
0x1800095d5  movsx   rax, bx
0x1800095d9  cmovz   rdx, r11
0x1800095dd  lea     rcx, [rax+rax*2]
0x1800095e1  lea     rbx, [r9+rdx]
0x1800095e5  movsx   rbx, word ptr [rbx+rcx*4]
0x1800095ea  lea     rcx, [rbx+rbx*2]
0x1800095ee  movzx   r15d, word ptr [r9+rcx*4+6]
0x1800095f4  test    r15w, r15w
0x1800095f8  js      short loc_1800095B0
0x1800095fa  mov     [rsp+38h+arg_10], r14
0x1800095ff  mov     r14, [r12]
0x180009603  cmp     ebx, 1
0x180009606  jz      short loc_180009676
0x180009608  mov     [rsp+38h+arg_0], rbp
0x18000960d  mov     [rsp+38h+arg_8], rsi
0x180009612  nop     dword ptr [rax+00h]
0x180009616  nop     word ptr [rax+rax+00000000h]
0x180009620  movsx   rax, bx
0x180009624  lea     edi, [rbx-1]
0x180009627  lea     rcx, [rax+rax*2]
0x18000962b  movsx   rax, di
0x18000962f  mov     esi, [r14+rcx*4+8]
0x180009634  lea     rcx, [rax+rax*2]
0x180009638  cmp     [r14+rcx*4+8], esi
0x18000963d  lea     rbp, [r14+rcx*4]
0x180009641  jge     short loc_18000964B
0x180009643  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009648  cmp     [rbp+8], esi
0x18000964b  jz      loc_180009700
0x180009651  movsx   rax, bx
0x180009655  lea     rcx, [rax+rax*2]
0x180009659  movzx   ebx, word ptr [r14+rcx*4]
0x18000965e  lea     eax, [rsi+1]
0x180009661  mov     [r14+rcx*4+8], eax
0x180009666  cmp     bx, 1
0x18000966a  jnz     short loc_180009620
0x18000966c  mov     rsi, [rsp+38h+arg_8]
0x180009671  mov     rbp, [rsp+38h+arg_0]
0x180009676  movzx   eax, bx
0x180009679  lea     rcx, [rax+rax*2]
0x18000967d  inc     dword ptr [r14+rcx*4+8]
0x180009682  lea     rdx, [r14+rcx*4]
0x180009686  movsx   rcx, word ptr [r14+rcx*4+4]
0x18000968c  mov     r9d, [rdx+8]
0x180009690  lea     r8, [rcx+rcx*2]
0x180009694  movsx   rcx, word ptr [rdx+2]
0x180009699  lea     rdx, [rcx+rcx*2]
0x18000969d  mov     ecx, [r14+r8*4+8]
0x1800096a2  add     ecx, [r14+rdx*4+8]
0x1800096a7  mov     r14, [rsp+38h+arg_10]
0x1800096ac  cmp     r9d, ecx
0x1800096af  jnz     loc_180009756
0x1800096b5  movzx   eax, r15w
0x1800096b9  mov     r15, [rsp+38h+arg_18]
0x1800096be  add     rsp, 20h
0x1800096c2  pop     r12
0x1800096c4  pop     rdi
0x1800096c5  pop     rbx
0x1800096c6  retn
0x1800096c7  movsxd  rdx, dword ptr [r8+8]
0x1800096cb  cmp     edx, [r8+0Ch]
0x1800096cf  jge     short loc_180009742
0x1800096d1  mov     rax, [r8]
0x1800096d4  movzx   ecx, byte ptr [rdx+rax]
0x1800096d8  lea     eax, [rdx+1]
0x1800096db  inc     dword ptr [r8+14h]
0x1800096df  mov     [r8+8], eax
0x1800096e3  mov     [r8+12h], cx
0x1800096e8  mov     word ptr [r8+10h], 7
0x1800096ef  jmp     loc_1800095C6
0x180009700  movzx   ebp, di
0x180009703  dec     di
0x180009706  movsx   rax, di
0x18000970a  lea     rcx, [rax+rax*2]
0x18000970e  cmp     [r14+rcx*4+8], esi
0x180009713  jz      short loc_180009700
0x180009715  cmp     bp, 1
0x180009719  jge     short loc_180009725
0x18000971b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009720  jmp     loc_180009651
0x180009725  jle     loc_180009651
0x18000972b  movzx   r8d, bp
0x18000972f  movzx   edx, bx
0x180009732  mov     rcx, r12
0x180009735  call    SwapNodes
0x18000973a  movzx   ebx, bp
0x18000973d  jmp     loc_180009651
0x180009742  mov     rcx, [r8+28h]
0x180009746  mov     edx, 0CE8h; Value
0x18000974b  add     rcx, 30h ; '0'; Buf
0x18000974f  call    cs:__imp_longjmp
0x180009756  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000975b  jmp     loc_1800096B5
```
