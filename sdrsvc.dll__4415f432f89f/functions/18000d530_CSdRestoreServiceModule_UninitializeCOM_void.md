# CSdRestoreServiceModule::UninitializeCOM(void)

- ea: `0x18000d530`
- end: `0x18000d594`
- name: `?UninitializeCOM@CSdRestoreServiceModule@@QEAAJXZ`
- size: `100`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d0a0`
- `0x18000e800`
- `0x18000e890`

## callees

- `0x18000d530`
- `0x18001586c`
- `0x180015974`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d56e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d56e`

## string_xrefs

- `0x18000d53c`: `CSdRestoreServiceModule::UninitializeCOM`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::UninitializeCOM(CSdRestoreServiceModule *this)
{
  unsigned int v1; // ebx
  unsigned int v3; // [rsp+20h] [rbp-48h] BYREF
  __int16 v4; // [rsp+24h] [rbp-44h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v3, "CSdRestoreServiceModule::UninitializeCOM", 280, 1);
  if ( dword_18002E20C )
  {
    CoUninitialize();
    v1 = v3;
    dword_18002E20C = 0;
  }
  else
  {
    v1 = 0;
    v3 = 0;
    v4 = 284;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v3);
  return v1;
}

```

## disassembly

```asm
0x18000d530  push    rbx
0x18000d532  sub     rsp, 60h
0x18000d536  mov     r9d, 1; unsigned __int16
0x18000d53c  lea     rdx, aCsdrestoreserv_7; "CSdRestoreServiceModule::UninitializeCO"...
0x18000d543  mov     r8d, 118h; unsigned __int16
0x18000d549  lea     rcx, [rsp+68h+var_48]; this
0x18000d54e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d553  cmp     cs:dword_18002E20C, 0
0x18000d55a  jnz     short loc_18000D56E
0x18000d55c  xor     ebx, ebx
0x18000d55e  mov     eax, 11Ch
0x18000d563  mov     [rsp+68h+var_48], ebx
0x18000d567  mov     [rsp+68h+var_44], ax
0x18000d56c  jmp     short loc_18000D582
0x18000d56e  call    cs:__imp_CoUninitialize
0x18000d574  mov     ebx, [rsp+68h+var_48]
0x18000d578  mov     cs:dword_18002E20C, 0
0x18000d582  lea     rcx, [rsp+68h+var_48]; this
0x18000d587  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d58c  mov     eax, ebx
0x18000d58e  add     rsp, 60h
0x18000d592  pop     rbx
0x18000d593  retn
```
