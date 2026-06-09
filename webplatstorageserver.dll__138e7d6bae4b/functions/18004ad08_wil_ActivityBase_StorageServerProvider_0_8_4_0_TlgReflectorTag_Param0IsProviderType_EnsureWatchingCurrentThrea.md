# wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x18004ad08`
- end: `0x18004add6`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `206`
- prototype: ``
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007bcc`
- `0x180028070`
- `0x1800294c4`
- `0x1800295b4`
- `0x18002b3a8`
- `0x18002bbf4`
- `0x18002ca90`
- `0x18002d1ac`
- `0x18002d5ec`
- `0x18002db1c`
- `0x18002e038`
- `0x18002e9b4`
- `0x18004d770`
- `0x1800520ec`
- `0x180055cac`
- `0x18005c768`
- `0x18005d31c`
- `0x18005fe2c`
- `0x18006f82c`
- `0x180071064`
- `0x18007708c`
- `0x180077510`
- `0x180078918`
- `0x18007c56c`
- `0x18007dac4`
- `0x18007fa9c`
- `0x1800a7dc0`
- `0x1800a7e74`
- `0x1800a7f98`
- `0x1800a804c`
- `0x1800a813c`
- `0x1800a8214`
- `0x1800a82f8`
- `0x1800a83d4`
- `0x1800a84b8`
- `0x1800a8594`
- `0x1800a86a4`
- `0x1800a877c`
- `0x1800a8858`

## callees

- `0x18004ad08`
- `0x18004aff4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ad2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ad79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ad2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ad79`

## pseudocode

```c
void __fastcall wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  DWORD CurrentThreadId; // ebp
  unsigned __int64 v4; // r8
  unsigned __int64 v5; // rsi
  __int64 i; // rcx
  _QWORD *v7; // rcx
  char *v8; // rax
  signed __int64 v9; // rdx
  signed __int64 v10; // rax

  if ( !*(_DWORD *)(a1 + 312) )
  {
    v1 = wil::details::g_pThreadFailureCallbacks;
    v2 = a1 + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
      for ( i = *(_QWORD *)(v1 + 8 * v5); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v7 = (_QWORD *)(i + 16);
          goto LABEL_7;
        }
      }
      v8 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v4);
      v9 = (signed __int64)v8;
      if ( v8 )
      {
        *(_DWORD *)v8 = CurrentThreadId;
        v7 = v8 + 16;
        *((_DWORD *)v8 + 1) = 0;
        *((_QWORD *)v8 + 1) = 0;
        *((_QWORD *)v8 + 2) = 0;
        do
        {
          v10 = *(_QWORD *)(v1 + 8 * v5);
          *(_QWORD *)(v9 + 8) = v10;
        }
        while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v1 + 8 * v5), v9, v10) );
      }
      else
      {
        v7 = 0;
      }
LABEL_7:
      *(_QWORD *)v2 = v7;
      if ( v7 )
      {
        *(_QWORD *)(v2 + 16) = *v7;
        *v7 = v2;
        *(_DWORD *)(v2 + 24) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v2 = 0;
    }
  }
}

```

## disassembly

```asm
0x18004ad08  push    rbx
0x18004ad0a  push    rbp
0x18004ad0b  push    rsi
0x18004ad0c  push    rdi
0x18004ad0d  sub     rsp, 28h
0x18004ad11  cmp     dword ptr [rcx+138h], 0
0x18004ad18  jnz     short loc_18004AD82
0x18004ad1a  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004ad21  lea     rbx, [rcx+120h]
0x18004ad28  test    rdi, rdi
0x18004ad2b  jz      short loc_18004AD91
0x18004ad2d  call    cs:__imp_GetCurrentThreadId
0x18004ad33  mov     esi, eax
0x18004ad35  mov     ebp, eax
0x18004ad37  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004ad41  shr     rsi, 2
0x18004ad45  mul     rsi
0x18004ad48  shr     rdx, 3
0x18004ad4c  lea     rcx, [rdx+rdx*4]
0x18004ad50  add     rcx, rcx
0x18004ad53  sub     rsi, rcx
0x18004ad56  mov     rcx, [rdi+rsi*8]
0x18004ad5a  test    rcx, rcx
0x18004ad5d  jz      short loc_18004AD9A
0x18004ad5f  cmp     [rcx], ebp
0x18004ad61  jnz     short loc_18004AD8B
0x18004ad63  add     rcx, 10h
0x18004ad67  mov     [rbx], rcx
0x18004ad6a  test    rcx, rcx
0x18004ad6d  jz      short loc_18004AD82
0x18004ad6f  mov     rax, [rcx]
0x18004ad72  mov     [rbx+10h], rax
0x18004ad76  mov     [rcx], rbx
0x18004ad79  call    cs:__imp_GetCurrentThreadId
0x18004ad7f  mov     [rbx+18h], eax
0x18004ad82  add     rsp, 28h
0x18004ad86  pop     rdi
0x18004ad87  pop     rsi
0x18004ad88  pop     rbp
0x18004ad89  pop     rbx
0x18004ad8a  retn
0x18004ad8b  mov     rcx, [rcx+8]
0x18004ad8f  jmp     short loc_18004AD5A
0x18004ad91  mov     qword ptr [rbx], 0
0x18004ad98  jmp     short loc_18004AD82
0x18004ad9a  mov     edx, 18h; dwBytes
0x18004ad9f  xor     ecx, ecx; dwFlags
0x18004ada1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18004ada6  mov     rdx, rax
0x18004ada9  test    rax, rax
0x18004adac  jnz     short loc_18004ADB2
0x18004adae  xor     ecx, ecx
0x18004adb0  jmp     short loc_18004AD67
0x18004adb2  mov     [rax], ebp
0x18004adb4  lea     rcx, [rdx+10h]
0x18004adb8  xor     eax, eax
0x18004adba  mov     [rdx+4], eax
0x18004adbd  mov     [rdx+8], rax
0x18004adc1  mov     [rcx], rax
0x18004adc4  mov     rax, [rdi+rsi*8]
0x18004adc8  mov     [rdx+8], rax
0x18004adcc  lock cmpxchg [rdi+rsi*8], rdx
0x18004add2  jnz     short loc_18004ADC4
0x18004add4  jmp     short loc_18004AD67
```
