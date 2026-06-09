# FreeProxyResolveUrl(tagProxyResolveUrl * *)

- ea: `0x1800403d4`
- end: `0x18004045e`
- name: `?FreeProxyResolveUrl@@YAXPEAPEAUtagProxyResolveUrl@@@Z`
- size: `138`
- prototype: `void __fastcall(struct tagProxyResolveUrl **)`
- caller_count: `23`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004b0c`
- `0x18000f744`
- `0x18001c588`
- `0x18001ea78`
- `0x180024acc`
- `0x180030ab0`
- `0x18003e450`
- `0x18003fad0`
- `0x180040650`
- `0x18004313c`
- `0x180043230`
- `0x180046988`
- `0x180046ee0`
- `0x1800472b0`
- `0x18004738c`
- `0x18006a0f0`
- `0x18006f348`
- `0x18006f7bc`
- `0x180070048`
- `0x180082c98`
- `0x18009c8c0`
- `0x1800accd8`
- `0x1800b2b70`

## callees

- `0x1800403d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040425`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004043a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004044d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040425`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004043a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004044d`

## pseudocode

```c
void __fastcall FreeProxyResolveUrl(LPVOID **a1)
{
  LPVOID *v1; // rbx
  LPVOID *v2; // rdi
  LPVOID *v3; // rdi

  if ( a1 )
  {
    v1 = *a1;
    *a1 = 0;
    if ( v1 )
    {
      v2 = v1 + 1;
      if ( v1 != (LPVOID *)-8LL && *v2 )
      {
        CoTaskMemFree(*v2);
        *v2 = 0;
      }
      v3 = v1 + 2;
      if ( v1 != (LPVOID *)-16LL && *v3 )
      {
        CoTaskMemFree(*v3);
        *v3 = 0;
      }
      if ( *v1 )
        CoTaskMemFree(*v1);
      *(_OWORD *)v1 = 0;
      *((_OWORD *)v1 + 1) = 0;
      CoTaskMemFree(v1);
    }
  }
}

```

## disassembly

```asm
0x1800403d4  test    rcx, rcx
0x1800403d7  jz      locret_18004045D
0x1800403dd  mov     [rsp+arg_0], rbx
0x1800403e2  push    rdi
0x1800403e3  sub     rsp, 20h
0x1800403e7  mov     rbx, [rcx]
0x1800403ea  mov     qword ptr [rcx], 0
0x1800403f1  test    rbx, rbx
0x1800403f4  jz      short loc_180040453
0x1800403f6  lea     rdi, [rbx+8]
0x1800403fa  test    rdi, rdi
0x1800403fd  jz      short loc_180040414
0x1800403ff  mov     rcx, [rdi]; pv
0x180040402  test    rcx, rcx
0x180040405  jz      short loc_180040414
0x180040407  call    cs:__imp_CoTaskMemFree
0x18004040d  mov     qword ptr [rdi], 0
0x180040414  lea     rdi, [rbx+10h]
0x180040418  test    rdi, rdi
0x18004041b  jz      short loc_180040432
0x18004041d  mov     rcx, [rdi]; pv
0x180040420  test    rcx, rcx
0x180040423  jz      short loc_180040432
0x180040425  call    cs:__imp_CoTaskMemFree
0x18004042b  mov     qword ptr [rdi], 0
0x180040432  mov     rcx, [rbx]; pv
0x180040435  test    rcx, rcx
0x180040438  jz      short loc_180040440
0x18004043a  call    cs:__imp_CoTaskMemFree
0x180040440  xorps   xmm0, xmm0
0x180040443  mov     rcx, rbx; pv
0x180040446  movups  xmmword ptr [rbx], xmm0
0x180040449  movups  xmmword ptr [rbx+10h], xmm0
0x18004044d  call    cs:__imp_CoTaskMemFree
0x180040453  mov     rbx, [rsp+28h+arg_0]
0x180040458  add     rsp, 20h
0x18004045c  pop     rdi
0x18004045d  retn
```
