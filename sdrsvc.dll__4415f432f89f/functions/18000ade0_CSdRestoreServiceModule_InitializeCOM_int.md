# CSdRestoreServiceModule::InitializeCOM(int)

- ea: `0x18000ade0`
- end: `0x18000ae7f`
- name: `?InitializeCOM@CSdRestoreServiceModule@@QEAAJH@Z`
- size: `159`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ac34`
- `0x18000e800`
- `0x18000e890`

## callees

- `0x18000ade0`
- `0x18001586c`
- `0x180015974`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae4e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000ae10`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000ae10`

## string_xrefs

- `0x18000adf1`: `CSdRestoreServiceModule::InitializeCOM`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::InitializeCOM(CSdRestoreServiceModule *this, int a2)
{
  HRESULT v3; // eax
  unsigned int v4; // edi
  DWORD CurrentThreadId; // eax
  HRESULT v7; // [rsp+20h] [rbp-48h] BYREF
  __int16 v8; // [rsp+24h] [rbp-44h]
  __int16 v9; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "CSdRestoreServiceModule::InitializeCOM", 244, 1);
  v3 = CoInitializeEx(0, 0xCu);
  v7 = v3;
  v4 = v3;
  if ( a2 && v3 == -2147417850 )
  {
    v4 = 0;
    v7 = 0;
    v8 = 251;
  }
  else if ( v3 >= 0 )
  {
    v8 = 253;
    CurrentThreadId = GetCurrentThreadId();
    v4 = v7;
    dword_18002E204 = CurrentThreadId;
    dword_18002E20C = 1;
  }
  else
  {
    v9 = 253;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return v4;
}

```

## disassembly

```asm
0x18000ade0  mov     [rsp+arg_0], rbx
0x18000ade5  push    rdi
0x18000ade6  sub     rsp, 60h
0x18000adea  mov     ebx, edx
0x18000adec  lea     rcx, [rsp+68h+var_48]; this
0x18000adf1  lea     rdx, aCsdrestoreserv_8; "CSdRestoreServiceModule::InitializeCOM"
0x18000adf8  mov     r9d, 1; unsigned __int16
0x18000adfe  mov     r8d, 0F4h; unsigned __int16
0x18000ae04  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ae09  mov     edx, 0Ch; dwCoInit
0x18000ae0e  xor     ecx, ecx; pvReserved
0x18000ae10  call    cs:__imp_CoInitializeEx
0x18000ae16  mov     [rsp+68h+var_48], eax
0x18000ae1a  mov     edi, eax
0x18000ae1c  test    ebx, ebx
0x18000ae1e  jz      short loc_18000AE39
0x18000ae20  cmp     eax, 80010106h
0x18000ae25  jnz     short loc_18000AE39
0x18000ae27  xor     edi, edi
0x18000ae29  mov     eax, 0FBh
0x18000ae2e  mov     [rsp+68h+var_48], edi
0x18000ae32  mov     [rsp+68h+var_44], ax
0x18000ae37  jmp     short loc_18000AE68
0x18000ae39  test    eax, eax
0x18000ae3b  mov     eax, 0FDh
0x18000ae40  jns     short loc_18000AE49
0x18000ae42  mov     [rsp+68h+var_42], ax
0x18000ae47  jmp     short loc_18000AE68
0x18000ae49  mov     [rsp+68h+var_44], ax
0x18000ae4e  call    cs:__imp_GetCurrentThreadId
0x18000ae54  mov     edi, [rsp+68h+var_48]
0x18000ae58  mov     cs:dword_18002E204, eax
0x18000ae5e  mov     cs:dword_18002E20C, 1
0x18000ae68  lea     rcx, [rsp+68h+var_48]; this
0x18000ae6d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ae72  mov     rbx, [rsp+68h+arg_0]
0x18000ae77  mov     eax, edi
0x18000ae79  add     rsp, 60h
0x18000ae7d  pop     rdi
0x18000ae7e  retn
```
