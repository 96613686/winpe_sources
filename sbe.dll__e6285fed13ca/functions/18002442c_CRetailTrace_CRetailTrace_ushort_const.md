# CRetailTrace::CRetailTrace(ushort const *)

- ea: `0x18002442c`
- end: `0x180024674`
- name: `??0CRetailTrace@@QEAA@PEBG@Z`
- size: `584`
- prototype: `CRetailTrace *__fastcall(CRetailTrace *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018c10`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x18000256c`
- `0x180002b7c`
- `0x18000624c`
- `0x18002442c`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x180024571`
- `KERNEL32!GetTempPath2W` at `0x180024571`
- `KERNEL32!OutputDebugStringA` at `0x1800245e6`
- `KERNEL32!OutputDebugStringA` at `0x180024606`
- `KERNEL32!OutputDebugStringA` at `0x18002464f`
- `KERNEL32!OutputDebugStringA` at `0x1800245e6`
- `KERNEL32!OutputDebugStringA` at `0x180024606`
- `KERNEL32!OutputDebugStringA` at `0x18002464f`
- `KERNEL32!CreateFileW` at `0x180024639`
- `KERNEL32!CreateFileW` at `0x180024639`
- `ADVAPI32!RegQueryValueExW` at `0x18002452a`
- `ADVAPI32!RegQueryValueExW` at `0x18002452a`
- `ADVAPI32!RegCloseKey` at `0x180024546`
- `ADVAPI32!RegCloseKey` at `0x180024546`
- `ADVAPI32!RegOpenKeyExW` at `0x1800244ee`
- `ADVAPI32!RegOpenKeyExW` at `0x1800244ee`

## string_xrefs

- `0x180024498`: `CRetailTrace::CRetailTrace() - fatal tracing error: StringCchCopy() failed`
- `0x1800245df`: `CRetailTrace::CRetailTrace() - fatal tracing error: StringCchCopy() failed`
- `0x180024648`: `CRetailTrace::CRetailTrace() - fatal tracing error: CreateFile() returned INVALID_HANDLE_VALUE`
- `0x1800245ff`: `CRetailTrace::CRetailTrace() - fatal tracing error: GetTempPath2() returned 0`

## pseudocode

```c
CRetailTrace *__fastcall CRetailTrace::CRetailTrace(CRetailTrace *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // r11
  const CHAR *v4; // rcx
  char v5; // di
  unsigned int TempPath2W; // eax
  unsigned __int64 v7; // rdi
  unsigned __int16 *v8; // rax
  const CHAR *v9; // rcx
  const CHAR *v10; // rcx
  unsigned __int64 v11; // rdx
  const WCHAR *v12; // rcx
  HANDLE FileW; // rax
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v18[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[1024]; // [rsp+260h] [rbp+160h] BYREF

  *(_DWORD *)this = 1;
  *((_BYTE *)this + 4) = 1;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = -1;
  hKey = 0;
  if ( (int)StringCchCopyW(SubKey, 0x400u, L"SOFTWARE\\Microsoft\\DirectShow\\Debug\\") < 0 )
  {
    v4 = "CRetailTrace::CRetailTrace() - fatal tracing error: StringCchCopy() failed";
LABEL_23:
    OutputDebugStringA(v4);
    return this;
  }
  if ( (int)StringCchCatW(SubKey, v3, L"multimedia\\dshow\\filters\\sbe\\analysis\\mp2v2a\\RetailTrace.h") < 0 )
  {
    v4 = "CRetailTrace::CRetailTrace() - fatal tracing error: StringCchCat() failed";
    goto LABEL_23;
  }
  v5 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TracePriority", 0, 0, Data, &cbData) )
    {
      v5 = 1;
      *(_DWORD *)this = *(_DWORD *)Data;
      *((_BYTE *)this + 4) = 0;
    }
    RegCloseKey(hKey);
  }
  memset_0(v18, 0, 0x208u);
  if ( v5 )
  {
    TempPath2W = GetTempPath2W(260, v18);
    if ( !TempPath2W )
    {
      v9 = "CRetailTrace::CRetailTrace() - fatal tracing error: GetTempPath2() returned 0";
      goto LABEL_19;
    }
    v7 = TempPath2W + 17LL;
    v8 = (unsigned __int16 *)operator new[](saturated_mul(v7, 2u));
    *((_QWORD *)this + 1) = v8;
    if ( !v8 )
    {
      v9 = "CRetailTrace::CRetailTrace() - fatal tracing error: Couldn't allocate file name";
LABEL_19:
      OutputDebugStringA(v9);
      goto LABEL_20;
    }
    if ( (int)StringCchCopyW(v8, v7, v18) < 0 )
    {
      v10 = "CRetailTrace::CRetailTrace() - fatal tracing error: StringCchCopy() failed";
    }
    else
    {
      if ( (int)StringCchCatW(*((unsigned __int16 **)this + 1), v7, L"RetailTrace.txt") >= 0 )
      {
LABEL_20:
        v12 = (const WCHAR *)*((_QWORD *)this + 1);
        if ( v12 )
        {
          FileW = CreateFileW(v12, 4u, 3u, 0, 4u, 0, 0);
          *((_QWORD *)this + 2) = FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            v4 = "CRetailTrace::CRetailTrace() - fatal tracing error: CreateFile() returned INVALID_HANDLE_VALUE";
            goto LABEL_23;
          }
        }
        return this;
      }
      v10 = "CRetailTrace::CRetailTrace() - fatal tracing error: StringCchCat() failed";
    }
    OutputDebugStringA(v10);
    operator delete(*((void **)this + 1), v11);
    *((_QWORD *)this + 1) = 0;
    goto LABEL_20;
  }
  return this;
}

```

