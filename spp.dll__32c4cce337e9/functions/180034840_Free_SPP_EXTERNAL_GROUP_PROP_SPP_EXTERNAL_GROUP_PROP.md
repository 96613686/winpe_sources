# Free_SPP_EXTERNAL_GROUP_PROP(_SPP_EXTERNAL_GROUP_PROP *)

- ea: `0x180034840`
- end: `0x180034990`
- name: `?Free_SPP_EXTERNAL_GROUP_PROP@@YAXPEAU_SPP_EXTERNAL_GROUP_PROP@@@Z`
- size: `336`
- prototype: `void __fastcall(struct _SPP_EXTERNAL_GROUP_PROP *)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800025e4`
- `0x180009bb0`
- `0x180011b30`
- `0x1800205e0`

## callees

- `0x1800346c0`
- `0x180034804`
- `0x180034840`
- `0x180034998`
- `0x180034bd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003485a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003485a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034945`

## pseudocode

```c
void __fastcall Free_SPP_EXTERNAL_GROUP_PROP(struct _SPP_EXTERNAL_GROUP_PROP *a1)
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
        Free_SPP_EXTERNAL_VOLUME_PROP((struct _SPP_EXTERNAL_VOLUME_PROP *)(*((_QWORD *)a1 + 11) + 24LL * i));
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
    v10 = (_QWORD *)((char *)a1 + 168);
    *((_DWORD *)a1 + 24) = 0;
    if ( *((_QWORD *)a1 + 21) )
    {
      v11 = 0;
      if ( *((_DWORD *)a1 + 40) )
      {
        do
          Free_SPP_ENVIRONMENT_PROP((struct _SPP_ENVIRONMENT_PROP *)(*v10 + 16LL * v11++));
        while ( v11 < *((_DWORD *)a1 + 40) );
        v12 = (LPVOID *)((char *)a1 + 168);
      }
      else
      {
        v12 = (LPVOID *)((char *)a1 + 168);
      }
      CoTaskMemFree(*v12);
      *v10 = 0;
    }
    *((_DWORD *)a1 + 40) = 0;
    Free_StringArray((unsigned int *)a1 + 28, (LPVOID *)a1 + 15);
    Free_StringArray((unsigned int *)a1 + 32, (LPVOID *)a1 + 17);
    Free_StringArray((unsigned int *)a1 + 36, (LPVOID *)a1 + 19);
  }
}

```

## disassembly

