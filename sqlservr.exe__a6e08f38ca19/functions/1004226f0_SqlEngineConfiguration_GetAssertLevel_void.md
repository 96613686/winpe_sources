# SqlEngineConfiguration::GetAssertLevel(void)

- ea: `0x1004226f0`
- end: `0x1004228f5`
- name: `?GetAssertLevel@SqlEngineConfiguration@@UEAAHXZ`
- size: `517`
- prototype: `__int64 __fastcall(SqlEngineConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x100401580`
- `0x100401800`
- `0x100401aa0`
- `0x100402080`
- `0x1004021d0`
- `0x1004226f0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x10042271f`
- `KERNEL32!GetTickCount` at `0x10042271f`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x1004227b1`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x1004227b1`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10042275a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100422874`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10042275a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100422874`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1004227c2`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1004227c2`
- `sqldk!?DebugBreakUncatchable@SOS_OS@@SAXXZ` at `0x1004227b7`
- `sqldk!?DebugBreakUncatchable@SOS_OS@@SAXXZ` at `0x1004227b7`
- `api-ms-win-crt-convert-l1-1-0!_wcstol_l` at `0x10042288d`
- `api-ms-win-crt-convert-l1-1-0!_wcstol_l` at `0x10042288d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SqlEngineConfiguration::GetAssertLevel(SqlEngineConfiguration *this)
{
  DWORD TickCount; // eax
  int v3; // edi
  __int64 v5; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // edi
  int v10; // eax
  __crt_locale_pointers *v11; // rax
  int v12; // eax
  int v13; // eax
  HKEY v14; // [rsp+50h] [rbp-268h] BYREF
  DWORD v15; // [rsp+58h] [rbp-260h] BYREF
  int v16; // [rsp+5Ch] [rbp-25Ch] BYREF
  __int64 v17; // [rsp+60h] [rbp-258h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-250h] BYREF
  wchar_t String[15]; // [rsp+70h] [rbp-248h] BYREF
  char v20; // [rsp+8Fh] [rbp-229h]
  wchar_t Buffer[264]; // [rsp+90h] [rbp-228h] BYREF

  v17 = -2;
  TickCount = GetTickCount();
  v3 = TickCount;
  if ( dword_1004A3360 != -1 && (int)abs32(TickCount - dword_1004D4800) < 30000 )
    return (unsigned int)dword_1004A3360;
  v5 = (*(__int64 (__fastcall **)(SqlEngineConfiguration *))(*(_QWORD *)this + 272LL))(this);
  DefaultLocale = GetDefaultLocale();
  v7 = StringCchPrintf_lW(Buffer, 0x104u, L"%ls", DefaultLocale, v5);
  v8 = 0;
  if ( v7 < 0 )
  {
    stackTrace(0, 0, L"Assert String Routine Failure", 63, 28, 0, 0, 0, 0);
    SOS_OS::DebugBreakUncatchable();
    SQLExit(326);
  }
  v14 = 0;
  if ( !IniRegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &v14) )
  {
    v15 = 32;
    if ( !(unsigned int)IniRegQueryValueExW((int)v14, (int)L"AssertLevel", 0, (int)&v16, (LPBYTE)String, &v15) )
    {
      if ( v16 == 1 )
      {
        v20 = 0;
        v11 = GetDefaultLocale();
        v10 = _wcstol_l(String, &EndPtr, 10, v11);
      }
      else
      {
        if ( v16 != 4 )
          goto LABEL_23;
        v10 = *(_DWORD *)String;
      }
      if ( !v10 )
      {
LABEL_24:
        dword_1004A3360 = v8;
        dword_1004D4800 = v3;
        if ( v14 )
          IniRegCloseKey(v14);
        return v8;
      }
      v12 = v10 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( !v13 )
        {
          v8 = 2;
          goto LABEL_24;
        }
        if ( v13 == 1 )
        {
          v8 = 3;
          goto LABEL_24;
        }
      }
LABEL_23:
      v8 = 1;
      goto LABEL_24;
    }
  }
  v9 = dword_1004A3360;
  if ( dword_1004A3360 == -1 )
    v9 = 1;
  if ( v14 )
    IniRegCloseKey(v14);
  return v9;
}

```

## disassembly

