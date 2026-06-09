# _lambda_7bd545f906ce9baac5389edd734cd35e_::operator()

- ea: `0x180100858`
- end: `0x180100943`
- name: `_lambda_7bd545f906ce9baac5389edd734cd35e_::operator()`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010050c`

## callees

- `0x180100858`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010088a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801008ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801008d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801008f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010088a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801008ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801008d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801008f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100923`

## pseudocode

```c
void **__fastcall lambda_7bd545f906ce9baac5389edd734cd35e_::operator()(void ***a1)
{
  unsigned int i; // esi
  unsigned __int64 v3; // rdi
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void **result; // rax
  void *v9; // rcx

  for ( i = 0; i < *((_DWORD *)a1 + 2); ++i )
  {
    v3 = (unsigned __int64)i << 6;
    v4 = *(void **)((char *)**a1 + v3);
    if ( v4 )
    {
      CoTaskMemFree(v4);
      *(_QWORD *)((char *)**a1 + v3) = 0;
    }
    v5 = *(void **)((char *)**a1 + v3 + 8);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *(_QWORD *)((char *)**a1 + v3 + 8) = 0;
    }
    v6 = *(void **)((char *)**a1 + v3 + 48);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *(_QWORD *)((char *)**a1 + v3 + 48) = 0;
    }
    v7 = *(void **)((char *)**a1 + v3 + 56);
    if ( v7 )
    {
      CoTaskMemFree(v7);
      *(_QWORD *)((char *)**a1 + v3 + 56) = 0;
    }
  }
  result = *a1;
  v9 = **a1;
  if ( v9 )
  {
    CoTaskMemFree(v9);
    result = *a1;
    **a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180100858  mov     [rsp+arg_0], rbx
0x18010085d  mov     [rsp+arg_8], rsi
0x180100862  push    rdi
0x180100863  sub     rsp, 20h
0x180100867  xor     esi, esi
0x180100869  mov     rbx, rcx
0x18010086c  cmp     [rcx+8], esi
0x18010086f  jbe     loc_180100918
0x180100875  mov     rax, [rbx]
0x180100878  mov     edi, esi
0x18010087a  shl     rdi, 6
0x18010087e  mov     rcx, [rax]
0x180100881  mov     rcx, [rdi+rcx]; pv
0x180100885  test    rcx, rcx
0x180100888  jz      short loc_18010089E
0x18010088a  call    cs:__imp_CoTaskMemFree
0x180100890  mov     rax, [rbx]
0x180100893  mov     rcx, [rax]
0x180100896  mov     qword ptr [rdi+rcx], 0
0x18010089e  mov     rax, [rbx]
0x1801008a1  mov     rcx, [rax]
0x1801008a4  mov     rcx, [rcx+rdi+8]; pv
0x1801008a9  test    rcx, rcx
0x1801008ac  jz      short loc_1801008C3
0x1801008ae  call    cs:__imp_CoTaskMemFree
0x1801008b4  mov     rax, [rbx]
0x1801008b7  mov     rcx, [rax]
0x1801008ba  mov     qword ptr [rcx+rdi+8], 0
0x1801008c3  mov     rax, [rbx]
0x1801008c6  mov     rcx, [rax]
0x1801008c9  mov     rcx, [rcx+rdi+30h]; pv
0x1801008ce  test    rcx, rcx
0x1801008d1  jz      short loc_1801008E8
0x1801008d3  call    cs:__imp_CoTaskMemFree
0x1801008d9  mov     rax, [rbx]
0x1801008dc  mov     rcx, [rax]
0x1801008df  mov     qword ptr [rcx+rdi+30h], 0
0x1801008e8  mov     rax, [rbx]
0x1801008eb  mov     rcx, [rax]
0x1801008ee  mov     rcx, [rcx+rdi+38h]; pv
0x1801008f3  test    rcx, rcx
0x1801008f6  jz      short loc_18010090D
0x1801008f8  call    cs:__imp_CoTaskMemFree
0x1801008fe  mov     rax, [rbx]
0x180100901  mov     rcx, [rax]
0x180100904  mov     qword ptr [rcx+rdi+38h], 0
0x18010090d  inc     esi
0x18010090f  cmp     esi, [rbx+8]
0x180100912  jb      loc_180100875
0x180100918  mov     rax, [rbx]
0x18010091b  mov     rcx, [rax]; pv
0x18010091e  test    rcx, rcx
0x180100921  jz      short loc_180100933
0x180100923  call    cs:__imp_CoTaskMemFree
0x180100929  mov     rax, [rbx]
0x18010092c  mov     qword ptr [rax], 0
0x180100933  mov     rbx, [rsp+28h+arg_0]
0x180100938  mov     rsi, [rsp+28h+arg_8]
0x18010093d  add     rsp, 20h
0x180100941  pop     rdi
0x180100942  retn
```
