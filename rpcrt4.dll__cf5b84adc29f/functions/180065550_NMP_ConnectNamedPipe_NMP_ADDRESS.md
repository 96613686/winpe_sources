# NMP_ConnectNamedPipe(NMP_ADDRESS *)

- ea: `0x180065550`
- end: `0x180065601`
- name: `?NMP_ConnectNamedPipe@@YAJPEAUNMP_ADDRESS@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(struct NMP_ADDRESS *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180064f20`

## callees

- `0x180063d88`
- `0x180065550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065599`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180065589`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180065589`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006556b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006556b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800655ce`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800655ce`

## pseudocode

```c
__int64 __fastcall NMP_ConnectNamedPipe(struct NMP_ADDRESS *a1)
{
  DWORD LastError; // ebx

  StartThreadpoolIo(**(PTP_IO **)(*((_QWORD *)a1 + 25) + 48LL));
  if ( ConnectNamedPipe(*(HANDLE *)(*((_QWORD *)a1 + 25) + 56LL), (LPOVERLAPPED)((char *)a1 + 136)) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      CancelThreadpoolIo(**(PTP_IO **)(*((_QWORD *)a1 + 25) + 48LL));
      if ( LastError == 232 )
      {
        NMP_FreePipeInstance(a1, *((struct NMP_PIPE_INSTANCE **)a1 + 25), 0);
        *((_QWORD *)a1 + 25) = 0;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180065550  mov     [rsp+arg_0], rbx
0x180065555  push    rdi
0x180065556  sub     rsp, 20h
0x18006555a  mov     rax, [rcx+0C8h]
0x180065561  mov     rdi, rcx
0x180065564  mov     rcx, [rax+30h]
0x180065568  mov     rcx, [rcx]; pio
0x18006556b  call    cs:__imp_StartThreadpoolIo
0x180065572  nop     dword ptr [rax+rax+00h]
0x180065577  mov     rcx, [rdi+0C8h]
0x18006557e  lea     rdx, [rdi+88h]; lpOverlapped
0x180065585  mov     rcx, [rcx+38h]; hNamedPipe
0x180065589  call    cs:__imp_ConnectNamedPipe
0x180065590  nop     dword ptr [rax+rax+00h]
0x180065595  test    eax, eax
0x180065597  jnz     short loc_1800655BC
0x180065599  call    cs:__imp_GetLastError
0x1800655a0  nop     dword ptr [rax+rax+00h]
0x1800655a5  mov     ebx, eax
0x1800655a7  cmp     eax, 3E5h
0x1800655ac  jnz     short loc_1800655C0
0x1800655ae  mov     eax, ebx
0x1800655b0  mov     rbx, [rsp+28h+arg_0]
0x1800655b5  add     rsp, 20h
0x1800655b9  pop     rdi
0x1800655ba  retn
0x1800655bc  xor     ebx, ebx
0x1800655be  jmp     short loc_1800655AE
0x1800655c0  mov     rcx, [rdi+0C8h]
0x1800655c7  mov     rcx, [rcx+30h]
0x1800655cb  mov     rcx, [rcx]; pio
0x1800655ce  call    cs:__imp_CancelThreadpoolIo
0x1800655d5  nop     dword ptr [rax+rax+00h]
0x1800655da  cmp     ebx, 0E8h
0x1800655e0  jnz     short loc_1800655AE
0x1800655e2  mov     rdx, [rdi+0C8h]; struct NMP_PIPE_INSTANCE *
0x1800655e9  xor     r8d, r8d; int
0x1800655ec  mov     rcx, rdi; struct NMP_ADDRESS *
0x1800655ef  call    ?NMP_FreePipeInstance@@YAXPEAUNMP_ADDRESS@@PEAVNMP_PIPE_INSTANCE@@H@Z; NMP_FreePipeInstance(NMP_ADDRESS *,NMP_PIPE_INSTANCE *,int)
0x1800655f4  mov     qword ptr [rdi+0C8h], 0
0x1800655ff  jmp     short loc_1800655AE
```
