# YReader::GetNextAttributeInfoItem(InfoSet *)

- ea: `0x1004038d0`
- end: `0x100403b35`
- name: `?GetNextAttributeInfoItem@YReader@@UEAAJPEAW4InfoSet@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(YReader *__hidden this, enum InfoSet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path`

## callees

- `0x100402d90`
- `0x1004038d0`
- `0x100404670`
- `0x10040b880`
- `0x10040bfc0`
- `0x10040ca10`
- `0x100415430`
- `0x100423dd0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall YReader::GetNextAttributeInfoItem(YReader *this, enum InfoSet *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r14
  __int64 result; // rax
  __int16 v7; // bx
  unsigned int v8; // r8d
  _QWORD *v9; // rdx
  unsigned int v10; // r8d
  _QWORD *v11; // rdx
  YReader *v12; // rcx
  YReader *v13; // rcx
  int v14; // ecx
  __int128 v15; // [rsp+40h] [rbp-28h]

  if ( *((int *)this + 70) > 0 && *((int *)this + 437) >= 0 )
  {
    *((_DWORD *)this + 437) = -1072894386;
    *(_QWORD *)&v15 = YReader::ParseError;
    DWORD2(v15) = 0;
    *((_OWORD *)this + 92) = v15;
    (*((void (__fastcall **)(char *))this + 184))((char *)this + *((int *)this + 370) - 32);
    goto LABEL_15;
  }
  v4 = *((unsigned int *)this + 692);
  if ( (unsigned int)v4 >= *((_DWORD *)this + 702) )
  {
LABEL_15:
    *((_DWORD *)this + 436) = 0;
    *(_DWORD *)a2 = 0;
    v14 = *((_DWORD *)this + 437);
    result = 1;
    if ( v14 < 0 )
      return (unsigned int)v14;
    return result;
  }
  *((_DWORD *)this + 692) = v4 + 1;
  v5 = *((_QWORD *)this + 350) + 152 * v4;
  *((_DWORD *)this + 436) = 4;
  *((_OWORD *)this + 96) = *(_OWORD *)v5;
  *((_OWORD *)this + 98) = *(_OWORD *)(v5 + 32);
  *((_OWORD *)this + 99) = *(_OWORD *)(v5 + 48);
  *((_OWORD *)this + 101) = *(_OWORD *)(v5 + 64);
  *((_BYTE *)this + 1754) = *(_DWORD *)(v5 + 96) == 0;
  if ( *(_QWORD *)(v5 + 104) )
  {
    BlockAlloc::PopScope((YReader *)((char *)this + 384), *((void **)this + 226));
    v7 = *(_WORD *)(v5 + 136);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 9) + 80LL))(*((_QWORD *)this + 9), v5 + 104);
    *((_WORD *)this + 136) = v7;
    v8 = *((_DWORD *)this + 28);
    if ( *((_DWORD *)this + 29) == v8 )
    {
      _stack<void (Scanner::*)(void),8>::grow((__int64)this + 88, 0);
      v8 = *((_DWORD *)this + 28);
    }
    v9 = (_QWORD *)(*((_QWORD *)this + 13) + 8LL * v8);
    *((_DWORD *)this + 28) = v8 + 1;
    *v9 = Scanner::ScanQuoteEnd;
    v10 = *((_DWORD *)this + 28);
    if ( *((_DWORD *)this + 29) == v10 )
    {
      _stack<void (Scanner::*)(void),8>::grow((__int64)this + 88, 0);
      v10 = *((_DWORD *)this + 28);
    }
    v11 = (_QWORD *)(*((_QWORD *)this + 13) + 8LL * v10);
    *((_DWORD *)this + 28) = v10 + 1;
    *v11 = Scanner::ScanAttributeValue;
    *((_QWORD *)this + 23) = Scanner::ScanAttributeValue;
    v12 = (YReader *)((char *)this - 32);
    if ( *(_DWORD *)(v5 + 140) )
    {
      YReader::ParseAttributeValue(v12, 0);
      YReader::NormalizeAttributeValue((YReader *)((char *)this - 32), (YReader *)((char *)this + 1600));
      YReader::NormalizeTypedAttributeValue(v13, (YReader *)((char *)this + 1600), *(_DWORD *)(v5 + 140));
    }
    else
    {
      YReader::ParseAttributeValue(v12, 1);
      YReader::NormalizeAttributeValue((YReader *)((char *)this - 32), (YReader *)((char *)this + 1600));
    }
    *(_DWORD *)a2 = *((_DWORD *)this + 436);
    return *((unsigned int *)this + 437);
  }
  else
  {
    *((_OWORD *)this + 100) = *(_OWORD *)(v5 + 80);
    *(_DWORD *)a2 = *((_DWORD *)this + 436);
    return *((unsigned int *)this + 437);
  }
}

```

## disassembly

