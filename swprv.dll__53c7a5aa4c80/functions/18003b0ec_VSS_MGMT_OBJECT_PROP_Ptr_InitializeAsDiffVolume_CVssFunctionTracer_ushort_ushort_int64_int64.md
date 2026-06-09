# VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume(CVssFunctionTracer &,ushort *,ushort *,__int64,__int64)

- ea: `0x18003b0ec`
- end: `0x18003b342`
- name: `?InitializeAsDiffVolume@VSS_MGMT_OBJECT_PROP_Ptr@@QEAAXAEAVCVssFunctionTracer@@PEAG1_J2@Z`
- size: `598`
- prototype: `void __fastcall(VSS_MGMT_OBJECT_PROP_Ptr *this, struct CVssFunctionTracer *, unsigned __int16 *, unsigned __int16 *, LONGLONG, LONGLONG)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d1f0`

## callees

- `0x18000212c`
- `0x180017284`
- `0x18003649c`
- `0x18003aad8`
- `0x18003ad20`
- `0x18003b0ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b17e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b17e`

## pseudocode

```c
void __fastcall VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume(
        VSS_MGMT_OBJECT_PROP_Ptr *this,
        struct CVssFunctionTracer *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        LONGLONG a5,
        LONGLONG a6)
{
  struct CVssFunctionTracer *v8; // rdi
  struct _VSS_MGMT_OBJECT_PROP *v10; // rax
  struct _VSS_MGMT_OBJECT_PROP *v11; // rsi
  void *v12; // rsi
  _DWORD *v13; // [rsp+40h] [rbp-178h]
  unsigned int v14; // [rsp+48h] [rbp-170h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-168h]
  const unsigned __int16 *v16; // [rsp+58h] [rbp-160h] BYREF
  const unsigned __int16 *v17; // [rsp+60h] [rbp-158h]
  const unsigned __int16 *v18; // [rsp+68h] [rbp-150h]
  int v19; // [rsp+70h] [rbp-148h]
  int v20; // [rsp+74h] [rbp-144h]
  int v21; // [rsp+78h] [rbp-140h]
  _BYTE v22[120]; // [rsp+80h] [rbp-138h] BYREF
  int v23; // [rsp+F8h] [rbp-C0h]
  _com_error *v24; // [rsp+108h] [rbp-B0h] BYREF
  const std::exception *v25; // [rsp+110h] [rbp-A8h] BYREF
  _OWORD v26[6]; // [rsp+120h] [rbp-98h] BYREF
  unsigned __int16 v27; // [rsp+180h] [rbp-38h]

  v8 = a2;
  v26[0] = *(_OWORD *)L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume";
  v26[1] = *(_OWORD *)L"_OBJECT_PROP_Ptr::InitializeAsDiffVolume";
  v26[2] = *(_OWORD *)L"PROP_Ptr::InitializeAsDiffVolume";
  v26[3] = *(_OWORD *)L"::InitializeAsDiffVolume";
  v26[4] = *(_OWORD *)L"lizeAsDiffVolume";
  v26[5] = *(_OWORD *)L"ffVolume";
  v27 = aVssMgmtObjectP[48];
  v13 = (_DWORD *)((char *)a2 + 8);
  *((_DWORD *)a2 + 2) = 0;
  v10 = (struct _VSS_MGMT_OBJECT_PROP *)CoTaskMemAlloc(0x30u);
  try
  {
    v11 = v10;
    pv = v10;
    if ( !v10 )
    {
      v16 = L"base\\stor\\vss\\modules\\prop\\pointer.cxx";
      v17 = L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume";
      v18 = L"PRPPNTRC";
      v19 = 468;
      v20 = 11;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::Throw(v8, &v16, 2147942414LL, L"%s: Error on allocating the Properties structure", v26);
    }
    VSS_MGMT_OBJECT_PROP_Copy::init(v10);
    v11->Type = VSS_MGMT_OBJECT_DIFF_VOLUME;
    VssSafeDuplicateStr(v8, &v11->Obj.Vol.m_pwszVolumeName, a3);
    VssSafeDuplicateStr(v8, &v11->Obj.Vol.m_pwszVolumeDisplayName, a4);
    v11->Obj.DiffVol.m_llVolumeFreeSpace = a5;
    v11->Obj.DiffVol.m_llVolumeTotalSpace = a6;
    *(_QWORD *)this = v11;
  }
  catch ( long v14 )
  {
    CVssFunctionTracer::HandleHresultException(
      a2,
      v14,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume",
      0x1E9u,
      *((_DWORD *)a2 + 9));
    v8 = a2;
  }
  catch ( _com_error *v24 )
  {
    CVssFunctionTracer::HandleComException(
      a2,
      v24,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume",
      0x1E9u,
      *((_DWORD *)a2 + 9));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      a2,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume",
      0x1E9u,
      *((_DWORD *)a2 + 9));
    v8 = a2;
  }
  catch ( const std::exception *v25 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      a2,
      v25,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsDiffVolume",
      0x1E9u,
      *((_DWORD *)a2 + 9));
  }
  v11 = v10;
}

```

