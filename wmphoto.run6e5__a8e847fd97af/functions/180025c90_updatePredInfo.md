# updatePredInfo

- ea: `0x180025c90`
- end: `0x180025e60`
- name: `updatePredInfo`
- size: `464`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180007340`
- `0x180008ce0`
- `0x18000f244`

## callees

- `0x180025c90`

## pseudocode

```c
__int64 __fastcall updatePredInfo(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v7; // ebx
  __int64 result; // rax
  __int64 v9; // r10
  __int64 v10; // rcx
  __int64 v11; // rdx
  _DWORD *v12; // r8
  _DWORD *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx

  if ( (unsigned int)(a4 - 1) <= 1 )
  {
    v7 = 1;
    LODWORD(result) = 0;
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 34240);
    result = 0;
    if ( v7 <= 0 )
      return result;
  }
  v9 = 48 * a3;
  do
  {
    v10 = (int)result;
    result = (unsigned int)(result + 1);
    v11 = *(_QWORD *)(a1 + 8 * v10 + 35392);
    v12 = *(_DWORD **)(v9 + v11 + 40);
    v13 = (_DWORD *)((v10 << 6) + a2);
    *(_DWORD *)(v9 + v11 + 8) = *v13;
    *(_DWORD *)(v9 + v11) = *(unsigned __int8 *)(a2 + 1156);
    *v12 = v13[1];
    v12[1] = v13[2];
    v12[2] = v13[3];
    v12[3] = v13[4];
    v12[4] = v13[8];
    v12[5] = v13[12];
  }
  while ( (int)result < v7 );
  if ( a4 == 1 )
  {
    v14 = v9 + *(_QWORD *)(a1 + 35400);
    *(_DWORD *)(v14 + 8) = *(_DWORD *)(a2 + 64);
    *(_DWORD *)v14 = *(unsigned __int8 *)(a2 + 1156);
    **(_DWORD **)(v14 + 40) = *(_DWORD *)(a2 + 68);
    *(_DWORD *)(*(_QWORD *)(v14 + 40) + 4LL) = *(_DWORD *)(a2 + 72);
    v15 = v9 + *(_QWORD *)(a1 + 35408);
    *(_DWORD *)(v15 + 8) = *(_DWORD *)(a2 + 128);
    *(_DWORD *)v15 = *(unsigned __int8 *)(a2 + 1156);
    **(_DWORD **)(v15 + 40) = *(_DWORD *)(a2 + 132);
    result = *(unsigned int *)(a2 + 136);
    *(_DWORD *)(*(_QWORD *)(v15 + 40) + 4LL) = result;
  }
  else if ( a4 == 2 )
  {
    v16 = v9 + *(_QWORD *)(a1 + 35400);
    *(_DWORD *)v16 = *(unsigned __int8 *)(a2 + 1156);
    *(_DWORD *)(v16 + 8) = *(_DWORD *)(a2 + 64);
    **(_DWORD **)(v16 + 40) = *(_DWORD *)(a2 + 68);
    *(_DWORD *)(*(_QWORD *)(v16 + 40) + 4LL) = *(_DWORD *)(a2 + 72);
    *(_DWORD *)(*(_QWORD *)(v16 + 40) + 8LL) = *(_DWORD *)(a2 + 84);
    *(_DWORD *)(*(_QWORD *)(v16 + 40) + 12LL) = *(_DWORD *)(a2 + 88);
    *(_DWORD *)(*(_QWORD *)(v16 + 40) + 16LL) = *(_DWORD *)(a2 + 80);
    v17 = v9 + *(_QWORD *)(a1 + 35408);
    *(_DWORD *)v17 = *(unsigned __int8 *)(a2 + 1156);
    *(_DWORD *)(v17 + 8) = *(_DWORD *)(a2 + 128);
    **(_DWORD **)(v17 + 40) = *(_DWORD *)(a2 + 132);
    *(_DWORD *)(*(_QWORD *)(v17 + 40) + 4LL) = *(_DWORD *)(a2 + 136);
    *(_DWORD *)(*(_QWORD *)(v17 + 40) + 8LL) = *(_DWORD *)(a2 + 148);
    *(_DWORD *)(*(_QWORD *)(v17 + 40) + 12LL) = *(_DWORD *)(a2 + 152);
    result = *(unsigned int *)(a2 + 144);
    *(_DWORD *)(*(_QWORD *)(v17 + 40) + 16LL) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180025c90  push    rbx
0x180025c92  push    rsi
0x180025c93  push    rdi
0x180025c94  lea     eax, [r9-1]
0x180025c98  mov     esi, r9d
0x180025c9b  mov     r11, rdx
0x180025c9e  mov     rdi, rcx
0x180025ca1  cmp     eax, 1
0x180025ca4  jbe     loc_180025D2E
0x180025caa  mov     ebx, [rcx+85C0h]
0x180025cb0  xor     eax, eax
0x180025cb2  test    ebx, ebx
0x180025cb4  jle     short loc_180025D2A
0x180025cb6  lea     r10, [r8+r8*2]
0x180025cba  shl     r10, 4
0x180025cbe  movsxd  rcx, eax
0x180025cc1  inc     eax
0x180025cc3  mov     rdx, [rdi+rcx*8+8A40h]
0x180025ccb  shl     rcx, 6
0x180025ccf  mov     r8, [r10+rdx+28h]
0x180025cd4  lea     r9, [rcx+r11]
0x180025cd8  mov     ecx, [rcx+r11]
0x180025cdc  mov     [r10+rdx+8], ecx
0x180025ce1  movzx   ecx, byte ptr [r11+484h]
0x180025ce9  mov     [r10+rdx], ecx
0x180025ced  mov     ecx, [r9+4]
0x180025cf1  mov     [r8], ecx
0x180025cf4  mov     ecx, [r9+8]
0x180025cf8  mov     [r8+4], ecx
0x180025cfc  mov     ecx, [r9+0Ch]
0x180025d00  mov     [r8+8], ecx
0x180025d04  mov     ecx, [r9+10h]
0x180025d08  mov     [r8+0Ch], ecx
0x180025d0c  mov     ecx, [r9+20h]
0x180025d10  mov     [r8+10h], ecx
0x180025d14  mov     ecx, [r9+30h]
0x180025d18  mov     [r8+14h], ecx
0x180025d1c  cmp     eax, ebx
0x180025d1e  jl      short loc_180025CBE
0x180025d20  cmp     esi, 1
0x180025d23  jz      short loc_180025D3A
0x180025d25  cmp     esi, 2
0x180025d28  jz      short loc_180025DA7
0x180025d2a  pop     rdi
0x180025d2b  pop     rsi
0x180025d2c  pop     rbx
0x180025d2d  retn
0x180025d2e  mov     ebx, 1
0x180025d33  xor     eax, eax
0x180025d35  jmp     loc_180025CB6
0x180025d3a  mov     rdx, [rdi+8A48h]
0x180025d41  mov     eax, [r11+40h]
0x180025d45  add     rdx, r10
0x180025d48  mov     [rdx+8], eax
0x180025d4b  movzx   eax, byte ptr [r11+484h]
0x180025d53  mov     [rdx], eax
0x180025d55  mov     rcx, [rdx+28h]
0x180025d59  mov     eax, [r11+44h]
0x180025d5d  mov     [rcx], eax
0x180025d5f  mov     rcx, [rdx+28h]
0x180025d63  mov     eax, [r11+48h]
0x180025d67  mov     [rcx+4], eax
0x180025d6a  mov     rdx, [rdi+8A50h]
0x180025d71  mov     eax, [r11+80h]
0x180025d78  add     rdx, r10
0x180025d7b  mov     [rdx+8], eax
0x180025d7e  movzx   eax, byte ptr [r11+484h]
0x180025d86  mov     [rdx], eax
0x180025d88  mov     rcx, [rdx+28h]
0x180025d8c  mov     eax, [r11+84h]
0x180025d93  mov     [rcx], eax
0x180025d95  mov     rcx, [rdx+28h]
0x180025d99  mov     eax, [r11+88h]
0x180025da0  mov     [rcx+4], eax
0x180025da3  pop     rdi
0x180025da4  pop     rsi
0x180025da5  pop     rbx
0x180025da6  retn
0x180025da7  mov     rdx, [rdi+8A48h]
0x180025dae  movzx   eax, byte ptr [r11+484h]
0x180025db6  add     rdx, r10
0x180025db9  mov     [rdx], eax
0x180025dbb  mov     eax, [r11+40h]
0x180025dbf  mov     [rdx+8], eax
0x180025dc2  mov     rcx, [rdx+28h]
0x180025dc6  mov     eax, [r11+44h]
0x180025dca  mov     [rcx], eax
0x180025dcc  mov     rcx, [rdx+28h]
0x180025dd0  mov     eax, [r11+48h]
0x180025dd4  mov     [rcx+4], eax
0x180025dd7  mov     rcx, [rdx+28h]
0x180025ddb  mov     eax, [r11+54h]
0x180025ddf  mov     [rcx+8], eax
0x180025de2  mov     rcx, [rdx+28h]
0x180025de6  mov     eax, [r11+58h]
0x180025dea  mov     [rcx+0Ch], eax
0x180025ded  mov     rcx, [rdx+28h]
0x180025df1  mov     eax, [r11+50h]
0x180025df5  mov     [rcx+10h], eax
0x180025df8  mov     rdx, [rdi+8A50h]
0x180025dff  movzx   eax, byte ptr [r11+484h]
0x180025e07  add     rdx, r10
0x180025e0a  mov     [rdx], eax
0x180025e0c  mov     eax, [r11+80h]
0x180025e13  mov     [rdx+8], eax
0x180025e16  mov     rcx, [rdx+28h]
0x180025e1a  mov     eax, [r11+84h]
0x180025e21  mov     [rcx], eax
0x180025e23  mov     rcx, [rdx+28h]
0x180025e27  mov     eax, [r11+88h]
0x180025e2e  mov     [rcx+4], eax
0x180025e31  mov     rcx, [rdx+28h]
0x180025e35  mov     eax, [r11+94h]
0x180025e3c  mov     [rcx+8], eax
0x180025e3f  mov     rcx, [rdx+28h]
0x180025e43  mov     eax, [r11+98h]
0x180025e4a  mov     [rcx+0Ch], eax
0x180025e4d  mov     rcx, [rdx+28h]
0x180025e51  mov     eax, [r11+90h]
0x180025e58  mov     [rcx+10h], eax
0x180025e5b  jmp     loc_180025D2A
```
