# Parser::CreateBinNode(OpCode,ParseNode *,ParseNode *)

- ea: `0x18002f7d0`
- end: `0x18002f955`
- name: `?CreateBinNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@PEAU2@1@Z`
- size: `389`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ee0`
- `0x18002dc68`
- `0x18002e740`
- `0x180030808`

## callees

- `0x18000b714`
- `0x18002f7d0`

## import_xrefs

- `msvcrt!malloc` at `0x18002f8a1`
- `msvcrt!malloc` at `0x18002f913`
- `msvcrt!malloc` at `0x18002f8a1`
- `msvcrt!malloc` at `0x18002f913`

## pseudocode

```c
_QWORD *__fastcall Parser::CreateBinNode(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int v4; // r15d
  int v5; // ebp
  _QWORD *v10; // rax
  _QWORD *result; // rax
  __int64 v12; // rdx
  int v13; // r13d
  int v14; // ecx
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rax
  _QWORD *v18; // rdx

  v4 = *(_DWORD *)(a1 + 28);
  v5 = *(_DWORD *)(a1 + 24);
  if ( v4 - v5 >= 40 )
    goto LABEL_2;
  v13 = *(_DWORD *)(a1 + 36);
  if ( v13 > 40 )
  {
    v14 = *(_DWORD *)(a1 + 32);
    v15 = 40;
    if ( v4 > 40 )
      v15 = v4;
    v16 = 2 * v15;
    if ( v14 <= v16 )
      v14 = v16;
    if ( v14 <= v13 )
    {
      if ( v14 < 40 )
        goto LABEL_26;
      v13 = v14;
    }
    if ( v13 + 8 > v13 && v13 + 8 >= 40 )
    {
      v17 = malloc((unsigned int)v13 + 8LL);
      if ( v17 )
      {
        v5 = 0;
        *v17 = *(_QWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 16) = v17;
        *(_DWORD *)(a1 + 28) = v13;
LABEL_2:
        *(_DWORD *)(a1 + 24) = v5 + 40;
        v10 = (_QWORD *)(*(_QWORD *)(a1 + 16) + v5);
        goto LABEL_3;
      }
    }
LABEL_26:
    Parser::Error((Parser *)a1, 1001);
  }
  v10 = malloc(0x30u);
  if ( !v10 )
    goto LABEL_26;
  v18 = *(_QWORD **)(a1 + 16);
  if ( v5 >= v4 )
  {
    *v10 = v18;
    *(_QWORD *)(a1 + 16) = v10;
  }
  else
  {
    *v10 = *v18;
    *v18 = v10;
  }
LABEL_3:
  result = v10 + 1;
  if ( !result )
    goto LABEL_26;
  *(_DWORD *)result = a2;
  *((_DWORD *)result + 1) = 0;
  result[2] = 0;
  result[3] = a3;
  result[4] = a4;
  if ( a3 )
  {
    *((_DWORD *)result + 2) = *(_DWORD *)(a3 + 8);
    if ( a4 )
      LODWORD(v12) = *(_DWORD *)(a4 + 12);
    else
      LODWORD(v12) = *(_DWORD *)(a3 + 12);
  }
  else
  {
    *((_DWORD *)result + 2) = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 352) + 32LL)
                                      - *(_QWORD *)(*(_QWORD *)(a1 + 352) + 16LL)) >> 1;
    v12 = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 352) + 40LL) - *(_QWORD *)(*(_QWORD *)(a1 + 352) + 16LL)) >> 1;
  }
  *((_DWORD *)result + 3) = v12;
  return result;
}

