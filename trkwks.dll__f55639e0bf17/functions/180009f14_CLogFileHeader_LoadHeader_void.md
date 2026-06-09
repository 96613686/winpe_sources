# CLogFileHeader::LoadHeader(void *)

- ea: `0x180009f14`
- end: `0x180009ff0`
- name: `?LoadHeader@CLogFileHeader@@AEAAXPEAX@Z`
- size: `220`
- prototype: `void __fastcall(CLogFileHeader *this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180009720`

## callees

- `0x1800028f0`
- `0x180009f14`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180009fa6`
- `ntdll!NtWaitForSingleObject` at `0x180009fa6`
- `ntdll!NtReadFile` at `0x180009f68`
- `ntdll!NtReadFile` at `0x180009f68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009fc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009fe9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009fc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009fe9`

## pseudocode

```c
void __fastcall CLogFileHeader::LoadHeader(CLogFileHeader *this, void *a2)
{
  NTSTATUS Status; // eax
  void *v5; // [rsp+28h] [rbp-40h]
  ULONG Length; // [rsp+30h] [rbp-38h]
  struct _IO_STATUS_BLOCK v7; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER v8; // [rsp+70h] [rbp+8h] BYREF

  Length = *((_DWORD *)this + 8);
  v5 = (void *)*((_QWORD *)this + 2);
  v8.QuadPart = 0;
  v7 = 0;
  Status = NtReadFile(a2, 0, 0, 0, &v7, v5, Length, &v8, 0);
  if ( Status == 259 )
  {
    Status = NtWaitForSingleObject(a2, 0, 0);
    if ( Status < 0 )
    {
LABEL_8:
      if ( Status == -1073741202 )
      {
        RaiseException(0xC000026E, 0, 0, 0);
        __debugbreak();
      }
LABEL_11:
      RaiseException(0x8DEAD001, 0, 0, 0);
      JUMPOUT(0x180009FEFLL);
    }
    Status = v7.Status;
  }
  if ( Status < 0 )
    goto LABEL_8;
  if ( g_ptrkwks )
    CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
  if ( *((_DWORD *)this + 8) != v7.Information )
    goto LABEL_11;
  *((_QWORD *)this + 1) = a2;
}

```

## disassembly

```asm
0x180009f14  mov     r11, rsp
0x180009f17  mov     [r11+10h], rbx
0x180009f1b  push    rdi
0x180009f1c  sub     rsp, 60h
0x180009f20  mov     qword ptr [r11-28h], 0
0x180009f28  lea     rax, [r11+8]
0x180009f2c  mov     [r11-30h], rax
0x180009f30  mov     rdi, rdx
0x180009f33  mov     eax, [rcx+20h]
0x180009f36  mov     rbx, rcx
0x180009f39  mov     [rsp+68h+Length], eax; Length
0x180009f3d  xorps   xmm0, xmm0
0x180009f40  mov     rax, [rcx+10h]
0x180009f44  xor     r9d, r9d; ApcContext
0x180009f47  mov     [r11-40h], rax
0x180009f4b  xor     r8d, r8d; ApcRoutine
0x180009f4e  lea     rax, [r11-18h]
0x180009f52  mov     qword ptr [r11+8], 0
0x180009f5a  xor     edx, edx; Event
0x180009f5c  mov     [r11-48h], rax
0x180009f60  mov     rcx, rdi; FileHandle
0x180009f63  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180009f68  call    cs:__imp_NtReadFile
0x180009f6e  cmp     eax, 103h
0x180009f73  jz      short loc_180009F9E
0x180009f75  test    eax, eax
0x180009f77  js      short loc_180009FB0
0x180009f79  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180009f80  test    rcx, rcx
0x180009f83  jnz     short loc_180009FD1
0x180009f85  mov     eax, [rbx+20h]
0x180009f88  cmp     rax, [rsp+68h+var_18.Information]
0x180009f8d  jnz     short loc_180009FDC
0x180009f8f  mov     [rbx+8], rdi
0x180009f93  mov     rbx, [rsp+68h+arg_8]
0x180009f98  add     rsp, 60h
0x180009f9c  pop     rdi
0x180009f9d  retn
0x180009f9e  xor     r8d, r8d; Timeout
0x180009fa1  xor     edx, edx; Alertable
0x180009fa3  mov     rcx, rdi; Handle
0x180009fa6  call    cs:__imp_NtWaitForSingleObject
0x180009fac  test    eax, eax
0x180009fae  jns     short loc_180009FCB
0x180009fb0  cmp     eax, 0C000026Eh
0x180009fb5  jnz     short loc_180009FDC
0x180009fb7  xor     r9d, r9d; lpArguments
0x180009fba  xor     r8d, r8d; nNumberOfArguments
0x180009fbd  xor     edx, edx; dwExceptionFlags
0x180009fbf  mov     ecx, 0C000026Eh; dwExceptionCode
0x180009fc4  call    cs:__imp_RaiseException
0x180009fca  int     3; Trap to Debugger
0x180009fcb  mov     eax, dword ptr [rsp+68h+var_18]
0x180009fcf  jmp     short loc_180009F75
0x180009fd1  add     rcx, 30h ; '0'; this
0x180009fd5  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x180009fda  jmp     short loc_180009F85
0x180009fdc  xor     r9d, r9d; lpArguments
0x180009fdf  xor     r8d, r8d; nNumberOfArguments
0x180009fe2  xor     edx, edx; dwExceptionFlags
0x180009fe4  mov     ecx, 8DEAD001h; dwExceptionCode
0x180009fe9  call    cs:__imp_RaiseException
```
