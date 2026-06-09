# StorageService::OfflineAppxVolumesIfMissing(std::vector<TrackedDevice,std::allocator<TrackedDevice>> const &)

- ea: `0x18002629c`
- end: `0x180026707`
- name: `?OfflineAppxVolumesIfMissing@StorageService@@AEAAJAEBV?$vector@UTrackedDevice@@V?$allocator@UTrackedDevice@@@std@@@std@@@Z`
- size: `1131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027080`

## callees

- `0x18000d030`
- `0x18000dd8c`
- `0x180012734`
- `0x180014a00`
- `0x18001ea50`
- `0x18001eae8`
- `0x18002629c`
- `0x18002c460`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180026520`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180026520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800264e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800265cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800264e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800265cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026513`

## string_xrefs

- `0x1800262ea`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x180026325`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x18002637c`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x180026604`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x180026636`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x18002665a`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`
- `0x180026691`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall StorageService::OfflineAppxVolumesIfMissing(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rdi
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  HRESULT v17; // eax
  const OLECHAR *StringRawBuffer; // rax
  _OWORD *i; // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v31; // [rsp+20h] [rbp-79h]
  _BYTE v32[8]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v33; // [rsp+38h] [rbp-61h] BYREF
  __int64 v34; // [rsp+40h] [rbp-59h] BYREF
  char v35; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v36[7]; // [rsp+49h] [rbp-50h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-49h] BYREF
  HSTRING string; // [rsp+58h] [rbp-41h] BYREF
  __int64 v39; // [rsp+60h] [rbp-39h] BYREF
  __int64 v40; // [rsp+68h] [rbp-31h] BYREF
  __int64 v41; // [rsp+70h] [rbp-29h] BYREF
  _OWORD Buf2[2]; // [rsp+78h] [rbp-21h] BYREF
  GUID iid; // [rsp+98h] [rbp-1h] BYREF
  HSTRING v44; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  Windows::Internal::StringReference::StringReference(&v44, (const unsigned __int16 (*)[45])a2);
  v41 = 0;
  v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>(
         v44,
         &v41);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x911,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)v3,
      v31);
    goto LABEL_57;
  }
  v34 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 88LL))(v41, &v34);
  v4 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x918,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)v5,
      v31);
    goto LABEL_5;
  }
  v33 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 48LL))(v34, &v33);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 2331;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)v7,
      v31);
    goto LABEL_10;
  }
  v32[0] = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 56LL))(v33, v32);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 2334;
    goto LABEL_9;
  }
  while ( 1 )
  {
    if ( !v32[0] )
    {
      v28 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v4 = 0;
      goto LABEL_57;
    }
    v37 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v33 + 48LL))(
            v33,
            &v37);
    v4 = v10;
    if ( v10 < 0 )
    {
      v11 = 2338;
      goto LABEL_50;
    }
    v35 = 0;
    v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*v37)[7])(v37, &v35);
    v4 = v10;
    if ( v10 < 0 )
    {
      v11 = 2341;
      goto LABEL_50;
    }
    if ( v35 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 64LL))(v33, v32);
      v4 = v10;
      if ( v10 >= 0 )
        goto LABEL_19;
      v11 = 2345;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
        (const char *)(unsigned int)v10,
        v31);
      goto LABEL_51;
    }
    v36[0] = 0;
    v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _BYTE *))(*v37)[6])(v37, v36);
    v4 = v10;
    if ( v10 < 0 )
    {
      v11 = 2350;
      goto LABEL_50;
    }
    if ( !v36[0] )
      break;
    v10 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 64LL))(v33, v32);
    v4 = v10;
    if ( v10 < 0 )
    {
      v11 = 2354;
      goto LABEL_50;
    }
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
  }
  v39 = 0;
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
  v13 = **v37;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  v14 = v13(v12, &GUID_d3e215de_c654_4759_9308_8be0d554881a, &v39);
  v4 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x937,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)v14,
      v31);
    goto LABEL_46;
  }
  string = 0;
  v15 = v39;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v17 = v16(v15, &string);
  v4 = v17;
  if ( v17 < 0 )
  {
    v26 = 2362;
    goto LABEL_43;
  }
  iid = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v17 = IIDFromString(StringRawBuffer, &iid);
  v4 = v17;
  if ( v17 < 0 )
  {
    v26 = 2365;
    goto LABEL_43;
  }
  for ( i = *(_OWORD **)a2; i != *(_OWORD **)(a2 + 8); i = (_OWORD *)((char *)i + 28) )
  {
    Buf2[0] = *i;
    *(_OWORD *)((char *)Buf2 + 12) = *(_OWORD *)((char *)i + 12);
    if ( !memcmp_0(&iid, (char *)Buf2 + 12, 0x10u) )
      goto LABEL_34;
  }
  v40 = 0;
  v20 = v41;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 136LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  v22 = v21(v20, v37, &v40);
  v4 = v22;
  if ( v22 < 0 )
  {
    v27 = 2382;
    goto LABEL_40;
  }
  v22 = Windows::Management::Deployment::WaitForDeploymentOperation(v23, v40, v24, v25, v31);
  v4 = v22;
  if ( v22 < 0 )
  {
    v27 = 2383;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)v22,
      v31);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    goto LABEL_44;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
