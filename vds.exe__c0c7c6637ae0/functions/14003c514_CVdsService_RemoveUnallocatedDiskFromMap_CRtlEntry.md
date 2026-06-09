# CVdsService::RemoveUnallocatedDiskFromMap(CRtlEntry &)

- ea: `0x14003c514`
- end: `0x14003c662`
- name: `?RemoveUnallocatedDiskFromMap@CVdsService@@CAXAEAVCRtlEntry@@@Z`
- size: `334`
- prototype: `void __fastcall(struct CRtlEntry *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x14001b14c`
- `0x140037a0c`
- `0x14003c340`
- `0x14003c424`

## callees

- `0x14003c514`
- `0x14003cde0`
- `0x140052e80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14003c5d9`
- `msvcrt!_wcsicmp` at `0x14003c5d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003c61b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003c61b`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14003c573`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14003c573`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x14003c615`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x14003c639`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x14003c615`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x14003c639`
- `vdsutil!VdsHeapFree` at `0x14003c629`
- `vdsutil!VdsHeapFree` at `0x14003c629`
- `vdsutil!VdsTraceEx` at `0x14003c605`
- `vdsutil!VdsTraceEx` at `0x14003c605`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c546`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c546`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c644`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c644`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003c5e7`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003c5e7`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003c5ab`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003c5ab`

## string_xrefs

- `0x14003c536`: `CVdsService::RemoveUnallocatedDiskFromMap()`
- `0x14003c5f6`: `CVdsService::RemoveUnallocatedDiskFromMap, 1, Key=%S`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsService::RemoveUnallocatedDiskFromMap(struct CRtlEntry *a1)
{
  unsigned __int64 v2; // rdx
  const wchar_t *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  const wchar_t *v6; // rbx
  HANDLE ProcessHeap; // rax
  __int128 v8; // [rsp+20h] [rbp-39h] BYREF
  __int64 v9; // [rsp+30h] [rbp-29h]
  _BYTE v10[16]; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int64 v11; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v12[24]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v13; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v14; // [rsp+78h] [rbp+1Fh]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v10, 0x5Eu, "CVdsService::RemoveUnallocatedDiskFromMap()");
  v8 = 0;
  v9 = 0;
  v13 = 0;
  v14 = 0;
  if ( !CRtlMap::Find((CRtlMap *)CVdsService::m_mapUnallocatedDisks, a1, (struct CRtlEntry *)&v13) )
  {
LABEL_9:
    CRtlMap::Remove((CRtlMap *)CVdsService::m_mapUnallocatedDisks, a1);
    goto LABEL_10;
  }
  v3 = *(const wchar_t **)(v14 + 272);
  if ( (int)StringCchLengthW(v3, v2, &v11) >= 0 )
  {
    v4 = CRtlMap::Begin(CVdsService::m_mapUnallocatedDisksByDeviceId, v12);
    v8 = *(_OWORD *)v4;
    v9 = *(_QWORD *)(v4 + 16);
    while ( (_QWORD)v8 )
    {
      v5 = *((_QWORD *)&v8 + 1);
      if ( !*((_QWORD *)&v8 + 1) )
        break;
      if ( !_wcsicmp(v3, *(const wchar_t **)(*((_QWORD *)&v8 + 1) + 16LL)) )
      {
        v6 = *(const wchar_t **)(v5 + 16);
        VdsTraceEx(94, 3, "CVdsService::RemoveUnallocatedDiskFromMap, 1, Key=%S", v6);
        CRtlMap::Remove((CRtlMap *)CVdsService::m_mapUnallocatedDisksByDeviceId, (struct CRtlEntry *)v5);
        ProcessHeap = GetProcessHeap();
        VdsHeapFree(ProcessHeap, 0, v6);
        goto LABEL_9;
      }
      CRtlMapIter::Next((CRtlMapIter *)&v8);
    }
    goto LABEL_9;
  }
LABEL_10:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v10);
}

