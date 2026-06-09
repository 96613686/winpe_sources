# WanpUpdateConnEntryWithLinkUpInfo

- ea: `0x140011230`
- end: `0x1400112e9`
- name: `WanpUpdateConnEntryWithLinkUpInfo`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140010448`

## callees

- `0x140011230`

## pseudocode

```c
char __fastcall WanpUpdateConnEntryWithLinkUpInfo(__int64 a1, __int64 a2)
{
  __int64 v3; // r10
  __int64 v4; // rcx
  bool v5; // zf
  char result; // al

  v3 = *(_QWORD *)(a2 + 32);
  *(_QWORD *)(a1 + 152) = (unsigned int)(100 * *(_DWORD *)a2);
  *(_QWORD *)(a1 + 160) = (unsigned int)(100 * *(_DWORD *)a2);
  *(_DWORD *)(a1 + 280) = *(_DWORD *)(a2 + 4);
  *(_QWORD *)(a1 + 288) = (unsigned int)(100 * *(_DWORD *)a2);
  v4 = (unsigned int)(100 * *(_DWORD *)a2);
  *(_DWORD *)(a1 + 272) = 1;
  *(_DWORD *)(a1 + 124) = 2;
  *(_QWORD *)(a1 + 296) = v4;
  *(_DWORD *)(a1 + 64) = *(_DWORD *)(v3 + 16);
  v5 = *(_BYTE *)(a1 + 4) == 0;
  *(_BYTE *)(a1 + 122) = *(_DWORD *)(v3 + 4) == 1;
  if ( v5 )
  {
    *(_QWORD *)(a1 + 48) = *(_QWORD *)(v3 + 588);
  }
  else
  {
    *(_DWORD *)(a1 + 28) = *(_DWORD *)(v3 + 588);
    *(_DWORD *)(a1 + 24) = *(_DWORD *)(v3 + 584);
    *(_DWORD *)(a1 + 32) = *(_DWORD *)(v3 + 592);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 96));
  result = -*(_BYTE *)(a1 + 4);
  *(_WORD *)(a1 + 120) = __ROR2__(*(_BYTE *)(a1 + 4) != 0 ? 2048 : -31011, 8);
  return result;
}

```

## disassembly

```asm
0x140011230  imul    r8d, [rdx], 64h ; 'd'
0x140011234  mov     r9, rcx
0x140011237  mov     r10, [rdx+20h]
0x14001123b  mov     [rcx+98h], r8
0x140011242  imul    r8d, [rdx], 64h ; 'd'
0x140011246  mov     [rcx+0A0h], r8
0x14001124d  mov     eax, [rdx+4]
0x140011250  mov     [rcx+118h], eax
0x140011256  imul    r8d, [rdx], 64h ; 'd'
0x14001125a  mov     [rcx+120h], r8
0x140011261  imul    ecx, [rdx], 64h ; 'd'
0x140011264  mov     dword ptr [r9+110h], 1
0x14001126f  mov     dword ptr [r9+7Ch], 2
0x140011277  mov     [r9+128h], rcx
0x14001127e  mov     eax, [r10+10h]
0x140011282  mov     [r9+40h], eax
0x140011286  cmp     dword ptr [r10+4], 1
0x14001128b  setz    al
0x14001128e  cmp     byte ptr [r9+4], 0
0x140011293  mov     [r9+7Ah], al
0x140011297  jz      short loc_1400112BC
0x140011299  mov     eax, [r10+24Ch]
0x1400112a0  mov     [r9+1Ch], eax
0x1400112a4  mov     eax, [r10+248h]
0x1400112ab  mov     [r9+18h], eax
0x1400112af  mov     eax, [r10+250h]
0x1400112b6  mov     [r9+20h], eax
0x1400112ba  jmp     short loc_1400112C7
0x1400112bc  mov     rax, [r10+24Ch]
0x1400112c3  mov     [r9+30h], rax
0x1400112c7  lock inc dword ptr [r9+60h]
0x1400112cc  mov     al, [r9+4]
0x1400112d0  neg     al
0x1400112d2  sbb     cx, cx
0x1400112d5  and     cx, 8123h
0x1400112da  add     cx, 86DDh
0x1400112df  ror     cx, 8
0x1400112e3  mov     [r9+78h], cx
0x1400112e8  retn
```
