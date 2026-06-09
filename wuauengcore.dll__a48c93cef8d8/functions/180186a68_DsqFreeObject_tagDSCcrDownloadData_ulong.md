# DsqFreeObject(tagDSCcrDownloadData *,ulong)

- ea: `0x180186a68`
- end: `0x180186bd0`
- name: `?DsqFreeObject@@YAXPEAUtagDSCcrDownloadData@@K@Z`
- size: `360`
- prototype: `void __fastcall(struct tagDSCcrDownloadData *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005263c`
- `0x180186158`

## callees

- `0x180113a3c`
- `0x180186a68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186aa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186aae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186adb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186aea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186af9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186ba4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186aa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186aae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186adb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186aea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186af9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186b8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186ba4`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSCcrDownloadData *a1, unsigned int a2)
{
  char *v2; // rbx
  __int64 v3; // rbp
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  unsigned int i; // edi
  __int64 v13; // rsi
  void *v14; // rcx
  void *v15; // rcx
  void **v16; // rcx
  void *v17; // rcx
  void *v18; // rcx

  if ( a1 && a2 )
  {
    v2 = (char *)a1 + 168;
    v3 = a2;
    do
    {
      v4 = (void *)*((_QWORD *)v2 - 11);
      if ( v4 )
        CoTaskMemFree(v4);
      if ( *(_QWORD *)v2 )
        CoTaskMemFree(*(LPVOID *)v2);
      v5 = (void *)*((_QWORD *)v2 - 4);
      if ( v5 )
        CoTaskMemFree(v5);
      v6 = (void *)*((_QWORD *)v2 - 2);
      if ( v6 )
        CoTaskMemFree(v6);
      v7 = (void *)*((_QWORD *)v2 - 10);
      if ( v7 )
        CoTaskMemFree(v7);
      v8 = (void *)*((_QWORD *)v2 - 9);
      if ( v8 )
        CoTaskMemFree(v8);
      v9 = (void *)*((_QWORD *)v2 - 8);
      if ( v9 )
        CoTaskMemFree(v9);
      v10 = (void *)*((_QWORD *)v2 - 7);
      if ( v10 )
        CoTaskMemFree(v10);
      v11 = (void *)*((_QWORD *)v2 - 6);
      if ( v11 )
        CoTaskMemFree(v11);
      for ( i = 0; i < *((_DWORD *)v2 + 2); ++i )
      {
        v13 = 232LL * i;
        v14 = *(void **)(v13 + *((_QWORD *)v2 + 2) + 48);
        if ( v14 )
          CoTaskMemFree(v14);
        v15 = *(void **)(v13 + *((_QWORD *)v2 + 2) + 64);
        if ( v15 )
          CoTaskMemFree(v15);
        SusFreePtrArray(*(void **)(v13 + *((_QWORD *)v2 + 2) + 80), *(unsigned int *)(v13 + *((_QWORD *)v2 + 2) + 76));
        v16 = *(void ***)(v13 + *((_QWORD *)v2 + 2) + 96);
        if ( v16 )
          SusFreePtrArray(v16[1], *(unsigned int *)v16);
        v17 = *(void **)(v13 + *((_QWORD *)v2 + 2) + 96);
        if ( v17 )
          CoTaskMemFree(v17);
      }
      v18 = (void *)*((_QWORD *)v2 + 2);
      if ( v18 )
        CoTaskMemFree(v18);
      v2 += 192;
      --v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x180186a68  test    rcx, rcx
0x180186a6b  jz      locret_180186BCF
0x180186a71  mov     [rsp+arg_0], rbx
0x180186a76  mov     [rsp+arg_8], rbp
0x180186a7b  mov     [rsp+arg_10], rsi
0x180186a80  push    rdi
0x180186a81  sub     rsp, 20h
0x180186a85  cmp     edx, 1
0x180186a88  jb      loc_180186BBB
0x180186a8e  lea     rbx, [rcx+0A8h]
0x180186a95  mov     ebp, edx
0x180186a97  mov     rcx, [rbx-58h]; pv
0x180186a9b  test    rcx, rcx
0x180186a9e  jz      short loc_180186AA6
0x180186aa0  call    cs:__imp_CoTaskMemFree
0x180186aa6  mov     rcx, [rbx]; pv
0x180186aa9  test    rcx, rcx
0x180186aac  jz      short loc_180186AB4
0x180186aae  call    cs:__imp_CoTaskMemFree
0x180186ab4  mov     rcx, [rbx-20h]; pv
0x180186ab8  test    rcx, rcx
0x180186abb  jz      short loc_180186AC3
0x180186abd  call    cs:__imp_CoTaskMemFree
0x180186ac3  mov     rcx, [rbx-10h]; pv
0x180186ac7  test    rcx, rcx
0x180186aca  jz      short loc_180186AD2
0x180186acc  call    cs:__imp_CoTaskMemFree
0x180186ad2  mov     rcx, [rbx-50h]; pv
0x180186ad6  test    rcx, rcx
0x180186ad9  jz      short loc_180186AE1
0x180186adb  call    cs:__imp_CoTaskMemFree
0x180186ae1  mov     rcx, [rbx-48h]; pv
0x180186ae5  test    rcx, rcx
0x180186ae8  jz      short loc_180186AF0
0x180186aea  call    cs:__imp_CoTaskMemFree
0x180186af0  mov     rcx, [rbx-40h]; pv
0x180186af4  test    rcx, rcx
0x180186af7  jz      short loc_180186AFF
0x180186af9  call    cs:__imp_CoTaskMemFree
0x180186aff  mov     rcx, [rbx-38h]; pv
0x180186b03  test    rcx, rcx
0x180186b06  jz      short loc_180186B0E
0x180186b08  call    cs:__imp_CoTaskMemFree
0x180186b0e  mov     rcx, [rbx-30h]; pv
0x180186b12  test    rcx, rcx
0x180186b15  jz      short loc_180186B1D
0x180186b17  call    cs:__imp_CoTaskMemFree
0x180186b1d  xor     edi, edi
0x180186b1f  cmp     [rbx+8], edi
0x180186b22  jbe     short loc_180186B9B
0x180186b24  mov     eax, edi
0x180186b26  imul    rsi, rax, 0E8h
0x180186b2d  mov     rax, [rbx+10h]
0x180186b31  mov     rcx, [rsi+rax+30h]; pv
0x180186b36  test    rcx, rcx
0x180186b39  jz      short loc_180186B41
0x180186b3b  call    cs:__imp_CoTaskMemFree
0x180186b41  mov     rax, [rbx+10h]
0x180186b45  mov     rcx, [rsi+rax+40h]; pv
0x180186b4a  test    rcx, rcx
0x180186b4d  jz      short loc_180186B55
0x180186b4f  call    cs:__imp_CoTaskMemFree
0x180186b55  mov     rcx, [rbx+10h]
0x180186b59  mov     edx, [rsi+rcx+4Ch]; unsigned __int64
0x180186b5d  mov     rcx, [rsi+rcx+50h]; lpMem
0x180186b62  call    ?SusFreePtrArray@@YAXPEAX_K@Z; SusFreePtrArray(void *,unsigned __int64)
0x180186b67  mov     rax, [rbx+10h]
0x180186b6b  mov     rcx, [rsi+rax+60h]
0x180186b70  test    rcx, rcx
0x180186b73  jz      short loc_180186B80
0x180186b75  mov     edx, [rcx]; unsigned __int64
0x180186b77  mov     rcx, [rcx+8]; lpMem
0x180186b7b  call    ?SusFreePtrArray@@YAXPEAX_K@Z; SusFreePtrArray(void *,unsigned __int64)
0x180186b80  mov     rax, [rbx+10h]
0x180186b84  mov     rcx, [rsi+rax+60h]; pv
0x180186b89  test    rcx, rcx
0x180186b8c  jz      short loc_180186B94
0x180186b8e  call    cs:__imp_CoTaskMemFree
0x180186b94  inc     edi
0x180186b96  cmp     edi, [rbx+8]
0x180186b99  jb      short loc_180186B24
0x180186b9b  mov     rcx, [rbx+10h]; pv
0x180186b9f  test    rcx, rcx
0x180186ba2  jz      short loc_180186BAA
0x180186ba4  call    cs:__imp_CoTaskMemFree
0x180186baa  add     rbx, 0C0h
0x180186bb1  sub     rbp, 1
0x180186bb5  jnz     loc_180186A97
0x180186bbb  mov     rbx, [rsp+28h+arg_0]
0x180186bc0  mov     rbp, [rsp+28h+arg_8]
0x180186bc5  mov     rsi, [rsp+28h+arg_10]
0x180186bca  add     rsp, 20h
0x180186bce  pop     rdi
0x180186bcf  retn
```
