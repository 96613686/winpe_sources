# CRegKey::OpenSubKey(CRegKey &,ushort const *,ulong,ulong)

- ea: `0x18002c5b0`
- end: `0x18002c759`
- name: `?OpenSubKey@CRegKey@@QEBAHAEAV1@PEBGKK@Z`
- size: `425`
- prototype: `int(CRegKey *__hidden this, struct CRegKey *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180026a60`
- `0x18002bdb4`

## callees

- `0x18000a804`
- `0x18001c2c8`
- `0x18002c5b0`
- `0x18004d550`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18002c6c7`
- `ntdll!RtlPopFrame` at `0x18002c6c7`
- `ntdll!RtlPushFrame` at `0x18002c612`
- `ntdll!RtlPushFrame` at `0x18002c612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c73f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c73f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c69b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c718`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c69b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c718`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c659`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c659`

## pseudocode

```c
__int64 __fastcall CRegKey::OpenSubKey(HKEY *this, HKEY *a2, const unsigned __int16 *a3)
{
  HKEY v6; // rcx
  LSTATUS v7; // eax
  unsigned int i; // edx
  HKEY v9; // rax
  HKEY v10; // rdx
  unsigned int v11; // ebx
  DWORD LastError; // eax
  _DWORD v14[2]; // [rsp+30h] [rbp-68h]
  HKEY phkResult; // [rsp+38h] [rbp-60h] BYREF
  int v16; // [rsp+40h] [rbp-58h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+48h] [rbp-50h] BYREF
  __int64 v18; // [rsp+60h] [rbp-38h]
  int v19; // [rsp+68h] [rbp-30h]
  unsigned int *v20; // [rsp+70h] [rbp-28h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D380;
  Frame.Previous = 0;
  v18 = 544438355;
  v19 = 507;
  v20 = (unsigned int *)&v16;
  v16 = 0;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v6 = *this;
  phkResult = 0;
  v14[0] = 2;
  v14[1] = 3;
  v7 = RegOpenKeyExW(v6, a3, 0, 0x20119u, &phkResult);
  if ( !v7 )
    goto LABEL_9;
  for ( i = 0; i < 2; ++i )
  {
    if ( v14[i] == v7 )
    {
      v9 = 0;
      phkResult = 0;
      goto LABEL_10;
    }
  }
  if ( i == 2 )
  {
    SetLastError(v7);
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007CA20);
  }
  else
  {
LABEL_9:
    v9 = phkResult;
LABEL_10:
    v10 = *a2;
    if ( v9 != *a2 )
    {
      *a2 = v9;
      if ( v10 )
        COperatorFRegCloseKey::operator()();
    }
    SetLastError(0);
    *v20 = 1;
  }
  v11 = *v20;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v11 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v11;
}

```

## disassembly

