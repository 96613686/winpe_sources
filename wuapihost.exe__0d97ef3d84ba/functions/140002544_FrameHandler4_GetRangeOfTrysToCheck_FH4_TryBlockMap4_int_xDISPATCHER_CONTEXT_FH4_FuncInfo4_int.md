# __FrameHandler4::GetRangeOfTrysToCheck(FH4::TryBlockMap4 &,int,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int)

- ea: `0x140002544`
- end: `0x1400026c4`
- name: `?GetRangeOfTrysToCheck@__FrameHandler4@@SA?AU?$pair@Viterator@TryBlockMap4@FH4@@V123@@std@@AEAVTryBlockMap4@FH4@@HPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@5@H@Z`
- size: `384`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140003624`
- `0x140003b64`

## callees

- `0x140002544`
- `0x1400027f4`

## pseudocode

```c
_OWORD *__fastcall __FrameHandler4::GetRangeOfTrysToCheck(_OWORD *a1, int *a2, int a3)
{
  __int128 v5; // xmm6
  int v7; // esi
  int v8; // r15d
  int v9; // r10d
  _BYTE *v10; // r11
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  _BYTE *v17; // rdx
  int v18; // eax
  __int64 v19; // rcx
  _DWORD *v20; // r11
  int v21; // eax
  int v22; // eax
  _OWORD *result; // rax
  __int128 v24; // [rsp+20h] [rbp-58h]
  __int128 v25; // [rsp+30h] [rbp-48h]
  __int128 v26; // [rsp+40h] [rbp-38h] BYREF

  *(_QWORD *)&v24 = a2;
  *(_QWORD *)&v25 = a2;
  DWORD2(v24) = 0;
  v5 = v24;
  v26 = v24;
  v7 = 0;
  FH4::TryBlockMap4::setBuffer(a2, &v26);
  v8 = *a2;
  v9 = 0;
  if ( *a2 )
  {
    v10 = (_BYTE *)*((_QWORD *)a2 + 1);
    do
    {
      v11 = *((_QWORD *)a2 + 3);
      if ( a3 >= (int)v11 && a3 <= SHIDWORD(v11) )
      {
        v7 = v9;
        DWORD2(v24) = 0;
        v5 = v24;
      }
      v12 = *v10 & 0xF;
      ++v9;
      v13 = *((char *)&FH4::s_negLengthTab + v12);
      LOBYTE(v12) = *((_BYTE *)&FH4::s_shiftTab + v12);
      v14 = *(_DWORD *)&v10[-v13 - 4];
      *((_QWORD *)a2 + 1) = &v10[-v13];
      a2[6] = v14 >> v12;
      v15 = v10[-v13] & 0xF;
      v16 = *((char *)&FH4::s_negLengthTab + v15);
      v17 = &v10[-v16 - v13];
      v18 = *((_DWORD *)v17 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v15);
      *((_QWORD *)a2 + 1) = v17;
      a2[7] = v18;
      v19 = *v17 & 0xF;
      v20 = &v10[-*((char *)&FH4::s_negLengthTab + v19) - v16 - v13];
      v21 = *(v20 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v19);
      *((_QWORD *)a2 + 1) = v20;
      a2[8] = v21;
      v22 = *v20;
      v10 = v20 + 1;
      *((_QWORD *)a2 + 1) = v10;
      a2[9] = v22;
    }
    while ( v9 != v8 );
  }
  v26 = v5;
  DWORD2(v25) = v7 + 1;
  FH4::TryBlockMap4::setBuffer(a2, &v26);
  result = a1;
  *a1 = v5;
  a1[1] = v25;
  return result;
}

