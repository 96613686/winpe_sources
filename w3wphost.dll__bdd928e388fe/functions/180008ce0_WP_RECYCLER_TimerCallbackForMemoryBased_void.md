# WP_RECYCLER::TimerCallbackForMemoryBased(void)

- ea: `0x180008ce0`
- end: `0x180008eea`
- name: `?TimerCallbackForMemoryBased@WP_RECYCLER@@QEAAXXZ`
- size: `522`
- prototype: `void __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008ef0`

## callees

- `0x18000850c`
- `0x180008ce0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180008d51`
- `ntdll!NtQuerySystemInformation` at `0x180008d51`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180008d1f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180008d1f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180008d30`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180008d30`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008d3b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008d7a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008d3b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008d7a`
- `iisutil!PuDbgPrint` at `0x180008ddd`
- `iisutil!PuDbgPrint` at `0x180008e5a`
- `iisutil!PuDbgPrint` at `0x180008ed2`
- `iisutil!PuDbgPrint` at `0x180008ddd`
- `iisutil!PuDbgPrint` at `0x180008e5a`
- `iisutil!PuDbgPrint` at `0x180008ed2`

## string_xrefs

- `0x180008dcb`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180008e3c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180008ec6`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180008e30`: `WP_RECYCLER::TimerCallbackForMemoryBased() - current VM:%I64u bytes, configured max VM:%I64u bytes - tell WAS to recycle\n`
- `0x180008ea8`: `WP_RECYCLER::TimerCallbackForMemoryBased() - current Private Bytes:%I64u bytes, configured max Private Bytes:%I64u bytes - tell WAS to recycle\n`

## pseudocode

```c
void __fastcall WP_RECYCLER::TimerCallbackForMemoryBased(WP_RECYCLER *this)
{
  ULONG Size; // ebx
  void *Ptr; // rax
  NTSTATUS v4; // eax
  __int64 i; // rbp
  char *v6; // rax
  char *v7; // rbx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // r8
  ULONG ReturnLength; // [rsp+60h] [rbp+8h] BYREF

  ReturnLength = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 46, 1, 0) )
  {
    while ( BUFFER::Resize((WP_RECYCLER *)((char *)this + 80), *((_DWORD *)this + 32)) )
    {
      Size = BUFFER::QuerySize((WP_RECYCLER *)((char *)this + 80));
      Ptr = BUFFER::QueryPtr((WP_RECYCLER *)((char *)this + 80));
      v4 = NtQuerySystemInformation(SystemProcessInformation, Ptr, Size, &ReturnLength);
      if ( v4 != -1073741820 )
      {
        if ( v4 < 0 )
        {
LABEL_10:
          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
              912,
              "WP_RECYCLER::TimerCallbackForMemoryBased",
              "NtQueryInformationProcess failed with Status: %d\n");
        }
        else
        {
          for ( i = 0; ; i = (unsigned int)(*(_DWORD *)&v6[i] + i) )
          {
            v6 = (char *)BUFFER::QueryPtr((WP_RECYCLER *)((char *)this + 80));
            v7 = v6;
            if ( *(_DWORD *)&v6[i + 80] == *((_DWORD *)this + 18) )
              break;
            if ( !*(_DWORD *)&v6[i] )
              goto LABEL_10;
          }
          v8 = *((_QWORD *)this + 7);
          if ( v8 && *(_QWORD *)&v6[i + 120] >= v8 )
          {
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
                935,
                "WP_RECYCLER::TimerCallbackForMemoryBased",
                "WP_RECYCLER::TimerCallbackForMemoryBased() - current VM:%I64u bytes, configured max VM:%I64u bytes - tel"
                "l WAS to recycle\n");
            WP_RECYCLER::SendRecyclingMsg(this, 5);
          }
          v9 = *((_QWORD *)this + 8);
          if ( v9 && *(_QWORD *)&v7[i + 200] >= v9 )
          {
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
                961,
                "WP_RECYCLER::TimerCallbackForMemoryBased",
                "WP_RECYCLER::TimerCallbackForMemoryBased() - current Private Bytes:%I64u bytes, configured max Private B"
                "ytes:%I64u bytes - tell WAS to recycle\n");
            WP_RECYCLER::SendRecyclingMsg(this, 7);
          }
        }
        break;
      }
      *((_DWORD *)this + 32) = ReturnLength + 4096;
    }
    *((_DWORD *)this + 46) = 0;
  }
}

