# RPCSplWOW64PrintUIDocumentProperties

- ea: `0x14000df00`
- end: `0x14000dfd2`
- name: `RPCSplWOW64PrintUIDocumentProperties`
- size: `210`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, LPVOID lpTlsValue, unsigned __int64, unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int8 **, int, unsigned __int8 *, int, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400077fc`
- `0x1400086e0`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000df1c`
- `KERNEL32!TlsSetValue` at `0x14000dfc3`
- `KERNEL32!TlsSetValue` at `0x14000df1c`
- `KERNEL32!TlsSetValue` at `0x14000dfc3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000dfb5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000dfb5`

## string_xrefs

- `0x14000df25`: `clientProcessID %u pszPrinterName %ws`

## pseudocode

```c
BOOL __fastcall RPCSplWOW64PrintUIDocumentProperties(
        PRPC_ASYNC_STATE pAsync,
        LPVOID lpTlsValue,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        int a8,
        unsigned __int8 *a9,
        int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int *a13)
{
  unsigned int v13; // ebx
  TLoad64BitDllsMgr *v17; // rcx
  unsigned int v19; // [rsp+30h] [rbp-58h]
  int Reply; // [rsp+98h] [rbp+10h] BYREF

  v13 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  SplWow64Telemetry::WriteDbgTraceInfo(
    "RPCSplWOW64PrintUIDocumentProperties",
    L"clientProcessID %u pszPrinterName %ws",
    v13,
    a4);
  Reply = TLoad64BitDllsMgr::PrintUIDocumentProperties(v17, a3, a4, a5, a6, a7, v19, a9, a10, a11, a12, a13);
  RpcAsyncCompleteCall(pAsync, &Reply);
  return TlsSetValue(g_GlobalTlsIndex, 0);
}

```

## disassembly

```asm
0x14000df00  push    rbx
0x14000df02  push    rbp
0x14000df03  push    rsi
0x14000df04  push    rdi
0x14000df05  sub     rsp, 68h
0x14000df09  mov     ebx, edx
0x14000df0b  mov     rbp, rcx
0x14000df0e  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000df14  mov     rdi, r9
0x14000df17  mov     edx, edx; lpTlsValue
0x14000df19  mov     rsi, r8
0x14000df1c  call    cs:__imp_TlsSetValue
0x14000df22  mov     r9, rdi
0x14000df25  lea     rdx, aClientprocessi_1; "clientProcessID %u pszPrinterName %ws"
0x14000df2c  mov     r8d, ebx
0x14000df2f  lea     rcx, aRpcsplwow64pri_0; "RPCSplWOW64PrintUIDocumentProperties"
0x14000df36  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000df3b  mov     rax, [rsp+88h+arg_60]
0x14000df43  mov     r8, rdi; unsigned __int16 *
0x14000df46  mov     r9, [rsp+88h+arg_20]; unsigned int *
0x14000df4e  mov     rdx, rsi; unsigned __int64
0x14000df51  mov     [rsp+88h+var_30], rax; unsigned int *
0x14000df56  mov     eax, [rsp+88h+arg_58]
0x14000df5d  mov     [rsp+88h+var_38], eax; unsigned int
0x14000df61  mov     eax, [rsp+88h+arg_50]
0x14000df68  mov     [rsp+88h+var_40], eax; unsigned int
0x14000df6c  mov     eax, [rsp+88h+arg_48]
0x14000df73  mov     [rsp+88h+var_48], eax; int
0x14000df77  mov     rax, [rsp+88h+arg_40]
0x14000df7f  mov     [rsp+88h+var_50], rax; unsigned __int8 *
0x14000df84  mov     rax, [rsp+88h+arg_30]
0x14000df8c  mov     [rsp+88h+var_60], rax; unsigned __int8 **
0x14000df91  mov     rax, [rsp+88h+arg_28]
0x14000df99  mov     [rsp+88h+var_68], rax; unsigned int *
0x14000df9e  call    ?PrintUIDocumentProperties@TLoad64BitDllsMgr@@QEAAJ_KPEAGPEAK2PEAPEAEKPEAEHKK2@Z; TLoad64BitDllsMgr::PrintUIDocumentProperties(unsigned __int64,ushort *,ulong *,ulong *,uchar * *,ulong,uchar *,int,ulong,ulong,ulong *)
0x14000dfa3  lea     rdx, [rsp+88h+Reply]; Reply
0x14000dfab  mov     [rsp+88h+Reply], eax
0x14000dfb2  mov     rcx, rbp; pAsync
0x14000dfb5  call    cs:__imp_RpcAsyncCompleteCall
0x14000dfbb  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000dfc1  xor     edx, edx; lpTlsValue
0x14000dfc3  call    cs:__imp_TlsSetValue
0x14000dfc9  add     rsp, 68h
0x14000dfcd  pop     rdi
0x14000dfce  pop     rsi
0x14000dfcf  pop     rbp
0x14000dfd0  pop     rbx
0x14000dfd1  retn
```