```

## disassembly

```asm
0x14003c514  push    rbp
0x14003c516  push    rbx
0x14003c517  push    rsi
0x14003c518  push    rdi
0x14003c519  lea     rbp, [rsp-3Fh]
0x14003c51e  sub     rsp, 98h
0x14003c525  mov     rax, cs:__security_cookie
0x14003c52c  xor     rax, rsp
0x14003c52f  mov     [rbp+57h+var_28], rax
0x14003c533  mov     rsi, rcx
0x14003c536  lea     r8, aCvdsserviceRem_1; "CVdsService::RemoveUnallocatedDiskFromM"...
0x14003c53d  mov     edx, 5Eh ; '^'
0x14003c542  lea     rcx, [rbp+57h+var_78]
0x14003c546  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003c54c  nop
0x14003c54d  xorps   xmm0, xmm0
0x14003c550  xor     eax, eax
0x14003c552  movups  [rbp+57h+var_90], xmm0
0x14003c556  mov     [rbp+57h+var_80], rax
0x14003c55a  xorps   xmm1, xmm1
0x14003c55d  movups  [rbp+57h+var_48], xmm1
0x14003c561  movups  [rbp+57h+var_38], xmm1
0x14003c565  lea     r8, [rbp+57h+var_48]
0x14003c569  mov     rdx, rsi
0x14003c56c  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x14003c573  call    cs:__imp_?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z; CRtlMap::Find(CRtlEntry &,CRtlEntry *)
0x14003c579  test    eax, eax
0x14003c57b  jz      loc_14003C62F
0x14003c581  mov     rax, qword ptr [rbp+57h+var_38]
0x14003c585  mov     rbx, [rax+110h]
0x14003c58c  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x14003c590  mov     rcx, rbx; unsigned __int16 *
0x14003c593  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14003c598  test    eax, eax
0x14003c59a  js      loc_14003C640
0x14003c5a0  lea     rdx, [rbp+57h+var_60]
0x14003c5a4  lea     rcx, ?m_mapUnallocatedDisksByDeviceId@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisksByDeviceId
0x14003c5ab  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x14003c5b1  movups  xmm0, xmmword ptr [rax]
0x14003c5b4  movups  [rbp+57h+var_90], xmm0
0x14003c5b8  movsd   xmm1, qword ptr [rax+10h]
0x14003c5bd  movsd   [rbp+57h+var_80], xmm1
0x14003c5c2  cmp     qword ptr [rbp+57h+var_90], 0
0x14003c5c7  jz      short loc_14003C62F
0x14003c5c9  mov     rdi, qword ptr [rbp+57h+var_90+8]
0x14003c5cd  test    rdi, rdi
0x14003c5d0  jz      short loc_14003C62F
0x14003c5d2  mov     rdx, [rdi+10h]; String2
0x14003c5d6  mov     rcx, rbx; String1
0x14003c5d9  call    cs:__imp__wcsicmp
0x14003c5df  test    eax, eax
0x14003c5e1  jz      short loc_14003C5EF
0x14003c5e3  lea     rcx, [rbp+57h+var_90]
0x14003c5e7  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x14003c5ed  jmp     short loc_14003C5C2
0x14003c5ef  mov     rbx, [rdi+10h]
0x14003c5f3  mov     r9, rbx
0x14003c5f6  lea     r8, aCvdsserviceRem_23; "CVdsService::RemoveUnallocatedDiskFromM"...
0x14003c5fd  mov     edx, 3
0x14003c602  lea     ecx, [rdx+5Bh]
0x14003c605  call    cs:__imp_VdsTraceEx
0x14003c60b  mov     rdx, rdi
0x14003c60e  lea     rcx, ?m_mapUnallocatedDisksByDeviceId@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisksByDeviceId
0x14003c615  call    cs:__imp_?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z; CRtlMap::Remove(CRtlEntry &)
0x14003c61b  call    cs:__imp_GetProcessHeap
0x14003c621  mov     rcx, rax
0x14003c624  mov     r8, rbx
0x14003c627  xor     edx, edx
0x14003c629  call    cs:__imp_VdsHeapFree
0x14003c62f  mov     rdx, rsi
0x14003c632  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x14003c639  call    cs:__imp_?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z; CRtlMap::Remove(CRtlEntry &)
0x14003c63f  nop
0x14003c640  lea     rcx, [rbp+57h+var_78]
0x14003c644  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003c64a  mov     rcx, [rbp+57h+var_28]
0x14003c64e  xor     rcx, rsp; StackCookie
0x14003c651  call    __security_check_cookie
0x14003c656  add     rsp, 98h
0x14003c65d  pop     rdi
0x14003c65e  pop     rsi
0x14003c65f  pop     rbx
0x14003c660  pop     rbp
0x14003c661  retn
```
