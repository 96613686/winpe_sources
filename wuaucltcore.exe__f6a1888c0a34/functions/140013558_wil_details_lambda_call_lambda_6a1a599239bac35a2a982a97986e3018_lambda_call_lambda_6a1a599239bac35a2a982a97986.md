# wil::details::lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___::_lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___

- ea: `0x140013558`
- end: `0x1400135e0`
- name: `wil::details::lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___::_lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140012be0`
- `0x1400218e5`

## callees

- `0x140013558`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400135aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400135c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400135aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400135c1`

## pseudocode

```c
_DWORD *__fastcall wil::details::lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___::_lambda_call__lambda_6a1a599239bac35a2a982a97986e3018___(
        __int64 a1)
{
  unsigned int v2; // edi
  _DWORD *result; // rax
  __int64 v4; // rsi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v2 = 0;
    for ( result = *(_DWORD **)a1; v2 < **(_DWORD **)a1; ++v2 )
    {
      v4 = 32LL * v2;
      v5 = *(void **)(**(_QWORD **)(a1 + 8) + v4 + 8);
      if ( v5 )
        CoTaskMemFree(v5);
      v6 = *(void **)(v4 + **(_QWORD **)(a1 + 8));
      if ( v6 )
        CoTaskMemFree(v6);
      v7 = *(void **)(**(_QWORD **)(a1 + 8) + v4 + 24);
      if ( v7 )
        CoTaskMemFree(v7);
      result = *(_DWORD **)a1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013558  mov     [rsp+arg_0], rbx
0x14001355d  mov     [rsp+arg_8], rsi
0x140013562  push    rdi
0x140013563  sub     rsp, 20h
0x140013567  cmp     byte ptr [rcx+10h], 0
0x14001356b  mov     rbx, rcx
0x14001356e  jz      short loc_1400135D0
0x140013570  mov     byte ptr [rcx+10h], 0
0x140013574  xor     edi, edi
0x140013576  mov     rax, [rcx]
0x140013579  cmp     [rax], edi
0x14001357b  jbe     short loc_1400135D0
0x14001357d  mov     rax, [rbx+8]
0x140013581  mov     esi, edi
0x140013583  shl     rsi, 5
0x140013587  mov     rcx, [rax]
0x14001358a  mov     rcx, [rcx+rsi+8]; pv
0x14001358f  test    rcx, rcx
0x140013592  jz      short loc_14001359A
0x140013594  call    cs:__imp_CoTaskMemFree
0x14001359a  mov     rax, [rbx+8]
0x14001359e  mov     rcx, [rax]
0x1400135a1  mov     rcx, [rsi+rcx]; pv
0x1400135a5  test    rcx, rcx
0x1400135a8  jz      short loc_1400135B0
0x1400135aa  call    cs:__imp_CoTaskMemFree
0x1400135b0  mov     rax, [rbx+8]
0x1400135b4  mov     rcx, [rax]
0x1400135b7  mov     rcx, [rcx+rsi+18h]; pv
0x1400135bc  test    rcx, rcx
0x1400135bf  jz      short loc_1400135C7
0x1400135c1  call    cs:__imp_CoTaskMemFree
0x1400135c7  mov     rax, [rbx]
0x1400135ca  inc     edi
0x1400135cc  cmp     edi, [rax]
0x1400135ce  jb      short loc_14001357D
0x1400135d0  mov     rbx, [rsp+28h+arg_0]
0x1400135d5  mov     rsi, [rsp+28h+arg_8]
0x1400135da  add     rsp, 20h
0x1400135de  pop     rdi
0x1400135df  retn
```
