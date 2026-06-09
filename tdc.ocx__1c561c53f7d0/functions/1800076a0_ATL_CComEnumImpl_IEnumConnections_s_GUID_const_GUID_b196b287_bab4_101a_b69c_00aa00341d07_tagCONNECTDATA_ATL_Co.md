# ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Next(ulong,tagCONNECTDATA *,ulong *)

- ea: `0x1800076a0`
- end: `0x18000776f`
- name: `?Next@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@UEAAJKPEAUtagCONNECTDATA@@PEAK@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800075c0`

## callees

- `0x180003b70`
- `0x1800076a0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Next(
        _QWORD *a1,
        unsigned int a2,
        _QWORD *a3,
        _DWORD *a4)
{
  _QWORD *v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rbx
  BOOL v9; // ebp
  _OWORD *v10; // rax

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
  v8 = (v7 - a1[4]) >> 4;
  v9 = (unsigned int)v8 < a2;
  if ( (unsigned int)v8 > a2 )
    LODWORD(v8) = a2;
  if ( a4 )
    *a4 = v8;
  if ( (_DWORD)v8 )
  {
    while ( 1 )
    {
      if ( !v4 || (v10 = (_OWORD *)a1[4]) == 0 )
        ATL::AtlThrowImpl(-2147467259);
      *(_OWORD *)v4 = *v10;
      if ( *v4 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
      a1[4] += 16LL;
      LODWORD(v8) = v8 - 1;
      if ( !(_DWORD)v8 )
        break;
      v4 += 2;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800076a0  push    rbx
0x1800076a2  push    rbp
0x1800076a3  push    rsi
0x1800076a4  push    rdi
0x1800076a5  sub     rsp, 28h
0x1800076a9  mov     rsi, r8
0x1800076ac  mov     rdi, rcx
0x1800076af  test    r9, r9
0x1800076b2  jz      short loc_1800076BB
0x1800076b4  mov     dword ptr [r9], 0
0x1800076bb  test    edx, edx
0x1800076bd  jnz     short loc_1800076C9
0x1800076bf  mov     eax, 80070057h
0x1800076c4  jmp     loc_18000775B
0x1800076c9  test    r8, r8
0x1800076cc  jz      loc_180007756
0x1800076d2  cmp     edx, 1
0x1800076d5  jz      short loc_1800076DC
0x1800076d7  test    r9, r9
0x1800076da  jz      short loc_180007756
0x1800076dc  cmp     qword ptr [rcx+10h], 0
0x1800076e1  jz      short loc_18000774F
0x1800076e3  mov     rbx, [rcx+18h]
0x1800076e7  test    rbx, rbx
0x1800076ea  jz      short loc_18000774F
0x1800076ec  cmp     qword ptr [rcx+20h], 0
0x1800076f1  jz      short loc_18000774F
0x1800076f3  sub     rbx, [rcx+20h]
0x1800076f7  xor     ebp, ebp
0x1800076f9  sar     rbx, 4
0x1800076fd  cmp     ebx, edx
0x1800076ff  setb    bpl
0x180007703  cmova   ebx, edx
0x180007706  test    r9, r9
0x180007709  jz      short loc_18000770E
0x18000770b  mov     [r9], ebx
0x18000770e  test    ebx, ebx
0x180007710  jz      short loc_18000774B
0x180007712  test    rsi, rsi
0x180007715  jz      short loc_180007764
0x180007717  mov     rax, [rdi+20h]
0x18000771b  test    rax, rax
0x18000771e  jz      short loc_180007764
0x180007720  movups  xmm0, xmmword ptr [rax]
0x180007723  movdqu  xmmword ptr [rsi], xmm0
0x180007727  mov     rcx, [rsi]
0x18000772a  test    rcx, rcx
0x18000772d  jz      short loc_18000773B
0x18000772f  mov     rax, [rcx]
0x180007732  mov     rax, [rax+8]
0x180007736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000773b  add     qword ptr [rdi+20h], 10h
0x180007740  add     ebx, 0FFFFFFFFh
0x180007743  jz      short loc_18000774B
0x180007745  add     rsi, 10h
0x180007749  jmp     short loc_180007712
0x18000774b  mov     eax, ebp
0x18000774d  jmp     short loc_18000775B
0x18000774f  mov     eax, 80004005h
0x180007754  jmp     short loc_18000775B
0x180007756  mov     eax, 80004003h
0x18000775b  add     rsp, 28h
0x18000775f  pop     rdi
0x180007760  pop     rsi
0x180007761  pop     rbp
0x180007762  pop     rbx
0x180007763  retn
0x180007764  mov     ecx, 80004005h; int
0x180007769  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
