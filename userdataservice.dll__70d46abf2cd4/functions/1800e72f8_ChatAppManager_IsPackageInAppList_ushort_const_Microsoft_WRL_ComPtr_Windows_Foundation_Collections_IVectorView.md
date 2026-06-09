# ChatAppManager::_IsPackageInAppList(ushort const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *>> const &,int *)

- ea: `0x1800e72f8`
- end: `0x1800e74c0`
- name: `?_IsPackageInAppList@ChatAppManager@@CAJPEBGAEBV?$ComPtr@U?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAH@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180095a94`

## callees

- `0x180004658`
- `0x180008f0c`
- `0x1800e72f8`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e73bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e744b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e748d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e73bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7429`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e744b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e748d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e73ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e73ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e73ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e73ff`

## string_xrefs

- `0x1800e732b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e7476`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x1800e749f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`

## pseudocode

```c
__int64 __fastcall ChatAppManager::_IsPackageInAppList(char *a1, __int64 *a2, _DWORD *a3)
{
  __int64 v6; // r9
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v10; // rcx
  unsigned int i; // r14d
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING v19; // rcx
  char *v20; // rax
  char *v21; // rcx
  int v22; // r8d
  int v23; // edx
  unsigned int v24; // [rsp+70h] [rbp+40h] BYREF
  HSTRING string; // [rsp+80h] [rbp+50h] BYREF
  __int64 v26; // [rsp+88h] [rbp+58h] BYREF

  *a3 = 0;
  if ( !a1 )
  {
    v6 = 360;
    v7 = 0;
    v8 = -2147024809;
LABEL_3:
    Log_HREvent(
      v8,
      v7,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
      v6);
    return v8;
  }
  v10 = *a2;
  v24 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v10 + 56LL))(v10, &v24);
  if ( (v8 & 0x80000000) != 0 )
  {
    v6 = 364;
    v7 = 1;
    goto LABEL_3;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v24 )
      return 0;
    v26 = 0;
    v12 = *a2;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a2 + 48LL);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v26);
    v14 = v13(v12, i, &v26);
    v8 = v14;
    if ( v14 < 0 )
      break;
    v15 = v26;
    string = 0;
    v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 72LL);
    WindowsDeleteString(0);
    string = 0;
    v17 = v16(v15, &string);
    v8 = v17;
    if ( v17 < 0 )
    {
      Log_HREvent(
        (unsigned int)v17,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
        372);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_21;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v19 = string;
    if ( StringRawBuffer )
    {
      v20 = (char *)((char *)WindowsGetStringRawBuffer(string, 0) - a1);
      v21 = a1;
      do
      {
        v22 = *(unsigned __int16 *)&v20[(_QWORD)v21];
        v23 = *(unsigned __int16 *)v21 - v22;
        if ( v23 )
          break;
        v21 += 2;
      }
      while ( v22 );
      v19 = string;
      if ( !v23 )
      {
        *a3 = 1;
        WindowsDeleteString(v19);
        string = 0;
        Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v26);
        return 0;
      }
    }
    WindowsDeleteString(v19);
    string = 0;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v26);
  }
  Log_HREvent(
    (unsigned int)v14,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
    369);
LABEL_21:
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v26);
  return v8;
}

