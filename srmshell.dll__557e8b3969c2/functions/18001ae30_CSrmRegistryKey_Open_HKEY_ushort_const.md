# CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)

- ea: `0x18001ae30`
- end: `0x18001b2bc`
- name: `?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ`
- size: `1164`
- prototype: `char(CSrmRegistryKey *this, HKEY hKey, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800079e0`
- `0x18000a460`
- `0x18000a704`

## callees

- `0x1800083e0`
- `0x18000d368`
- `0x1800161e8`
- `0x18001623c`
- `0x180016564`
- `0x180018f68`
- `0x180019b84`
- `0x18001a384`
- `0x18001ae30`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18001af02`
- `msvcrt!_vsnwprintf` at `0x18001af02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b157`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b157`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001af7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001af7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001af65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001af65`

## string_xrefs

- `0x18001ae76`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001ae82`: `CSrmRegistryKey::Open`

## pseudocode

```c
char CSrmRegistryKey::Open(CSrmRegistryKey *this, HKEY hKey, const unsigned __int16 *a3, ...)
{
  unsigned int v5; // eax
  int v6; // eax
  __int64 v8; // rbx
  __int64 v9; // rcx
  wchar_t *v10; // rdi
  unsigned __int64 v11; // rdx
  signed int v12; // ecx
  __int64 v13; // rcx
  wchar_t *v14; // r8
  wchar_t *v15; // rax
  wchar_t v16; // r9
  wchar_t *v17; // rcx
  char v18; // al
  int v19; // eax
  char v20; // al
  unsigned int Hr; // ebx
  __int64 v22; // rax
  int v23; // eax
  char v24; // al
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v26; // [rsp+50h] [rbp-B0h]
  _QWORD v27[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+74h] [rbp-8Ch]
  int v30; // [rsp+78h] [rbp-88h]
  char v31[96]; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+E0h] [rbp-20h]
  _QWORD v33[3]; // [rsp+E8h] [rbp-18h] BYREF
  int v34; // [rsp+100h] [rbp+0h]
  int v35; // [rsp+104h] [rbp+4h]
  int v36; // [rsp+108h] [rbp+8h]
  char v37[96]; // [rsp+110h] [rbp+10h] BYREF
  int v38; // [rsp+170h] [rbp+70h]
  _BYTE v39[152]; // [rsp+178h] [rbp+78h] BYREF
  void **v40; // [rsp+210h] [rbp+110h] BYREF
  int v41; // [rsp+218h] [rbp+118h]
  void **v42; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v43; // [rsp+2C8h] [rbp+1C8h]
  wchar_t Buffer[259]; // [rsp+370h] [rbp+270h] BYREF
  __int16 v45; // [rsp+576h] [rbp+476h]
  va_list Args; // [rsp+5F8h] [rbp+4F8h] BYREF

  va_start(Args, a3);
  v27[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
  v27[1] = L"CSrmRegistryKey::Open";
  v27[2] = L"SRMREGSC";
  v28 = 109;
  v29 = 17;
  v30 = 255;
  v32 = 0x1000000;
  memset_0(v31, 0, sizeof(v31));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v42, (const struct CSrmDebugInfo *)v27, 0);
  v26 = 0;
  v5 = _vsnwprintf(Buffer, 0x103u, a3, Args);
  if ( v5 >= 0x104 )
  {
    v45 = 0;
    v43 = -2147024774;
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v42);
    v26 = v39;
    v22 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v39,
            (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
            (__int64)L"SRMREGSC",
            (__int64)L"CSrmRegistryKey::Open",
            121,
            17);
    CSrmFunctionTracer::TranslateGenericError(&v42, v22, Hr, L"StringCchVPrintfW()");
  }
  v43 = 0;
  if ( v5 == 259 )
    v45 = 0;
  hKeya = 0;
  v6 = RegOpenKeyExW(hKey, Buffer, 0, *(_DWORD *)this, &hKeya);
  if ( v6 != 2 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v43 = v6;
    if ( v6 < 0 )
    {
      v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v42);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v42, v23);
      v24 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v42);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v42, 0x87u, v24, 0);
    }
    v43 = v6;
    CSrmRegistryKey::Close(this);
    v26 = v33;
    v33[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h";
    v33[1] = L"SrmDuplicateStr";
    v33[2] = L"INCLSTRH";
    v34 = 78;
    v35 = 17;
    v36 = 255;
    v38 = 0x1000000;
    memset_0(v37, 0, sizeof(v37));
    CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v40, (const struct CSrmDebugInfo *)v33, 0);
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( Buffer[v9] );
    v10 = (wchar_t *)CoTaskMemAlloc(2 * v9 + 2);
    if ( !v10 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v40, -2147024882);
      v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v40);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v40, 0x57u, v18, 0);
    }
    v41 = 0;
    do
      ++v8;
    while ( Buffer[v8] );
    v11 = v8 + 1;
    v12 = -2147024809;
    if ( v8 != -1 )
    {
      if ( v11 > 0x7FFFFFFF )
      {
        *v10 = 0;
        v41 = -2147024809;
        goto LABEL_29;
      }
      v13 = 2147483646;
      v14 = Buffer;
      v15 = v10;
      do
      {
        if ( !v13 )
          break;
        v16 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v15++ = v16;
        --v13;
        --v11;
      }
      while ( v11 );
      v17 = v15 - 1;
      if ( v11 )
        v17 = v15;
      *v17 = 0;
      v12 = v11 == 0 ? 0x8007007A : 0;
    }
    v41 = v12;
    if ( v12 >= 0 )
    {
      v41 = v12;
      v40 = &CSrmFunctionTracer::`vftable';
      CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v40);
      CoTaskMemFree(*((LPVOID *)this + 2));
      *((_QWORD *)this + 2) = v10;
      *((_QWORD *)this + 1) = hKeya;
      hKeya = 0;
      v42 = &CSrmFunctionTracer::`vftable';
      CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v42);
      return 1;
    }
LABEL_29:
    v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v40);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v40, v19);
    v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v40);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v40, 0x59u, v20, 0);
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  hKeya = 0;
  v42 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v42);
  return 0;
}

```