```asm
0x1004038d0  mov     [rsp+arg_10], rbx
0x1004038d5  mov     [rsp+arg_18], rsi
0x1004038da  mov     [rsp+arg_8], rdx
0x1004038df  mov     [rsp+arg_0], rcx
0x1004038e4  push    rdi
0x1004038e5  push    r14
0x1004038e7  push    r15
0x1004038e9  sub     rsp, 50h
0x1004038ed  mov     rsi, rdx
0x1004038f0  mov     rdi, rcx
0x1004038f3  cmp     dword ptr [rcx+118h], 0
0x1004038fa  jle     short loc_10040394D
0x1004038fc  cmp     dword ptr [rcx+6D4h], 0
0x100403903  jl      short loc_10040394D
0x100403905  mov     dword ptr [rcx+6D4h], 0C00CEE4Eh
0x10040390f  lea     rax, ?ParseError@YReader@@AEAAXXZ; YReader::ParseError(void)
0x100403916  mov     qword ptr [rsp+68h+var_28], rax
0x10040391b  xor     ebx, ebx
0x10040391d  mov     dword ptr [rsp+68h+var_28+8], ebx
0x100403921  movups  xmm0, [rsp+68h+var_28]
0x100403926  movups  xmmword ptr [rcx+5C0h], xmm0
0x10040392d  movsxd  rax, dword ptr [rcx+5C8h]
0x100403934  add     rcx, 0FFFFFFFFFFFFFFE0h
0x100403938  add     rcx, rax
0x10040393b  mov     rax, [rdi+5C0h]
0x100403942  call    cs:__guard_dispatch_icall_fptr
0x100403948  jmp     loc_100403B07
0x10040394d  mov     ecx, [rcx+0AD0h]
0x100403953  cmp     ecx, [rdi+0AF8h]
0x100403959  jnb     loc_100403B05
0x10040395f  lea     eax, [rcx+1]
0x100403962  mov     [rdi+0AD0h], eax
0x100403968  imul    r14, rcx, 98h
0x10040396f  add     r14, [rdi+0AF0h]
0x100403976  mov     dword ptr [rdi+6D0h], 4
0x100403980  movups  xmm0, xmmword ptr [r14]
0x100403984  movups  xmmword ptr [rdi+600h], xmm0
0x10040398b  movups  xmm0, xmmword ptr [r14+20h]
0x100403990  movups  xmmword ptr [rdi+620h], xmm0
0x100403997  movups  xmm0, xmmword ptr [r14+30h]
0x10040399c  movups  xmmword ptr [rdi+630h], xmm0
0x1004039a3  movups  xmm0, xmmword ptr [r14+40h]
0x1004039a8  movups  xmmword ptr [rdi+650h], xmm0
0x1004039af  cmp     dword ptr [r14+60h], 0
0x1004039b4  setz    al
0x1004039b7  mov     [rdi+6DAh], al
0x1004039bd  cmp     qword ptr [r14+68h], 0
0x1004039c2  jnz     short loc_1004039E3
0x1004039c4  movups  xmm0, xmmword ptr [r14+50h]
0x1004039c9  movups  xmmword ptr [rdi+640h], xmm0
0x1004039d0  mov     eax, [rdi+6D0h]
0x1004039d6  mov     [rsi], eax
0x1004039d8  mov     eax, [rdi+6D4h]
0x1004039de  jmp     loc_100403B1F
0x1004039e3  lea     rcx, [rdi+180h]; this
0x1004039ea  mov     rdx, [rdi+710h]; void *
0x1004039f1  call    ?PopScope@BlockAlloc@@QEAAXPEAX@Z; BlockAlloc::PopScope(void *)
0x1004039f6  movzx   ebx, word ptr [r14+88h]
0x1004039fe  mov     rcx, [rdi+48h]
0x100403a02  mov     rax, [rcx]
0x100403a05  lea     rdx, [r14+68h]
0x100403a09  mov     rax, [rax+50h]
0x100403a0d  call    cs:__guard_dispatch_icall_fptr
0x100403a13  mov     [rdi+110h], bx
0x100403a1a  mov     r8d, [rdi+70h]
0x100403a1e  cmp     [rdi+74h], r8d
0x100403a22  jnz     short loc_100403A33
0x100403a24  xor     edx, edx
0x100403a26  lea     rcx, [rdi+58h]
0x100403a2a  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x100403a2f  mov     r8d, [rdi+70h]
0x100403a33  mov     ecx, r8d
0x100403a36  mov     rax, [rdi+68h]
0x100403a3a  lea     rdx, [rax+rcx*8]
0x100403a3e  lea     eax, [r8+1]
0x100403a42  mov     [rdi+70h], eax
0x100403a45  lea     rax, ?ScanQuoteEnd@Scanner@@AEAAXXZ; Scanner::ScanQuoteEnd(void)
0x100403a4c  mov     [rdx], rax
0x100403a4f  mov     r8d, [rdi+70h]
0x100403a53  cmp     [rdi+74h], r8d
0x100403a57  jnz     short loc_100403A68
0x100403a59  xor     edx, edx
0x100403a5b  lea     rcx, [rdi+58h]
0x100403a5f  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x100403a64  mov     r8d, [rdi+70h]
0x100403a68  mov     ecx, r8d
0x100403a6b  mov     rax, [rdi+68h]
0x100403a6f  lea     rdx, [rax+rcx*8]
0x100403a73  lea     eax, [r8+1]
0x100403a77  mov     [rdi+70h], eax
0x100403a7a  lea     rax, ?ScanAttributeValue@Scanner@@AEAAXXZ; Scanner::ScanAttributeValue(void)
0x100403a81  mov     [rdx], rax
0x100403a84  mov     [rdi+0B8h], rax
0x100403a8b  lea     rcx, [rdi-20h]; this
0x100403a8f  cmp     dword ptr [r14+8Ch], 0
0x100403a97  jz      short loc_100403AC5
0x100403a99  xor     edx, edx; bool
0x100403a9b  call    ?ParseAttributeValue@YReader@@AEAAX_N@Z; YReader::ParseAttributeValue(bool)
0x100403aa0  lea     rdx, [rdi+640h]; struct StringPtr *
0x100403aa7  lea     rcx, [rdi-20h]; this
0x100403aab  call    ?NormalizeAttributeValue@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::NormalizeAttributeValue(StringPtr *)
0x100403ab0  mov     r8d, [r14+8Ch]; int
0x100403ab7  lea     rdx, [rdi+640h]; struct StringPtr *
0x100403abe  call    ?NormalizeTypedAttributeValue@YReader@@AEAAXPEAUStringPtr@@H@Z; YReader::NormalizeTypedAttributeValue(StringPtr *,int)
0x100403ac3  jmp     short loc_100403ADC
0x100403ac5  mov     dl, 1; bool
0x100403ac7  call    ?ParseAttributeValue@YReader@@AEAAX_N@Z; YReader::ParseAttributeValue(bool)
0x100403acc  lea     rdx, [rdi+640h]; struct StringPtr *
0x100403ad3  lea     rcx, [rdi-20h]; this
0x100403ad7  call    ?NormalizeAttributeValue@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::NormalizeAttributeValue(StringPtr *)
0x100403adc  jmp     short loc_100403AF5
0x100403ade  mov     rdi, [rsp+68h+arg_0]
0x100403ae3  lea     rcx, [rdi-20h]; this
0x100403ae7  mov     edx, [rsp+68h+var_48]; int
0x100403aeb  call    ?HandleException@YReader@@AEAAXJ@Z; YReader::HandleException(long)
0x100403af0  mov     rsi, [rsp+68h+arg_8]
0x100403af5  mov     eax, [rdi+6D0h]
0x100403afb  mov     [rsi], eax
0x100403afd  mov     eax, [rdi+6D4h]
0x100403b03  jmp     short loc_100403B1F
0x100403b05  xor     ebx, ebx
0x100403b07  mov     [rdi+6D0h], ebx
0x100403b0d  mov     [rsi], ebx
0x100403b0f  mov     ecx, [rdi+6D4h]
0x100403b15  mov     eax, 1
0x100403b1a  test    ecx, ecx
0x100403b1c  cmovs   eax, ecx
0x100403b1f  lea     r11, [rsp+68h+var_18]
0x100403b24  mov     rbx, [r11+30h]
0x100403b28  mov     rsi, [r11+38h]
0x100403b2c  mov     rsp, r11
0x100403b2f  pop     r15
0x100403b31  pop     r14
0x100403b33  pop     rdi
0x100403b34  retn
0x100439f20  push    rbp
0x100439f22  sub     rsp, 20h
0x100439f26  mov     rbp, rdx
0x100439f29  mov     [rbp+38h], rcx
0x100439f2d  mov     [rbp+30h], rcx
0x100439f31  mov     rax, [rbp+30h]
0x100439f35  mov     rcx, [rax]
0x100439f38  mov     [rbp+28h], rcx
0x100439f3c  mov     rax, [rbp+28h]
0x100439f40  mov     eax, [rax]
0x100439f42  cmp     eax, 0C0000005h
0x100439f47  jz      short loc_100439F79
0x100439f49  add     eax, 1FFFFFFFh
0x100439f4e  cmp     eax, 1
0x100439f51  ja      short loc_100439F69
0x100439f53  mov     rax, [rbp+28h]
0x100439f57  cmp     dword ptr [rax+18h], 1
0x100439f5b  jnz     short loc_100439F69
0x100439f5d  mov     rax, [rbp+28h]
0x100439f61  mov     ecx, [rax+20h]
0x100439f64  mov     [rbp+20h], ecx
0x100439f67  jmp     short loc_100439F70
0x100439f69  mov     dword ptr [rbp+20h], 8000FFFFh
0x100439f70  mov     dword ptr [rbp+24h], 1
0x100439f77  jmp     short loc_100439F80
0x100439f79  mov     dword ptr [rbp+24h], 0
0x100439f80  mov     eax, [rbp+24h]
0x100439f83  add     rsp, 20h
0x100439f87  pop     rbp
0x100439f88  retn
```
