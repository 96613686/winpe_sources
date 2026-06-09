# CPackage::SchdpGetStringKey(ushort const *,ulong *)

- ea: `0x180004fd4`
- end: `0x1800050b8`
- name: `?SchdpGetStringKey@CPackage@@AEAAJPEBGPEAK@Z`
- size: `228`
- prototype: `__int64 __fastcall(CPackage *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048bc`
- `0x180004b8c`

## callees

- `0x180004fd4`
- `0x18000b13c`

## pseudocode

```c
__int64 __fastcall CPackage::SchdpGetStringKey(CPackage *this, const unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v3; // edi
  unsigned int v5; // ebx
  unsigned __int64 v6; // rax
  unsigned __int64 v8; // rax
  unsigned __int16 v9; // dx
  unsigned __int16 v10; // r8
  __int64 result; // rax

  v3 = 0;
  v5 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 >= 2 )
  {
    v8 = v6 - 1;
    v9 = v8 - 1;
    v10 = v8 - 25;
    if ( v8 <= 0x19 )
      v10 = 0;
    while ( v9 >= v10 )
    {
      v5 = a2[v9 + 1] + 37 * v5;
      if ( !v9 )
        break;
      --v9;
    }
    v5 = (69069 * v5 + 1) & 0xFFFF0000 | ((1103515245 * v5 + 12345) >> 16);
  }
  else
  {
    v3 = -2147024809;
    SdpDebugTrace(1u, L"CPackage::SchdpGetStringKey", 0x17Bu, -2147024809);
  }
  result = v3;
  *a3 = v5 % 0x7FFFFFFF;
  return result;
}

```

## disassembly

```asm
0x180004fd4  mov     [rsp+arg_0], rbx
0x180004fd9  mov     [rsp+arg_8], rsi
0x180004fde  push    rdi
0x180004fdf  sub     rsp, 20h
0x180004fe3  xor     edi, edi
0x180004fe5  mov     rsi, r8
0x180004fe8  mov     ebx, edi
0x180004fea  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004fee  mov     r9, rdx
0x180004ff1  inc     rax
0x180004ff4  cmp     [rdx+rax*2], di
0x180004ff8  jnz     short loc_180004FF1
0x180004ffa  cmp     rax, 2
0x180004ffe  jnb     short loc_180005021
0x180005000  mov     edi, 80070057h
0x180005005  lea     rdx, aCpackageSchdpg; "CPackage::SchdpGetStringKey"
0x18000500c  mov     r9d, edi; int
0x18000500f  mov     r8d, 17Bh; int
0x180005015  mov     ecx, 1; Level
0x18000501a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000501f  jmp     short loc_180005089
0x180005021  mov     r10d, 1
0x180005027  sub     rax, r10
0x18000502a  movzx   edx, ax
0x18000502d  movzx   r8d, ax
0x180005031  sub     dx, r10w
0x180005035  lea     ecx, [r10+18h]
0x180005039  sub     r8w, cx
0x18000503d  cmp     rax, rcx
0x180005040  cmovbe  r8w, di
0x180005045  jmp     short loc_180005062
0x180005047  imul    ebx, 25h ; '%'
0x18000504a  movzx   eax, dx
0x18000504d  movzx   ecx, word ptr [r9+rax*2+2]
0x180005053  add     ebx, ecx
0x180005055  test    dx, dx
0x180005058  jz      short loc_180005068
0x18000505a  mov     eax, 0FFFFh
0x18000505f  add     dx, ax
0x180005062  cmp     dx, r8w
0x180005066  jnb     short loc_180005047
0x180005068  imul    ecx, ebx, 41C64E6Dh
0x18000506e  imul    eax, ebx, 10DCDh
0x180005074  add     ecx, 3039h
0x18000507a  shr     ecx, 10h
0x18000507d  add     eax, r10d
0x180005080  mov     ebx, ecx
0x180005082  and     eax, 0FFFF0000h
0x180005087  or      ebx, eax
0x180005089  mov     ecx, ebx
0x18000508b  mov     eax, 3
0x180005090  mul     ebx
0x180005092  mov     eax, edi
0x180005094  sub     ecx, edx
0x180005096  shr     ecx, 1
0x180005098  add     ecx, edx
0x18000509a  shr     ecx, 1Eh
0x18000509d  imul    ecx, 7FFFFFFFh
0x1800050a3  sub     ebx, ecx
0x1800050a5  mov     [rsi], ebx
0x1800050a7  mov     rbx, [rsp+28h+arg_0]
0x1800050ac  mov     rsi, [rsp+28h+arg_8]
0x1800050b1  add     rsp, 20h
0x1800050b5  pop     rdi
0x1800050b6  retn
```
