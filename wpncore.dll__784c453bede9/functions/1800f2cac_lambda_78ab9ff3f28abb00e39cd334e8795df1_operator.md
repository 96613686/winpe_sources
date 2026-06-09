# _lambda_78ab9ff3f28abb00e39cd334e8795df1_::operator()

- ea: `0x1800f2cac`
- end: `0x1800f2ddf`
- name: `_lambda_78ab9ff3f28abb00e39cd334e8795df1_::operator()`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7dfc`
- `0x1800f2b90`

## callees

- `0x1800f2cac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2ce1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2dc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2ce1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2d99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f2dc6`

## pseudocode

```c
void **__fastcall lambda_78ab9ff3f28abb00e39cd334e8795df1_::operator()(unsigned int **a1)
{
  void ***v1; // rbx
  unsigned int i; // ebp
  __int64 v4; // rdi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void **result; // rax
  void *v12; // rcx

  v1 = (void ***)(a1 + 1);
  for ( i = 0; i < **a1; ++i )
  {
    v4 = 176LL * i;
    v5 = *(void **)((char *)**v1 + v4);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *(_QWORD *)((char *)**v1 + v4) = 0;
    }
    v6 = *(void **)((char *)**v1 + v4 + 8);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *(_QWORD *)((char *)**v1 + v4 + 8) = 0;
    }
    v7 = *(void **)((char *)**v1 + v4 + 40);
    if ( v7 )
    {
      CoTaskMemFree(v7);
      *(_QWORD *)((char *)**v1 + v4 + 40) = 0;
    }
    v8 = *(void **)((char *)**v1 + v4 + 80);
    if ( v8 )
    {
      CoTaskMemFree(v8);
      *(_QWORD *)((char *)**v1 + v4 + 80) = 0;
    }
    v9 = *(void **)((char *)**v1 + v4 + 88);
    if ( v9 )
    {
      CoTaskMemFree(v9);
      *(_QWORD *)((char *)**v1 + v4 + 88) = 0;
    }
    v10 = *(void **)((char *)**v1 + v4 + 104);
    if ( v10 )
    {
      CoTaskMemFree(v10);
      *(_QWORD *)((char *)**v1 + v4 + 104) = 0;
    }
  }
  result = *v1;
  v12 = **v1;
  if ( v12 )
  {
    CoTaskMemFree(v12);
    result = *v1;
    **v1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800f2cac  push    rbx
0x1800f2cae  push    rbp
0x1800f2caf  push    rsi
0x1800f2cb0  push    rdi
0x1800f2cb1  sub     rsp, 28h
0x1800f2cb5  mov     rax, [rcx]
0x1800f2cb8  lea     rbx, [rcx+8]
0x1800f2cbc  xor     ebp, ebp
0x1800f2cbe  mov     rsi, rcx
0x1800f2cc1  cmp     [rax], ebp
0x1800f2cc3  jbe     loc_1800F2DBB
0x1800f2cc9  mov     eax, ebp
0x1800f2ccb  imul    rdi, rax, 0B0h
0x1800f2cd2  mov     rax, [rbx]
0x1800f2cd5  mov     rcx, [rax]
0x1800f2cd8  mov     rcx, [rdi+rcx]; pv
0x1800f2cdc  test    rcx, rcx
0x1800f2cdf  jz      short loc_1800F2CF5
0x1800f2ce1  call    cs:__imp_CoTaskMemFree
0x1800f2ce7  mov     rax, [rbx]
0x1800f2cea  mov     rcx, [rax]
0x1800f2ced  mov     qword ptr [rdi+rcx], 0
0x1800f2cf5  mov     rax, [rbx]
0x1800f2cf8  mov     rcx, [rax]
0x1800f2cfb  mov     rcx, [rcx+rdi+8]; pv
0x1800f2d00  test    rcx, rcx
0x1800f2d03  jz      short loc_1800F2D1A
0x1800f2d05  call    cs:__imp_CoTaskMemFree
0x1800f2d0b  mov     rax, [rbx]
0x1800f2d0e  mov     rcx, [rax]
0x1800f2d11  mov     qword ptr [rcx+rdi+8], 0
0x1800f2d1a  mov     rax, [rbx]
0x1800f2d1d  mov     rcx, [rax]
0x1800f2d20  mov     rcx, [rcx+rdi+28h]; pv
0x1800f2d25  test    rcx, rcx
0x1800f2d28  jz      short loc_1800F2D3F
0x1800f2d2a  call    cs:__imp_CoTaskMemFree
0x1800f2d30  mov     rax, [rbx]
0x1800f2d33  mov     rcx, [rax]
0x1800f2d36  mov     qword ptr [rcx+rdi+28h], 0
0x1800f2d3f  mov     rax, [rbx]
0x1800f2d42  mov     rcx, [rax]
0x1800f2d45  mov     rcx, [rcx+rdi+50h]; pv
0x1800f2d4a  test    rcx, rcx
0x1800f2d4d  jz      short loc_1800F2D64
0x1800f2d4f  call    cs:__imp_CoTaskMemFree
0x1800f2d55  mov     rax, [rbx]
0x1800f2d58  mov     rcx, [rax]
0x1800f2d5b  mov     qword ptr [rcx+rdi+50h], 0
0x1800f2d64  mov     rax, [rbx]
0x1800f2d67  mov     rcx, [rax]
0x1800f2d6a  mov     rcx, [rcx+rdi+58h]; pv
0x1800f2d6f  test    rcx, rcx
0x1800f2d72  jz      short loc_1800F2D89
0x1800f2d74  call    cs:__imp_CoTaskMemFree
0x1800f2d7a  mov     rax, [rbx]
0x1800f2d7d  mov     rcx, [rax]
0x1800f2d80  mov     qword ptr [rcx+rdi+58h], 0
0x1800f2d89  mov     rax, [rbx]
0x1800f2d8c  mov     rcx, [rax]
0x1800f2d8f  mov     rcx, [rcx+rdi+68h]; pv
0x1800f2d94  test    rcx, rcx
0x1800f2d97  jz      short loc_1800F2DAE
0x1800f2d99  call    cs:__imp_CoTaskMemFree
0x1800f2d9f  mov     rax, [rbx]
0x1800f2da2  mov     rcx, [rax]
0x1800f2da5  mov     qword ptr [rcx+rdi+68h], 0
0x1800f2dae  mov     rax, [rsi]
0x1800f2db1  inc     ebp
0x1800f2db3  cmp     ebp, [rax]
0x1800f2db5  jb      loc_1800F2CC9
0x1800f2dbb  mov     rax, [rbx]
0x1800f2dbe  mov     rcx, [rax]; pv
0x1800f2dc1  test    rcx, rcx
0x1800f2dc4  jz      short loc_1800F2DD6
0x1800f2dc6  call    cs:__imp_CoTaskMemFree
0x1800f2dcc  mov     rax, [rbx]
0x1800f2dcf  mov     qword ptr [rax], 0
0x1800f2dd6  add     rsp, 28h
0x1800f2dda  pop     rdi
0x1800f2ddb  pop     rsi
0x1800f2ddc  pop     rbp
0x1800f2ddd  pop     rbx
0x1800f2dde  retn
```
