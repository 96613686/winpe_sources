# GenericTable<HTTP2ServerCookie,0,&DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::SwitchToTree(void)

- ea: `0x180019d0c`
- end: `0x180019dfe`
- name: `?SwitchToTree@?$GenericTable@VHTTP2ServerCookie@@$0A@$1??$DefaultCompareKeys@VHTTP2Cookie@@@@YAHAEBVHTTP2Cookie@@0@Z@@AEAAXXZ`
- size: `242`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004298`
- `0x18000dfe8`

## callees

- `0x180019d0c`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x180019d92`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180019d92`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180019ddd`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180019ddd`

## pseudocode

```c
_QWORD *__fastcall GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::SwitchToTree(
        PRTL_AVL_TABLE Table)
{
  PRTL_AVL_TABLE *i; // rax
  struct _RTL_BALANCED_LINKS *v3; // rcx
  __int64 v4; // rcx
  struct _RTL_BALANCED_LINKS *v5; // rdx
  _QWORD *result; // rax
  __int64 v7; // rax
  _QWORD v8[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 NewElement; // [rsp+50h] [rbp+10h] BYREF

  v8[1] = v8;
  for ( i = (PRTL_AVL_TABLE *)v8; ; *(_QWORD *)(v4 + 8) = i )
  {
    v8[0] = i;
    i = (PRTL_AVL_TABLE *)Table->BalancedRoot.Parent;
    if ( (PRTL_AVL_TABLE)Table->BalancedRoot.Parent == Table )
      break;
    if ( i[1] != Table
      || (v3 = (struct _RTL_BALANCED_LINKS *)*i, (PRTL_AVL_TABLE *)(*i)->BalancedRoot.LeftChild != i)
      || (Table->BalancedRoot.Parent = v3,
          v3->LeftChild = &Table->BalancedRoot,
          v4 = v8[0],
          *(_QWORD **)(v8[0] + 8LL) != v8) )
    {
LABEL_12:
      __fastfail(3u);
    }
    *i = (PRTL_AVL_TABLE)v8[0];
    i[1] = (PRTL_AVL_TABLE)v8;
  }
  RtlInitializeGenericTableAvl(
    Table,
    GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::Compare,
    GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::Allocate,
    HTTP2Channel::PingTrafficSentNotify,
    Table);
  while ( 1 )
  {
    v5 = (struct _RTL_BALANCED_LINKS *)v8[0];
    result = v8;
    if ( (_QWORD *)v8[0] == v8 )
      break;
    if ( *(_QWORD **)(v8[0] + 8LL) != v8 )
      goto LABEL_12;
    v7 = *(_QWORD *)v8[0];
    if ( *(_QWORD *)(*(_QWORD *)v8[0] + 8LL) != v8[0] )
      goto LABEL_12;
    v8[0] = *(_QWORD *)v8[0];
    *(_QWORD *)(v7 + 8) = v8;
    Table[1].BalancedRoot.Parent = v5;
    NewElement = 0;
    RtlInsertElementGenericTableAvl(Table, &v5[1], 0x10u, &NewElement);
  }
  LODWORD(Table[1].BalancedRoot.RightChild) = 1;
  return result;
}

```

## disassembly

```asm
0x180019d0c  mov     [rsp-8+arg_8], rbx
0x180019d11  push    rbp
0x180019d12  mov     rbp, rsp
0x180019d15  sub     rsp, 40h
0x180019d19  lea     rax, [rbp+var_10]
0x180019d1d  mov     rbx, rcx
0x180019d20  mov     [rbp+var_8], rax
0x180019d24  lea     rax, [rbp+var_10]
0x180019d28  mov     [rbp+var_10], rax
0x180019d2c  mov     rax, [rbx]
0x180019d2f  cmp     rax, rbx
0x180019d32  jz      short loc_180019D75
0x180019d34  cmp     [rax+8], rbx
0x180019d38  jnz     loc_180019DE5
0x180019d3e  mov     rcx, [rax]
0x180019d41  cmp     [rcx+8], rax
0x180019d45  jnz     loc_180019DE5
0x180019d4b  mov     [rbx], rcx
0x180019d4e  lea     rdx, [rbp+var_10]
0x180019d52  mov     [rcx+8], rbx
0x180019d56  mov     rcx, [rbp+var_10]
0x180019d5a  cmp     [rcx+8], rdx
0x180019d5e  jnz     loc_180019DE5
0x180019d64  lea     rdx, [rbp+var_10]
0x180019d68  mov     [rax], rcx
0x180019d6b  mov     [rax+8], rdx
0x180019d6f  mov     [rcx+8], rax
0x180019d73  jmp     short loc_180019D28
0x180019d75  lea     r9, ?PingTrafficSentNotify@HTTP2Channel@@UEAAXK@Z; FreeRoutine
0x180019d7c  mov     [rsp+40h+TableContext], rbx; TableContext
0x180019d81  lea     r8, ?Allocate@?$GenericTable@VHTTP2ServerCookie@@$0A@$1??$DefaultCompareKeys@VHTTP2Cookie@@@@YAHAEBVHTTP2Cookie@@0@Z@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180019d88  mov     rcx, rbx; Table
0x180019d8b  lea     rdx, ?Compare@?$GenericTable@VHTTP2ServerCookie@@$0A@$1??$DefaultCompareKeys@VHTTP2Cookie@@@@YAHAEBVHTTP2Cookie@@0@Z@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180019d92  call    cs:__imp_RtlInitializeGenericTableAvl
0x180019d98  mov     rdx, [rbp+var_10]
0x180019d9c  lea     rax, [rbp+var_10]
0x180019da0  cmp     rdx, rax
0x180019da3  jz      short loc_180019DEC
0x180019da5  lea     rax, [rbp+var_10]
0x180019da9  cmp     [rdx+8], rax
0x180019dad  jnz     short loc_180019DE5
0x180019daf  mov     rax, [rdx]
0x180019db2  cmp     [rax+8], rdx
0x180019db6  jnz     short loc_180019DE5
0x180019db8  lea     rcx, [rbp+var_10]
0x180019dbc  mov     [rbp+var_10], rax
0x180019dc0  mov     [rax+8], rcx
0x180019dc4  lea     r9, [rbp+NewElement]; NewElement
0x180019dc8  mov     [rbx+68h], rdx
0x180019dcc  mov     r8d, 10h; BufferSize
0x180019dd2  add     rdx, 20h ; ' '; Buffer
0x180019dd6  mov     [rbp+NewElement], 0
0x180019dda  mov     rcx, rbx; Table
0x180019ddd  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180019de3  jmp     short loc_180019D98
0x180019de5  mov     ecx, 3
0x180019dea  int     29h; Win8: RtlFailFast(ecx)
0x180019dec  mov     dword ptr [rbx+78h], 1
0x180019df3  mov     rbx, [rsp+40h+arg_8]
0x180019df8  add     rsp, 40h
0x180019dfc  pop     rbp
0x180019dfd  retn
```
