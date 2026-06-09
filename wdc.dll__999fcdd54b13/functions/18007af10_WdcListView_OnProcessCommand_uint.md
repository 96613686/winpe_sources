# WdcListView::OnProcessCommand(uint)

- ea: `0x18007af10`
- end: `0x18007b1b3`
- name: `?OnProcessCommand@WdcListView@@AEAAJI@Z`
- size: `675`
- prototype: `__int64 __fastcall(WdcListView *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021aa4`

## callees

- `0x18000b854`
- `0x1800281c4`
- `0x18003b0ac`
- `0x1800761cc`
- `0x18007a598`
- `0x18007af10`
- `0x18007c538`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18007b0f7`
- `KERNEL32!GetCurrentProcessId` at `0x18007b0f7`
- `KERNEL32!GetLastError` at `0x18007b123`
- `KERNEL32!GetLastError` at `0x18007b123`
- `USER32!PostMessageW` at `0x18007b115`
- `USER32!PostMessageW` at `0x18007b115`
- `USER32!SendMessageW` at `0x18007b043`
- `USER32!SendMessageW` at `0x18007b085`
- `USER32!SendMessageW` at `0x18007b043`
- `USER32!SendMessageW` at `0x18007b085`

## string_xrefs

- `0x18007afbf`: `WdcListView::OnProcessCommand`

## pseudocode

```c
__int64 __fastcall WdcListView::OnProcessCommand(WdcListView *this, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // r13
  int SelectedProcessCount; // eax
  int v7; // edi
  HWND v8; // rax
  int v9; // eax
  WPARAM v10; // rbx
  HWND v11; // rax
  LRESULT v12; // rax
  __int64 v13; // rcx
  HWND v14; // rax
  __int64 v15; // r15
  unsigned __int64 v16; // rdx
  double v17; // xmm0_8
  unsigned __int64 v18; // rbx
  signed int LastError; // eax
  int *v21; // [rsp+20h] [rbp-69h]
  int v22; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-41h] BYREF
  _DWORD lParam[10]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v25; // [rsp+78h] [rbp-11h]
  LRESULT v26; // [rsp+F0h] [rbp+67h] BYREF
  int v27; // [rsp+100h] [rbp+77h] BYREF
  int v28; // [rsp+108h] [rbp+7Fh] BYREF

  v28 = 0;
  v27 = 0;
  LODWORD(v26) = 0;
  v23 = 0;
  v22 = 0;
  memset_0(lParam, 0, 0x58u);
  v4 = *((_QWORD *)this + 45);
  if ( v4 && *((_QWORD *)this + 44) && (v5 = *(_QWORD *)(v4 + 168)) != 0 )
  {
    SelectedProcessCount = WdcListView::GetSelectedProcessCount(this, &v28, &v27, (int *)&v26, 0, &v23, &v22);
    v7 = SelectedProcessCount;
    if ( SelectedProcessCount < 0
      || (v8 = (HWND)(*(__int64 (__fastcall **)(WdcListView *))(*(_QWORD *)this + 360LL))(this),
          SelectedProcessCount = WdcConfirmProcessCommand(v8, v28 + v27 + (int)v26, v23, v22, a2),
          v7 = SelectedProcessCount,
          SelectedProcessCount < 0) )
    {
      LODWORD(v21) = SelectedProcessCount;
LABEL_6:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\listview.cpp",
        "WdcListView::OnProcessCommand",
        0,
        L"FAILURE: 0x%08x",
        v21);
    }
    else if ( SelectedProcessCount == 1 )
    {
      return 0;
    }
    else
    {
      v9 = -1;
      while ( 1 )
      {
        v10 = v9;
        v11 = (HWND)(*(__int64 (__fastcall **)(WdcListView *))(*(_QWORD *)this + 360LL))(this);
        v12 = SendMessageW(v11, 0x100Cu, v10, 2);
        v26 = v12;
        if ( (_DWORD)v12 == -1 )
          break;
        v13 = *(_QWORD *)this;
        lParam[1] = v12;
        lParam[2] = 0;
        lParam[0] = 4;
        v14 = (HWND)(*(__int64 (__fastcall **)(WdcListView *))(v13 + 360))(this);
        if ( !(unsigned int)SendMessageW(v14, 0x104Bu, 0, (LPARAM)lParam) )
          return (unsigned int)-2147467259;
        v15 = v25;
        if ( !v25 )
          return (unsigned int)-2147467259;
        v16 = 0;
        v17 = *(double *)(*(_QWORD *)(v25 + 80) + 16LL * *(unsigned __int16 *)(*((_QWORD *)this + 44) + 9326LL) + 8);
        if ( v17 >= 9.223372036854776e18 )
        {
          v17 = v17 - 9.223372036854776e18;
          if ( v17 < 9.223372036854776e18 )
            v16 = 0x8000000000000000uLL;
        }
        v18 = v16 + (unsigned int)(int)v17;
        if ( a2 == 30400 && GetCurrentProcessId() == v18 )
        {
          if ( PostMessageW(g_MainWindow, 0x10u, 0, 0) )
          {
            v7 = 0;
          }
          else
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError )
            {
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              v7 = -2147467259;
            }
          }
        }
        else
        {
          v7 = WdcProcessMonitor::OnProcessCommand(*(WdcProcessMonitor **)(v5 + 152), v18, a2);
        }
        RmSqmAction(
          *((_DWORD *)this + 128),
          a2,
          *(const unsigned __int16 **)(*(_QWORD *)(v15 + 80)
                                     + 16LL * *(unsigned __int16 *)(*((_QWORD *)this + 44) + 9324LL)
                                     + 8),
          v7);
        v9 = v26;
        if ( v7 < 0 )
        {
          LODWORD(v21) = v7;
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007af10  push    rbp
0x18007af12  push    rbx
0x18007af13  push    rsi
0x18007af14  push    rdi
0x18007af15  push    r12
0x18007af17  push    r13
0x18007af19  push    r15
0x18007af1b  lea     rbp, [rsp-27h]
0x18007af20  sub     rsp, 0B0h
0x18007af27  xor     r15d, r15d
0x18007af2a  mov     r12d, edx
0x18007af2d  mov     rsi, rcx
0x18007af30  mov     [rbp+57h+arg_18], r15d
0x18007af34  xor     edx, edx; Val
0x18007af36  mov     [rbp+57h+arg_10], r15d
0x18007af3a  lea     rcx, [rbp+57h+lParam]; void *
0x18007af3e  mov     dword ptr [rbp+57h+arg_0], r15d
0x18007af42  lea     r8d, [r15+58h]; Size
0x18007af46  mov     [rbp+57h+var_98], r15
0x18007af4a  mov     [rbp+57h+var_A0], r15d
0x18007af4e  call    memset_0
0x18007af53  mov     rax, [rsi+168h]
0x18007af5a  test    rax, rax
0x18007af5d  jz      loc_18007B19A
0x18007af63  cmp     [rsi+160h], r15
0x18007af6a  jz      loc_18007B19A
0x18007af70  mov     r13, [rax+0A8h]
0x18007af77  test    r13, r13
0x18007af7a  jz      loc_18007B19A
0x18007af80  lea     rax, [rbp+57h+var_A0]
0x18007af84  mov     rcx, rsi; this
0x18007af87  mov     [rsp+0E0h+var_B0], rax; int *
0x18007af8c  lea     r9, [rbp+57h+arg_0]; int *
0x18007af90  lea     rax, [rbp+57h+var_98]
0x18007af94  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 **
0x18007af99  lea     r8, [rbp+57h+arg_10]; int *
0x18007af9d  lea     rdx, [rbp+57h+arg_18]; int *
0x18007afa1  mov     [rsp+0E0h+var_C0], r15; int *
0x18007afa6  call    ?GetSelectedProcessCount@WdcListView@@AEAAJPEAH000PEAPEAG0@Z; WdcListView::GetSelectedProcessCount(int *,int *,int *,int *,ushort * *,int *)
0x18007afab  mov     edi, eax
0x18007afad  test    eax, eax
0x18007afaf  jns     short loc_18007AFD7
0x18007afb1  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18007afb5  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18007afbc  xor     r8d, r8d; int
0x18007afbf  lea     rdx, aWdclistviewOnp; "WdcListView::OnProcessCommand"
0x18007afc6  lea     rcx, aBaseDiagnosisP_29; "base\\diagnosis\\pdui\\perfmon\\mon\\li"...
0x18007afcd  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18007afd2  jmp     loc_18007B19F
0x18007afd7  mov     rax, [rsi]
0x18007afda  mov     rcx, rsi
0x18007afdd  mov     rax, [rax+168h]
0x18007afe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007afe9  mov     edx, dword ptr [rbp+57h+arg_0]
0x18007afec  mov     rcx, rax; HWND
0x18007afef  add     edx, [rbp+57h+arg_10]
0x18007aff2  add     edx, [rbp+57h+arg_18]; int
0x18007aff5  mov     r9d, [rbp+57h+var_A0]; int
0x18007aff9  mov     r8, [rbp+57h+var_98]; unsigned __int16 *
0x18007affd  mov     dword ptr [rsp+0E0h+var_C0], r12d; unsigned int
0x18007b002  call    ?WdcConfirmProcessCommand@@YAJPEAUHWND__@@HPEBGHI@Z; WdcConfirmProcessCommand(HWND__ *,int,ushort const *,int,uint)
0x18007b007  mov     edi, eax
0x18007b009  test    eax, eax
0x18007b00b  js      short loc_18007AFB1
0x18007b00d  cmp     eax, 1
0x18007b010  jnz     short loc_18007B01A
0x18007b012  mov     edi, r15d
0x18007b015  jmp     loc_18007B19F
0x18007b01a  or      eax, 0FFFFFFFFh
0x18007b01d  movsxd  rbx, eax
0x18007b020  mov     rcx, rsi
0x18007b023  mov     rax, [rsi]
0x18007b026  mov     rax, [rax+168h]
0x18007b02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b032  mov     rcx, rax; hWnd
0x18007b035  mov     r9d, 2; lParam
0x18007b03b  mov     r8, rbx; wParam
0x18007b03e  mov     edx, 100Ch; Msg
0x18007b043  call    cs:__imp_SendMessageW
0x18007b049  mov     [rbp+57h+arg_0], rax
0x18007b04d  cmp     eax, 0FFFFFFFFh
0x18007b050  jz      loc_18007B19F
0x18007b056  mov     rcx, [rsi]
0x18007b059  mov     dword ptr [rbp+57h+lParam+4], eax
0x18007b05c  mov     [rbp+57h+var_88], r15d
0x18007b060  mov     dword ptr [rbp+57h+lParam], 4
0x18007b067  mov     rax, [rcx+168h]
0x18007b06e  mov     rcx, rsi
0x18007b071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b076  mov     rcx, rax; hWnd
0x18007b079  lea     r9, [rbp+57h+lParam]; lParam
0x18007b07d  xor     r8d, r8d; wParam
0x18007b080  mov     edx, 104Bh; Msg
0x18007b085  call    cs:__imp_SendMessageW
0x18007b08b  test    eax, eax
0x18007b08d  jz      loc_18007B19A
0x18007b093  mov     r15, [rbp+57h+var_68]
0x18007b097  test    r15, r15
0x18007b09a  jz      loc_18007B19A
0x18007b0a0  mov     rax, [rsi+160h]
0x18007b0a7  xor     edx, edx
0x18007b0a9  movzx   ecx, word ptr [rax+246Eh]
0x18007b0b0  mov     rax, [r15+50h]
0x18007b0b4  add     rcx, rcx
0x18007b0b7  movsd   xmm0, qword ptr [rax+rcx*8+8]
0x18007b0bd  comisd  xmm0, cs:__real@43e0000000000000
0x18007b0c5  jb      short loc_18007B0E6
0x18007b0c7  subsd   xmm0, cs:__real@43e0000000000000
0x18007b0cf  comisd  xmm0, cs:__real@43e0000000000000
0x18007b0d7  jnb     short loc_18007B0E6
0x18007b0d9  mov     rax, 8000000000000000h
0x18007b0e3  mov     rdx, rax
0x18007b0e6  cvttsd2si rbx, xmm0
0x18007b0eb  add     rbx, rdx
0x18007b0ee  cmp     r12d, 76C0h
0x18007b0f5  jnz     short loc_18007B143
0x18007b0f7  call    cs:__imp_GetCurrentProcessId
0x18007b0fd  mov     eax, eax
0x18007b0ff  cmp     rax, rbx
0x18007b102  jnz     short loc_18007B143
0x18007b104  mov     rcx, cs:?g_MainWindow@@3PEAUHWND__@@EA; hWnd
0x18007b10b  xor     r9d, r9d; lParam
0x18007b10e  xor     r8d, r8d; wParam
0x18007b111  lea     edx, [r9+10h]; Msg
0x18007b115  call    cs:__imp_PostMessageW
0x18007b11b  test    eax, eax
0x18007b11d  jz      short loc_18007B123
0x18007b11f  xor     edi, edi
0x18007b121  jmp     short loc_18007B157
0x18007b123  call    cs:__imp_GetLastError
0x18007b129  mov     edi, eax
0x18007b12b  test    eax, eax
0x18007b12d  jz      short loc_18007B13C
0x18007b12f  jle     short loc_18007B157
0x18007b131  movzx   edi, ax
0x18007b134  or      edi, 80070000h
0x18007b13a  jmp     short loc_18007B157
0x18007b13c  mov     edi, 80004005h
0x18007b141  jmp     short loc_18007B157
0x18007b143  mov     rcx, [r13+98h]; this
0x18007b14a  mov     r8d, r12d; unsigned int
0x18007b14d  mov     rdx, rbx; unsigned __int64
0x18007b150  call    ?OnProcessCommand@WdcProcessMonitor@@QEAAJ_KI@Z; WdcProcessMonitor::OnProcessCommand(unsigned __int64,uint)
0x18007b155  mov     edi, eax
0x18007b157  mov     rax, [rsi+160h]
0x18007b15e  mov     r9d, edi; unsigned int
0x18007b161  mov     r8, [r15+50h]
0x18007b165  mov     edx, r12d; unsigned int
0x18007b168  movzx   ecx, word ptr [rax+246Ch]
0x18007b16f  add     rcx, rcx
0x18007b172  mov     r8, [r8+rcx*8+8]; unsigned __int16 *
0x18007b177  mov     ecx, [rsi+200h]; unsigned int
0x18007b17d  call    ?RmSqmAction@@YAJKKPEBGK@Z; RmSqmAction(ulong,ulong,ushort const *,ulong)
0x18007b182  mov     rax, [rbp+57h+arg_0]
0x18007b186  xor     r15d, r15d
0x18007b189  test    edi, edi
0x18007b18b  jns     loc_18007B01D
0x18007b191  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18007b195  jmp     loc_18007AFB5
0x18007b19a  mov     edi, 80004005h
0x18007b19f  mov     eax, edi
0x18007b1a1  add     rsp, 0B0h
0x18007b1a8  pop     r15
0x18007b1aa  pop     r13
0x18007b1ac  pop     r12
0x18007b1ae  pop     rdi
0x18007b1af  pop     rsi
0x18007b1b0  pop     rbx
0x18007b1b1  pop     rbp
0x18007b1b2  retn
```
