# NMP_FlushPipe(NMP_PIPE_INSTANCE *,NMP_ADDRESS *)

- ea: `0x180060eb8`
- end: `0x180060fa2`
- name: `?NMP_FlushPipe@@YAJPEAVNMP_PIPE_INSTANCE@@PEAUNMP_ADDRESS@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct NMP_PIPE_INSTANCE *, struct NMP_ADDRESS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18006008c`

## callees

- `0x180060eb8`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x180060f58`
- `ntdll!NtFsControlFile` at `0x180060f58`
- `ntdll!RtlNtStatusToDosError` at `0x180060f9a`
- `ntdll!RtlNtStatusToDosError` at `0x180060f9a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180060f17`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180060f17`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180060f92`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180060f92`

## pseudocode

```c
ULONG __fastcall NMP_FlushPipe(struct NMP_PIPE_INSTANCE *a1, struct NMP_ADDRESS *a2)
{
  struct _IO_STATUS_BLOCK *IoStatusBlock; // rsi
  unsigned int v5; // r8d
  int v6; // esi

  IoStatusBlock = (struct _IO_STATUS_BLOCK *)((char *)a1 + 8);
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 1) = 259;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 4) = 0;
  v5 = _InterlockedIncrement((volatile signed __int32 *)a2 + 73);
  if ( v5 > gNumberOfProcessors << 10 )
  {
    _InterlockedDecrement((volatile signed __int32 *)a2 + 73);
    return 1723;
  }
  else
  {
    StartThreadpoolIo(**((PTP_IO **)a1 + 6));
    v6 = NtFsControlFile(*((HANDLE *)a1 + 7), 0, 0, IoStatusBlock, IoStatusBlock, 0x118040u, 0, 0, 0, 0);
    if ( v6 < 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)a2 + 73);
      CancelThreadpoolIo(**((PTP_IO **)a1 + 6));
      return RtlNtStatusToDosError(v6);
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180060eb8  mov     [rsp+arg_0], rbx
0x180060ebd  mov     [rsp+arg_8], rsi
0x180060ec2  push    rdi
0x180060ec3  sub     rsp, 50h
0x180060ec7  lea     rsi, [rcx+8]
0x180060ecb  mov     qword ptr [rcx+10h], 0
0x180060ed3  mov     qword ptr [rsi], 103h
0x180060eda  mov     rbx, rdx
0x180060edd  mov     rdi, rcx
0x180060ee0  mov     qword ptr [rcx+18h], 0
0x180060ee8  mov     qword ptr [rcx+20h], 0
0x180060ef0  mov     r8d, 1
0x180060ef6  lock xadd [rdx+124h], r8d
0x180060eff  mov     eax, cs:?gNumberOfProcessors@@3IA; uint gNumberOfProcessors
0x180060f05  inc     r8d
0x180060f08  shl     eax, 0Ah
0x180060f0b  cmp     r8d, eax
0x180060f0e  ja      short loc_180060F76
0x180060f10  mov     rcx, [rcx+30h]
0x180060f14  mov     rcx, [rcx]; pio
0x180060f17  call    cs:__imp_StartThreadpoolIo
0x180060f1d  mov     rcx, [rdi+38h]; FileHandle
0x180060f21  mov     r9, rsi; ApcContext
0x180060f24  mov     [rsp+58h+OutputBufferLength], 0; OutputBufferLength
0x180060f2c  xor     r8d, r8d; ApcRoutine
0x180060f2f  mov     [rsp+58h+OutputBuffer], 0; OutputBuffer
0x180060f38  xor     edx, edx; Event
0x180060f3a  mov     [rsp+58h+InputBufferLength], 0; InputBufferLength
0x180060f42  mov     [rsp+58h+InputBuffer], 0; InputBuffer
0x180060f4b  mov     [rsp+58h+FsControlCode], 118040h; FsControlCode
0x180060f53  mov     [rsp+58h+IoStatusBlock], rsi; IoStatusBlock
0x180060f58  call    cs:__imp_NtFsControlFile
0x180060f5e  mov     esi, eax
0x180060f60  test    eax, eax
0x180060f62  js      short loc_180060F84
0x180060f64  xor     eax, eax
0x180060f66  mov     rbx, [rsp+58h+arg_0]
0x180060f6b  mov     rsi, [rsp+58h+arg_8]
0x180060f70  add     rsp, 50h
0x180060f74  pop     rdi
0x180060f75  retn
0x180060f76  lock dec dword ptr [rdx+124h]
0x180060f7d  mov     eax, 6BBh
0x180060f82  jmp     short loc_180060F66
0x180060f84  lock dec dword ptr [rbx+124h]
0x180060f8b  mov     rcx, [rdi+30h]
0x180060f8f  mov     rcx, [rcx]; pio
0x180060f92  call    cs:__imp_CancelThreadpoolIo
0x180060f98  mov     ecx, esi; Status
0x180060f9a  call    cs:__imp_RtlNtStatusToDosError
0x180060fa0  jmp     short loc_180060F66
```
