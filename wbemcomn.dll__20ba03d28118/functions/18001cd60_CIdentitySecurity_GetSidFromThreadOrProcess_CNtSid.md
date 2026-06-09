# CIdentitySecurity::GetSidFromThreadOrProcess(CNtSid &)

- ea: `0x18001cd60`
- end: `0x18001d196`
- name: `?GetSidFromThreadOrProcess@CIdentitySecurity@@AEAAJAEAVCNtSid@@@Z`
- size: `1078`
- prototype: `__int64 __fastcall(CIdentitySecurity *__hidden this, struct CNtSid *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001f250`
- `0x18001f360`
- `0x180023160`

## callees

- `0x18000ab30`
- `0x18001cd60`
- `0x18001d19c`
- `0x1800298f0`
- `0x18002a1f0`
- `0x18002c98c`
- `0x180033f0c`
- `0x1800442d3`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cf79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cfa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cf79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cfa0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ce2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cec0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ce2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d16b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d16b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cfee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d0d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d165`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cfee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d0d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d165`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d02b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d061`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d097`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d0f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d02b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d061`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d097`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d0f2`
- `ntdll!RtlLengthSid` at `0x18001ce0b`
- `ntdll!RtlLengthSid` at `0x18001cea2`
- `ntdll!RtlLengthSid` at `0x18001ce0b`
- `ntdll!RtlLengthSid` at `0x18001cea2`

## string_xrefs

- `0x18001d01d`: `CopySid`
- `0x18001d053`: `CopySid`
- `0x18001d089`: `IsValidSid`
- `0x18001d0e4`: `GetTokenInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
signed int __fastcall CIdentitySecurity::GetSidFromThreadOrProcess(CIdentitySecurity *this, struct CNtSid *a2)
{
  FARPROC ProcAddress; // rax
  PSID v4; // r14
  void *v5; // rdi
  DWORD LastError; // ebx
  FARPROC v7; // rax
  ULONG v8; // eax
  ULONG v9; // r12d
  void *v10; // rax
  FARPROC v11; // rax
  __int64 v12; // r14
  ULONG v13; // eax
  size_t v14; // r12
  LPVOID v15; // rax
  void *v16; // rbx
  FARPROC v17; // rax
  int v18; // eax
  void *v19; // r8
  int v20; // eax
  signed int v21; // ebx
  signed int result; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD SecurityDll; // eax
  void *v27; // [rsp+30h] [rbp-79h] BYREF
  __int64 v28; // [rsp+38h] [rbp-71h]
  int v29; // [rsp+40h] [rbp-69h]
  int v30; // [rsp+44h] [rbp-65h]
  void *v31; // [rsp+48h] [rbp-61h]
  int v32; // [rsp+50h] [rbp-59h]
  int v33; // [rsp+54h] [rbp-55h]
  int v34; // [rsp+58h] [rbp-51h] BYREF
  void *v35[2]; // [rsp+60h] [rbp-49h] BYREF
  PSID Sid[12]; // [rsp+70h] [rbp-39h] BYREF

  v34 = 88;
  ProcAddress = (FARPROC)qword_180070310;
  if ( qword_180070310 )
    goto LABEL_62;
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
    goto LABEL_28;
  }
  ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetTokenInformation");
  qword_180070310 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_62:
    if ( ((unsigned int (__fastcall *)(__int64, __int64, PSID *, __int64, int *))ProcAddress)(-6, 1, Sid, 88, &v34) )
    {
      v4 = Sid[0];
      v5 = 0;
      v31 = 0;
      LastError = 0;
      v32 = 0;
      v33 = 8;
      v7 = (FARPROC)qword_1800702F8;
      if ( !qword_1800702F8 )
      {
        v25 = DLpLoadSecurityDll();
        if ( v25 )
        {
          SetLastError(v25);
          goto LABEL_32;
        }
        v7 = GetProcAddress(g_hInstSecurityDLL, "IsValidSid");
        qword_1800702F8 = (__int64)v7;
        if ( !v7 )
          goto LABEL_32;
      }
      if ( ((unsigned int (__fastcall *)(PSID))v7)(v4) )
      {
        v8 = RtlLengthSid(v4);
        v9 = v8;
        if ( hHeap )
        {
          v10 = HeapAlloc(hHeap, 0, v8);
          v5 = v10;
          v31 = v10;
          if ( v10 )
          {
            memset_0(v10, 0, v9);
            v11 = (FARPROC)qword_180070338;
            if ( qword_180070338 )
              goto LABEL_8;
            v23 = DLpLoadSecurityDll();
            if ( v23 )
            {
              SetLastError(v23);
            }
            else
            {
              v11 = GetProcAddress(g_hInstSecurityDLL, "CopySid");
              qword_180070338 = (__int64)v11;
              if ( v11 )
              {
LABEL_8:
                if ( ((unsigned int (__fastcall *)(_QWORD, void *, PSID))v11)(v9, v5, v4) )
                {
                  v10 = v5;
                  goto LABEL_10;
                }
              }
            }
            CMUILocale::_Free(v5);
            v5 = 0;
            v31 = 0;
            LastError = GetLastError();
            v32 = LastError;
            v33 = 8;
            v10 = 0;
LABEL_10:
            v12 = 0;
            v28 = 0;
            v30 = 8;
            if ( LastError )
            {
              v29 = LastError;
            }
            else
            {
              v29 = 1;
              if ( v10 )
              {
                v13 = RtlLengthSid(v5);
                v14 = v13;
                if ( hHeap )
                  v15 = HeapAlloc(hHeap, 0, v13);
                else
                  v15 = 0;
                std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&v27, (__int64)v15);
                v16 = v27;
                if ( !v27 )
                {
                  LastError = 14;
                  v29 = 14;
                  goto LABEL_18;
                }
                memset_0(v27, 0, v14);
                v17 = (FARPROC)qword_180070338;
                if ( !qword_180070338 )
                {
                  v24 = DLpLoadSecurityDll();
                  if ( v24 )
                  {
                    SetLastError(v24);
                    goto LABEL_57;
                  }
                  v17 = GetProcAddress(g_hInstSecurityDLL, "CopySid");
                  qword_180070338 = (__int64)v17;
                  if ( !v17 )
                    goto LABEL_57;
                }
                if ( ((unsigned int (__fastcall *)(_QWORD, void *, void *))v17)((unsigned int)v14, v16, v5) )
                {
                  CWbemTime::CWbemTime((CWbemTime *)v35);
                  v12 = std::unique_ptr<CExecQueue::CThreadRecord>::release(&v27);
                  v28 = v12;
                  LastError = 0;
                  v29 = 0;
                  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v35);
LABEL_18:
                  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v27);
                  goto LABEL_19;
                }
LABEL_57:
                LastError = GetLastError();
                v29 = LastError;
                goto LABEL_18;
              }
              LastError = 6;
              v29 = 6;
            }
LABEL_19:
            v18 = *((_DWORD *)a2 + 2);
            *((_DWORD *)a2 + 2) = LastError;
            v29 = v18;
            v19 = *(void **)a2;
            *(_QWORD *)a2 = v12;
            v28 = (__int64)v19;
            v20 = *((_DWORD *)a2 + 3);
            *((_DWORD *)a2 + 3) = 8;
            v30 = v20;
            if ( hHeap && v19 )
              HeapFree(hHeap, 0, v19);
            v21 = *((_DWORD *)a2 + 2);
            if ( v21 )
            {
              if ( v21 == 14 )
              {
                CMUILocale::_Free(v5);
                return -2147217402;
              }
              else
              {
                if ( v21 > 0 )
                  v21 = (unsigned __int16)v21 | 0x80070000;
                CMUILocale::_Free(v5);
                return v21;
              }
            }
            else
            {
              if ( hHeap )
              {
                if ( v5 )
                  HeapFree(hHeap, 0, v5);
              }
              return 0;
            }
          }
        }
        else
        {
          v31 = 0;
          v10 = 0;
        }
        LastError = 14;
        v32 = 14;
        goto LABEL_10;
      }
