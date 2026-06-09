# WP_RECYCLER::TimerCallbackForMemoryBased(void)

- ea: `0x1800096cc`
- end: `0x180009907`
- name: `?TimerCallbackForMemoryBased@WP_RECYCLER@@QEAAXXZ`
- size: `571`
- prototype: `void __fastcall(WP_RECYCLER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009910`

## callees

- `0x180008e1c`
- `0x1800096cc`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000974f`
- `ntdll!NtQuerySystemInformation` at `0x18000974f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000970b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000970b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180009722`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180009722`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009733`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000977e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009733`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000977e`
- `iisutil!PuDbgPrint` at `0x1800097e7`
- `iisutil!PuDbgPrint` at `0x18000986b`
- `iisutil!PuDbgPrint` at `0x1800098e9`
- `iisutil!PuDbgPrint` at `0x1800097e7`
- `iisutil!PuDbgPrint` at `0x18000986b`
- `iisutil!PuDbgPrint` at `0x1800098e9`

## string_xrefs

- `0x1800097d5`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x18000984d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x1800098dd`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180009841`: `WP_RECYCLER::TimerCallbackForMemoryBased() - current VM:%I64u bytes, configured max VM:%I64u bytes - tell WAS to recycle\n`
- `0x1800098bf`: `WP_RECYCLER::TimerCallbackForMemoryBased() - current Private Bytes:%I64u bytes, configured max Private Bytes:%I64u bytes - tell WAS to recycle\n`

## pseudocode

```c
void __fastcall WP_RECYCLER::TimerCallbackForMemoryBased(WP_RECYCLER *this)
{
  ULONG Size; // ebx
  void *Ptr; // rax
  NTSTATUS v4; // eax
  int v5; // edx
  __int64 i; // rbp
  char *v7; // rax
  char *v8; // rbx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rdx
  ULONG ReturnLength; // [rsp+60h] [rbp+8h] BYREF

  ReturnLength = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 46, 1, 0) )
  {
    while ( BUFFER::Resize((WP_RECYCLER *)((char *)this + 80), *((_DWORD *)this + 32)) )
    {
      Size = BUFFER::QuerySize((WP_RECYCLER *)((char *)this + 80));
      Ptr = BUFFER::QueryPtr((WP_RECYCLER *)((char *)this + 80));
      v4 = NtQuerySystemInformation(SystemProcessInformation, Ptr, Size, &ReturnLength);
      v5 = v4;
      if ( v4 != -1073741820 )
      {
        if ( v4 < 0 )
        {
LABEL_11:
          if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
              912,
              "WP_RECYCLER::TimerCallbackForMemoryBased",
              "NtQueryInformationProcess failed with Status: %d\n",
              v5);
        }
        else
        {
          for ( i = 0; ; i = (unsigned int)(*(_DWORD *)&v7[i] + i) )
          {
            v7 = (char *)BUFFER::QueryPtr((WP_RECYCLER *)((char *)this + 80));
            v8 = v7;
            if ( *(_DWORD *)&v7[i + 80] == *((_DWORD *)this + 18) )
              break;
            if ( !*(_DWORD *)&v7[i] )
            {
              v5 = -1073741275;
              goto LABEL_11;
            }
          }
          v9 = *((_QWORD *)this + 7);
          if ( v9 )
          {
            v10 = *(_QWORD *)&v7[i + 120];
            if ( v10 >= v9 )
            {
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
                  935,
                  "WP_RECYCLER::TimerCallbackForMemoryBased",
                  "WP_RECYCLER::TimerCallbackForMemoryBased() - current VM:%I64u bytes, configured max VM:%I64u bytes - t"
                  "ell WAS to recycle\n",
                  v10,
                  *((_QWORD *)this + 7));
              WP_RECYCLER::SendRecyclingMsg(this, 5);
            }
          }
          v11 = *((_QWORD *)this + 8);
          if ( v11 )
          {
            v12 = *(_QWORD *)&v8[i + 200];
            if ( v12 >= v11 )
            {
              if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
                  961,
                  "WP_RECYCLER::TimerCallbackForMemoryBased",
                  "WP_RECYCLER::TimerCallbackForMemoryBased() - current Private Bytes:%I64u bytes, configured max Private"
                  " Bytes:%I64u bytes - tell WAS to recycle\n",
                  v12,
                  *((_QWORD *)this + 8));
              WP_RECYCLER::SendRecyclingMsg(this, 7);
            }
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
0x1800096cc  mov     [rsp+arg_8], rbx
0x1800096d1  mov     [rsp+arg_10], rbp
0x1800096d6  push    rsi
0x1800096d7  push    rdi
0x1800096d8  push    r14
0x1800096da  sub     rsp, 40h
0x1800096de  mov     rdi, rcx
0x1800096e1  mov     [rsp+58h+ReturnLength], 0
0x1800096e9  mov     ecx, 1
0x1800096ee  xor     eax, eax
0x1800096f0  lock cmpxchg [rdi+0B8h], ecx
0x1800096f8  jnz     loc_1800097FD
0x1800096fe  lea     r14, [rdi+50h]
0x180009702  mov     edx, [rdi+80h]
0x180009708  mov     rcx, r14
0x18000970b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180009712  nop     dword ptr [rax+rax+00h]
0x180009717  test    al, al
0x180009719  jz      loc_1800097F3
0x18000971f  mov     rcx, r14
0x180009722  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180009729  nop     dword ptr [rax+rax+00h]
0x18000972e  mov     rcx, r14
0x180009731  mov     ebx, eax
0x180009733  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000973a  nop     dword ptr [rax+rax+00h]
0x18000973f  lea     r9, [rsp+58h+ReturnLength]; ReturnLength
0x180009744  mov     r8d, ebx; SystemInformationLength
0x180009747  mov     rdx, rax; SystemInformation
0x18000974a  mov     ecx, 5; SystemInformationClass
0x18000974f  call    cs:__imp_NtQuerySystemInformation
0x180009756  nop     dword ptr [rax+rax+00h]
0x18000975b  mov     edx, eax
0x18000975d  cmp     eax, 0C0000004h
0x180009762  jnz     short loc_180009775
0x180009764  mov     eax, [rsp+58h+ReturnLength]
0x180009768  add     eax, 1000h
0x18000976d  mov     [rdi+80h], eax
0x180009773  jmp     short loc_180009702
0x180009775  test    eax, eax
0x180009777  js      short loc_1800097A6
0x180009779  xor     ebp, ebp
0x18000977b  mov     rcx, r14
0x18000977e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180009785  nop     dword ptr [rax+rax+00h]
0x18000978a  mov     ecx, [rdi+48h]
0x18000978d  mov     rbx, rax
0x180009790  cmp     [rax+rbp+50h], ecx
0x180009794  jz      short loc_180009811
0x180009796  cmp     dword ptr [rax+rbp], 0
0x18000979a  jz      short loc_1800097A1
0x18000979c  add     ebp, [rax+rbp]
0x18000979f  jmp     short loc_18000977B
0x1800097a1  mov     edx, 0C0000225h
0x1800097a6  mov     eax, cs:g_dwDebugFlags
0x1800097ac  test    al, 3
0x1800097ae  setnz   cl
0x1800097b1  bt      eax, 14h
0x1800097b5  setb    al
0x1800097b8  test    al, cl
0x1800097ba  jz      short loc_1800097F3
0x1800097bc  mov     rcx, cs:g_pDebug
0x1800097c3  lea     rax, aNtqueryinforma; "NtQueryInformationProcess failed with S"...
0x1800097ca  mov     dword ptr [rsp+58h+var_30], edx
0x1800097ce  lea     r9, aWpRecyclerTime; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x1800097d5  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800097dc  mov     [rsp+58h+var_38], rax
0x1800097e1  mov     r8d, 390h
0x1800097e7  call    cs:__imp_PuDbgPrint
0x1800097ee  nop     dword ptr [rax+rax+00h]
0x1800097f3  mov     dword ptr [rdi+0B8h], 0
0x1800097fd  mov     rbx, [rsp+58h+arg_8]
0x180009802  mov     rbp, [rsp+58h+arg_10]
0x180009807  add     rsp, 40h
0x18000980b  pop     r14
0x18000980d  pop     rdi
0x18000980e  pop     rsi
0x18000980f  retn
0x180009811  mov     r8, [rdi+38h]
0x180009815  test    r8, r8
0x180009818  jz      short loc_180009884
0x18000981a  mov     r9, [rax+rbp+78h]
0x18000981f  cmp     r9, r8
0x180009822  jb      short loc_180009884
0x180009824  mov     eax, cs:g_dwDebugFlags
0x18000982a  test    al, 3
0x18000982c  setnz   cl
0x18000982f  bt      eax, 14h
0x180009833  setb    al
0x180009836  test    al, cl
0x180009838  jz      short loc_180009877
0x18000983a  mov     rcx, cs:g_pDebug
0x180009841  lea     rax, aWpRecyclerTime_2; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x180009848  mov     [rsp+58h+var_28], r8
0x18000984d  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009854  mov     [rsp+58h+var_30], r9
0x180009859  mov     r8d, 3A7h
0x18000985f  lea     r9, aWpRecyclerTime; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x180009866  mov     [rsp+58h+var_38], rax
0x18000986b  call    cs:__imp_PuDbgPrint
0x180009872  nop     dword ptr [rax+rax+00h]
0x180009877  mov     edx, 5
0x18000987c  mov     rcx, rdi
0x18000987f  call    ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
0x180009884  mov     r8, [rdi+40h]
0x180009888  test    r8, r8
0x18000988b  jz      loc_1800097F3
0x180009891  mov     rdx, [rbx+rbp+0C8h]
0x180009899  cmp     rdx, r8
0x18000989c  jb      loc_1800097F3
0x1800098a2  mov     eax, cs:g_dwDebugFlags
0x1800098a8  test    al, 3
0x1800098aa  setnz   cl
0x1800098ad  bt      eax, 14h
0x1800098b1  setb    al
0x1800098b4  test    al, cl
0x1800098b6  jz      short loc_1800098F5
0x1800098b8  mov     rcx, cs:g_pDebug
0x1800098bf  lea     rax, aWpRecyclerTime_4; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x1800098c6  mov     [rsp+58h+var_28], r8
0x1800098cb  lea     r9, aWpRecyclerTime; "WP_RECYCLER::TimerCallbackForMemoryBase"...
0x1800098d2  mov     [rsp+58h+var_30], rdx
0x1800098d7  mov     r8d, 3C1h
0x1800098dd  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800098e4  mov     [rsp+58h+var_38], rax
0x1800098e9  call    cs:__imp_PuDbgPrint
0x1800098f0  nop     dword ptr [rax+rax+00h]
0x1800098f5  mov     edx, 7
0x1800098fa  mov     rcx, rdi
0x1800098fd  call    ?SendRecyclingMsg@WP_RECYCLER@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_RECYCLER::SendRecyclingMsg(IPM_WP_SHUTDOWN_MSG)
0x180009902  jmp     loc_1800097F3
```
