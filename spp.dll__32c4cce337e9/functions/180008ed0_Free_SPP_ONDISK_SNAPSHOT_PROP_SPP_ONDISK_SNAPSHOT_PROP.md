# Free_SPP_ONDISK_SNAPSHOT_PROP(_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x180008ed0`
- end: `0x180008ff4`
- name: `?Free_SPP_ONDISK_SNAPSHOT_PROP@@YAXPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z`
- size: `292`
- prototype: `void __fastcall(struct _SPP_ONDISK_SNAPSHOT_PROP *)`
- caller_count: `10`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005360`
- `0x180006110`
- `0x180006550`
- `0x180006730`
- `0x180006cf0`
- `0x180008e54`
- `0x180013c7c`
- `0x180017304`
- `0x18001d0f0`
- `0x18001d47c`

## callees

- `0x180008ed0`
- `0x180008ffc`
- `0x1800346c0`
- `0x180034804`
- `0x180034bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ef0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ef0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fcd`

## pseudocode

```c
void __fastcall Free_SPP_ONDISK_SNAPSHOT_PROP(struct _SPP_ONDISK_SNAPSHOT_PROP *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  unsigned int *v5; // rdi
  unsigned int i; // esi
  _QWORD *v7; // rdi
  unsigned int v8; // esi
  LPVOID *v9; // rcx
  _QWORD *v10; // rdi
  unsigned int v11; // esi
  LPVOID *v12; // rcx

  CoTaskMemFree(*((LPVOID *)a1 + 5));
  v2 = (void *)*((_QWORD *)a1 + 8);
  *((_QWORD *)a1 + 5) = 0;
  CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)a1 + 9);
  *((_QWORD *)a1 + 8) = 0;
  CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)a1 + 10);
  *((_QWORD *)a1 + 9) = 0;
  CoTaskMemFree(v4);
  v5 = (unsigned int *)((char *)a1 + 92);
  *((_QWORD *)a1 + 10) = 0;
  if ( *((_QWORD *)a1 + 12) )
  {
    for ( i = 0; i < *v5; ++i )
      Free_SPP_ONDISK_VOLUME_PROP((LPVOID *)(*((_QWORD *)a1 + 12) + 48LL * i));
    CoTaskMemFree(*((LPVOID *)a1 + 12));
    *((_QWORD *)a1 + 12) = 0;
  }
  *v5 = 0;
  v7 = (_QWORD *)((char *)a1 + 112);
  if ( *((_QWORD *)a1 + 14) )
  {
    v8 = 0;
    if ( *((_DWORD *)a1 + 26) )
    {
      do
        Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)(*v7 + 48LL * v8++));
      while ( v8 < *((_DWORD *)a1 + 26) );
      v9 = (LPVOID *)((char *)a1 + 112);
    }
    else
    {
      v9 = (LPVOID *)((char *)a1 + 112);
    }
    CoTaskMemFree(*v9);
    *v7 = 0;
  }
  v10 = (_QWORD *)((char *)a1 + 144);
  *((_DWORD *)a1 + 26) = 0;
  if ( *((_QWORD *)a1 + 18) )
  {
    v11 = 0;
    if ( *((_DWORD *)a1 + 34) )
    {
      do
        Free_SPP_ENVIRONMENT_PROP((struct _SPP_ENVIRONMENT_PROP *)(*v10 + 16LL * v11++));
      while ( v11 < *((_DWORD *)a1 + 34) );
      v12 = (LPVOID *)((char *)a1 + 144);
    }
    else
    {
      v12 = (LPVOID *)((char *)a1 + 144);
    }
    CoTaskMemFree(*v12);
    *v10 = 0;
  }
  *((_DWORD *)a1 + 34) = 0;
  Free_StringArray((unsigned int *)a1 + 30, (LPVOID *)a1 + 16);
}

