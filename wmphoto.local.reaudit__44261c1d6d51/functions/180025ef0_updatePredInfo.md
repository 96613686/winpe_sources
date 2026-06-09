# updatePredInfo

- ea: `0x180025ef0`
- end: `0x1800260c2`
- name: `updatePredInfo`
- size: `466`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180007400`
- `0x180008df0`
- `0x18000f3b4`

## callees

- `0x180025ef0`

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
0x180025ef0  push    rbx
0x180025ef2  push    rsi
0x180025ef3  push    rdi
0x180025ef4  lea     eax, [r9-1]
0x180025ef8  mov     esi, r9d
0x180025efb  mov     r11, rdx
0x180025efe  mov     rdi, rcx
0x180025f01  cmp     eax, 1
0x180025f04  jbe     loc_180025F8F
0x180025f0a  mov     ebx, [rcx+85C0h]
0x180025f10  xor     eax, eax
0x180025f12  test    ebx, ebx
0x180025f14  jle     short loc_180025F8A
0x180025f16  lea     r10, [r8+r8*2]
0x180025f1a  shl     r10, 4
0x180025f1e  movsxd  rcx, eax
0x180025f21  inc     eax
0x180025f23  mov     rdx, [rdi+rcx*8+8A40h]
0x180025f2b  shl     rcx, 6
0x180025f2f  mov     r8, [r10+rdx+28h]
0x180025f34  lea     r9, [rcx+r11]
0x180025f38  mov     ecx, [rcx+r11]
0x180025f3c  mov     [r10+rdx+8], ecx
0x180025f41  movzx   ecx, byte ptr [r11+484h]
0x180025f49  mov     [r10+rdx], ecx
0x180025f4d  mov     ecx, [r9+4]
0x180025f51  mov     [r8], ecx
0x180025f54  mov     ecx, [r9+8]
0x180025f58  mov     [r8+4], ecx
0x180025f5c  mov     ecx, [r9+0Ch]
0x180025f60  mov     [r8+8], ecx
0x180025f64  mov     ecx, [r9+10h]
0x180025f68  mov     [r8+0Ch], ecx
0x180025f6c  mov     ecx, [r9+20h]
0x180025f70  mov     [r8+10h], ecx
0x180025f74  mov     ecx, [r9+30h]
0x180025f78  mov     [r8+14h], ecx
0x180025f7c  cmp     eax, ebx
0x180025f7e  jl      short loc_180025F1E
0x180025f80  cmp     esi, 1
0x180025f83  jz      short loc_180025F9B
0x180025f85  cmp     esi, 2
0x180025f88  jz      short loc_180026009
0x180025f8a  pop     rdi
0x180025f8b  pop     rsi
0x180025f8c  pop     rbx
0x180025f8d  retn
0x180025f8f  mov     ebx, 1
0x180025f94  xor     eax, eax
0x180025f96  jmp     loc_180025F16
0x180025f9b  mov     rdx, [rdi+8A48h]
0x180025fa2  mov     eax, [r11+40h]
0x180025fa6  add     rdx, r10
0x180025fa9  mov     [rdx+8], eax
0x180025fac  movzx   eax, byte ptr [r11+484h]
0x180025fb4  mov     [rdx], eax
0x180025fb6  mov     rcx, [rdx+28h]
0x180025fba  mov     eax, [r11+44h]
0x180025fbe  mov     [rcx], eax
0x180025fc0  mov     rcx, [rdx+28h]
0x180025fc4  mov     eax, [r11+48h]
0x180025fc8  mov     [rcx+4], eax
0x180025fcb  mov     rdx, [rdi+8A50h]
0x180025fd2  mov     eax, [r11+80h]
0x180025fd9  add     rdx, r10
0x180025fdc  mov     [rdx+8], eax
0x180025fdf  movzx   eax, byte ptr [r11+484h]
0x180025fe7  mov     [rdx], eax
0x180025fe9  mov     rcx, [rdx+28h]
0x180025fed  mov     eax, [r11+84h]
0x180025ff4  mov     [rcx], eax
0x180025ff6  mov     rcx, [rdx+28h]
0x180025ffa  mov     eax, [r11+88h]
0x180026001  mov     [rcx+4], eax
0x180026004  pop     rdi
0x180026005  pop     rsi
0x180026006  pop     rbx
0x180026007  retn
0x180026009  mov     rdx, [rdi+8A48h]
0x180026010  movzx   eax, byte ptr [r11+484h]
0x180026018  add     rdx, r10
0x18002601b  mov     [rdx], eax
0x18002601d  mov     eax, [r11+40h]
0x180026021  mov     [rdx+8], eax
0x180026024  mov     rcx, [rdx+28h]
0x180026028  mov     eax, [r11+44h]
0x18002602c  mov     [rcx], eax
0x18002602e  mov     rcx, [rdx+28h]
0x180026032  mov     eax, [r11+48h]
0x180026036  mov     [rcx+4], eax
0x180026039  mov     rcx, [rdx+28h]
0x18002603d  mov     eax, [r11+54h]
0x180026041  mov     [rcx+8], eax
0x180026044  mov     rcx, [rdx+28h]
0x180026048  mov     eax, [r11+58h]
0x18002604c  mov     [rcx+0Ch], eax
0x18002604f  mov     rcx, [rdx+28h]
0x180026053  mov     eax, [r11+50h]
0x180026057  mov     [rcx+10h], eax
0x18002605a  mov     rdx, [rdi+8A50h]
0x180026061  movzx   eax, byte ptr [r11+484h]
0x180026069  add     rdx, r10
0x18002606c  mov     [rdx], eax
0x18002606e  mov     eax, [r11+80h]
0x180026075  mov     [rdx+8], eax
0x180026078  mov     rcx, [rdx+28h]
0x18002607c  mov     eax, [r11+84h]
0x180026083  mov     [rcx], eax
0x180026085  mov     rcx, [rdx+28h]
0x180026089  mov     eax, [r11+88h]
0x180026090  mov     [rcx+4], eax
0x180026093  mov     rcx, [rdx+28h]
0x180026097  mov     eax, [r11+94h]
0x18002609e  mov     [rcx+8], eax
0x1800260a1  mov     rcx, [rdx+28h]
0x1800260a5  mov     eax, [r11+98h]
0x1800260ac  mov     [rcx+0Ch], eax
0x1800260af  mov     rcx, [rdx+28h]
0x1800260b3  mov     eax, [r11+90h]
0x1800260ba  mov     [rcx+10h], eax
0x1800260bd  jmp     loc_180025F8A
```
