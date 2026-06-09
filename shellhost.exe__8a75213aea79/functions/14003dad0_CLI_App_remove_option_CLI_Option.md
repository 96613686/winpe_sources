# CLI::App::remove_option(CLI::Option *)

- ea: `0x14003dad0`
- end: `0x14003dc99`
- name: `?remove_option@App@CLI@@QEAA_NPEAVOption@2@@Z`
- size: `457`
- prototype: `bool __fastcall(CLI::App *__hidden this, struct CLI::Option *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400162d0`
- `0x140020320`
- `0x14003eb20`

## callees

- `0x14000fab8`
- `0x14001fd10`
- `0x14002c800`
- `0x14003dad0`

## pseudocode

```c
char __fastcall CLI::App::remove_option(CLI::App *this, struct CLI::Option *a2)
{
  __int64 v2; // rdi
  __int64 i; // rbp
  _QWORD *v6; // r8
  _QWORD *v7; // rdx
  __int64 **v8; // rcx
  __int64 j; // rax
  __int64 *k; // rcx
  void *v11; // rax
  _QWORD *v12; // r8
  _QWORD *v13; // rdx
  __int64 **v14; // rcx
  __int64 m; // rax
  __int64 *n; // rcx
  void *v17; // rax
  struct CLI::Option **v18; // rax
  struct CLI::Option **v19; // r8
  char v21; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 39);
  for ( i = *((_QWORD *)this + 40); v2 != i; v2 += 8 )
  {
    v6 = *(_QWORD **)(*(_QWORD *)v2 + 464LL);
    v7 = (_QWORD *)*v6;
    if ( (_QWORD *)*v6 != v6 )
    {
      while ( (struct CLI::Option *)v7[4] != a2 )
      {
        v8 = (__int64 **)v7[2];
        if ( *((_BYTE *)v8 + 25) )
        {
          for ( j = v7[1]; !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 8) )
          {
            if ( v7 != *(_QWORD **)(j + 16) )
              break;
            v7 = (_QWORD *)j;
          }
          v7 = (_QWORD *)j;
        }
        else
        {
          v7 = (_QWORD *)v7[2];
          for ( k = *v8; !*((_BYTE *)k + 25); k = (__int64 *)*k )
            v7 = k;
        }
        if ( v7 == v6 )
          goto LABEL_14;
      }
      v11 = (void *)std::_Tree_val<std::_Tree_simple_types<CLI::Option *>>::_Extract(*(_QWORD *)v2 + 464LL);
      operator delete(v11);
    }
LABEL_14:
    v12 = *(_QWORD **)(*(_QWORD *)v2 + 480LL);
    v13 = (_QWORD *)*v12;
    if ( (_QWORD *)*v12 != v12 )
    {
      while ( (struct CLI::Option *)v13[4] != a2 )
      {
        v14 = (__int64 **)v13[2];
        if ( *((_BYTE *)v14 + 25) )
        {
          for ( m = v13[1]; !*(_BYTE *)(m + 25); m = *(_QWORD *)(m + 8) )
          {
            if ( v13 != *(_QWORD **)(m + 16) )
              break;
            v13 = (_QWORD *)m;
          }
          v13 = (_QWORD *)m;
        }
        else
        {
          v13 = (_QWORD *)v13[2];
          for ( n = *v14; !*((_BYTE *)n + 25); n = (__int64 *)*n )
            v13 = n;
        }
        if ( v13 == v12 )
          goto LABEL_26;
      }
      v17 = (void *)std::_Tree_val<std::_Tree_simple_types<CLI::Option *>>::_Extract(*(_QWORD *)v2 + 480LL);
      operator delete(v17);
    }
LABEL_26:
    ;
  }
  if ( *((struct CLI::Option **)this + 66) == a2 )
    *((_QWORD *)this + 66) = 0;
  if ( *((struct CLI::Option **)this + 67) == a2 )
    *((_QWORD *)this + 67) = 0;
  v18 = (struct CLI::Option **)*((_QWORD *)this + 40);
  v19 = (struct CLI::Option **)*((_QWORD *)this + 39);
  if ( v19 == v18 )
    return 0;
  while ( *v19 != a2 )
  {
    if ( ++v19 == v18 )
      return 0;
  }
  std::vector<std::unique_ptr<CLI::Option>>::erase((char *)this + 312, &v21);
  return 1;
}

```

