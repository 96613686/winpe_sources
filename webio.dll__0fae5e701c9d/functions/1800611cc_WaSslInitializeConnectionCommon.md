# WaSslInitializeConnectionCommon

- ea: `0x1800611cc`
- end: `0x18006135c`
- name: `WaSslInitializeConnectionCommon`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008f7e0`

## callees

- `0x18002e460`
- `0x1800611cc`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006131a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006131a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800612ab`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800612c4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800612ab`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800612c4`

## pseudocode

```c
__int64 __fastcall WaSslInitializeConnectionCommon(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int LastError; // edi

  *(_DWORD *)a2 = 1129075539;
  *(_QWORD *)(a2 + 1360) = 0;
  *(_BYTE *)(a2 + 1368) = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(a2 + 1256);
  *(_QWORD *)(a2 + 1376) = 0;
  *(_QWORD *)(a2 + 1384) = 0;
  *(_QWORD *)(a2 + 1344) = 0;
  *(_QWORD *)(a2 + 1408) = 0;
  *(_QWORD *)(a2 + 1416) = 0;
  *(_DWORD *)(a2 + 1400) = 0;
  *(_QWORD *)(a2 + 1304) = a2 + 1296;
  *(_QWORD *)(a2 + 1296) = a2 + 1296;
  *(_QWORD *)(a2 + 1504) = a2 + 1496;
  *(_QWORD *)(a2 + 1496) = a2 + 1496;
  *(_QWORD *)(a2 + 56) = -1;
  *(_QWORD *)(a2 + 48) = -1;
  *(_DWORD *)(a2 + 116) = -1;
  *(_BYTE *)(a2 + 1240) = 0;
  *(_WORD *)(a2 + 1242) = 0;
  *(_QWORD *)(a2 + 1224) = 0;
  *(_WORD *)(a2 + 1232) = 0;
  *(_QWORD *)(a2 + 64) = 0;
  *(_DWORD *)(a2 + 80) = 0;
  *(_QWORD *)(a2 + 96) = 0;
  *(_WORD *)(a2 + 104) = 0;
  *(_DWORD *)(a2 + 1052) = 0;
  *(_DWORD *)(a2 + 1056) = 10240;
  *(_BYTE *)(a2 + 1076) = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a2 + 1256), 0xFA0u) )
  {
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a2 + 1456), 0xFA0u) )
    {
      LastError = 0;
      *(_QWORD *)(a2 + 16) = a3;
      *(_QWORD *)(a2 + 24) = a4;
      *(_QWORD *)(a2 + 8) = a1;
      *(_DWORD *)(a2 + 1448) = 0;
      *(_DWORD *)(a2 + 1248) = 0;
      return LastError;
    }
    LastError = WaGetLastError(v10);
    DeleteCriticalSection(v4);
  }
  else
  {
    LastError = WaGetLastError(v9);
  }
  if ( LastError && LastError != 997 && LastError != 234 && (xmmword_1800AD710 & 8) != 0 )
    WPP_SF_d(515, 10, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800611cc  push    rbx
0x1800611ce  push    rbp
0x1800611cf  push    rsi
0x1800611d0  push    rdi
0x1800611d1  push    r12
0x1800611d3  push    r14
0x1800611d5  push    r15
0x1800611d7  sub     rsp, 20h
0x1800611db  xor     r12d, r12d
0x1800611de  mov     dword ptr [rdx], 434C5353h
0x1800611e4  mov     [rdx+550h], r12
0x1800611eb  lea     rax, [rdx+510h]
0x1800611f2  mov     [rdx+558h], r12b
0x1800611f9  lea     rsi, [rdx+4E8h]
0x180061200  mov     [rdx+560h], r12
0x180061207  mov     rbx, rdx
0x18006120a  mov     [rdx+568h], r12
0x180061211  mov     r15, rcx
0x180061214  mov     [rdx+540h], r12
0x18006121b  mov     edi, 0FA0h
0x180061220  mov     [rdx+580h], r12
0x180061227  mov     rcx, rsi; lpCriticalSection
0x18006122a  mov     [rdx+588h], r12
0x180061231  mov     rbp, r9
0x180061234  mov     [rdx+578h], r12d
0x18006123b  mov     r14, r8
0x18006123e  mov     [rax+8], rax
0x180061242  mov     [rax], rax
0x180061245  lea     rax, [rdx+5D8h]
0x18006124c  mov     [rax+8], rax
0x180061250  mov     [rax], rax
0x180061253  or      rax, 0FFFFFFFFFFFFFFFFh
0x180061257  mov     [rdx+38h], rax
0x18006125b  mov     [rdx+30h], rax
0x18006125f  mov     [rdx+74h], eax
0x180061262  mov     [rdx+4D8h], r12b
0x180061269  mov     [rdx+4DAh], r12w
0x180061271  mov     [rdx+4C8h], r12
0x180061278  mov     [rdx+4D0h], r12w
0x180061280  mov     [rdx+40h], r12
0x180061284  mov     [rdx+50h], r12d
0x180061288  mov     [rdx+60h], r12
0x18006128c  mov     [rdx+68h], r12w
0x180061291  mov     [rdx+41Ch], r12d
0x180061298  mov     dword ptr [rdx+420h], 2800h
0x1800612a2  mov     [rdx+434h], r12b
0x1800612a9  mov     edx, edi; dwSpinCount
0x1800612ab  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800612b2  nop     dword ptr [rax+rax+00h]
0x1800612b7  test    eax, eax
0x1800612b9  jz      short loc_1800612F3
0x1800612bb  lea     rcx, [rbx+5B0h]; lpCriticalSection
0x1800612c2  mov     edx, edi; dwSpinCount
0x1800612c4  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800612cb  nop     dword ptr [rax+rax+00h]
0x1800612d0  test    eax, eax
0x1800612d2  jz      short loc_180061310
0x1800612d4  mov     edi, r12d
0x1800612d7  mov     [rbx+10h], r14
0x1800612db  mov     [rbx+18h], rbp
0x1800612df  mov     [rbx+8], r15
0x1800612e3  mov     [rbx+5A8h], r12d
0x1800612ea  mov     [rbx+4E0h], r12d
0x1800612f1  jmp     short loc_1800612FE
0x1800612f3  call    WaGetLastError
0x1800612f8  mov     edi, eax
0x1800612fa  test    edi, edi
0x1800612fc  jnz     short loc_180061328
0x1800612fe  mov     eax, edi
0x180061300  add     rsp, 20h
0x180061304  pop     r15
0x180061306  pop     r14
0x180061308  pop     r12
0x18006130a  pop     rdi
0x18006130b  pop     rsi
0x18006130c  pop     rbp
0x18006130d  pop     rbx
0x18006130e  retn
0x180061310  call    WaGetLastError
0x180061315  mov     rcx, rsi; lpCriticalSection
0x180061318  mov     edi, eax
0x18006131a  call    cs:__imp_DeleteCriticalSection
0x180061321  nop     dword ptr [rax+rax+00h]
0x180061326  jmp     short loc_1800612FA
0x180061328  cmp     edi, 3E5h
0x18006132e  jz      short loc_1800612FE
0x180061330  cmp     edi, 0EAh
0x180061336  jz      short loc_1800612FE
0x180061338  test    byte ptr cs:xmmword_1800AD710, 8
0x18006133f  jz      short loc_1800612FE
0x180061341  mov     edx, 0Ah
0x180061346  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x18006134d  mov     ecx, 203h
0x180061352  mov     r9d, edi
0x180061355  call    WPP_SF_d
0x18006135a  jmp     short loc_1800612FE
```
