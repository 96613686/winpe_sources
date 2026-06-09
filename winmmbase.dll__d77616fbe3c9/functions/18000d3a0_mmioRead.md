# mmioRead

- ea: `0x18000d3a0`
- end: `0x18000d623`
- name: `mmioRead`
- size: `643`
- prototype: `LONG __stdcall(HMMIO hmmio, HPSTR pch, LONG cch)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012970`

## callees

- `0x180009300`
- `0x18000d3a0`
- `0x18000e4e8`
- `0x180012d08`
- `0x1800207bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d406`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d406`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d434`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d56f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d591`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d434`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d56f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d591`

## pseudocode

```c
LONG __stdcall mmioRead(HMMIO hmmio, HPSTR pch, LONG cch)
{
  HMMIO v7; // r15
  _QWORD *i; // rax
  LONG v9; // ebp
  BOOL v10; // eax
  LONG v11; // esi
  _QWORD *j; // rax
  int v13; // eax
  int v14; // eax

  if ( (unsigned __int64)hmmio < 0x10000
    || hmmio == (HMMIO)-1LL
    || (unsigned __int64)hmmio > gdwMaxVirtualAddress
    || hmmio == (HMMIO)0xFFFFFFFFLL
    || (unsigned __int64)hmmio < gdwMinVirtualAddress )
  {
    return -1;
  }
  v7 = hmmio - 20;
  EnterCriticalSection(&HandleListCritSec);
  for ( i = (_QWORD *)pHandleList; i; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)v7 )
    {
      LeaveCriticalSection(&HandleListCritSec);
      v9 = 0;
      v10 = *((_DWORD *)v7 + 2) == 5;
      goto LABEL_12;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
  }
  LeaveCriticalSection(&HandleListCritSec);
  v9 = 0;
  v10 = 0;
LABEL_12:
  if ( !v10 || !pch )
    return -1;
  while ( 2 )
  {
    v11 = cch;
    if ( *((_DWORD *)hmmio + 12) - *((_DWORD *)hmmio + 10) <= cch )
      v11 = *((_DWORD *)hmmio + 12) - *((_DWORD *)hmmio + 10);
    if ( v11 > 0 )
    {
      memcpy_0(pch, *((const void **)hmmio + 5), v11);
      *((_QWORD *)hmmio + 5) += v11;
      pch += v11;
      cch -= v11;
      v9 += v11;
    }
    if ( *((_DWORD *)hmmio + 1) == 541934925 || !cch )
      return v9;
    if ( cch <= *((_DWORD *)hmmio + 7) )
    {
      if ( (unsigned __int64)hmmio <= gdwMaxVirtualAddress && (unsigned __int64)hmmio >= gdwMinVirtualAddress )
      {
        EnterCriticalSection(&HandleListCritSec);
        for ( j = (_QWORD *)pHandleList; ; j = (_QWORD *)*j )
        {
          if ( !j )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
            }
            LeaveCriticalSection(&HandleListCritSec);
            return -1;
          }
          if ( j == (_QWORD *)v7 )
            break;
        }
        LeaveCriticalSection(&HandleListCritSec);
        if ( *((_DWORD *)v7 + 2) != 5 )
          return -1;
        if ( !*((_QWORD *)hmmio + 4) )
          return -1;
        if ( *((_DWORD *)hmmio + 1) == 541934925 )
          return -1;
        if ( mmioFlush(hmmio, 0x10u) )
          return -1;
        v13 = mmioDiskIO((__int64)hmmio, 0, *((_QWORD *)hmmio + 4), *((_DWORD *)hmmio + 7));
        if ( v13 == -1 )
          return -1;
        *((_QWORD *)hmmio + 6) += v13;
        if ( *((_QWORD *)hmmio + 5) != *((_QWORD *)hmmio + 6) )
          continue;
        return v9;
      }
      return -1;
    }
    break;
  }
  if ( mmioFlush(hmmio, 0x10u) )
    return -1;
  v14 = mmioDiskIO((__int64)hmmio, 0, (__int64)pch, cch);
  hmmio[16] = hmmio[17];
  if ( v14 == -1 )
    return -1;
  return v9 + v14;
}

