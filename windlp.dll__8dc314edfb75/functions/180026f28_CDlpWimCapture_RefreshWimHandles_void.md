# CDlpWimCapture::RefreshWimHandles(void)

- ea: `0x180026f28`
- end: `0x180027213`
- name: `?RefreshWimHandles@CDlpWimCapture@@AEAAJXZ`
- size: `747`
- prototype: `__int64 __fastcall(CDlpWimCapture *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800309dc`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180026f28`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x180026f3e`
- `WIMGAPI!WIMCloseHandle` at `0x180026f55`
- `WIMGAPI!WIMCloseHandle` at `0x180027018`
- `WIMGAPI!WIMCloseHandle` at `0x18002714e`
- `WIMGAPI!WIMCloseHandle` at `0x180026f3e`
- `WIMGAPI!WIMCloseHandle` at `0x180026f55`
- `WIMGAPI!WIMCloseHandle` at `0x180027018`
- `WIMGAPI!WIMCloseHandle` at `0x18002714e`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1800270b3`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1800270b3`
- `WIMGAPI!WIMSetReferenceFile` at `0x18002711e`
- `WIMGAPI!WIMSetReferenceFile` at `0x18002711e`
- `WIMGAPI!WIMLoadImage` at `0x18002713c`
- `WIMGAPI!WIMLoadImage` at `0x18002713c`
- `WIMGAPI!WIMCreateFile` at `0x180027006`
- `WIMGAPI!WIMCreateFile` at `0x180027006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027174`

## string_xrefs

- `0x18002709a`: `Wim Capture: Setting temp path to [%s]`
- `0x180026fcd`: `Wim Capture: Attempting to refresh handle to [%s]`
- `0x18002707c`: `Wim Capture: Successfully reopened WIM file.`
- `0x1800271f0`: `Wim Capture: Successfully reopened image in WIM`

## pseudocode

