# CleanupBackupSetInfo(_BLB_BACKUP_SET_INFO *)

- ea: `0x14012d104`
- end: `0x14012d1e1`
- name: `?CleanupBackupSetInfo@@YAXPEAU_BLB_BACKUP_SET_INFO@@@Z`
- size: `221`
- prototype: `void __fastcall(struct _BLB_BACKUP_SET_INFO *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140044500`
- `0x14012dbcc`

## callees

- `0x140007ad3`
- `0x14012d104`
- `0x14012d1e8`
- `0x14012d2d8`
- `0x14012e834`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14012d11a`
- `ole32!CoTaskMemFree` at `0x14012d132`
- `ole32!CoTaskMemFree` at `0x14012d141`
- `ole32!CoTaskMemFree` at `0x14012d150`
- `ole32!CoTaskMemFree` at `0x14012d167`
- `ole32!CoTaskMemFree` at `0x14012d17e`
- `ole32!CoTaskMemFree` at `0x14012d1c1`
- `ole32!CoTaskMemFree` at `0x14012d11a`
- `ole32!CoTaskMemFree` at `0x14012d132`
- `ole32!CoTaskMemFree` at `0x14012d141`
- `ole32!CoTaskMemFree` at `0x14012d150`
- `ole32!CoTaskMemFree` at `0x14012d167`
- `ole32!CoTaskMemFree` at `0x14012d17e`
- `ole32!CoTaskMemFree` at `0x14012d1c1`

## pseudocode

```c
void __fastcall CleanupBackupSetInfo(struct _BLB_BACKUP_SET_INFO *a1)
{
  void *v2; // rcx
  struct _BLB_TARGET_INFO *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  unsigned int i; // edi

  v2 = (void *)*((_QWORD *)a1 + 2);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (struct _BLB_TARGET_INFO *)*((_QWORD *)a1 + 4);
  if ( v3 )
  {
    CleanupTargetInfo(v3);
    CoTaskMemFree(*((LPVOID *)a1 + 4));
  }
  v4 = (void *)*((_QWORD *)a1 + 5);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)a1 + 12);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)a1 + 12) = 0;
  }
  v6 = (void *)*((_QWORD *)a1 + 13);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)a1 + 13) = 0;
  }
  v7 = (void *)*((_QWORD *)a1 + 15);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)a1 + 15) = 0;
  }
  FreeVolumes((struct _BLB_VOLUME_INFO **)a1 + 7, (unsigned int *)a1 + 12);
  if ( *((_QWORD *)a1 + 9) )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 16); ++i )
      CleanupComponentInfo((struct _BLB_COMPONENT_INFO *)(*((_QWORD *)a1 + 9) + 112LL * i));
    CoTaskMemFree(*((LPVOID *)a1 + 9));
  }
  memset_0(a1, 0, 0xA8u);
}

```

## disassembly

```asm
0x14012d104  mov     [rsp+arg_0], rbx
0x14012d109  push    rdi
0x14012d10a  sub     rsp, 20h
0x14012d10e  mov     rbx, rcx
0x14012d111  mov     rcx, [rcx+10h]; pv
0x14012d115  test    rcx, rcx
0x14012d118  jz      short loc_14012D120
0x14012d11a  call    cs:__imp_CoTaskMemFree
0x14012d120  mov     rcx, [rbx+20h]; struct _BLB_TARGET_INFO *
0x14012d124  test    rcx, rcx
0x14012d127  jz      short loc_14012D138
0x14012d129  call    ?CleanupTargetInfo@@YAXPEAU_BLB_TARGET_INFO@@@Z; CleanupTargetInfo(_BLB_TARGET_INFO *)
0x14012d12e  mov     rcx, [rbx+20h]; pv
0x14012d132  call    cs:__imp_CoTaskMemFree
0x14012d138  mov     rcx, [rbx+28h]; pv
0x14012d13c  test    rcx, rcx
0x14012d13f  jz      short loc_14012D147
0x14012d141  call    cs:__imp_CoTaskMemFree
0x14012d147  mov     rcx, [rbx+60h]; pv
0x14012d14b  test    rcx, rcx
0x14012d14e  jz      short loc_14012D15E
0x14012d150  call    cs:__imp_CoTaskMemFree
0x14012d156  mov     qword ptr [rbx+60h], 0
0x14012d15e  mov     rcx, [rbx+68h]; pv
0x14012d162  test    rcx, rcx
0x14012d165  jz      short loc_14012D175
0x14012d167  call    cs:__imp_CoTaskMemFree
0x14012d16d  mov     qword ptr [rbx+68h], 0
0x14012d175  mov     rcx, [rbx+78h]; pv
0x14012d179  test    rcx, rcx
0x14012d17c  jz      short loc_14012D18C
0x14012d17e  call    cs:__imp_CoTaskMemFree
0x14012d184  mov     qword ptr [rbx+78h], 0
0x14012d18c  lea     rdx, [rbx+30h]; unsigned int *
0x14012d190  lea     rcx, [rbx+38h]; struct _BLB_VOLUME_INFO **
0x14012d194  call    ?FreeVolumes@@YAXAEAPEAU_BLB_VOLUME_INFO@@AEAK@Z; FreeVolumes(_BLB_VOLUME_INFO * &,ulong &)
0x14012d199  cmp     qword ptr [rbx+48h], 0
0x14012d19e  jz      short loc_14012D1C7
0x14012d1a0  xor     edi, edi
0x14012d1a2  cmp     [rbx+40h], edi
0x14012d1a5  jbe     short loc_14012D1BD
0x14012d1a7  mov     eax, edi
0x14012d1a9  imul    rcx, rax, 70h ; 'p'
0x14012d1ad  add     rcx, [rbx+48h]; struct _BLB_COMPONENT_INFO *
0x14012d1b1  call    ?CleanupComponentInfo@@YAXPEAU_BLB_COMPONENT_INFO@@@Z; CleanupComponentInfo(_BLB_COMPONENT_INFO *)
0x14012d1b6  inc     edi
0x14012d1b8  cmp     edi, [rbx+40h]
0x14012d1bb  jb      short loc_14012D1A7
0x14012d1bd  mov     rcx, [rbx+48h]; pv
0x14012d1c1  call    cs:__imp_CoTaskMemFree
0x14012d1c7  xor     edx, edx; Val
0x14012d1c9  mov     r8d, 0A8h; Size
0x14012d1cf  mov     rcx, rbx; void *
0x14012d1d2  mov     rbx, [rsp+28h+arg_0]
0x14012d1d7  add     rsp, 20h
0x14012d1db  pop     rdi
0x14012d1dc  jmp     memset_0
```