```

## disassembly

```asm
0x18002f7d0  push    rbx
0x18002f7d2  push    rbp
0x18002f7d3  push    rsi
0x18002f7d4  push    rdi
0x18002f7d5  push    r12
0x18002f7d7  push    r13
0x18002f7d9  push    r14
0x18002f7db  push    r15
0x18002f7dd  sub     rsp, 28h
0x18002f7e1  mov     r15d, [rcx+1Ch]
0x18002f7e5  xor     r12d, r12d
0x18002f7e8  mov     ebp, [rcx+18h]
0x18002f7eb  mov     eax, r15d
0x18002f7ee  sub     eax, ebp
0x18002f7f0  mov     rbx, r9
0x18002f7f3  mov     rdi, r8
0x18002f7f6  mov     r14d, edx
0x18002f7f9  mov     rsi, rcx
0x18002f7fc  cmp     eax, 28h ; '('
0x18002f7ff  jl      short loc_18002F85B
0x18002f801  lea     eax, [rbp+28h]
0x18002f804  mov     [rsi+18h], eax
0x18002f807  movsxd  rax, ebp
0x18002f80a  add     rax, [rsi+10h]
0x18002f80e  add     rax, 8
0x18002f812  jz      loc_18002F947
0x18002f818  mov     [rax], r14d
0x18002f81b  mov     [rax+4], r12d
0x18002f81f  mov     [rax+10h], r12
0x18002f823  mov     [rax+18h], rdi
0x18002f827  mov     [rax+20h], rbx
0x18002f82b  test    rdi, rdi
0x18002f82e  jz      loc_18002F8CD
0x18002f834  mov     ecx, [rdi+8]
0x18002f837  mov     [rax+8], ecx
0x18002f83a  test    rbx, rbx
0x18002f83d  jz      loc_18002F8F9
0x18002f843  mov     edx, [rbx+0Ch]
0x18002f846  mov     [rax+0Ch], edx
0x18002f849  add     rsp, 28h
0x18002f84d  pop     r15
0x18002f84f  pop     r14
0x18002f851  pop     r13
0x18002f853  pop     r12
0x18002f855  pop     rdi
0x18002f856  pop     rsi
0x18002f857  pop     rbp
0x18002f858  pop     rbx
0x18002f859  retn
0x18002f85b  mov     r13d, [rcx+24h]
0x18002f85f  cmp     r13d, 28h ; '('
0x18002f863  jle     loc_18002F90E
0x18002f869  mov     ecx, [rcx+20h]
0x18002f86c  mov     eax, 28h ; '('
0x18002f871  cmp     r15d, eax
0x18002f874  cmovg   eax, r15d
0x18002f878  add     eax, eax
0x18002f87a  cmp     ecx, eax
0x18002f87c  cmovle  ecx, eax
0x18002f87f  cmp     ecx, r13d
0x18002f882  jle     short loc_18002F901
0x18002f884  lea     eax, [r13+8]
0x18002f888  cmp     eax, r13d
0x18002f88b  jl      loc_18002F947
0x18002f891  cmp     eax, 28h ; '('
0x18002f894  jl      loc_18002F947
0x18002f89a  mov     ecx, r13d
0x18002f89d  add     rcx, 8; Size
0x18002f8a1  call    cs:__imp_malloc
0x18002f8a8  nop     dword ptr [rax+rax+00h]
0x18002f8ad  test    rax, rax
0x18002f8b0  jz      loc_18002F947
0x18002f8b6  mov     rcx, [rsi+10h]
0x18002f8ba  mov     ebp, r12d
0x18002f8bd  mov     [rax], rcx
0x18002f8c0  mov     [rsi+10h], rax
0x18002f8c4  mov     [rsi+1Ch], r13d
0x18002f8c8  jmp     loc_18002F801
0x18002f8cd  mov     rcx, [rsi+160h]
0x18002f8d4  mov     rdx, [rcx+20h]
0x18002f8d8  sub     rdx, [rcx+10h]
0x18002f8dc  sar     rdx, 1
0x18002f8df  mov     [rax+8], edx
0x18002f8e2  mov     rcx, [rsi+160h]
0x18002f8e9  mov     rdx, [rcx+28h]
0x18002f8ed  sub     rdx, [rcx+10h]
0x18002f8f1  sar     rdx, 1
0x18002f8f4  jmp     loc_18002F846
0x18002f8f9  mov     edx, [rdi+0Ch]
0x18002f8fc  jmp     loc_18002F846
0x18002f901  cmp     ecx, 28h ; '('
0x18002f904  jl      short loc_18002F947
0x18002f906  mov     r13d, ecx
0x18002f909  jmp     loc_18002F884
0x18002f90e  mov     ecx, 30h ; '0'; Size
0x18002f913  call    cs:__imp_malloc
0x18002f91a  nop     dword ptr [rax+rax+00h]
0x18002f91f  test    rax, rax
0x18002f922  jz      short loc_18002F947
0x18002f924  mov     rdx, [rsi+10h]
0x18002f928  cmp     ebp, r15d
0x18002f92b  jge     short loc_18002F93B
0x18002f92d  mov     rcx, [rdx]
0x18002f930  mov     [rax], rcx
0x18002f933  mov     [rdx], rax
0x18002f936  jmp     loc_18002F80E
0x18002f93b  mov     [rax], rdx
0x18002f93e  mov     [rsi+10h], rax
0x18002f942  jmp     loc_18002F80E
0x18002f947  mov     edx, 3E9h; int
0x18002f94c  mov     rcx, rsi; this
0x18002f94f  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
