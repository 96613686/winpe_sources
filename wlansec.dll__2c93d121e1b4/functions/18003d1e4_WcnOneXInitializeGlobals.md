# WcnOneXInitializeGlobals

- ea: `0x18003d1e4`
- end: `0x18003d34a`
- name: `WcnOneXInitializeGlobals`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007a2e4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18003d1e4`

## import_xrefs

- `MobileNetworking!CreateReadWriteLock` at `0x18003d2d6`
- `MobileNetworking!CreateReadWriteLock` at `0x18003d2d6`

## pseudocode

```c
__int64 __fastcall WcnOneXInitializeGlobals(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  __int128 v4; // xmm0
  __int64 v5; // xmm1_8
  unsigned int v6; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v4 = *(_OWORD *)a1;
    qword_1800BB504 = 0;
    v5 = *(_QWORD *)(a1 + 16);
    qword_1800BB5B0 = (__int64)WcnOneXSendEapPacket;
    qword_1800BB5B8 = (__int64)WcnOneXStopEapSession;
    qword_1800BB518 = (__int64)&qword_1800BB510;
    qword_1800BB510 = (__int64)&qword_1800BB510;
    xmmword_1800BB590 = v4;
    qword_1800BB5A0 = v5;
    qword_1800BB588 = 0;
    qword_1800BB5A8 = 0;
    hLibModule = 0;
    v6 = CreateReadWriteLock(qword_1800BB520);
    v3 = v6;
    if ( v6 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_13;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids, v6);
    }
    goto LABEL_12;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    WPP_SF_(v2[2], 11, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids);
LABEL_12:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_13:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_d(v2[2], 13, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18003d1e4  mov     [rsp+arg_0], rbx
0x18003d1e9  push    rsi
0x18003d1ea  sub     rsp, 20h
0x18003d1ee  mov     rbx, rcx
0x18003d1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d1f8  lea     rsi, WPP_GLOBAL_Control
0x18003d1ff  cmp     rcx, rsi
0x18003d202  jz      short loc_18003D226
0x18003d204  test    byte ptr [rcx+1Ch], 1
0x18003d208  jz      short loc_18003D226
0x18003d20a  mov     rcx, [rcx+10h]
0x18003d20e  lea     r8, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids
0x18003d215  mov     edx, 0Ah
0x18003d21a  call    WPP_SF_
0x18003d21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d226  test    rbx, rbx
0x18003d229  jnz     short loc_18003D25B
0x18003d22b  mov     ebx, 57h ; 'W'
0x18003d230  cmp     rcx, rsi
0x18003d233  jz      loc_18003D33C
0x18003d239  test    byte ptr [rcx+1Ch], 4
0x18003d23d  jz      loc_18003D319
0x18003d243  mov     rcx, [rcx+10h]
0x18003d247  lea     edx, [rbx-4Ch]
0x18003d24a  lea     r8, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids
0x18003d251  call    WPP_SF_
0x18003d256  jmp     loc_18003D312
0x18003d25b  movups  xmm0, xmmword ptr [rbx]
0x18003d25e  lea     rax, WcnOneXSendEapPacket
0x18003d265  mov     cs:qword_1800BB504, 0
0x18003d270  movsd   xmm1, qword ptr [rbx+10h]
0x18003d275  lea     rcx, qword_1800BB520
0x18003d27c  mov     cs:qword_1800BB5B0, rax
0x18003d283  lea     rax, WcnOneXStopEapSession
0x18003d28a  mov     cs:qword_1800BB5B8, rax
0x18003d291  lea     rax, qword_1800BB510
0x18003d298  mov     cs:qword_1800BB518, rax
0x18003d29f  mov     cs:qword_1800BB510, rax
0x18003d2a6  movaps  cs:xmmword_1800BB590, xmm0
0x18003d2ad  movsd   cs:qword_1800BB5A0, xmm1
0x18003d2b5  mov     cs:qword_1800BB588, 0
0x18003d2c0  mov     cs:qword_1800BB5A8, 0
0x18003d2cb  mov     cs:hLibModule, 0
0x18003d2d6  call    cs:__imp_CreateReadWriteLock
0x18003d2dd  nop     dword ptr [rax+rax+00h]
0x18003d2e2  mov     ebx, eax
0x18003d2e4  test    eax, eax
0x18003d2e6  jz      short loc_18003D312
0x18003d2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d2ef  cmp     rcx, rsi
0x18003d2f2  jz      short loc_18003D33C
0x18003d2f4  test    byte ptr [rcx+1Ch], 4
0x18003d2f8  jz      short loc_18003D319
0x18003d2fa  mov     rcx, [rcx+10h]
0x18003d2fe  lea     r8, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids
0x18003d305  mov     edx, 0Ch
0x18003d30a  mov     r9d, eax
0x18003d30d  call    WPP_SF_d
0x18003d312  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d319  cmp     rcx, rsi
0x18003d31c  jz      short loc_18003D33C
0x18003d31e  test    byte ptr [rcx+1Ch], 1
0x18003d322  jz      short loc_18003D33C
0x18003d324  mov     rcx, [rcx+10h]
0x18003d328  lea     r8, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids
0x18003d32f  mov     edx, 0Dh
0x18003d334  mov     r9d, ebx
0x18003d337  call    WPP_SF_d
0x18003d33c  mov     eax, ebx
0x18003d33e  mov     rbx, [rsp+28h+arg_0]
0x18003d343  add     rsp, 20h
0x18003d347  pop     rsi
0x18003d348  retn
```
