# FreeProxySettings(tagProxySettings *)

- ea: `0x18001f4b8`
- end: `0x18001f605`
- name: `?FreeProxySettings@@YAXPEAUtagProxySettings@@@Z`
- size: `333`
- prototype: `void __fastcall(struct tagProxySettings *)`
- caller_count: `14`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001451c`
- `0x18001d690`
- `0x18001de3c`
- `0x18001ea78`
- `0x18001f024`
- `0x1800506c0`
- `0x1800652c0`
- `0x1800690c4`
- `0x1800940dc`
- `0x1800accd8`
- `0x1800b2294`
- `0x1800bdcf0`
- `0x1800bf910`
- `0x1800c1fbc`

## callees

- `0x18001f4b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f57c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f58e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f57c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f58e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f5fa`

## pseudocode

```c
void __fastcall FreeProxySettings(struct tagProxySettings *a1)
{
  void **v2; // rax
  void *v3; // rcx
  void **v4; // rax
  void *v5; // rcx
  void **v6; // rax
  void *v7; // rcx
  void **v8; // rax
  void *v9; // rcx
  void **v10; // rax
  void *v11; // rcx
  void **v12; // rax
  void *v13; // rcx
  void **v14; // rax
  void *v15; // rcx
  void **v16; // rbx
  void *v17; // rcx

  if ( a1 )
  {
    v2 = (void **)((char *)a1 + 16);
    if ( a1 != (struct tagProxySettings *)-16LL )
    {
      v3 = *v2;
      if ( *v2 )
      {
        *v2 = 0;
        CoTaskMemFree(v3);
      }
    }
    v4 = (void **)((char *)a1 + 24);
    if ( a1 != (struct tagProxySettings *)-24LL )
    {
      v5 = *v4;
      if ( *v4 )
      {
        *v4 = 0;
        CoTaskMemFree(v5);
      }
    }
    v6 = (void **)((char *)a1 + 32);
    if ( a1 != (struct tagProxySettings *)-32LL )
    {
      v7 = *v6;
      if ( *v6 )
      {
        *v6 = 0;
        CoTaskMemFree(v7);
      }
    }
    v8 = (void **)((char *)a1 + 64);
    if ( a1 != (struct tagProxySettings *)-64LL )
    {
      v9 = *v8;
      if ( *v8 )
      {
        *v8 = 0;
        CoTaskMemFree(v9);
      }
    }
    v10 = (void **)((char *)a1 + 40);
    if ( a1 != (struct tagProxySettings *)-40LL )
    {
      v11 = *v10;
      if ( *v10 )
      {
        *v10 = 0;
        CoTaskMemFree(v11);
      }
    }
    v12 = (void **)((char *)a1 + 48);
    if ( a1 != (struct tagProxySettings *)-48LL )
    {
      v13 = *v12;
      if ( *v12 )
      {
        *v12 = 0;
        CoTaskMemFree(v13);
      }
    }
    v14 = (void **)((char *)a1 + 88);
    if ( a1 != (struct tagProxySettings *)-88LL )
    {
      v15 = *v14;
      if ( *v14 )
      {
        *v14 = 0;
        CoTaskMemFree(v15);
      }
    }
    v16 = (void **)((char *)a1 + 104);
    if ( v16 )
    {
      v17 = *v16;
      if ( *v16 )
      {
        *v16 = 0;
        CoTaskMemFree(v17);
      }
    }
  }
}

```

## disassembly

```asm
0x18001f4b8  push    rbx
0x18001f4ba  sub     rsp, 20h
0x18001f4be  mov     rbx, rcx
0x18001f4c1  test    rcx, rcx
0x18001f4c4  jz      loc_18001F56F
0x18001f4ca  lea     rax, [rcx+10h]
0x18001f4ce  test    rax, rax
0x18001f4d1  jz      short loc_18001F4DF
0x18001f4d3  mov     rcx, [rax]; pv
0x18001f4d6  test    rcx, rcx
0x18001f4d9  jnz     loc_18001F575
0x18001f4df  lea     rax, [rbx+18h]
0x18001f4e3  test    rax, rax
0x18001f4e6  jz      short loc_18001F4F4
0x18001f4e8  mov     rcx, [rax]; pv
0x18001f4eb  test    rcx, rcx
0x18001f4ee  jnz     loc_18001F587
0x18001f4f4  lea     rax, [rbx+20h]
0x18001f4f8  test    rax, rax
0x18001f4fb  jz      short loc_18001F509
0x18001f4fd  mov     rcx, [rax]; pv
0x18001f500  test    rcx, rcx
0x18001f503  jnz     loc_18001F599
0x18001f509  lea     rax, [rbx+40h]
0x18001f50d  test    rax, rax
0x18001f510  jz      short loc_18001F51E
0x18001f512  mov     rcx, [rax]; pv
0x18001f515  test    rcx, rcx
0x18001f518  jnz     loc_18001F5AB
0x18001f51e  lea     rax, [rbx+28h]
0x18001f522  test    rax, rax
0x18001f525  jz      short loc_18001F533
0x18001f527  mov     rcx, [rax]; pv
0x18001f52a  test    rcx, rcx
0x18001f52d  jnz     loc_18001F5BD
0x18001f533  lea     rax, [rbx+30h]
0x18001f537  test    rax, rax
0x18001f53a  jz      short loc_18001F548
0x18001f53c  mov     rcx, [rax]; pv
0x18001f53f  test    rcx, rcx
0x18001f542  jnz     loc_18001F5CF
0x18001f548  lea     rax, [rbx+58h]
0x18001f54c  test    rax, rax
0x18001f54f  jz      short loc_18001F55D
0x18001f551  mov     rcx, [rax]; pv
0x18001f554  test    rcx, rcx
0x18001f557  jnz     loc_18001F5E1
0x18001f55d  add     rbx, 68h ; 'h'
0x18001f561  jz      short loc_18001F56F
0x18001f563  mov     rcx, [rbx]; pv
0x18001f566  test    rcx, rcx
0x18001f569  jnz     loc_18001F5F3
0x18001f56f  add     rsp, 20h
0x18001f573  pop     rbx
0x18001f574  retn
0x18001f575  mov     qword ptr [rax], 0
0x18001f57c  call    cs:__imp_CoTaskMemFree
0x18001f582  jmp     loc_18001F4DF
0x18001f587  mov     qword ptr [rax], 0
0x18001f58e  call    cs:__imp_CoTaskMemFree
0x18001f594  jmp     loc_18001F4F4
0x18001f599  mov     qword ptr [rax], 0
0x18001f5a0  call    cs:__imp_CoTaskMemFree
0x18001f5a6  jmp     loc_18001F509
0x18001f5ab  mov     qword ptr [rax], 0
0x18001f5b2  call    cs:__imp_CoTaskMemFree
0x18001f5b8  jmp     loc_18001F51E
0x18001f5bd  mov     qword ptr [rax], 0
0x18001f5c4  call    cs:__imp_CoTaskMemFree
0x18001f5ca  jmp     loc_18001F533
0x18001f5cf  mov     qword ptr [rax], 0
0x18001f5d6  call    cs:__imp_CoTaskMemFree
0x18001f5dc  jmp     loc_18001F548
0x18001f5e1  mov     qword ptr [rax], 0
0x18001f5e8  call    cs:__imp_CoTaskMemFree
0x18001f5ee  jmp     loc_18001F55D
0x18001f5f3  mov     qword ptr [rbx], 0
0x18001f5fa  call    cs:__imp_CoTaskMemFree
0x18001f600  jmp     loc_18001F56F
```
