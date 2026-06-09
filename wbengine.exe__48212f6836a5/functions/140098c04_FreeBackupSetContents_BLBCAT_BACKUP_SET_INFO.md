# FreeBackupSetContents(_BLBCAT_BACKUP_SET_INFO *)

- ea: `0x140098c04`
- end: `0x140098d19`
- name: `?FreeBackupSetContents@@YAXPEAU_BLBCAT_BACKUP_SET_INFO@@@Z`
- size: `277`
- prototype: `void __fastcall(struct _BLBCAT_BACKUP_SET_INFO *)`
- caller_count: `34`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000b820`
- `0x14000ce1c`
- `0x1400160a8`
- `0x140019fd0`
- `0x14001dad0`
- `0x14001e86c`
- `0x140021210`
- `0x1400228fc`
- `0x140024ff4`
- `0x140026dfc`
- `0x140027114`
- `0x140035dd0`
- `0x140040150`
- `0x140040980`
- `0x140041270`
- `0x14004a690`
- `0x14004bfb0`
- `0x14004c680`
- `0x14004dd70`
- `0x14004fb00`
- `0x140051320`
- `0x1400526d0`
- `0x1400540f0`
- `0x14005a62c`
- `0x14006ba88`
- `0x140071174`
- `0x14007649c`
- `0x14007f698`
- `0x1400803b4`
- `0x14009b0b0`
- `0x14009d8a4`
- `0x140104348`
- `0x14010ff8c`
- `0x1401358ff`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x140098c04`
- `0x140098d20`
- `0x140098ec8`
- `0x140098fc8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140098c5f`
- `ole32!CoTaskMemFree` at `0x140098c76`
- `ole32!CoTaskMemFree` at `0x140098c8d`
- `ole32!CoTaskMemFree` at `0x140098ca7`
- `ole32!CoTaskMemFree` at `0x140098cc4`
- `ole32!CoTaskMemFree` at `0x140098ce1`
- `ole32!CoTaskMemFree` at `0x140098cfe`
- `ole32!CoTaskMemFree` at `0x140098c5f`
- `ole32!CoTaskMemFree` at `0x140098c76`
- `ole32!CoTaskMemFree` at `0x140098c8d`
- `ole32!CoTaskMemFree` at `0x140098ca7`
- `ole32!CoTaskMemFree` at `0x140098cc4`
- `ole32!CoTaskMemFree` at `0x140098ce1`
- `ole32!CoTaskMemFree` at `0x140098cfe`

## pseudocode

```c
void __fastcall FreeBackupSetContents(struct _BLBCAT_BACKUP_SET_INFO *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( a1 )
  {
    CBLBCatalog::FreeComponents((struct _BLBCAT_COMPONENT_INFO **)a1 + 11, (unsigned int *)a1 + 20);
    CBLBCatalog::FreeTargets((struct _BLBCAT_TARGET_INFO **)a1 + 6, (unsigned int *)a1 + 10);
    CBLBCatalog::FreeVolumes((struct _BLBCAT_VOLUME_INFO **)a1 + 9, (unsigned int *)a1 + 16);
    v2 = (void *)*((_QWORD *)a1 + 2);
    if ( v2 )
    {
      CoTaskMemFree(v2);
      *((_QWORD *)a1 + 2) = 0;
    }
    v3 = (void *)*((_QWORD *)a1 + 4);
    if ( v3 )
    {
      CoTaskMemFree(v3);
      *((_QWORD *)a1 + 4) = 0;
    }
    v4 = (void *)*((_QWORD *)a1 + 7);
    if ( v4 )
    {
      CoTaskMemFree(v4);
      *((_QWORD *)a1 + 7) = 0;
    }
    v5 = (void *)*((_QWORD *)a1 + 16);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *((_QWORD *)a1 + 16) = 0;
    }
    v6 = (void *)*((_QWORD *)a1 + 17);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *((_QWORD *)a1 + 17) = 0;
    }
    v7 = (void *)*((_QWORD *)a1 + 19);
    if ( v7 )
    {
      CoTaskMemFree(v7);
      *((_QWORD *)a1 + 19) = 0;
    }
    v8 = (void *)*((_QWORD *)a1 + 22);
    if ( v8 )
      CoTaskMemFree(v8);
    memset_0(a1, 0, 0xD0u);
  }
  else
  {
    BlbAssert("base\\stor\\blb\\catalog\\catalog.cpp", 0x46Eu, "pBackupSet != NULL");
  }
}

```

