# CleanUpBlbVolumeInfo(_BLB_VOLUME_INFO *)

- ea: `0x18008ec84`
- end: `0x18008ed3d`
- name: `?CleanUpBlbVolumeInfo@@YAXPEAU_BLB_VOLUME_INFO@@@Z`
- size: `185`
- prototype: `void __fastcall(struct _BLB_VOLUME_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18008ee18`

## callees

- `0x18008ec84`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18008ec99`
- `ole32!CoTaskMemFree` at `0x18008ecb1`
- `ole32!CoTaskMemFree` at `0x18008ecc9`
- `ole32!CoTaskMemFree` at `0x18008ece1`
- `ole32!CoTaskMemFree` at `0x18008ecf9`
- `ole32!CoTaskMemFree` at `0x18008ed11`
- `ole32!CoTaskMemFree` at `0x18008ec99`
- `ole32!CoTaskMemFree` at `0x18008ecb1`
- `ole32!CoTaskMemFree` at `0x18008ecc9`
- `ole32!CoTaskMemFree` at `0x18008ece1`
- `ole32!CoTaskMemFree` at `0x18008ecf9`
- `ole32!CoTaskMemFree` at `0x18008ed11`

## pseudocode

```c
void __fastcall CleanUpBlbVolumeInfo(LPVOID *a1)
{
  LPVOID *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rax

  if ( a1 )
  {
    v1 = a1;
    CoTaskMemFree(a1[2]);
    v2 = v1[3];
    v1[2] = 0;
    CoTaskMemFree(v2);
    v3 = v1[4];
    v1[3] = 0;
    CoTaskMemFree(v3);
    v4 = v1[5];
    v1[4] = 0;
    CoTaskMemFree(v4);
    v5 = v1[6];
    v1[5] = 0;
    CoTaskMemFree(v5);
    v6 = v1[12];
    v1[6] = 0;
    CoTaskMemFree(v6);
    v7 = 128;
    v1[12] = 0;
    do
    {
      *(_BYTE *)v1 = 0;
      v1 = (LPVOID *)((char *)v1 + 1);
      --v7;
    }
    while ( v7 );
  }
}

```

## disassembly

```asm
0x18008ec84  test    rcx, rcx
0x18008ec87  jz      locret_18008ED3B
0x18008ec8d  push    rbx
0x18008ec8e  sub     rsp, 20h
0x18008ec92  mov     rbx, rcx
0x18008ec95  mov     rcx, [rcx+10h]; pv
0x18008ec99  call    cs:__imp_CoTaskMemFree
0x18008eca0  nop     dword ptr [rax+rax+00h]
0x18008eca5  mov     rcx, [rbx+18h]; pv
0x18008eca9  mov     qword ptr [rbx+10h], 0
0x18008ecb1  call    cs:__imp_CoTaskMemFree
0x18008ecb8  nop     dword ptr [rax+rax+00h]
0x18008ecbd  mov     rcx, [rbx+20h]; pv
0x18008ecc1  mov     qword ptr [rbx+18h], 0
0x18008ecc9  call    cs:__imp_CoTaskMemFree
0x18008ecd0  nop     dword ptr [rax+rax+00h]
0x18008ecd5  mov     rcx, [rbx+28h]; pv
0x18008ecd9  mov     qword ptr [rbx+20h], 0
0x18008ece1  call    cs:__imp_CoTaskMemFree
0x18008ece8  nop     dword ptr [rax+rax+00h]
0x18008eced  mov     rcx, [rbx+30h]; pv
0x18008ecf1  mov     qword ptr [rbx+28h], 0
0x18008ecf9  call    cs:__imp_CoTaskMemFree
0x18008ed00  nop     dword ptr [rax+rax+00h]
0x18008ed05  mov     rcx, [rbx+60h]; pv
0x18008ed09  mov     qword ptr [rbx+30h], 0
0x18008ed11  call    cs:__imp_CoTaskMemFree
0x18008ed18  nop     dword ptr [rax+rax+00h]
0x18008ed1d  mov     eax, 80h
0x18008ed22  mov     qword ptr [rbx+60h], 0
0x18008ed2a  mov     byte ptr [rbx], 0
0x18008ed2d  inc     rbx
0x18008ed30  sub     rax, 1
0x18008ed34  jnz     short loc_18008ED2A
0x18008ed36  add     rsp, 20h
0x18008ed3a  pop     rbx
0x18008ed3b  retn
```
