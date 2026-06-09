# WofPreFsctlRemoveOverlay

- ea: `0x1400247b0`
- end: `0x140024921`
- name: `WofPreFsctlRemoveOverlay`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400346f0`

## callees

- `0x1400014d0`
- `0x14000e7d8`
- `0x14000f45c`
- `0x140011640`
- `0x1400247b0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140024880`
- `FLTMGR!FltReleaseContext` at `0x140024880`

## pseudocode

```c
__int64 __fastcall WofPreFsctlRemoveOverlay(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v6; // r15d
  unsigned int v7; // ebp
  int v8; // ebx
  _DWORD *v9; // rbx
  __int64 v10; // rax
  int v11; // r12d
  int VolumeContext; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  int IfrLog; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rcx
  __int64 result; // rax
  __int64 v21; // r9
  __int64 (__fastcall *v22)(char *, _DWORD *, _QWORD, _QWORD, int, __int64 *); // r10
  PFLT_CONTEXT Context; // [rsp+70h] [rbp+8h] BYREF
  __int64 v24; // [rsp+80h] [rbp+18h] BYREF

  v24 = a3;
  v3 = *(_QWORD *)(a1 + 16);
  LODWORD(v24) = 0;
  Context = 0;
  v6 = *(_DWORD *)(v3 + 32);
  if ( v6 < 8 )
  {
    v7 = 4;
    v8 = -1073741811;
    goto LABEL_12;
  }
  v9 = *(_DWORD **)(v3 + 48);
  v7 = 5;
  if ( *v9 == 1 )
  {
    v10 = (unsigned int)v9[1];
    if ( (unsigned int)v10 < 4 )
    {
      if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v10) )
      {
        v11 = *(_DWORD *)(v3 + 24);
        VolumeContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
        if ( VolumeContext >= 0 )
        {
          v21 = 424LL * (unsigned int)v9[1];
          v7 = 4;
          v22 = *(__int64 (__fastcall **)(char *, _DWORD *, _QWORD, _QWORD, int, __int64 *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                           + v21
                                                                                           + 48);
          if ( v22 && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x400000) != 0 )
            v8 = v22(
                   (char *)Context + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v21 + 20),
                   v9 + 2,
                   v6 - 8,
                   *(_QWORD *)(v3 + 48),
                   v11,
                   &v24);
          else
            v8 = -1073741637;
          goto LABEL_10;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          IfrLog = WofGetIfrLog(v13, (unsigned int)VolumeContext, v14, 28);
          WPP_RECORDER_SF_qdd(IfrLog, v16, v17, v18);
        }
      }
    }
  }
  v8 = 0;
LABEL_10:
  if ( Context )
    FltReleaseContext(Context);
LABEL_12:
  v19 = (unsigned int)v24;
  *(_DWORD *)(a1 + 24) = v8;
  result = v7;
  *(_QWORD *)(a1 + 32) = v19;
  return result;
}

