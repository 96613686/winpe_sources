# waveOutWrite

- ea: `0x180005fb0`
- end: `0x1800062f4`
- name: `waveOutWrite`
- size: `836`
- prototype: `MMRESULT __stdcall(HWAVEOUT hwo, LPWAVEHDR pwh, UINT cbwh)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180005fb0`
- `0x1800065d0`
- `0x180012d08`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800060ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006127`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006169`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800060ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006127`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006169`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006032`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000606f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006103`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006190`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006209`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000623e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006032`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000606f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006103`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006190`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006209`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000623e`

## pseudocode

```c
MMRESULT __stdcall waveOutWrite(HWAVEOUT hwo, LPWAVEHDR pwh, UINT cbwh)
{
  __int64 v3; // r14
  DWORD dwFlags; // eax
  _BOOL8 v8; // rax
  MMRESULT v9; // ebx
  HWAVEOUT v10; // rbp
  _QWORD *i; // rax
  int v12; // r15d
  BOOL v13; // eax
  struct _RTL_CRITICAL_SECTION *v14; // rsi
  int v15; // ecx
  unsigned __int64 v16; // rax
  _QWORD *j; // rax
  _QWORD *k; // rax

  v3 = cbwh;
  if ( !pwh )
    return 11;
  if ( cbwh < 0x30 )
    return 11;
  dwFlags = pwh->dwFlags;
  if ( (dwFlags & 0xFFFFCFE0) != 0 )
    return 11;
  if ( (dwFlags & 2) == 0 )
    return 34;
  if ( (dwFlags & 0x10) == 0 )
  {
    ClientUpdatePnpInfo();
    if ( (unsigned __int64)hwo < 0x10000
      || hwo == (HWAVEOUT)-1LL
      || (unsigned __int64)hwo > gdwMaxVirtualAddress
      || hwo == (HWAVEOUT)0xFFFFFFFFLL
      || (unsigned __int64)hwo < gdwMinVirtualAddress )
    {
      return 5;
    }
    v10 = hwo - 20;
    EnterCriticalSection(&HandleListCritSec);
    for ( i = (_QWORD *)pHandleList; i; i = (_QWORD *)*i )
    {
      if ( i == (_QWORD *)v10 )
      {
        LeaveCriticalSection(&HandleListCritSec);
        v12 = 0;
        v13 = *((_DWORD *)v10 + 2) == 1;
        goto LABEL_24;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
    }
    LeaveCriticalSection(&HandleListCritSec);
    v12 = 0;
    v13 = 0;
LABEL_24:
    if ( !v13 )
      return 5;
    pwh->dwFlags &= ~1u;
    v14 = (struct _RTL_CRITICAL_SECTION *)(hwo - 10);
    EnterCriticalSection((LPCRITICAL_SECTION)hwo - 1);
    v15 = *((_DWORD *)hwo - 17);
    if ( (v15 & 1) != 0 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)hwo - 1);
      return 6;
    }
    if ( (v15 & 2) != 0 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)hwo - 1);
      return 12;
    }
    v16 = gdwMinVirtualAddress;
    if ( (unsigned __int64)hwo < gdwMinVirtualAddress )
      goto LABEL_30;
    if ( (unsigned __int64)hwo <= gdwMaxVirtualAddress )
    {
      EnterCriticalSection(&HandleListCritSec);
      for ( j = (_QWORD *)pHandleList; j; j = (_QWORD *)*j )
      {
        if ( j == (_QWORD *)v10 )
        {
          LeaveCriticalSection(&HandleListCritSec);
          v8 = *((_DWORD *)hwo - 18) == 1;
          goto LABEL_11;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
      }
      LeaveCriticalSection(&HandleListCritSec);
      LODWORD(v8) = 0;
LABEL_11:
      if ( v8 )
        goto LABEL_12;
      v16 = gdwMinVirtualAddress;
    }
    if ( (unsigned __int64)hwo > gdwMaxVirtualAddress || (unsigned __int64)hwo < v16 )
      goto LABEL_30;
    EnterCriticalSection(&HandleListCritSec);
    for ( k = (_QWORD *)pHandleList; k; k = (_QWORD *)*k )
    {
      if ( k == (_QWORD *)v10 )
      {
        LeaveCriticalSection(&HandleListCritSec);
        LOBYTE(v12) = *((_DWORD *)v10 + 2) == 2;
        goto LABEL_45;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
    }
    LeaveCriticalSection(&HandleListCritSec);
LABEL_45:
    if ( !v12 )
    {
LABEL_30:
      v9 = 5;
      goto LABEL_13;
    }
LABEL_12:
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPWAVEHDR, __int64))(*(_QWORD *)hwo + 80LL))(
           *((unsigned int *)hwo + 2),
           9,
           *((_QWORD *)hwo + 2),
           pwh,
           v3);
LABEL_13:
    LeaveCriticalSection(v14);
    return v9;
  }
  return 33;
}

