# TextLogUpdateSectionTag

- ea: `0x18000b900`
- end: `0x18000b96d`
- name: `TextLogUpdateSectionTag`
- size: `109`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000b5f0`
- `0x18000b7a0`

## callees

- `0x18000b900`

## pseudocode

```c
__int64 __fastcall TextLogUpdateSectionTag(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // r9d
  unsigned __int64 v4; // r10
  unsigned __int64 v5; // rcx

  if ( a3 > 0x2710 )
    return 0;
  v3 = 0;
  v4 = 20LL * (a3 + 1);
  if ( v4 > (unsigned int)(*(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16)) )
    return 0;
  v5 = *(_QWORD *)(a1 + 24) - v4;
  if ( *(_DWORD *)v5 == -522186479 && *(_DWORD *)(v5 + 4) == *(_DWORD *)(a2 + 4) )
  {
    *(_OWORD *)v5 = *(_OWORD *)a2;
    *(_DWORD *)(v5 + 16) = *(_DWORD *)(a2 + 16);
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x18000b900  sub     rsp, 18h
0x18000b904  cmp     r8d, 2710h
0x18000b90b  ja      short loc_18000B966
0x18000b90d  xor     r9d, r9d
0x18000b910  mov     [rsp+18h+var_18], r9d
0x18000b914  lea     eax, [r8+1]
0x18000b918  lea     r10, [rax+rax*4]
0x18000b91c  shl     r10, 2
0x18000b920  mov     eax, [rcx+18h]
0x18000b923  sub     eax, [rcx+10h]
0x18000b926  cmp     r10, rax
0x18000b929  ja      short loc_18000B966
0x18000b92b  mov     rcx, [rcx+18h]
0x18000b92f  sub     rcx, r10
0x18000b932  cmp     dword ptr [rcx], 0E0E01111h
0x18000b938  jnz     short loc_18000B958
0x18000b93a  mov     eax, [rdx+4]
0x18000b93d  cmp     [rcx+4], eax
0x18000b940  jnz     short loc_18000B958
0x18000b942  movups  xmm0, xmmword ptr [rdx]
0x18000b945  movups  xmmword ptr [rcx], xmm0
0x18000b948  mov     eax, [rdx+10h]
0x18000b94b  mov     [rcx+10h], eax
0x18000b94e  mov     r9d, 1
0x18000b954  mov     [rsp+18h+var_18], r9d
0x18000b958  jmp     short loc_18000B95E
0x18000b95a  mov     r9d, [rsp+18h+var_18]
0x18000b95e  mov     eax, r9d
0x18000b961  add     rsp, 18h
0x18000b965  retn
0x18000b966  xor     eax, eax
0x18000b968  add     rsp, 18h
0x18000b96c  retn
```
