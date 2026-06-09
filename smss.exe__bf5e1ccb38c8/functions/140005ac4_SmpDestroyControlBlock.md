# SmpDestroyControlBlock

- ea: `0x140005ac4`
- end: `0x140005bd1`
- name: `SmpDestroyControlBlock`
- size: `269`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001880`
- `0x140001f60`
- `0x1400036d0`

## callees

- `0x1400010b0`
- `0x140001630`
- `0x140003114`
- `0x140004ec0`
- `0x140005ac4`
- `0x140008f80`
- `0x140017d5c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140005b49`
- `ntdll!RtlInitUnicodeString` at `0x140005b49`
- `ntdll!NtWaitForSingleObject` at `0x140005bc0`
- `ntdll!NtWaitForSingleObject` at `0x140005bc0`
- `ntdll!NtTerminateProcess` at `0x140005ba8`
- `ntdll!NtTerminateProcess` at `0x140005ba8`

## pseudocode

```c
__int64 __fastcall SmpDestroyControlBlock(HANDLE *BaseAddress, int a2)
{
  unsigned int v2; // ebx
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rbx
  __int64 v9; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int64 Parameters[9]; // [rsp+40h] [rbp-48h] BYREF

  v2 = 0;
  if ( (*(_BYTE *)BaseAddress & 2) == 0 )
  {
    _m_prefetchw(BaseAddress);
    v5 = *(_DWORD *)BaseAddress;
    do
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)BaseAddress, v5 | 2, v5);
    }
    while ( v6 != v5 );
    if ( (v5 & 2) == 0 )
    {
      v7 = *((unsigned int *)BaseAddress + 2);
      SmpReleaseControlBlock((char *)BaseAddress);
      if ( a2 )
      {
        if ( (unsigned __int8)SmpSessionIdIsInitialSessions((unsigned int)v7)
          && !*(_DWORD *)(SmpCoreProcessIds
                        + 40LL * (unsigned int)SmpSessionIdToInitialSessionIndex((unsigned int)v7)
                        + 4) )
        {
          v8 = (unsigned __int64)BaseAddress[2];
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"initial session process or");
          v9 = (__int64)BaseAddress[7];
          Parameters[0] = (unsigned __int64)&DestinationString;
          Parameters[1] = *(int *)(v8 + 4);
          Parameters[2] = v7;
          Parameters[3] = v8;
          SmLogFailureInt((__int64)"SmpDestroyControlBlock", 0x2A3u, v9, 0, *(_DWORD *)(v8 + 4));
          SmpTerminate(Parameters, 1u, 4u);
        }
        NtTerminateProcess(BaseAddress[6], -1073741823);
        v2 = SmpTerminateCSR(v7);
      }
    }
  }
  NtWaitForSingleObject(BaseAddress[6], 0, 0);
  return v2;
}

```

## disassembly

```asm
0x140005ac4  push    rbx
0x140005ac6  push    rbp
0x140005ac7  push    rsi
0x140005ac8  push    rdi
0x140005ac9  sub     rsp, 68h
0x140005acd  xor     ebx, ebx
0x140005acf  mov     ebp, edx
0x140005ad1  test    byte ptr [rcx], 2
0x140005ad4  mov     rdi, rcx
0x140005ad7  jnz     loc_140005BB7
0x140005add  prefetchw byte ptr [rcx]
0x140005ae0  mov     eax, [rcx]
0x140005ae2  mov     ecx, eax
0x140005ae4  or      ecx, 2
0x140005ae7  lock cmpxchg [rdi], ecx
0x140005aeb  jnz     short loc_140005AE2
0x140005aed  test    al, 2
0x140005aef  jnz     loc_140005BB7
0x140005af5  mov     esi, [rdi+8]
0x140005af8  mov     rcx, rdi; BaseAddress
0x140005afb  call    SmpReleaseControlBlock
0x140005b00  test    ebp, ebp
0x140005b02  jz      loc_140005BB7
0x140005b08  mov     ecx, esi
0x140005b0a  call    SmpSessionIdIsInitialSessions
0x140005b0f  test    al, al
0x140005b11  jz      loc_140005B9F
0x140005b17  mov     ecx, esi
0x140005b19  call    SmpSessionIdToInitialSessionIndex
0x140005b1e  mov     ecx, eax
0x140005b20  mov     rax, cs:SmpCoreProcessIds
0x140005b27  lea     rdx, [rcx+rcx*4]
0x140005b2b  cmp     [rax+rdx*8+4], ebx
0x140005b2f  jnz     short loc_140005B9F
0x140005b31  mov     rbx, [rdi+10h]
0x140005b35  lea     rdx, aInitialSession; "initial session process or"
0x140005b3c  xorps   xmm0, xmm0
0x140005b3f  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x140005b44  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x140005b49  call    cs:__imp_RtlInitUnicodeString
0x140005b4f  mov     r8, [rdi+38h]
0x140005b53  lea     rax, [rsp+88h+DestinationString]
0x140005b58  mov     [rsp+88h+Parameters], rax
0x140005b5d  lea     rcx, aSmpdestroycont; "SmpDestroyControlBlock"
0x140005b64  movsxd  rax, dword ptr [rbx+4]
0x140005b68  xor     r9d, r9d
0x140005b6b  mov     [rsp+88h+var_40], rax
0x140005b70  mov     edx, 2A3h
0x140005b75  mov     [rsp+88h+var_38], rsi
0x140005b7a  mov     [rsp+88h+var_30], rbx
0x140005b7f  mov     eax, [rbx+4]
0x140005b82  mov     [rsp+88h+var_68], eax
0x140005b86  call    SmLogFailureInt
0x140005b8b  mov     edx, 1; UnicodeStringParameterMask
0x140005b90  lea     rcx, [rsp+88h+Parameters]; Parameters
0x140005b95  lea     r8d, [rdx+3]; NumberOfParameters
0x140005b99  call    SmpTerminate
0x140005b9f  mov     rcx, [rdi+30h]; ProcessHandle
0x140005ba3  mov     edx, 0C0000001h; ExitStatus
0x140005ba8  call    cs:__imp_NtTerminateProcess
0x140005bae  mov     ecx, esi
0x140005bb0  call    SmpTerminateCSR
0x140005bb5  mov     ebx, eax
0x140005bb7  mov     rcx, [rdi+30h]; Object
0x140005bbb  xor     r8d, r8d; Timeout
0x140005bbe  xor     edx, edx; Alertable
0x140005bc0  call    cs:__imp_NtWaitForSingleObject
0x140005bc6  mov     eax, ebx
0x140005bc8  add     rsp, 68h
0x140005bcc  pop     rdi
0x140005bcd  pop     rsi
0x140005bce  pop     rbp
0x140005bcf  pop     rbx
0x140005bd0  retn
```
