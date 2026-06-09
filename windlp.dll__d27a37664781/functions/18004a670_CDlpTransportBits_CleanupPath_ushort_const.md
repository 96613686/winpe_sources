# CDlpTransportBits::CleanupPath(ushort const *)

- ea: `0x18004a670`
- end: `0x18004ae25`
- name: `?CleanupPath@CDlpTransportBits@@UEAAJPEBG@Z`
- size: `1973`
- prototype: `__int64 __fastcall(CDlpTransportBits *__hidden this, PCNZWCH lpString2)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18003d1c4`
- `0x18004a670`
- `0x18005a960`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004a747`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004a747`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a9b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a9b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad84`

## string_xrefs

- `0x18004a79a`: `BitsTransport: Directory %s do not exist.`
- `0x18004a735`: `BitsTransport: Trying to cancel existing BITS Download Job to directory %s`
- `0x18004a7fa`: `CDlpTransportBits::CleanupPath`
- `0x18004ad33`: `CDlpTransportBits::CleanupPath`
- `0x18004ab18`: `BitsTransport: Cancelled existing BITS Download Job to directory %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CDlpTransportBits::CleanupPath(CDlpTransportBits *this, PCNZWCH lpString2)
{
  int v4; // r14d
  struct IBackgroundCopyManager *v5; // r15
  char *v6; // rbx
  __int64 (__fastcall *v7)(char *); // rax
  char *v8; // rcx
  int BitsCopyManager; // edi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  DWORD FileAttributesW; // edi
  int v14; // edi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // r13d
  int v20; // esi
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  PCNZWCH lpString2a; // [rsp+20h] [rbp-50h]
  __int64 cchCount2; // [rsp+28h] [rbp-48h]
  __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  __int64 v29; // [rsp+38h] [rbp-38h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-28h] BYREF
  __int64 v32; // [rsp+50h] [rbp-20h] BYREF
  __int64 v33; // [rsp+58h] [rbp-18h] BYREF
  struct IBackgroundCopyManager *v34; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v35; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v36; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int v37; // [rsp+C8h] [rbp+58h] BYREF

  v4 = 0;
  v5 = 0;
  v34 = 0;
  v33 = 0;
  v28 = 0;
  v29 = 0;
  v32 = 0;
  v37 = 0;
  pv = 0;
  String1 = 0;
  v36 = 0;
  v35 = 0;
  v6 = (char *)this + 168;
  v7 = *(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL);
  v8 = (char *)this + 168;
  if ( !lpString2 )
  {
    BitsCopyManager = -2147024809;
    if ( !v7(v8) )
      goto LABEL_86;
    v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
    v11 = 0;
    if ( !v10 )
      goto LABEL_85;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2a) = 957;
    goto LABEL_83;
  }
  if ( v7(v8) )
  {
    v12 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v12,
      2,
      L"BitsTransport: Trying to cancel existing BITS Download Job to directory %s",
      lpString2);
  }
  FileAttributesW = GetFileAttributesW(lpString2);
  if ( FileAttributesW == -1 )
    v14 = 0;
  else
    v14 = (FileAttributesW >> 4) & 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v14 )
  {
    BitsCopyManager = CDlpTransportBits::GetBitsCopyManager(this, &v34);
    if ( BitsCopyManager >= 0 )
    {
      v5 = v34;
      BitsCopyManager = ((__int64 (__fastcall *)(struct IBackgroundCopyManager *, _QWORD, __int64 *))v34->lpVtbl->EnumJobsA)(
                          v34,
                          0,
                          &v33);
      if ( BitsCopyManager >= 0 )
      {
        BitsCopyManager = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 56LL))(v33, &v36);
        if ( BitsCopyManager >= 0 )
        {
          v19 = 0;
          if ( !v36 )
            goto LABEL_86;
          while ( 1 )
          {
            if ( v28 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
              v28 = 0;
            }
            BitsCopyManager = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 24LL))(
                                v33,
                                1,
                                &v28);
            if ( BitsCopyManager < 0 )
              break;
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            BitsCopyManager = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v28 + 144LL))(v28, &pv);
            if ( BitsCopyManager < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
                goto LABEL_86;
              v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
              v11 = 0;
              if ( v10 )
              {
                LODWORD(cchCount2) = BitsCopyManager;
                LODWORD(lpString2a) = 978;
                goto LABEL_83;
              }
              goto LABEL_85;
            }
            BitsCopyManager = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 112LL))(v28, &v37);
            if ( BitsCopyManager < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
                goto LABEL_86;
              v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
              v11 = 0;
              if ( v10 )
              {
                LODWORD(cchCount2) = BitsCopyManager;
                LODWORD(lpString2a) = 979;
                goto LABEL_83;
              }
              goto LABEL_85;
            }
            if ( CompareStringW(0x409u, 1u, (PCNZWCH)pv, -1, L"Windows Dlp Manager", -1) == 2 && v37 <= 3 )
            {
              if ( v29 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                v29 = 0;
              }
              BitsCopyManager = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 40LL))(v28, &v29);
              if ( BitsCopyManager < 0 )
              {
                if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
                  goto LABEL_86;
                v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
                v11 = 0;
                if ( v10 )
                {
                  LODWORD(cchCount2) = BitsCopyManager;
                  LODWORD(lpString2a) = 992;
                  goto LABEL_83;
                }
                goto LABEL_85;
              }
              BitsCopyManager = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v29 + 56LL))(v29, &v35);
              if ( BitsCopyManager < 0 )
              {
                if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
                  goto LABEL_86;
                v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
                v11 = 0;
                if ( v10 )
                {
                  LODWORD(cchCount2) = BitsCopyManager;
                  LODWORD(lpString2a) = 993;
                  goto LABEL_83;
                }
                goto LABEL_85;
              }
              v20 = 1;
              if ( v35 )
              {
                while ( 1 )
                {
                  if ( v32 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                    v32 = 0;
                  }
                  BitsCopyManager = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v29 + 24LL))(
                                      v29,
                                      1,
                                      &v32);
                  if ( BitsCopyManager < 0 )
                    break;
                  if ( String1 )
                  {
                    CoTaskMemFree(String1);
                    String1 = 0;
                  }
                  BitsCopyManager = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v32 + 32LL))(
                                      v32,
                                      &String1);
                  if ( BitsCopyManager < 0 )
                  {
                    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
                      goto LABEL_86;
                    v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
                    v11 = 0;
                    if ( v10 )
                    {
                      LODWORD(cchCount2) = BitsCopyManager;
                      LODWORD(lpString2a) = 1001;
                      goto LABEL_83;
                    }
                    goto LABEL_85;
                  }
                  v21 = (unsigned int)WdsIsPathInsideFolder(String1, lpString2) != 0 ? v20 : 0;
                  v20 = v21;
                  if ( ++v4 >= v35 )
                  {
                    v4 = 0;
                    if ( !v21 )
                      goto LABEL_57;
                    goto LABEL_54;
                  }
                }
                if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
                  goto LABEL_86;
                v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
                v11 = 0;
                if ( v10 )
                {
                  LODWORD(cchCount2) = BitsCopyManager;
                  LODWORD(lpString2a) = 998;
                  goto LABEL_83;
                }
                goto LABEL_85;
              }
              v4 = 0;
