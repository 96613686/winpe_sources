# WdiGetLoggerSnapshotPath

- ea: `0x180005000`
- end: `0x180005337`
- name: `WdiGetLoggerSnapshotPath`
- size: `823`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002ba0`
- `0x180005000`
- `0x180006b90`
- `0x1800093d0`
- `0x18000f1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005098`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000524b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005273`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005098`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000524b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005273`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005259`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005281`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005259`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005281`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052cb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800050e4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800050e4`

## string_xrefs

- `0x180005046`: `WdiGetLoggerSnapshotPath`
- `0x180005238`: `WdipGetContextLoggerPathPattern`
- `0x1800052aa`: `WdipGetContextLoggerPathPattern`
- `0x1800050dd`: `%systemroot%\System32\WDI\LogFiles\WdiContextLog.etl*`
- `0x180005173`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`

## pseudocode

```c
__int64 __fastcall WdiGetLoggerSnapshotPath(__int64 a1, unsigned int a2, unsigned __int16 *a3, unsigned int *a4)
{
  int v7; // r8d
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HANDLE ProcessHeap; // rax
  void *v11; // rdi
  int v12; // r8d
  signed int LastError; // eax
  int v14; // r8d
  WCHAR *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  _WORD *v18; // r8
  _WORD *v19; // rcx
  __int64 v20; // rcx
  _WORD *v21; // rax
  unsigned __int64 v22; // r10
  HANDLE v23; // rax
  int v24; // esi
  HANDLE v25; // rax
  HANDLE v26; // rax
  HANDLE v27; // rax
  int LoggerPath; // eax
  char Args; // [rsp+20h] [rbp-848h]
  WCHAR Dst[1024]; // [rsp+30h] [rbp-838h] BYREF

  if ( !a1 )
  {
    v7 = 241;
LABEL_3:
    v8 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiGetLoggerSnapshotPath",
      v7,
      (int)L"Error = %d",
      87);
    return v8;
  }
  v9 = *(_QWORD *)(a1 + 40);
  if ( !v9 )
  {
    v7 = 242;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v7 = 243;
    goto LABEL_3;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 16) - 1) <= 1 )
    return (unsigned int)-2147020579;
  *(_DWORD *)(v9 + 120) |= 8u;
  if ( a2 == 2 )
  {
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 8u, 0x208u);
    if ( !v11 )
    {
      v8 = -2147024882;
      Args = 14;
      v12 = 327;
LABEL_41:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
        (int)L"WdipGetContextLoggerPathPattern",
        v12,
        (int)L"Error = %d",
        Args);
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v11);
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
        (int)L"WdiGetLoggerSnapshotPath",
        257,
        (int)L"Error = %d",
        v8);
      return v8;
    }
    if ( !ExpandEnvironmentStringsW(L"%systemroot%\\System32\\WDI\\LogFiles\\WdiContextLog.etl*", Dst, 0x400u) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (v8 & 0x80000000) != 0 )
      {
        v14 = 137;
LABEL_26:
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
          (int)L"WdipExpandVariables",
          v14,
          (int)L"Error = %d",
          v8);
        v12 = 333;
        Args = v8;
        goto LABEL_41;
      }
    }
    v15 = Dst;
    v16 = 260;
    v17 = 2147483646;
    v18 = v11;
    do
    {
      if ( !v17 )
        break;
      if ( !*v15 )
        break;
      *v18++ = *v15++;
      --v17;
      --v16;
    }
    while ( v16 );
    v19 = v18 - 1;
    v8 = -2147024774;
    if ( v16 )
    {
      v19 = v18;
      v8 = 0;
    }
    *v19 = 0;
    if ( !v16 )
    {
      v14 = 140;
      goto LABEL_26;
    }
    v20 = 260;
    v21 = v11;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v20;
    }
    while ( v20 );
    v8 = -2147024809;
    if ( v20 )
      v8 = 0;
    v22 = 260 - v20;
    if ( !v20 )
    {
      v12 = 339;
      Args = v8;
      goto LABEL_41;
    }
    if ( v22 > 0xFFFFFFFF )
    {
      v8 = -2147024362;
      Args = 22;
      v12 = 342;
      goto LABEL_41;
    }
    if ( a3 )
    {
      v24 = StringCchCopyW(a3, *a4, (unsigned __int16 *)v11);
      if ( v24 >= 0 )
      {
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v11);
        return (unsigned int)v24;
      }
      else
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
          (int)L"WdipGetContextLoggerPathPattern",
          353,
          (int)L"Error = %d",
          v24);
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v11);
        v8 = v24;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
          (int)L"WdiGetLoggerSnapshotPath",
          257,
          (int)L"Error = %d",
          v24);
      }
    }
    else
    {
      *a4 = v22 + 1;
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v11);
      return 0;
    }
  }
  else
  {
    LoggerPath = WdipGetLoggerPath(*(_QWORD *)(a1 + 40) + 48LL, *(_QWORD *)(a1 + 40) + 64LL, a3, a4, a2);
    v8 = LoggerPath;
    if ( LoggerPath < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
        (int)L"WdiGetLoggerSnapshotPath",
        266,
        (int)L"Error = %d",
        LoggerPath);
  }
  return v8;
}

```

