# LsaCallAuthenticationPackage

- ea: `0x1800095f0`
- end: `0x18000973c`
- name: `LsaCallAuthenticationPackage`
- size: `332`
- prototype: `NTSTATUS __stdcall(HANDLE LsaHandle, ULONG AuthenticationPackage, PVOID ProtocolSubmitBuffer, ULONG SubmitBufferLength, PVOID *ProtocolReturnBuffer, PULONG ReturnBufferLength, PNTSTATUS ProtocolStatus)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800197b0`

## callees

- `0x180008180`
- `0x1800095f0`
- `0x18000a0a0`
- `0x18000a108`
- `0x18002205f`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000965c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000965c`

## pseudocode

```c
NTSTATUS __stdcall LsaCallAuthenticationPackage(
        HANDLE LsaHandle,
        ULONG AuthenticationPackage,
        PVOID ProtocolSubmitBuffer,
        ULONG SubmitBufferLength,
        PVOID *ProtocolReturnBuffer,
        PULONG ReturnBufferLength,
        PNTSTATUS ProtocolStatus)
{
  _DWORD *Value; // rax
  NTSTATUS result; // eax
  NTSTATUS v13; // ebx
  _QWORD v14[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+48h] [rbp-B8h]
  NTSTATUS v16; // [rsp+4Ch] [rbp-B4h]
  __int64 v17; // [rsp+50h] [rbp-B0h]
  PVOID v18; // [rsp+58h] [rbp-A8h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+70h] [rbp-90h]

  memset_0(v14, 0, 0xF0u);
  v20 = 0;
  v19 = 0;
  v17 = AuthenticationPackage;
  v18 = ProtocolSubmitBuffer;
  LODWORD(v19) = SubmitBufferLength;
  if ( (DllState & 0x20000000) != 0 || (Value = TlsGetValue(SecTlsIP)) == 0 )
    HIDWORD(v20) = 0;
  else
    HIDWORD(v20) = Value[8];
  v15 = 1;
  v14[0] = 15728840;
  if ( SecpLsaDispatchFn )
  {
    v13 = SecpLsaDispatchFn(v14);
  }
  else
  {
    if ( (NtCurrentPeb()->BitField & 2) != 0 )
    {
      result = LsaInsertProtectedProcessAddress(ProtocolSubmitBuffer, SubmitBufferLength);
      if ( result < 0 )
        return result;
    }
    v13 = CallRpcSPM((__int64)LsaHandle, (__int64)v14, 0xF0u, v14);
    if ( (NtCurrentPeb()->BitField & 2) != 0 )
      LsaRemoveProtectedProcessAddress(ProtocolSubmitBuffer, SubmitBufferLength);
  }
  if ( v13 >= 0 )
  {
    if ( ProtocolReturnBuffer )
      *ProtocolReturnBuffer = (PVOID)*((_QWORD *)&v19 + 1);
    if ( ReturnBufferLength )
      *ReturnBufferLength = v20;
    if ( ProtocolStatus )
      *ProtocolStatus = DWORD1(v19);
    return v16;
  }
  return v13;
}

