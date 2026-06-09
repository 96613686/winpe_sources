# CHtmlLocalFileResolver::GetStorageItems(IDataObject *,STORAGEITEM_CREATION_FLAGS,IUnknown *)

- ea: `0x1800621e0`
- end: `0x180062469`
- name: `?GetStorageItems@CHtmlLocalFileResolver@@UEAAJPEAUIDataObject@@W4STORAGEITEM_CREATION_FLAGS@@PEAUIUnknown@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(__int64, struct IDataObject *, int, __int64 (__fastcall ***)(_QWORD, GUID *, const WCHAR **))`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x18006042c`
- `0x180061350`
- `0x1800617e0`
- `0x1800621e0`
- `0x18006556c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180062277`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180062277`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180062382`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180062382`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062343`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006241d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006241d`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800622f0`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800622f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CHtmlLocalFileResolver::GetStorageItems(
        __int64 a1,
        struct IDataObject *a2,
        int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, const WCHAR **))
{
  LONG FormatEtc; // ebx
  unsigned __int16 v7; // si
  char *v8; // rdi
  WCHAR *v9; // rdi
  __int64 v10; // rcx
  const WCHAR *v11; // rsi
  __int64 v12; // rcx
  const WCHAR *v13; // rcx
  UINT32 packageFamilyNameLength; // [rsp+30h] [rbp-D0h] BYREF
  __int64 ppv; // [rsp+38h] [rbp-C8h] BYREF
  const WCHAR *v17; // [rsp+40h] [rbp-C0h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR packageFullName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+68h] [rbp-98h]
  WCHAR packageFamilyName[72]; // [rsp+70h] [rbp-90h] BYREF

  v17 = 0;
  FormatEtc = (**a4)(a4, &GUID_802508e2_9c2c_5b91_89a8_39bcf7223344, &v17);
  if ( FormatEtc >= 0 )
  {
    v7 = word_1800AA61E;
    FormatEtc = FindFormatEtc(a2, word_1800AA61E, 0);
    if ( FormatEtc )
    {
      v7 = 15;
      if ( (unsigned int)FindFormatEtc(a2, 0xFu, 0) )
      {
        FormatEtc = -2147024891;
        RoOriginateError(2147942405LL, 0);
      }
      else
      {
        FormatEtc = 0;
      }
    }
    v8 = 0;
    TokenHandle = 0;
    ppv = 0;
    if ( FormatEtc < 0 )
      goto LABEL_20;
    packageFullName = 0;
    v21 = -1;
    v22 = -1;
    FormatEtc = CHtmlLocalFileResolver::s_ValidateCallerAndClipboardContent(
                  a2,
                  v7,
                  &TokenHandle,
                  (unsigned __int16 **)&packageFullName,
                  0);
    v9 = (WCHAR *)packageFullName;
    if ( FormatEtc >= 0 )
    {
      memset_0(packageFamilyName, 0, 0x82u);
      packageFamilyNameLength = 65;
      FormatEtc = PackageFamilyNameFromFullName(v9, &packageFamilyNameLength, packageFamilyName);
      if ( FormatEtc >= 0 )
      {
        v10 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
        FormatEtc = CreateStorageItemVectorFromFormat((int)a2, v7, a3, (int)packageFamilyName, &ppv);
      }
    }
    if ( v9 )
      CoTaskMemFree(v9);
    v8 = (char *)TokenHandle;
    if ( FormatEtc < 0 )
      goto LABEL_20;
    ReturnLength = 0;
    packageFamilyNameLength = 0;
    GetTokenInformation(TokenHandle, TokenIsAppContainer, &packageFamilyNameLength, 4u, &ReturnLength);
    v11 = v17;
    packageFullName = v17;
    if ( v17 )
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v17 + 8LL))(v17);
    v21 = (__int64)v8;
    LODWORD(v22) = packageFamilyNameLength;
    FormatEtc = IterateOverVector_Windows::Storage::IStorageItem__lambda_d01e397cc7e6270c25a33f459ef56c8a___(
                  ppv,
                  &packageFullName);
    if ( v11 )
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( FormatEtc < 0 )
LABEL_20:
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v17 + 120LL))(v17);
    v12 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v8);
  }
  v13 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)FormatEtc;
}

```

## disassembly

