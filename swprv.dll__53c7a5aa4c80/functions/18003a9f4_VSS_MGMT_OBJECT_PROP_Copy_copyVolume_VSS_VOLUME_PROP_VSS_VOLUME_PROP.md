# VSS_MGMT_OBJECT_PROP_Copy::copyVolume(_VSS_VOLUME_PROP *,_VSS_VOLUME_PROP *)

- ea: `0x18003a9f4`
- end: `0x18003aad0`
- name: `?copyVolume@VSS_MGMT_OBJECT_PROP_Copy@@SAJPEAU_VSS_VOLUME_PROP@@0@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct _VSS_VOLUME_PROP *, struct _VSS_VOLUME_PROP *)`
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
- `0x18003a9f4`

## string_xrefs

- `0x18003aa25`: `PRPCOPYC`
- `0x18003aa09`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18003aa17`: `VSS_MGMT_OBJECT_PROP_Copy::copyVolume`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VSS_MGMT_OBJECT_PROP_Copy::copyVolume(struct _VSS_VOLUME_PROP *a1, struct _VSS_VOLUME_PROP *a2)
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
  v12[1] = L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume";
  v12[2] = L"PRPCOPYC";
  v13 = 221;
  v14 = 11;
  v15 = 255;
  v16[30] = 0x1000000;
  memset_0(v16, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v9, (__int64)v12, 0);
  try
  {
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeName, a2->m_pwszVolumeName);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeDisplayName, a2->m_pwszVolumeDisplayName);
  }
  catch ( long v6 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v9,
      v6,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume",
      0xE9u,
      v11);
  }
  catch ( _com_error *v7 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v9,
      v7,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume",
      0xE9u,
      v11);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v9,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume",
      0xE9u,
      v11);
  }
  catch ( const std::exception *v8 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v9,
      v8,
      L"base\\stor\\vss\\modules\\prop\\copy.cxx",
      L"PRPCOPYC",
      L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume",
      0xE9u,
      v11);
  }
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeName, a2->m_pwszVolumeName);
  VssSafeDuplicateStr((struct CVssFunctionTracer *)&v9, &a1->m_pwszVolumeDisplayName, a2->m_pwszVolumeDisplayName);
  CVssFunctionTracer::HandleHresultException(
    (CVssFunctionTracer *)&v9,
    v6,
    L"base\\stor\\vss\\modules\\prop\\copy.cxx",
    L"PRPCOPYC",
    L"VSS_MGMT_OBJECT_PROP_Copy::copyVolume",
    0xE9u,
    v11);
}

```

## disassembly

```asm
0x18003a9f4  mov     r11, rsp
0x18003a9f7  mov     [r11+10h], rbx
0x18003a9fb  push    rdi
0x18003a9fc  sub     rsp, 180h
0x18003aa03  mov     rbx, rdx
0x18003aa06  mov     rdi, rcx
0x18003aa09  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003aa10  mov     [r11-0B8h], rax
0x18003aa17  lea     rax, aVssMgmtObjectP_2; "VSS_MGMT_OBJECT_PROP_Copy::copyVolume"
0x18003aa1e  mov     [r11-0B0h], rax
0x18003aa25  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003aa2c  mov     [r11-0A8h], rax
0x18003aa33  mov     [rsp+188h+var_A0], 0DDh
0x18003aa3e  mov     [rsp+188h+var_9C], 0Bh
0x18003aa49  mov     [rsp+188h+var_98], 0FFh
0x18003aa54  mov     dword ptr [r11-18h], 1000000h
0x18003aa5c  xor     edx, edx; Val
0x18003aa5e  lea     r8d, [rdx+78h]; Size
0x18003aa62  lea     rcx, [r11-90h]; void *
0x18003aa69  call    memset_0
0x18003aa6e  xor     r8d, r8d
0x18003aa71  lea     rdx, [rsp+188h+var_B8]
0x18003aa79  lea     rcx, [rsp+188h+var_128]
0x18003aa7e  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003aa83  nop
0x18003aa84  mov     r8, [rbx]; unsigned __int16 *
0x18003aa87  mov     rdx, rdi; unsigned __int16 **
0x18003aa8a  lea     rcx, [rsp+188h+var_128]; struct CVssFunctionTracer *
0x18003aa8f  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003aa94  lea     rdx, [rdi+8]; unsigned __int16 **
0x18003aa98  mov     r8, [rbx+8]; unsigned __int16 *
0x18003aa9c  lea     rcx, [rsp+188h+var_128]; struct CVssFunctionTracer *
0x18003aaa1  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003aaa6  nop
0x18003aaa7  jmp     short loc_18003AAAF
0x18003aaa9  jmp     short loc_18003AAAF
0x18003aaab  jmp     short loc_18003AAAF
0x18003aaad  jmp     short $+2
0x18003aaaf  mov     ebx, [rsp+188h+var_120]
0x18003aab3  lea     rcx, [rsp+188h+var_128]; this
0x18003aab8  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003aabd  mov     eax, ebx
0x18003aabf  mov     rbx, [rsp+188h+arg_8]
0x18003aac7  add     rsp, 180h
0x18003aace  pop     rdi
0x18003aacf  retn
```