```

## disassembly

```asm
0x1800095f0  push    rbp
0x1800095f2  push    rbx
0x1800095f3  push    rsi
0x1800095f4  push    rdi
0x1800095f5  push    r12
0x1800095f7  push    r14
0x1800095f9  lea     rbp, [rsp-18h]
0x1800095fe  sub     rsp, 118h
0x180009605  mov     rsi, r8
0x180009608  mov     ebx, edx
0x18000960a  mov     r14, rcx
0x18000960d  mov     r12d, 0F0h
0x180009613  mov     r8d, r12d; Size
0x180009616  lea     rcx, [rsp+140h+var_120]; void *
0x18000961b  xor     edx, edx; Val
0x18000961d  mov     edi, r9d
0x180009620  call    memset_0
0x180009625  xor     eax, eax
0x180009627  xorps   xmm0, xmm0
0x18000962a  test    cs:DllState, 20000000h
0x180009634  movups  [rsp+140h+var_F0], xmm0
0x180009639  mov     [rsp+140h+var_D0], rax
0x18000963e  movups  [rsp+140h+var_E0], xmm0
0x180009643  mov     dword ptr [rsp+140h+var_F0], ebx
0x180009647  mov     qword ptr [rsp+140h+var_F0+8], rsi
0x18000964c  mov     dword ptr [rsp+140h+var_E0], edi
0x180009650  mov     dword ptr [rsp+140h+var_D0+4], eax
0x180009654  jnz     short loc_180009670
0x180009656  mov     ecx, cs:SecTlsIP; dwTlsIndex
0x18000965c  call    cs:__imp_TlsGetValue
0x180009662  test    rax, rax
0x180009665  jz      short loc_180009670
0x180009667  mov     eax, [rax+20h]
0x18000966a  mov     dword ptr [rsp+140h+var_D0+4], eax
0x18000966e  jmp     short loc_180009678
0x180009670  mov     dword ptr [rsp+140h+var_D0+4], 0
0x180009678  mov     rax, cs:SecpLsaDispatchFn
0x18000967f  mov     [rsp+140h+var_F8], 1
0x180009687  mov     [rsp+140h+var_120], 0F000C8h
0x180009690  test    rax, rax
0x180009693  jnz     short loc_1800096E4
0x180009695  mov     rax, gs:60h
0x18000969e  test    byte ptr [rax+3], 2
0x1800096a2  jz      short loc_1800096B2
0x1800096a4  mov     edx, edi; BufferSize
0x1800096a6  mov     rcx, rsi; BufferAddress
0x1800096a9  call    LsaInsertProtectedProcessAddress
0x1800096ae  test    eax, eax
0x1800096b0  js      short loc_18000972C
0x1800096b2  lea     r9, [rsp+140h+var_120]
0x1800096b7  mov     r8d, r12d
0x1800096ba  lea     rdx, [rsp+140h+var_120]
0x1800096bf  mov     rcx, r14
0x1800096c2  call    CallRpcSPM
0x1800096c7  mov     rcx, gs:60h
0x1800096d0  mov     ebx, eax
0x1800096d2  test    byte ptr [rcx+3], 2
0x1800096d6  jz      short loc_1800096F0
0x1800096d8  mov     edx, edi; BufferSize
0x1800096da  mov     rcx, rsi; BufferAddress
0x1800096dd  call    LsaRemoveProtectedProcessAddress
0x1800096e2  jmp     short loc_1800096F0
0x1800096e4  lea     rcx, [rsp+140h+var_120]
0x1800096e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ee  mov     ebx, eax
0x1800096f0  test    ebx, ebx
0x1800096f2  js      short loc_18000972A
0x1800096f4  mov     rcx, [rbp+40h+ProtocolReturnBuffer]
0x1800096f8  test    rcx, rcx
0x1800096fb  jz      short loc_180009705
0x1800096fd  mov     rax, qword ptr [rsp+140h+var_E0+8]
0x180009702  mov     [rcx], rax
0x180009705  mov     rcx, [rbp+40h+ReturnBufferLength]
0x180009709  test    rcx, rcx
0x18000970c  jz      short loc_180009714
0x18000970e  mov     eax, dword ptr [rsp+140h+var_D0]
0x180009712  mov     [rcx], eax
0x180009714  mov     rcx, [rbp+40h+ProtocolStatus]
0x18000971b  test    rcx, rcx
0x18000971e  jz      short loc_180009726
0x180009720  mov     eax, dword ptr [rsp+140h+var_E0+4]
0x180009724  mov     [rcx], eax
0x180009726  mov     ebx, [rsp+140h+var_F4]
0x18000972a  mov     eax, ebx
0x18000972c  add     rsp, 118h
0x180009733  pop     r14
0x180009735  pop     r12
0x180009737  pop     rdi
0x180009738  pop     rsi
0x180009739  pop     rbx
0x18000973a  pop     rbp
0x18000973b  retn
```