```

## disassembly

```asm
0x1400247b0  mov     rax, rsp
0x1400247b3  mov     [rax+10h], rbx
0x1400247b7  mov     [rax+20h], rbp
0x1400247bb  mov     [rax+18h], r8
0x1400247bf  push    rsi
0x1400247c0  push    rdi
0x1400247c1  push    r12
0x1400247c3  push    r14
0x1400247c5  push    r15
0x1400247c7  sub     rsp, 40h
0x1400247cb  mov     rsi, [rcx+10h]
0x1400247cf  mov     r14, rdx
0x1400247d2  mov     dword ptr [rax+18h], 0
0x1400247d9  mov     rdi, rcx
0x1400247dc  mov     qword ptr [rax+8], 0
0x1400247e4  mov     r15d, [rsi+20h]
0x1400247e8  cmp     r15d, 8
0x1400247ec  jnb     short loc_1400247FD
0x1400247ee  mov     ebp, 4
0x1400247f3  mov     ebx, 0C000000Dh
0x1400247f8  jmp     loc_14002488C
0x1400247fd  mov     rbx, [rsi+30h]
0x140024801  mov     ebp, 5
0x140024806  cmp     dword ptr [rbx], 1
0x140024809  jnz     short loc_140024874
0x14002480b  mov     eax, [rbx+4]
0x14002480e  cmp     eax, 4
0x140024811  jnb     short loc_140024874
0x140024813  imul    rcx, rax, 1A8h
0x14002481a  lea     rax, WPP_MAIN_CB.Queue+10h
0x140024821  cmp     byte ptr [rcx+rax], 0
0x140024825  jz      short loc_140024874
0x140024827  mov     rcx, [r14+18h]; Instance
0x14002482b  lea     rdx, [rsp+68h+Context]
0x140024830  mov     r12d, [rsi+18h]
0x140024834  call    WofGetVolumeContext
0x140024839  mov     edx, eax
0x14002483b  test    eax, eax
0x14002483d  jns     short loc_1400248B6
0x14002483f  lea     rax, WPP_RECORDER_INITIALIZED
0x140024846  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002484d  jz      short loc_140024874
0x14002484f  lea     r9d, [rbp+17h]
0x140024853  call    WofGetIfrLog
0x140024858  mov     rcx, rax
0x14002485b  mov     [rsp+68h+var_30], edx
0x14002485f  mov     eax, [rbx+4]
0x140024862  mov     [rsp+68h+var_38], eax
0x140024866  mov     rax, [r14+18h]
0x14002486a  mov     [rsp+68h+var_40], rax
0x14002486f  call    WPP_RECORDER_SF_qdd
0x140024874  xor     ebx, ebx
0x140024876  mov     rcx, [rsp+68h+Context]; Context
0x14002487b  test    rcx, rcx
0x14002487e  jz      short loc_14002488C
0x140024880  call    cs:__imp_FltReleaseContext
0x140024887  nop     dword ptr [rax+rax+00h]
0x14002488c  mov     ecx, dword ptr [rsp+68h+arg_10]
0x140024893  lea     r11, [rsp+68h+var_28]
0x140024898  mov     [rdi+18h], ebx
0x14002489b  mov     eax, ebp
0x14002489d  mov     rbx, [r11+38h]
0x1400248a1  mov     rbp, [r11+48h]
0x1400248a5  mov     [rdi+20h], rcx
0x1400248a9  mov     rsp, r11
0x1400248ac  pop     r15
0x1400248ae  pop     r14
0x1400248b0  pop     r12
0x1400248b2  pop     rdi
0x1400248b3  pop     rsi
0x1400248b4  retn
0x1400248b6  mov     eax, [rbx+4]
0x1400248b9  lea     r11, WPP_MAIN_CB.Queue+10h
0x1400248c0  imul    r9, rax, 1A8h
0x1400248c7  mov     ebp, 4
0x1400248cc  mov     r10, [r9+r11+30h]
0x1400248d1  test    r10, r10
0x1400248d4  jnz     short loc_1400248DD
0x1400248d6  mov     ebx, 0C00000BBh
0x1400248db  jmp     short loc_140024876
0x1400248dd  mov     rax, [r14+20h]
0x1400248e1  test    dword ptr [rax+50h], 400000h
0x1400248e8  jz      short loc_1400248D6
0x1400248ea  mov     ecx, [r9+r11+14h]
0x1400248ef  lea     rax, [rsp+68h+arg_10]
0x1400248f7  add     rcx, [rsp+68h+Context]
0x1400248fc  lea     r8d, [r15-8]
0x140024900  mov     r9, [rsi+30h]
0x140024904  lea     rdx, [rbx+8]
0x140024908  mov     [rsp+68h+var_40], rax
0x14002490d  mov     rax, r10
0x140024910  mov     [rsp+68h+var_48], r12d
0x140024915  call    _guard_dispatch_icall
0x14002491a  mov     ebx, eax
0x14002491c  jmp     loc_140024876
```
