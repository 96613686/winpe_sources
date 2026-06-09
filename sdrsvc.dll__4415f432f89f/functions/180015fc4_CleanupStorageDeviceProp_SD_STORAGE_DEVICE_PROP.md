# CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)

- ea: `0x180015fc4`
- end: `0x1800160bf`
- name: `?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `251`
- prototype: `void __fastcall(struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800101c0`
- `0x180011760`
- `0x180012948`
- `0x180014184`
- `0x18001445c`
- `0x180017f18`

## callees

- `0x180015fc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015feb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016045`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001605a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015feb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016045`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001605a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016096`

## pseudocode

```c
void __fastcall CleanupStorageDeviceProp(struct _SD_STORAGE_DEVICE_PROP *a1)
{
  LPVOID *v1; // rdi
  LPVOID *v2; // rbx
  LPVOID *v3; // rdi
  LPVOID *v4; // rdi
  LPVOID *v5; // rdi
  LPVOID *v6; // rdi
  LPVOID *v7; // rdi
  __int64 v8; // rax

  if ( a1 )
  {
    v1 = (LPVOID *)((char *)a1 + 24);
    v2 = (LPVOID *)a1;
    if ( a1 != (struct _SD_STORAGE_DEVICE_PROP *)-24LL && *v1 )
    {
      CoTaskMemFree(*v1);
      *v1 = 0;
    }
    v3 = v2 + 4;
    if ( v2 != (LPVOID *)-32LL && *v3 )
    {
      CoTaskMemFree(*v3);
      *v3 = 0;
    }
    v4 = v2 + 5;
    if ( v2 != (LPVOID *)-40LL && *v4 )
    {
      CoTaskMemFree(*v4);
      *v4 = 0;
    }
    v5 = v2 + 6;
    if ( v2 != (LPVOID *)-48LL && *v5 )
    {
      CoTaskMemFree(*v5);
      *v5 = 0;
    }
    if ( *v2 )
    {
      CoTaskMemFree(*v2);
      *v2 = 0;
    }
    v6 = v2 + 1;
    if ( v2 != (LPVOID *)-8LL && *v6 )
    {
      CoTaskMemFree(*v6);
      *v6 = 0;
    }
    v7 = v2 + 2;
    if ( v2 != (LPVOID *)-16LL && *v7 )
    {
      CoTaskMemFree(*v7);
      *v7 = 0;
    }
    v8 = 144;
    do
    {
      *(_BYTE *)v2 = 0;
      v2 = (LPVOID *)((char *)v2 + 1);
      --v8;
    }
    while ( v8 );
  }
}

```

## disassembly

```asm
0x180015fc4  test    rcx, rcx
0x180015fc7  jz      locret_1800160BE
0x180015fcd  mov     [rsp+arg_0], rbx
0x180015fd2  push    rdi
0x180015fd3  sub     rsp, 20h
0x180015fd7  lea     rdi, [rcx+18h]
0x180015fdb  mov     rbx, rcx
0x180015fde  test    rdi, rdi
0x180015fe1  jz      short loc_180015FF8
0x180015fe3  mov     rcx, [rdi]; pv
0x180015fe6  test    rcx, rcx
0x180015fe9  jz      short loc_180015FF8
0x180015feb  call    cs:__imp_CoTaskMemFree
0x180015ff1  mov     qword ptr [rdi], 0
0x180015ff8  lea     rdi, [rbx+20h]
0x180015ffc  test    rdi, rdi
0x180015fff  jz      short loc_180016016
0x180016001  mov     rcx, [rdi]; pv
0x180016004  test    rcx, rcx
0x180016007  jz      short loc_180016016
0x180016009  call    cs:__imp_CoTaskMemFree
0x18001600f  mov     qword ptr [rdi], 0
0x180016016  lea     rdi, [rbx+28h]
0x18001601a  test    rdi, rdi
0x18001601d  jz      short loc_180016034
0x18001601f  mov     rcx, [rdi]; pv
0x180016022  test    rcx, rcx
0x180016025  jz      short loc_180016034
0x180016027  call    cs:__imp_CoTaskMemFree
0x18001602d  mov     qword ptr [rdi], 0
0x180016034  lea     rdi, [rbx+30h]
0x180016038  test    rdi, rdi
0x18001603b  jz      short loc_180016052
0x18001603d  mov     rcx, [rdi]; pv
0x180016040  test    rcx, rcx
0x180016043  jz      short loc_180016052
0x180016045  call    cs:__imp_CoTaskMemFree
0x18001604b  mov     qword ptr [rdi], 0
0x180016052  mov     rcx, [rbx]; pv
0x180016055  test    rcx, rcx
0x180016058  jz      short loc_180016067
0x18001605a  call    cs:__imp_CoTaskMemFree
0x180016060  mov     qword ptr [rbx], 0
0x180016067  lea     rdi, [rbx+8]
0x18001606b  test    rdi, rdi
0x18001606e  jz      short loc_180016085
0x180016070  mov     rcx, [rdi]; pv
0x180016073  test    rcx, rcx
0x180016076  jz      short loc_180016085
0x180016078  call    cs:__imp_CoTaskMemFree
0x18001607e  mov     qword ptr [rdi], 0
0x180016085  lea     rdi, [rbx+10h]
0x180016089  test    rdi, rdi
0x18001608c  jz      short loc_1800160A3
0x18001608e  mov     rcx, [rdi]; pv
0x180016091  test    rcx, rcx
0x180016094  jz      short loc_1800160A3
0x180016096  call    cs:__imp_CoTaskMemFree
0x18001609c  mov     qword ptr [rdi], 0
0x1800160a3  mov     eax, 90h
0x1800160a8  mov     byte ptr [rbx], 0
0x1800160ab  inc     rbx
0x1800160ae  sub     rax, 1
0x1800160b2  jnz     short loc_1800160A8
0x1800160b4  mov     rbx, [rsp+28h+arg_0]
0x1800160b9  add     rsp, 20h
0x1800160bd  pop     rdi
0x1800160be  retn
```
