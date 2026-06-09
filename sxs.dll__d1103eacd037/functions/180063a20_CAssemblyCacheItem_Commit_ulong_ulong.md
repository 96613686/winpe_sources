# CAssemblyCacheItem::Commit(ulong,ulong *)

- ea: `0x180063a20`
- end: `0x180063c13`
- name: `?Commit@CAssemblyCacheItem@@UEAAJKPEAK@Z`
- size: `499`
- prototype: `__int64 __fastcall(CAssemblyCacheItem *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x18002ff90`
- `0x18005cc58`
- `0x18005d2b0`
- `0x18005f1f0`
- `0x180063a20`
- `0x1800683a4`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063b4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063b4f`

## string_xrefs

- `0x180063bca`: `SXS.DLL: SxspDeleteDirectory returns FALSE\n`
- `0x180063a9d`: `CAssemblyCacheItem::Commit`
- `0x180063b23`: `CAssemblyCacheItem::Commit`
- `0x180063ba5`: `CAssemblyCacheItem::Commit`
- `0x180063b90`: `SXS: %s - setting disposition to IASSEMBLYCACHEITEM_COMMIT_DISPOSITION_REFRESHED\n`
- `0x180063b9e`: `SXS: %s - setting disposition to IASSEMBLYCACHEITEM_COMMIT_DISPOSITION_INSTALLED\n`
- `0x180063b2f`: `SXS: %s - setting disposition to IASSEMBLYCACHEITEM_COMMIT_DISPOSITION_ALREADY_INSTALLED\n`

## pseudocode

```c
__int64 __fastcall CAssemblyCacheItem::Commit(CAssemblyCacheItem *this, int a2, unsigned int *a3)
{
  const char *v6; // rcx
  _WORD *v7; // rax
  unsigned int v8; // edi
  unsigned int v9; // ebx
  int v11; // [rsp+30h] [rbp-49h] BYREF
  __int128 v12; // [rsp+34h] [rbp-45h]
  __int128 v13; // [rsp+44h] [rbp-35h]
  __int128 v14; // [rsp+54h] [rbp-25h]
  int v15; // [rsp+64h] [rbp-15h]
  unsigned int v16; // [rsp+68h] [rbp-11h] BYREF
  int v17; // [rsp+70h] [rbp-9h] BYREF
  __int64 v18; // [rsp+78h] [rbp-1h]
  __int64 *v19; // [rsp+80h] [rbp+7h]
  __int64 v20; // [rsp+88h] [rbp+Fh]
  int v21; // [rsp+90h] [rbp+17h]
  unsigned int *v22; // [rsp+98h] [rbp+1Fh]

  v17 = 1;
  v19 = &qword_1800772E0;
  v20 = 544438355;
  v22 = &v16;
  v16 = 0;
  v18 = 0;
  v21 = 199;
  CFrame::BaseEnter((CFrame *)&v17);
  v11 = 56;
  v15 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  FusionpDbgPrintEx(
    0x80400000,
    "SXS: %s called:\n   dwFlags = 0x%08lx\n   pulDisposition = %p\n",
    "CAssemblyCacheItem::Commit",
    a2,
    a3);
  if ( a3 )
    *a3 = 0;
  if ( (a2 & 0xFFFFFFFE) != 0 )
  {
    v21 = 216;
LABEL_5:
    FusionpTraceParameterCheck(v6);
    *v22 = -2147024809;
    goto LABEL_25;
  }
  if ( !*((_DWORD *)this + 4) )
  {
    v21 = 219;
    goto LABEL_5;
  }
  v7 = (_WORD *)*((_QWORD *)this + 97);
  if ( *v7 )
  {
    if ( !*((_DWORD *)this + 3) || (a2 & 1) != 0 )
    {
      LODWORD(v12) = 0x20000;
      *(_QWORD *)((char *)&v12 + 4) = v7;
      SetLastError(0);
      if ( !(unsigned int)SxsInstallW(&v11) )
      {
        CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v17);
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800772C0);
        goto LABEL_25;
      }
      if ( (a2 & 1) != 0 && *((_DWORD *)this + 3) )
      {
        v8 = 2;
        FusionpDbgPrintEx(
          0x80400000,
          "SXS: %s - setting disposition to IASSEMBLYCACHEITEM_COMMIT_DISPOSITION_REFRESHED\n",
          "CAssemblyCacheItem::Commit");
      }
      else
      {
        v8 = 1;
        FusionpDbgPrintEx(
          0x80400000,
          "SXS: %s - setting disposition to IASSEMBLYCACHEITEM_COMMIT_DISPOSITION_INSTALLED\n",
          "CAssemblyCacheItem::Commit");
      }
      *((_DWORD *)this + 3) = 1;
    }
    else
    {
      FusionpDbgPrintEx(
        0x80400000,
        "SXS: %s - setting disposition to IASSEMBLYCACHEITEM_COMMIT_DISPOSITION_ALREADY_INSTALLED\n",
        "CAssemblyCacheItem::Commit");
      v8 = 3;
    }
    if ( !(unsigned int)SxspDeleteDirectory((char *)this + 32) )
      FusionpDbgPrintEx(0xC0000000, "SXS.DLL: SxspDeleteDirectory returns FALSE\n");
    *((_DWORD *)this + 5) = 0;
    if ( a3 )
      *a3 = v8;
    v16 = 0;
  }
  else
  {
    *v22 = -2147023537;
  }