## disassembly

```asm
0x14003dad0  mov     [rsp+arg_8], rbx
0x14003dad5  mov     [rsp+arg_10], rbp
0x14003dada  push    rsi
0x14003dadb  push    rdi
0x14003dadc  push    r14
0x14003dade  sub     rsp, 20h
0x14003dae2  mov     rdi, [rcx+138h]
0x14003dae9  mov     rbx, rdx
0x14003daec  mov     rbp, [rcx+140h]
0x14003daf3  mov     rsi, rcx
0x14003daf6  cmp     rdi, rbp
0x14003daf9  jz      loc_14003DC2C
0x14003daff  nop
0x14003db00  mov     r9, [rdi]
0x14003db03  mov     r8, [r9+1D0h]
0x14003db0a  mov     rdx, [r8]
0x14003db0d  cmp     rdx, r8
0x14003db10  jz      short loc_14003DB8F
0x14003db12  cmp     [rdx+20h], rbx
0x14003db16  jz      short loc_14003DB76
0x14003db18  mov     rcx, [rdx+10h]
0x14003db1c  cmp     byte ptr [rcx+19h], 0
0x14003db20  jz      short loc_14003DB48
0x14003db22  mov     rax, [rdx+8]
0x14003db26  cmp     byte ptr [rax+19h], 0
0x14003db2a  jnz     short loc_14003DB43
0x14003db2c  nop     dword ptr [rax+00h]
0x14003db30  cmp     rdx, [rax+10h]
0x14003db34  jnz     short loc_14003DB43
0x14003db36  mov     rdx, rax
0x14003db39  mov     rax, [rax+8]
0x14003db3d  cmp     byte ptr [rax+19h], 0
0x14003db41  jz      short loc_14003DB30
0x14003db43  mov     rdx, rax
0x14003db46  jmp     short loc_14003DB6F
0x14003db48  mov     rdx, rcx
0x14003db4b  mov     rcx, [rcx]
0x14003db4e  cmp     byte ptr [rcx+19h], 0
0x14003db52  jnz     short loc_14003DB6F
0x14003db54  nop     dword ptr [rax+00h]
0x14003db58  nop     dword ptr [rax+rax+00000000h]
0x14003db60  mov     rax, [rcx]
0x14003db63  mov     rdx, rcx
0x14003db66  mov     rcx, rax
0x14003db69  cmp     byte ptr [rax+19h], 0
0x14003db6d  jz      short loc_14003DB60
0x14003db6f  cmp     rdx, r8
0x14003db72  jnz     short loc_14003DB12
0x14003db74  jmp     short loc_14003DB8F
0x14003db76  lea     rcx, [r9+1D0h]
0x14003db7d  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@PEAVOption@CLI@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVOption@CLI@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVOption@CLI@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<CLI::Option *>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CLI::Option *>>,std::_Iterator_base0>)
0x14003db82  mov     edx, 28h ; '('; unsigned __int64
0x14003db87  mov     rcx, rax; void *
0x14003db8a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003db8f  mov     r9, [rdi]
0x14003db92  mov     r8, [r9+1E0h]
0x14003db99  mov     rdx, [r8]
0x14003db9c  cmp     rdx, r8
0x14003db9f  jz      short loc_14003DC1F
0x14003dba1  cmp     [rdx+20h], rbx
0x14003dba5  jz      short loc_14003DC06
0x14003dba7  mov     rcx, [rdx+10h]
0x14003dbab  cmp     byte ptr [rcx+19h], 0
0x14003dbaf  jz      short loc_14003DBD8
0x14003dbb1  mov     rax, [rdx+8]
0x14003dbb5  cmp     byte ptr [rax+19h], 0
0x14003dbb9  jnz     short loc_14003DBD3
0x14003dbbb  nop     dword ptr [rax+rax+00h]
0x14003dbc0  cmp     rdx, [rax+10h]
0x14003dbc4  jnz     short loc_14003DBD3
0x14003dbc6  mov     rdx, rax
0x14003dbc9  mov     rax, [rax+8]
0x14003dbcd  cmp     byte ptr [rax+19h], 0
0x14003dbd1  jz      short loc_14003DBC0
0x14003dbd3  mov     rdx, rax
0x14003dbd6  jmp     short loc_14003DBFF
0x14003dbd8  mov     rdx, rcx
0x14003dbdb  mov     rcx, [rcx]
0x14003dbde  cmp     byte ptr [rcx+19h], 0
0x14003dbe2  jnz     short loc_14003DBFF
0x14003dbe4  nop     dword ptr [rax+00h]
0x14003dbe8  nop     dword ptr [rax+rax+00000000h]
0x14003dbf0  mov     rax, [rcx]
0x14003dbf3  mov     rdx, rcx
0x14003dbf6  mov     rcx, rax
0x14003dbf9  cmp     byte ptr [rax+19h], 0
0x14003dbfd  jz      short loc_14003DBF0
0x14003dbff  cmp     rdx, r8
0x14003dc02  jnz     short loc_14003DBA1
0x14003dc04  jmp     short loc_14003DC1F
0x14003dc06  lea     rcx, [r9+1E0h]
0x14003dc0d  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@PEAVOption@CLI@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVOption@CLI@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVOption@CLI@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<CLI::Option *>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CLI::Option *>>,std::_Iterator_base0>)
0x14003dc12  mov     edx, 28h ; '('; unsigned __int64
0x14003dc17  mov     rcx, rax; void *
0x14003dc1a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003dc1f  add     rdi, 8
0x14003dc23  cmp     rdi, rbp
0x14003dc26  jnz     loc_14003DB00
0x14003dc2c  xor     eax, eax
0x14003dc2e  cmp     [rsi+210h], rbx
0x14003dc35  jnz     short loc_14003DC3E
0x14003dc37  mov     [rsi+210h], rax
0x14003dc3e  cmp     [rsi+218h], rbx
0x14003dc45  jnz     short loc_14003DC4E
0x14003dc47  mov     [rsi+218h], rax
0x14003dc4e  mov     rax, [rsi+140h]
0x14003dc55  mov     r8, [rsi+138h]
0x14003dc5c  cmp     r8, rax
0x14003dc5f  jz      short loc_14003DC6F
0x14003dc61  cmp     [r8], rbx
0x14003dc64  jz      short loc_14003DC84
0x14003dc66  add     r8, 8
0x14003dc6a  cmp     r8, rax
0x14003dc6d  jnz     short loc_14003DC61
0x14003dc6f  xor     al, al
0x14003dc71  mov     rbx, [rsp+38h+arg_8]
0x14003dc76  mov     rbp, [rsp+38h+arg_10]
0x14003dc7b  add     rsp, 20h
0x14003dc7f  pop     r14
0x14003dc81  pop     rdi
0x14003dc82  pop     rsi
0x14003dc83  retn
0x14003dc84  lea     rdx, [rsp+38h+arg_0]
0x14003dc89  lea     rcx, [rsi+138h]
0x14003dc90  call    ?erase@?$vector@V?$unique_ptr@VOption@CLI@@U?$default_delete@VOption@CLI@@@std@@@std@@V?$allocator@V?$unique_ptr@VOption@CLI@@U?$default_delete@VOption@CLI@@@std@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VOption@CLI@@U?$default_delete@VOption@CLI@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VOption@CLI@@U?$default_delete@VOption@CLI@@@std@@@std@@@std@@@std@@@2@@Z; std::vector<std::unique_ptr<CLI::Option>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::unique_ptr<CLI::Option>>>>)
0x14003dc95  mov     al, 1
0x14003dc97  jmp     short loc_14003DC71
```
