# VSS_OBJECT_PROP_Copy::copyProvider(_VSS_PROVIDER_PROP *,_VSS_PROVIDER_PROP *)

- ea: `0x18003a790`
- end: `0x18003a88c`
- name: `?copyProvider@VSS_OBJECT_PROP_Copy@@SAJPEAU_VSS_PROVIDER_PROP@@0@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct _VSS_PROVIDER_PROP *, struct _VSS_PROVIDER_PROP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800179f0`

## callees

- `0x18000212c`
- `0x180017284`
- `0x180033a8c`
- `0x180033c78`
- `0x18003a790`

## string_xrefs

- `0x18003a7c1`: `PRPCOPYC`
- `0x18003a7a5`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18003a7b3`: `VSS_OBJECT_PROP_Copy::copyProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VSS_OBJECT_PROP_Copy::copyProvider(struct _VSS_PROVIDER_PROP *a1, struct _VSS_PROVIDER_PROP *a2)
{
  unsigned int v4; // ebx
  int v6; // [rsp+40h] [rbp-148h] BYREF
  _com_error *v7; // [rsp+48h] [rbp-140h] BYREF
  const std::exception *v8; // [rsp+50h] [rbp-138h] BYREF
  LPVOID v9; // [rsp+60h] [rbp-128h] BYREF
  unsigned int v10; // [rsp+68h] [rbp-120h]
  unsigned int v11; // [rsp+84h] [rbp-104h]
  _QWORD v12[3]; // [rsp+D0h] [rbp-B8h] BYREF
  int v13; // [rsp+E8h] [rbp-A0h]
  int v14; // [rsp+ECh] [rbp-9Ch]
  int v15; // [rsp+F0h] [rbp-98h]
  _DWORD v16[36]; // [rsp+F8h] [rbp-90h] BYREF

  v12[0] = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v12[1] = L"VSS_OBJECT_PROP_Copy::copyProvider";
  v12[2] = L"PRPCOPYC";
  v13 = 101;
  v14 = 11;
  v15 = 255;
  v16[30] = 0x1000000;
  memset_0(v16, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v9, (__int64)v12, 0);
  a1->m_ProviderId = a2->m_ProviderId;
  try
  {
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszProviderName, a2->m_pwszProviderName);
    a1->m_eProviderType = a2->m_eProviderType;
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszProviderVersion, a2->m_pwszProviderVersion);
    a1->m_ProviderVersionId = a2->m_ProviderVersionId;
    a1->m_ClassId = a2->m_ClassId;
  }
  catch ( long v6 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v9,
      v6,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_OBJECT_PROP_Copy::copyProvider",
      0x75u,
      v11);
  }
  catch ( _com_error *v7 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v9,
      v7,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_OBJECT_PROP_Copy::copyProvider",
      0x75u,
      v11);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v9,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_OBJECT_PROP_Copy::copyProvider",
      0x75u,
      v11);
  }
  catch ( const std::exception *v8 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v9,
      v8,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_OBJECT_PROP_Copy::copyProvider",
      0x75u,
      v11);
  }
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszProviderName, a2->m_pwszProviderName);
  a1->m_eProviderType = a2->m_eProviderType;
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszProviderVersion, a2->m_pwszProviderVersion);
}

```

## disassembly

```asm
0x18003a790  mov     r11, rsp
0x18003a793  mov     [r11+10h], rbx
0x18003a797  push    rdi
0x18003a798  sub     rsp, 180h
0x18003a79f  mov     rbx, rdx
0x18003a7a2  mov     rdi, rcx
0x18003a7a5  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003a7ac  mov     [r11-0B8h], rax
0x18003a7b3  lea     rax, aVssObjectPropC_2; "VSS_OBJECT_PROP_Copy::copyProvider"
0x18003a7ba  mov     [r11-0B0h], rax
0x18003a7c1  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003a7c8  mov     [r11-0A8h], rax
0x18003a7cf  mov     [rsp+188h+var_A0], 65h ; 'e'
0x18003a7da  mov     [rsp+188h+var_9C], 0Bh
0x18003a7e5  mov     [rsp+188h+var_98], 0FFh
0x18003a7f0  mov     dword ptr [r11-18h], 1000000h
0x18003a7f8  xor     edx, edx; Val
0x18003a7fa  lea     r8d, [rdx+78h]; Size
0x18003a7fe  lea     rcx, [r11-90h]; void *
0x18003a805  call    memset_0
0x18003a80a  xor     r8d, r8d
0x18003a80d  lea     rdx, [rsp+188h+var_B8]
0x18003a815  lea     rcx, [rsp+188h+var_128]
0x18003a81a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003a81f  nop
0x18003a820  movups  xmm0, xmmword ptr [rbx]
0x18003a823  movdqu  xmmword ptr [rdi], xmm0
0x18003a827  lea     rdx, [rdi+10h]; unsigned __int16 **
0x18003a82b  mov     r8, [rbx+10h]; unsigned __int16 *
0x18003a82f  lea     rcx, [rsp+188h+var_128]; struct CVssFunctionTracer *
0x18003a834  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a839  mov     eax, [rbx+18h]
0x18003a83c  mov     [rdi+18h], eax
0x18003a83f  lea     rdx, [rdi+20h]; unsigned __int16 **
0x18003a843  mov     r8, [rbx+20h]; unsigned __int16 *
0x18003a847  lea     rcx, [rsp+188h+var_128]; struct CVssFunctionTracer *
0x18003a84c  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a851  movups  xmm0, xmmword ptr [rbx+28h]
0x18003a855  movdqu  xmmword ptr [rdi+28h], xmm0
0x18003a85a  movups  xmm1, xmmword ptr [rbx+38h]
0x18003a85e  movdqu  xmmword ptr [rdi+38h], xmm1
0x18003a863  jmp     short loc_18003A86B
0x18003a865  jmp     short loc_18003A86B
0x18003a867  jmp     short loc_18003A86B
0x18003a869  jmp     short $+2
0x18003a86b  mov     ebx, [rsp+188h+var_120]
0x18003a86f  lea     rcx, [rsp+188h+var_128]; this
0x18003a874  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003a879  mov     eax, ebx
0x18003a87b  mov     rbx, [rsp+188h+arg_8]
0x18003a883  add     rsp, 180h
0x18003a88a  pop     rdi
0x18003a88b  retn
```
