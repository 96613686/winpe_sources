# WdcListView::KillProcessTree(ulong,_LARGE_INTEGER,void *,WdcTraceControl *)

- ea: `0x180032f58`
- end: `0x180033051`
- name: `?KillProcessTree@WdcListView@@AEAAJKT_LARGE_INTEGER@@PEAXPEAVWdcTraceControl@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(WdcListView *__hidden this, unsigned int, union _LARGE_INTEGER, void *, struct WdcTraceControl *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032f58`
- `0x18007a1fc`

## callees

- `0x18000b854`
- `0x1800281c4`
- `0x180032f58`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180032fb5`
- `KERNEL32!GetCurrentProcessId` at `0x180032fb5`
- `KERNEL32!GetLastError` at `0x180032fde`
- `KERNEL32!GetLastError` at `0x180032fde`
- `USER32!PostMessageW` at `0x180032fd0`
- `USER32!PostMessageW` at `0x180032fd0`

## pseudocode

```c
__int64 __fastcall WdcListView::KillProcessTree(
        WdcListView *this,
        unsigned int a2,
        union _LARGE_INTEGER a3,
        union _LARGE_INTEGER *a4,
        WdcProcessMonitor **a5)
{
  unsigned __int64 v7; // rbp
  union _LARGE_INTEGER *i; // rsi
  unsigned int LowPart; // edx
  int v11; // eax
  unsigned int v12; // edi
  signed int LastError; // eax
  struct WdcTraceControl *v15; // [rsp+20h] [rbp-48h]

  v7 = a2;
  for ( i = a4; ; i = (union _LARGE_INTEGER *)((char *)i + i->LowPart) )
  {
    if ( i[11].LowPart == (_DWORD)v7 )
    {
      LowPart = i[10].LowPart;
      if ( LowPart != (_DWORD)v7 && i[4].QuadPart > a3.QuadPart )
      {
        v11 = WdcListView::KillProcessTree(this, LowPart, i[4], a4, (struct WdcTraceControl *)a5);
        v12 = v11;
        if ( v11 < 0 )
          goto LABEL_19;
      }
    }
    if ( !i->LowPart )
      break;
  }
  if ( GetCurrentProcessId() != (_DWORD)v7 )
  {
    v11 = WdcProcessMonitor::OnProcessCommand(a5[19], v7, 0x76C0u);
    v12 = v11;
    if ( v11 >= 0 )
      return v12;
    goto LABEL_19;
  }
  if ( PostMessageW(g_MainWindow, 0x10u, 0, 0) )
    return 0;
  LastError = GetLastError();
  v12 = LastError;
  if ( !LastError )
  {
    v12 = -2147467259;
LABEL_17:
    v11 = v12;
LABEL_19:
    LODWORD(v15) = v11;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
      "WdcListView::KillProcessTree",
      0,
      L"FAILURE: 0x%08x",
      v15);
    return v12;
  }
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  if ( (v12 & 0x80000000) != 0 )
    goto LABEL_17;
  return v12;
}

```

## disassembly

```asm
0x180032f58  push    rbx
0x180032f5a  push    rbp
0x180032f5b  push    rsi
0x180032f5c  push    rdi
0x180032f5d  push    r12
0x180032f5f  push    r14
0x180032f61  push    r15
0x180032f63  sub     rsp, 30h
0x180032f67  mov     r14, [rsp+68h+arg_20]
0x180032f6f  mov     r15, r9
0x180032f72  mov     rbx, r8
0x180032f75  mov     ebp, edx
0x180032f77  mov     r12, rcx
0x180032f7a  mov     rsi, r9
0x180032f7d  cmp     [rsi+58h], ebp
0x180032f80  jnz     short loc_180032FA9
0x180032f82  mov     edx, [rsi+50h]; unsigned int
0x180032f85  cmp     edx, ebp
0x180032f87  jz      short loc_180032FA9
0x180032f89  cmp     [rsi+20h], rbx
0x180032f8d  jle     short loc_180032FA9
0x180032f8f  mov     r8, [rsi+20h]; union _LARGE_INTEGER
0x180032f93  mov     r9, r15; void *
0x180032f96  mov     rcx, r12; this
0x180032f99  mov     [rsp+68h+var_48], r14; struct WdcTraceControl *
0x180032f9e  call    ?KillProcessTree@WdcListView@@AEAAJKT_LARGE_INTEGER@@PEAXPEAVWdcTraceControl@@@Z; WdcListView::KillProcessTree(ulong,_LARGE_INTEGER,void *,WdcTraceControl *)
0x180032fa3  mov     edi, eax
0x180032fa5  test    eax, eax
0x180032fa7  js      short loc_18003301F
0x180032fa9  cmp     dword ptr [rsi], 0
0x180032fac  jz      short loc_180032FB5
0x180032fae  mov     eax, [rsi]
0x180032fb0  add     rsi, rax
0x180032fb3  jmp     short loc_180032F7D
0x180032fb5  call    cs:__imp_GetCurrentProcessId
0x180032fbb  cmp     eax, ebp
0x180032fbd  jnz     short loc_180033004
0x180032fbf  mov     rcx, cs:?g_MainWindow@@3PEAUHWND__@@EA; hWnd
0x180032fc6  xor     r9d, r9d; lParam
0x180032fc9  xor     r8d, r8d; wParam
0x180032fcc  lea     edx, [r9+10h]; Msg
0x180032fd0  call    cs:__imp_PostMessageW
0x180032fd6  test    eax, eax
0x180032fd8  jz      short loc_180032FDE
0x180032fda  xor     edi, edi
0x180032fdc  jmp     short loc_180033040
0x180032fde  call    cs:__imp_GetLastError
0x180032fe4  mov     edi, eax
0x180032fe6  test    eax, eax
0x180032fe8  jz      short loc_180032FFB
0x180032fea  jle     short loc_180032FF5
0x180032fec  movzx   edi, ax
0x180032fef  or      edi, 80070000h
0x180032ff5  test    edi, edi
0x180032ff7  jns     short loc_180033040
0x180032ff9  jmp     short loc_180033000
0x180032ffb  mov     edi, 80004005h
0x180033000  mov     eax, edi
0x180033002  jmp     short loc_18003301F
0x180033004  mov     rcx, [r14+98h]; this
0x18003300b  mov     rdx, rbp; unsigned __int64
0x18003300e  mov     r8d, 76C0h; unsigned int
0x180033014  call    ?OnProcessCommand@WdcProcessMonitor@@QEAAJ_KI@Z; WdcProcessMonitor::OnProcessCommand(unsigned __int64,uint)
0x180033019  mov     edi, eax
0x18003301b  test    eax, eax
0x18003301d  jns     short loc_180033040
0x18003301f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180033026  mov     dword ptr [rsp+68h+var_48], eax
0x18003302a  xor     r8d, r8d; int
0x18003302d  lea     rdx, aWdclistviewKil; "WdcListView::KillProcessTree"
0x180033034  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18003303b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180033040  mov     eax, edi
0x180033042  add     rsp, 30h
0x180033046  pop     r15
0x180033048  pop     r14
0x18003304a  pop     r12
0x18003304c  pop     rdi
0x18003304d  pop     rsi
0x18003304e  pop     rbp
0x18003304f  pop     rbx
0x180033050  retn
```