LABEL_34:
  v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 64LL))(v33, v32);
  v4 = v17;
  if ( v17 >= 0 )
  {
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
    goto LABEL_19;
  }
  v26 = 2386;
LABEL_43:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v26,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
    (const char *)(unsigned int)v17,
    v31);
LABEL_44:
  WindowsDeleteString(string);
  string = 0;
LABEL_46:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
LABEL_51:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
LABEL_10:
  v9 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
LABEL_5:
  v6 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
LABEL_57:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
  return v4;
}

```

## disassembly

```asm
0x18002629c  push    rbp
0x18002629e  push    rbx
0x18002629f  push    rsi
0x1800262a0  push    rdi
0x1800262a1  push    r14
0x1800262a3  lea     rbp, [rsp-37h]
0x1800262a8  sub     rsp, 0D0h
0x1800262af  mov     rax, cs:__security_cookie
0x1800262b6  xor     rax, rsp
0x1800262b9  mov     [rbp+57h+var_28], rax
0x1800262bd  mov     rsi, rdx
0x1800262c0  lea     rcx, [rbp+57h+var_48]; string
0x1800262c4  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800262c9  xor     r14d, r14d
0x1800262cc  mov     [rbp+57h+var_80], r14
0x1800262d0  lea     rdx, [rbp+57h+var_80]
0x1800262d4  mov     rcx, [rbp+57h+var_48]
0x1800262d8  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager3@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager3@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager3>>)
0x1800262dd  mov     ebx, eax
0x1800262df  test    eax, eax
0x1800262e1  jns     short loc_180026300
0x1800262e3  mov     rcx, [rbp+5Fh]; this
0x1800262e7  mov     r9d, eax; char *
0x1800262ea  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800262f1  mov     edx, 911h; void *
0x1800262f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800262fb  jmp     loc_1800266E2
0x180026300  mov     [rbp+57h+var_B0], r14
0x180026304  mov     rcx, [rbp+57h+var_80]
0x180026308  mov     rax, [rcx]
0x18002630b  lea     rdx, [rbp+57h+var_B0]
0x18002630f  mov     rax, [rax+58h]
0x180026313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026318  mov     ebx, eax
0x18002631a  test    eax, eax
0x18002631c  jns     short loc_180026359
0x18002631e  mov     rcx, [rbp+5Fh]; this
0x180026322  mov     r9d, eax; char *
0x180026325  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002632c  mov     edx, 918h; void *
0x180026331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026336  nop
0x180026337  mov     rcx, [rbp+57h+var_B0]
0x18002633b  test    rcx, rcx
0x18002633e  jz      loc_1800266E2
0x180026344  mov     [rbp+57h+var_B0], r14
0x180026348  mov     rax, [rcx]
0x18002634b  mov     rax, [rax+10h]
0x18002634f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026354  jmp     loc_1800266E2
0x180026359  mov     [rbp+57h+var_B8], r14
0x18002635d  mov     rcx, [rbp+57h+var_B0]
0x180026361  mov     rax, [rcx]
0x180026364  lea     rdx, [rbp+57h+var_B8]
0x180026368  mov     rax, [rax+30h]
0x18002636c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026371  mov     ebx, eax
0x180026373  test    eax, eax
0x180026375  jns     short loc_1800263AB
0x180026377  mov     edx, 91Bh; void *
0x18002637c  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180026383  mov     r9d, eax; char *
0x180026386  mov     rcx, [rbp+5Fh]; this
0x18002638a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002638f  nop
0x180026390  mov     rcx, [rbp+57h+var_B8]
0x180026394  test    rcx, rcx
0x180026397  jz      short loc_180026337
0x180026399  mov     [rbp+57h+var_B8], r14
0x18002639d  mov     rax, [rcx]
0x1800263a0  mov     rax, [rax+10h]
0x1800263a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263a9  jmp     short loc_180026337
0x1800263ab  mov     [rbp+57h+var_C0], r14b
0x1800263af  mov     rcx, [rbp+57h+var_B8]
0x1800263b3  mov     rax, [rcx]
0x1800263b6  lea     rdx, [rbp+57h+var_C0]
0x1800263ba  mov     rax, [rax+38h]
0x1800263be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263c3  mov     ebx, eax
0x1800263c5  test    eax, eax
0x1800263c7  jns     short loc_1800263D0
0x1800263c9  mov     edx, 91Eh
0x1800263ce  jmp     short loc_18002637C
0x1800263d0  cmp     [rbp+57h+var_C0], r14b
0x1800263d4  jz      loc_1800266AC
0x1800263da  mov     [rbp+57h+var_A0], r14
0x1800263de  mov     rcx, [rbp+57h+var_B8]
0x1800263e2  mov     rax, [rcx]
0x1800263e5  lea     rdx, [rbp+57h+var_A0]
0x1800263e9  mov     rax, [rax+30h]
0x1800263ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263f2  mov     ebx, eax
0x1800263f4  test    eax, eax
0x1800263f6  js      loc_180026685
0x1800263fc  mov     [rbp+57h+var_A8], r14b
0x180026400  mov     rcx, [rbp+57h+var_A0]
0x180026404  mov     rax, [rcx]
0x180026407  lea     rdx, [rbp+57h+var_A8]
0x18002640b  mov     rax, [rax+38h]
0x18002640f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026414  mov     ebx, eax
0x180026416  test    eax, eax
0x180026418  js      loc_18002667E
0x18002641e  cmp     [rbp+57h+var_A8], r14b
0x180026422  jz      short loc_18002644D
0x180026424  mov     rcx, [rbp+57h+var_B8]
0x180026428  mov     rax, [rcx]
0x18002642b  lea     rdx, [rbp+57h+var_C0]
0x18002642f  mov     rax, [rax+40h]
0x180026433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026438  mov     ebx, eax
0x18002643a  test    eax, eax
0x18002643c  js      loc_1800265E7
0x180026442  lea     rcx, [rbp+57h+var_A0]
0x180026446  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002644b  jmp     short loc_1800263D0
0x18002644d  mov     [rbp+57h+var_A7], r14b
0x180026451  mov     rcx, [rbp+57h+var_A0]
0x180026455  mov     rax, [rcx]
0x180026458  lea     rdx, [rbp+57h+var_A7]
0x18002645c  mov     rax, [rax+30h]
0x180026460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026465  mov     ebx, eax
0x180026467  test    eax, eax
0x180026469  js      loc_180026677
0x18002646f  cmp     [rbp+57h+var_A7], r14b
0x180026473  jz      short loc_180026499
0x180026475  mov     rcx, [rbp+57h+var_B8]
0x180026479  mov     rax, [rcx]
0x18002647c  lea     rdx, [rbp+57h+var_C0]
0x180026480  mov     rax, [rax+40h]
0x180026484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026489  mov     ebx, eax
0x18002648b  test    eax, eax
0x18002648d  jns     short loc_180026442
0x18002648f  mov     edx, 932h
0x180026494  jmp     loc_18002668A
0x180026499  mov     [rbp+57h+var_90], r14
0x18002649d  mov     rbx, [rbp+57h+var_A0]
0x1800264a1  mov     rax, [rbx]
0x1800264a4  mov     rdi, [rax]
0x1800264a7  lea     rcx, [rbp+57h+var_90]
0x1800264ab  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800264b0  lea     r8, [rbp+57h+var_90]
0x1800264b4  lea     rdx, _GUID_d3e215de_c654_4759_9308_8be0d554881a
0x1800264bb  mov     rcx, rbx
0x1800264be  mov     rax, rdi
0x1800264c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264c6  mov     ebx, eax
0x1800264c8  test    eax, eax
0x1800264ca  js      loc_180026653
0x1800264d0  mov     [rbp+57h+string], r14
0x1800264d4  mov     rdi, [rbp+57h+var_90]
0x1800264d8  mov     rax, [rdi]
0x1800264db  mov     rbx, [rax+30h]
0x1800264df  mov     rcx, [rbp+57h+string]; string
0x1800264e3  call    cs:__imp_WindowsDeleteString
0x1800264e9  mov     [rbp+57h+string], r14
0x1800264ed  lea     rdx, [rbp+57h+string]
0x1800264f1  mov     rcx, rdi
0x1800264f4  mov     rax, rbx
0x1800264f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264fc  mov     ebx, eax
0x1800264fe  test    eax, eax
0x180026500  js      loc_18002662A
0x180026506  xorps   xmm0, xmm0
0x180026509  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18002650d  xor     edx, edx; length
0x18002650f  mov     rcx, [rbp+57h+string]; string
0x180026513  call    cs:__imp_WindowsGetStringRawBuffer
0x180026519  lea     rdx, [rbp+57h+iid]; lpiid
0x18002651d  mov     rcx, rax; lpsz
0x180026520  call    cs:__imp_IIDFromString
0x180026526  mov     ebx, eax
0x180026528  test    eax, eax
0x18002652a  js      loc_180026623
0x180026530  mov     rbx, [rsi]
0x180026533  jmp     short loc_18002655F
0x180026535  movups  xmm0, xmmword ptr [rbx]
0x180026538  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x18002653c  movups  xmm1, xmmword ptr [rbx+0Ch]
0x180026540  movups  xmmword ptr [rbp+57h+Buf2+0Ch], xmm1
0x180026544  mov     r8d, 10h; Size
0x18002654a  lea     rdx, [rbp+57h+Buf2+0Ch]; Buf2
0x18002654e  lea     rcx, [rbp+57h+iid]; Buf1
0x180026552  call    memcmp_0
0x180026557  test    eax, eax
0x180026559  jz      short loc_1800265B1
0x18002655b  add     rbx, 1Ch
0x18002655f  cmp     rbx, [rsi+8]
0x180026563  jnz     short loc_180026535
0x180026565  mov     [rbp+57h+var_88], r14
0x180026569  mov     rdi, [rbp+57h+var_80]
0x18002656d  mov     rax, [rdi]
0x180026570  mov     rbx, [rax+88h]
0x180026577  lea     rcx, [rbp+57h+var_88]
0x18002657b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026580  lea     r8, [rbp+57h+var_88]
0x180026584  mov     rdx, [rbp+57h+var_A0]
0x180026588  mov     rcx, rdi
0x18002658b  mov     rax, rbx
0x18002658e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026593  mov     ebx, eax
0x180026595  test    eax, eax
0x180026597  js      short loc_1800265FF
0x180026599  mov     rdx, [rbp+57h+var_88]
0x18002659d  call    ?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z; Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)
0x1800265a2  mov     ebx, eax
0x1800265a4  test    eax, eax
0x1800265a6  js      short loc_1800265F8
0x1800265a8  lea     rcx, [rbp+57h+var_88]
0x1800265ac  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800265b1  mov     rcx, [rbp+57h+var_B8]
0x1800265b5  mov     rax, [rcx]
0x1800265b8  lea     rdx, [rbp+57h+var_C0]
0x1800265bc  mov     rax, [rax+40h]
0x1800265c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265c5  mov     ebx, eax
0x1800265c7  test    eax, eax
0x1800265c9  js      short loc_1800265F1
0x1800265cb  mov     rcx, [rbp+57h+string]; string
0x1800265cf  call    cs:__imp_WindowsDeleteString
0x1800265d5  mov     [rbp+57h+string], r14
0x1800265d9  lea     rcx, [rbp+57h+var_90]
0x1800265dd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800265e2  jmp     loc_180026442
0x1800265e7  mov     edx, 929h
0x1800265ec  jmp     loc_18002668A
0x1800265f1  mov     edx, 952h
0x1800265f6  jmp     short loc_18002662F
0x1800265f8  mov     edx, 94Fh
0x1800265fd  jmp     short loc_180026604
0x1800265ff  mov     edx, 94Eh; void *
0x180026604  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002660b  mov     r9d, eax; char *
0x18002660e  mov     rcx, [rbp+5Fh]; this
0x180026612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026617  nop
0x180026618  lea     rcx, [rbp+57h+var_88]
0x18002661c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026621  jmp     short loc_180026643
0x180026623  mov     edx, 93Dh
0x180026628  jmp     short loc_18002662F
0x18002662a  mov     edx, 93Ah; void *
0x18002662f  mov     rcx, [rbp+5Fh]; this
0x180026633  mov     r9d, eax; char *
0x180026636  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002663d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026642  nop
0x180026643  mov     rcx, [rbp+57h+string]; string
0x180026647  call    cs:__imp_WindowsDeleteString
0x18002664d  mov     [rbp+57h+string], r14
0x180026651  jmp     short loc_18002666C
0x180026653  mov     rcx, [rbp+5Fh]; this
0x180026657  mov     r9d, eax; char *
0x18002665a  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180026661  mov     edx, 937h; void *
0x180026666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002666b  nop
0x18002666c  lea     rcx, [rbp+57h+var_90]
0x180026670  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180026675  jmp     short loc_18002669E
0x180026677  mov     edx, 92Eh
0x18002667c  jmp     short loc_18002668A
0x18002667e  mov     edx, 925h
0x180026683  jmp     short loc_18002668A
0x180026685  mov     edx, 922h; void *
0x18002668a  mov     rcx, [rbp+5Fh]; this
0x18002668e  mov     r9d, eax; char *
0x180026691  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180026698  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002669d  nop
0x18002669e  lea     rcx, [rbp+57h+var_A0]
0x1800266a2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800266a7  jmp     loc_180026390
0x1800266ac  mov     rcx, [rbp+57h+var_B8]
0x1800266b0  test    rcx, rcx
0x1800266b3  jz      short loc_1800266C6
0x1800266b5  mov     [rbp+57h+var_B8], r14
0x1800266b9  mov     rax, [rcx]
0x1800266bc  mov     rax, [rax+10h]
0x1800266c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266c5  nop
0x1800266c6  mov     rcx, [rbp+57h+var_B0]
0x1800266ca  test    rcx, rcx
0x1800266cd  jz      short loc_1800266DF
0x1800266cf  mov     [rbp+57h+var_B0], r14
0x1800266d3  mov     rax, [rcx]
0x1800266d6  mov     rax, [rax+10h]
0x1800266da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266df  mov     ebx, r14d
0x1800266e2  lea     rcx, [rbp+57h+var_80]
0x1800266e6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800266eb  mov     eax, ebx
0x1800266ed  mov     rcx, [rbp+57h+var_28]
0x1800266f1  xor     rcx, rsp; StackCookie
0x1800266f4  call    __security_check_cookie
0x1800266f9  add     rsp, 0D0h
0x180026700  pop     r14
  ... truncated ...
```