## disassembly

```asm
0x140098c04  push    rbx
0x140098c06  sub     rsp, 20h
0x140098c0a  mov     rbx, rcx
0x140098c0d  test    rcx, rcx
0x140098c10  jnz     short loc_140098C2F
0x140098c12  lea     r8, aPbackupsetNull; "pBackupSet != NULL"
0x140098c19  mov     edx, 46Eh; unsigned int
0x140098c1e  lea     rcx, aBaseStorBlbCat_15; "base\\stor\\blb\\catalog\\catalog.cpp"
0x140098c25  add     rsp, 20h
0x140098c29  pop     rbx
0x140098c2a  jmp     ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140098c2f  lea     rdx, [rcx+50h]; unsigned int *
0x140098c33  add     rcx, 58h ; 'X'; struct _BLBCAT_COMPONENT_INFO **
0x140098c37  call    ?FreeComponents@CBLBCatalog@@SAXPEAPEAU_BLBCAT_COMPONENT_INFO@@PEAK@Z; CBLBCatalog::FreeComponents(_BLBCAT_COMPONENT_INFO * *,ulong *)
0x140098c3c  lea     rdx, [rbx+28h]; unsigned int *
0x140098c40  lea     rcx, [rbx+30h]; struct _BLBCAT_TARGET_INFO **
0x140098c44  call    ?FreeTargets@CBLBCatalog@@SAXPEAPEAU_BLBCAT_TARGET_INFO@@PEAK@Z; CBLBCatalog::FreeTargets(_BLBCAT_TARGET_INFO * *,ulong *)
0x140098c49  lea     rdx, [rbx+40h]; unsigned int *
0x140098c4d  lea     rcx, [rbx+48h]; struct _BLBCAT_VOLUME_INFO **
0x140098c51  call    ?FreeVolumes@CBLBCatalog@@SAXPEAPEAU_BLBCAT_VOLUME_INFO@@PEAK@Z; CBLBCatalog::FreeVolumes(_BLBCAT_VOLUME_INFO * *,ulong *)
0x140098c56  mov     rcx, [rbx+10h]; pv
0x140098c5a  test    rcx, rcx
0x140098c5d  jz      short loc_140098C6D
0x140098c5f  call    cs:__imp_CoTaskMemFree
0x140098c65  mov     qword ptr [rbx+10h], 0
0x140098c6d  mov     rcx, [rbx+20h]; pv
0x140098c71  test    rcx, rcx
0x140098c74  jz      short loc_140098C84
0x140098c76  call    cs:__imp_CoTaskMemFree
0x140098c7c  mov     qword ptr [rbx+20h], 0
0x140098c84  mov     rcx, [rbx+38h]; pv
0x140098c88  test    rcx, rcx
0x140098c8b  jz      short loc_140098C9B
0x140098c8d  call    cs:__imp_CoTaskMemFree
0x140098c93  mov     qword ptr [rbx+38h], 0
0x140098c9b  mov     rcx, [rbx+80h]; pv
0x140098ca2  test    rcx, rcx
0x140098ca5  jz      short loc_140098CB8
0x140098ca7  call    cs:__imp_CoTaskMemFree
0x140098cad  mov     qword ptr [rbx+80h], 0
0x140098cb8  mov     rcx, [rbx+88h]; pv
0x140098cbf  test    rcx, rcx
0x140098cc2  jz      short loc_140098CD5
0x140098cc4  call    cs:__imp_CoTaskMemFree
0x140098cca  mov     qword ptr [rbx+88h], 0
0x140098cd5  mov     rcx, [rbx+98h]; pv
0x140098cdc  test    rcx, rcx
0x140098cdf  jz      short loc_140098CF2
0x140098ce1  call    cs:__imp_CoTaskMemFree
0x140098ce7  mov     qword ptr [rbx+98h], 0
0x140098cf2  mov     rcx, [rbx+0B0h]; pv
0x140098cf9  test    rcx, rcx
0x140098cfc  jz      short loc_140098D04
0x140098cfe  call    cs:__imp_CoTaskMemFree
0x140098d04  xor     edx, edx; Val
0x140098d06  mov     r8d, 0D0h; Size
0x140098d0c  mov     rcx, rbx; void *
0x140098d0f  add     rsp, 20h
0x140098d13  pop     rbx
0x140098d14  jmp     memset_0
```
