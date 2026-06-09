# FreeBackupStatus(_BLB_BACKUP_STATUS &)

- ea: `0x14012dc30`
- end: `0x14012dd2f`
- name: `?FreeBackupStatus@@YAXAEAU_BLB_BACKUP_STATUS@@@Z`
- size: `255`
- prototype: `void __fastcall(struct _BLB_BACKUP_STATUS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140033510`

## callees

- `0x14012daec`
- `0x14012dc30`
- `0x14012dd98`
- `0x14012e5b0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14012dc46`
- `ole32!CoTaskMemFree` at `0x14012dc58`
- `ole32!CoTaskMemFree` at `0x14012dc7d`
- `ole32!CoTaskMemFree` at `0x14012dc98`
- `ole32!CoTaskMemFree` at `0x14012dca9`
- `ole32!CoTaskMemFree` at `0x14012dcbb`
- `ole32!CoTaskMemFree` at `0x14012dcec`
- `ole32!CoTaskMemFree` at `0x14012dd11`
- `ole32!CoTaskMemFree` at `0x14012dc46`
- `ole32!CoTaskMemFree` at `0x14012dc58`
- `ole32!CoTaskMemFree` at `0x14012dc7d`
- `ole32!CoTaskMemFree` at `0x14012dc98`
- `ole32!CoTaskMemFree` at `0x14012dca9`
- `ole32!CoTaskMemFree` at `0x14012dcbb`
- `ole32!CoTaskMemFree` at `0x14012dcec`
- `ole32!CoTaskMemFree` at `0x14012dd11`

## pseudocode

```c
void __fastcall FreeBackupStatus(LPVOID *a1)
{
  void *v2; // rcx
  unsigned int v3; // esi
  LPVOID *i; // rdi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  struct _BLB_COMPONENT_STATUS *v8; // rdx
  unsigned int v9; // ecx
  struct _BLB_BACKUP_SYSTEM_STATE_STATUS *v10; // rcx
  void *v11; // rcx
  struct _BLB_APPLICATION_BACKUP_STATUS *v12; // rcx
  void *v13; // rcx

  CoTaskMemFree(a1[7]);
  v2 = a1[6];
  a1[7] = 0;
  CoTaskMemFree(v2);
  v3 = 0;
  a1[6] = 0;
  for ( i = a1 + 8; v3 < *((_DWORD *)a1 + 11); ++v3 )
  {
    v5 = (void *)*((_QWORD *)*i + 8);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *((_QWORD *)*i + 8) = 0;
    }
  }
  CoTaskMemFree(*i);
  v6 = a1[2];
  *i = 0;
  CoTaskMemFree(v6);
  v7 = a1[10];
  a1[2] = 0;
  CoTaskMemFree(v7);
  v8 = (struct _BLB_COMPONENT_STATUS *)a1[12];
  v9 = *((_DWORD *)a1 + 22);
  a1[10] = 0;
  FreeComponentConsistencyStatus(v9, v8);
  v10 = (struct _BLB_BACKUP_SYSTEM_STATE_STATUS *)a1[14];
  if ( v10 )
  {
    FreeSystemStateBackupStatus(v10);
    v11 = a1[14];
    if ( v11 )
    {
      CoTaskMemFree(v11);
      a1[14] = 0;
    }
  }
  v12 = (struct _BLB_APPLICATION_BACKUP_STATUS *)a1[13];
  if ( v12 )
  {
    FreeApplicationBackupStatus(v12);
    v13 = a1[13];
    if ( v13 )
    {
      CoTaskMemFree(v13);
      a1[13] = 0;
    }
  }
}

```

## disassembly

