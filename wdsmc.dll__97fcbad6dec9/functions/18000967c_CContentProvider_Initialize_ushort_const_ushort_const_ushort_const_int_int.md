# CContentProvider::Initialize(ushort const *,ushort const *,ushort const *,int,int)

- ea: `0x18000967c`
- end: `0x180009ab1`
- name: `?Initialize@CContentProvider@@QEAAKPEBG00HH@Z`
- size: `1077`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, const unsigned __int16 *, LPCWSTR lpLibFileName, LPCWCH lpWideCharStr, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18000aa44`

## callees

- `0x18000967c`
- `0x180009ab8`
- `0x18001a9a8`
- `0x180024320`
- `0x1800244bc`
- `0x180024760`
- `0x180024dec`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180009848`
- `KERNEL32!GetProcAddress` at `0x180009848`
- `KERNEL32!LoadLibraryExW` at `0x180009709`
- `KERNEL32!LoadLibraryExW` at `0x180009709`
- `KERNEL32!GetLastError` at `0x180009718`
- `KERNEL32!GetLastError` at `0x180009857`
- `KERNEL32!GetLastError` at `0x180009718`
- `KERNEL32!GetLastError` at `0x180009857`
- `ADVAPI32!RegCloseKey` at `0x1800097c0`
- `ADVAPI32!RegCloseKey` at `0x1800097c0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800097e3`
- `ADVAPI32!RegOpenKeyExW` at `0x1800097e3`

## string_xrefs

