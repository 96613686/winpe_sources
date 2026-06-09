# CVdsService::FindRawDisk(ushort *)

- ea: `0x140038618`
- end: `0x140038706`
- name: `?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@PEAG@Z`
- size: `238`
- prototype: `struct CVdsRawDiskLun *__fastcall(wchar_t *String1)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400074c0`
- `0x1400113f0`
- `0x14001b958`
- `0x140024360`
- `0x140025a6c`
- `0x140037a0c`

## callees

- `0x140038618`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400386c5`
- `msvcrt!_wcsicmp` at `0x1400386c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400386d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400386e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400386d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400386e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003865d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003865d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140038636`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140038636`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400386f2`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400386f2`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x1400386a5`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x1400386a5`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x140038670`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x140038670`
- `vdsutil!VdsTraceW` at `0x14003864b`
- `vdsutil!VdsTraceW` at `0x14003869a`
- `vdsutil!VdsTraceW` at `0x14003864b`
- `vdsutil!VdsTraceW` at `0x14003869a`

## string_xrefs

- `0x140038625`: `CVdsService::FindRawDisk()`
- `0x140038642`: `CVdsService::FindRawDisk, 1`
- `0x140038691`: `CVdsService::FindRawDisk, 2`
- `0x1400386b9`: `CVdsService::FindRawDisk, 3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct CVdsRawDiskLun *__fastcall CVdsService::FindRawDisk(wchar_t *String1)
{
  __int64 v2; // rbx
  const wchar_t *v3; // rdx
  _BYTE v5[16]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+38h] [rbp-20h]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v5, 0x5Eu, "CVdsService::FindRawDisk()");
  if ( String1 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    CRtlMap::Begin(CVdsService::m_mapUnallocatedDisks, &v6);
    while ( v6 && v7 )
    {
      v2 = *(_QWORD *)(v7 + 48);
      if ( v2 )
      {
        v3 = *(const wchar_t **)(v2 + 240);
        if ( v3 )
        {
          if ( !_wcsicmp(String1, v3) )
          {
            LeaveCriticalSection(&g_GlobalCriticalSection);
            goto LABEL_15;
          }
        }
        else
        {
          VdsTraceW(0, L"CVdsService::FindRawDisk, 3");
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsService::FindRawDisk, 2");
      }
      CRtlMapIter::Next((CRtlMapIter *)&v6);
    }
    LeaveCriticalSection(&g_GlobalCriticalSection);
  }
  else
  {
    VdsTraceW(0, L"CVdsService::FindRawDisk, 1");
  }
  v2 = 0;
LABEL_15:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v5);
  return (struct CVdsRawDiskLun *)v2;
}

```

## disassembly

```asm
0x140038618  mov     [rsp+arg_0], rbx
0x14003861d  push    rdi
0x14003861e  sub     rsp, 50h
0x140038622  mov     rdi, rcx
0x140038625  lea     r8, aCvdsserviceFin_12; "CVdsService::FindRawDisk()"
0x14003862c  mov     edx, 5Eh ; '^'
0x140038631  lea     rcx, [rsp+58h+var_38]
0x140038636  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003863c  nop
0x14003863d  test    rdi, rdi
0x140038640  jnz     short loc_140038656
0x140038642  lea     rdx, aCvdsserviceFin_4; "CVdsService::FindRawDisk, 1"
0x140038649  xor     ecx, ecx
0x14003864b  call    cs:__imp_VdsTraceW
0x140038651  jmp     loc_1400386EB
0x140038656  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003865d  call    cs:__imp_EnterCriticalSection
0x140038663  nop
0x140038664  lea     rdx, [rsp+58h+var_28]
0x140038669  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x140038670  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x140038676  cmp     [rsp+58h+var_28], 0
0x14003867c  jz      short loc_1400386DE
0x14003867e  mov     rbx, [rsp+58h+var_20]
0x140038683  test    rbx, rbx
0x140038686  jz      short loc_1400386DE
0x140038688  mov     rbx, [rbx+30h]
0x14003868c  test    rbx, rbx
0x14003868f  jnz     short loc_1400386AD
0x140038691  lea     rdx, aCvdsserviceFin_11; "CVdsService::FindRawDisk, 2"
0x140038698  xor     ecx, ecx
0x14003869a  call    cs:__imp_VdsTraceW
0x1400386a0  lea     rcx, [rsp+58h+var_28]
0x1400386a5  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x1400386ab  jmp     short loc_140038676
0x1400386ad  mov     rdx, [rbx+0F0h]; String2
0x1400386b4  test    rdx, rdx
0x1400386b7  jnz     short loc_1400386C2
0x1400386b9  lea     rdx, aCvdsserviceFin_9; "CVdsService::FindRawDisk, 3"
0x1400386c0  jmp     short loc_140038698
0x1400386c2  mov     rcx, rdi; String1
0x1400386c5  call    cs:__imp__wcsicmp
0x1400386cb  test    eax, eax
0x1400386cd  jnz     short loc_1400386A0
0x1400386cf  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400386d6  call    cs:__imp_LeaveCriticalSection
0x1400386dc  jmp     short loc_1400386ED
0x1400386de  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400386e5  call    cs:__imp_LeaveCriticalSection
0x1400386eb  xor     ebx, ebx
0x1400386ed  lea     rcx, [rsp+58h+var_38]
0x1400386f2  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400386f8  mov     rax, rbx
0x1400386fb  mov     rbx, [rsp+58h+arg_0]
0x140038700  add     rsp, 50h
0x140038704  pop     rdi
0x140038705  retn
```
