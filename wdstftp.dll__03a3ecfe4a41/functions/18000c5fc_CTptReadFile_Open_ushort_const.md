# CTptReadFile::Open(ushort const *)

- ea: `0x18000c5fc`
- end: `0x18000c87d`
- name: `?Open@CTptReadFile@@QEAAKPEBG@Z`
- size: `641`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006590`
- `0x180008d80`
- `0x180009008`

## callees

- `0x18000be08`
- `0x18000c168`
- `0x18000c5fc`
- `0x18000c884`
- `0x18000c9c4`
- `0x18003bd24`
- `0x18003ce78`
- `0x18003cf50`
- `0x18003d028`
- `0x1800607b0`
- `0x180060808`
- `0x180060e70`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000c697`
- `msvcrt!wcsrchr` at `0x18000c697`
- `msvcrt!_wcsicmp` at `0x18000c6b5`
- `msvcrt!_wcsicmp` at `0x18000c6cf`
- `msvcrt!_wcsicmp` at `0x18000c6b5`
- `msvcrt!_wcsicmp` at `0x18000c6cf`
- `KERNEL32!EnterCriticalSection` at `0x18000c627`
- `KERNEL32!EnterCriticalSection` at `0x18000c627`
- `KERNEL32!LeaveCriticalSection` at `0x18000c849`
- `KERNEL32!LeaveCriticalSection` at `0x18000c849`
- `KERNEL32!SystemTimeToFileTime` at `0x18000c683`
- `KERNEL32!SystemTimeToFileTime` at `0x18000c683`
- `KERNEL32!GetSystemTime` at `0x18000c66e`
- `KERNEL32!GetSystemTime` at `0x18000c66e`

## string_xrefs

- `0x18000c645`: `base\eco\wds\transport\lib\tptreadfile.cpp`
- `0x18000c703`: `base\eco\wds\transport\lib\tptreadfile.cpp`
- `0x18000c757`: `base\eco\wds\transport\lib\tptreadfile.cpp`
- `0x18000c807`: `TptReadFile: File=%s, Size=%I64u`

## pseudocode

```c
__int64 __fastcall CTptReadFile::Open(LPCRITICAL_SECTION lpCriticalSection, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  const char *v5; // rdx
  wchar_t *v6; // rax
  const wchar_t *v7; // rdi
  unsigned int v8; // eax
  const char *v9; // rdx
  unsigned int v10; // r9d
  int v11; // ecx
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // r14
  int v14; // esi
  const char *v15; // rdx
  const char *v16; // r8
  unsigned int v17; // r9d
  int v18; // eax
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // rax
  void *v21; // rax
  __int64 v22; // rdx
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-48h] BYREF

  EnterCriticalSection(lpCriticalSection);
  v4 = DuplicateStringW(a2, (unsigned __int16 **)&lpCriticalSection[1].LockCount);
  if ( !ElValidateWin32(v4, v5, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x162u) )
  {
    *(_QWORD *)&SystemTime.wYear = 0;
    *(_QWORD *)&SystemTime.wHour = 0;
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, (LPFILETIME)&lpCriticalSection[2].SpinCount);
    v6 = wcsrchr(a2, 0x2Eu);
    v7 = v6;
    if ( !v6 || _wcsicmp(v6, L".wim") && _wcsicmp(v7, L".rwm") )
    {
      v8 = CTptReadFile::OpenRegularFile(lpCriticalSection, a2);
      v10 = 369;
    }
    else
    {
      v8 = CTptReadFile::OpenWIMFile(lpCriticalSection, a2);
      v10 = 364;
    }
    v4 = v8;
    if ( !ElValidateWin32(v8, v9, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", v10) )
    {
      if ( HIDWORD(lpCriticalSection[3].DebugInfo) == 1 )
      {
        v12 = (unsigned __int64)lpCriticalSection[1].LockSemaphore / LODWORD(lpCriticalSection[2].LockSemaphore);
        v13 = LODWORD(lpCriticalSection[2].LockSemaphore) * (unsigned __int64)(unsigned int)v12;
        if ( is_mul_ok(LODWORD(lpCriticalSection[2].LockSemaphore), (unsigned int)v12) )
        {
          v14 = 0;
        }
        else
        {
          v14 = -2147024362;
          v13 = -1;
        }
        ElValidateHrLite(
          v14,
          (const char *)((LODWORD(lpCriticalSection[2].LockSemaphore) * (unsigned __int128)(unsigned int)v12) >> 64),
          "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp",
          0x186u);
        if ( v14 >= 0 )
          v18 = v14;
        else
          v18 = ElValidateHr(v14, v15, v16, v17);
        if ( v18 < 0 )
        {
          if ( v14 >= 0 )
            v4 = v14;
          else
            v4 = (unsigned __int16)v14;
          goto LABEL_31;
        }
        v19 = (unsigned int)(v12 + 1);
        if ( (HANDLE)v13 >= lpCriticalSection[1].LockSemaphore )
          v19 = (unsigned int)v12;
        v20 = 8 * v19;
        if ( !is_mul_ok(v19, 8u) )
          v20 = -1;
        v21 = operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
        lpCriticalSection[3].SpinCount = (ULONG_PTR)v21;
        if ( !v21 )
        {
          v4 = 8;
LABEL_32:
          CTptReadFile::Shutdown(lpCriticalSection);
          goto LABEL_33;
        }
        v22 = 0;
        for ( LODWORD(lpCriticalSection[4].DebugInfo) = v19;
              (unsigned int)v22 < LODWORD(lpCriticalSection[4].DebugInfo);
              v22 = (unsigned int)(v22 + 1) )
        {
          *(_QWORD *)(lpCriticalSection[3].SpinCount + 8 * v22) = 0;
        }
      }
      if ( g_ErrLibTraceFunction )
        g_ErrLibTraceFunction(L"TptReadFile: File=%s, Size=%I64u", a2, lpCriticalSection[1].LockSemaphore);
      if ( (Microsoft_Windows_Deployment_Services_DiagnosticsEnableBits & 1) != 0 )
        McTemplateU0zxq(
          v11,
          (unsigned int)TptReadFileBufferCreated,
          (_DWORD)a2,
          lpCriticalSection[1].LockSemaphore,
          HIDWORD(lpCriticalSection[3].DebugInfo));
    }
  }
LABEL_31:
  if ( v4 )
    goto LABEL_32;
LABEL_33:
  LeaveCriticalSection(lpCriticalSection);
  return v4;
}

```