```

## disassembly

```asm
0x1800e72f8  push    rbp
0x1800e72fa  push    rbx
0x1800e72fb  push    rdi
0x1800e72fc  push    r12
0x1800e72fe  push    r13
0x1800e7300  push    r14
0x1800e7302  push    r15
0x1800e7304  mov     rbp, rsp
0x1800e7307  sub     rsp, 30h
0x1800e730b  xor     edi, edi
0x1800e730d  mov     r15, r8
0x1800e7310  mov     [r8], edi
0x1800e7313  mov     r13, rdx
0x1800e7316  mov     r12, rcx
0x1800e7319  test    rcx, rcx
0x1800e731c  jnz     short loc_1800E7340
0x1800e731e  mov     r9d, 168h
0x1800e7324  xor     edx, edx
0x1800e7326  mov     ebx, 80070057h
0x1800e732b  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e7332  mov     ecx, ebx
0x1800e7334  call    Log_HREvent
0x1800e7339  mov     eax, ebx
0x1800e733b  jmp     loc_1800E7460
0x1800e7340  mov     rcx, [rdx]
0x1800e7343  lea     rdx, [rbp+arg_0]
0x1800e7347  mov     [rbp+arg_0], edi
0x1800e734a  mov     rax, [rcx]
0x1800e734d  mov     rax, [rax+38h]
0x1800e7351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7356  mov     ebx, eax
0x1800e7358  test    eax, eax
0x1800e735a  jns     short loc_1800E7369
0x1800e735c  mov     r9d, 16Ch
0x1800e7362  mov     edx, 1
0x1800e7367  jmp     short loc_1800E732B
0x1800e7369  mov     r14d, edi
0x1800e736c  cmp     r14d, [rbp+arg_0]
0x1800e7370  jnb     loc_1800E745E
0x1800e7376  mov     [rbp+arg_18], rdi
0x1800e737a  lea     rcx, [rbp+arg_18]
0x1800e737e  mov     rdi, [r13+0]
0x1800e7382  mov     rax, [rdi]
0x1800e7385  mov     rbx, [rax+30h]
0x1800e7389  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800e738e  lea     r8, [rbp+arg_18]
0x1800e7392  mov     edx, r14d
0x1800e7395  mov     rcx, rdi
0x1800e7398  mov     rax, rbx
0x1800e739b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e73a0  mov     ebx, eax
0x1800e73a2  test    eax, eax
0x1800e73a4  js      loc_1800E7499
0x1800e73aa  mov     rdi, [rbp+arg_18]
0x1800e73ae  xor     ecx, ecx; string
0x1800e73b0  mov     [rbp+string], 0
0x1800e73b8  mov     rax, [rdi]
0x1800e73bb  mov     rbx, [rax+48h]
0x1800e73bf  call    cs:__imp_WindowsDeleteString
0x1800e73c5  lea     rdx, [rbp+string]
0x1800e73c9  mov     [rbp+string], 0
0x1800e73d1  mov     rcx, rdi
0x1800e73d4  mov     rax, rbx
0x1800e73d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e73dc  xor     edi, edi
0x1800e73de  mov     ebx, eax
0x1800e73e0  test    eax, eax
0x1800e73e2  js      loc_1800E7470
0x1800e73e8  mov     rcx, [rbp+string]; string
0x1800e73ec  xor     edx, edx; length
0x1800e73ee  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e73f4  mov     rcx, [rbp+string]; string
0x1800e73f8  test    rax, rax
0x1800e73fb  jz      short loc_1800E7429
0x1800e73fd  xor     edx, edx; length
0x1800e73ff  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e7405  sub     rax, r12
0x1800e7408  mov     rcx, r12
0x1800e740b  movzx   edx, word ptr [rcx]
0x1800e740e  movzx   r8d, word ptr [rcx+rax]
0x1800e7413  sub     edx, r8d
0x1800e7416  jnz     short loc_1800E7421
0x1800e7418  add     rcx, 2
0x1800e741c  test    r8d, r8d
0x1800e741f  jnz     short loc_1800E740B
0x1800e7421  mov     rcx, [rbp+string]; string
0x1800e7425  test    edx, edx
0x1800e7427  jz      short loc_1800E7444
0x1800e7429  call    cs:__imp_WindowsDeleteString
0x1800e742f  lea     rcx, [rbp+arg_18]
0x1800e7433  mov     [rbp+string], rdi
0x1800e7437  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800e743c  inc     r14d
0x1800e743f  jmp     loc_1800E736C
0x1800e7444  mov     dword ptr [r15], 1
0x1800e744b  call    cs:__imp_WindowsDeleteString
0x1800e7451  lea     rcx, [rbp+arg_18]
0x1800e7455  mov     [rbp+string], rdi
0x1800e7459  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800e745e  xor     eax, eax
0x1800e7460  add     rsp, 30h
0x1800e7464  pop     r15
0x1800e7466  pop     r14
0x1800e7468  pop     r13
0x1800e746a  pop     r12
0x1800e746c  pop     rdi
0x1800e746d  pop     rbx
0x1800e746e  pop     rbp
0x1800e746f  retn
0x1800e7470  mov     r9d, 174h
0x1800e7476  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e747d  mov     edx, 1
0x1800e7482  mov     ecx, eax
0x1800e7484  call    Log_HREvent
0x1800e7489  mov     rcx, [rbp+string]; string
0x1800e748d  call    cs:__imp_WindowsDeleteString
0x1800e7493  mov     [rbp+string], rdi
0x1800e7497  jmp     short loc_1800E74B2
0x1800e7499  mov     r9d, 171h
0x1800e749f  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e74a6  mov     edx, 1
0x1800e74ab  mov     ecx, eax
0x1800e74ad  call    Log_HREvent
0x1800e74b2  lea     rcx, [rbp+arg_18]
0x1800e74b6  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800e74bb  jmp     loc_1800E7339
```