LABEL_25:
  v9 = v16;
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v17);
  return v9;
}

```

## disassembly

```asm
0x180063a20  push    rbp
0x180063a22  push    rbx
0x180063a23  push    rsi
0x180063a24  push    rdi
0x180063a25  push    r14
0x180063a27  lea     rbp, [rsp-37h]
0x180063a2c  sub     rsp, 0B0h
0x180063a33  mov     rax, cs:__security_cookie
0x180063a3a  xor     rax, rsp
0x180063a3d  mov     [rbp+57h+var_30], rax
0x180063a41  lea     rax, qword_1800772E0
0x180063a48  mov     [rbp+57h+var_60], 1
0x180063a4f  mov     [rbp+57h+var_50], rax
0x180063a53  mov     rbx, rcx
0x180063a56  lea     rax, [rbp+57h+var_68]
0x180063a5a  mov     [rbp+57h+var_48], 20737853h
0x180063a62  xor     r14d, r14d
0x180063a65  mov     [rbp+57h+var_38], rax
0x180063a69  lea     rcx, [rbp+57h+var_60]; this
0x180063a6d  mov     [rbp+57h+var_68], r14d
0x180063a71  mov     rsi, r8
0x180063a74  mov     [rbp+57h+var_58], r14
0x180063a78  mov     edi, edx
0x180063a7a  mov     [rbp+57h+var_40], 0C7h
0x180063a81  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180063a86  xorps   xmm0, xmm0
0x180063a89  mov     [rbp+57h+var_A0], 38h ; '8'
0x180063a90  xor     eax, eax
0x180063a92  mov     [rsp+0D0h+var_B0], rsi
0x180063a97  mov     r9d, edi
0x180063a9a  mov     [rbp+57h+var_6C], eax
0x180063a9d  lea     r8, aCassemblycache_4; "CAssemblyCacheItem::Commit"
0x180063aa4  mov     ecx, 80400000h; unsigned int
0x180063aa9  lea     rdx, aSxsSCalledDwfl; "SXS: %s called:\n   dwFlags = 0x%08lx\n"...
0x180063ab0  movups  [rbp+57h+var_9C], xmm0
0x180063ab4  movups  [rbp+57h+var_8C], xmm0
0x180063ab8  movups  [rbp+57h+var_7C], xmm0
0x180063abc  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180063ac1  test    rsi, rsi
0x180063ac4  jz      short loc_180063AC9
0x180063ac6  mov     [rsi], r14d
0x180063ac9  test    edi, 0FFFFFFFEh
0x180063acf  jz      short loc_180063AEC
0x180063ad1  mov     [rbp+57h+var_40], 0D8h
0x180063ad8  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180063add  mov     rax, [rbp+57h+var_38]
0x180063ae1  mov     dword ptr [rax], 80070057h
0x180063ae7  jmp     loc_180063BEA
0x180063aec  cmp     [rbx+10h], r14d
0x180063af0  jnz     short loc_180063AFB
0x180063af2  mov     [rbp+57h+var_40], 0DBh
0x180063af9  jmp     short loc_180063AD8
0x180063afb  mov     rax, [rbx+308h]
0x180063b02  cmp     [rax], r14w
0x180063b06  jnz     short loc_180063B17
0x180063b08  mov     rax, [rbp+57h+var_38]
0x180063b0c  mov     dword ptr [rax], 8007054Fh
0x180063b12  jmp     loc_180063BEA
0x180063b17  cmp     [rbx+0Ch], r14d
0x180063b1b  jz      short loc_180063B42
0x180063b1d  test    dil, 1
0x180063b21  jnz     short loc_180063B42
0x180063b23  lea     r8, aCassemblycache_4; "CAssemblyCacheItem::Commit"
0x180063b2a  mov     ecx, 80400000h; unsigned int
0x180063b2f  lea     rdx, aSxsSSettingDis_1; "SXS: %s - setting disposition to IASSEM"...
0x180063b36  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180063b3b  mov     edi, 3
0x180063b40  jmp     short loc_180063BBD
0x180063b42  xor     ecx, ecx; dwErrCode
0x180063b44  mov     dword ptr [rbp+57h+var_9C], 20000h
0x180063b4b  mov     qword ptr [rbp+57h+var_9C+4], rax
0x180063b4f  call    cs:__imp_SetLastError
0x180063b56  nop     dword ptr [rax+rax+00h]
0x180063b5b  lea     rcx, [rbp+57h+var_A0]
0x180063b5f  call    SxsInstallW
0x180063b64  test    eax, eax
0x180063b66  jnz     short loc_180063B7F
0x180063b68  lea     rcx, [rbp+57h+var_60]; this
0x180063b6c  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180063b71  lea     rcx, off_1800772C0; struct _CALL_SITE_INFO *
0x180063b78  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180063b7d  jmp     short loc_180063BEA
0x180063b7f  test    dil, 1
0x180063b83  jz      short loc_180063B99
0x180063b85  cmp     [rbx+0Ch], r14d
0x180063b89  jz      short loc_180063B99
0x180063b8b  mov     edi, 2
0x180063b90  lea     rdx, aSxsSSettingDis; "SXS: %s - setting disposition to IASSEM"...
0x180063b97  jmp     short loc_180063BA5
0x180063b99  mov     edi, 1
0x180063b9e  lea     rdx, aSxsSSettingDis_0; "SXS: %s - setting disposition to IASSEM"...
0x180063ba5  lea     r8, aCassemblycache_4; "CAssemblyCacheItem::Commit"
0x180063bac  mov     ecx, 80400000h; unsigned int
0x180063bb1  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180063bb6  mov     dword ptr [rbx+0Ch], 1
0x180063bbd  lea     rcx, [rbx+20h]
0x180063bc1  call    ?SxspDeleteDirectory@@YAHAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspDeleteDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x180063bc6  test    eax, eax
0x180063bc8  jnz     short loc_180063BDB
0x180063bca  lea     rdx, aSxsDllSxspdele; "SXS.DLL: SxspDeleteDirectory returns FA"...
0x180063bd1  mov     ecx, 0C0000000h; unsigned int
0x180063bd6  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180063bdb  mov     [rbx+14h], r14d
0x180063bdf  test    rsi, rsi
0x180063be2  jz      short loc_180063BE6
0x180063be4  mov     [rsi], edi
0x180063be6  mov     [rbp+57h+var_68], r14d
0x180063bea  mov     ebx, [rbp+57h+var_68]
0x180063bed  lea     rcx, [rbp+57h+var_60]; this
0x180063bf1  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x180063bf6  mov     eax, ebx
0x180063bf8  mov     rcx, [rbp+57h+var_30]
0x180063bfc  xor     rcx, rsp; StackCookie
0x180063bff  call    __security_check_cookie
0x180063c04  add     rsp, 0B0h
0x180063c0b  pop     r14
0x180063c0d  pop     rdi
0x180063c0e  pop     rsi
0x180063c0f  pop     rbx
0x180063c10  pop     rbp
0x180063c11  retn
```