LABEL_54:
              BitsCopyManager = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 64LL))(v28);
              v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
              if ( BitsCopyManager < 0 )
              {
                if ( !v22 )
                  goto LABEL_86;
                v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
                v11 = 0;
                if ( v10 )
                {
                  LODWORD(cchCount2) = BitsCopyManager;
                  LODWORD(lpString2a) = 1014;
                  goto LABEL_83;
                }
                goto LABEL_85;
              }
              if ( v22 )
              {
                v23 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
                CDlpLogT<CEmptyType>::DlpLogFormat(
                  v23,
                  2,
                  L"BitsTransport: Cancelled existing BITS Download Job to directory %s",
                  lpString2);
              }
            }
LABEL_57:
            if ( ++v19 >= v36 )
              goto LABEL_86;
          }
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
            goto LABEL_86;
          v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
          v11 = 0;
          if ( v10 )
          {
            LODWORD(cchCount2) = BitsCopyManager;
            LODWORD(lpString2a) = 975;
            goto LABEL_83;
          }
          goto LABEL_85;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
          goto LABEL_86;
        v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
        v11 = 0;
        if ( !v10 )
        {
LABEL_85:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
          goto LABEL_86;
        }
        LODWORD(cchCount2) = BitsCopyManager;
        LODWORD(lpString2a) = 971;
      }
      else
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
          goto LABEL_86;
        v10 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
        v11 = 0;
        if ( !v10 )
          goto LABEL_85;
        LODWORD(cchCount2) = BitsCopyManager;
        LODWORD(lpString2a) = 969;
      }
