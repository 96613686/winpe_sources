# WinUSB_SetInterface

- ea: `0x140007694`
- end: `0x1400079c1`
- name: `WinUSB_SetInterface`
- size: `813`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140004130`
- `0x1400043cc`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140006acc`
- `0x140006dec`
- `0x140007694`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000787e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000787e`
- `ntoskrnl!ExAllocatePool2` at `0x1400077f8`
- `ntoskrnl!ExAllocatePool2` at `0x1400077f8`

## pseudocode

```c
__int64 __fastcall WinUSB_SetInterface(__int64 a1, unsigned __int8 a2, unsigned __int8 a3)
{
  __int64 v3; // rbx
  __int64 v6; // rdi
  unsigned __int8 v7; // bl
  __int64 v8; // rdi
  int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  int v12; // r9d
  __int64 Pool2; // rax
  unsigned __int8 v14; // al
  __int64 v15; // r8
  unsigned int v16; // r14d
  char v17; // bp
  __int64 v18; // rax
  int inited; // eax
  char v21; // [rsp+28h] [rbp-60h]
  __int128 v22; // [rsp+30h] [rbp-58h] BYREF

  v3 = a2;
  v22 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      37,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  v6 = 280 * v3;
  v7 = 1;
  v8 = *(_QWORD *)(a1 + 136) + v6;
  do
    WinUSB_FreePipe(v8, v7++);
  while ( v7 < 0x20u );
  if ( *(_BYTE *)(v8 + 1) != a3 )
  {
    *(_QWORD *)&v22 = 0x1100000010LL;
    *((_QWORD *)&v22 + 1) = a3;
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int128 *))(WdfFunctions_01015 + 2880))(
           WdfDriverGlobals,
           *(_QWORD *)(v8 + 8),
           0,
           &v22);
    v11 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v11;
      v12 = 38;
      v21 = v9;
      LOBYTE(v10) = 3;
      goto LABEL_10;
    }
    *(_BYTE *)(v8 + 1) = a3;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      26,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  v10 = *(_QWORD *)(v8 + 24);
  if ( v10 )
    goto LABEL_20;
  Pool2 = ExAllocatePool2(64, 240, 1112757591);
  v10 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(v8 + 24) = Pool2;
LABEL_20:
    *(_BYTE *)(v10 + 8) = 0;
    v11 = 0;
    *(_DWORD *)(v10 + 4) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 7LL);
    *(_DWORD *)(v10 + 16) = 4096;
    *(_DWORD *)(v10 + 12) = 1;
    *(_OWORD *)(v10 + 20) = *(_OWORD *)(a1 + 280);
    *(_DWORD *)(v10 + 24) = 5000;
    KeInitializeSpinLock((PKSPIN_LOCK)(v10 + 40));
    goto LABEL_21;
  }
  v11 = -1073741670;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_24;
  LOBYTE(v10) = 2;
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v10,
    3,
    27,
    (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
    154);
LABEL_21:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      28,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      v11);
  }
LABEL_24:
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v11;
    v12 = 39;
    v21 = v11;
    goto LABEL_27;
  }
  v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2912))(
          WdfDriverGlobals,
          *(_QWORD *)(v8 + 8));
  v16 = v14;
  v17 = 0;
  *(_DWORD *)(v8 + 16) = v14;
  if ( !v14 )
    goto LABEL_31;
  while ( 1 )
  {
    LOBYTE(v15) = v17;
    v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, _QWORD))(WdfFunctions_01015 + 2920))(
            WdfDriverGlobals,
            *(_QWORD *)(v8 + 8),
            v15,
            0);
    inited = WinUSB_InitPipe(a1, v8, v18);
    v11 = inited;
    if ( inited < 0 )
      break;
    if ( (unsigned __int8)++v17 >= v16 )
      goto LABEL_31;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = 40;
    v21 = inited;
LABEL_27:
    LOBYTE(v10) = 2;
LABEL_10:
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      v12,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      v21);
LABEL_31:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v10) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        41,
        (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
        v11);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x140007694  push    rbx
