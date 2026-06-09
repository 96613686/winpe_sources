# midiMessage

- ea: `0x18000c1d0`
- end: `0x18000c375`
- name: `midiMessage`
- size: `421`
- prototype: ``
- caller_count: `20`
- callee_count: `4`
- tags: ``

## callers

- `0x180009160`
- `0x180009250`
- `0x1800096f0`
- `0x18000bee0`
- `0x18000c6a0`
- `0x18000e860`
- `0x18000fa80`
- `0x18001787c`
- `0x180018bb0`
- `0x180019000`
- `0x180019060`
- `0x1800190b0`
- `0x180019100`
- `0x1800191b0`
- `0x180019270`
- `0x1800194d0`
- `0x180019740`
- `0x180019840`
- `0x180019b30`
- `0x180019bc0`

## callees

- `0x180007560`
- `0x18000c1d0`
- `0x180012d08`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c1f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c27c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c1f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c27c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c206`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c29f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c30f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c206`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c29f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c30f`

## pseudocode

```c
__int64 __fastcall midiMessage(unsigned __int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int v9; // ecx
  unsigned __int64 v11; // r15
  _QWORD *i; // rax
  BOOL v13; // eax
  unsigned int v14; // edi

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 - 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 - 40));
  v9 = *(_DWORD *)(a1 - 68);
  if ( (v9 & 1) != 0 )
  {
    LeaveCriticalSection(v4);
    return 6;
  }
  else if ( (v9 & 2) != 0 )
  {
    LeaveCriticalSection(v4);
    return 12;
  }
  else
  {
    if ( a1 >= 0x10000 && a1 != -1 && a1 <= gdwMaxVirtualAddress && a1 != 0xFFFFFFFF && a1 >= gdwMinVirtualAddress )
    {
      v11 = a1 - 80;
      EnterCriticalSection(&HandleListCritSec);
      for ( i = (_QWORD *)pHandleList; i; i = (_QWORD *)*i )
      {
        if ( i == (_QWORD *)v11 )
        {
          LeaveCriticalSection(&HandleListCritSec);
          v13 = *(_DWORD *)(v11 + 8) == 3;
          goto LABEL_16;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b291d698302c3933274e905320ac47d5_Traceguids);
      }
      LeaveCriticalSection(&HandleListCritSec);
      v13 = 0;
LABEL_16:
      if ( v13 )
        goto LABEL_17;
    }
    if ( ValidateHandle(a1, 9) || ValidateHandle(a1, 4) )
LABEL_17:
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)a1 + 80LL))(
              *(unsigned int *)(a1 + 8),
              a2,
              *(_QWORD *)(a1 + 16),
              a3,
              a4);
    else
      v14 = 5;
    LeaveCriticalSection(v4);
    return v14;
  }
}

