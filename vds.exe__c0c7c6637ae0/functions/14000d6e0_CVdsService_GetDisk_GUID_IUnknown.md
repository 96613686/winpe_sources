# CVdsService::GetDisk(_GUID,IUnknown * *)

- ea: `0x14000d6e0`
- end: `0x14000d81e`
- name: `?GetDisk@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct IUnknown **)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140005630`
- `0x14000e920`
- `0x140013f50`
- `0x140038c64`
- `0x1400392a0`
- `0x14003c668`

## callees

- `0x14000d6e0`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d7ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d7ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d73c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d73c`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14000d781`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14000d781`
- `vdsutil!VdsTraceEx` at `0x14000d754`
- `vdsutil!VdsTraceEx` at `0x14000d7a4`
- `vdsutil!VdsTraceEx` at `0x14000d7db`
- `vdsutil!VdsTraceEx` at `0x14000d754`
- `vdsutil!VdsTraceEx` at `0x14000d7a4`
- `vdsutil!VdsTraceEx` at `0x14000d7db`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000d72e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000d72e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000d7f8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000d7f8`

## string_xrefs

- `0x14000d71d`: `CVdsService::GetDisk()`
- `0x14000d748`: `CVdsService::GetDisk(), 1`
- `0x14000d798`: `CVdsService::GetDisk(), 2, hr=%lX`
- `0x14000d7cf`: `CVdsService::GetDisk(), 3, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::GetDisk(struct _GUID *a1, struct IUnknown **a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  _BYTE v6[16]; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v7[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v8; // [rsp+50h] [rbp-38h] BYREF
  __int128 v9; // [rsp+60h] [rbp-28h]

  v7[0] = 0;
  v8 = 0;
  v9 = 0;
  v7[1] = *a1;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v6, 0x5Eu, "CVdsService::GetDisk()");
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( a2 )
  {
    v3 = -2147212283;
    *a2 = 0;
    if ( CRtlMap::Find((CRtlMap *)CVdsService::m_mapUnallocatedDisks, (struct CRtlEntry *)v7, (struct CRtlEntry *)&v8) )
    {
      if ( (_QWORD)v9 )
      {
        v4 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))v9)(v9, &IID_IUnknown, a2);
        v3 = v4;
        if ( v4 >= 0 )
          v3 = 0;
        else
          VdsTraceEx(94, 0, "CVdsService::GetDisk(), 3, hr=%lX", v4);
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsService::GetDisk(), 2, hr=%lX", -2147212283);
        v3 = -2147212216;
      }
    }
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsService::GetDisk(), 1");
    v3 = -2147024809;
  }
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v6);
  return v3;
}

```

## disassembly

```asm
0x14000d6e0  mov     [rsp+arg_0], rbx
0x14000d6e5  push    rdi
0x14000d6e6  sub     rsp, 80h
0x14000d6ed  mov     rax, cs:__security_cookie
0x14000d6f4  xor     rax, rsp
0x14000d6f7  mov     [rsp+88h+var_10], rax
0x14000d6fc  mov     rdi, rdx
0x14000d6ff  xorps   xmm0, xmm0
0x14000d702  movups  [rsp+88h+var_58], xmm0
0x14000d707  xorps   xmm1, xmm1
0x14000d70a  movups  [rsp+88h+var_38], xmm1
0x14000d70f  movups  [rsp+88h+var_28], xmm1
0x14000d714  movaps  xmm0, xmmword ptr [rcx]
0x14000d717  movdqu  [rsp+88h+var_48], xmm0
0x14000d71d  lea     r8, aCvdsserviceGet_131; "CVdsService::GetDisk()"
0x14000d724  mov     edx, 5Eh ; '^'
0x14000d729  lea     rcx, [rsp+88h+var_68]
0x14000d72e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000d734  nop
0x14000d735  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000d73c  call    cs:__imp_EnterCriticalSection
0x14000d742  nop
0x14000d743  test    rdi, rdi
0x14000d746  jnz     short loc_14000D764
0x14000d748  lea     r8, aCvdsserviceGet_43; "CVdsService::GetDisk(), 1"
0x14000d74f  xor     edx, edx
0x14000d751  lea     ecx, [rdi+5Eh]
0x14000d754  call    cs:__imp_VdsTraceEx
0x14000d75a  mov     ebx, 80070057h
0x14000d75f  jmp     loc_14000D7E5
0x14000d764  mov     ebx, 80042405h
0x14000d769  mov     qword ptr [rdi], 0
0x14000d770  lea     r8, [rsp+88h+var_38]
0x14000d775  lea     rdx, [rsp+88h+var_58]
0x14000d77a  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x14000d781  call    cs:__imp_?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z; CRtlMap::Find(CRtlEntry &,CRtlEntry *)
0x14000d787  test    eax, eax
0x14000d789  jz      short loc_14000D7E5
0x14000d78b  mov     rcx, qword ptr [rsp+88h+var_28]
0x14000d790  test    rcx, rcx
0x14000d793  jnz     short loc_14000D7B1
0x14000d795  mov     r9d, ebx
0x14000d798  lea     r8, aCvdsserviceGet_12; "CVdsService::GetDisk(), 2, hr=%lX"
0x14000d79f  xor     edx, edx
0x14000d7a1  lea     ecx, [rdx+5Eh]
0x14000d7a4  call    cs:__imp_VdsTraceEx
0x14000d7aa  mov     ebx, 80042448h
0x14000d7af  jmp     short loc_14000D7E5
0x14000d7b1  mov     rax, [rcx]
0x14000d7b4  mov     r8, rdi
0x14000d7b7  lea     rdx, IID_IUnknown
0x14000d7be  mov     rax, [rax]
0x14000d7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7c6  mov     ebx, eax
0x14000d7c8  test    eax, eax
0x14000d7ca  jns     short loc_14000D7E3
0x14000d7cc  mov     r9d, eax
0x14000d7cf  lea     r8, aCvdsserviceGet_74; "CVdsService::GetDisk(), 3, hr=%lX"
0x14000d7d6  xor     edx, edx
0x14000d7d8  lea     ecx, [rdx+5Eh]
0x14000d7db  call    cs:__imp_VdsTraceEx
0x14000d7e1  jmp     short loc_14000D7E5
0x14000d7e3  xor     ebx, ebx
0x14000d7e5  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000d7ec  call    cs:__imp_LeaveCriticalSection
0x14000d7f2  nop
0x14000d7f3  lea     rcx, [rsp+88h+var_68]
0x14000d7f8  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000d7fe  mov     eax, ebx
0x14000d800  mov     rcx, [rsp+88h+var_10]
0x14000d805  xor     rcx, rsp; StackCookie
0x14000d808  call    __security_check_cookie
0x14000d80d  mov     rbx, [rsp+88h+arg_0]
0x14000d815  add     rsp, 80h
0x14000d81c  pop     rdi
0x14000d81d  retn
```
