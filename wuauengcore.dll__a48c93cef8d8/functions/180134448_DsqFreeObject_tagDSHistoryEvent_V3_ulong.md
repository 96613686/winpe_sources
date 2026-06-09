# DsqFreeObject(tagDSHistoryEvent_V3 *,ulong)

- ea: `0x180134448`
- end: `0x18013458e`
- name: `?DsqFreeObject@@YAXPEAUtagDSHistoryEvent_V3@@K@Z`
- size: `326`
- prototype: `void __fastcall(struct tagDSHistoryEvent_V3 *, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010cac`
- `0x180011afc`
- `0x1800d38c8`
- `0x1800d4414`
- `0x1800d99e8`
- `0x1801a5eb0`
- `0x180232ca8`

## callees

- `0x180134448`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801344a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801344b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801344d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801344ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013450b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134567`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134486`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801344a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801344b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801344d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801344ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013450b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134567`

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
0x180134448  test    rcx, rcx
0x18013444b  jz      locret_18013458D
0x180134451  mov     [rsp+arg_0], rbx
0x180134456  mov     [rsp+arg_8], rsi
0x18013445b  push    rdi
0x18013445c  sub     rsp, 20h
0x180134460  cmp     edx, 1
0x180134463  jb      loc_18013457E
0x180134469  lea     rbx, [rcx+58h]
0x18013446d  mov     esi, edx
0x18013446f  mov     rcx, [rbx-10h]; pv
0x180134473  test    rcx, rcx
0x180134476  jz      short loc_18013447E
0x180134478  call    cs:__imp_CoTaskMemFree
0x18013447e  mov     rcx, [rbx]; pv
0x180134481  test    rcx, rcx
0x180134484  jz      short loc_18013448C
0x180134486  call    cs:__imp_CoTaskMemFree
0x18013448c  mov     rcx, [rbx-18h]; pv
0x180134490  test    rcx, rcx
0x180134493  jz      short loc_18013449B
0x180134495  call    cs:__imp_CoTaskMemFree
0x18013449b  mov     rcx, [rbx-8]; pv
0x18013449f  test    rcx, rcx
0x1801344a2  jz      short loc_1801344AA
0x1801344a4  call    cs:__imp_CoTaskMemFree
0x1801344aa  mov     rcx, [rbx+8]; pv
0x1801344ae  test    rcx, rcx
0x1801344b1  jz      short loc_1801344B9
0x1801344b3  call    cs:__imp_CoTaskMemFree
0x1801344b9  cmp     qword ptr [rbx+18h], 0
0x1801344be  jz      short loc_1801344F0
0x1801344c0  xor     edi, edi
0x1801344c2  cmp     [rbx+10h], edi
0x1801344c5  jbe     short loc_1801344E1
0x1801344c7  mov     rax, [rbx+18h]
0x1801344cb  mov     rcx, [rax+rdi*8]; pv
0x1801344cf  test    rcx, rcx
0x1801344d2  jz      short loc_1801344DA
0x1801344d4  call    cs:__imp_CoTaskMemFree
0x1801344da  inc     edi
0x1801344dc  cmp     edi, [rbx+10h]
0x1801344df  jb      short loc_1801344C7
0x1801344e1  mov     rcx, [rbx+18h]; pv
0x1801344e5  test    rcx, rcx
0x1801344e8  jz      short loc_1801344F0
0x1801344ea  call    cs:__imp_CoTaskMemFree
0x1801344f0  cmp     qword ptr [rbx+28h], 0
0x1801344f5  jz      short loc_180134527
0x1801344f7  xor     edi, edi
0x1801344f9  cmp     [rbx+20h], edi
0x1801344fc  jbe     short loc_180134518
0x1801344fe  mov     rax, [rbx+28h]
0x180134502  mov     rcx, [rax+rdi*8]; pv
0x180134506  test    rcx, rcx
0x180134509  jz      short loc_180134511
0x18013450b  call    cs:__imp_CoTaskMemFree
0x180134511  inc     edi
0x180134513  cmp     edi, [rbx+20h]
0x180134516  jb      short loc_1801344FE
0x180134518  mov     rcx, [rbx+28h]; pv
0x18013451c  test    rcx, rcx
0x18013451f  jz      short loc_180134527
0x180134521  call    cs:__imp_CoTaskMemFree
0x180134527  cmp     qword ptr [rbx+38h], 0
0x18013452c  jz      short loc_18013455E
0x18013452e  xor     edi, edi
0x180134530  cmp     [rbx+34h], edi
0x180134533  jbe     short loc_18013454F
0x180134535  mov     rax, [rbx+38h]
0x180134539  mov     rcx, [rax+rdi*8]; pv
0x18013453d  test    rcx, rcx
0x180134540  jz      short loc_180134548
0x180134542  call    cs:__imp_CoTaskMemFree
0x180134548  inc     edi
0x18013454a  cmp     edi, [rbx+34h]
0x18013454d  jb      short loc_180134535
0x18013454f  mov     rcx, [rbx+38h]; pv
0x180134553  test    rcx, rcx
0x180134556  jz      short loc_18013455E
0x180134558  call    cs:__imp_CoTaskMemFree
0x18013455e  mov     rcx, [rbx+48h]; pv
0x180134562  test    rcx, rcx
0x180134565  jz      short loc_18013456D
0x180134567  call    cs:__imp_CoTaskMemFree
0x18013456d  add     rbx, 0C0h
0x180134574  sub     rsi, 1
0x180134578  jnz     loc_18013446F
0x18013457e  mov     rbx, [rsp+28h+arg_0]
0x180134583  mov     rsi, [rsp+28h+arg_8]
0x180134588  add     rsp, 20h
0x18013458c  pop     rdi
0x18013458d  retn
```
