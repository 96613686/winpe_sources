# CSDiagSchd::SchdpStringExpand(ushort * *,ushort const *)

- ea: `0x180008038`
- end: `0x1800081e8`
- name: `?SchdpStringExpand@CSDiagSchd@@CAJPEAPEAGPEBG@Z`
- size: `432`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007c60`

## callees

- `0x180008038`
- `0x18000b13c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000819d`
- `KERNEL32!HeapFree` at `0x18000819d`
- `KERNEL32!GetProcessHeap` at `0x1800080e2`
- `KERNEL32!GetProcessHeap` at `0x180008189`
- `KERNEL32!GetProcessHeap` at `0x1800080e2`
- `KERNEL32!GetProcessHeap` at `0x180008189`
- `KERNEL32!HeapAlloc` at `0x1800080f6`
- `KERNEL32!HeapAlloc` at `0x1800080f6`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000806f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180008125`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000806f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180008125`
- `KERNEL32!GetLastError` at `0x180008081`
- `KERNEL32!GetLastError` at `0x180008135`
- `KERNEL32!GetLastError` at `0x180008081`
- `KERNEL32!GetLastError` at `0x180008135`

## string_xrefs

- `0x180008066`: `%systemroot%\diagnostics\scheduled`
- `0x18000811b`: `%systemroot%\diagnostics\scheduled`

## pseudocode

```c
__int64 __fastcall CSDiagSchd::SchdpStringExpand(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  signed int v3; // edi
  int v4; // r8d
  DWORD v5; // eax
  __int64 v6; // rsi
  signed int LastError; // eax
  int v8; // r9d
  int v9; // eax
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rax
  unsigned __int16 *v13; // rbx
  DWORD v14; // eax
  signed int v15; // eax
  int v16; // r8d
  int v17; // r9d
  HANDLE v18; // rax

  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 91;
LABEL_25:
    v8 = v3;
    goto LABEL_26;
  }
  v5 = ExpandEnvironmentStringsW(L"%systemroot%\\diagnostics\\scheduled", 0, 0);
  v6 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = 95;
    if ( v3 >= 0 )
      v3 = -2147467259;
    goto LABEL_25;
  }
  if ( v5 > 0x40 )
  {
    v8 = -2147024785;
    v4 = 99;
    v3 = -2147024785;
LABEL_26:
    SdpDebugTrace(1u, L"CSDiagSchd::SchdpStringExpand", v4, v8);
    return (unsigned int)v3;
  }
  v9 = 2 * v5;
  if ( (unsigned __int64)(2 * v6) > 0xFFFFFFFF )
  {
    v3 = -2147024362;
    v4 = 103;
    goto LABEL_25;
  }
  v10 = v9;
  v3 = 0;
  ProcessHeap = GetProcessHeap();
  v12 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v10);
  v13 = v12;
  if ( !v12 )
  {
    v3 = -2147024882;
    v4 = 106;
    goto LABEL_25;
  }
  v14 = ExpandEnvironmentStringsW(L"%systemroot%\\diagnostics\\scheduled", v12, v6);
  if ( v14 )
  {
    if ( v14 <= (unsigned int)v6 )
    {
      *a1 = v13;
      return (unsigned int)v3;
    }
    v17 = -2147024785;
    v16 = 113;
    v3 = -2147024785;
  }
  else
  {
    v15 = GetLastError();
    v3 = v15;
    if ( v15 > 0 )
      v3 = (unsigned __int16)v15 | 0x80070000;
    v16 = 109;
    if ( v3 >= 0 )
      v3 = -2147467259;
    v17 = v3;
  }
  SdpDebugTrace(1u, L"CSDiagSchd::SchdpStringExpand", v16, v17);
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008038  mov     [rsp+arg_0], rbx
0x18000803d  mov     [rsp+arg_8], rsi
0x180008042  mov     [rsp+arg_10], rdi
0x180008047  push    r14
0x180008049  sub     rsp, 20h
0x18000804d  mov     r14, rcx
0x180008050  test    rcx, rcx
0x180008053  jnz     short loc_180008063
0x180008055  mov     edi, 80070057h
0x18000805a  lea     r8d, [rcx+5Bh]
0x18000805e  jmp     loc_1800081BB
0x180008063  xor     r8d, r8d; nSize
0x180008066  lea     rcx, Src; "%systemroot%\\diagnostics\\scheduled"
0x18000806d  xor     edx, edx; lpDst
0x18000806f  call    cs:__imp_ExpandEnvironmentStringsW
0x180008076  nop     dword ptr [rax+rax+00h]
0x18000807b  mov     esi, eax
0x18000807d  test    eax, eax
0x18000807f  jnz     short loc_1800080B1
0x180008081  call    cs:__imp_GetLastError
0x180008088  nop     dword ptr [rax+rax+00h]
0x18000808d  mov     edi, eax
0x18000808f  test    eax, eax
0x180008091  jle     short loc_18000809C
0x180008093  movzx   edi, ax
0x180008096  or      edi, 80070000h
0x18000809c  test    edi, edi
0x18000809e  mov     eax, 80004005h
0x1800080a3  mov     r8d, 5Fh ; '_'
0x1800080a9  cmovns  edi, eax
0x1800080ac  jmp     loc_1800081BB
0x1800080b1  cmp     esi, 40h ; '@'
0x1800080b4  jbe     short loc_1800080CA
0x1800080b6  mov     r9d, 8007006Fh
0x1800080bc  mov     r8d, 63h ; 'c'
0x1800080c2  mov     edi, r9d
0x1800080c5  jmp     loc_1800081BE
0x1800080ca  mov     rax, rsi
0x1800080cd  mov     ecx, 0FFFFFFFFh
0x1800080d2  add     rax, rax
0x1800080d5  cmp     rax, rcx
0x1800080d8  ja      loc_1800081B0
0x1800080de  mov     ebx, eax
0x1800080e0  xor     edi, edi
0x1800080e2  call    cs:__imp_GetProcessHeap
0x1800080e9  nop     dword ptr [rax+rax+00h]
0x1800080ee  mov     r8d, ebx; dwBytes
0x1800080f1  xor     edx, edx; dwFlags
0x1800080f3  mov     rcx, rax; hHeap
0x1800080f6  call    cs:__imp_HeapAlloc
0x1800080fd  nop     dword ptr [rax+rax+00h]
0x180008102  mov     rbx, rax
0x180008105  test    rax, rax
0x180008108  jnz     short loc_180008118
0x18000810a  mov     edi, 8007000Eh
0x18000810f  lea     r8d, [rax+6Ah]
0x180008113  jmp     loc_1800081BB
0x180008118  mov     r8d, esi; nSize
0x18000811b  lea     rcx, Src; "%systemroot%\\diagnostics\\scheduled"
0x180008122  mov     rdx, rbx; lpDst
0x180008125  call    cs:__imp_ExpandEnvironmentStringsW
0x18000812c  nop     dword ptr [rax+rax+00h]
0x180008131  test    eax, eax
0x180008133  jnz     short loc_180008165
0x180008135  call    cs:__imp_GetLastError
0x18000813c  nop     dword ptr [rax+rax+00h]
0x180008141  mov     edi, eax
0x180008143  test    eax, eax
0x180008145  jle     short loc_180008150
0x180008147  movzx   edi, ax
0x18000814a  or      edi, 80070000h
0x180008150  test    edi, edi
0x180008152  mov     eax, 80004005h
0x180008157  mov     r8d, 6Dh ; 'm'
0x18000815d  cmovns  edi, eax
0x180008160  mov     r9d, edi
0x180008163  jmp     short loc_180008178
0x180008165  cmp     eax, esi
0x180008167  jbe     short loc_1800081AB
0x180008169  mov     r9d, 8007006Fh; int
0x18000816f  mov     r8d, 71h ; 'q'; int
0x180008175  mov     edi, r9d
0x180008178  lea     rdx, aCsdiagschdSchd; "CSDiagSchd::SchdpStringExpand"
0x18000817f  mov     ecx, 1; Level
0x180008184  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180008189  call    cs:__imp_GetProcessHeap
0x180008190  nop     dword ptr [rax+rax+00h]
0x180008195  mov     r8, rbx; lpMem
0x180008198  xor     edx, edx; dwFlags
0x18000819a  mov     rcx, rax; hHeap
0x18000819d  call    cs:__imp_HeapFree
0x1800081a4  nop     dword ptr [rax+rax+00h]
0x1800081a9  jmp     short loc_1800081CF
0x1800081ab  mov     [r14], rbx
0x1800081ae  jmp     short loc_1800081CF
0x1800081b0  mov     edi, 80070216h
0x1800081b5  mov     r8d, 67h ; 'g'; int
0x1800081bb  mov     r9d, edi; int
0x1800081be  lea     rdx, aCsdiagschdSchd; "CSDiagSchd::SchdpStringExpand"
0x1800081c5  mov     ecx, 1; Level
0x1800081ca  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800081cf  mov     rbx, [rsp+28h+arg_0]
0x1800081d4  mov     eax, edi
0x1800081d6  mov     rdi, [rsp+28h+arg_10]
0x1800081db  mov     rsi, [rsp+28h+arg_8]
0x1800081e0  add     rsp, 20h
0x1800081e4  pop     r14
0x1800081e6  retn
```
