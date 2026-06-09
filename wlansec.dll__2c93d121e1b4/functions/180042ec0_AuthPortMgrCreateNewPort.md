# AuthPortMgrCreateNewPort

- ea: `0x180042ec0`
- end: `0x180043195`
- name: `AuthPortMgrCreateNewPort`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180079fac`

## callees

- `0x18000431c`
- `0x1800063b0`
- `0x18000892c`
- `0x180008998`
- `0x180042ec0`
- `0x18007c1b0`
- `0x18007c308`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180043005`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180043005`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180042ff9`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180042ff9`
- `api-ms-win-crt-time-l1-1-0!_time32` at `0x180042fea`
- `api-ms-win-crt-time-l1-1-0!_time32` at `0x180042fea`
- `MobileNetworking!ReleaseWriteLock` at `0x18004311b`
- `MobileNetworking!ReleaseWriteLock` at `0x18004311b`
- `MobileNetworking!AllocateMemory` at `0x180042f83`
- `MobileNetworking!AllocateMemory` at `0x180042f83`
- `MobileNetworking!FreeMemory` at `0x180043091`
- `MobileNetworking!FreeMemory` at `0x180043091`
- `MobileNetworking!AcquireWriteLock` at `0x1800430c5`
- `MobileNetworking!AcquireWriteLock` at `0x1800430c5`

## string_xrefs

- `0x180042f73`: `AuthPortMgrCreateNewPort`
- `0x180043086`: `AuthPortMgrCreateNewPort`
- `0x1800430b0`: `AuthPortMgrCreateNewPort`
- `0x1800430ef`: `AuthPortMgrCreateNewPort`

## pseudocode

```c
__int64 __fastcall AuthPortMgrCreateNewPort(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // esi
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int inited; // eax
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v16; // [rsp+90h] [rbp+58h] BYREF

  v16 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids);
  if ( !*a3 || (unsigned int)AuthPortMgrFindInGlobalListAndRemove(*a3, 0) )
  {
    *a3 = 0;
    v8 = AllocateMemory(304, &v16, "AuthPortMgrCreateNewPort", 68);
    v6 = v8;
    if ( v8 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_25;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v8);
    }
    else
    {
      *(_DWORD *)(v16 + 132) = _InterlockedIncrement((volatile signed __int32 *)&qword_1800BB588);
      v9 = *(_DWORD *)(v16 + 132);
      LODWORD(v10) = _time32(0);
      _o_srand(v10);
      *(_BYTE *)(v16 + 296) = rand() % 256;
      *(_QWORD *)(v16 + 272) = a1;
      v11 = v16;
      *(_DWORD *)(v16 + 297) = *(_DWORD *)a2;
      *(_WORD *)(v11 + 301) = *(_WORD *)(a2 + 4);
      inited = AuthPortMgrInitPort(v16);
      v6 = inited;
      if ( !inited )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 16));
        AcquireWriteLock(&g_WcnOneXInfo, qword_1800BB520, "AuthPortMgrCreateNewPort", 94);
        v13 = (__int64 *)qword_1800BB518;
        if ( *(__int64 **)qword_1800BB518 != &qword_1800BB510 )
          __fastfail(3u);
        v14 = v16;
        *(_QWORD *)v16 = &qword_1800BB510;
        *(_QWORD *)(v14 + 8) = v13;
        *v13 = v14;
        qword_1800BB518 = v14;
        ReleaseWriteLock(&g_WcnOneXInfo, qword_1800BB520, "AuthPortMgrCreateNewPort", 96);
        _InterlockedIncrement((_DWORD *)&qword_1800BB588 + 1);
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v9);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        *a3 = v16;
        goto LABEL_25;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v9, inited);
      FreeMemory(&v16, "AuthPortMgrCreateNewPort", 113);
    }
    goto LABEL_9;
  }
  v6 = 1247;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, *a3);