```asm
0x1004226f0  push    rdi
0x1004226f2  sub     rsp, 2B0h
0x1004226f9  mov     [rsp+2B8h+var_258], 0FFFFFFFFFFFFFFFEh
0x100422702  mov     [rsp+2B8h+arg_8], rbx
0x10042270a  mov     rax, cs:__security_cookie
0x100422711  xor     rax, rsp
0x100422714  mov     [rsp+2B8h+var_18], rax
0x10042271c  mov     rbx, rcx
0x10042271f  call    cs:__imp_GetTickCount
0x100422725  mov     edi, eax
0x100422727  mov     ecx, cs:dword_1004A3360
0x10042272d  cmp     ecx, 0FFFFFFFFh
0x100422730  jz      short loc_10042274B
0x100422732  sub     eax, cs:dword_1004D4800
0x100422738  cdq
0x100422739  xor     eax, edx
0x10042273b  sub     eax, edx
0x10042273d  cmp     eax, 7530h
0x100422742  jge     short loc_10042274B
0x100422744  mov     eax, ecx
0x100422746  jmp     loc_1004228D4
0x10042274b  mov     rax, [rbx]
0x10042274e  mov     rcx, rbx
0x100422751  call    qword ptr [rax+110h]
0x100422757  mov     rbx, rax
0x10042275a  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100422760  mov     r9, rax; struct __crt_locale_pointers *
0x100422763  mov     [rsp+2B8h+var_298], rbx
0x100422768  lea     r8, aLs; "%ls"
0x10042276f  mov     edx, 104h; unsigned __int64
0x100422774  lea     rcx, [rsp+2B8h+Buffer]; Buffer
0x10042277c  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100422781  xor     ebx, ebx
0x100422783  test    eax, eax
0x100422785  jns     short loc_1004227C8
0x100422787  mov     [rsp+2B8h+var_278], rbx
0x10042278c  mov     [rsp+2B8h+var_280], rbx
0x100422791  mov     [rsp+2B8h+var_288], ebx
0x100422795  mov     [rsp+2B8h+var_290], rbx
0x10042279a  mov     dword ptr [rsp+2B8h+var_298], 1Ch
0x1004227a2  lea     r9d, [rbx+3Fh]
0x1004227a6  lea     r8, aAssertStringRo; "Assert String Routine Failure"
0x1004227ad  xor     edx, edx
0x1004227af  xor     ecx, ecx
0x1004227b1  call    cs:__imp_?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z; stackTrace(SOS_Task *,ExecutionContext *,wchar_t const *,ulong,StackTraceClass,CDStream *,WatsonBucketHint,_GUID const *,CopiedStackInfo *)
0x1004227b7  call    cs:__imp_?DebugBreakUncatchable@SOS_OS@@SAXXZ; SOS_OS::DebugBreakUncatchable(void)
0x1004227bd  mov     ecx, 146h
0x1004227c2  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x1004227c8  mov     [rsp+2B8h+var_268], rbx
0x1004227cd  lea     rax, [rsp+2B8h+var_268]
0x1004227d2  mov     [rsp+2B8h+var_298], rax; PHKEY
0x1004227d7  mov     r9d, 20019h; int
0x1004227dd  xor     r8d, r8d; int
0x1004227e0  lea     rdx, [rsp+2B8h+Buffer]; int
0x1004227e8  mov     rcx, 0FFFFFFFF80000002h; int
0x1004227ef  call    IniRegOpenKeyExW
0x1004227f4  test    eax, eax
0x1004227f6  jz      short loc_10042281F
0x1004227f8  mov     edi, cs:dword_1004A3360
0x1004227fe  mov     ebx, 1
0x100422803  cmp     edi, 0FFFFFFFFh
0x100422806  cmovz   edi, ebx
0x100422809  mov     rcx, [rsp+2B8h+var_268]
0x10042280e  test    rcx, rcx
0x100422811  jz      short loc_100422818
0x100422813  call    IniRegCloseKey
0x100422818  mov     eax, edi
0x10042281a  jmp     loc_1004228D4
0x10042281f  mov     [rsp+2B8h+var_260], 20h ; ' '
0x100422827  lea     rax, [rsp+2B8h+var_260]
0x10042282c  mov     [rsp+2B8h+var_290], rax; LPDWORD
0x100422831  lea     rax, [rsp+2B8h+String]
0x100422836  mov     [rsp+2B8h+var_298], rax; LPBYTE
0x10042283b  lea     r9, [rsp+2B8h+var_25C]; int
0x100422840  xor     r8d, r8d; int
0x100422843  lea     rdx, aAssertlevel; "AssertLevel"
0x10042284a  mov     rcx, [rsp+2B8h+var_268]; int
0x10042284f  call    IniRegQueryValueExW
0x100422854  test    eax, eax
0x100422856  jnz     short loc_1004227F8
0x100422858  mov     eax, [rsp+2B8h+var_25C]
0x10042285c  sub     eax, 1
0x10042285f  jz      short loc_10042286C
0x100422861  cmp     eax, 3
0x100422864  jnz     short loc_1004228B2
0x100422866  mov     eax, dword ptr [rsp+2B8h+String]
0x10042286a  jmp     short loc_100422893
0x10042286c  mov     [rsp+2B8h+var_229], 0
0x100422874  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10042287a  mov     r9, rax; Locale
0x10042287d  mov     r8d, 0Ah; Radix
0x100422883  lea     rdx, [rsp+2B8h+EndPtr]; EndPtr
0x100422888  lea     rcx, [rsp+2B8h+String]; String
0x10042288d  call    cs:__imp__wcstol_l
0x100422893  test    eax, eax
0x100422895  jz      short loc_1004228B7
0x100422897  sub     eax, 1
0x10042289a  jz      short loc_1004228B2
0x10042289c  sub     eax, 1
0x10042289f  jz      short loc_1004228AB
0x1004228a1  cmp     eax, 1
0x1004228a4  jnz     short loc_1004228B2
0x1004228a6  lea     ebx, [rax+2]
0x1004228a9  jmp     short loc_1004228B7
0x1004228ab  mov     ebx, 2
0x1004228b0  jmp     short loc_1004228B7
0x1004228b2  mov     ebx, 1
0x1004228b7  mov     cs:dword_1004A3360, ebx
0x1004228bd  mov     cs:dword_1004D4800, edi
0x1004228c3  mov     rcx, [rsp+2B8h+var_268]
0x1004228c8  test    rcx, rcx
0x1004228cb  jz      short loc_1004228D2
0x1004228cd  call    IniRegCloseKey
0x1004228d2  mov     eax, ebx
0x1004228d4  mov     rcx, [rsp+2B8h+var_18]
0x1004228dc  xor     rcx, rsp; StackCookie
0x1004228df  call    __security_check_cookie
0x1004228e4  mov     rbx, [rsp+2B8h+arg_8]
0x1004228ec  add     rsp, 2B0h
0x1004228f3  pop     rdi
0x1004228f4  retn
```
