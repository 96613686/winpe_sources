# WimCbRead

- ea: `0x14003d320`
- end: `0x14003d4a9`
- name: `WimCbRead`
- size: `393`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA Data@<rcx>, __int64, char, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000c20c`
- `0x14000d3b8`
- `0x14000fb60`
- `0x140010758`
- `0x140022544`
- `0x14003d320`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x14003d407`
- `ntoskrnl!KeQueryPriorityThread` at `0x14003d407`
- `FLTMGR!FltGetIoPriorityHintFromCallbackData` at `0x14003d419`
- `FLTMGR!FltGetIoPriorityHintFromCallbackData` at `0x14003d419`

## pseudocode

```c
__int64 __fastcall WimCbRead(
        PFLT_CALLBACK_DATA Data,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        int a8,
        __int64 a9,
        __int64 a10,
        _QWORD *a11)
{
  char v14; // si
  int Parameters; // eax
  _QWORD *v16; // rdi
  int v17; // ebx
  BOOL v18; // eax
  PVOID Parameter[9]; // [rsp+20h] [rbp-48h] BYREF

  Parameter[0] = 0;
  v14 = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids);
  Parameters = WimFSFAllocateReadCbReadParameters(*(_QWORD *)(a5 + 24), 0, Parameter);
  v16 = Parameter[0];
  v17 = Parameters;
  if ( !Parameters )
  {
    v14 = 1;
    *(_QWORD *)Parameter[0] = Data;
    v16[1] = a3 & -(__int64)(a6 != 0);
    v16[2] = a4;
    *((_OWORD *)v16 + 2) = *(_OWORD *)(a5 + 40);
    v16[6] = *(_QWORD *)(a5 + 56);
    *((_BYTE *)v16 + 56) = a6;
    v16[8] = a7;
    v16[12] = a9;
    v16[9] = a10;
    *((_DWORD *)v16 + 22) = a8;
    v16[10] = a5 - 64;
    *((_DWORD *)v16 + 27) = KeQueryPriorityThread(KeGetCurrentThread());
    *((_DWORD *)v16 + 26) = FltGetIoPriorityHintFromCallbackData(Data);
    v18 = !a6 || !a3;
    *((_DWORD *)v16 + 30) = v18;
    v17 = WimFSFReadWimResourceSwitchStacks(v16);
  }
  if ( v17 >= 0 && v17 != 259 )
    *a11 = *((unsigned int *)v16 + 23);
  if ( v14 )
    WimFSFReleaseReadCbReadParameters(v16);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids, (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14003d320  push    rbx
0x14003d322  push    rbp
0x14003d323  push    rsi
0x14003d324  push    rdi
0x14003d325  push    r12
0x14003d327  push    r14
0x14003d329  push    r15
0x14003d32b  sub     rsp, 30h
0x14003d32f  mov     r12, r9
0x14003d332  mov     [rsp+68h+Parameter], 0
0x14003d33b  mov     r14, r8
0x14003d33e  mov     r15, rcx
0x14003d341  xor     sil, sil
0x14003d344  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d34b  mov     eax, [rcx+2Ch]
0x14003d34e  test    al, 20h
0x14003d350  jz      short loc_14003D36D
0x14003d352  cmp     byte ptr [rcx+29h], 4
0x14003d356  jb      short loc_14003D36D
0x14003d358  mov     rcx, [rcx+18h]
0x14003d35c  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x14003d363  mov     edx, 19h
0x14003d368  call    WPP_SF_
0x14003d36d  mov     rbp, [rsp+68h+arg_20]
0x14003d375  lea     r8, [rsp+68h+Parameter]
0x14003d37a  xor     edx, edx
0x14003d37c  mov     rcx, [rbp+18h]
0x14003d380  call    WimFSFAllocateReadCbReadParameters
0x14003d385  mov     rdi, [rsp+68h+Parameter]
0x14003d38a  mov     ebx, eax
0x14003d38c  test    eax, eax
0x14003d38e  jnz     loc_14003D444
0x14003d394  mov     bl, [rsp+68h+arg_28]
0x14003d39b  lea     esi, [rax+1]
0x14003d39e  mov     [rdi], r15
0x14003d3a1  mov     al, bl
0x14003d3a3  neg     al
0x14003d3a5  mov     rax, [rsp+68h+arg_30]
0x14003d3ad  sbb     rcx, rcx
0x14003d3b0  and     rcx, r14
0x14003d3b3  mov     [rdi+8], rcx
0x14003d3b7  mov     [rdi+10h], r12
0x14003d3bb  movups  xmm0, xmmword ptr [rbp+28h]
0x14003d3bf  movups  xmmword ptr [rdi+20h], xmm0
0x14003d3c3  movsd   xmm1, qword ptr [rbp+38h]
0x14003d3c8  movsd   qword ptr [rdi+30h], xmm1
0x14003d3cd  mov     [rdi+38h], bl
0x14003d3d0  mov     [rdi+40h], rax
0x14003d3d4  mov     rax, [rsp+68h+arg_40]
0x14003d3dc  mov     [rdi+60h], rax
0x14003d3e0  mov     rax, [rsp+68h+arg_48]
0x14003d3e8  mov     [rdi+48h], rax
0x14003d3ec  mov     eax, [rsp+68h+arg_38]
0x14003d3f3  mov     [rdi+58h], eax
0x14003d3f6  lea     rax, [rbp-40h]
0x14003d3fa  mov     [rdi+50h], rax
0x14003d3fe  mov     rcx, gs:188h; Thread
0x14003d407  call    cs:__imp_KeQueryPriorityThread
0x14003d40e  nop     dword ptr [rax+rax+00h]
0x14003d413  mov     rcx, r15; Data
0x14003d416  mov     [rdi+6Ch], eax
0x14003d419  call    cs:__imp_FltGetIoPriorityHintFromCallbackData
0x14003d420  nop     dword ptr [rax+rax+00h]
0x14003d425  mov     [rdi+68h], eax
0x14003d428  test    bl, bl
0x14003d42a  jz      short loc_14003D435
0x14003d42c  test    r14, r14
0x14003d42f  jz      short loc_14003D435
0x14003d431  xor     eax, eax
0x14003d433  jmp     short loc_14003D437
0x14003d435  mov     eax, esi
0x14003d437  mov     rcx, rdi; Parameter
0x14003d43a  mov     [rdi+78h], eax
0x14003d43d  call    WimFSFReadWimResourceSwitchStacks
0x14003d442  mov     ebx, eax
0x14003d444  test    ebx, ebx
0x14003d446  js      short loc_14003D45E
0x14003d448  cmp     ebx, 103h
0x14003d44e  jz      short loc_14003D45E
0x14003d450  mov     rax, [rsp+68h+arg_50]
0x14003d458  mov     edx, [rdi+5Ch]
0x14003d45b  mov     [rax], rdx
0x14003d45e  test    sil, sil
0x14003d461  jz      short loc_14003D46B
0x14003d463  mov     rcx, rdi
0x14003d466  call    WimFSFReleaseReadCbReadParameters
0x14003d46b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d472  mov     eax, [rcx+2Ch]
0x14003d475  test    al, 20h
0x14003d477  jz      short loc_14003D497
0x14003d479  cmp     byte ptr [rcx+29h], 4
0x14003d47d  jb      short loc_14003D497
0x14003d47f  mov     rcx, [rcx+18h]
0x14003d483  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x14003d48a  mov     edx, 1Ah
0x14003d48f  mov     r9d, ebx
0x14003d492  call    WPP_SF_d
0x14003d497  mov     eax, ebx
0x14003d499  add     rsp, 30h
0x14003d49d  pop     r15
0x14003d49f  pop     r14
0x14003d4a1  pop     r12
0x14003d4a3  pop     rdi
0x14003d4a4  pop     rsi
0x14003d4a5  pop     rbp
0x14003d4a6  pop     rbx
0x14003d4a7  retn
```
