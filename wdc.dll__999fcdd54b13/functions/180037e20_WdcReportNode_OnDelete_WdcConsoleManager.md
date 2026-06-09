# WdcReportNode::OnDelete(WdcConsoleManager *)

- ea: `0x180037e20`
- end: `0x180037f9f`
- name: `?OnDelete@WdcReportNode@@UEAAJPEAVWdcConsoleManager@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct WdcConsoleManager *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000b854`
- `0x180037e20`
- `0x180048988`
- `0x180049054`
- `0x18004dc08`
- `0x18005090c`
- `0x180067398`
- `0x180068f70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180037f7a`
- `KERNEL32!GetLastError` at `0x180037f7a`
- `KERNEL32!DeleteFileW` at `0x180037f70`
- `KERNEL32!DeleteFileW` at `0x180037f70`
- `PLA!PlaDeleteReport` at `0x180037f0a`
- `PLA!PlaDeleteReport` at `0x180037f0a`

## string_xrefs

- `0x180037ee8`: `base\diagnosis\pdui\perfmon\mmc\componentdata.cpp`
- `0x180037f31`: `WdcReportNode::OnDelete`

## pseudocode

```c
__int64 __fastcall WdcReportNode::OnDelete(const unsigned __int16 **this, struct WdcConsoleManager *a2)
{
  int MainWindow; // ebx
  int v5; // eax
  const unsigned __int16 *v6; // r13
  struct WdcConsoleManager *v7; // r15
  __int64 **i; // r14
  int v9; // eax
  const WCHAR *v10; // rcx
  bool v11; // sf
  signed int LastError; // eax
  __int64 v14; // [rsp+20h] [rbp-58h]
  HWND v15; // [rsp+90h] [rbp+18h] BYREF

  v15 = 0;
  MainWindow = WdcReportNode::Validate((WdcReportNode *)this);
  if ( MainWindow >= 0 )
  {
    MainWindow = WdcConsoleManager::GetMainWindow(a2, &v15);
    if ( MainWindow >= 0 )
    {
      v5 = WdcConfirmDelete(v15, this[131]);
      MainWindow = v5;
      if ( v5 >= 0 )
      {
        if ( v5 == 1 )
          return (unsigned int)MainWindow;
        v6 = this[133];
        MainWindow = 0;
        v7 = *(struct WdcConsoleManager **)a2;
LABEL_7:
        if ( v7 != a2 )
        {
          for ( i = (__int64 **)*((_QWORD *)v7 + 2); ; i = (__int64 **)*i )
          {
            if ( i == (__int64 **)((char *)v7 + 16) )
            {
              v7 = *(struct WdcConsoleManager **)v7;
              goto LABEL_7;
            }
            if ( i[3] == (__int64 *)v6 )
            {
              v9 = WdcReportNode::CloseSysmonLog((struct IUnknown *)i[2]);
              MainWindow = v9;
              if ( v9 < 0 )
                break;
            }
          }
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\componentdata.cpp",
            "WdcConsoleManager::ForEachControl",
            0,
            L"FAILURE: 0x%08x",
            v9);
          goto LABEL_20;
        }
        if ( MainWindow >= 0 )
        {
          v10 = this[131];
          if ( (*((_BYTE *)this + 444) & 0x10) != 0 )
          {
            MainWindow = PlaDeleteReport(v10);
            v11 = MainWindow < 0;
          }
          else
          {
            if ( DeleteFileW(v10) )
            {
LABEL_19:
              MainWindow = WdcConsoleManager::Delete(a2, (struct WdcBaseNode *)this);
              if ( MainWindow >= 0 )
                return (unsigned int)MainWindow;
              goto LABEL_20;
            }
            LastError = GetLastError();
            MainWindow = LastError;
            if ( !LastError )
            {
              MainWindow = -2147467259;
              goto LABEL_20;
            }
            if ( LastError > 0 )
              MainWindow = (unsigned __int16)LastError | 0x80070000;
            v11 = MainWindow < 0;
          }
          if ( !v11 )
            goto LABEL_19;
        }
      }
    }
  }
LABEL_20:
  LODWORD(v14) = MainWindow;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\reportnode.cpp",
    "WdcReportNode::OnDelete",
    0,
    L"FAILURE: 0x%08x",
    v14);
  if ( MainWindow < 0 )
    WdcShowErrorMessage(v15, 0x32Fu, MainWindow);
  return (unsigned int)MainWindow;
}

```

## disassembly

