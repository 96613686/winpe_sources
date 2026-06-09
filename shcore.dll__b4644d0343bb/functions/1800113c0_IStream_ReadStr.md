# IStream_ReadStr

- ea: `0x1800113c0`
- end: `0x180011532`
- name: `IStream_ReadStr`
- size: `370`
- prototype: `HRESULT __stdcall(IStream *pstm, PWSTR *ppsz)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011180`
- `0x18004af70`

## callees

- `0x1800113c0`
- `0x1800672e8`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011524`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011524`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001145f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001145f`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180011486`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180011486`

## pseudocode

```c
HRESULT __stdcall IStream_ReadStr(IStream *pstm, PWSTR *ppsz)
{
  __int64 v3; // rax
  HRESULT result; // eax
  __int64 v6; // rsi
  unsigned __int64 v7; // rcx
  HRESULT v8; // ebx
  WCHAR *v9; // rax
  WCHAR *v10; // rbx
  size_t v11; // rbp
  __int64 v12; // rax
  PWSTR v13; // rdx
  unsigned __int16 v14; // [rsp+60h] [rbp+8h] BYREF
  int v15; // [rsp+68h] [rbp+10h] BYREF
  LPMALLOC ppMalloc; // [rsp+70h] [rbp+18h] BYREF

  *ppsz = 0;
  v3 = *(_QWORD *)pstm;
  v15 = 0;
  v14 = 0;
  result = (*(__int64 (__fastcall **)(IStream *, unsigned __int16 *, __int64, int *))(v3 + 24))(pstm, &v14, 2, &v15);
  if ( result >= 0 )
  {
    if ( v15 != 2 )
      return -2147467259;
    v6 = v14;
    v7 = (unsigned int)v14 + 1;
    if ( (unsigned int)v7 < v14 )
      return -2147024362;
    *ppsz = 0;
    ppMalloc = 0;
    if ( !is_mul_ok(v7, 2u) )
      return -2147024362;
    v9 = (WCHAR *)CoTaskMemAlloc(2 * v7);
    *ppsz = v9;
    v10 = v9;
    if ( v9 )
    {
      ppMalloc = 0;
      v11 = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v11 = ((__int64 (__fastcall *)(LPMALLOC, WCHAR *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v10);
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      memset_0(*ppsz, 0, v11);
      v8 = 0;
    }
    else
    {
      v8 = -2147024882;
    }
    if ( v8 < 0 )
      return v8;
    v12 = *(_QWORD *)pstm;
    v13 = *ppsz;
    LODWORD(ppMalloc) = 0;
    v8 = (*(__int64 (__fastcall **)(IStream *, PWSTR, _QWORD, LPMALLOC *))(v12 + 24))(
           pstm,
           v13,
           (unsigned int)(2 * v6),
           &ppMalloc);
    if ( v8 >= 0 )
    {
      if ( 2 * (_DWORD)v6 == (_DWORD)ppMalloc )
      {
        (*ppsz)[v6] = 0;
        return v8;
      }
      v8 = -2147467259;
    }
    CoTaskMemFree(*ppsz);
    *ppsz = 0;
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800113c0  push    rdi
0x1800113c2  push    r14
0x1800113c4  push    r15
0x1800113c6  sub     rsp, 40h
0x1800113ca  xor     r15d, r15d
0x1800113cd  lea     r9, [rsp+58h+arg_8]
0x1800113d2  mov     [rdx], r15
0x1800113d5  mov     rdi, rdx
0x1800113d8  mov     rax, [rcx]
0x1800113db  lea     rdx, [rsp+58h+arg_0]
0x1800113e0  mov     r8d, 2
0x1800113e6  mov     [rsp+58h+arg_8], r15d
0x1800113eb  mov     r14, rcx
0x1800113ee  mov     [rsp+58h+arg_0], r15w
0x1800113f4  mov     rax, [rax+18h]
0x1800113f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113fd  test    eax, eax
0x1800113ff  js      short loc_180011452
0x180011401  cmp     [rsp+58h+arg_8], 2
0x180011406  mov     [rsp+58h+arg_18], rbx
0x18001140b  jnz     loc_180011512
0x180011411  mov     [rsp+58h+var_28], rsi
0x180011416  movzx   esi, [rsp+58h+arg_0]
0x18001141b  mov     [rsp+58h+var_20], rbp
0x180011420  lea     ecx, [rsi+1]
0x180011423  cmp     ecx, esi
0x180011425  jb      short loc_18001143C
0x180011427  mov     eax, 2
0x18001142c  mov     [rdi], r15
0x18001142f  mul     rcx
0x180011432  mov     [rsp+58h+ppMalloc], r15
0x180011437  test    rdx, rdx
0x18001143a  jz      short loc_18001145C
0x18001143c  mov     ebx, 80070216h
0x180011441  mov     rsi, [rsp+58h+var_28]
0x180011446  mov     eax, ebx
0x180011448  mov     rbp, [rsp+58h+var_20]
0x18001144d  mov     rbx, [rsp+58h+arg_18]
0x180011452  add     rsp, 40h
0x180011456  pop     r15
0x180011458  pop     r14
0x18001145a  pop     rdi
0x18001145b  retn
0x18001145c  mov     rcx, rax; cb
0x18001145f  call    cs:__imp_CoTaskMemAlloc
0x180011465  mov     [rdi], rax
0x180011468  mov     rbx, rax
0x18001146b  test    rax, rax
0x18001146e  jz      loc_18001150B
0x180011474  lea     rdx, [rsp+58h+ppMalloc]; ppMalloc
0x180011479  mov     [rsp+58h+ppMalloc], r15
0x18001147e  mov     ecx, 1; dwMemContext
0x180011483  mov     rbp, r15
0x180011486  call    cs:__imp_CoGetMalloc
0x18001148c  test    eax, eax
0x18001148e  js      short loc_1800114B8
0x180011490  mov     rcx, [rsp+58h+ppMalloc]
0x180011495  mov     rdx, rbx
0x180011498  mov     rax, [rcx]
0x18001149b  mov     rax, [rax+30h]
0x18001149f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114a4  mov     rcx, [rsp+58h+ppMalloc]
0x1800114a9  mov     rbp, rax
0x1800114ac  mov     rdx, [rcx]
0x1800114af  mov     rax, [rdx+10h]
0x1800114b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114b8  mov     rcx, [rdi]; void *
0x1800114bb  mov     r8, rbp; Size
0x1800114be  xor     edx, edx; Val
0x1800114c0  call    memset_0
0x1800114c5  mov     ebx, r15d
0x1800114c8  test    ebx, ebx
0x1800114ca  js      loc_180011441
0x1800114d0  mov     rax, [r14]
0x1800114d3  lea     ebp, [rsi+rsi]
0x1800114d6  mov     rdx, [rdi]
0x1800114d9  lea     r9, [rsp+58h+ppMalloc]
0x1800114de  mov     r8d, ebp
0x1800114e1  mov     dword ptr [rsp+58h+ppMalloc], r15d
0x1800114e6  mov     rcx, r14
0x1800114e9  mov     rax, [rax+18h]
0x1800114ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114f2  mov     ebx, eax
0x1800114f4  test    eax, eax
0x1800114f6  js      short loc_180011521
0x1800114f8  cmp     ebp, dword ptr [rsp+58h+ppMalloc]
0x1800114fc  jnz     short loc_18001151C
0x1800114fe  mov     rcx, [rdi]
0x180011501  mov     [rcx+rsi*2], r15w
0x180011506  jmp     loc_180011441
0x18001150b  mov     ebx, 8007000Eh
0x180011510  jmp     short loc_1800114C8
0x180011512  mov     eax, 80004005h
0x180011517  jmp     loc_18001144D
0x18001151c  mov     ebx, 80004005h
0x180011521  mov     rcx, [rdi]; pv
0x180011524  call    cs:__imp_CoTaskMemFree
0x18001152a  mov     [rdi], r15
0x18001152d  jmp     loc_180011441
```
