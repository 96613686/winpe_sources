# CVdsService::RemoveObjectFromMap(IUnknown *,_VDS_OBJECT_TYPE)

- ea: `0x140009610`
- end: `0x1400096fb`
- name: `?RemoveObjectFromMap@CVdsService@@QEAAXPEAUIUnknown@@W4_VDS_OBJECT_TYPE@@@Z`
- size: `235`
- prototype: `void __fastcall(CVdsService *__hidden this, struct IUnknown *, enum _VDS_OBJECT_TYPE)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x140001980`
- `0x140008b10`
- `0x14000bc80`
- `0x14000bed0`
- `0x14000bf60`
- `0x14000c450`
- `0x14001bb50`
- `0x14002f010`
- `0x14003c668`
- `0x14004b820`
- `0x14004c250`
- `0x14004c7d0`

## callees

- `0x140009610`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000969e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000969e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009679`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009679`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140009691`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140009691`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x1400096da`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x1400096da`
- `vdsutil!VdsTraceEx` at `0x1400096f2`
- `vdsutil!VdsTraceEx` at `0x1400096f2`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140009643`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140009643`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400096aa`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400096aa`

## string_xrefs

- `0x140009632`: `CVdsService::RemoveObjectFromMap()`
- `0x1400096e4`: `CVdsService::RemoveObjectFromMap(),1: The map is corrupt, elements can be found but not removed!!!!`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVdsService::RemoveObjectFromMap(
        struct _RTL_CRITICAL_SECTION *this,
        struct IUnknown *a2,
        enum _VDS_OBJECT_TYPE a3)
{
  _BYTE v5[16]; // [rsp+28h] [rbp-60h] BYREF
  _QWORD v6[4]; // [rsp+38h] [rbp-50h] BYREF
  _OWORD v7[2]; // [rsp+58h] [rbp-30h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v5, 0x5Eu, "CVdsService::RemoveObjectFromMap()");
  v6[0] = 0;
  v6[1] = 0;
  v6[3] = 0;
  memset(v7, 0, sizeof(v7));
  v6[2] = a2;
  EnterCriticalSection(this + 3);
  if ( CRtlMap::Find((CRtlMap *)&this[4].LockCount, (struct CRtlEntry *)v6, (struct CRtlEntry *)v7)
    && !CRtlMap::Remove((CRtlMap *)&this[4].LockCount, (struct CRtlEntry *)v6) )
  {
    VdsTraceEx(
      94,
      0,
      "CVdsService::RemoveObjectFromMap(),1: The map is corrupt, elements can be found but not removed!!!!");
  }
  LeaveCriticalSection(this + 3);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v5);
}

```

## disassembly

```asm
0x140009610  mov     [rsp+arg_8], rbx
0x140009615  push    rdi
0x140009616  sub     rsp, 80h
0x14000961d  mov     rax, cs:__security_cookie
0x140009624  xor     rax, rsp
0x140009627  mov     [rsp+88h+var_10], rax
0x14000962c  mov     rbx, rdx
0x14000962f  mov     rdi, rcx
0x140009632  lea     r8, aCvdsserviceRem_4; "CVdsService::RemoveObjectFromMap()"
0x140009639  mov     edx, 5Eh ; '^'
0x14000963e  lea     rcx, [rsp+88h+var_60]
0x140009643  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140009649  nop
0x14000964a  xor     eax, eax
0x14000964c  mov     [rsp+88h+var_50], rax
0x140009651  mov     [rsp+88h+var_48], rax
0x140009656  mov     [rsp+88h+var_38], rax
0x14000965b  xorps   xmm0, xmm0
0x14000965e  movups  [rsp+88h+var_30], xmm0
0x140009663  movups  [rsp+88h+var_20], xmm0
0x140009668  mov     [rsp+88h+var_40], rbx
0x14000966d  lea     rbx, [rdi+78h]
0x140009671  mov     [rsp+88h+var_68], rbx
0x140009676  mov     rcx, rbx; lpCriticalSection
0x140009679  call    cs:__imp_EnterCriticalSection
0x14000967f  nop
0x140009680  lea     r8, [rsp+88h+var_30]
0x140009685  lea     rdx, [rsp+88h+var_50]
0x14000968a  lea     rcx, [rdi+0A8h]
0x140009691  call    cs:__imp_?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z; CRtlMap::Find(CRtlEntry &,CRtlEntry *)
0x140009697  test    eax, eax
0x140009699  jnz     short loc_1400096CE
0x14000969b  mov     rcx, rbx; lpCriticalSection
0x14000969e  call    cs:__imp_LeaveCriticalSection
0x1400096a4  nop
0x1400096a5  lea     rcx, [rsp+88h+var_60]
0x1400096aa  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400096b0  mov     rcx, [rsp+88h+var_10]
0x1400096b5  xor     rcx, rsp; StackCookie
0x1400096b8  call    __security_check_cookie
0x1400096bd  mov     rbx, [rsp+88h+arg_8]
0x1400096c5  add     rsp, 80h
0x1400096cc  pop     rdi
0x1400096cd  retn
0x1400096ce  lea     rdx, [rsp+88h+var_50]
0x1400096d3  lea     rcx, [rdi+0A8h]
0x1400096da  call    cs:__imp_?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z; CRtlMap::Remove(CRtlEntry &)
0x1400096e0  test    eax, eax
0x1400096e2  jnz     short loc_14000969B
0x1400096e4  lea     r8, aCvdsserviceRem_27; "CVdsService::RemoveObjectFromMap(),1: T"...
0x1400096eb  xor     edx, edx
0x1400096ed  mov     ecx, 5Eh ; '^'
0x1400096f2  call    cs:__imp_VdsTraceEx
0x1400096f8  jmp     short loc_14000969B
```
