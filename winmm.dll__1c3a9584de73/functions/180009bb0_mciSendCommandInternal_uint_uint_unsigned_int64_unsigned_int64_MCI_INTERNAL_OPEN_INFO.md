# mciSendCommandInternal(uint,uint,unsigned __int64,unsigned __int64,MCI_INTERNAL_OPEN_INFO *)

- ea: `0x180009bb0`
- end: `0x180009d93`
- name: `?mciSendCommandInternal@@YAKII_K0PEAUMCI_INTERNAL_OPEN_INFO@@@Z`
- size: `483`
- prototype: `unsigned int(unsigned int, unsigned int, unsigned __int64, unsigned __int64, struct MCI_INTERNAL_OPEN_INFO *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009a90`
- `0x180010504`

## callees

- `0x180009bb0`
- `0x1800102a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ce6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ce6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009bd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009bd7`

## pseudocode

```c
__int64 __fastcall mciSendCommandInternal(
        unsigned int a1,
        UINT a2,
        LPARAM a3,
        DWORD_PTR a4,
        struct MCI_INTERNAL_OPEN_INFO *a5)
{
  DWORD_PTR v5; // rdi
  DWORD CurrentThreadId; // eax
  unsigned int v9; // esi
  unsigned int v10; // edi
  int v11; // r12d
  __int64 v12; // r13
  __int64 v13; // rbp

  v5 = a4;
  CurrentThreadId = GetCurrentThreadId();
  if ( a1 == -1 && ((a2 - 2064) & 0xFFFFFFFD) != 0 )
  {
    if ( a2 == 2051 )
    {
      v9 = 0;
      v10 = 279;
      EnterCriticalSection(&mciCritSec);
      goto LABEL_37;
    }
    v11 = 1;
    a1 = 1;
  }
  else
  {
    v11 = 0;
  }
  v12 = CurrentThreadId;
  EnterCriticalSection(&mciCritSec);
  if ( v11 )
  {
    v13 = 0;
    v9 = 0;
    goto LABEL_18;
  }
  if ( a2 == 2051 || a2 == 2066 || a2 == 2064 )
  {
    v13 = 0;
    v9 = 0;
  }
  else
  {
    if ( !a1 || a1 >= MCI_wNextDeviceID || (v13 = *((_QWORD *)MCI_lpDeviceList + a1)) == 0 )
    {
      v10 = 257;
      v9 = 0;
      goto LABEL_37;
    }
    v9 = 0;
LABEL_22:
    if ( (*(_BYTE *)(v13 + 104) & 1) != 0 && a2 != 2050 )
      goto LABEL_35;
    if ( *(_QWORD *)(v13 + 80) != v12 )
    {
      if ( a2 != 2052 )
      {
        v10 = 303;
        goto LABEL_37;
      }
      if ( (*(_DWORD *)(v13 + 104) & 0x10000) != 0 )
      {
LABEL_35:
        v10 = 288;
        goto LABEL_37;
      }
    }
  }
  LeaveCriticalSection(&mciCritSec);
  v10 = mciSendSingleCommand(a1, a2, a3, v5, (struct tagMCI_DEVICE_NODE *)v13, v11, a5);
  EnterCriticalSection(&mciCritSec);
  if ( v11 )
  {
    if ( v10 )
    {
      if ( v9 )
        v9 = 280;
      else
        v9 = v10;
    }
    while ( ++a1 < MCI_wNextDeviceID )
    {
      v5 = a4;
LABEL_18:
      if ( a2 != 2064 )
        v13 = *((_QWORD *)MCI_lpDeviceList + a1);
      if ( v13 && *(_QWORD *)(v13 + 88) == v12 )
        goto LABEL_22;
      v10 = 0;
    }
  }
LABEL_37:
  LeaveCriticalSection(&mciCritSec);
  if ( v9 != 280 )
    return v10;
  return v9;
}

```

## disassembly