```asm
0x180034840  test    rcx, rcx
0x180034843  jz      locret_18003498F
0x180034849  push    rbx
0x18003484a  push    rbp
0x18003484b  push    rsi
0x18003484c  push    rdi
0x18003484d  sub     rsp, 28h
0x180034851  mov     rbx, rcx
0x180034854  xor     ebp, ebp
0x180034856  mov     rcx, [rcx+20h]; pv
0x18003485a  call    cs:__imp_CoTaskMemFree
0x180034860  mov     rcx, [rbx+38h]; pv
0x180034864  mov     [rbx+20h], rbp
0x180034868  call    cs:__imp_CoTaskMemFree
0x18003486e  mov     rcx, [rbx+40h]; pv
0x180034872  mov     [rbx+38h], rbp
0x180034876  call    cs:__imp_CoTaskMemFree
0x18003487c  mov     rcx, [rbx+48h]; pv
0x180034880  mov     [rbx+40h], rbp
0x180034884  call    cs:__imp_CoTaskMemFree
0x18003488a  lea     rdi, [rbx+50h]
0x18003488e  mov     [rbx+48h], rbp
0x180034892  cmp     [rbx+58h], rbp
0x180034896  jz      short loc_1800348C5
0x180034898  mov     esi, ebp
0x18003489a  cmp     [rdi], ebp
0x18003489c  jbe     short loc_1800348B7
0x18003489e  mov     eax, esi
0x1800348a0  lea     rcx, [rax+rax*2]
0x1800348a4  mov     rax, [rbx+58h]
0x1800348a8  lea     rcx, [rax+rcx*8]; struct _SPP_EXTERNAL_VOLUME_PROP *
0x1800348ac  call    ?Free_SPP_EXTERNAL_VOLUME_PROP@@YAXPEAU_SPP_EXTERNAL_VOLUME_PROP@@@Z; Free_SPP_EXTERNAL_VOLUME_PROP(_SPP_EXTERNAL_VOLUME_PROP *)
0x1800348b1  inc     esi
0x1800348b3  cmp     esi, [rdi]
0x1800348b5  jb      short loc_18003489E
0x1800348b7  mov     rcx, [rbx+58h]; pv
0x1800348bb  call    cs:__imp_CoTaskMemFree
0x1800348c1  mov     [rbx+58h], rbp
0x1800348c5  mov     [rdi], ebp
0x1800348c7  lea     rdi, [rbx+68h]
0x1800348cb  cmp     [rdi], rbp
0x1800348ce  jz      short loc_180034905
0x1800348d0  mov     esi, ebp
0x1800348d2  cmp     [rbx+60h], ebp
0x1800348d5  jbe     short loc_1800348F6
0x1800348d7  mov     eax, esi
0x1800348d9  lea     rcx, [rax+rax*2]
0x1800348dd  shl     rcx, 4
0x1800348e1  add     rcx, [rdi]; struct _SPP_CLIENT_PROP *
0x1800348e4  call    ?Free_SPP_CLIENT_PROP@@YAXPEAU_SPP_CLIENT_PROP@@@Z; Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *)
0x1800348e9  inc     esi
0x1800348eb  cmp     esi, [rbx+60h]
0x1800348ee  jb      short loc_1800348D7
0x1800348f0  lea     rcx, [rbx+68h]
0x1800348f4  jmp     short loc_1800348F9
0x1800348f6  mov     rcx, rdi
0x1800348f9  mov     rcx, [rcx]; pv
0x1800348fc  call    cs:__imp_CoTaskMemFree
0x180034902  mov     [rdi], rbp
0x180034905  lea     rdi, [rbx+0A8h]
0x18003490c  mov     [rbx+60h], ebp
0x18003490f  cmp     [rdi], rbp
0x180034912  jz      short loc_18003494E
0x180034914  mov     esi, ebp
0x180034916  cmp     [rbx+0A0h], ebp
0x18003491c  jbe     short loc_18003493F
0x18003491e  mov     ecx, esi
0x180034920  shl     rcx, 4
0x180034924  add     rcx, [rdi]; struct _SPP_ENVIRONMENT_PROP *
0x180034927  call    ?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z; Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)
0x18003492c  inc     esi
0x18003492e  cmp     esi, [rbx+0A0h]
0x180034934  jb      short loc_18003491E
0x180034936  lea     rcx, [rbx+0A8h]
0x18003493d  jmp     short loc_180034942
0x18003493f  mov     rcx, rdi
0x180034942  mov     rcx, [rcx]; pv
0x180034945  call    cs:__imp_CoTaskMemFree
0x18003494b  mov     [rdi], rbp
0x18003494e  lea     rdx, [rbx+78h]; unsigned __int16 ***
0x180034952  mov     [rbx+0A0h], ebp
0x180034958  lea     rcx, [rbx+70h]; unsigned int *
0x18003495c  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x180034961  lea     rdx, [rbx+88h]; unsigned __int16 ***
0x180034968  lea     rcx, [rbx+80h]; unsigned int *
0x18003496f  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x180034974  lea     rdx, [rbx+98h]; unsigned __int16 ***
0x18003497b  lea     rcx, [rbx+90h]; unsigned int *
0x180034982  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x180034987  add     rsp, 28h
0x18003498b  pop     rdi
0x18003498c  pop     rsi
0x18003498d  pop     rbp
0x18003498e  pop     rbx
0x18003498f  retn
```