## disassembly

```asm
0x18003b0ec  mov     rax, rsp
0x18003b0ef  mov     [rax+8], rbx
0x18003b0f3  mov     [rax+18h], rsi
0x18003b0f7  mov     [rax+10h], rdx
0x18003b0fb  push    rdi
0x18003b0fc  push    r12
0x18003b0fe  push    r13
0x18003b100  push    r14
0x18003b102  push    r15
0x18003b104  sub     rsp, 190h
0x18003b10b  mov     r12, r9
0x18003b10e  mov     r15, r8
0x18003b111  mov     rdi, rdx
0x18003b114  mov     r13, rcx
0x18003b117  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsD"...
0x18003b11e  movaps  xmmword ptr [rax-98h], xmm0
0x18003b125  movaps  xmm1, xmmword ptr cs:aVssMgmtObjectP+10h; "_OBJECT_PROP_Ptr::InitializeAsDiffVolum"...
0x18003b12c  movaps  xmmword ptr [rax-88h], xmm1
0x18003b133  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP+20h; "PROP_Ptr::InitializeAsDiffVolume"
0x18003b13a  movaps  xmmword ptr [rax-78h], xmm0
0x18003b13e  movaps  xmm1, xmmword ptr cs:aVssMgmtObjectP+30h; "::InitializeAsDiffVolume"
0x18003b145  movaps  xmmword ptr [rax-68h], xmm1
0x18003b149  movaps  xmm0, xmmword ptr cs:aVssMgmtObjectP+40h; "lizeAsDiffVolume"
0x18003b150  movaps  xmmword ptr [rax-58h], xmm0
0x18003b154  movaps  xmm1, xmmword ptr cs:aVssMgmtObjectP+50h; "ffVolume"
0x18003b15b  movaps  xmmword ptr [rax-48h], xmm1
0x18003b15f  movzx   eax, word ptr cs:aVssMgmtObjectP+60h; ""
0x18003b166  mov     [rsp+1B8h+var_38], ax
0x18003b16e  lea     rax, [rdx+8]
0x18003b172  mov     [rsp+1B8h+var_178], rax
0x18003b177  xor     ebx, ebx
0x18003b179  mov     [rax], ebx
0x18003b17b  lea     ecx, [rbx+30h]; cb
0x18003b17e  call    cs:__imp_CoTaskMemAlloc
0x18003b184  mov     rsi, rax
0x18003b187  mov     [rsp+1B8h+pv], rax
0x18003b18c  test    rax, rax
0x18003b18f  jnz     loc_18003B216
0x18003b195  lea     rax, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\prop\\pointer"...
0x18003b19c  mov     [rsp+1B8h+var_160], rax
0x18003b1a1  lea     rax, aVssMgmtObjectP; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsD"...
0x18003b1a8  mov     [rsp+1B8h+var_158], rax
0x18003b1ad  lea     rax, aPrppntrc; "PRPPNTRC"
0x18003b1b4  mov     [rsp+1B8h+var_150], rax
0x18003b1b9  mov     [rsp+1B8h+var_148], 1D4h
0x18003b1c1  mov     [rsp+1B8h+var_144], 0Bh
0x18003b1c9  mov     [rsp+1B8h+var_140], 0FFh
0x18003b1d1  mov     [rsp+1B8h+var_C0], 1000000h
0x18003b1dc  xor     edx, edx; Val
0x18003b1de  lea     r8d, [rbx+78h]; Size
0x18003b1e2  lea     rcx, [rsp+1B8h+var_138]; void *
0x18003b1ea  call    memset_0
0x18003b1ef  lea     rax, [rsp+1B8h+var_98]
0x18003b1f7  mov     [rsp+1B8h+var_198], rax
0x18003b1fc  lea     r9, aSErrorOnAlloca; "%s: Error on allocating the Properties "...
0x18003b203  mov     r8d, 8007000Eh
0x18003b209  lea     rdx, [rsp+1B8h+var_160]
0x18003b20e  mov     rcx, rdi
0x18003b211  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003b216  mov     rcx, rsi; struct _VSS_MGMT_OBJECT_PROP *
0x18003b219  call    ?init@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z; VSS_MGMT_OBJECT_PROP_Copy::init(_VSS_MGMT_OBJECT_PROP *)
0x18003b21e  mov     dword ptr [rsi], 2
0x18003b224  mov     r8, r15; unsigned __int16 *
0x18003b227  lea     rdx, [rsi+8]; unsigned __int16 **
0x18003b22b  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b22e  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b233  lea     rdx, [rsi+10h]; unsigned __int16 **
0x18003b237  mov     r8, r12; unsigned __int16 *
0x18003b23a  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b23d  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b242  mov     rax, [rsp+1B8h+arg_20]
0x18003b24a  mov     [rsi+18h], rax
0x18003b24e  mov     rax, [rsp+1B8h+arg_28]
0x18003b256  mov     [rsi+20h], rax
0x18003b25a  mov     [r13+0], rsi
0x18003b25e  jmp     short loc_18003B270
0x18003b260  jmp     short loc_18003B266
0x18003b262  jmp     short loc_18003B266
0x18003b264  jmp     short $+2
0x18003b266  mov     rdi, [rsp+1B8h+arg_8]
0x18003b26e  xor     ebx, ebx
0x18003b270  mov     rax, [rsp+1B8h+var_178]
0x18003b275  cmp     [rax], ebx
0x18003b277  jge     loc_18003B325
0x18003b27d  mov     rsi, [rsp+1B8h+pv]
0x18003b282  test    rsi, rsi
0x18003b285  jz      short loc_18003B298
0x18003b287  mov     rcx, rsi; struct _VSS_MGMT_OBJECT_PROP *
0x18003b28a  call    ?destroy@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z; VSS_MGMT_OBJECT_PROP_Copy::destroy(_VSS_MGMT_OBJECT_PROP *)
0x18003b28f  mov     rcx, rsi; pv
0x18003b292  call    cs:__imp_CoTaskMemFree
0x18003b298  lea     rax, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\prop\\pointer"...
0x18003b29f  mov     [rsp+1B8h+var_160], rax
0x18003b2a4  lea     rax, aVssMgmtObjectP; "VSS_MGMT_OBJECT_PROP_Ptr::InitializeAsD"...
0x18003b2ab  mov     [rsp+1B8h+var_158], rax
0x18003b2b0  lea     rax, aPrppntrc; "PRPPNTRC"
0x18003b2b7  mov     [rsp+1B8h+var_150], rax
0x18003b2bc  mov     [rsp+1B8h+var_148], 1F4h
0x18003b2c4  mov     [rsp+1B8h+var_144], 0Bh
0x18003b2cc  mov     [rsp+1B8h+var_140], 0FFh
0x18003b2d4  mov     [rsp+1B8h+var_C0], 1000000h
0x18003b2df  xor     edx, edx; Val
0x18003b2e1  lea     r8d, [rdx+78h]; Size
0x18003b2e5  lea     rcx, [rsp+1B8h+var_138]; void *
0x18003b2ed  call    memset_0
0x18003b2f2  mov     rax, [rsp+1B8h+var_178]
0x18003b2f7  mov     ecx, [rax]
0x18003b2f9  mov     [rsp+1B8h+var_190], ecx
0x18003b2fd  lea     rax, [rsp+1B8h+var_98]
0x18003b305  mov     [rsp+1B8h+var_198], rax
0x18003b30a  lea     r9, aSErrorCatched0; "%s: Error catched 0x%08lx"
0x18003b311  mov     r8d, 8007000Eh
0x18003b317  lea     rdx, [rsp+1B8h+var_160]
0x18003b31c  mov     rcx, rdi
0x18003b31f  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003b325  lea     r11, [rsp+1B8h+var_28]
0x18003b32d  mov     rbx, [r11+30h]
0x18003b331  mov     rsi, [r11+40h]
0x18003b335  mov     rsp, r11
0x18003b338  pop     r15
0x18003b33a  pop     r14
0x18003b33c  pop     r13
0x18003b33e  pop     r12
0x18003b340  pop     rdi
0x18003b341  retn
```
