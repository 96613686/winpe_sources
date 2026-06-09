# CVdsDiskLun::InternalRelease(void)

- ea: `0x140008b10`
- end: `0x140008cdd`
- name: `?InternalRelease@CVdsDiskLun@@UEAAKXZ`
- size: `461`
- prototype: `unsigned int __fastcall(CVdsDiskLun *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140008b10`
- `0x140009610`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008c04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008c04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008c37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008b4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008b69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008bdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008b4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008b69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008bdb`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140008bf3`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140008bf3`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x140008ca4`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x140008ca4`
- `vdsutil!VdsTraceEx` at `0x140008cc0`
- `vdsutil!VdsTraceEx` at `0x140008cc0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140008ba5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140008ba5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140008c10`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140008c10`

## string_xrefs

- `0x140008b94`: `CVdsService::RemoveObjectFromMap()`
- `0x140008cb2`: `CVdsService::RemoveObjectFromMap(),1: The map is corrupt, elements can be found but not removed!!!!`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVdsDiskLun::InternalRelease(CVdsDiskLun *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  enum _VDS_OBJECT_TYPE v3; // r8d
  __int64 v4; // r14
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  struct IUnknown *v6; // rdx
  signed __int32 i; // ecx
  _BYTE v9[16]; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v10[4]; // [rsp+40h] [rbp-68h] BYREF
  _OWORD v11[2]; // [rsp+60h] [rbp-48h] BYREF

  if ( *((_QWORD *)this + 27) )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v2 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 27) + 120LL);
    EnterCriticalSection(v2);
    if ( *((_DWORD *)this + 38) == 1 )
    {
      v4 = *((_QWORD *)this + 26);
      if ( v4 )
      {
        v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 27);
        CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v9, 0x5Eu, "CVdsService::RemoveObjectFromMap()");
        v10[0] = 0;
        v10[1] = 0;
        v10[3] = 0;
        memset(v11, 0, sizeof(v11));
        v10[2] = v4;
        EnterCriticalSection(v5 + 3);
        if ( CRtlMap::Find((CRtlMap *)&v5[4].LockCount, (struct CRtlEntry *)v10, (struct CRtlEntry *)v11)
          && !CRtlMap::Remove((CRtlMap *)&v5[4].LockCount, (struct CRtlEntry *)v10) )
        {
          VdsTraceEx(
            94,
            0,
            "CVdsService::RemoveObjectFromMap(),1: The map is corrupt, elements can be found but not removed!!!!");
        }
        LeaveCriticalSection(v5 + 3);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v9);
      }
      v6 = (struct IUnknown *)*((_QWORD *)this + 37);
      if ( v6 )
        CVdsService::RemoveObjectFromMap(*((struct _RTL_CRITICAL_SECTION **)this + 27), v6, v3);
    }
    LeaveCriticalSection(v2);
    LeaveCriticalSection(&g_GlobalCriticalSection);
  }
  for ( i = *((_DWORD *)this + 38); i != 0x7FFFFFFF; i = *((_DWORD *)this + 38) )
  {
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)this + 38, i - 1, i) )
      break;
  }
  return (unsigned int)(i - 1);
}

