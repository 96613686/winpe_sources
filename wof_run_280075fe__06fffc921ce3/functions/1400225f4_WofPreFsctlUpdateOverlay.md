# WofPreFsctlUpdateOverlay

- ea: `0x1400225f4`
- end: `0x14002273f`
- name: `WofPreFsctlUpdateOverlay`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400346f0`

## callees

- `0x1400014d0`
- `0x140011640`
- `0x1400225f4`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140022709`
- `FLTMGR!FltReleaseContext` at `0x140022709`

## pseudocode

```c
__int64 __fastcall WofPreFsctlUpdateOverlay(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v6; // r15d
  unsigned int v7; // ebp
  int v8; // ebx
  _DWORD *v9; // rbx
  __int64 v10; // rax
  int v11; // r12d
  __int64 v12; // rdx
  __int64 (__fastcall *v13)(__int64, char *, _DWORD *, _QWORD, _QWORD, int, __int64 *); // r10
  __int64 v14; // rcx
  __int64 result; // rax
  PFLT_CONTEXT Context; // [rsp+70h] [rbp+8h] BYREF
  __int64 v17; // [rsp+80h] [rbp+18h] BYREF

  v17 = a3;
  v3 = *(_QWORD *)(a1 + 16);
  LODWORD(v17) = 0;
  Context = 0;
  v6 = *(_DWORD *)(v3 + 32);
  if ( v6 >= 8 )
  {
    v9 = *(_DWORD **)(v3 + 48);
    v7 = 5;
    if ( *v9 == 1
      && (v10 = (unsigned int)v9[1], (unsigned int)v10 < 4)
      && *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v10)
      && (v11 = *(_DWORD *)(v3 + 24), (int)WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context) >= 0) )
    {
      v12 = 424LL * (unsigned int)v9[1];
      v7 = 4;
      v13 = *(__int64 (__fastcall **)(__int64, char *, _DWORD *, _QWORD, _QWORD, int, __int64 *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                                + v12
                                                                                                + 64);
      if ( v13 && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x400000) != 0 )
        v8 = v13(
               a1,
               (char *)Context + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v12 + 20),
               v9 + 2,
               v6 - 8,
               *(_QWORD *)(v3 + 48),
               v11,
               &v17);
      else
        v8 = -1073741637;
    }
    else
    {
      v8 = 0;
    }
    if ( Context )
      FltReleaseContext(Context);
  }
  else
  {
    v7 = 4;
    v8 = -1073741811;
  }
  v14 = (unsigned int)v17;
  *(_DWORD *)(a1 + 24) = v8;
  result = v7;
  *(_QWORD *)(a1 + 32) = v14;
  return result;
}

```

## disassembly

```asm
0x1400225f4  mov     rax, rsp
0x1400225f7  mov     [rax+10h], rbx
0x1400225fb  mov     [rax+20h], rbp
0x1400225ff  mov     [rax+18h], r8
0x140022603  push    rsi
0x140022604  push    rdi
0x140022605  push    r12
0x140022607  push    r14
0x140022609  push    r15
0x14002260b  sub     rsp, 40h
0x14002260f  mov     rsi, [rcx+10h]
0x140022613  mov     r14, rdx
0x140022616  mov     dword ptr [rax+18h], 0
0x14002261d  mov     rdi, rcx
0x140022620  mov     qword ptr [rax+8], 0
0x140022628  mov     r15d, [rsi+20h]
0x14002262c  cmp     r15d, 8
0x140022630  jnb     short loc_140022641
0x140022632  mov     ebp, 4
0x140022637  mov     ebx, 0C000000Dh
0x14002263c  jmp     loc_140022715
0x140022641  mov     rbx, [rsi+30h]
0x140022645  mov     ebp, 5
0x14002264a  cmp     dword ptr [rbx], 1
0x14002264d  jnz     loc_1400226FD
0x140022653  mov     eax, [rbx+4]
0x140022656  cmp     eax, 4
0x140022659  jnb     loc_1400226FD
0x14002265f  imul    rcx, rax, 1A8h
0x140022666  lea     rax, WPP_MAIN_CB.Queue+10h
0x14002266d  cmp     byte ptr [rcx+rax], 0
0x140022671  jz      loc_1400226FD
0x140022677  mov     rcx, [r14+18h]; Instance
0x14002267b  lea     rdx, [rsp+68h+Context]
0x140022680  mov     r12d, [rsi+18h]
0x140022684  call    WofGetVolumeContext
0x140022689  test    eax, eax
0x14002268b  js      short loc_1400226FD
0x14002268d  mov     eax, [rbx+4]
0x140022690  lea     r11, WPP_MAIN_CB.Queue+10h
0x140022697  imul    rdx, rax, 1A8h
0x14002269e  mov     ebp, 4
0x1400226a3  mov     r10, [rdx+r11+40h]
0x1400226a8  test    r10, r10
0x1400226ab  jnz     short loc_1400226B4
0x1400226ad  mov     ebx, 0C00000BBh
0x1400226b2  jmp     short loc_1400226FF
0x1400226b4  mov     rax, [r14+20h]
0x1400226b8  test    dword ptr [rax+50h], 400000h
0x1400226bf  jz      short loc_1400226AD
0x1400226c1  mov     edx, [rdx+r11+14h]
0x1400226c6  lea     rax, [rsp+68h+arg_10]
0x1400226ce  add     rdx, [rsp+68h+Context]
0x1400226d3  lea     r9d, [r15-8]
0x1400226d7  mov     [rsp+68h+var_38], rax
0x1400226dc  lea     r8, [rbx+8]
0x1400226e0  mov     rax, [rsi+30h]
0x1400226e4  mov     rcx, rdi
0x1400226e7  mov     [rsp+68h+var_40], r12d
0x1400226ec  mov     [rsp+68h+var_48], rax
0x1400226f1  mov     rax, r10
0x1400226f4  call    _guard_dispatch_icall
0x1400226f9  mov     ebx, eax
0x1400226fb  jmp     short loc_1400226FF
0x1400226fd  xor     ebx, ebx
0x1400226ff  mov     rcx, [rsp+68h+Context]; Context
0x140022704  test    rcx, rcx
0x140022707  jz      short loc_140022715
0x140022709  call    cs:__imp_FltReleaseContext
0x140022710  nop     dword ptr [rax+rax+00h]
0x140022715  mov     ecx, dword ptr [rsp+68h+arg_10]
0x14002271c  lea     r11, [rsp+68h+var_28]
0x140022721  mov     [rdi+18h], ebx
0x140022724  mov     eax, ebp
0x140022726  mov     rbx, [r11+38h]
0x14002272a  mov     rbp, [r11+48h]
0x14002272e  mov     [rdi+20h], rcx
0x140022732  mov     rsp, r11
0x140022735  pop     r15
0x140022737  pop     r14
0x140022739  pop     r12
0x14002273b  pop     rdi
0x14002273c  pop     rsi
0x14002273d  retn
```
