# CDlpActionRecoverCrypto::GetEncryptedRangesFromWim(int *)

- ea: `0x18001a464`
- end: `0x18001a99f`
- name: `?GetEncryptedRangesFromWim@CDlpActionRecoverCrypto@@AEAAJPEAH@Z`
- size: `1339`
- prototype: `__int64 __fastcall(CDlpActionRecoverCrypto *__hidden this, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18000fb18`

## callees

- `0x180002108`
- `0x1800023f4`
- `0x180002638`
- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001a464`
- `0x18001fb4c`
- `0x18001fd60`
- `0x18007ed40`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x18001a898`
- `WIMGAPI!WIMCloseHandle` at `0x18001a898`
- `WIMGAPI!WIMGetImageInformation` at `0x18001a598`
- `WIMGAPI!WIMGetImageInformation` at `0x18001a598`
- `WIMGAPI!WIMCreateFile` at `0x18001a52d`
- `WIMGAPI!WIMCreateFile` at `0x18001a52d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a726`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a78f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a837`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a85d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a726`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a78f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a837`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a85d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a734`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a79d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a846`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a86b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a734`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a79d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a846`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a882`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a882`
- `UNATTEND!UnattendCtxCleanup` at `0x18001a824`
- `UNATTEND!UnattendCtxCleanup` at `0x18001a824`
- `UNATTEND!UnattendCtxGetString` at `0x18001a62f`
- `UNATTEND!UnattendCtxGetString` at `0x18001a759`
- `UNATTEND!UnattendCtxGetString` at `0x18001a7c2`
- `UNATTEND!UnattendCtxGetString` at `0x18001a62f`
- `UNATTEND!UnattendCtxGetString` at `0x18001a759`
- `UNATTEND!UnattendCtxGetString` at `0x18001a7c2`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18001a5ef`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18001a5ef`

## pseudocode

```c
__int64 __fastcall CDlpActionRecoverCrypto::GetEncryptedRangesFromWim(CDlpActionRecoverCrypto *this, int *a2)
{
  __int64 v4; // rbx
  __int64 v5; // r13
  signed int v6; // esi
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  signed int v11; // eax
  signed int LastError; // eax
  int v13; // eax
  int String; // eax
  int v15; // eax
  int StringCch; // eax
  int v17; // eax
  int v18; // r14d
  void *v19; // rsi
  HANDLE ProcessHeap; // rax
  int v21; // eax
  int v22; // eax
  void *v23; // rsi
  HANDLE v24; // rax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  HANDLE v28; // rax
  void *v29; // rdi
  HANDLE v30; // rax
  __int64 v32; // [rsp+20h] [rbp-49h]
  __int64 v33; // [rsp+28h] [rbp-41h]
  LPVOID lpMem; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-31h] BYREF
  int v36; // [rsp+3Ch] [rbp-2Dh] BYREF
  unsigned int v37; // [rsp+40h] [rbp-29h] BYREF
  __int64 v38; // [rsp+48h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-19h] BYREF
  __int64 v40; // [rsp+58h] [rbp-11h] BYREF
  __int64 v41; // [rsp+60h] [rbp-9h]
  __int128 v42; // [rsp+68h] [rbp-1h] BYREF
  __int64 v43; // [rsp+78h] [rbp+Fh]

  v4 = 0;
  v41 = 0;
  hMem = 0;
  lpMem = 0;
  v43 = 0;
  v35 = 0;
  v38 = 0;
  v42 = 0;
  v36 = 0;
  v5 = 0;
  v40 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = *((_QWORD *)this + 11);
    if ( !v7 )
      goto LABEL_57;
    LODWORD(v33) = -2147024809;
    LODWORD(v32) = 1833;
    goto LABEL_4;
  }
  v10 = WIMCreateFile(*((_QWORD *)this + 69), 0, 3, 0x20000000, 0, 0);
  v4 = v10;
  if ( v10 )
  {
    v41 = v10;
    v35 = 0;
    if ( (unsigned int)WIMGetImageInformation(v10, &hMem, &v35) )
    {
      v13 = UnattendCtxDeserializeBuffer(&v38, hMem, v35);
      v6 = v13;
      if ( v13 >= 0 )
      {
        String = UnattendCtxGetString(&v38, L"WIM\\ESD\\ENCRYPTED", L"Count", &lpMem);
        v6 = String;
        if ( String >= 0 )
        {
          if ( String == 1 )
          {
            *a2 = 0;
            v6 = 0;
            goto LABEL_57;
          }
          v15 = CMiscHelpersT<CEmptyType>::ConvertString2Number<int>(lpMem, &v36);
          v6 = v15;
          if ( v15 >= 0 )
          {
            v37 = 0;
            StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(
                          L"WIM\\ESD\\ENCRYPTED\\RANGE[*]",
                          &v37);
            v6 = StringCch;
            if ( StringCch >= 0 )
            {
              v17 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                      L"WIM\\ESD\\ENCRYPTED\\RANGE[*]",
                      v37,
                      &v40);
              v6 = v17;
              if ( v17 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
              v5 = v40;
            }
            else
            {
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
            if ( v6 >= 0 )
            {
              v18 = 0;
              if ( v36 > 0 )
              {
                while ( 1 )
                {
                  v19 = lpMem;
                  if ( lpMem )
                  {
                    ProcessHeap = GetProcessHeap();
                    HeapFree(ProcessHeap, 0, v19);
                    lpMem = 0;
                  }
                  v21 = UnattendCtxGetString(&v38, v5, L"Offset", &lpMem);
                  v6 = v21;
                  if ( v21 < 0 )
                    break;
                  if ( v21 )
                  {
                    v6 = -1048575725;
                    v7 = *((_QWORD *)this + 11);
                    if ( !v7 )
                      goto LABEL_57;
                    LODWORD(v33) = -1048575725;
                    LODWORD(v32) = 1882;
                    goto LABEL_4;
                  }
                  v22 = CMiscHelpersT<CEmptyType>::ConvertString2Number<unsigned __int64>(lpMem, &v42);
                  v6 = v22;
                  if ( v22 < 0 )
                  {
                    v7 = *((_QWORD *)this + 11);
                    if ( !v7 )
                      goto LABEL_57;
                    LODWORD(v33) = v22;
                    LODWORD(v32) = 1883;
                    goto LABEL_4;
                  }
                  v23 = lpMem;
                  if ( lpMem )
                  {
                    v24 = GetProcessHeap();
                    HeapFree(v24, 0, v23);
                    lpMem = 0;
                  }
                  v25 = UnattendCtxGetString(&v38, v5, L"Bytes", &lpMem);
                  v6 = v25;
                  if ( v25 < 0 )
                  {
                    v7 = *((_QWORD *)this + 11);
                    if ( !v7 )
                      goto LABEL_57;
                    LODWORD(v33) = v25;
                    LODWORD(v32) = 1886;
                    goto LABEL_4;
                  }
                  if ( v25 )
                  {
                    v6 = -1048575725;
                    v7 = *((_QWORD *)this + 11);
                    if ( !v7 )
                      goto LABEL_57;
                    LODWORD(v33) = -1048575725;
                    LODWORD(v32) = 1887;
                    goto LABEL_4;
                  }
                  v26 = CMiscHelpersT<CEmptyType>::ConvertString2Number<unsigned long>(lpMem, (char *)&v42 + 8);
                  v6 = v26;
                  if ( v26 < 0 )
                  {
                    v7 = *((_QWORD *)this + 11);
                    if ( !v7 )
                      goto LABEL_57;
                    LODWORD(v33) = v26;
                    LODWORD(v32) = 1888;
                    goto LABEL_4;
                  }
                  v27 = CArray<_WINDLP_WIM_RANGE,_WINDLP_WIM_RANGE,CAdaptorDefaultSpecialize,CPoliciesDefault>::Insert(
                          (char *)this + 616,
                          *((unsigned int *)this + 155),
                          &v42);
                  v6 = v27;
                  if ( v27 < 0 )
                  {
                    v7 = *((_QWORD *)this + 11);
                    if ( !v7 )
                      goto LABEL_57;
                    LODWORD(v33) = v27;
                    LODWORD(v32) = 1890;
                    goto LABEL_4;
                  }
                  if ( ++v18 >= v36 )
                    goto LABEL_56;
                }
                v7 = *((_QWORD *)this + 11);
                if ( !v7 )
                  goto LABEL_57;
                LODWORD(v33) = v21;
                LODWORD(v32) = 1881;
                goto LABEL_4;
              }
LABEL_56:
              *a2 = 1;
              goto LABEL_57;
            }
            v7 = *((_QWORD *)this + 11);
            if ( !v7 )
              goto LABEL_57;
            LODWORD(v33) = v6;
            LODWORD(v32) = 1871;
          }
          else
          {
            v7 = *((_QWORD *)this + 11);
            if ( !v7 )
              goto LABEL_57;
            LODWORD(v33) = v15;
            LODWORD(v32) = 1865;
          }
        }
        else
        {
          v7 = *((_QWORD *)this + 11);
          if ( !v7 )
            goto LABEL_57;
          LODWORD(v33) = String;
          LODWORD(v32) = 1853;
        }
      }
      else
      {
        v7 = *((_QWORD *)this + 11);
        if ( !v7 )
          goto LABEL_57;
        LODWORD(v33) = v13;
        LODWORD(v32) = 1852;
      }
LABEL_4:
      v8 = CDlpLogT<CEmptyType>::DlpLogFormat(
             v7,
             4u,
             (__int64)L"%s(%d): Result = 0x%X",
             L"CDlpActionRecoverCrypto::GetEncryptedRangesFromWim",
             v32,
             v33);
      v9 = (unsigned int)v8;
      if ( v8 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
      goto LABEL_6;
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v9 = 0;
      if ( v6 < 0 )
      {
        LODWORD(v33) = v6;
        LODWORD(v32) = 1848;
        goto LABEL_15;
      }
LABEL_6:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
    }
  }
  else
  {
    v41 = 0;
    v11 = GetLastError();
    v6 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v9 = 0;
      if ( v6 < 0 )
      {
        LODWORD(v33) = v6;
        LODWORD(v32) = 1845;
LABEL_15:
        v7 = *((_QWORD *)this + 11);
        goto LABEL_4;
      }
      goto LABEL_6;
    }
  }
LABEL_57:
  UnattendCtxCleanup(&v38);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v5 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v29 = lpMem;
  if ( lpMem )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v29);
    lpMem = 0;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v4 )
    WIMCloseHandle(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a464  push    rbp
0x18001a466  push    rbx
0x18001a467  push    rsi
0x18001a468  push    rdi
0x18001a469  push    r13
0x18001a46b  push    r14
0x18001a46d  push    r15
0x18001a46f  lea     rbp, [rsp-27h]
0x18001a474  sub     rsp, 90h
0x18001a47b  mov     rax, cs:__security_cookie
0x18001a482  xor     rax, rsp
0x18001a485  mov     [rbp+57h+var_40], rax
0x18001a489  mov     r15, rdx
0x18001a48c  mov     rdi, rcx
0x18001a48f  xor     ebx, ebx
0x18001a491  mov     [rbp+57h+var_60], rbx
0x18001a495  mov     [rbp+57h+hMem], rbx
0x18001a499  mov     [rbp+57h+lpMem], rbx
0x18001a49d  mov     [rbp+57h+var_48], rbx
0x18001a4a1  mov     [rbp+57h+var_88], ebx
0x18001a4a4  mov     [rbp+57h+var_78], rbx
0x18001a4a8  xorps   xmm0, xmm0
0x18001a4ab  movups  [rbp+57h+var_58], xmm0
0x18001a4af  mov     [rbp+57h+var_84], ebx
0x18001a4b2  xor     r13d, r13d
0x18001a4b5  mov     [rbp+57h+var_68], r13
0x18001a4b9  test    rdx, rdx
0x18001a4bc  jnz     short loc_18001A509
0x18001a4be  mov     esi, 80070057h
0x18001a4c3  mov     rcx, [rcx+58h]
0x18001a4c7  test    rcx, rcx
0x18001a4ca  jz      loc_18001A820
0x18001a4d0  mov     dword ptr [rsp+0C0h+var_98], esi
0x18001a4d4  mov     dword ptr [rsp+0C0h+var_A0], 729h
0x18001a4dc  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001a4e3  lea     r9, aCdlpactionreco_5; "CDlpActionRecoverCrypto::GetEncryptedRa"...
0x18001a4ea  mov     edx, 4
0x18001a4ef  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001a4f4  test    eax, eax
0x18001a4f6  mov     ecx, eax
0x18001a4f8  jns     short loc_18001A4FF
0x18001a4fa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001a4ff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001a504  jmp     loc_18001A820
0x18001a509  mov     [rsp+0C0h+var_98], 0
0x18001a512  mov     dword ptr [rsp+0C0h+var_A0], 0
0x18001a51a  xor     edx, edx
0x18001a51c  mov     r9d, 20000000h
0x18001a522  lea     r8d, [rdx+3]
0x18001a526  mov     rcx, [rcx+228h]
0x18001a52d  call    cs:__imp_WIMCreateFile
0x18001a533  mov     rbx, rax
0x18001a536  test    rax, rax
0x18001a539  jnz     short loc_18001A582
0x18001a53b  mov     [rbp+57h+var_60], rax
0x18001a53f  call    cs:__imp_GetLastError
0x18001a545  mov     esi, eax
0x18001a547  test    eax, eax
0x18001a549  jnz     short loc_18001A552
0x18001a54b  mov     esi, 80004005h
0x18001a550  jmp     short loc_18001A55D
0x18001a552  jle     short loc_18001A55D
0x18001a554  movzx   esi, ax
0x18001a557  or      esi, 80070000h
0x18001a55d  cmp     [rdi+58h], rbx
0x18001a561  jz      loc_18001A820
0x18001a567  xor     ecx, ecx
0x18001a569  test    esi, esi
0x18001a56b  jns     short loc_18001A4FF
0x18001a56d  mov     dword ptr [rsp+0C0h+var_98], esi
0x18001a571  mov     dword ptr [rsp+0C0h+var_A0], 735h
0x18001a579  mov     rcx, [rdi+58h]
0x18001a57d  jmp     loc_18001A4DC
0x18001a582  mov     [rbp+57h+var_60], rax
0x18001a586  mov     [rbp+57h+var_88], 0
0x18001a58d  lea     r8, [rbp+57h+var_88]
0x18001a591  lea     rdx, [rbp+57h+hMem]
0x18001a595  mov     rcx, rax
0x18001a598  call    cs:__imp_WIMGetImageInformation
0x18001a59e  test    eax, eax
0x18001a5a0  jnz     short loc_18001A5E3
0x18001a5a2  call    cs:__imp_GetLastError
0x18001a5a8  mov     esi, eax
0x18001a5aa  test    eax, eax
0x18001a5ac  jnz     short loc_18001A5B5
0x18001a5ae  mov     esi, 80004005h
0x18001a5b3  jmp     short loc_18001A5C0
0x18001a5b5  jle     short loc_18001A5C0
0x18001a5b7  movzx   esi, ax
0x18001a5ba  or      esi, 80070000h
0x18001a5c0  cmp     qword ptr [rdi+58h], 0
0x18001a5c5  jz      loc_18001A820
0x18001a5cb  xor     ecx, ecx
0x18001a5cd  test    esi, esi
0x18001a5cf  jns     loc_18001A4FF
0x18001a5d5  mov     dword ptr [rsp+0C0h+var_98], esi
0x18001a5d9  mov     dword ptr [rsp+0C0h+var_A0], 738h
0x18001a5e1  jmp     short loc_18001A579
0x18001a5e3  mov     r8d, [rbp+57h+var_88]
0x18001a5e7  mov     rdx, [rbp+57h+hMem]
0x18001a5eb  lea     rcx, [rbp+57h+var_78]
0x18001a5ef  call    cs:__imp_UnattendCtxDeserializeBuffer
0x18001a5f5  mov     esi, eax
0x18001a5f7  test    eax, eax
0x18001a5f9  jns     short loc_18001A619
0x18001a5fb  mov     rcx, [rdi+58h]
0x18001a5ff  test    rcx, rcx
0x18001a602  jz      loc_18001A820
0x18001a608  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001a60c  mov     dword ptr [rsp+0C0h+var_A0], 73Ch
0x18001a614  jmp     loc_18001A4DC
0x18001a619  lea     r9, [rbp+57h+lpMem]
0x18001a61d  lea     r8, aCount; "Count"
0x18001a624  lea     rdx, aWimEsdEncrypte_0; "WIM\\ESD\\ENCRYPTED"
0x18001a62b  lea     rcx, [rbp+57h+var_78]
0x18001a62f  call    cs:__imp_UnattendCtxGetString
0x18001a635  mov     esi, eax
0x18001a637  test    eax, eax
0x18001a639  jns     short loc_18001A659
0x18001a63b  mov     rcx, [rdi+58h]
0x18001a63f  test    rcx, rcx
0x18001a642  jz      loc_18001A820
0x18001a648  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001a64c  mov     dword ptr [rsp+0C0h+var_A0], 73Dh
0x18001a654  jmp     loc_18001A4DC
0x18001a659  cmp     eax, 1
0x18001a65c  jnz     short loc_18001A66C
0x18001a65e  mov     dword ptr [r15], 0
0x18001a665  xor     esi, esi
0x18001a667  jmp     loc_18001A820
0x18001a66c  lea     rdx, [rbp+57h+var_84]
0x18001a670  mov     rcx, [rbp+57h+lpMem]
0x18001a674  call    ??$ConvertString2Number@H@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::ConvertString2Number<int>(ushort const *,int *)
0x18001a679  mov     esi, eax
0x18001a67b  test    eax, eax
0x18001a67d  jns     short loc_18001A69D
0x18001a67f  mov     rcx, [rdi+58h]
0x18001a683  test    rcx, rcx
0x18001a686  jz      loc_18001A820
0x18001a68c  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001a690  mov     dword ptr [rsp+0C0h+var_A0], 749h
0x18001a698  jmp     loc_18001A4DC
0x18001a69d  mov     [rbp+57h+var_80], 0
0x18001a6a4  lea     rdx, [rbp+57h+var_80]
0x18001a6a8  lea     rcx, aWimEsdEncrypte; "WIM\\ESD\\ENCRYPTED\\RANGE[*]"
0x18001a6af  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18001a6b4  mov     esi, eax
0x18001a6b6  test    eax, eax
0x18001a6b8  jns     short loc_18001A6C3
0x18001a6ba  mov     ecx, eax
0x18001a6bc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001a6c1  jmp     short loc_18001A6E7
0x18001a6c3  lea     r8, [rbp+57h+var_68]
0x18001a6c7  mov     edx, [rbp+57h+var_80]
0x18001a6ca  lea     rcx, aWimEsdEncrypte; "WIM\\ESD\\ENCRYPTED\\RANGE[*]"
0x18001a6d1  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001a6d6  mov     esi, eax
0x18001a6d8  test    eax, eax
0x18001a6da  jns     short loc_18001A6E3
0x18001a6dc  mov     ecx, eax
0x18001a6de  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001a6e3  mov     r13, [rbp+57h+var_68]
0x18001a6e7  mov     ecx, esi
0x18001a6e9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001a6ee  test    esi, esi
0x18001a6f0  jns     short loc_18001A710
0x18001a6f2  mov     rcx, [rdi+58h]
0x18001a6f6  test    rcx, rcx
0x18001a6f9  jz      loc_18001A820
0x18001a6ff  mov     dword ptr [rsp+0C0h+var_98], esi
0x18001a703  mov     dword ptr [rsp+0C0h+var_A0], 74Fh
0x18001a70b  jmp     loc_18001A4DC
0x18001a710  xor     r14d, r14d
0x18001a713  cmp     [rbp+57h+var_84], r14d
0x18001a717  jle     loc_18001A819
0x18001a71d  mov     rsi, [rbp+57h+lpMem]
0x18001a721  test    rsi, rsi
0x18001a724  jz      short loc_18001A742
0x18001a726  call    cs:__imp_GetProcessHeap
0x18001a72c  mov     rcx, rax; hHeap
0x18001a72f  mov     r8, rsi; lpMem
0x18001a732  xor     edx, edx; dwFlags
0x18001a734  call    cs:__imp_HeapFree
0x18001a73a  mov     [rbp+57h+lpMem], 0
0x18001a742  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18001a747  lea     r9, [rbp+57h+lpMem]
0x18001a74b  lea     r8, aOffset; "Offset"
0x18001a752  mov     rdx, r13
0x18001a755  lea     rcx, [rbp+57h+var_78]
0x18001a759  call    cs:__imp_UnattendCtxGetString
0x18001a75f  mov     esi, eax
0x18001a761  test    eax, eax
0x18001a763  js      loc_18001A980
0x18001a769  jnz     loc_18001A95B
0x18001a76f  lea     rdx, [rbp+57h+var_58]
0x18001a773  mov     rcx, [rbp+57h+lpMem]
0x18001a777  call    ??$ConvertString2Number@_K@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEA_K@Z; CMiscHelpersT<CEmptyType>::ConvertString2Number<unsigned __int64>(ushort const *,unsigned __int64 *)
0x18001a77c  mov     esi, eax
0x18001a77e  test    eax, eax
0x18001a780  js      loc_18001A93D
0x18001a786  mov     rsi, [rbp+57h+lpMem]
0x18001a78a  test    rsi, rsi
0x18001a78d  jz      short loc_18001A7AB
0x18001a78f  call    cs:__imp_GetProcessHeap
0x18001a795  mov     rcx, rax; hHeap
0x18001a798  mov     r8, rsi; lpMem
0x18001a79b  xor     edx, edx; dwFlags
0x18001a79d  call    cs:__imp_HeapFree
0x18001a7a3  mov     [rbp+57h+lpMem], 0
0x18001a7ab  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18001a7b0  lea     r9, [rbp+57h+lpMem]
0x18001a7b4  lea     r8, aBytes; "Bytes"
0x18001a7bb  mov     rdx, r13
0x18001a7be  lea     rcx, [rbp+57h+var_78]
0x18001a7c2  call    cs:__imp_UnattendCtxGetString
0x18001a7c8  mov     esi, eax
0x18001a7ca  test    eax, eax
0x18001a7cc  js      loc_18001A91F
0x18001a7d2  jnz     loc_18001A8FA
0x18001a7d8  lea     rdx, [rbp+57h+var_58+8]
0x18001a7dc  mov     rcx, [rbp+57h+lpMem]
0x18001a7e0  call    ??$ConvertString2Number@K@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAK@Z; CMiscHelpersT<CEmptyType>::ConvertString2Number<ulong>(ushort const *,ulong *)
0x18001a7e5  mov     esi, eax
0x18001a7e7  test    eax, eax
0x18001a7e9  js      loc_18001A8DC
0x18001a7ef  lea     rcx, [rdi+268h]
0x18001a7f6  lea     r8, [rbp+57h+var_58]
0x18001a7fa  mov     edx, [rcx+4]
0x18001a7fd  call    ?Insert@?$CArray@U_WINDLP_WIM_RANGE@@U1@VCAdaptorDefaultSpecialize@@VCPoliciesDefault@@@@QEAAJHAEBU_WINDLP_WIM_RANGE@@@Z; CArray<_WINDLP_WIM_RANGE,_WINDLP_WIM_RANGE,CAdaptorDefaultSpecialize,CPoliciesDefault>::Insert(int,_WINDLP_WIM_RANGE const &)
0x18001a802  mov     esi, eax
0x18001a804  test    eax, eax
0x18001a806  js      loc_18001A8BE
0x18001a80c  inc     r14d
0x18001a80f  cmp     r14d, [rbp+57h+var_84]
0x18001a813  jl      loc_18001A71D
0x18001a819  mov     dword ptr [r15], 1
0x18001a820  lea     rcx, [rbp+57h+var_78]
0x18001a824  call    cs:__imp_UnattendCtxCleanup
0x18001a82a  mov     ecx, esi
0x18001a82c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001a831  nop
0x18001a832  test    r13, r13
0x18001a835  jz      short loc_18001A854
0x18001a837  call    cs:__imp_GetProcessHeap
0x18001a83d  mov     rcx, rax; hHeap
0x18001a840  lea     r8, [r13-4]; lpMem
0x18001a844  xor     edx, edx; dwFlags
0x18001a846  call    cs:__imp_HeapFree
0x18001a84c  xor     ecx, ecx
0x18001a84e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001a853  nop
0x18001a854  mov     rdi, [rbp+57h+lpMem]
0x18001a858  test    rdi, rdi
0x18001a85b  jz      short loc_18001A879
0x18001a85d  call    cs:__imp_GetProcessHeap
0x18001a863  mov     rcx, rax; hHeap
0x18001a866  mov     r8, rdi; lpMem
0x18001a869  xor     edx, edx; dwFlags
0x18001a86b  call    cs:__imp_HeapFree
0x18001a871  mov     [rbp+57h+lpMem], 0
0x18001a879  mov     rcx, [rbp+57h+hMem]; hMem
0x18001a87d  test    rcx, rcx
0x18001a880  jz      short loc_18001A890
0x18001a882  call    cs:__imp_LocalFree
0x18001a888  mov     [rbp+57h+hMem], 0
0x18001a890  test    rbx, rbx
0x18001a893  jz      short loc_18001A89E
0x18001a895  mov     rcx, rbx
0x18001a898  call    cs:__imp_WIMCloseHandle
0x18001a89e  mov     eax, esi
0x18001a8a0  mov     rcx, [rbp+57h+var_40]
0x18001a8a4  xor     rcx, rsp; StackCookie
0x18001a8a7  call    __security_check_cookie
0x18001a8ac  add     rsp, 90h
0x18001a8b3  pop     r15
0x18001a8b5  pop     r14
0x18001a8b7  pop     r13
0x18001a8b9  pop     rdi
0x18001a8ba  pop     rsi
0x18001a8bb  pop     rbx
0x18001a8bc  pop     rbp
0x18001a8bd  retn
0x18001a8be  mov     rcx, [rdi+58h]
0x18001a8c2  test    rcx, rcx
0x18001a8c5  jz      loc_18001A820
0x18001a8cb  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001a8cf  mov     dword ptr [rsp+0C0h+var_A0], 762h
0x18001a8d7  jmp     loc_18001A4DC
0x18001a8dc  mov     rcx, [rdi+58h]
0x18001a8e0  test    rcx, rcx
0x18001a8e3  jz      loc_18001A820
0x18001a8e9  mov     dword ptr [rsp+0C0h+var_98], eax
0x18001a8ed  mov     dword ptr [rsp+0C0h+var_A0], 760h
0x18001a8f5  jmp     loc_18001A4DC
0x18001a8fa  mov     eax, 0C1800113h
0x18001a8ff  mov     esi, eax
0x18001a901  mov     rcx, [rdi+58h]
0x18001a905  test    rcx, rcx
0x18001a908  jz      loc_18001A820
0x18001a90e  mov     dword ptr [rsp+0C0h+var_98], eax
  ... truncated ...
```
