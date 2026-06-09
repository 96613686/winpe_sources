# CFlexArray::operator[](int)

- ea: `0x180007e30`
- end: `0x180007f3e`
- name: `??ACFlexArray@@QEAAAEAPEAXH@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `28`
- callee_count: `4`
- tags: ``

## callers

- `0x1800024f0`
- `0x180003270`
- `0x1800036e0`
- `0x180003730`
- `0x180003940`
- `0x180003990`
- `0x180003af0`
- `0x180003bb0`
- `0x180007ddc`
- `0x180007f80`
- `0x180008cc0`
- `0x18000af60`
- `0x18000e8b0`
- `0x180026140`
- `0x180027190`
- `0x180027500`
- `0x18002b600`
- `0x1800335d0`
- `0x180033a90`
- `0x180034340`
- `0x180034520`
- `0x180034540`
- `0x180034600`
- `0x1800392d0`
- `0x180039540`
- `0x1800398a0`
- `0x180040fe0`
- `0x1800411b0`

## callees

- `0x180007e30`
- `0x18002ca74`
- `0x18002ee7c`
- `0x1800442d3`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e9c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180007f0c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180007f0c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180007ec6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180007ec6`

## pseudocode

```c
__int64 __fastcall CFlexArray::operator[](__int64 a1, int a2)
{
  __int64 *v3; // rbx
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF
  __int64 v5; // [rsp+40h] [rbp+18h]

  if ( a2 < 0 || a2 >= *(_DWORD *)a1 )
  {
    if ( byte_18006F9C8 )
    {
      v5 = 4294967294LL;
      v3 = &qword_18006A9C0[10 * (unsigned __int8)_InterlockedExchangeAdd(&dword_18006F9C0, 1u)];
      v3[1] = 4294967294LL;
      *(_DWORD *)v3 = GetCurrentThreadId();
      memset_0(v3 + 2, 0, 0x40u);
      RtlCaptureStackBackTrace(1u, 8u, (PVOID *)v3 + 2, 0);
      if ( (unsigned int)(dword_18007007C + 2) <= 1 )
        DebugBreak();
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_163ce0ae94013f6f38d9fc28353ec4f3_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  return *(_QWORD *)(a1 + 16) + 8LL * a2;
}

```

## disassembly

```asm
0x180007e30  sub     rsp, 28h
0x180007e34  test    edx, edx
0x180007e36  js      short loc_180007E4C
0x180007e38  cmp     edx, [rcx]
0x180007e3a  jge     short loc_180007E4C
0x180007e3c  mov     rax, [rcx+10h]
0x180007e40  movsxd  r8, edx
0x180007e43  lea     rax, [rax+r8*8]
0x180007e47  add     rsp, 28h
0x180007e4b  retn
0x180007e4c  cmp     cs:byte_18006F9C8, 0
0x180007e53  jz      loc_180007EDF
0x180007e59  mov     [rsp+28h+var_8], rbx
0x180007e5e  mov     eax, 1
0x180007e63  lock xadd cs:dword_18006F9C0, eax
0x180007e6b  mov     eax, eax
0x180007e6d  movzx   ecx, al
0x180007e70  mov     [rsp+28h+arg_10], 0
0x180007e79  mov     dword ptr [rsp+28h+arg_10], 0FFFFFFFEh
0x180007e81  mov     rax, [rsp+28h+arg_10]
0x180007e86  lea     rbx, [rcx+rcx*4]
0x180007e8a  lea     rcx, qword_18006A9C0
0x180007e91  shl     rbx, 4
0x180007e95  add     rbx, rcx
0x180007e98  mov     [rbx+8], rax
0x180007e9c  call    cs:__imp_GetCurrentThreadId
0x180007ea2  xor     edx, edx; Val
0x180007ea4  lea     rcx, [rbx+10h]; void *
0x180007ea8  mov     r8d, 40h ; '@'; Size
0x180007eae  mov     [rbx], eax
0x180007eb0  call    memset_0
0x180007eb5  xor     r9d, r9d; BackTraceHash
0x180007eb8  lea     r8, [rbx+10h]; BackTrace
0x180007ebc  mov     edx, 8; FramesToCapture
0x180007ec1  mov     ecx, 1; FramesToSkip
0x180007ec6  call    cs:__imp_RtlCaptureStackBackTrace
0x180007ecc  mov     eax, cs:dword_18007007C
0x180007ed2  mov     rbx, [rsp+28h+var_8]
0x180007ed7  add     eax, 2
0x180007eda  cmp     eax, 1
0x180007edd  jbe     short loc_180007F0C
0x180007edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ee6  lea     rax, WPP_GLOBAL_Control
0x180007eed  cmp     rcx, rax
0x180007ef0  jnz     short loc_180007F14
0x180007ef2  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180007ef9  mov     [rsp+28h+pExceptionObject], 57h ; 'W'
0x180007f01  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180007f06  call    _CxxThrowException_0
0x180007f0c  call    cs:__imp_DebugBreak
0x180007f12  jmp     short loc_180007EDF
0x180007f14  test    byte ptr [rcx+1Ch], 1
0x180007f18  jz      short loc_180007EF2
0x180007f1a  cmp     byte ptr [rcx+19h], 2
0x180007f1e  jb      short loc_180007EF2
0x180007f20  mov     rcx, [rcx+10h]
0x180007f24  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180007f2b  mov     edx, 0Fh
0x180007f30  lea     r8, WPP_163ce0ae94013f6f38d9fc28353ec4f3_Traceguids
0x180007f37  call    WPP_SF_s
0x180007f3c  jmp     short loc_180007EF2
```
