# CRpcHandler::RequestDone(void *,ulong)

- ea: `0x180005600`
- end: `0x180005c68`
- name: `?RequestDone@CRpcHandler@@UEAAKPEAXK@Z`
- size: `1640`
- prototype: `__int64 __fastcall(CRpcHandler *this, char *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003944`
- `0x180005600`
- `0x180006184`
- `0x18001c11e`
- `0x18001d010`

## import_xrefs

- `msvcrt!malloc` at `0x180005674`
- `msvcrt!malloc` at `0x180005674`
- `KERNEL32!SetLastError` at `0x1800058a9`
- `KERNEL32!SetLastError` at `0x1800058d3`
- `KERNEL32!SetLastError` at `0x1800058a9`
- `KERNEL32!SetLastError` at `0x1800058d3`
- `KERNEL32!GetLastError` at `0x180005820`
- `KERNEL32!GetLastError` at `0x18000586e`
- `KERNEL32!GetLastError` at `0x1800058b5`
- `KERNEL32!GetLastError` at `0x180005820`
- `KERNEL32!GetLastError` at `0x18000586e`
- `KERNEL32!GetLastError` at `0x1800058b5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800056f8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180005993`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800056f8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180005993`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800057fd`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005a88`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005b6d`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800057fd`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005a88`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180005b6d`
- `WdsServerCommonLib!?Batch@CPerfCounters@@QEAAKKZZ` at `0x180005c3e`
- `WdsServerCommonLib!?Batch@CPerfCounters@@QEAAKKZZ` at `0x180005c3e`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800058e1`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800058e1`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180005bfe`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180005bfe`

## pseudocode

```c
__int64 __fastcall CRpcHandler::RequestDone(CRpcHandler *this, char *a2, unsigned int a3)
{
  char *v3; // rbx
  int v4; // r15d
  __int64 v6; // rsi
  unsigned int v7; // r12d
  unsigned int v8; // r14d
  char *v9; // r13
  int v10; // ecx
  unsigned int v11; // ecx
  char *v12; // rax
  char *v13; // r15
  __int128 v14; // xmm0
  __int64 v15; // rbx
  size_t v16; // r8
  const void *v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  const wchar_t *v21; // r9
  DWORD LastError; // ebx
  DWORD v23; // ebx
  _QWORD *v24; // rsi
  _QWORD *v25; // rax
  _QWORD *v26; // rdx
  _QWORD *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  const wchar_t *v34; // r9
  const wchar_t *v35; // rsi
  __int64 v36; // rcx
  const wchar_t *v37; // r9
  unsigned int v38; // edx
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v42; // [rsp+20h] [rbp-59h]
  __int64 v43; // [rsp+28h] [rbp-51h]
  __int64 v44; // [rsp+28h] [rbp-51h]
  __int64 v45; // [rsp+30h] [rbp-49h]
  __int64 v46; // [rsp+38h] [rbp-41h]
  __int64 v47; // [rsp+38h] [rbp-41h]
  __int64 v48; // [rsp+40h] [rbp-39h]
  __int64 v49; // [rsp+48h] [rbp-31h]
  __int64 v50; // [rsp+48h] [rbp-31h]
  __int64 v51; // [rsp+50h] [rbp-29h]
  __int64 v52; // [rsp+50h] [rbp-29h]
  __int64 v53; // [rsp+58h] [rbp-21h]
  __int64 v54; // [rsp+58h] [rbp-21h]
  __int64 v55; // [rsp+60h] [rbp-19h]
  __int64 v56; // [rsp+68h] [rbp-11h]
  __int64 v57; // [rsp+68h] [rbp-11h]
  __int64 v58; // [rsp+70h] [rbp-9h]
  __int64 v59; // [rsp+80h] [rbp+7h]
  __int128 v60[4]; // [rsp+90h] [rbp+17h] BYREF
  unsigned int Reply; // [rsp+F0h] [rbp+77h] BYREF

  Reply = 0;
  v3 = a2 + 2216;
  v4 = 0;
  if ( !a3 )
  {
    v6 = *(_QWORD *)v3;
    v7 = 40;
    v8 = 40;
    v9 = a2 + 2216;
    if ( !*(_QWORD *)v3 )
    {
LABEL_7:
      v12 = (char *)malloc(v8);
      v13 = v12;
      if ( !v12 )
      {
        v4 = 0;
        Reply = 8;
        goto LABEL_26;
      }
      *((_QWORD *)v12 + 3) = 0;
      *((_QWORD *)v12 + 4) = 0;
      v14 = *((_OWORD *)a2 + 73);
      *(_DWORD *)v12 = 16777256;
      *((_DWORD *)v12 + 1) = v8 - 40;
      *(_OWORD *)(v12 + 8) = v14;
      while ( v6 )
      {
        v15 = v6;
        v16 = *(unsigned int *)(v6 + 48);
        v17 = *(const void **)(v6 + 40);
        v6 = *(_QWORD *)(v6 + 56);
        memmove_0(&v13[v7], v17, v16);
        v7 += *(_DWORD *)(v15 + 48);
      }
      **((_DWORD **)a2 + 11) = v8;
      **((_QWORD **)a2 + 12) = v13;
      v18 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)a2 + 7), &Reply);
      Reply = ElValidateWin32(v18, v19, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 1396);
      v4 = 1;
      v3 = v9;
      if ( Reply )
        goto LABEL_26;
      v20 = *(_QWORD *)(*((_QWORD *)a2 + 280) + 64LL);
      if ( v20 )
        v21 = *(const wchar_t **)(v20 + 16);
      else
        v21 = L"<Unknown>";
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x10000u,
        L"[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}] Reply To:%s Len:%u",
        v21,
        *((_DWORD *)a2 + 292),
        *((unsigned __int16 *)a2 + 586),
        *((unsigned __int16 *)a2 + 587),
        (unsigned __int8)a2[1176],
        (unsigned __int8)a2[1177],
        (unsigned __int8)a2[1178],
        (unsigned __int8)a2[1179],
        (unsigned __int8)a2[1180],
        (unsigned __int8)a2[1181],
        (unsigned __int8)a2[1182],
        (unsigned __int8)a2[1183],
        a2 + 132,
        v8 - 40LL);
      v4 = 1;
