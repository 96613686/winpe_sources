# VSS_OBJECT_PROP_Copy::init(_VSS_OBJECT_PROP *)

- ea: `0x18003ade0`
- end: `0x18003ae8d`
- name: `?init@VSS_OBJECT_PROP_Copy@@SAXPEAU_VSS_OBJECT_PROP@@@Z`
- size: `173`
- prototype: `void __fastcall(struct _VSS_OBJECT_PROP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18003b348`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003a57c`
- `0x18003ade0`

## string_xrefs

- `0x18003ae0a`: `PRPCOPYC`
- `0x18003adee`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18003adfc`: `VSS_OBJECT_PROP_Copy::init`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VSS_OBJECT_PROP_Copy::init(struct _VSS_OBJECT_PROP *a1)
{
  LPVOID v2[14]; // [rsp+60h] [rbp-128h] BYREF
  _QWORD v3[3]; // [rsp+D0h] [rbp-B8h] BYREF
  int v4; // [rsp+E8h] [rbp-A0h]
  int v5; // [rsp+ECh] [rbp-9Ch]
  int v6; // [rsp+F0h] [rbp-98h]
  _DWORD v7[36]; // [rsp+F8h] [rbp-90h] BYREF

  v3[0] = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v3[1] = L"VSS_OBJECT_PROP_Copy::init";
  v3[2] = L"PRPCOPYC";
  v4 = 165;
  v5 = 11;
  v6 = 255;
  v7[30] = 0x1000000;
  memset_0(v7, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)v2, (__int64)v3, 0);
  VssZeroOut<_VSS_OBJECT_PROP>(a1);
  CVssFunctionTracer::~CVssFunctionTracer(v2);
}

```

## disassembly

```asm
0x18003ade0  mov     r11, rsp
0x18003ade3  push    rbx
0x18003ade4  sub     rsp, 180h
0x18003adeb  mov     rbx, rcx
0x18003adee  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003adf5  mov     [r11-0B8h], rax
0x18003adfc  lea     rax, aVssObjectPropC_0; "VSS_OBJECT_PROP_Copy::init"
0x18003ae03  mov     [r11-0B0h], rax
0x18003ae0a  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003ae11  mov     [r11-0A8h], rax
0x18003ae18  mov     [rsp+188h+var_A0], 0A5h
0x18003ae23  mov     [rsp+188h+var_9C], 0Bh
0x18003ae2e  mov     [rsp+188h+var_98], 0FFh
0x18003ae39  mov     dword ptr [r11-18h], 1000000h
0x18003ae41  xor     edx, edx; Val
0x18003ae43  lea     r8d, [rdx+78h]; Size
0x18003ae47  lea     rcx, [r11-90h]; void *
0x18003ae4e  call    memset_0
0x18003ae53  xor     r8d, r8d
0x18003ae56  lea     rdx, [rsp+188h+var_B8]
0x18003ae5e  lea     rcx, [rsp+188h+var_128]
0x18003ae63  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003ae68  nop
0x18003ae69  mov     rcx, rbx
0x18003ae6c  call    ??$VssZeroOut@U_VSS_OBJECT_PROP@@@@YAXPEAU_VSS_OBJECT_PROP@@@Z; VssZeroOut<_VSS_OBJECT_PROP>(_VSS_OBJECT_PROP *)
0x18003ae71  nop
0x18003ae72  jmp     short loc_18003AE7A
0x18003ae74  jmp     short loc_18003AE7A
0x18003ae76  jmp     short loc_18003AE7A
0x18003ae78  jmp     short $+2
0x18003ae7a  lea     rcx, [rsp+188h+var_128]; this
0x18003ae7f  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003ae84  add     rsp, 180h
0x18003ae8b  pop     rbx
0x18003ae8c  retn
```