```

## disassembly

```asm
0x18000d3a0  push    rbx
0x18000d3a2  push    rbp
0x18000d3a3  push    rsi
0x18000d3a4  push    rdi
0x18000d3a5  push    r12
0x18000d3a7  push    r13
0x18000d3a9  push    r14
0x18000d3ab  push    r15
0x18000d3ad  sub     rsp, 28h
0x18000d3b1  mov     r14d, r8d
0x18000d3b4  mov     r12, rdx
0x18000d3b7  mov     rbx, rcx
0x18000d3ba  cmp     rcx, 10000h
0x18000d3c1  jb      short loc_18000D3D7
0x18000d3c3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d3c7  jz      short loc_18000D3D7
0x18000d3c9  cmp     rcx, cs:gdwMaxVirtualAddress
0x18000d3d0  mov     eax, 0FFFFFFFFh
0x18000d3d5  jbe     short loc_18000D3ED
0x18000d3d7  mov     eax, 0FFFFFFFFh
0x18000d3dc  add     rsp, 28h
0x18000d3e0  pop     r15
0x18000d3e2  pop     r14
0x18000d3e4  pop     r13
0x18000d3e6  pop     r12
0x18000d3e8  pop     rdi
0x18000d3e9  pop     rsi
0x18000d3ea  pop     rbp
0x18000d3eb  pop     rbx
0x18000d3ec  retn
0x18000d3ed  cmp     rbx, rax
0x18000d3f0  jz      short loc_18000D3D7
0x18000d3f2  cmp     rbx, cs:gdwMinVirtualAddress
0x18000d3f9  jb      short loc_18000D3D7
0x18000d3fb  lea     r15, [rcx-50h]
0x18000d3ff  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000d406  call    cs:__imp_EnterCriticalSection
0x18000d40c  mov     rax, cs:pHandleList
0x18000d413  lea     r13, WPP_GLOBAL_Control
0x18000d41a  test    rax, rax
0x18000d41d  jz      loc_18000D55C
0x18000d423  cmp     rax, r15
0x18000d426  jz      short loc_18000D42D
0x18000d428  mov     rax, [rax]
0x18000d42b  jmp     short loc_18000D413
0x18000d42d  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000d434  call    cs:__imp_LeaveCriticalSection
0x18000d43a  xor     ebp, ebp
0x18000d43c  cmp     dword ptr [r15+8], 5
0x18000d441  mov     eax, ebp
0x18000d443  setz    al
0x18000d446  test    eax, eax
0x18000d448  jz      short loc_18000D3D7
0x18000d44a  test    r12, r12
0x18000d44d  jz      short loc_18000D3D7
0x18000d44f  mov     eax, [rbx+30h]
0x18000d452  mov     esi, r14d
0x18000d455  sub     eax, [rbx+28h]
0x18000d458  cmp     eax, r14d
0x18000d45b  cmovle  esi, eax
0x18000d45e  test    esi, esi
0x18000d460  jle     short loc_18000D480
0x18000d462  mov     rdx, [rbx+28h]; Src
0x18000d466  mov     rcx, r12; void *
0x18000d469  movsxd  rdi, esi
0x18000d46c  mov     r8, rdi; Size
0x18000d46f  call    memcpy_0
0x18000d474  add     [rbx+28h], rdi
0x18000d478  add     r12, rdi
0x18000d47b  sub     r14d, esi
0x18000d47e  add     ebp, esi
0x18000d480  cmp     dword ptr [rbx+4], 204D454Dh
0x18000d487  jz      loc_18000D555
0x18000d48d  test    r14d, r14d
0x18000d490  jz      loc_18000D555
0x18000d496  cmp     r14d, [rbx+1Ch]
0x18000d49a  jg      loc_18000D5E8
0x18000d4a0  cmp     rbx, cs:gdwMaxVirtualAddress
0x18000d4a7  ja      loc_18000D3D7
0x18000d4ad  cmp     rbx, cs:gdwMinVirtualAddress
0x18000d4b4  jb      loc_18000D3D7
0x18000d4ba  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000d4c1  call    cs:__imp_EnterCriticalSection
0x18000d4c7  mov     rax, cs:pHandleList
0x18000d4ce  test    rax, rax
0x18000d4d1  jz      loc_18000D57E
0x18000d4d7  cmp     rax, r15
0x18000d4da  jz      short loc_18000D4E1
0x18000d4dc  mov     rax, [rax]
0x18000d4df  jmp     short loc_18000D4CE
0x18000d4e1  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000d4e8  call    cs:__imp_LeaveCriticalSection
0x18000d4ee  cmp     dword ptr [r15+8], 5
0x18000d4f3  jnz     loc_18000D3D7
0x18000d4f9  cmp     qword ptr [rbx+20h], 0
0x18000d4fe  jz      loc_18000D3D7
0x18000d504  cmp     dword ptr [rbx+4], 204D454Dh
0x18000d50b  jz      loc_18000D3D7
0x18000d511  mov     edx, 10h; fuFlush
0x18000d516  mov     rcx, rbx; hmmio
0x18000d519  call    mmioFlush
0x18000d51e  test    eax, eax
0x18000d520  jnz     loc_18000D3D7
0x18000d526  mov     r9d, [rbx+1Ch]
0x18000d52a  xor     edx, edx
0x18000d52c  mov     r8, [rbx+20h]
0x18000d530  mov     rcx, rbx
0x18000d533  call    mmioDiskIO
0x18000d538  cmp     eax, 0FFFFFFFFh
0x18000d53b  jz      loc_18000D3D7
0x18000d541  cdqe
0x18000d543  add     [rbx+30h], rax
0x18000d547  mov     rax, [rbx+30h]
0x18000d54b  cmp     [rbx+28h], rax
0x18000d54f  jnz     loc_18000D44F
0x18000d555  mov     eax, ebp
0x18000d557  jmp     loc_18000D3DC
0x18000d55c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d563  cmp     rcx, r13
0x18000d566  jnz     short loc_18000D59C
0x18000d568  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000d56f  call    cs:__imp_LeaveCriticalSection
0x18000d575  xor     ebp, ebp
0x18000d577  mov     eax, ebp
0x18000d579  jmp     loc_18000D446
0x18000d57e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d585  cmp     rcx, r13
0x18000d588  jnz     short loc_18000D5C2
0x18000d58a  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000d591  call    cs:__imp_LeaveCriticalSection
0x18000d597  jmp     loc_18000D3D7
0x18000d59c  test    dword ptr [rcx+1Ch], 400000h
0x18000d5a3  jz      short loc_18000D568
0x18000d5a5  cmp     byte ptr [rcx+19h], 1
0x18000d5a9  jb      short loc_18000D568
0x18000d5ab  mov     rcx, [rcx+10h]
0x18000d5af  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x18000d5b6  mov     edx, 0Ah
0x18000d5bb  call    WPP_SF_
0x18000d5c0  jmp     short loc_18000D568
0x18000d5c2  test    dword ptr [rcx+1Ch], 400000h
0x18000d5c9  jz      short loc_18000D58A
0x18000d5cb  cmp     byte ptr [rcx+19h], 1
0x18000d5cf  jb      short loc_18000D58A
0x18000d5d1  mov     rcx, [rcx+10h]
0x18000d5d5  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x18000d5dc  mov     edx, 0Ah
0x18000d5e1  call    WPP_SF_
0x18000d5e6  jmp     short loc_18000D58A
0x18000d5e8  mov     edx, 10h; fuFlush
0x18000d5ed  mov     rcx, rbx; hmmio
0x18000d5f0  call    mmioFlush
0x18000d5f5  test    eax, eax
0x18000d5f7  jnz     loc_18000D3D7
0x18000d5fd  mov     r9d, r14d
0x18000d600  mov     r8, r12
0x18000d603  xor     edx, edx
0x18000d605  mov     rcx, rbx
0x18000d608  call    mmioDiskIO
0x18000d60d  mov     ecx, [rbx+44h]
0x18000d610  mov     [rbx+40h], ecx
0x18000d613  cmp     eax, 0FFFFFFFFh
0x18000d616  jz      loc_18000D3D7
0x18000d61c  add     eax, ebp
0x18000d61e  jmp     loc_18000D3DC
```
