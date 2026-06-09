# VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffArea(CVssFunctionTracer &,ushort *,ushort *,__int64,__int64,__int64)

- ea: `0x18003ae94`
- end: `0x18003b0e4`
- name: `?InitializeAsDiffArea@VSS_MGMT_OBJECT_PROP_Ptr@@QEAAXAEAVCVssFunctionTracer@@PEAG1_J22@Z`
- size: `592`
- prototype: `void __fastcall(VSS_MGMT_OBJECT_PROP_Ptr *this, struct CVssFunctionTracer *, unsigned __int16 *, unsigned __int16 *, LONGLONG, LONGLONG, LONGLONG)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b490`
- `0x18002c080`
- `0x18002c830`

## callees

- `0x18000212c`
- `0x180017284`
- `0x18003649c`
- `0x18003aad8`
- `0x18003ad20`
- `0x18003ae94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003af14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003af14`

## pseudocode

```c
void __fastcall VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffArea(
        VSS_MGMT_OBJECT_PROP_Ptr *this,
        struct CVssFunctionTracer *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        LONGLONG a5,
        LONGLONG a6,
        LONGLONG a7)
{
  struct CVssFunctionTracer *v9; // rdi
  struct _VSS_MGMT_OBJECT_PROP *v11; // rax
  struct _VSS_MGMT_OBJECT_PROP *v12; // rsi
  void *v13; // rsi
  _DWORD *v14; // [rsp+40h] [rbp-168h]
  unsigned int v15; // [rsp+48h] [rbp-160h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-158h]
  const unsigned __int16 *v17; // [rsp+58h] [rbp-150h] BYREF
  const unsigned __int16 *v18; // [rsp+60h] [rbp-148h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp-140h]
  int v20; // [rsp+70h] [rbp-138h]
  int v21; // [rsp+74h] [rbp-134h]
  int v22; // [rsp+78h] [rbp-130h]
  _BYTE v23[120]; // [rsp+80h] [rbp-128h] BYREF
  int v24; // [rsp+F8h] [rbp-B0h]
  _com_error *v25; // [rsp+108h] [rbp-A0h] BYREF
  const std::exception *v26; // [rsp+110h] [rbp-98h] BYREF
  _OWORD v27[4]; // [rsp+120h] [rbp-88h] BYREF
  _OWORD v28[2]; // [rsp+160h] [rbp-48h]

  v9 = a2;
  v27[0] = *(_OWORD *)L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsProvider";
  v27[1] = *(_OWORD *)L"_OBJECT_PROP_Ptr::InitializeAsProvider";
  v27[2] = *(_OWORD *)L"PROP_Ptr::InitializeAsProvider";
  v27[3] = *(_OWORD *)L"::InitializeAsProvider";
  v28[0] = *(_OWORD *)L"lizeAsProvider";
  *(_OWORD *)((char *)v28 + 14) = *(_OWORD *)L"rovider";
  v14 = (_DWORD *)((char *)a2 + 8);
  *((_DWORD *)a2 + 2) = 0;
  v11 = (struct _VSS_MGMT_OBJECT_PROP *)CoTaskMemAlloc(0x30u);
  try
  {
    v12 = v11;
    pv = v11;
    if ( !v11 )
    {
      v17 = L"base\\stor\\vss\\modules\\prop\\pointer.cxx";
      v18 = L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffArea";
      v19 = L"PRPPNTRC";
      v20 = 545;
      v21 = 11;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::Throw(v9, &v17, 2147942414LL, L"%s: Error on allocating the Properties structure", v27);
    }
    VSS_MGMT_OBJECT_PROP_Copy::init(v11);
    v12->Type = VSS_MGMT_OBJECT_DIFF_AREA;
    VssSafeDuplicateStr(v9, &v12->Obj.Vol.m_pwszVolumeName, a3);
    VssSafeDuplicateStr(v9, &v12->Obj.Vol.m_pwszVolumeDisplayName, a4);
    v12->Obj.DiffVol.m_llVolumeFreeSpace = a7;
    v12->Obj.DiffVol.m_llVolumeTotalSpace = a6;
    v12->Obj.DiffArea.m_llUsedDiffSpace = a5;
    *(_QWORD *)this = v12;
  }
  catch ( long v15 )
  {
    CVssFunctionTracer::HandleHresultException(
      a2,
      v15,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffArea",
      0x237u,
      *((_DWORD *)a2 + 9));
    v9 = a2;
  }
  catch ( _com_error *v25 )
  {
    CVssFunctionTracer::HandleComException(
      a2,
      v25,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffArea",
      0x237u,
      *((_DWORD *)a2 + 9));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      a2,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffArea",
      0x237u,
      *((_DWORD *)a2 + 9));
    v9 = a2;
  }
  catch ( const std::exception *v26 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      a2,
      v26,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffArea",
      0x237u,
      *((_DWORD *)a2 + 9));
  }
  v12 = v11;
}

```

