# CSdController::_AddAppDataPathsToEngine(ISdBackup2 *,_UserProfileData *)

- ea: `0x180010980`
- end: `0x180010b45`
- name: `?_AddAppDataPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@PEAU_UserProfileData@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(CSdController *this, struct ISdBackup2 *, struct _UserProfileData *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011224`

## callees

- `0x180010980`
- `0x18001586c`
- `0x180015974`
- `0x180018f6c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010b28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010ab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010b28`

## string_xrefs

- `0x1800109a0`: `CSdController::_AddAppDataPathsToEngine`

## pseudocode

```c
__int64 __fastcall CSdController::_AddAppDataPathsToEngine(
        CSdController *this,
        struct ISdBackup2 *a2,
        struct _UserProfileData *a3)
{
  __int16 v5; // ax
  int ShellPath; // ebx
  void *v7; // rdi
  int v9; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]
  __int16 v11; // [rsp+26h] [rbp-42h]
  LPVOID pv; // [rsp+90h] [rbp+28h] BYREF

  pv = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CSdController::_AddAppDataPathsToEngine", 859, 0);
  pv = 0;
  v5 = 863;
  if ( !a2 || (v10 = 863, v5 = 864, !a3) )
  {
    ShellPath = -2147024809;
    v9 = -2147024809;
LABEL_3:
    v11 = v5;
    goto LABEL_17;
  }
  v9 = 0;
  v10 = 864;
  ShellPath = GetShellPath(a3, L"AppData", (unsigned __int16 **)&pv);
  v9 = ShellPath;
  v5 = 866;
  if ( ShellPath < 0 )
    goto LABEL_3;
  v10 = 866;
  ShellPath = (*(__int64 (__fastcall **)(struct ISdBackup2 *, LPVOID, __int64))(*(_QWORD *)a2 + 32LL))(
                a2,
                pv,
                3221225839LL);
  v9 = ShellPath;
  v5 = 867;
  if ( ShellPath < 0 )
    goto LABEL_3;
  v10 = 867;
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  ShellPath = GetShellPath(a3, L"Local AppData", (unsigned __int16 **)&pv);
  v9 = ShellPath;
  v5 = 870;
  if ( ShellPath < 0 )
    goto LABEL_3;
  v10 = 870;
  ShellPath = (*(__int64 (__fastcall **)(struct ISdBackup2 *, LPVOID, __int64))(*(_QWORD *)a2 + 32LL))(
                a2,
                pv,
                3221225839LL);
  v9 = ShellPath;
  v5 = 871;
  if ( ShellPath < 0 )
    goto LABEL_3;
  v10 = 871;
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  ShellPath = GetShellPath(a3, L"{A520A1A4-1780-4FF6-BD18-167343C5AF16}", (unsigned __int16 **)&pv);
  v9 = ShellPath;
  v5 = 874;
  if ( ShellPath < 0 )
    goto LABEL_3;
  v7 = pv;
  v10 = 874;
  ShellPath = (*(__int64 (__fastcall **)(struct ISdBackup2 *, LPVOID, __int64))(*(_QWORD *)a2 + 32LL))(
                a2,
                pv,
                3221225839LL);
  v9 = ShellPath;
  v5 = 875;
  if ( ShellPath < 0 )
    goto LABEL_3;
  v10 = 875;
  if ( v7 )
  {
    CoTaskMemFree(v7);
    ShellPath = v9;
  }
LABEL_17:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)ShellPath;
}

```

## disassembly