LABEL_83:
      v24 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v10,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpTransportBits::CleanupPath",
              lpString2a,
              cchCount2);
      v11 = (unsigned int)v24;
      if ( v24 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v24);
      goto LABEL_85;
    }
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
    {
      v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      v17 = 0;
      if ( v16 )
      {
        v18 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v16,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpTransportBits::CleanupPath",
                968,
                BitsCopyManager);
        v17 = (unsigned int)v18;
        if ( v18 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v18);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
    }
    v5 = v34;
  }
  else
  {
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
    {
      v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      CDlpLogT<CEmptyType>::DlpLogFormat(v15, 2, L"BitsTransport: Directory %s do not exist.", lpString2);
    }
    BitsCopyManager = 0;
  }
LABEL_86:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsCopyManager);
  if ( String1 )
  {
    CoTaskMemFree(String1);
    String1 = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v5 )
    ((void (__fastcall *)(struct IBackgroundCopyManager *))v5->lpVtbl->Release)(v5);
  return (unsigned int)BitsCopyManager;
}

```

## disassembly

```asm
0x18004a670  mov     [rsp-38h+arg_0], rbx
0x18004a675  push    rbp
0x18004a676  push    rsi
0x18004a677  push    rdi
0x18004a678  push    r12
0x18004a67a  push    r13
0x18004a67c  push    r14
0x18004a67e  push    r15
0x18004a680  mov     rbp, rsp
0x18004a683  sub     rsp, 70h
0x18004a687  mov     r12, rdx
0x18004a68a  mov     rsi, rcx
0x18004a68d  xor     r14d, r14d
0x18004a690  mov     r15d, r14d
0x18004a693  mov     [rbp+var_10], r14
0x18004a697  mov     [rbp+var_18], r14
0x18004a69b  mov     [rbp+var_40], r14
0x18004a69f  mov     [rbp+var_38], r14
0x18004a6a3  mov     [rbp+var_20], r14
0x18004a6a7  mov     [rbp+arg_18], r14d
0x18004a6ab  mov     [rbp+pv], r14
0x18004a6af  mov     [rbp+String1], r14
0x18004a6b3  mov     [rbp+arg_10], r14d
0x18004a6b7  mov     [rbp+arg_8], r14d
0x18004a6bb  lea     rbx, [rcx+0A8h]
0x18004a6c2  mov     rax, [rbx]
0x18004a6c5  mov     rax, [rax+10h]
0x18004a6c9  mov     rcx, rbx
0x18004a6cc  test    rdx, rdx
0x18004a6cf  jnz     short loc_18004A710
0x18004a6d1  mov     edi, 80070057h
0x18004a6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6db  test    rax, rax
0x18004a6de  jz      loc_18004AD5E
0x18004a6e4  mov     rax, [rbx]
0x18004a6e7  mov     rcx, rbx
0x18004a6ea  mov     rax, [rax+10h]
0x18004a6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6f3  mov     ecx, r14d
0x18004a6f6  test    rax, rax
0x18004a6f9  jz      loc_18004AD59
0x18004a6ff  mov     dword ptr [rsp+70h+cchCount2], edi
0x18004a703  mov     dword ptr [rsp+70h+lpString2], 3BDh
0x18004a70b  jmp     loc_18004AD33
0x18004a710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a715  mov     r13d, 2
0x18004a71b  test    rax, rax
0x18004a71e  jz      short loc_18004A744
0x18004a720  mov     rax, [rbx]
0x18004a723  mov     rcx, rbx
0x18004a726  mov     rax, [rax+10h]
0x18004a72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a72f  mov     rcx, rax
0x18004a732  mov     r9, r12
0x18004a735  lea     r8, aBitstransportT; "BitsTransport: Trying to cancel existin"...
0x18004a73c  mov     edx, r13d
0x18004a73f  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004a744  mov     rcx, r12; lpFileName
0x18004a747  call    cs:__imp_GetFileAttributesW
0x18004a74d  mov     edi, eax
0x18004a74f  cmp     eax, 0FFFFFFFFh
0x18004a752  jz      short loc_18004A75C
0x18004a754  shr     edi, 4
0x18004a757  and     edi, 1
0x18004a75a  jmp     short loc_18004A75F
0x18004a75c  mov     edi, r14d
0x18004a75f  xor     ecx, ecx
0x18004a761  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004a766  xor     ecx, ecx
0x18004a768  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004a76d  test    edi, edi
0x18004a76f  jnz     short loc_18004A7B1
0x18004a771  mov     rax, [rbx]
0x18004a774  mov     rcx, rbx
0x18004a777  mov     rax, [rax+10h]
0x18004a77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a780  test    rax, rax
0x18004a783  jz      short loc_18004A7A9
0x18004a785  mov     rax, [rbx]
0x18004a788  mov     rcx, rbx
0x18004a78b  mov     rax, [rax+10h]
0x18004a78f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a794  mov     rcx, rax
0x18004a797  mov     r9, r12
0x18004a79a  lea     r8, aBitstransportD; "BitsTransport: Directory %s do not exis"...
0x18004a7a1  mov     edx, r13d
0x18004a7a4  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004a7a9  mov     edi, r14d
0x18004a7ac  jmp     loc_18004AD5E
0x18004a7b1  lea     rdx, [rbp+var_10]; struct IBackgroundCopyManager **
0x18004a7b5  mov     rcx, rsi; this
0x18004a7b8  call    ?GetBitsCopyManager@CDlpTransportBits@@AEAAJPEAPEAUIBackgroundCopyManager@@@Z; CDlpTransportBits::GetBitsCopyManager(IBackgroundCopyManager * *)
0x18004a7bd  mov     edi, eax
0x18004a7bf  test    eax, eax
0x18004a7c1  jns     short loc_18004A82E
0x18004a7c3  mov     rcx, [rbx]
0x18004a7c6  mov     rax, [rcx+10h]
0x18004a7ca  mov     rcx, rbx
0x18004a7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7d2  test    rax, rax
0x18004a7d5  jz      short loc_18004A825
0x18004a7d7  mov     rcx, [rbx]
0x18004a7da  mov     rax, [rcx+10h]
0x18004a7de  mov     rcx, rbx
0x18004a7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7e6  mov     ecx, r14d
0x18004a7e9  test    rax, rax
0x18004a7ec  jz      short loc_18004A820
0x18004a7ee  mov     dword ptr [rsp+70h+cchCount2], edi
0x18004a7f2  mov     dword ptr [rsp+70h+lpString2], 3C8h
0x18004a7fa  lea     r9, aCdlptransportb_26; "CDlpTransportBits::CleanupPath"
0x18004a801  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004a808  mov     edx, 4
0x18004a80d  mov     rcx, rax
0x18004a810  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004a815  mov     ecx, eax
0x18004a817  test    eax, eax
0x18004a819  jns     short loc_18004A820
0x18004a81b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004a820  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004a825  mov     r15, [rbp+var_10]
0x18004a829  jmp     loc_18004AD5E
0x18004a82e  mov     r15, [rbp+var_10]
0x18004a832  mov     rax, [r15]
0x18004a835  lea     r8, [rbp+var_18]
0x18004a839  xor     edx, edx
0x18004a83b  mov     rcx, r15
0x18004a83e  mov     rax, [rax+28h]
0x18004a842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a847  mov     edi, eax
0x18004a849  test    eax, eax
0x18004a84b  jns     short loc_18004A891
0x18004a84d  mov     rax, [rbx]
0x18004a850  mov     rcx, rbx
0x18004a853  mov     rax, [rax+10h]
0x18004a857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a85c  test    rax, rax
0x18004a85f  jz      loc_18004AD5E
0x18004a865  mov     rax, [rbx]
0x18004a868  mov     rcx, rbx
0x18004a86b  mov     rax, [rax+10h]
0x18004a86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a874  mov     ecx, r14d
0x18004a877  test    rax, rax
0x18004a87a  jz      loc_18004AD59
0x18004a880  mov     dword ptr [rsp+70h+cchCount2], edi
0x18004a884  mov     dword ptr [rsp+70h+lpString2], 3C9h
0x18004a88c  jmp     loc_18004AD33
0x18004a891  mov     rcx, [rbp+var_18]
0x18004a895  mov     rax, [rcx]
0x18004a898  lea     rdx, [rbp+arg_10]
0x18004a89c  mov     rax, [rax+38h]
0x18004a8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8a5  mov     edi, eax
0x18004a8a7  test    eax, eax
0x18004a8a9  jns     short loc_18004A8EF
0x18004a8ab  mov     rax, [rbx]
0x18004a8ae  mov     rcx, rbx
0x18004a8b1  mov     rax, [rax+10h]
0x18004a8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8ba  test    rax, rax
0x18004a8bd  jz      loc_18004AD5E
0x18004a8c3  mov     rax, [rbx]
0x18004a8c6  mov     rcx, rbx
0x18004a8c9  mov     rax, [rax+10h]
0x18004a8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8d2  mov     ecx, r14d
0x18004a8d5  test    rax, rax
0x18004a8d8  jz      loc_18004AD59
0x18004a8de  mov     dword ptr [rsp+70h+cchCount2], edi
0x18004a8e2  mov     dword ptr [rsp+70h+lpString2], 3CBh
0x18004a8ea  jmp     loc_18004AD33
0x18004a8ef  mov     r13d, r14d
0x18004a8f2  cmp     [rbp+arg_10], r14d
0x18004a8f6  jbe     loc_18004AD5E
0x18004a8fc  mov     rcx, [rbp+var_40]
0x18004a900  test    rcx, rcx
0x18004a903  jz      short loc_18004A916
0x18004a905  mov     rax, [rcx]
0x18004a908  mov     rax, [rax+10h]
0x18004a90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a911  nop
0x18004a912  mov     [rbp+var_40], r14
0x18004a916  mov     rcx, [rbp+var_18]
0x18004a91a  mov     rax, [rcx]
0x18004a91d  xor     r9d, r9d
0x18004a920  lea     r8, [rbp+var_40]
0x18004a924  lea     edx, [r9+1]
0x18004a928  mov     rax, [rax+18h]
0x18004a92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a931  mov     edi, eax
0x18004a933  test    eax, eax
0x18004a935  js      loc_18004ACFC
0x18004a93b  mov     rcx, [rbp+pv]; pv
0x18004a93f  test    rcx, rcx
0x18004a942  jz      short loc_18004A94E
0x18004a944  call    cs:__imp_CoTaskMemFree
0x18004a94a  mov     [rbp+pv], r14
0x18004a94e  mov     rcx, [rbp+var_40]
0x18004a952  mov     rax, [rcx]
0x18004a955  lea     rdx, [rbp+pv]
0x18004a959  mov     rax, [rax+90h]
0x18004a960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a965  mov     edi, eax
0x18004a967  test    eax, eax
0x18004a969  js      loc_18004ACBF
0x18004a96f  mov     rcx, [rbp+var_40]
0x18004a973  mov     rax, [rcx]
0x18004a976  lea     rdx, [rbp+arg_18]
0x18004a97a  mov     rax, [rax+70h]
0x18004a97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a983  mov     edi, eax
0x18004a985  test    eax, eax
0x18004a987  js      loc_18004AC7E
0x18004a98d  mov     dword ptr [rsp+70h+cchCount2], 0FFFFFFFFh; cchCount2
0x18004a995  lea     rax, pszAgentW; "Windows Dlp Manager"
0x18004a99c  mov     [rsp+70h+lpString2], rax; lpString2
0x18004a9a1  or      r9d, 0FFFFFFFFh; cchCount1
0x18004a9a5  mov     r8, [rbp+pv]; lpString1
0x18004a9a9  lea     edx, [r9+2]; dwCmpFlags
0x18004a9ad  mov     ecx, 409h; Locale
0x18004a9b2  call    cs:__imp_CompareStringW
0x18004a9b8  cmp     eax, 2
0x18004a9bb  jnz     loc_18004AB29
0x18004a9c1  cmp     [rbp+arg_18], 3
0x18004a9c5  ja      loc_18004AB29
0x18004a9cb  mov     rcx, [rbp+var_38]
0x18004a9cf  test    rcx, rcx
0x18004a9d2  jz      short loc_18004A9E5
0x18004a9d4  mov     rax, [rcx]
0x18004a9d7  mov     rax, [rax+10h]
0x18004a9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9e0  nop
0x18004a9e1  mov     [rbp+var_38], r14
0x18004a9e5  mov     rcx, [rbp+var_40]
0x18004a9e9  mov     rax, [rcx]
0x18004a9ec  lea     rdx, [rbp+var_38]
0x18004a9f0  mov     rax, [rax+28h]
0x18004a9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9f9  mov     edi, eax
0x18004a9fb  test    eax, eax
0x18004a9fd  js      loc_18004AC3A
0x18004aa03  mov     rcx, [rbp+var_38]
0x18004aa07  mov     rax, [rcx]
0x18004aa0a  lea     rdx, [rbp+arg_8]
0x18004aa0e  mov     rax, [rax+38h]
0x18004aa12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa17  mov     edi, eax
0x18004aa19  test    eax, eax
0x18004aa1b  js      loc_18004ABF6
0x18004aa21  mov     esi, 1
0x18004aa26  cmp     [rbp+arg_8], 0
0x18004aa2a  jbe     loc_18004AAD2
0x18004aa30  mov     rcx, [rbp+var_20]
0x18004aa34  test    rcx, rcx
0x18004aa37  jz      short loc_18004AA4E
0x18004aa39  mov     rax, [rcx]
0x18004aa3c  mov     rax, [rax+10h]
0x18004aa40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa45  nop
0x18004aa46  mov     [rbp+var_20], 0
0x18004aa4e  mov     rcx, [rbp+var_38]
0x18004aa52  mov     rax, [rcx]
0x18004aa55  xor     r9d, r9d
0x18004aa58  lea     r8, [rbp+var_20]
0x18004aa5c  lea     edx, [r9+1]
0x18004aa60  mov     rax, [rax+18h]
0x18004aa64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa69  mov     edi, eax
0x18004aa6b  test    eax, eax
0x18004aa6d  js      loc_18004AB7E
0x18004aa73  mov     rcx, [rbp+String1]; pv
0x18004aa77  test    rcx, rcx
0x18004aa7a  jz      short loc_18004AA8A
0x18004aa7c  call    cs:__imp_CoTaskMemFree
0x18004aa82  mov     [rbp+String1], 0
0x18004aa8a  mov     rcx, [rbp+var_20]
0x18004aa8e  mov     rax, [rcx]
0x18004aa91  lea     rdx, [rbp+String1]
0x18004aa95  mov     rax, [rax+20h]
0x18004aa99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa9e  mov     edi, eax
0x18004aaa0  test    eax, eax
0x18004aaa2  js      loc_18004AB3B
0x18004aaa8  mov     rdx, r12; lpString2
0x18004aaab  mov     rcx, [rbp+String1]; String1
0x18004aaaf  call    WdsIsPathInsideFolder
0x18004aab4  neg     eax
0x18004aab6  sbb     ecx, ecx
0x18004aab8  and     ecx, esi
0x18004aaba  mov     esi, ecx
0x18004aabc  inc     r14d
0x18004aabf  cmp     r14d, [rbp+arg_8]
0x18004aac3  jb      loc_18004AA30
0x18004aac9  xor     r14d, r14d
0x18004aacc  test    ecx, ecx
0x18004aace  jz      short loc_18004AB29
0x18004aad0  jmp     short loc_18004AAD5
0x18004aad2  xor     r14d, r14d
0x18004aad5  mov     rcx, [rbp+var_40]
  ... truncated ...
```
