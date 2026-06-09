# JSONParserLib::JSONNode::`scalar deleting destructor'(uint)

- ea: `0x10082c530`
- end: `0x10082c6b4`
- name: `??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z`
- size: `388`
- prototype: `void *__fastcall(JSONParserLib::JSONNode *__hidden this, unsigned int)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x10082c180`
- `0x10082c510`
- `0x10082c530`
- `0x10082cfb0`
- `0x10082e560`
- `0x10082fe90`
- `0x1008303b0`
- `0x100830750`
- `0x100830bd0`
- `0x100831d50`

## callees

- `0x10082c530`

## import_xrefs

- `sqldk!??3@YAXPEAX_K@Z` at `0x10082c580`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10082c610`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10082c689`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10082c580`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10082c610`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10082c689`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10082c65f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10082c65f`

## string_xrefs

- `0x10082c648`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Parser.cpp`

## pseudocode

```c
JSONParserLib::JSONNode *__fastcall JSONParserLib::JSONNode::`scalar deleting destructor'(
        JSONParserLib::JSONNode *this,
        char a2)
{
  void *v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // eax
  JSONParserLib::JSONNode **v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rbx
  JSONParserLib::JSONNode *v10; // rcx

  switch ( *(_DWORD *)this )
  {
    case 0:
    case 4:
    case 5:
    case 6:
      break;
    case 1:
      v5 = *((_QWORD *)this + 2);
      if ( v5 )
      {
        v9 = *(_QWORD *)(v5 + 8);
        if ( !v9 )
          goto LABEL_11;
        do
        {
          if ( *(_QWORD *)v9 )
          {
            operator delete(*(void **)v9, 2u);
            *(_QWORD *)v9 = 0;
          }
          v10 = *(JSONParserLib::JSONNode **)(v9 + 8);
          if ( v10 )
            JSONParserLib::JSONNode::`scalar deleting destructor'(v10, 1u);
          *(_QWORD *)(v9 + 8) = 0;
          v9 = *(_QWORD *)(v9 + 16);
        }
        while ( v9 );
        goto LABEL_10;
      }
      break;
    case 2:
      v5 = *((_QWORD *)this + 2);
      if ( v5 )
      {
        v6 = *(_DWORD *)(v5 + 28);
        v7 = *(JSONParserLib::JSONNode ***)(v5 + 16);
        if ( !v6 )
          goto LABEL_11;
        v8 = v6;
        do
        {
          if ( *v7 )
          {
            JSONParserLib::JSONNode::`scalar deleting destructor'(*v7, 1u);
            *v7 = 0;
          }
          ++v7;
          --v8;
        }
        while ( v8 );
LABEL_10:
        v5 = *((_QWORD *)this + 2);
        if ( v5 )
        {
LABEL_11:
          (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
          *((_QWORD *)this + 2) = 0;
        }
      }
      break;
    case 3:
      v4 = (void *)*((_QWORD *)this + 2);
      if ( v4 )
      {
        operator delete(v4, 2u);
        *((_QWORD *)this + 2) = 0;
      }
      break;
    default:
      utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_Parser.cpp", 102, "Invalid switch value");
      break;
  }
  *((_QWORD *)this + 3) = 0;
  *(_DWORD *)this = 0;
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x20u);
  return this;
}

```

## disassembly

```asm
0x10082c530  push    rdi
0x10082c532  sub     rsp, 30h
0x10082c536  movsxd  rax, dword ptr [rcx]
0x10082c539  mov     rdi, rcx
0x10082c53c  mov     [rsp+38h+arg_0], rbx
0x10082c541  mov     [rsp+38h+arg_8], rbp
0x10082c546  mov     ebp, edx
0x10082c548  mov     [rsp+38h+arg_18], r14
0x10082c54d  xor     r14d, r14d
0x10082c550  cmp     eax, 6; switch 7 cases
0x10082c553  ja      def_10082C56B; jumptable 000000010082C56B default case
0x10082c559  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10082c560  mov     r8d, ds:(jpt_10082C56B - 100400000h)[rcx+rax*4]
0x10082c568  add     r8, rcx
0x10082c56b  jmp     r8; switch jump
0x10082c56e  mov     rcx, [rdi+10h]; jumptable 000000010082C56B case 3
0x10082c572  test    rcx, rcx
0x10082c575  jz      loc_10082C665; jumptable 000000010082C56B cases 0,4-6
0x10082c57b  mov     edx, 2
0x10082c580  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10082c586  mov     [rdi+10h], r14
0x10082c58a  jmp     loc_10082C665; jumptable 000000010082C56B cases 0,4-6
0x10082c58f  mov     rcx, [rdi+10h]; jumptable 000000010082C56B case 2
0x10082c593  test    rcx, rcx
0x10082c596  jz      loc_10082C665; jumptable 000000010082C56B cases 0,4-6
0x10082c59c  mov     eax, [rcx+1Ch]
0x10082c59f  mov     rbx, [rcx+10h]
0x10082c5a3  test    eax, eax
0x10082c5a5  jz      short loc_10082C5E1
0x10082c5a7  mov     [rsp+38h+arg_10], rsi
0x10082c5ac  mov     esi, eax
0x10082c5ae  xchg    ax, ax
0x10082c5b0  mov     rcx, [rbx]; this
0x10082c5b3  test    rcx, rcx
0x10082c5b6  jz      short loc_10082C5C5
0x10082c5b8  mov     edx, 1; unsigned int
0x10082c5bd  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x10082c5c2  mov     [rbx], r14
0x10082c5c5  add     rbx, 8
0x10082c5c9  sub     rsi, 1
0x10082c5cd  jnz     short loc_10082C5B0
0x10082c5cf  mov     rsi, [rsp+38h+arg_10]
0x10082c5d4  mov     rcx, [rdi+10h]
0x10082c5d8  test    rcx, rcx
0x10082c5db  jz      loc_10082C665; jumptable 000000010082C56B cases 0,4-6
0x10082c5e1  mov     rax, [rcx]
0x10082c5e4  mov     edx, 1
0x10082c5e9  call    qword ptr [rax]
0x10082c5eb  mov     [rdi+10h], r14
0x10082c5ef  jmp     short loc_10082C665; jumptable 000000010082C56B cases 0,4-6
0x10082c5f1  mov     rcx, [rdi+10h]; jumptable 000000010082C56B case 1
0x10082c5f5  test    rcx, rcx
0x10082c5f8  jz      short loc_10082C665; jumptable 000000010082C56B cases 0,4-6
0x10082c5fa  mov     rbx, [rcx+8]
0x10082c5fe  test    rbx, rbx
0x10082c601  jz      short loc_10082C5E1
0x10082c603  mov     rcx, [rbx]
0x10082c606  test    rcx, rcx
0x10082c609  jz      short loc_10082C619
0x10082c60b  mov     edx, 2
0x10082c610  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10082c616  mov     [rbx], r14
0x10082c619  mov     rcx, [rbx+8]; this
0x10082c61d  test    rcx, rcx
0x10082c620  jz      short loc_10082C62C
0x10082c622  mov     edx, 1; unsigned int
0x10082c627  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x10082c62c  mov     [rbx+8], r14
0x10082c630  mov     rbx, [rbx+10h]
0x10082c634  test    rbx, rbx
0x10082c637  jnz     short loc_10082C603
0x10082c639  jmp     short loc_10082C5D4
0x10082c63b  mov     r9d, 66h ; 'f'; jumptable 000000010082C56B default case
0x10082c641  lea     rax, aInvalidSwitchV; "Invalid switch value"
0x10082c648  lea     r8, aSqlNtdbmsStore_5; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x10082c64f  mov     [rsp+38h+var_18], rax
0x10082c654  lea     rdx, aFalse_0; "FALSE"
0x10082c65b  lea     ecx, [r9-65h]
0x10082c65f  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10082c665  mov     rbx, [rsp+38h+arg_0]; jumptable 000000010082C56B cases 0,4-6
0x10082c66a  test    bpl, 1
0x10082c66e  mov     rbp, [rsp+38h+arg_8]
0x10082c673  mov     [rdi+18h], r14
0x10082c677  mov     [rdi], r14d
0x10082c67a  mov     r14, [rsp+38h+arg_18]
0x10082c67f  jz      short loc_10082C68F
0x10082c681  mov     edx, 20h ; ' '
0x10082c686  mov     rcx, rdi
0x10082c689  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10082c68f  mov     rax, rdi
0x10082c692  add     rsp, 30h
0x10082c696  pop     rdi
0x10082c697  retn
```
