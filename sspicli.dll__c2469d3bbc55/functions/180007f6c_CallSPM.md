# CallSPM

- ea: `0x180007f6c`
- end: `0x1800080b5`
- name: `CallSPM`
- size: `329`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180003ca4`
- `0x1800079f8`
- `0x180007e40`
- `0x180008e94`
- `0x180009460`
- `0x18000a3e8`
- `0x180020adc`
- `0x180020d74`
- `0x180021018`
- `0x1800211a0`
- `0x180021328`
- `0x18002145c`
- `0x1800215b0`
- `0x180021738`
- `0x1800219ec`

## callees

- `0x180007f6c`
- `0x180008180`
- `0x18001b048`
- `0x180020fd0`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CallSPM(__int64 a1, _OWORD *a2, __int64 a3)
{
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // edi
  PVOID *v11; // rcx
  __int64 v12; // rax
  _OWORD *v13; // rcx
  __int128 v14; // xmm1

  if ( SecpLsaDispatchFn )
  {
    if ( a2 == (_OWORD *)a3 )
    {
      return (unsigned int)SecpLsaDispatchFn(a3);
    }
    else
    {
      v12 = 3;
      v13 = (_OWORD *)a3;
      do
      {
        *v13 = *a2;
        v13[1] = a2[1];
        v13[2] = a2[2];
        v13[3] = a2[3];
        v13[4] = a2[4];
        v13[5] = a2[5];
        v13[6] = a2[6];
        v14 = a2[7];
        a2 += 8;
        v13[7] = v14;
        v13 += 8;
        --v12;
      }
      while ( v12 );
      *v13 = *a2;
      v13[1] = a2[1];
      v13[2] = a2[2];
      v13[3] = a2[3];
      v13[4] = a2[4];
      v13[5] = a2[5];
      v13[6] = a2[6];
      *((_QWORD *)v13 + 14) = *((_QWORD *)a2 + 14);
      return (unsigned int)SecpLsaDispatchFn(a3);
    }
  }
  else
  {
    v5 = CallRpcSPM(*(_QWORD *)(a1 + 24), (__int64)a2, 0x1F8u, (void *)a3);
    v8 = v5;
    if ( v5 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xBu, &WPP_50d0cea9f22235195ca4bdcfdf3b495e_Traceguids, v5);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
          WPP_SF_i(v11[2], v6, v7, *(_QWORD *)(a1 + 16));
      }
      *(_WORD *)(a3 + 48) |= 1u;
      *(_DWORD *)(a3 + 44) = v8;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180007f6c  push    rbx
0x180007f6e  push    rbp
0x180007f6f  push    rsi
0x180007f70  push    rdi
0x180007f71  sub     rsp, 28h
0x180007f75  mov     rax, cs:SecpLsaDispatchFn
0x180007f7c  mov     rbx, r8
0x180007f7f  mov     rsi, rcx
0x180007f82  test    rax, rax
0x180007f85  jnz     short loc_180007FAA
0x180007f87  mov     rcx, [rcx+18h]
0x180007f8b  mov     r9, rbx
0x180007f8e  mov     r8d, 1F8h
0x180007f94  call    CallRpcSPM
0x180007f99  mov     edi, eax
0x180007f9b  test    eax, eax
0x180007f9d  js      short loc_180007FBB
0x180007f9f  mov     eax, edi
0x180007fa1  add     rsp, 28h
0x180007fa5  pop     rdi
0x180007fa6  pop     rsi
0x180007fa7  pop     rbp
0x180007fa8  pop     rbx
0x180007fa9  retn
0x180007faa  cmp     rdx, rbx
0x180007fad  jnz     short loc_180008015
0x180007faf  mov     rcx, rbx
0x180007fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fb7  mov     edi, eax
0x180007fb9  jmp     short loc_180007F9F
0x180007fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fc2  lea     rbp, WPP_GLOBAL_Control
0x180007fc9  cmp     rcx, rbp
0x180007fcc  jz      short loc_18000800B
0x180007fce  test    byte ptr [rcx+1Ch], 1
0x180007fd2  jz      short loc_180007FF3
0x180007fd4  mov     rcx, [rcx+10h]
0x180007fd8  lea     r8, WPP_50d0cea9f22235195ca4bdcfdf3b495e_Traceguids
0x180007fdf  mov     edx, 0Bh
0x180007fe4  mov     r9d, edi
0x180007fe7  call    WPP_SF_D
0x180007fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ff3  cmp     rcx, rbp
0x180007ff6  jz      short loc_18000800B
0x180007ff8  test    byte ptr [rcx+1Ch], 1
0x180007ffc  jz      short loc_18000800B
0x180007ffe  mov     r9, [rsi+10h]
0x180008002  mov     rcx, [rcx+10h]
0x180008006  call    WPP_SF_i
0x18000800b  or      word ptr [rbx+30h], 1
0x180008010  mov     [rbx+2Ch], edi
0x180008013  jmp     short loc_180007F9F
0x180008015  mov     eax, 3
0x18000801a  mov     rcx, rbx
0x18000801d  lea     r8d, [rax+7Dh]
0x180008021  movups  xmm0, xmmword ptr [rdx]
0x180008024  movups  xmmword ptr [rcx], xmm0
0x180008027  movups  xmm1, xmmword ptr [rdx+10h]
0x18000802b  movups  xmmword ptr [rcx+10h], xmm1
0x18000802f  movups  xmm0, xmmword ptr [rdx+20h]
0x180008033  movups  xmmword ptr [rcx+20h], xmm0
0x180008037  movups  xmm1, xmmword ptr [rdx+30h]
0x18000803b  movups  xmmword ptr [rcx+30h], xmm1
0x18000803f  movups  xmm0, xmmword ptr [rdx+40h]
0x180008043  movups  xmmword ptr [rcx+40h], xmm0
0x180008047  movups  xmm1, xmmword ptr [rdx+50h]
0x18000804b  movups  xmmword ptr [rcx+50h], xmm1
0x18000804f  movups  xmm0, xmmword ptr [rdx+60h]
0x180008053  movups  xmmword ptr [rcx+60h], xmm0
0x180008057  movups  xmm1, xmmword ptr [rdx+70h]
0x18000805b  add     rdx, r8
0x18000805e  movups  xmmword ptr [rcx+70h], xmm1
0x180008062  add     rcx, r8
0x180008065  sub     rax, 1
0x180008069  jnz     short loc_180008021
0x18000806b  movups  xmm0, xmmword ptr [rdx]
0x18000806e  movups  xmmword ptr [rcx], xmm0
0x180008071  movups  xmm1, xmmword ptr [rdx+10h]
0x180008075  movups  xmmword ptr [rcx+10h], xmm1
0x180008079  movups  xmm0, xmmword ptr [rdx+20h]
0x18000807d  movups  xmmword ptr [rcx+20h], xmm0
0x180008081  movups  xmm1, xmmword ptr [rdx+30h]
0x180008085  movups  xmmword ptr [rcx+30h], xmm1
0x180008089  movups  xmm0, xmmword ptr [rdx+40h]
0x18000808d  movups  xmmword ptr [rcx+40h], xmm0
0x180008091  movups  xmm1, xmmword ptr [rdx+50h]
0x180008095  movups  xmmword ptr [rcx+50h], xmm1
0x180008099  movups  xmm0, xmmword ptr [rdx+60h]
0x18000809d  movups  xmmword ptr [rcx+60h], xmm0
0x1800080a1  mov     rax, [rdx+70h]
0x1800080a5  mov     [rcx+70h], rax
0x1800080a9  mov     rax, cs:SecpLsaDispatchFn
0x1800080b0  jmp     loc_180007FAF
```
