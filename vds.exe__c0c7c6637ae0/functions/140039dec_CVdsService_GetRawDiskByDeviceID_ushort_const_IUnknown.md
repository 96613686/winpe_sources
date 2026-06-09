# CVdsService::GetRawDiskByDeviceID(ushort const *,IUnknown * *)

- ea: `0x140039dec`
- end: `0x140039f7c`
- name: `?GetRawDiskByDeviceID@CVdsService@@AEAAJPEBGPEAPEAUIUnknown@@@Z`
- size: `400`
- prototype: `int(CVdsService *__hidden this, const unsigned __int16 *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140038f90`

## callees

- `0x140039dec`
- `0x14003cde0`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039f45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039f45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039e5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039e5a`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140039edc`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140039edc`
- `vdsutil!VdsTraceEx` at `0x140039e82`
- `vdsutil!VdsTraceEx` at `0x140039eb9`
- `vdsutil!VdsTraceEx` at `0x140039efe`
- `vdsutil!VdsTraceEx` at `0x140039e82`
- `vdsutil!VdsTraceEx` at `0x140039eb9`
- `vdsutil!VdsTraceEx` at `0x140039efe`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039e4c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039e4c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140039f50`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140039f50`

## string_xrefs

- `0x140039e38`: `CVdsService::GetRawDiskByDeviceID()`
- `0x140039e76`: `CVdsService::GetRawDiskByDeviceID(), 1, hr=%lX`
- `0x140039ead`: `CVdsService::GetRawDiskByDeviceID(), 2`
- `0x140039ef2`: `CVdsService::GetRawDiskByDeviceID(), 3, hr=%lX`
- `0x140039f29`: `CVdsService::GetRawDiskByDeviceID(), 4, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::GetRawDiskByDeviceID(
        CVdsService *this,
        const unsigned __int16 *a2,
        struct IUnknown **a3)
{
  unsigned __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned __int64 v10; // [rsp+20h] [rbp-29h] BYREF
  _BYTE v11[16]; // [rsp+28h] [rbp-21h] BYREF
  __int128 v12; // [rsp+38h] [rbp-11h] BYREF
  __int128 v13; // [rsp+48h] [rbp-1h]
  __int128 v14; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v15; // [rsp+68h] [rbp+1Fh]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v10 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsService::GetRawDiskByDeviceID()");
  EnterCriticalSection(&g_GlobalCriticalSection);
  v6 = StringCchLengthW(a2, v5, &v10);
  v7 = v6;
  if ( v6 >= 0 )
  {
    *((_QWORD *)&v12 + 1) = 2 * v10 + 2;
    *(_QWORD *)&v13 = a2;
    LODWORD(v12) = 7;
    if ( a3 )
    {
      *a3 = 0;
      if ( CRtlMap::Find(
             (CRtlMap *)CVdsService::m_mapUnallocatedDisksByDeviceId,
             (struct CRtlEntry *)&v12,
             (struct CRtlEntry *)&v14) )
      {
        if ( (_QWORD)v15 )
        {
          v8 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))v15)(v15, &IID_IUnknown, a3);
          v7 = v8;
          if ( v8 >= 0 )
            v7 = 0;
          else
            VdsTraceEx(94, 0, "CVdsService::GetRawDiskByDeviceID(), 4, hr=%lX", (unsigned int)v8);
        }
        else
        {
          VdsTraceEx(94, 0, "CVdsService::GetRawDiskByDeviceID(), 3, hr=%lX", v7);
          v7 = -2147212216;
        }
      }
      else
      {
        v7 = -2147212283;
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsService::GetRawDiskByDeviceID(), 2");
      v7 = -2147024809;
    }
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsService::GetRawDiskByDeviceID(), 1, hr=%lX", (unsigned int)v6);
  }
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
  return v7;
}

