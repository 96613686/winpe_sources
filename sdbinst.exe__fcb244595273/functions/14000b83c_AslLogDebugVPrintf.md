# AslLogDebugVPrintf

- ea: `0x14000b83c`
- end: `0x14000bff2`
- name: `AslLogDebugVPrintf`
- size: `1974`
- prototype: `void __fastcall(__int64 *, int, __int64, __int64, char *, va_list)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140006070`

## callees

- `0x140001632`
- `0x14000166e`
- `0x14000167a`
- `0x140001686`
- `0x1400016b6`
- `0x1400016c2`
- `0x1400016ce`
- `0x140009cd4`
- `0x140009e54`
- `0x14000a058`
- `0x14000a164`
- `0x14000acf4`
- `0x14000adb8`
- `0x14000ae38`
- `0x14000b000`
- `0x14000b83c`
- `0x14002e420`
- `0x14002e4e0`

## import_xrefs

- `KERNEL32!GetModuleHandleExA` at `0x14000b946`
- `KERNEL32!GetModuleHandleExA` at `0x14000b946`
- `KERNEL32!CreateFileW` at `0x14000b9af`
- `KERNEL32!CreateFileW` at `0x14000b9af`
- `msvcrt!_vsnwprintf` at `0x14000bc1d`
- `msvcrt!_vsnwprintf` at `0x14000bc1d`
- `msvcrt!_vsnprintf` at `0x14000be71`
- `msvcrt!_vsnprintf` at `0x14000be71`
- `ntdll!EtwEventWrite` at `0x14000bf72`
- `ntdll!EtwEventWrite` at `0x14000bf72`

## string_xrefs

- `0x14000b93d`: `wdscore.dll`

## pseudocode