LABEL_25:
      v3 = v9;
      goto LABEL_26;
    }
    while ( 1 )
    {
      v10 = *(_DWORD *)(v6 + 48);
      v6 = *(_QWORD *)(v6 + 56);
      v11 = v8 + v10;
      if ( v11 < v8 )
        break;
      v8 = v11;
      if ( !v6 )
      {
        v6 = *(_QWORD *)v3;
        goto LABEL_7;
      }
    }
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, hr=0x%x",
        "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp",
        1337,
        &dword_18001F974,
        -2147024362);
    }
    else
    {
      if ( !g_ErrLibTraceFunction )
      {
LABEL_22:
        v23 = GetLastError();
        if ( (g_uErrLibFlags & 1) != 0 )
          ElTraceErrorInfo();
        SetLastError(v23);
        Reply = WIN32_FROM_HRESULT(-2147024362);
        goto LABEL_25;
      }
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, hr=0x%x",
        "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp",
        1337,
        &dword_18001F974,
        -2147024362);
    }
    SetLastError(LastError);
    goto LABEL_22;
  }
  Reply = a3;
LABEL_26:
  v24 = *(_QWORD **)v3;
  while ( v24 )
  {
    v25 = *(_QWORD **)v3;
    v26 = v24;
    v27 = (_QWORD *)*((_QWORD *)v3 + 1);
    if ( *(_QWORD **)v3 == v27 )
    {
      *((_QWORD *)v3 + 1) = 0;
      *(_QWORD *)v3 = 0;
LABEL_33:
      v24 = 0;
      goto LABEL_35;
    }
    if ( v24 == v25 )
    {
      v28 = v25[7];
      *(_QWORD *)v3 = v28;
      *(_QWORD *)(v28 + 64) = 0;
      v24 = *(_QWORD **)v3;
      goto LABEL_35;
    }
    if ( v24 == v27 )
    {
      v29 = v27[8];
      *((_QWORD *)v3 + 1) = v29;
      *(_QWORD *)(v29 + 56) = 0;
      goto LABEL_33;
    }
    v30 = v24 + 7;
    v24 = (_QWORD *)v24[7];
    *(_QWORD *)(v26[8] + 56LL) = v24;
    *(_QWORD *)(*v30 + 64LL) = v26[8];
LABEL_35:
    --*((_DWORD *)v3 + 5);
    (*(void (__fastcall **)(_QWORD *))(*v26 + 8LL))(v26);
  }
  if ( !v4 )
  {
    **((_DWORD **)a2 + 11) = 0;
    **((_QWORD **)a2 + 12) = 0;
    v31 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)a2 + 7), &Reply);
    Reply = ElValidateWin32(v31, v32, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 1431);
    if ( !Reply )
    {
      v33 = *(_QWORD *)(*((_QWORD *)a2 + 280) + 64LL);
      if ( v33 )
        v34 = *(const wchar_t **)(v33 + 16);
      else
        v34 = L"<Unknown>";
      LODWORD(v59) = 0;
      LODWORD(v58) = (unsigned __int8)a2[1183];
      LODWORD(v56) = (unsigned __int8)a2[1182];
      LODWORD(v55) = (unsigned __int8)a2[1181];
      LODWORD(v53) = (unsigned __int8)a2[1180];
      LODWORD(v51) = (unsigned __int8)a2[1179];
      LODWORD(v49) = (unsigned __int8)a2[1178];
      LODWORD(v48) = (unsigned __int8)a2[1177];
      LODWORD(v46) = (unsigned __int8)a2[1176];
      LODWORD(v45) = *((unsigned __int16 *)a2 + 587);
      LODWORD(v43) = *((unsigned __int16 *)a2 + 586);
      LODWORD(v42) = *((_DWORD *)a2 + 292);
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x80000u,
        L"[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}] Client:%s Request Cancelled (rc=%u)",
        v34,
        v42,
        v43,
        v45,
        v46,
        v48,
        v49,
        v51,
        v53,
        v55,
        v56,
        v58,
        a2 + 132,
        v59);
    }
  }
  if ( Reply )
  {
    v35 = L"<Unknown>";
    v36 = *(_QWORD *)(*((_QWORD *)a2 + 280) + 64LL);
    if ( v36 )
      v37 = *(const wchar_t **)(v36 + 16);
    else
      v37 = L"<Unknown>";
    LODWORD(v59) = Reply;
    LODWORD(v58) = (unsigned __int8)a2[1183];
    LODWORD(v56) = (unsigned __int8)a2[1182];
    LODWORD(v55) = (unsigned __int8)a2[1181];
    LODWORD(v53) = (unsigned __int8)a2[1180];
    LODWORD(v51) = (unsigned __int8)a2[1179];
    LODWORD(v49) = (unsigned __int8)a2[1178];
    LODWORD(v48) = (unsigned __int8)a2[1177];
    LODWORD(v46) = (unsigned __int8)a2[1176];
    LODWORD(v45) = *((unsigned __int16 *)a2 + 587);
    LODWORD(v43) = *((unsigned __int16 *)a2 + 586);
    LODWORD(v42) = *((_DWORD *)a2 + 292);
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x80000u,
      L"[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}] Error Sending Reply To:%s (rc=%u)",
      v37,
      v42,
      v43,
      v45,
      v46,
      v48,
      v49,
      v51,
      v53,
      v55,
      v56,
      v58,
      a2 + 132,
      v59);
    v38 = *((_DWORD *)a2 + 18);
    v39 = *((_QWORD *)a2 + 10);
    if ( v38 > 0x20 )
      v38 = 32;
    v40 = *(_QWORD *)(*((_QWORD *)a2 + 280) + 64LL);
    if ( v40 )
      v35 = *(const wchar_t **)(v40 + 16);
    LODWORD(v57) = v38;
    LODWORD(v54) = 10;
    LODWORD(v52) = Reply;
    LODWORD(v50) = 5;
    LODWORD(v47) = 1;
    LODWORD(v44) = 1;
    v60[0] = *((_OWORD *)a2 + 73);
    CEventLog::Log(
      (CEventLog *)qword_180039300,
      0xC101040C,
      4,
      8,
      v60,
      v44,
      a2 + 132,
      v47,
      v35,
      v50,
      v52,
      v54,
      v39,
      v57);
  }
  LODWORD(v46) = 1;
  LODWORD(v45) = 1;
  LODWORD(v43) = 2;
  _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 280) + 56LL));
  LODWORD(v42) = 1;
  CPerfCounters::Batch((CPerfCounters *)&g_PerfCounters, 2u, 1, 0, v42, v43, v45, v46);
  return 0;
}

