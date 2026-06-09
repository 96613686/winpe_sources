# ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(IConnectionPoint * *,IConnectionPoint * *,IUnknown *,ATL::CComEnumFlags)

- ea: `0x180006a9c`
- end: `0x180006ba9`
- name: `?Init@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@QEAAJPEAPEAUIConnectionPoint@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003fbc`
- `0x180004fd0`

## callees

- `0x1800011ac`
- `0x180003b70`
- `0x180006a9c`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 **v5; // rsi
  __int64 v7; // rbp
  __int64 *v8; // rdi
  unsigned __int64 v10; // r15
  __int64 *v11; // rax
  __int64 result; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx

  v5 = (__int64 **)(a1 + 32);
  v7 = a3;
  v8 = a2;
  if ( a5 == 3 )
  {
    v10 = (a3 - (__int64)a2) >> 3;
    v11 = (__int64 *)operator new[](saturated_mul(v10, 8u));
    *(_QWORD *)(a1 + 16) = v11;
    *v5 = v11;
    if ( !v11 )
      return 2147942414LL;
    while ( v8 != (__int64 *)v7 )
    {
      if ( !v11 || !v8 )
        ATL::AtlThrowImpl(-2147467259);
      v13 = *v8;
      *v11 = *v8;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      v11 = ++*v5;
      ++v8;
    }
    v7 = *(_QWORD *)(a1 + 16) + 8 * v10;
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a2;
  }
  *(_QWORD *)(a1 + 24) = v7;
  if ( *(_QWORD *)(a1 + 8) != a4 )
  {
    if ( a4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
    v14 = *(_QWORD *)(a1 + 8);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *(_QWORD *)(a1 + 8) = a4;
  }
  *v5 = *(__int64 **)(a1 + 16);
  result = 0;
  *(_DWORD *)(a1 + 40) = a5;
  return result;
}

```

## disassembly

```asm
0x180006a9c  push    rbx
0x180006a9e  push    rbp
0x180006a9f  push    rsi
0x180006aa0  push    rdi
0x180006aa1  push    r12
0x180006aa3  push    r14
0x180006aa5  push    r15
0x180006aa7  sub     rsp, 20h
0x180006aab  mov     r12d, [rsp+58h+arg_20]
0x180006ab3  lea     rsi, [rcx+20h]
0x180006ab7  mov     r14, r9
0x180006aba  mov     rbp, r8
0x180006abd  mov     rdi, rdx
0x180006ac0  mov     rbx, rcx
0x180006ac3  cmp     r12d, 3
0x180006ac7  jnz     short loc_180006B47
0x180006ac9  mov     r15, r8
0x180006acc  lea     eax, [r12+5]
0x180006ad1  sub     r15, rdx
0x180006ad4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006adb  sar     r15, 3
0x180006adf  mul     r15
0x180006ae2  cmovb   rax, rcx
0x180006ae6  mov     rcx, rax; unsigned __int64
0x180006ae9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006aee  mov     [rbx+10h], rax
0x180006af2  mov     [rsi], rax
0x180006af5  test    rax, rax
0x180006af8  jnz     short loc_180006B38
0x180006afa  mov     eax, 8007000Eh
0x180006aff  jmp     loc_180006B8F
0x180006b04  test    rax, rax
0x180006b07  jz      loc_180006B9E
0x180006b0d  test    rdi, rdi
0x180006b10  jz      loc_180006B9E
0x180006b16  mov     rcx, [rdi]
0x180006b19  mov     [rax], rcx
0x180006b1c  test    rcx, rcx
0x180006b1f  jz      short loc_180006B2D
0x180006b21  mov     rax, [rcx]
0x180006b24  mov     rax, [rax+8]
0x180006b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b2d  add     qword ptr [rsi], 8
0x180006b31  mov     rax, [rsi]
0x180006b34  add     rdi, 8
0x180006b38  cmp     rdi, rbp
0x180006b3b  jnz     short loc_180006B04
0x180006b3d  mov     rax, [rbx+10h]
0x180006b41  lea     rbp, [rax+r15*8]
0x180006b45  jmp     short loc_180006B4B
0x180006b47  mov     [rcx+10h], rdi
0x180006b4b  mov     [rbx+18h], rbp
0x180006b4f  cmp     [rbx+8], r14
0x180006b53  jz      short loc_180006B82
0x180006b55  test    r14, r14
0x180006b58  jz      short loc_180006B69
0x180006b5a  mov     rax, [r14]
0x180006b5d  mov     rcx, r14
0x180006b60  mov     rax, [rax+8]
0x180006b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b69  mov     rcx, [rbx+8]
0x180006b6d  test    rcx, rcx
0x180006b70  jz      short loc_180006B7E
0x180006b72  mov     rax, [rcx]
0x180006b75  mov     rax, [rax+10h]
0x180006b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7e  mov     [rbx+8], r14
0x180006b82  mov     rax, [rbx+10h]
0x180006b86  mov     [rsi], rax
0x180006b89  xor     eax, eax
0x180006b8b  mov     [rbx+28h], r12d
0x180006b8f  add     rsp, 20h
0x180006b93  pop     r15
0x180006b95  pop     r14
0x180006b97  pop     r12
0x180006b99  pop     rdi
0x180006b9a  pop     rsi
0x180006b9b  pop     rbp
0x180006b9c  pop     rbx
0x180006b9d  retn
0x180006b9e  mov     ecx, 80004005h; int
0x180006ba3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