```asm
0x180009bb0  mov     rax, rsp
0x180009bb3  mov     [rax+8], rbx
0x180009bb7  mov     [rax+10h], rbp
0x180009bbb  mov     [rax+20h], r9
0x180009bbf  mov     [rax+18h], r8
0x180009bc3  push    rsi
0x180009bc4  push    rdi
0x180009bc5  push    r12
0x180009bc7  push    r13
0x180009bc9  push    r14
0x180009bcb  sub     rsp, 40h
0x180009bcf  mov     rdi, r9
0x180009bd2  mov     r14d, edx
0x180009bd5  mov     ebx, ecx
0x180009bd7  call    cs:__imp_GetCurrentThreadId
0x180009bdd  mov     esi, 803h
0x180009be2  mov     edx, 1
0x180009be7  cmp     ebx, 0FFFFFFFFh
0x180009bea  jnz     short loc_180009C20
0x180009bec  lea     ecx, [r14-810h]
0x180009bf3  test    ecx, 0FFFFFFFDh
0x180009bf9  jz      short loc_180009C20
0x180009bfb  cmp     r14d, esi
0x180009bfe  jnz     short loc_180009C19
0x180009c00  xor     esi, esi
0x180009c02  lea     rcx, mciCritSec; lpCriticalSection
0x180009c09  mov     edi, 117h
0x180009c0e  call    cs:__imp_EnterCriticalSection
0x180009c14  jmp     loc_180009D64
0x180009c19  mov     r12d, edx
0x180009c1c  mov     ebx, edx
0x180009c1e  jmp     short loc_180009C23
0x180009c20  xor     r12d, r12d
0x180009c23  lea     rcx, mciCritSec; lpCriticalSection
0x180009c2a  mov     r13d, eax
0x180009c2d  call    cs:__imp_EnterCriticalSection
0x180009c33  test    r12d, r12d
0x180009c36  jnz     short loc_180009C83
0x180009c38  cmp     r14d, esi
0x180009c3b  jz      short loc_180009C7D
0x180009c3d  cmp     r14d, 812h
0x180009c44  jz      short loc_180009C7D
0x180009c46  cmp     r14d, 810h
0x180009c4d  jz      short loc_180009C7D
0x180009c4f  test    ebx, ebx
0x180009c51  jz      short loc_180009C71
0x180009c53  cmp     ebx, cs:MCI_wNextDeviceID
0x180009c59  jnb     short loc_180009C71
0x180009c5b  mov     rax, cs:MCI_lpDeviceList
0x180009c62  mov     ecx, ebx
0x180009c64  mov     rbp, [rax+rcx*8]
0x180009c68  test    rbp, rbp
0x180009c6b  jz      short loc_180009C71
0x180009c6d  xor     esi, esi
0x180009c6f  jmp     short loc_180009CB0
0x180009c71  mov     edi, 101h
0x180009c76  xor     esi, esi
0x180009c78  jmp     loc_180009D64
0x180009c7d  xor     ebp, ebp
0x180009c7f  xor     esi, esi
0x180009c81  jmp     short loc_180009CDF
0x180009c83  xor     ebp, ebp
0x180009c85  xor     esi, esi
0x180009c87  cmp     r14d, 810h
0x180009c8e  jz      short loc_180009C9D
0x180009c90  mov     rax, cs:MCI_lpDeviceList
0x180009c97  mov     ecx, ebx
0x180009c99  mov     rbp, [rax+rcx*8]
0x180009c9d  test    rbp, rbp
0x180009ca0  jz      loc_180009D3F
0x180009ca6  cmp     [rbp+58h], r13
0x180009caa  jnz     loc_180009D3F
0x180009cb0  test    byte ptr [rbp+68h], 1
0x180009cb4  jz      short loc_180009CC3
0x180009cb6  cmp     r14d, 802h
0x180009cbd  jnz     loc_180009D58
0x180009cc3  cmp     [rbp+50h], r13
0x180009cc7  jz      short loc_180009CDF
0x180009cc9  cmp     r14d, 804h
0x180009cd0  jnz     loc_180009D5F
0x180009cd6  test    dword ptr [rbp+68h], 10000h
0x180009cdd  jnz     short loc_180009D58
0x180009cdf  lea     rcx, mciCritSec; lpCriticalSection
0x180009ce6  call    cs:__imp_LeaveCriticalSection
0x180009cec  mov     rax, [rsp+68h+arg_20]
0x180009cf4  mov     r9, rdi; dwParam2
0x180009cf7  mov     r8, [rsp+68h+dwParam1]; dwParam1
0x180009cff  mov     edx, r14d; message
0x180009d02  mov     [rsp+68h+var_38], rax; struct MCI_INTERNAL_OPEN_INFO *
0x180009d07  mov     ecx, ebx; mciId
0x180009d09  mov     [rsp+68h+var_40], r12d; int
0x180009d0e  mov     [rsp+68h+var_48], rbp; struct tagMCI_DEVICE_NODE *
0x180009d13  call    ?mciSendSingleCommand@@YAKII_K0PEAUtagMCI_DEVICE_NODE@@HPEAUMCI_INTERNAL_OPEN_INFO@@@Z; mciSendSingleCommand(uint,uint,unsigned __int64,unsigned __int64,tagMCI_DEVICE_NODE *,int,MCI_INTERNAL_OPEN_INFO *)
0x180009d18  lea     rcx, mciCritSec; lpCriticalSection
0x180009d1f  mov     edi, eax
0x180009d21  call    cs:__imp_EnterCriticalSection
0x180009d27  test    r12d, r12d
0x180009d2a  jz      short loc_180009D64
0x180009d2c  test    edi, edi
0x180009d2e  jz      short loc_180009D41
0x180009d30  test    esi, esi
0x180009d32  jz      short loc_180009D3B
0x180009d34  mov     esi, 118h
0x180009d39  jmp     short loc_180009D41
0x180009d3b  mov     esi, edi
0x180009d3d  jmp     short loc_180009D41
0x180009d3f  xor     edi, edi
0x180009d41  inc     ebx
0x180009d43  cmp     ebx, cs:MCI_wNextDeviceID
0x180009d49  jnb     short loc_180009D64
0x180009d4b  mov     rdi, [rsp+68h+arg_18]
0x180009d53  jmp     loc_180009C87
0x180009d58  mov     edi, 120h
0x180009d5d  jmp     short loc_180009D64
0x180009d5f  mov     edi, 12Fh
0x180009d64  lea     rcx, mciCritSec; lpCriticalSection
0x180009d6b  call    cs:__imp_LeaveCriticalSection
0x180009d71  mov     rbx, [rsp+68h+arg_0]
0x180009d76  cmp     esi, 118h
0x180009d7c  mov     rbp, [rsp+68h+arg_8]
0x180009d81  cmovnz  esi, edi
0x180009d84  mov     eax, esi
0x180009d86  add     rsp, 40h
0x180009d8a  pop     r14
0x180009d8c  pop     r13
0x180009d8e  pop     r12
0x180009d90  pop     rdi
0x180009d91  pop     rsi
0x180009d92  retn
```
