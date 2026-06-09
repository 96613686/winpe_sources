# FusionpLogActCtxGenError(ulong,ushort const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)

- ea: `0x180058904`
- end: `0x180058aab`
- name: `?FusionpLogActCtxGenError@@YAJKPEBGPEBU_UNICODE_STRING@@111@Z`
- size: `423`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, const unsigned __int16 *@<rdx>, const struct _UNICODE_STRING *@<r8>, const struct _UNICODE_STRING *@<r9>, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180002a70`
- `0x180016870`
- `0x1800278b0`
- `0x18002bdb4`
- `0x18003f060`
- `0x1800659f0`

## callees

- `0x18000c000`
- `0x180058904`
- `0x180058ab4`
- `0x180058cb8`
- `0x180058dc4`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058a75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058a75`

## string_xrefs

- `0x180058961`: `SXS.DLL: %s() entered\n`
- `0x180058a62`: `SXS.DLL: %s():%#lx exited\n`

## pseudocode

```c
__int64 __fastcall FusionpLogActCtxGenError(
        unsigned int a1,
        const unsigned __int16 *a2,
        const struct _UNICODE_STRING *a3,
        const struct _UNICODE_STRING *a4,
        const struct _UNICODE_STRING *a5)
{
  int v9; // eax
  DWORD v10; // edi
  unsigned int v11; // ebx
  unsigned int v12; // edx
  __int64 v13; // rax
  __int64 v14; // rdx
  _WORD v16[4]; // [rsp+20h] [rbp-A9h] BYREF
  const unsigned __int16 *v17; // [rsp+28h] [rbp-A1h]
  struct _UNICODE_STRING *v18[2]; // [rsp+30h] [rbp-99h] BYREF
  __int128 v19; // [rsp+40h] [rbp-89h]
  __int128 v20; // [rsp+50h] [rbp-79h]
  __int128 v21; // [rsp+60h] [rbp-69h]
  __int128 v22; // [rsp+70h] [rbp-59h]
  __int128 v23; // [rsp+80h] [rbp-49h]
  __int128 v24; // [rsp+90h] [rbp-39h]
  __int128 v25; // [rsp+A0h] [rbp-29h]
  __int128 v26; // [rsp+B0h] [rbp-19h]
  __int128 v27; // [rsp+C0h] [rbp-9h]

  v9 = FusionpEventIdToError(a1);
  v10 = v9;
  if ( v9 > 0 )
    v11 = (unsigned __int16)v9 | 0x80070000;
  else
    v11 = v9;
  FusionpDbgPrintEx(0x80000002, "SXS.DLL: %s() entered\n", "FusionpLogActCtxGenError");
  *(_OWORD *)v18 = *(_OWORD *)off_180072BB0;
  v19 = *(_OWORD *)off_180072BC0;
  v20 = *(_OWORD *)off_180072BD0;
  v21 = *(_OWORD *)off_180072BE0;
  v22 = *(_OWORD *)off_180072BF0;
  v23 = *(_OWORD *)off_180072C00;
  v24 = *(_OWORD *)off_180072C10;
  v25 = *(_OWORD *)off_180072C20;
  v26 = *(_OWORD *)off_180072C30;
  v27 = *(_OWORD *)off_180072C40;
  if ( a3 )
    v18[0] = (struct _UNICODE_STRING *)a3;
  if ( a4 )
    v18[1] = (struct _UNICODE_STRING *)a4;
  if ( a5 )
    *(_QWORD *)&v19 = a5;
  *((_QWORD *)&v19 + 1) = &g_strEmptyUnicodeString;
  if ( a2 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
  }
  else
  {
    LOWORD(v13) = 0;
  }
  v17 = a2;
  v16[0] = 2 * v13;
  v16[1] = 2 * v13;
  *(_QWORD *)&v23 = v16;
  FusionpLogErrorToEventLog(a1, v12, (const struct _UNICODE_STRING *const *)v18);
  FusionpLogErrorToDebugger(a1, v14, (va_list *)v18);
  FusionpDbgPrintEx(0x80000002, "SXS.DLL: %s():%#lx exited\n", "FusionpLogActCtxGenError", v11);
  SetLastError(v10);
  return v11;
}

```

## disassembly

