# WdcComponentData::NotifyEventVerify(WdcBaseNode *)

- ea: `0x1800494f8`
- end: `0x18004965a`
- name: `?NotifyEventVerify@WdcComponentData@@AEAAJPEAVWdcBaseNode@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(WdcComponentData *__hidden this, struct WdcBaseNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180047970`

## callees

- `0x18000b854`
- `0x1800287e4`
- `0x1800494f8`
- `0x18004aec0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800495a8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800495a8`
- `KERNEL32!CloseHandle` at `0x1800495f1`
- `KERNEL32!CloseHandle` at `0x1800495f1`
- `KERNEL32!WaitForSingleObject` at `0x1800495da`
- `KERNEL32!WaitForSingleObject` at `0x1800495da`
- `KERNEL32!LeaveCriticalSection` at `0x18004963b`
- `KERNEL32!LeaveCriticalSection` at `0x18004963b`
- `KERNEL32!EnterCriticalSection` at `0x180049517`
- `KERNEL32!EnterCriticalSection` at `0x180049517`
- `KERNEL32!SetEvent` at `0x1800495ca`
- `KERNEL32!SetEvent` at `0x1800495ca`
- `OLEAUT32!__imp_SysFreeString` at `0x180049649`
- `OLEAUT32!__imp_SysFreeString` at `0x180049649`

## string_xrefs

- `0x180049551`: `base\diagnosis\pdui\perfmon\mmc\componentdata.cpp`
- `0x180049628`: `base\diagnosis\pdui\perfmon\mmc\componentdata.cpp`
- `0x18004954a`: `WdcComponentData::NotifyEventVerify`
- `0x180049621`: `WdcComponentData::NotifyEventVerify`

## pseudocode

```c
__int64 __fastcall WdcComponentData::NotifyEventVerify(WdcComponentData *this, struct WdcBaseNode *a2)
{
  unsigned __int16 *v3; // rbx
  unsigned int v5; // edi
  int ComputerNameW; // eax
  BOOL v7; // eax
  _WORD *v8; // rdx
  int v9; // eax
  bool v10; // zf
  char *v11; // rcx
  int v12; // eax
  unsigned __int16 *v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = 0;
  v14 = 0;
  v5 = 0;
  EnterCriticalSection(&g_cs);
  if ( *((_DWORD *)this + 33) )
    goto LABEL_21;
  ComputerNameW = WdcBaseNode::GetComputerNameW(a2, &v14);
  v5 = ComputerNameW;
  if ( ComputerNameW < 0 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\componentdata.cpp",
      "WdcComponentData::NotifyEventVerify",
      0,
      L"FAILURE: 0x%08x",
      ComputerNameW);
    v3 = v14;
    goto LABEL_21;
  }
  v3 = v14;
  if ( v14 )
    v7 = *v14 == 0;
  else
    v7 = 1;
  v8 = (_WORD *)*((_QWORD *)this + 22);
  if ( v7 )
  {
    v9 = 0;
    if ( !v8 )
      goto LABEL_16;
    v10 = *v8 == 0;
    goto LABEL_15;
  }
  if ( v8 && *v8 )
  {
    v9 = _o__wcsicmp(v14, v8);
    goto LABEL_16;
  }
  v9 = 0;
  if ( v14 )
  {
    v10 = *v14 == 0;
LABEL_15:
    LOBYTE(v9) = !v10;
  }
LABEL_16:
  if ( v9 )
  {
    SetEvent(*((HANDLE *)this + 17));
    WaitForSingleObject(*((HANDLE *)this + 18), 0xFFFFFFFF);
    v11 = (char *)*((_QWORD *)this + 18);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v11);
      *((_QWORD *)this + 18) = 0;
    }
    v12 = WdcComponentData::NotifyEventStart(this, v3);
    v5 = v12;
    if ( v12 < 0 )
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\componentdata.cpp",
        "WdcComponentData::NotifyEventVerify",
        0,
        L"FAILURE: 0x%08x",
        v12);
  }
LABEL_21:
  LeaveCriticalSection(&g_cs);
  if ( v3 )
    SysFreeString(v3);
  return v5;
}

```

## disassembly

