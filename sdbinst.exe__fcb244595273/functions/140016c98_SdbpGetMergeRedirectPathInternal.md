# SdbpGetMergeRedirectPathInternal

- ea: `0x140016c98`
- end: `0x140017492`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `2042`
- prototype: `__int64 __fastcall(WCHAR **, _DWORD *, int, WCHAR *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015eb4`

## callees

- `0x140001f94`
- `0x14001008c`
- `0x140010270`
- `0x140010568`
- `0x140010678`
- `0x140010a68`
- `0x1400165cc`
- `0x14001687c`
- `0x140016c98`
- `0x14001759c`
- `0x140017928`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140016dc5`
- `KERNEL32!GetLastError` at `0x140016dcf`
- `KERNEL32!GetLastError` at `0x140016dd9`
- `KERNEL32!GetLastError` at `0x140016e60`
- `KERNEL32!GetLastError` at `0x140016e6a`
- `KERNEL32!GetLastError` at `0x140016e74`
- `KERNEL32!GetLastError` at `0x140016dc5`
- `KERNEL32!GetLastError` at `0x140016dcf`
- `KERNEL32!GetLastError` at `0x140016dd9`
- `KERNEL32!GetLastError` at `0x140016e60`
- `KERNEL32!GetLastError` at `0x140016e6a`
- `KERNEL32!GetLastError` at `0x140016e74`
- `KERNEL32!GetFullPathNameW` at `0x140016db9`
- `KERNEL32!GetFullPathNameW` at `0x140016e56`
- `KERNEL32!GetFullPathNameW` at `0x140016db9`
- `KERNEL32!GetFullPathNameW` at `0x140016e56`
- `msvcrt!_wcsnicmp` at `0x140016ef1`
- `msvcrt!_wcsnicmp` at `0x140016ef1`
- `ntdll!RtlAllocateHeap` at `0x140016e2f`
- `ntdll!RtlAllocateHeap` at `0x140016e2f`
- `ntdll!RtlFreeHeap` at `0x140016fdd`
- `ntdll!RtlFreeHeap` at `0x140016ffa`
- `ntdll!RtlFreeHeap` at `0x140017017`
- `ntdll!RtlFreeHeap` at `0x140017038`
- `ntdll!RtlFreeHeap` at `0x140017059`
- `ntdll!RtlFreeHeap` at `0x14001707a`
- `ntdll!RtlFreeHeap` at `0x140016fdd`
- `ntdll!RtlFreeHeap` at `0x140016ffa`
- `ntdll!RtlFreeHeap` at `0x140017017`
- `ntdll!RtlFreeHeap` at `0x140017038`
- `ntdll!RtlFreeHeap` at `0x140017059`
- `ntdll!RtlFreeHeap` at `0x14001707a`
- `ntdll!ZwClose` at `0x14001746c`
- `ntdll!ZwClose` at `0x14001746c`

## string_xrefs

- `0x140016e85`: `Failed to get full path [%x]`
- `0x1400170b8`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1400170db`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x140017398`: `Failed to get manifested stub [%x]`
- `0x140016dea`: `Failed to get full path size [%x]`
- `0x140016df6`: `SdbpGetMergeRedirectPathInternal`
- `0x140016e91`: `SdbpGetMergeRedirectPathInternal`
- `0x140016fa9`: `SdbpGetMergeRedirectPathInternal`
- `0x140017187`: `SdbpGetMergeRedirectPathInternal`
- `0x140017211`: `SdbpGetMergeRedirectPathInternal`
- `0x140017266`: `SdbpGetMergeRedirectPathInternal`
- `0x1400172fe`: `SdbpGetMergeRedirectPathInternal`
- `0x14001734a`: `SdbpGetMergeRedirectPathInternal`
- `0x140017417`: `SdbpGetMergeRedirectPathInternal`
- `0x140017441`: `SdbpGetMergeRedirectPathInternal`
- `0x140016f7e`: `StagedDelete_`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(WCHAR **a1, _DWORD *a2, int a3, WCHAR *a4)
{
  wchar_t *v5; // r15
  WCHAR *v6; // rdi
  signed int LastError; // ebx
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  bool v11; // zf
  WCHAR *v12; // r12
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *Heap; // rax
  const wchar_t *FileNamePart; // rax
  const wchar_t *v17; // r13
  const wchar_t *i; // rdi
  const wchar_t *v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  const WCHAR *v22; // rdi
  int Key; // eax
  wchar_t *v24; // rbx
  int UInt32; // eax
  const char *v26; // r9
  __int64 v27; // r8
  int v28; // eax
  int v29; // eax
  __int64 v30; // rcx
  WCHAR *v31; // rax
  unsigned __int64 v32; // r8
  int v33; // eax
  int FileTimestamp; // eax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // [rsp+20h] [rbp-89h]
  __int64 v38; // [rsp+20h] [rbp-89h]
  __int64 v39; // [rsp+20h] [rbp-89h]
  wchar_t *String1; // [rsp+30h] [rbp-79h] BYREF
  WCHAR *v41; // [rsp+38h] [rbp-71h]
  unsigned int v42; // [rsp+40h] [rbp-69h] BYREF
  int v43; // [rsp+44h] [rbp-65h]
  HANDLE Handle; // [rsp+48h] [rbp-61h] BYREF
  int v45; // [rsp+50h] [rbp-59h] BYREF
  WCHAR *v46; // [rsp+58h] [rbp-51h]
  WCHAR *v47; // [rsp+60h] [rbp-49h] BYREF
  PVOID P; // [rsp+68h] [rbp-41h] BYREF
  PVOID v49; // [rsp+70h] [rbp-39h] BYREF
  PVOID v50; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v51; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v52; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v53; // [rsp+90h] [rbp-19h] BYREF
  _DWORD *v54; // [rsp+98h] [rbp-11h]
  unsigned __int64 v55; // [rsp+A0h] [rbp-9h]
  WCHAR **v56; // [rsp+A8h] [rbp-1h]
  wchar_t String2[12]; // [rsp+B0h] [rbp+7h] BYREF

  v43 = a3;
  v5 = 0;
  v54 = a2;
  v6 = 0;
  v56 = a1;
  v42 = 0;
  Handle = 0;
  String1 = 0;
  v45 = 0;
  v41 = 0;
  v47 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  P = 0;
  v49 = 0;
  v50 = 0;
  wcscpy(String2, L"\\AppPach\\");
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 && a3 )
    *a2 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 0;
    if ( v9 <= 3 )
    {
      if ( v9 <= 1 )
      {
LABEL_16:
        FullPathNameW = GetFullPathNameW(a4, 0, 0, 0);
        v14 = FullPathNameW;
        if ( !FullPathNameW )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1816, "Failed to get full path size [%x]", LastError);
          return (unsigned int)LastError;
        }
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * FullPathNameW);
        v46 = Heap;
        v12 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        if ( !GetFullPathNameW(a4, v14, Heap, 0) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1830, "Failed to get full path [%x]", LastError);
          goto LABEL_52;
        }
        a4 = v12;
LABEL_33:
        LastError = -1073741772;
        FileNamePart = AslPathGetFileNamePart(a4);
        v17 = FileNamePart;
        if ( FileNamePart == a4 )
          goto LABEL_51;
        for ( i = FileNamePart - 2; ; --i )
        {
          if ( i < a4 )
          {
            v6 = 0;
            goto LABEL_51;
          }
          if ( (*i == 92 || *i == 47) && !_wcsnicmp(i, String2, 0xAu) )
            break;
        }
        if ( v17 )
        {
          v19 = v17;
          v20 = 0x7FFFFFFF;
          do
          {
            if ( !*v19 )
              break;
            ++v19;
            --v20;
          }
          while ( v20 );
          LastError = v20 == 0 ? 0xC000000D : 0;
          v55 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
          if ( v20 )
          {
            if ( v43 )
            {
              v21 = SdbpSafeAllocAndConcatW(
                      (unsigned int)&v50,
                      (unsigned int)L"StagedDelete_",
                      13,
                      (_DWORD)v17,
                      (0x7FFFFFFF - v20) & -(__int64)(v20 != 0));
              LastError = v21;
              if ( v21 < 0 )
              {
                LODWORD(v37) = v21;
                AslLogCallPrintf(
                  1,
                  "SdbpGetMergeRedirectPathInternal",
                  1878,
                  "Failed to alloc and cat file to prefix [%x]",
                  v37);
LABEL_49:
                v6 = v41;
                v5 = String1;
LABEL_50:
                v12 = v46;
LABEL_51:
                if ( !v12 )
                {
LABEL_53:
                  if ( v5 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
                  if ( v6 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
                  if ( P )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                  if ( v49 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v49);
                  if ( v50 )
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v50);
                  return (unsigned int)LastError;
                }
LABEL_52:
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
                goto LABEL_53;
              }
              v22 = (const WCHAR *)v50;
            }
            else
            {
              v22 = v17;
            }
            Key = AslRegistryGetKey(
                    &Handle,
                    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                    0x80000100);
            LastError = Key;
            if ( Key < 0 )
            {
              if ( Key != -1073741772 )
              {
                LODWORD(v37) = Key;
                AslLogCallPrintf(
                  1,
                  "SdbpGetMergeRedirectPathInternal",
                  1895,
                  "AslRegistryGetKey failed to open SdbUpdates key [%x]",
                  v37);
              }
              goto LABEL_122;
            }
            LastError = AslRegistryGetString(&String1, Handle, v22);
            if ( LastError < 0 )
            {
LABEL_122:
              v6 = v41;
              goto LABEL_123;
            }
            v24 = String1;
            if ( !wcsicmp_0(String1, v17) )
            {
              LastError = -1073741772;
LABEL_72:
              v6 = 0;
LABEL_123:
              v5 = String1;
LABEL_124:
              if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                ZwClose(Handle);
              goto LABEL_50;
            }
            if ( v43 && !wcsicmp_0(v24, L"__NotRedirected__") && v54 )
            {
              *v54 = 1;
              LastError = 0;
              goto LABEL_72;
            }
            UInt32 = SdbpSafeAllocAndConcatW((unsigned int)&v49, (unsigned int)L"MergeVer_", 9, (_DWORD)v22, 0);
            v6 = 0;
            LastError = UInt32;
            if ( UInt32 < 0 )
            {
              v26 = "Failed to alloc and cat file to prefix [%x]";
              v27 = 1929;
LABEL_79:
              LODWORD(v38) = UInt32;
              AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v27, v26, v38);
              goto LABEL_123;
            }
            UInt32 = AslRegistryGetUInt32((__int64)&v45, (__int64)Handle, (const WCHAR *)v49);
            LastError = UInt32;
            if ( UInt32 != -1073741772 )
            {
              if ( UInt32 < 0 )
              {
                v26 = "Failed to query reg value. [%x]";
                v27 = 1938;
                goto LABEL_79;
              }
              LODWORD(v6) = v45;
            }
            v28 = AslRegistryGetUInt32((__int64)&v42, (__int64)Handle, L"MergeVer");
            LastError = v28;
            if ( v28 < 0 )
            {
              LODWORD(v38) = v28;
              AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1944, "Failed to query reg value. [%x]", v38);
              goto LABEL_122;
            }
            if ( v42 < (unsigned int)v6 )
              AslLogCallPrintf(
                1,
                "SdbpGetMergeRedirectPathInternal",
                1953,
                "Merge target is too high of a version, this code might not handle it correctly.");
            v29 = AslRegistryGetUInt32((__int64)&v42, (__int64)Handle, L"MinMergeVer");
            LastError = v29;
            if ( v29 < 0 )
            {
              LODWORD(v38) = v29;
              AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1959, "Failed to query reg value. [%x]", v38);
              goto LABEL_122;
            }
            if ( (unsigned int)v6 < v42 )
              AslLogCallPrintf(
                1,
                "SdbpGetMergeRedirectPathInternal",
                1968,
                "Merge target is too low of a version, it might not be possible to handle correctly.");
            if ( a4 )
            {
              v30 = 0x7FFFFFFF;
              v31 = a4;
              do
              {
                if ( !*v31 )
                  break;
                ++v31;
                --v30;
              }
              while ( v30 );
              LastError = v30 == 0 ? 0xC000000D : 0;
              v32 = (0x7FFFFFFF - v30) & -(__int64)(v30 != 0);
              if ( v30 )
              {
                if ( v32 < v55 )
                {
                  LastError = -1073741675;
                  AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1982, "RtlSizeTSub failed [%x]", -1073741675);
                  v6 = 0;
                  goto LABEL_123;
                }
                v5 = String1;
                v33 = SdbpSafeAllocAndConcatW((unsigned int)&v47, (_DWORD)a4, (int)v32 - (int)v55, (_DWORD)String1, 0);
                LastError = v33;
                if ( v33 < 0 )
                {
                  AslLogCallPrintf(
                    1,
                    "SdbpGetMergeRedirectPathInternal",
                    1992,
                    "Failed to alloc and cat file to prefix [%x]",
                    v33);
                  v6 = v47;
                  goto LABEL_124;
                }
                v6 = v47;
                FileTimestamp = SdbpGetFileTimestamp(&v51, v47, 1);
                LastError = FileTimestamp;
                if ( FileTimestamp >= 0 )
                {
                  FileTimestamp = SdbpGetFileTimestamp(&v52, a4, 0);
                  LastError = FileTimestamp;
                  if ( FileTimestamp >= 0 )
                  {
                    FileTimestamp = SdbpGetManifestedMergeStubAlloc(&P, v17);
                    LastError = FileTimestamp;
                    if ( FileTimestamp == -1073741772 )
                      goto LABEL_113;
                    if ( FileTimestamp < 0 )
                    {
                      v36 = "Failed to get manifested stub [%x]";
                      v35 = 2028;
                      goto LABEL_104;
                    }
                    FileTimestamp = SdbpGetFileTimestamp(&v53, (const WCHAR *)P, 0);
                    LastError = FileTimestamp;
                    if ( FileTimestamp >= 0 )
                    {
LABEL_113:
                      if ( v51 < v52 || v51 < v53 )
                      {
                        LastError = -1073741772;
                      }
                      else
                      {
                        *v56 = v6;
                        if ( v54 && v43 )
                          *v54 = 1;
                        v6 = 0;
                        LastError = 0;
                      }
                      goto LABEL_124;
                    }
                    v35 = 2038;
                  }
                  else
                  {
                    v35 = 2014;
                  }
                }
                else
                {
                  if ( FileTimestamp == -1073741772 )
                    goto LABEL_124;
                  v35 = 2003;
                }
                v36 = "Failed to check timestamp [%x]";
LABEL_104:
                LODWORD(v39) = FileTimestamp;
                AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v35, v36, v39);
                goto LABEL_124;
              }
            }
            else
            {
              LastError = -1073741811;
            }
            LODWORD(v38) = LastError;
            AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1975, "RtlStringCchLengthW failed [%x]", v38);
            goto LABEL_122;
          }
        }
        else
        {
          LastError = -1073741811;
        }
        AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1866, "RtlStringCchLengthW failed [%x]", LastError);
        goto LABEL_49;
      }
    }
    else if ( a4[1] == 58 )
    {
      v10 = a4[2] == 92;
    }
    v11 = *a4 == 92;
    v12 = 0;
    v46 = 0;
    if ( v10 || v11 )
      goto LABEL_33;
    goto LABEL_16;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x140016c98  mov     [rsp-8+arg_10], rbx
0x140016c9d  push    rbp
0x140016c9e  push    rsi
0x140016c9f  push    rdi
0x140016ca0  push    r12
0x140016ca2  push    r13
0x140016ca4  push    r14
0x140016ca6  push    r15
0x140016ca8  lea     rbp, [rsp-27h]
0x140016cad  sub     rsp, 0D0h
0x140016cb4  mov     rax, cs:__security_cookie
0x140016cbb  xor     rax, rsp
0x140016cbe  mov     [rbp+57h+var_38], rax
0x140016cc2  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x140016cc9  xor     r14d, r14d
0x140016ccc  mov     rsi, r9
0x140016ccf  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x140016cd7  mov     rax, rdx
0x140016cda  mov     [rbp+57h+var_BC], r8d
0x140016cde  mov     r15d, r14d
0x140016ce1  mov     [rbp+57h+var_68], rdx
0x140016ce5  mov     edi, r14d
0x140016ce8  mov     [rbp+57h+var_58], rcx
0x140016cec  mov     [rbp+57h+var_C0], r14d
0x140016cf0  mov     [rbp+57h+Handle], r14
0x140016cf4  mov     [rbp+57h+String1], r14
0x140016cf8  mov     [rbp+57h+var_B0], r14d
0x140016cfc  mov     [rbp+57h+var_C8], r14
0x140016d00  mov     [rbp+57h+var_A0], r14
0x140016d04  mov     [rbp+57h+var_80], r14
0x140016d08  mov     [rbp+57h+var_78], r14
0x140016d0c  mov     [rbp+57h+var_70], r14
0x140016d10  mov     [rbp+57h+P], r14
0x140016d14  mov     [rbp+57h+var_90], r14
0x140016d18  mov     [rbp+57h+var_88], r14
0x140016d1c  movups  xmmword ptr [rbp+57h+String2], xmm0
0x140016d20  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x140016d25  test    rcx, rcx
0x140016d28  jnz     short loc_140016D34
0x140016d2a  mov     eax, 0C00000EFh
0x140016d2f  jmp     loc_140017082
0x140016d34  mov     [rcx], r14
0x140016d37  test    rax, rax
0x140016d3a  jz      short loc_140016D44
0x140016d3c  test    r8d, r8d
0x140016d3f  jz      short loc_140016D44
0x140016d41  mov     [rdx], r14d
0x140016d44  call    SdbpGetMergeSdbsSupported
0x140016d49  test    eax, eax
0x140016d4b  jnz     short loc_140016D57
0x140016d4d  mov     ebx, 0C0000034h
0x140016d52  jmp     loc_140017080
0x140016d57  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016d5b  inc     rax
0x140016d5e  cmp     [rsi+rax*2], r14w
0x140016d63  jnz     short loc_140016D5B
0x140016d65  mov     r13d, 1
0x140016d6b  mov     ecx, r14d
0x140016d6e  cmp     rax, 3
0x140016d72  jbe     short loc_140016D87
0x140016d74  cmp     word ptr [rsi+2], 3Ah ; ':'
0x140016d79  jnz     short loc_140016D8C
0x140016d7b  cmp     word ptr [rsi+4], 5Ch ; '\'
0x140016d80  jnz     short loc_140016D8C
0x140016d82  mov     ecx, r13d
0x140016d85  jmp     short loc_140016D8C
0x140016d87  cmp     rax, r13
0x140016d8a  jbe     short loc_140016DAE
0x140016d8c  cmp     word ptr [rsi], 5Ch ; '\'
0x140016d90  mov     eax, r14d
0x140016d93  mov     r12, r14
0x140016d96  mov     [rbp+57h+var_A8], r14
0x140016d9a  cmovz   eax, r13d
0x140016d9e  test    ecx, ecx
0x140016da0  jnz     loc_140016EB5
0x140016da6  test    eax, eax
0x140016da8  jnz     loc_140016EB5
0x140016dae  xor     r9d, r9d; lpFilePart
0x140016db1  xor     r8d, r8d; lpBuffer
0x140016db4  xor     edx, edx; nBufferLength
0x140016db6  mov     rcx, rsi; lpFileName
0x140016db9  call    cs:__imp_GetFullPathNameW
0x140016dbf  mov     ebx, eax
0x140016dc1  test    eax, eax
0x140016dc3  jnz     short loc_140016E17
0x140016dc5  call    cs:__imp_GetLastError
0x140016dcb  test    eax, eax
0x140016dcd  jg      short loc_140016DD9
0x140016dcf  call    cs:__imp_GetLastError
0x140016dd5  mov     ebx, eax
0x140016dd7  jmp     short loc_140016DE8
0x140016dd9  call    cs:__imp_GetLastError
0x140016ddf  movzx   ebx, ax
0x140016de2  or      ebx, 0C0070000h
0x140016de8  test    ebx, ebx
0x140016dea  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x140016df1  mov     eax, 0C00000E5h
0x140016df6  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x140016dfd  cmovns  ebx, eax
0x140016e00  mov     r8d, 718h
0x140016e06  mov     ecx, r13d
0x140016e09  mov     dword ptr [rsp+100h+var_E0], ebx
0x140016e0d  call    AslLogCallPrintf
0x140016e12  jmp     loc_140017080
0x140016e17  mov     rcx, gs:60h
0x140016e20  mov     r8, rbx
0x140016e23  add     r8, r8; Size
0x140016e26  mov     edx, 8; Flags
0x140016e2b  mov     rcx, [rcx+30h]; HeapHandle
0x140016e2f  call    cs:__imp_RtlAllocateHeap
0x140016e35  mov     [rbp+57h+var_A8], rax
0x140016e39  mov     r12, rax
0x140016e3c  test    rax, rax
0x140016e3f  jnz     short loc_140016E4B
0x140016e41  mov     ebx, 0C0000017h
0x140016e46  jmp     loc_140017080
0x140016e4b  xor     r9d, r9d; lpFilePart
0x140016e4e  mov     r8, r12; lpBuffer
0x140016e51  mov     edx, ebx; nBufferLength
0x140016e53  mov     rcx, rsi; lpFileName
0x140016e56  call    cs:__imp_GetFullPathNameW
0x140016e5c  test    eax, eax
0x140016e5e  jnz     short loc_140016EB2
0x140016e60  call    cs:__imp_GetLastError
0x140016e66  test    eax, eax
0x140016e68  jg      short loc_140016E74
0x140016e6a  call    cs:__imp_GetLastError
0x140016e70  mov     ebx, eax
0x140016e72  jmp     short loc_140016E83
0x140016e74  call    cs:__imp_GetLastError
0x140016e7a  movzx   ebx, ax
0x140016e7d  or      ebx, 0C0070000h
0x140016e83  test    ebx, ebx
0x140016e85  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x140016e8c  mov     eax, 0C00000E5h
0x140016e91  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x140016e98  cmovns  ebx, eax
0x140016e9b  mov     r8d, 726h
0x140016ea1  mov     ecx, r13d
0x140016ea4  mov     dword ptr [rsp+100h+var_E0], ebx
0x140016ea8  call    AslLogCallPrintf
0x140016ead  jmp     loc_140016FCB
0x140016eb2  mov     rsi, r12
0x140016eb5  mov     r14d, 0C0000034h
0x140016ebb  mov     rcx, rsi
0x140016ebe  mov     ebx, r14d
0x140016ec1  call    AslPathGetFileNamePart
0x140016ec6  mov     r13, rax
0x140016ec9  cmp     rax, rsi
0x140016ecc  jz      loc_140016FC6
0x140016ed2  lea     rdi, [rax-4]
0x140016ed6  jmp     short loc_140016F02
0x140016ed8  cmp     word ptr [rdi], 5Ch ; '\'
0x140016edc  jz      short loc_140016EE4
0x140016ede  cmp     word ptr [rdi], 2Fh ; '/'
0x140016ee2  jnz     short loc_140016EFE
0x140016ee4  mov     r8d, 0Ah; MaxCount
0x140016eea  lea     rdx, [rbp+57h+String2]; String2
0x140016eee  mov     rcx, rdi; String1
0x140016ef1  call    cs:__imp__wcsnicmp
0x140016ef7  xor     r8d, r8d
0x140016efa  test    eax, eax
0x140016efc  jz      short loc_140016F0F
0x140016efe  sub     rdi, 2
0x140016f02  cmp     rdi, rsi
0x140016f05  jnb     short loc_140016ED8
0x140016f07  mov     rdi, r15
0x140016f0a  jmp     loc_140016FC6
0x140016f0f  test    r13, r13
0x140016f12  jz      loc_140017477
0x140016f18  mov     r12d, 7FFFFFFFh
0x140016f1e  mov     rax, r13
0x140016f21  mov     edx, r12d
0x140016f24  cmp     [rax], r8w
0x140016f28  jz      short loc_140016F34
0x140016f2a  add     rax, 2
0x140016f2e  sub     rdx, 1
0x140016f32  jnz     short loc_140016F24
0x140016f34  mov     rax, rdx
0x140016f37  mov     r15d, 0C000000Dh
0x140016f3d  neg     rax
0x140016f40  mov     rcx, r12
0x140016f43  mov     rax, rdx
0x140016f46  sbb     ebx, ebx
0x140016f48  sub     rcx, rdx
0x140016f4b  not     ebx
0x140016f4d  and     ebx, r15d
0x140016f50  neg     rax
0x140016f53  sbb     rax, rax
0x140016f56  and     rax, rcx
0x140016f59  mov     [rbp+57h+var_60], rax
0x140016f5d  test    rdx, rdx
0x140016f60  jz      loc_14001747C
0x140016f66  cmp     [rbp+57h+var_BC], r8d
0x140016f6a  jz      loc_1400170AF
0x140016f70  mov     r9, r13
0x140016f73  mov     [rsp+100h+var_E0], rax
0x140016f78  mov     r8d, 0Dh
0x140016f7e  lea     rdx, aStageddelete; "StagedDelete_"
0x140016f85  lea     rcx, [rbp+57h+var_88]
0x140016f89  call    SdbpSafeAllocAndConcatW
0x140016f8e  mov     ebx, eax
0x140016f90  test    eax, eax
0x140016f92  jns     loc_1400170A9
0x140016f98  mov     dword ptr [rsp+100h+var_E0], eax
0x140016f9c  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x140016fa3  mov     r8d, 756h
0x140016fa9  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x140016fb0  mov     ecx, 1
0x140016fb5  call    AslLogCallPrintf
0x140016fba  mov     rdi, [rbp+57h+var_C8]
0x140016fbe  mov     r15, [rbp+57h+String1]
0x140016fc2  mov     r12, [rbp+57h+var_A8]
0x140016fc6  test    r12, r12
0x140016fc9  jz      short loc_140016FE3
0x140016fcb  mov     rcx, gs:60h
0x140016fd4  mov     r8, r12; P
0x140016fd7  xor     edx, edx; Flags
0x140016fd9  mov     rcx, [rcx+30h]; HeapHandle
0x140016fdd  call    cs:__imp_RtlFreeHeap
0x140016fe3  test    r15, r15
0x140016fe6  jz      short loc_140017000
0x140016fe8  mov     rcx, gs:60h
0x140016ff1  mov     r8, r15; P
0x140016ff4  xor     edx, edx; Flags
0x140016ff6  mov     rcx, [rcx+30h]; HeapHandle
0x140016ffa  call    cs:__imp_RtlFreeHeap
0x140017000  test    rdi, rdi
0x140017003  jz      short loc_14001701D
0x140017005  mov     rcx, gs:60h
0x14001700e  mov     r8, rdi; P
0x140017011  xor     edx, edx; Flags
0x140017013  mov     rcx, [rcx+30h]; HeapHandle
0x140017017  call    cs:__imp_RtlFreeHeap
0x14001701d  mov     rax, [rbp+57h+P]
0x140017021  test    rax, rax
0x140017024  jz      short loc_14001703E
0x140017026  mov     rcx, gs:60h
0x14001702f  mov     r8, rax; P
0x140017032  xor     edx, edx; Flags
0x140017034  mov     rcx, [rcx+30h]; HeapHandle
0x140017038  call    cs:__imp_RtlFreeHeap
0x14001703e  mov     rax, [rbp+57h+var_90]
0x140017042  test    rax, rax
0x140017045  jz      short loc_14001705F
0x140017047  mov     rcx, gs:60h
0x140017050  mov     r8, rax; P
0x140017053  xor     edx, edx; Flags
0x140017055  mov     rcx, [rcx+30h]; HeapHandle
0x140017059  call    cs:__imp_RtlFreeHeap
0x14001705f  mov     rax, [rbp+57h+var_88]
0x140017063  test    rax, rax
0x140017066  jz      short loc_140017080
0x140017068  mov     rcx, gs:60h
0x140017071  mov     r8, rax; P
0x140017074  xor     edx, edx; Flags
0x140017076  mov     rcx, [rcx+30h]; HeapHandle
0x14001707a  call    cs:__imp_RtlFreeHeap
0x140017080  mov     eax, ebx
0x140017082  mov     rcx, [rbp+57h+var_38]
0x140017086  xor     rcx, rsp; StackCookie
0x140017089  call    __security_check_cookie
0x14001708e  mov     rbx, [rsp+100h+arg_10]
0x140017096  add     rsp, 0D0h
0x14001709d  pop     r15
0x14001709f  pop     r14
0x1400170a1  pop     r13
0x1400170a3  pop     r12
0x1400170a5  pop     rdi
0x1400170a6  pop     rsi
0x1400170a7  pop     rbp
0x1400170a8  retn
0x1400170a9  mov     rdi, [rbp+57h+var_88]
0x1400170ad  jmp     short loc_1400170B2
0x1400170af  mov     rdi, r13
0x1400170b2  mov     r8d, 80000100h
0x1400170b8  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400170bf  lea     rcx, [rbp+57h+Handle]
0x1400170c3  call    AslRegistryGetKey
0x1400170c8  mov     ebx, eax
0x1400170ca  test    eax, eax
0x1400170cc  jns     short loc_1400170ED
0x1400170ce  cmp     eax, r14d
0x1400170d1  jz      loc_140017452
0x1400170d7  mov     dword ptr [rsp+100h+var_E0], eax
0x1400170db  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x1400170e2  mov     r8d, 767h
0x1400170e8  jmp     loc_140017441
0x1400170ed  mov     rdx, [rbp+57h+Handle]
0x1400170f1  lea     rcx, [rbp+57h+String1]
0x1400170f5  mov     r8, rdi
0x1400170f8  call    AslRegistryGetString
0x1400170fd  mov     ebx, eax
0x1400170ff  test    eax, eax
0x140017101  js      loc_140017452
0x140017107  mov     rbx, [rbp+57h+String1]
0x14001710b  mov     rdx, r13; String2
0x14001710e  mov     rcx, rbx; String1
0x140017111  call    _wcsicmp_0
0x140017116  xor     ecx, ecx
  ... truncated ...
```