```

## disassembly

```asm
0x18000c1d0  mov     [rsp+arg_8], rbx
0x18000c1d5  mov     [rsp+arg_10], rbp
0x18000c1da  push    rsi
0x18000c1db  push    rdi
0x18000c1dc  push    r14
0x18000c1de  sub     rsp, 30h
0x18000c1e2  lea     rbx, [rcx-28h]
0x18000c1e6  mov     rdi, rcx
0x18000c1e9  mov     rcx, rbx; lpCriticalSection
0x18000c1ec  mov     rsi, r9
0x18000c1ef  mov     rbp, r8
0x18000c1f2  mov     r14d, edx
0x18000c1f5  call    cs:__imp_EnterCriticalSection
0x18000c1fb  mov     ecx, [rdi-44h]
0x18000c1fe  test    cl, 1
0x18000c201  jz      short loc_18000C224
0x18000c203  mov     rcx, rbx; lpCriticalSection
0x18000c206  call    cs:__imp_LeaveCriticalSection
0x18000c20c  mov     eax, 6
0x18000c211  mov     rbx, [rsp+48h+arg_8]
0x18000c216  mov     rbp, [rsp+48h+arg_10]
0x18000c21b  add     rsp, 30h
0x18000c21f  pop     r14
0x18000c221  pop     rdi
0x18000c222  pop     rsi
0x18000c223  retn
0x18000c224  test    cl, 2
0x18000c227  jnz     loc_18000C30C
0x18000c22d  cmp     rdi, 10000h
0x18000c234  jb      loc_18000C348
0x18000c23a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c23e  jz      loc_18000C348
0x18000c244  cmp     rdi, cs:gdwMaxVirtualAddress
0x18000c24b  mov     eax, 0FFFFFFFFh
0x18000c250  ja      loc_18000C348
0x18000c256  cmp     rdi, rax
0x18000c259  jz      loc_18000C348
0x18000c25f  cmp     rdi, cs:gdwMinVirtualAddress
0x18000c266  jb      loc_18000C348
0x18000c26c  mov     [rsp+48h+arg_0], r15
0x18000c271  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000c278  lea     r15, [rdi-50h]
0x18000c27c  call    cs:__imp_EnterCriticalSection
0x18000c282  mov     rax, cs:pHandleList
0x18000c289  test    rax, rax
0x18000c28c  jz      short loc_18000C2B1
0x18000c28e  cmp     rax, r15
0x18000c291  jz      short loc_18000C298
0x18000c293  mov     rax, [rax]
0x18000c296  jmp     short loc_18000C289
0x18000c298  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000c29f  call    cs:__imp_LeaveCriticalSection
0x18000c2a5  xor     eax, eax
0x18000c2a7  cmp     dword ptr [r15+8], 3
0x18000c2ac  setz    al
0x18000c2af  jmp     short loc_18000C2D3
0x18000c2b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2b8  lea     rax, WPP_GLOBAL_Control
0x18000c2bf  cmp     rcx, rax
0x18000c2c2  jnz     short loc_18000C31F
0x18000c2c4  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000c2cb  call    cs:__imp_LeaveCriticalSection
0x18000c2d1  xor     eax, eax
0x18000c2d3  mov     r15, [rsp+48h+arg_0]
0x18000c2d8  test    eax, eax
0x18000c2da  jz      short loc_18000C348
0x18000c2dc  mov     rax, [rdi]
0x18000c2df  mov     r9, rbp
0x18000c2e2  mov     r8, [rdi+10h]
0x18000c2e6  mov     edx, r14d
0x18000c2e9  mov     ecx, [rdi+8]
0x18000c2ec  mov     [rsp+48h+var_28], rsi
0x18000c2f1  mov     rax, [rax+50h]
0x18000c2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2fa  mov     edi, eax
0x18000c2fc  mov     rcx, rbx; lpCriticalSection
0x18000c2ff  call    cs:__imp_LeaveCriticalSection
0x18000c305  mov     eax, edi
0x18000c307  jmp     loc_18000C211
0x18000c30c  mov     rcx, rbx; lpCriticalSection
0x18000c30f  call    cs:__imp_LeaveCriticalSection
0x18000c315  mov     eax, 0Ch
0x18000c31a  jmp     loc_18000C211
0x18000c31f  test    dword ptr [rcx+1Ch], 400000h
0x18000c326  jz      short loc_18000C2C4
0x18000c328  cmp     byte ptr [rcx+19h], 1
0x18000c32c  jb      short loc_18000C2C4
0x18000c32e  mov     rcx, [rcx+10h]
0x18000c332  lea     r8, WPP_b291d698302c3933274e905320ac47d5_Traceguids
0x18000c339  mov     edx, 0Ah
0x18000c33e  call    WPP_SF_
0x18000c343  jmp     loc_18000C2C4
0x18000c348  mov     edx, 9
0x18000c34d  mov     rcx, rdi
0x18000c350  call    ValidateHandle
0x18000c355  test    eax, eax
0x18000c357  jnz     short loc_18000C2DC
0x18000c359  mov     edx, 4
0x18000c35e  mov     rcx, rdi
0x18000c361  call    ValidateHandle
0x18000c366  test    eax, eax
0x18000c368  jnz     loc_18000C2DC
0x18000c36e  mov     edi, 5
0x18000c373  jmp     short loc_18000C2FC
```
