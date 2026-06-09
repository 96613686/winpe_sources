# CleanUpBlbBackupSet(_BLB_BACKUP_SET_INFO *)

- ea: `0x18008e690`
- end: `0x18008e76c`
- name: `?CleanUpBlbBackupSet@@YAXPEAU_BLB_BACKUP_SET_INFO@@@Z`
- size: `220`
- prototype: `void __fastcall(struct _BLB_BACKUP_SET_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008ed44`

## callees

- `0x18008e690`
- `0x18008ea20`
- `0x18008edb0`
- `0x18008ee18`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008e6a5`
- `ole32!CoTaskMemFree` at `0x18008e6bd`
- `ole32!CoTaskMemFree` at `0x18008e6d5`
- `ole32!CoTaskMemFree` at `0x18008e6ed`
- `ole32!CoTaskMemFree` at `0x18008e705`
- `ole32!CoTaskMemFree` at `0x18008e740`
- `ole32!CoTaskMemFree` at `0x18008e6a5`
- `ole32!CoTaskMemFree` at `0x18008e6bd`
- `ole32!CoTaskMemFree` at `0x18008e6d5`
- `ole32!CoTaskMemFree` at `0x18008e6ed`
- `ole32!CoTaskMemFree` at `0x18008e705`
- `ole32!CoTaskMemFree` at `0x18008e740`

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
0x18008e690  test    rcx, rcx
0x18008e693  jz      locret_18008E76A
0x18008e699  push    rbx
0x18008e69a  sub     rsp, 20h
0x18008e69e  mov     rbx, rcx
0x18008e6a1  mov     rcx, [rcx+10h]; pv
0x18008e6a5  call    cs:__imp_CoTaskMemFree
0x18008e6ac  nop     dword ptr [rax+rax+00h]
0x18008e6b1  mov     rcx, [rbx+28h]; pv
0x18008e6b5  mov     qword ptr [rbx+10h], 0
0x18008e6bd  call    cs:__imp_CoTaskMemFree
0x18008e6c4  nop     dword ptr [rax+rax+00h]
0x18008e6c9  mov     rcx, [rbx+60h]; pv
0x18008e6cd  mov     qword ptr [rbx+28h], 0
0x18008e6d5  call    cs:__imp_CoTaskMemFree
0x18008e6dc  nop     dword ptr [rax+rax+00h]
0x18008e6e1  mov     rcx, [rbx+68h]; pv
0x18008e6e5  mov     qword ptr [rbx+60h], 0
0x18008e6ed  call    cs:__imp_CoTaskMemFree
0x18008e6f4  nop     dword ptr [rax+rax+00h]
0x18008e6f9  mov     rcx, [rbx+78h]; pv
0x18008e6fd  mov     qword ptr [rbx+68h], 0
0x18008e705  call    cs:__imp_CoTaskMemFree
0x18008e70c  nop     dword ptr [rax+rax+00h]
0x18008e711  lea     rdx, [rbx+30h]; unsigned int *
0x18008e715  mov     qword ptr [rbx+78h], 0
0x18008e71d  lea     rcx, [rbx+38h]; struct _BLB_VOLUME_INFO **
0x18008e721  call    ?FreeBlbVolumeInfoArray@@YAXPEAPEAU_BLB_VOLUME_INFO@@PEAK@Z; FreeBlbVolumeInfoArray(_BLB_VOLUME_INFO * *,ulong *)
0x18008e726  lea     rdx, [rbx+40h]; unsigned int *
0x18008e72a  lea     rcx, [rbx+48h]; struct _BLB_COMPONENT_INFO **
0x18008e72e  call    ?FreeBlbComponentInfoArray@@YAXPEAPEAU_BLB_COMPONENT_INFO@@PEAK@Z; FreeBlbComponentInfoArray(_BLB_COMPONENT_INFO * *,ulong *)
0x18008e733  mov     rcx, [rbx+20h]; struct _BLB_TARGET_INFO *
0x18008e737  call    ?CleanUpBlbTargetInfo@@YAXPEAU_BLB_TARGET_INFO@@@Z; CleanUpBlbTargetInfo(_BLB_TARGET_INFO *)
0x18008e73c  mov     rcx, [rbx+20h]; pv
0x18008e740  call    cs:__imp_CoTaskMemFree
0x18008e747  nop     dword ptr [rax+rax+00h]
0x18008e74c  mov     eax, 0A8h
0x18008e751  mov     qword ptr [rbx+20h], 0
0x18008e759  mov     byte ptr [rbx], 0
0x18008e75c  inc     rbx
0x18008e75f  sub     rax, 1
0x18008e763  jnz     short loc_18008E759
0x18008e765  add     rsp, 20h
0x18008e769  pop     rbx
0x18008e76a  retn
```
