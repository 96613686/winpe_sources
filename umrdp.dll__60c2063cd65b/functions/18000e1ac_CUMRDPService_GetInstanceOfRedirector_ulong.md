# CUMRDPService::GetInstanceOfRedirector(ulong)

- ea: `0x18000e1ac`
- end: `0x18000e2d8`
- name: `?GetInstanceOfRedirector@CUMRDPService@@AEAAPEAVCUmRdpDr@@K@Z`
- size: `300`
- prototype: `struct CUmRdpDr *(CUMRDPService *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a5cc`
- `0x18000e5c0`

## callees

- `0x180008f20`
- `0x18000bd04`
- `0x18000dd80`
- `0x18000e1ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e27c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e27c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e2aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e2aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e1f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e1f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e1e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e1e7`
- `ntdll!RtlInsertElementGenericTable` at `0x18000e294`
- `ntdll!RtlInsertElementGenericTable` at `0x18000e294`
- `WINSTA!WinStationQueryInformationW` at `0x18000e21e`
- `WINSTA!WinStationQueryInformationW` at `0x18000e21e`

## pseudocode

```c
struct CUmRdpDr *__fastcall CUMRDPService::GetInstanceOfRedirector(CUMRDPService *this, unsigned int a2)
{
  CUmRdpDr *v4; // rbx
  HANDLE v5; // rdi
  CUmRdpDr *v6; // rax
  CUmRdpDr *v7; // rax
  bool v8; // zf
  CUmRdpDr *Buffer; // [rsp+30h] [rbp-30h] BYREF
  int v11; // [rsp+38h] [rbp-28h]
  _QWORD v12[2]; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-10h]
  unsigned __int8 NewElement; // [rsp+90h] [rbp+30h] BYREF
  int v15; // [rsp+98h] [rbp+38h] BYREF

  v4 = 0;
  if ( (unsigned int)TSNUTL_IsProtocolRDP(a2) )
  {
    hObject = 0;
    v15 = 0;
    v12[0] = (int)GetCurrentProcessId();
    v12[1] = (int)GetCurrentThreadId();
    if ( (unsigned __int8)WinStationQueryInformationW(0, a2, 14, v12, 24, &v15) )
    {
      v5 = hObject;
      v6 = (CUmRdpDr *)operator new(0x958u);
      if ( v6 && (v7 = CUmRdpDr::CUmRdpDr(v6, a2, v5), (v4 = v7) != 0) )
      {
        v8 = *((_DWORD *)this + 54) == 0;
        Buffer = v7;
        v11 = *(_DWORD *)v7;
        NewElement = 0;
        if ( !v8 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
          if ( RtlInsertElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 104), &Buffer, 0x10u, &NewElement) )
            _InterlockedIncrement((volatile signed __int32 *)Buffer + 4);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
        }
      }
      else if ( v5 )
      {
        CloseHandle(v5);
      }
    }
    else
    {
      GetLastError();
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000e1ac  mov     [rsp-18h+arg_0], rbx
0x18000e1b1  mov     [rsp-18h+arg_8], rsi
0x18000e1b6  push    rbp
0x18000e1b7  push    rdi
0x18000e1b8  push    r14
0x18000e1ba  mov     rbp, rsp
0x18000e1bd  sub     rsp, 60h
0x18000e1c1  mov     r14, rcx
0x18000e1c4  mov     esi, edx
0x18000e1c6  mov     ecx, edx; unsigned int
0x18000e1c8  xor     ebx, ebx
0x18000e1ca  call    ?TSNUTL_IsProtocolRDP@@YAHK@Z; TSNUTL_IsProtocolRDP(ulong)
0x18000e1cf  test    eax, eax
0x18000e1d1  jz      loc_18000E2C0
0x18000e1d7  xor     eax, eax
0x18000e1d9  xorps   xmm0, xmm0
0x18000e1dc  movups  [rbp+var_20], xmm0
0x18000e1e0  mov     [rbp+hObject], rax
0x18000e1e4  mov     [rbp+arg_18], eax
0x18000e1e7  call    cs:__imp_GetCurrentProcessId
0x18000e1ed  movsxd  rcx, eax
0x18000e1f0  mov     qword ptr [rbp+var_20], rcx
0x18000e1f4  call    cs:__imp_GetCurrentThreadId
0x18000e1fa  movsxd  rcx, eax
0x18000e1fd  lea     r9, [rbp+var_20]
0x18000e201  mov     qword ptr [rbp+var_20+8], rcx
0x18000e205  mov     edx, esi
0x18000e207  lea     rax, [rbp+arg_18]
0x18000e20b  xor     ecx, ecx
0x18000e20d  mov     [rsp+60h+var_38], rax
0x18000e212  lea     r8d, [rbx+0Eh]
0x18000e216  mov     [rsp+60h+var_40], 18h
0x18000e21e  call    cs:__imp_WinStationQueryInformationW
0x18000e224  test    al, al
0x18000e226  jnz     short loc_18000E233
0x18000e228  call    cs:__imp_GetLastError
0x18000e22e  jmp     loc_18000E2C0
0x18000e233  mov     rdi, [rbp+hObject]
0x18000e237  mov     ecx, 958h; Size
0x18000e23c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e241  test    rax, rax
0x18000e244  jz      short loc_18000E2B2
0x18000e246  mov     r8, rdi; void *
0x18000e249  mov     edx, esi; unsigned int
0x18000e24b  mov     rcx, rax; this
0x18000e24e  call    ??0CUmRdpDr@@QEAA@KPEAX@Z; CUmRdpDr::CUmRdpDr(ulong,void *)
0x18000e253  mov     rbx, rax
0x18000e256  test    rax, rax
0x18000e259  jz      short loc_18000E2B2
0x18000e25b  cmp     dword ptr [r14+0D8h], 0
0x18000e263  mov     [rbp+Buffer], rax
0x18000e267  mov     eax, [rax]
0x18000e269  mov     [rbp+var_28], eax
0x18000e26c  mov     [rbp+NewElement], 0
0x18000e270  jz      short loc_18000E2C0
0x18000e272  lea     rdi, [r14+0B0h]
0x18000e279  mov     rcx, rdi; lpCriticalSection
0x18000e27c  call    cs:__imp_EnterCriticalSection
0x18000e282  lea     r9, [rbp+NewElement]; NewElement
0x18000e286  mov     r8d, 10h; BufferSize
0x18000e28c  lea     rdx, [rbp+Buffer]; Buffer
0x18000e290  lea     rcx, [r14+68h]; Table
0x18000e294  call    cs:__imp_RtlInsertElementGenericTable
0x18000e29a  mov     rcx, rdi; lpCriticalSection
0x18000e29d  test    rax, rax
0x18000e2a0  jz      short loc_18000E2AA
0x18000e2a2  mov     rax, [rbp+Buffer]
0x18000e2a6  lock inc dword ptr [rax+10h]
0x18000e2aa  call    cs:__imp_LeaveCriticalSection
0x18000e2b0  jmp     short loc_18000E2C0
0x18000e2b2  test    rdi, rdi
0x18000e2b5  jz      short loc_18000E2C0
0x18000e2b7  mov     rcx, rdi; hObject
0x18000e2ba  call    cs:__imp_CloseHandle
0x18000e2c0  lea     r11, [rsp+60h+var_s0]
0x18000e2c5  mov     rax, rbx
0x18000e2c8  mov     rbx, [r11+20h]
0x18000e2cc  mov     rsi, [r11+28h]
0x18000e2d0  mov     rsp, r11
0x18000e2d3  pop     r14
0x18000e2d5  pop     rdi
0x18000e2d6  pop     rbp
0x18000e2d7  retn
```
