# CBitsJob::SetRemoteName(ulong,wchar_t const * *,wchar_t const * *,wchar_t const * *)

- ea: `0x1800f8ca0`
- end: `0x1800f915b`
- name: `?SetRemoteName@CBitsJob@@UEAAJKPEAPEB_W00@Z`
- size: `1211`
- prototype: `__int64 __usercall@<rax>(CBitsJob *__hidden this@<rcx>, unsigned int@<edx>, const wchar_t **@<r8>, const wchar_t **@<r9>, const wchar_t **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1800f8208`
- `0x1800f8464`
- `0x1800f8ca0`
- `0x180113ae8`
- `0x18012b618`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800f8e75`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800f8e75`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800f8d18`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800f912c`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800f8d18`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800f912c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8f78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8fbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9000`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8e8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8f78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f8fbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9000`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9085`

## string_xrefs

- `0x1800f90ca`: `%lu of %lu files' URLs are updated.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CBitsJob::SetRemoteName(
        CBitsJob *this,
        unsigned int a2,
        const wchar_t **a3,
        const wchar_t **a4,
        const wchar_t **a5)
{
  CBitsJob *v6; // rbx
  int v7; // r13d
  struct IBackgroundCopyFile **v8; // rdi
  __int64 v9; // r14
  int v10; // r12d
  HRESULT Files; // esi
  const wchar_t *v12; // rax
  struct IBackgroundCopyFile *v13; // rbx
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, LPVOID *); // r12
  void *v16; // rcx
  const wchar_t **v17; // r12
  const WCHAR *v18; // r8
  struct IBackgroundCopyFile **v19; // rbx
  __int64 v21; // [rsp+30h] [rbp-71h]
  __int64 v22; // [rsp+38h] [rbp-69h]
  char v23; // [rsp+40h] [rbp-61h]
  int v24; // [rsp+44h] [rbp-5Dh]
  struct IBackgroundCopyFile **v25; // [rsp+48h] [rbp-59h] BYREF
  unsigned int v26; // [rsp+50h] [rbp-51h]
  struct IBackgroundCopyFile *v27; // [rsp+58h] [rbp-49h] BYREF
  CBitsJob *v28; // [rsp+60h] [rbp-41h]
  __int128 v29; // [rsp+68h] [rbp-39h] BYREF
  const wchar_t **v30; // [rsp+78h] [rbp-29h]
  const wchar_t **v31; // [rsp+80h] [rbp-21h]
  const wchar_t **v32; // [rsp+88h] [rbp-19h]
  LPVOID pv; // [rsp+90h] [rbp-11h] BYREF
  __int64 v34; // [rsp+98h] [rbp-9h] BYREF
  IUnknown *ppOldObject[2]; // [rsp+A0h] [rbp-1h] BYREF

  v32 = a4;
  v31 = a3;
  v26 = a2;
  v6 = this;
  v28 = this;
  v30 = a5;
  v7 = 0;
  ppOldObject[0] = 0;
  ppOldObject[1] = 0;
  v8 = 0;
  v25 = 0;
  v9 = 0;
  LODWORD(pv) = 0;
  v10 = 0;
  v24 = 0;
  v23 = 0;
  Files = CoSwitchCallContext(0, &ppOldObject[1]);
  if ( Files < 0 )
    goto LABEL_61;
  LODWORD(ppOldObject[0]) = 1;
  Files = CBitsJob::GetFiles(v6, &v25, (unsigned int *)&pv);
  v9 = (unsigned int)pv;
  v8 = v25;
  if ( Files < 0 )
    goto LABEL_61;
  if ( !(_DWORD)pv )
  {
    Files = -2145124344;
    goto LABEL_61;
  }
  if ( !a2 )
  {
LABEL_60:
    LODWORD(v22) = v9;
    LODWORD(v21) = v10;
    WUTrace(0, 0, 2, 4, 0, L"%lu of %lu files' URLs are updated.", v21, v22);
    goto LABEL_61;
  }
  while ( 1 )
  {
    v27 = 0;
    v34 = 0;
    pv = 0;
    v29 = 0;
    v12 = v30[v7];
    if ( v12 )
      BYTE8(v29) = 1;
    else
      v12 = v31[v7];
    *(_QWORD *)&v29 = v12;
    Files = CBitsJob::FindFileInFileArray(v6, (const struct PathOrFileId *)&v29, v8, v9, &v27);
    if ( Files < 0 )
      break;
    if ( v34 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      v34 = 0;
    }
    v13 = v27;
    Files = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *, GUID *, __int64 *))v27->lpVtbl->QueryInterface)(
              v27,
              &GUID_83e81b93_0873_474d_8a8c_f2018b1a939c,
              &v34);
    if ( Files < 0 )
    {
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v34 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        v34 = 0;
      }
      goto LABEL_52;
    }
    v14 = v34;
    v15 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v34 + 24LL);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    Files = v15(v14, &pv);
    if ( Files < 0 )
    {
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v34 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        v34 = 0;
      }
      goto LABEL_52;
    }
    v16 = pv;
    v17 = v32;
    v18 = v32[v7];
    if ( v18 == pv )
      goto LABEL_21;
    if ( v18 && pv && CompareStringW(0x7Fu, 1u, v18, -1, (PCNZWCH)pv, -1) == 2 )
    {
      v16 = pv;
LABEL_21:
      v10 = v24;
      goto LABEL_22;
    }
    if ( !v23 )
    {
      Files = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v28 + 14) + 48LL))(*((_QWORD *)v28 + 14));
      if ( Files < 0 )
      {
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v34 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          v34 = 0;
        }
        goto LABEL_52;
      }
      v23 = 1;
    }
    Files = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v34 + 56LL))(v34, v17[v7]);
    if ( Files < 0 )
    {
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v34 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        v34 = 0;
      }
LABEL_52:
      ((void (__fastcall *)(struct IBackgroundCopyFile *))v13->lpVtbl->Release)(v13);
      goto LABEL_61;
    }
    WUTrace(0, 0, 2, 5, 0, L"Change the URL from %ws to %ws", pv, v17[v7]);
    v10 = ++v24;
    v16 = pv;
LABEL_22:
    if ( v16 )
    {
      CoTaskMemFree(v16);
      pv = 0;
    }
    if ( v34 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      v34 = 0;
    }
    ((void (__fastcall *)(struct IBackgroundCopyFile *))v13->lpVtbl->Release)(v13);
    if ( ++v7 >= v26 )
      goto LABEL_60;
    v6 = v28;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v27 )
    ((void (__fastcall *)(struct IBackgroundCopyFile *))v27->lpVtbl->Release)(v27);
LABEL_61:
  if ( (_DWORD)v9 )
  {
    v19 = v8;
    do
    {
      ((void (__fastcall *)(struct IBackgroundCopyFile *))(*v19)->lpVtbl->Release)(*v19);
      ++v19;
      --v9;
    }
    while ( v9 );
  }
  if ( v8 )
    SusFree(v8);
  if ( LODWORD(ppOldObject[0]) )
    CoSwitchCallContext(ppOldObject[1], &ppOldObject[1]);
  return (unsigned int)Files;
}

```

