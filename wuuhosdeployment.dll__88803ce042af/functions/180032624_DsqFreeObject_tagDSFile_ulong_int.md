# DsqFreeObject(tagDSFile *,ulong,int)

- ea: `0x180032624`
- end: `0x180032791`
- name: `?DsqFreeObject@@YAXPEAUtagDSFile@@KH@Z`
- size: `365`
- prototype: `void __fastcall(struct tagDSFile *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002147c`

## callees

- `0x18003259c`
- `0x180032624`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003265c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003266b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003267a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032689`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003269b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032759`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003265c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003266b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003267a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032689`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003269b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800326ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032759`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSFile *a1, unsigned int a2)
{
  char *v2; // rbx
  __int64 v3; // rsi
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx

  if ( a1 && a2 )
  {
    v2 = (char *)a1 + 8;
    v3 = a2;
    do
    {
      DsqFreeObject((struct tagDSFileState *)(v2 + 8));
      if ( *(_QWORD *)v2 )
        CoTaskMemFree(*(LPVOID *)v2);
      v4 = (void *)*((_QWORD *)v2 + 8);
      if ( v4 )
        CoTaskMemFree(v4);
      v5 = (void *)*((_QWORD *)v2 + 9);
      if ( v5 )
        CoTaskMemFree(v5);
      v6 = (void *)*((_QWORD *)v2 + 15);
      if ( v6 )
        CoTaskMemFree(v6);
      v7 = (void *)*((_QWORD *)v2 + 16);
      if ( v7 )
        CoTaskMemFree(v7);
      v8 = (void *)*((_QWORD *)v2 + 11);
      if ( v8 )
        CoTaskMemFree(v8);
      v9 = (void *)*((_QWORD *)v2 + 12);
      if ( v9 )
        CoTaskMemFree(v9);
      v10 = (void *)*((_QWORD *)v2 + 27);
      if ( v10 )
        CoTaskMemFree(v10);
      v11 = (void *)*((_QWORD *)v2 + 22);
      if ( v11 )
        CoTaskMemFree(v11);
      v12 = (void *)*((_QWORD *)v2 + 23);
      if ( v12 )
        CoTaskMemFree(v12);
      v13 = (void *)*((_QWORD *)v2 + 25);
      if ( v13 )
        CoTaskMemFree(v13);
      v14 = (void *)*((_QWORD *)v2 + 26);
      if ( v14 )
        CoTaskMemFree(v14);
      memset(*((void **)v2 + 18), 0, *((unsigned int *)v2 + 34));
      v15 = (void *)*((_QWORD *)v2 + 18);
      if ( v15 )
        CoTaskMemFree(v15);
      memset(*((void **)v2 + 20), 0, *((unsigned int *)v2 + 39));
      v16 = (void *)*((_QWORD *)v2 + 20);
      if ( v16 )
        CoTaskMemFree(v16);
      memset(v2 - 8, 0, 0xF8u);
      v2 += 248;
      --v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x180032624  test    rcx, rcx
0x180032627  jz      locret_180032790
0x18003262d  mov     [rsp+arg_0], rbx
0x180032632  mov     [rsp+arg_8], rsi
0x180032637  push    rdi
0x180032638  sub     rsp, 20h
0x18003263c  cmp     edx, 1
0x18003263f  jb      loc_180032781
0x180032645  lea     rbx, [rcx+8]
0x180032649  mov     esi, edx
0x18003264b  lea     rcx, [rbx+8]; struct tagDSFileState *
0x18003264f  call    ?DsqFreeObject@@YAXAEAUtagDSFileState@@@Z; DsqFreeObject(tagDSFileState &)
0x180032654  mov     rcx, [rbx]; pv
0x180032657  test    rcx, rcx
0x18003265a  jz      short loc_180032662
0x18003265c  call    cs:__imp_CoTaskMemFree
0x180032662  mov     rcx, [rbx+40h]; pv
0x180032666  test    rcx, rcx
0x180032669  jz      short loc_180032671
0x18003266b  call    cs:__imp_CoTaskMemFree
0x180032671  mov     rcx, [rbx+48h]; pv
0x180032675  test    rcx, rcx
0x180032678  jz      short loc_180032680
0x18003267a  call    cs:__imp_CoTaskMemFree
0x180032680  mov     rcx, [rbx+78h]; pv
0x180032684  test    rcx, rcx
0x180032687  jz      short loc_18003268F
0x180032689  call    cs:__imp_CoTaskMemFree
0x18003268f  mov     rcx, [rbx+80h]; pv
0x180032696  test    rcx, rcx
0x180032699  jz      short loc_1800326A1
0x18003269b  call    cs:__imp_CoTaskMemFree
0x1800326a1  mov     rcx, [rbx+58h]; pv
0x1800326a5  test    rcx, rcx
0x1800326a8  jz      short loc_1800326B0
0x1800326aa  call    cs:__imp_CoTaskMemFree
0x1800326b0  mov     rcx, [rbx+60h]; pv
0x1800326b4  test    rcx, rcx
0x1800326b7  jz      short loc_1800326BF
0x1800326b9  call    cs:__imp_CoTaskMemFree
0x1800326bf  mov     rcx, [rbx+0D8h]; pv
0x1800326c6  test    rcx, rcx
0x1800326c9  jz      short loc_1800326D1
0x1800326cb  call    cs:__imp_CoTaskMemFree
0x1800326d1  mov     rcx, [rbx+0B0h]; pv
0x1800326d8  test    rcx, rcx
0x1800326db  jz      short loc_1800326E3
0x1800326dd  call    cs:__imp_CoTaskMemFree
0x1800326e3  mov     rcx, [rbx+0B8h]; pv
0x1800326ea  test    rcx, rcx
0x1800326ed  jz      short loc_1800326F5
0x1800326ef  call    cs:__imp_CoTaskMemFree
0x1800326f5  mov     rcx, [rbx+0C8h]; pv
0x1800326fc  test    rcx, rcx
0x1800326ff  jz      short loc_180032707
0x180032701  call    cs:__imp_CoTaskMemFree
0x180032707  mov     rcx, [rbx+0D0h]; pv
0x18003270e  test    rcx, rcx
0x180032711  jz      short loc_180032719
0x180032713  call    cs:__imp_CoTaskMemFree
0x180032719  mov     ecx, [rbx+88h]
0x18003271f  xor     eax, eax
0x180032721  mov     rdi, [rbx+90h]
0x180032728  rep stosb
0x18003272a  mov     rcx, [rbx+90h]; pv
0x180032731  test    rcx, rcx
0x180032734  jz      short loc_18003273C
0x180032736  call    cs:__imp_CoTaskMemFree
0x18003273c  mov     ecx, [rbx+9Ch]
0x180032742  xor     eax, eax
0x180032744  mov     rdi, [rbx+0A0h]
0x18003274b  rep stosb
0x18003274d  mov     rcx, [rbx+0A0h]; pv
0x180032754  test    rcx, rcx
0x180032757  jz      short loc_18003275F
0x180032759  call    cs:__imp_CoTaskMemFree
0x18003275f  lea     rcx, [rbx-8]; void *
0x180032763  xor     edx, edx; Val
0x180032765  mov     r8d, 0F8h; Size
0x18003276b  call    memset
0x180032770  add     rbx, 0F8h
0x180032777  sub     rsi, 1
0x18003277b  jnz     loc_18003264B
0x180032781  mov     rbx, [rsp+28h+arg_0]
0x180032786  mov     rsi, [rsp+28h+arg_8]
0x18003278b  add     rsp, 20h
0x18003278f  pop     rdi
0x180032790  retn
```