```asm
0x180058904  mov     [rsp-8+arg_10], rbx
0x180058909  push    rbp
0x18005890a  push    rsi
0x18005890b  push    rdi
0x18005890c  push    r12
0x18005890e  push    r13
0x180058910  push    r14
0x180058912  push    r15
0x180058914  lea     rbp, [rsp-17h]
0x180058919  sub     rsp, 0E0h
0x180058920  mov     rax, cs:__security_cookie
0x180058927  xor     rax, rsp
0x18005892a  mov     [rbp+47h+var_40], rax
0x18005892e  mov     r14, r9
0x180058931  mov     r12, r8
0x180058934  mov     rsi, rdx
0x180058937  mov     r15d, ecx
0x18005893a  call    ?FusionpEventIdToError@@YAKK@Z; FusionpEventIdToError(ulong)
0x18005893f  xor     r13d, r13d
0x180058942  mov     edi, eax
0x180058944  test    eax, eax
0x180058946  jg      short loc_18005894C
0x180058948  mov     ebx, eax
0x18005894a  jmp     short loc_180058955
0x18005894c  movzx   ebx, di
0x18005894f  or      ebx, 80070000h
0x180058955  lea     r8, aFusionplogactc; "FusionpLogActCtxGenError"
0x18005895c  mov     ecx, 80000002h; unsigned int
0x180058961  lea     rdx, aSxsDllSEntered; "SXS.DLL: %s() entered\n"
0x180058968  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18005896d  movaps  xmm0, xmmword ptr cs:off_180072BB0
0x180058974  movaps  xmm1, xmmword ptr cs:off_180072BC0
0x18005897b  movups  xmmword ptr [rsp+110h+var_E0], xmm0
0x180058980  movaps  xmm0, xmmword ptr cs:off_180072BD0
0x180058987  movups  [rsp+110h+var_D0], xmm1
0x18005898c  movaps  xmm1, xmmword ptr cs:off_180072BE0
0x180058993  movups  [rbp+47h+var_C0], xmm0
0x180058997  movaps  xmm0, xmmword ptr cs:off_180072BF0
0x18005899e  movups  [rbp+47h+var_B0], xmm1
0x1800589a2  movaps  xmm1, xmmword ptr cs:off_180072C00
0x1800589a9  movups  [rbp+47h+var_A0], xmm0
0x1800589ad  movaps  xmm0, xmmword ptr cs:off_180072C10
0x1800589b4  movups  [rbp+47h+var_90], xmm1
0x1800589b8  movaps  xmm1, xmmword ptr cs:off_180072C20
0x1800589bf  movups  [rbp+47h+var_80], xmm0
0x1800589c3  movaps  xmm0, xmmword ptr cs:off_180072C30
0x1800589ca  movups  [rbp+47h+var_70], xmm1
0x1800589ce  movaps  xmm1, xmmword ptr cs:off_180072C40
0x1800589d5  movups  [rbp+47h+var_60], xmm0
0x1800589d9  movups  [rbp+47h+var_50], xmm1
0x1800589dd  test    r12, r12
0x1800589e0  jz      short loc_1800589E7
0x1800589e2  mov     [rsp+110h+var_E0], r12
0x1800589e7  test    r14, r14
0x1800589ea  jz      short loc_1800589F1
0x1800589ec  mov     [rsp+110h+var_E0+8], r14
0x1800589f1  mov     rax, [rbp+47h+arg_20]
0x1800589f5  test    rax, rax
0x1800589f8  jz      short loc_1800589FF
0x1800589fa  mov     qword ptr [rsp+110h+var_D0], rax
0x1800589ff  lea     rax, ?g_strEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const g_strEmptyUnicodeString
0x180058a06  mov     qword ptr [rsp+110h+var_D0+8], rax
0x180058a0b  test    rsi, rsi
0x180058a0e  jz      short loc_180058A20
0x180058a10  or      rax, 0FFFFFFFFFFFFFFFFh
0x180058a14  inc     rax
0x180058a17  cmp     [rsi+rax*2], r13w
0x180058a1c  jnz     short loc_180058A14
0x180058a1e  jmp     short loc_180058A23
0x180058a20  mov     rax, r13
0x180058a23  add     ax, ax
0x180058a26  mov     [rsp+110h+var_E8], rsi
0x180058a2b  mov     [rsp+110h+var_F0], ax
0x180058a30  lea     r8, [rsp+110h+var_E0]; struct _UNICODE_STRING **
0x180058a35  mov     [rsp+110h+var_EE], ax
0x180058a3a  mov     ecx, r15d; unsigned int
0x180058a3d  lea     rax, [rsp+110h+var_F0]
0x180058a42  mov     qword ptr [rbp+47h+var_90], rax
0x180058a46  call    ?FusionpLogErrorToEventLog@@YAJKKPEBQEBU_UNICODE_STRING@@@Z; FusionpLogErrorToEventLog(ulong,ulong,_UNICODE_STRING const * const *)
0x180058a4b  lea     r8, [rsp+110h+var_E0]; struct _UNICODE_STRING **
0x180058a50  mov     ecx, r15d; dwMessageId
0x180058a53  call    ?FusionpLogErrorToDebugger@@YAJKKPEBQEBU_UNICODE_STRING@@@Z; FusionpLogErrorToDebugger(ulong,ulong,_UNICODE_STRING const * const *)
0x180058a58  mov     r9d, ebx
0x180058a5b  lea     r8, aFusionplogactc; "FusionpLogActCtxGenError"
0x180058a62  lea     rdx, aSxsDllSLxExite; "SXS.DLL: %s():%#lx exited\n"
0x180058a69  mov     ecx, 80000002h; unsigned int
0x180058a6e  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180058a73  mov     ecx, edi; dwErrCode
0x180058a75  call    cs:__imp_SetLastError
0x180058a7c  nop     dword ptr [rax+rax+00h]
0x180058a81  mov     eax, ebx
0x180058a83  mov     rcx, [rbp+47h+var_40]
0x180058a87  xor     rcx, rsp; StackCookie
0x180058a8a  call    __security_check_cookie
0x180058a8f  mov     rbx, [rsp+110h+arg_10]
0x180058a97  add     rsp, 0E0h
0x180058a9e  pop     r15
0x180058aa0  pop     r14
0x180058aa2  pop     r13
0x180058aa4  pop     r12
0x180058aa6  pop     rdi
0x180058aa7  pop     rsi
0x180058aa8  pop     rbp
0x180058aa9  retn
```
