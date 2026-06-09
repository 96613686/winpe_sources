# CleanUpBlbBackupSet(_BLB_BACKUP_SET_INFO *)

- ea: `0x18008aa5c`
- end: `0x18008ab13`
- name: `?CleanUpBlbBackupSet@@YAXPEAU_BLB_BACKUP_SET_INFO@@@Z`
- size: `183`
- prototype: `void __fastcall(struct _BLB_BACKUP_SET_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008afdc`

## callees

- `0x18008aa5c`
- `0x18008ad48`
- `0x18008b040`
- `0x18008b0a4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008aa71`
- `ole32!CoTaskMemFree` at `0x18008aa83`
- `ole32!CoTaskMemFree` at `0x18008aa95`
- `ole32!CoTaskMemFree` at `0x18008aaa7`
- `ole32!CoTaskMemFree` at `0x18008aab9`
- `ole32!CoTaskMemFree` at `0x18008aaee`
- `ole32!CoTaskMemFree` at `0x18008aa71`
- `ole32!CoTaskMemFree` at `0x18008aa83`
- `ole32!CoTaskMemFree` at `0x18008aa95`
- `ole32!CoTaskMemFree` at `0x18008aaa7`
- `ole32!CoTaskMemFree` at `0x18008aab9`
- `ole32!CoTaskMemFree` at `0x18008aaee`

## pseudocode

```c
void __fastcall CleanUpBlbBackupSet(LPVOID *a1)
{
  LPVOID *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rax

  if ( a1 )
  {
    v1 = a1;
    CoTaskMemFree(a1[2]);
    v2 = v1[5];
    v1[2] = 0;
    CoTaskMemFree(v2);
    v3 = v1[12];
    v1[5] = 0;
    CoTaskMemFree(v3);
    v4 = v1[13];
    v1[12] = 0;
    CoTaskMemFree(v4);
    v5 = v1[15];
    v1[13] = 0;
    CoTaskMemFree(v5);
    v1[15] = 0;
    FreeBlbVolumeInfoArray((struct _BLB_VOLUME_INFO **)v1 + 7, (unsigned int *)v1 + 12);
    FreeBlbComponentInfoArray((struct _BLB_COMPONENT_INFO **)v1 + 9, (unsigned int *)v1 + 16);
    CleanUpBlbTargetInfo((struct _BLB_TARGET_INFO *)v1[4]);
    CoTaskMemFree(v1[4]);
    v6 = 168;
    v1[4] = 0;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (LPVOID *)((char *)v1 + 1);
      --v6;
    }
    while ( v6 );
  }
}

```

## disassembly

```asm
0x18008aa5c  test    rcx, rcx
0x18008aa5f  jz      locret_18008AB12
0x18008aa65  push    rbx
0x18008aa66  sub     rsp, 20h
0x18008aa6a  mov     rbx, rcx
0x18008aa6d  mov     rcx, [rcx+10h]; pv
0x18008aa71  call    cs:__imp_CoTaskMemFree
0x18008aa77  mov     rcx, [rbx+28h]; pv
0x18008aa7b  mov     qword ptr [rbx+10h], 0
0x18008aa83  call    cs:__imp_CoTaskMemFree
0x18008aa89  mov     rcx, [rbx+60h]; pv
0x18008aa8d  mov     qword ptr [rbx+28h], 0
0x18008aa95  call    cs:__imp_CoTaskMemFree
0x18008aa9b  mov     rcx, [rbx+68h]; pv
0x18008aa9f  mov     qword ptr [rbx+60h], 0
0x18008aaa7  call    cs:__imp_CoTaskMemFree
0x18008aaad  mov     rcx, [rbx+78h]; pv
0x18008aab1  mov     qword ptr [rbx+68h], 0
0x18008aab9  call    cs:__imp_CoTaskMemFree
0x18008aabf  lea     rdx, [rbx+30h]; unsigned int *
0x18008aac3  mov     qword ptr [rbx+78h], 0
0x18008aacb  lea     rcx, [rbx+38h]; struct _BLB_VOLUME_INFO **
0x18008aacf  call    ?FreeBlbVolumeInfoArray@@YAXPEAPEAU_BLB_VOLUME_INFO@@PEAK@Z; FreeBlbVolumeInfoArray(_BLB_VOLUME_INFO * *,ulong *)
0x18008aad4  lea     rdx, [rbx+40h]; unsigned int *
0x18008aad8  lea     rcx, [rbx+48h]; struct _BLB_COMPONENT_INFO **
0x18008aadc  call    ?FreeBlbComponentInfoArray@@YAXPEAPEAU_BLB_COMPONENT_INFO@@PEAK@Z; FreeBlbComponentInfoArray(_BLB_COMPONENT_INFO * *,ulong *)
0x18008aae1  mov     rcx, [rbx+20h]; struct _BLB_TARGET_INFO *
0x18008aae5  call    ?CleanUpBlbTargetInfo@@YAXPEAU_BLB_TARGET_INFO@@@Z; CleanUpBlbTargetInfo(_BLB_TARGET_INFO *)
0x18008aaea  mov     rcx, [rbx+20h]; pv
0x18008aaee  call    cs:__imp_CoTaskMemFree
0x18008aaf4  mov     eax, 0A8h
0x18008aaf9  mov     qword ptr [rbx+20h], 0
0x18008ab01  mov     byte ptr [rbx], 0
0x18008ab04  inc     rbx
0x18008ab07  sub     rax, 1
0x18008ab0b  jnz     short loc_18008AB01
0x18008ab0d  add     rsp, 20h
0x18008ab11  pop     rbx
0x18008ab12  retn
```