- `0x1800096d4`: `Content Provider: Name=%s, DLL=%s, InitRoutine=%s`
- `0x180009783`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Providers\%s`

## pseudocode

```c
__int64 __fastcall CContentProvider::Initialize(
        LPCRITICAL_SECTION lpCriticalSection,
        const unsigned __int16 *a2,
        LPCWSTR lpLibFileName,
        LPCWCH lpWideCharStr,
        LONG a5,
        int a6)
{
  LPCRITICAL_SECTION v10; // rsi
  unsigned int v11; // edi
  HMODULE Library; // rax
  DWORD LastError; // eax
  const char *v14; // rdx
  __int64 v15; // rdx
  const char *v16; // rdx
  HANDLE *p_LockSemaphore; // r15
  HKEY LockSemaphore; // rcx
  const char *v19; // rdx
  unsigned int v20; // eax
  CHAR *v21; // r15
  struct _RTL_CRITICAL_SECTION_DEBUG *ProcAddress; // rax
  DWORD v23; // eax
  const char *v24; // rdx
  int v25; // eax
  unsigned int v26; // edx
  unsigned int v27; // edx
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-9h] BYREF
  LPCSTR lpProcName; // [rsp+70h] [rbp-1h] BYREF
  __int64 v31; // [rsp+78h] [rbp+7h] BYREF
  HANDLE v32; // [rsp+80h] [rbp+Fh]
  LPCRITICAL_SECTION v33; // [rsp+88h] [rbp+17h]
  __int64 v34; // [rsp+C8h] [rbp+57h] BYREF

  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  lpProcName = 0;
  lpSubKey = 0;
  if ( g_ErrLibTraceFunction )
    g_ErrLibTraceFunction(L"Content Provider: Name=%s, DLL=%s, InitRoutine=%s");
  v10 = lpCriticalSection + 1;
  v11 = DuplicateStringW(a2, (unsigned __int16 **)&lpCriticalSection[1]);
  if ( !v11 )
  {
    lpCriticalSection[1].RecursionCount = a5;
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    lpCriticalSection[1].OwningThread = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v11 = ElValidateWin32(LastError, v14, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", v11 + 85);
      CEventLog::Log((CEventLog *)&hEventLog, 0xC1210250, 3, 1, lpLibFileName, 1, v10->DebugInfo, 5, v11);
      goto LABEL_38;
    }
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v11 = FormatString(
            (unsigned __int16 **)&lpSubKey,
            v15 + 70,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Providers\\%s",
            a2);
    if ( ElValidateWin32(v11, v16, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x6Bu) )
      goto LABEL_36;
    p_LockSemaphore = &lpCriticalSection[1].LockSemaphore;
    LockSemaphore = (HKEY)lpCriticalSection[1].LockSemaphore;
    if ( LockSemaphore )
    {
      RegCloseKey(LockSemaphore);
      *p_LockSemaphore = 0;
    }
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF013Fu, (PHKEY)&lpCriticalSection[1].LockSemaphore);
    if ( ElValidateWin32(v11, v19, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x72u) )
    {
LABEL_36:
      if ( lpSubKey )
        operator delete((void *)lpSubKey);
LABEL_38:
      if ( !v11 )
        return v11;
      goto LABEL_39;
    }
    v32 = *p_LockSemaphore;
    v31 = 0x100000018LL;
    v33 = lpCriticalSection;
    LODWORD(v34) = 8;
    v20 = ToAnsi(lpWideCharStr, (char **)&lpProcName);
    v21 = (CHAR *)lpProcName;
    v11 = v20;
    if ( !v20 )
    {
      ProcAddress = (struct _RTL_CRITICAL_SECTION_DEBUG *)GetProcAddress(
                                                            (HMODULE)lpCriticalSection[1].OwningThread,
                                                            lpProcName);
      lpCriticalSection[2].DebugInfo = ProcAddress;
      if ( ProcAddress )
      {
        v25 = ((__int64 (__fastcall *)(__int64 *, __int64 *, _QWORD))ProcAddress)(&v31, &v34, (unsigned int)v34);
        if ( v25 >= 0 )
        {
          lpCriticalSection[1].LockCount = 1;
          if ( HIDWORD(v34) <= 1 )
          {
            if ( *(_QWORD *)&lpCriticalSection[2].LockCount
              && lpCriticalSection[2].OwningThread
              && lpCriticalSection[2].LockSemaphore
              && lpCriticalSection[3].DebugInfo
              && *(_QWORD *)&lpCriticalSection[3].LockCount
              && lpCriticalSection[3].LockSemaphore
              && lpCriticalSection[3].SpinCount
              && lpCriticalSection[4].DebugInfo
              && lpCriticalSection[2].SpinCount )
            {
              if ( g_ErrLibTraceFunction )
                g_ErrLibTraceFunction(L"Content Provider '%s' Initialized.", v10->DebugInfo);
              goto LABEL_34;
            }
            v11 = -1054801663;
            v26 = -1054801324;
          }
          else
          {
            v11 = -1054801662;
            v26 = -1054801325;
          }
          CEventLog::Log((CEventLog *)&hEventLog, v26, 1, 1, v10->DebugInfo);
        }
        else
        {
          v11 = (unsigned __int16)v25;
          if ( (v25 & 0x1FFF0000) != 0x70000 )
            v11 = v25;
          CEventLog::Log((CEventLog *)&hEventLog, 0xC1210252, 3, 1, v10->DebugInfo, 1, lpLibFileName, 5, v11);
        }
      }
      else
      {
        v23 = GetLastError();
        v11 = ElValidateWin32(v23, v24, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x89u);
        CEventLog::Log(
          (CEventLog *)&hEventLog,
          0xC1210251,
          4,
          1,
          lpLibFileName,
          1,
          v10->DebugInfo,
          1,
          lpWideCharStr,
          5,
          v11);
      }
    }
LABEL_34:
    if ( v21 )
      operator delete(v21);
    goto LABEL_36;
  }
LABEL_39:
  if ( g_ErrLibTraceFunction )
    g_ErrLibTraceFunction(L"Failed to initialize Content Provider '%s', Error=0x%x", a2, v11);
  if ( a6 )
  {
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(L"'%s' is marked critical.", a2);
    v27 = -1054801317;
  }
  else
  {
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(L"'%s' is marked non-critical.", a2);
    v27 = -2128543142;
  }
  CEventLog::Log((CEventLog *)&hEventLog, v27, 2);
  if ( lpCriticalSection[1].LockCount )
    CContentProvider::Shutdown(lpCriticalSection);
  return v11;
}

