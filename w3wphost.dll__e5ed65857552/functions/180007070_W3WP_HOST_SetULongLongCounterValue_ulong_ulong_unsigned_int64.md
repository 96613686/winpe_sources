# W3WP_HOST::SetULongLongCounterValue(ulong,ulong,unsigned __int64)

- ea: `0x180007070`
- end: `0x18000713f`
- name: `?SetULongLongCounterValue@W3WP_HOST@@UEAAJKK_K@Z`
- size: `207`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, unsigned int, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007070`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1800070c5`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1800070c5`
- `iisutil!PuDbgPrintError` at `0x180007120`
- `iisutil!PuDbgPrintError` at `0x180007120`

## string_xrefs

- `0x18000710a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

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
0x180007070  mov     [rsp+arg_0], rbx
0x180007075  mov     [rsp+arg_8], rsi
0x18000707a  push    rdi
0x18000707b  sub     rsp, 40h
0x18000707f  mov     rax, [rcx+108h]
0x180007086  mov     esi, r8d
0x180007089  mov     edi, edx
0x18000708b  cmp     dword ptr [rax+58h], 0
0x18000708f  jz      short loc_180007098
0x180007091  xor     eax, eax
0x180007093  jmp     loc_18000712E
0x180007098  xor     ebx, ebx
0x18000709a  cmp     [rcx+48h], ebx
0x18000709d  jz      loc_18000712C
0x1800070a3  test    edi, edi
0x1800070a5  jnz     short loc_1800070B4
0x1800070a7  mov     rcx, [rcx+40h]
0x1800070ab  mov     rdx, [rcx+20h]
0x1800070af  mov     rcx, [rcx]
0x1800070b2  jmp     short loc_1800070C5
0x1800070b4  cmp     edi, 1
0x1800070b7  jnz     short loc_18000712C
0x1800070b9  mov     rcx, [rcx+40h]
0x1800070bd  mov     rdx, [rcx+38h]; Instance
0x1800070c1  mov     rcx, [rcx+8]; Provider
0x1800070c5  call    cs:__imp_PerfSetULongLongCounterValue
0x1800070cc  nop     dword ptr [rax+rax+00h]
0x1800070d1  test    eax, eax
0x1800070d3  jz      short loc_18000712C
0x1800070d5  jg      short loc_1800070DB
0x1800070d7  mov     ebx, eax
0x1800070d9  jmp     short loc_1800070E4
0x1800070db  movzx   ebx, ax
0x1800070de  or      ebx, 80070000h
0x1800070e4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800070eb  jz      short loc_18000712C
0x1800070ed  mov     rcx, cs:g_pDebug
0x1800070f4  lea     rax, aPerfsetulongco; "PerfSetULongCounterValue() failed for s"...
0x1800070fb  mov     [rsp+48h+var_10], esi
0x1800070ff  lea     r9, aW3wpHostSetulo; "W3WP_HOST::SetULongLongCounterValue"
0x180007106  mov     [rsp+48h+var_18], edi
0x18000710a  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007111  mov     [rsp+48h+var_20], rax
0x180007116  mov     r8d, 616h
0x18000711c  mov     [rsp+48h+var_28], ebx
0x180007120  call    cs:__imp_PuDbgPrintError
0x180007127  nop     dword ptr [rax+rax+00h]
0x18000712c  mov     eax, ebx
0x18000712e  mov     rbx, [rsp+48h+arg_0]
0x180007133  mov     rsi, [rsp+48h+arg_8]
0x180007138  add     rsp, 40h
0x18000713c  pop     rdi
0x18000713d  retn
```
