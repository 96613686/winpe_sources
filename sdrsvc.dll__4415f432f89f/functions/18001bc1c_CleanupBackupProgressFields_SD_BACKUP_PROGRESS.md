# CleanupBackupProgressFields(SD_BACKUP_PROGRESS *)

- ea: `0x18001bc1c`
- end: `0x18001bc71`
- name: `?CleanupBackupProgressFields@@YAJPEAUSD_BACKUP_PROGRESS@@@Z`
- size: `85`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fc50`
- `0x180012948`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001bc1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bc49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bc49`

## pseudocode

```c
__int64 __fastcall CleanupBackupProgressFields(LPVOID *a1)
{
  unsigned int v2; // ebx
  _DWORD v4[18]; // [rsp+20h] [rbp-48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v4, "CleanupBackupProgressFields", 80, 1);
  if ( a1 )
  {
    CoTaskMemFree(a1[1]);
    *(_OWORD *)a1 = 0;
    a1[2] = 0;
  }
  v2 = v4[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v4);
  return v2;
}

```

## disassembly

```asm
0x18001bc1c  push    rbx
0x18001bc1e  sub     rsp, 60h
0x18001bc22  mov     r9d, 1; unsigned __int16
0x18001bc28  lea     rdx, aCleanupbackupp; "CleanupBackupProgressFields"
0x18001bc2f  mov     rbx, rcx
0x18001bc32  lea     rcx, [rsp+68h+var_48]; this
0x18001bc37  lea     r8d, [r9+4Fh]; unsigned __int16
0x18001bc3b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001bc40  test    rbx, rbx
0x18001bc43  jz      short loc_18001BC5B
0x18001bc45  mov     rcx, [rbx+8]; pv
0x18001bc49  call    cs:__imp_CoTaskMemFree
0x18001bc4f  xorps   xmm0, xmm0
0x18001bc52  xor     eax, eax
0x18001bc54  movups  xmmword ptr [rbx], xmm0
0x18001bc57  mov     [rbx+10h], rax
0x18001bc5b  mov     ebx, [rsp+68h+var_48]
0x18001bc5f  lea     rcx, [rsp+68h+var_48]; this
0x18001bc64  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001bc69  mov     eax, ebx
0x18001bc6b  add     rsp, 60h
0x18001bc6f  pop     rbx
0x18001bc70  retn
```