```

## disassembly

```asm
0x140039dec  mov     [rsp-8+arg_0], rbx
0x140039df1  mov     [rsp-8+arg_18], rsi
0x140039df6  push    rbp
0x140039df7  push    rdi
0x140039df8  push    r14
0x140039dfa  lea     rbp, [rsp-47h]
0x140039dff  sub     rsp, 90h
0x140039e06  mov     rax, cs:__security_cookie
0x140039e0d  xor     rax, rsp
0x140039e10  mov     [rbp+57h+var_20], rax
0x140039e14  mov     rdi, r8
0x140039e17  mov     rsi, rdx
0x140039e1a  xorps   xmm0, xmm0
0x140039e1d  movups  [rbp+57h+var_68], xmm0
0x140039e21  movups  [rbp+57h+var_58], xmm0
0x140039e25  xorps   xmm1, xmm1
0x140039e28  movups  [rbp+57h+var_48], xmm1
0x140039e2c  movups  [rbp+57h+var_38], xmm1
0x140039e30  mov     [rbp+57h+var_80], 0
0x140039e38  lea     r8, aCvdsserviceGet_95; "CVdsService::GetRawDiskByDeviceID()"
0x140039e3f  mov     r14d, 5Eh ; '^'
0x140039e45  mov     edx, r14d
0x140039e48  lea     rcx, [rbp+57h+var_78]
0x140039e4c  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140039e52  nop
0x140039e53  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140039e5a  call    cs:__imp_EnterCriticalSection
0x140039e60  nop
0x140039e61  lea     r8, [rbp+57h+var_80]; unsigned __int64 *
0x140039e65  mov     rcx, rsi; unsigned __int16 *
0x140039e68  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140039e6d  mov     ebx, eax
0x140039e6f  test    eax, eax
0x140039e71  jns     short loc_140039E8D
0x140039e73  mov     r9d, eax
0x140039e76  lea     r8, aCvdsserviceGet_69; "CVdsService::GetRawDiskByDeviceID(), 1,"...
0x140039e7d  xor     edx, edx
0x140039e7f  mov     ecx, r14d
0x140039e82  call    cs:__imp_VdsTraceEx
0x140039e88  jmp     loc_140039F3E
0x140039e8d  mov     rax, [rbp+57h+var_80]
0x140039e91  lea     rax, ds:2[rax*2]
0x140039e99  mov     qword ptr [rbp+57h+var_68+8], rax
0x140039e9d  mov     qword ptr [rbp+57h+var_58], rsi
0x140039ea1  mov     dword ptr [rbp+57h+var_68], 7
0x140039ea8  test    rdi, rdi
0x140039eab  jnz     short loc_140039EC6
0x140039ead  lea     r8, aCvdsserviceGet_105; "CVdsService::GetRawDiskByDeviceID(), 2"
0x140039eb4  xor     edx, edx
0x140039eb6  mov     ecx, r14d
0x140039eb9  call    cs:__imp_VdsTraceEx
0x140039ebf  mov     ebx, 80070057h
0x140039ec4  jmp     short loc_140039F3E
0x140039ec6  mov     qword ptr [rdi], 0
0x140039ecd  lea     r8, [rbp+57h+var_48]
0x140039ed1  lea     rdx, [rbp+57h+var_68]
0x140039ed5  lea     rcx, ?m_mapUnallocatedDisksByDeviceId@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisksByDeviceId
0x140039edc  call    cs:__imp_?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z; CRtlMap::Find(CRtlEntry &,CRtlEntry *)
0x140039ee2  test    eax, eax
0x140039ee4  jz      short loc_140039F39
0x140039ee6  mov     rcx, qword ptr [rbp+57h+var_38]
0x140039eea  test    rcx, rcx
0x140039eed  jnz     short loc_140039F0B
0x140039eef  mov     r9d, ebx
0x140039ef2  lea     r8, aCvdsserviceGet_34; "CVdsService::GetRawDiskByDeviceID(), 3,"...
0x140039ef9  xor     edx, edx
0x140039efb  mov     ecx, r14d
0x140039efe  call    cs:__imp_VdsTraceEx
0x140039f04  mov     ebx, 80042448h
0x140039f09  jmp     short loc_140039F3E
0x140039f0b  mov     rax, [rcx]
0x140039f0e  mov     r8, rdi
0x140039f11  lea     rdx, IID_IUnknown
0x140039f18  mov     rax, [rax]
0x140039f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039f20  mov     ebx, eax
0x140039f22  test    eax, eax
0x140039f24  jns     short loc_140039F35
0x140039f26  mov     r9d, eax
0x140039f29  lea     r8, aCvdsserviceGet_136; "CVdsService::GetRawDiskByDeviceID(), 4,"...
0x140039f30  jmp     loc_140039E7D
0x140039f35  xor     ebx, ebx
0x140039f37  jmp     short loc_140039F3E
0x140039f39  mov     ebx, 80042405h
0x140039f3e  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140039f45  call    cs:__imp_LeaveCriticalSection
0x140039f4b  nop
0x140039f4c  lea     rcx, [rbp+57h+var_78]
0x140039f50  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140039f56  mov     eax, ebx
0x140039f58  mov     rcx, [rbp+57h+var_20]
0x140039f5c  xor     rcx, rsp; StackCookie
0x140039f5f  call    __security_check_cookie
0x140039f64  lea     r11, [rsp+0A0h+var_10]
0x140039f6c  mov     rbx, [r11+20h]
0x140039f70  mov     rsi, [r11+38h]
0x140039f74  mov     rsp, r11
0x140039f77  pop     r14
0x140039f79  pop     rdi
0x140039f7a  pop     rbp
0x140039f7b  retn
```
