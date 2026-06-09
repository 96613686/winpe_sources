# DsqFreeObject(tagDSConfig *)

- ea: `0x1801820a0`
- end: `0x18018218b`
- name: `?DsqFreeObject@@YAXPEAUtagDSConfig@@@Z`
- size: `235`
- prototype: `void __fastcall(struct tagDSConfig *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b4430`
- `0x1800b5360`
- `0x18017fd18`

## callees

- `0x1801820a0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801820cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801820cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180182167`
- `OLEAUT32!__imp_SysFreeString` at `0x1801820be`
- `OLEAUT32!__imp_SysFreeString` at `0x1801820ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1801820fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18018210b`
- `OLEAUT32!__imp_SysFreeString` at `0x180182142`
- `OLEAUT32!__imp_SysFreeString` at `0x180182151`
- `OLEAUT32!__imp_SysFreeString` at `0x1801820be`
- `OLEAUT32!__imp_SysFreeString` at `0x1801820ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1801820fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18018210b`
- `OLEAUT32!__imp_SysFreeString` at `0x180182142`
- `OLEAUT32!__imp_SysFreeString` at `0x180182151`

## pseudocode

```c
void __fastcall DsqFreeObject(BSTR *a1)
{
  BSTR v2; // rcx
  __int64 i; // rsi
  BSTR v4; // rcx
  unsigned int j; // esi
  BSTR v6; // rcx

  if ( a1 )
  {
    SysFreeString(*a1);
    v2 = a1[4];
    if ( v2 )
      CoTaskMemFree(v2);
    if ( a1[2] )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 6); i = (unsigned int)(i + 1) )
      {
        SysFreeString(*(BSTR *)&a1[2][12 * i]);
        SysFreeString(*(BSTR *)&a1[2][12 * i + 4]);
        SysFreeString(*(BSTR *)&a1[2][12 * i + 8]);
      }
      v4 = a1[2];
      if ( v4 )
        CoTaskMemFree(v4);
    }
    if ( a1[6] )
    {
      for ( j = 0; j < *((_DWORD *)a1 + 14); ++j )
      {
        SysFreeString(*(BSTR *)&a1[6][8 * j]);
        SysFreeString(*(BSTR *)&a1[6][8 * j + 4]);
      }
      v6 = a1[6];
      if ( v6 )
        CoTaskMemFree(v6);
    }
    memset(a1, 0, 0x40u);
  }
}

```

## disassembly

```asm
0x1801820a0  test    rcx, rcx
0x1801820a3  jz      locret_18018218A
0x1801820a9  mov     [rsp+arg_0], rbx
0x1801820ae  mov     [rsp+arg_8], rsi
0x1801820b3  push    rdi
0x1801820b4  sub     rsp, 20h
0x1801820b8  mov     rdi, rcx
0x1801820bb  mov     rcx, [rcx]; bstrString
0x1801820be  call    cs:__imp_SysFreeString
0x1801820c4  mov     rcx, [rdi+20h]; pv
0x1801820c8  test    rcx, rcx
0x1801820cb  jz      short loc_1801820D3
0x1801820cd  call    cs:__imp_CoTaskMemFree
0x1801820d3  cmp     qword ptr [rdi+10h], 0
0x1801820d8  jz      short loc_180182127
0x1801820da  xor     esi, esi
0x1801820dc  cmp     [rdi+18h], esi
0x1801820df  jbe     short loc_180182118
0x1801820e1  mov     rcx, [rdi+10h]
0x1801820e5  lea     rbx, [rsi+rsi*2]
0x1801820e9  mov     rcx, [rcx+rbx*8]; bstrString
0x1801820ed  call    cs:__imp_SysFreeString
0x1801820f3  mov     rcx, [rdi+10h]
0x1801820f7  mov     rcx, [rcx+rbx*8+8]; bstrString
0x1801820fc  call    cs:__imp_SysFreeString
0x180182102  mov     rcx, [rdi+10h]
0x180182106  mov     rcx, [rcx+rbx*8+10h]; bstrString
0x18018210b  call    cs:__imp_SysFreeString
0x180182111  inc     esi
0x180182113  cmp     esi, [rdi+18h]
0x180182116  jb      short loc_1801820E1
0x180182118  mov     rcx, [rdi+10h]; pv
0x18018211c  test    rcx, rcx
0x18018211f  jz      short loc_180182127
0x180182121  call    cs:__imp_CoTaskMemFree
0x180182127  cmp     qword ptr [rdi+30h], 0
0x18018212c  jz      short loc_18018216D
0x18018212e  xor     esi, esi
0x180182130  cmp     [rdi+38h], esi
0x180182133  jbe     short loc_18018215E
0x180182135  mov     rcx, [rdi+30h]
0x180182139  mov     ebx, esi
0x18018213b  add     rbx, rbx
0x18018213e  mov     rcx, [rcx+rbx*8]; bstrString
0x180182142  call    cs:__imp_SysFreeString
0x180182148  mov     rcx, [rdi+30h]
0x18018214c  mov     rcx, [rcx+rbx*8+8]; bstrString
0x180182151  call    cs:__imp_SysFreeString
0x180182157  inc     esi
0x180182159  cmp     esi, [rdi+38h]
0x18018215c  jb      short loc_180182135
0x18018215e  mov     rcx, [rdi+30h]; pv
0x180182162  test    rcx, rcx
0x180182165  jz      short loc_18018216D
0x180182167  call    cs:__imp_CoTaskMemFree
0x18018216d  xor     edx, edx; Val
0x18018216f  mov     rcx, rdi; void *
0x180182172  lea     r8d, [rdx+40h]; Size
0x180182176  call    memset
0x18018217b  mov     rbx, [rsp+28h+arg_0]
0x180182180  mov     rsi, [rsp+28h+arg_8]
0x180182185  add     rsp, 20h
0x180182189  pop     rdi
0x18018218a  retn
```
