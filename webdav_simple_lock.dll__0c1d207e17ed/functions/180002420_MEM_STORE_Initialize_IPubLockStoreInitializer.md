# MEM_STORE::Initialize(IPubLockStoreInitializer *)

- ea: `0x180002420`
- end: `0x180002574`
- name: `?Initialize@MEM_STORE@@UEAAJPEAVIPubLockStoreInitializer@@@Z`
- size: `340`
- prototype: `RPC_STATUS __fastcall(MEM_STORE *this, int (__fastcall ***)(struct IPubLockStoreInitializer *, const wchar_t *, struct _FILETIME *))`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002420`
- `0x180003c30`
- `0x180004010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180002530`
- `msvcrt!wcstoul` at `0x180002530`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024b7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002492`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002492`
- `RPCRT4!RpcStringFreeW` at `0x18000249e`
- `RPCRT4!RpcStringFreeW` at `0x18000249e`
- `RPCRT4!UuidToStringW` at `0x180002480`
- `RPCRT4!UuidToStringW` at `0x180002480`
- `RPCRT4!UuidCreate` at `0x18000245b`
- `RPCRT4!UuidCreate` at `0x18000245b`

## pseudocode

```c
RPC_STATUS __fastcall MEM_STORE::Initialize(
        MEM_STORE *this,
        int (__fastcall ***a2)(struct IPubLockStoreInitializer *, const wchar_t *, struct _FILETIME *))
{
  RPC_STATUS result; // eax
  bool v5; // cc
  int v6; // ebx
  int (__fastcall **v7)(struct IPubLockStoreInitializer *, const wchar_t *, struct _FILETIME *); // rax
  int v8; // ebx
  const wchar_t *v9; // rcx
  unsigned int v10; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-30h] BYREF
  RPC_WSTR StringUuid; // [rsp+28h] [rbp-28h] BYREF
  wchar_t *EndPtr; // [rsp+30h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-18h] BYREF

  Uuid = 0;
  StringUuid = 0;
  result = UuidCreate(&Uuid);
  v5 = result <= 0;
  if ( !result )
  {
    result = UuidToStringW(&Uuid, &StringUuid);
    v5 = result <= 0;
    if ( !result )
    {
      v6 = STRU::Copy((MEM_STORE *)((char *)this + 16), StringUuid);
      RpcStringFreeW(&StringUuid);
      if ( v6 < 0 )
        return v6;
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      *((_QWORD *)this + 1) = __ROR8__(SystemTimeAsFileTime, 16);
      v7 = *a2;
      v8 = 1000;
      SystemTimeAsFileTime = 0;
      if ( v7[1]((struct IPubLockStoreInitializer *)a2, L"maxLockCount", &SystemTimeAsFileTime) < 0
        || (v9 = (const wchar_t *)SystemTimeAsFileTime) == 0
        || !*(_WORD *)SystemTimeAsFileTime.dwLowDateTime )
      {
        if ( (**a2)((struct IPubLockStoreInitializer *)a2, L"maxLockCount", &SystemTimeAsFileTime) < 0 )
        {
LABEL_17:
          *((_DWORD *)this + 25) = v8;
          result = 0;
          *((_DWORD *)this + 26) = 0;
          return result;
        }
        v9 = (const wchar_t *)SystemTimeAsFileTime;
      }
      if ( v9 )
      {
        EndPtr = 0;
        v10 = wcstoul(v9, &EndPtr, 0);
        if ( EndPtr )
        {
          if ( !*EndPtr && v10 )
            v8 = v10;
        }
      }
      goto LABEL_17;
    }
  }
  if ( !v5 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002420  mov     [rsp-18h+arg_10], rbx
0x180002425  mov     [rsp-18h+arg_18], rsi
0x18000242a  push    rbp
0x18000242b  push    rdi
0x18000242c  push    r14
0x18000242e  mov     rbp, rsp
0x180002431  sub     rsp, 50h
0x180002435  mov     rax, cs:__security_cookie
0x18000243c  xor     rax, rsp
0x18000243f  mov     [rbp+var_8], rax
0x180002443  mov     rdi, rcx
0x180002446  xorps   xmm0, xmm0
0x180002449  xor     r14d, r14d
0x18000244c  lea     rcx, [rbp+Uuid]; Uuid
0x180002450  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180002454  mov     [rbp+StringUuid], r14
0x180002458  mov     rsi, rdx
0x18000245b  call    cs:__imp_UuidCreate
0x180002461  test    eax, eax
0x180002463  jz      short loc_180002478
0x180002465  jle     loc_180002553
0x18000246b  movzx   eax, ax
0x18000246e  or      eax, 80070000h
0x180002473  jmp     loc_180002553
0x180002478  lea     rdx, [rbp+StringUuid]; StringUuid
0x18000247c  lea     rcx, [rbp+Uuid]; Uuid
0x180002480  call    cs:__imp_UuidToStringW
0x180002486  test    eax, eax
0x180002488  jnz     short loc_180002465
0x18000248a  mov     rdx, [rbp+StringUuid]
0x18000248e  lea     rcx, [rdi+10h]
0x180002492  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002498  lea     rcx, [rbp+StringUuid]; String
0x18000249c  mov     ebx, eax
0x18000249e  call    cs:__imp_RpcStringFreeW
0x1800024a4  test    ebx, ebx
0x1800024a6  jns     short loc_1800024AF
0x1800024a8  mov     eax, ebx
0x1800024aa  jmp     loc_180002553
0x1800024af  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800024b3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800024b7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800024bd  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800024c1  lea     r8, [rbp+SystemTimeAsFileTime]
0x1800024c5  ror     rax, 10h
0x1800024c9  lea     rdx, aMaxlockcount; "maxLockCount"
0x1800024d0  mov     [rdi+8], rax
0x1800024d4  mov     rcx, rsi
0x1800024d7  mov     rax, [rsi]
0x1800024da  mov     ebx, 3E8h
0x1800024df  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800024e3  mov     rax, [rax+8]
0x1800024e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024ec  test    eax, eax
0x1800024ee  js      short loc_1800024FF
0x1800024f0  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800024f4  test    rcx, rcx
0x1800024f7  jz      short loc_1800024FF
0x1800024f9  cmp     [rcx], r14w
0x1800024fd  jnz     short loc_180002520
0x1800024ff  mov     rax, [rsi]
0x180002502  lea     r8, [rbp+SystemTimeAsFileTime]
0x180002506  lea     rdx, aMaxlockcount; "maxLockCount"
0x18000250d  mov     rcx, rsi
0x180002510  mov     rax, [rax]
0x180002513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002518  test    eax, eax
0x18000251a  js      short loc_18000254A
0x18000251c  mov     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]; String
0x180002520  test    rcx, rcx
0x180002523  jz      short loc_18000254A
0x180002525  xor     r8d, r8d; Radix
0x180002528  mov     [rbp+EndPtr], r14
0x18000252c  lea     rdx, [rbp+EndPtr]; EndPtr
0x180002530  call    cs:__imp_wcstoul
0x180002536  mov     rcx, [rbp+EndPtr]
0x18000253a  test    rcx, rcx
0x18000253d  jz      short loc_18000254A
0x18000253f  cmp     [rcx], r14w
0x180002543  jnz     short loc_18000254A
0x180002545  test    eax, eax
0x180002547  cmovnz  ebx, eax
0x18000254a  mov     [rdi+64h], ebx
0x18000254d  xor     eax, eax
0x18000254f  mov     [rdi+68h], r14d
0x180002553  mov     rcx, [rbp+var_8]
0x180002557  xor     rcx, rsp; StackCookie
0x18000255a  call    __security_check_cookie
0x18000255f  lea     r11, [rsp+50h+var_s0]
0x180002564  mov     rbx, [r11+30h]
0x180002568  mov     rsi, [r11+38h]
0x18000256c  mov     rsp, r11
0x18000256f  pop     r14
0x180002571  pop     rdi
0x180002572  pop     rbp
0x180002573  retn
```
