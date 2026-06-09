# DsqFreeObject(tagDSHistoryEvent_V3 *,ulong)

- ea: `0x180097968`
- end: `0x180097aae`
- name: `?DsqFreeObject@@YAXPEAUtagDSHistoryEvent_V3@@K@Z`
- size: `326`
- prototype: `void __fastcall(struct tagDSHistoryEvent_V3 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b5f0`
- `0x18006e940`

## callees

- `0x180097968`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800979f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097a87`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSHistoryEvent_V3 *a1, unsigned int a2)
{
  char *v2; // rbx
  __int64 v3; // rsi
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 i; // rdi
  void *v9; // rcx
  void *v10; // rcx
  __int64 j; // rdi
  void *v12; // rcx
  void *v13; // rcx
  __int64 k; // rdi
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx

  if ( a1 && a2 )
  {
    v2 = (char *)a1 + 88;
    v3 = a2;
    do
    {
      v4 = (void *)*((_QWORD *)v2 - 2);
      if ( v4 )
        CoTaskMemFree(v4);
      if ( *(_QWORD *)v2 )
        CoTaskMemFree(*(LPVOID *)v2);
      v5 = (void *)*((_QWORD *)v2 - 3);
      if ( v5 )
        CoTaskMemFree(v5);
      v6 = (void *)*((_QWORD *)v2 - 1);
      if ( v6 )
        CoTaskMemFree(v6);
      v7 = (void *)*((_QWORD *)v2 + 1);
      if ( v7 )
        CoTaskMemFree(v7);
      if ( *((_QWORD *)v2 + 3) )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)v2 + 4); i = (unsigned int)(i + 1) )
        {
          v9 = *(void **)(*((_QWORD *)v2 + 3) + 8 * i);
          if ( v9 )
            CoTaskMemFree(v9);
        }
        v10 = (void *)*((_QWORD *)v2 + 3);
        if ( v10 )
          CoTaskMemFree(v10);
      }
      if ( *((_QWORD *)v2 + 5) )
      {
        for ( j = 0; (unsigned int)j < *((_DWORD *)v2 + 8); j = (unsigned int)(j + 1) )
        {
          v12 = *(void **)(*((_QWORD *)v2 + 5) + 8 * j);
          if ( v12 )
            CoTaskMemFree(v12);
        }
        v13 = (void *)*((_QWORD *)v2 + 5);
        if ( v13 )
          CoTaskMemFree(v13);
      }
      if ( *((_QWORD *)v2 + 7) )
      {
        for ( k = 0; (unsigned int)k < *((_DWORD *)v2 + 13); k = (unsigned int)(k + 1) )
        {
          v15 = *(void **)(*((_QWORD *)v2 + 7) + 8 * k);
          if ( v15 )
            CoTaskMemFree(v15);
        }
        v16 = (void *)*((_QWORD *)v2 + 7);
        if ( v16 )
          CoTaskMemFree(v16);
      }
      v17 = (void *)*((_QWORD *)v2 + 9);
      if ( v17 )
        CoTaskMemFree(v17);
      v2 += 192;
      --v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x180097968  test    rcx, rcx
0x18009796b  jz      locret_180097AAD
0x180097971  mov     [rsp+arg_0], rbx
0x180097976  mov     [rsp+arg_8], rsi
0x18009797b  push    rdi
0x18009797c  sub     rsp, 20h
0x180097980  cmp     edx, 1
0x180097983  jb      loc_180097A9E
0x180097989  lea     rbx, [rcx+58h]
0x18009798d  mov     esi, edx
0x18009798f  mov     rcx, [rbx-10h]; pv
0x180097993  test    rcx, rcx
0x180097996  jz      short loc_18009799E
0x180097998  call    cs:__imp_CoTaskMemFree
0x18009799e  mov     rcx, [rbx]; pv
0x1800979a1  test    rcx, rcx
0x1800979a4  jz      short loc_1800979AC
0x1800979a6  call    cs:__imp_CoTaskMemFree
0x1800979ac  mov     rcx, [rbx-18h]; pv
0x1800979b0  test    rcx, rcx
0x1800979b3  jz      short loc_1800979BB
0x1800979b5  call    cs:__imp_CoTaskMemFree
0x1800979bb  mov     rcx, [rbx-8]; pv
0x1800979bf  test    rcx, rcx
0x1800979c2  jz      short loc_1800979CA
0x1800979c4  call    cs:__imp_CoTaskMemFree
0x1800979ca  mov     rcx, [rbx+8]; pv
0x1800979ce  test    rcx, rcx
0x1800979d1  jz      short loc_1800979D9
0x1800979d3  call    cs:__imp_CoTaskMemFree
0x1800979d9  cmp     qword ptr [rbx+18h], 0
0x1800979de  jz      short loc_180097A10
0x1800979e0  xor     edi, edi
0x1800979e2  cmp     [rbx+10h], edi
0x1800979e5  jbe     short loc_180097A01
0x1800979e7  mov     rax, [rbx+18h]
0x1800979eb  mov     rcx, [rax+rdi*8]; pv
0x1800979ef  test    rcx, rcx
0x1800979f2  jz      short loc_1800979FA
0x1800979f4  call    cs:__imp_CoTaskMemFree
0x1800979fa  inc     edi
0x1800979fc  cmp     edi, [rbx+10h]
0x1800979ff  jb      short loc_1800979E7
0x180097a01  mov     rcx, [rbx+18h]; pv
0x180097a05  test    rcx, rcx
0x180097a08  jz      short loc_180097A10
0x180097a0a  call    cs:__imp_CoTaskMemFree
0x180097a10  cmp     qword ptr [rbx+28h], 0
0x180097a15  jz      short loc_180097A47
0x180097a17  xor     edi, edi
0x180097a19  cmp     [rbx+20h], edi
0x180097a1c  jbe     short loc_180097A38
0x180097a1e  mov     rax, [rbx+28h]
0x180097a22  mov     rcx, [rax+rdi*8]; pv
0x180097a26  test    rcx, rcx
0x180097a29  jz      short loc_180097A31
0x180097a2b  call    cs:__imp_CoTaskMemFree
0x180097a31  inc     edi
0x180097a33  cmp     edi, [rbx+20h]
0x180097a36  jb      short loc_180097A1E
0x180097a38  mov     rcx, [rbx+28h]; pv
0x180097a3c  test    rcx, rcx
0x180097a3f  jz      short loc_180097A47
0x180097a41  call    cs:__imp_CoTaskMemFree
0x180097a47  cmp     qword ptr [rbx+38h], 0
0x180097a4c  jz      short loc_180097A7E
0x180097a4e  xor     edi, edi
0x180097a50  cmp     [rbx+34h], edi
0x180097a53  jbe     short loc_180097A6F
0x180097a55  mov     rax, [rbx+38h]
0x180097a59  mov     rcx, [rax+rdi*8]; pv
0x180097a5d  test    rcx, rcx
0x180097a60  jz      short loc_180097A68
0x180097a62  call    cs:__imp_CoTaskMemFree
0x180097a68  inc     edi
0x180097a6a  cmp     edi, [rbx+34h]
0x180097a6d  jb      short loc_180097A55
0x180097a6f  mov     rcx, [rbx+38h]; pv
0x180097a73  test    rcx, rcx
0x180097a76  jz      short loc_180097A7E
0x180097a78  call    cs:__imp_CoTaskMemFree
0x180097a7e  mov     rcx, [rbx+48h]; pv
0x180097a82  test    rcx, rcx
0x180097a85  jz      short loc_180097A8D
0x180097a87  call    cs:__imp_CoTaskMemFree
0x180097a8d  add     rbx, 0C0h
0x180097a94  sub     rsi, 1
0x180097a98  jnz     loc_18009798F
0x180097a9e  mov     rbx, [rsp+28h+arg_0]
0x180097aa3  mov     rsi, [rsp+28h+arg_8]
0x180097aa8  add     rsp, 20h
0x180097aac  pop     rdi
0x180097aad  retn
```
