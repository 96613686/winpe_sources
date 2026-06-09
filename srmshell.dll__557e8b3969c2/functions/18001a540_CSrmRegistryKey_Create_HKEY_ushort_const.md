# CSrmRegistryKey::Create(HKEY__ *,ushort const *,...)

- ea: `0x18001a540`
- end: `0x18001a9f1`
- name: `?Create@CSrmRegistryKey@@QEAAXPEAUHKEY__@@PEBGZZ`
- size: `1201`
- prototype: `void(CSrmRegistryKey *__hidden this, HKEY hKey, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800079e0`

## callees

- `0x1800083e0`
- `0x18000d368`
- `0x1800161e8`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x180019b84`
- `0x18001a384`
- `0x18001a540`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18001a60c`
- `msvcrt!_vsnwprintf` at `0x18001a60c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a763`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a763`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a690`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a690`

## string_xrefs

- `0x18001a590`: `CSrmRegistryKey::Create`
- `0x18001a584`: `base\fs\fsrm\utilities\registry\srmreg.cpp`

## pseudocode

```c
void CSrmRegistryKey::Create(CSrmRegistryKey *this, HKEY hKey, const unsigned __int16 *a3, ...)
{
  unsigned int v5; // eax
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rcx
  wchar_t *v9; // rdi
  unsigned __int64 v10; // rdx
  signed int v11; // ecx
  __int64 v12; // rcx
  wchar_t *v13; // r8
  wchar_t *v14; // rax
  wchar_t v15; // r9
  wchar_t *v16; // rcx
  char v17; // al
  int v18; // eax
  char v19; // al
  unsigned int Hr; // ebx
  __int64 v21; // rax
  int v22; // eax
  char v23; // al
  char v24; // al
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  void **v26; // [rsp+58h] [rbp-A8h]
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v28; // [rsp+68h] [rbp-98h]
  _QWORD v29[3]; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+88h] [rbp-78h]
  int v31; // [rsp+8Ch] [rbp-74h]
  int v32; // [rsp+90h] [rbp-70h]
  char v33[96]; // [rsp+98h] [rbp-68h] BYREF
  int v34; // [rsp+F8h] [rbp-8h]
  _QWORD v35[3]; // [rsp+100h] [rbp+0h] BYREF
  int v36; // [rsp+118h] [rbp+18h]
  int v37; // [rsp+11Ch] [rbp+1Ch]
  int v38; // [rsp+120h] [rbp+20h]
  char v39[96]; // [rsp+128h] [rbp+28h] BYREF
  int v40; // [rsp+188h] [rbp+88h]
  _BYTE v41[144]; // [rsp+190h] [rbp+90h] BYREF
  void **v42; // [rsp+220h] [rbp+120h] BYREF
  int v43; // [rsp+228h] [rbp+128h]
  void **v44; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v45; // [rsp+2D8h] [rbp+1D8h]
  wchar_t Buffer[259]; // [rsp+380h] [rbp+280h] BYREF
  __int16 v47; // [rsp+586h] [rbp+486h]
  va_list Args; // [rsp+5F8h] [rbp+4F8h] BYREF

  va_start(Args, a3);
  v29[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
  v29[1] = L"CSrmRegistryKey::Create";
  v29[2] = L"SRMREGSC";
  v30 = 62;
  v31 = 17;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v42, (const struct CSrmDebugInfo *)v29, 0);
  v28 = 0;
  v5 = _vsnwprintf(Buffer, 0x103u, a3, Args);
  if ( v5 >= 0x104 )
  {
    v47 = 0;
    v43 = -2147024774;
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v42);
    v28 = v41;
    v21 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v41,
            (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
            (__int64)L"SRMREGSC",
            (__int64)L"CSrmRegistryKey::Create",
            74,
            17);
    CSrmFunctionTracer::TranslateGenericError(&v42, v21, Hr, L"StringCchVPrintfW()");
  }
  v43 = 0;
  if ( v5 == 259 )
    v47 = 0;
  v26 = &CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable';
  dwDisposition = 0;
  phkResult = 0;
  v6 = RegCreateKeyExW(hKey, Buffer, 0, 0, *((_DWORD *)this + 1), *(_DWORD *)this, 0, &phkResult, &dwDisposition);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  v43 = v6;
  if ( v6 < 0 )
  {
    v22 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v42);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v42, v22);
    v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v42);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v42, 0x5Au, v23, 0);
  }
  v43 = v6;
  if ( dwDisposition == 2 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v42, -2147200253);
    v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v42);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v42, 0x5Cu, v17, 0);
  }
  v43 = 0;
  CSrmRegistryKey::Close(this);
  v28 = v35;
  v35[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h";
  v35[1] = L"SrmDuplicateStr";
  v35[2] = L"INCLSTRH";
  v36 = 78;
  v37 = 17;
  v38 = 255;
  v40 = 0x1000000;
  memset_0(v39, 0, sizeof(v39));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v44, (const struct CSrmDebugInfo *)v35, 0);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( Buffer[v8] );
  v9 = (wchar_t *)CoTaskMemAlloc(2 * v8 + 2);
  if ( !v9 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v44, -2147024882);
    v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v44, 0x57u, v24, 0);
  }
  v45 = 0;
  do
    ++v7;
  while ( Buffer[v7] );
  v10 = v7 + 1;
  v11 = -2147024809;
  if ( v7 != -1 )
  {
    if ( v10 > 0x7FFFFFFF )
    {
      *v9 = 0;
      v45 = -2147024809;
LABEL_26:
      v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v44, v18);
      v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v44);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v44, 0x59u, v19, 0);
    }
    v12 = 2147483646;
    v13 = Buffer;
    v14 = v9;
    do
    {
      if ( !v12 )
        break;
      v15 = *v13;
      if ( !*v13 )
        break;
      ++v13;
      *v14++ = v15;
      --v12;
      --v10;
    }
    while ( v10 );
    v16 = v14 - 1;
    if ( v10 )
      v16 = v14;
    *v16 = 0;
    v11 = v10 == 0 ? 0x8007007A : 0;
  }
  v45 = v11;
  if ( v11 < 0 )
    goto LABEL_26;
  v45 = v11;
  v44 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v44);
  CoTaskMemFree(*((LPVOID *)this + 2));
  *((_QWORD *)this + 2) = v9;
  *((_QWORD *)this + 1) = phkResult;
  v26 = &CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&public: static HKEY__ * & DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable';
  phkResult = 0;
  v42 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v42);
}

