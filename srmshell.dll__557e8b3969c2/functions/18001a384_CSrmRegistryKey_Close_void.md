# CSrmRegistryKey::Close(void)

- ea: `0x18001a384`
- end: `0x18001a53a`
- name: `?Close@CSrmRegistryKey@@QEAAXXZ`
- size: `438`
- prototype: `void __fastcall(CSrmRegistryKey *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a460`
- `0x18001a280`
- `0x18001a540`
- `0x18001ae30`

## callees

- `0x18001623c`
- `0x180016564`
- `0x1800193ec`
- `0x18001a384`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a4eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a4eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a432`

## string_xrefs

- `0x18001a3b1`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18001a3bd`: `CSrmRegistryKey::Close`

## pseudocode

```c
void __fastcall CSrmRegistryKey::Close(CSrmRegistryKey *this)
{
  HKEY v2; // rcx
  LSTATUS v3; // edx
  __int64 v4; // r9
  unsigned __int16 v5; // cx
  LSTATUS v6; // [rsp+20h] [rbp-248h]
  int v7; // [rsp+44h] [rbp-224h] BYREF
  _QWORD *v8; // [rsp+48h] [rbp-220h]
  _com_error *v9; // [rsp+50h] [rbp-218h] BYREF
  const exception *v10; // [rsp+58h] [rbp-210h] BYREF
  _QWORD v11[3]; // [rsp+60h] [rbp-208h] BYREF
  int v12; // [rsp+78h] [rbp-1F0h]
  int v13; // [rsp+7Ch] [rbp-1ECh]
  int v14; // [rsp+80h] [rbp-1E8h]
  _BYTE v15[96]; // [rsp+88h] [rbp-1E0h] BYREF
  int v16; // [rsp+E8h] [rbp-180h]
  _QWORD v17[3]; // [rsp+F0h] [rbp-178h] BYREF
  int v18; // [rsp+108h] [rbp-160h]
  int v19; // [rsp+10Ch] [rbp-15Ch]
  int v20; // [rsp+110h] [rbp-158h]
  _QWORD v21[12]; // [rsp+118h] [rbp-150h]
  __int16 v22; // [rsp+178h] [rbp-F0h]
  char v23; // [rsp+17Ah] [rbp-EEh]
  char v24; // [rsp+17Bh] [rbp-EDh]
  _QWORD v25[5]; // [rsp+180h] [rbp-E8h] BYREF
  unsigned int v26; // [rsp+1ACh] [rbp-BCh]

  v8 = v11;
  v11[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
  v11[1] = L"CSrmRegistryKey::Close";
  v11[2] = L"SRMREGSC";
  v12 = 869;
  v13 = 17;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v25, (const struct CSrmDebugInfo *)v11, 0);
  try
  {
    v2 = (HKEY)*((_QWORD *)this + 1);
    if ( v2 )
    {
      v3 = RegCloseKey(v2);
      if ( v3 )
      {
        v4 = *((_QWORD *)this + 2);
        v8 = v17;
        v17[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
        v17[1] = L"CSrmRegistryKey::Close";
        v17[2] = L"SRMREGSC";
        v18 = 877;
        v19 = 17;
        v20 = 255;
        v5 = 0;
        v22 = 0;
        v23 = 0;
        v24 = 1;
        while ( v5 < 0xCu )
          v21[v5++] = 0;
        v6 = v3;
        CSrmFunctionTracer::Trace(v25, v17, L"%s: Error on closing key with name %s. lRes == 0x%08lx", v4, v6);
      }
      *((_QWORD *)this + 1) = 0;
    }
    CoTaskMemFree(*((LPVOID *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  catch ( long v7 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)v25,
      v7,
      L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
      L"SRMREGSC",
      L"CSrmRegistryKey::Close",
      0x373u,
      v26);
  }
  catch ( _com_error *v9 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)v25,
      v9,
      L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
      L"SRMREGSC",
      L"CSrmRegistryKey::Close",
      0x373u,
      v26);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)v25,
      L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
      L"SRMREGSC",
      L"CSrmRegistryKey::Close",
      0x373u,
      v26);
  }
  catch ( const exception *v10 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)v25,
      v10,
      L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
      L"SRMREGSC",
      L"CSrmRegistryKey::Close",
      0x373u,
      v26);
  }
  v2 = (HKEY)*((_QWORD *)this + 1);
  if ( v2 )
  {
    v3 = RegCloseKey(v2);
    if ( v3 )
    {
      v4 = *((_QWORD *)this + 2);
      v8 = v17;
      v17[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
      v17[1] = L"CSrmRegistryKey::Close";
      v17[2] = L"SRMREGSC";
      v18 = 877;
      v19 = 17;
      v20 = 255;
      v5 = 0;
      v22 = 0;
      v23 = 0;
      v24 = 1;
      while ( v5 < 0xCu )
        v21[v5++] = 0;
      v6 = v3;
      CSrmFunctionTracer::Trace(v25, v17, L"%s: Error on closing key with name %s. lRes == 0x%08lx", v4, v6);
    }
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18001a384  push    rbx
0x18001a386  push    rsi
0x18001a387  push    r14
0x18001a389  push    r15
0x18001a38b  sub     rsp, 248h
0x18001a392  mov     rax, cs:__security_cookie
0x18001a399  xor     rax, rsp
0x18001a39c  mov     [rsp+268h+var_38], rax
0x18001a3a4  mov     rbx, rcx
0x18001a3a7  lea     rax, [rsp+268h+var_208]
0x18001a3ac  mov     [rsp+268h+var_220], rax
0x18001a3b1  lea     rsi, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x18001a3b8  mov     [rsp+268h+var_208], rsi
0x18001a3bd  lea     r14, aCsrmregistryke_0; "CSrmRegistryKey::Close"
0x18001a3c4  mov     [rsp+268h+var_200], r14
0x18001a3c9  lea     r15, aSrmregsc; "SRMREGSC"
0x18001a3d0  mov     [rsp+268h+var_1F8], r15
0x18001a3d5  mov     [rsp+268h+var_1F0], 365h
0x18001a3dd  mov     [rsp+268h+var_1EC], 11h
0x18001a3e5  mov     [rsp+268h+var_1E8], 0FFh
0x18001a3f0  mov     [rsp+268h+var_180], 1000000h
0x18001a3fb  xor     edx, edx; Val
0x18001a3fd  lea     r8d, [rdx+60h]; Size
0x18001a401  lea     rcx, [rsp+268h+var_1E0]; void *
0x18001a409  call    memset_0
0x18001a40e  nop
0x18001a40f  xor     r8d, r8d
0x18001a412  lea     rdx, [rsp+268h+var_208]
0x18001a417  lea     rcx, [rsp+268h+var_E8]
0x18001a41f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001a424  nop
0x18001a425  mov     rcx, [rbx+8]; hKey
0x18001a429  test    rcx, rcx
0x18001a42c  jz      loc_18001A4E7
0x18001a432  call    cs:__imp_RegCloseKey
0x18001a438  mov     edx, eax
0x18001a43a  test    eax, eax
0x18001a43c  jz      loc_18001A4DF
0x18001a442  mov     r9, [rbx+10h]
0x18001a446  lea     r10, [rsp+268h+var_178]
0x18001a44e  mov     [rsp+268h+var_220], r10
0x18001a453  mov     [rsp+268h+var_178], rsi
0x18001a45b  mov     [rsp+268h+var_170], r14
0x18001a463  mov     [rsp+268h+var_168], r15
0x18001a46b  mov     [rsp+268h+var_160], 36Dh
0x18001a476  mov     [rsp+268h+var_15C], 11h
0x18001a481  mov     [rsp+268h+var_158], 0FFh
0x18001a48c  xor     ecx, ecx
0x18001a48e  mov     [rsp+268h+var_F0], cx
0x18001a496  mov     [rsp+268h+var_EE], cl
0x18001a49d  mov     [rsp+268h+var_ED], 1
0x18001a4a5  mov     [rsp+268h+var_228], cx
0x18001a4aa  cmp     cx, 0Ch
0x18001a4ae  jnb     short loc_18001A4C4
0x18001a4b0  movzx   eax, cx
0x18001a4b3  mov     [rsp+rax*8+268h+var_150], 0
0x18001a4bf  inc     cx
0x18001a4c2  jmp     short loc_18001A4A5
0x18001a4c4  mov     [rsp+268h+var_248], edx
0x18001a4c8  lea     r8, aSErrorOnClosin; "%s: Error on closing key with name %s. "...
0x18001a4cf  mov     rdx, r10
0x18001a4d2  lea     rcx, [rsp+268h+var_E8]
0x18001a4da  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001a4df  mov     qword ptr [rbx+8], 0
0x18001a4e7  mov     rcx, [rbx+10h]; pv
0x18001a4eb  call    cs:__imp_CoTaskMemFree
0x18001a4f1  mov     qword ptr [rbx+10h], 0
0x18001a4f9  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001a500  mov     [rsp+268h+var_E8], rax
0x18001a508  lea     rcx, [rsp+268h+var_E8]; this
0x18001a510  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001a515  mov     rcx, [rsp+268h+var_38]
0x18001a51d  xor     rcx, rsp; StackCookie
0x18001a520  call    __security_check_cookie
0x18001a525  add     rsp, 248h
0x18001a52c  pop     r15
0x18001a52e  pop     r14
0x18001a530  pop     rsi
0x18001a531  pop     rbx
0x18001a532  retn
0x18001a533  jmp     short loc_18001A4F9
0x18001a535  jmp     short loc_18001A4F9
0x18001a537  jmp     short loc_18001A4F9
```