```

## disassembly

```asm
0x180005fb0  push    rbx
0x180005fb2  push    rdi
0x180005fb3  push    r14
0x180005fb5  sub     rsp, 30h
0x180005fb9  mov     r14d, r8d
0x180005fbc  mov     rdi, rdx
0x180005fbf  mov     rbx, rcx
0x180005fc2  test    rdx, rdx
0x180005fc5  jz      loc_18000621D
0x180005fcb  cmp     r14d, 30h ; '0'
0x180005fcf  jb      loc_18000621D
0x180005fd5  mov     eax, [rdx+18h]
0x180005fd8  test    eax, 0FFFFCFE0h
0x180005fdd  jnz     loc_18000621D
0x180005fe3  test    al, 2
0x180005fe5  jz      loc_18000624C
0x180005feb  test    al, 10h
0x180005fed  jnz     loc_180006256
0x180005ff3  mov     [rsp+48h+arg_0], rbp
0x180005ff8  mov     [rsp+48h+arg_10], r12
0x180005ffd  mov     [rsp+48h+arg_18], r15
0x180006002  call    ClientUpdatePnpInfo
0x180006007  cmp     rbx, 10000h
0x18000600e  jb      short loc_180006024
0x180006010  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180006014  jz      short loc_180006024
0x180006016  cmp     rbx, cs:gdwMaxVirtualAddress
0x18000601d  mov     eax, 0FFFFFFFFh
0x180006022  jbe     short loc_180006094
0x180006024  mov     eax, 5
0x180006029  jmp     short loc_18000607C
0x18000602b  lea     rcx, HandleListCritSec; lpCriticalSection
0x180006032  call    cs:__imp_LeaveCriticalSection
0x180006038  cmp     dword ptr [rbp+8], 1
0x18000603c  mov     eax, r15d
0x18000603f  setz    al
0x180006042  test    eax, eax
0x180006044  jz      loc_1800062B7
0x18000604a  mov     rax, [rbx]
0x18000604d  mov     r9, rdi
0x180006050  mov     r8, [rbx+10h]
0x180006054  mov     edx, 9
0x180006059  mov     ecx, [rbx+8]
0x18000605c  mov     [rsp+48h+var_28], r14
0x180006061  mov     rax, [rax+50h]
0x180006065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000606a  mov     ebx, eax
0x18000606c  mov     rcx, rsi; lpCriticalSection
0x18000606f  call    cs:__imp_LeaveCriticalSection
0x180006075  mov     rsi, [rsp+48h+arg_8]
0x18000607a  mov     eax, ebx
0x18000607c  mov     r12, [rsp+48h+arg_10]
0x180006081  mov     rbp, [rsp+48h+arg_0]
0x180006086  mov     r15, [rsp+48h+arg_18]
0x18000608b  add     rsp, 30h
0x18000608f  pop     r14
0x180006091  pop     rdi
0x180006092  pop     rbx
0x180006093  retn
0x180006094  cmp     rbx, rax
0x180006097  jz      short loc_180006024
0x180006099  cmp     rbx, cs:gdwMinVirtualAddress
0x1800060a0  jb      short loc_180006024
0x1800060a2  lea     rcx, HandleListCritSec; lpCriticalSection
0x1800060a9  lea     rbp, [rbx-50h]
0x1800060ad  call    cs:__imp_EnterCriticalSection
0x1800060b3  mov     rax, cs:pHandleList
0x1800060ba  lea     r12, WPP_GLOBAL_Control
0x1800060c1  test    rax, rax
0x1800060c4  jz      short loc_1800060EC
0x1800060c6  cmp     rax, rbp
0x1800060c9  jz      short loc_1800060D0
0x1800060cb  mov     rax, [rax]
0x1800060ce  jmp     short loc_1800060BA
0x1800060d0  lea     rcx, HandleListCritSec; lpCriticalSection
0x1800060d7  call    cs:__imp_LeaveCriticalSection
0x1800060dd  xor     r15d, r15d
0x1800060e0  cmp     dword ptr [rbp+8], 1
0x1800060e4  mov     eax, r15d
0x1800060e7  setz    al
0x1800060ea  jmp     short loc_18000610F
0x1800060ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060f3  cmp     rcx, r12
0x1800060f6  jnz     loc_180006260
0x1800060fc  lea     rcx, HandleListCritSec; lpCriticalSection
0x180006103  call    cs:__imp_LeaveCriticalSection
0x180006109  xor     r15d, r15d
0x18000610c  mov     eax, r15d
0x18000610f  test    eax, eax
0x180006111  jz      loc_180006024
0x180006117  and     dword ptr [rdi+18h], 0FFFFFFFEh
0x18000611b  mov     [rsp+48h+arg_8], rsi
0x180006120  lea     rsi, [rbx-28h]
0x180006124  mov     rcx, rsi; lpCriticalSection
0x180006127  call    cs:__imp_EnterCriticalSection
0x18000612d  mov     ecx, [rbx-44h]
0x180006130  test    cl, 1
0x180006133  jnz     short loc_18000618D
0x180006135  test    cl, 2
0x180006138  jnz     short loc_1800061A0
0x18000613a  mov     rax, cs:gdwMinVirtualAddress
0x180006141  cmp     rbx, rax
0x180006144  jb      short loc_180006158
0x180006146  cmp     rbx, cs:gdwMaxVirtualAddress
0x18000614d  jbe     short loc_180006162
0x18000614f  cmp     rbx, cs:gdwMaxVirtualAddress
0x180006156  jbe     short loc_1800061B3
0x180006158  mov     ebx, 5
0x18000615d  jmp     loc_18000606C
0x180006162  lea     rcx, HandleListCritSec; lpCriticalSection
0x180006169  call    cs:__imp_EnterCriticalSection
0x18000616f  mov     rax, cs:pHandleList
0x180006176  test    rax, rax
0x180006179  jz      loc_18000622B
0x18000617f  cmp     rax, rbp
0x180006182  jz      loc_18000602B
0x180006188  mov     rax, [rax]
0x18000618b  jmp     short loc_180006176
0x18000618d  mov     rcx, rsi; lpCriticalSection
0x180006190  call    cs:__imp_LeaveCriticalSection
0x180006196  mov     ebx, 6
0x18000619b  jmp     loc_180006075
0x1800061a0  mov     rcx, rsi; lpCriticalSection
0x1800061a3  call    cs:__imp_LeaveCriticalSection
0x1800061a9  mov     ebx, 0Ch
0x1800061ae  jmp     loc_180006075
0x1800061b3  cmp     rbx, rax
0x1800061b6  jb      short loc_180006158
0x1800061b8  lea     rcx, HandleListCritSec; lpCriticalSection
0x1800061bf  call    cs:__imp_EnterCriticalSection
0x1800061c5  mov     rax, cs:pHandleList
0x1800061cc  test    rax, rax
0x1800061cf  jz      short loc_1800061F2
0x1800061d1  cmp     rax, rbp
0x1800061d4  jz      short loc_1800061DB
0x1800061d6  mov     rax, [rax]
0x1800061d9  jmp     short loc_1800061CC
0x1800061db  lea     rcx, HandleListCritSec; lpCriticalSection
0x1800061e2  call    cs:__imp_LeaveCriticalSection
0x1800061e8  cmp     dword ptr [rbp+8], 2
0x1800061ec  setz    r15b
0x1800061f0  jmp     short loc_18000620F
0x1800061f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061f9  cmp     rcx, r12
0x1800061fc  jnz     loc_1800062C3
0x180006202  lea     rcx, HandleListCritSec; lpCriticalSection
0x180006209  call    cs:__imp_LeaveCriticalSection
0x18000620f  test    r15d, r15d
0x180006212  jnz     loc_18000604A
0x180006218  jmp     loc_180006158
0x18000621d  mov     eax, 0Bh
0x180006222  add     rsp, 30h
0x180006226  pop     r14
0x180006228  pop     rdi
0x180006229  pop     rbx
0x18000622a  retn
0x18000622b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006232  cmp     rcx, r12
0x180006235  jnz     short loc_180006291
0x180006237  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000623e  call    cs:__imp_LeaveCriticalSection
0x180006244  mov     eax, r15d
0x180006247  jmp     loc_180006042
0x18000624c  mov     eax, 22h ; '"'
0x180006251  jmp     loc_18000608B
0x180006256  mov     eax, 21h ; '!'
0x18000625b  jmp     loc_18000608B
0x180006260  test    dword ptr [rcx+1Ch], 400000h
0x180006267  jz      loc_1800060FC
0x18000626d  cmp     byte ptr [rcx+19h], 1
0x180006271  jb      loc_1800060FC
0x180006277  mov     rcx, [rcx+10h]
0x18000627b  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x180006282  mov     edx, 0Ah
0x180006287  call    WPP_SF_
0x18000628c  jmp     loc_1800060FC
0x180006291  test    dword ptr [rcx+1Ch], 400000h
0x180006298  jz      short loc_180006237
0x18000629a  cmp     byte ptr [rcx+19h], 1
0x18000629e  jb      short loc_180006237
0x1800062a0  mov     rcx, [rcx+10h]
0x1800062a4  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x1800062ab  mov     edx, 0Ah
0x1800062b0  call    WPP_SF_
0x1800062b5  jmp     short loc_180006237
0x1800062b7  mov     rax, cs:gdwMinVirtualAddress
0x1800062be  jmp     loc_18000614F
0x1800062c3  test    dword ptr [rcx+1Ch], 400000h
0x1800062ca  jz      loc_180006202
0x1800062d0  cmp     byte ptr [rcx+19h], 1
0x1800062d4  jb      loc_180006202
0x1800062da  mov     rcx, [rcx+10h]
0x1800062de  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x1800062e5  mov     edx, 0Ah
0x1800062ea  call    WPP_SF_
0x1800062ef  jmp     loc_180006202
```