```

## disassembly

```asm
0x180008ed0  push    rbx
0x180008ed2  push    rbp
0x180008ed3  push    rsi
0x180008ed4  push    rdi
0x180008ed5  sub     rsp, 28h
0x180008ed9  mov     rbx, rcx
0x180008edc  mov     rcx, [rcx+28h]; pv
0x180008ee0  call    cs:__imp_CoTaskMemFree
0x180008ee6  mov     rcx, [rbx+40h]; pv
0x180008eea  xor     ebp, ebp
0x180008eec  mov     [rbx+28h], rbp
0x180008ef0  call    cs:__imp_CoTaskMemFree
0x180008ef6  mov     rcx, [rbx+48h]; pv
0x180008efa  mov     [rbx+40h], rbp
0x180008efe  call    cs:__imp_CoTaskMemFree
0x180008f04  mov     rcx, [rbx+50h]; pv
0x180008f08  mov     [rbx+48h], rbp
0x180008f0c  call    cs:__imp_CoTaskMemFree
0x180008f12  lea     rdi, [rbx+5Ch]
0x180008f16  mov     [rbx+50h], rbp
0x180008f1a  cmp     [rbx+60h], rbp
0x180008f1e  jz      short loc_180008F4D
0x180008f20  mov     esi, ebp
0x180008f22  cmp     [rdi], ebp
0x180008f24  jbe     short loc_180008F3F
0x180008f26  mov     eax, esi
0x180008f28  lea     rcx, [rax+rax*2]
0x180008f2c  shl     rcx, 4
0x180008f30  add     rcx, [rbx+60h]; struct _SPP_ONDISK_VOLUME_PROP *
0x180008f34  call    ?Free_SPP_ONDISK_VOLUME_PROP@@YAXPEAU_SPP_ONDISK_VOLUME_PROP@@@Z; Free_SPP_ONDISK_VOLUME_PROP(_SPP_ONDISK_VOLUME_PROP *)
0x180008f39  inc     esi
0x180008f3b  cmp     esi, [rdi]
0x180008f3d  jb      short loc_180008F26
0x180008f3f  mov     rcx, [rbx+60h]; pv
0x180008f43  call    cs:__imp_CoTaskMemFree
0x180008f49  mov     [rbx+60h], rbp
0x180008f4d  mov     [rdi], ebp
0x180008f4f  lea     rdi, [rbx+70h]
0x180008f53  cmp     [rdi], rbp
0x180008f56  jz      short loc_180008F8D
0x180008f58  mov     esi, ebp
0x180008f5a  cmp     [rbx+68h], ebp
0x180008f5d  jbe     short loc_180008F7E
0x180008f5f  mov     eax, esi
0x180008f61  lea     rcx, [rax+rax*2]
0x180008f65  shl     rcx, 4
0x180008f69  add     rcx, [rdi]; struct _SPP_CLIENT_PROP *
0x180008f6c  call    ?Free_SPP_CLIENT_PROP@@YAXPEAU_SPP_CLIENT_PROP@@@Z; Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *)
0x180008f71  inc     esi
0x180008f73  cmp     esi, [rbx+68h]
0x180008f76  jb      short loc_180008F5F
0x180008f78  lea     rcx, [rbx+70h]
0x180008f7c  jmp     short loc_180008F81
0x180008f7e  mov     rcx, rdi
0x180008f81  mov     rcx, [rcx]; pv
0x180008f84  call    cs:__imp_CoTaskMemFree
0x180008f8a  mov     [rdi], rbp
0x180008f8d  lea     rdi, [rbx+90h]
0x180008f94  mov     [rbx+68h], ebp
0x180008f97  cmp     [rdi], rbp
0x180008f9a  jz      short loc_180008FD6
0x180008f9c  mov     esi, ebp
0x180008f9e  cmp     [rbx+88h], ebp
0x180008fa4  jbe     short loc_180008FC7
0x180008fa6  mov     ecx, esi
0x180008fa8  shl     rcx, 4
0x180008fac  add     rcx, [rdi]; struct _SPP_ENVIRONMENT_PROP *
0x180008faf  call    ?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z; Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)
0x180008fb4  inc     esi
0x180008fb6  cmp     esi, [rbx+88h]
0x180008fbc  jb      short loc_180008FA6
0x180008fbe  lea     rcx, [rbx+90h]
0x180008fc5  jmp     short loc_180008FCA
0x180008fc7  mov     rcx, rdi
0x180008fca  mov     rcx, [rcx]; pv
0x180008fcd  call    cs:__imp_CoTaskMemFree
0x180008fd3  mov     [rdi], rbp
0x180008fd6  lea     rdx, [rbx+80h]; unsigned __int16 ***
0x180008fdd  mov     [rbx+88h], ebp
0x180008fe3  lea     rcx, [rbx+78h]; unsigned int *
0x180008fe7  add     rsp, 28h
0x180008feb  pop     rdi
0x180008fec  pop     rsi
0x180008fed  pop     rbp
0x180008fee  pop     rbx
0x180008fef  jmp     ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
```
