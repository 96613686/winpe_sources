# SampDumpLanguageToLog(ushort const *)

- ea: `0x180008250`
- end: `0x180008398`
- name: `?SampDumpLanguageToLog@@YAXPEBG@Z`
- size: `328`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180008c40`

## callees

- `0x180006620`
- `0x180006ed0`
- `0x180008250`
- `0x180008bb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x180008373`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x180008373`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180008291`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180008291`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000829f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000829f`

## string_xrefs

- `0x1800082de`: `%d\%d\%d  %d:%d:%d - Sid refresh operation started: Process %d, Thread %d\n`

## pseudocode

```c
void __fastcall SampDumpLanguageToLog(const unsigned __int16 *a1)
{
  unsigned __int64 v2; // rbx
  int wDay; // [rsp+20h] [rbp-58h]
  int wHour; // [rsp+28h] [rbp-50h]
  int wMinute; // [rsp+30h] [rbp-48h]
  int wSecond; // [rsp+38h] [rbp-40h]
  DWORD CurrentProcessId; // [rsp+40h] [rbp-38h]
  DWORD CurrentThreadId; // [rsp+48h] [rbp-30h]
  unsigned __int64 v9; // [rsp+50h] [rbp-28h] BYREF
  struct _SYSTEMTIME v10; // [rsp+58h] [rbp-20h] BYREF

  v10 = 0;
  v9 = 0;
  if ( SamMuiLogFile )
  {
    GetLocalTime(&v10);
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    wSecond = v10.wSecond;
    wMinute = v10.wMinute;
    wHour = v10.wHour;
    wDay = v10.wDay;
    fwprintf(
      SamMuiLogFile,
      L"%d\\%d\\%d  %d:%d:%d - Sid refresh operation started: Process %d, Thread %d\n",
      v10.wYear,
      v10.wMonth,
      wDay,
      wHour,
      wMinute,
      wSecond,
      CurrentProcessId,
      CurrentThreadId);
    if ( a1 )
    {
      fwprintf(SamMuiLogFile, L" Original Language list: ");
      v2 = 0x7FFFFFFF;
      while ( *a1 && (int)StringCchLengthW(a1, v2, &v9) >= 0 )
      {
        fwprintf(SamMuiLogFile, L"%s;", a1);
        v2 += -1LL - v9;
        a1 += v9 + 1;
      }
    }
    fwprintf(SamMuiLogFile, L"\n");
    fflush(SamMuiLogFile);
  }
}

```

## disassembly

```asm
0x180008250  mov     r11, rsp
0x180008253  mov     [r11+10h], rbx
0x180008257  mov     [r11+18h], rsi
0x18000825b  push    rdi
0x18000825c  sub     rsp, 70h
0x180008260  mov     rax, cs:__security_cookie
0x180008267  xor     rax, rsp
0x18000826a  mov     [rsp+78h+var_10], rax
0x18000826f  xor     esi, esi
0x180008271  xorps   xmm0, xmm0
0x180008274  cmp     cs:?SamMuiLogFile@@3PEAU_iobuf@@EA, rsi; _iobuf * SamMuiLogFile
0x18000827b  mov     rdi, rcx
0x18000827e  movups  [rsp+78h+var_20], xmm0
0x180008283  mov     [r11-28h], rsi
0x180008287  jz      loc_180008379
0x18000828d  lea     rcx, [r11-20h]; lpSystemTime
0x180008291  call    cs:__imp_GetLocalTime
0x180008297  call    cs:__imp_GetCurrentThreadId
0x18000829d  mov     ebx, eax
0x18000829f  call    cs:__imp_GetCurrentProcessId
0x1800082a5  movzx   ecx, word ptr [rsp+78h+var_20+0Ch]
0x1800082aa  movzx   edx, word ptr [rsp+78h+var_20+0Ah]
0x1800082af  movzx   r10d, word ptr [rsp+78h+var_20+8]
0x1800082b5  movzx   r11d, word ptr [rsp+78h+var_20+6]
0x1800082bb  movzx   r9d, word ptr [rsp+78h+var_20+2]
0x1800082c1  movzx   r8d, word ptr [rsp+78h+var_20]
0x1800082c7  mov     [rsp+78h+var_30], ebx
0x1800082cb  mov     [rsp+78h+var_38], eax
0x1800082cf  mov     [rsp+78h+var_40], ecx
0x1800082d3  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x1800082da  mov     [rsp+78h+var_48], edx
0x1800082de  lea     rdx, aDDDDDDSidRefre; "%d\\%d\\%d  %d:%d:%d - Sid refresh oper"...
0x1800082e5  mov     [rsp+78h+var_50], r10d
0x1800082ea  mov     [rsp+78h+var_58], r11d
0x1800082ef  call    fwprintf
0x1800082f4  test    rdi, rdi
0x1800082f7  jz      short loc_180008359
0x1800082f9  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x180008300  lea     rdx, aOriginalLangua; " Original Language list: "
0x180008307  call    fwprintf
0x18000830c  mov     ebx, 7FFFFFFFh
0x180008311  jmp     short loc_180008354
0x180008313  lea     r8, [rsp+78h+var_28]; unsigned __int64 *
0x180008318  mov     rdx, rbx; unsigned __int64
0x18000831b  mov     rcx, rdi; unsigned __int16 *
0x18000831e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180008323  test    eax, eax
0x180008325  js      short loc_180008359
0x180008327  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x18000832e  lea     rdx, aS; "%s;"
0x180008335  mov     r8, rdi
0x180008338  call    fwprintf
0x18000833d  mov     rcx, [rsp+78h+var_28]
0x180008342  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008346  sub     rax, rcx
0x180008349  add     rbx, rax
0x18000834c  lea     rdi, [rdi+rcx*2]
0x180008350  add     rdi, 2
0x180008354  cmp     [rdi], si
0x180008357  jnz     short loc_180008313
0x180008359  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x180008360  lea     rdx, asc_180020778; "\n"
0x180008367  call    fwprintf
0x18000836c  mov     rcx, cs:?SamMuiLogFile@@3PEAU_iobuf@@EA; Stream
0x180008373  call    cs:__imp_fflush
0x180008379  mov     rcx, [rsp+78h+var_10]
0x18000837e  xor     rcx, rsp; StackCookie
0x180008381  call    __security_check_cookie
0x180008386  lea     r11, [rsp+78h+var_8]
0x18000838b  mov     rbx, [r11+18h]
0x18000838f  mov     rsi, [r11+20h]
0x180008393  mov     rsp, r11
0x180008396  pop     rdi
0x180008397  retn
```
