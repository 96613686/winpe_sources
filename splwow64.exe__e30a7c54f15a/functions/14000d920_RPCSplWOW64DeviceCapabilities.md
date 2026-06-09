# RPCSplWOW64DeviceCapabilities

- ea: `0x14000d920`
- end: `0x14000d9cc`
- name: `RPCSplWOW64DeviceCapabilities`
- size: `172`
- prototype: `__int64 __usercall@<rax>(LPVOID lpTlsValue@<rcx>, unsigned __int16 *@<rdx>, int, unsigned __int8 *, int, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1400069b8`
- `0x1400086e0`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000d940`
- `KERNEL32!TlsSetValue` at `0x14000d9b4`
- `KERNEL32!TlsSetValue` at `0x14000d940`
- `KERNEL32!TlsSetValue` at `0x14000d9b4`

## string_xrefs

- `0x14000d949`: `clientProcessID %u pszDeviceName %ws`

## pseudocode

```c
__int64 __fastcall RPCSplWOW64DeviceCapabilities(
        LPVOID lpTlsValue,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 a4,
        int a5,
        unsigned __int8 *a6,
        int a7,
        unsigned int *a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  unsigned int v11; // ebx
  TLoad64BitDllsMgr *v13; // rcx
  unsigned __int16 *v14; // r8
  unsigned int v15; // ebx
  unsigned int v17; // [rsp+20h] [rbp-38h]

  v11 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  SplWow64Telemetry::WriteDbgTraceInfo(
    "RPCSplWOW64DeviceCapabilities",
    L"clientProcessID %u pszDeviceName %ws",
    v11,
    a2);
  v15 = TLoad64BitDllsMgr::DeviceCapabilitiesW(v13, a2, v14, a4, v17, a6, a7, a8, a9, a10);
  TlsSetValue(g_GlobalTlsIndex, 0);
  return v15;
}

```

## disassembly

```asm
0x14000d920  mov     [rsp+arg_0], rbx
0x14000d925  mov     [rsp+arg_8], rsi
0x14000d92a  push    rdi
0x14000d92b  sub     rsp, 50h
0x14000d92f  mov     rdi, rdx
0x14000d932  mov     ebx, ecx
0x14000d934  mov     edx, ecx; lpTlsValue
0x14000d936  movzx   esi, r9w
0x14000d93a  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000d940  call    cs:__imp_TlsSetValue
0x14000d946  mov     r9, rdi
0x14000d949  lea     rdx, aClientprocessi_0; "clientProcessID %u pszDeviceName %ws"
0x14000d950  mov     r8d, ebx
0x14000d953  lea     rcx, aRpcsplwow64dev; "RPCSplWOW64DeviceCapabilities"
0x14000d95a  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000d95f  mov     rax, [rsp+58h+arg_48]
0x14000d967  movzx   r9d, si; unsigned __int16
0x14000d96b  mov     [rsp+58h+var_10], rax; unsigned int *
0x14000d970  mov     rdx, rdi; unsigned __int16 *
0x14000d973  mov     rax, [rsp+58h+arg_40]
0x14000d97b  mov     [rsp+58h+var_18], rax; unsigned __int8 **
0x14000d980  mov     rax, [rsp+58h+arg_38]
0x14000d988  mov     [rsp+58h+var_20], rax; unsigned int *
0x14000d98d  mov     eax, [rsp+58h+arg_30]
0x14000d994  mov     [rsp+58h+var_28], eax; int
0x14000d998  mov     rax, [rsp+58h+arg_28]
0x14000d9a0  mov     [rsp+58h+var_30], rax; unsigned __int8 *
0x14000d9a5  call    ?DeviceCapabilitiesW@TLoad64BitDllsMgr@@QEAAHPEAG0GKPEAEHPEAKPEAPEAE2@Z; TLoad64BitDllsMgr::DeviceCapabilitiesW(ushort *,ushort *,ushort,ulong,uchar *,int,ulong *,uchar * *,ulong *)
0x14000d9aa  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000d9b0  xor     edx, edx; lpTlsValue
0x14000d9b2  mov     ebx, eax
0x14000d9b4  call    cs:__imp_TlsSetValue
0x14000d9ba  mov     rsi, [rsp+58h+arg_8]
0x14000d9bf  mov     eax, ebx
0x14000d9c1  mov     rbx, [rsp+58h+arg_0]
0x14000d9c6  add     rsp, 50h
0x14000d9ca  pop     rdi
0x14000d9cb  retn
```
