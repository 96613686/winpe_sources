# VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea(_VSS_DIFF_AREA_PROP *,_VSS_DIFF_AREA_PROP *)

- ea: `0x18003a5a0`
- end: `0x18003a693`
- name: `?copyDiffArea@VSS_MGMT_OBJECT_PROP_Copy@@SAJPEAU_VSS_DIFF_AREA_PROP@@0@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct _VSS_DIFF_AREA_PROP *, struct _VSS_DIFF_AREA_PROP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026650`

## callees

- `0x18000212c`
- `0x180017284`
- `0x180033a8c`
- `0x180033c78`
- `0x18003a5a0`

## string_xrefs

- `0x18003a5d1`: `PRPCOPYC`
- `0x18003a5b5`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18003a5c3`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea(
        struct _VSS_DIFF_AREA_PROP *a1,
        struct _VSS_DIFF_AREA_PROP *a2)
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
  v12[1] = L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea";
  v12[2] = L"PRPCOPYC";
  v13 = 269;
  v14 = 11;
  v15 = 255;
  v16[30] = 0x1000000;
  memset_0(v16, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v9, (__int64)v12, 0);
  try
  {
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeName, a2->m_pwszVolumeName);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszDiffAreaVolumeName, a2->m_pwszDiffAreaVolumeName);
    a1->m_llMaximumDiffSpace = a2->m_llMaximumDiffSpace;
    a1->m_llAllocatedDiffSpace = a2->m_llAllocatedDiffSpace;
    a1->m_llUsedDiffSpace = a2->m_llUsedDiffSpace;
  }
  catch ( long v6 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v9,
      v6,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea",
      0x11Cu,
      v11);
  }
  catch ( _com_error *v7 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v9,
      v7,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea",
      0x11Cu,
      v11);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v9,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea",
      0x11Cu,
      v11);
  }
  catch ( const std::exception *v8 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v9,
      v8,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea",
      0x11Cu,
      v11);
  }
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeName, a2->m_pwszVolumeName);
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszDiffAreaVolumeName, a2->m_pwszDiffAreaVolumeName);
  a1->m_llMaximumDiffSpace = a2->m_llMaximumDiffSpace;
}

```

## disassembly

```asm
0x18003a5a0  mov     r11, rsp
0x18003a5a3  mov     [r11+10h], rbx
0x18003a5a7  push    rdi
0x18003a5a8  sub     rsp, 180h
0x18003a5af  mov     rbx, rdx
0x18003a5b2  mov     rdi, rcx
0x18003a5b5  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003a5bc  mov     [r11-0B8h], rax
0x18003a5c3  lea     rax, aVssMgmtObjectP_0; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffArea"
0x18003a5ca  mov     [r11-0B0h], rax
0x18003a5d1  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003a5d8  mov     [r11-0A8h], rax
0x18003a5df  mov     [rsp+188h+var_A0], 10Dh
0x18003a5ea  mov     [rsp+188h+var_9C], 0Bh
0x18003a5f5  mov     [rsp+188h+var_98], 0FFh
0x18003a600  mov     dword ptr [r11-18h], 1000000h
0x18003a608  xor     edx, edx; Val
0x18003a60a  lea     r8d, [rdx+78h]; Size
0x18003a60e  lea     rcx, [r11-90h]; void *
0x18003a615  call    memset_0
0x18003a61a  xor     r8d, r8d
0x18003a61d  lea     rdx, [rsp+188h+var_B8]
0x18003a625  lea     rcx, [rsp+188h+var_128]
0x18003a62a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003a62f  nop
0x18003a630  mov     r8, [rbx]; unsigned __int16 *
0x18003a633  mov     rdx, rdi; unsigned __int16 **
0x18003a636  lea     rcx, [rsp+188h+var_128]; struct CVssFunctionTracer *
0x18003a63b  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a640  lea     rdx, [rdi+8]; unsigned __int16 **
0x18003a644  mov     r8, [rbx+8]; unsigned __int16 *
0x18003a648  lea     rcx, [rsp+188h+var_128]; struct CVssFunctionTracer *
0x18003a64d  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a652  mov     rax, [rbx+10h]
0x18003a656  mov     [rdi+10h], rax
0x18003a65a  mov     rax, [rbx+18h]
0x18003a65e  mov     [rdi+18h], rax
0x18003a662  mov     rax, [rbx+20h]
0x18003a666  mov     [rdi+20h], rax
0x18003a66a  jmp     short loc_18003A672
0x18003a66c  jmp     short loc_18003A672
0x18003a66e  jmp     short loc_18003A672
0x18003a670  jmp     short $+2
0x18003a672  mov     ebx, [rsp+188h+var_120]
0x18003a676  lea     rcx, [rsp+188h+var_128]; this
0x18003a67b  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003a680  mov     eax, ebx
0x18003a682  mov     rbx, [rsp+188h+arg_8]
0x18003a68a  add     rsp, 180h
0x18003a691  pop     rdi
0x18003a692  retn
```
