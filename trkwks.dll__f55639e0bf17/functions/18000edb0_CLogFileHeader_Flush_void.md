# CLogFileHeader::Flush(void)

- ea: `0x18000edb0`
- end: `0x18000ee94`
- name: `?Flush@CLogFileHeader@@QEAAXXZ`
- size: `228`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180002b50`
- `0x18000c3d4`
- `0x18000d790`
- `0x18000e784`
- `0x18000eac0`

## callees

- `0x1800028f0`
- `0x18000cfd0`
- `0x18000cff8`
- `0x18000edb0`

## import_xrefs

- `ntdll!NtWriteFile` at `0x18000ee1a`
- `ntdll!NtWriteFile` at `0x18000ee1a`
- `ntdll!NtWaitForSingleObject` at `0x18000ee30`
- `ntdll!NtWaitForSingleObject` at `0x18000ee30`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ee4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ee7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ee4c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ee7f`

## pseudocode

```c
void __fastcall CLogFileHeader::Flush(HANDLE *this)
{
  HANDLE v2; // rcx
  bool v3; // zf
  signed int Status; // eax
  PVOID Buffer; // [rsp+28h] [rbp-40h]
  ULONG Length; // [rsp+30h] [rbp-38h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp+8h] BYREF

  CLogFileHeader::RaiseIfNotOpen((CLogFileHeader *)this);
  v2 = this[1];
  if ( v2 )
  {
    v3 = (*(_BYTE *)this & 1) == 0;
    IoStatusBlock = 0;
    if ( !v3 )
    {
      Length = *((_DWORD *)this + 8);
      Buffer = this[2];
      ByteOffset.QuadPart = 0;
      Status = NtWriteFile(v2, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(this[1], 0, 0);
        if ( Status < 0 )
          goto LABEL_7;
        Status = IoStatusBlock.Status;
      }
      if ( Status < 0 )
      {
LABEL_7:
        RaiseException(Status, 0, 0, 0);
        __debugbreak();
      }
      if ( g_ptrkwks )
        CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
      if ( *((_DWORD *)this + 8) != IoStatusBlock.Information )
      {
        RaiseException(0x8DEAD001, 0, 0, 0);
        __debugbreak();
      }
      CLogFileHeader::SetDirty((CLogFileHeader *)this, 0);
    }
  }
}

```

## disassembly

```asm
0x18000edb0  push    rbx
0x18000edb2  sub     rsp, 60h
0x18000edb6  mov     rbx, rcx
0x18000edb9  call    ?RaiseIfNotOpen@CLogFileHeader@@AEBAXXZ; CLogFileHeader::RaiseIfNotOpen(void)
0x18000edbe  mov     rcx, [rbx+8]; FileHandle
0x18000edc2  test    rcx, rcx
0x18000edc5  jz      loc_18000EE8E
0x18000edcb  test    byte ptr [rbx], 1
0x18000edce  xorps   xmm0, xmm0
0x18000edd1  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x18000edd6  jz      loc_18000EE8E
0x18000eddc  mov     [rsp+68h+Key], 0; Key
0x18000ede5  lea     rax, [rsp+68h+arg_0]
0x18000edea  mov     [rsp+68h+ByteOffset], rax; ByteOffset
0x18000edef  xor     r9d, r9d; ApcContext
0x18000edf2  mov     eax, [rbx+20h]
0x18000edf5  xor     r8d, r8d; ApcRoutine
0x18000edf8  mov     [rsp+68h+Length], eax; Length
0x18000edfc  xor     edx, edx; Event
0x18000edfe  mov     rax, [rbx+10h]
0x18000ee02  mov     [rsp+68h+Buffer], rax; Buffer
0x18000ee07  lea     rax, [rsp+68h+var_18]
0x18000ee0c  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x18000ee11  mov     qword ptr [rsp+68h+arg_0], 0
0x18000ee1a  call    cs:__imp_NtWriteFile
0x18000ee20  cmp     eax, 103h
0x18000ee25  jnz     short loc_18000EE3E
0x18000ee27  mov     rcx, [rbx+8]; Handle
0x18000ee2b  xor     r8d, r8d; Timeout
0x18000ee2e  xor     edx, edx; Alertable
0x18000ee30  call    cs:__imp_NtWaitForSingleObject
0x18000ee36  test    eax, eax
0x18000ee38  js      short loc_18000EE42
0x18000ee3a  mov     eax, dword ptr [rsp+68h+var_18]
0x18000ee3e  test    eax, eax
0x18000ee40  jns     short loc_18000EE53
0x18000ee42  xor     r9d, r9d; lpArguments
0x18000ee45  xor     r8d, r8d; nNumberOfArguments
0x18000ee48  xor     edx, edx; dwExceptionFlags
0x18000ee4a  mov     ecx, eax; dwExceptionCode
0x18000ee4c  call    cs:__imp_RaiseException
0x18000ee52  int     3; Trap to Debugger
0x18000ee53  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x18000ee5a  test    rcx, rcx
0x18000ee5d  jz      short loc_18000EE68
0x18000ee5f  add     rcx, 30h ; '0'; this
0x18000ee63  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x18000ee68  mov     eax, [rbx+20h]
0x18000ee6b  xor     edx, edx; int
0x18000ee6d  cmp     rax, [rsp+68h+var_18.Information]
0x18000ee72  jz      short loc_18000EE86
0x18000ee74  xor     r9d, r9d; lpArguments
0x18000ee77  xor     r8d, r8d; nNumberOfArguments
0x18000ee7a  mov     ecx, 8DEAD001h; dwExceptionCode
0x18000ee7f  call    cs:__imp_RaiseException
0x18000ee85  int     3; Trap to Debugger
0x18000ee86  mov     rcx, rbx; this
0x18000ee89  call    ?SetDirty@CLogFileHeader@@QEAAXH@Z; CLogFileHeader::SetDirty(int)
0x18000ee8e  add     rsp, 60h
0x18000ee92  pop     rbx
0x18000ee93  retn
```
