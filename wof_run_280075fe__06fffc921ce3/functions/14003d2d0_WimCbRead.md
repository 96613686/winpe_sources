# WimCbRead

- ea: `0x14003d2d0`
- end: `0x14003d459`
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
- `0x14003d2d0`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x14003d3b7`
- `ntoskrnl!KeQueryPriorityThread` at `0x14003d3b7`
- `FLTMGR!FltGetIoPriorityHintFromCallbackData` at `0x14003d3c9`
- `FLTMGR!FltGetIoPriorityHintFromCallbackData` at `0x14003d3c9`

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
0x14003d2d0  push    rbx
0x14003d2d2  push    rbp
0x14003d2d3  push    rsi
0x14003d2d4  push    rdi
0x14003d2d5  push    r12
0x14003d2d7  push    r14
0x14003d2d9  push    r15
0x14003d2db  sub     rsp, 30h
0x14003d2df  mov     r12, r9
0x14003d2e2  mov     [rsp+68h+Parameter], 0
0x14003d2eb  mov     r14, r8
0x14003d2ee  mov     r15, rcx
0x14003d2f1  xor     sil, sil
0x14003d2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d2fb  mov     eax, [rcx+2Ch]
0x14003d2fe  test    al, 20h
0x14003d300  jz      short loc_14003D31D
0x14003d302  cmp     byte ptr [rcx+29h], 4
0x14003d306  jb      short loc_14003D31D
0x14003d308  mov     rcx, [rcx+18h]
0x14003d30c  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x14003d313  mov     edx, 19h
0x14003d318  call    WPP_SF_
0x14003d31d  mov     rbp, [rsp+68h+arg_20]
0x14003d325  lea     r8, [rsp+68h+Parameter]
0x14003d32a  xor     edx, edx
0x14003d32c  mov     rcx, [rbp+18h]
0x14003d330  call    WimFSFAllocateReadCbReadParameters
0x14003d335  mov     rdi, [rsp+68h+Parameter]
0x14003d33a  mov     ebx, eax
0x14003d33c  test    eax, eax
0x14003d33e  jnz     loc_14003D3F4
0x14003d344  mov     bl, [rsp+68h+arg_28]
0x14003d34b  lea     esi, [rax+1]
0x14003d34e  mov     [rdi], r15
0x14003d351  mov     al, bl
0x14003d353  neg     al
0x14003d355  mov     rax, [rsp+68h+arg_30]
0x14003d35d  sbb     rcx, rcx
0x14003d360  and     rcx, r14
0x14003d363  mov     [rdi+8], rcx
0x14003d367  mov     [rdi+10h], r12
0x14003d36b  movups  xmm0, xmmword ptr [rbp+28h]
0x14003d36f  movups  xmmword ptr [rdi+20h], xmm0
0x14003d373  movsd   xmm1, qword ptr [rbp+38h]
0x14003d378  movsd   qword ptr [rdi+30h], xmm1
0x14003d37d  mov     [rdi+38h], bl
0x14003d380  mov     [rdi+40h], rax
0x14003d384  mov     rax, [rsp+68h+arg_40]
0x14003d38c  mov     [rdi+60h], rax
0x14003d390  mov     rax, [rsp+68h+arg_48]
0x14003d398  mov     [rdi+48h], rax
0x14003d39c  mov     eax, [rsp+68h+arg_38]
0x14003d3a3  mov     [rdi+58h], eax
0x14003d3a6  lea     rax, [rbp-40h]
0x14003d3aa  mov     [rdi+50h], rax
0x14003d3ae  mov     rcx, gs:188h; Thread
0x14003d3b7  call    cs:__imp_KeQueryPriorityThread
0x14003d3be  nop     dword ptr [rax+rax+00h]
0x14003d3c3  mov     rcx, r15; Data
0x14003d3c6  mov     [rdi+6Ch], eax
0x14003d3c9  call    cs:__imp_FltGetIoPriorityHintFromCallbackData
0x14003d3d0  nop     dword ptr [rax+rax+00h]
0x14003d3d5  mov     [rdi+68h], eax
0x14003d3d8  test    bl, bl
0x14003d3da  jz      short loc_14003D3E5
0x14003d3dc  test    r14, r14
0x14003d3df  jz      short loc_14003D3E5
0x14003d3e1  xor     eax, eax
0x14003d3e3  jmp     short loc_14003D3E7
0x14003d3e5  mov     eax, esi
0x14003d3e7  mov     rcx, rdi; Parameter
0x14003d3ea  mov     [rdi+78h], eax
0x14003d3ed  call    WimFSFReadWimResourceSwitchStacks
0x14003d3f2  mov     ebx, eax
0x14003d3f4  test    ebx, ebx
0x14003d3f6  js      short loc_14003D40E
0x14003d3f8  cmp     ebx, 103h
0x14003d3fe  jz      short loc_14003D40E
0x14003d400  mov     rax, [rsp+68h+arg_50]
0x14003d408  mov     edx, [rdi+5Ch]
0x14003d40b  mov     [rax], rdx
0x14003d40e  test    sil, sil
0x14003d411  jz      short loc_14003D41B
0x14003d413  mov     rcx, rdi
0x14003d416  call    WimFSFReleaseReadCbReadParameters
0x14003d41b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d422  mov     eax, [rcx+2Ch]
0x14003d425  test    al, 20h
0x14003d427  jz      short loc_14003D447
0x14003d429  cmp     byte ptr [rcx+29h], 4
0x14003d42d  jb      short loc_14003D447
0x14003d42f  mov     rcx, [rcx+18h]
0x14003d433  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x14003d43a  mov     edx, 1Ah
0x14003d43f  mov     r9d, ebx
0x14003d442  call    WPP_SF_d
0x14003d447  mov     eax, ebx
0x14003d449  add     rsp, 30h
0x14003d44d  pop     r15
0x14003d44f  pop     r14
0x14003d451  pop     r12
0x14003d453  pop     rdi
0x14003d454  pop     rsi
0x14003d455  pop     rbp
0x14003d456  pop     rbx
0x14003d457  retn
```
