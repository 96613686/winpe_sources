# CVssQueuedSnapshot::ResetAsPreparing(void)

- ea: `0x18001a770`
- end: `0x18001a852`
- name: `?ResetAsPreparing@CVssQueuedSnapshot@@QEAAXXZ`
- size: `226`
- prototype: `void __fastcall(CVssQueuedSnapshot *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de70`

## callees

- `0x18000212c`
- `0x180004a38`
- `0x180019458`
- `0x180033a8c`
- `0x180033c78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a809`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a809`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssQueuedSnapshot::ResetAsPreparing(CVssQueuedSnapshot *this)
{
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // rbx
  _QWORD v3[3]; // [rsp+20h] [rbp-E0h] BYREF
  int v4; // [rsp+38h] [rbp-C8h]
  int v5; // [rsp+3Ch] [rbp-C4h]
  int v6; // [rsp+40h] [rbp-C0h]
  _BYTE v7[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v8; // [rsp+C0h] [rbp-40h]
  LPVOID v9[14]; // [rsp+D0h] [rbp-30h] BYREF

  v3[0] = L"base\\stor\\vss\\modules\\softprv\\src\\qsnap.cxx";
  v3[1] = L"CVssQueuedSnapshot::ResetAsPreparing";
  v3[2] = L"SPRQSNPC";
  v4 = 660;
  v5 = 2;
  v6 = 255;
  v8 = 0x1000000;
  memset_0(v7, 0, sizeof(v7));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v9, (__int64)v3, 0);
  SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties(this);
  SnapshotProperties->m_SnapshotId = GUID_NULL;
  CoTaskMemFree(SnapshotProperties->m_pwszSnapshotDeviceObject);
  SnapshotProperties->m_pwszSnapshotDeviceObject = 0;
  SnapshotProperties->m_eStatus = VSS_SS_PREPARING;
  CVssIOCTLChannel::Close((CVssQueuedSnapshot *)((char *)this + 32));
  CVssIOCTLChannel::Close((CVssQueuedSnapshot *)((char *)this + 144));
  CVssFunctionTracer::~CVssFunctionTracer(v9);
}

```

## disassembly

```asm
0x18001a770  mov     [rsp-8+arg_8], rbx
0x18001a775  mov     [rsp-8+arg_10], rdi
0x18001a77a  push    rbp
0x18001a77b  lea     rbp, [rsp-40h]
0x18001a780  sub     rsp, 140h
0x18001a787  mov     rdi, rcx
0x18001a78a  lea     rax, aBaseStorVssMod_18; "base\\stor\\vss\\modules\\softprv\\src"...
0x18001a791  mov     [rsp+140h+var_120], rax
0x18001a796  lea     rax, aCvssqueuedsnap_4; "CVssQueuedSnapshot::ResetAsPreparing"
0x18001a79d  mov     [rsp+140h+var_118], rax
0x18001a7a2  lea     rax, aSprqsnpc; "SPRQSNPC"
0x18001a7a9  mov     [rsp+140h+var_110], rax
0x18001a7ae  mov     [rsp+140h+var_108], 294h
0x18001a7b6  mov     [rsp+140h+var_104], 2
0x18001a7be  mov     [rsp+140h+var_100], 0FFh
0x18001a7c6  mov     [rbp+40h+var_80], 1000000h
0x18001a7cd  xor     edx, edx; Val
0x18001a7cf  lea     r8d, [rdx+78h]; Size
0x18001a7d3  lea     rcx, [rsp+140h+var_F8]; void *
0x18001a7d8  call    memset_0
0x18001a7dd  xor     r8d, r8d
0x18001a7e0  lea     rdx, [rsp+140h+var_120]
0x18001a7e5  lea     rcx, [rbp+40h+var_70]
0x18001a7e9  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18001a7ee  nop
0x18001a7ef  mov     rcx, rdi; this
0x18001a7f2  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18001a7f7  mov     rbx, rax
0x18001a7fa  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001a801  movdqu  xmmword ptr [rax], xmm0
0x18001a805  mov     rcx, [rax+28h]; pv
0x18001a809  call    cs:__imp_CoTaskMemFree
0x18001a80f  mov     qword ptr [rbx+28h], 0
0x18001a817  mov     dword ptr [rbx+78h], 1
0x18001a81e  lea     rcx, [rdi+20h]; this
0x18001a822  call    ?Close@CVssIOCTLChannel@@QEAAXXZ; CVssIOCTLChannel::Close(void)
0x18001a827  lea     rcx, [rdi+90h]; this
0x18001a82e  call    ?Close@CVssIOCTLChannel@@QEAAXXZ; CVssIOCTLChannel::Close(void)
0x18001a833  nop
0x18001a834  lea     rcx, [rbp+40h+var_70]; this
0x18001a838  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001a83d  lea     r11, [rsp+140h+var_s0]
0x18001a845  mov     rbx, [r11+18h]
0x18001a849  mov     rdi, [r11+20h]
0x18001a84d  mov     rsp, r11
0x18001a850  pop     rbp
0x18001a851  retn
```
