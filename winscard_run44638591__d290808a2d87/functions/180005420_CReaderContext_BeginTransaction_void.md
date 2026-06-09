# CReaderContext::BeginTransaction(void)

- ea: `0x180005420`
- end: `0x18000549e`
- name: `?BeginTransaction@CReaderContext@@QEAAXXZ`
- size: `126`
- prototype: `void(CReaderContext *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180010f50`

## callees

- `0x18000534c`
- `0x180005420`
- `0x180005970`
- `0x180005a90`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000544f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000544f`

## pseudocode

```c

```

## disassembly

```asm
0x180005420  mov     qword ptr [rsp+arg_10], rbx; int
0x180005425  mov     qword ptr [rsp+arg_18], rsi; int
0x18000542a  push    rdi; int
0x18000542b  sub     rsp, 20h
0x18000542f  mov     rdi, rcx
0x180005432  mov     rsi, [rcx+18h]
0x180005436  mov     qword ptr [rsp+28h+arg_8], 0
0x18000543f  mov     rcx, rsi; this
0x180005442  call    ?WaitForAvailable@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::WaitForAvailable(void)
0x180005447  mov     qword ptr [rsp+28h+arg_8], rsi; int
0x18000544c  mov     ebx, [rdi+20h]
0x18000544f  call    cs:__imp_GetCurrentProcessId
0x180005455  mov     rcx, [rdi+18h]
0x180005459  mov     r8d, ebx; int
0x18000545c  mov     edx, eax; int
0x18000545e  mov     rcx, [rcx+70h]; int
0x180005462  call    CalRpcBeginTransaction
0x180005467  test    eax, eax
0x180005469  jnz     short loc_180005488
0x18000546b  test    rsi, rsi
0x18000546e  jz      short loc_180005478
0x180005470  mov     rcx, rsi; this
0x180005473  call    ?ReleaseSubcontext@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::ReleaseSubcontext(void)
0x180005478  mov     rbx, qword ptr [rsp+28h+arg_10]
0x18000547d  mov     rsi, qword ptr [rsp+28h+arg_18]
0x180005482  add     rsp, 20h
0x180005486  pop     rdi
0x180005487  retn
0x180005488  mov     [rsp+28h+pExceptionObject], eax
0x18000548c  lea     rdx, _TI1K; pThrowInfo
0x180005493  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180005498  call    _CxxThrowException_0
```