## disassembly

```asm
0x1800f8ca0  mov     [rsp-8+arg_8], rbx
0x1800f8ca5  push    rbp
0x1800f8ca6  push    rsi
0x1800f8ca7  push    rdi
0x1800f8ca8  push    r12
0x1800f8caa  push    r13
0x1800f8cac  push    r14
0x1800f8cae  push    r15
0x1800f8cb0  lea     rbp, [rsp-1Fh]
0x1800f8cb5  sub     rsp, 0C0h
0x1800f8cbc  mov     rax, cs:__security_cookie
0x1800f8cc3  xor     rax, rsp
0x1800f8cc6  mov     [rbp+4Fh+var_40], rax
0x1800f8cca  mov     [rbp+4Fh+var_68], r9
0x1800f8cce  mov     [rbp+4Fh+var_70], r8
0x1800f8cd2  mov     r15d, edx
0x1800f8cd5  mov     [rbp+4Fh+var_A0], edx
0x1800f8cd8  mov     rbx, rcx
0x1800f8cdb  mov     [rbp+4Fh+var_90], rcx
0x1800f8cdf  mov     rax, [rbp+4Fh+arg_20]
0x1800f8ce3  mov     [rbp+4Fh+var_78], rax
0x1800f8ce7  xorps   xmm0, xmm0
0x1800f8cea  movups  xmmword ptr [rbp+4Fh+ppOldObject], xmm0
0x1800f8cee  xor     r13d, r13d
0x1800f8cf1  mov     dword ptr [rbp+4Fh+ppOldObject], r13d
0x1800f8cf5  mov     [rbp+4Fh+ppOldObject+8], r13
0x1800f8cf9  mov     edi, r13d
0x1800f8cfc  mov     [rbp+4Fh+var_A8], r13
0x1800f8d00  mov     r14d, r13d
0x1800f8d03  mov     dword ptr [rbp+4Fh+pv], r14d
0x1800f8d07  mov     r12d, r13d
0x1800f8d0a  mov     [rbp+4Fh+var_AC], r13d
0x1800f8d0e  mov     [rbp+4Fh+var_B0], r13b
0x1800f8d12  lea     rdx, [rbp+4Fh+ppOldObject+8]; ppOldObject
0x1800f8d16  xor     ecx, ecx; pNewObject
0x1800f8d18  call    cs:__imp_CoSwitchCallContext
0x1800f8d1e  mov     esi, eax
0x1800f8d20  test    eax, eax
0x1800f8d22  js      loc_1800F90EF
0x1800f8d28  mov     dword ptr [rbp+4Fh+ppOldObject], 1
0x1800f8d2f  lea     r8, [rbp+4Fh+pv]; unsigned int *
0x1800f8d33  lea     rdx, [rbp+4Fh+var_A8]; struct IBackgroundCopyFile ***
0x1800f8d37  mov     rcx, rbx; this
0x1800f8d3a  call    ?GetFiles@CBitsJob@@AEAAJPEAPEAPEAUIBackgroundCopyFile@@PEAK@Z; CBitsJob::GetFiles(IBackgroundCopyFile * * *,ulong *)
0x1800f8d3f  mov     esi, eax
0x1800f8d41  mov     r14d, dword ptr [rbp+4Fh+pv]
0x1800f8d45  mov     rdi, [rbp+4Fh+var_A8]
0x1800f8d49  test    eax, eax
0x1800f8d4b  js      loc_1800F90EF
0x1800f8d51  test    r14d, r14d
0x1800f8d54  jnz     short loc_1800F8D60
0x1800f8d56  mov     esi, 80240008h
0x1800f8d5b  jmp     loc_1800F90EF
0x1800f8d60  test    r15d, r15d
0x1800f8d63  jz      loc_1800F90C0
0x1800f8d69  xor     r12d, r12d
0x1800f8d6c  mov     [rbp+4Fh+var_98], r12
0x1800f8d70  mov     [rbp+4Fh+var_58], r12
0x1800f8d74  mov     [rbp+4Fh+pv], r12
0x1800f8d78  xorps   xmm0, xmm0
0x1800f8d7b  movups  [rbp+4Fh+var_88], xmm0
0x1800f8d7f  mov     r15d, r13d
0x1800f8d82  mov     rax, [rbp+4Fh+var_78]
0x1800f8d86  mov     rax, [rax+r15*8]
0x1800f8d8a  test    rax, rax
0x1800f8d8d  jnz     short loc_1800F8D99
0x1800f8d8f  mov     rax, [rbp+4Fh+var_70]
0x1800f8d93  mov     rax, [rax+r15*8]
0x1800f8d97  jmp     short loc_1800F8D9D
0x1800f8d99  mov     byte ptr [rbp+4Fh+var_88+8], 1
0x1800f8d9d  mov     qword ptr [rbp+4Fh+var_88], rax
0x1800f8da1  lea     rax, [rbp+4Fh+var_98]
0x1800f8da5  mov     [rsp+0F0h+lpString2], rax; struct IBackgroundCopyFile **
0x1800f8daa  mov     r9d, r14d; unsigned int
0x1800f8dad  mov     r8, rdi; struct IBackgroundCopyFile **
0x1800f8db0  lea     rdx, [rbp+4Fh+var_88]; struct PathOrFileId *
0x1800f8db4  mov     rcx, rbx; this
0x1800f8db7  call    ?FindFileInFileArray@CBitsJob@@AEAAJAEBUPathOrFileId@@PEAPEAUIBackgroundCopyFile@@K1@Z; CBitsJob::FindFileInFileArray(PathOrFileId const &,IBackgroundCopyFile * *,ulong,IBackgroundCopyFile * *)
0x1800f8dbc  mov     esi, eax
0x1800f8dbe  test    eax, eax
0x1800f8dc0  js      loc_1800F9079
0x1800f8dc6  mov     rcx, [rbp+4Fh+var_58]
0x1800f8dca  test    rcx, rcx
0x1800f8dcd  jz      short loc_1800F8DDF
0x1800f8dcf  mov     rax, [rcx]
0x1800f8dd2  mov     rax, [rax+10h]
0x1800f8dd6  call    _guard_dispatch_icall
0x1800f8ddb  mov     [rbp+4Fh+var_58], r12
0x1800f8ddf  mov     rbx, [rbp+4Fh+var_98]
0x1800f8de3  mov     rax, [rbx]
0x1800f8de6  lea     r8, [rbp+4Fh+var_58]
0x1800f8dea  lea     rdx, _GUID_83e81b93_0873_474d_8a8c_f2018b1a939c
0x1800f8df1  mov     rcx, rbx
0x1800f8df4  mov     rax, [rax]
0x1800f8df7  call    _guard_dispatch_icall
0x1800f8dfc  mov     esi, eax
0x1800f8dfe  test    eax, eax
0x1800f8e00  js      loc_1800F9038
0x1800f8e06  mov     rsi, [rbp+4Fh+var_58]
0x1800f8e0a  mov     rax, [rsi]
0x1800f8e0d  mov     r12, [rax+18h]
0x1800f8e11  mov     rcx, [rbp+4Fh+pv]; pv
0x1800f8e15  test    rcx, rcx
0x1800f8e18  jz      short loc_1800F8E28
0x1800f8e1a  call    cs:__imp_CoTaskMemFree
0x1800f8e20  mov     [rbp+4Fh+pv], 0
0x1800f8e28  lea     rdx, [rbp+4Fh+pv]
0x1800f8e2c  mov     rcx, rsi
0x1800f8e2f  mov     rax, r12
0x1800f8e32  call    _guard_dispatch_icall
0x1800f8e37  mov     esi, eax
0x1800f8e39  test    eax, eax
0x1800f8e3b  js      loc_1800F8FF4
0x1800f8e41  mov     rcx, [rbp+4Fh+pv]
0x1800f8e45  mov     r12, [rbp+4Fh+var_68]
0x1800f8e49  mov     r8, [r12+r15*8]; lpString1
0x1800f8e4d  cmp     r8, rcx
0x1800f8e50  jz      short loc_1800F8E84
0x1800f8e52  test    r8, r8
0x1800f8e55  jz      loc_1800F8EDE
0x1800f8e5b  test    rcx, rcx
0x1800f8e5e  jz      short loc_1800F8EDE
0x1800f8e60  or      eax, 0FFFFFFFFh
0x1800f8e63  mov     [rsp+0F0h+cchCount2], eax; cchCount2
0x1800f8e67  mov     [rsp+0F0h+lpString2], rcx; lpString2
0x1800f8e6c  mov     r9d, eax; cchCount1
0x1800f8e6f  lea     edx, [rax+2]; dwCmpFlags
0x1800f8e72  lea     ecx, [rdx+7Eh]; Locale
0x1800f8e75  call    cs:__imp_CompareStringW
0x1800f8e7b  cmp     eax, 2
0x1800f8e7e  jnz     short loc_1800F8EDE
0x1800f8e80  mov     rcx, [rbp+4Fh+pv]; pv
0x1800f8e84  mov     r12d, [rbp+4Fh+var_AC]
0x1800f8e88  test    rcx, rcx
0x1800f8e8b  jz      short loc_1800F8E9B
0x1800f8e8d  call    cs:__imp_CoTaskMemFree
0x1800f8e93  mov     [rbp+4Fh+pv], 0
0x1800f8e9b  mov     rcx, [rbp+4Fh+var_58]
0x1800f8e9f  test    rcx, rcx
0x1800f8ea2  jz      short loc_1800F8EB8
0x1800f8ea4  mov     rax, [rcx]
0x1800f8ea7  mov     rax, [rax+10h]
0x1800f8eab  call    _guard_dispatch_icall
0x1800f8eb0  mov     [rbp+4Fh+var_58], 0
0x1800f8eb8  mov     rax, [rbx]
0x1800f8ebb  mov     rcx, rbx
0x1800f8ebe  mov     rax, [rax+10h]
0x1800f8ec2  call    _guard_dispatch_icall
0x1800f8ec7  nop
0x1800f8ec8  inc     r13d
0x1800f8ecb  cmp     r13d, [rbp+4Fh+var_A0]
0x1800f8ecf  jnb     loc_1800F90C0
0x1800f8ed5  mov     rbx, [rbp+4Fh+var_90]
0x1800f8ed9  jmp     loc_1800F8D69
0x1800f8ede  cmp     [rbp+4Fh+var_B0], 0
0x1800f8ee2  jnz     short loc_1800F8F02
0x1800f8ee4  mov     rcx, [rbp+4Fh+var_90]
0x1800f8ee8  mov     rcx, [rcx+70h]
0x1800f8eec  mov     rax, [rcx]
0x1800f8eef  mov     rax, [rax+30h]
0x1800f8ef3  call    _guard_dispatch_icall
0x1800f8ef8  mov     esi, eax
0x1800f8efa  test    eax, eax
0x1800f8efc  js      short loc_1800F8F6C
0x1800f8efe  mov     [rbp+4Fh+var_B0], 1
0x1800f8f02  mov     rcx, [rbp+4Fh+var_58]
0x1800f8f06  mov     rax, [rcx]
0x1800f8f09  mov     rdx, [r12+r15*8]
0x1800f8f0d  mov     rax, [rax+38h]
0x1800f8f11  call    _guard_dispatch_icall
0x1800f8f16  mov     esi, eax
0x1800f8f18  test    eax, eax
0x1800f8f1a  js      loc_1800F8FB0
0x1800f8f20  mov     rax, [r12+r15*8]
0x1800f8f24  mov     [rsp+0F0h+var_B8], rax
0x1800f8f29  mov     rax, [rbp+4Fh+pv]
0x1800f8f2d  mov     [rsp+0F0h+var_C0], rax
0x1800f8f32  lea     rax, aChangeTheUrlFr; "Change the URL from %ws to %ws"
0x1800f8f39  mov     qword ptr [rsp+0F0h+cchCount2], rax
0x1800f8f3e  mov     [rsp+0F0h+lpString2], 0
0x1800f8f47  xor     edx, edx
0x1800f8f49  xor     ecx, ecx
0x1800f8f4b  lea     r9d, [rdx+5]
0x1800f8f4f  lea     r8d, [rdx+2]
0x1800f8f53  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800f8f58  mov     r12d, [rbp+4Fh+var_AC]
0x1800f8f5c  inc     r12d
0x1800f8f5f  mov     [rbp+4Fh+var_AC], r12d
0x1800f8f63  mov     rcx, [rbp+4Fh+pv]
0x1800f8f67  jmp     loc_1800F8E88
0x1800f8f6c  mov     rcx, [rbp+4Fh+pv]; pv
0x1800f8f70  xor     r13d, r13d
0x1800f8f73  test    rcx, rcx
0x1800f8f76  jz      short loc_1800F8F82
0x1800f8f78  call    cs:__imp_CoTaskMemFree
0x1800f8f7e  mov     [rbp+4Fh+pv], r13
0x1800f8f82  mov     rcx, [rbp+4Fh+var_58]
0x1800f8f86  test    rcx, rcx
0x1800f8f89  jz      short loc_1800F8F9B
0x1800f8f8b  mov     rax, [rcx]
0x1800f8f8e  mov     rax, [rax+10h]
0x1800f8f92  call    _guard_dispatch_icall
0x1800f8f97  mov     [rbp+4Fh+var_58], r13
0x1800f8f9b  mov     rax, [rbx]
0x1800f8f9e  mov     rcx, rbx
0x1800f8fa1  mov     rax, [rax+10h]
0x1800f8fa5  call    _guard_dispatch_icall
0x1800f8faa  nop
0x1800f8fab  jmp     loc_1800F90EF
0x1800f8fb0  mov     rcx, [rbp+4Fh+pv]; pv
0x1800f8fb4  xor     r13d, r13d
0x1800f8fb7  test    rcx, rcx
0x1800f8fba  jz      short loc_1800F8FC6
0x1800f8fbc  call    cs:__imp_CoTaskMemFree
0x1800f8fc2  mov     [rbp+4Fh+pv], r13
0x1800f8fc6  mov     rcx, [rbp+4Fh+var_58]
0x1800f8fca  test    rcx, rcx
0x1800f8fcd  jz      short loc_1800F8FDF
0x1800f8fcf  mov     rax, [rcx]
0x1800f8fd2  mov     rax, [rax+10h]
0x1800f8fd6  call    _guard_dispatch_icall
0x1800f8fdb  mov     [rbp+4Fh+var_58], r13
0x1800f8fdf  mov     rax, [rbx]
0x1800f8fe2  mov     rcx, rbx
0x1800f8fe5  mov     rax, [rax+10h]
0x1800f8fe9  call    _guard_dispatch_icall
0x1800f8fee  nop
0x1800f8fef  jmp     loc_1800F90EF
0x1800f8ff4  mov     rcx, [rbp+4Fh+pv]; pv
0x1800f8ff8  xor     r13d, r13d
0x1800f8ffb  test    rcx, rcx
0x1800f8ffe  jz      short loc_1800F900A
0x1800f9000  call    cs:__imp_CoTaskMemFree
0x1800f9006  mov     [rbp+4Fh+pv], r13
0x1800f900a  mov     rcx, [rbp+4Fh+var_58]
0x1800f900e  test    rcx, rcx
0x1800f9011  jz      short loc_1800F9023
0x1800f9013  mov     rax, [rcx]
0x1800f9016  mov     rax, [rax+10h]
0x1800f901a  call    _guard_dispatch_icall
0x1800f901f  mov     [rbp+4Fh+var_58], r13
0x1800f9023  mov     rax, [rbx]
0x1800f9026  mov     rcx, rbx
0x1800f9029  mov     rax, [rax+10h]
0x1800f902d  call    _guard_dispatch_icall
0x1800f9032  nop
0x1800f9033  jmp     loc_1800F90EF
0x1800f9038  mov     rcx, [rbp+4Fh+pv]; pv
0x1800f903c  xor     r13d, r13d
0x1800f903f  test    rcx, rcx
0x1800f9042  jz      short loc_1800F904E
0x1800f9044  call    cs:__imp_CoTaskMemFree
0x1800f904a  mov     [rbp+4Fh+pv], r13
0x1800f904e  mov     rcx, [rbp+4Fh+var_58]
0x1800f9052  test    rcx, rcx
0x1800f9055  jz      short loc_1800F9067
0x1800f9057  mov     rax, [rcx]
0x1800f905a  mov     rax, [rax+10h]
0x1800f905e  call    _guard_dispatch_icall
0x1800f9063  mov     [rbp+4Fh+var_58], r13
0x1800f9067  mov     rax, [rbx]
0x1800f906a  mov     rcx, rbx
0x1800f906d  mov     rax, [rax+10h]
0x1800f9071  call    _guard_dispatch_icall
0x1800f9076  nop
0x1800f9077  jmp     short loc_1800F90EF
0x1800f9079  mov     rcx, [rbp+4Fh+pv]; pv
0x1800f907d  xor     r13d, r13d
0x1800f9080  test    rcx, rcx
0x1800f9083  jz      short loc_1800F908F
0x1800f9085  call    cs:__imp_CoTaskMemFree
0x1800f908b  mov     [rbp+4Fh+pv], r13
0x1800f908f  mov     rcx, [rbp+4Fh+var_58]
0x1800f9093  test    rcx, rcx
0x1800f9096  jz      short loc_1800F90A8
0x1800f9098  mov     rax, [rcx]
0x1800f909b  mov     rax, [rax+10h]
0x1800f909f  call    _guard_dispatch_icall
0x1800f90a4  mov     [rbp+4Fh+var_58], r13
0x1800f90a8  mov     rcx, [rbp+4Fh+var_98]
0x1800f90ac  test    rcx, rcx
0x1800f90af  jz      short loc_1800F90BE
0x1800f90b1  mov     rax, [rcx]
0x1800f90b4  mov     rax, [rax+10h]
0x1800f90b8  call    _guard_dispatch_icall
0x1800f90bd  nop
0x1800f90be  jmp     short loc_1800F90EF
0x1800f90c0  mov     dword ptr [rsp+0F0h+var_B8], r14d
0x1800f90c5  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1800f90ca  lea     rax, aLuOfLuFilesUrl; "%lu of %lu files' URLs are updated."
0x1800f90d1  mov     qword ptr [rsp+0F0h+cchCount2], rax
0x1800f90d6  xor     r13d, r13d
0x1800f90d9  mov     [rsp+0F0h+lpString2], r13
0x1800f90de  xor     edx, edx
0x1800f90e0  xor     ecx, ecx
0x1800f90e2  lea     r9d, [r13+4]
0x1800f90e6  lea     r8d, [r13+2]
0x1800f90ea  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800f90ef  test    r14d, r14d
0x1800f90f2  jz      short loc_1800F9110
  ... truncated ...
```
