# CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::SetValue(ulong,CASFScriptCommandObjectBase::COMMAND_RECORD)

- ea: `0x18000cb20`
- end: `0x18000cc30`
- name: `?SetValue@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@QEAAJKUCOMMAND_RECORD@CASFScriptCommandObjectBase@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c36c`
- `0x1800221d0`

## callees

- `0x1800015d0`
- `0x18000cb20`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::SetValue(
        _DWORD *a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 result; // rax
  _DWORD *v6; // rsi
  _DWORD *i; // rbx
  unsigned int v8; // eax
  __int64 (__fastcall **v9)(_DWORD *, __int64 *); // rax
  _DWORD *v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 (__fastcall **v13)(_QWORD, _QWORD *); // xmm1_8
  _DWORD *v14; // [rsp+20h] [rbp-28h] BYREF

  if ( !a1 )
    return 2147500035LL;
  v6 = 0;
  for ( i = a1; i; i = (_DWORD *)*((_QWORD *)i + 66) )
  {
    v8 = i[2];
    if ( a2 < v8 )
      break;
    if ( a2 < v8 + 20 )
      goto LABEL_12;
    v6 = i;
  }
  v9 = *(__int64 (__fastcall ***)(_DWORD *, __int64 *))a1;
  v14 = 0;
  result = (*v9)(a1, (__int64 *)&v14);
  if ( (int)result < 0 )
    return result;
  v14[2] = 20 * (a2 / 0x14);
  v10 = v14;
  if ( v6 )
    *((_QWORD *)v6 + 66) = v14;
  *((_QWORD *)v10 + 66) = i;
  i = v14;
LABEL_12:
  v11 = a2 - i[2];
  if ( ((unsigned int)v11 & 0xFFFFFFF8) >= 0x18 )
    return 2147549183LL;
  *((_BYTE *)i + ((unsigned __int64)(unsigned int)v11 >> 3) + 40) |= CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::s_bSingleBitMasks[v11 & 7];
  if ( (unsigned int)v11 >= 0x14 )
    return 2147549183LL;
  v12 = 3 * v11;
  v13 = *(__int64 (__fastcall ***)(_QWORD, _QWORD *))(a3 + 16);
  *(_OWORD *)&i[2 * v12 + 12] = *(_OWORD *)a3;
  *(_QWORD *)&i[2 * v12 + 16] = v13;
  return 0;
}

```

## disassembly

```asm
0x18000cb20  mov     [rsp+arg_10], rbx
0x18000cb25  push    rbp
0x18000cb26  push    rsi
0x18000cb27  push    rdi
0x18000cb28  sub     rsp, 30h
0x18000cb2c  mov     rax, cs:__security_cookie
0x18000cb33  xor     rax, rsp
0x18000cb36  mov     [rsp+48h+var_20], rax
0x18000cb3b  mov     rbp, r8
0x18000cb3e  mov     edi, edx
0x18000cb40  test    rcx, rcx
0x18000cb43  jnz     short loc_18000CB4F
0x18000cb45  mov     eax, 80004003h
0x18000cb4a  jmp     loc_18000CC16
0x18000cb4f  xor     esi, esi
0x18000cb51  mov     rbx, rcx
0x18000cb54  test    rbx, rbx
0x18000cb57  jz      short loc_18000CB73
0x18000cb59  mov     eax, [rbx+8]
0x18000cb5c  cmp     edi, eax
0x18000cb5e  jb      short loc_18000CB73
0x18000cb60  add     eax, 14h
0x18000cb63  cmp     edi, eax
0x18000cb65  jb      short loc_18000CBC9
0x18000cb67  mov     rsi, rbx
0x18000cb6a  mov     rbx, [rbx+210h]
0x18000cb71  jmp     short loc_18000CB54
0x18000cb73  mov     rax, [rcx]
0x18000cb76  lea     rdx, [rsp+48h+var_28]
0x18000cb7b  mov     [rsp+48h+var_28], 0
0x18000cb84  mov     rax, [rax]
0x18000cb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb8c  test    eax, eax
0x18000cb8e  js      loc_18000CC16
0x18000cb94  mov     eax, 0CCCCCCCDh
0x18000cb99  mul     edi
0x18000cb9b  mov     rax, [rsp+48h+var_28]
0x18000cba0  shr     edx, 4
0x18000cba3  lea     ecx, [rdx+rdx*4]
0x18000cba6  shl     ecx, 2
0x18000cba9  mov     [rax+8], ecx
0x18000cbac  mov     rax, [rsp+48h+var_28]
0x18000cbb1  test    rsi, rsi
0x18000cbb4  jz      short loc_18000CBBD
0x18000cbb6  mov     [rsi+210h], rax
0x18000cbbd  mov     [rax+210h], rbx
0x18000cbc4  mov     rbx, [rsp+48h+var_28]
0x18000cbc9  sub     edi, [rbx+8]
0x18000cbcc  mov     eax, edi
0x18000cbce  and     eax, 0FFFFFFF8h
0x18000cbd1  cmp     eax, 18h
0x18000cbd4  jnb     short loc_18000CC11
0x18000cbd6  mov     eax, edi
0x18000cbd8  lea     r8, ?s_bSingleBitMasks@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::s_bSingleBitMasks
0x18000cbdf  and     eax, 7
0x18000cbe2  mov     ecx, edi
0x18000cbe4  shr     rcx, 3
0x18000cbe8  mov     al, [rax+r8]
0x18000cbec  or      [rcx+rbx+28h], al
0x18000cbf0  cmp     edi, 14h
0x18000cbf3  jnb     short loc_18000CC11
0x18000cbf5  movaps  xmm0, xmmword ptr [rbp+0]
0x18000cbf9  lea     rax, [rdi+rdi*2]
0x18000cbfd  movsd   xmm1, qword ptr [rbp+10h]
0x18000cc02  movups  xmmword ptr [rbx+rax*8+30h], xmm0
0x18000cc07  movsd   qword ptr [rbx+rax*8+40h], xmm1
0x18000cc0d  xor     eax, eax
0x18000cc0f  jmp     short loc_18000CC16
0x18000cc11  mov     eax, 8000FFFFh
0x18000cc16  mov     rcx, [rsp+48h+var_20]
0x18000cc1b  xor     rcx, rsp; StackCookie
0x18000cc1e  call    __security_check_cookie
0x18000cc23  mov     rbx, [rsp+48h+arg_10]
0x18000cc28  add     rsp, 30h
0x18000cc2c  pop     rdi
0x18000cc2d  pop     rsi
0x18000cc2e  pop     rbp
0x18000cc2f  retn
```