0x140007696  push    rbp
0x140007697  push    rsi
0x140007698  push    rdi
0x140007699  push    r12
0x14000769b  push    r13
0x14000769d  push    r14
0x14000769f  push    r15
0x1400076a1  sub     rsp, 48h
0x1400076a5  xorps   xmm0, xmm0
0x1400076a8  movzx   ebx, dl
0x1400076ab  movups  [rsp+88h+var_58], xmm0
0x1400076b0  mov     sil, r8b
0x1400076b3  mov     r15, rcx
0x1400076b6  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400076bd  xor     r12d, r12d
0x1400076c0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400076c7  lea     rbp, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x1400076ce  jz      short loc_1400076F8
0x1400076d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400076d7  cmp     [rcx+48h], r12w
0x1400076dc  jz      short loc_1400076F8
0x1400076de  mov     rcx, [rcx+40h]
0x1400076e2  lea     r9d, [r12+25h]
0x1400076e7  lea     r8d, [r12+1]
0x1400076ec  mov     [rsp+88h+var_68], rbp
0x1400076f1  mov     dl, 5
0x1400076f3  call    WPP_RECORDER_SF_
0x1400076f8  imul    rdi, rbx, 118h
0x1400076ff  mov     bl, 1
0x140007701  add     rdi, [r15+88h]
0x140007708  mov     dl, bl
0x14000770a  mov     rcx, rdi
0x14000770d  call    WinUSB_FreePipe
0x140007712  inc     bl
0x140007714  cmp     bl, 20h ; ' '
0x140007717  jb      short loc_140007708
0x140007719  cmp     [rdi+1], sil
0x14000771d  jz      loc_1400077AB
0x140007723  mov     rax, cs:WdfFunctions_01015
0x14000772a  lea     r9, [rsp+88h+var_58]
0x14000772f  mov     rcx, cs:WdfDriverGlobals
0x140007736  xorps   xmm0, xmm0
0x140007739  movups  [rsp+88h+var_58], xmm0
0x14000773e  mov     dword ptr [rsp+88h+var_58], 10h
0x140007746  xor     r8d, r8d
0x140007749  mov     dword ptr [rsp+88h+var_58+4], 11h
0x140007751  mov     byte ptr [rsp+88h+var_58+8], sil
0x140007756  mov     rax, [rax+0B40h]
0x14000775d  mov     rdx, [rdi+8]
0x140007761  call    _guard_dispatch_icall
0x140007766  mov     ebx, eax
0x140007768  test    eax, eax
0x14000776a  jns     short loc_1400077A7
0x14000776c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140007773  jz      loc_14000798E
0x140007779  mov     r9d, 26h ; '&'
0x14000777f  mov     dword ptr [rsp+88h+var_60], eax
0x140007783  lea     esi, [r9-23h]
0x140007787  mov     dl, sil
0x14000778a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007791  mov     r8d, esi
0x140007794  mov     [rsp+88h+var_68], rbp
0x140007799  mov     rcx, [rcx+40h]
0x14000779d  call    WPP_RECORDER_SF_d
0x1400077a2  jmp     loc_140007959
0x1400077a7  mov     [rdi+1], sil
0x1400077ab  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400077b2  jz      short loc_1400077DC
0x1400077b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400077bb  cmp     [rcx+48h], r12w
0x1400077c0  jz      short loc_1400077DC
0x1400077c2  mov     rcx, [rcx+40h]
0x1400077c6  mov     r9d, 1Ah
0x1400077cc  mov     dl, 5
0x1400077ce  mov     [rsp+88h+var_68], rbp
0x1400077d3  lea     r8d, [r9-19h]
0x1400077d7  call    WPP_RECORDER_SF_
0x1400077dc  mov     rdx, [rdi+18h]
0x1400077e0  mov     esi, 3
0x1400077e5  test    rdx, rdx
0x1400077e8  jnz     short loc_140007846
0x1400077ea  mov     edx, 0F0h
0x1400077ef  lea     ecx, [rsi+3Dh]
0x1400077f2  mov     r8d, 42535557h
0x1400077f8  call    cs:__imp_ExAllocatePool2
0x1400077ff  nop     dword ptr [rax+rax+00h]
0x140007804  mov     rdx, rax
0x140007807  test    rax, rax
0x14000780a  jnz     short loc_140007842
0x14000780c  mov     ebx, 0C000009Ah
0x140007811  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140007818  jz      loc_1400078BF
0x14000781e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007825  lea     r9d, [rsi+18h]
0x140007829  mov     dword ptr [rsp+88h+var_60], ebx
0x14000782d  mov     r8d, esi
0x140007830  mov     dl, 2
0x140007832  mov     [rsp+88h+var_68], rbp
0x140007837  mov     rcx, [rcx+40h]
0x14000783b  call    WPP_RECORDER_SF_d
0x140007840  jmp     short loc_14000788A
0x140007842  mov     [rdi+18h], rax
0x140007846  mov     [rdx+8], r12b
0x14000784a  mov     ebx, r12d
0x14000784d  mov     rax, [r15+30h]
0x140007851  movzx   ecx, byte ptr [rax+7]
0x140007855  mov     [rdx+4], ecx
0x140007858  lea     rcx, [rdx+28h]; SpinLock
0x14000785c  mov     dword ptr [rdx+10h], 1000h
0x140007863  mov     dword ptr [rdx+0Ch], 1
0x14000786a  movups  xmm0, xmmword ptr [r15+118h]
0x140007872  movdqu  xmmword ptr [rdx+14h], xmm0
0x140007877  mov     dword ptr [rdx+18h], 1388h
0x14000787e  call    cs:__imp_KeInitializeSpinLock
0x140007885  nop     dword ptr [rax+rax+00h]
0x14000788a  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140007891  jz      short loc_1400078BF
0x140007893  mov     rcx, cs:WPP_GLOBAL_Control
0x14000789a  cmp     [rcx+48h], r12w
0x14000789f  jz      short loc_1400078BF
0x1400078a1  mov     rcx, [rcx+40h]
0x1400078a5  mov     r9d, 1Ch
0x1400078ab  mov     dword ptr [rsp+88h+var_60], ebx
0x1400078af  mov     dl, 5
0x1400078b1  mov     [rsp+88h+var_68], rbp
0x1400078b6  lea     r8d, [r9-1Bh]
0x1400078ba  call    WPP_RECORDER_SF_d
0x1400078bf  test    ebx, ebx
0x1400078c1  jns     short loc_1400078E1
0x1400078c3  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400078ca  jz      loc_14000798E
0x1400078d0  mov     r9d, 27h ; '''
0x1400078d6  mov     dword ptr [rsp+88h+var_60], ebx
0x1400078da  mov     dl, 2
0x1400078dc  jmp     loc_14000778A
0x1400078e1  mov     rax, cs:WdfFunctions_01015
0x1400078e8  mov     rdx, [rdi+8]
0x1400078ec  mov     rcx, cs:WdfDriverGlobals
0x1400078f3  mov     rax, [rax+0B60h]
0x1400078fa  call    _guard_dispatch_icall
0x1400078ff  movzx   r14d, al
0x140007903  mov     bpl, r12b
0x140007906  mov     [rdi+10h], r14d
0x14000790a  test    al, al
0x14000790c  jz      short loc_140007952
0x14000790e  mov     rax, cs:WdfFunctions_01015
0x140007915  xor     r9d, r9d
0x140007918  mov     rdx, [rdi+8]
0x14000791c  mov     r8b, bpl
0x14000791f  mov     rcx, cs:WdfDriverGlobals
0x140007926  mov     rax, [rax+0B68h]
0x14000792d  call    _guard_dispatch_icall
0x140007932  mov     r8, rax
0x140007935  mov     rdx, rdi
0x140007938  mov     rcx, r15
0x14000793b  call    WinUSB_InitPipe
0x140007940  mov     ebx, eax
0x140007942  test    eax, eax
0x140007944  js      short loc_1400079A2
0x140007946  inc     bpl
0x140007949  movzx   eax, bpl
0x14000794d  cmp     eax, r14d
0x140007950  jb      short loc_14000790E
0x140007952  lea     rbp, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140007959  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140007960  jz      short loc_14000798E
0x140007962  mov     rcx, cs:WPP_GLOBAL_Control
0x140007969  cmp     [rcx+48h], r12w
0x14000796e  jz      short loc_14000798E
0x140007970  mov     rcx, [rcx+40h]
0x140007974  mov     r9d, 29h ; ')'
0x14000797a  mov     dword ptr [rsp+88h+var_60], ebx
0x14000797e  mov     dl, 5
0x140007980  mov     [rsp+88h+var_68], rbp
0x140007985  lea     r8d, [r9-28h]
0x140007989  call    WPP_RECORDER_SF_d
0x14000798e  mov     eax, ebx
0x140007990  add     rsp, 48h
0x140007994  pop     r15
0x140007996  pop     r14
0x140007998  pop     r13
0x14000799a  pop     r12
0x14000799c  pop     rdi
0x14000799d  pop     rsi
0x14000799e  pop     rbp
0x14000799f  pop     rbx
0x1400079a0  retn
0x1400079a2  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400079a9  jz      short loc_14000798E
0x1400079ab  mov     r9d, 28h ; '('
0x1400079b1  mov     dword ptr [rsp+88h+var_60], eax
0x1400079b5  lea     rbp, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x1400079bc  jmp     loc_1400078DA
```
