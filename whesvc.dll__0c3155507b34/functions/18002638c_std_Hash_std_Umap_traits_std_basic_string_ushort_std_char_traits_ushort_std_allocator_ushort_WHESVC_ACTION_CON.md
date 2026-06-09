# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>,void *> *,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>,void *> * const)

- ea: `0x18002638c`
- end: `0x18002655d`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `465`
- prototype: `char *__fastcall(_QWORD *, char *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180026088`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x18002638c`

## pseudocode

```c
char *__fastcall std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        char *a2,
        char *a3)
{
  char **v6; // rax
  char *v7; // rsi
  __int64 v8; // r12
  _QWORD *v9; // rcx
  char **v10; // r14
  __int64 v11; // r10
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // r10
  __int64 v15; // rax
  __int64 v16; // r13
  char **v17; // rbx
  _QWORD *v18; // r9
  char **v19; // rax
  _QWORD *v20; // rcx
  unsigned __int64 v21; // r8
  __int64 v22; // rdx
  unsigned __int64 v23; // r10
  __int64 v24; // rax
  __int64 v25; // r15
  char **v26; // r13
  char **v27; // rbx
  char *v30; // [rsp+78h] [rbp+10h]
  char **v31; // [rsp+80h] [rbp+18h]
  char **v32; // [rsp+88h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = (char **)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = a2 + 16;
    v10 = (char **)*((_QWORD *)a2 + 1);
    v11 = *((_QWORD *)a2 + 4);
    v31 = v6;
    if ( *((_QWORD *)a2 + 5) > 7u )
      v9 = (_QWORD *)*v9;
    v12 = 0;
    v13 = 0xCBF29CE484222325uLL;
    v14 = 2 * v11;
    if ( v14 )
    {
      do
      {
        v15 = *((unsigned __int8 *)v9 + v12++);
        v13 = 0x100000001B3LL * (v15 ^ v13);
      }
      while ( v12 < v14 );
    }
    v16 = 2 * (v13 & a1[6]);
    v30 = *(char **)(v8 + 16 * (v13 & a1[6]));
    v32 = *(char ***)(v8 + 16 * (v13 & a1[6]) + 8);
    while ( 1 )
    {
      v17 = (char **)v7;
      v7 = *(char **)v7;
      std::wstring::~wstring(v17 + 2);
      operator delete(v17);
      v18 = a1;
      --a1[2];
      if ( v17 == v32 )
        break;
      if ( v7 == a3 )
      {
        if ( v30 == a2 )
          *(_QWORD *)(v8 + 8 * v16) = v7;
        goto LABEL_24;
      }
    }
    if ( v30 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v16) = v31;
      v19 = v31;
    }
    else
    {
      v19 = v10;
    }
    *(_QWORD *)(v8 + 8 * v16 + 8) = v19;
    while ( v7 != a3 )
    {
      v20 = v7 + 16;
      if ( *((_QWORD *)v7 + 5) > 7u )
        v20 = (_QWORD *)*v20;
      v21 = 0;
      v22 = 0xCBF29CE484222325uLL;
      v23 = 2LL * *((_QWORD *)v7 + 4);
      if ( v23 )
      {
        do
        {
          v24 = *((unsigned __int8 *)v20 + v21++);
          v22 = 0x100000001B3LL * (v24 ^ v22);
        }
        while ( v21 < v23 );
        v18 = a1;
      }
      v25 = 2 * (v22 & v18[6]);
      v26 = *(char ***)(v8 + 16 * (v22 & v18[6]) + 8);
      while ( 1 )
      {
        v27 = (char **)v7;
        v7 = *(char **)v7;
        std::wstring::~wstring(v27 + 2);
        operator delete(v27);
        v18 = a1;
        --a1[2];
        if ( v27 == v26 )
          break;
        if ( v7 == a3 )
        {
          *(_QWORD *)(v8 + 8 * v25) = v7;
          goto LABEL_24;
        }
      }
      *(_QWORD *)(v8 + 8 * v25) = v31;
      *(_QWORD *)(v8 + 8 * v25 + 8) = v31;
    }
LABEL_24:
    *v10 = v7;
    *((_QWORD *)v7 + 1) = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x18002638c  mov     [rsp+arg_0], rcx
