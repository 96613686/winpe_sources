# ArchiveConflictItems::GetItem(uint,CONFIRM_CONFLICT_ITEM *)

- ea: `0x180067870`
- end: `0x180067a38`
- name: `?GetItem@ArchiveConflictItems@@UEAAJIPEAUCONFIRM_CONFLICT_ITEM@@@Z`
- size: `456`
- prototype: `int(ArchiveConflictItems *__hidden this, unsigned int, struct CONFIRM_CONFLICT_ITEM *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180031e94`
- `0x180067870`
- `0x180067b0c`
- `0x180071010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18006795d`
- `SHLWAPI!SHStrDupW` at `0x18006795d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800678bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800678d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067987`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800679e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800679f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800678bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800678d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067987`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800679e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800679f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a15`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArchiveConflictItems::GetItem(
        ArchiveConflictItems *this,
        unsigned int a2,
        struct CONFIRM_CONFLICT_ITEM *a3)
{
  struct IShellItem *v5; // r15
  LPVOID *p_pszOriginalName; // rdi
  int FileName; // eax
  unsigned int v8; // r14d
  LPVOID *p_pszAlternateName; // rsi
  HRESULT v10; // eax
  int v11; // eax
  unsigned int v12; // ebp
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_OWORD *)&a3->pShellItem = 0;
  *(_OWORD *)&a3->pszAlternateName = 0;
  *(_OWORD *)&a3->pszLocationFull = 0;
  if ( a2 >= 2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D0,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)0x80070057LL,
      v13);
    CoTaskMemFree(a3->pszOriginalName);
    a3->pszOriginalName = 0;
    CoTaskMemFree(a3->pszAlternateName);
    a3->pszAlternateName = 0;
    return 2147942487LL;
  }
  v5 = *(struct IShellItem **)((char *)this + (a2 != 0 ? 8 : 0) + 24);
  a3->nType = SYNCMGR_CIT_UPDATED;
  p_pszOriginalName = (LPVOID *)&a3->pszOriginalName;
  FileName = IShellItem_GetFileName(v5, &a3->pszOriginalName);
  v8 = FileName;
  p_pszAlternateName = (LPVOID *)&a3->pszAlternateName;
  if ( FileName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D5,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)FileName,
      v13);
    CoTaskMemFree(*p_pszOriginalName);
    *p_pszOriginalName = 0;
    CoTaskMemFree(*p_pszAlternateName);
    *p_pszAlternateName = 0;
    return v8;
  }
  v10 = SHStrDupW((LPCWSTR)*p_pszOriginalName, &a3->pszAlternateName);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D9,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v10,
      v13);
    CoTaskMemFree(*p_pszOriginalName);
    *p_pszOriginalName = 0;
    CoTaskMemFree(*p_pszAlternateName);
    *p_pszAlternateName = 0;
    return v8;
  }
  v11 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, struct CONFIRM_CONFLICT_ITEM *))v5->lpVtbl->QueryInterface)(
          v5,
          &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
          a3);
  v12 = v11;
  if ( v11 >= 0 )
  {
    CoTaskMemFree(*p_pszOriginalName);
    *p_pszOriginalName = 0;
    CoTaskMemFree(*p_pszAlternateName);
    *p_pszAlternateName = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4DB,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v11,
      v13);
    CoTaskMemFree(*p_pszOriginalName);
    *p_pszOriginalName = 0;
    CoTaskMemFree(*p_pszAlternateName);
    *p_pszAlternateName = 0;
    return v12;
  }
}

