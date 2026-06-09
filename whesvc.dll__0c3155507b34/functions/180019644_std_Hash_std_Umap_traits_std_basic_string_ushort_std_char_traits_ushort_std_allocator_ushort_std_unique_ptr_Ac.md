# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>,void *> *,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>,void *> * const)

- ea: `0x180019644`
- end: `0x180019887`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `579`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180019890`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x180019644`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001970b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001981f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001970b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001981f`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  __int64 v8; // r15
  _QWORD *v9; // rcx
  _QWORD *v10; // rsi
  __int64 v11; // r9
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // r14
  _QWORD *v17; // r13
  char **v18; // rax
  HMODULE *v19; // r12
  _QWORD *v20; // r10
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  unsigned __int64 v24; // r8
  __int64 v25; // rdx
  unsigned __int64 v26; // r9
  __int64 v27; // rax
  char **v28; // r13
  HMODULE *v29; // rbp
  _QWORD *v30; // [rsp+20h] [rbp-58h]
  _QWORD *v31; // [rsp+28h] [rbp-50h]
  _QWORD *v33; // [rsp+88h] [rbp+10h]
  char **v34; // [rsp+90h] [rbp+18h]
  char **v35; // [rsp+90h] [rbp+18h]
  void *v36; // [rsp+98h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = (_QWORD *)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = a2 + 2;
    v10 = (_QWORD *)a2[1];
    v11 = a2[4];
    v33 = v6;
    if ( a2[5] > 7u )
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
    v17 = *(_QWORD **)(v8 + 16 * (v13 & a1[6]));
    v30 = *(_QWORD **)(v8 + 16 * (v13 & a1[6]) + 8);
    while ( 1 )
    {
      v31 = v7;
      v18 = (char **)(v7 + 2);
      v36 = v7;
      v7 = (_QWORD *)*v7;
      v34 = v18;
      v19 = (HMODULE *)v18[4];
      if ( v19 )
      {
        if ( *v19 )
          FreeLibrary(*v19);
        operator delete(v19);
        v18 = v34;
      }
      std::wstring::~wstring(v18);
      operator delete(v36);
      v20 = a1;
      --a1[2];
      if ( v31 == v30 )
        break;
      if ( v7 == a3 )
      {
        if ( v17 == a2 )
LABEL_14:
          *(_QWORD *)(v8 + 8 * v16) = v7;
        goto LABEL_15;
      }
    }
    if ( v17 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v16) = v33;
      v22 = v33;
    }
    else
    {
      v22 = v10;
    }
    while ( 1 )
    {
      *(_QWORD *)(v8 + 8 * v16 + 8) = v22;
      if ( v7 == a3 )
        break;
      v23 = v7 + 2;
      if ( v7[5] > 7u )
        v23 = (_QWORD *)*v23;
      v24 = 0;
      v25 = 0xCBF29CE484222325uLL;
      v26 = 2LL * v7[4];
      if ( v26 )
      {
        do
        {
          v27 = *((unsigned __int8 *)v23 + v24++);
          v25 = 0x100000001B3LL * (v27 ^ v25);
        }
        while ( v24 < v26 );
        v20 = a1;
      }
      v16 = 2 * (v25 & v20[6]);
      v35 = *(char ***)(v8 + 16 * (v25 & v20[6]) + 8);
      while ( 1 )
      {
        v28 = (char **)v7;
        v7 = (_QWORD *)*v7;
        v29 = (HMODULE *)v28[6];
        if ( v29 )
        {
          if ( *v29 )
            FreeLibrary(*v29);
          operator delete(v29);
        }
        std::wstring::~wstring(v28 + 2);
        operator delete(v28);
        v20 = a1;
        --a1[2];
        if ( v28 == v35 )
          break;
        if ( v7 == a3 )
          goto LABEL_14;
      }
      v22 = v33;
      *(_QWORD *)(v8 + 8 * v16) = v33;
    }
LABEL_15:
    *v10 = v7;
    v7[1] = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x180019644  mov     [rsp+arg_0], rcx
0x180019649  push    rbx
0x18001964a  push    rbp
0x18001964b  push    rsi
0x18001964c  push    rdi
0x18001964d  push    r12
0x18001964f  push    r13
0x180019651  push    r14
0x180019653  push    r15
0x180019655  sub     rsp, 38h
0x180019659  mov     rdi, r8
0x18001965c  mov     rbp, rdx
0x18001965f  mov     r10, rcx
0x180019662  cmp     rdx, r8
0x180019665  jz      loc_180019771
0x18001966b  mov     rax, [rcx+8]
0x18001966f  mov     rbx, rdx
0x180019672  mov     r15, [rcx+18h]
0x180019676  lea     rcx, [rdx+10h]
0x18001967a  cmp     qword ptr [rcx+18h], 7
0x18001967f  mov     rsi, [rdx+8]
0x180019683  mov     r9, [rcx+10h]
0x180019687  mov     [rsp+78h+arg_8], rax
0x18001968f  jbe     short loc_180019694
0x180019691  mov     rcx, [rcx]
0x180019694  xor     edx, edx
0x180019696  mov     r8, 0CBF29CE484222325h
0x1800196a0  mov     r11, 100000001B3h
0x1800196aa  add     r9, r9
0x1800196ad  jz      short loc_1800196C2
0x1800196af  movzx   eax, byte ptr [rcx+rdx]
0x1800196b3  inc     rdx
0x1800196b6  xor     r8, rax
0x1800196b9  imul    r8, r11
0x1800196bd  cmp     rdx, r9
0x1800196c0  jb      short loc_1800196AF
0x1800196c2  mov     r14, [r10+30h]
0x1800196c6  and     r14, r8
0x1800196c9  add     r14, r14
0x1800196cc  mov     rax, [r15+r14*8+8]
0x1800196d1  mov     r13, [r15+r14*8]
0x1800196d5  mov     [rsp+78h+var_58], rax
0x1800196da  mov     rax, rbx
0x1800196dd  mov     [rsp+78h+var_50], rbx
0x1800196e2  add     rax, 10h
0x1800196e6  mov     [rsp+78h+arg_18], rbx
0x1800196ee  mov     rbx, [rbx]
0x1800196f1  mov     [rsp+78h+arg_10], rax
0x1800196f9  mov     r12, [rax+20h]
0x1800196fd  test    r12, r12
0x180019700  jz      short loc_180019726
0x180019702  mov     rcx, [r12]; hLibModule
0x180019706  test    rcx, rcx
0x180019709  jz      short loc_180019711
0x18001970b  call    cs:__imp_FreeLibrary
0x180019711  mov     edx, 10h; unsigned __int64
0x180019716  mov     rcx, r12; void *
0x180019719  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001971e  mov     rax, [rsp+78h+arg_10]
0x180019726  mov     rcx, rax
0x180019729  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001972e  mov     rcx, [rsp+78h+arg_18]; void *
0x180019736  mov     edx, 38h ; '8'; unsigned __int64
0x18001973b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019740  mov     r10, [rsp+78h+arg_0]
0x180019748  mov     rax, [rsp+78h+var_58]
0x18001974d  dec     qword ptr [r10+10h]
0x180019751  cmp     [rsp+78h+var_50], rax
0x180019756  jz      short loc_180019785
0x180019758  cmp     rbx, rdi
0x18001975b  jnz     loc_1800196DA
0x180019761  cmp     r13, rbp
0x180019764  jnz     short loc_18001976A
0x180019766  mov     [r15+r14*8], rbx
0x18001976a  mov     [rsi], rbx
0x18001976d  mov     [rbx+8], rsi
0x180019771  mov     rax, rdi
0x180019774  add     rsp, 38h
0x180019778  pop     r15
0x18001977a  pop     r14
0x18001977c  pop     r13
0x18001977e  pop     r12
0x180019780  pop     rdi
0x180019781  pop     rsi
0x180019782  pop     rbp
0x180019783  pop     rbx
0x180019784  retn
0x180019785  cmp     r13, rbp
0x180019788  jnz     short loc_18001979E
0x18001978a  mov     rdx, [rsp+78h+arg_8]
0x180019792  mov     [r15+r14*8], rdx
0x180019796  mov     rax, rdx
0x180019799  jmp     loc_180019874
0x18001979e  mov     rax, rsi
0x1800197a1  jmp     loc_180019874
0x1800197a6  lea     rcx, [rbx+10h]
0x1800197aa  cmp     qword ptr [rcx+18h], 7
0x1800197af  mov     r9, [rcx+10h]
0x1800197b3  jbe     short loc_1800197B8
0x1800197b5  mov     rcx, [rcx]
0x1800197b8  xor     r8d, r8d
0x1800197bb  mov     rdx, 0CBF29CE484222325h
0x1800197c5  add     r9, r9
0x1800197c8  jz      short loc_1800197F0
0x1800197ca  mov     r10, 100000001B3h
0x1800197d4  movzx   eax, byte ptr [rcx+r8]
0x1800197d9  inc     r8
0x1800197dc  xor     rdx, rax
0x1800197df  imul    rdx, r10
0x1800197e3  cmp     r8, r9
0x1800197e6  jb      short loc_1800197D4
0x1800197e8  mov     r10, [rsp+78h+arg_0]
0x1800197f0  mov     r14, [r10+30h]
0x1800197f4  and     r14, rdx
0x1800197f7  add     r14, r14
0x1800197fa  mov     rax, [r15+r14*8+8]
0x1800197ff  mov     [rsp+78h+arg_10], rax
0x180019807  mov     r13, rbx
0x18001980a  mov     rbx, [rbx]
0x18001980d  mov     rbp, [r13+30h]
0x180019811  test    rbp, rbp
0x180019814  jz      short loc_180019832
0x180019816  mov     rcx, [rbp+0]; hLibModule
0x18001981a  test    rcx, rcx
0x18001981d  jz      short loc_180019825
0x18001981f  call    cs:__imp_FreeLibrary
0x180019825  mov     edx, 10h; unsigned __int64
0x18001982a  mov     rcx, rbp; void *
0x18001982d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019832  lea     rcx, [r13+10h]
0x180019836  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001983b  mov     edx, 38h ; '8'; unsigned __int64
0x180019840  mov     rcx, r13; void *
0x180019843  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019848  mov     r10, [rsp+78h+arg_0]
0x180019850  dec     qword ptr [r10+10h]
0x180019854  cmp     r13, [rsp+78h+arg_10]
0x18001985c  jz      short loc_180019868
0x18001985e  cmp     rbx, rdi
0x180019861  jnz     short loc_180019807
0x180019863  jmp     loc_180019766
0x180019868  mov     rax, [rsp+78h+arg_8]
0x180019870  mov     [r15+r14*8], rax
0x180019874  mov     [r15+r14*8+8], rax
0x180019879  cmp     rbx, rdi
0x18001987c  jnz     loc_1800197A6
0x180019882  jmp     loc_18001976A
```