```

## disassembly

```asm
0x140002544  mov     rax, rsp
0x140002547  mov     [rax+8], rbx
0x14000254b  mov     [rax+10h], rbp
0x14000254f  mov     [rax+18h], rsi
0x140002553  mov     [rax+20h], rdi
0x140002557  push    r12
0x140002559  push    r14
0x14000255b  push    r15
0x14000255d  sub     rsp, 60h
0x140002561  mov     qword ptr [rsp+78h+var_58], rdx
0x140002566  mov     rbx, rdx
0x140002569  movaps  xmmword ptr [rax-28h], xmm6
0x14000256d  mov     rbp, rcx
0x140002570  mov     qword ptr [rsp+78h+var_48], rdx
0x140002575  xor     edi, edi
0x140002577  mov     dword ptr [rsp+78h+var_58+8], edi
0x14000257b  lea     rdx, [rax-38h]
0x14000257f  movaps  xmm6, [rsp+78h+var_58]
0x140002584  mov     rcx, rbx
0x140002587  movdqa  xmmword ptr [rax-38h], xmm6
0x14000258c  mov     r14d, r8d
0x14000258f  xor     esi, esi
0x140002591  call    ?setBuffer@TryBlockMap4@FH4@@QEAAXViterator@12@@Z; FH4::TryBlockMap4::setBuffer(FH4::TryBlockMap4::iterator)
0x140002596  mov     r15d, [rbx]
0x140002599  xor     r10d, r10d
0x14000259c  test    r15d, r15d
0x14000259f  jz      loc_140002675
0x1400025a5  mov     r11, [rbx+8]
0x1400025a9  lea     r12, cs:140000000h
0x1400025b0  mov     rax, [rbx+18h]
0x1400025b4  cmp     r14d, eax
0x1400025b7  jl      short loc_1400025D8
0x1400025b9  shr     rax, 20h
0x1400025bd  cmp     r14d, eax
0x1400025c0  jg      short loc_1400025D8
0x1400025c2  test    edi, edi
0x1400025c4  mov     eax, r10d
0x1400025c7  mov     esi, r10d
0x1400025ca  cmovz   eax, edi
0x1400025cd  mov     dword ptr [rsp+78h+var_58+8], eax
0x1400025d1  mov     edi, eax
0x1400025d3  movaps  xmm6, [rsp+78h+var_58]
0x1400025d8  movzx   ecx, byte ptr [r11]
0x1400025dc  mov     rdx, r11
0x1400025df  and     ecx, 0Fh
0x1400025e2  inc     r10d
0x1400025e5  movsx   r9, byte ptr [rcx+r12+7460h]
0x1400025ee  mov     cl, [rcx+r12+7470h]
0x1400025f6  sub     rdx, r9
0x1400025f9  mov     eax, [rdx-4]
0x1400025fc  mov     [rbx+8], rdx
0x140002600  shr     eax, cl
0x140002602  mov     [rbx+18h], eax
0x140002605  movzx   ecx, byte ptr [rdx]
0x140002608  mov     rdx, r11
0x14000260b  and     ecx, 0Fh
0x14000260e  movsx   r8, byte ptr [rcx+r12+7460h]
0x140002617  mov     cl, [rcx+r12+7470h]
0x14000261f  sub     rdx, r8
0x140002622  sub     rdx, r9
0x140002625  mov     eax, [rdx-4]
0x140002628  shr     eax, cl
0x14000262a  mov     [rbx+8], rdx
0x14000262e  mov     [rbx+1Ch], eax
0x140002631  movzx   ecx, byte ptr [rdx]
0x140002634  and     ecx, 0Fh
0x140002637  movsx   rax, byte ptr [rcx+r12+7460h]
0x140002640  mov     cl, [rcx+r12+7470h]
0x140002648  sub     r11, rax
0x14000264b  sub     r11, r8
0x14000264e  sub     r11, r9
0x140002651  mov     eax, [r11-4]
0x140002655  shr     eax, cl
0x140002657  mov     [rbx+8], r11
0x14000265b  mov     [rbx+20h], eax
0x14000265e  mov     eax, [r11]
0x140002661  add     r11, 4
0x140002665  mov     [rbx+8], r11
0x140002669  mov     [rbx+24h], eax
0x14000266c  cmp     r10d, r15d
0x14000266f  jnz     loc_1400025B0
0x140002675  inc     esi
0x140002677  movdqa  [rsp+78h+var_38], xmm6
0x14000267d  lea     rdx, [rsp+78h+var_38]
0x140002682  mov     dword ptr [rsp+78h+var_48+8], esi
0x140002686  mov     rcx, rbx
0x140002689  call    ?setBuffer@TryBlockMap4@FH4@@QEAAXViterator@12@@Z; FH4::TryBlockMap4::setBuffer(FH4::TryBlockMap4::iterator)
0x14000268e  movups  xmm0, [rsp+78h+var_48]
0x140002693  lea     r11, [rsp+78h+var_18]
0x140002698  mov     rax, rbp
0x14000269b  mov     rbx, [r11+20h]
0x14000269f  mov     rsi, [r11+30h]
0x1400026a3  mov     rdi, [r11+38h]
0x1400026a7  movdqu  xmmword ptr [rbp+0], xmm6
0x1400026ac  movaps  xmm6, [rsp+78h+var_28]
0x1400026b1  movdqu  xmmword ptr [rbp+10h], xmm0
0x1400026b6  mov     rbp, [r11+28h]
0x1400026ba  mov     rsp, r11
0x1400026bd  pop     r15
0x1400026bf  pop     r14
0x1400026c1  pop     r12
0x1400026c3  retn
```