## disassembly

```asm
0x180005000  push    rbx
0x180005002  push    rbp
0x180005003  push    rsi
0x180005004  push    rdi
0x180005005  sub     rsp, 848h
0x18000500c  mov     rax, cs:__security_cookie
0x180005013  xor     rax, rsp
0x180005016  mov     [rsp+868h+var_38], rax
0x18000501e  mov     rbp, r8
0x180005021  mov     r8d, edx
0x180005024  mov     rsi, r9
0x180005027  test    rcx, rcx
0x18000502a  jnz     short loc_18000505E
0x18000502c  mov     r8d, 0F1h; int
0x180005032  mov     ebx, 80070057h
0x180005037  mov     dword ptr [rsp+868h+Args], 57h ; 'W'; Args
0x18000503f  lea     r9, aErrorD_0; "Error = %d"
0x180005046  lea     rdx, aWdigetloggersn_0; "WdiGetLoggerSnapshotPath"
0x18000504d  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005054  call    WdipTraceError
0x180005059  jmp     loc_180005319
0x18000505e  mov     rdx, [rcx+28h]
0x180005062  test    rdx, rdx
0x180005065  jnz     short loc_18000506F
0x180005067  mov     r8d, 0F2h
0x18000506d  jmp     short loc_180005032
0x18000506f  test    rsi, rsi
0x180005072  jnz     short loc_18000507C
0x180005074  mov     r8d, 0F3h
0x18000507a  jmp     short loc_180005032
0x18000507c  mov     eax, [rcx+10h]
0x18000507f  dec     eax
0x180005081  cmp     eax, 1
0x180005084  jbe     loc_180005314
0x18000508a  or      dword ptr [rdx+78h], 8
0x18000508e  cmp     r8d, 2
0x180005092  jnz     loc_1800052E3
0x180005098  call    cs:__imp_GetProcessHeap
0x18000509e  mov     edx, 8; dwFlags
0x1800050a3  mov     r8d, 208h; dwBytes
0x1800050a9  mov     rcx, rax; hHeap
0x1800050ac  call    cs:__imp_HeapAlloc
0x1800050b2  mov     rdi, rax
0x1800050b5  test    rax, rax
0x1800050b8  jnz     short loc_1800050D2
0x1800050ba  mov     ebx, 8007000Eh
0x1800050bf  mov     dword ptr [rsp+868h+Args], 0Eh
0x1800050c7  mov     r8d, 147h
0x1800050cd  jmp     loc_1800052A1
0x1800050d2  mov     r8d, 400h; nSize
0x1800050d8  lea     rdx, [rsp+868h+Dst]; lpDst
0x1800050dd  lea     rcx, Src; "%systemroot%\\System32\\WDI\\LogFiles\\"...
0x1800050e4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800050ea  test    eax, eax
0x1800050ec  jnz     short loc_18000510F
0x1800050ee  call    cs:__imp_GetLastError
0x1800050f4  mov     ebx, eax
0x1800050f6  test    eax, eax
0x1800050f8  jle     short loc_180005103
0x1800050fa  movzx   ebx, ax
0x1800050fd  or      ebx, 80070000h
0x180005103  test    ebx, ebx
0x180005105  jns     short loc_18000510F
0x180005107  mov     r8d, 89h
0x18000510d  jmp     short loc_180005169
0x18000510f  mov     r10d, 104h
0x180005115  lea     rcx, [rsp+868h+Dst]
0x18000511a  mov     edx, r10d
0x18000511d  mov     eax, 7FFFFFFEh
0x180005122  mov     r8, rdi
0x180005125  test    rax, rax
0x180005128  jz      short loc_180005149
0x18000512a  movzx   r9d, word ptr [rcx]
0x18000512e  test    r9w, r9w
0x180005132  jz      short loc_180005149
0x180005134  mov     [r8], r9w
0x180005138  add     rcx, 2
0x18000513c  add     r8, 2
0x180005140  dec     rax
0x180005143  sub     rdx, 1
0x180005147  jnz     short loc_180005125
0x180005149  xor     eax, eax
0x18000514b  lea     rcx, [r8-2]
0x18000514f  test    rdx, rdx
0x180005152  mov     ebx, 8007007Ah
0x180005157  cmovnz  rcx, r8
0x18000515b  cmovnz  ebx, eax
0x18000515e  mov     [rcx], ax
0x180005161  jnz     short loc_18000519C
0x180005163  mov     r8d, 8Ch; int
0x180005169  movzx   eax, bx
0x18000516c  lea     rdx, aWdipexpandvari; "WdipExpandVariables"
0x180005173  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000517a  mov     dword ptr [rsp+868h+Args], eax; Args
0x18000517e  lea     r9, aErrorD_0; "Error = %d"
0x180005185  call    WdipTraceError
0x18000518a  movzx   eax, bx
0x18000518d  mov     r8d, 14Dh
0x180005193  mov     dword ptr [rsp+868h+Args], eax
0x180005197  jmp     loc_1800052A1
0x18000519c  mov     rcx, r10
0x18000519f  mov     rax, rdi
0x1800051a2  cmp     word ptr [rax], 0
0x1800051a6  jz      short loc_1800051B2
0x1800051a8  add     rax, 2
0x1800051ac  sub     rcx, 1
0x1800051b0  jnz     short loc_1800051A2
0x1800051b2  xor     eax, eax
0x1800051b4  mov     ebx, 80070057h
0x1800051b9  test    rcx, rcx
0x1800051bc  cmovnz  ebx, eax
0x1800051bf  sub     r10, rcx
0x1800051c2  test    rcx, rcx
0x1800051c5  cmovz   r10, rax
0x1800051c9  jnz     short loc_1800051DD
0x1800051cb  movzx   eax, bx
0x1800051ce  mov     r8d, 153h
0x1800051d4  mov     dword ptr [rsp+868h+Args], eax
0x1800051d8  jmp     loc_1800052A1
0x1800051dd  mov     eax, 0FFFFFFFFh
0x1800051e2  cmp     r10, rax
0x1800051e5  ja      loc_18000528E
0x1800051eb  test    rbp, rbp
0x1800051ee  jnz     short loc_180005211
0x1800051f0  lea     eax, [r10+1]
0x1800051f4  mov     [rsi], eax
0x1800051f6  call    cs:__imp_GetProcessHeap
0x1800051fc  mov     r8, rdi; lpMem
0x1800051ff  xor     edx, edx; dwFlags
0x180005201  mov     rcx, rax; hHeap
0x180005204  call    cs:__imp_HeapFree
0x18000520a  xor     ebx, ebx
0x18000520c  jmp     loc_180005319
0x180005211  mov     edx, [rsi]; unsigned __int64
0x180005213  mov     r8, rdi; unsigned __int16 *
0x180005216  mov     rcx, rbp; unsigned __int16 *
0x180005219  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000521e  mov     esi, eax
0x180005220  test    eax, eax
0x180005222  jns     short loc_180005273
0x180005224  movzx   eax, si
0x180005227  lea     r9, aErrorD_0; "Error = %d"
0x18000522e  mov     r8d, 161h; int
0x180005234  mov     dword ptr [rsp+868h+Args], eax; Args
0x180005238  lea     rdx, aWdipgetcontext; "WdipGetContextLoggerPathPattern"
0x18000523f  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180005246  call    WdipTraceError
0x18000524b  call    cs:__imp_GetProcessHeap
0x180005251  mov     r8, rdi; lpMem
0x180005254  xor     edx, edx; dwFlags
0x180005256  mov     rcx, rax; hHeap
0x180005259  call    cs:__imp_HeapFree
0x18000525f  movzx   eax, si
0x180005262  mov     ebx, esi
0x180005264  mov     dword ptr [rsp+868h+Args], eax
0x180005268  mov     r8d, 101h
0x18000526e  jmp     loc_18000503F
0x180005273  call    cs:__imp_GetProcessHeap
0x180005279  mov     r8, rdi; lpMem
0x18000527c  xor     edx, edx; dwFlags
0x18000527e  mov     rcx, rax; hHeap
0x180005281  call    cs:__imp_HeapFree
0x180005287  mov     ebx, esi
0x180005289  jmp     loc_180005319
0x18000528e  mov     ebx, 80070216h
0x180005293  mov     dword ptr [rsp+868h+Args], 216h; Args
0x18000529b  mov     r8d, 156h; int
0x1800052a1  lea     r9, aErrorD_0; "Error = %d"
0x1800052a8  mov     esi, ebx
0x1800052aa  lea     rdx, aWdipgetcontext; "WdipGetContextLoggerPathPattern"
0x1800052b1  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800052b8  call    WdipTraceError
0x1800052bd  call    cs:__imp_GetProcessHeap
0x1800052c3  mov     r8, rdi; lpMem
0x1800052c6  xor     edx, edx; dwFlags
0x1800052c8  mov     rcx, rax; hHeap
0x1800052cb  call    cs:__imp_HeapFree
0x1800052d1  movzx   eax, si
0x1800052d4  mov     r8d, 101h
0x1800052da  mov     dword ptr [rsp+868h+Args], eax
0x1800052de  jmp     loc_18000503F
0x1800052e3  mov     rcx, [rcx+28h]
0x1800052e7  mov     dword ptr [rsp+868h+Args], r8d
0x1800052ec  mov     r8, rbp
0x1800052ef  lea     rdx, [rcx+40h]
0x1800052f3  add     rcx, 30h ; '0'
0x1800052f7  call    WdipGetLoggerPath
0x1800052fc  mov     ebx, eax
0x1800052fe  test    eax, eax
0x180005300  jns     short loc_180005319
0x180005302  movzx   ecx, ax
0x180005305  mov     r8d, 10Ah
0x18000530b  mov     dword ptr [rsp+868h+Args], ecx
0x18000530f  jmp     loc_18000503F
0x180005314  mov     ebx, 800710DDh
0x180005319  mov     eax, ebx
0x18000531b  mov     rcx, [rsp+868h+var_38]
0x180005323  xor     rcx, rsp; StackCookie
0x180005326  call    __security_check_cookie
0x18000532b  add     rsp, 848h
0x180005332  pop     rdi
0x180005333  pop     rsi
0x180005334  pop     rbp
0x180005335  pop     rbx
0x180005336  retn
```
