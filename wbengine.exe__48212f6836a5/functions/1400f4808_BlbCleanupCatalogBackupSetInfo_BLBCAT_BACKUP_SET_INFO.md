# BlbCleanupCatalogBackupSetInfo(_BLBCAT_BACKUP_SET_INFO *)

- ea: `0x1400f4808`
- end: `0x1400f4910`
- name: `?BlbCleanupCatalogBackupSetInfo@@YAXPEAU_BLBCAT_BACKUP_SET_INFO@@@Z`
- size: `264`
- prototype: `void __fastcall(struct _BLBCAT_BACKUP_SET_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140015558`

## callees

- `0x140007ad3`
- `0x1400f4808`
- `0x1400f4918`
- `0x1400f4a5c`
- `0x1400f5850`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400f4819`
- `ole32!CoTaskMemFree` at `0x1400f4823`
- `ole32!CoTaskMemFree` at `0x1400f4853`
- `ole32!CoTaskMemFree` at `0x1400f485d`
- `ole32!CoTaskMemFree` at `0x1400f486a`
- `ole32!CoTaskMemFree` at `0x1400f4877`
- `ole32!CoTaskMemFree` at `0x1400f4884`
- `ole32!CoTaskMemFree` at `0x1400f4891`
- `ole32!CoTaskMemFree` at `0x1400f48bf`
- `ole32!CoTaskMemFree` at `0x1400f48f0`
- `ole32!CoTaskMemFree` at `0x1400f4819`
- `ole32!CoTaskMemFree` at `0x1400f4823`
- `ole32!CoTaskMemFree` at `0x1400f4853`
- `ole32!CoTaskMemFree` at `0x1400f485d`
- `ole32!CoTaskMemFree` at `0x1400f486a`
- `ole32!CoTaskMemFree` at `0x1400f4877`
- `ole32!CoTaskMemFree` at `0x1400f4884`
- `ole32!CoTaskMemFree` at `0x1400f4891`
- `ole32!CoTaskMemFree` at `0x1400f48bf`
- `ole32!CoTaskMemFree` at `0x1400f48f0`

## pseudocode

```c
void __fastcall BlbCleanupCatalogBackupSetInfo(LPVOID *a1)
{
  __int64 i; // rdi
  unsigned int j; // edi
  unsigned int k; // edi

  CoTaskMemFree(a1[2]);
  CoTaskMemFree(a1[4]);
  if ( a1[6] )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 10); i = (unsigned int)(i + 1) )
      BlbCleanupCatalogTargetInfo((struct _BLBCAT_TARGET_INFO *)((char *)a1[6] + 40 * i));
    CoTaskMemFree(a1[6]);
  }
  CoTaskMemFree(a1[7]);
  CoTaskMemFree(a1[16]);
  CoTaskMemFree(a1[17]);
  CoTaskMemFree(a1[19]);
  CoTaskMemFree(a1[22]);
  if ( a1[9] )
  {
    for ( j = 0; j < *((_DWORD *)a1 + 16); ++j )
      BlbCleanupCatalogVolumeInfo((struct _BLBCAT_VOLUME_INFO *)((char *)a1[9] + 120 * j));
    CoTaskMemFree(a1[9]);
  }
  if ( a1[11] )
  {
    for ( k = 0; k < *((_DWORD *)a1 + 20); ++k )
      BlbFreeCatComponentInfo((struct _BLBCAT_COMPONENT_INFO *)((char *)a1[11] + 136 * k));
    CoTaskMemFree(a1[11]);
  }
  memset_0(a1, 0, 0xD0u);
}

