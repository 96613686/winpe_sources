# W3WP_HOST::DeleteCounterSetInstance(ulong)

- ea: `0x180003e20`
- end: `0x180003f82`
- name: `?DeleteCounterSetInstance@W3WP_HOST@@UEAAJK@Z`
- size: `354`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002dbc`

## callees

- `0x180003e20`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180003e64`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180003ed6`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180003e64`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180003ed6`
- `iisutil!PuDbgPrintError` at `0x180003f68`
- `iisutil!PuDbgPrintError` at `0x180003f68`

## string_xrefs

- `0x180003f61`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003ea2`: `Failed to delete WAS_W3WP counterset instance (%x).\n`
- `0x180003f5a`: `W3WP_HOST::DeleteCounterSetInstance`
- `0x180003f10`: `Failed to delete W3SVC_W3WP counterset instance (%x).\n`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::DeleteCounterSetInstance(W3WP_HOST *this, int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  struct _PERF_COUNTERSET_INSTANCE *v6; // rdx
  signed int v7; // eax
  __int64 v8; // rcx
  struct _PERF_COUNTERSET_INSTANCE *v9; // rdx
  signed int v10; // eax

  if ( *(_DWORD *)(*((_QWORD *)this + 33) + 88LL) )
    return 0;
  v4 = 0;
  if ( *((_DWORD *)this + 18) )
  {
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        v8 = *((_QWORD *)this + 8);
        v9 = *(struct _PERF_COUNTERSET_INSTANCE **)(v8 + 56);
        if ( v9 )
        {
          v10 = PerfDeleteInstance(*(HANDLE *)(v8 + 8), v9);
          if ( v10 )
          {
            v4 = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
                1346,
                "W3WP_HOST::DeleteCounterSetInstance",
                v4,
                "Failed to delete W3SVC_W3WP counterset instance (%x).\n",
                *(_QWORD *)(*((_QWORD *)this + 8) + 56LL));
          }
        }
      }
      else
      {
        v4 = -2147418113;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
            1364,
            "W3WP_HOST::DeleteCounterSetInstance",
            -2147418113,
            "Invalid counter set id (%d).\n",
            a2);
      }
    }
    else
    {
      v5 = *((_QWORD *)this + 8);
      v6 = *(struct _PERF_COUNTERSET_INSTANCE **)(v5 + 32);
      if ( v6 )
      {
        v7 = PerfDeleteInstance(*(HANDLE *)v5, v6);
        if ( v7 )
        {
          if ( v7 > 0 )
            v4 = (unsigned __int16)v7 | 0x80070000;
          else
            v4 = v7;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
              1318,
              "W3WP_HOST::DeleteCounterSetInstance",
              v4,
              "Failed to delete WAS_W3WP counterset instance (%x).\n",
              *(_QWORD *)(*((_QWORD *)this + 8) + 32LL));
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180003e20  mov     [rsp+arg_0], rbx
0x180003e25  push    rdi
0x180003e26  sub     rsp, 40h
0x180003e2a  mov     rax, [rcx+108h]
0x180003e31  mov     rdi, rcx
0x180003e34  cmp     dword ptr [rax+58h], 0
0x180003e38  jz      short loc_180003E41
0x180003e3a  xor     eax, eax
0x180003e3c  jmp     loc_180003F76
0x180003e41  xor     ebx, ebx
0x180003e43  cmp     [rcx+48h], ebx
0x180003e46  jz      loc_180003F74
0x180003e4c  test    edx, edx
0x180003e4e  jnz     short loc_180003EBC
0x180003e50  mov     rcx, [rcx+40h]
0x180003e54  mov     rdx, [rcx+20h]; InstanceBlock
0x180003e58  test    rdx, rdx
0x180003e5b  jz      loc_180003F74
0x180003e61  mov     rcx, [rcx]; Provider
0x180003e64  call    cs:__imp_PerfDeleteInstance
0x180003e6b  nop     dword ptr [rax+rax+00h]
0x180003e70  test    eax, eax
0x180003e72  jz      loc_180003F74
0x180003e78  jg      short loc_180003E7E
0x180003e7a  mov     ebx, eax
0x180003e7c  jmp     short loc_180003E87
0x180003e7e  movzx   ebx, ax
0x180003e81  or      ebx, 80070000h
0x180003e87  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003e8e  jz      loc_180003F74
0x180003e94  mov     rax, [rdi+40h]
0x180003e98  mov     r8d, 526h
0x180003e9e  mov     rcx, [rax+20h]
0x180003ea2  lea     rax, aFailedToDelete_0; "Failed to delete WAS_W3WP counterset in"...
0x180003ea9  mov     [rsp+48h+var_18], rcx
0x180003eae  mov     [rsp+48h+var_20], rax
0x180003eb3  mov     [rsp+48h+var_28], ebx
0x180003eb7  jmp     loc_180003F53
0x180003ebc  cmp     edx, 1
0x180003ebf  jnz     short loc_180003F27
0x180003ec1  mov     rcx, [rcx+40h]
0x180003ec5  mov     rdx, [rcx+38h]; InstanceBlock
0x180003ec9  test    rdx, rdx
0x180003ecc  jz      loc_180003F74
0x180003ed2  mov     rcx, [rcx+8]; Provider
0x180003ed6  call    cs:__imp_PerfDeleteInstance
0x180003edd  nop     dword ptr [rax+rax+00h]
0x180003ee2  test    eax, eax
0x180003ee4  jz      loc_180003F74
0x180003eea  jg      short loc_180003EF0
0x180003eec  mov     ebx, eax
0x180003eee  jmp     short loc_180003EF9
0x180003ef0  movzx   ebx, ax
0x180003ef3  or      ebx, 80070000h
0x180003ef9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003f00  jz      short loc_180003F74
0x180003f02  mov     rax, [rdi+40h]
0x180003f06  mov     r8d, 542h
0x180003f0c  mov     rcx, [rax+38h]
0x180003f10  lea     rax, aFailedToDelete; "Failed to delete W3SVC_W3WP counterset "...
0x180003f17  mov     [rsp+48h+var_18], rcx
0x180003f1c  mov     [rsp+48h+var_20], rax
0x180003f21  mov     [rsp+48h+var_28], ebx
0x180003f25  jmp     short loc_180003F53
0x180003f27  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003f2e  mov     ebx, 8000FFFFh
0x180003f33  jz      short loc_180003F74
0x180003f35  mov     dword ptr [rsp+48h+var_18], edx
0x180003f39  lea     rax, aInvalidCounter_0; "Invalid counter set id (%d).\n"
0x180003f40  mov     [rsp+48h+var_20], rax
0x180003f45  mov     r8d, 554h
0x180003f4b  mov     [rsp+48h+var_28], 8000FFFFh
0x180003f53  mov     rcx, cs:g_pDebug
0x180003f5a  lea     r9, aW3wpHostDelete; "W3WP_HOST::DeleteCounterSetInstance"
0x180003f61  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003f68  call    cs:__imp_PuDbgPrintError
0x180003f6f  nop     dword ptr [rax+rax+00h]
0x180003f74  mov     eax, ebx
0x180003f76  mov     rbx, [rsp+48h+arg_0]
0x180003f7b  add     rsp, 40h
0x180003f7f  pop     rdi
0x180003f80  retn
```
