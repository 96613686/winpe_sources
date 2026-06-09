# CQuietHoursManager::_UpdateTimers(QuietHoursTimerId)

- ea: `0x180070c2c`
- end: `0x180070e52`
- name: `?_UpdateTimers@CQuietHoursManager@@AEAAXW4QuietHoursTimerId@@@Z`
- size: `550`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180070704`
- `0x180070770`
- `0x1800709d0`
- `0x1802c4350`

## callees

- `0x180070c2c`
- `0x18013d330`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070ccb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070d8f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070de1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070e47`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070ccb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070d8f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070de1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180070e47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070c92`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070da8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070e25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070c92`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070d61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070da8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180070e25`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180070c67`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180070c67`

## pseudocode

```c
void __fastcall CQuietHoursManager::_UpdateTimers(__int64 a1, int a2)
{
  int v4; // r14d
  int v5; // ebx
  int v6; // eax
  struct _TP_TIMER *v7; // rcx
  int v8; // ebx
  int v9; // r8d
  int v10; // ecx
  int v11; // edx
  int v12; // ebx
  struct _TP_TIMER *v13; // rcx
  int v14; // ebx
  int v15; // eax
  struct _TP_TIMER *v16; // rcx
  struct _TP_TIMER *v17; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-18h] BYREF

  SystemTimeAsFileTime = 0;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v4 = (unsigned __int16)(SystemTime.wMinute + 60 * SystemTime.wHour);
  if ( (a2 & 0xFFFFFFFB) == 0 )
  {
    v5 = *(unsigned __int16 *)(a1 + 192) - v4;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v6 = v5 + 1440;
    if ( v5 > 0 )
      v6 = v5;
    v7 = *(struct _TP_TIMER **)(a1 + 200);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL * v6;
    SetThreadpoolTimer(v7, &SystemTimeAsFileTime, 0, 0x7530u);
    if ( a2 == 4 )
      goto LABEL_9;
  }
  if ( a2 == 1 )
  {
LABEL_9:
    v8 = *(unsigned __int16 *)(a1 + 194);
    v9 = *(unsigned __int16 *)(a1 + 192);
    v10 = *(unsigned __int16 *)(a1 + 196);
    v11 = v8 - v9;
    if ( (unsigned __int16)v9 >= (unsigned __int16)v8 )
    {
      if ( v10 >= v11 + 1440 )
        LOWORD(v10) = v8 - v9 + 1440;
    }
    else if ( v10 >= v11 )
    {
      LOWORD(v10) = v8 - v9;
    }
    v12 = v8 - (unsigned __int16)v10 - v4;
    if ( v12 > -1440 )
    {
      if ( v12 <= 0 )
        v12 += 1440;
    }
    else
    {
      v12 += 2880;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v13 = *(struct _TP_TIMER **)(a1 + 208);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL * v12;
    SetThreadpoolTimer(v13, &SystemTimeAsFileTime, 0, 0x7530u);
  }
  if ( ((a2 - 2) & 0xFFFFFFFD) == 0 )
  {
    v14 = *(unsigned __int16 *)(a1 + 194) - v4;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v15 = v14 + 1440;
    if ( v14 > 0 )
      v15 = v14;
    v16 = *(struct _TP_TIMER **)(a1 + 216);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL * v15;
    SetThreadpoolTimer(v16, &SystemTimeAsFileTime, 0, 0x7530u);
  }
  if ( a2 == 3 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v17 = *(struct _TP_TIMER **)(a1 + 224);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL;
    SetThreadpoolTimer(v17, &SystemTimeAsFileTime, 0, 0x7530u);
  }
}

