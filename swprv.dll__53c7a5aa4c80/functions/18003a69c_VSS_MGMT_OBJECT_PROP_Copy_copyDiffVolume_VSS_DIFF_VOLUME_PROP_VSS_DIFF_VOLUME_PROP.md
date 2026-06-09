# VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume(_VSS_DIFF_VOLUME_PROP *,_VSS_DIFF_VOLUME_PROP *)

- ea: `0x18003a69c`
- end: `0x18003a787`
- name: `?copyDiffVolume@VSS_MGMT_OBJECT_PROP_Copy@@SAJPEAU_VSS_DIFF_VOLUME_PROP@@0@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct _VSS_DIFF_VOLUME_PROP *, struct _VSS_DIFF_VOLUME_PROP *)`
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
- `0x18003a69c`

## string_xrefs

- `0x18003a6cd`: `PRPCOPYC`
- `0x18003a6b1`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18003a6bf`: `VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume(
        struct _VSS_DIFF_VOLUME_PROP *a1,
        struct _VSS_DIFF_VOLUME_PROP *a2)
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
  v12[1] = L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume";
  v12[2] = L"PRPCOPYC";
  v13 = 244;
  v14 = 11;
  v15 = 255;
  v16[30] = 0x1000000;
  memset_0(v16, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v9, (__int64)v12, 0);
  try
  {
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeName, a2->m_pwszVolumeName);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeDisplayName, a2->m_pwszVolumeDisplayName);
    a1->m_llVolumeFreeSpace = a2->m_llVolumeFreeSpace;
    a1->m_llVolumeTotalSpace = a2->m_llVolumeTotalSpace;
  }
  catch ( long v6 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v9,
      v6,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume",
      0x102u,
      v11);
  }
  catch ( _com_error *v7 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v9,
      v7,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume",
      0x102u,
      v11);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v9,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume",
      0x102u,
      v11);
  }
  catch ( const std::exception *v8 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v9,
      v8,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolume",
      0x102u,
      v11);
  }
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeName, a2->m_pwszVolumeName);
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeDisplayName, a2->m_pwszVolumeDisplayName);
  a1->m_llVolumeFreeSpace = a2->m_llVolumeFreeSpace;
}

```

## disassembly

```asm
0x18003a69c  mov     r11, rsp
0x18003a69f  mov     [r11+10h], rbx
0x18003a6a3  push    rdi
0x18003a6a4  sub     rsp, 180h
0x18003a6ab  mov     rbx, rdx
0x18003a6ae  mov     rdi, rcx
0x18003a6b1  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003a6b8  mov     [r11-0B8h], rax
0x18003a6bf  lea     rax, aVssMgmtObjectP_1; "VSS_MGMT_OBJECT_PROP_Copy::copyDiffVolu"...
0x18003a6c6  mov     [r11-0B0h], rax
0x18003a6cd  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003a6d4  mov     [r11-0A8h], rax
0x18003a6db  mov     [rsp+188h+var_A0], 0F4h
0x18003a6e6  mov     [rsp+188h+var_9C], 0Bh
0x18003a6f1  mov     [rsp+188h+var_98], 0FFh
0x18003a6fc  mov     dword ptr [r11-18h], 1000000h
0x18003a704  xor     edx, edx; Val
0x18003a706  lea     r8d, [rdx+78h]; Size
0x18003a70a  lea     rcx, [r11-90h]; void *
0x18003a711  call    memset_0
0x18003a716  xor     r8d, r8d
0x18003a719  lea     rdx, [rsp+188h+var_B8]
0x18003a721  lea     rcx, [rsp+188h+var_128]
0x18003a726  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003a72b  nop
0x18003a72c  mov     r8, [rbx]; unsigned __int16 *
0x18003a72f  mov     rdx, rdi; unsigned __int16 **
0x18003a732  lea     rcx, [rsp+188h+var_128]; struct CVssFunctionTracer *
0x18003a737  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a73c  lea     rdx, [rdi+8]; unsigned __int16 **
0x18003a740  mov     r8, [rbx+8]; unsigned __int16 *
0x18003a744  lea     rcx, [rsp+188h+var_128]; struct CVssFunctionTracer *
0x18003a749  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003a74e  mov     rax, [rbx+10h]
0x18003a752  mov     [rdi+10h], rax
0x18003a756  mov     rax, [rbx+18h]
0x18003a75a  mov     [rdi+18h], rax
0x18003a75e  jmp     short loc_18003A766
0x18003a760  jmp     short loc_18003A766
0x18003a762  jmp     short loc_18003A766
0x18003a764  jmp     short $+2
0x18003a766  mov     ebx, [rsp+188h+var_120]
0x18003a76a  lea     rcx, [rsp+188h+var_128]; this
0x18003a76f  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003a774  mov     eax, ebx
0x18003a776  mov     rbx, [rsp+188h+arg_8]
0x18003a77e  add     rsp, 180h
0x18003a785  pop     rdi
0x18003a786  retn
```