```asm
0x1800494f8  push    rbx
0x1800494fa  push    rbp
0x1800494fb  push    rsi
0x1800494fc  push    rdi
0x1800494fd  sub     rsp, 38h
0x180049501  mov     rsi, rcx
0x180049504  xor     ebx, ebx
0x180049506  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004950d  mov     [rsp+58h+arg_0], rbx
0x180049512  mov     rbp, rdx
0x180049515  xor     edi, edi
0x180049517  call    cs:__imp_EnterCriticalSection
0x18004951d  cmp     [rsi+84h], ebx
0x180049523  jnz     loc_180049634
0x180049529  lea     rdx, [rsp+58h+arg_0]; unsigned __int16 **
0x18004952e  mov     rcx, rbp; this
0x180049531  call    ?GetComputerNameW@WdcBaseNode@@QEAAJPEAPEAG@Z; WdcBaseNode::GetComputerNameW(ushort * *)
0x180049536  mov     edi, eax
0x180049538  test    eax, eax
0x18004953a  jns     short loc_180049567
0x18004953c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180049543  mov     [rsp+58h+var_38], eax
0x180049547  xor     r8d, r8d; int
0x18004954a  lea     rdx, aWdccomponentda_7; "WdcComponentData::NotifyEventVerify"
0x180049551  lea     rcx, aBaseDiagnosisP_41; "base\\diagnosis\\pdui\\perfmon\\mmc\\co"...
0x180049558  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18004955d  mov     rbx, [rsp+58h+arg_0]
0x180049562  jmp     loc_180049634
0x180049567  mov     rbx, [rsp+58h+arg_0]
0x18004956c  test    rbx, rbx
0x18004956f  jnz     short loc_180049576
0x180049571  lea     eax, [rbx+1]
0x180049574  jmp     short loc_180049580
0x180049576  xor     eax, eax
0x180049578  xor     ecx, ecx
0x18004957a  cmp     cx, [rbx]
0x18004957d  setz    al
0x180049580  mov     rdx, [rsi+0B0h]
0x180049587  test    eax, eax
0x180049589  jz      short loc_180049599
0x18004958b  xor     eax, eax
0x18004958d  test    rdx, rdx
0x180049590  jz      short loc_1800495BF
0x180049592  xor     ecx, ecx
0x180049594  cmp     cx, [rdx]
0x180049597  jmp     short loc_1800495BC
0x180049599  test    rdx, rdx
0x18004959c  jz      short loc_1800495B0
0x18004959e  xor     eax, eax
0x1800495a0  cmp     ax, [rdx]
0x1800495a3  jz      short loc_1800495B0
0x1800495a5  mov     rcx, rbx
0x1800495a8  call    cs:__imp__o__wcsicmp
0x1800495ae  jmp     short loc_1800495BF
0x1800495b0  xor     eax, eax
0x1800495b2  test    rbx, rbx
0x1800495b5  jz      short loc_1800495BF
0x1800495b7  xor     ecx, ecx
0x1800495b9  cmp     cx, [rbx]
0x1800495bc  setnz   al
0x1800495bf  test    eax, eax
0x1800495c1  jz      short loc_180049634
0x1800495c3  mov     rcx, [rsi+88h]; hEvent
0x1800495ca  call    cs:__imp_SetEvent
0x1800495d0  mov     rcx, [rsi+90h]; hHandle
0x1800495d7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800495da  call    cs:__imp_WaitForSingleObject
0x1800495e0  mov     rcx, [rsi+90h]; hObject
0x1800495e7  lea     rax, [rcx-1]
0x1800495eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800495ef  ja      short loc_180049602
0x1800495f1  call    cs:__imp_CloseHandle
0x1800495f7  mov     qword ptr [rsi+90h], 0
0x180049602  mov     rdx, rbx; unsigned __int16 *
0x180049605  mov     rcx, rsi; this
0x180049608  call    ?NotifyEventStart@WdcComponentData@@AEAAJPEBG@Z; WdcComponentData::NotifyEventStart(ushort const *)
0x18004960d  mov     edi, eax
0x18004960f  test    eax, eax
0x180049611  jns     short loc_180049634
0x180049613  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18004961a  mov     [rsp+58h+var_38], eax
0x18004961e  xor     r8d, r8d; int
0x180049621  lea     rdx, aWdccomponentda_7; "WdcComponentData::NotifyEventVerify"
0x180049628  lea     rcx, aBaseDiagnosisP_41; "base\\diagnosis\\pdui\\perfmon\\mmc\\co"...
0x18004962f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180049634  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004963b  call    cs:__imp_LeaveCriticalSection
0x180049641  test    rbx, rbx
0x180049644  jz      short loc_18004964F
0x180049646  mov     rcx, rbx; bstrString
0x180049649  call    cs:__imp_SysFreeString
0x18004964f  mov     eax, edi
0x180049651  add     rsp, 38h
0x180049655  pop     rdi
0x180049656  pop     rsi
0x180049657  pop     rbp
0x180049658  pop     rbx
0x180049659  retn
```
