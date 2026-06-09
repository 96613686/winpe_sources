# FusionpLogParseError(ushort const *,ushort const *,unsigned __int64,ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)

- ea: `0x18002e4a0`
- end: `0x18002e6c5`
- name: `?FusionpLogParseError@@YAJPEBG0_KKKPEBU_UNICODE_STRING@@2222222222222222222@Z`
- size: `549`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, unsigned int, DWORD dwMessageId, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *)`
- caller_count: `8`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002e290`
- `0x18002e6d0`
- `0x180031260`
- `0x180048e00`
- `0x1800515ec`
- `0x180069d70`
- `0x180069df4`
- `0x180069e80`

## callees

- `0x18000c000`
- `0x18002e4a0`
- `0x180058ab4`
- `0x180058cb8`
- `0x180058dc4`
- `0x180059bf0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e695`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e695`

## string_xrefs

- `0x18002e503`: `SXS.DLL: %s() entered\n`
- `0x18002e682`: `SXS.DLL: %s():%#lx exited\n`

## pseudocode

```c
__int64 __fastcall FusionpLogParseError(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int16 a3,
        unsigned int a4,
        DWORD dwMessageId,
        const struct _UNICODE_STRING *a6,
        const struct _UNICODE_STRING *a7,
        const struct _UNICODE_STRING *a8)
{
  int v11; // eax
  DWORD v12; // esi
  unsigned int v13; // edi
  __int64 v14; // rbx
  __int64 v15; // rax
  unsigned int v16; // edx
  __int64 v17; // rdx
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v24[64]; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING *v25[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v26; // [rsp+F0h] [rbp-10h]
  __int128 v27; // [rsp+100h] [rbp+0h]
  __int128 v28; // [rsp+110h] [rbp+10h]
  __int128 v29; // [rsp+120h] [rbp+20h]
  __int128 v30; // [rsp+130h] [rbp+30h]
  __int128 v31; // [rsp+140h] [rbp+40h]
  __int128 v32; // [rsp+150h] [rbp+50h]
  __int128 v33; // [rsp+160h] [rbp+60h]
  __int128 v34; // [rsp+170h] [rbp+70h]

  v11 = FusionpEventIdToError(dwMessageId);
  v12 = v11;
  if ( v11 > 0 )
    v13 = (unsigned __int16)v11 | 0x80070000;
  else
    v13 = v11;
  FusionpDbgPrintEx(0x80000002, "SXS.DLL: %s() entered\n", "FusionpLogParseError");
  *(_OWORD *)v25 = *(_OWORD *)off_18006FDD0;
  v26 = *(_OWORD *)off_18006FDE0;
  v27 = *(_OWORD *)off_18006FDF0;
  v28 = *(_OWORD *)off_18006FE00;
  v29 = *(_OWORD *)off_18006FE10;
  v30 = *(_OWORD *)off_18006FE20;
  v31 = *(_OWORD *)off_18006FE30;
  v32 = *(_OWORD *)off_18006FE40;
  v33 = *(_OWORD *)off_18006FE50;
  v34 = *(_OWORD *)off_18006FE60;
  if ( a6 )
    v25[0] = (struct _UNICODE_STRING *)a6;
  if ( a7 )
    v25[1] = (struct _UNICODE_STRING *)a7;
  if ( a8 )
    *(_QWORD *)&v26 = a8;
  v14 = -1;
  if ( a1 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a1[v15] );
  }
  else
  {
    LOWORD(v15) = 0;
  }
  v24[0] = 0;
  LOWORD(v20) = 2 * v15;
  WORD1(v20) = 2 * v15;
  v24[63] = 0;
  v23 = v24;
  LOWORD(v21) = 2 * a3;
  WORD1(v21) = 2 * a3;
  v22 = 0x800000;
  StringCchPrintfW(v24, 0x40u, L"%lld", a4, a4, v20, a1, v21, a2);
  do
    ++v14;
  while ( v23[v14] );
  *(_QWORD *)&v30 = &v20;
  *((_QWORD *)&v30 + 1) = &v21;
  *(_QWORD *)&v31 = &v22;
  LOWORD(v22) = 2 * v14;
  FusionpLogErrorToEventLog(dwMessageId, v16, (const struct _UNICODE_STRING *const *)v25);
  FusionpLogErrorToDebugger(dwMessageId, v17, (va_list *)v25);
  FusionpDbgPrintEx(0x80000002, "SXS.DLL: %s():%#lx exited\n", "FusionpLogParseError", v13);
  SetLastError(v12);
  return v13;
}

```

