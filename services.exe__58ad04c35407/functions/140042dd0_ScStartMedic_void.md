# ScStartMedic(void)

- ea: `0x140042dd0`
- end: `0x140042f7e`
- name: `?ScStartMedic@@YAKXZ`
- size: `430`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140039bd4`

## callees

- `0x14003a708`
- `0x14003aab0`
- `0x140042dd0`
- `0x140042f84`
- `0x1400575b0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140042ec2`
- `RPCRT4!UuidCreate` at `0x140042ec2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140042e3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140042e97`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140042e3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140042e97`
- `ntdll!RtlNtStatusToDosError` at `0x140042eee`
- `ntdll!RtlNtStatusToDosError` at `0x140042eee`
- `ntdll!RtlFreeHeap` at `0x140042f4f`
- `ntdll!RtlFreeHeap` at `0x140042f4f`
- `ntdll!TpReleaseTimer` at `0x140042f1e`
- `ntdll!TpReleaseTimer` at `0x140042f1e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140042e0d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140042e0d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140042df5`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140042df5`
- `ntdll!RtlAllocateHeap` at `0x140042e6c`
- `ntdll!RtlAllocateHeap` at `0x140042e6c`

## string_xrefs

- `0x140042e37`: `%SystemRoot%\System32\Upfc.exe`
- `0x140042e8d`: `%SystemRoot%\System32\Upfc.exe`

## pseudocode

```c
__int64 ScStartMedic(void)
{
  DWORD v0; // eax
  DWORD v1; // ebx
  ULONG v2; // ebx
  RPC_STATUS v3; // eax
  void *v4; // r8
  NTSTATUS v5; // eax
  ULONG v6; // eax
  int v8; // [rsp+20h] [rbp-28h] BYREF
  WCHAR Dst; // [rsp+24h] [rbp-24h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-20h] BYREF

  v8 = 0;
  Uuid = 0;
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
    return 0;
  RtlGetDeviceFamilyInfoEnum(0, &v8, 0);
  if ( v8 == 5 || (unsigned int)(v8 - 11) <= 1 )
    return 0;
  v0 = ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\Upfc.exe", &Dst, 1u);
  v1 = v0;
  if ( v0 > 1 )
  {
    P = (LPWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * v0 + 326);
    if ( !P )
    {
      v2 = 8;
      goto LABEL_16;
    }
    ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\Upfc.exe", P, v1);
    BufferCount = 163;
    Buffer = &P[v1 - 1];
    v3 = UuidCreate(&Uuid);
    v2 = v3;
    if ( v3 && v3 != 1824 )
      goto LABEL_16;
    v5 = ScAllocTimer(&qword_1400BC668, ScpMedicTimerCallback, v4);
    if ( v5 < 0 )
    {
      v2 = RtlNtStatusToDosError(v5);
      goto LABEL_15;
    }
    v6 = SkpMedicLaunch(1);
    if ( v6 )
    {
      v2 = 0;
      if ( v6 != 2 )
        v2 = v6;
LABEL_15:
      if ( !v2 )
        return v2;
      goto LABEL_16;
    }
    SkpMedicTimerArm();
    return 0;
  }
  v2 = 3;
LABEL_16:
  if ( qword_1400BC668 )
  {
    TpReleaseTimer();
    qword_1400BC668 = 0;
  }
  if ( P )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    P = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x140042dd0  push    rbx
0x140042dd2  sub     rsp, 40h
0x140042dd6  mov     rax, cs:__security_cookie
0x140042ddd  xor     rax, rsp
0x140042de0  mov     [rsp+48h+var_10], rax
0x140042de5  xorps   xmm0, xmm0
0x140042de8  mov     [rsp+48h+var_28], 0
0x140042df0  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x140042df5  call    cs:__imp_RtlGetCurrentServiceSessionId
0x140042dfb  test    eax, eax
0x140042dfd  jnz     loc_140042F67
0x140042e03  xor     r8d, r8d
0x140042e06  lea     rdx, [rsp+48h+var_28]
0x140042e0b  xor     ecx, ecx
0x140042e0d  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x140042e13  mov     eax, [rsp+48h+var_28]
0x140042e17  cmp     eax, 5
0x140042e1a  jz      loc_140042F67
0x140042e20  add     eax, 0FFFFFFF5h
0x140042e23  cmp     eax, 1
0x140042e26  jbe     loc_140042F67
0x140042e2c  mov     r8d, 1; nSize
0x140042e32  lea     rdx, [rsp+48h+Dst]; lpDst
0x140042e37  lea     rcx, Src; "%SystemRoot%\\System32\\Upfc.exe"
0x140042e3e  call    cs:__imp_ExpandEnvironmentStringsW
0x140042e44  mov     ebx, eax
0x140042e46  cmp     eax, 1
0x140042e49  ja      short loc_140042E55
0x140042e4b  mov     ebx, 3
0x140042e50  jmp     loc_140042F12
0x140042e55  mov     rcx, gs:60h
0x140042e5e  lea     r8, ds:146h[rbx*2]; Size
0x140042e66  xor     edx, edx; Flags
0x140042e68  mov     rcx, [rcx+30h]; HeapHandle
0x140042e6c  call    cs:__imp_RtlAllocateHeap
0x140042e72  mov     cs:P, rax
0x140042e79  test    rax, rax
0x140042e7c  jnz     short loc_140042E86
0x140042e7e  lea     ebx, [rax+8]
0x140042e81  jmp     loc_140042F12
0x140042e86  mov     rdx, cs:P; lpDst
0x140042e8d  lea     rcx, Src; "%SystemRoot%\\System32\\Upfc.exe"
0x140042e94  mov     r8d, ebx; nSize
0x140042e97  call    cs:__imp_ExpandEnvironmentStringsW
0x140042e9d  mov     rax, cs:P
0x140042ea4  lea     ecx, [rbx-1]
0x140042ea7  mov     cs:BufferCount, 0A3h
0x140042eb2  lea     rcx, [rax+rcx*2]
0x140042eb6  mov     cs:Buffer, rcx
0x140042ebd  lea     rcx, [rsp+48h+Uuid]; Uuid
0x140042ec2  call    cs:__imp_UuidCreate
0x140042ec8  mov     ebx, eax
0x140042eca  test    eax, eax
0x140042ecc  jz      short loc_140042ED5
0x140042ece  cmp     eax, 720h
0x140042ed3  jnz     short loc_140042F12
0x140042ed5  lea     rdx, ScpMedicTimerCallback; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)
0x140042edc  lea     rcx, qword_1400BC668; struct _TP_TIMER **
0x140042ee3  call    ?ScAllocTimer@@YAJPEAPEAU_TP_TIMER@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z2@Z; ScAllocTimer(_TP_TIMER * *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *)
0x140042ee8  test    eax, eax
0x140042eea  jns     short loc_140042EF8
0x140042eec  mov     ecx, eax; Status
0x140042eee  call    cs:__imp_RtlNtStatusToDosError
0x140042ef4  mov     ebx, eax
0x140042ef6  jmp     short loc_140042F0E
0x140042ef8  mov     ecx, 1
0x140042efd  call    SkpMedicLaunch
0x140042f02  test    eax, eax
0x140042f04  jz      short loc_140042F62
0x140042f06  xor     ebx, ebx
0x140042f08  cmp     eax, 2
0x140042f0b  cmovnz  ebx, eax
0x140042f0e  test    ebx, ebx
0x140042f10  jz      short loc_140042F69
0x140042f12  mov     rcx, cs:qword_1400BC668
0x140042f19  test    rcx, rcx
0x140042f1c  jz      short loc_140042F2F
0x140042f1e  call    cs:__imp_TpReleaseTimer
0x140042f24  mov     cs:qword_1400BC668, 0
0x140042f2f  cmp     cs:P, 0
0x140042f37  jz      short loc_140042F69
0x140042f39  mov     rcx, gs:60h
0x140042f42  xor     edx, edx; Flags
0x140042f44  mov     r8, cs:P; P
0x140042f4b  mov     rcx, [rcx+30h]; HeapHandle
0x140042f4f  call    cs:__imp_RtlFreeHeap
0x140042f55  mov     cs:P, 0
0x140042f60  jmp     short loc_140042F69
0x140042f62  call    SkpMedicTimerArm
0x140042f67  xor     ebx, ebx
0x140042f69  mov     eax, ebx
0x140042f6b  mov     rcx, [rsp+48h+var_10]
0x140042f70  xor     rcx, rsp; StackCookie
0x140042f73  call    __security_check_cookie
0x140042f78  add     rsp, 40h
0x140042f7c  pop     rbx
0x140042f7d  retn
```