```

## disassembly

```asm
0x180067870  mov     [rsp+arg_8], rbp
0x180067875  mov     [rsp+arg_18], rsi
0x18006787a  push    rdi
0x18006787b  push    r14
0x18006787d  push    r15; int
0x18006787f  sub     rsp, 20h
0x180067883  mov     rbp, r8
0x180067886  xorps   xmm0, xmm0
0x180067889  movups  xmmword ptr [r8], xmm0
0x18006788d  movups  xmmword ptr [r8+10h], xmm0
0x180067892  movups  xmmword ptr [r8+20h], xmm0
0x180067897  cmp     edx, 2
0x18006789a  jb      short loc_1800678E6
0x18006789c  mov     rcx, [rsp+38h]; this
0x1800678a1  mov     edi, 80070057h
0x1800678a6  mov     r9d, edi; char *
0x1800678a9  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800678b0  mov     edx, 4D0h; void *
0x1800678b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800678ba  nop
0x1800678bb  mov     rcx, [rbp+8]; pv
0x1800678bf  call    cs:__imp_CoTaskMemFree
0x1800678c5  mov     qword ptr [rbp+8], 0
0x1800678cd  mov     rcx, [rbp+10h]; pv
0x1800678d1  call    cs:__imp_CoTaskMemFree
0x1800678d7  mov     qword ptr [rbp+10h], 0
0x1800678df  mov     eax, edi
0x1800678e1  jmp     loc_180067A24
0x1800678e6  neg     edx
0x1800678e8  sbb     rax, rax
0x1800678eb  and     eax, 8
0x1800678ee  mov     r15, [rax+rcx+18h]
0x1800678f3  mov     dword ptr [r8+28h], 1
0x1800678fb  lea     rdi, [r8+8]
0x1800678ff  mov     rdx, rdi; unsigned __int16 **
0x180067902  mov     rcx, r15; struct IShellItem *
0x180067905  call    ?IShellItem_GetFileName@@YAJPEAUIShellItem@@PEAPEAG@Z; IShellItem_GetFileName(IShellItem *,ushort * *)
0x18006790a  mov     r14d, eax
0x18006790d  lea     rsi, [rbp+10h]
0x180067911  test    eax, eax
0x180067913  jns     short loc_180067957
0x180067915  mov     rcx, [rsp+38h]; this
0x18006791a  mov     r9d, eax; char *
0x18006791d  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180067924  mov     edx, 4D5h; void *
0x180067929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006792e  nop
0x18006792f  mov     rcx, [rdi]; pv
0x180067932  call    cs:__imp_CoTaskMemFree
0x180067938  mov     qword ptr [rdi], 0
0x18006793f  mov     rcx, [rsi]; pv
0x180067942  call    cs:__imp_CoTaskMemFree
0x180067948  mov     qword ptr [rsi], 0
0x18006794f  mov     eax, r14d
0x180067952  jmp     loc_180067A24
0x180067957  mov     rdx, rsi; ppwsz
0x18006795a  mov     rcx, [rdi]; psz
0x18006795d  call    cs:__imp_SHStrDupW
0x180067963  mov     r14d, eax
0x180067966  test    eax, eax
0x180067968  jns     short loc_1800679A6
0x18006796a  mov     rcx, [rsp+38h]; this
0x18006796f  mov     r9d, eax; char *
0x180067972  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180067979  mov     edx, 4D9h; void *
0x18006797e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067983  nop
0x180067984  mov     rcx, [rdi]; pv
0x180067987  call    cs:__imp_CoTaskMemFree
0x18006798d  mov     qword ptr [rdi], 0
0x180067994  mov     rcx, [rsi]; pv
0x180067997  call    cs:__imp_CoTaskMemFree
0x18006799d  mov     qword ptr [rsi], 0
0x1800679a4  jmp     short loc_18006794F
0x1800679a6  mov     rax, [r15]
0x1800679a9  mov     r8, rbp
0x1800679ac  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x1800679b3  mov     rcx, r15
0x1800679b6  mov     rax, [rax]
0x1800679b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679be  mov     ebp, eax
0x1800679c0  test    eax, eax
0x1800679c2  jns     short loc_180067A02
0x1800679c4  mov     rcx, [rsp+38h]; this
0x1800679c9  mov     r9d, eax; char *
0x1800679cc  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800679d3  mov     edx, 4DBh; void *
0x1800679d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800679dd  nop
0x1800679de  mov     rcx, [rdi]; pv
0x1800679e1  call    cs:__imp_CoTaskMemFree
0x1800679e7  mov     qword ptr [rdi], 0
0x1800679ee  mov     rcx, [rsi]; pv
0x1800679f1  call    cs:__imp_CoTaskMemFree
0x1800679f7  mov     qword ptr [rsi], 0
0x1800679fe  mov     eax, ebp
0x180067a00  jmp     short loc_180067A24
0x180067a02  mov     rcx, [rdi]; pv
0x180067a05  call    cs:__imp_CoTaskMemFree
0x180067a0b  mov     qword ptr [rdi], 0
0x180067a12  mov     rcx, [rsi]; pv
0x180067a15  call    cs:__imp_CoTaskMemFree
0x180067a1b  mov     qword ptr [rsi], 0
0x180067a22  xor     eax, eax
0x180067a24  mov     rbp, [rsp+38h+arg_8]
0x180067a29  mov     rsi, [rsp+38h+arg_18]
0x180067a2e  add     rsp, 20h
0x180067a32  pop     r15
0x180067a34  pop     r14
0x180067a36  pop     rdi
0x180067a37  retn
```