```asm
0x1800621e0  mov     [rsp-8+arg_0], rbx
0x1800621e5  push    rbp
0x1800621e6  push    rsi
0x1800621e7  push    rdi
0x1800621e8  push    r14
0x1800621ea  push    r15
0x1800621ec  lea     rbp, [rsp-10h]
0x1800621f1  sub     rsp, 110h
0x1800621f8  mov     rax, cs:__security_cookie
0x1800621ff  xor     rax, rsp
0x180062202  mov     [rbp+30h+var_30], rax
0x180062206  mov     r15d, r8d
0x180062209  mov     r14, rdx
0x18006220c  mov     [rsp+130h+var_F0], 0
0x180062215  mov     rax, [r9]
0x180062218  lea     r8, [rsp+130h+var_F0]
0x18006221d  lea     rdx, _GUID_802508e2_9c2c_5b91_89a8_39bcf7223344
0x180062224  mov     rcx, r9
0x180062227  mov     rax, [rax]
0x18006222a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006222f  mov     ebx, eax
0x180062231  test    eax, eax
0x180062233  js      loc_180062424
0x180062239  movzx   esi, cs:word_1800AA61E
0x180062240  xor     r8d, r8d; struct tagFORMATETC *
0x180062243  movzx   edx, si; unsigned __int16
0x180062246  mov     rcx, r14; struct IDataObject *
0x180062249  call    ?FindFormatEtc@@YAJPEAUIDataObject@@GPEAUtagFORMATETC@@@Z; FindFormatEtc(IDataObject *,ushort,tagFORMATETC *)
0x18006224e  mov     ebx, eax
0x180062250  test    eax, eax
0x180062252  jz      short loc_18006227D
0x180062254  mov     esi, 0Fh
0x180062259  mov     edx, esi; unsigned __int16
0x18006225b  xor     r8d, r8d; struct tagFORMATETC *
0x18006225e  mov     rcx, r14; struct IDataObject *
0x180062261  call    ?FindFormatEtc@@YAJPEAUIDataObject@@GPEAUtagFORMATETC@@@Z; FindFormatEtc(IDataObject *,ushort,tagFORMATETC *)
0x180062266  test    eax, eax
0x180062268  jnz     short loc_18006226E
0x18006226a  xor     ebx, ebx
0x18006226c  jmp     short loc_18006227D
0x18006226e  xor     edx, edx
0x180062270  mov     ebx, 80070005h
0x180062275  mov     ecx, ebx
0x180062277  call    cs:__imp_RoOriginateError
0x18006227d  xor     edi, edi
0x18006227f  mov     [rsp+130h+TokenHandle], rdi
0x180062284  mov     [rsp+130h+ppv], rdi
0x180062289  test    ebx, ebx
0x18006228b  js      loc_1800623DE
0x180062291  mov     [rsp+130h+packageFullName], rdi
0x180062296  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006229a  mov     [rsp+130h+var_D0], rax
0x18006229f  mov     [rsp+130h+var_C8], rax
0x1800622a4  mov     [rsp+130h+ReturnLength], rdi; struct tagSTGMEDIUM *
0x1800622a9  lea     r9, [rsp+130h+packageFullName]; unsigned __int16 **
0x1800622ae  lea     r8, [rsp+130h+TokenHandle]; void **
0x1800622b3  movzx   edx, si; unsigned __int16
0x1800622b6  mov     rcx, r14; struct IDataObject *
0x1800622b9  call    ?s_ValidateCallerAndClipboardContent@CHtmlLocalFileResolver@@CAJPEAUIDataObject@@GPEAPEAXPEAPEAGPEAUtagSTGMEDIUM@@@Z; CHtmlLocalFileResolver::s_ValidateCallerAndClipboardContent(IDataObject *,ushort,void * *,ushort * *,tagSTGMEDIUM *)
0x1800622be  mov     ebx, eax
0x1800622c0  mov     rdi, [rsp+130h+packageFullName]
0x1800622c5  test    eax, eax
0x1800622c7  js      short loc_18006233B
0x1800622c9  xor     edx, edx; Val
0x1800622cb  mov     r8d, 82h; Size
0x1800622d1  lea     rcx, [rsp+130h+packageFamilyName]; void *
0x1800622d6  call    memset_0
0x1800622db  mov     [rsp+130h+packageFamilyNameLength], 41h ; 'A'
0x1800622e3  lea     r8, [rsp+130h+packageFamilyName]; packageFamilyName
0x1800622e8  lea     rdx, [rsp+130h+packageFamilyNameLength]; packageFamilyNameLength
0x1800622ed  mov     rcx, rdi; packageFullName
0x1800622f0  call    cs:__imp_PackageFamilyNameFromFullName
0x1800622f6  mov     ebx, eax
0x1800622f8  test    eax, eax
0x1800622fa  js      short loc_18006233B
0x1800622fc  mov     rcx, [rsp+130h+ppv]
0x180062301  test    rcx, rcx
0x180062304  jz      short loc_18006231C
0x180062306  mov     [rsp+130h+ppv], 0
0x18006230f  mov     rax, [rcx]
0x180062312  mov     rax, [rax+10h]
0x180062316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006231b  nop
0x18006231c  lea     rax, [rsp+130h+ppv]
0x180062321  mov     [rsp+130h+ReturnLength], rax; ppv
0x180062326  lea     r9, [rsp+130h+packageFamilyName]; int
0x18006232b  mov     r8d, r15d; int
0x18006232e  movzx   edx, si; int
0x180062331  mov     rcx, r14; int
0x180062334  call    ?CreateStorageItemVectorFromFormat@@YAJPEAUIDataObject@@GW4STORAGEITEM_CREATION_FLAGS@@PEBGPEAPEAU?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Z; CreateStorageItemVectorFromFormat(IDataObject *,ushort,STORAGEITEM_CREATION_FLAGS,ushort const *,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *> * *)
0x180062339  mov     ebx, eax
0x18006233b  test    rdi, rdi
0x18006233e  jz      short loc_180062349
0x180062340  mov     rcx, rdi; pv
0x180062343  call    cs:__imp_CoTaskMemFree
0x180062349  mov     rdi, [rsp+130h+TokenHandle]
0x18006234e  test    ebx, ebx
0x180062350  js      loc_1800623DE
0x180062356  mov     [rsp+130h+var_E8], 0
0x18006235e  mov     [rsp+130h+packageFamilyNameLength], 0
0x180062366  lea     rax, [rsp+130h+var_E8]
0x18006236b  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x180062370  mov     r9d, 4; TokenInformationLength
0x180062376  lea     r8, [rsp+130h+packageFamilyNameLength]; TokenInformation
0x18006237b  lea     edx, [r9+19h]; TokenInformationClass
0x18006237f  mov     rcx, rdi; TokenHandle
0x180062382  call    cs:__imp_GetTokenInformation
0x180062388  mov     rsi, [rsp+130h+var_F0]
0x18006238d  mov     [rsp+130h+packageFullName], rsi
0x180062392  test    rsi, rsi
0x180062395  jz      short loc_1800623A7
0x180062397  mov     rax, [rsi]
0x18006239a  mov     rcx, rsi
0x18006239d  mov     rax, [rax+8]
0x1800623a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623a6  nop
0x1800623a7  mov     [rsp+130h+var_D0], rdi
0x1800623ac  mov     eax, [rsp+130h+packageFamilyNameLength]
0x1800623b0  mov     dword ptr [rsp+130h+var_C8], eax
0x1800623b4  lea     rdx, [rsp+130h+packageFullName]
0x1800623b9  mov     rcx, [rsp+130h+ppv]
0x1800623be  call    IterateOverVector_Windows__Storage__IStorageItem__lambda_d01e397cc7e6270c25a33f459ef56c8a___
0x1800623c3  mov     ebx, eax
0x1800623c5  test    rsi, rsi
0x1800623c8  jz      short loc_1800623DA
0x1800623ca  mov     rax, [rsi]
0x1800623cd  mov     rcx, rsi
0x1800623d0  mov     rax, [rax+10h]
0x1800623d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623d9  nop
0x1800623da  test    ebx, ebx
0x1800623dc  jns     short loc_1800623F0
0x1800623de  mov     rcx, [rsp+130h+var_F0]
0x1800623e3  mov     rax, [rcx]
0x1800623e6  mov     rax, [rax+78h]
0x1800623ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623ef  nop
0x1800623f0  mov     rcx, [rsp+130h+ppv]
0x1800623f5  test    rcx, rcx
0x1800623f8  jz      short loc_180062410
0x1800623fa  mov     [rsp+130h+ppv], 0
0x180062403  mov     rax, [rcx]
0x180062406  mov     rax, [rax+10h]
0x18006240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006240f  nop
0x180062410  lea     rax, [rdi-1]
0x180062414  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180062418  ja      short loc_180062424
0x18006241a  mov     rcx, rdi; hObject
0x18006241d  call    cs:__imp_CloseHandle
0x180062423  nop
0x180062424  mov     rcx, [rsp+130h+var_F0]
0x180062429  test    rcx, rcx
0x18006242c  jz      short loc_180062444
0x18006242e  mov     [rsp+130h+var_F0], 0
0x180062437  mov     rax, [rcx]
0x18006243a  mov     rax, [rax+10h]
0x18006243e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062443  nop
0x180062444  mov     eax, ebx
0x180062446  mov     rcx, [rbp+30h+var_30]
0x18006244a  xor     rcx, rsp; StackCookie
0x18006244d  call    __security_check_cookie
0x180062452  mov     rbx, [rsp+130h+arg_0]
0x18006245a  add     rsp, 110h
0x180062461  pop     r15
0x180062463  pop     r14
0x180062465  pop     rdi
0x180062466  pop     rsi
0x180062467  pop     rbp
0x180062468  retn
```