```asm
0x180010980  mov     [rsp-20h+pv], rcx
0x180010985  push    rbp
0x180010986  push    rbx
0x180010987  push    rsi
0x180010988  push    rdi
0x180010989  mov     rbp, rsp
0x18001098c  sub     rsp, 68h
0x180010990  mov     rdi, r8
0x180010993  lea     rcx, [rbp+var_48]; this
0x180010997  mov     rsi, rdx
0x18001099a  mov     r8d, 35Bh; unsigned __int16
0x1800109a0  lea     rdx, aCsdcontrollerA_2; "CSdController::_AddAppDataPathsToEngine"
0x1800109a7  xor     r9d, r9d; unsigned __int16
0x1800109aa  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800109af  mov     [rbp+pv], 0
0x1800109b7  mov     eax, 35Fh
0x1800109bc  test    rsi, rsi
0x1800109bf  jnz     short loc_1800109D2
0x1800109c1  mov     ebx, 80070057h
0x1800109c6  mov     [rbp+var_48], ebx
0x1800109c9  mov     [rbp+var_42], ax
0x1800109cd  jmp     loc_180010B31
0x1800109d2  mov     [rbp+var_44], ax
0x1800109d6  mov     eax, 360h
0x1800109db  test    rdi, rdi
0x1800109de  jz      short loc_1800109C1
0x1800109e0  lea     r8, [rbp+pv]; unsigned __int16 **
0x1800109e4  mov     [rbp+var_48], 0
0x1800109eb  lea     rdx, aAppdata_0; "AppData"
0x1800109f2  mov     [rbp+var_44], ax
0x1800109f6  mov     rcx, rdi; struct _UserProfileData *
0x1800109f9  call    ?GetShellPath@@YAJPEAU_UserProfileData@@PEBGPEAPEAG@Z; GetShellPath(_UserProfileData *,ushort const *,ushort * *)
0x1800109fe  mov     ebx, eax
0x180010a00  mov     [rbp+var_48], eax
0x180010a03  test    eax, eax
0x180010a05  mov     eax, 362h
0x180010a0a  js      short loc_1800109C9
0x180010a0c  mov     rdx, [rbp+pv]
0x180010a10  mov     r8d, 0C000016Fh
0x180010a16  mov     [rbp+var_44], ax
0x180010a1a  mov     rcx, rsi
0x180010a1d  mov     rax, [rsi]
0x180010a20  mov     rax, [rax+20h]
0x180010a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a29  mov     ebx, eax
0x180010a2b  mov     [rbp+var_48], eax
0x180010a2e  test    eax, eax
0x180010a30  mov     eax, 363h
0x180010a35  js      short loc_1800109C9
0x180010a37  cmp     [rbp+pv], 0
0x180010a3c  mov     [rbp+var_44], ax
0x180010a40  jz      short loc_180010A54
0x180010a42  mov     rcx, [rbp+pv]; pv
0x180010a46  call    cs:__imp_CoTaskMemFree
0x180010a4c  mov     [rbp+pv], 0
0x180010a54  lea     r8, [rbp+pv]; unsigned __int16 **
0x180010a58  mov     rcx, rdi; struct _UserProfileData *
0x180010a5b  lea     rdx, aLocalAppdata_0; "Local AppData"
0x180010a62  call    ?GetShellPath@@YAJPEAU_UserProfileData@@PEBGPEAPEAG@Z; GetShellPath(_UserProfileData *,ushort const *,ushort * *)
0x180010a67  mov     ebx, eax
0x180010a69  mov     [rbp+var_48], eax
0x180010a6c  test    eax, eax
0x180010a6e  mov     eax, 366h
0x180010a73  js      loc_1800109C9
0x180010a79  mov     rdx, [rbp+pv]
0x180010a7d  mov     r8d, 0C000016Fh
0x180010a83  mov     [rbp+var_44], ax
0x180010a87  mov     rcx, rsi
0x180010a8a  mov     rax, [rsi]
0x180010a8d  mov     rax, [rax+20h]
0x180010a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a96  mov     ebx, eax
0x180010a98  mov     [rbp+var_48], eax
0x180010a9b  test    eax, eax
0x180010a9d  mov     eax, 367h
0x180010aa2  js      loc_1800109C9
0x180010aa8  cmp     [rbp+pv], 0
0x180010aad  mov     [rbp+var_44], ax
0x180010ab1  jz      short loc_180010AC5
0x180010ab3  mov     rcx, [rbp+pv]; pv
0x180010ab7  call    cs:__imp_CoTaskMemFree
0x180010abd  mov     [rbp+pv], 0
0x180010ac5  lea     r8, [rbp+pv]; unsigned __int16 **
0x180010ac9  mov     rcx, rdi; struct _UserProfileData *
0x180010acc  lea     rdx, aA520a1a417804f; "{A520A1A4-1780-4FF6-BD18-167343C5AF16}"
0x180010ad3  call    ?GetShellPath@@YAJPEAU_UserProfileData@@PEBGPEAPEAG@Z; GetShellPath(_UserProfileData *,ushort const *,ushort * *)
0x180010ad8  mov     ebx, eax
0x180010ada  mov     [rbp+var_48], eax
0x180010add  test    eax, eax
0x180010adf  mov     eax, 36Ah
0x180010ae4  js      loc_1800109C9
0x180010aea  mov     rdi, [rbp+pv]
0x180010aee  mov     r8d, 0C000016Fh
0x180010af4  mov     [rbp+var_44], ax
0x180010af8  mov     rdx, rdi
0x180010afb  mov     rax, [rsi]
0x180010afe  mov     rcx, rsi
0x180010b01  mov     rax, [rax+20h]
0x180010b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b0a  mov     ebx, eax
0x180010b0c  mov     [rbp+var_48], eax
0x180010b0f  test    eax, eax
0x180010b11  mov     eax, 36Bh
0x180010b16  js      loc_1800109C9
0x180010b1c  mov     [rbp+var_44], ax
0x180010b20  test    rdi, rdi
0x180010b23  jz      short loc_180010B31
0x180010b25  mov     rcx, rdi; pv
0x180010b28  call    cs:__imp_CoTaskMemFree
0x180010b2e  mov     ebx, [rbp+var_48]
0x180010b31  lea     rcx, [rbp+var_48]; this
0x180010b35  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010b3a  mov     eax, ebx
0x180010b3c  add     rsp, 68h
0x180010b40  pop     rdi
0x180010b41  pop     rsi
0x180010b42  pop     rbx
0x180010b43  pop     rbp
0x180010b44  retn
```
