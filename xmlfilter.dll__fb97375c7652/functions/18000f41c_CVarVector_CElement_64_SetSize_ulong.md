# CVarVector<CElement,64>::SetSize(ulong)

- ea: `0x18000f41c`
- end: `0x18000f534`
- name: `?SetSize@?$CVarVector@VCElement@@$0EA@@@QEAAXK@Z`
- size: `280`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ef44`
- `0x18000f640`
- `0x18000f7e0`
- `0x18000fc90`

## callees

- `0x180003f50`
- `0x18000c7ec`
- `0x18000ef44`
- `0x18000f41c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f4c0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f4c0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f455`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f455`

## string_xrefs

- `0x18000f522`: `onecoreuap\base\appmodel\search\filters\xml\VarVector.h`

## pseudocode

```c
void __fastcall CVarVector<CElement,64>::SetSize(__int64 a1, unsigned int a2)
{
  unsigned int v4; // edi
  unsigned int v5; // r14d
  _DWORD *v6; // r15
  __int64 v7; // rbp
  unsigned int i; // ebp
  _DWORD *v9; // rcx
  unsigned int j; // ebp
  unsigned int v11; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = *(_DWORD *)(a1 + 272);
  v5 = *(_DWORD *)(a1 + 276);
  if ( a2 > v5 )
  {
    do
      v5 *= 2;
    while ( a2 > v5 );
    v6 = malloc(4LL * v5);
    if ( !v6 )
    {
      v11 = wil::verify_hresult<long>(2147942414LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\VarVector.h",
        (const char *)v11,
        0);
    }
    v7 = 0;
    if ( v4 )
    {
      do
      {
        v6[v7] = *(_DWORD *)CVarVector<CElement,64>::GetCell(a1, (unsigned int)v7);
        v7 = (unsigned int)(v7 + 1);
      }
      while ( (unsigned int)v7 < v4 );
      for ( i = 0; i < v4; ++i )
        CVarVector<CElement,64>::GetCell(a1, i);
    }
    *(_DWORD *)(a1 + 276) = v5;
    v9 = *(_DWORD **)a1;
    if ( *(_DWORD **)a1 != v6 )
    {
      if ( *(_BYTE *)(a1 + 8) && v9 )
        free(v9);
      *(_QWORD *)a1 = v6;
    }
    *(_BYTE *)(a1 + 8) = v6 != 0;
  }
  for ( j = a2; j < v4; ++j )
    CVarVector<CElement,64>::GetCell(a1, j);
  *(_DWORD *)(a1 + 272) = a2;
  while ( v4 < a2 )
    *(_DWORD *)CVarVector<CElement,64>::GetCell(a1, v4++) = 0;
}

```

## disassembly

```asm
0x18000f41c  push    rbx
0x18000f41e  push    rbp
0x18000f41f  push    rsi
0x18000f420  push    rdi
0x18000f421  push    r12
0x18000f423  push    r14
0x18000f425  push    r15
0x18000f427  sub     rsp, 30h
0x18000f42b  mov     esi, edx
0x18000f42d  mov     rbx, rcx
0x18000f430  mov     edi, [rcx+110h]
0x18000f436  mov     r14d, [rcx+114h]
0x18000f43d  cmp     edx, r14d
0x18000f440  jbe     loc_18000F4CD
0x18000f446  add     r14d, r14d
0x18000f449  cmp     esi, r14d
0x18000f44c  ja      short loc_18000F446
0x18000f44e  mov     ecx, r14d
0x18000f451  shl     rcx, 2; Size
0x18000f455  call    cs:__imp_malloc
0x18000f45b  mov     r15, rax
0x18000f45e  mov     qword ptr [rsp+68h+var_48], rax; int
0x18000f463  test    rax, rax
0x18000f466  setnz   r12b
0x18000f46a  mov     [rsp+68h+var_40], r12b
0x18000f46f  test    rax, rax
0x18000f472  jz      loc_18000F510
0x18000f478  xor     ebp, ebp
0x18000f47a  test    edi, edi
0x18000f47c  jz      short loc_18000F4A6
0x18000f47e  mov     edx, ebp
0x18000f480  mov     rcx, rbx
0x18000f483  call    ?GetCell@?$CVarVector@VCElement@@$0EA@@@IEAAPEAVCElement@@K@Z; CVarVector<CElement,64>::GetCell(ulong)
0x18000f488  mov     eax, [rax]
0x18000f48a  mov     [r15+rbp*4], eax
0x18000f48e  inc     ebp
0x18000f490  cmp     ebp, edi
0x18000f492  jb      short loc_18000F47E
0x18000f494  xor     ebp, ebp
0x18000f496  mov     edx, ebp
0x18000f498  mov     rcx, rbx
0x18000f49b  call    ?GetCell@?$CVarVector@VCElement@@$0EA@@@IEAAPEAVCElement@@K@Z; CVarVector<CElement,64>::GetCell(ulong)
0x18000f4a0  inc     ebp
0x18000f4a2  cmp     ebp, edi
0x18000f4a4  jb      short loc_18000F496
0x18000f4a6  mov     [rbx+114h], r14d
0x18000f4ad  mov     rcx, [rbx]; Block
0x18000f4b0  cmp     rcx, r15
0x18000f4b3  jz      short loc_18000F4C9
0x18000f4b5  cmp     byte ptr [rbx+8], 0
0x18000f4b9  jz      short loc_18000F4C6
0x18000f4bb  test    rcx, rcx
0x18000f4be  jz      short loc_18000F4C6
0x18000f4c0  call    cs:__imp_free
0x18000f4c6  mov     [rbx], r15
0x18000f4c9  mov     [rbx+8], r12b
0x18000f4cd  mov     ebp, esi
0x18000f4cf  cmp     esi, edi
0x18000f4d1  jnb     short loc_18000F4E3
0x18000f4d3  mov     edx, ebp
0x18000f4d5  mov     rcx, rbx
0x18000f4d8  call    ?GetCell@?$CVarVector@VCElement@@$0EA@@@IEAAPEAVCElement@@K@Z; CVarVector<CElement,64>::GetCell(ulong)
0x18000f4dd  inc     ebp
0x18000f4df  cmp     ebp, edi
0x18000f4e1  jb      short loc_18000F4D3
0x18000f4e3  mov     [rbx+110h], esi
0x18000f4e9  jmp     short loc_18000F4FD
0x18000f4eb  mov     edx, edi
0x18000f4ed  mov     rcx, rbx
0x18000f4f0  call    ?GetCell@?$CVarVector@VCElement@@$0EA@@@IEAAPEAVCElement@@K@Z; CVarVector<CElement,64>::GetCell(ulong)
0x18000f4f5  mov     dword ptr [rax], 0
0x18000f4fb  inc     edi
0x18000f4fd  cmp     edi, esi
0x18000f4ff  jb      short loc_18000F4EB
0x18000f501  add     rsp, 30h
0x18000f505  pop     r15
0x18000f507  pop     r14
0x18000f509  pop     r12
0x18000f50b  pop     rdi
0x18000f50c  pop     rsi
0x18000f50d  pop     rbp
0x18000f50e  pop     rbx
0x18000f50f  retn
0x18000f510  mov     ecx, 8007000Eh
0x18000f515  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000f51a  mov     r9d, eax; char *
0x18000f51d  mov     rcx, [rsp+68h]; this
0x18000f522  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000f529  mov     edx, 87h; void *
0x18000f52e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
