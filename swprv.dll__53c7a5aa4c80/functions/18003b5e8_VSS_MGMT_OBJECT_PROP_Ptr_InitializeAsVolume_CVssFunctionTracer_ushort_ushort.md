# VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsVolume(CVssFunctionTracer &,ushort *,ushort *)

- ea: `0x18003b5e8`
- end: `0x18003b803`
- name: `?InitializeAsVolume@VSS_MGMT_OBJECT_PROP_Ptr@@QEAAXAEAVCVssFunctionTracer@@PEAG1@Z`
- size: `539`
- prototype: `void __fastcall(VSS_MGMT_OBJECT_PROP_Ptr *this, struct CVssFunctionTracer *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026da0`

## callees

- `0x18000212c`
- `0x180017284`
- `0x18003649c`
- `0x18003aad8`
- `0x18003ad20`
- `0x18003b5e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b65d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b65d`

## pseudocode

```c
void __fastcall VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsVolume(
        VSS_MGMT_OBJECT_PROP_Ptr *this,
        struct CVssFunctionTracer *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  struct CVssFunctionTracer *v6; // rdi
  struct _VSS_MGMT_OBJECT_PROP *v8; // rax
  struct _VSS_MGMT_OBJECT_PROP *v9; // rsi
  void *v10; // rsi
  unsigned int v11; // [rsp+40h] [rbp-158h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-150h]
  const unsigned __int16 *v13; // [rsp+58h] [rbp-140h] BYREF
  const unsigned __int16 *v14; // [rsp+60h] [rbp-138h]
  const unsigned __int16 *v15; // [rsp+68h] [rbp-130h]
  int v16; // [rsp+70h] [rbp-128h]
  int v17; // [rsp+74h] [rbp-124h]
  int v18; // [rsp+78h] [rbp-120h]
  _BYTE v19[120]; // [rsp+80h] [rbp-118h] BYREF
  int v20; // [rsp+F8h] [rbp-A0h]
  _com_error *v21; // [rsp+100h] [rbp-98h] BYREF
  const std::exception *v22; // [rsp+108h] [rbp-90h] BYREF
  _OWORD v23[4]; // [rsp+110h] [rbp-88h] BYREF
  _OWORD v24[2]; // [rsp+150h] [rbp-48h]

  v6 = a2;
  v23[0] = *(_OWORD *)L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsVolume";
  v23[1] = *(_OWORD *)L"_OBJECT_PROP_Ptr::InitializeAsVolume";
  v23[2] = *(_OWORD *)L"PROP_Ptr::InitializeAsVolume";
  v23[3] = *(_OWORD *)L"::InitializeAsVolume";
  v24[0] = *(_OWORD *)L"lizeAsVolume";
  *(_OWORD *)((char *)v24 + 10) = *(_OWORD *)L"sVolume";
  v8 = (struct _VSS_MGMT_OBJECT_PROP *)CoTaskMemAlloc(0x30u);
  try
  {
    v9 = v8;
    pv = v8;
    if ( !v8 )
    {
      v13 = L"base\\stor\\vss\\modules\\prop\\pointer.cxx";
      v14 = L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsVolume";
      v15 = L"PRPPNTRC";
      v16 = 395;
      v17 = 11;
      v18 = 255;
      v20 = 0x1000000;
      memset_0(v19, 0, sizeof(v19));
      CVssFunctionTracer::Throw(v6, &v13, 2147942414LL, L"%s: Error on allocating the Properties structure", v23);
    }
    VSS_MGMT_OBJECT_PROP_Copy::init(v8);
    v9->Type = VSS_MGMT_OBJECT_VOLUME;
    VssSafeDuplicateStr(v6, &v9->Obj.Vol.m_pwszVolumeName, a3);
    VssSafeDuplicateStr(v6, &v9->Obj.Vol.m_pwszVolumeDisplayName, a4);
    *(_QWORD *)this = v9;
  }
  catch ( long v11 )
  {
    CVssFunctionTracer::HandleHresultException(
      a2,
      v11,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsVolume",
      0x19Eu,
      *((_DWORD *)a2 + 9));
    v6 = a2;
  }
  catch ( _com_error *v21 )
  {
    CVssFunctionTracer::HandleComException(
      a2,
      v21,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsVolume",
      0x19Eu,
      *((_DWORD *)a2 + 9));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      a2,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsVolume",
      0x19Eu,
      *((_DWORD *)a2 + 9));
    v6 = a2;
  }
  catch ( const std::exception *v22 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      a2,
      v22,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsVolume",
      0x19Eu,
      *((_DWORD *)a2 + 9));
  }
  v9 = v8;
}

```

