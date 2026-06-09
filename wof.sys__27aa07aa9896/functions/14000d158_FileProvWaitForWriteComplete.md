# FileProvWaitForWriteComplete

- ea: `0x14000d158`
- end: `0x14000d247`
- name: `FileProvWaitForWriteComplete`
- size: `239`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003a6f8`
- `0x14003ae2c`

## callees

- `0x14000d158`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14000d1cd`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000d1cd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d192`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d192`
- `FLTMGR!FltWriteFile` at `0x14000d21f`
- `FLTMGR!FltWriteFile` at `0x14000d21f`

## pseudocode

```c
NTSTATUS __fastcall FileProvWaitForWriteComplete(__int64 a1, unsigned int a2, char a3)
{
  unsigned __int64 v4; // rdi
  NTSTATUS result; // eax
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF
  ULONG BytesWritten; // [rsp+70h] [rbp+18h] BYREF

  v4 = (unsigned __int64)a2 << 6;
  BytesWritten = 0;
  result = KeWaitForSingleObject((PVOID)(v4 + a1 + 120), Executive, 0, 0, 0);
  if ( a3 && *(_DWORD *)(v4 + a1 + 112) == -1073741740 )
  {
    do
    {
      Interval.QuadPart = -100000;
      KeDelayExecutionThread(0, 1u, &Interval);
      result = FltWriteFile(
                 *(PFLT_INSTANCE *)(a1 + 64),
                 *(PFILE_OBJECT *)(a1 + 72),
                 (PLARGE_INTEGER)(a1 + 144 + v4),
                 *(_DWORD *)(v4 + a1 + 152),
                 (PVOID)(*(_QWORD *)(v4 + a1 + 96) + *(unsigned int *)(v4 + a1 + 108)),
                 0xFu,
                 &BytesWritten,
                 0,
                 0);
    }
    while ( result == -1073741740 );
    *(_DWORD *)(v4 + a1 + 112) = result;
  }
  return result;
}

```

## disassembly

```asm
0x14000d158  mov     rax, rsp
0x14000d15b  mov     [rax+10h], rbx
0x14000d15f  mov     [rax+20h], rsi
0x14000d163  push    rdi
0x14000d164  sub     rsp, 50h
0x14000d168  mov     edi, edx
0x14000d16a  mov     rsi, rcx
0x14000d16d  add     rcx, 78h ; 'x'
0x14000d171  shl     rdi, 6
0x14000d175  mov     bl, r8b
0x14000d178  mov     dword ptr [rax+18h], 0
0x14000d17f  add     rcx, rdi; Object
0x14000d182  mov     qword ptr [rax-38h], 0
0x14000d18a  xor     r9d, r9d; Alertable
0x14000d18d  xor     r8d, r8d; WaitMode
0x14000d190  xor     edx, edx; WaitReason
0x14000d192  call    cs:__imp_KeWaitForSingleObject
0x14000d199  nop     dword ptr [rax+rax+00h]
0x14000d19e  test    bl, bl
0x14000d1a0  jz      loc_14000D236
0x14000d1a6  cmp     dword ptr [rdi+rsi+70h], 0C0000054h
0x14000d1ae  jnz     loc_14000D236
0x14000d1b4  lea     rbx, [rsi+90h]
0x14000d1bb  lea     r8, [rsp+58h+Interval]; Interval
0x14000d1c0  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFE7960h
0x14000d1c9  mov     dl, 1; Alertable
0x14000d1cb  xor     ecx, ecx; WaitMode
0x14000d1cd  call    cs:__imp_KeDelayExecutionThread
0x14000d1d4  nop     dword ptr [rax+rax+00h]
0x14000d1d9  mov     eax, [rdi+rsi+6Ch]
0x14000d1dd  lea     rcx, [rsp+58h+arg_10]
0x14000d1e2  add     rax, [rdi+rsi+60h]
0x14000d1e7  lea     r8, [rbx+rdi]; ByteOffset
0x14000d1eb  mov     r9d, [rdi+rsi+98h]; Length
0x14000d1f3  mov     rdx, [rsi+48h]; FileObject
0x14000d1f7  mov     [rsp+58h+CallbackContext], 0; CallbackContext
0x14000d200  mov     [rsp+58h+CallbackRoutine], 0; CallbackRoutine
0x14000d209  mov     [rsp+58h+BytesWritten], rcx; BytesWritten
0x14000d20e  mov     rcx, [rsi+40h]; InitiatingInstance
0x14000d212  mov     [rsp+58h+Flags], 0Fh; Flags
0x14000d21a  mov     [rsp+58h+Buffer], rax; Buffer
0x14000d21f  call    cs:__imp_FltWriteFile
0x14000d226  nop     dword ptr [rax+rax+00h]
0x14000d22b  cmp     eax, 0C0000054h
0x14000d230  jz      short loc_14000D1BB
0x14000d232  mov     [rdi+rsi+70h], eax
0x14000d236  mov     rbx, [rsp+58h+arg_8]
0x14000d23b  mov     rsi, [rsp+58h+arg_18]
0x14000d240  add     rsp, 50h
0x14000d244  pop     rdi
0x14000d245  retn
```
