# CVdsRawDiskLun::GetUniqueId(ushort * *)

- ea: `0x14004e2c0`
- end: `0x14004e39a`
- name: `?GetUniqueId@CVdsRawDiskLun@@UEAAJPEAPEAG@Z`
- size: `218`
- prototype: `__int64 __fastcall(CVdsRawDiskLun *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14004e2c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004e37b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004e37b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004e2ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004e2ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e367`
- `vdsutil!VdsAllocateString` at `0x14004e33b`
- `vdsutil!VdsAllocateString` at `0x14004e33b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004e2e1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004e2e1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004e387`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004e387`
- `vdsutil!VdsTraceW` at `0x14004e359`
- `vdsutil!VdsTraceW` at `0x14004e359`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsRawDiskLun::GetUniqueId(CVdsRawDiskLun *this, LPVOID *a2)
{
  int String; // ebx
  __int64 v5; // r8
  __int64 v6; // rcx
  _BYTE v8[40]; // [rsp+20h] [rbp-28h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v8, 0x5Eu, "CVdsRawDiskLun::GetUniqueId()");
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( *((_DWORD *)this + 72) == 1 )
  {
    String = -2147212277;
  }
  else
  {
    if ( a2 )
    {
      *a2 = 0;
      v6 = *((_QWORD *)this + 28);
      if ( v6 )
      {
        String = VdsAllocateString(v6, a2);
        if ( String >= 0 )
          goto LABEL_11;
        v5 = 2968;
      }
      else
      {
        String = -2147418113;
        v5 = 2962;
      }
    }
    else
    {
      String = -2147024809;
      v5 = 2954;
    }
    VdsTraceW(0, L"CVdsRawDiskLun::GetUniqueId(), line=%ld error=%lX", v5, (unsigned int)String);
    if ( *a2 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
  }
LABEL_11:
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v8);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x14004e2c0  mov     [rsp+arg_0], rbx
0x14004e2c5  push    rdi
0x14004e2c6  sub     rsp, 40h
0x14004e2ca  mov     rdi, rdx
0x14004e2cd  mov     rbx, rcx
0x14004e2d0  lea     r8, aCvdsrawdisklun_94; "CVdsRawDiskLun::GetUniqueId()"
0x14004e2d7  mov     edx, 5Eh ; '^'
0x14004e2dc  lea     rcx, [rsp+48h+var_28]
0x14004e2e1  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14004e2e7  nop
0x14004e2e8  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004e2ef  call    cs:__imp_EnterCriticalSection
0x14004e2f5  nop
0x14004e2f6  cmp     dword ptr [rbx+120h], 1
0x14004e2fd  jnz     short loc_14004E306
0x14004e2ff  mov     ebx, 8004240Bh
0x14004e304  jmp     short loc_14004E374
0x14004e306  test    rdi, rdi
0x14004e309  jnz     short loc_14004E318
0x14004e30b  mov     ebx, 80070057h
0x14004e310  mov     r8d, 0B8Ah
0x14004e316  jmp     short loc_14004E34D
0x14004e318  mov     qword ptr [rdi], 0
0x14004e31f  mov     rcx, [rbx+0E0h]
0x14004e326  test    rcx, rcx
0x14004e329  jnz     short loc_14004E338
0x14004e32b  mov     ebx, 8000FFFFh
0x14004e330  mov     r8d, 0B92h
0x14004e336  jmp     short loc_14004E34D
0x14004e338  mov     rdx, rdi
0x14004e33b  call    cs:__imp_VdsAllocateString
0x14004e341  mov     ebx, eax
0x14004e343  test    eax, eax
0x14004e345  jns     short loc_14004E374
0x14004e347  mov     r8d, 0B98h
0x14004e34d  mov     r9d, ebx
0x14004e350  lea     rdx, aCvdsrawdisklun_95; "CVdsRawDiskLun::GetUniqueId(), line=%ld"...
0x14004e357  xor     ecx, ecx
0x14004e359  call    cs:__imp_VdsTraceW
0x14004e35f  mov     rcx, [rdi]; pv
0x14004e362  test    rcx, rcx
0x14004e365  jz      short loc_14004E374
0x14004e367  call    cs:__imp_CoTaskMemFree
0x14004e36d  mov     qword ptr [rdi], 0
0x14004e374  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004e37b  call    cs:__imp_LeaveCriticalSection
0x14004e381  nop
0x14004e382  lea     rcx, [rsp+48h+var_28]
0x14004e387  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004e38d  mov     eax, ebx
0x14004e38f  mov     rbx, [rsp+48h+arg_0]
0x14004e394  add     rsp, 40h
0x14004e398  pop     rdi
0x14004e399  retn
```