```

## disassembly

```asm
0x180070c2c  mov     [rsp-18h+arg_8], rbx
0x180070c31  mov     [rsp-18h+arg_10], rsi
0x180070c36  push    rbp
0x180070c37  push    rdi
0x180070c38  push    r14
0x180070c3a  mov     rbp, rsp
0x180070c3d  sub     rsp, 40h
0x180070c41  mov     rax, cs:__security_cookie
0x180070c48  xor     rax, rsp
0x180070c4b  mov     [rbp+var_8], rax
0x180070c4f  mov     rdi, rcx
0x180070c52  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180070c5a  xorps   xmm0, xmm0
0x180070c5d  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180070c61  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180070c65  mov     esi, edx
0x180070c67  call    cs:__imp_GetLocalTime
0x180070c6d  movzx   eax, [rbp+SystemTime.wHour]
0x180070c71  imul    ecx, eax, 3Ch ; '<'
0x180070c74  add     cx, [rbp+SystemTime.wMinute]
0x180070c78  movzx   r14d, cx
0x180070c7c  test    esi, 0FFFFFFFBh
0x180070c82  jnz     short loc_180070CD6
0x180070c84  movzx   ebx, word ptr [rdi+0C0h]
0x180070c8b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180070c8f  sub     ebx, r14d
0x180070c92  call    cs:__imp_GetSystemTimeAsFileTime
0x180070c98  lea     eax, [rbx+5A0h]
0x180070c9e  test    ebx, ebx
0x180070ca0  mov     r9d, 7530h; msWindowLength
0x180070ca6  lea     rdx, [rbp+SystemTimeAsFileTime]; pftDueTime
0x180070caa  cmovg   eax, ebx
0x180070cad  xor     r8d, r8d; msPeriod
0x180070cb0  imul    eax, 0EA60h
0x180070cb6  movsxd  rcx, eax
0x180070cb9  imul    rax, rcx, 2710h
0x180070cc0  mov     rcx, [rdi+0C8h]; pti
0x180070cc7  add     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180070ccb  call    cs:__imp_SetThreadpoolTimer
0x180070cd1  cmp     esi, 4
0x180070cd4  jz      short loc_180070D11
0x180070cd6  cmp     esi, 1
0x180070cd9  jz      short loc_180070D11
0x180070cdb  lea     eax, [rsi-2]
0x180070cde  test    eax, 0FFFFFFFDh
0x180070ce3  jz      loc_180070D9A
0x180070ce9  cmp     esi, 3
0x180070cec  jz      loc_180070E21
0x180070cf2  mov     rcx, [rbp+var_8]
0x180070cf6  xor     rcx, rsp; StackCookie
0x180070cf9  call    __security_check_cookie
0x180070cfe  mov     rbx, [rsp+40h+arg_8]
0x180070d03  mov     rsi, [rsp+40h+arg_10]
0x180070d08  add     rsp, 40h
0x180070d0c  pop     r14
0x180070d0e  pop     rdi
0x180070d0f  pop     rbp
0x180070d10  retn
0x180070d11  movzx   ebx, word ptr [rdi+0C2h]
0x180070d18  movzx   r8d, word ptr [rdi+0C0h]
0x180070d20  mov     edx, ebx
0x180070d22  movzx   ecx, word ptr [rdi+0C4h]
0x180070d29  sub     edx, r8d
0x180070d2c  cmp     r8w, bx
0x180070d30  jnb     loc_180070DEC
0x180070d36  movzx   eax, bx
0x180070d39  sub     ax, r8w
0x180070d3d  cmp     ecx, edx
0x180070d3f  cmovge  cx, ax
0x180070d43  movzx   eax, cx
0x180070d46  sub     ebx, eax
0x180070d48  sub     ebx, r14d
0x180070d4b  cmp     ebx, 0FFFFFA60h
0x180070d51  jg      loc_180070E0E
0x180070d57  add     ebx, 0B40h
0x180070d5d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180070d61  call    cs:__imp_GetSystemTimeAsFileTime
0x180070d67  imul    eax, ebx, 0EA60h
0x180070d6d  lea     rdx, [rbp+SystemTimeAsFileTime]; pftDueTime
0x180070d71  mov     r9d, 7530h; msWindowLength
0x180070d77  xor     r8d, r8d; msPeriod
0x180070d7a  movsxd  rcx, eax
0x180070d7d  imul    rax, rcx, 2710h
0x180070d84  mov     rcx, [rdi+0D0h]; pti
0x180070d8b  add     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180070d8f  call    cs:__imp_SetThreadpoolTimer
0x180070d95  jmp     loc_180070CDB
0x180070d9a  movzx   ebx, word ptr [rdi+0C2h]
0x180070da1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180070da5  sub     ebx, r14d
0x180070da8  call    cs:__imp_GetSystemTimeAsFileTime
0x180070dae  test    ebx, ebx
0x180070db0  lea     eax, [rbx+5A0h]
0x180070db6  mov     r9d, 7530h; msWindowLength
0x180070dbc  lea     rdx, [rbp+SystemTimeAsFileTime]; pftDueTime
0x180070dc0  cmovg   eax, ebx
0x180070dc3  xor     r8d, r8d; msPeriod
0x180070dc6  imul    eax, 0EA60h
0x180070dcc  movsxd  rcx, eax
0x180070dcf  imul    rax, rcx, 2710h
0x180070dd6  mov     rcx, [rdi+0D8h]; pti
0x180070ddd  add     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180070de1  call    cs:__imp_SetThreadpoolTimer
0x180070de7  jmp     loc_180070CE9
0x180070dec  lea     eax, [rdx+5A0h]
0x180070df2  cmp     ecx, eax
0x180070df4  jl      loc_180070D43
0x180070dfa  movzx   eax, bx
0x180070dfd  mov     ecx, 5A0h
0x180070e02  sub     ax, r8w
0x180070e06  add     cx, ax
0x180070e09  jmp     loc_180070D43
0x180070e0e  test    ebx, ebx
0x180070e10  jg      loc_180070D5D
0x180070e16  add     ebx, 5A0h
0x180070e1c  jmp     loc_180070D5D
0x180070e21  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180070e25  call    cs:__imp_GetSystemTimeAsFileTime
0x180070e2b  mov     rcx, [rdi+0E0h]; pti
0x180070e32  lea     rdx, [rbp+SystemTimeAsFileTime]; pftDueTime
0x180070e36  add     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 23C34600h
0x180070e3e  mov     r9d, 7530h; msWindowLength
0x180070e44  xor     r8d, r8d; msPeriod
0x180070e47  call    cs:__imp_SetThreadpoolTimer
0x180070e4d  jmp     loc_180070CF2
```