## disassembly

```asm
0x18002442c  push    rbp
0x18002442e  push    rbx
0x18002442f  push    rdi
0x180024430  push    r15
0x180024432  lea     rbp, [rsp-978h]
0x18002443a  sub     rsp, 0A78h
0x180024441  mov     rax, cs:__security_cookie
0x180024448  xor     rax, rsp
0x18002444b  mov     [rbp+990h+var_30], rax
0x180024452  mov     rbx, rcx
0x180024455  mov     dword ptr [rcx], 1
0x18002445b  mov     byte ptr [rcx+4], 1
0x18002445f  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\DirectShow\\Debug"...
0x180024466  mov     qword ptr [rcx+8], 0
0x18002446e  or      r15, 0FFFFFFFFFFFFFFFFh
0x180024472  mov     [rcx+10h], r15
0x180024476  mov     r11d, 400h
0x18002447c  lea     rcx, [rbp+990h+SubKey]; unsigned __int16 *
0x180024483  mov     [rsp+0A90h+hKey], 0
0x18002448c  mov     edx, r11d; unsigned __int64
0x18002448f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024494  test    eax, eax
0x180024496  jns     short loc_1800244A4
0x180024498  lea     rcx, OutputString; "CRetailTrace::CRetailTrace() - fatal tr"...
0x18002449f  jmp     loc_18002464F
0x1800244a4  lea     r8, aMultimediaDsho_0; "multimedia\\dshow\\filters\\sbe\\analys"...
0x1800244ab  mov     rdx, r11; unsigned __int64
0x1800244ae  lea     rcx, [rbp+990h+SubKey]; unsigned __int16 *
0x1800244b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800244ba  test    eax, eax
0x1800244bc  jns     short loc_1800244CA
0x1800244be  lea     rcx, aCretailtraceCr_2; "CRetailTrace::CRetailTrace() - fatal tr"...
0x1800244c5  jmp     loc_18002464F
0x1800244ca  lea     rax, [rsp+0A90h+hKey]
0x1800244cf  mov     r9d, 20019h; samDesired
0x1800244d5  xor     r8d, r8d; ulOptions
0x1800244d8  mov     [rsp+0A90h+phkResult], rax; phkResult
0x1800244dd  lea     rdx, [rbp+990h+SubKey]; lpSubKey
0x1800244e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800244eb  xor     dil, dil
0x1800244ee  call    cs:__imp_RegOpenKeyExW
0x1800244f4  test    eax, eax
0x1800244f6  jnz     short loc_18002454C
0x1800244f8  mov     rcx, [rsp+0A90h+hKey]; hKey
0x1800244fd  lea     rdx, aTracepriority; "TracePriority"
0x180024504  mov     dword ptr [rsp+0A90h+Data], eax
0x180024508  xor     r9d, r9d; lpType
0x18002450b  lea     rax, [rsp+0A90h+cbData]
0x180024510  mov     [rsp+0A90h+cbData], 4
0x180024518  mov     [rsp+0A90h+lpcbData], rax; lpcbData
0x18002451d  xor     r8d, r8d; lpReserved
0x180024520  lea     rax, [rsp+0A90h+Data]
0x180024525  mov     [rsp+0A90h+phkResult], rax; lpData
0x18002452a  call    cs:__imp_RegQueryValueExW
0x180024530  test    eax, eax
0x180024532  jnz     short loc_180024541
0x180024534  mov     eax, dword ptr [rsp+0A90h+Data]
0x180024538  mov     dil, 1
0x18002453b  mov     [rbx], eax
0x18002453d  mov     byte ptr [rbx+4], 0
0x180024541  mov     rcx, [rsp+0A90h+hKey]; hKey
0x180024546  call    cs:__imp_RegCloseKey
0x18002454c  xor     edx, edx; Val
0x18002454e  lea     rcx, [rsp+0A90h+var_A40]; void *
0x180024553  mov     r8d, 208h; Size
0x180024559  call    memset_0
0x18002455e  test    dil, dil
0x180024561  jz      loc_180024655
0x180024567  lea     rdx, [rsp+0A90h+var_A40]
0x18002456c  mov     ecx, 104h
0x180024571  call    cs:__imp_GetTempPath2W
0x180024577  test    eax, eax
0x180024579  jz      loc_1800245FF
0x18002457f  mov     edi, eax
0x180024581  mov     eax, 2
0x180024586  add     rdi, 11h
0x18002458a  mul     rdi
0x18002458d  cmovb   rax, r15
0x180024591  mov     rcx, rax; unsigned __int64
0x180024594  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180024599  mov     [rbx+8], rax
0x18002459d  test    rax, rax
0x1800245a0  jnz     short loc_1800245AB
0x1800245a2  lea     rcx, aCretailtraceCr_3; "CRetailTrace::CRetailTrace() - fatal tr"...
0x1800245a9  jmp     short loc_180024606
0x1800245ab  lea     r8, [rsp+0A90h+var_A40]; unsigned __int16 *
0x1800245b0  mov     rdx, rdi; unsigned __int64
0x1800245b3  mov     rcx, rax; unsigned __int16 *
0x1800245b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800245bb  test    eax, eax
0x1800245bd  js      short loc_1800245DF
0x1800245bf  mov     rcx, [rbx+8]; unsigned __int16 *
0x1800245c3  lea     r8, aRetailtraceTxt; "RetailTrace.txt"
0x1800245ca  mov     rdx, rdi; unsigned __int64
0x1800245cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800245d2  test    eax, eax
0x1800245d4  jns     short loc_18002460C
0x1800245d6  lea     rcx, aCretailtraceCr_2; "CRetailTrace::CRetailTrace() - fatal tr"...
0x1800245dd  jmp     short loc_1800245E6
0x1800245df  lea     rcx, OutputString; "CRetailTrace::CRetailTrace() - fatal tr"...
0x1800245e6  call    cs:__imp_OutputDebugStringA
0x1800245ec  mov     rcx, [rbx+8]; void *
0x1800245f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800245f5  mov     qword ptr [rbx+8], 0
0x1800245fd  jmp     short loc_18002460C
0x1800245ff  lea     rcx, aCretailtraceCr; "CRetailTrace::CRetailTrace() - fatal tr"...
0x180024606  call    cs:__imp_OutputDebugStringA
0x18002460c  mov     rcx, [rbx+8]; lpFileName
0x180024610  test    rcx, rcx
0x180024613  jz      short loc_180024655
0x180024615  xor     r9d, r9d; lpSecurityAttributes
0x180024618  mov     [rsp+0A90h+hTemplateFile], 0; hTemplateFile
0x180024621  mov     dword ptr [rsp+0A90h+lpcbData], 0; dwFlagsAndAttributes
0x180024629  mov     dword ptr [rsp+0A90h+phkResult], 4; dwCreationDisposition
0x180024631  lea     edx, [r9+4]; dwDesiredAccess
0x180024635  lea     r8d, [r9+3]; dwShareMode
0x180024639  call    cs:__imp_CreateFileW
0x18002463f  mov     [rbx+10h], rax
0x180024643  cmp     rax, r15
0x180024646  jnz     short loc_180024655
0x180024648  lea     rcx, aCretailtraceCr_1; "CRetailTrace::CRetailTrace() - fatal tr"...
0x18002464f  call    cs:__imp_OutputDebugStringA
0x180024655  mov     rax, rbx
0x180024658  mov     rcx, [rbp+990h+var_30]
0x18002465f  xor     rcx, rsp; StackCookie
0x180024662  call    __security_check_cookie
0x180024667  add     rsp, 0A78h
0x18002466e  pop     r15
0x180024670  pop     rdi
0x180024671  pop     rbx
0x180024672  pop     rbp
0x180024673  retn
```