```

## disassembly

```asm
0x140008b10  mov     [rsp+arg_8], rbx
0x140008b15  mov     [rsp+arg_10], rbp
0x140008b1a  push    rsi
0x140008b1b  push    rdi
0x140008b1c  push    r14
0x140008b1e  sub     rsp, 90h
0x140008b25  mov     rax, cs:__security_cookie
0x140008b2c  xor     rax, rsp
0x140008b2f  mov     [rsp+0A8h+var_20], rax
0x140008b37  mov     rsi, rcx
0x140008b3a  cmp     qword ptr [rcx+0D8h], 0
0x140008b42  jz      loc_140008C3D
0x140008b48  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140008b4f  call    cs:__imp_EnterCriticalSection
0x140008b55  nop
0x140008b56  mov     rbp, [rsi+0D8h]
0x140008b5d  add     rbp, 78h ; 'x'
0x140008b61  mov     [rsp+0A8h+var_88], rbp
0x140008b66  mov     rcx, rbp; lpCriticalSection
0x140008b69  call    cs:__imp_EnterCriticalSection
0x140008b6f  nop
0x140008b70  cmp     dword ptr [rsi+98h], 1
0x140008b77  jnz     loc_140008C26
0x140008b7d  mov     r14, [rsi+0D0h]
0x140008b84  test    r14, r14
0x140008b87  jz      loc_140008C16
0x140008b8d  mov     rbx, [rsi+0D8h]
0x140008b94  lea     r8, aCvdsserviceRem_4; "CVdsService::RemoveObjectFromMap()"
0x140008b9b  mov     edx, 5Eh ; '^'
0x140008ba0  lea     rcx, [rsp+0A8h+var_78]
0x140008ba5  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140008bab  nop
0x140008bac  xor     eax, eax
0x140008bae  mov     [rsp+0A8h+var_68], rax
0x140008bb3  mov     [rsp+0A8h+var_60], rax
0x140008bb8  mov     [rsp+0A8h+var_50], rax
0x140008bbd  xorps   xmm0, xmm0
0x140008bc0  movups  [rsp+0A8h+var_48], xmm0
0x140008bc5  movups  [rsp+0A8h+var_38], xmm0
0x140008bca  mov     [rsp+0A8h+var_58], r14
0x140008bcf  lea     r14, [rbx+78h]
0x140008bd3  mov     [rsp+0A8h+var_80], r14
0x140008bd8  mov     rcx, r14; lpCriticalSection
0x140008bdb  call    cs:__imp_EnterCriticalSection
0x140008be1  nop
0x140008be2  lea     r8, [rsp+0A8h+var_48]
0x140008be7  lea     rdx, [rsp+0A8h+var_68]
0x140008bec  lea     rcx, [rbx+0A8h]
0x140008bf3  call    cs:__imp_?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z; CRtlMap::Find(CRtlEntry &,CRtlEntry *)
0x140008bf9  test    eax, eax
0x140008bfb  jnz     loc_140008C98
0x140008c01  mov     rcx, r14; lpCriticalSection
0x140008c04  call    cs:__imp_LeaveCriticalSection
0x140008c0a  nop
0x140008c0b  lea     rcx, [rsp+0A8h+var_78]
0x140008c10  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140008c16  mov     rdx, [rsi+128h]; struct IUnknown *
0x140008c1d  test    rdx, rdx
0x140008c20  jnz     loc_140008CCB
0x140008c26  mov     rcx, rbp; lpCriticalSection
0x140008c29  call    cs:__imp_LeaveCriticalSection
0x140008c2f  nop
0x140008c30  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140008c37  call    cs:__imp_LeaveCriticalSection
0x140008c3d  mov     ecx, [rsi+98h]
0x140008c43  cmp     ecx, 7FFFFFFFh
0x140008c49  jz      short loc_140008C6D
0x140008c4b  nop     dword ptr [rax+rax+00h]
0x140008c50  lea     edx, [rcx-1]
0x140008c53  mov     eax, ecx
0x140008c55  lock cmpxchg [rsi+98h], edx
0x140008c5d  jz      short loc_140008C6D
0x140008c5f  mov     ecx, [rsi+98h]
0x140008c65  cmp     ecx, 7FFFFFFFh
0x140008c6b  jnz     short loc_140008C50
0x140008c6d  lea     eax, [rcx-1]
0x140008c70  mov     rcx, [rsp+0A8h+var_20]
0x140008c78  xor     rcx, rsp; StackCookie
0x140008c7b  call    __security_check_cookie
0x140008c80  lea     r11, [rsp+0A8h+var_18]
0x140008c88  mov     rbx, [r11+28h]
0x140008c8c  mov     rbp, [r11+30h]
0x140008c90  mov     rsp, r11
0x140008c93  pop     r14
0x140008c95  pop     rdi
0x140008c96  pop     rsi
0x140008c97  retn
0x140008c98  lea     rdx, [rsp+0A8h+var_68]
0x140008c9d  lea     rcx, [rbx+0A8h]
0x140008ca4  call    cs:__imp_?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z; CRtlMap::Remove(CRtlEntry &)
0x140008caa  test    eax, eax
0x140008cac  jnz     loc_140008C01
0x140008cb2  lea     r8, aCvdsserviceRem_27; "CVdsService::RemoveObjectFromMap(),1: T"...
0x140008cb9  xor     edx, edx
0x140008cbb  mov     ecx, 5Eh ; '^'
0x140008cc0  call    cs:__imp_VdsTraceEx
0x140008cc6  jmp     loc_140008C01
0x140008ccb  mov     rcx, [rsi+0D8h]; this
0x140008cd2  call    ?RemoveObjectFromMap@CVdsService@@QEAAXPEAUIUnknown@@W4_VDS_OBJECT_TYPE@@@Z; CVdsService::RemoveObjectFromMap(IUnknown *,_VDS_OBJECT_TYPE)
0x140008cd7  jmp     loc_140008C26
```