```c
void __fastcall AslLogDebugVPrintf(__int64 *a1, int a2, __int64 a3, __int64 a4, char *a5, va_list a6)
{
  __int64 v9; // rax
  char v10; // r15
  int v11; // r14d
  int v12; // ecx
  FARPROC ConstructPartialMsgIfA; // rax
  HMODULE v14; // rcx
  HANDLE FileW; // rax
  DWORD LastError_0; // eax
  char v17; // al
  const wchar_t *v18; // rbx
  __int64 v19; // rcx
  wchar_t *v20; // rax
  const wchar_t *v21; // r8
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  wchar_t v24; // ax
  wchar_t *v25; // rcx
  int v26; // eax
  __int64 v27; // r13
  __int64 v28; // rcx
  WCHAR *v29; // rax
  __int64 v30; // rdx
  WCHAR *v31; // rcx
  wchar_t *v32; // r14
  int v33; // r12d
  unsigned __int64 v34; // rsi
  unsigned __int16 *v35; // rdi
  unsigned __int64 v36; // r15
  wchar_t *v37; // rdx
  unsigned __int64 v38; // rax
  int v39; // ecx
  unsigned __int64 v40; // rbx
  int v41; // eax
  __int64 v42; // rax
  const wchar_t *v43; // rdx
  wchar_t *v44; // rcx
  unsigned __int64 i; // rax
  unsigned __int16 v46; // cx
  __int64 v47; // r14
  unsigned __int64 v48; // rbx
  CHAR v49; // al
  int v50; // ecx
  const char *v51; // rax
  __int64 v52; // r15
  __int64 v53; // rax
  const char *v54; // r8
  unsigned __int64 v55; // rdx
  CHAR *v56; // rcx
  CHAR *v57; // rax
  __int64 v58; // rax
  CHAR *v59; // rdi
  unsigned __int64 v60; // rbx
  unsigned __int64 v61; // rsi
  int v62; // eax
  const char *v63; // rax
  unsigned __int64 v64; // rdx
  CHAR *v65; // rcx
  CHAR *v66; // rax
  size_t v67; // r8
  struct _ASL_LOG *v68; // rbx
  __int64 v69; // rcx
  int v70; // edi
  __int64 *v71; // rdx
  char v72; // [rsp+50h] [rbp-B0h]
  char v73; // [rsp+51h] [rbp-AFh]
  int v74; // [rsp+54h] [rbp-ACh]
  int v75; // [rsp+58h] [rbp-A8h]
  DWORD dwErrCode; // [rsp+60h] [rbp-A0h]
  wchar_t *Buffer; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v80; // [rsp+78h] [rbp-88h] BYREF
  va_list Args; // [rsp+80h] [rbp-80h]
  struct _ASL_LOG *v82; // [rsp+88h] [rbp-78h]
  __int64 v83; // [rsp+90h] [rbp-70h]
  char *v84; // [rsp+98h] [rbp-68h] BYREF
  int v85; // [rsp+A0h] [rbp-60h]
  int v86; // [rsp+A4h] [rbp-5Ch]
  CHAR MultiByteStr[1024]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Format[1024]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wchar_t WideCharStr[1024]; // [rsp+CB0h] [rbp+BB0h] BYREF

  v84 = a5;
  Args = a6;
  v83 = a4;
  v82 = (struct _ASL_LOG *)a1;
  if ( a1 )
  {
    dwErrCode = GetLastError_0();
    MultiByteStr[0] = 0;
    if ( a2 != 3 || (v9 = *a1, (*(_BYTE *)(*a1 + 80) & 0x10) != 0) )
    {
      v9 = *a1;
      v10 = 1;
      v72 = 1;
    }
    else
    {
      v10 = 0;
      v72 = 0;
    }
    v11 = 3;
    v12 = *(_DWORD *)(v9 + 80) & 0x100;
    v74 = v12;
    if ( a2 < 3 )
      v11 = a2;
    v75 = v11;
    if ( !a1[90] && qword_140042B18 )
    {
      dword_140042B2C = 0;
      qword_140042B18 = 0;
      WdsSetupLogMessageA = 0;
    }
    if ( !dword_140042B2C )
    {
      dword_140042B2C = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", (HMODULE *)a1 + 90) )
      {
        ConstructPartialMsgIfA = GetProcAddress_0((HMODULE)a1[90], "ConstructPartialMsgIfA");
        v14 = (HMODULE)a1[90];
        qword_140042B18 = (__int64)ConstructPartialMsgIfA;
        WdsSetupLogMessageA = (__int64)GetProcAddress_0(v14, "WdsSetupLogMessageA");
      }
      FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError_0 = GetLastError_0();
        v12 = v74;
        if ( LastError_0 == 231 )
          dword_140042B14 = 1;
      }
      else
      {
        dword_140042B14 = 1;
        CloseHandle_0(FileW);
        v12 = v74;
      }
    }
    if ( !qword_140042B18 || (v17 = 1, !WdsSetupLogMessageA) )
      v17 = 0;
    v73 = v17;
    if ( v10 || a2 == 1 || v17 || dword_140042B14 || v12 )
    {
      Buffer = WideCharStr;
      v80 = 1022;
      v18 = L"ASL_LOG FAIL: ";
      if ( (int)RtlStringCchPrintfW(Format, 1024, L"%hs", a5) < 0 )
      {
        v19 = 2147483646;
        v20 = Format;
        v21 = L"ASL_LOG FAIL: ";
        v22 = 1024;
        do
        {
          if ( !v19 )
            break;
          if ( !*v21 )
            break;
          *v20++ = *v21++;
          --v19;
          --v22;
        }
        while ( v22 );
        v23 = v20 - 1;
        if ( v22 )
          v23 = v20;
        *v23 = 0;
      }
      v24 = Format[0];
      if ( Format[0] )
      {
        v25 = Format;
        do
        {
          if ( v24 == 37 )
          {
            do
            {
              do
                ++v25;
              while ( *v25 == 46 );
            }
            while ( (unsigned __int16)(*v25 - 48) <= 9u );
            if ( *v25 == 115 )
            {
              *v25 = 83;
            }
            else if ( *v25 == 83 )
            {
              *v25 = 115;
            }
          }
          v24 = *++v25;
        }
        while ( *v25 );
      }
      v26 = a4;
      if ( a4 == -1 )
        v26 = 0;
      v27 = 2LL * v11;
      if ( (int)RtlStringCchPrintfExW(
                  WideCharStr,
                  0x3FEu,
                  &Buffer,
                  &v80,
                  0x100u,
                  L"%hs,%hs,%d,",
                  (&off_140030E98)[2 * v11],
                  a3,
                  v26) < 0 )
      {
        v28 = 2147483646;
        v29 = WideCharStr;
        v30 = 1024;
        do
        {
          if ( !v28 )
            break;
          if ( !*v18 )
            break;
          *v29++ = *v18++;
          --v28;
          --v30;
        }
        while ( v30 );
        v31 = v29 - 1;
        if ( v30 )
          v31 = v29;
        *v31 = 0;
      }
      v32 = Buffer;
      v33 = -2147483643;
      v34 = v80;
      v35 = Buffer;
      v36 = v80;
      if ( !Buffer && v80 || v80 > 0x7FFFFFFF )
      {
        *Buffer = 0;
LABEL_73:
        if ( v34 )
        {
          if ( v34 <= 0x7FFFFFFF )
          {
            v42 = 2147483646;
            v43 = L"Message too long!";
            do
            {
              if ( !v42 )
                break;
              if ( !*v43 )
                break;
              *v32++ = *v43++;
              --v42;
              --v34;
            }
            while ( v34 );
            v44 = v32 - 1;
            if ( v34 )
              v44 = v32;
            *v44 = 0;
          }
          else
          {
            *v32 = 0;
          }
        }
LABEL_83:
        for ( i = 0; i < v36; ++i )
        {
          v46 = v35[i];
          if ( !v46 )
            break;
          if ( v46 == 10 || v46 == 13 )
          {
            v35[i] = 35;
          }
          else if ( v46 == 44 )
          {
            v35[i] = 95;
          }
        }
        RtlStringCchCatW(v35, v36, L"\r\n");
        v47 = -1;
        v48 = -1;
        do
          ++v48;
        while ( WideCharStr[v48] );
        if ( dword_140042B14 )
          AslLogpWritePipe(WideCharStr, 2 * v48);
        if ( WideCharToMultiByte_0(0xFDE9u, 0, WideCharStr, -1, MultiByteStr, 1024, 0, 0) )
        {
          v49 = MultiByteStr[0];
        }
        else
        {
          v49 = 0;
          MultiByteStr[0] = 0;
        }
        if ( v49 )
        {
LABEL_136:
          v67 = -1;
          do
            ++v67;
          while ( MultiByteStr[v67] );
          if ( v72 || v74 )
          {
            v68 = v82;
            AslLogpWriteLog(v82, MultiByteStr, v67);
          }
          else
          {
            v68 = v82;
          }
          if ( a2 != 1 || (v69 = *((_QWORD *)v68 + 89)) == 0 )
          {
            v70 = v75;
            goto LABEL_152;
          }
          v84 = MultiByteStr;
          do
            ++v47;
          while ( MultiByteStr[v47] );
          v70 = v75;
          v85 = v47 + 1;
          v86 = 0;
          if ( v75 == 1 )
          {
            v71 = AE_DEBUG_EVENT;
          }
          else
          {
            if ( v75 != 2 )
            {
LABEL_152:
              if ( v73 )
                AslLogpWritePanther((const char **)v68, v70, a3, v83, MultiByteStr);
              SetLastError_0(dwErrCode);
              if ( v70 == 1 && (*(_BYTE *)(*(_QWORD *)v68 + 80LL) & 2) != 0 )
              {
                if ( IsDebuggerPresent_0() )
                  DebugBreak_0();
              }
              return;
            }
            v71 = AE_MARK_EVENT;
          }
          EtwEventWrite(v69, v71, 1, &v84);
          goto LABEL_152;
        }
        v50 = v83;
        if ( v83 == -1 )
          v50 = 0;
        v51 = (const char *)a3;
        if ( !a3 )
          v51 = (const char *)&dword_1400326D4;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v48, "%s,%s,%d,", (&off_140030E98)[v27], v51, v50) < 0 && v48 )
        {
          v52 = 2147483646;
          if ( v48 <= 0x7FFFFFFF )
          {
            v53 = 2147483646;
            v54 = "ASL_LOG FAIL: ";
            v55 = v48;
            v56 = MultiByteStr;
            do
            {
              if ( !v53 )
                break;
              if ( !*v54 )
                break;
              *v56++ = *v54++;
              --v53;
              --v55;
            }
            while ( v55 );
            v57 = v56 - 1;
            if ( v55 )
              v57 = v56;
            *v57 = 0;
          }
          else
          {
            MultiByteStr[0] = 0;
          }
        }
        else
        {
          v52 = 2147483646;
        }
        v58 = -1;
        do
          ++v58;
        while ( MultiByteStr[v58] );
        v59 = &MultiByteStr[v58];
        v60 = v48 - v58;
        if ( v60 )
        {
          if ( v60 > 0x7FFFFFFF )
          {
            *v59 = 0;
            goto LABEL_126;
          }
          v61 = v60 - 1;
          v62 = _vsnprintf(&MultiByteStr[v58], v60 - 1, v84, Args);
          if ( v62 < 0 || v62 > v61 || (v33 = 0, v62 == v61) )
            v59[v61] = 0;
          if ( v33 >= 0 )
            goto LABEL_135;
        }
        if ( !v60 )
        {
LABEL_135:
          AslLogpFinalizeBuffer(v59, v60 + 2);
          goto LABEL_136;
        }
LABEL_126:
        if ( v60 <= 0x7FFFFFFF )
        {
          v63 = "Message too long!";
          v64 = v60;
          v65 = v59;
          do
          {
            if ( !v52 )
              break;
            if ( !*v63 )
              break;
            *v65++ = *v63++;
            --v52;
            --v64;
          }
          while ( v64 );
          v66 = v65 - 1;
          if ( v64 )
            v66 = v65;
          *v66 = 0;
        }
        else
        {
          *v59 = 0;
        }
        goto LABEL_135;
      }
      if ( !v80 )
      {
        v37 = Buffer;
        v38 = 0;
        v39 = 0;
        if ( Format[0] )
        {
          if ( !Buffer )
          {
            v39 = -1073741811;
LABEL_71:
            if ( (int)(v39 + 0x80000000) < 0 || v39 == -2147483643 )
              goto LABEL_83;
            goto LABEL_73;
          }
          v39 = -2147483643;
        }
LABEL_70:
        v32 = v37;
        v34 = v38;
        goto LABEL_71;
      }
      v40 = v80 - 1;
      v41 = _vsnwprintf(Buffer, v80 - 1, Format, Args);
      if ( v41 < 0 || v41 > v40 )
      {
        v39 = -2147483643;
      }
      else
      {
        v39 = 0;
        if ( v41 != v40 )
        {
          v40 = v41;
LABEL_69:
          v37 = &v32[v40];
          v38 = v36 - v40;
          goto LABEL_70;
        }
      }
      v32[v40] = 0;
      goto LABEL_69;
    }
  }
}

```