```

## disassembly

```asm
0x180005600  mov     [rsp-8+arg_0], rbx
0x180005605  push    rbp
0x180005606  push    rsi
0x180005607  push    rdi
0x180005608  push    r12
0x18000560a  push    r13
0x18000560c  push    r14
0x18000560e  push    r15
0x180005610  lea     rbp, [rsp-27h]
0x180005615  sub     rsp, 0A0h
0x18000561c  and     [rbp+57h+Reply], 0
0x180005620  lea     rbx, [rdx+8A8h]
0x180005627  xor     r15d, r15d
0x18000562a  mov     rdi, rdx
0x18000562d  mov     [rbp+57h+arg_8], r15d
0x180005631  test    r8d, r8d
0x180005634  jz      short loc_18000563F
0x180005636  mov     [rbp+57h+Reply], r8d
0x18000563a  jmp     loc_1800058F3
0x18000563f  mov     rsi, [rbx]
0x180005642  mov     r12d, 28h ; '('
0x180005648  mov     r14d, r12d
0x18000564b  mov     r13, rbx
0x18000564e  test    rsi, rsi
0x180005651  jz      short loc_180005671
0x180005653  mov     ecx, [rsi+30h]
0x180005656  mov     rsi, [rsi+38h]
0x18000565a  add     ecx, r14d
0x18000565d  cmp     ecx, r14d
0x180005660  jb      loc_180005812
0x180005666  mov     r14d, ecx
0x180005669  test    rsi, rsi
0x18000566c  jnz     short loc_180005653
0x18000566e  mov     rsi, [rbx]
0x180005671  mov     ecx, r14d; Size
0x180005674  call    cs:__imp_malloc
0x18000567b  nop     dword ptr [rax+rax+00h]
0x180005680  mov     r15, rax
0x180005683  test    rax, rax
0x180005686  jnz     short loc_180005698
0x180005688  mov     r15d, [rbp+57h+arg_8]
0x18000568c  mov     [rbp+57h+Reply], 8
0x180005693  jmp     loc_1800058F3
0x180005698  and     qword ptr [rax+18h], 0
0x18000569d  and     qword ptr [rax+20h], 0
0x1800056a2  movups  xmm0, xmmword ptr [rdi+490h]
0x1800056a9  mov     dword ptr [rax], 1000028h
0x1800056af  lea     eax, [r14-28h]
0x1800056b3  mov     [r15+4], eax
0x1800056b7  movdqu  xmmword ptr [r15+8], xmm0
0x1800056bd  jmp     short loc_1800056DD
0x1800056bf  lea     rbx, [rsi]
0x1800056c2  mov     ecx, r12d
0x1800056c5  mov     r8d, [rbx+30h]; Size
0x1800056c9  add     rcx, r15; void *
0x1800056cc  mov     rdx, [rbx+28h]; Src
0x1800056d0  mov     rsi, [rsi+38h]
0x1800056d4  call    memmove_0
0x1800056d9  add     r12d, [rbx+30h]
0x1800056dd  test    rsi, rsi
0x1800056e0  jnz     short loc_1800056BF
0x1800056e2  mov     rax, [rdi+58h]
0x1800056e6  lea     rdx, [rbp+57h+Reply]; Reply
0x1800056ea  mov     [rax], r14d
0x1800056ed  mov     rax, [rdi+60h]
0x1800056f1  mov     [rax], r15
0x1800056f4  mov     rcx, [rdi+38h]; pAsync
0x1800056f8  call    cs:__imp_RpcAsyncCompleteCall
0x1800056ff  nop     dword ptr [rax+rax+00h]
0x180005704  mov     r9d, 574h
0x18000570a  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180005711  mov     ecx, eax
0x180005713  call    ElValidateWin32
0x180005718  mov     [rbp+57h+Reply], eax
0x18000571b  lea     r15d, [rsi+1]
0x18000571f  mov     [rbp+57h+arg_8], r15d
0x180005723  mov     rbx, r13
0x180005726  test    eax, eax
0x180005728  jnz     loc_1800058F3
0x18000572e  mov     rax, [rdi+8C0h]
0x180005735  movzx   r8d, byte ptr [rdi+49Fh]
0x18000573d  movzx   r10d, byte ptr [rdi+49Eh]
0x180005745  movzx   r11d, byte ptr [rdi+49Dh]
0x18000574d  mov     rcx, [rax+40h]
0x180005751  movzx   ebx, byte ptr [rdi+49Ch]
0x180005758  movzx   esi, byte ptr [rdi+49Bh]
0x18000575f  movzx   r15d, byte ptr [rdi+499h]
0x180005767  movzx   r12d, byte ptr [rdi+498h]
0x18000576f  mov     edx, r14d
0x180005772  movzx   r14d, byte ptr [rdi+49Ah]
0x18000577a  add     rdx, 0FFFFFFFFFFFFFFD8h
0x18000577e  test    rcx, rcx
0x180005781  jz      short loc_180005789
0x180005783  mov     r9, [rcx+10h]
0x180005787  jmp     short loc_180005790
0x180005789  lea     r9, aUnknown_0; "<Unknown>"
0x180005790  mov     [rsp+0D0h+var_50], rdx
0x180005798  lea     rax, [rdi+84h]
0x18000579f  mov     [rsp+0D0h+var_58], rax
0x1800057a4  lea     rcx, qword_180039310
0x1800057ab  movzx   eax, word ptr [rdi+496h]
0x1800057b2  mov     edx, 10000h
0x1800057b7  mov     dword ptr [rsp+0D0h+var_60], r8d
0x1800057bc  lea     r8, aSRpcEp08x04x04_0; "[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%"...
0x1800057c3  mov     dword ptr [rsp+0D0h+var_68], r10d
0x1800057c8  mov     dword ptr [rsp+0D0h+var_70], r11d
0x1800057cd  mov     dword ptr [rsp+0D0h+var_78], ebx
0x1800057d1  mov     dword ptr [rsp+0D0h+var_80], esi
0x1800057d5  mov     dword ptr [rsp+0D0h+var_88], r14d
0x1800057da  mov     dword ptr [rsp+0D0h+var_90], r15d
0x1800057df  mov     dword ptr [rsp+0D0h+var_98], r12d
0x1800057e4  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1800057e8  movzx   eax, word ptr [rdi+494h]
0x1800057ef  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800057f3  mov     eax, [rdi+490h]
0x1800057f9  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800057fd  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180005804  nop     dword ptr [rax+rax+00h]
0x180005809  mov     r15d, [rbp+57h+arg_8]
0x18000580d  jmp     loc_1800058F0
0x180005812  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, r15; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180005819  mov     esi, 80070216h
0x18000581e  jz      short loc_180005865
0x180005820  call    cs:__imp_GetLastError
0x180005827  nop     dword ptr [rax+rax+00h]
0x18000582c  lea     r9, dword_18001F974
0x180005833  mov     dword ptr [rsp+0D0h+var_A8], esi
0x180005837  mov     [rsp+0D0h+var_B0], r9
0x18000583c  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180005843  mov     ebx, eax
0x180005845  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000584c  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180005853  mov     r9d, 539h
0x180005859  mov     ecx, 80000h
0x18000585e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005863  jmp     short loc_1800058A7
0x180005865  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, r15; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000586c  jz      short loc_1800058B5
0x18000586e  call    cs:__imp_GetLastError
0x180005875  nop     dword ptr [rax+rax+00h]
0x18000587a  lea     r9, dword_18001F974
0x180005881  mov     dword ptr [rsp+0D0h+var_B0], esi
0x180005885  mov     ebx, eax
0x180005887  lea     rdx, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x18000588e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180005895  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000589c  mov     r8d, 539h
0x1800058a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a7  mov     ecx, ebx; dwErrCode
0x1800058a9  call    cs:__imp_SetLastError
0x1800058b0  nop     dword ptr [rax+rax+00h]
0x1800058b5  call    cs:__imp_GetLastError
0x1800058bc  nop     dword ptr [rax+rax+00h]
0x1800058c1  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x1800058c8  mov     ebx, eax
0x1800058ca  jz      short loc_1800058D1
0x1800058cc  call    ElTraceErrorInfo
0x1800058d1  mov     ecx, ebx; dwErrCode
0x1800058d3  call    cs:__imp_SetLastError
0x1800058da  nop     dword ptr [rax+rax+00h]
0x1800058df  mov     ecx, esi
0x1800058e1  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800058e8  nop     dword ptr [rax+rax+00h]
0x1800058ed  mov     [rbp+57h+Reply], eax
0x1800058f0  mov     rbx, r13
0x1800058f3  mov     rsi, [rbx]
0x1800058f6  jmp     short loc_18000596F
0x1800058f8  mov     rax, [rbx]
0x1800058fb  mov     rdx, rsi
0x1800058fe  mov     rcx, [rbx+8]
0x180005902  cmp     rax, rcx
0x180005905  jnz     short loc_180005912
0x180005907  and     qword ptr [rbx+8], 0
0x18000590c  and     qword ptr [rbx], 0
0x180005910  jmp     short loc_18000593A
0x180005912  cmp     rsi, rax
0x180005915  jnz     short loc_180005928
0x180005917  mov     rax, [rax+38h]
0x18000591b  mov     [rbx], rax
0x18000591e  and     qword ptr [rax+40h], 0
0x180005923  mov     rsi, [rbx]
0x180005926  jmp     short loc_180005958
0x180005928  cmp     rsi, rcx
0x18000592b  jnz     short loc_18000593E
0x18000592d  mov     rax, [rcx+40h]
0x180005931  mov     [rbx+8], rax
0x180005935  and     qword ptr [rax+38h], 0
0x18000593a  xor     esi, esi
0x18000593c  jmp     short loc_180005958
0x18000593e  mov     rax, [rdx+40h]
0x180005942  lea     rcx, [rsi+38h]
0x180005946  mov     rsi, [rcx]
0x180005949  mov     [rax+38h], rsi
0x18000594d  mov     rcx, [rcx]
0x180005950  mov     rax, [rdx+40h]
0x180005954  mov     [rcx+40h], rax
0x180005958  dec     dword ptr [rbx+14h]
0x18000595b  test    rdx, rdx
0x18000595e  jz      short loc_18000596F
0x180005960  mov     rax, [rdx]
0x180005963  mov     rcx, rdx
0x180005966  mov     rax, [rax+8]
0x18000596a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596f  test    rsi, rsi
0x180005972  jnz     short loc_1800058F8
0x180005974  test    r15d, r15d
0x180005977  jnz     loc_180005A94
0x18000597d  mov     rax, [rdi+58h]
0x180005981  lea     rdx, [rbp+57h+Reply]; Reply
0x180005985  and     [rax], r15d
0x180005988  mov     rax, [rdi+60h]
0x18000598c  and     [rax], rsi
0x18000598f  mov     rcx, [rdi+38h]; pAsync
0x180005993  call    cs:__imp_RpcAsyncCompleteCall
0x18000599a  nop     dword ptr [rax+rax+00h]
0x18000599f  mov     r9d, 597h
0x1800059a5  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x1800059ac  mov     ecx, eax
0x1800059ae  call    ElValidateWin32
0x1800059b3  mov     [rbp+57h+Reply], eax
0x1800059b6  test    eax, eax
0x1800059b8  jnz     loc_180005A94
0x1800059be  mov     rax, [rdi+8C0h]
0x1800059c5  movzx   edx, byte ptr [rdi+49Fh]
0x1800059cc  movzx   r8d, byte ptr [rdi+49Eh]
0x1800059d4  movzx   r10d, byte ptr [rdi+49Dh]
0x1800059dc  mov     rcx, [rax+40h]
0x1800059e0  movzx   r11d, byte ptr [rdi+49Ch]
0x1800059e8  movzx   ebx, byte ptr [rdi+49Bh]
0x1800059ef  movzx   esi, byte ptr [rdi+49Ah]
0x1800059f6  movzx   r14d, byte ptr [rdi+499h]
0x1800059fe  movzx   r15d, byte ptr [rdi+498h]
0x180005a06  movzx   r12d, word ptr [rdi+496h]
0x180005a0e  movzx   r13d, word ptr [rdi+494h]
0x180005a16  test    rcx, rcx
0x180005a19  jz      short loc_180005A21
0x180005a1b  mov     r9, [rcx+10h]
0x180005a1f  jmp     short loc_180005A28
0x180005a21  lea     r9, aUnknown_0; "<Unknown>"
0x180005a28  and     dword ptr [rsp+0D0h+var_50], 0
0x180005a30  lea     rax, [rdi+84h]
0x180005a37  mov     [rsp+0D0h+var_58], rax
0x180005a3c  lea     rcx, qword_180039310
0x180005a43  mov     eax, [rdi+490h]
0x180005a49  mov     dword ptr [rsp+0D0h+var_60], edx
0x180005a4d  mov     edx, 80000h
0x180005a52  mov     dword ptr [rsp+0D0h+var_68], r8d
0x180005a57  lea     r8, aSRpcEp08x04x04_3; "[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%"...
0x180005a5e  mov     dword ptr [rsp+0D0h+var_70], r10d
0x180005a63  mov     dword ptr [rsp+0D0h+var_78], r11d
0x180005a68  mov     dword ptr [rsp+0D0h+var_80], ebx
0x180005a6c  mov     dword ptr [rsp+0D0h+var_88], esi
0x180005a70  mov     dword ptr [rsp+0D0h+var_90], r14d
0x180005a75  mov     dword ptr [rsp+0D0h+var_98], r15d
0x180005a7a  mov     dword ptr [rsp+0D0h+var_A0], r12d
0x180005a7f  mov     dword ptr [rsp+0D0h+var_A8], r13d
0x180005a84  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180005a88  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180005a8f  nop     dword ptr [rax+rax+00h]
0x180005a94  cmp     [rbp+57h+Reply], 0
0x180005a98  jz      loc_180005C0C
0x180005a9e  mov     rax, [rdi+8C0h]
0x180005aa5  lea     rsi, aUnknown_0; "<Unknown>"
0x180005aac  movzx   edx, byte ptr [rdi+49Fh]
0x180005ab3  movzx   r8d, byte ptr [rdi+49Eh]
0x180005abb  movzx   r10d, byte ptr [rdi+49Dh]
0x180005ac3  mov     rcx, [rax+40h]
0x180005ac7  movzx   r11d, byte ptr [rdi+49Ch]
0x180005acf  movzx   r14d, byte ptr [rdi+49Bh]
0x180005ad7  movzx   r15d, byte ptr [rdi+49Ah]
0x180005adf  movzx   r12d, byte ptr [rdi+499h]
0x180005ae7  movzx   r13d, byte ptr [rdi+498h]
0x180005aef  test    rcx, rcx
0x180005af2  jz      short loc_180005AFA
0x180005af4  mov     r9, [rcx+10h]
0x180005af8  jmp     short loc_180005AFD
0x180005afa  mov     r9, rsi
0x180005afd  mov     eax, [rbp+57h+Reply]
0x180005b00  lea     rbx, [rdi+84h]
0x180005b07  mov     dword ptr [rsp+0D0h+var_50], eax
0x180005b0e  lea     rcx, qword_180039310
0x180005b15  movzx   eax, word ptr [rdi+496h]
0x180005b1c  mov     [rsp+0D0h+var_58], rbx
0x180005b21  mov     dword ptr [rsp+0D0h+var_60], edx
0x180005b25  mov     edx, 80000h
0x180005b2a  mov     dword ptr [rsp+0D0h+var_68], r8d
0x180005b2f  lea     r8, aSRpcEp08x04x04_2; "[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%"...
0x180005b36  mov     dword ptr [rsp+0D0h+var_70], r10d
0x180005b3b  mov     dword ptr [rsp+0D0h+var_78], r11d
0x180005b40  mov     dword ptr [rsp+0D0h+var_80], r14d
0x180005b45  mov     dword ptr [rsp+0D0h+var_88], r15d
0x180005b4a  mov     dword ptr [rsp+0D0h+var_90], r12d
0x180005b4f  mov     dword ptr [rsp+0D0h+var_98], r13d
0x180005b54  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180005b58  movzx   eax, word ptr [rdi+494h]
0x180005b5f  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180005b63  mov     eax, [rdi+490h]
0x180005b69  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180005b6d  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180005b74  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