```

## disassembly

```asm
0x18001a540  mov     [rsp-8+Format], r8
0x18001a545  mov     qword ptr [rsp-8+Args], r9
0x18001a54a  push    rbp
0x18001a54b  push    rbx
0x18001a54c  push    rsi
0x18001a54d  push    rdi
0x18001a54e  push    r12
0x18001a550  push    r14
0x18001a552  push    r15
0x18001a554  lea     rbp, [rsp-4A0h]
0x18001a55c  sub     rsp, 5A0h
0x18001a563  mov     rax, cs:__security_cookie
0x18001a56a  xor     rax, rsp
0x18001a56d  mov     [rbp+4D0h+var_40], rax
0x18001a574  mov     rbx, rdx
0x18001a577  mov     rsi, rcx
0x18001a57a  lea     rax, [rsp+5D0h+var_560]
0x18001a57f  mov     [rsp+5D0h+var_568], rax
0x18001a584  lea     r15, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001a58b  mov     [rsp+5D0h+var_560], r15
0x18001a590  lea     r12, aCsrmregistryke_3; "CSrmRegistryKey::Create"
0x18001a597  mov     [rsp+5D0h+var_558], r12
0x18001a59c  lea     rax, aSrmregsc; "SRMREGSC"
0x18001a5a3  mov     [rbp+4D0h+var_550], rax
0x18001a5a7  mov     [rbp+4D0h+var_548], 3Eh ; '>'
0x18001a5ae  mov     [rbp+4D0h+var_544], 11h
0x18001a5b5  mov     [rbp+4D0h+var_540], 0FFh
0x18001a5bc  xor     r14d, r14d
0x18001a5bf  mov     [rbp+4D0h+var_4D8], 1000000h
0x18001a5c6  xor     edx, edx; Val
0x18001a5c8  lea     r8d, [r14+60h]; Size
0x18001a5cc  lea     rcx, [rbp+4D0h+var_538]; void *
0x18001a5d0  call    memset_0
0x18001a5d5  nop
0x18001a5d6  xor     r8d, r8d
0x18001a5d9  lea     rdx, [rsp+5D0h+var_560]
0x18001a5de  lea     rcx, [rbp+4D0h+var_3B0]
0x18001a5e5  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001a5ea  nop
0x18001a5eb  mov     [rsp+5D0h+var_568], r14
0x18001a5f0  lea     r9, [rbp+4D0h+Args]; Args
0x18001a5f7  mov     r8, [rbp+4D0h+Format]; Format
0x18001a5fe  mov     edi, 103h
0x18001a603  mov     edx, edi; BufferCount
0x18001a605  lea     rcx, [rbp+4D0h+Buffer]; Buffer
0x18001a60c  call    cs:__imp__vsnwprintf
0x18001a612  test    eax, eax
0x18001a614  js      loc_18001A910
0x18001a61a  cmp     eax, edi
0x18001a61c  ja      loc_18001A910
0x18001a622  mov     [rbp+4D0h+var_3A8], r14d
0x18001a629  jnz     short loc_18001A633
0x18001a62b  mov     [rbp+4D0h+var_4A], r14w
0x18001a633  lea     r15, ??_7?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable'
0x18001a63a  mov     [rsp+5D0h+var_578], r15
0x18001a63f  mov     [rsp+5D0h+var_570], r14
0x18001a644  lea     r12, ??_7?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x18001a64b  mov     [rsp+5D0h+var_578], r12
0x18001a650  mov     [rsp+5D0h+dwDisposition], r14d
0x18001a655  mov     [rsp+5D0h+var_570], r14
0x18001a65a  lea     rax, [rsp+5D0h+dwDisposition]
0x18001a65f  mov     [rsp+5D0h+lpdwDisposition], rax; lpdwDisposition
0x18001a664  lea     rax, [rsp+5D0h+var_570]
0x18001a669  mov     [rsp+5D0h+phkResult], rax; phkResult
0x18001a66e  mov     [rsp+5D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001a673  mov     eax, [rsi]
0x18001a675  mov     [rsp+5D0h+samDesired], eax; samDesired
0x18001a679  mov     eax, [rsi+4]
0x18001a67c  mov     [rsp+5D0h+dwOptions], eax; dwOptions
0x18001a680  xor     r9d, r9d; lpClass
0x18001a683  xor     r8d, r8d; Reserved
0x18001a686  lea     rdx, [rbp+4D0h+Buffer]; lpSubKey
0x18001a68d  mov     rcx, rbx; hKey
0x18001a690  call    cs:__imp_RegCreateKeyExW
0x18001a696  test    eax, eax
0x18001a698  jle     short loc_18001A6A2
0x18001a69a  movzx   eax, ax
0x18001a69d  or      eax, 80070000h
0x18001a6a2  mov     [rbp+4D0h+var_3A8], eax
0x18001a6a8  test    eax, eax
0x18001a6aa  js      loc_18001A980
0x18001a6b0  mov     [rbp+4D0h+var_3A8], eax
0x18001a6b6  mov     [rbp+4D0h+var_3A8], eax
0x18001a6bc  cmp     [rsp+5D0h+dwDisposition], 2
0x18001a6c1  jz      loc_18001A895
0x18001a6c7  mov     [rbp+4D0h+var_3A8], r14d
0x18001a6ce  mov     rcx, rsi; this
0x18001a6d1  call    ?Close@CSrmRegistryKey@@QEAAXXZ; CSrmRegistryKey::Close(void)
0x18001a6d6  lea     rax, [rbp+4D0h+var_4D0]
0x18001a6da  mov     [rsp+5D0h+var_568], rax
0x18001a6df  lea     rax, aBaseFsFsrmUtil_0; "base\\fs\\fsrm\\utilities\\inc\\srmstr."...
0x18001a6e6  mov     [rbp+4D0h+var_4D0], rax
0x18001a6ea  lea     rax, aSrmduplicatest; "SrmDuplicateStr"
0x18001a6f1  mov     [rbp+4D0h+var_4C8], rax
0x18001a6f5  lea     rax, aInclstrh; "INCLSTRH"
0x18001a6fc  mov     [rbp+4D0h+var_4C0], rax
0x18001a700  mov     [rbp+4D0h+var_4B8], 4Eh ; 'N'
0x18001a707  mov     [rbp+4D0h+var_4B4], 11h
0x18001a70e  mov     [rbp+4D0h+var_4B0], 0FFh
0x18001a715  mov     [rbp+4D0h+var_448], 1000000h
0x18001a71f  xor     edx, edx; Val
0x18001a721  lea     r8d, [rdx+60h]; Size
0x18001a725  lea     rcx, [rbp+4D0h+var_4A8]; void *
0x18001a729  call    memset_0
0x18001a72e  nop
0x18001a72f  xor     r8d, r8d
0x18001a732  lea     rdx, [rbp+4D0h+var_4D0]
0x18001a736  lea     rcx, [rbp+4D0h+var_300]
0x18001a73d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001a742  nop
0x18001a743  lea     rax, [rbp+4D0h+Buffer]
0x18001a74a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001a74e  mov     rcx, rbx
0x18001a751  inc     rcx
0x18001a754  cmp     [rax+rcx*2], r14w
0x18001a759  jnz     short loc_18001A751
0x18001a75b  lea     rcx, ds:2[rcx*2]; cb
0x18001a763  call    cs:__imp_CoTaskMemAlloc
0x18001a769  mov     rdi, rax
0x18001a76c  mov     ecx, [rbp+4D0h+var_2F8]
0x18001a772  mov     [rbp+4D0h+var_2F8], ecx
0x18001a778  test    rax, rax
0x18001a77b  jz      loc_18001A9BD
0x18001a781  mov     [rbp+4D0h+var_2F8], r14d
0x18001a788  lea     rax, [rbp+4D0h+Buffer]
0x18001a78f  inc     rbx
0x18001a792  cmp     [rax+rbx*2], r14w
0x18001a797  jnz     short loc_18001A78F
0x18001a799  lea     rdx, [rbx+1]
0x18001a79d  mov     ecx, 80070057h
0x18001a7a2  test    rdx, rdx
0x18001a7a5  jz      short loc_18001A803
0x18001a7a7  cmp     rdx, 7FFFFFFFh
0x18001a7ae  ja      loc_18001A8C9
0x18001a7b4  mov     ecx, 7FFFFFFEh
0x18001a7b9  lea     r8, [rbp+4D0h+Buffer]
0x18001a7c0  mov     rax, rdi
0x18001a7c3  test    rcx, rcx
0x18001a7c6  jz      short loc_18001A7E7
0x18001a7c8  movzx   r9d, word ptr [r8]
0x18001a7cc  test    r9w, r9w
0x18001a7d0  jz      short loc_18001A7E7
0x18001a7d2  add     r8, 2
0x18001a7d6  mov     [rax], r9w
0x18001a7da  add     rax, 2
0x18001a7de  dec     rcx
0x18001a7e1  sub     rdx, 1
0x18001a7e5  jnz     short loc_18001A7C3
0x18001a7e7  lea     rcx, [rax-2]
0x18001a7eb  test    rdx, rdx
0x18001a7ee  cmovnz  rcx, rax
0x18001a7f2  mov     [rcx], r14w
0x18001a7f6  neg     rdx
0x18001a7f9  sbb     ecx, ecx
0x18001a7fb  not     ecx
0x18001a7fd  and     ecx, 8007007Ah
0x18001a803  mov     [rbp+4D0h+var_2F8], ecx
0x18001a809  test    ecx, ecx
0x18001a80b  js      loc_18001A8D3
0x18001a811  mov     [rbp+4D0h+var_2F8], ecx
0x18001a817  lea     rbx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001a81e  mov     [rbp+4D0h+var_300], rbx
0x18001a825  lea     rcx, [rbp+4D0h+var_300]; this
0x18001a82c  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001a831  mov     rcx, [rsi+10h]; pv
0x18001a835  call    cs:__imp_CoTaskMemFree
0x18001a83b  mov     [rsi+10h], rdi
0x18001a83f  mov     rax, [rsp+5D0h+var_570]
0x18001a844  mov     [rsp+5D0h+var_570], r14
0x18001a849  mov     [rsi+8], rax
0x18001a84d  mov     [rsp+5D0h+var_578], r12
0x18001a852  mov     [rsp+5D0h+var_570], r14
0x18001a857  mov     [rsp+5D0h+var_578], r15
0x18001a85c  mov     [rsp+5D0h+var_570], r14
0x18001a861  mov     [rbp+4D0h+var_3B0], rbx
0x18001a868  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a86f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001a874  mov     rcx, [rbp+4D0h+var_40]
0x18001a87b  xor     rcx, rsp; StackCookie
0x18001a87e  call    __security_check_cookie
0x18001a883  add     rsp, 5A0h
0x18001a88a  pop     r15
0x18001a88c  pop     r14
0x18001a88e  pop     r12
0x18001a890  pop     rdi
0x18001a891  pop     rsi
0x18001a892  pop     rbx
0x18001a893  pop     rbp
0x18001a894  retn
0x18001a895  mov     edx, 80045303h; int
0x18001a89a  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a8a1  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001a8a6  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a8ad  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001a8b2  mov     r8d, eax; char
0x18001a8b5  xor     r9d, r9d; unsigned __int16 *
0x18001a8b8  lea     edx, [r9+5Ch]; unsigned int
0x18001a8bc  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a8c3  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18001a8c9  mov     [rdi], r14w
0x18001a8cd  mov     [rbp+4D0h+var_2F8], ecx
0x18001a8d3  lea     rcx, [rbp+4D0h+var_300]; this
0x18001a8da  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001a8df  mov     edx, eax; int
0x18001a8e1  lea     rcx, [rbp+4D0h+var_300]; this
0x18001a8e8  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001a8ed  lea     rcx, [rbp+4D0h+var_300]; this
0x18001a8f4  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001a8f9  mov     r8d, eax; char
0x18001a8fc  xor     r9d, r9d; unsigned __int16 *
0x18001a8ff  lea     edx, [r9+59h]; unsigned int
0x18001a903  lea     rcx, [rbp+4D0h+var_300]; this
0x18001a90a  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18001a910  mov     [rbp+4D0h+var_4A], r14w
0x18001a918  mov     [rbp+4D0h+var_3A8], 8007007Ah
0x18001a922  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a929  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001a92e  mov     ebx, eax
0x18001a930  lea     rax, [rbp+4D0h+var_440]
0x18001a937  mov     [rsp+5D0h+var_568], rax
0x18001a93c  mov     [rsp+5D0h+samDesired], 11h
0x18001a944  mov     [rsp+5D0h+dwOptions], 4Ah ; 'J'
0x18001a94c  mov     r9, r12
0x18001a94f  lea     r8, aSrmregsc; "SRMREGSC"
0x18001a956  mov     rdx, r15
0x18001a959  lea     rcx, [rbp+4D0h+var_440]
0x18001a960  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001a965  nop
0x18001a966  lea     r9, aStringcchvprin; "StringCchVPrintfW()"
0x18001a96d  mov     r8d, ebx
0x18001a970  mov     rdx, rax
0x18001a973  lea     rcx, [rbp+4D0h+var_3B0]
0x18001a97a  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18001a980  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a987  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001a98c  mov     edx, eax; int
0x18001a98e  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a995  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001a99a  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a9a1  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001a9a6  mov     r8d, eax; char
0x18001a9a9  xor     r9d, r9d; unsigned __int16 *
0x18001a9ac  lea     edx, [r9+5Ah]; unsigned int
0x18001a9b0  lea     rcx, [rbp+4D0h+var_3B0]; this
0x18001a9b7  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18001a9bd  mov     edx, 8007000Eh; int
0x18001a9c2  lea     rcx, [rbp+4D0h+var_300]; this
0x18001a9c9  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001a9ce  lea     rcx, [rbp+4D0h+var_300]; this
0x18001a9d5  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001a9da  mov     r8d, eax; char
0x18001a9dd  xor     r9d, r9d; unsigned __int16 *
0x18001a9e0  lea     edx, [r9+57h]; unsigned int
0x18001a9e4  lea     rcx, [rbp+4D0h+var_300]; this
0x18001a9eb  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