## disassembly

```asm
0x18001ae30  mov     [rsp-8+Format], r8
0x18001ae35  mov     qword ptr [rsp-8+Args], r9
0x18001ae3a  push    rbp
0x18001ae3b  push    rbx
0x18001ae3c  push    rsi
0x18001ae3d  push    rdi
0x18001ae3e  push    r12
0x18001ae40  push    r13
0x18001ae42  push    r14
0x18001ae44  push    r15
0x18001ae46  lea     rbp, [rsp-498h]
0x18001ae4e  sub     rsp, 598h
0x18001ae55  mov     rax, cs:__security_cookie
0x18001ae5c  xor     rax, rsp
0x18001ae5f  mov     [rbp+4D0h+var_50], rax
0x18001ae66  mov     rbx, rdx
0x18001ae69  mov     rsi, rcx
0x18001ae6c  lea     rax, [rsp+5D0h+var_578]
0x18001ae71  mov     [rsp+5D0h+var_580], rax
0x18001ae76  lea     r15, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001ae7d  mov     [rsp+5D0h+var_578], r15
0x18001ae82  lea     r12, aCsrmregistryke_1; "CSrmRegistryKey::Open"
0x18001ae89  mov     [rsp+5D0h+var_570], r12
0x18001ae8e  lea     r13, aSrmregsc; "SRMREGSC"
0x18001ae95  mov     [rsp+5D0h+var_568], r13
0x18001ae9a  mov     [rsp+5D0h+var_560], 6Dh ; 'm'
0x18001aea2  mov     [rsp+5D0h+var_55C], 11h
0x18001aeaa  mov     [rsp+5D0h+var_558], 0FFh
0x18001aeb2  xor     r14d, r14d
0x18001aeb5  mov     [rbp+4D0h+var_4F0], 1000000h
0x18001aebc  xor     edx, edx; Val
0x18001aebe  lea     r8d, [r14+60h]; Size
0x18001aec2  lea     rcx, [rbp+4D0h+var_550]; void *
0x18001aec6  call    memset_0
0x18001aecb  nop
0x18001aecc  xor     r8d, r8d
0x18001aecf  lea     rdx, [rsp+5D0h+var_578]
0x18001aed4  lea     rcx, [rbp+4D0h+var_310]
0x18001aedb  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001aee0  nop
0x18001aee1  mov     [rsp+5D0h+var_580], r14
0x18001aee6  lea     r9, [rbp+4D0h+Args]; Args
0x18001aeed  mov     r8, [rbp+4D0h+Format]; Format
0x18001aef4  mov     edi, 103h
0x18001aef9  mov     edx, edi; BufferCount
0x18001aefb  lea     rcx, [rbp+4D0h+Buffer]; Buffer
0x18001af02  call    cs:__imp__vsnwprintf
0x18001af08  test    eax, eax
0x18001af0a  js      loc_18001B218
0x18001af10  cmp     eax, edi
0x18001af12  ja      loc_18001B218
0x18001af18  mov     [rbp+4D0h+var_308], r14d
0x18001af1f  jnz     short loc_18001AF29
0x18001af21  mov     [rbp+4D0h+var_5A], r14w
0x18001af29  lea     r12, ??_7?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@6B@; const CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>::`vftable'
0x18001af30  mov     [rsp+5D0h+var_590], r12
0x18001af35  mov     [rsp+5D0h+hKey], r14
0x18001af3a  lea     r15, ??_7?$CSrmAuto@PEAUHKEY__@@V?$CSrmAutoGenericValue_Storage@PEAUHKEY__@@$0A@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAUHKEY__@@@@SAAEAPEAU1@1@Z@@@@6B@; const CSrmAuto<HKEY__ *,CSrmAutoGenericValue_Storage<HKEY__ *,0,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ * & (*)(HKEY__ * &),&DTyper<HKEY__ *>::Identity(HKEY__ * &)>>::`vftable'
0x18001af41  mov     [rsp+5D0h+var_590], r15
0x18001af46  mov     [rsp+5D0h+hKey], r14
0x18001af4b  lea     rax, [rsp+5D0h+hKey]
0x18001af50  mov     [rsp+5D0h+phkResult], rax; phkResult
0x18001af55  mov     r9d, [rsi]; samDesired
0x18001af58  xor     r8d, r8d; ulOptions
0x18001af5b  lea     rdx, [rbp+4D0h+Buffer]; lpSubKey
0x18001af62  mov     rcx, rbx; hKey
0x18001af65  call    cs:__imp_RegOpenKeyExW
0x18001af6b  cmp     eax, 2
0x18001af6e  jnz     short loc_18001AFD3
0x18001af70  mov     [rsp+5D0h+var_590], r15
0x18001af75  mov     rcx, [rsp+5D0h+hKey]; hKey
0x18001af7a  test    rcx, rcx
0x18001af7d  jz      short loc_18001AF85
0x18001af7f  call    cs:__imp_RegCloseKey
0x18001af85  mov     [rsp+5D0h+hKey], r14
0x18001af8a  mov     [rsp+5D0h+var_590], r12
0x18001af8f  mov     [rsp+5D0h+hKey], r14
0x18001af94  lea     rbx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001af9b  mov     [rbp+4D0h+var_310], rbx
0x18001afa2  lea     rcx, [rbp+4D0h+var_310]; this
0x18001afa9  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001afae  xor     al, al
0x18001afb0  mov     rcx, [rbp+4D0h+var_50]
0x18001afb7  xor     rcx, rsp; StackCookie
0x18001afba  call    __security_check_cookie
0x18001afbf  add     rsp, 598h
0x18001afc6  pop     r15
0x18001afc8  pop     r14
0x18001afca  pop     r13
0x18001afcc  pop     r12
0x18001afce  pop     rdi
0x18001afcf  pop     rsi
0x18001afd0  pop     rbx
0x18001afd1  pop     rbp
0x18001afd2  retn
0x18001afd3  test    eax, eax
0x18001afd5  jle     short loc_18001AFDF
0x18001afd7  movzx   eax, ax
0x18001afda  or      eax, 80070000h
0x18001afdf  mov     [rbp+4D0h+var_308], eax
0x18001afe5  test    eax, eax
0x18001afe7  js      loc_18001B27E
0x18001afed  mov     [rbp+4D0h+var_308], eax
0x18001aff3  mov     rcx, rsi; this
0x18001aff6  call    ?Close@CSrmRegistryKey@@QEAAXXZ; CSrmRegistryKey::Close(void)
0x18001affb  lea     rax, [rbp+4D0h+var_4E8]
0x18001afff  mov     [rsp+5D0h+var_580], rax
0x18001b004  lea     rax, aBaseFsFsrmUtil_0; "base\\fs\\fsrm\\utilities\\inc\\srmstr."...
0x18001b00b  mov     [rbp+4D0h+var_4E8], rax
0x18001b00f  lea     rax, aSrmduplicatest; "SrmDuplicateStr"
0x18001b016  mov     [rbp+4D0h+var_4E0], rax
0x18001b01a  lea     rax, aInclstrh; "INCLSTRH"
0x18001b021  mov     [rbp+4D0h+var_4D8], rax
0x18001b025  mov     [rbp+4D0h+var_4D0], 4Eh ; 'N'
0x18001b02c  mov     [rbp+4D0h+var_4CC], 11h
0x18001b033  mov     [rbp+4D0h+var_4C8], 0FFh
0x18001b03a  mov     [rbp+4D0h+var_460], 1000000h
0x18001b041  xor     edx, edx; Val
0x18001b043  lea     r8d, [rdx+60h]; Size
0x18001b047  lea     rcx, [rbp+4D0h+var_4C0]; void *
0x18001b04b  call    memset_0
0x18001b050  nop
0x18001b051  xor     r8d, r8d
0x18001b054  lea     rdx, [rbp+4D0h+var_4E8]
0x18001b058  lea     rcx, [rbp+4D0h+var_3C0]
0x18001b05f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001b064  nop
0x18001b065  lea     rax, [rbp+4D0h+Buffer]
0x18001b06c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b070  mov     rcx, rbx
0x18001b073  inc     rcx
0x18001b076  cmp     [rax+rcx*2], r14w
0x18001b07b  jnz     short loc_18001B073
0x18001b07d  lea     rcx, ds:2[rcx*2]; cb
0x18001b085  call    cs:__imp_CoTaskMemAlloc
0x18001b08b  mov     rdi, rax
0x18001b08e  mov     eax, [rbp+4D0h+var_3B8]
0x18001b094  mov     [rbp+4D0h+var_3B8], eax
0x18001b09a  test    rdi, rdi
0x18001b09d  jz      loc_18001B19D
0x18001b0a3  mov     [rbp+4D0h+var_3B8], r14d
0x18001b0aa  lea     rax, [rbp+4D0h+Buffer]
0x18001b0b1  inc     rbx
0x18001b0b4  cmp     [rax+rbx*2], r14w
0x18001b0b9  jnz     short loc_18001B0B1
0x18001b0bb  lea     rdx, [rbx+1]
0x18001b0bf  mov     ecx, 80070057h
0x18001b0c4  test    rdx, rdx
0x18001b0c7  jz      short loc_18001B125
0x18001b0c9  cmp     rdx, 7FFFFFFFh
0x18001b0d0  ja      loc_18001B1D1
0x18001b0d6  mov     ecx, 7FFFFFFEh
0x18001b0db  lea     r8, [rbp+4D0h+Buffer]
0x18001b0e2  mov     rax, rdi
0x18001b0e5  test    rcx, rcx
0x18001b0e8  jz      short loc_18001B109
0x18001b0ea  movzx   r9d, word ptr [r8]
0x18001b0ee  test    r9w, r9w
0x18001b0f2  jz      short loc_18001B109
0x18001b0f4  add     r8, 2
0x18001b0f8  mov     [rax], r9w
0x18001b0fc  add     rax, 2
0x18001b100  dec     rcx
0x18001b103  sub     rdx, 1
0x18001b107  jnz     short loc_18001B0E5
0x18001b109  lea     rcx, [rax-2]
0x18001b10d  test    rdx, rdx
0x18001b110  cmovnz  rcx, rax
0x18001b114  mov     [rcx], r14w
0x18001b118  neg     rdx
0x18001b11b  sbb     ecx, ecx
0x18001b11d  not     ecx
0x18001b11f  and     ecx, 8007007Ah
0x18001b125  mov     [rbp+4D0h+var_3B8], ecx
0x18001b12b  test    ecx, ecx
0x18001b12d  js      loc_18001B1DB
0x18001b133  mov     [rbp+4D0h+var_3B8], ecx
0x18001b139  lea     rbx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001b140  mov     [rbp+4D0h+var_3C0], rbx
0x18001b147  lea     rcx, [rbp+4D0h+var_3C0]; this
0x18001b14e  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001b153  mov     rcx, [rsi+10h]; pv
0x18001b157  call    cs:__imp_CoTaskMemFree
0x18001b15d  mov     [rsi+10h], rdi
0x18001b161  mov     rax, [rsp+5D0h+hKey]
0x18001b166  mov     [rsp+5D0h+hKey], r14
0x18001b16b  mov     [rsi+8], rax
0x18001b16f  mov     [rsp+5D0h+var_590], r15
0x18001b174  mov     [rsp+5D0h+hKey], r14
0x18001b179  mov     [rsp+5D0h+var_590], r12
0x18001b17e  mov     [rsp+5D0h+hKey], r14
0x18001b183  mov     [rbp+4D0h+var_310], rbx
0x18001b18a  lea     rcx, [rbp+4D0h+var_310]; this
0x18001b191  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001b196  mov     al, 1
0x18001b198  jmp     loc_18001AFB0
0x18001b19d  mov     edx, 8007000Eh; int
0x18001b1a2  lea     rcx, [rbp+4D0h+var_3C0]; this
0x18001b1a9  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001b1ae  lea     rcx, [rbp+4D0h+var_3C0]; this
0x18001b1b5  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001b1ba  mov     r8d, eax; char
0x18001b1bd  xor     r9d, r9d; unsigned __int16 *
0x18001b1c0  lea     edx, [r9+57h]; unsigned int
0x18001b1c4  lea     rcx, [rbp+4D0h+var_3C0]; this
0x18001b1cb  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18001b1d1  mov     [rdi], r14w
0x18001b1d5  mov     [rbp+4D0h+var_3B8], ecx
0x18001b1db  lea     rcx, [rbp+4D0h+var_3C0]; this
0x18001b1e2  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001b1e7  mov     edx, eax; int
0x18001b1e9  lea     rcx, [rbp+4D0h+var_3C0]; this
0x18001b1f0  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001b1f5  lea     rcx, [rbp+4D0h+var_3C0]; this
0x18001b1fc  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001b201  mov     r8d, eax; char
0x18001b204  xor     r9d, r9d; unsigned __int16 *
0x18001b207  lea     edx, [r9+59h]; unsigned int
0x18001b20b  lea     rcx, [rbp+4D0h+var_3C0]; this
0x18001b212  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18001b218  mov     [rbp+4D0h+var_5A], r14w
0x18001b220  mov     [rbp+4D0h+var_308], 8007007Ah
0x18001b22a  lea     rcx, [rbp+4D0h+var_310]; this
0x18001b231  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001b236  mov     ebx, eax
0x18001b238  lea     rax, [rbp+4D0h+var_458]
0x18001b23c  mov     [rsp+5D0h+var_580], rax
0x18001b241  mov     [rsp+5D0h+var_5A8], 11h
0x18001b249  mov     dword ptr [rsp+5D0h+phkResult], 79h ; 'y'
0x18001b251  mov     r9, r12
0x18001b254  mov     r8, r13
0x18001b257  mov     rdx, r15
0x18001b25a  lea     rcx, [rbp+4D0h+var_458]
0x18001b25e  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18001b263  nop
0x18001b264  lea     r9, aStringcchvprin; "StringCchVPrintfW()"
0x18001b26b  mov     r8d, ebx
0x18001b26e  mov     rdx, rax
0x18001b271  lea     rcx, [rbp+4D0h+var_310]
0x18001b278  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18001b27e  lea     rcx, [rbp+4D0h+var_310]; this
0x18001b285  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001b28a  mov     edx, eax; int
0x18001b28c  lea     rcx, [rbp+4D0h+var_310]; this
0x18001b293  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18001b298  lea     rcx, [rbp+4D0h+var_310]; this
0x18001b29f  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18001b2a4  mov     r8d, eax; char
0x18001b2a7  xor     r9d, r9d; unsigned __int16 *
0x18001b2aa  mov     edx, 87h; unsigned int
0x18001b2af  lea     rcx, [rbp+4D0h+var_310]; this
0x18001b2b6  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