## disassembly

```asm
0x18003ae94  mov     rax, rsp
0x18003ae97  mov     [rax+8], rbx
0x18003ae9b  mov     [rax+18h], rsi
0x18003ae9f  mov     [rax+10h], rdx
0x18003aea3  push    rdi
0x18003aea4  push    r12
0x18003aea6  push    r13
0x18003aea8  push    r14
0x18003aeaa  push    r15
0x18003aeac  sub     rsp, 180h
0x18003aeb3  mov     r12, r9
0x18003aeb6  mov     r15, r8
0x18003aeb9  mov     rdi, rdx
0x18003aebc  mov     r13, rcx
0x18003aebf  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP_5; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsP"...
0x18003aec6  movaps  xmmword ptr [rax-88h], xmm0
0x18003aecd  movaps  xmm1, xmmword ptr cs:aVssMgmtObjectP_5+10h; "_OBJECT_PROP_Ptr::InitializeAsProvider"
0x18003aed4  movaps  xmmword ptr [rax-78h], xmm1
0x18003aed8  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP_5+20h; "PROP_Ptr::InitializeAsProvider"
0x18003aedf  movaps  xmmword ptr [rax-68h], xmm0
0x18003aee3  movaps  xmm1, xmmword ptr cs:aVssMgmtObjectP_5+30h; "::InitializeAsProvider"
0x18003aeea  movaps  xmmword ptr [rax-58h], xmm1
0x18003aeee  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP_5+40h; "lizeAsProvider"
0x18003aef5  movaps  xmmword ptr [rax-48h], xmm0
0x18003aef9  movups  xmm1, xmmword ptr cs:aVssMgmtObjectP_5+4Eh; "rovider"
0x18003af00  movups  xmmword ptr [rax-3Ah], xmm1
0x18003af04  lea     rax, [rdx+8]
0x18003af08  mov     [rsp+1A8h+var_168], rax
0x18003af0d  xor     ebx, ebx
0x18003af0f  mov     [rax], ebx
0x18003af11  lea     ecx, [rbx+30h]; cb
0x18003af14  call    cs:__imp_CoTaskMemAlloc
0x18003af1a  mov     rsi, rax
0x18003af1d  mov     [rsp+1A8h+pv], rax
0x18003af22  test    rax, rax
0x18003af25  jnz     loc_18003AFAC
0x18003af2b  lea     rax, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\prop\\pointer"...
0x18003af32  mov     [rsp+1A8h+var_150], rax
0x18003af37  lea     rax, aVssMgmtObjectP_3; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsD"...
0x18003af3e  mov     [rsp+1A8h+var_148], rax
0x18003af43  lea     rax, aPrppntrc; "PRPPNTRC"
0x18003af4a  mov     [rsp+1A8h+var_140], rax
0x18003af4f  mov     [rsp+1A8h+var_138], 221h
0x18003af57  mov     [rsp+1A8h+var_134], 0Bh
0x18003af5f  mov     [rsp+1A8h+var_130], 0FFh
0x18003af67  mov     [rsp+1A8h+var_B0], 1000000h
0x18003af72  xor     edx, edx; Val
0x18003af74  lea     r8d, [rbx+78h]; Size
0x18003af78  lea     rcx, [rsp+1A8h+var_128]; void *
0x18003af80  call    memset_0
0x18003af85  lea     rax, [rsp+1A8h+var_88]
0x18003af8d  mov     [rsp+1A8h+var_188], rax
0x18003af92  lea     r9, aSErrorOnAlloca; "%s: Error on allocating the Properties "...
0x18003af99  mov     r8d, 8007000Eh
0x18003af9f  lea     rdx, [rsp+1A8h+var_150]
0x18003afa4  mov     rcx, rdi
0x18003afa7  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003afac  mov     rcx, rsi; struct _VSS_MGMT_OBJECT_PROP *
0x18003afaf  call    ?init@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z; VSS_MGMT_OBJECT_PROP_Copy::init(_VSS_MGMT_OBJECT_PROP *)
0x18003afb4  mov     dword ptr [rsi], 3
0x18003afba  mov     r8, r15; unsigned __int16 *
0x18003afbd  lea     rdx, [rsi+8]; unsigned __int16 **
0x18003afc1  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003afc4  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003afc9  lea     rdx, [rsi+10h]; unsigned __int16 **
0x18003afcd  mov     r8, r12; unsigned __int16 *
0x18003afd0  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003afd3  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003afd8  mov     rax, [rsp+1A8h+arg_30]
0x18003afe0  mov     [rsi+18h], rax
0x18003afe4  mov     rax, [rsp+1A8h+arg_28]
0x18003afec  mov     [rsi+20h], rax
0x18003aff0  mov     rax, [rsp+1A8h+arg_20]
0x18003aff8  mov     [rsi+28h], rax
0x18003affc  mov     [r13+0], rsi
0x18003b000  jmp     short loc_18003B012
0x18003b002  jmp     short loc_18003B008
0x18003b004  jmp     short loc_18003B008
0x18003b006  jmp     short $+2
0x18003b008  mov     rdi, [rsp+1A8h+arg_8]
0x18003b010  xor     ebx, ebx
0x18003b012  mov     rax, [rsp+1A8h+var_168]
0x18003b017  cmp     [rax], ebx
0x18003b019  jge     loc_18003B0C7
0x18003b01f  mov     rsi, [rsp+1A8h+pv]
0x18003b024  test    rsi, rsi
0x18003b027  jz      short loc_18003B03A
0x18003b029  mov     rcx, rsi; struct _VSS_MGMT_OBJECT_PROP *
0x18003b02c  call    ?destroy@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z; VSS_MGMT_OBJECT_PROP_Copy::destroy(_VSS_MGMT_OBJECT_PROP *)
0x18003b031  mov     rcx, rsi; pv
0x18003b034  call    cs:__imp_CoTaskMemFree
0x18003b03a  lea     rax, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\prop\\pointer"...
0x18003b041  mov     [rsp+1A8h+var_150], rax
0x18003b046  lea     rax, aVssMgmtObjectP_3; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsD"...
0x18003b04d  mov     [rsp+1A8h+var_148], rax
0x18003b052  lea     rax, aPrppntrc; "PRPPNTRC"
0x18003b059  mov     [rsp+1A8h+var_140], rax
0x18003b05e  mov     [rsp+1A8h+var_138], 242h
0x18003b066  mov     [rsp+1A8h+var_134], 0Bh
0x18003b06e  mov     [rsp+1A8h+var_130], 0FFh
0x18003b076  mov     [rsp+1A8h+var_B0], 1000000h
0x18003b081  xor     edx, edx; Val
0x18003b083  lea     r8d, [rdx+78h]; Size
0x18003b087  lea     rcx, [rsp+1A8h+var_128]; void *
0x18003b08f  call    memset_0
0x18003b094  mov     rax, [rsp+1A8h+var_168]
0x18003b099  mov     ecx, [rax]
0x18003b09b  mov     [rsp+1A8h+var_180], ecx
0x18003b09f  lea     rax, [rsp+1A8h+var_88]
0x18003b0a7  mov     [rsp+1A8h+var_188], rax
0x18003b0ac  lea     r9, aSErrorCatched0; "%s: Error catched 0x%08lx"
0x18003b0b3  mov     r8d, 8007000Eh
0x18003b0b9  lea     rdx, [rsp+1A8h+var_150]
0x18003b0be  mov     rcx, rdi
0x18003b0c1  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003b0c7  lea     r11, [rsp+1A8h+var_28]
0x18003b0cf  mov     rbx, [r11+30h]
0x18003b0d3  mov     rsi, [r11+40h]
0x18003b0d7  mov     rsp, r11
0x18003b0da  pop     r15
0x18003b0dc  pop     r14
0x18003b0de  pop     r13
0x18003b0e0  pop     r12
0x18003b0e2  pop     rdi
0x18003b0e3  retn
```