```

## disassembly

```asm
0x18000967c  mov     rax, rsp
0x18000967f  mov     [rax+10h], rbx
0x180009683  mov     [rax+18h], rsi
0x180009687  mov     [rax+20h], rdi
0x18000968b  push    rbp
0x18000968c  push    r12
0x18000968e  push    r13
0x180009690  push    r14
0x180009692  push    r15
0x180009694  lea     rbp, [rax-4Fh]
0x180009698  sub     rsp, 90h
0x18000969f  xor     eax, eax
0x1800096a1  xor     r15d, r15d
0x1800096a4  mov     [rbp+47h+var_40], rax
0x1800096a8  mov     r13, r9
0x1800096ab  mov     [rbp+47h+var_38], rax
0x1800096af  mov     r12, r8
0x1800096b2  mov     [rbp+47h+var_30], rax
0x1800096b6  mov     r14, rdx
0x1800096b9  mov     [rbp+47h+arg_0], rax
0x1800096bd  mov     rbx, rcx
0x1800096c0  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800096c7  mov     [rbp+47h+lpProcName], r15
0x1800096cb  mov     [rbp+47h+lpSubKey], r15
0x1800096cf  test    rax, rax
0x1800096d2  jz      short loc_1800096E1
0x1800096d4  lea     rcx, aContentProvide_0; "Content Provider: Name=%s, DLL=%s, Init"...
0x1800096db  call    cs:__guard_dispatch_icall_fptr
0x1800096e1  lea     rsi, [rbx+28h]
0x1800096e5  mov     rcx, r14; unsigned __int16 *
0x1800096e8  mov     rdx, rsi; unsigned __int16 **
0x1800096eb  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800096f0  mov     edi, eax
0x1800096f2  test    eax, eax
0x1800096f4  jnz     loc_1800099F4
0x1800096fa  mov     eax, [rbp+47h+arg_20]
0x1800096fd  lea     r8d, [rdi+8]; dwFlags
0x180009701  xor     edx, edx; hFile
0x180009703  mov     [rbx+34h], eax
0x180009706  mov     rcx, r12; lpLibFileName
0x180009709  call    cs:__imp_LoadLibraryExW
0x18000970f  mov     [rbx+38h], rax
0x180009713  test    rax, rax
0x180009716  jnz     short loc_180009771
0x180009718  call    cs:__imp_GetLastError
0x18000971e  mov     ecx, eax; unsigned int
0x180009720  lea     r9d, [rdi+55h]; unsigned int
0x180009724  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000972b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009730  mov     [rsp+0B0h+var_70], eax
0x180009734  lea     rcx, hEventLog; this
0x18000973b  mov     edi, eax
0x18000973d  mov     dword ptr [rsp+0B0h+var_78], 5
0x180009745  mov     rax, [rsi]
0x180009748  mov     edx, 0C1210250h; unsigned int
0x18000974d  mov     qword ptr [rsp+0B0h+var_80], rax
0x180009752  mov     eax, 1
0x180009757  mov     dword ptr [rsp+0B0h+var_88], eax
0x18000975b  mov     r9d, eax
0x18000975e  mov     [rsp+0B0h+phkResult], r12
0x180009763  lea     r8d, [rax+2]; int
0x180009767  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000976c  jmp     loc_1800099EC
0x180009771  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009775  inc     rdx
0x180009778  cmp     [r14+rdx*2], r15w
0x18000977d  jnz     short loc_180009775
0x18000977f  add     rdx, 46h ; 'F'; unsigned __int64
0x180009783  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\WD"...
0x18000978a  mov     r9, r14
0x18000978d  lea     rcx, [rbp+47h+lpSubKey]; unsigned __int16 **
0x180009791  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x180009796  mov     r9d, 6Bh ; 'k'; unsigned int
0x18000979c  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800097a3  mov     ecx, eax; unsigned int
0x1800097a5  mov     edi, eax
0x1800097a7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800097ac  test    eax, eax
0x1800097ae  jnz     loc_1800099DB
0x1800097b4  lea     r15, [rbx+40h]
0x1800097b8  mov     rcx, [r15]; hKey
0x1800097bb  test    rcx, rcx
0x1800097be  jz      short loc_1800097CA
0x1800097c0  call    cs:__imp_RegCloseKey
0x1800097c6  and     qword ptr [r15], 0
0x1800097ca  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x1800097ce  mov     r9d, 0F013Fh; samDesired
0x1800097d4  xor     r8d, r8d; ulOptions
0x1800097d7  mov     [rsp+0B0h+phkResult], r15; phkResult
0x1800097dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800097e3  call    cs:__imp_RegOpenKeyExW
0x1800097e9  mov     r9d, 72h ; 'r'; unsigned int
0x1800097ef  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800097f6  mov     ecx, eax; unsigned int
0x1800097f8  mov     edi, eax
0x1800097fa  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800097ff  test    eax, eax
0x180009801  jnz     loc_1800099D8
0x180009807  mov     rax, [r15]
0x18000980a  lea     rdx, [rbp+47h+lpProcName]; char **
0x18000980e  mov     rcx, r13; lpWideCharStr
0x180009811  mov     [rbp+47h+var_38], rax
0x180009815  mov     dword ptr [rbp+47h+var_40], 18h
0x18000981c  mov     dword ptr [rbp+47h+var_40+4], 1
0x180009823  mov     [rbp+47h+var_30], rbx
0x180009827  mov     dword ptr [rbp+47h+arg_0], 8
0x18000982e  call    ?ToAnsi@@YAKPEBGPEAPEAD@Z; ToAnsi(ushort const *,char * *)
0x180009833  mov     r15, [rbp+47h+lpProcName]
0x180009837  mov     edi, eax
0x180009839  test    eax, eax
0x18000983b  jnz     loc_1800099CB
0x180009841  mov     rcx, [rbx+38h]; hModule
0x180009845  mov     rdx, r15; lpProcName
0x180009848  call    cs:__imp_GetProcAddress
0x18000984e  mov     [rbx+50h], rax
0x180009852  test    rax, rax
0x180009855  jnz     short loc_1800098BB
0x180009857  call    cs:__imp_GetLastError
0x18000985d  mov     r9d, 89h; unsigned int
0x180009863  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000986a  mov     ecx, eax; unsigned int
0x18000986c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009871  mov     [rsp+0B0h+var_60], eax
0x180009875  mov     ecx, 1
0x18000987a  mov     [rsp+0B0h+var_68], 5
0x180009882  mov     edi, eax
0x180009884  mov     rax, [rsi]
0x180009887  mov     r9d, ecx
0x18000988a  mov     qword ptr [rsp+0B0h+var_70], r13
0x18000988f  mov     edx, 0C1210251h; unsigned int
0x180009894  mov     dword ptr [rsp+0B0h+var_78], ecx
0x180009898  lea     r8d, [rcx+3]; int
0x18000989c  mov     qword ptr [rsp+0B0h+var_80], rax
0x1800098a1  mov     dword ptr [rsp+0B0h+var_88], ecx
0x1800098a5  lea     rcx, hEventLog; this
0x1800098ac  mov     [rsp+0B0h+phkResult], r12
0x1800098b1  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800098b6  jmp     loc_1800099CB
0x1800098bb  mov     r8d, dword ptr [rbp+47h+arg_0]
0x1800098bf  lea     rdx, [rbp+47h+arg_0]
0x1800098c3  lea     rcx, [rbp+47h+var_40]
0x1800098c7  call    cs:__guard_dispatch_icall_fptr
0x1800098cd  xor     r13d, r13d
0x1800098d0  test    eax, eax
0x1800098d2  jns     short loc_18000992B
0x1800098d4  mov     ecx, eax
0x1800098d6  movzx   edi, ax
0x1800098d9  and     ecx, 1FFF0000h
0x1800098df  cmp     ecx, 70000h
0x1800098e5  jz      short loc_1800098E9
0x1800098e7  mov     edi, eax
0x1800098e9  mov     rax, [rsi]
0x1800098ec  lea     rcx, hEventLog; this
0x1800098f3  mov     [rsp+0B0h+var_70], edi
0x1800098f7  mov     edx, 0C1210252h; unsigned int
0x1800098fc  mov     dword ptr [rsp+0B0h+var_78], 5
0x180009904  mov     qword ptr [rsp+0B0h+var_80], r12
0x180009909  mov     r12d, 1
0x18000990f  mov     dword ptr [rsp+0B0h+var_88], r12d
0x180009914  mov     r9d, r12d
0x180009917  mov     [rsp+0B0h+phkResult], rax
0x18000991c  lea     r8d, [r12+2]; int
0x180009921  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180009926  jmp     loc_1800099CB
0x18000992b  mov     r12d, 1
0x180009931  mov     [rbx+30h], r12d
0x180009935  cmp     dword ptr [rbp+47h+arg_0+4], r12d
0x180009939  jbe     short loc_180009947
0x18000993b  mov     edi, 0C1210102h
0x180009940  mov     edx, 0C1210253h
0x180009945  jmp     short loc_1800099B1
0x180009947  cmp     [rbx+58h], r13
0x18000994b  jz      short loc_1800099A7
0x18000994d  cmp     [rbx+60h], r13
0x180009951  jz      short loc_1800099A7
0x180009953  cmp     [rbx+68h], r13
0x180009957  jz      short loc_1800099A7
0x180009959  cmp     [rbx+78h], r13
0x18000995d  jz      short loc_1800099A7
0x18000995f  cmp     [rbx+80h], r13
0x180009966  jz      short loc_1800099A7
0x180009968  cmp     [rbx+90h], r13
0x18000996f  jz      short loc_1800099A7
0x180009971  cmp     [rbx+98h], r13
0x180009978  jz      short loc_1800099A7
0x18000997a  cmp     [rbx+0A0h], r13
0x180009981  jz      short loc_1800099A7
0x180009983  cmp     [rbx+70h], r13
0x180009987  jz      short loc_1800099A7
0x180009989  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180009990  test    rax, rax
0x180009993  jz      short loc_1800099CB
0x180009995  mov     rdx, [rsi]
0x180009998  lea     rcx, aContentProvide; "Content Provider '%s' Initialized."
0x18000999f  call    cs:__guard_dispatch_icall_fptr
0x1800099a5  jmp     short loc_1800099CB
0x1800099a7  mov     edi, 0C1210101h
0x1800099ac  mov     edx, 0C1210254h; unsigned int
0x1800099b1  mov     rax, [rsi]
0x1800099b4  lea     rcx, hEventLog; this
0x1800099bb  mov     r9d, r12d
0x1800099be  mov     [rsp+0B0h+phkResult], rax
0x1800099c3  mov     r8d, r12d; int
0x1800099c6  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800099cb  test    r15, r15
0x1800099ce  jz      short loc_1800099D8
0x1800099d0  mov     rcx, r15; void *
0x1800099d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099d8  xor     r15d, r15d
0x1800099db  mov     rax, [rbp+47h+lpSubKey]
0x1800099df  test    rax, rax
0x1800099e2  jz      short loc_1800099EC
0x1800099e4  mov     rcx, rax; void *
0x1800099e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099ec  test    edi, edi
0x1800099ee  jz      loc_180009A8E
0x1800099f4  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800099fb  test    rax, rax
0x1800099fe  jz      short loc_180009A13
0x180009a00  mov     r8d, edi
0x180009a03  lea     rcx, aFailedToInitia; "Failed to initialize Content Provider '"...
0x180009a0a  mov     rdx, r14
0x180009a0d  call    cs:__guard_dispatch_icall_fptr
0x180009a13  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180009a1a  cmp     [rbp+47h+arg_28], r15d
0x180009a1e  jz      short loc_180009A3C
0x180009a20  test    rax, rax
0x180009a23  jz      short loc_180009A35
0x180009a25  mov     rdx, r14
0x180009a28  lea     rcx, aSIsMarkedCriti; "'%s' is marked critical."
0x180009a2f  call    cs:__guard_dispatch_icall_fptr
0x180009a35  mov     edx, 0C121025Bh
0x180009a3a  jmp     short loc_180009A56
0x180009a3c  test    rax, rax
0x180009a3f  jz      short loc_180009A51
0x180009a41  mov     rdx, r14
0x180009a44  lea     rcx, aSIsMarkedNonCr; "'%s' is marked non-critical."
0x180009a4b  call    cs:__guard_dispatch_icall_fptr
0x180009a51  mov     edx, 8121025Ah; unsigned int
0x180009a56  mov     rax, [rsi]
0x180009a59  lea     rcx, hEventLog; this
0x180009a60  mov     r9d, 1
0x180009a66  mov     [rsp+0B0h+var_80], edi
0x180009a6a  mov     dword ptr [rsp+0B0h+var_88], 5
0x180009a72  mov     [rsp+0B0h+phkResult], rax
0x180009a77  lea     r8d, [r9+1]; int
0x180009a7b  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180009a80  cmp     [rbx+30h], r15d
0x180009a84  jz      short loc_180009A8E
0x180009a86  mov     rcx, rbx; lpCriticalSection
0x180009a89  call    ?Shutdown@CContentProvider@@QEAAKXZ; CContentProvider::Shutdown(void)
0x180009a8e  lea     r11, [rsp+0B0h+var_20]
0x180009a96  mov     eax, edi
0x180009a98  mov     rbx, [r11+38h]
0x180009a9c  mov     rsi, [r11+40h]
0x180009aa0  mov     rdi, [r11+48h]
0x180009aa4  mov     rsp, r11
0x180009aa7  pop     r15
0x180009aa9  pop     r14
0x180009aab  pop     r13
0x180009aad  pop     r12
0x180009aaf  pop     rbp
0x180009ab0  retn
```
