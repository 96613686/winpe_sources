# NMP_FlushPipe(NMP_PIPE_INSTANCE *,NMP_ADDRESS *)

- ea: `0x18006530c`
- end: `0x18006540f`
- name: `?NMP_FlushPipe@@YAJPEAVNMP_PIPE_INSTANCE@@PEAUNMP_ADDRESS@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(struct NMP_PIPE_INSTANCE *, struct NMP_ADDRESS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18006403c`

## callees

- `0x18006530c`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x1800653b2`
- `ntdll!NtFsControlFile` at `0x1800653b2`
- `ntdll!RtlNtStatusToDosError` at `0x180065401`
- `ntdll!RtlNtStatusToDosError` at `0x180065401`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006536b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006536b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800653f3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800653f3`

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
0x18006530c  mov     [rsp+arg_0], rbx
0x180065311  mov     [rsp+arg_8], rsi
0x180065316  push    rdi
0x180065317  sub     rsp, 50h
0x18006531b  lea     rsi, [rcx+8]
0x18006531f  mov     qword ptr [rcx+10h], 0
0x180065327  mov     qword ptr [rsi], 103h
0x18006532e  mov     rbx, rdx
0x180065331  mov     rdi, rcx
0x180065334  mov     qword ptr [rcx+18h], 0
0x18006533c  mov     qword ptr [rcx+20h], 0
0x180065344  mov     r8d, 1
0x18006534a  lock xadd [rdx+124h], r8d
0x180065353  mov     eax, cs:?gNumberOfProcessors@@3IA; uint gNumberOfProcessors
0x180065359  inc     r8d
0x18006535c  shl     eax, 0Ah
0x18006535f  cmp     r8d, eax
0x180065362  ja      short loc_1800653D7
0x180065364  mov     rcx, [rcx+30h]
0x180065368  mov     rcx, [rcx]; pio
0x18006536b  call    cs:__imp_StartThreadpoolIo
0x180065372  nop     dword ptr [rax+rax+00h]
0x180065377  mov     rcx, [rdi+38h]; FileHandle
0x18006537b  mov     r9, rsi; ApcContext
0x18006537e  mov     [rsp+58h+OutputBufferLength], 0; OutputBufferLength
0x180065386  xor     r8d, r8d; ApcRoutine
0x180065389  mov     [rsp+58h+OutputBuffer], 0; OutputBuffer
0x180065392  xor     edx, edx; Event
0x180065394  mov     [rsp+58h+InputBufferLength], 0; InputBufferLength
0x18006539c  mov     [rsp+58h+InputBuffer], 0; InputBuffer
0x1800653a5  mov     [rsp+58h+FsControlCode], 118040h; FsControlCode
0x1800653ad  mov     [rsp+58h+IoStatusBlock], rsi; IoStatusBlock
0x1800653b2  call    cs:__imp_NtFsControlFile
0x1800653b9  nop     dword ptr [rax+rax+00h]
0x1800653be  mov     esi, eax
0x1800653c0  test    eax, eax
0x1800653c2  js      short loc_1800653E5
0x1800653c4  xor     eax, eax
0x1800653c6  mov     rbx, [rsp+58h+arg_0]
0x1800653cb  mov     rsi, [rsp+58h+arg_8]
0x1800653d0  add     rsp, 50h
0x1800653d4  pop     rdi
0x1800653d5  retn
0x1800653d7  lock dec dword ptr [rdx+124h]
0x1800653de  mov     eax, 6BBh
0x1800653e3  jmp     short loc_1800653C6
0x1800653e5  lock dec dword ptr [rbx+124h]
0x1800653ec  mov     rcx, [rdi+30h]
0x1800653f0  mov     rcx, [rcx]; pio
0x1800653f3  call    cs:__imp_CancelThreadpoolIo
0x1800653fa  nop     dword ptr [rax+rax+00h]
0x1800653ff  mov     ecx, esi; Status
0x180065401  call    cs:__imp_RtlNtStatusToDosError
0x180065408  nop     dword ptr [rax+rax+00h]
0x18006540d  jmp     short loc_1800653C6
```