```asm
0x180037e20  mov     rax, rsp
0x180037e23  push    rbx
0x180037e24  push    rbp
0x180037e25  push    rsi
0x180037e26  push    rdi
0x180037e27  push    r12
0x180037e29  push    r13
0x180037e2b  push    r14
0x180037e2d  push    r15
0x180037e2f  sub     rsp, 38h
0x180037e33  mov     rbp, rdx
0x180037e36  mov     qword ptr [rax+18h], 0
0x180037e3e  mov     rsi, rcx
0x180037e41  call    ?Validate@WdcReportNode@@AEAAJXZ; WdcReportNode::Validate(void)
0x180037e46  mov     ebx, eax
0x180037e48  test    eax, eax
0x180037e4a  jns     short loc_180037E58
0x180037e4c  lea     rdi, aFailure0x08x; "FAILURE: 0x%08x"
0x180037e53  jmp     loc_180037F27
0x180037e58  lea     rdx, [rsp+78h+arg_10]; HWND *
0x180037e60  mov     rcx, rbp; this
0x180037e63  call    ?GetMainWindow@WdcConsoleManager@@QEAAJPEAPEAUHWND__@@@Z; WdcConsoleManager::GetMainWindow(HWND__ * *)
0x180037e68  mov     ebx, eax
0x180037e6a  test    eax, eax
0x180037e6c  js      short loc_180037E4C
0x180037e6e  mov     rdx, [rsi+418h]; unsigned __int16 *
0x180037e75  mov     rcx, [rsp+78h+arg_10]; HWND
0x180037e7d  call    ?WdcConfirmDelete@@YAJPEAUHWND__@@PEBG@Z; WdcConfirmDelete(HWND__ *,ushort const *)
0x180037e82  mov     ebx, eax
0x180037e84  test    eax, eax
0x180037e86  js      short loc_180037E4C
0x180037e88  cmp     eax, 1
0x180037e8b  jnz     short loc_180037E92
0x180037e8d  jmp     loc_180037F5D
0x180037e92  mov     r13, [rsi+428h]
0x180037e99  xor     ebx, ebx
0x180037e9b  mov     r15, [rbp+0]
0x180037e9f  lea     rdi, aFailure0x08x; "FAILURE: 0x%08x"
0x180037ea6  cmp     r15, rbp
0x180037ea9  jz      short loc_180037EF6
0x180037eab  lea     r12, [r15+10h]
0x180037eaf  mov     r14, [r12]
0x180037eb3  cmp     r14, r12
0x180037eb6  jz      short loc_180037ED2
0x180037eb8  cmp     [r14+18h], r13
0x180037ebc  jnz     short loc_180037ECD
0x180037ebe  mov     rcx, [r14+10h]; struct IUnknown *
0x180037ec2  call    ?CloseSysmonLog@WdcReportNode@@SAJPEAUIUnknown@@@Z; WdcReportNode::CloseSysmonLog(IUnknown *)
0x180037ec7  mov     ebx, eax
0x180037ec9  test    eax, eax
0x180037ecb  js      short loc_180037ED7
0x180037ecd  mov     r14, [r14]
0x180037ed0  jmp     short loc_180037EB3
0x180037ed2  mov     r15, [r15]
0x180037ed5  jmp     short loc_180037E9F
0x180037ed7  mov     r9, rdi; unsigned __int16 *
0x180037eda  mov     dword ptr [rsp+78h+var_58], eax
0x180037ede  xor     r8d, r8d; int
0x180037ee1  lea     rdx, aWdcconsolemana_8; "WdcConsoleManager::ForEachControl"
0x180037ee8  lea     rcx, aBaseDiagnosisP_41; "base\\diagnosis\\pdui\\perfmon\\mmc\\co"...
0x180037eef  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180037ef4  jmp     short loc_180037F27
0x180037ef6  test    ebx, ebx
0x180037ef8  js      short loc_180037F27
0x180037efa  test    byte ptr [rsi+1BCh], 10h
0x180037f01  mov     rcx, [rsi+418h]; lpFileName
0x180037f08  jz      short loc_180037F70
0x180037f0a  call    cs:__imp_PlaDeleteReport
0x180037f10  mov     ebx, eax
0x180037f12  test    eax, eax
0x180037f14  js      short loc_180037F27
0x180037f16  mov     rdx, rsi; struct WdcBaseNode *
0x180037f19  mov     rcx, rbp; this
0x180037f1c  call    ?Delete@WdcConsoleManager@@QEAAJPEAVWdcBaseNode@@@Z; WdcConsoleManager::Delete(WdcBaseNode *)
0x180037f21  mov     ebx, eax
0x180037f23  test    eax, eax
0x180037f25  jns     short loc_180037F5D
0x180037f27  lea     rcx, aBaseDiagnosisP_40; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x180037f2e  xor     r8d, r8d; int
0x180037f31  lea     rdx, aWdcreportnodeO_1; "WdcReportNode::OnDelete"
0x180037f38  mov     r9, rdi; unsigned __int16 *
0x180037f3b  mov     dword ptr [rsp+78h+var_58], ebx
0x180037f3f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180037f44  test    ebx, ebx
0x180037f46  jns     short loc_180037F5D
0x180037f48  mov     rcx, [rsp+78h+arg_10]; HWND
0x180037f50  mov     r8d, ebx; int
0x180037f53  mov     edx, 32Fh; unsigned int
0x180037f58  call    ?WdcShowErrorMessage@@YAJPEAUHWND__@@KJ@Z; WdcShowErrorMessage(HWND__ *,ulong,long)
0x180037f5d  mov     eax, ebx
0x180037f5f  add     rsp, 38h
0x180037f63  pop     r15
0x180037f65  pop     r14
0x180037f67  pop     r13
0x180037f69  pop     r12
0x180037f6b  pop     rdi
0x180037f6c  pop     rsi
0x180037f6d  pop     rbp
0x180037f6e  pop     rbx
0x180037f6f  retn
0x180037f70  call    cs:__imp_DeleteFileW
0x180037f76  test    eax, eax
0x180037f78  jnz     short loc_180037F16
0x180037f7a  call    cs:__imp_GetLastError
0x180037f80  mov     ebx, eax
0x180037f82  test    eax, eax
0x180037f84  jz      short loc_180037F98
0x180037f86  jle     short loc_180037F91
0x180037f88  movzx   ebx, ax
0x180037f8b  or      ebx, 80070000h
0x180037f91  test    ebx, ebx
0x180037f93  jmp     loc_180037F14
0x180037f98  mov     ebx, 80004005h
0x180037f9d  jmp     short loc_180037F27
```