LABEL_9:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_25:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
    WPP_SF_d(v7[2], 15, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180042ec0  push    rbp
0x180042ec2  push    rbx
0x180042ec3  push    rsi
0x180042ec4  push    rdi
0x180042ec5  push    r12
0x180042ec7  push    r13
0x180042ec9  push    r14
0x180042ecb  push    r15
0x180042ecd  mov     rbp, rsp
0x180042ed0  sub     rsp, 38h
0x180042ed4  mov     rdi, r8
0x180042ed7  mov     [rbp+arg_10], 0
0x180042edf  mov     r14, rdx
0x180042ee2  mov     r15, rcx
0x180042ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180042eec  lea     r12, WPP_GLOBAL_Control
0x180042ef3  lea     r13, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x180042efa  cmp     rcx, r12
0x180042efd  jz      short loc_180042F16
0x180042eff  test    byte ptr [rcx+1Ch], 1
0x180042f03  jz      short loc_180042F16
0x180042f05  mov     rcx, [rcx+10h]
0x180042f09  mov     edx, 0Ah
0x180042f0e  mov     r8, r13
0x180042f11  call    WPP_SF_
0x180042f16  mov     rcx, [rdi]
0x180042f19  test    rcx, rcx
0x180042f1c  jz      short loc_180042F66
0x180042f1e  xor     edx, edx
0x180042f20  call    AuthPortMgrFindInGlobalListAndRemove
0x180042f25  test    eax, eax
0x180042f27  jnz     short loc_180042F66
0x180042f29  mov     ebx, 4DFh
0x180042f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f35  cmp     rcx, r12
0x180042f38  jz      loc_180043181
0x180042f3e  test    byte ptr [rcx+1Ch], 2
0x180042f42  jz      loc_180043162
0x180042f48  mov     r9, [rdi]
0x180042f4b  lea     edx, [rax+0Bh]
0x180042f4e  mov     rcx, [rcx+10h]
0x180042f52  mov     r8, r13
0x180042f55  call    WPP_SF_q
0x180042f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f61  jmp     loc_180043162
0x180042f66  mov     r9d, 44h ; 'D'
0x180042f6c  mov     qword ptr [rdi], 0
0x180042f73  lea     r8, aAuthportmgrcre; "AuthPortMgrCreateNewPort"
0x180042f7a  mov     ecx, 130h
0x180042f7f  lea     rdx, [rbp+arg_10]
0x180042f83  call    cs:__imp_AllocateMemory
0x180042f8a  nop     dword ptr [rax+rax+00h]
0x180042f8f  mov     ebx, eax
0x180042f91  test    eax, eax
0x180042f93  jz      short loc_180042FC5
0x180042f95  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f9c  cmp     rcx, r12
0x180042f9f  jz      loc_180043181
0x180042fa5  test    byte ptr [rcx+1Ch], 2
0x180042fa9  jz      loc_180043162
0x180042faf  mov     rcx, [rcx+10h]
0x180042fb3  mov     edx, 0Ch
0x180042fb8  mov     r9d, eax
0x180042fbb  mov     r8, r13
0x180042fbe  call    WPP_SF_d
0x180042fc3  jmp     short loc_180042F5A
0x180042fc5  mov     rcx, [rbp+arg_10]
0x180042fc9  mov     eax, 1
0x180042fce  lock xadd dword ptr cs:qword_1800BB588, eax
0x180042fd6  inc     eax
0x180042fd8  mov     [rcx+84h], eax
0x180042fde  xor     ecx, ecx; Time
0x180042fe0  mov     rax, [rbp+arg_10]
0x180042fe4  mov     esi, [rax+84h]
0x180042fea  call    cs:__imp__time32
0x180042ff1  nop     dword ptr [rax+rax+00h]
0x180042ff6  mov     rcx, rax
0x180042ff9  call    cs:__imp__o_srand
0x180043000  nop     dword ptr [rax+rax+00h]
0x180043005  call    cs:__imp_rand
0x18004300c  nop     dword ptr [rax+rax+00h]
0x180043011  cdq
0x180043012  mov     ecx, 100h
0x180043017  idiv    ecx
0x180043019  mov     rax, [rbp+arg_10]
0x18004301d  mov     [rax+128h], dl
0x180043023  mov     rax, [rbp+arg_10]
0x180043027  mov     [rax+110h], r15
0x18004302e  mov     rcx, [rbp+arg_10]
0x180043032  mov     eax, [r14]
0x180043035  mov     [rcx+129h], eax
0x18004303b  movzx   eax, word ptr [r14+4]
0x180043040  mov     [rcx+12Dh], ax
0x180043047  mov     rcx, [rbp+arg_10]
0x18004304b  call    AuthPortMgrInitPort
0x180043050  mov     ebx, eax
0x180043052  test    eax, eax
0x180043054  jz      short loc_1800430A2
0x180043056  mov     rcx, cs:WPP_GLOBAL_Control
0x18004305d  cmp     rcx, r12
0x180043060  jz      short loc_180043080
0x180043062  test    byte ptr [rcx+1Ch], 2
0x180043066  jz      short loc_180043080
0x180043068  mov     rcx, [rcx+10h]
0x18004306c  mov     edx, 0Dh
0x180043071  mov     r9d, esi
0x180043074  mov     [rsp+38h+var_18], eax
0x180043078  mov     r8, r13
0x18004307b  call    WPP_SF_dd
0x180043080  mov     r8d, 71h ; 'q'
0x180043086  lea     rdx, aAuthportmgrcre; "AuthPortMgrCreateNewPort"
0x18004308d  lea     rcx, [rbp+arg_10]
0x180043091  call    cs:__imp_FreeMemory
0x180043098  nop     dword ptr [rax+rax+00h]
0x18004309d  jmp     loc_180042F5A
0x1800430a2  mov     rax, [rbp+arg_10]
0x1800430a6  lock inc dword ptr [rax+10h]
0x1800430aa  mov     r9d, 5Eh ; '^'
0x1800430b0  lea     r8, aAuthportmgrcre; "AuthPortMgrCreateNewPort"
0x1800430b7  lea     rdx, qword_1800BB520
0x1800430be  lea     rcx, g_WcnOneXInfo
0x1800430c5  call    cs:__imp_AcquireWriteLock
0x1800430cc  nop     dword ptr [rax+rax+00h]
0x1800430d1  mov     rcx, cs:qword_1800BB518
0x1800430d8  lea     rdx, qword_1800BB510
0x1800430df  cmp     [rcx], rdx
0x1800430e2  jz      short loc_1800430EB
0x1800430e4  mov     ecx, 3
0x1800430e9  int     29h; Win8: RtlFailFast(ecx)
0x1800430eb  mov     rax, [rbp+arg_10]
0x1800430ef  lea     r8, aAuthportmgrcre; "AuthPortMgrCreateNewPort"
0x1800430f6  mov     r9d, 60h ; '`'
0x1800430fc  mov     [rax], rdx
0x1800430ff  lea     rdx, qword_1800BB520
0x180043106  mov     [rax+8], rcx
0x18004310a  mov     [rcx], rax
0x18004310d  lea     rcx, g_WcnOneXInfo
0x180043114  mov     cs:qword_1800BB518, rax
0x18004311b  call    cs:__imp_ReleaseWriteLock
0x180043122  nop     dword ptr [rax+rax+00h]
0x180043127  lock inc dword ptr cs:qword_1800BB588+4
0x18004312e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043135  cmp     rcx, r12
0x180043138  jz      short loc_18004315B
0x18004313a  test    byte ptr [rcx+1Ch], 1
0x18004313e  jz      short loc_18004315B
0x180043140  mov     rcx, [rcx+10h]
0x180043144  mov     edx, 0Eh
0x180043149  mov     r9d, esi
0x18004314c  mov     r8, r13
0x18004314f  call    WPP_SF_d
0x180043154  mov     rcx, cs:WPP_GLOBAL_Control
0x18004315b  mov     rax, [rbp+arg_10]
0x18004315f  mov     [rdi], rax
0x180043162  cmp     rcx, r12
0x180043165  jz      short loc_180043181
0x180043167  test    byte ptr [rcx+1Ch], 1
0x18004316b  jz      short loc_180043181
0x18004316d  mov     rcx, [rcx+10h]
0x180043171  mov     edx, 0Fh
0x180043176  mov     r9d, ebx
0x180043179  mov     r8, r13
0x18004317c  call    WPP_SF_d
0x180043181  mov     eax, ebx
0x180043183  add     rsp, 38h
0x180043187  pop     r15
0x180043189  pop     r14
0x18004318b  pop     r13
0x18004318d  pop     r12
0x18004318f  pop     rdi
0x180043190  pop     rsi
0x180043191  pop     rbx
0x180043192  pop     rbp
0x180043193  retn
```