```asm
0x14012dc30  mov     [rsp+arg_0], rbx
0x14012dc35  mov     [rsp+arg_8], rsi
0x14012dc3a  push    rdi
0x14012dc3b  sub     rsp, 20h
0x14012dc3f  mov     rbx, rcx
0x14012dc42  mov     rcx, [rcx+38h]; pv
0x14012dc46  call    cs:__imp_CoTaskMemFree
0x14012dc4c  mov     rcx, [rbx+30h]; pv
0x14012dc50  mov     qword ptr [rbx+38h], 0
0x14012dc58  call    cs:__imp_CoTaskMemFree
0x14012dc5e  xor     esi, esi
0x14012dc60  mov     qword ptr [rbx+30h], 0
0x14012dc68  lea     rdi, [rbx+40h]
0x14012dc6c  cmp     [rbx+2Ch], esi
0x14012dc6f  jbe     short loc_14012DC95
0x14012dc71  mov     rax, [rdi]
0x14012dc74  mov     rcx, [rax+40h]; pv
0x14012dc78  test    rcx, rcx
0x14012dc7b  jz      short loc_14012DC8E
0x14012dc7d  call    cs:__imp_CoTaskMemFree
0x14012dc83  mov     rax, [rdi]
0x14012dc86  mov     qword ptr [rax+40h], 0
0x14012dc8e  inc     esi
0x14012dc90  cmp     esi, [rbx+2Ch]
0x14012dc93  jb      short loc_14012DC71
0x14012dc95  mov     rcx, [rdi]; pv
0x14012dc98  call    cs:__imp_CoTaskMemFree
0x14012dc9e  mov     rcx, [rbx+10h]; pv
0x14012dca2  mov     qword ptr [rdi], 0
0x14012dca9  call    cs:__imp_CoTaskMemFree
0x14012dcaf  mov     rcx, [rbx+50h]; pv
0x14012dcb3  mov     qword ptr [rbx+10h], 0
0x14012dcbb  call    cs:__imp_CoTaskMemFree
0x14012dcc1  mov     rdx, [rbx+60h]; struct _BLB_COMPONENT_STATUS *
0x14012dcc5  mov     ecx, [rbx+58h]; unsigned int
0x14012dcc8  mov     qword ptr [rbx+50h], 0
0x14012dcd0  call    ?FreeComponentConsistencyStatus@@YAXKPEAU_BLB_COMPONENT_STATUS@@@Z; FreeComponentConsistencyStatus(ulong,_BLB_COMPONENT_STATUS *)
0x14012dcd5  mov     rcx, [rbx+70h]; struct _BLB_BACKUP_SYSTEM_STATE_STATUS *
0x14012dcd9  test    rcx, rcx
0x14012dcdc  jz      short loc_14012DCFA
0x14012dcde  call    ?FreeSystemStateBackupStatus@@YAXAEAU_BLB_BACKUP_SYSTEM_STATE_STATUS@@@Z; FreeSystemStateBackupStatus(_BLB_BACKUP_SYSTEM_STATE_STATUS &)
0x14012dce3  mov     rcx, [rbx+70h]; pv
0x14012dce7  test    rcx, rcx
0x14012dcea  jz      short loc_14012DCFA
0x14012dcec  call    cs:__imp_CoTaskMemFree
0x14012dcf2  mov     qword ptr [rbx+70h], 0
0x14012dcfa  mov     rcx, [rbx+68h]; struct _BLB_APPLICATION_BACKUP_STATUS *
0x14012dcfe  test    rcx, rcx
0x14012dd01  jz      short loc_14012DD1F
0x14012dd03  call    ?FreeApplicationBackupStatus@@YAXAEAU_BLB_APPLICATION_BACKUP_STATUS@@@Z; FreeApplicationBackupStatus(_BLB_APPLICATION_BACKUP_STATUS &)
0x14012dd08  mov     rcx, [rbx+68h]; pv
0x14012dd0c  test    rcx, rcx
0x14012dd0f  jz      short loc_14012DD1F
0x14012dd11  call    cs:__imp_CoTaskMemFree
0x14012dd17  mov     qword ptr [rbx+68h], 0
0x14012dd1f  mov     rbx, [rsp+28h+arg_0]
0x14012dd24  mov     rsi, [rsp+28h+arg_8]
0x14012dd29  add     rsp, 20h
0x14012dd2d  pop     rdi
0x14012dd2e  retn
```
