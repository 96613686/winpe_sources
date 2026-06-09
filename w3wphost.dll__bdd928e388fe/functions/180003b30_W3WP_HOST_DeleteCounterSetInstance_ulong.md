# W3WP_HOST::DeleteCounterSetInstance(ulong)

- ea: `0x180003b30`
- end: `0x180003c7f`
- name: `?DeleteCounterSetInstance@W3WP_HOST@@UEAAJK@Z`
- size: `335`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002c20`

## callees

- `0x180003b30`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180003b74`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180003be0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180003b74`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180003be0`
- `iisutil!PuDbgPrintError` at `0x180003c6c`
- `iisutil!PuDbgPrintError` at `0x180003c6c`

## string_xrefs

- `0x180003c65`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180003bac`: `Failed to delete WAS_W3WP counterset instance (%x).\n`
- `0x180003c5e`: `W3WP_HOST::DeleteCounterSetInstance`
- `0x180003c14`: `Failed to delete W3SVC_W3WP counterset instance (%x).\n`

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
0x180003b30  mov     [rsp+arg_0], rbx
0x180003b35  push    rdi
0x180003b36  sub     rsp, 40h
0x180003b3a  mov     rax, [rcx+108h]
0x180003b41  mov     rdi, rcx
0x180003b44  cmp     dword ptr [rax+58h], 0
0x180003b48  jz      short loc_180003B51
0x180003b4a  xor     eax, eax
0x180003b4c  jmp     loc_180003C74
0x180003b51  xor     ebx, ebx
0x180003b53  cmp     [rcx+48h], ebx
0x180003b56  jz      loc_180003C72
0x180003b5c  test    edx, edx
0x180003b5e  jnz     short loc_180003BC6
0x180003b60  mov     rcx, [rcx+40h]
0x180003b64  mov     rdx, [rcx+20h]; InstanceBlock
0x180003b68  test    rdx, rdx
0x180003b6b  jz      loc_180003C72
0x180003b71  mov     rcx, [rcx]; Provider
0x180003b74  call    cs:__imp_PerfDeleteInstance
0x180003b7a  test    eax, eax
0x180003b7c  jz      loc_180003C72
0x180003b82  jg      short loc_180003B88
0x180003b84  mov     ebx, eax
0x180003b86  jmp     short loc_180003B91
0x180003b88  movzx   ebx, ax
0x180003b8b  or      ebx, 80070000h
0x180003b91  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003b98  jz      loc_180003C72
0x180003b9e  mov     rax, [rdi+40h]
0x180003ba2  mov     r8d, 526h
0x180003ba8  mov     rcx, [rax+20h]
0x180003bac  lea     rax, aFailedToDelete_0; "Failed to delete WAS_W3WP counterset in"...
0x180003bb3  mov     [rsp+48h+var_18], rcx
0x180003bb8  mov     [rsp+48h+var_20], rax
0x180003bbd  mov     [rsp+48h+var_28], ebx
0x180003bc1  jmp     loc_180003C57
0x180003bc6  cmp     edx, 1
0x180003bc9  jnz     short loc_180003C2B
0x180003bcb  mov     rcx, [rcx+40h]
0x180003bcf  mov     rdx, [rcx+38h]; InstanceBlock
0x180003bd3  test    rdx, rdx
0x180003bd6  jz      loc_180003C72
0x180003bdc  mov     rcx, [rcx+8]; Provider
0x180003be0  call    cs:__imp_PerfDeleteInstance
0x180003be6  test    eax, eax
0x180003be8  jz      loc_180003C72
0x180003bee  jg      short loc_180003BF4
0x180003bf0  mov     ebx, eax
0x180003bf2  jmp     short loc_180003BFD
0x180003bf4  movzx   ebx, ax
0x180003bf7  or      ebx, 80070000h
0x180003bfd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003c04  jz      short loc_180003C72
0x180003c06  mov     rax, [rdi+40h]
0x180003c0a  mov     r8d, 542h
0x180003c10  mov     rcx, [rax+38h]
0x180003c14  lea     rax, aFailedToDelete; "Failed to delete W3SVC_W3WP counterset "...
0x180003c1b  mov     [rsp+48h+var_18], rcx
0x180003c20  mov     [rsp+48h+var_20], rax
0x180003c25  mov     [rsp+48h+var_28], ebx
0x180003c29  jmp     short loc_180003C57
0x180003c2b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003c32  mov     ebx, 8000FFFFh
0x180003c37  jz      short loc_180003C72
0x180003c39  mov     dword ptr [rsp+48h+var_18], edx
0x180003c3d  lea     rax, aInvalidCounter_0; "Invalid counter set id (%d).\n"
0x180003c44  mov     [rsp+48h+var_20], rax
0x180003c49  mov     r8d, 554h
0x180003c4f  mov     [rsp+48h+var_28], 8000FFFFh
0x180003c57  mov     rcx, cs:g_pDebug
0x180003c5e  lea     r9, aW3wpHostDelete; "W3WP_HOST::DeleteCounterSetInstance"
0x180003c65  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003c6c  call    cs:__imp_PuDbgPrintError
0x180003c72  mov     eax, ebx
0x180003c74  mov     rbx, [rsp+48h+arg_0]
0x180003c79  add     rsp, 40h
0x180003c7d  pop     rdi
0x180003c7e  retn
```