## disassembly

```asm
0x18000c5fc  mov     [rsp+arg_10], rbx
0x18000c601  mov     [rsp+arg_18], rbp
0x18000c606  push    rsi
0x18000c607  push    rdi
0x18000c608  push    r13
0x18000c60a  push    r14
0x18000c60c  push    r15
0x18000c60e  sub     rsp, 50h
0x18000c612  mov     rax, cs:__security_cookie
0x18000c619  xor     rax, rsp
0x18000c61c  mov     [rsp+78h+var_38], rax
0x18000c621  mov     rbp, rdx
0x18000c624  mov     rbx, rcx
0x18000c627  call    cs:__imp_EnterCriticalSection
0x18000c62e  nop     dword ptr [rax+rax+00h]
0x18000c633  lea     rdx, [rbx+30h]; unsigned __int16 **
0x18000c637  mov     rcx, rbp; unsigned __int16 *
0x18000c63a  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000c63f  mov     r9d, 162h; unsigned int
0x18000c645  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c64c  mov     ecx, eax; unsigned int
0x18000c64e  mov     edi, eax
0x18000c650  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c655  test    eax, eax
0x18000c657  jnz     loc_18000C83A
0x18000c65d  xor     eax, eax
0x18000c65f  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x18000c664  mov     qword ptr [rsp+78h+SystemTime.wYear], rax
0x18000c669  mov     qword ptr [rsp+78h+SystemTime.wHour], rax
0x18000c66e  call    cs:__imp_GetSystemTime
0x18000c675  nop     dword ptr [rax+rax+00h]
0x18000c67a  lea     rdx, [rbx+70h]; lpFileTime
0x18000c67e  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x18000c683  call    cs:__imp_SystemTimeToFileTime
0x18000c68a  nop     dword ptr [rax+rax+00h]
0x18000c68f  mov     edx, 2Eh ; '.'; Ch
0x18000c694  mov     rcx, rbp; Str
0x18000c697  call    cs:__imp_wcsrchr
0x18000c69e  nop     dword ptr [rax+rax+00h]
0x18000c6a3  mov     rdi, rax
0x18000c6a6  test    rax, rax
0x18000c6a9  jz      short loc_18000C6F2
0x18000c6ab  lea     rdx, aWim_0; ".wim"
0x18000c6b2  mov     rcx, rax; String1
0x18000c6b5  call    cs:__imp__wcsicmp
0x18000c6bc  nop     dword ptr [rax+rax+00h]
0x18000c6c1  test    eax, eax
0x18000c6c3  jz      short loc_18000C6DF
0x18000c6c5  lea     rdx, aRwm; ".rwm"
0x18000c6cc  mov     rcx, rdi; String1
0x18000c6cf  call    cs:__imp__wcsicmp
0x18000c6d6  nop     dword ptr [rax+rax+00h]
0x18000c6db  test    eax, eax
0x18000c6dd  jnz     short loc_18000C6F2
0x18000c6df  mov     rdx, rbp; unsigned __int16 *
0x18000c6e2  mov     rcx, rbx; lpCriticalSection
0x18000c6e5  call    ?OpenWIMFile@CTptReadFile@@AEAAKPEBG@Z; CTptReadFile::OpenWIMFile(ushort const *)
0x18000c6ea  mov     r9d, 16Ch
0x18000c6f0  jmp     short loc_18000C703
0x18000c6f2  mov     rdx, rbp; lpFileName
0x18000c6f5  mov     rcx, rbx; lpCriticalSection
0x18000c6f8  call    ?OpenRegularFile@CTptReadFile@@AEAAKPEBG@Z; CTptReadFile::OpenRegularFile(ushort const *)
0x18000c6fd  mov     r9d, 171h; unsigned int
0x18000c703  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c70a  mov     ecx, eax; unsigned int
0x18000c70c  mov     edi, eax
0x18000c70e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c713  test    eax, eax
0x18000c715  jnz     loc_18000C83A
0x18000c71b  cmp     dword ptr [rbx+7Ch], 1
0x18000c71f  jnz     loc_18000C7F7
0x18000c725  mov     ecx, [rbx+68h]
0x18000c728  xor     edx, edx; char *
0x18000c72a  mov     rax, [rbx+40h]
0x18000c72e  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000c732  div     rcx
0x18000c735  mov     r15, rax
0x18000c738  mov     eax, eax
0x18000c73a  mul     rcx
0x18000c73d  mov     r14, rax
0x18000c740  test    rdx, rdx
0x18000c743  jnz     short loc_18000C749
0x18000c745  xor     esi, esi
0x18000c747  jmp     short loc_18000C751
0x18000c749  mov     esi, 80070216h
0x18000c74e  mov     r14, r13
0x18000c751  mov     r9d, 186h; unsigned int
0x18000c757  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c75e  mov     ecx, esi; int
0x18000c760  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x18000c765  test    esi, esi
0x18000c767  jns     short loc_18000C772
0x18000c769  mov     ecx, esi; int
0x18000c76b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000c770  jmp     short loc_18000C774
0x18000c772  mov     eax, esi
0x18000c774  test    eax, eax
0x18000c776  jns     short loc_18000C799
0x18000c778  test    esi, esi
0x18000c77a  jns     short loc_18000C792
0x18000c77c  mov     eax, esi
0x18000c77e  and     eax, 1FFF0000h
0x18000c783  cmp     eax, 70000h
0x18000c788  jnz     short loc_18000C792
0x18000c78a  movzx   edi, si
0x18000c78d  jmp     loc_18000C83A
0x18000c792  mov     edi, esi
0x18000c794  jmp     loc_18000C83A
0x18000c799  cmp     r14, [rbx+40h]
0x18000c79d  lea     esi, [r15+1]
0x18000c7a1  mov     r14d, 8
0x18000c7a7  cmovnb  esi, r15d
0x18000c7ab  mov     eax, r14d
0x18000c7ae  mul     rsi
0x18000c7b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c7b8  cmovo   rax, r13
0x18000c7bc  mov     rcx, rax; unsigned __int64
0x18000c7bf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c7c4  mov     [rbx+98h], rax
0x18000c7cb  test    rax, rax
0x18000c7ce  jnz     short loc_18000C7D5
0x18000c7d0  mov     edi, r14d
0x18000c7d3  jmp     short loc_18000C83E
0x18000c7d5  xor     edx, edx
0x18000c7d7  mov     [rbx+0A0h], esi
0x18000c7dd  test    esi, esi
0x18000c7df  jz      short loc_18000C7F7
0x18000c7e1  mov     rax, [rbx+98h]
0x18000c7e8  and     qword ptr [rax+rdx*8], 0
0x18000c7ed  inc     edx
0x18000c7ef  cmp     edx, [rbx+0A0h]
0x18000c7f5  jb      short loc_18000C7E1
0x18000c7f7  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000c7fe  test    rax, rax
0x18000c801  jz      short loc_18000C817
0x18000c803  mov     r8, [rbx+40h]
0x18000c807  lea     rcx, aTptreadfileFil; "TptReadFile: File=%s, Size=%I64u"
0x18000c80e  mov     rdx, rbp
0x18000c811  call    cs:__guard_dispatch_icall_fptr
0x18000c817  test    cs:Microsoft_Windows_Deployment_Services_DiagnosticsEnableBits, 1
0x18000c81e  jz      short loc_18000C83A
0x18000c820  mov     eax, [rbx+7Ch]
0x18000c823  lea     rdx, TptReadFileBufferCreated
0x18000c82a  mov     r9, [rbx+40h]
0x18000c82e  mov     r8, rbp
0x18000c831  mov     [rsp+78h+var_58], eax
0x18000c835  call    McTemplateU0zxq
0x18000c83a  test    edi, edi
0x18000c83c  jz      short loc_18000C846
0x18000c83e  mov     rcx, rbx; lpCriticalSection
0x18000c841  call    ?Shutdown@CTptReadFile@@QEAAKXZ; CTptReadFile::Shutdown(void)
0x18000c846  mov     rcx, rbx; lpCriticalSection
0x18000c849  call    cs:__imp_LeaveCriticalSection
0x18000c850  nop     dword ptr [rax+rax+00h]
0x18000c855  mov     eax, edi
0x18000c857  mov     rcx, [rsp+78h+var_38]
0x18000c85c  xor     rcx, rsp; StackCookie
0x18000c85f  call    __security_check_cookie
0x18000c864  lea     r11, [rsp+78h+var_28]
0x18000c869  mov     rbx, [r11+40h]
0x18000c86d  mov     rbp, [r11+48h]
0x18000c871  mov     rsp, r11
0x18000c874  pop     r15
0x18000c876  pop     r14
0x18000c878  pop     r13
0x18000c87a  pop     rdi
0x18000c87b  pop     rsi
0x18000c87c  retn
```