```c
__int64 __fastcall CDlpWimCapture::RefreshWimHandles(CDlpWimCapture *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  signed int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  signed int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  signed int v17; // eax
  int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rbx
  signed int LastError; // eax
  signed int v23; // eax
  __int64 v24; // rcx
  __int64 v26; // [rsp+20h] [rbp-18h]
  __int64 v27; // [rsp+28h] [rbp-10h]

  v2 = *((_QWORD *)this + 11);
  if ( v2 )
  {
    WIMCloseHandle(v2);
    *((_QWORD *)this + 11) = 0;
  }
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    WIMCloseHandle(v3);
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((_DWORD *)this + 9) )
  {
    v8 = *((int *)this + 9);
    v9 = *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v8 - 8);
    v10 = *((_QWORD *)this + 15);
    if ( v10 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v10,
        2u,
        (__int64)L"Wim Capture: Attempting to refresh handle to [%s]",
        *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v8 - 8));
    v11 = WIMCreateFile(v9, 3221225472LL, 3, *((unsigned int *)this + 34), *((_DWORD *)this + 32), 0);
    v12 = *((_QWORD *)this + 10);
    v13 = v11;
    if ( v12 )
      WIMCloseHandle(v12);
    if ( v13 )
    {
      *((_QWORD *)this + 10) = v13;
      v15 = *((_QWORD *)this + 15);
      if ( v15 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v15, 2u, (__int64)L"Wim Capture: Successfully reopened WIM file.");
      v16 = *((_QWORD *)this + 15);
      if ( v16 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v16,
          2u,
          (__int64)L"Wim Capture: Setting temp path to [%s]",
          *((_QWORD *)this + 9));
      if ( (unsigned int)WIMSetTemporaryPath(*((_QWORD *)this + 10), *((_QWORD *)this + 9)) )
      {
        v18 = 0;
        if ( *((_DWORD *)this + 9) == 1 )
        {
LABEL_39:
          v19 = WIMLoadImage(*((_QWORD *)this + 10), 1);
          v20 = *((_QWORD *)this + 11);
          v21 = v19;
          if ( v20 )
            WIMCloseHandle(v20);
          if ( v21 )
          {
            *((_QWORD *)this + 11) = v21;
            v5 = 0;
            v24 = *((_QWORD *)this + 15);
            if ( v24 )
              CDlpLogT<CEmptyType>::DlpLogFormat(v24, 2u, (__int64)L"Wim Capture: Successfully reopened image in WIM");
            goto LABEL_58;
          }
          *((_QWORD *)this + 11) = 0;
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v5 = -2147467259;
          }
          if ( !*((_QWORD *)this + 15) )
            goto LABEL_58;
          v7 = 0;
          if ( v5 < 0 )
          {
            LODWORD(v27) = v5;
            LODWORD(v26) = 774;
            goto LABEL_23;
          }
        }
        else
        {
          while ( (unsigned int)WIMSetReferenceFile(
                                  *((_QWORD *)this + 10),
                                  *(_QWORD *)(*((_QWORD *)this + 5) + 8LL * v18),
                                  0x10000) )
          {
            if ( ++v18 >= (unsigned int)(*((_DWORD *)this + 9) - 1) )
              goto LABEL_39;
          }
          v23 = GetLastError();
          v5 = v23;
          if ( v23 )
          {
            if ( v23 > 0 )
              v5 = (unsigned __int16)v23 | 0x80070000;
          }
          else
          {
            v5 = -2147467259;
          }
          if ( !*((_QWORD *)this + 15) )
            goto LABEL_58;
          v7 = 0;
          if ( v5 < 0 )
          {
            LODWORD(v27) = v5;
            LODWORD(v26) = 770;
            goto LABEL_23;
          }
        }
      }
      else
      {
        v17 = GetLastError();
        v5 = v17;
        if ( v17 )
        {
          if ( v17 > 0 )
            v5 = (unsigned __int16)v17 | 0x80070000;
        }
        else
        {
          v5 = -2147467259;
        }
        if ( !*((_QWORD *)this + 15) )
          goto LABEL_58;
        v7 = 0;
        if ( v5 < 0 )
        {
          LODWORD(v27) = v5;
          LODWORD(v26) = 766;
          goto LABEL_23;
        }
      }
    }
    else
    {
      *((_QWORD *)this + 10) = 0;
      v14 = GetLastError();
      v5 = v14;
      if ( v14 )
      {
        if ( v14 > 0 )
          v5 = (unsigned __int16)v14 | 0x80070000;
      }
      else
      {
        v5 = -2147467259;
      }
      if ( !*((_QWORD *)this + 15) )
        goto LABEL_58;
      v7 = 0;
      if ( v5 < 0 )
      {
        LODWORD(v27) = v5;
        LODWORD(v26) = 762;
LABEL_23:
        v4 = *((_QWORD *)this + 15);
LABEL_8:
        v6 = CDlpLogT<CEmptyType>::DlpLogFormat(
               v4,
               4u,
               (__int64)L"%s(%d): Result = 0x%X",
               L"CDlpWimCapture::RefreshWimHandles",
               v26,
               v27);
        v7 = (unsigned int)v6;
        if ( v6 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
      }
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
    goto LABEL_58;
  }
  v4 = *((_QWORD *)this + 15);
  v5 = -2147023728;
  if ( v4 )
  {
    LODWORD(v27) = -2147023728;
    LODWORD(v26) = 750;
    goto LABEL_8;
  }
LABEL_58:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180026f28  mov     [rsp+arg_0], rbx
0x180026f2d  push    rdi
0x180026f2e  sub     rsp, 30h
0x180026f32  mov     rdi, rcx
0x180026f35  mov     rcx, [rcx+58h]
0x180026f39  test    rcx, rcx
0x180026f3c  jz      short loc_180026F4C
0x180026f3e  call    cs:__imp_WIMCloseHandle
0x180026f44  mov     qword ptr [rdi+58h], 0
0x180026f4c  mov     rcx, [rdi+50h]
0x180026f50  test    rcx, rcx
0x180026f53  jz      short loc_180026F63
0x180026f55  call    cs:__imp_WIMCloseHandle
0x180026f5b  mov     qword ptr [rdi+50h], 0
0x180026f63  cmp     dword ptr [rdi+24h], 0
0x180026f67  jnz     short loc_180026FB4
0x180026f69  mov     rcx, [rdi+78h]
0x180026f6d  mov     ebx, 80070490h
0x180026f72  test    rcx, rcx
0x180026f75  jz      loc_1800271FF
0x180026f7b  mov     dword ptr [rsp+38h+var_10], ebx
0x180026f7f  mov     dword ptr [rsp+38h+var_18], 2EEh
0x180026f87  lea     r9, aCdlpwimcapture_0; "CDlpWimCapture::RefreshWimHandles"
0x180026f8e  mov     edx, 4
0x180026f93  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180026f9a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180026f9f  mov     ecx, eax
0x180026fa1  test    eax, eax
0x180026fa3  jns     short loc_180026FAA
0x180026fa5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180026faa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180026faf  jmp     loc_1800271FF
0x180026fb4  mov     rcx, [rdi+28h]
0x180026fb8  movsxd  rax, dword ptr [rdi+24h]
0x180026fbc  mov     rbx, [rcx+rax*8-8]
0x180026fc1  mov     rcx, [rdi+78h]
0x180026fc5  test    rcx, rcx
0x180026fc8  jz      short loc_180026FDE
0x180026fca  mov     r9, rbx
0x180026fcd  lea     r8, aWimCaptureAtte; "Wim Capture: Attempting to refresh hand"...
0x180026fd4  mov     edx, 2
0x180026fd9  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180026fde  mov     eax, [rdi+80h]
0x180026fe4  mov     edx, 0C0000000h
0x180026fe9  mov     r9d, [rdi+88h]
0x180026ff0  mov     r8d, 3
0x180026ff6  mov     [rsp+38h+var_10], 0
0x180026fff  mov     rcx, rbx
0x180027002  mov     dword ptr [rsp+38h+var_18], eax
0x180027006  call    cs:__imp_WIMCreateFile
0x18002700c  mov     rcx, [rdi+50h]
0x180027010  mov     rbx, rax
0x180027013  test    rcx, rcx
0x180027016  jz      short loc_18002701E
0x180027018  call    cs:__imp_WIMCloseHandle
0x18002701e  test    rbx, rbx
0x180027021  jnz     short loc_18002706F
0x180027023  mov     [rdi+50h], rbx
0x180027027  call    cs:__imp_GetLastError
0x18002702d  mov     ebx, eax
0x18002702f  test    eax, eax
0x180027031  jnz     short loc_18002703A
0x180027033  mov     ebx, 80004005h
0x180027038  jmp     short loc_180027045
0x18002703a  jle     short loc_180027045
0x18002703c  movzx   ebx, ax
0x18002703f  or      ebx, 80070000h
0x180027045  cmp     qword ptr [rdi+78h], 0
0x18002704a  jz      loc_1800271FF
0x180027050  xor     ecx, ecx
0x180027052  test    ebx, ebx
0x180027054  jns     loc_180026FAA
0x18002705a  mov     dword ptr [rsp+38h+var_10], ebx
0x18002705e  mov     dword ptr [rsp+38h+var_18], 2FAh
0x180027066  mov     rcx, [rdi+78h]
0x18002706a  jmp     loc_180026F87
0x18002706f  mov     [rdi+50h], rbx
0x180027073  mov     rcx, [rdi+78h]
0x180027077  test    rcx, rcx
0x18002707a  jz      short loc_18002708D
0x18002707c  lea     r8, aWimCaptureSucc; "Wim Capture: Successfully reopened WIM "...
0x180027083  mov     edx, 2
0x180027088  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002708d  mov     rcx, [rdi+78h]
0x180027091  test    rcx, rcx
0x180027094  jz      short loc_1800270AB
0x180027096  mov     r9, [rdi+48h]
0x18002709a  lea     r8, aWimCaptureSett; "Wim Capture: Setting temp path to [%s]"
0x1800270a1  mov     edx, 2
0x1800270a6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800270ab  mov     rdx, [rdi+48h]
0x1800270af  mov     rcx, [rdi+50h]
0x1800270b3  call    cs:__imp_WIMSetTemporaryPath
0x1800270b9  test    eax, eax
0x1800270bb  jnz     short loc_180027101
0x1800270bd  call    cs:__imp_GetLastError
0x1800270c3  mov     ebx, eax
0x1800270c5  test    eax, eax
0x1800270c7  jnz     short loc_1800270D0
0x1800270c9  mov     ebx, 80004005h
0x1800270ce  jmp     short loc_1800270DB
0x1800270d0  jle     short loc_1800270DB
0x1800270d2  movzx   ebx, ax
0x1800270d5  or      ebx, 80070000h
0x1800270db  cmp     qword ptr [rdi+78h], 0
0x1800270e0  jz      loc_1800271FF
0x1800270e6  xor     ecx, ecx
0x1800270e8  test    ebx, ebx
0x1800270ea  jns     loc_180026FAA
0x1800270f0  mov     dword ptr [rsp+38h+var_10], ebx
0x1800270f4  mov     dword ptr [rsp+38h+var_18], 2FEh
0x1800270fc  jmp     loc_180027066
0x180027101  xor     ebx, ebx
0x180027103  cmp     dword ptr [rdi+24h], 1
0x180027107  jz      short loc_180027133
0x180027109  mov     rcx, [rdi+28h]
0x18002710d  mov     r8d, 10000h
0x180027113  movsxd  rax, ebx
0x180027116  mov     rdx, [rcx+rax*8]
0x18002711a  mov     rcx, [rdi+50h]
0x18002711e  call    cs:__imp_WIMSetReferenceFile
0x180027124  test    eax, eax
0x180027126  jz      short loc_180027174
0x180027128  mov     eax, [rdi+24h]
0x18002712b  inc     ebx
0x18002712d  dec     eax
0x18002712f  cmp     ebx, eax
0x180027131  jb      short loc_180027109
0x180027133  mov     rcx, [rdi+50h]
0x180027137  mov     edx, 1
0x18002713c  call    cs:__imp_WIMLoadImage
0x180027142  mov     rcx, [rdi+58h]
0x180027146  mov     rbx, rax
0x180027149  test    rcx, rcx
0x18002714c  jz      short loc_180027154
0x18002714e  call    cs:__imp_WIMCloseHandle
0x180027154  test    rbx, rbx
0x180027157  jnz     loc_1800271E1
0x18002715d  mov     [rdi+58h], rbx
0x180027161  call    cs:__imp_GetLastError
0x180027167  mov     ebx, eax
0x180027169  test    eax, eax
0x18002716b  jnz     short loc_1800271B4
0x18002716d  mov     ebx, 80004005h
0x180027172  jmp     short loc_1800271BF
0x180027174  call    cs:__imp_GetLastError
0x18002717a  mov     ebx, eax
0x18002717c  test    eax, eax
0x18002717e  jnz     short loc_180027187
0x180027180  mov     ebx, 80004005h
0x180027185  jmp     short loc_180027192
0x180027187  jle     short loc_180027192
0x180027189  movzx   ebx, ax
0x18002718c  or      ebx, 80070000h
0x180027192  cmp     qword ptr [rdi+78h], 0
0x180027197  jz      short loc_1800271FF
0x180027199  xor     ecx, ecx
0x18002719b  test    ebx, ebx
0x18002719d  jns     loc_180026FAA
0x1800271a3  mov     dword ptr [rsp+38h+var_10], ebx
0x1800271a7  mov     dword ptr [rsp+38h+var_18], 302h
0x1800271af  jmp     loc_180027066
0x1800271b4  jle     short loc_1800271BF
0x1800271b6  movzx   ebx, ax
0x1800271b9  or      ebx, 80070000h
0x1800271bf  cmp     qword ptr [rdi+78h], 0
0x1800271c4  jz      short loc_1800271FF
0x1800271c6  xor     ecx, ecx
0x1800271c8  test    ebx, ebx
0x1800271ca  jns     loc_180026FAA
0x1800271d0  mov     dword ptr [rsp+38h+var_10], ebx
0x1800271d4  mov     dword ptr [rsp+38h+var_18], 306h
0x1800271dc  jmp     loc_180027066
0x1800271e1  mov     [rdi+58h], rbx
0x1800271e5  xor     ebx, ebx
0x1800271e7  mov     rcx, [rdi+78h]
0x1800271eb  test    rcx, rcx
0x1800271ee  jz      short loc_1800271FF
0x1800271f0  lea     r8, aWimCaptureSucc_0; "Wim Capture: Successfully reopened imag"...
0x1800271f7  lea     edx, [rbx+2]
0x1800271fa  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800271ff  mov     ecx, ebx
0x180027201  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180027206  mov     eax, ebx
0x180027208  mov     rbx, [rsp+38h+arg_0]
0x18002720d  add     rsp, 30h
0x180027211  pop     rdi
0x180027212  retn
```
