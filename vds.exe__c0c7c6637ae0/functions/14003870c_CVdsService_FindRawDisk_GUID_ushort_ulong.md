# CVdsService::FindRawDisk(_GUID,ushort * &,ulong &)

- ea: `0x14003870c`
- end: `0x14003884f`
- name: `?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@U_GUID@@AEAPEAGAEAK@Z`
- size: `323`
- prototype: `struct CVdsRawDiskLun *__fastcall(struct _GUID *__struct_ptr, unsigned __int16 **, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000fa00`
- `0x140013f50`
- `0x14001b6f0`
- `0x140026c0c`

## callees

- `0x14003870c`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003881a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003881a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140038770`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140038770`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14003879c`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14003879c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140038744`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140038744`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140038826`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140038826`
- `vdsutil!VdsTraceW` at `0x140038785`
- `vdsutil!VdsTraceW` at `0x1400387ad`
- `vdsutil!VdsTraceW` at `0x1400387c0`
- `vdsutil!VdsTraceW` at `0x1400387d9`
- `vdsutil!VdsTraceW` at `0x1400387f0`
- `vdsutil!VdsTraceW` at `0x140038809`
- `vdsutil!VdsTraceW` at `0x140038785`
- `vdsutil!VdsTraceW` at `0x1400387ad`
- `vdsutil!VdsTraceW` at `0x1400387c0`
- `vdsutil!VdsTraceW` at `0x1400387d9`
- `vdsutil!VdsTraceW` at `0x1400387f0`
- `vdsutil!VdsTraceW` at `0x140038809`

## string_xrefs

- `0x140038733`: `CVdsService::FindRawDisk()`
- `0x140038777`: `CVdsService::FindRawDisk, 0`
- `0x1400387a4`: `CVdsService::FindRawDisk, 1`
- `0x1400387b7`: `CVdsService::FindRawDisk, 2`
- `0x1400387d0`: `CVdsService::FindRawDisk, 3`
- `0x1400387e7`: `CVdsService::FindRawDisk, 4`
- `0x140038800`: `CVdsService::FindRawDisk, 5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct CVdsRawDiskLun *__fastcall CVdsService::FindRawDisk(struct _GUID *a1, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 v6; // rbx
  _BYTE v8[16]; // [rsp+20h] [rbp-78h] BYREF
  _OWORD v9[2]; // [rsp+30h] [rbp-68h] BYREF
  __int128 v10; // [rsp+50h] [rbp-48h] BYREF
  __int128 v11; // [rsp+60h] [rbp-38h]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v8, 0x5Eu, "CVdsService::FindRawDisk()");
  v9[0] = 0;
  v10 = 0;
  v11 = 0;
  v9[1] = *a1;
  EnterCriticalSection(&g_GlobalCriticalSection);
  VdsTraceW(3, L"CVdsService::FindRawDisk, 0");
  LODWORD(a1) = CRtlMap::Find(
                  (CRtlMap *)CVdsService::m_mapUnallocatedDisks,
                  (struct CRtlEntry *)v9,
                  (struct CRtlEntry *)&v10);
  VdsTraceW(3, L"CVdsService::FindRawDisk, 1");
  if ( (_DWORD)a1 && (VdsTraceW(3, L"CVdsService::FindRawDisk, 2"), (v6 = v11) != 0) )
  {
    VdsTraceW(3, L"CVdsService::FindRawDisk, 3");
    *a3 = *(_DWORD *)(v6 + 168);
    VdsTraceW(3, L"CVdsService::FindRawDisk, 4");
    *a2 = *(unsigned __int16 **)(v6 + 240);
    VdsTraceW(3, L"CVdsService::FindRawDisk, 5");
  }
  else
  {
    v6 = 0;
  }
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v8);
  return (struct CVdsRawDiskLun *)v6;
}

