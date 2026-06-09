# CVdsService::GetInitiatorName(ushort * *)

- ea: `0x140039840`
- end: `0x140039955`
- name: `?GetInitiatorName@CVdsService@@UEAAJPEAPEAG@Z`
- size: `277`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140039840`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400398b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400398b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039915`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003989e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003989e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039866`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039866`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003993d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003993d`
- `vdsutil!VdsTraceW` at `0x1400398c8`
- `vdsutil!VdsTraceW` at `0x140039907`
- `vdsutil!VdsTraceW` at `0x14003992d`
- `vdsutil!VdsTraceW` at `0x1400398c8`
- `vdsutil!VdsTraceW` at `0x140039907`
- `vdsutil!VdsTraceW` at `0x14003992d`

## string_xrefs

- `0x140039855`: `CVdsService::GetInitiatorName()`
- `0x140039924`: `CVdsService::GetInitiatorName: Could not access necessary function in iSCSI library.`
- `0x1400398bf`: `CVdsService::GetInitiatorName: Out of memory.`
- `0x1400398fb`: `CVdsService::GetInitiatorName: GetIScsiInitiatorNodeName failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::GetInitiatorName(CVdsService *this, unsigned __int16 **a2)
{
  int v4; // ebx
  FARPROC ProcAddress; // rbx
  LPVOID v6; // rax
  void *v7; // rdi
  unsigned int v8; // eax
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v10, 0x5Eu, "CVdsService::GetInitiatorName()");
  v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16);
  if ( v4 >= 0 )
  {
    if ( CVdsService::m_hIscsidscModule
      && (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "GetIScsiInitiatorNodeNameW")) != 0 )
    {
      v6 = CoTaskMemAlloc(0x1C0u);
      v7 = v6;
      if ( v6 )
      {
        v8 = ((__int64 (__fastcall *)(LPVOID))ProcAddress)(v6);
        if ( v8 && ((v8 & 0xFFF0000) == 0 || (v8 & 0xC0000000) == 0xC0000000) )
        {
          VdsTraceW(1, L"CVdsService::GetInitiatorName: GetIScsiInitiatorNodeName failed: %X", v8);
          v4 = -2147211000;
          CoTaskMemFree(v7);
        }
        else
        {
          v4 = 0;
          *a2 = (unsigned __int16 *)v7;
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsService::GetInitiatorName: Out of memory.");
        v4 = -2147024882;
      }
    }
    else
    {
      VdsTraceW(0, L"CVdsService::GetInitiatorName: Could not access necessary function in iSCSI library.");
      v4 = -2147212288;
    }
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140039840  mov     [rsp+arg_0], rbx
0x140039845  mov     [rsp+arg_8], rsi
0x14003984a  push    rdi
0x14003984b  sub     rsp, 30h
0x14003984f  mov     rsi, rdx
0x140039852  mov     rbx, rcx
0x140039855  lea     r8, aCvdsserviceGet_55; "CVdsService::GetInitiatorName()"
0x14003985c  mov     edx, 5Eh ; '^'
0x140039861  lea     rcx, [rsp+38h+var_18]
0x140039866  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003986c  nop
0x14003986d  lea     rcx, [rbx-10h]
0x140039871  mov     rax, [rcx]
0x140039874  mov     rax, [rax+20h]
0x140039878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003987d  mov     ebx, eax
0x14003987f  test    eax, eax
0x140039881  js      loc_140039938
0x140039887  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14003988e  test    rcx, rcx
0x140039891  jz      loc_140039924
0x140039897  lea     rdx, aGetiscsiinitia; "GetIScsiInitiatorNodeNameW"
0x14003989e  call    cs:__imp_GetProcAddress
0x1400398a4  mov     rbx, rax
0x1400398a7  test    rax, rax
0x1400398aa  jz      short loc_140039924
0x1400398ac  mov     ecx, 1C0h; cb
0x1400398b1  call    cs:__imp_CoTaskMemAlloc
0x1400398b7  mov     rdi, rax
0x1400398ba  test    rax, rax
0x1400398bd  jnz     short loc_1400398D5
0x1400398bf  lea     rdx, aCvdsserviceGet_16; "CVdsService::GetInitiatorName: Out of m"...
0x1400398c6  xor     ecx, ecx
0x1400398c8  call    cs:__imp_VdsTraceW
0x1400398ce  mov     ebx, 8007000Eh
0x1400398d3  jmp     short loc_140039938
0x1400398d5  mov     rcx, rdi
0x1400398d8  mov     rax, rbx
0x1400398db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400398e0  test    eax, eax
0x1400398e2  jz      short loc_14003991D
0x1400398e4  test    eax, 0FFF0000h
0x1400398e9  jz      short loc_1400398F8
0x1400398eb  mov     ecx, eax
0x1400398ed  mov     edx, 0C0000000h
0x1400398f2  and     ecx, edx
0x1400398f4  cmp     ecx, edx
0x1400398f6  jnz     short loc_14003991D
0x1400398f8  mov     r8d, eax
0x1400398fb  lea     rdx, aCvdsserviceGet_111; "CVdsService::GetInitiatorName: GetIScsi"...
0x140039902  mov     ecx, 1
0x140039907  call    cs:__imp_VdsTraceW
0x14003990d  mov     ebx, 80042908h
0x140039912  mov     rcx, rdi; pv
0x140039915  call    cs:__imp_CoTaskMemFree
0x14003991b  jmp     short loc_140039938
0x14003991d  xor     ebx, ebx
0x14003991f  mov     [rsi], rdi
0x140039922  jmp     short loc_140039938
0x140039924  lea     rdx, aCvdsserviceGet_126; "CVdsService::GetInitiatorName: Could no"...
0x14003992b  xor     ecx, ecx
0x14003992d  call    cs:__imp_VdsTraceW
0x140039933  mov     ebx, 80042400h
0x140039938  lea     rcx, [rsp+38h+var_18]
0x14003993d  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140039943  mov     eax, ebx
0x140039945  mov     rbx, [rsp+38h+arg_0]
0x14003994a  mov     rsi, [rsp+38h+arg_8]
0x14003994f  add     rsp, 30h
0x140039953  pop     rdi
0x140039954  retn
```
