# CbsClient::OpenPackageByKB(ushort const *)

- ea: `0x140011190`
- end: `0x14001142f`
- name: `?OpenPackageByKB@CbsClient@@QEAAJPEBG@Z`
- size: `671`
- prototype: `__int64 __fastcall(CbsClient *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000afc0`

## callees

- `0x14000e280`
- `0x140010e1c`
- `0x140011190`
- `0x14001150c`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140011418`
- `KERNEL32!LocalFree` at `0x140011418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400112f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011380`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400112f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011380`

## string_xrefs

- `0x1400111a5`: `CbsClient::OpenPackageByKB`
- `0x140011208`: `Failed to enumerate installed packages`
- `0x140011361`: `Failed to open a CBS package`

## pseudocode

```c
__int64 __fastcall CbsClient::OpenPackageByKB(CbsClient *this, char *a2)
{
  signed int Properties; // ebx
  unsigned __int16 *v5; // rax
  int v6; // r8d
  int v7; // edx
  HLOCAL v8; // rdi
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+38h] [rbp-8h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+50h] BYREF
  __int64 v14; // [rsp+98h] [rbp+58h] BYREF

  v11 = 0;
  v10 = 0;
  v14 = 0;
  pv = 0;
  if ( *(_QWORD *)this )
  {
    CbsClient::ClosePackage(this);
    Properties = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)this + 56LL))(
                   *(_QWORD *)this,
                   16,
                   &v11);
    if ( Properties >= 0 )
    {
      while ( 1 )
      {
        LODWORD(hMem) = 0;
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, HLOCAL *))(*(_QWORD *)v11 + 24LL))(
               v11,
               1,
               &v10,
               &hMem)
          || (_DWORD)hMem != 1 )
        {
          break;
        }
        Properties = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *, __int64 *))(**(_QWORD **)this + 48LL))(
                       *(_QWORD *)this,
                       0,
                       v10,
                       (char *)this + 16,
                       &v14);
        if ( Properties < 0 )
        {
          WusaLogDebugEventA(L"CbsClient::OpenPackageByKB", 287, "Failed to open a CBS package");
          goto LABEL_26;
        }
        Properties = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v14)(
                       v14,
                       &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
                       (char *)this + 8);
        if ( Properties < 0 )
        {
          WusaLogDebugEventA(L"CbsClient::OpenPackageByKB", 290, "Failed to QI on a CBS package");
          goto LABEL_26;
        }
        Properties = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(**((_QWORD **)this + 1) + 32LL))(
                       *((_QWORD *)this + 1),
                       7,
                       &pv);
        if ( Properties < 0 )
        {
          WusaLogDebugEventA(L"CbsClient::OpenPackageByKB", 293, "Failed to query keyword property");
          goto LABEL_26;
        }
        v5 = (unsigned __int16 *)pv;
        do
        {
          v6 = *(unsigned __int16 *)((char *)v5 + a2 - (_BYTE *)pv);
          v7 = *v5 - v6;
          if ( v7 )
            break;
          ++v5;
        }
        while ( v6 );
        if ( !v7 )
        {
          Properties = CbsClient::QueryProperties(this);
          goto LABEL_26;
        }
        CbsClient::ClosePackage(this);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v14 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          v14 = 0;
        }
        if ( v10 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v10 = 0;
        }
      }
      Properties = 2359303;
    }
    else
    {
      WusaLogDebugEventA(L"CbsClient::OpenPackageByKB", 273, "Failed to enumerate installed packages");
    }
  }
  else
  {
    Properties = -2147418113;
    WusaLogDebugEventA(L"CbsClient::OpenPackageByKB", 267, "CBS session is not initialized.");
  }
LABEL_26:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( Properties < 0 )
  {
    CbsClient::ClosePackage(this);
    hMem = 0;
    WusaGetErrorMessage(Properties, (unsigned __int16 **)&hMem);
    v8 = hMem;
    WusaLogDebugEventA(
      L"CbsClient::OpenPackageByKB",
      319,
      "Exit with error code 0X%x (%ls)",
      Properties,
      (const wchar_t *)hMem);
    if ( v8 )
      LocalFree(v8);
  }
  return (unsigned int)Properties;
}

```

## disassembly

