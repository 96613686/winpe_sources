# RPCSplWOW64DocumentProperties

- ea: `0x14000dc10`
- end: `0x14000dcd7`
- name: `RPCSplWOW64DocumentProperties`
- size: `199`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, LPVOID lpTlsValue, unsigned __int64, unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int8 **, int, unsigned __int8 *, int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140006c10`
- `0x1400086e0`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000dc2c`
- `KERNEL32!TlsSetValue` at `0x14000dcc8`
- `KERNEL32!TlsSetValue` at `0x14000dc2c`
- `KERNEL32!TlsSetValue` at `0x14000dcc8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000dcba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000dcba`

## string_xrefs

- `0x14000dc35`: `clientProcessID %u pszPrinterName %ws`

## pseudocode

```c
BOOL __fastcall RPCSplWOW64DocumentProperties(
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
        unsigned int *a12)
{
  unsigned int v12; // ebx
  TLoad64BitDllsMgr *v16; // rcx
  signed int v18; // [rsp+30h] [rbp-58h]
  int Reply; // [rsp+98h] [rbp+10h] BYREF

  v12 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  SplWow64Telemetry::WriteDbgTraceInfo(
    "RPCSplWOW64DocumentProperties",
    L"clientProcessID %u pszPrinterName %ws",
    v12,
    a4);
  Reply = TLoad64BitDllsMgr::DocumentPropertiesW(v16, a3, a4, a5, a6, a7, v18, a9, a10, a11, a12);
  RpcAsyncCompleteCall(pAsync, &Reply);
  return TlsSetValue(g_GlobalTlsIndex, 0);
}

```

## disassembly

```asm
0x14000dc10  push    rbx
0x14000dc12  push    rbp
0x14000dc13  push    rsi
0x14000dc14  push    rdi
0x14000dc15  sub     rsp, 68h
0x14000dc19  mov     ebx, edx
0x14000dc1b  mov     rbp, rcx
0x14000dc1e  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000dc24  mov     rdi, r9
0x14000dc27  mov     edx, edx; lpTlsValue
0x14000dc29  mov     rsi, r8
0x14000dc2c  call    cs:__imp_TlsSetValue
0x14000dc32  mov     r9, rdi
0x14000dc35  lea     rdx, aClientprocessi_1; "clientProcessID %u pszPrinterName %ws"
0x14000dc3c  mov     r8d, ebx
0x14000dc3f  lea     rcx, aRpcsplwow64doc_0; "RPCSplWOW64DocumentProperties"
0x14000dc46  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000dc4b  mov     rax, [rsp+88h+arg_58]
0x14000dc53  mov     r8, rdi; unsigned __int16 *
0x14000dc56  mov     r9, [rsp+88h+arg_20]; unsigned int *
0x14000dc5e  mov     rdx, rsi; unsigned __int64
0x14000dc61  mov     [rsp+88h+var_38], rax; unsigned int *
0x14000dc66  mov     eax, [rsp+88h+arg_50]
0x14000dc6d  mov     [rsp+88h+var_40], eax; unsigned int
0x14000dc71  mov     eax, [rsp+88h+arg_48]
0x14000dc78  mov     [rsp+88h+var_48], eax; int
0x14000dc7c  mov     rax, [rsp+88h+arg_40]
0x14000dc84  mov     [rsp+88h+var_50], rax; unsigned __int8 *
0x14000dc89  mov     rax, [rsp+88h+arg_30]
0x14000dc91  mov     [rsp+88h+var_60], rax; unsigned __int8 **
0x14000dc96  mov     rax, [rsp+88h+arg_28]
0x14000dc9e  mov     [rsp+88h+var_68], rax; unsigned int *
0x14000dca3  call    ?DocumentPropertiesW@TLoad64BitDllsMgr@@QEAAJ_KPEAGPEAK2PEAPEAEKPEAEHK2@Z; TLoad64BitDllsMgr::DocumentPropertiesW(unsigned __int64,ushort *,ulong *,ulong *,uchar * *,ulong,uchar *,int,ulong,ulong *)
0x14000dca8  lea     rdx, [rsp+88h+Reply]; Reply
0x14000dcb0  mov     [rsp+88h+Reply], eax
0x14000dcb7  mov     rcx, rbp; pAsync
0x14000dcba  call    cs:__imp_RpcAsyncCompleteCall
0x14000dcc0  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000dcc6  xor     edx, edx; lpTlsValue
0x14000dcc8  call    cs:__imp_TlsSetValue
0x14000dcce  add     rsp, 68h
0x14000dcd2  pop     rdi
0x14000dcd3  pop     rsi
0x14000dcd4  pop     rbp
0x14000dcd5  pop     rbx
0x14000dcd6  retn
```
