# Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *)

- ea: `0x1800349d0`
- end: `0x180034af6`
- name: `?Free_SPP_GROUP_PROP@@YAXPEAU_SPP_GROUP_PROP@@@Z`
- size: `294`
- prototype: `void __fastcall(struct _SPP_GROUP_PROP *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002648`
- `0x18000e184`
- `0x180020650`

## callees

- `0x1800346c0`
- `0x180034804`
- `0x1800349d0`
- `0x180034b88`
- `0x180034bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800349ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800349f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800349ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800349f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ad1`

## pseudocode

```c
void __fastcall Free_SPP_GROUP_PROP(struct _SPP_GROUP_PROP *a1)
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

  if ( a1 )
  {
    CoTaskMemFree(*((LPVOID *)a1 + 4));
    v2 = (void *)*((_QWORD *)a1 + 7);
    *((_QWORD *)a1 + 4) = 0;
    CoTaskMemFree(v2);
    v3 = (void *)*((_QWORD *)a1 + 8);
    *((_QWORD *)a1 + 7) = 0;
    CoTaskMemFree(v3);
    v4 = (void *)*((_QWORD *)a1 + 9);
    *((_QWORD *)a1 + 8) = 0;
    CoTaskMemFree(v4);
    v5 = (unsigned int *)((char *)a1 + 80);
    *((_QWORD *)a1 + 9) = 0;
    if ( *((_QWORD *)a1 + 11) )
    {
      for ( i = 0; i < *v5; ++i )
        Free_SPP_VOLUME_PROP((struct _SPP_VOLUME_PROP *)(*((_QWORD *)a1 + 11) + 56LL * i));
      CoTaskMemFree(*((LPVOID *)a1 + 11));
      *((_QWORD *)a1 + 11) = 0;
    }
    *v5 = 0;
    v7 = (_QWORD *)((char *)a1 + 104);
    if ( *((_QWORD *)a1 + 13) )
    {
      v8 = 0;
      if ( *((_DWORD *)a1 + 24) )
      {
        do
          Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)(*v7 + 48LL * v8++));
        while ( v8 < *((_DWORD *)a1 + 24) );
        v9 = (LPVOID *)((char *)a1 + 104);
      }
      else
      {
        v9 = (LPVOID *)((char *)a1 + 104);
      }
      CoTaskMemFree(*v9);
      *v7 = 0;
    }
    v10 = (_QWORD *)((char *)a1 + 136);
    *((_DWORD *)a1 + 24) = 0;
    if ( *((_QWORD *)a1 + 17) )
    {
      v11 = 0;
      if ( *((_DWORD *)a1 + 32) )
      {
        do
          Free_SPP_ENVIRONMENT_PROP((struct _SPP_ENVIRONMENT_PROP *)(*v10 + 16LL * v11++));
        while ( v11 < *((_DWORD *)a1 + 32) );
        v12 = (LPVOID *)((char *)a1 + 136);
      }
      else
      {
        v12 = (LPVOID *)((char *)a1 + 136);
      }
      CoTaskMemFree(*v12);
      *v10 = 0;
    }
    *((_DWORD *)a1 + 32) = 0;
    Free_StringArray((unsigned int *)a1 + 28, (LPVOID *)a1 + 15);
  }
}

```

## disassembly