```asm
0x140011190  push    rbp
0x140011192  push    rbx
0x140011193  push    rsi
0x140011194  push    rdi
0x140011195  push    r12
0x140011197  push    r14
0x140011199  push    r15
0x14001119b  mov     rbp, rsp
0x14001119e  sub     rsp, 40h
0x1400111a2  xor     r15d, r15d
0x1400111a5  lea     r12, aCbsclientOpenp; "CbsClient::OpenPackageByKB"
0x1400111ac  mov     r14, rdx
0x1400111af  mov     rdi, rcx
0x1400111b2  mov     [rbp+var_8], r15
0x1400111b6  mov     [rbp+var_10], r15
0x1400111ba  mov     [rbp+arg_18], r15
0x1400111be  mov     [rbp+pv], r15
0x1400111c2  cmp     [rcx], r15
0x1400111c5  jnz     short loc_1400111E5
0x1400111c7  mov     ebx, 8000FFFFh
0x1400111cc  lea     r8, aCbsSessionIsNo; "CBS session is not initialized."
0x1400111d3  mov     edx, 10Bh
0x1400111d8  mov     rcx, r12
0x1400111db  call    WusaLogDebugEventA
0x1400111e0  jmp     loc_140011377
0x1400111e5  call    ?ClosePackage@CbsClient@@AEAAXXZ; CbsClient::ClosePackage(void)
0x1400111ea  mov     rcx, [rdi]
0x1400111ed  lea     r8, [rbp+var_8]
0x1400111f1  mov     edx, 10h
0x1400111f6  mov     rax, [rcx]
0x1400111f9  mov     rax, [rax+38h]
0x1400111fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011202  mov     ebx, eax
0x140011204  test    eax, eax
0x140011206  jns     short loc_140011216
0x140011208  lea     r8, aFailedToEnumer; "Failed to enumerate installed packages"
0x14001120f  mov     edx, 111h
0x140011214  jmp     short loc_1400111D8
0x140011216  mov     rcx, [rbp+var_8]
0x14001121a  lea     r9, [rbp+hMem]
0x14001121e  mov     dword ptr [rbp+hMem], r15d
0x140011222  lea     r8, [rbp+var_10]
0x140011226  mov     edx, 1
0x14001122b  mov     rax, [rcx]
0x14001122e  mov     rax, [rax+18h]
0x140011232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011237  test    eax, eax
0x140011239  jnz     loc_140011372
0x14001123f  cmp     dword ptr [rbp+hMem], 1
0x140011243  jnz     loc_140011372
0x140011249  mov     rcx, [rdi]
0x14001124c  lea     rdx, [rbp+arg_18]
0x140011250  mov     r8, [rbp+var_10]
0x140011254  lea     r9, [rdi+10h]
0x140011258  mov     [rsp+40h+var_20], rdx
0x14001125d  xor     edx, edx
0x14001125f  mov     rax, [rcx]
0x140011262  mov     rax, [rax+30h]
0x140011266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001126b  mov     ebx, eax
0x14001126d  test    eax, eax
0x14001126f  js      loc_140011361
0x140011275  mov     rcx, [rbp+arg_18]
0x140011279  lea     r8, [rdi+8]
0x14001127d  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x140011284  mov     rax, [rcx]
0x140011287  mov     rax, [rax]
0x14001128a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001128f  mov     ebx, eax
0x140011291  test    eax, eax
0x140011293  js      loc_140011350
0x140011299  mov     rcx, [rdi+8]
0x14001129d  lea     r8, [rbp+pv]
0x1400112a1  mov     edx, 7
0x1400112a6  mov     rax, [rcx]
0x1400112a9  mov     rax, [rax+20h]
0x1400112ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400112b2  mov     ebx, eax
0x1400112b4  test    eax, eax
0x1400112b6  js      loc_14001133F
0x1400112bc  mov     rax, [rbp+pv]
0x1400112c0  mov     rcx, r14
0x1400112c3  sub     rcx, rax
0x1400112c6  movzx   edx, word ptr [rax]
0x1400112c9  movzx   r8d, word ptr [rax+rcx]
0x1400112ce  sub     edx, r8d
0x1400112d1  jnz     short loc_1400112DC
0x1400112d3  add     rax, 2
0x1400112d7  test    r8d, r8d
0x1400112da  jnz     short loc_1400112C6
0x1400112dc  mov     rcx, rdi; this
0x1400112df  test    edx, edx
0x1400112e1  jz      short loc_140011336
0x1400112e3  call    ?ClosePackage@CbsClient@@AEAAXXZ; CbsClient::ClosePackage(void)
0x1400112e8  mov     rcx, [rbp+pv]; pv
0x1400112ec  test    rcx, rcx
0x1400112ef  jz      short loc_1400112FB
0x1400112f1  call    cs:__imp_CoTaskMemFree
0x1400112f7  mov     [rbp+pv], r15
0x1400112fb  mov     rcx, [rbp+arg_18]
0x1400112ff  test    rcx, rcx
0x140011302  jz      short loc_140011314
0x140011304  mov     rax, [rcx]
0x140011307  mov     rax, [rax+10h]
0x14001130b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011310  mov     [rbp+arg_18], r15
0x140011314  mov     rcx, [rbp+var_10]
0x140011318  test    rcx, rcx
0x14001131b  jz      loc_140011216
0x140011321  mov     rax, [rcx]
0x140011324  mov     rax, [rax+10h]
0x140011328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001132d  mov     [rbp+var_10], r15
0x140011331  jmp     loc_140011216
0x140011336  call    ?QueryProperties@CbsClient@@AEAAJXZ; CbsClient::QueryProperties(void)
0x14001133b  mov     ebx, eax
0x14001133d  jmp     short loc_140011377
0x14001133f  lea     r8, aFailedToQueryK; "Failed to query keyword property"
0x140011346  mov     edx, 125h
0x14001134b  jmp     loc_1400111D8
0x140011350  lea     r8, aFailedToQiOnAC; "Failed to QI on a CBS package"
0x140011357  mov     edx, 122h
0x14001135c  jmp     loc_1400111D8
0x140011361  lea     r8, aFailedToOpenAC; "Failed to open a CBS package"
0x140011368  mov     edx, 11Fh
0x14001136d  jmp     loc_1400111D8
0x140011372  mov     ebx, 240007h
0x140011377  mov     rcx, [rbp+pv]; pv
0x14001137b  test    rcx, rcx
0x14001137e  jz      short loc_14001138A
0x140011380  call    cs:__imp_CoTaskMemFree
0x140011386  mov     [rbp+pv], r15
0x14001138a  mov     rcx, [rbp+arg_18]
0x14001138e  test    rcx, rcx
0x140011391  jz      short loc_1400113A3
0x140011393  mov     rax, [rcx]
0x140011396  mov     rax, [rax+10h]
0x14001139a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001139f  mov     [rbp+arg_18], r15
0x1400113a3  mov     rcx, [rbp+var_10]
0x1400113a7  test    rcx, rcx
0x1400113aa  jz      short loc_1400113BC
0x1400113ac  mov     rax, [rcx]
0x1400113af  mov     rax, [rax+10h]
0x1400113b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400113b8  mov     [rbp+var_10], r15
0x1400113bc  mov     rcx, [rbp+var_8]
0x1400113c0  test    rcx, rcx
0x1400113c3  jz      short loc_1400113D5
0x1400113c5  mov     rax, [rcx]
0x1400113c8  mov     rax, [rax+10h]
0x1400113cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400113d1  mov     [rbp+var_8], r15
0x1400113d5  test    ebx, ebx
0x1400113d7  jns     short loc_14001141E
0x1400113d9  mov     rcx, rdi; this
0x1400113dc  call    ?ClosePackage@CbsClient@@AEAAXXZ; CbsClient::ClosePackage(void)
0x1400113e1  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x1400113e5  mov     [rbp+hMem], r15
0x1400113e9  mov     ecx, ebx; dwMessageId
0x1400113eb  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x1400113f0  mov     rdi, [rbp+hMem]
0x1400113f4  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x1400113fb  mov     r9d, ebx
0x1400113fe  mov     [rsp+40h+var_20], rdi
0x140011403  mov     edx, 13Fh
0x140011408  mov     rcx, r12
0x14001140b  call    WusaLogDebugEventA
0x140011410  test    rdi, rdi
0x140011413  jz      short loc_14001141E
0x140011415  mov     rcx, rdi; hMem
0x140011418  call    cs:__imp_LocalFree
0x14001141e  mov     eax, ebx
0x140011420  add     rsp, 40h
0x140011424  pop     r15
0x140011426  pop     r14
0x140011428  pop     r12
0x14001142a  pop     rdi
0x14001142b  pop     rsi
0x14001142c  pop     rbx
0x14001142d  pop     rbp
0x14001142e  retn
```
