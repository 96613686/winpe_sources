# ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Next(ulong,IConnectionPoint * *,ulong *)

- ea: `0x1800075cc`
- end: `0x180007697`
- name: `?Next@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@UEAAJKPEAPEAUIConnectionPoint@@PEAK@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800075b0`

## callees

- `0x180003b70`
- `0x1800075cc`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Next(
        _QWORD *a1,
        unsigned int a2,
        _QWORD *a3,
        _DWORD *a4)
{
  _QWORD *v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rbx
  BOOL v9; // ebp
  __int64 *v10; // rcx
  __int64 v11; // rcx

  v4 = a3;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 || a2 != 1 && !a4 )
    return 2147500035LL;
  if ( !a1[2] )
    return 2147500037LL;
  v7 = a1[3];
  if ( !v7 || !a1[4] )
    return 2147500037LL;
  v8 = (v7 - a1[4]) >> 3;
  v9 = (unsigned int)v8 < a2;
  if ( (unsigned int)v8 > a2 )
    LODWORD(v8) = a2;
  if ( a4 )
    *a4 = v8;
  if ( (_DWORD)v8 )
  {
    while ( 1 )
    {
      if ( !v4 || (v10 = (__int64 *)a1[4]) == 0 )
        ATL::AtlThrowImpl(-2147467259);
      v11 = *v10;
      *v4 = v11;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      a1[4] += 8LL;
      LODWORD(v8) = v8 - 1;
      if ( !(_DWORD)v8 )
        break;
      ++v4;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800075cc  push    rbx
0x1800075ce  push    rbp
0x1800075cf  push    rsi
0x1800075d0  push    rdi
0x1800075d1  sub     rsp, 28h
0x1800075d5  mov     rsi, r8
0x1800075d8  mov     rdi, rcx
0x1800075db  test    r9, r9
0x1800075de  jz      short loc_1800075E7
0x1800075e0  mov     dword ptr [r9], 0
0x1800075e7  test    edx, edx
0x1800075e9  jnz     short loc_1800075F5
0x1800075eb  mov     eax, 80070057h
0x1800075f0  jmp     loc_180007683
0x1800075f5  test    r8, r8
0x1800075f8  jz      loc_18000767E
0x1800075fe  cmp     edx, 1
0x180007601  jz      short loc_180007608
0x180007603  test    r9, r9
0x180007606  jz      short loc_18000767E
0x180007608  cmp     qword ptr [rcx+10h], 0
0x18000760d  jz      short loc_180007677
0x18000760f  mov     rbx, [rcx+18h]
0x180007613  test    rbx, rbx
0x180007616  jz      short loc_180007677
0x180007618  cmp     qword ptr [rcx+20h], 0
0x18000761d  jz      short loc_180007677
0x18000761f  sub     rbx, [rcx+20h]
0x180007623  xor     ebp, ebp
0x180007625  sar     rbx, 3
0x180007629  cmp     ebx, edx
0x18000762b  setb    bpl
0x18000762f  cmova   ebx, edx
0x180007632  test    r9, r9
0x180007635  jz      short loc_18000763A
0x180007637  mov     [r9], ebx
0x18000763a  test    ebx, ebx
0x18000763c  jz      short loc_180007673
0x18000763e  test    rsi, rsi
0x180007641  jz      short loc_18000768C
0x180007643  mov     rcx, [rdi+20h]
0x180007647  test    rcx, rcx
0x18000764a  jz      short loc_18000768C
0x18000764c  mov     rcx, [rcx]
0x18000764f  mov     [rsi], rcx
0x180007652  test    rcx, rcx
0x180007655  jz      short loc_180007663
0x180007657  mov     rax, [rcx]
0x18000765a  mov     rax, [rax+8]
0x18000765e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007663  add     qword ptr [rdi+20h], 8
0x180007668  add     ebx, 0FFFFFFFFh
0x18000766b  jz      short loc_180007673
0x18000766d  add     rsi, 8
0x180007671  jmp     short loc_18000763E
0x180007673  mov     eax, ebp
0x180007675  jmp     short loc_180007683
0x180007677  mov     eax, 80004005h
0x18000767c  jmp     short loc_180007683
0x18000767e  mov     eax, 80004003h
0x180007683  add     rsp, 28h
0x180007687  pop     rdi
0x180007688  pop     rsi
0x180007689  pop     rbp
0x18000768a  pop     rbx
0x18000768b  retn
0x18000768c  mov     ecx, 80004005h; int
0x180007691  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
