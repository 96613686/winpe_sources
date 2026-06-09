# VSS_MGMT_OBJECT_PROP_Copy::init(_VSS_MGMT_OBJECT_PROP *)

- ea: `0x18003ad20`
- end: `0x18003add7`
- name: `?init@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z`
- size: `183`
- prototype: `void __fastcall(struct _VSS_MGMT_OBJECT_PROP *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003ae94`
- `0x18003b0ec`
- `0x18003b5e8`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003ad20`

## string_xrefs

- `0x18003ad4a`: `PRPCOPYC`
- `0x18003ad2e`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18003ad3c`: `VSS_MGMT_OBJECT_PROP_Copy::init`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VSS_MGMT_OBJECT_PROP_Copy::init(struct _VSS_MGMT_OBJECT_PROP *a1)
{
  LPVOID v2[14]; // [rsp+60h] [rbp-128h] BYREF
  _QWORD v3[3]; // [rsp+D0h] [rbp-B8h] BYREF
  int v4; // [rsp+E8h] [rbp-A0h]
  int v5; // [rsp+ECh] [rbp-9Ch]
  int v6; // [rsp+F0h] [rbp-98h]
  _DWORD v7[36]; // [rsp+F8h] [rbp-90h] BYREF

  v3[0] = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v3[1] = L"VSS_MGMT_OBJECT_PROP_Copy::init";
  v3[2] = L"PRPCOPYC";
  v4 = 336;
  v5 = 11;
  v6 = 255;
  v7[30] = 0x1000000;
  memset_0(v7, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)v2, (__int64)v3, 0);
  if ( a1 )
  {
    *(_OWORD *)&a1->Type = 0;
    *(_OWORD *)&a1->Obj.DiffArea.m_pwszDiffAreaVolumeName = 0;
    *(_OWORD *)&a1->Obj.DiffArea.m_llAllocatedDiffSpace = 0;
  }
  CVssFunctionTracer::~CVssFunctionTracer(v2);
}

```

## disassembly

```asm
0x18003ad20  mov     r11, rsp
0x18003ad23  push    rbx
0x18003ad24  sub     rsp, 180h
0x18003ad2b  mov     rbx, rcx
0x18003ad2e  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003ad35  mov     [r11-0B8h], rax
0x18003ad3c  lea     rax, aVssMgmtObjectP_6; "VSS_MGMT_OBJECT_PROP_Copy::init"
0x18003ad43  mov     [r11-0B0h], rax
0x18003ad4a  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003ad51  mov     [r11-0A8h], rax
0x18003ad58  mov     [rsp+188h+var_A0], 150h
0x18003ad63  mov     [rsp+188h+var_9C], 0Bh
0x18003ad6e  mov     [rsp+188h+var_98], 0FFh
0x18003ad79  mov     dword ptr [r11-18h], 1000000h
0x18003ad81  xor     edx, edx; Val
0x18003ad83  lea     r8d, [rdx+78h]; Size
0x18003ad87  lea     rcx, [r11-90h]; void *
0x18003ad8e  call    memset_0
0x18003ad93  xor     r8d, r8d
0x18003ad96  lea     rdx, [rsp+188h+var_B8]
0x18003ad9e  lea     rcx, [rsp+188h+var_128]
0x18003ada3  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003ada8  nop
0x18003ada9  test    rbx, rbx
0x18003adac  jz      short loc_18003ADBC
0x18003adae  xorps   xmm0, xmm0
0x18003adb1  movups  xmmword ptr [rbx], xmm0
0x18003adb4  movups  xmmword ptr [rbx+10h], xmm0
0x18003adb8  movups  xmmword ptr [rbx+20h], xmm0
0x18003adbc  jmp     short loc_18003ADC4
0x18003adbe  jmp     short loc_18003ADC4
0x18003adc0  jmp     short loc_18003ADC4
0x18003adc2  jmp     short $+2
0x18003adc4  lea     rcx, [rsp+188h+var_128]; this
0x18003adc9  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003adce  add     rsp, 180h
0x18003add5  pop     rbx
0x18003add6  retn
```