## disassembly

```asm
0x14000b83c  push    rbp
0x14000b83e  push    rbx
0x14000b83f  push    rsi
0x14000b840  push    rdi
0x14000b841  push    r12
0x14000b843  push    r13
0x14000b845  push    r14
0x14000b847  push    r15
0x14000b849  lea     rbp, [rsp-13C8h]
0x14000b851  mov     eax, 14C8h
0x14000b856  call    _alloca_probe
0x14000b85b  sub     rsp, rax
0x14000b85e  mov     rax, cs:__security_cookie
0x14000b865  xor     rax, rsp
0x14000b868  mov     [rbp+1400h+var_50], rax
0x14000b86f  mov     r12, [rbp+1400h+arg_20]
0x14000b876  mov     r13, r9
0x14000b879  mov     rax, [rbp+1400h+arg_28]
0x14000b880  mov     esi, edx
0x14000b882  mov     [rbp+1400h+var_1468], r12
0x14000b886  mov     rbx, rcx
0x14000b889  mov     [rbp+1400h+Args], rax
0x14000b88d  mov     [rbp+1400h+var_1470], r9
0x14000b891  mov     [rsp+1500h+var_1498], r8
0x14000b896  mov     [rsp+1500h+var_14A4], edx
0x14000b89a  mov     [rbp+1400h+var_1478], rcx
0x14000b89e  test    rcx, rcx
0x14000b8a1  jz      loc_14000BFCF
0x14000b8a7  call    GetLastError_0
0x14000b8ac  xor     edx, edx
0x14000b8ae  mov     [rsp+1500h+dwErrCode], eax
0x14000b8b2  mov     [rbp+1400h+MultiByteStr], dl
0x14000b8b5  cmp     esi, 3
0x14000b8b8  jnz     short loc_14000B8CC
0x14000b8ba  mov     rax, [rbx]
0x14000b8bd  test    byte ptr [rax+50h], 10h
0x14000b8c1  jnz     short loc_14000B8CC
0x14000b8c3  mov     r15b, dl
0x14000b8c6  mov     [rsp+1500h+var_14B0], dl
0x14000b8ca  jmp     short loc_14000B8D7
0x14000b8cc  mov     rax, [rbx]
0x14000b8cf  mov     r15b, 1
0x14000b8d2  mov     [rsp+1500h+var_14B0], r15b
0x14000b8d7  mov     ecx, [rax+50h]
0x14000b8da  mov     r14d, 3
0x14000b8e0  and     ecx, 100h
0x14000b8e6  cmp     esi, r14d
0x14000b8e9  mov     [rsp+1500h+var_14AC], ecx
0x14000b8ed  cmovl   r14d, esi
0x14000b8f1  mov     [rsp+1500h+var_14A8], r14d
0x14000b8f6  cmp     [rbx+2D0h], rdx
0x14000b8fd  jnz     short loc_14000B91C
0x14000b8ff  cmp     cs:qword_140042B18, rdx
0x14000b906  jz      short loc_14000B91C
0x14000b908  mov     cs:dword_140042B2C, edx
0x14000b90e  mov     cs:qword_140042B18, rdx
0x14000b915  mov     cs:WdsSetupLogMessageA, rdx
0x14000b91c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000b920  cmp     cs:dword_140042B2C, edx
0x14000b926  jnz     loc_14000B9F0
0x14000b92c  lea     r8, [rbx+2D0h]; phModule
0x14000b933  mov     cs:dword_140042B2C, 1
0x14000b93d  lea     rdx, aWdscoreDll; "wdscore.dll"
0x14000b944  xor     ecx, ecx; dwFlags
0x14000b946  call    cs:__imp_GetModuleHandleExA
0x14000b94c  test    eax, eax
0x14000b94e  jz      short loc_14000B984
0x14000b950  mov     rcx, [rbx+2D0h]; hModule
0x14000b957  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x14000b95e  call    GetProcAddress_0
0x14000b963  mov     rcx, [rbx+2D0h]; hModule
0x14000b96a  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x14000b971  mov     cs:qword_140042B18, rax
0x14000b978  call    GetProcAddress_0
0x14000b97d  mov     cs:WdsSetupLogMessageA, rax
0x14000b984  mov     [rsp+1500h+hTemplateFile], 0; hTemplateFile
0x14000b98d  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x14000b994  mov     [rsp+1500h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14000b99c  xor     r9d, r9d; lpSecurityAttributes
0x14000b99f  xor     r8d, r8d; dwShareMode
0x14000b9a2  mov     [rsp+1500h+dwCreationDisposition], 3; dwCreationDisposition
0x14000b9aa  mov     edx, 40000000h; dwDesiredAccess
0x14000b9af  call    cs:__imp_CreateFileW
0x14000b9b5  cmp     rax, rdi
0x14000b9b8  jnz     short loc_14000B9D8
0x14000b9ba  call    GetLastError_0
0x14000b9bf  mov     ecx, [rsp+1500h+var_14AC]
0x14000b9c3  xor     edx, edx
0x14000b9c5  cmp     eax, 0E7h
0x14000b9ca  jnz     short loc_14000B9F0
0x14000b9cc  mov     cs:dword_140042B14, 1
0x14000b9d6  jmp     short loc_14000B9F0
0x14000b9d8  mov     rcx, rax; hObject
0x14000b9db  mov     cs:dword_140042B14, 1
0x14000b9e5  call    CloseHandle_0
0x14000b9ea  mov     ecx, [rsp+1500h+var_14AC]
0x14000b9ee  xor     edx, edx
0x14000b9f0  cmp     cs:qword_140042B18, rdx
0x14000b9f7  jz      short loc_14000BA04
0x14000b9f9  cmp     cs:WdsSetupLogMessageA, rdx
0x14000ba00  mov     al, 1
0x14000ba02  jnz     short loc_14000BA06
0x14000ba04  mov     al, dl
0x14000ba06  mov     [rsp+1500h+var_14AF], al
0x14000ba0a  test    r15b, r15b
0x14000ba0d  jnz     short loc_14000BA28
0x14000ba0f  cmp     esi, 1
0x14000ba12  jz      short loc_14000BA28
0x14000ba14  test    al, al
0x14000ba16  jnz     short loc_14000BA28
0x14000ba18  cmp     cs:dword_140042B14, edx
0x14000ba1e  jnz     short loc_14000BA28
0x14000ba20  test    ecx, ecx
0x14000ba22  jz      loc_14000BFCF
0x14000ba28  mov     r15d, 3FEh
0x14000ba2e  lea     rax, [rbp+1400h+WideCharStr]
0x14000ba35  mov     r9, r12
0x14000ba38  mov     [rsp+1500h+Buffer], rax
0x14000ba3d  lea     r8, aHs_1; "%hs"
0x14000ba44  mov     [rsp+1500h+var_1488], r15
0x14000ba49  lea     rcx, [rbp+1400h+Format]
0x14000ba50  lea     r12d, [r15+2]
0x14000ba54  mov     edx, r12d
0x14000ba57  call    RtlStringCchPrintfW
0x14000ba5c  xor     r10d, r10d
0x14000ba5f  lea     rbx, aAslLogFail; "ASL_LOG FAIL: "
0x14000ba66  mov     esi, 7FFFFFFEh
0x14000ba6b  test    eax, eax
0x14000ba6d  jns     short loc_14000BAB1
0x14000ba6f  mov     ecx, esi
0x14000ba71  lea     rax, [rbp+1400h+Format]
0x14000ba78  mov     r8, rbx
0x14000ba7b  mov     edx, r12d
0x14000ba7e  test    rcx, rcx
0x14000ba81  jz      short loc_14000BAA2
0x14000ba83  movzx   r9d, word ptr [r8]
0x14000ba87  test    r9w, r9w
0x14000ba8b  jz      short loc_14000BAA2
0x14000ba8d  mov     [rax], r9w
0x14000ba91  add     r8, 2
0x14000ba95  add     rax, 2
0x14000ba99  dec     rcx
0x14000ba9c  sub     rdx, 1
0x14000baa0  jnz     short loc_14000BA7E
0x14000baa2  test    rdx, rdx
0x14000baa5  lea     rcx, [rax-2]
0x14000baa9  cmovnz  rcx, rax
0x14000baad  mov     [rcx], r10w
0x14000bab1  movzx   eax, [rbp+1400h+Format]
0x14000bab8  test    ax, ax
0x14000babb  jz      short loc_14000BB0A
0x14000babd  mov     edx, 53h ; 'S'
0x14000bac2  lea     rcx, [rbp+1400h+Format]
0x14000bac9  lea     r8d, [rdx+20h]
0x14000bacd  cmp     ax, 25h ; '%'
0x14000bad1  jnz     short loc_14000BAFE
0x14000bad3  add     rcx, 2
0x14000bad7  cmp     word ptr [rcx], 2Eh ; '.'
0x14000badb  jz      short loc_14000BAD3
0x14000badd  movzx   eax, word ptr [rcx]
0x14000bae0  sub     ax, 30h ; '0'
0x14000bae4  cmp     ax, 9
0x14000bae8  jbe     short loc_14000BAD3
0x14000baea  cmp     [rcx], r8w
0x14000baee  jnz     short loc_14000BAF5
0x14000baf0  mov     [rcx], dx
0x14000baf3  jmp     short loc_14000BAFE
0x14000baf5  cmp     [rcx], dx
0x14000baf8  jnz     short loc_14000BAFE
0x14000bafa  mov     [rcx], r8w
0x14000bafe  add     rcx, 2
0x14000bb02  movzx   eax, word ptr [rcx]
0x14000bb05  test    ax, ax
0x14000bb08  jnz     short loc_14000BACD
0x14000bb0a  mov     eax, r13d
0x14000bb0d  cmp     r13, rdi
0x14000bb10  jnz     short loc_14000BB15
0x14000bb12  mov     eax, r10d
0x14000bb15  mov     [rsp+1500h+var_14C0], eax
0x14000bb19  lea     rcx, off_140030E98; "PRINT"
0x14000bb20  mov     rax, [rsp+1500h+var_1498]
0x14000bb25  lea     r9, [rsp+1500h+var_1488]; unsigned __int64 *
0x14000bb2a  mov     [rsp+1500h+lpUsedDefaultChar], rax
0x14000bb2f  lea     r8, [rsp+1500h+Buffer]; unsigned __int16 **
0x14000bb34  movsxd  r13, r14d
0x14000bb37  mov     rdx, r15; unsigned __int64
0x14000bb3a  add     r13, r13
0x14000bb3d  mov     rax, [rcx+r13*8]
0x14000bb41  lea     rcx, [rbp+1400h+WideCharStr]; Buffer
0x14000bb48  mov     [rsp+1500h+hTemplateFile], rax
0x14000bb4d  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x14000bb54  mov     qword ptr [rsp+1500h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x14000bb59  mov     [rsp+1500h+dwCreationDisposition], 100h; unsigned int
0x14000bb61  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x14000bb66  xor     r9d, r9d
0x14000bb69  test    eax, eax
0x14000bb6b  jns     short loc_14000BBAD
0x14000bb6d  mov     rcx, rsi
0x14000bb70  lea     rax, [rbp+1400h+WideCharStr]
0x14000bb77  mov     rdx, r12
0x14000bb7a  test    rcx, rcx
0x14000bb7d  jz      short loc_14000BB9E
0x14000bb7f  movzx   r8d, word ptr [rbx]
0x14000bb83  test    r8w, r8w
0x14000bb87  jz      short loc_14000BB9E
0x14000bb89  mov     [rax], r8w
0x14000bb8d  add     rbx, 2
0x14000bb91  add     rax, 2
0x14000bb95  dec     rcx
0x14000bb98  sub     rdx, 1
0x14000bb9c  jnz     short loc_14000BB7A
0x14000bb9e  test    rdx, rdx
0x14000bba1  lea     rcx, [rax-2]
0x14000bba5  cmovnz  rcx, rax
0x14000bba9  mov     [rcx], r9w
0x14000bbad  mov     r14, [rsp+1500h+Buffer]
0x14000bbb2  mov     r12d, 80000005h
0x14000bbb8  mov     rsi, [rsp+1500h+var_1488]
0x14000bbbd  mov     rdi, r14
0x14000bbc0  mov     r15, rsi
0x14000bbc3  test    r14, r14
0x14000bbc6  jnz     short loc_14000BBCD
0x14000bbc8  test    rsi, rsi
0x14000bbcb  jnz     short loc_14000BBD6
0x14000bbcd  cmp     r15, 7FFFFFFFh
0x14000bbd4  jbe     short loc_14000BBDF
0x14000bbd6  mov     [r14], r9w
0x14000bbda  jmp     loc_14000BC6D
0x14000bbdf  test    r15, r15
0x14000bbe2  jnz     short loc_14000BC08
0x14000bbe4  mov     rdx, rdi
0x14000bbe7  mov     rax, r15
0x14000bbea  mov     ecx, r9d
0x14000bbed  cmp     [rbp+1400h+Format], r9w
0x14000bbf5  jz      short loc_14000BC56
0x14000bbf7  test    rdi, rdi
0x14000bbfa  jnz     short loc_14000BC03
0x14000bbfc  mov     ecx, 0C000000Dh
0x14000bc01  jmp     short loc_14000BC5C
0x14000bc03  mov     ecx, r12d
0x14000bc06  jmp     short loc_14000BC56
0x14000bc08  mov     r9, [rbp+1400h+Args]; Args
0x14000bc0c  lea     rbx, [rsi-1]
0x14000bc10  mov     rdx, rbx; BufferCount
0x14000bc13  lea     r8, [rbp+1400h+Format]; Format
0x14000bc1a  mov     rcx, rdi; Buffer
0x14000bc1d  call    cs:__imp__vsnwprintf
0x14000bc23  xor     r9d, r9d
0x14000bc26  test    eax, eax
0x14000bc28  js      short loc_14000BC3B
0x14000bc2a  cdqe
0x14000bc2c  cmp     rax, rbx
0x14000bc2f  ja      short loc_14000BC3B
0x14000bc31  mov     ecx, r9d
0x14000bc34  jz      short loc_14000BC3E
0x14000bc36  mov     rbx, rax
0x14000bc39  jmp     short loc_14000BC43
0x14000bc3b  mov     ecx, r12d
0x14000bc3e  mov     [r14+rbx*2], r9w
0x14000bc43  mov     rax, r15
0x14000bc46  lea     rdx, [r14+rbx*2]
0x14000bc4a  sub     rax, rbx
0x14000bc4d  test    ecx, ecx
0x14000bc4f  jns     short loc_14000BC56
0x14000bc51  cmp     ecx, r12d
0x14000bc54  jnz     short loc_14000BC5C
0x14000bc56  mov     r14, rdx
0x14000bc59  mov     rsi, rax
0x14000bc5c  mov     edx, 80000000h
0x14000bc61  lea     eax, [rcx+rdx]
0x14000bc64  test    edx, eax
0x14000bc66  jnz     short loc_14000BCC3
0x14000bc68  cmp     ecx, r12d
0x14000bc6b  jz      short loc_14000BCC3
0x14000bc6d  test    rsi, rsi
0x14000bc70  jz      short loc_14000BCC3
0x14000bc72  cmp     rsi, 7FFFFFFFh
0x14000bc79  jbe     short loc_14000BC83
0x14000bc7b  xor     esi, esi
0x14000bc7d  mov     [r14], si
0x14000bc81  jmp     short loc_14000BCC5
0x14000bc83  mov     eax, 7FFFFFFEh
0x14000bc88  lea     rdx, aMessageTooLong; "Message too long!"
0x14000bc8f  test    rax, rax
0x14000bc92  jz      short loc_14000BCB1
0x14000bc94  movzx   ecx, word ptr [rdx]
0x14000bc97  test    cx, cx
0x14000bc9a  jz      short loc_14000BCB1
0x14000bc9c  mov     [r14], cx
0x14000bca0  add     rdx, 2
0x14000bca4  add     r14, 2
0x14000bca8  dec     rax
0x14000bcab  sub     rsi, 1
0x14000bcaf  jnz     short loc_14000BC8F
0x14000bcb1  test    rsi, rsi
0x14000bcb4  lea     rcx, [r14-2]
0x14000bcb8  cmovnz  rcx, r14
0x14000bcbc  xor     esi, esi
0x14000bcbe  mov     [rcx], si
0x14000bcc1  jmp     short loc_14000BCC5
  ... truncated ...
```
