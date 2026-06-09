# WaSslInitializeConnection

- ea: `0x180060250`
- end: `0x180060407`
- name: `WaSslInitializeConnection`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e460`
- `0x180060250`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006039f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006039f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180060330`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180060349`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180060330`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180060349`

## pseudocode

```c
__int64 __fastcall WaSslInitializeConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int LastError; // edi

  v4 = *(_QWORD *)(a1 + 24);
  *(_DWORD *)v4 = 1129075539;
  *(_QWORD *)(v4 + 1360) = 0;
  *(_BYTE *)(v4 + 1368) = 0;
  *(_QWORD *)(v4 + 1376) = 0;
  *(_QWORD *)(v4 + 1384) = 0;
  *(_QWORD *)(v4 + 1344) = 0;
  *(_QWORD *)(v4 + 1408) = 0;
  *(_QWORD *)(v4 + 1416) = 0;
  *(_DWORD *)(v4 + 1400) = 0;
  *(_QWORD *)(v4 + 1304) = v4 + 1296;
  *(_QWORD *)(v4 + 1296) = v4 + 1296;
  *(_QWORD *)(v4 + 1504) = v4 + 1496;
  *(_QWORD *)(v4 + 1496) = v4 + 1496;
  *(_QWORD *)(v4 + 56) = -1;
  *(_QWORD *)(v4 + 48) = -1;
  *(_DWORD *)(v4 + 116) = -1;
  *(_BYTE *)(v4 + 1240) = 0;
  *(_WORD *)(v4 + 1242) = 0;
  *(_QWORD *)(v4 + 1224) = 0;
  *(_WORD *)(v4 + 1232) = 0;
  *(_QWORD *)(v4 + 64) = 0;
  *(_DWORD *)(v4 + 80) = 0;
  *(_QWORD *)(v4 + 96) = 0;
  *(_WORD *)(v4 + 104) = 0;
  *(_DWORD *)(v4 + 1052) = 0;
  *(_DWORD *)(v4 + 1056) = 10240;
  *(_BYTE *)(v4 + 1076) = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v4 + 1256), 0xFA0u) )
  {
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v4 + 1456), 0xFA0u) )
    {
      LastError = 0;
      *(_QWORD *)(v4 + 16) = a3;
      *(_QWORD *)(v4 + 24) = a4;
      *(_QWORD *)(v4 + 8) = a1;
      *(_DWORD *)(v4 + 1448) = 0;
      *(_DWORD *)(v4 + 1248) = 0;
      return LastError;
    }
    LastError = WaGetLastError(v9);
    DeleteCriticalSection((LPCRITICAL_SECTION)(v4 + 1256));
  }
  else
  {
    LastError = WaGetLastError(v8);
  }
  if ( LastError )
  {
    if ( LastError != 997 && LastError != 234 && (xmmword_1800AD710 & 8) != 0 )
    {
      WPP_SF_d(515, 10, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, LastError);
      if ( (xmmword_1800AD710 & 8) != 0 )
        WPP_SF_d(515, 11, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180060250  push    rbx
0x180060252  push    rbp
0x180060253  push    rsi
0x180060254  push    rdi
0x180060255  push    r12
0x180060257  push    r14
0x180060259  push    r15
0x18006025b  sub     rsp, 20h
0x18006025f  mov     rbx, [rcx+18h]
0x180060263  xor     r12d, r12d
0x180060266  mov     rbp, rcx
0x180060269  mov     edi, 0FA0h
0x18006026e  mov     edx, edi; dwSpinCount
0x180060270  mov     r14, r9
0x180060273  mov     r15, r8
0x180060276  mov     dword ptr [rbx], 434C5353h
0x18006027c  lea     rax, [rbx+510h]
0x180060283  mov     [rbx+550h], r12
0x18006028a  lea     rsi, [rbx+4E8h]
0x180060291  mov     [rbx+558h], r12b
0x180060298  mov     rcx, rsi; lpCriticalSection
0x18006029b  mov     [rbx+560h], r12
0x1800602a2  mov     [rbx+568h], r12
0x1800602a9  mov     [rbx+540h], r12
0x1800602b0  mov     [rbx+580h], r12
0x1800602b7  mov     [rbx+588h], r12
0x1800602be  mov     [rbx+578h], r12d
0x1800602c5  mov     [rax+8], rax
0x1800602c9  mov     [rax], rax
0x1800602cc  lea     rax, [rbx+5D8h]
0x1800602d3  mov     [rax+8], rax
0x1800602d7  mov     [rax], rax
0x1800602da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800602de  mov     [rbx+38h], rax
0x1800602e2  mov     [rbx+30h], rax
0x1800602e6  mov     [rbx+74h], eax
0x1800602e9  mov     [rbx+4D8h], r12b
0x1800602f0  mov     [rbx+4DAh], r12w
0x1800602f8  mov     [rbx+4C8h], r12
0x1800602ff  mov     [rbx+4D0h], r12w
0x180060307  mov     [rbx+40h], r12
0x18006030b  mov     [rbx+50h], r12d
0x18006030f  mov     [rbx+60h], r12
0x180060313  mov     [rbx+68h], r12w
0x180060318  mov     [rbx+41Ch], r12d
0x18006031f  mov     dword ptr [rbx+420h], 2800h
0x180060329  mov     [rbx+434h], r12b
0x180060330  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180060337  nop     dword ptr [rax+rax+00h]
0x18006033c  test    eax, eax
0x18006033e  jz      short loc_180060378
0x180060340  lea     rcx, [rbx+5B0h]; lpCriticalSection
0x180060347  mov     edx, edi; dwSpinCount
0x180060349  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180060350  nop     dword ptr [rax+rax+00h]
0x180060355  test    eax, eax
0x180060357  jz      short loc_180060395
0x180060359  mov     edi, r12d
0x18006035c  mov     [rbx+10h], r15
0x180060360  mov     [rbx+18h], r14
0x180060364  mov     [rbx+8], rbp
0x180060368  mov     [rbx+5A8h], r12d
0x18006036f  mov     [rbx+4E0h], r12d
0x180060376  jmp     short loc_180060383
0x180060378  call    WaGetLastError
0x18006037d  mov     edi, eax
0x18006037f  test    edi, edi
0x180060381  jnz     short loc_1800603AD
0x180060383  mov     eax, edi
0x180060385  add     rsp, 20h
0x180060389  pop     r15
0x18006038b  pop     r14
0x18006038d  pop     r12
0x18006038f  pop     rdi
0x180060390  pop     rsi
0x180060391  pop     rbp
0x180060392  pop     rbx
0x180060393  retn
0x180060395  call    WaGetLastError
0x18006039a  mov     rcx, rsi; lpCriticalSection
0x18006039d  mov     edi, eax
0x18006039f  call    cs:__imp_DeleteCriticalSection
0x1800603a6  nop     dword ptr [rax+rax+00h]
0x1800603ab  jmp     short loc_18006037F
0x1800603ad  cmp     edi, 3E5h
0x1800603b3  jz      short loc_180060383
0x1800603b5  cmp     edi, 0EAh
0x1800603bb  jz      short loc_180060383
0x1800603bd  mov     al, byte ptr cs:xmmword_1800AD710
0x1800603c3  mov     ebx, 203h
0x1800603c8  test    al, 8
0x1800603ca  jz      short loc_180060383
0x1800603cc  mov     edx, 0Ah
0x1800603d1  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x1800603d8  mov     ecx, ebx
0x1800603da  mov     r9d, edi
0x1800603dd  call    WPP_SF_d
0x1800603e2  mov     al, byte ptr cs:xmmword_1800AD710
0x1800603e8  test    al, 8
0x1800603ea  jz      short loc_180060383
0x1800603ec  mov     edx, 0Bh
0x1800603f1  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x1800603f8  mov     ecx, ebx
0x1800603fa  mov     r9d, edi
0x1800603fd  call    WPP_SF_d
0x180060402  jmp     loc_180060383
```