```asm
0x1800349d0  test    rcx, rcx
0x1800349d3  jz      locret_180034AF5
0x1800349d9  push    rbx
0x1800349da  push    rbp
0x1800349db  push    rsi
0x1800349dc  push    rdi
0x1800349dd  sub     rsp, 28h
0x1800349e1  mov     rbx, rcx
0x1800349e4  xor     ebp, ebp
0x1800349e6  mov     rcx, [rcx+20h]; pv
0x1800349ea  call    cs:__imp_CoTaskMemFree
0x1800349f0  mov     rcx, [rbx+38h]; pv
0x1800349f4  mov     [rbx+20h], rbp
0x1800349f8  call    cs:__imp_CoTaskMemFree
0x1800349fe  mov     rcx, [rbx+40h]; pv
0x180034a02  mov     [rbx+38h], rbp
0x180034a06  call    cs:__imp_CoTaskMemFree
0x180034a0c  mov     rcx, [rbx+48h]; pv
0x180034a10  mov     [rbx+40h], rbp
0x180034a14  call    cs:__imp_CoTaskMemFree
0x180034a1a  lea     rdi, [rbx+50h]
0x180034a1e  mov     [rbx+48h], rbp
0x180034a22  cmp     [rbx+58h], rbp
0x180034a26  jz      short loc_180034A51
0x180034a28  mov     esi, ebp
0x180034a2a  cmp     [rdi], ebp
0x180034a2c  jbe     short loc_180034A43
0x180034a2e  mov     eax, esi
0x180034a30  imul    rcx, rax, 38h ; '8'
0x180034a34  add     rcx, [rbx+58h]; struct _SPP_VOLUME_PROP *
0x180034a38  call    ?Free_SPP_VOLUME_PROP@@YAXPEAU_SPP_VOLUME_PROP@@@Z; Free_SPP_VOLUME_PROP(_SPP_VOLUME_PROP *)
0x180034a3d  inc     esi
0x180034a3f  cmp     esi, [rdi]
0x180034a41  jb      short loc_180034A2E
0x180034a43  mov     rcx, [rbx+58h]; pv
0x180034a47  call    cs:__imp_CoTaskMemFree
0x180034a4d  mov     [rbx+58h], rbp
0x180034a51  mov     [rdi], ebp
0x180034a53  lea     rdi, [rbx+68h]
0x180034a57  cmp     [rdi], rbp
0x180034a5a  jz      short loc_180034A91
0x180034a5c  mov     esi, ebp
0x180034a5e  cmp     [rbx+60h], ebp
0x180034a61  jbe     short loc_180034A82
0x180034a63  mov     eax, esi
0x180034a65  lea     rcx, [rax+rax*2]
0x180034a69  shl     rcx, 4
0x180034a6d  add     rcx, [rdi]; struct _SPP_CLIENT_PROP *
0x180034a70  call    ?Free_SPP_CLIENT_PROP@@YAXPEAU_SPP_CLIENT_PROP@@@Z; Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *)
0x180034a75  inc     esi
0x180034a77  cmp     esi, [rbx+60h]
0x180034a7a  jb      short loc_180034A63
0x180034a7c  lea     rcx, [rbx+68h]
0x180034a80  jmp     short loc_180034A85
0x180034a82  mov     rcx, rdi
0x180034a85  mov     rcx, [rcx]; pv
0x180034a88  call    cs:__imp_CoTaskMemFree
0x180034a8e  mov     [rdi], rbp
0x180034a91  lea     rdi, [rbx+88h]
0x180034a98  mov     [rbx+60h], ebp
0x180034a9b  cmp     [rdi], rbp
0x180034a9e  jz      short loc_180034ADA
0x180034aa0  mov     esi, ebp
0x180034aa2  cmp     [rbx+80h], ebp
0x180034aa8  jbe     short loc_180034ACB
0x180034aaa  mov     ecx, esi
0x180034aac  shl     rcx, 4
0x180034ab0  add     rcx, [rdi]; struct _SPP_ENVIRONMENT_PROP *
0x180034ab3  call    ?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z; Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)
0x180034ab8  inc     esi
0x180034aba  cmp     esi, [rbx+80h]
0x180034ac0  jb      short loc_180034AAA
0x180034ac2  lea     rcx, [rbx+88h]
0x180034ac9  jmp     short loc_180034ACE
0x180034acb  mov     rcx, rdi
0x180034ace  mov     rcx, [rcx]; pv
0x180034ad1  call    cs:__imp_CoTaskMemFree
0x180034ad7  mov     [rdi], rbp
0x180034ada  lea     rdx, [rbx+78h]; unsigned __int16 ***
0x180034ade  mov     [rbx+80h], ebp
0x180034ae4  lea     rcx, [rbx+70h]; unsigned int *
0x180034ae8  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x180034aed  add     rsp, 28h
0x180034af1  pop     rdi
0x180034af2  pop     rsi
0x180034af3  pop     rbp
0x180034af4  pop     rbx
0x180034af5  retn
```
