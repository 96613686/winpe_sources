# VSS_OBJECT_PROP_Copy::copySnapshot(_VSS_SNAPSHOT_PROP *,_VSS_SNAPSHOT_PROP *)

- ea: `0x18003a894`
- end: `0x18003a9ec`
- name: `?copySnapshot@VSS_OBJECT_PROP_Copy@@SAJPEAU_VSS_SNAPSHOT_PROP@@0@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct _VSS_SNAPSHOT_PROP *, struct _VSS_SNAPSHOT_PROP *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180010a20`
- `0x1800179f0`

## callees

- `0x18000212c`
- `0x180017284`
- `0x180033a8c`
- `0x180033c78`
- `0x18003a894`

## string_xrefs

- `0x18003a8b7`: `VSS_OBJECT_PROP_Copy::copySnapshot`
- `0x18003a8c5`: `PRPCOPYC`
- `0x18003a8a9`: `base\stor\vss\modules\prop\copy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VSS_OBJECT_PROP_Copy::copySnapshot(struct _VSS_SNAPSHOT_PROP *a1, struct _VSS_SNAPSHOT_PROP *a2)
{
  unsigned int v4; // ebx
  int v6; // [rsp+40h] [rbp-148h] BYREF
  LPVOID v7; // [rsp+50h] [rbp-138h] BYREF
  unsigned int v8; // [rsp+58h] [rbp-130h]
  unsigned int v9; // [rsp+74h] [rbp-114h]
  _com_error *v10; // [rsp+C0h] [rbp-C8h] BYREF
  const std::exception *v11; // [rsp+C8h] [rbp-C0h] BYREF
  _QWORD v12[3]; // [rsp+D0h] [rbp-B8h] BYREF
  int v13; // [rsp+E8h] [rbp-A0h]
  int v14; // [rsp+ECh] [rbp-9Ch]
  int v15; // [rsp+F0h] [rbp-98h]
  _DWORD v16[36]; // [rsp+F8h] [rbp-90h] BYREF

  v12[0] = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v12[1] = L"VSS_OBJECT_PROP_Copy::copySnapshot";
  v12[2] = L"PRPCOPYC";
  v13 = 67;
  v14 = 11;
  v15 = 255;
  v16[30] = 0x1000000;
  memset_0(v16, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v7, (__int64)v12, 0);
  a1->m_SnapshotId = a2->m_SnapshotId;
  a1->m_SnapshotSetId = a2->m_SnapshotSetId;
  a1->m_lSnapshotsCount = a2->m_lSnapshotsCount;
  try
  {
    VssSafeDuplicateStr(
      (struct CVssFunctionTracer *)&v7,
      &a1->m_pwszSnapshotDeviceObject,
      a2->m_pwszSnapshotDeviceObject);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v7, &a1->m_pwszOriginalVolumeName, a2->m_pwszOriginalVolumeName);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v7, &a1->m_pwszOriginatingMachine, a2->m_pwszOriginatingMachine);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v7, &a1->m_pwszServiceMachine, a2->m_pwszServiceMachine);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v7, &a1->m_pwszExposedName, a2->m_pwszExposedName);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v7, &a1->m_pwszExposedPath, a2->m_pwszExposedPath);
    a1->m_ProviderId = a2->m_ProviderId;
    a1->m_lSnapshotAttributes = a2->m_lSnapshotAttributes;
    a1->m_tsCreationTimestamp = a2->m_tsCreationTimestamp;
    a1->m_eStatus = a2->m_eStatus;
  }
  catch ( long v6 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v7,
      v6,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_OBJECT_PROP_Copy::copySnapshot",
      0x5Au,
      v9);
  }
  catch ( _com_error *v10 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v7,
      v10,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_OBJECT_PROP_Copy::copySnapshot",
      0x5Au,
      v9);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v7,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_OBJECT_PROP_Copy::copySnapshot",
      0x5Au,
      v9);
  }
  catch ( const std::exception *v11 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v7,
      v11,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_OBJECT_PROP_Copy::copySnapshot",
      0x5Au,
      v9);
  }
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v7, &a1->m_pwszSnapshotDeviceObject, a2->m_pwszSnapshotDeviceObject);
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v7, &a1->m_pwszOriginalVolumeName, a2->m_pwszOriginalVolumeName);
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v7, &a1->m_pwszOriginatingMachine, a2->m_pwszOriginatingMachine);
}

```

## disassembly