```

## disassembly

```asm
0x180008ce0  mov     [rsp+arg_8], rbx
0x180008ce5  mov     [rsp+arg_10], rbp
0x180008cea  push    rsi
0x180008ceb  push    rdi
0x180008cec  push    r14
0x180008cee  sub     rsp, 40h
0x180008cf2  mov     rdi, rcx
0x180008cf5  mov     [rsp+58h+ReturnLength], 0
0x180008cfd  mov     ecx, 1
0x180008d02  xor     eax, eax
0x180008d04  lock cmpxchg [rdi+0B8h], ecx
0x180008d0c  jnz     loc_180008DED
0x180008d12  lea     r14, [rdi+50h]
0x180008d16  mov     edx, [rdi+80h]
0x180008d1c  mov     rcx, r14
0x180008d1f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180008d25  test    al, al
0x180008d27  jz      loc_180008DE3
0x180008d2d  mov     rcx, r14
0x180008d30  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180008d36  mov     rcx, r14
0x180008d39  mov     ebx, eax
0x180008d3b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008d41  lea     r9, [rsp+58h+ReturnLength]; ReturnLength
0x180008d46  mov     r8d, ebx; SystemInformationLength
0x180008d49  mov     rdx, rax; SystemInformation
0x180008d4c  mov     ecx, 5; SystemInformationClass
0x180008d51  call    cs:__imp_NtQuerySystemInformation
0x180008d57  mov     edx, eax
0x180008d59  cmp     eax, 0C0000004h
0x180008d5e  jnz     short loc_180008D71
0x180008d60  mov     eax, [rsp+58h+ReturnLength]
0x180008d64  add     eax, 1000h
0x180008d69  mov     [rdi+80h], eax
0x180008d6f  jmp     short loc_180008D16
0x180008d71  test    eax, eax
0x180008d73  js      short loc_180008D9C
0x180008d75  xor     ebp, ebp
0x180008d77  mov     rcx, r14
0x180008d7a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008d80  mov     ecx, [rdi+48h]
0x180008d83  mov     rbx, rax
0x180008d86  cmp     [rax+rbp+50h], ecx
0x180008d8a  jz      short loc_180008E00
0x180008d8c  cmp     dword ptr [rax+rbp], 0
0x180008d90  jz      short loc_180008D97
0x180008d92  add     ebp, [rax+rbp]
0x180008d95  jmp     short loc_180008D77
0x180008d97  mov     edx, 0C0000225h
0x180008d9c  mov     eax, cs:g_dwDebugFlags
0x180008da2  test    al, 3
0x180008da4  setnz   cl
0x180008da7  bt      eax, 14h
0x180008dab  setb    al
0x180008dae  test    al, cl
0x180008db0  jz      short loc_180008DE3
0x180008db2  mov     rcx, cs:g_pDebug
0x180008db9  lea     rax, aNtqueryinforma; "NtQueryInformationProcess failed with S"...
0x180008dc0  mov     dword ptr [rsp+58h+var_30], edx
0x180008dc4  lea     r9, aWpRecyclerTime; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x180008dcb  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008dd2  mov     [rsp+58h+var_38], rax
0x180008dd7  mov     r8d, 390h
0x180008ddd  call    cs:__imp_PuDbgPrint
0x180008de3  mov     dword ptr [rdi+0B8h], 0
0x180008ded  mov     rbx, [rsp+58h+arg_8]
0x180008df2  mov     rbp, [rsp+58h+arg_10]
0x180008df7  add     rsp, 40h
0x180008dfb  pop     r14
0x180008dfd  pop     rdi
0x180008dfe  pop     rsi
0x180008dff  retn
0x180008e00  mov     r8, [rdi+38h]
0x180008e04  test    r8, r8
0x180008e07  jz      short loc_180008E6D
0x180008e09  mov     r9, [rax+rbp+78h]
0x180008e0e  cmp     r9, r8
0x180008e11  jb      short loc_180008E6D
0x180008e13  mov     eax, cs:g_dwDebugFlags
0x180008e19  test    al, 3
0x180008e1b  setnz   cl
0x180008e1e  bt      eax, 14h
0x180008e22  setb    al
0x180008e25  test    al, cl
0x180008e27  jz      short loc_180008E60
0x180008e29  mov     rcx, cs:g_pDebug
0x180008e30  lea     rax, aWpRecyclerTime_2; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x180008e37  mov     [rsp+58h+var_28], r8
0x180008e3c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008e43  mov     [rsp+58h+var_30], r9
0x180008e48  mov     r8d, 3A7h
0x180008e4e  lea     r9, aWpRecyclerTime; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x180008e55  mov     [rsp+58h+var_38], rax
0x180008e5a  call    cs:__imp_PuDbgPrint
0x180008e60  mov     edx, 5
0x180008e65  mov     rcx, rdi
0x180008e68  call    ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
0x180008e6d  mov     r8, [rdi+40h]
0x180008e71  test    r8, r8
0x180008e74  jz      loc_180008DE3
0x180008e7a  mov     rdx, [rbx+rbp+0C8h]
0x180008e82  cmp     rdx, r8
0x180008e85  jb      loc_180008DE3
0x180008e8b  mov     eax, cs:g_dwDebugFlags
0x180008e91  test    al, 3
0x180008e93  setnz   cl
0x180008e96  bt      eax, 14h
0x180008e9a  setb    al
0x180008e9d  test    al, cl
0x180008e9f  jz      short loc_180008ED8
0x180008ea1  mov     rcx, cs:g_pDebug
0x180008ea8  lea     rax, aWpRecyclerTime_4; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x180008eaf  mov     [rsp+58h+var_28], r8
0x180008eb4  lea     r9, aWpRecyclerTime; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x180008ebb  mov     [rsp+58h+var_30], rdx
0x180008ec0  mov     r8d, 3C1h
0x180008ec6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008ecd  mov     [rsp+58h+var_38], rax
0x180008ed2  call    cs:__imp_PuDbgPrint
0x180008ed8  mov     edx, 7
0x180008edd  mov     rcx, rdi
0x180008ee0  call    ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
0x180008ee5  jmp     loc_180008DE3
```
