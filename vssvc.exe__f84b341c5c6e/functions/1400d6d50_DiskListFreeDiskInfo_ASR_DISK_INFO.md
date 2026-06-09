# DiskListFreeDiskInfo(_ASR_DISK_INFO *)

- ea: `0x1400d6d50`
- end: `0x1400d6e3b`
- name: `?DiskListFreeDiskInfo@@YAPEAU_ASR_DISK_INFO@@PEAU1@@Z`
- size: `235`
- prototype: `struct _ASR_DISK_INFO *__fastcall(struct _ASR_DISK_INFO *pv)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140021558`
- `0x140043d68`
- `0x1400d6d0c`
- `0x1400d6e44`

## callees

- `0x14005ab34`
- `0x1400d6d50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6d94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6db5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6deb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6dfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6e29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6d94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6db5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6deb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6dfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6e29`

## pseudocode

```c
struct _ASR_DISK_INFO *__fastcall DiskListFreeDiskInfo(struct _ASR_DISK_INFO *pv)
{
  __int64 v1; // rsi
  __int64 v3; // rax
  __int64 v4; // rbp
  __int64 v5; // rbx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  v1 = 0;
  if ( pv )
  {
    v1 = *(_QWORD *)pv;
    if ( *((_QWORD *)pv + 5) )
    {
      v3 = *((_QWORD *)pv + 2);
      if ( v3 )
      {
        v4 = 0;
        if ( *(_DWORD *)(v3 + 4) )
        {
          do
          {
            v5 = 3 * v4;
            CoTaskMemFree(*(LPVOID *)(*((_QWORD *)pv + 5) + 24 * v4));
            v4 = (unsigned int)(v4 + 1);
            *(_QWORD *)(*((_QWORD *)pv + 5) + 8 * v5) = 0;
          }
          while ( (unsigned int)v4 < *(_DWORD *)(*((_QWORD *)pv + 2) + 4LL) );
        }
      }
    }
    CoTaskMemFree(*((LPVOID *)pv + 1));
    v6 = (void *)*((_QWORD *)pv + 2);
    *((_QWORD *)pv + 1) = 0;
    CoTaskMemFree(v6);
    v7 = (void *)*((_QWORD *)pv + 3);
    *((_QWORD *)pv + 2) = 0;
    CoTaskMemFree(v7);
    v8 = (void *)*((_QWORD *)pv + 4);
    *((_QWORD *)pv + 3) = 0;
    CoTaskMemFree(v8);
    v9 = (void *)*((_QWORD *)pv + 6);
    *((_QWORD *)pv + 4) = 0;
    CoTaskMemFree(v9);
    v10 = (void *)*((_QWORD *)pv + 5);
    *((_QWORD *)pv + 6) = 0;
    CoTaskMemFree(v10);
    *((_QWORD *)pv + 5) = 0;
    AsrFreeVirtualDiskInfo((struct _ASR_VIRTUAL_DISK_INFO **)pv + 14);
    CoTaskMemFree(pv);
  }
  return (struct _ASR_DISK_INFO *)v1;
}

```

## disassembly

```asm
0x1400d6d50  push    rbx
0x1400d6d52  push    rbp
0x1400d6d53  push    rsi
0x1400d6d54  push    rdi
0x1400d6d55  sub     rsp, 28h
0x1400d6d59  xor     esi, esi
0x1400d6d5b  mov     rdi, rcx
0x1400d6d5e  test    rcx, rcx
0x1400d6d61  jz      loc_1400D6E2F
0x1400d6d67  cmp     qword ptr [rcx+28h], 0
0x1400d6d6c  mov     rsi, [rcx]
0x1400d6d6f  jz      short loc_1400D6DB1
0x1400d6d71  mov     rax, [rcx+10h]
0x1400d6d75  test    rax, rax
0x1400d6d78  jz      short loc_1400D6DB1
0x1400d6d7a  xor     ebp, ebp
0x1400d6d7c  cmp     [rax+4], ebp
0x1400d6d7f  jbe     short loc_1400D6DB1
0x1400d6d81  mov     rcx, [rdi+28h]
0x1400d6d85  lea     rbx, ds:0[rbp*2]
0x1400d6d8d  add     rbx, rbp
0x1400d6d90  mov     rcx, [rcx+rbx*8]; pv
0x1400d6d94  call    cs:__imp_CoTaskMemFree
0x1400d6d9a  mov     rax, [rdi+28h]
0x1400d6d9e  inc     ebp
0x1400d6da0  mov     qword ptr [rax+rbx*8], 0
0x1400d6da8  mov     rax, [rdi+10h]
0x1400d6dac  cmp     ebp, [rax+4]
0x1400d6daf  jb      short loc_1400D6D81
0x1400d6db1  mov     rcx, [rdi+8]; pv
0x1400d6db5  call    cs:__imp_CoTaskMemFree
0x1400d6dbb  mov     rcx, [rdi+10h]; pv
0x1400d6dbf  mov     qword ptr [rdi+8], 0
0x1400d6dc7  call    cs:__imp_CoTaskMemFree
0x1400d6dcd  mov     rcx, [rdi+18h]; pv
0x1400d6dd1  mov     qword ptr [rdi+10h], 0
0x1400d6dd9  call    cs:__imp_CoTaskMemFree
0x1400d6ddf  mov     rcx, [rdi+20h]; pv
0x1400d6de3  mov     qword ptr [rdi+18h], 0
0x1400d6deb  call    cs:__imp_CoTaskMemFree
0x1400d6df1  mov     rcx, [rdi+30h]; pv
0x1400d6df5  mov     qword ptr [rdi+20h], 0
0x1400d6dfd  call    cs:__imp_CoTaskMemFree
0x1400d6e03  mov     rcx, [rdi+28h]; pv
0x1400d6e07  mov     qword ptr [rdi+30h], 0
0x1400d6e0f  call    cs:__imp_CoTaskMemFree
0x1400d6e15  lea     rcx, [rdi+70h]; struct _ASR_VIRTUAL_DISK_INFO **
0x1400d6e19  mov     qword ptr [rdi+28h], 0
0x1400d6e21  call    ?AsrFreeVirtualDiskInfo@@YAXPEAPEAU_ASR_VIRTUAL_DISK_INFO@@@Z; AsrFreeVirtualDiskInfo(_ASR_VIRTUAL_DISK_INFO * *)
0x1400d6e26  mov     rcx, rdi; pv
0x1400d6e29  call    cs:__imp_CoTaskMemFree
0x1400d6e2f  mov     rax, rsi
0x1400d6e32  add     rsp, 28h
0x1400d6e36  pop     rdi
0x1400d6e37  pop     rsi
0x1400d6e38  pop     rbp
0x1400d6e39  pop     rbx
0x1400d6e3a  retn
```
