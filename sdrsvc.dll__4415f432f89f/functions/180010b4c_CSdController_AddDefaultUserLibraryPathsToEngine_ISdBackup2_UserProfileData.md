# CSdController::_AddDefaultUserLibraryPathsToEngine(ISdBackup2 *,_UserProfileData *)

- ea: `0x180010b4c`
- end: `0x180010c77`
- name: `?_AddDefaultUserLibraryPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@PEAU_UserProfileData@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(CSdController *this, struct ISdBackup2 *, struct _UserProfileData *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010c80`

## callees

- `0x180010b4c`
- `0x18001586c`
- `0x180015974`
- `0x180018f6c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010bc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010bc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010c52`

## string_xrefs

- `0x180010b74`: `CSdController::_AddDefaultUserLibraryPathsToEngine`

## pseudocode

```c
__int64 __fastcall CSdController::_AddDefaultUserLibraryPathsToEngine(
        CSdController *this,
        struct ISdBackup2 *a2,
        struct _UserProfileData *a3)
{
  void *v5; // rdi
  __int16 v6; // ax
  unsigned int v7; // esi
  int ShellPath; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v12; // [rsp+20h] [rbp-48h] BYREF
  __int16 v13; // [rsp+24h] [rbp-44h]
  __int16 v14; // [rsp+26h] [rbp-42h]
  LPVOID pv; // [rsp+B0h] [rbp+48h] BYREF

  pv = this;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v12,
    "CSdController::_AddDefaultUserLibraryPathsToEngine",
    834,
    0);
  v5 = 0;
  v6 = 838;
  pv = 0;
  if ( a2 && (v13 = 838, v6 = 839, a3) )
  {
    v12 = 0;
    v13 = 839;
    v7 = 0;
    while ( 1 )
    {
      if ( v5 )
      {
        CoTaskMemFree(v5);
        pv = 0;
      }
      ShellPath = GetShellPath(a3, &aPersonal_0[260 * v7], (unsigned __int16 **)&pv);
      v5 = pv;
      v9 = ShellPath;
      v12 = ShellPath;
      if ( ShellPath < 0 )
        break;
      v10 = *(_QWORD *)a2;
      v13 = 844;
      v12 = (*(__int64 (__fastcall **)(struct ISdBackup2 *, LPVOID, __int64))(v10 + 32))(a2, pv, 3221225839LL);
      v9 = v12;
      if ( v12 < 0 )
      {
        v14 = 845;
        goto LABEL_13;
      }
      ++v7;
      v13 = 845;
      if ( v7 >= 4 )
        goto LABEL_13;
    }
    v14 = 844;
  }
  else
  {
    v9 = -2147024809;
    v14 = v6;
    v12 = -2147024809;
  }
LABEL_13:
  if ( v5 )
  {
    CoTaskMemFree(v5);
    v9 = v12;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return v9;
}

```

## disassembly

```asm
0x180010b4c  mov     [rsp-40h+pv], rcx
0x180010b51  push    rbp
0x180010b52  push    rbx
0x180010b53  push    rsi
0x180010b54  push    rdi
0x180010b55  push    r12
0x180010b57  push    r13
0x180010b59  push    r14
0x180010b5b  push    r15
0x180010b5d  mov     rbp, rsp
0x180010b60  sub     rsp, 68h
0x180010b64  mov     r14, r8
0x180010b67  lea     rcx, [rbp+var_48]; this
0x180010b6b  mov     r15, rdx
0x180010b6e  mov     r8d, 342h; unsigned __int16
0x180010b74  lea     rdx, aCsdcontrollerA; "CSdController::_AddDefaultUserLibraryPa"...
0x180010b7b  xor     r9d, r9d; unsigned __int16
0x180010b7e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010b83  xor     edi, edi
0x180010b85  mov     eax, 346h
0x180010b8a  mov     [rbp+pv], rdi
0x180010b8e  test    r15, r15
0x180010b91  jz      loc_180010C3E
0x180010b97  mov     [rbp+var_44], ax
0x180010b9b  mov     eax, 347h
0x180010ba0  test    r14, r14
0x180010ba3  jz      loc_180010C3E
0x180010ba9  mov     [rbp+var_48], edi
0x180010bac  lea     r13d, [rax+5]
0x180010bb0  mov     [rbp+var_44], ax
0x180010bb4  lea     r12d, [rax+6]
0x180010bb8  xor     esi, esi
0x180010bba  test    rdi, rdi
0x180010bbd  jz      short loc_180010BD0
0x180010bbf  mov     rcx, rdi; pv
0x180010bc2  call    cs:__imp_CoTaskMemFree
0x180010bc8  mov     [rbp+pv], 0
0x180010bd0  mov     eax, esi
0x180010bd2  lea     r8, [rbp+pv]; unsigned __int16 **
0x180010bd6  imul    rdx, rax, 208h
0x180010bdd  lea     rax, aPersonal_0; "Personal"
0x180010be4  mov     rcx, r14; struct _UserProfileData *
0x180010be7  add     rdx, rax; unsigned __int16 *
0x180010bea  call    ?GetShellPath@@YAJPEAU_UserProfileData@@PEBGPEAPEAG@Z; GetShellPath(_UserProfileData *,ushort const *,ushort * *)
0x180010bef  mov     rdi, [rbp+pv]
0x180010bf3  mov     ebx, eax
0x180010bf5  mov     [rbp+var_48], eax
0x180010bf8  test    eax, eax
0x180010bfa  js      short loc_180010C37
0x180010bfc  mov     rax, [r15]
0x180010bff  mov     r8d, 0C000016Fh
0x180010c05  mov     rdx, rdi
0x180010c08  mov     [rbp+var_44], r13w
0x180010c0d  mov     rcx, r15
0x180010c10  mov     rax, [rax+20h]
0x180010c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c19  mov     [rbp+var_48], eax
0x180010c1c  mov     ebx, eax
0x180010c1e  test    eax, eax
0x180010c20  js      short loc_180010C30
0x180010c22  inc     esi
0x180010c24  mov     [rbp+var_44], r12w
0x180010c29  cmp     esi, 4
0x180010c2c  jb      short loc_180010BBA
0x180010c2e  jmp     short loc_180010C4A
0x180010c30  mov     [rbp+var_42], r12w
0x180010c35  jmp     short loc_180010C4A
0x180010c37  mov     [rbp+var_42], r13w
0x180010c3c  jmp     short loc_180010C4A
0x180010c3e  mov     ebx, 80070057h
0x180010c43  mov     [rbp+var_42], ax
0x180010c47  mov     [rbp+var_48], ebx
0x180010c4a  test    rdi, rdi
0x180010c4d  jz      short loc_180010C5B
0x180010c4f  mov     rcx, rdi; pv
0x180010c52  call    cs:__imp_CoTaskMemFree
0x180010c58  mov     ebx, [rbp+var_48]
0x180010c5b  lea     rcx, [rbp+var_48]; this
0x180010c5f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010c64  mov     eax, ebx
0x180010c66  add     rsp, 68h
0x180010c6a  pop     r15
0x180010c6c  pop     r14
0x180010c6e  pop     r13
0x180010c70  pop     r12
0x180010c72  pop     rdi
0x180010c73  pop     rsi
0x180010c74  pop     rbx
0x180010c75  pop     rbp
0x180010c76  retn
```