## disassembly

```asm
0x18003b5e8  mov     rax, rsp
0x18003b5eb  mov     [rax+8], rbx
0x18003b5ef  mov     [rax+18h], rsi
0x18003b5f3  mov     [rax+10h], rdx
0x18003b5f7  push    rdi
0x18003b5f8  push    r12
0x18003b5fa  push    r13
0x18003b5fc  push    r14
0x18003b5fe  push    r15
0x18003b600  sub     rsp, 170h
0x18003b607  mov     r13, r9
0x18003b60a  mov     r15, r8
0x18003b60d  mov     rdi, rdx
0x18003b610  mov     r12, rcx
0x18003b613  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP_7; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsV"...
0x18003b61a  movaps  xmmword ptr [rax-88h], xmm0
0x18003b621  movaps  xmm1, xmmword ptr cs:aVssMgmtObjectP_7+10h; "_OBJECT_PROP_Ptr::InitializeAsVolume"
0x18003b628  movaps  xmmword ptr [rax-78h], xmm1
0x18003b62c  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP_7+20h; "PROP_Ptr::InitializeAsVolume"
0x18003b633  movaps  xmmword ptr [rax-68h], xmm0
0x18003b637  movaps  xmm1, xmmword ptr cs:aVssMgmtObjectP_7+30h; "::InitializeAsVolume"
0x18003b63e  movaps  xmmword ptr [rax-58h], xmm1
0x18003b642  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP_7+40h; "lizeAsVolume"
0x18003b649  movaps  xmmword ptr [rax-48h], xmm0
0x18003b64d  movups  xmm1, xmmword ptr cs:aVssMgmtObjectP_7+4Ah; "sVolume"
0x18003b654  movups  xmmword ptr [rax-3Eh], xmm1
0x18003b658  mov     ecx, 30h ; '0'; cb
0x18003b65d  call    cs:__imp_CoTaskMemAlloc
0x18003b663  mov     rsi, rax
0x18003b666  mov     [rsp+198h+pv], rax
0x18003b66b  xor     ebx, ebx
0x18003b66d  test    rax, rax
0x18003b670  jnz     loc_18003B6F7
0x18003b676  lea     rax, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\prop\\pointer"...
0x18003b67d  mov     [rsp+198h+var_140], rax
0x18003b682  lea     rax, aVssMgmtObjectP_7; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsV"...
0x18003b689  mov     [rsp+198h+var_138], rax
0x18003b68e  lea     rax, aPrppntrc; "PRPPNTRC"
0x18003b695  mov     [rsp+198h+var_130], rax
0x18003b69a  mov     [rsp+198h+var_128], 18Bh
0x18003b6a2  mov     [rsp+198h+var_124], 0Bh
0x18003b6aa  mov     [rsp+198h+var_120], 0FFh
0x18003b6b2  mov     [rsp+198h+var_A0], 1000000h
0x18003b6bd  xor     edx, edx; Val
0x18003b6bf  lea     r8d, [rsi+78h]; Size
0x18003b6c3  lea     rcx, [rsp+198h+var_118]; void *
0x18003b6cb  call    memset_0
0x18003b6d0  lea     rax, [rsp+198h+var_88]
0x18003b6d8  mov     [rsp+198h+var_178], rax
0x18003b6dd  lea     r9, aSErrorOnAlloca; "%s: Error on allocating the Properties "...
0x18003b6e4  mov     r8d, 8007000Eh
0x18003b6ea  lea     rdx, [rsp+198h+var_140]
0x18003b6ef  mov     rcx, rdi
0x18003b6f2  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003b6f7  mov     rcx, rsi; struct _VSS_MGMT_OBJECT_PROP *
0x18003b6fa  call    ?init@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z; VSS_MGMT_OBJECT_PROP_Copy::init(_VSS_MGMT_OBJECT_PROP *)
0x18003b6ff  mov     dword ptr [rsi], 1
0x18003b705  mov     r8, r15; unsigned __int16 *
0x18003b708  lea     rdx, [rsi+8]; unsigned __int16 **
0x18003b70c  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b70f  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b714  lea     rdx, [rsi+10h]; unsigned __int16 **
0x18003b718  mov     r8, r13; unsigned __int16 *
0x18003b71b  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b71e  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b723  mov     [r12], rsi
0x18003b727  jmp     short loc_18003B739
0x18003b729  jmp     short loc_18003B72F
0x18003b72b  jmp     short loc_18003B72F
0x18003b72d  jmp     short $+2
0x18003b72f  mov     rdi, [rsp+198h+arg_8]
0x18003b737  xor     ebx, ebx
0x18003b739  cmp     [rdi+8], ebx
0x18003b73c  jge     loc_18003B7E6
0x18003b742  mov     rsi, [rsp+198h+pv]
0x18003b747  test    rsi, rsi
0x18003b74a  jz      short loc_18003B75D
0x18003b74c  mov     rcx, rsi; struct _VSS_MGMT_OBJECT_PROP *
0x18003b74f  call    ?destroy@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z; VSS_MGMT_OBJECT_PROP_Copy::destroy(_VSS_MGMT_OBJECT_PROP *)
0x18003b754  mov     rcx, rsi; pv
0x18003b757  call    cs:__imp_CoTaskMemFree
0x18003b75d  lea     rax, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\prop\\pointer"...
0x18003b764  mov     [rsp+198h+var_140], rax
0x18003b769  lea     rax, aVssMgmtObjectP_7; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsV"...
0x18003b770  mov     [rsp+198h+var_138], rax
0x18003b775  lea     rax, aPrppntrc; "PRPPNTRC"
0x18003b77c  mov     [rsp+198h+var_130], rax
0x18003b781  mov     [rsp+198h+var_128], 1A9h
0x18003b789  mov     [rsp+198h+var_124], 0Bh
0x18003b791  mov     [rsp+198h+var_120], 0FFh
0x18003b799  mov     [rsp+198h+var_A0], 1000000h
0x18003b7a4  xor     edx, edx; Val
0x18003b7a6  lea     r8d, [rdx+78h]; Size
0x18003b7aa  lea     rcx, [rsp+198h+var_118]; void *
0x18003b7b2  call    memset_0
0x18003b7b7  mov     eax, [rdi+8]
0x18003b7ba  mov     [rsp+198h+var_170], eax
0x18003b7be  lea     rax, [rsp+198h+var_88]
0x18003b7c6  mov     [rsp+198h+var_178], rax
0x18003b7cb  lea     r9, aSErrorCatched0; "%s: Error catched 0x%08lx"
0x18003b7d2  mov     r8d, 8007000Eh
0x18003b7d8  lea     rdx, [rsp+198h+var_140]
0x18003b7dd  mov     rcx, rdi
0x18003b7e0  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003b7e6  lea     r11, [rsp+198h+var_28]
0x18003b7ee  mov     rbx, [r11+30h]
0x18003b7f2  mov     rsi, [r11+40h]
0x18003b7f6  mov     rsp, r11
0x18003b7f9  pop     r15
0x18003b7fb  pop     r14
0x18003b7fd  pop     r13
0x18003b7ff  pop     r12
0x18003b801  pop     rdi
0x18003b802  retn
```