```

## disassembly

```asm
0x1400f4808  mov     [rsp+arg_0], rbx
0x1400f480d  push    rdi
0x1400f480e  sub     rsp, 20h
0x1400f4812  mov     rbx, rcx
0x1400f4815  mov     rcx, [rcx+10h]; pv
0x1400f4819  call    cs:__imp_CoTaskMemFree
0x1400f481f  mov     rcx, [rbx+20h]; pv
0x1400f4823  call    cs:__imp_CoTaskMemFree
0x1400f4829  cmp     qword ptr [rbx+30h], 0
0x1400f482e  jz      short loc_1400F4859
0x1400f4830  xor     edi, edi
0x1400f4832  cmp     [rbx+28h], edi
0x1400f4835  jbe     short loc_1400F484F
0x1400f4837  mov     rax, [rbx+30h]
0x1400f483b  lea     rcx, [rdi+rdi*4]
0x1400f483f  lea     rcx, [rax+rcx*8]; struct _BLBCAT_TARGET_INFO *
0x1400f4843  call    ?BlbCleanupCatalogTargetInfo@@YAXPEAU_BLBCAT_TARGET_INFO@@@Z; BlbCleanupCatalogTargetInfo(_BLBCAT_TARGET_INFO *)
0x1400f4848  inc     edi
0x1400f484a  cmp     edi, [rbx+28h]
0x1400f484d  jb      short loc_1400F4837
0x1400f484f  mov     rcx, [rbx+30h]; pv
0x1400f4853  call    cs:__imp_CoTaskMemFree
0x1400f4859  mov     rcx, [rbx+38h]; pv
0x1400f485d  call    cs:__imp_CoTaskMemFree
0x1400f4863  mov     rcx, [rbx+80h]; pv
0x1400f486a  call    cs:__imp_CoTaskMemFree
0x1400f4870  mov     rcx, [rbx+88h]; pv
0x1400f4877  call    cs:__imp_CoTaskMemFree
0x1400f487d  mov     rcx, [rbx+98h]; pv
0x1400f4884  call    cs:__imp_CoTaskMemFree
0x1400f488a  mov     rcx, [rbx+0B0h]; pv
0x1400f4891  call    cs:__imp_CoTaskMemFree
0x1400f4897  cmp     qword ptr [rbx+48h], 0
0x1400f489c  jz      short loc_1400F48C5
0x1400f489e  xor     edi, edi
0x1400f48a0  cmp     [rbx+40h], edi
0x1400f48a3  jbe     short loc_1400F48BB
0x1400f48a5  mov     eax, edi
0x1400f48a7  imul    rcx, rax, 78h ; 'x'
0x1400f48ab  add     rcx, [rbx+48h]; struct _BLBCAT_VOLUME_INFO *
0x1400f48af  call    ?BlbCleanupCatalogVolumeInfo@@YAXPEAU_BLBCAT_VOLUME_INFO@@@Z; BlbCleanupCatalogVolumeInfo(_BLBCAT_VOLUME_INFO *)
0x1400f48b4  inc     edi
0x1400f48b6  cmp     edi, [rbx+40h]
0x1400f48b9  jb      short loc_1400F48A5
0x1400f48bb  mov     rcx, [rbx+48h]; pv
0x1400f48bf  call    cs:__imp_CoTaskMemFree
0x1400f48c5  cmp     qword ptr [rbx+58h], 0
0x1400f48ca  jz      short loc_1400F48F6
0x1400f48cc  xor     edi, edi
0x1400f48ce  cmp     [rbx+50h], edi
0x1400f48d1  jbe     short loc_1400F48EC
0x1400f48d3  mov     eax, edi
0x1400f48d5  imul    rcx, rax, 88h
0x1400f48dc  add     rcx, [rbx+58h]; struct _BLBCAT_COMPONENT_INFO *
0x1400f48e0  call    ?BlbFreeCatComponentInfo@@YAXPEAU_BLBCAT_COMPONENT_INFO@@@Z; BlbFreeCatComponentInfo(_BLBCAT_COMPONENT_INFO *)
0x1400f48e5  inc     edi
0x1400f48e7  cmp     edi, [rbx+50h]
0x1400f48ea  jb      short loc_1400F48D3
0x1400f48ec  mov     rcx, [rbx+58h]; pv
0x1400f48f0  call    cs:__imp_CoTaskMemFree
0x1400f48f6  xor     edx, edx; Val
0x1400f48f8  mov     r8d, 0D0h; Size
0x1400f48fe  mov     rcx, rbx; void *
0x1400f4901  mov     rbx, [rsp+28h+arg_0]
0x1400f4906  add     rsp, 20h
0x1400f490a  pop     rdi
0x1400f490b  jmp     memset_0
```