## disassembly

```asm
0x18002e4a0  push    rbp
0x18002e4a2  push    rbx
0x18002e4a3  push    rsi
0x18002e4a4  push    rdi
0x18002e4a5  push    r12
0x18002e4a7  push    r13
0x18002e4a9  push    r14
0x18002e4ab  lea     rbp, [rsp-90h]
0x18002e4b3  sub     rsp, 190h
0x18002e4ba  mov     rax, cs:__security_cookie
0x18002e4c1  xor     rax, rsp
0x18002e4c4  mov     [rbp+0C0h+var_40], rax
0x18002e4cb  mov     r14, rcx
0x18002e4ce  mov     [rsp+1C0h+var_1A0], r9d
0x18002e4d3  mov     ecx, [rbp+0C0h+dwMessageId]; unsigned int
0x18002e4d9  mov     r12, r8
0x18002e4dc  mov     r13, rdx
0x18002e4df  call    ?FusionpEventIdToError@@YAKK@Z; FusionpEventIdToError(ulong)
0x18002e4e4  mov     esi, eax
0x18002e4e6  test    eax, eax
0x18002e4e8  jg      short loc_18002E4EE
0x18002e4ea  mov     edi, eax
0x18002e4ec  jmp     short loc_18002E4F7
0x18002e4ee  movzx   edi, si
0x18002e4f1  or      edi, 80070000h
0x18002e4f7  lea     r8, aFusionplogpars; "FusionpLogParseError"
0x18002e4fe  mov     ecx, 80000002h; unsigned int
0x18002e503  lea     rdx, aSxsDllSEntered; "SXS.DLL: %s() entered\n"
0x18002e50a  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18002e50f  movaps  xmm0, xmmword ptr cs:off_18006FDD0
0x18002e516  xor     ecx, ecx
0x18002e518  movaps  xmm1, xmmword ptr cs:off_18006FDE0
0x18002e51f  mov     rax, [rbp+0C0h+arg_28]
0x18002e526  movups  xmmword ptr [rbp+0C0h+var_E0], xmm0
0x18002e52a  movaps  xmm0, xmmword ptr cs:off_18006FDF0
0x18002e531  movups  [rbp+0C0h+var_D0], xmm1
0x18002e535  movaps  xmm1, xmmword ptr cs:off_18006FE00
0x18002e53c  movups  [rbp+0C0h+var_C0], xmm0
0x18002e540  movaps  xmm0, xmmword ptr cs:off_18006FE10
0x18002e547  movups  [rbp+0C0h+var_B0], xmm1
0x18002e54b  movaps  xmm1, xmmword ptr cs:off_18006FE20
0x18002e552  movups  [rbp+0C0h+var_A0], xmm0
0x18002e556  movaps  xmm0, xmmword ptr cs:off_18006FE30
0x18002e55d  movups  [rbp+0C0h+var_90], xmm1
0x18002e561  movaps  xmm1, xmmword ptr cs:off_18006FE40
0x18002e568  movups  [rbp+0C0h+var_80], xmm0
0x18002e56c  movaps  xmm0, xmmword ptr cs:off_18006FE50
0x18002e573  movups  [rbp+0C0h+var_70], xmm1
0x18002e577  movaps  xmm1, xmmword ptr cs:off_18006FE60
0x18002e57e  movups  [rbp+0C0h+var_60], xmm0
0x18002e582  movups  [rbp+0C0h+var_50], xmm1
0x18002e586  test    rax, rax
0x18002e589  jz      short loc_18002E58F
0x18002e58b  mov     [rbp+0C0h+var_E0], rax
0x18002e58f  mov     rax, [rbp+0C0h+arg_30]
0x18002e596  test    rax, rax
0x18002e599  jz      short loc_18002E59F
0x18002e59b  mov     [rbp+0C0h+var_E0+8], rax
0x18002e59f  mov     rax, [rbp+0C0h+arg_38]
0x18002e5a6  test    rax, rax
0x18002e5a9  jz      short loc_18002E5AF
0x18002e5ab  mov     qword ptr [rbp+0C0h+var_D0], rax
0x18002e5af  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e5b3  test    r14, r14
0x18002e5b6  jz      short loc_18002E5C7
0x18002e5b8  mov     rax, rbx
0x18002e5bb  inc     rax
0x18002e5be  cmp     [r14+rax*2], cx
0x18002e5c3  jnz     short loc_18002E5BB
0x18002e5c5  jmp     short loc_18002E5CA
0x18002e5c7  mov     rax, rcx
0x18002e5ca  mov     r9d, [rsp+1C0h+var_1A0]
0x18002e5cf  lea     r8, aLld; "%lld"
0x18002e5d6  add     ax, ax
0x18002e5d9  mov     [rsp+1C0h+var_160], cx
0x18002e5de  mov     [rsp+1C0h+var_198], ax
0x18002e5e3  add     r12w, r12w
0x18002e5e7  mov     [rsp+1C0h+var_196], ax
0x18002e5ec  mov     edx, 40h ; '@'; unsigned __int64
0x18002e5f1  lea     rax, [rsp+1C0h+var_160]
0x18002e5f6  mov     [rbp+0C0h+var_E2], cx
0x18002e5fa  lea     rcx, [rsp+1C0h+var_160]; unsigned __int16 *
0x18002e5ff  mov     [rsp+1C0h+var_168], rax
0x18002e604  mov     [rsp+1C0h+var_190], r14
0x18002e609  mov     [rsp+1C0h+var_180], r13
0x18002e60e  mov     [rsp+1C0h+var_188], r12w
0x18002e614  mov     [rsp+1C0h+var_186], r12w
0x18002e61a  mov     [rsp+1C0h+var_170], 800000h
0x18002e622  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e627  mov     rax, [rsp+1C0h+var_168]
0x18002e62c  xor     ecx, ecx
0x18002e62e  inc     rbx
0x18002e631  cmp     [rax+rbx*2], cx
0x18002e635  jnz     short loc_18002E62E
0x18002e637  mov     ecx, [rbp+0C0h+dwMessageId]; unsigned int
0x18002e63d  lea     rax, [rsp+1C0h+var_198]
0x18002e642  mov     qword ptr [rbp+0C0h+var_90], rax
0x18002e646  lea     r8, [rbp+0C0h+var_E0]; struct _UNICODE_STRING **
0x18002e64a  lea     rax, [rsp+1C0h+var_188]
0x18002e64f  add     bx, bx
0x18002e652  mov     qword ptr [rbp+0C0h+var_90+8], rax
0x18002e656  lea     rax, [rsp+1C0h+var_170]
0x18002e65b  mov     qword ptr [rbp+0C0h+var_80], rax
0x18002e65f  mov     word ptr [rsp+1C0h+var_170], bx
0x18002e664  call    ?FusionpLogErrorToEventLog@@YAJKKPEBQEBU_UNICODE_STRING@@@Z; FusionpLogErrorToEventLog(ulong,ulong,_UNICODE_STRING const * const *)
0x18002e669  mov     ecx, [rbp+0C0h+dwMessageId]; dwMessageId
0x18002e66f  lea     r8, [rbp+0C0h+var_E0]; struct _UNICODE_STRING **
0x18002e673  call    ?FusionpLogErrorToDebugger@@YAJKKPEBQEBU_UNICODE_STRING@@@Z; FusionpLogErrorToDebugger(ulong,ulong,_UNICODE_STRING const * const *)
0x18002e678  mov     r9d, edi
0x18002e67b  lea     r8, aFusionplogpars; "FusionpLogParseError"
0x18002e682  lea     rdx, aSxsDllSLxExite; "SXS.DLL: %s():%#lx exited\n"
0x18002e689  mov     ecx, 80000002h; unsigned int
0x18002e68e  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18002e693  mov     ecx, esi; dwErrCode
0x18002e695  call    cs:__imp_SetLastError
0x18002e69c  nop     dword ptr [rax+rax+00h]
0x18002e6a1  mov     eax, edi
0x18002e6a3  mov     rcx, [rbp+0C0h+var_40]
0x18002e6aa  xor     rcx, rsp; StackCookie
0x18002e6ad  call    __security_check_cookie
0x18002e6b2  add     rsp, 190h
0x18002e6b9  pop     r14
0x18002e6bb  pop     r13
0x18002e6bd  pop     r12
0x18002e6bf  pop     rdi
0x18002e6c0  pop     rsi
0x18002e6c1  pop     rbx
0x18002e6c2  pop     rbp
0x18002e6c3  retn
```
