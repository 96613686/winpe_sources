# UdfCreateFileTimesEa

- ea: `0x14001636c`
- end: `0x14001646f`
- name: `UdfCreateFileTimesEa`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x140030818`

## callees

- `0x140009450`
- `0x14001636c`

## pseudocode

```c
__int64 __fastcall UdfCreateFileTimesEa(__int64 a1, __int16 *a2)
{
  __int16 v2; // r9
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // edx
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 result; // rax

  v2 = *a2;
  v5 = 86;
  if ( *a2 != 261 )
    v5 = 106;
  v6 = 216;
  v7 = *(unsigned int *)&a2[v5];
  v8 = 84;
  if ( v2 != 261 )
    v8 = 104;
  v9 = (__int64)a2 + *(unsigned int *)&a2[v8];
  if ( v2 != 266 )
    v6 = 176;
  v10 = *((_DWORD *)a2 + 3);
  v11 = v7 + v9 + v6;
  *(_WORD *)v11 = 262;
  *(_WORD *)(v11 + 2) = 3 - (*(_WORD *)(*(_QWORD *)(a1 + 16) + 2136LL) != 10);
  *(_WORD *)(v11 + 6) = *(_WORD *)(*(_QWORD *)(a1 + 16) + 2140LL);
  *(_DWORD *)(v11 + 12) = v10;
  *(_DWORD *)(v11 + 20) = -1;
  *(_DWORD *)(v11 + 16) = -1;
  UdfUpdateChecksumAndCrc(v11, 24);
  *(_DWORD *)(v11 + 24) = 5;
  v12 = 42;
  *(_DWORD *)(v11 + 28) = 1;
  *(_DWORD *)(v11 + 32) = 32;
  *(_DWORD *)(v11 + 36) = 12;
  *(_DWORD *)(v11 + 40) = 1;
  if ( *a2 != 261 )
    v12 = 46;
  *(_QWORD *)(v11 + 44) = *(_QWORD *)&a2[v12];
  result = *(unsigned int *)&a2[v12 + 4];
  *(_DWORD *)(v11 + 52) = result;
  if ( *a2 == 266 )
    *((_DWORD *)a2 + 52) = 56;
  else
    *((_DWORD *)a2 + 42) = 56;
  return result;
}

```

## disassembly

```asm
0x14001636c  push    rbx
0x14001636e  push    rbp
0x14001636f  push    rsi
0x140016370  push    rdi
0x140016371  sub     rsp, 28h
0x140016375  movzx   r9d, word ptr [rdx]
0x140016379  mov     r10, rcx
0x14001637c  mov     ebp, 105h
0x140016381  mov     rdi, rdx
0x140016384  cmp     r9w, bp
0x140016388  lea     ecx, [rbp-31h]
0x14001638b  lea     eax, [rbp-59h]
0x14001638e  cmovnz  eax, ecx
0x140016391  lea     esi, [rbp+5]
0x140016394  lea     ecx, [rbp-35h]
0x140016397  lea     ebx, [rbp-2Dh]
0x14001639a  mov     r8d, [rax+rdx]
0x14001639e  lea     eax, [rbp-5Dh]
0x1400163a1  cmovnz  eax, ecx
0x1400163a4  mov     ecx, [rax+rdx]
0x1400163a7  add     rcx, rdx
0x1400163aa  lea     edx, [rbp-55h]
0x1400163ad  cmp     r9w, si
0x1400163b1  cmovnz  ebx, edx
0x1400163b4  mov     edx, [rdi+0Ch]
0x1400163b7  add     rcx, r8
0x1400163ba  add     rbx, rcx
0x1400163bd  mov     ecx, 0Ah
0x1400163c2  mov     word ptr [rbx], 106h
0x1400163c7  mov     rax, [r10+10h]
0x1400163cb  sub     cx, [rax+858h]
0x1400163d2  neg     cx
0x1400163d5  sbb     ax, ax
0x1400163d8  add     ax, 3
0x1400163dc  mov     [rbx+2], ax
0x1400163e0  mov     rax, [r10+10h]
0x1400163e4  movzx   ecx, word ptr [rax+85Ch]
0x1400163eb  or      eax, 0FFFFFFFFh
0x1400163ee  mov     [rbx+6], cx
0x1400163f2  mov     rcx, rbx
0x1400163f5  mov     [rbx+0Ch], edx
0x1400163f8  mov     edx, 18h
0x1400163fd  mov     [rbx+14h], eax
0x140016400  mov     [rbx+10h], eax
0x140016403  call    UdfUpdateChecksumAndCrc
0x140016408  mov     dword ptr [rbx+18h], 5
0x14001640f  mov     eax, 54h ; 'T'
0x140016414  mov     dword ptr [rbx+1Ch], 1
0x14001641b  mov     dword ptr [rbx+20h], 20h ; ' '
0x140016422  mov     dword ptr [rbx+24h], 0Ch
0x140016429  mov     dword ptr [rbx+28h], 1
0x140016430  lea     ecx, [rax+8]
0x140016433  cmp     [rdi], bp
0x140016436  cmovnz  eax, ecx
0x140016439  movsd   xmm0, qword ptr [rax+rdi]
0x14001643e  movsd   qword ptr [rbx+2Ch], xmm0
0x140016443  mov     eax, [rax+rdi+8]
0x140016447  mov     [rbx+34h], eax
0x14001644a  cmp     [rdi], si
0x14001644d  jnz     short loc_14001645B
0x14001644f  mov     dword ptr [rdi+0D0h], 38h ; '8'
0x140016459  jmp     short loc_140016465
0x14001645b  mov     dword ptr [rdi+0A8h], 38h ; '8'
0x140016465  add     rsp, 28h
0x140016469  pop     rdi
0x14001646a  pop     rsi
0x14001646b  pop     rbp
0x14001646c  pop     rbx
0x14001646d  retn
```
