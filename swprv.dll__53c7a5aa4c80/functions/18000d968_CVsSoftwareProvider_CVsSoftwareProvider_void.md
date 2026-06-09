# CVsSoftwareProvider::CVsSoftwareProvider(void)

- ea: `0x18000d968`
- end: `0x18000db75`
- name: `??0CVsSoftwareProvider@@QEAA@XZ`
- size: `525`
- prototype: `CVsSoftwareProvider *__fastcall(CVsSoftwareProvider *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800096f0`
- `0x180009824`

## callees

- `0x18000212c`
- `0x18000d968`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x180037e24`
- `0x180039718`
- `0x18003a05c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000da2a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000da2a`

## string_xrefs

- `0x18000da9a`: `CoCreateGuid failed 0x%08lx`
- `0x18000dadb`: `SYSTEM\CurrentControlSet\Services\VSS\Settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CVsSoftwareProvider *__fastcall CVsSoftwareProvider::CVsSoftwareProvider(CVsSoftwareProvider *this)
{
  CVsSoftwareProvider *v1; // rbx
  HRESULT Guid; // edi
  bool v3; // r9
  unsigned int v4; // eax
  int v6; // [rsp+40h] [rbp-178h] BYREF
  _QWORD v7[4]; // [rsp+48h] [rbp-170h] BYREF
  const unsigned __int16 *v8; // [rsp+68h] [rbp-150h] BYREF
  const unsigned __int16 *v9; // [rsp+70h] [rbp-148h]
  const unsigned __int16 *v10; // [rsp+78h] [rbp-140h]
  int v11; // [rsp+80h] [rbp-138h]
  int v12; // [rsp+84h] [rbp-134h]
  int v13; // [rsp+88h] [rbp-130h]
  _BYTE v14[120]; // [rsp+90h] [rbp-128h] BYREF
  int v15; // [rsp+108h] [rbp-B0h]
  _com_error *v16; // [rsp+110h] [rbp-A8h] BYREF
  const std::exception *v17; // [rsp+118h] [rbp-A0h] BYREF
  _BYTE v18[8]; // [rsp+120h] [rbp-98h] BYREF
  HRESULT v19; // [rsp+128h] [rbp-90h]
  unsigned int v20; // [rsp+144h] [rbp-74h]
  unsigned int v22; // [rsp+1C8h] [rbp+10h] BYREF

  v1 = this;
  *((_DWORD *)this + 8) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 80) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_WORD *)this + 54) = 0;
  *((_DWORD *)this + 28) = 64;
  v8 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v9 = L"CVsSoftwareProvider::CVsSoftwareProvider";
  v10 = L"SPRPROVC";
  v11 = 2544;
  v12 = 2;
  v13 = 255;
  v15 = 0x1000000;
  memset_0(v14, 0, sizeof(v14));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v18, (__int64)&v8, 0);
  Guid = CoCreateGuid((GUID *)((char *)v1 + 88));
  v19 = Guid;
  if ( Guid < 0 )
  {
    *(GUID *)((char *)v1 + 88) = GUID_NULL;
    v8 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v9 = L"CVsSoftwareProvider::CVsSoftwareProvider";
    v10 = L"SPRPROVC";
    v11 = 2550;
    v12 = 2;
    v13 = 255;
    v15 = 0x1000000;
    memset_0(v14, 0, sizeof(v14));
    CVssFunctionTracer::Trace(v18, &v8, L"CoCreateGuid failed 0x%08lx", (unsigned int)Guid);
  }
  try
  {
    v7[3] = 0;
    v7[2] = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v7[1] = 0;
    v7[0] = 131097;
    if ( CVssRegistryKey::Open(
           (CVssRegistryKey *)v7,
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Settings") )
    {
      v22 = 0;
      if ( CVssRegistryKey::GetValue((CVssRegistryKey *)v7, L"MaxShadowCopies", &v22, v3) )
      {
        v4 = v22;
        if ( !v22 )
          v4 = -1;
        *((_DWORD *)v1 + 28) = v4;
      }
    }
    CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v7);
  }
  catch ( long v6 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)v18,
      v6,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::CVsSoftwareProvider",
      0xA0Fu,
      v20);
    v1 = this;
  }
  catch ( _com_error *v16 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)v18,
      v16,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::CVsSoftwareProvider",
      0xA0Fu,
      v20);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)v18,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::CVsSoftwareProvider",
      0xA0Fu,
      v20);
    v1 = this;
  }
  catch ( const std::exception *v17 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)v18,
      v17,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::CVsSoftwareProvider",
      0xA0Fu,
      v20);
  }
  v7[3] = 0;
  v7[2] = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
}

