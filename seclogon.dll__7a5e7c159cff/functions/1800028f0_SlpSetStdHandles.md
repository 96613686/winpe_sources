# SlpSetStdHandles

- ea: `0x1800028f0`
- end: `0x180002b2b`
- name: `SlpSetStdHandles`
- size: `571`
- prototype: `__int64 __fastcall(HANDLE hProcess, HANDLE hSourceProcessHandle, void *, void *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001470`

## callees

- `0x1800028f0`
- `0x180004430`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800029aa`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800029d8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800029aa`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800029d8`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180002acb`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180002af9`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180002acb`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180002af9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180002aaa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180002aaa`
- `ntdll!NtQueryInformationProcess` at `0x180002947`
- `ntdll!NtQueryInformationProcess` at `0x180002947`
- `ntdll!RtlNtStatusToDosError` at `0x180002953`
- `ntdll!RtlNtStatusToDosError` at `0x180002953`

## pseudocode

```c
__int64 __fastcall SlpSetStdHandles(HANDLE hProcess, HANDLE hSourceProcessHandle, void *a3, void *a4, void *a5)
{
  int InformationProcess; // eax
  __int64 v11; // r15
  __int64 v12; // r15
  unsigned int i; // edi
  void *v14; // rdx
  void *v15; // rdx
  unsigned int v16; // [rsp+40h] [rbp-81h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-79h] BYREF
  __int64 v18; // [rsp+50h] [rbp-71h] BYREF
  __int64 Buffer; // [rsp+58h] [rbp-69h] BYREF
  HANDLE hSourceHandle; // [rsp+60h] [rbp-61h]
  LPVOID lpBaseAddress; // [rsp+68h] [rbp-59h]
  LPVOID v22[8]; // [rsp+70h] [rbp-51h]
  _OWORD ProcessInformation[6]; // [rsp+B0h] [rbp-11h] BYREF

  Buffer = 0;
  TargetHandle = 0;
  v16 = 0;
  v18 = 0;
  memset(ProcessInformation, 0, 44);
  InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess < 0 )
  {
    RtlNtStatusToDosError(InformationProcess);
    return 0;
  }
  v11 = *((_QWORD *)&ProcessInformation[0] + 1);
  if ( !*((_QWORD *)&ProcessInformation[0] + 1)
    || !(unsigned int)SlpGetPeb32Address(hProcess, &v18)
    || !ReadProcessMemory(hProcess, (LPCVOID)(v11 + 32), &Buffer, 8u, 0) )
  {
    return 0;
  }
  if ( v18 )
  {
    if ( !ReadProcessMemory(hProcess, (LPCVOID)(v18 + 16), &v16, 4u, 0) )
      return 0;
    v12 = v16;
  }
  else
  {
    v12 = 0;
  }
  if ( (__int64)a3 < 0 || (__int64)a4 < 0 || (__int64)a5 < 0 )
    return 0;
  hSourceHandle = a3;
  v22[1] = a4;
  v22[4] = a5;
  lpBaseAddress = (LPVOID)(Buffer + 32);
  v22[2] = (LPVOID)(Buffer + 40);
  v22[5] = (LPVOID)(Buffer + 48);
  if ( v12 )
  {
    v22[0] = (LPVOID)(v12 + 24);
    v22[3] = (LPVOID)(v12 + 28);
    v22[6] = (LPVOID)(v12 + 32);
  }
  for ( i = 0; i < 3; ++i )
  {
    v14 = *(&hSourceHandle + 3 * (int)i);
    if ( v14 )
    {
      if ( ((unsigned __int64)*(&hSourceHandle + 3 * (int)i) & 0x10000003) != 3 )
      {
        if ( !DuplicateHandle(hSourceProcessHandle, v14, hProcess, &TargetHandle, 0, 1, 2u) )
          return 0;
        if ( !WriteProcessMemory(hProcess, v22[3 * (int)i - 1], &TargetHandle, 8u, 0) )
          return 0;
        if ( v12 )
        {
          v15 = v22[3 * (int)i];
          v16 = (unsigned int)TargetHandle;
          if ( !WriteProcessMemory(hProcess, v15, &v16, 4u, 0) )
            return 0;
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800028f0  push    rbp
0x1800028f2  push    rbx
0x1800028f3  push    rsi
0x1800028f4  push    rdi
0x1800028f5  push    r12
0x1800028f7  push    r14
0x1800028f9  lea     rbp, [rsp-27h]
0x1800028fe  sub     rsp, 0E8h
0x180002905  xor     r12d, r12d
0x180002908  xorps   xmm0, xmm0
0x18000290b  mov     rdi, r9
0x18000290e  mov     [rbp+4Fh+Buffer], r12
0x180002912  mov     rsi, r8
0x180002915  mov     [rbp+4Fh+TargetHandle], r12
0x180002919  mov     r14, rdx
0x18000291c  mov     [rsp+110h+var_D0], r12d
0x180002921  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x180002925  xor     eax, eax
0x180002927  mov     [rbp+4Fh+var_C0], r12
0x18000292b  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180002931  mov     [rsp+110h+ReturnLength], r12; ReturnLength
0x180002936  lea     r8, [rbp+4Fh+ProcessInformation]; ProcessInformation
0x18000293a  xor     edx, edx; ProcessInformationClass
0x18000293c  movups  xmmword ptr [rbp+4Fh+var_50+0Ch], xmm0
0x180002940  mov     rbx, rcx
0x180002943  movups  [rbp+4Fh+ProcessInformation], xmm0
0x180002947  call    cs:__imp_NtQueryInformationProcess
0x18000294d  test    eax, eax
0x18000294f  jns     short loc_18000296B
0x180002951  mov     ecx, eax; Status
0x180002953  call    cs:__imp_RtlNtStatusToDosError
0x180002959  xor     eax, eax
0x18000295b  add     rsp, 0E8h
0x180002962  pop     r14
0x180002964  pop     r12
0x180002966  pop     rdi
0x180002967  pop     rsi
0x180002968  pop     rbx
0x180002969  pop     rbp
0x18000296a  retn
0x18000296b  mov     [rsp+110h+arg_0], r15
0x180002973  mov     r15, qword ptr [rbp+4Fh+ProcessInformation+8]
0x180002977  test    r15, r15
0x18000297a  jz      loc_180002B11
0x180002980  lea     rdx, [rbp+4Fh+var_C0]
0x180002984  mov     rcx, rbx
0x180002987  call    SlpGetPeb32Address
0x18000298c  test    eax, eax
0x18000298e  jz      loc_180002B11
0x180002994  lea     rdx, [r15+20h]; lpBaseAddress
0x180002998  mov     [rsp+110h+ReturnLength], r12; lpNumberOfBytesRead
0x18000299d  mov     r9d, 8; nSize
0x1800029a3  lea     r8, [rbp+4Fh+Buffer]; lpBuffer
0x1800029a7  mov     rcx, rbx; hProcess
0x1800029aa  call    cs:__imp_ReadProcessMemory
0x1800029b0  test    eax, eax
0x1800029b2  jz      loc_180002B11
0x1800029b8  mov     rdx, [rbp+4Fh+var_C0]
0x1800029bc  test    rdx, rdx
0x1800029bf  jz      short loc_1800029ED
0x1800029c1  add     rdx, 10h; lpBaseAddress
0x1800029c5  mov     [rsp+110h+ReturnLength], r12; lpNumberOfBytesRead
0x1800029ca  mov     r9d, 4; nSize
0x1800029d0  lea     r8, [rsp+110h+var_D0]; lpBuffer
0x1800029d5  mov     rcx, rbx; hProcess
0x1800029d8  call    cs:__imp_ReadProcessMemory
0x1800029de  test    eax, eax
0x1800029e0  jz      loc_180002B11
0x1800029e6  mov     r15d, [rsp+110h+var_D0]
0x1800029eb  jmp     short loc_1800029F0
0x1800029ed  mov     r15, r12
0x1800029f0  test    rsi, rsi
0x1800029f3  js      loc_180002B11
0x1800029f9  test    rdi, rdi
0x1800029fc  js      loc_180002B11
0x180002a02  mov     rdx, [rbp+4Fh+arg_20]
0x180002a06  test    rdx, rdx
0x180002a09  js      loc_180002B11
0x180002a0f  mov     rcx, [rbp+4Fh+Buffer]
0x180002a13  mov     [rbp+4Fh+hSourceHandle], rsi
0x180002a17  mov     [rbp+4Fh+var_98], rdi
0x180002a1b  mov     [rbp+4Fh+var_80], rdx
0x180002a1f  lea     rax, [rcx+20h]
0x180002a23  mov     [rbp+4Fh+lpBaseAddress], rax
0x180002a27  lea     rax, [rcx+28h]
0x180002a2b  mov     [rbp+4Fh+var_90], rax
0x180002a2f  lea     rax, [rcx+30h]
0x180002a33  mov     [rbp+4Fh+var_78], rax
0x180002a37  test    r15, r15
0x180002a3a  jz      short loc_180002A54
0x180002a3c  lea     rax, [r15+18h]
0x180002a40  mov     [rbp+4Fh+var_A0], rax
0x180002a44  lea     rax, [r15+1Ch]
0x180002a48  mov     [rbp+4Fh+var_88], rax
0x180002a4c  lea     rax, [r15+20h]
0x180002a50  mov     [rbp+4Fh+var_70], rax
0x180002a54  mov     edi, r12d
0x180002a57  cmp     edi, 3
0x180002a5a  jnb     loc_180002B0A
0x180002a60  movsxd  rax, edi
0x180002a63  lea     rcx, [rax+rax*2]
0x180002a67  lea     rsi, ds:0[rcx*8]
0x180002a6f  mov     rdx, [rbp+rsi+4Fh+hSourceHandle]; hSourceHandle
0x180002a74  test    rdx, rdx
0x180002a77  jz      loc_180002B03
0x180002a7d  mov     rax, rdx
0x180002a80  and     eax, 10000003h
0x180002a85  cmp     rax, 3
0x180002a89  jz      short loc_180002B03
0x180002a8b  mov     [rsp+110h+dwOptions], 2; dwOptions
0x180002a93  lea     r9, [rbp+4Fh+TargetHandle]; lpTargetHandle
0x180002a97  mov     [rsp+110h+bInheritHandle], 1; bInheritHandle
0x180002a9f  mov     r8, rbx; hTargetProcessHandle
0x180002aa2  mov     rcx, r14; hSourceProcessHandle
0x180002aa5  mov     dword ptr [rsp+110h+ReturnLength], r12d; dwDesiredAccess
0x180002aaa  call    cs:__imp_DuplicateHandle
0x180002ab0  test    eax, eax
0x180002ab2  jz      short loc_180002B11
0x180002ab4  mov     rdx, [rbp+rsi+4Fh+lpBaseAddress]; lpBaseAddress
0x180002ab9  lea     r8, [rbp+4Fh+TargetHandle]; lpBuffer
0x180002abd  mov     r9d, 8; nSize
0x180002ac3  mov     [rsp+110h+ReturnLength], r12; lpNumberOfBytesWritten
0x180002ac8  mov     rcx, rbx; hProcess
0x180002acb  call    cs:__imp_WriteProcessMemory
0x180002ad1  test    eax, eax
0x180002ad3  jz      short loc_180002B11
0x180002ad5  test    r15, r15
0x180002ad8  jz      short loc_180002B03
0x180002ada  mov     eax, dword ptr [rbp+4Fh+TargetHandle]
0x180002add  lea     r8, [rsp+110h+var_D0]; lpBuffer
0x180002ae2  mov     rdx, [rbp+rsi+4Fh+var_A0]; lpBaseAddress
0x180002ae7  mov     r9d, 4; nSize
0x180002aed  mov     rcx, rbx; hProcess
0x180002af0  mov     [rsp+110h+var_D0], eax
0x180002af4  mov     [rsp+110h+ReturnLength], r12; lpNumberOfBytesWritten
0x180002af9  call    cs:__imp_WriteProcessMemory
0x180002aff  test    eax, eax
0x180002b01  jz      short loc_180002B11
0x180002b03  inc     edi
0x180002b05  jmp     loc_180002A57
0x180002b0a  mov     eax, 1
0x180002b0f  jmp     short loc_180002B13
0x180002b11  xor     eax, eax
0x180002b13  mov     r15, [rsp+110h+arg_0]
0x180002b1b  add     rsp, 0E8h
0x180002b22  pop     r14
0x180002b24  pop     r12
0x180002b26  pop     rdi
0x180002b27  pop     rsi
0x180002b28  pop     rbx
0x180002b29  pop     rbp
0x180002b2a  retn
```
