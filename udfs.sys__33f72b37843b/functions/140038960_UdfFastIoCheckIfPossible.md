# UdfFastIoCheckIfPossible

- ea: `0x140038960`
- end: `0x140038a62`
- name: `UdfFastIoCheckIfPossible`
- size: `258`
- prototype: `__int64 __usercall@<rax>(PVOID FileObject@<rcx>, PLARGE_INTEGER StartingByte@<rdx>, ULONG Key, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140038960`
- `0x140054460`

## import_xrefs

- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x1400389df`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x1400389df`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400389b9`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038a25`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400389b9`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038a25`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x140038a4b`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x140038a4b`

## pseudocode

```c
bool __fastcall UdfFastIoCheckIfPossible(
        struct _FILE_OBJECT *FileObject,
        PLARGE_INTEGER StartingByte,
        __int64 a3,
        __int64 a4,
        ULONG Key,
        char a6)
{
  union _LARGE_INTEGER v8; // r11
  FILE_LOCK *v9; // rbx
  PEPROCESS ProcessId; // rax
  FILE_LOCK *v12; // rbx
  PEPROCESS CurrentProcess; // rax
  __int64 v14; // [rsp+30h] [rbp-18h] BYREF
  union _LARGE_INTEGER Length; // [rsp+38h] [rbp-10h] BYREF

  v14 = 0;
  if ( (unsigned int)UdfDecodeFileObject(FileObject, &v14, &Length) != 4 )
    return 0;
  Length = v8;
  if ( a6 )
  {
    if ( *(_QWORD *)(v14 + 504) )
    {
      v9 = *(FILE_LOCK **)(v14 + 504);
      ProcessId = IoGetCurrentProcess();
      if ( !FsRtlFastCheckLockForRead(v9, StartingByte, &Length, Key, FileObject, ProcessId) )
        return 0;
    }
  }
  else
  {
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 136) + 8LL) + 48LL) & 0x90) != 0 )
      return 0;
    if ( *(_QWORD *)(v14 + 504) )
    {
      v12 = *(FILE_LOCK **)(v14 + 504);
      CurrentProcess = IoGetCurrentProcess();
      return FsRtlFastCheckLockForWrite(v12, StartingByte, &Length, Key, FileObject, CurrentProcess) != 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140038960  mov     rax, rsp
0x140038963  mov     [rax+8], rbx
0x140038967  mov     [rax+10h], rsi
0x14003896b  push    rdi
0x14003896c  sub     rsp, 40h
0x140038970  mov     r11d, r8d
0x140038973  mov     rsi, rdx
0x140038976  lea     r8, [rax-10h]
0x14003897a  mov     qword ptr [rax-18h], 0
0x140038982  lea     rdx, [rax-18h]
0x140038986  mov     rdi, rcx
0x140038989  call    UdfDecodeFileObject
0x14003898e  cmp     eax, 4
0x140038991  jnz     short loc_1400389EF
0x140038993  cmp     [rsp+48h+arg_28], 0
0x140038998  mov     rbx, [rsp+48h+var_18]
0x14003899d  mov     qword ptr [rsp+48h+Length], r11
0x1400389a2  jz      short loc_140038A02
0x1400389a4  cmp     qword ptr [rbx+1F8h], 0
0x1400389ac  jz      loc_140038A5E
0x1400389b2  mov     rbx, [rbx+1F8h]
0x1400389b9  call    cs:__imp_IoGetCurrentProcess
0x1400389c0  nop     dword ptr [rax+rax+00h]
0x1400389c5  mov     r9d, [rsp+48h+Key]; Key
0x1400389ca  lea     r8, [rsp+48h+Length]; Length
0x1400389cf  mov     [rsp+48h+ProcessId], rax; ProcessId
0x1400389d4  mov     rdx, rsi; StartingByte
0x1400389d7  mov     rcx, rbx; FileLock
0x1400389da  mov     [rsp+48h+FileObject], rdi; FileObject
0x1400389df  call    cs:__imp_FsRtlFastCheckLockForRead
0x1400389e6  nop     dword ptr [rax+rax+00h]
0x1400389eb  test    al, al
0x1400389ed  jnz     short loc_140038A5E
0x1400389ef  xor     al, al
0x1400389f1  mov     rbx, [rsp+48h+arg_0]
0x1400389f6  mov     rsi, [rsp+48h+arg_8]
0x1400389fb  add     rsp, 40h
0x1400389ff  pop     rdi
0x140038a00  retn
0x140038a02  mov     rax, [rbx+88h]
0x140038a09  mov     rcx, [rax+8]
0x140038a0d  mov     eax, [rcx+30h]
0x140038a10  test    al, 90h
0x140038a12  jnz     short loc_1400389EF
0x140038a14  cmp     qword ptr [rbx+1F8h], 0
0x140038a1c  jz      short loc_140038A5E
0x140038a1e  mov     rbx, [rbx+1F8h]
0x140038a25  call    cs:__imp_IoGetCurrentProcess
0x140038a2c  nop     dword ptr [rax+rax+00h]
0x140038a31  mov     r9d, [rsp+48h+Key]; Key
0x140038a36  lea     r8, [rsp+48h+Length]; Length
0x140038a3b  mov     [rsp+48h+ProcessId], rax; ProcessId
0x140038a40  mov     rdx, rsi; StartingByte
0x140038a43  mov     rcx, rbx; FileLock
0x140038a46  mov     [rsp+48h+FileObject], rdi; FileObject
0x140038a4b  call    cs:__imp_FsRtlFastCheckLockForWrite
0x140038a52  nop     dword ptr [rax+rax+00h]
0x140038a57  test    al, al
0x140038a59  setnz   al
0x140038a5c  jmp     short loc_1400389F1
0x140038a5e  mov     al, 1
0x140038a60  jmp     short loc_1400389F1
```
