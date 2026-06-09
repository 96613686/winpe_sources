# OneXDuplicateRuntimeState

- ea: `0x18007ed3c`
- end: `0x18007ef17`
- name: `OneXDuplicateRuntimeState`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180030b00`

## callees

- `0x18007ed3c`
- `0x18007ef20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ee2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ee2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007eddc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007edeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007eddc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007edeb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007ee1c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007ee1c`
- `MobileNetworking!AllocateMemory` at `0x18007ed8d`
- `MobileNetworking!AllocateMemory` at `0x18007ed8d`
- `MobileNetworking!SetBufferAndLength` at `0x18007ee6e`
- `MobileNetworking!SetBufferAndLength` at `0x18007ee6e`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x18007eea8`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x18007eea8`

## pseudocode

```c
__int64 __fastcall OneXDuplicateRuntimeState(__int64 a1, _QWORD *a2)
{
  DWORD LastError; // r15d
  HANDLE *v5; // rdi
  void *v6; // rsi
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  _DWORD *v10; // [rsp+70h] [rbp+30h] BYREF

  v10 = 0;
  *a2 = 0;
  if ( a1 )
  {
    LastError = AllocateMemory(56, &v10, "OneXDuplicateRuntimeState", 228);
    if ( !LastError )
    {
      if ( (*(_BYTE *)a1 & 8) != 0 )
      {
        *v10 |= 8u;
        v10[8] = *(_DWORD *)(a1 + 32);
      }
      v10[9] = *(_DWORD *)(a1 + 36);
      if ( (*(_BYTE *)a1 & 1) != 0 && *(_QWORD *)(a1 + 8) )
      {
        v5 = (HANDLE *)v10;
        v6 = *(void **)(a1 + 8);
        CurrentProcess = GetCurrentProcess();
        v8 = GetCurrentProcess();
        if ( !DuplicateHandle(v8, v6, CurrentProcess, v5 + 1, 0, 0, 2u) )
        {
          LastError = GetLastError();
          if ( LastError )
            goto LABEL_22;
        }
        *v10 |= 1u;
      }
      if ( (*(_BYTE *)a1 & 2) != 0 && *(_DWORD *)(a1 + 16) && *(_QWORD *)(a1 + 24) )
      {
        LastError = SetBufferAndLength(v10 + 6, v10 + 4);
        if ( LastError )
          goto LABEL_22;
        *v10 |= 2u;
      }
      if ( (*(_BYTE *)a1 & 4) == 0 || !*(_DWORD *)(a1 + 44) || !*(_QWORD *)(a1 + 48) )
      {
        *a2 = v10;
        return LastError;
      }
      LastError = AllocateAndCopyPointerData(v10 + 12);
      if ( !LastError )
      {
        *v10 |= 4u;
        v10[10] = *(_DWORD *)(a1 + 40);
        v10[11] = *(_DWORD *)(a1 + 44);
        *a2 = v10;
        return LastError;
      }
    }
LABEL_22:
    OneXFreeRuntimeState();
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x18007ed3c  mov     [rsp-28h+arg_8], rbx
0x18007ed41  mov     [rsp-28h+arg_10], rsi
0x18007ed46  push    rbp
0x18007ed47  push    rdi
0x18007ed48  push    r12
0x18007ed4a  push    r14
0x18007ed4c  push    r15
0x18007ed4e  mov     rbp, rsp
0x18007ed51  sub     rsp, 40h
0x18007ed55  mov     [rbp+arg_0], 0
0x18007ed5d  mov     r12, rdx
0x18007ed60  mov     qword ptr [rdx], 0
0x18007ed67  mov     r14, rcx
0x18007ed6a  test    rcx, rcx
0x18007ed6d  jnz     short loc_18007ED77
0x18007ed6f  xor     r15d, r15d
0x18007ed72  jmp     loc_18007EEFA
0x18007ed77  mov     r9d, 0E4h
0x18007ed7d  lea     r8, aOnexduplicater; "OneXDuplicateRuntimeState"
0x18007ed84  lea     rdx, [rbp+arg_0]
0x18007ed88  mov     ecx, 38h ; '8'
0x18007ed8d  call    cs:__imp_AllocateMemory
0x18007ed94  nop     dword ptr [rax+rax+00h]
0x18007ed99  mov     r15d, eax
0x18007ed9c  test    eax, eax
0x18007ed9e  jnz     loc_18007EEF1
0x18007eda4  test    byte ptr [r14], 8
0x18007eda8  jz      short loc_18007EDBC
0x18007edaa  mov     rcx, [rbp+arg_0]
0x18007edae  or      dword ptr [rcx], 8
0x18007edb1  mov     rcx, [rbp+arg_0]
0x18007edb5  mov     edx, [r14+20h]
0x18007edb9  mov     [rcx+20h], edx
0x18007edbc  mov     rax, [rbp+arg_0]
0x18007edc0  mov     ecx, [r14+24h]
0x18007edc4  mov     [rax+24h], ecx
0x18007edc7  test    byte ptr [r14], 1
0x18007edcb  jz      short loc_18007EE4A
0x18007edcd  cmp     qword ptr [r14+8], 0
0x18007edd2  jz      short loc_18007EE4A
0x18007edd4  mov     rdi, [rbp+arg_0]
0x18007edd8  mov     rsi, [r14+8]
0x18007eddc  call    cs:__imp_GetCurrentProcess
0x18007ede3  nop     dword ptr [rax+rax+00h]
0x18007ede8  mov     rbx, rax
0x18007edeb  call    cs:__imp_GetCurrentProcess
0x18007edf2  nop     dword ptr [rax+rax+00h]
0x18007edf7  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18007edff  lea     r9, [rdi+8]; lpTargetHandle
0x18007ee03  mov     rcx, rax; hSourceProcessHandle
0x18007ee06  mov     [rsp+40h+bInheritHandle], 0; bInheritHandle
0x18007ee0e  mov     r8, rbx; hTargetProcessHandle
0x18007ee11  mov     [rsp+40h+dwDesiredAccess], 0; dwDesiredAccess
0x18007ee19  mov     rdx, rsi; hSourceHandle
0x18007ee1c  call    cs:__imp_DuplicateHandle
0x18007ee23  nop     dword ptr [rax+rax+00h]
0x18007ee28  test    eax, eax
0x18007ee2a  jnz     short loc_18007EE43
0x18007ee2c  call    cs:__imp_GetLastError
0x18007ee33  nop     dword ptr [rax+rax+00h]
0x18007ee38  mov     r15d, eax
0x18007ee3b  test    eax, eax
0x18007ee3d  jnz     loc_18007EEF1
0x18007ee43  mov     rax, [rbp+arg_0]
0x18007ee47  or      dword ptr [rax], 1
0x18007ee4a  test    byte ptr [r14], 2
0x18007ee4e  jz      short loc_18007EE88
0x18007ee50  mov     r9d, [r14+10h]
0x18007ee54  test    r9d, r9d
0x18007ee57  jz      short loc_18007EE88
0x18007ee59  mov     r8, [r14+18h]
0x18007ee5d  test    r8, r8
0x18007ee60  jz      short loc_18007EE88
0x18007ee62  mov     rcx, [rbp+arg_0]
0x18007ee66  lea     rdx, [rcx+10h]
0x18007ee6a  add     rcx, 18h
0x18007ee6e  call    cs:__imp_SetBufferAndLength
0x18007ee75  nop     dword ptr [rax+rax+00h]
0x18007ee7a  mov     r15d, eax
0x18007ee7d  test    eax, eax
0x18007ee7f  jnz     short loc_18007EEF1
0x18007ee81  mov     rax, [rbp+arg_0]
0x18007ee85  or      dword ptr [rax], 2
0x18007ee88  test    byte ptr [r14], 4
0x18007ee8c  jz      short loc_18007EEE2
0x18007ee8e  mov     r8d, [r14+2Ch]
0x18007ee92  test    r8d, r8d
0x18007ee95  jz      short loc_18007EEE2
0x18007ee97  mov     rdx, [r14+30h]
0x18007ee9b  test    rdx, rdx
0x18007ee9e  jz      short loc_18007EEE2
0x18007eea0  mov     rcx, [rbp+arg_0]
0x18007eea4  add     rcx, 30h ; '0'
0x18007eea8  call    cs:__imp_AllocateAndCopyPointerData
0x18007eeaf  nop     dword ptr [rax+rax+00h]
0x18007eeb4  mov     r15d, eax
0x18007eeb7  test    eax, eax
0x18007eeb9  jnz     short loc_18007EEF1
0x18007eebb  mov     rax, [rbp+arg_0]
0x18007eebf  or      dword ptr [rax], 4
0x18007eec2  mov     ecx, [r14+28h]
0x18007eec6  mov     rax, [rbp+arg_0]
0x18007eeca  mov     [rax+28h], ecx
0x18007eecd  mov     rax, [rbp+arg_0]
0x18007eed1  mov     ecx, [r14+2Ch]
0x18007eed5  mov     [rax+2Ch], ecx
0x18007eed8  mov     rax, [rbp+arg_0]
0x18007eedc  mov     [r12], rax
0x18007eee0  jmp     short loc_18007EEFA
0x18007eee2  mov     rcx, [rbp+arg_0]
0x18007eee6  mov     [r12], rcx
0x18007eeea  test    r15d, r15d
0x18007eeed  jz      short loc_18007EEFA
0x18007eeef  jmp     short loc_18007EEF5
0x18007eef1  mov     rcx, [rbp+arg_0]
0x18007eef5  call    OneXFreeRuntimeState
0x18007eefa  lea     r11, [rsp+40h+var_s0]
0x18007eeff  mov     eax, r15d
0x18007ef02  mov     rbx, [r11+38h]
0x18007ef06  mov     rsi, [r11+40h]
0x18007ef0a  mov     rsp, r11
0x18007ef0d  pop     r15
0x18007ef0f  pop     r14
0x18007ef11  pop     r12
0x18007ef13  pop     rdi
0x18007ef14  pop     rbp
0x18007ef15  retn
```
