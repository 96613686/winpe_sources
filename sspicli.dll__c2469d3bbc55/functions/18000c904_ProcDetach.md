# ProcDetach

- ea: `0x18000c904`
- end: `0x18000ca1e`
- name: `ProcDetach`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c878`

## callees

- `0x18000c904`
- `0x18000d0f0`
- `0x1800102bc`
- `0x18001b020`

## import_xrefs

- `ntdll!NtClose` at `0x18000c96c`
- `ntdll!NtClose` at `0x18000c96c`
- `ntdll!RtlDeleteCriticalSection` at `0x18000c9af`
- `ntdll!RtlDeleteCriticalSection` at `0x18000c9c8`
- `ntdll!RtlDeleteCriticalSection` at `0x18000c9af`
- `ntdll!RtlDeleteCriticalSection` at `0x18000c9c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c9da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c9da`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000c93c`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000c953`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000c93c`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000c953`

## pseudocode

```c
__int64 __fastcall ProcDetach(__int64 a1, __int64 a2)
{
  bool v3; // di
  int v4; // eax

  v3 = a2 != 0;
  v4 = DllState | 0x100000;
  DllState |= 0x100000u;
  if ( !a2 )
  {
    if ( v4 < 0 )
    {
      if ( SecTlsPackage != -1 )
      {
        TlsFree(SecTlsPackage);
        v4 = DllState;
      }
      a1 = SecTlsIP;
      if ( SecTlsIP != -1 )
      {
        TlsFree(SecTlsIP);
        v4 = DllState;
      }
    }
    if ( (v4 & 0x400000) != 0 )
    {
      NtClose(KsecddHandle);
      v4 = DllState;
    }
  }
  if ( (v4 & 0x2000000) != 0 )
  {
    LOBYTE(a1) = v3;
    SecUnloadPackages(a1);
    v4 = DllState;
  }
  if ( !a2 )
  {
    if ( (v4 & 0x8000000) != 0 )
    {
      SecpUnloadVMList();
      v4 = DllState;
    }
    if ( (v4 & 0x10000000) != 0 )
    {
      RtlDeleteCriticalSection(&csSecurity);
      v4 = DllState;
    }
    if ( (v4 & 0x1000000) != 0 )
      RtlDeleteCriticalSection(&Logon32Lock);
  }
  if ( SecDllClient )
    LocalFree(SecDllClient);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_7b25146ef51239e0444a068fecac4892_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x18000c904  mov     [rsp+arg_0], rbx
0x18000c909  push    rdi
0x18000c90a  sub     rsp, 20h
0x18000c90e  mov     eax, cs:DllState
0x18000c914  test    rdx, rdx
0x18000c917  mov     rbx, rdx
0x18000c91a  setnz   dil
0x18000c91e  bts     eax, 14h
0x18000c922  mov     cs:DllState, eax
0x18000c928  test    rdx, rdx
0x18000c92b  jnz     short loc_18000C978
0x18000c92d  test    eax, eax
0x18000c92f  jns     short loc_18000C95F
0x18000c931  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18000c937  cmp     ecx, 0FFFFFFFFh
0x18000c93a  jz      short loc_18000C948
0x18000c93c  call    cs:__imp_TlsFree
0x18000c942  mov     eax, cs:DllState
0x18000c948  mov     ecx, cs:SecTlsIP; dwTlsIndex
0x18000c94e  cmp     ecx, 0FFFFFFFFh
0x18000c951  jz      short loc_18000C95F
0x18000c953  call    cs:__imp_TlsFree
0x18000c959  mov     eax, cs:DllState
0x18000c95f  bt      eax, 16h
0x18000c963  jnb     short loc_18000C978
0x18000c965  mov     rcx, cs:KsecddHandle; Handle
0x18000c96c  call    cs:__imp_NtClose
0x18000c972  mov     eax, cs:DllState
0x18000c978  bt      eax, 19h
0x18000c97c  jnb     short loc_18000C98C
0x18000c97e  mov     cl, dil
0x18000c981  call    SecUnloadPackages
0x18000c986  mov     eax, cs:DllState
0x18000c98c  test    rbx, rbx
0x18000c98f  jnz     short loc_18000C9CE
0x18000c991  bt      eax, 1Bh
0x18000c995  jnb     short loc_18000C9A2
0x18000c997  call    ?SecpUnloadVMList@@YAXXZ; SecpUnloadVMList(void)
0x18000c99c  mov     eax, cs:DllState
0x18000c9a2  bt      eax, 1Ch
0x18000c9a6  jnb     short loc_18000C9BB
0x18000c9a8  lea     rcx, csSecurity; CriticalSection
0x18000c9af  call    cs:__imp_RtlDeleteCriticalSection
0x18000c9b5  mov     eax, cs:DllState
0x18000c9bb  bt      eax, 18h
0x18000c9bf  jnb     short loc_18000C9CE
0x18000c9c1  lea     rcx, ?Logon32Lock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000c9c8  call    cs:__imp_RtlDeleteCriticalSection
0x18000c9ce  mov     rcx, cs:SecDllClient; hMem
0x18000c9d5  test    rcx, rcx
0x18000c9d8  jz      short loc_18000C9E0
0x18000c9da  call    cs:__imp_LocalFree
0x18000c9e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9e7  lea     rax, WPP_GLOBAL_Control
0x18000c9ee  cmp     rcx, rax
0x18000c9f1  jz      short loc_18000CA0E
0x18000c9f3  test    byte ptr [rcx+1Ch], 4
0x18000c9f7  jz      short loc_18000CA0E
0x18000c9f9  mov     rcx, [rcx+10h]
0x18000c9fd  lea     r8, WPP_7b25146ef51239e0444a068fecac4892_Traceguids
0x18000ca04  mov     edx, 14h
0x18000ca09  call    WPP_SF_
0x18000ca0e  mov     rbx, [rsp+28h+arg_0]
0x18000ca13  mov     eax, 1
0x18000ca18  add     rsp, 20h
0x18000ca1c  pop     rdi
0x18000ca1d  retn
```
