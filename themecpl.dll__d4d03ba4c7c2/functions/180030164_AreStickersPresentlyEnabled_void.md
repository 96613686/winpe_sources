# AreStickersPresentlyEnabled(void)

- ea: `0x180030164`
- end: `0x18003044f`
- name: `?AreStickersPresentlyEnabled@@YA_NXZ`
- size: `747`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030bc0`
- `0x180030d40`

## callees

- `0x180030164`
- `0x180031bac`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030199`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030199`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800302ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030301`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003035e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800303a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800303b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800302ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030301`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003035e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800303a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800303b9`
- `USER32!EnumDisplayMonitors` at `0x180030340`
- `USER32!EnumDisplayMonitors` at `0x180030340`

## string_xrefs

- `0x1800303fe`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\StickerHelpers.h`
- `0x180030413`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\StickerHelpers.h`
- `0x180030428`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\StickerHelpers.h`
- `0x18003043c`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\StickerHelpers.h`
- `0x1800303e9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
char AreStickersPresentlyEnabled(void)
{
  HRESULT Instance; // eax
  int v1; // eax
  __int64 v3; // rax
  int v4; // eax
  __int64 v5; // rax
  int v6; // eax
  int v7; // eax
  int ppv; // [rsp+20h] [rbp-38h]
  __int64 *v9; // [rsp+30h] [rbp-28h] BYREF
  LPVOID v10; // [rsp+38h] [rbp-20h] BYREF
  LPVOID pv[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v13; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+68h] [rbp+10h] BYREF
  LPARAM dwData; // [rsp+70h] [rbp+18h] BYREF
  int v16; // [rsp+78h] [rbp+20h]

  v16 = 2;
  v9 = 0;
  Instance = CoCreateInstance(
               &GUID_c2cf3110_460e_4fc1_b9d0_8a1c0c9cc4bd,
               0,
               4u,
               &GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b,
               (LPVOID *)&v9);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      ppv);
  v13 = 0;
  v1 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v9 + 136))(v9, &v13);
  if ( v1 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\StickerHelpers.h",
      (const char *)(unsigned int)v1,
      ppv);
  if ( (v13 & 3) == 3 )
  {
    if ( v9 )
      (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
    return 0;
  }
  else
  {
    v10 = 0;
    v3 = *v9;
    v10 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, LPVOID *))(v3 + 40))(v9, 0, &v10);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\StickerHelpers.h",
        (const char *)(unsigned int)v4,
        ppv);
    pv[0] = 0;
    v5 = *v9;
    pv[0] = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, LPVOID *))(v5 + 32))(v9, v10, pv);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\StickerHelpers.h",
        (const char *)(unsigned int)v6,
        ppv);
    if ( *(_WORD *)pv[0] )
    {
      v14 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v9 + 88))(v9, &v14);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\StickerHelpers.h",
          (const char *)(unsigned int)v7,
          ppv);
      if ( v14 == 4 )
      {
        LODWORD(dwData) = 0;
        EnumDisplayMonitors(0, 0, MonitorEnumProc, (LPARAM)&dwData);
        if ( (int)dwData <= 1 )
        {
          if ( pv[0] )
            CoTaskMemFree(pv[0]);
          if ( v10 )
            CoTaskMemFree(v10);
          if ( v9 )
            (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
          return 1;
        }
        else
        {
          if ( pv[0] )
            CoTaskMemFree(pv[0]);
          if ( v10 )
            CoTaskMemFree(v10);
          if ( v9 )
            (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
          return 0;
        }
      }
      else
      {
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        if ( v10 )
          CoTaskMemFree(v10);
        if ( v9 )
          (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
        return 0;
      }
    }
    else
    {
      CoTaskMemFree(pv[0]);
      if ( v10 )
        CoTaskMemFree(v10);
      if ( v9 )
        (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180030164  mov     rax, rsp
0x180030167  push    rbx
0x180030168  sub     rsp, 50h
0x18003016c  xor     ebx, ebx
0x18003016e  mov     [rax+20h], ebx
0x180030171  mov     dword ptr [rax+20h], 2
0x180030178  mov     [rax-28h], rbx
0x18003017c  lea     rax, [rax-28h]
0x180030180  mov     qword ptr [rsp+58h+ppv], rax; int
0x180030185  lea     r9, _GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b; riid
0x18003018c  xor     edx, edx; pUnkOuter
0x18003018e  lea     r8d, [rbx+4]; dwClsContext
0x180030192  lea     rcx, _GUID_c2cf3110_460e_4fc1_b9d0_8a1c0c9cc4bd; rclsid
0x180030199  call    cs:__imp_CoCreateInstance
0x1800301a0  nop     dword ptr [rax+rax+00h]
0x1800301a5  mov     rcx, [rsp+58h]; this
0x1800301aa  test    eax, eax
0x1800301ac  js      loc_1800303E6
0x1800301b2  mov     [rsp+58h+arg_0], ebx
0x1800301b6  mov     rcx, [rsp+58h+var_28]
0x1800301bb  mov     rax, [rcx]
0x1800301be  lea     rdx, [rsp+58h+arg_0]
0x1800301c3  mov     rax, [rax+88h]
0x1800301ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301cf  mov     rcx, [rsp+58h]; this
0x1800301d4  test    eax, eax
0x1800301d6  js      loc_1800303FB
0x1800301dc  mov     eax, [rsp+58h+arg_0]
0x1800301e0  and     eax, 3
0x1800301e3  cmp     al, 3
0x1800301e5  jnz     short loc_180030205
0x1800301e7  mov     rcx, [rsp+58h+var_28]
0x1800301ec  test    rcx, rcx
0x1800301ef  jz      short loc_1800301FE
0x1800301f1  mov     rax, [rcx]
0x1800301f4  mov     rax, [rax+10h]
0x1800301f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301fd  nop
0x1800301fe  xor     al, al
0x180030200  jmp     loc_1800303DF
0x180030205  mov     [rsp+58h+var_20], rbx
0x18003020a  mov     rcx, [rsp+58h+var_28]
0x18003020f  mov     rax, [rcx]
0x180030212  mov     [rsp+58h+var_20], rbx
0x180030217  lea     r8, [rsp+58h+var_20]
0x18003021c  xor     edx, edx
0x18003021e  mov     rax, [rax+28h]
0x180030222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030227  mov     rcx, [rsp+58h]; this
0x18003022c  test    eax, eax
0x18003022e  js      loc_180030410
0x180030234  mov     [rsp+58h+pv], rbx
0x180030239  mov     rcx, [rsp+58h+var_28]
0x18003023e  mov     rax, [rcx]
0x180030241  mov     [rsp+58h+pv], rbx
0x180030246  lea     r8, [rsp+58h+pv]
0x18003024b  mov     rdx, [rsp+58h+var_20]
0x180030250  mov     rax, [rax+20h]
0x180030254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030259  mov     rcx, [rsp+58h]; this
0x18003025e  test    eax, eax
0x180030260  js      loc_180030425
0x180030266  mov     rcx, [rsp+58h+pv]; pv
0x18003026b  cmp     [rcx], bx
0x18003026e  jnz     short loc_1800302B2
0x180030270  call    cs:__imp_CoTaskMemFree
0x180030277  nop     dword ptr [rax+rax+00h]
0x18003027c  nop
0x18003027d  mov     rcx, [rsp+58h+var_20]; pv
0x180030282  test    rcx, rcx
0x180030285  jz      short loc_180030294
0x180030287  call    cs:__imp_CoTaskMemFree
0x18003028e  nop     dword ptr [rax+rax+00h]
0x180030293  nop
0x180030294  mov     rcx, [rsp+58h+var_28]
0x180030299  test    rcx, rcx
0x18003029c  jz      short loc_1800302AB
0x18003029e  mov     rax, [rcx]
0x1800302a1  mov     rax, [rax+10h]
0x1800302a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302aa  nop
0x1800302ab  xor     al, al
0x1800302ad  jmp     loc_1800303DF
0x1800302b2  mov     [rsp+58h+arg_8], ebx
0x1800302b6  mov     rcx, [rsp+58h+var_28]
0x1800302bb  mov     rax, [rcx]
0x1800302be  lea     rdx, [rsp+58h+arg_8]
0x1800302c3  mov     rax, [rax+58h]
0x1800302c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302cc  mov     rcx, [rsp+58h]; this
0x1800302d1  test    eax, eax
0x1800302d3  js      loc_180030439
0x1800302d9  cmp     [rsp+58h+arg_8], 4
0x1800302de  jz      short loc_18003032C
0x1800302e0  mov     rcx, [rsp+58h+pv]; pv
0x1800302e5  test    rcx, rcx
0x1800302e8  jz      short loc_1800302F7
0x1800302ea  call    cs:__imp_CoTaskMemFree
0x1800302f1  nop     dword ptr [rax+rax+00h]
0x1800302f6  nop
0x1800302f7  mov     rcx, [rsp+58h+var_20]; pv
0x1800302fc  test    rcx, rcx
0x1800302ff  jz      short loc_18003030E
0x180030301  call    cs:__imp_CoTaskMemFree
0x180030308  nop     dword ptr [rax+rax+00h]
0x18003030d  nop
0x18003030e  mov     rcx, [rsp+58h+var_28]
0x180030313  test    rcx, rcx
0x180030316  jz      short loc_180030325
0x180030318  mov     rax, [rcx]
0x18003031b  mov     rax, [rax+10h]
0x18003031f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030324  nop
0x180030325  xor     al, al
0x180030327  jmp     loc_1800303DF
0x18003032c  mov     dword ptr [rsp+58h+dwData], ebx
0x180030330  lea     r9, [rsp+58h+dwData]; dwData
0x180030335  lea     r8, ?MonitorEnumProc@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x18003033c  xor     edx, edx; lprcClip
0x18003033e  xor     ecx, ecx; hdc
0x180030340  call    cs:__imp_EnumDisplayMonitors
0x180030347  nop     dword ptr [rax+rax+00h]
0x18003034c  nop
0x18003034d  mov     rcx, [rsp+58h+pv]; pv
0x180030352  cmp     dword ptr [rsp+58h+dwData], 1
0x180030357  jle     short loc_18003039D
0x180030359  test    rcx, rcx
0x18003035c  jz      short loc_18003036B
0x18003035e  call    cs:__imp_CoTaskMemFree
0x180030365  nop     dword ptr [rax+rax+00h]
0x18003036a  nop
0x18003036b  mov     rcx, [rsp+58h+var_20]; pv
0x180030370  test    rcx, rcx
0x180030373  jz      short loc_180030382
0x180030375  call    cs:__imp_CoTaskMemFree
0x18003037c  nop     dword ptr [rax+rax+00h]
0x180030381  nop
0x180030382  mov     rcx, [rsp+58h+var_28]
0x180030387  test    rcx, rcx
0x18003038a  jz      short loc_180030399
0x18003038c  mov     rax, [rcx]
0x18003038f  mov     rax, [rax+10h]
0x180030393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030398  nop
0x180030399  xor     al, al
0x18003039b  jmp     short loc_1800303DF
0x18003039d  test    rcx, rcx
0x1800303a0  jz      short loc_1800303AF
0x1800303a2  call    cs:__imp_CoTaskMemFree
0x1800303a9  nop     dword ptr [rax+rax+00h]
0x1800303ae  nop
0x1800303af  mov     rcx, [rsp+58h+var_20]; pv
0x1800303b4  test    rcx, rcx
0x1800303b7  jz      short loc_1800303C6
0x1800303b9  call    cs:__imp_CoTaskMemFree
0x1800303c0  nop     dword ptr [rax+rax+00h]
0x1800303c5  nop
0x1800303c6  mov     rcx, [rsp+58h+var_28]
0x1800303cb  test    rcx, rcx
0x1800303ce  jz      short loc_1800303DD
0x1800303d0  mov     rax, [rcx]
0x1800303d3  mov     rax, [rax+10h]
0x1800303d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303dc  nop
0x1800303dd  mov     al, 1
0x1800303df  add     rsp, 50h
0x1800303e3  pop     rbx
0x1800303e4  retn
0x1800303e6  mov     r9d, eax; char *
0x1800303e9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800303f0  mov     edx, 1CBEh; void *
0x1800303f5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800303fb  mov     r9d, eax; char *
0x1800303fe  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180030405  mov     edx, 49h ; 'I'; void *
0x18003040a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180030410  mov     r9d, eax; char *
0x180030413  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18003041a  mov     edx, 53h ; 'S'; void *
0x18003041f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180030425  mov     r9d, eax; char *
0x180030428  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18003042f  mov     edx, 56h ; 'V'; void *
0x180030434  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180030439  mov     r9d, eax; char *
0x18003043c  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180030443  mov     edx, 5Eh ; '^'; void *
0x180030448  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