0x180026391  push    rbx
0x180026392  push    rbp
0x180026393  push    rsi
0x180026394  push    rdi
0x180026395  push    r12
0x180026397  push    r13
0x180026399  push    r14
0x18002639b  push    r15
0x18002639d  sub     rsp, 28h
0x1800263a1  mov     rbp, r8
0x1800263a4  mov     r15, rdx
0x1800263a7  mov     r9, rcx
0x1800263aa  cmp     rdx, r8
0x1800263ad  jz      loc_18002652D
0x1800263b3  mov     rax, [rcx+8]
0x1800263b7  mov     rsi, rdx
0x1800263ba  mov     r12, [rcx+18h]
0x1800263be  lea     rcx, [rdx+10h]
0x1800263c2  cmp     qword ptr [rcx+18h], 7
0x1800263c7  mov     r14, [rdx+8]
0x1800263cb  mov     r10, [rcx+10h]
0x1800263cf  mov     [rsp+68h+arg_10], rax
0x1800263d7  jbe     short loc_1800263DC
0x1800263d9  mov     rcx, [rcx]
0x1800263dc  xor     edx, edx
0x1800263de  mov     r8, 0CBF29CE484222325h
0x1800263e8  mov     r11, 100000001B3h
0x1800263f2  add     r10, r10
0x1800263f5  jz      short loc_18002640A
0x1800263f7  movzx   eax, byte ptr [rcx+rdx]
0x1800263fb  inc     rdx
0x1800263fe  xor     r8, rax
0x180026401  imul    r8, r11
0x180026405  cmp     rdx, r10
0x180026408  jb      short loc_1800263F7
0x18002640a  mov     r13, [r9+30h]
0x18002640e  and     r13, r8
0x180026411  add     r13, r13
0x180026414  mov     rax, [r12+r13*8]
0x180026418  mov     [rsp+68h+arg_8], rax
0x18002641d  mov     rax, [r12+r13*8+8]
0x180026422  mov     [rsp+68h+arg_18], rax
0x18002642a  mov     rbx, rsi
0x18002642d  mov     rdi, rsi
0x180026430  mov     rsi, [rsi]
0x180026433  lea     rcx, [rbx+10h]
0x180026437  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002643c  mov     edx, 48h ; 'H'; unsigned __int64
0x180026441  mov     rcx, rbx; void *
0x180026444  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026449  mov     r9, [rsp+68h+arg_0]
0x18002644e  dec     qword ptr [r9+10h]
0x180026452  cmp     rbx, [rsp+68h+arg_18]
0x18002645a  jz      short loc_180026475
0x18002645c  cmp     rsi, rbp
0x18002645f  jnz     short loc_18002642A
0x180026461  cmp     [rsp+68h+arg_8], r15
0x180026466  jnz     loc_180026526
0x18002646c  mov     [r12+r13*8], rsi
0x180026470  jmp     loc_180026526
0x180026475  cmp     [rsp+68h+arg_8], r15
0x18002647a  jnz     short loc_18002648D
0x18002647c  mov     rdx, [rsp+68h+arg_10]
0x180026484  mov     [r12+r13*8], rdx
0x180026488  mov     rax, rdx
0x18002648b  jmp     short loc_180026490
0x18002648d  mov     rax, r14
0x180026490  mov     [r12+r13*8+8], rax
0x180026495  jmp     loc_180026552
0x18002649a  lea     rcx, [rsi+10h]
0x18002649e  cmp     qword ptr [rcx+18h], 7
0x1800264a3  mov     r10, [rcx+10h]
0x1800264a7  jbe     short loc_1800264AC
0x1800264a9  mov     rcx, [rcx]
0x1800264ac  xor     r8d, r8d
0x1800264af  mov     rdx, 0CBF29CE484222325h
0x1800264b9  add     r10, r10
0x1800264bc  jz      short loc_1800264E1
0x1800264be  mov     r9, 100000001B3h
0x1800264c8  movzx   eax, byte ptr [rcx+r8]
0x1800264cd  inc     r8
0x1800264d0  xor     rdx, rax
0x1800264d3  imul    rdx, r9
0x1800264d7  cmp     r8, r10
0x1800264da  jb      short loc_1800264C8
0x1800264dc  mov     r9, [rsp+68h+arg_0]
0x1800264e1  mov     r15, [r9+30h]
0x1800264e5  and     r15, rdx
0x1800264e8  add     r15, r15
0x1800264eb  mov     r13, [r12+r15*8+8]
0x1800264f0  mov     rbx, rsi
0x1800264f3  mov     rdi, rsi
0x1800264f6  mov     rsi, [rsi]
0x1800264f9  lea     rcx, [rbx+10h]
0x1800264fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026502  mov     edx, 48h ; 'H'; unsigned __int64
0x180026507  mov     rcx, rbx; void *
0x18002650a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002650f  mov     r9, [rsp+68h+arg_0]
0x180026514  dec     qword ptr [r9+10h]
0x180026518  cmp     rbx, r13
0x18002651b  jz      short loc_180026541
0x18002651d  cmp     rsi, rbp
0x180026520  jnz     short loc_1800264F0
0x180026522  mov     [r12+r15*8], rsi
0x180026526  mov     [r14], rsi
0x180026529  mov     [rsi+8], r14
0x18002652d  mov     rax, rbp
0x180026530  add     rsp, 28h
0x180026534  pop     r15
0x180026536  pop     r14
0x180026538  pop     r13
0x18002653a  pop     r12
0x18002653c  pop     rdi
0x18002653d  pop     rsi
0x18002653e  pop     rbp
0x18002653f  pop     rbx
0x180026540  retn
0x180026541  mov     rax, [rsp+68h+arg_10]
0x180026549  mov     [r12+r15*8], rax
0x18002654d  mov     [r12+r15*8+8], rax
0x180026552  cmp     rsi, rbp
0x180026555  jnz     loc_18002649A
0x18002655b  jmp     short loc_180026526
```
