# AgCxStart

- ea: `0x1800ab390`
- end: `0x1800ab515`
- name: `AgCxStart`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800aadec`

## callees

- `0x18003cbe4`
- `0x18003cffc`
- `0x1800ab390`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x1800ab48e`
- `ntdll!NtSetSystemInformation` at `0x1800ab48e`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab49a`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab49a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab3b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab3df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab3b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3ca`

## pseudocode

```c
DWORD __fastcall AgCxStart(__int64 a1)
{
  HANDLE EventW; // rax
  HANDLE v4; // rax
  __int64 v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // r10
  int v7; // eax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  __int64 v12; // [rsp+20h] [rbp-50h] BYREF
  _DWORD SystemInformation[2]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-40h]
  int *v15; // [rsp+38h] [rbp-38h]
  __int64 v16; // [rsp+40h] [rbp-30h]
  int v17; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+4Ch] [rbp-24h]
  __int128 v19; // [rsp+54h] [rbp-1Ch]
  int v20; // [rsp+64h] [rbp-Ch]

  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 19040) = EventW;
  if ( !EventW )
    return GetLastError();
  v4 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 19032) = v4;
  if ( !v4 )
    return GetLastError();
  v12 = PfsActionItemGetCurrentTime(v5) + 864000000000LL;
  PfsActionItemQueueEx(v6 + 43, 6u, (unsigned __int64 *)&v12, 0);
  if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 1600LL) & 0x10) != 0 )
  {
    if ( *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1872LL) == -1 )
    {
      v14 = 10;
      v15 = &v17;
      v16 = 32;
      v20 = 0;
      v19 = 0;
      SystemInformation[0] = 45;
      SystemInformation[1] = 1802856515;
      v17 = 4;
      v18 = 4;
      v7 = NtSetSystemInformation(SystemSuperfetchInformation, SystemInformation, 0x20u);
      if ( v7 < 0 )
        RtlNtStatusToDosError(v7);
    }
    v8 = *(_QWORD *)&PfSvcGlobals;
    v9 = (unsigned __int64)((((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                           * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64) >> 10;
    *(_DWORD *)(a1 + 19064) = 2;
    v10 = *(_DWORD *)(v8 + 240);
    v8 += 1928;
    v11 = v9 + v10;
    *(_QWORD *)(a1 + 19048) = v8;
    ++*(_DWORD *)(v8 + 8);
    *(_DWORD *)(a1 + 19056) = v11;
    *(_DWORD *)(a1 + 19060) = v11 + 200;
  }
  return 0;
}

```

## disassembly