```

## disassembly

```asm
0x14003870c  mov     [rsp+arg_0], rbx
0x140038711  push    rbp
0x140038712  push    rsi
0x140038713  push    rdi
0x140038714  sub     rsp, 80h
0x14003871b  mov     rax, cs:__security_cookie
0x140038722  xor     rax, rsp
0x140038725  mov     [rsp+98h+var_20], rax
0x14003872a  mov     rsi, r8
0x14003872d  mov     rdi, rdx
0x140038730  mov     rbx, rcx
0x140038733  lea     r8, aCvdsserviceFin_12; "CVdsService::FindRawDisk()"
0x14003873a  mov     edx, 5Eh ; '^'
0x14003873f  lea     rcx, [rsp+98h+var_78]
0x140038744  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003874a  nop
0x14003874b  xorps   xmm0, xmm0
0x14003874e  movups  [rsp+98h+var_68], xmm0
0x140038753  xorps   xmm1, xmm1
0x140038756  movups  [rsp+98h+var_48], xmm1
0x14003875b  movups  [rsp+98h+var_38], xmm1
0x140038760  movaps  xmm0, xmmword ptr [rbx]
0x140038763  movdqu  [rsp+98h+var_58], xmm0
0x140038769  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140038770  call    cs:__imp_EnterCriticalSection
0x140038776  nop
0x140038777  lea     rdx, aCvdsserviceFin_16; "CVdsService::FindRawDisk, 0"
0x14003877e  mov     ebp, 3
0x140038783  mov     ecx, ebp
0x140038785  call    cs:__imp_VdsTraceW
0x14003878b  lea     r8, [rsp+98h+var_48]
0x140038790  lea     rdx, [rsp+98h+var_68]
0x140038795  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x14003879c  call    cs:__imp_?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z; CRtlMap::Find(CRtlEntry &,CRtlEntry *)
0x1400387a2  mov     ebx, eax
0x1400387a4  lea     rdx, aCvdsserviceFin_4; "CVdsService::FindRawDisk, 1"
0x1400387ab  mov     ecx, ebp
0x1400387ad  call    cs:__imp_VdsTraceW
0x1400387b3  test    ebx, ebx
0x1400387b5  jz      short loc_140038811
0x1400387b7  lea     rdx, aCvdsserviceFin_11; "CVdsService::FindRawDisk, 2"
0x1400387be  mov     ecx, ebp
0x1400387c0  call    cs:__imp_VdsTraceW
0x1400387c6  mov     rbx, qword ptr [rsp+98h+var_38]
0x1400387cb  test    rbx, rbx
0x1400387ce  jz      short loc_140038811
0x1400387d0  lea     rdx, aCvdsserviceFin_9; "CVdsService::FindRawDisk, 3"
0x1400387d7  mov     ecx, ebp
0x1400387d9  call    cs:__imp_VdsTraceW
0x1400387df  mov     eax, [rbx+0A8h]
0x1400387e5  mov     [rsi], eax
0x1400387e7  lea     rdx, aCvdsserviceFin_0; "CVdsService::FindRawDisk, 4"
0x1400387ee  mov     ecx, ebp
0x1400387f0  call    cs:__imp_VdsTraceW
0x1400387f6  mov     rax, [rbx+0F0h]
0x1400387fd  mov     [rdi], rax
0x140038800  lea     rdx, aCvdsserviceFin_5; "CVdsService::FindRawDisk, 5"
0x140038807  mov     ecx, ebp
0x140038809  call    cs:__imp_VdsTraceW
0x14003880f  jmp     short loc_140038813
0x140038811  xor     ebx, ebx
0x140038813  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003881a  call    cs:__imp_LeaveCriticalSection
0x140038820  nop
0x140038821  lea     rcx, [rsp+98h+var_78]
0x140038826  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003882c  mov     rax, rbx
0x14003882f  mov     rcx, [rsp+98h+var_20]
0x140038834  xor     rcx, rsp; StackCookie
0x140038837  call    __security_check_cookie
0x14003883c  mov     rbx, [rsp+98h+arg_0]
0x140038844  add     rsp, 80h
0x14003884b  pop     rdi
0x14003884c  pop     rsi
0x14003884d  pop     rbp
0x14003884e  retn
```
