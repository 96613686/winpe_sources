# W3WP_HOST::SetULongLongCounterValue(ulong,ulong,unsigned __int64)

- ea: `0x1800069d0`
- end: `0x180006a8e`
- name: `?SetULongLongCounterValue@W3WP_HOST@@UEAAJKK_K@Z`
- size: `190`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, unsigned int, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800069d0`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x180006a21`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x180006a21`
- `iisutil!PuDbgPrintError` at `0x180006a76`
- `iisutil!PuDbgPrintError` at `0x180006a76`

## string_xrefs

- `0x180006a60`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::SetULongLongCounterValue(W3WP_HOST *this, int a2, ULONG a3, ULONGLONG a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  struct _PERF_COUNTERSET_INSTANCE *v9; // rdx
  void *v10; // rcx
  __int64 v11; // rcx
  signed int v12; // eax

  if ( *(_DWORD *)(*((_QWORD *)this + 33) + 88LL) )
    return 0;
  v7 = 0;
  if ( *((_DWORD *)this + 18) )
  {
    if ( !a2 )
    {
      v8 = *((_QWORD *)this + 8);
      v9 = *(struct _PERF_COUNTERSET_INSTANCE **)(v8 + 32);
      v10 = *(void **)v8;
      goto LABEL_8;
    }
    if ( a2 == 1 )
    {
      v11 = *((_QWORD *)this + 8);
      v9 = *(struct _PERF_COUNTERSET_INSTANCE **)(v11 + 56);
      v10 = *(void **)(v11 + 8);
LABEL_8:
      v12 = PerfSetULongLongCounterValue(v10, v9, a3, a4);
      if ( v12 )
      {
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        else
          v7 = v12;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
            1558,
            "W3WP_HOST::SetULongLongCounterValue",
            v7,
            "PerfSetULongCounterValue() failed for setId=%d, counterId=%d.\n",
            a2,
            a3);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800069d0  mov     [rsp+arg_0], rbx
0x1800069d5  mov     [rsp+arg_8], rsi
0x1800069da  push    rdi
0x1800069db  sub     rsp, 40h
0x1800069df  mov     rax, [rcx+108h]
0x1800069e6  mov     esi, r8d
0x1800069e9  mov     edi, edx
0x1800069eb  cmp     dword ptr [rax+58h], 0
0x1800069ef  jz      short loc_1800069F8
0x1800069f1  xor     eax, eax
0x1800069f3  jmp     loc_180006A7E
0x1800069f8  xor     ebx, ebx
0x1800069fa  cmp     [rcx+48h], ebx
0x1800069fd  jz      short loc_180006A7C
0x1800069ff  test    edi, edi
0x180006a01  jnz     short loc_180006A10
0x180006a03  mov     rcx, [rcx+40h]
0x180006a07  mov     rdx, [rcx+20h]
0x180006a0b  mov     rcx, [rcx]
0x180006a0e  jmp     short loc_180006A21
0x180006a10  cmp     edi, 1
0x180006a13  jnz     short loc_180006A7C
0x180006a15  mov     rcx, [rcx+40h]
0x180006a19  mov     rdx, [rcx+38h]; Instance
0x180006a1d  mov     rcx, [rcx+8]; Provider
0x180006a21  call    cs:__imp_PerfSetULongLongCounterValue
0x180006a27  test    eax, eax
0x180006a29  jz      short loc_180006A7C
0x180006a2b  jg      short loc_180006A31
0x180006a2d  mov     ebx, eax
0x180006a2f  jmp     short loc_180006A3A
0x180006a31  movzx   ebx, ax
0x180006a34  or      ebx, 80070000h
0x180006a3a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006a41  jz      short loc_180006A7C
0x180006a43  mov     rcx, cs:g_pDebug
0x180006a4a  lea     rax, aPerfsetulongco; "PerfSetULongCounterValue() failed for s"...
0x180006a51  mov     [rsp+48h+var_10], esi
0x180006a55  lea     r9, aW3wpHostSetulo; "W3WP_HOST::SetULongLongCounterValue"
0x180006a5c  mov     [rsp+48h+var_18], edi
0x180006a60  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006a67  mov     [rsp+48h+var_20], rax
0x180006a6c  mov     r8d, 616h
0x180006a72  mov     [rsp+48h+var_28], ebx
0x180006a76  call    cs:__imp_PuDbgPrintError
0x180006a7c  mov     eax, ebx
0x180006a7e  mov     rbx, [rsp+48h+arg_0]
0x180006a83  mov     rsi, [rsp+48h+arg_8]
0x180006a88  add     rsp, 40h
0x180006a8c  pop     rdi
0x180006a8d  retn
```