```asm
0x18003a894  mov     r11, rsp
0x18003a897  mov     [r11+10h], rbx
0x18003a89b  push    rdi
0x18003a89c  sub     rsp, 180h
0x18003a8a3  mov     rbx, rdx
0x18003a8a6  mov     rdi, rcx
0x18003a8a9  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003a8b0  mov     [r11-0B8h], rax
0x18003a8b7  lea     rax, aVssObjectPropC_1; "VSS_OBJECT_PROP_Copy::copySnapshot"
0x18003a8be  mov     [r11-0B0h], rax
0x18003a8c5  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003a8cc  mov     [r11-0A8h], rax
0x18003a8d3  mov     [rsp+188h+var_A0], 43h ; 'C'
0x18003a8de  mov     [rsp+188h+var_9C], 0Bh
0x18003a8e9  mov     [rsp+188h+var_98], 0FFh
0x18003a8f4  mov     dword ptr [r11-18h], 1000000h
0x18003a8fc  xor     edx, edx; Val
0x18003a8fe  lea     r8d, [rdx+78h]; Size
0x18003a902  lea     rcx, [r11-90h]; void *
0x18003a909  call    memset_0
0x18003a90e  xor     r8d, r8d
0x18003a911  lea     rdx, [rsp+188h+var_B8]
0x18003a919  lea     rcx, [rsp+188h+var_138]
0x18003a91e  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003a923  nop
0x18003a924  movups  xmm0, xmmword ptr [rbx]
0x18003a927  movdqu  xmmword ptr [rdi], xmm0
0x18003a92b  movups  xmm1, xmmword ptr [rbx+10h]
0x18003a92f  movdqu  xmmword ptr [rdi+10h], xmm1
0x18003a934  mov     eax, [rbx+20h]
0x18003a937  mov     [rdi+20h], eax
0x18003a93a  lea     rdx, [rdi+28h]; unsigned __int16 **
0x18003a93e  mov     r8, [rbx+28h]; unsigned __int16 *
0x18003a942  lea     rcx, [rsp+188h+var_138]; struct CVssFunctionTracer *
0x18003a947  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a94c  lea     rdx, [rdi+30h]; unsigned __int16 **
0x18003a950  mov     r8, [rbx+30h]; unsigned __int16 *
0x18003a954  lea     rcx, [rsp+188h+var_138]; struct CVssFunctionTracer *
0x18003a959  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a95e  lea     rdx, [rdi+38h]; unsigned __int16 **
0x18003a962  mov     r8, [rbx+38h]; unsigned __int16 *
0x18003a966  lea     rcx, [rsp+188h+var_138]; struct CVssFunctionTracer *
0x18003a96b  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a970  lea     rdx, [rdi+40h]; unsigned __int16 **
0x18003a974  mov     r8, [rbx+40h]; unsigned __int16 *
0x18003a978  lea     rcx, [rsp+188h+var_138]; struct CVssFunctionTracer *
0x18003a97d  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a982  lea     rdx, [rdi+48h]; unsigned __int16 **
0x18003a986  mov     r8, [rbx+48h]; unsigned __int16 *
0x18003a98a  lea     rcx, [rsp+188h+var_138]; struct CVssFunctionTracer *
0x18003a98f  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a994  lea     rdx, [rdi+50h]; unsigned __int16 **
0x18003a998  mov     r8, [rbx+50h]; unsigned __int16 *
0x18003a99c  lea     rcx, [rsp+188h+var_138]; struct CVssFunctionTracer *
0x18003a9a1  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a9a6  movups  xmm0, xmmword ptr [rbx+58h]
0x18003a9aa  movdqu  xmmword ptr [rdi+58h], xmm0
0x18003a9af  mov     eax, [rbx+68h]
0x18003a9b2  mov     [rdi+68h], eax
0x18003a9b5  mov     rax, [rbx+70h]
0x18003a9b9  mov     [rdi+70h], rax
0x18003a9bd  mov     eax, [rbx+78h]
0x18003a9c0  mov     [rdi+78h], eax
0x18003a9c3  jmp     short loc_18003A9CB
0x18003a9c5  jmp     short loc_18003A9CB
0x18003a9c7  jmp     short loc_18003A9CB
0x18003a9c9  jmp     short $+2
0x18003a9cb  mov     ebx, [rsp+188h+var_130]
0x18003a9cf  lea     rcx, [rsp+188h+var_138]; this
0x18003a9d4  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003a9d9  mov     eax, ebx
0x18003a9db  mov     rbx, [rsp+188h+arg_8]
0x18003a9e3  add     rsp, 180h
0x18003a9ea  pop     rdi
0x18003a9eb  retn
```