LABEL_32:
      LastError = 13;
      v32 = 13;
      v10 = 0;
      goto LABEL_10;
    }
  }
LABEL_28:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001cd60  mov     [rsp-8+arg_0], rbx
0x18001cd65  mov     [rsp-8+arg_10], rsi
0x18001cd6a  push    rbp
0x18001cd6b  push    rdi
0x18001cd6c  push    r12
0x18001cd6e  push    r14
0x18001cd70  push    r15
0x18001cd72  lea     rbp, [rsp-37h]
0x18001cd77  sub     rsp, 0E0h
0x18001cd7e  mov     rax, cs:__security_cookie
0x18001cd85  xor     rax, rsp
0x18001cd88  mov     [rbp+57h+var_30], rax
0x18001cd8c  mov     rsi, rdx
0x18001cd8f  mov     [rbp+57h+var_A8], 58h ; 'X'
0x18001cd96  mov     rax, cs:qword_180070310
0x18001cd9d  test    rax, rax
0x18001cda0  jz      loc_18001D0CE
0x18001cda6  lea     rcx, [rbp+57h+var_A8]
0x18001cdaa  mov     [rsp+100h+var_E0], rcx
0x18001cdaf  mov     r9d, 58h ; 'X'
0x18001cdb5  lea     r8, [rbp+57h+Sid]
0x18001cdb9  mov     edx, 1
0x18001cdbe  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18001cdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdca  test    eax, eax
0x18001cdcc  jz      loc_18001CFD0
0x18001cdd2  mov     r14, [rbp+57h+Sid]
0x18001cdd6  xor     edi, edi
0x18001cdd8  mov     [rbp+57h+var_B8], rdi
0x18001cddc  xor     ebx, ebx
0x18001cdde  mov     [rbp+57h+var_B0], ebx
0x18001cde1  mov     [rbp+57h+var_AC], 8
0x18001cde8  mov     rax, cs:qword_1800702F8
0x18001cdef  test    rax, rax
0x18001cdf2  jz      loc_18001D07C
0x18001cdf8  mov     rcx, r14
0x18001cdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce00  test    eax, eax
0x18001ce02  jz      loc_18001CFF4
0x18001ce08  mov     rcx, r14; Sid
0x18001ce0b  call    cs:__imp_RtlLengthSid
0x18001ce11  mov     r12d, eax
0x18001ce14  cmp     cs:hHeap, rbx
0x18001ce1b  jz      loc_18001D10D
0x18001ce21  mov     r8d, r12d; dwBytes
0x18001ce24  xor     edx, edx; dwFlags
0x18001ce26  mov     rcx, cs:hHeap; hHeap
0x18001ce2d  call    cs:__imp_HeapAlloc
0x18001ce33  mov     rdi, rax
0x18001ce36  mov     [rbp+57h+var_B8], rax
0x18001ce3a  test    rax, rax
0x18001ce3d  jz      loc_18001D113
0x18001ce43  mov     r8d, r12d; Size
0x18001ce46  xor     edx, edx; Val
0x18001ce48  mov     rcx, rax; void *
0x18001ce4b  call    memset_0
0x18001ce50  mov     rax, cs:qword_180070338
0x18001ce57  test    rax, rax
0x18001ce5a  jz      loc_18001D010
0x18001ce60  mov     r8, r14
0x18001ce63  mov     rdx, rdi
0x18001ce66  mov     ecx, r12d
0x18001ce69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce6e  test    eax, eax
0x18001ce70  jz      loc_18001D128
0x18001ce76  mov     rax, rdi
0x18001ce79  xor     r14d, r14d
0x18001ce7c  mov     [rbp+57h+var_C8], r14
0x18001ce80  mov     [rbp+57h+var_BC], 8
0x18001ce87  test    ebx, ebx
0x18001ce89  jnz     loc_18001CFE4
0x18001ce8f  mov     [rbp+57h+var_C0], 1
0x18001ce96  test    rax, rax
0x18001ce99  jz      loc_18001D003
0x18001ce9f  mov     rcx, rdi; Sid
0x18001cea2  call    cs:__imp_RtlLengthSid
0x18001cea8  mov     r12d, eax
0x18001ceab  mov     rcx, cs:hHeap; hHeap
0x18001ceb2  test    rcx, rcx
0x18001ceb5  jz      loc_18001D14F
0x18001cebb  mov     r8d, r12d; dwBytes
0x18001cebe  xor     edx, edx; dwFlags
0x18001cec0  call    cs:__imp_HeapAlloc
0x18001cec6  mov     rdx, rax
0x18001cec9  lea     rcx, [rbp+57h+var_D0]
0x18001cecd  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18001ced2  nop
0x18001ced3  mov     rbx, [rbp+57h+var_D0]
0x18001ced7  test    rbx, rbx
0x18001ceda  jz      loc_18001D156
0x18001cee0  mov     r8, r12; Size
0x18001cee3  xor     edx, edx; Val
0x18001cee5  mov     rcx, rbx; void *
0x18001cee8  call    memset_0
0x18001ceed  mov     rax, cs:qword_180070338
0x18001cef4  test    rax, rax
0x18001cef7  jz      loc_18001D046
0x18001cefd  mov     r8, rdi
0x18001cf00  mov     rdx, rbx
0x18001cf03  mov     ecx, r12d
0x18001cf06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf0b  test    eax, eax
0x18001cf0d  jz      loc_18001D16B
0x18001cf13  lea     rcx, [rbp+57h+var_A0]; this
0x18001cf17  call    ??0CWbemTime@@QEAA@XZ; CWbemTime::CWbemTime(void)
0x18001cf1c  nop
0x18001cf1d  lea     rcx, [rbp+57h+var_D0]
0x18001cf21  call    ?release@?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAAPEAVCThreadRecord@CExecQueue@@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::release(void)
0x18001cf26  mov     r14, rax
0x18001cf29  mov     [rbp+57h+var_C8], rax
0x18001cf2d  xor     ebx, ebx
0x18001cf2f  mov     [rbp+57h+var_C0], ebx
0x18001cf32  lea     rcx, [rbp+57h+var_A0]
0x18001cf36  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001cf3b  nop
0x18001cf3c  lea     rcx, [rbp+57h+var_D0]
0x18001cf40  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001cf45  nop
0x18001cf46  mov     eax, [rsi+8]
0x18001cf49  mov     [rsi+8], ebx
0x18001cf4c  mov     [rbp+57h+var_C0], eax
0x18001cf4f  mov     r8, [rsi]; lpMem
0x18001cf52  mov     [rsi], r14
0x18001cf55  mov     [rbp+57h+var_C8], r8
0x18001cf59  mov     eax, [rsi+0Ch]
0x18001cf5c  mov     dword ptr [rsi+0Ch], 8
0x18001cf63  mov     [rbp+57h+var_BC], eax
0x18001cf66  mov     rcx, cs:hHeap; hHeap
0x18001cf6d  test    rcx, rcx
0x18001cf70  jz      short loc_18001CF7F
0x18001cf72  test    r8, r8
0x18001cf75  jz      short loc_18001CF7F
0x18001cf77  xor     edx, edx; dwFlags
0x18001cf79  call    cs:__imp_HeapFree
0x18001cf7f  mov     ebx, [rsi+8]
0x18001cf82  test    ebx, ebx
0x18001cf84  jnz     loc_18001D17B
0x18001cf8a  mov     rcx, cs:hHeap; hHeap
0x18001cf91  test    rcx, rcx
0x18001cf94  jz      short loc_18001CFA6
0x18001cf96  test    rdi, rdi
0x18001cf99  jz      short loc_18001CFA6
0x18001cf9b  mov     r8, rdi; lpMem
0x18001cf9e  xor     edx, edx; dwFlags
0x18001cfa0  call    cs:__imp_HeapFree
0x18001cfa6  xor     eax, eax
0x18001cfa8  mov     rcx, [rbp+57h+var_30]
0x18001cfac  xor     rcx, rsp; StackCookie
0x18001cfaf  call    __security_check_cookie
0x18001cfb4  lea     r11, [rsp+100h+var_20]
0x18001cfbc  mov     rbx, [r11+30h]
0x18001cfc0  mov     rsi, [r11+40h]
0x18001cfc4  mov     rsp, r11
0x18001cfc7  pop     r15
0x18001cfc9  pop     r14
0x18001cfcb  pop     r12
0x18001cfcd  pop     rdi
0x18001cfce  pop     rbp
0x18001cfcf  retn
0x18001cfd0  call    cs:__imp_GetLastError
0x18001cfd6  test    eax, eax
0x18001cfd8  jle     short loc_18001CFA8
0x18001cfda  movzx   eax, ax
0x18001cfdd  or      eax, 80070000h
0x18001cfe2  jmp     short loc_18001CFA8
0x18001cfe4  mov     [rbp+57h+var_C0], ebx
0x18001cfe7  jmp     loc_18001CF46
0x18001cfec  mov     ecx, eax; dwErrCode
0x18001cfee  call    cs:__imp_SetLastError
0x18001cff4  mov     ebx, 0Dh
0x18001cff9  mov     [rbp+57h+var_B0], ebx
0x18001cffc  xor     eax, eax
0x18001cffe  jmp     loc_18001CE79
0x18001d003  mov     ebx, 6
0x18001d008  mov     [rbp+57h+var_C0], ebx
0x18001d00b  jmp     loc_18001CF46
0x18001d010  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001d015  test    eax, eax
0x18001d017  jnz     loc_18001D120
0x18001d01d  lea     rdx, aCopysid; "CopySid"
0x18001d024  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d02b  call    cs:__imp_GetProcAddress
0x18001d031  mov     cs:qword_180070338, rax
0x18001d038  test    rax, rax
0x18001d03b  jnz     loc_18001CE60
0x18001d041  jmp     loc_18001D128
0x18001d046  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001d04b  test    eax, eax
0x18001d04d  jnz     loc_18001D163
0x18001d053  lea     rdx, aCopysid; "CopySid"
0x18001d05a  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d061  call    cs:__imp_GetProcAddress
0x18001d067  mov     cs:qword_180070338, rax
0x18001d06e  test    rax, rax
0x18001d071  jnz     loc_18001CEFD
0x18001d077  jmp     loc_18001D16B
0x18001d07c  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001d081  test    eax, eax
0x18001d083  jnz     loc_18001CFEC
0x18001d089  lea     rdx, aIsvalidsid; "IsValidSid"
0x18001d090  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d097  call    cs:__imp_GetProcAddress
0x18001d09d  mov     cs:qword_1800702F8, rax
0x18001d0a4  test    rax, rax
0x18001d0a7  jnz     loc_18001CDF8
0x18001d0ad  jmp     loc_18001CFF4
0x18001d0b2  test    ebx, ebx
0x18001d0b4  jle     short loc_18001D0BF
0x18001d0b6  movzx   ebx, bx
0x18001d0b9  or      ebx, 80070000h
0x18001d0bf  mov     rcx, rdi; void *
0x18001d0c2  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001d0c7  mov     eax, ebx
0x18001d0c9  jmp     loc_18001CFA8
0x18001d0ce  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001d0d3  test    eax, eax
0x18001d0d5  jz      short loc_18001D0E4
0x18001d0d7  mov     ecx, eax; dwErrCode
0x18001d0d9  call    cs:__imp_SetLastError
0x18001d0df  jmp     loc_18001CFD0
0x18001d0e4  lea     rdx, aGettokeninform; "GetTokenInformation"
0x18001d0eb  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d0f2  call    cs:__imp_GetProcAddress
0x18001d0f8  mov     cs:qword_180070310, rax
0x18001d0ff  test    rax, rax
0x18001d102  jz      loc_18001CFD0
0x18001d108  jmp     loc_18001CDA6
0x18001d10d  mov     [rbp+57h+var_B8], rdi
0x18001d111  xor     eax, eax
0x18001d113  mov     ebx, 0Eh
0x18001d118  mov     [rbp+57h+var_B0], ebx
0x18001d11b  jmp     loc_18001CE79
0x18001d120  mov     ecx, eax; dwErrCode
0x18001d122  call    cs:__imp_SetLastError
0x18001d128  mov     rcx, rdi; void *
0x18001d12b  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001d130  xor     edi, edi
0x18001d132  mov     [rbp+57h+var_B8], rdi
0x18001d136  call    cs:__imp_GetLastError
0x18001d13c  mov     ebx, eax
0x18001d13e  mov     [rbp+57h+var_B0], eax
0x18001d141  mov     [rbp+57h+var_AC], 8
0x18001d148  xor     eax, eax
0x18001d14a  jmp     loc_18001CE79
0x18001d14f  xor     eax, eax
0x18001d151  jmp     loc_18001CEC6
0x18001d156  mov     ebx, 0Eh
0x18001d15b  mov     [rbp+57h+var_C0], ebx
0x18001d15e  jmp     loc_18001CF3C
0x18001d163  mov     ecx, eax; dwErrCode
0x18001d165  call    cs:__imp_SetLastError
0x18001d16b  call    cs:__imp_GetLastError
0x18001d171  mov     ebx, eax
0x18001d173  mov     [rbp+57h+var_C0], eax
0x18001d176  jmp     loc_18001CF3C
0x18001d17b  cmp     ebx, 0Eh
0x18001d17e  jnz     loc_18001D0B2
0x18001d184  mov     rcx, rdi; void *
0x18001d187  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001d18c  mov     eax, 80041006h
0x18001d191  jmp     loc_18001CFA8
```
