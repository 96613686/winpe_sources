# TreeView_KillCheckedProcess(HWND__ *,_TREEITEM *,WdcTraceControl *,ulong)

- ea: `0x18002d2c8`
- end: `0x18002d4b8`
- name: `?TreeView_KillCheckedProcess@@YAJPEAUHWND__@@PEAU_TREEITEM@@PEAVWdcTraceControl@@K@Z`
- size: `496`
- prototype: `__int64 __fastcall(HWND hWnd, LPARAM lParam, struct WdcTraceControl *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d2c8`
- `0x180078890`

## callees

- `0x18000b854`
- `0x18000ff88`
- `0x1800281c4`
- `0x18002d2c8`
- `0x1800761cc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18002d366`
- `KERNEL32!GetCurrentProcessId` at `0x18002d366`
- `KERNEL32!GetLastError` at `0x18002d393`
- `KERNEL32!GetLastError` at `0x18002d393`
- `USER32!PostMessageW` at `0x18002d385`
- `USER32!PostMessageW` at `0x18002d385`
- `USER32!SendMessageW` at `0x18002d322`
- `USER32!SendMessageW` at `0x18002d352`
- `USER32!SendMessageW` at `0x18002d463`
- `USER32!SendMessageW` at `0x18002d495`
- `USER32!SendMessageW` at `0x18002d322`
- `USER32!SendMessageW` at `0x18002d352`
- `USER32!SendMessageW` at `0x18002d463`
- `USER32!SendMessageW` at `0x18002d495`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d440`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d440`

## pseudocode

