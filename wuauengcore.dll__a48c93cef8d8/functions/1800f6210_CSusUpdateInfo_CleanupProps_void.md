# CSusUpdateInfo::CleanupProps(void)

- ea: `0x1800f6210`
- end: `0x1800f637e`
- name: `?CleanupProps@CSusUpdateInfo@@QEAAXXZ`
- size: `366`
- prototype: `void __fastcall(CSusUpdateInfo *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800c7604`
- `0x1800f61dc`

## callees

- `0x1800f6210`
- `0x180113a3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f622e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f624b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6268`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f62b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f62db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f634e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f622e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f624b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6268`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f62b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f62db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f6323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f634e`

## pseudocode

```c
void __fastcall CSusUpdateInfo::CleanupProps(CSusUpdateInfo *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rdi
  void *v7; // rcx
  void *v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // rcx
  __int64 v11; // rdi
  void *v12; // rcx
  void *v13; // rcx

  v2 = (void *)*((_QWORD *)this + 31);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 31) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 33);
  *((_QWORD *)this + 32) = 0;
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 34);
  *((_QWORD *)this + 33) = 0;
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = 0;
  for ( *((_QWORD *)this + 34) = 0; (unsigned int)v6 < *((_DWORD *)this + 70); v6 = (unsigned int)(v6 + 1) )
  {
    v7 = *(void **)(*((_QWORD *)this + 36) + 8 * v6);
    if ( v7 )
      CoTaskMemFree(v7);
    *(_QWORD *)(*((_QWORD *)this + 36) + 8 * v6) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 36);
  if ( v8 )
    CoTaskMemFree(v8);
  v9 = *((unsigned int *)this + 76);
  v10 = (void *)*((_QWORD *)this + 39);
  *((_QWORD *)this + 36) = 0;
  SusFreePtrArray(v10, v9);
  v11 = 0;
  for ( *((_QWORD *)this + 39) = 0; (unsigned int)v11 < *((_DWORD *)this + 85); v11 = (unsigned int)(v11 + 1) )
  {
    v12 = *(void **)(*((_QWORD *)this + 43) + 8 * v11);
    if ( v12 )
      CoTaskMemFree(v12);
    *(_QWORD *)(*((_QWORD *)this + 43) + 8 * v11) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 43);
  if ( v13 )
    CoTaskMemFree(v13);
  *((_QWORD *)this + 43) = 0;
  *((GUID *)this + 20) = GUID_NULL;
}

```

## disassembly

```asm
0x1800f6210  mov     [rsp+arg_0], rbx
0x1800f6215  mov     [rsp+arg_8], rsi
0x1800f621a  push    rdi
0x1800f621b  sub     rsp, 20h
0x1800f621f  mov     rbx, rcx
0x1800f6222  mov     rcx, [rcx+0F8h]; pv
0x1800f6229  test    rcx, rcx
0x1800f622c  jz      short loc_1800F6234
0x1800f622e  call    cs:__imp_CoTaskMemFree
0x1800f6234  mov     rcx, [rbx+100h]; pv
0x1800f623b  mov     qword ptr [rbx+0F8h], 0
0x1800f6246  test    rcx, rcx
0x1800f6249  jz      short loc_1800F6251
0x1800f624b  call    cs:__imp_CoTaskMemFree
0x1800f6251  mov     rcx, [rbx+108h]; pv
0x1800f6258  mov     qword ptr [rbx+100h], 0
0x1800f6263  test    rcx, rcx
0x1800f6266  jz      short loc_1800F626E
0x1800f6268  call    cs:__imp_CoTaskMemFree
0x1800f626e  mov     rcx, [rbx+110h]; pv
0x1800f6275  mov     qword ptr [rbx+108h], 0
0x1800f6280  test    rcx, rcx
0x1800f6283  jz      short loc_1800F628B
0x1800f6285  call    cs:__imp_CoTaskMemFree
0x1800f628b  xor     edi, edi
0x1800f628d  mov     qword ptr [rbx+110h], 0
0x1800f6298  cmp     [rbx+118h], edi
0x1800f629e  jbe     short loc_1800F62CF
0x1800f62a0  mov     rax, [rbx+120h]
0x1800f62a7  mov     rcx, [rax+rdi*8]; pv
0x1800f62ab  test    rcx, rcx
0x1800f62ae  jz      short loc_1800F62B6
0x1800f62b0  call    cs:__imp_CoTaskMemFree
0x1800f62b6  mov     rax, [rbx+120h]
0x1800f62bd  mov     qword ptr [rax+rdi*8], 0
0x1800f62c5  inc     edi
0x1800f62c7  cmp     edi, [rbx+118h]
0x1800f62cd  jb      short loc_1800F62A0
0x1800f62cf  mov     rcx, [rbx+120h]; pv
0x1800f62d6  test    rcx, rcx
0x1800f62d9  jz      short loc_1800F62E1
0x1800f62db  call    cs:__imp_CoTaskMemFree
0x1800f62e1  mov     edx, [rbx+130h]; unsigned __int64
0x1800f62e7  mov     rcx, [rbx+138h]; lpMem
0x1800f62ee  mov     qword ptr [rbx+120h], 0
0x1800f62f9  call    ?SusFreePtrArray@@YAXPEAX_K@Z; SusFreePtrArray(void *,unsigned __int64)
0x1800f62fe  xor     edi, edi
0x1800f6300  mov     qword ptr [rbx+138h], 0
0x1800f630b  cmp     [rbx+154h], edi
0x1800f6311  jbe     short loc_1800F6342
0x1800f6313  mov     rax, [rbx+158h]
0x1800f631a  mov     rcx, [rax+rdi*8]; pv
0x1800f631e  test    rcx, rcx
0x1800f6321  jz      short loc_1800F6329
0x1800f6323  call    cs:__imp_CoTaskMemFree
0x1800f6329  mov     rax, [rbx+158h]
0x1800f6330  mov     qword ptr [rax+rdi*8], 0
0x1800f6338  inc     edi
0x1800f633a  cmp     edi, [rbx+154h]
0x1800f6340  jb      short loc_1800F6313
0x1800f6342  mov     rcx, [rbx+158h]; pv
0x1800f6349  test    rcx, rcx
0x1800f634c  jz      short loc_1800F6354
0x1800f634e  call    cs:__imp_CoTaskMemFree
0x1800f6354  mov     rsi, [rsp+28h+arg_8]
0x1800f6359  mov     qword ptr [rbx+158h], 0
0x1800f6364  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800f636b  movdqu  xmmword ptr [rbx+140h], xmm0
0x1800f6373  mov     rbx, [rsp+28h+arg_0]
0x1800f6378  add     rsp, 20h
0x1800f637c  pop     rdi
0x1800f637d  retn
```
