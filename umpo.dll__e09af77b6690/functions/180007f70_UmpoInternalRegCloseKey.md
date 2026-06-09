# UmpoInternalRegCloseKey

- ea: `0x180007f70`
- end: `0x18000803e`
- name: `UmpoInternalRegCloseKey`
- size: `206`
- prototype: `void __fastcall(__int64, HKEY)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800061d0`
- `0x18000681c`
- `0x180007790`
- `0x18000b9b8`

## callees

- `0x180007f70`
- `0x18000f3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007fd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007fd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000801e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000801e`

## pseudocode

```c
void __fastcall UmpoInternalRegCloseKey(__int64 a1, HKEY a2)
{
  unsigned int i; // eax
  __int64 v5; // rbx
  __int64 v7; // rax

  if ( (unsigned __int64)a2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( *(_BYTE *)(a1 + 112) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
    for ( i = 0; ; ++i )
    {
      if ( i >= 2 )
        goto LABEL_19;
      v5 = 32LL * i;
      if ( *(HKEY *)(v5 + a1 + 24) == a2 )
        break;
    }
    if ( !*(_DWORD *)(v5 + a1 + 32) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (*(_DWORD *)(v5 + a1 + 32))-- == 1 )
    {
      v7 = *(_QWORD *)(v5 + a1 + 8) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v7 )
        v7 = *(_QWORD *)(v5 + a1 + 16) - *(_QWORD *)GUID_NULL.Data4;
      if ( !v7 )
      {
        *(_QWORD *)(v5 + a1 + 24) = -1;
LABEL_19:
        RegCloseKey(a2);
      }
    }
    if ( *(_BYTE *)(a1 + 112) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  }
}

```

## disassembly

```asm
0x180007f70  mov     [rsp+arg_18], rbp
0x180007f75  push    rdi
0x180007f76  sub     rsp, 20h
0x180007f7a  lea     rax, [rdx-1]
0x180007f7e  mov     rbp, rdx
0x180007f81  mov     rdi, rcx
0x180007f84  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007f88  ja      short loc_180007FE4
0x180007f8a  cmp     byte ptr [rcx+70h], 1
0x180007f8e  mov     [rsp+28h+arg_10], rsi
0x180007f93  jnz     loc_18000802D
0x180007f99  lea     rcx, [rdi+48h]; lpCriticalSection
0x180007f9d  call    cs:__imp_EnterCriticalSection
0x180007fa3  xor     eax, eax
0x180007fa5  mov     [rsp+28h+arg_0], rbx
0x180007faa  cmp     eax, 2
0x180007fad  jnb     short loc_18000801B
0x180007faf  mov     ebx, eax
0x180007fb1  shl     rbx, 5
0x180007fb5  cmp     [rbx+rdi+18h], rbp
0x180007fba  jnz     short loc_180007FEF
0x180007fbc  cmp     dword ptr [rbx+rdi+20h], 0
0x180007fc1  jbe     short loc_180008037
0x180007fc3  add     dword ptr [rbx+rdi+20h], 0FFFFFFFFh
0x180007fc8  jz      short loc_180007FF3
0x180007fca  cmp     byte ptr [rdi+70h], 1
0x180007fce  mov     rbx, [rsp+28h+arg_0]
0x180007fd3  jnz     short loc_180008026
0x180007fd5  lea     rcx, [rdi+48h]; lpCriticalSection
0x180007fd9  call    cs:__imp_LeaveCriticalSection
0x180007fdf  mov     rsi, [rsp+28h+arg_10]
0x180007fe4  mov     rbp, [rsp+28h+arg_18]
0x180007fe9  add     rsp, 20h
0x180007fed  pop     rdi
0x180007fee  retn
0x180007fef  inc     eax
0x180007ff1  jmp     short loc_180007FAA
0x180007ff3  mov     rax, [rbx+rdi+8]
0x180007ff8  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180007fff  jnz     short loc_18000800D
0x180008001  mov     rax, [rbx+rdi+10h]
0x180008006  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000800d  test    rax, rax
0x180008010  jnz     short loc_180007FCA
0x180008012  mov     qword ptr [rbx+rdi+18h], 0FFFFFFFFFFFFFFFFh
0x18000801b  mov     rcx, rbp; hKey
0x18000801e  call    cs:__imp_RegCloseKey
0x180008024  jmp     short loc_180007FCA
0x180008026  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000802b  jmp     short loc_180007FD5
0x18000802d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008032  jmp     loc_180007F99
0x180008037  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000803c  jmp     short loc_180007FC3
```
