# CLogFile::CreateAlwaysFile(ushort const *)

- ea: `0x18000e7c0`
- end: `0x18000e89f`
- name: `?CreateAlwaysFile@CLogFile@@MEAAXPEBG@Z`
- size: `223`
- prototype: `void __fastcall(void **this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800015f0`
- `0x18000cff8`
- `0x18000d038`
- `0x18000d68c`
- `0x18000d7dc`
- `0x18000e7c0`
- `0x18000e8a8`
- `0x18000ecb4`
- `0x180010fca`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e803`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e7e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e824`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e7e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e824`

## pseudocode

```c
void __fastcall CLogFile::CreateAlwaysFile(void **this, const unsigned __int16 *a2)
{
  void **v2; // r14
  signed int AlwaysSecureFile; // eax
  DWORD LastError; // eax
  void *v6; // rbx

  v2 = this + 2;
  AlwaysSecureFile = CSecureFile::CreateAlwaysSecureFile(this + 2, a2);
  if ( AlwaysSecureFile < 0 )
  {
    RaiseException(AlwaysSecureFile, 0, 0, 0);
    __debugbreak();
  }
  if ( !(unsigned int)CLogFile::SetSize((CLogFile *)this, dword_18001B0B4 << 10) )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  if ( *((_DWORD *)this + 18) <= 2u )
  {
    RaiseException(0x80004005, 0, 0, 0);
    __debugbreak();
  }
  v6 = *v2;
  memset_0(this[12], 0, *((unsigned int *)this + 28));
  *((_DWORD *)this[12] + 4) = 0x10000;
  *(GUID *)this[12] = s_guidLogSignature;
  this[11] = v6;
  CLogFileHeader::SetDirty((CLogFileHeader *)(this + 10), 1);
  this[16] = *v2;
  CLogFile::InitializeLogEntries((CLogFile *)this, 0, *((_DWORD *)this + 18) - 1);
  CLogFile::SetShutdown((CLogFile *)this, 1);
  CLogFile::CloseLog((CLogFile *)this);
}

```

## disassembly

```asm
0x18000e7c0  push    rbx
0x18000e7c2  push    rsi
0x18000e7c3  push    rdi
0x18000e7c4  push    r14
0x18000e7c6  sub     rsp, 28h
0x18000e7ca  lea     r14, [rcx+10h]
0x18000e7ce  mov     rsi, rcx
0x18000e7d1  mov     rcx, r14; this
0x18000e7d4  call    ?CreateAlwaysSecureFile@CSecureFile@@QEAAJPEBG@Z; CSecureFile::CreateAlwaysSecureFile(ushort const *)
0x18000e7d9  test    eax, eax
0x18000e7db  jns     short loc_18000E7EE
0x18000e7dd  xor     r9d, r9d; lpArguments
0x18000e7e0  xor     r8d, r8d; nNumberOfArguments
0x18000e7e3  xor     edx, edx; dwExceptionFlags
0x18000e7e5  mov     ecx, eax; dwExceptionCode
0x18000e7e7  call    cs:__imp_RaiseException
0x18000e7ed  int     3; Trap to Debugger
0x18000e7ee  mov     edx, cs:dword_18001B0B4
0x18000e7f4  mov     rcx, rsi; this
0x18000e7f7  shl     edx, 0Ah; unsigned int
0x18000e7fa  call    ?SetSize@CLogFile@@AEAAHK@Z; CLogFile::SetSize(ulong)
0x18000e7ff  test    eax, eax
0x18000e801  jnz     short loc_18000E811
0x18000e803  call    cs:__imp_GetLastError
0x18000e809  mov     ecx, eax; int
0x18000e80b  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000e811  xor     edx, edx; Val
0x18000e813  cmp     dword ptr [rsi+48h], 2
0x18000e817  ja      short loc_18000E82B
0x18000e819  xor     r9d, r9d; lpArguments
0x18000e81c  xor     r8d, r8d; nNumberOfArguments
0x18000e81f  mov     ecx, 80004005h; dwExceptionCode
0x18000e824  call    cs:__imp_RaiseException
0x18000e82a  int     3; Trap to Debugger
0x18000e82b  mov     r8d, [rsi+70h]; Size
0x18000e82f  mov     rcx, [rsi+60h]; void *
0x18000e833  mov     rbx, [r14]
0x18000e836  call    memset_0
0x18000e83b  mov     rax, [rsi+60h]
0x18000e83f  lea     rcx, [rsi+50h]; this
0x18000e843  mov     dword ptr [rax+10h], 10000h
0x18000e84a  movups  xmm0, xmmword ptr cs:?s_guidLogSignature@@3U_GUID@@B.Data1; _GUID const s_guidLogSignature ...
0x18000e851  mov     rax, [rsi+60h]
0x18000e855  movdqu  xmmword ptr [rax], xmm0
0x18000e859  mov     [rsi+58h], rbx
0x18000e85d  mov     ebx, 1
0x18000e862  mov     edx, ebx; int
0x18000e864  call    ?SetDirty@CLogFileHeader@@QEAAXH@Z; CLogFileHeader::SetDirty(int)
0x18000e869  mov     rax, [r14]
0x18000e86c  xor     edx, edx; unsigned int
0x18000e86e  mov     [rsi+80h], rax
0x18000e875  mov     rcx, rsi; this
0x18000e878  mov     r8d, [rsi+48h]
0x18000e87c  sub     r8d, ebx; unsigned int
0x18000e87f  call    ?InitializeLogEntries@CLogFile@@AEAAXKK@Z; CLogFile::InitializeLogEntries(ulong,ulong)
0x18000e884  mov     edx, ebx; int
0x18000e886  mov     rcx, rsi; this
0x18000e889  call    ?SetShutdown@CLogFile@@QEAAXH@Z; CLogFile::SetShutdown(int)
0x18000e88e  mov     rcx, rsi; this
0x18000e891  add     rsp, 28h
0x18000e895  pop     r14
0x18000e897  pop     rdi
0x18000e898  pop     rsi
0x18000e899  pop     rbx
0x18000e89a  jmp     ?CloseLog@CLogFile@@AEAAXXZ; CLogFile::CloseLog(void)
```