```asm
0x18002c5b0  mov     r11, rsp
0x18002c5b3  mov     [r11+20h], rbx
0x18002c5b7  push    rbp
0x18002c5b8  push    rsi
0x18002c5b9  push    rdi
0x18002c5ba  sub     rsp, 80h
0x18002c5c1  mov     rax, cs:__security_cookie
0x18002c5c8  xor     rax, rsp
0x18002c5cb  mov     [rsp+98h+var_20], rax
0x18002c5d0  mov     [rsp+98h+Frame.Flags], 1
0x18002c5d8  lea     rax, qword_18006D380
0x18002c5df  mov     [r11-40h], rax
0x18002c5e3  xor     ebp, ebp
0x18002c5e5  lea     rax, [r11-58h]
0x18002c5e9  mov     [r11-48h], rbp
0x18002c5ed  mov     rdi, rcx
0x18002c5f0  mov     qword ptr [r11-38h], 20737853h
0x18002c5f8  mov     [rsp+98h+var_30], 1FBh
0x18002c600  lea     rcx, [r11-50h]; Frame
0x18002c604  mov     [r11-28h], rax
0x18002c608  mov     rsi, r8
0x18002c60b  mov     rbx, rdx
0x18002c60e  mov     [rsp+98h+var_58], ebp
0x18002c612  call    cs:__imp_RtlPushFrame
0x18002c619  nop     dword ptr [rax+rax+00h]
0x18002c61e  cmp     cs:g_FusionEnterExitTracingEnabled, bpl
0x18002c625  jnz     loc_18002C705
0x18002c62b  mov     rcx, [rdi]; hKey
0x18002c62e  lea     rax, [rsp+98h+var_60]
0x18002c633  mov     r9d, 20119h; samDesired
0x18002c639  mov     [rsp+98h+phkResult], rax; phkResult
0x18002c63e  xor     r8d, r8d; ulOptions
0x18002c641  mov     [rsp+98h+var_60], rbp
0x18002c646  mov     rdx, rsi; lpSubKey
0x18002c649  mov     [rsp+98h+var_68], 2
0x18002c651  mov     [rsp+98h+var_64], 3
0x18002c659  call    cs:__imp_RegOpenKeyExW
0x18002c660  nop     dword ptr [rax+rax+00h]
0x18002c665  test    eax, eax
0x18002c667  jz      short loc_18002C68C
0x18002c669  mov     edx, ebp
0x18002c66b  cmp     edx, 2
0x18002c66e  jnb     short loc_18002C686
0x18002c670  mov     ecx, edx
0x18002c672  cmp     [rsp+rcx*4+98h+var_68], eax
0x18002c676  jnz     loc_18002C70F
0x18002c67c  mov     rax, rbp
0x18002c67f  mov     [rsp+98h+var_60], rax
0x18002c684  jmp     short loc_18002C691
0x18002c686  jz      loc_18002C716
0x18002c68c  mov     rax, [rsp+98h+var_60]
0x18002c691  mov     rdx, [rbx]
0x18002c694  cmp     rax, rdx
0x18002c697  jnz     short loc_18002C6F6
0x18002c699  xor     ecx, ecx; dwErrCode
0x18002c69b  call    cs:__imp_SetLastError
0x18002c6a2  nop     dword ptr [rax+rax+00h]
0x18002c6a7  mov     rax, [rsp+98h+var_28]
0x18002c6ac  mov     dword ptr [rax], 1
0x18002c6b2  cmp     cs:g_FusionEnterExitTracingEnabled, bpl
0x18002c6b9  mov     rax, [rsp+98h+var_28]
0x18002c6be  mov     ebx, [rax]
0x18002c6c0  jnz     short loc_18002C732
0x18002c6c2  lea     rcx, [rsp+98h+Frame]; Frame
0x18002c6c7  call    cs:__imp_RtlPopFrame
0x18002c6ce  nop     dword ptr [rax+rax+00h]
0x18002c6d3  mov     eax, ebx
0x18002c6d5  mov     rcx, [rsp+98h+var_20]
0x18002c6da  xor     rcx, rsp; StackCookie
0x18002c6dd  call    __security_check_cookie
0x18002c6e2  mov     rbx, [rsp+98h+arg_18]
0x18002c6ea  add     rsp, 80h
0x18002c6f1  pop     rdi
0x18002c6f2  pop     rsi
0x18002c6f3  pop     rbp
0x18002c6f4  retn
0x18002c6f6  mov     [rbx], rax
0x18002c6f9  test    rdx, rdx
0x18002c6fc  jz      short loc_18002C699
0x18002c6fe  call    ??RCOperatorFRegCloseKey@@QEBAHPEAX@Z; COperatorFRegCloseKey::operator()(void *)
0x18002c703  jmp     short loc_18002C699
0x18002c705  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18002c70a  jmp     loc_18002C62B
0x18002c70f  inc     edx
0x18002c711  jmp     loc_18002C66B
0x18002c716  mov     ecx, eax; dwErrCode
0x18002c718  call    cs:__imp_SetLastError
0x18002c71f  nop     dword ptr [rax+rax+00h]
0x18002c724  lea     rcx, off_18007CA20; struct _CALL_SITE_INFO *
0x18002c72b  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18002c730  jmp     short loc_18002C6B2
0x18002c732  test    ebx, ebx
0x18002c734  jz      short loc_18002C73F
0x18002c736  xor     ecx, ecx; char *
0x18002c738  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18002c73d  jmp     short loc_18002C6C2
0x18002c73f  call    cs:__imp_GetLastError
0x18002c746  nop     dword ptr [rax+rax+00h]
0x18002c74b  mov     ecx, eax; unsigned int
0x18002c74d  xor     edx, edx; Format
0x18002c74f  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18002c754  jmp     loc_18002C6C2
```