```asm
0x1800ab390  mov     [rsp-8+arg_8], rbx
0x1800ab395  push    rbp
0x1800ab396  mov     rbp, rsp
0x1800ab399  sub     rsp, 70h
0x1800ab39d  mov     rax, cs:__security_cookie
0x1800ab3a4  xor     rax, rsp
0x1800ab3a7  mov     [rbp+var_8], rax
0x1800ab3ab  mov     rbx, rcx
0x1800ab3ae  xor     r9d, r9d; lpName
0x1800ab3b1  xor     ecx, ecx; lpEventAttributes
0x1800ab3b3  xor     r8d, r8d; bInitialState
0x1800ab3b6  xor     edx, edx; bManualReset
0x1800ab3b8  call    cs:__imp_CreateEventW
0x1800ab3be  mov     [rbx+4A60h], rax
0x1800ab3c5  test    rax, rax
0x1800ab3c8  jnz     short loc_1800AB3D5
0x1800ab3ca  call    cs:__imp_GetLastError
0x1800ab3d0  jmp     loc_1800AB4FB
0x1800ab3d5  xor     r9d, r9d; lpName
0x1800ab3d8  xor     r8d, r8d; bInitialState
0x1800ab3db  xor     edx, edx; bManualReset
0x1800ab3dd  xor     ecx, ecx; lpEventAttributes
0x1800ab3df  call    cs:__imp_CreateEventW
0x1800ab3e5  mov     [rbx+4A58h], rax
0x1800ab3ec  test    rax, rax
0x1800ab3ef  jz      short loc_1800AB3CA
0x1800ab3f1  mov     r10, cs:PfSvcGlobals
0x1800ab3f8  call    PfsActionItemGetCurrentTime
0x1800ab3fd  xor     r9d, r9d
0x1800ab400  lea     r8, [rbp+var_50]
0x1800ab404  mov     rcx, 0C92A69C000h
0x1800ab40e  add     rax, rcx
0x1800ab411  lea     rcx, [r10+6B8h]; lpCriticalSection
0x1800ab418  mov     [rbp+var_50], rax
0x1800ab41c  lea     edx, [r9+6]
0x1800ab420  call    PfsActionItemQueueEx
0x1800ab425  mov     rax, cs:PfSvcGlobals
0x1800ab42c  test    byte ptr [rax+640h], 10h
0x1800ab433  jz      loc_1800AB4F9
0x1800ab439  cmp     dword ptr [rax+750h], 0FFFFFFFFh
0x1800ab440  jnz     short loc_1800AB4A0
0x1800ab442  lea     rax, [rbp+var_28]
0x1800ab446  mov     [rbp+var_40], 0Ah
0x1800ab44e  mov     [rbp+var_38], rax
0x1800ab452  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x1800ab456  mov     eax, 4
0x1800ab45b  mov     [rbp+var_30], 20h ; ' '
0x1800ab463  xorps   xmm0, xmm0
0x1800ab466  mov     [rbp+var_C], 0
0x1800ab46d  movdqu  [rbp+var_1C], xmm0
0x1800ab472  mov     [rbp+SystemInformation], 2Dh ; '-'
0x1800ab479  lea     r8d, [rax+1Ch]; SystemInformationLength
0x1800ab47d  mov     [rbp+var_44], 6B756843h
0x1800ab484  lea     ecx, [rax+4Bh]; SystemInformationClass
0x1800ab487  mov     [rbp+var_28], eax
0x1800ab48a  mov     [rbp+var_24], rax
0x1800ab48e  call    cs:__imp_NtSetSystemInformation
0x1800ab494  test    eax, eax
0x1800ab496  jns     short loc_1800AB4A0
0x1800ab498  mov     ecx, eax; Status
0x1800ab49a  call    cs:__imp_RtlNtStatusToDosError
0x1800ab4a0  mov     ecx, ds:7FFE0004h
0x1800ab4a7  mov     eax, 7FFE0320h
0x1800ab4ac  shl     rcx, 20h
0x1800ab4b0  mov     rax, [rax]
0x1800ab4b3  shl     rax, 8
0x1800ab4b7  mul     rcx
0x1800ab4ba  mov     rcx, cs:PfSvcGlobals
0x1800ab4c1  shr     rdx, 0Ah
0x1800ab4c5  mov     dword ptr [rbx+4A78h], 2
0x1800ab4cf  mov     eax, [rcx+0F0h]
0x1800ab4d5  add     rcx, 788h
0x1800ab4dc  add     eax, edx
0x1800ab4de  mov     [rbx+4A68h], rcx
0x1800ab4e5  inc     dword ptr [rcx+8]
0x1800ab4e8  mov     [rbx+4A70h], eax
0x1800ab4ee  add     eax, 0C8h
0x1800ab4f3  mov     [rbx+4A74h], eax
0x1800ab4f9  xor     eax, eax
0x1800ab4fb  mov     rcx, [rbp+var_8]
0x1800ab4ff  xor     rcx, rsp; StackCookie
0x1800ab502  call    __security_check_cookie
0x1800ab507  mov     rbx, [rsp+70h+arg_8]
0x1800ab50f  add     rsp, 70h
0x1800ab513  pop     rbp
0x1800ab514  retn
```
