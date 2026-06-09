# WapHttp3StartWaitForDisconnect

- ea: `0x18007eb88`
- end: `0x18007ec8f`
- name: `WapHttp3StartWaitForDisconnect`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180080510`

## callees

- `0x180071500`
- `0x18007a9e0`
- `0x18007eb88`
- `0x18008059c`
- `0x1800971ec`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007ec3e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007ec3e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007ec06`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007ec06`

## pseudocode

```c
__int64 __fastcall WapHttp3StartWaitForDisconnect(_QWORD *a1)
{
  __int64 IoContext; // rax
  unsigned int v3; // ebx
  __int64 v4; // rcx

  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_q(1050, 102, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, a1);
  IoContext = WapHttpApiAllocateIoContext(
                (_DWORD)a1,
                (_DWORD)a1,
                0,
                4,
                (__int64)WapHttp3WaitForDisconnectCompletionRoutine,
                0,
                0);
  if ( IoContext )
  {
    *(_BYTE *)(IoContext + 132) = 1;
    v4 = a1[11];
    a1[226] = IoContext;
    StartThreadpoolIo(*(PTP_IO *)(v4 + 8));
    v3 = WaHttpApiConnectionWaitForDisconnect(*(_QWORD *)a1[11], a1[10], a1[226] + 32LL);
    if ( v3 == 997 )
    {
      v3 = 0;
    }
    else
    {
      CancelThreadpoolIo(*(PTP_IO *)(a1[11] + 8LL));
      WapHttp3WaitForDisconnectCompletionRoutine(a1[226], v3, 0);
    }
  }
  else
  {
    v3 = 8;
  }
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 103, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18007eb88  mov     [rsp+arg_0], rbx
0x18007eb8d  push    rdi
0x18007eb8e  sub     rsp, 40h
0x18007eb92  mov     rdi, rcx
0x18007eb95  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007eb9c  jz      short loc_18007EBB7
0x18007eb9e  mov     edx, 66h ; 'f'
0x18007eba3  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007ebaa  mov     ecx, 41Ah
0x18007ebaf  mov     r9, rdi
0x18007ebb2  call    WPP_SF_q
0x18007ebb7  mov     [rsp+48h+var_18], 0
0x18007ebc0  lea     rax, WapHttp3WaitForDisconnectCompletionRoutine
0x18007ebc7  mov     [rsp+48h+var_20], 0
0x18007ebd0  mov     r9d, 4
0x18007ebd6  xor     r8d, r8d
0x18007ebd9  mov     [rsp+48h+var_28], rax
0x18007ebde  mov     rdx, rdi
0x18007ebe1  call    WapHttpApiAllocateIoContext
0x18007ebe6  test    rax, rax
0x18007ebe9  jnz     short loc_18007EBF0
0x18007ebeb  lea     ebx, [rax+8]
0x18007ebee  jmp     short loc_18007EC5F
0x18007ebf0  mov     byte ptr [rax+84h], 1
0x18007ebf7  mov     rcx, [rdi+58h]
0x18007ebfb  mov     [rdi+710h], rax
0x18007ec02  mov     rcx, [rcx+8]; pio
0x18007ec06  call    cs:__imp_StartThreadpoolIo
0x18007ec0d  nop     dword ptr [rax+rax+00h]
0x18007ec12  mov     rcx, [rdi+58h]
0x18007ec16  mov     r8, [rdi+710h]
0x18007ec1d  mov     rdx, [rdi+50h]
0x18007ec21  add     r8, 20h ; ' '
0x18007ec25  mov     rcx, [rcx]
0x18007ec28  call    WaHttpApiConnectionWaitForDisconnect
0x18007ec2d  mov     ebx, eax
0x18007ec2f  cmp     eax, 3E5h
0x18007ec34  jz      short loc_18007EC5D
0x18007ec36  mov     rcx, [rdi+58h]
0x18007ec3a  mov     rcx, [rcx+8]; pio
0x18007ec3e  call    cs:__imp_CancelThreadpoolIo
0x18007ec45  nop     dword ptr [rax+rax+00h]
0x18007ec4a  mov     rcx, [rdi+710h]
0x18007ec51  xor     r8d, r8d
0x18007ec54  mov     edx, ebx
0x18007ec56  call    WapHttp3WaitForDisconnectCompletionRoutine
0x18007ec5b  jmp     short loc_18007EC5F
0x18007ec5d  xor     ebx, ebx
0x18007ec5f  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007ec66  jz      short loc_18007EC81
0x18007ec68  mov     edx, 67h ; 'g'
0x18007ec6d  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007ec74  mov     ecx, 41Ah
0x18007ec79  mov     r9d, ebx
0x18007ec7c  call    WPP_SF_d
0x18007ec81  mov     eax, ebx
0x18007ec83  mov     rbx, [rsp+48h+arg_0]
0x18007ec88  add     rsp, 40h
0x18007ec8c  pop     rdi
0x18007ec8d  retn
```