```c
__int64 __fastcall TreeView_KillCheckedProcess(HWND hWnd, LPARAM lParam, WdcProcessMonitor **a3, unsigned int a4)
{
  int v4; // edi
  unsigned __int64 v9; // rbx
  signed int LastError; // eax
  int v11; // eax
  OLECHAR *v13; // rbx
  LRESULT v14; // rax
  int v15; // [rsp+20h] [rbp-50h]
  LPARAM lParama[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h]
  __int128 v18; // [rsp+50h] [rbp-20h]
  __int64 v19; // [rsp+60h] [rbp-10h]
  BSTR bstrString; // [rsp+A8h] [rbp+38h] BYREF

  v4 = 0;
  v19 = 0;
  bstrString = 0;
  *(_OWORD *)lParama = 0;
  v17 = 0;
  v18 = 0;
  while ( lParam )
  {
    if ( (SendMessageW(hWnd, 0x1127u, lParam, 61440) & 0xFFFFF000) == 0x2000 )
    {
      lParama[1] = lParam;
      LODWORD(lParama[0]) = 4;
      if ( (unsigned int)SendMessageW(hWnd, 0x113Eu, 0, (LPARAM)lParama) )
      {
        v9 = (unsigned int)v19 & 0xFFFFFFFE;
        if ( GetCurrentProcessId() == (_DWORD)v9 )
        {
          if ( !PostMessageW(g_MainWindow, 0x10u, 0, 0) )
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( !LastError )
            {
              v4 = -2147467259;
              v11 = -2147467259;
LABEL_11:
              v15 = v11;
LABEL_12:
              WdcDebugMessage(
                "base\\diagnosis\\pdui\\perfmon\\mon\\waitchain.cpp",
                "TreeView_KillCheckedProcess",
                0,
                L"FAILURE: 0x%08x",
                v15);
              return (unsigned int)v4;
            }
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            v11 = v4;
            if ( v4 < 0 )
              goto LABEL_11;
          }
        }
        else
        {
          v4 = WdcProcessMonitor::OnProcessCommand(a3[19], v9, 0x76C0u);
          if ( !(unsigned int)WdcTraceControl::GetImageName((WdcTraceControl *)a3, v9, &bstrString, 0) )
          {
            v13 = bstrString;
            RmSqmAction(a4, 0x76DEu, bstrString, v4);
            if ( v13 )
            {
              SysFreeString(v13);
              bstrString = 0;
            }
          }
          if ( v4 < 0 )
          {
            v15 = v4;
            goto LABEL_12;
          }
        }
      }
    }
    v14 = SendMessageW(hWnd, 0x110Au, 4u, lParam);
    v11 = TreeView_KillCheckedProcess(hWnd, v14, (struct WdcTraceControl *)a3, a4);
    v4 = v11;
    if ( v11 < 0 )
      goto LABEL_11;
    lParam = SendMessageW(hWnd, 0x110Au, 1u, lParam);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002d2c8  mov     [rsp-28h+arg_0], rbx
0x18002d2cd  mov     [rsp-28h+arg_10], rsi
0x18002d2d2  push    rbp
0x18002d2d3  push    rdi
0x18002d2d4  push    r13
0x18002d2d6  push    r14
0x18002d2d8  push    r15
0x18002d2da  mov     rbp, rsp
0x18002d2dd  sub     rsp, 70h
0x18002d2e1  xorps   xmm0, xmm0
0x18002d2e4  xor     edi, edi
0x18002d2e6  xor     eax, eax
0x18002d2e8  mov     r15d, r9d
0x18002d2eb  mov     [rbp+var_10], rax
0x18002d2ef  mov     r13, r8
0x18002d2f2  mov     [rbp+bstrString], rax
0x18002d2f6  mov     rsi, rdx
0x18002d2f9  mov     r14, rcx
0x18002d2fc  movups  xmmword ptr [rbp+lParam], xmm0
0x18002d300  movups  [rbp+var_30], xmm0
0x18002d304  movups  [rbp+var_20], xmm0
0x18002d308  test    rsi, rsi
0x18002d30b  jz      loc_18002D3D9
0x18002d311  mov     r9d, 0F000h; lParam
0x18002d317  mov     r8, rsi; wParam
0x18002d31a  mov     edx, 1127h; Msg
0x18002d31f  mov     rcx, r14; hWnd
0x18002d322  call    cs:__imp_SendMessageW
0x18002d328  and     eax, 0FFFFF000h
0x18002d32d  cmp     eax, 2000h
0x18002d332  jnz     loc_18002D452
0x18002d338  lea     r9, [rbp+lParam]; lParam
0x18002d33c  mov     [rbp+lParam+8], rsi
0x18002d340  xor     r8d, r8d; wParam
0x18002d343  mov     dword ptr [rbp+lParam], 4
0x18002d34a  mov     edx, 113Eh; Msg
0x18002d34f  mov     rcx, r14; hWnd
0x18002d352  call    cs:__imp_SendMessageW
0x18002d358  test    eax, eax
0x18002d35a  jz      loc_18002D452
0x18002d360  mov     ebx, dword ptr [rbp+var_10]
0x18002d363  and     ebx, 0FFFFFFFEh
0x18002d366  call    cs:__imp_GetCurrentProcessId
0x18002d36c  cmp     eax, ebx
0x18002d36e  jnz     loc_18002D3F4
0x18002d374  mov     rcx, cs:?g_MainWindow@@3PEAUHWND__@@EA; hWnd
0x18002d37b  xor     r9d, r9d; lParam
0x18002d37e  xor     r8d, r8d; wParam
0x18002d381  lea     edx, [r9+10h]; Msg
0x18002d385  call    cs:__imp_PostMessageW
0x18002d38b  test    eax, eax
0x18002d38d  jnz     loc_18002D452
0x18002d393  call    cs:__imp_GetLastError
0x18002d399  mov     edi, eax
0x18002d39b  test    eax, eax
0x18002d39d  jz      loc_18002D4A3
0x18002d3a3  jle     short loc_18002D3AE
0x18002d3a5  movzx   edi, ax
0x18002d3a8  or      edi, 80070000h
0x18002d3ae  mov     eax, edi
0x18002d3b0  test    edi, edi
0x18002d3b2  jns     loc_18002D452
0x18002d3b8  mov     [rsp+70h+var_50], eax
0x18002d3bc  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002d3c3  xor     r8d, r8d; int
0x18002d3c6  lea     rdx, aTreeviewKillch; "TreeView_KillCheckedProcess"
0x18002d3cd  lea     rcx, aBaseDiagnosisP_51; "base\\diagnosis\\pdui\\perfmon\\mon\\wa"...
0x18002d3d4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002d3d9  lea     r11, [rsp+70h+var_s0]
0x18002d3de  mov     eax, edi
0x18002d3e0  mov     rbx, [r11+30h]
0x18002d3e4  mov     rsi, [r11+40h]
0x18002d3e8  mov     rsp, r11
0x18002d3eb  pop     r15
0x18002d3ed  pop     r14
0x18002d3ef  pop     r13
0x18002d3f1  pop     rdi
0x18002d3f2  pop     rbp
0x18002d3f3  retn
0x18002d3f4  mov     rcx, [r13+98h]; this
0x18002d3fb  mov     r8d, 76C0h; unsigned int
0x18002d401  mov     rdx, rbx; unsigned __int64
0x18002d404  call    ?OnProcessCommand@WdcProcessMonitor@@QEAAJ_KI@Z; WdcProcessMonitor::OnProcessCommand(unsigned __int64,uint)
0x18002d409  xor     r9d, r9d; int
0x18002d40c  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18002d410  mov     rdx, rbx; unsigned __int64
0x18002d413  mov     rcx, r13; this
0x18002d416  mov     edi, eax
0x18002d418  call    ?GetImageName@WdcTraceControl@@QEAAJ_KPEAPEAGH@Z; WdcTraceControl::GetImageName(unsigned __int64,ushort * *,int)
0x18002d41d  test    eax, eax
0x18002d41f  jnz     short loc_18002D44E
0x18002d421  mov     rbx, [rbp+bstrString]
0x18002d425  mov     r9d, edi; unsigned int
0x18002d428  mov     r8, rbx; unsigned __int16 *
0x18002d42b  mov     edx, 76DEh; unsigned int
0x18002d430  mov     ecx, r15d; unsigned int
0x18002d433  call    ?RmSqmAction@@YAJKKPEBGK@Z; RmSqmAction(ulong,ulong,ushort const *,ulong)
0x18002d438  test    rbx, rbx
0x18002d43b  jz      short loc_18002D44E
0x18002d43d  mov     rcx, rbx; bstrString
0x18002d440  call    cs:__imp_SysFreeString
0x18002d446  mov     [rbp+bstrString], 0
0x18002d44e  test    edi, edi
0x18002d450  js      short loc_18002D4AF
0x18002d452  mov     r9, rsi; lParam
0x18002d455  mov     edx, 110Ah; Msg
0x18002d45a  mov     r8d, 4; wParam
0x18002d460  mov     rcx, r14; hWnd
0x18002d463  call    cs:__imp_SendMessageW
0x18002d469  mov     r9d, r15d; unsigned int
0x18002d46c  mov     r8, r13; struct WdcTraceControl *
0x18002d46f  mov     rdx, rax; lParam
0x18002d472  mov     rcx, r14; hWnd
0x18002d475  call    ?TreeView_KillCheckedProcess@@YAJPEAUHWND__@@PEAU_TREEITEM@@PEAVWdcTraceControl@@K@Z; TreeView_KillCheckedProcess(HWND__ *,_TREEITEM *,WdcTraceControl *,ulong)
0x18002d47a  mov     edi, eax
0x18002d47c  test    eax, eax
0x18002d47e  js      loc_18002D3B8
0x18002d484  mov     r9, rsi; lParam
0x18002d487  mov     edx, 110Ah; Msg
0x18002d48c  mov     r8d, 1; wParam
0x18002d492  mov     rcx, r14; hWnd
0x18002d495  call    cs:__imp_SendMessageW
0x18002d49b  mov     rsi, rax
0x18002d49e  jmp     loc_18002D308
0x18002d4a3  mov     edi, 80004005h
0x18002d4a8  mov     eax, edi
0x18002d4aa  jmp     loc_18002D3B8
0x18002d4af  mov     [rsp+70h+var_50], edi
0x18002d4b3  jmp     loc_18002D3BC
```