```

## disassembly

```asm
0x18000d968  mov     [rsp+arg_10], rbx
0x18000d96d  mov     [rsp+arg_0], rcx
0x18000d972  push    rsi
0x18000d973  push    rdi
0x18000d974  push    r12
0x18000d976  push    r13
0x18000d978  push    r15
0x18000d97a  sub     rsp, 190h
0x18000d981  mov     rbx, rcx
0x18000d984  mov     dword ptr [rcx+20h], 0
0x18000d98b  xorps   xmm0, xmm0
0x18000d98e  xor     eax, eax
0x18000d990  movups  xmmword ptr [rcx+28h], xmm0
0x18000d994  movups  xmmword ptr [rcx+38h], xmm0
0x18000d998  mov     [rcx+48h], rax
0x18000d99c  mov     [rcx+50h], al
0x18000d99f  mov     [rcx+68h], eax
0x18000d9a2  mov     [rcx+6Ch], ax
0x18000d9a6  mov     dword ptr [rcx+70h], 40h ; '@'
0x18000d9ad  lea     r15, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000d9b4  mov     [rsp+1B8h+var_150], r15
0x18000d9b9  lea     r12, aCvssoftwarepro_5; "CVsSoftwareProvider::CVsSoftwareProvide"...
0x18000d9c0  mov     [rsp+1B8h+var_148], r12
0x18000d9c5  lea     r13, aSprprovc; "SPRPROVC"
0x18000d9cc  mov     [rsp+1B8h+var_140], r13
0x18000d9d1  mov     [rsp+1B8h+var_138], 9F0h
0x18000d9dc  mov     [rsp+1B8h+var_134], 2
0x18000d9e7  mov     [rsp+1B8h+var_130], 0FFh
0x18000d9f2  mov     [rsp+1B8h+var_B0], 1000000h
0x18000d9fd  xor     edx, edx; Val
0x18000d9ff  lea     r8d, [rax+78h]; Size
0x18000da03  lea     rcx, [rsp+1B8h+var_128]; void *
0x18000da0b  call    memset_0
0x18000da10  xor     r8d, r8d
0x18000da13  lea     rdx, [rsp+1B8h+var_150]
0x18000da18  lea     rcx, [rsp+1B8h+var_98]
0x18000da20  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000da25  nop
0x18000da26  lea     rcx, [rbx+58h]; pguid
0x18000da2a  call    cs:__imp_CoCreateGuid
0x18000da30  mov     edi, eax
0x18000da32  mov     [rsp+1B8h+var_90], eax
0x18000da39  test    eax, eax
0x18000da3b  jns     short loc_18000DAB4
0x18000da3d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000da44  movdqu  xmmword ptr [rbx+58h], xmm0
0x18000da49  mov     [rsp+1B8h+var_150], r15
0x18000da4e  mov     [rsp+1B8h+var_148], r12
0x18000da53  mov     [rsp+1B8h+var_140], r13
0x18000da58  mov     [rsp+1B8h+var_138], 9F6h
0x18000da63  mov     [rsp+1B8h+var_134], 2
0x18000da6e  mov     [rsp+1B8h+var_130], 0FFh
0x18000da79  mov     [rsp+1B8h+var_B0], 1000000h
0x18000da84  xor     edx, edx; Val
0x18000da86  lea     r8d, [rdx+78h]; Size
0x18000da8a  lea     rcx, [rsp+1B8h+var_128]; void *
0x18000da92  call    memset_0
0x18000da97  mov     r9d, edi
0x18000da9a  lea     r8, aCocreateguidFa; "CoCreateGuid failed 0x%08lx"
0x18000daa1  lea     rdx, [rsp+1B8h+var_150]
0x18000daa6  lea     rcx, [rsp+1B8h+var_98]
0x18000daae  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000dab3  nop
0x18000dab4  mov     [rsp+1B8h+var_158], 0
0x18000dabd  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18000dac4  mov     [rsp+1B8h+var_160], rax
0x18000dac9  mov     [rsp+1B8h+var_168], 0
0x18000dad2  mov     [rsp+1B8h+var_170], 20019h
0x18000dadb  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x18000dae2  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000dae9  lea     rcx, [rsp+1B8h+var_170]; this
0x18000daee  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18000daf3  test    al, al
0x18000daf5  jz      short loc_18000DB31
0x18000daf7  mov     [rsp+1B8h+arg_8], 0
0x18000db02  lea     r8, [rsp+1B8h+arg_8]; unsigned int *
0x18000db0a  lea     rdx, aMaxshadowcopie; "MaxShadowCopies"
0x18000db11  lea     rcx, [rsp+1B8h+var_170]; this
0x18000db16  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAK_N@Z; CVssRegistryKey::GetValue(ushort const *,ulong &,bool)
0x18000db1b  test    al, al
0x18000db1d  jz      short loc_18000DB31
0x18000db1f  mov     eax, [rsp+1B8h+arg_8]
0x18000db26  or      ecx, 0FFFFFFFFh
0x18000db29  test    eax, eax
0x18000db2b  cmovz   eax, ecx
0x18000db2e  mov     [rbx+70h], eax
0x18000db31  lea     rcx, [rsp+1B8h+var_170]; this
0x18000db36  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18000db3b  nop
0x18000db3c  jmp     short loc_18000DB4C
0x18000db3e  jmp     short loc_18000DB44
0x18000db40  jmp     short loc_18000DB44
0x18000db42  jmp     short $+2
0x18000db44  mov     rbx, [rsp+1B8h+arg_0]
0x18000db4c  lea     rcx, [rsp+1B8h+var_98]; this
0x18000db54  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18000db59  nop
0x18000db5a  mov     rax, rbx
0x18000db5d  mov     rbx, [rsp+1B8h+arg_10]
0x18000db65  add     rsp, 190h
0x18000db6c  pop     r15
0x18000db6e  pop     r13
0x18000db70  pop     r12
0x18000db72  pop     rdi
0x18000db73  pop     rsi
0x18000db74  retn
```
