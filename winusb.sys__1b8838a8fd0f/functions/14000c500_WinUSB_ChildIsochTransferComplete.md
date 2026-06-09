# WinUSB_ChildIsochTransferComplete

- ea: `0x14000c500`
- end: `0x14000c941`
- name: `WinUSB_ChildIsochTransferComplete`
- size: `1089`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400014bc`
- `0x14000bc4c`
- `0x14000c500`
- `0x14000c948`
- `0x14000ced8`
- `0x14000fe14`
- `0x140010700`
- `0x1400108c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c68c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c68c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c7ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c86b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c7ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c86b`

## pseudocode

```c
__int64 __fastcall WinUSB_ChildIsochTransferComplete(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  char v6; // bp
  int v7; // esi
  __int64 v8; // rbx
  __int64 v9; // r13
  __int64 v10; // rax
  int v11; // edx
  int v12; // r8d
  __int64 v13; // r14
  unsigned int v14; // edx
  unsigned int i; // ebp
  KIRQL v16; // al
  KIRQL v17; // r12
  __int64 v18; // r8
  __int64 **v19; // rdx
  int v20; // ebp
  __int64 v21; // r9
  __int64 v22; // rdi
  int v23; // edx
  int v24; // ebp
  int v25; // edx
  __int64 result; // rax
  int v27; // [rsp+20h] [rbp-58h]
  int v29; // [rsp+90h] [rbp+18h]
  __int64 v30; // [rsp+98h] [rbp+20h] BYREF

  v30 = 0;
  v6 = a1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      67,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v7 = *(_DWORD *)(a3 + 8);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a4[12],
         off_1400150C0);
  v9 = *a4;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1552))(
          WdfDriverGlobals,
          a4[1],
          &v30);
  v13 = v10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDD(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 68, v27, v6, v7, *(_DWORD *)(v10 + 4));
  if ( v7 >= 0 )
  {
    v14 = *(_DWORD *)(v13 + 132);
    if ( v14 )
    {
      for ( i = 0; i < v14; ++i )
      {
        if ( *(int *)(v13 + 12LL * i + 148) < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 4;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              3,
              69,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              *(_DWORD *)(v13 + 12LL * i + 148));
            v14 = *(_DWORD *)(v13 + 132);
          }
          v7 = -1073741823;
        }
      }
    }
  }
  _InterlockedAdd((volatile signed __int32 *)(v9 + 200), -*((_DWORD *)a4 + 10));
  if ( a4[2] )
    WinUSB_UnmapIsochBuffer(a4);
  v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 232));
  ++*(_DWORD *)(v8 + 60);
  v17 = v16;
  v29 = *(_DWORD *)(v8 + 60);
  if ( *((_BYTE *)a4 + 124) )
  {
    v20 = --*(_DWORD *)(v8 + 140);
  }
  else
  {
    v18 = a4[6];
    if ( *(__int64 **)(v18 + 8) != a4 + 6 || (v19 = (__int64 **)a4[7], *v19 != a4 + 6) )
      __fastfail(3u);
    *v19 = (__int64 *)v18;
    v20 = 0;
    *(_QWORD *)(v18 + 8) = v19;
  }
  v21 = *(_QWORD *)(v8 + 24);
  if ( v21 )
    memmove(
      (void *)(v21 + 12LL * (unsigned int)(*((_DWORD *)a4 + 26) * *(_DWORD *)(v8 + 64))),
      (const void *)(v13 + 140),
      12LL * *(unsigned int *)(v13 + 132));
  v22 = a4[12];
  WinUSB_FreeChildIsochRequest(v22, a1);
  if ( v7 < 0 && *(int *)(v8 + 40) >= 0 )
    *(_DWORD *)(v8 + 40) = v7;
  if ( *(_BYTE *)(v8 + 137) || (*(_BYTE *)(v8 + 136) != 1 || v20) && v29 != *(_DWORD *)(v8 + 52) )
    goto LABEL_39;
  if ( *(_BYTE *)(v8 + 138) != 1 )
    goto LABEL_36;
  v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2048))(WdfDriverGlobals, v22);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v23) = 4;
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      3,
      70,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      v22,
      v24);
  }
  if ( v24 == -1073741536 && !*(_BYTE *)(v8 + 136) )
  {
LABEL_39:
    KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 232), v17);
  }
  else
  {
LABEL_36:
    *(_BYTE *)(v8 + 137) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 232), v17);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v25) = 4;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        3,
        71,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
        v22,
        *(_DWORD *)(v8 + 40));
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
      WdfDriverGlobals,
      v22,
      *(unsigned int *)(v8 + 40),
      *(_QWORD *)(v8 + 32));
  }
  if ( v7 == -1073741632 || v7 == -1073741810 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        3,
        72,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, _QWORD))(WdfFunctions_01015 + 1320))(
               WdfDriverGlobals,
               *(_QWORD *)(v9 + 192),
               0,
               0);
  }
  else
  {
    result = WinUSB_DispatchIsochRequests(v9);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      return WPP_RECORDER_SF_(
               WPP_GLOBAL_Control->DeviceExtension,
               5,
               1,
               73,
               (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000c500  mov     r11, rsp
0x14000c503  mov     [r11+10h], rbx
0x14000c507  mov     [r11+8], rcx
0x14000c50b  push    rbp
0x14000c50c  push    rsi
0x14000c50d  push    rdi
0x14000c50e  push    r12
0x14000c510  push    r13
0x14000c512  push    r14
0x14000c514  push    r15
0x14000c516  sub     rsp, 40h
0x14000c51a  xor     r15d, r15d
0x14000c51d  mov     rdi, r9
0x14000c520  mov     [r11+20h], r15
0x14000c524  mov     rsi, r8
0x14000c527  mov     rbp, rcx
0x14000c52a  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000c531  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000c538  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c53f  jz      short loc_14000C566
0x14000c541  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c548  cmp     [rcx+48h], r15w
0x14000c54d  jz      short loc_14000C566
0x14000c54f  mov     rcx, [rcx+40h]
0x14000c553  lea     r9d, [r15+43h]
0x14000c557  lea     r8d, [r15+1]
0x14000c55b  mov     [r11-58h], rax
0x14000c55f  mov     dl, 5
0x14000c561  call    WPP_RECORDER_SF_
0x14000c566  mov     rax, cs:WdfFunctions_01015
0x14000c56d  mov     r8, cs:off_1400150C0
0x14000c574  mov     rdx, [rdi+60h]
0x14000c578  mov     rcx, cs:WdfDriverGlobals
0x14000c57f  mov     rax, [rax+650h]
0x14000c586  mov     esi, [rsi+8]
0x14000c589  call    _guard_dispatch_icall
0x14000c58e  mov     rcx, cs:WdfFunctions_01015
0x14000c595  lea     r8, [rsp+78h+arg_18]
0x14000c59d  mov     rdx, [rdi+8]
0x14000c5a1  mov     rbx, rax
0x14000c5a4  mov     r13, [rdi]
0x14000c5a7  mov     [rsp+78h+arg_10], rax
0x14000c5af  mov     rax, [rcx+610h]
0x14000c5b6  mov     rcx, cs:WdfDriverGlobals
0x14000c5bd  call    _guard_dispatch_icall
0x14000c5c2  mov     r14, rax
0x14000c5c5  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000c5cc  jz      short loc_14000C5F4
0x14000c5ce  mov     ecx, [rax+4]
0x14000c5d1  mov     r9d, 44h ; 'D'
0x14000c5d7  mov     [rsp+78h+var_40], ecx
0x14000c5db  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c5e2  mov     [rsp+78h+var_48], esi
0x14000c5e6  mov     [rsp+78h+var_50], rbp
0x14000c5eb  mov     rcx, [rcx+40h]
0x14000c5ef  call    WPP_RECORDER_SF_qDD
0x14000c5f4  test    esi, esi
0x14000c5f6  js      short loc_14000C667
0x14000c5f8  mov     edx, [r14+84h]
0x14000c5ff  test    edx, edx
0x14000c601  jz      short loc_14000C667
0x14000c603  mov     ebp, r15d
0x14000c606  lea     rbx, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c60d  mov     eax, ebp
0x14000c60f  lea     rcx, [rax+rax*2]
0x14000c613  mov     eax, [r14+rcx*4+94h]
0x14000c61b  test    eax, eax
0x14000c61d  jns     short loc_14000C659
0x14000c61f  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000c626  jz      short loc_14000C654
0x14000c628  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c62f  mov     r9d, 45h ; 'E'
0x14000c635  mov     dword ptr [rsp+78h+var_50], eax
0x14000c639  mov     dl, 4
0x14000c63b  mov     [rsp+78h+var_58], rbx
0x14000c640  mov     rcx, [rcx+40h]
0x14000c644  lea     r8d, [r9-42h]
0x14000c648  call    WPP_RECORDER_SF_d
0x14000c64d  mov     edx, [r14+84h]
0x14000c654  mov     esi, 0C0000001h
0x14000c659  inc     ebp
0x14000c65b  cmp     ebp, edx
0x14000c65d  jb      short loc_14000C60D
0x14000c65f  mov     rbx, [rsp+78h+arg_10]
0x14000c667  mov     eax, [rdi+28h]
0x14000c66a  neg     eax
0x14000c66c  lock add [r13+0C8h], eax
0x14000c674  cmp     [rdi+10h], r15
0x14000c678  jz      short loc_14000C682
0x14000c67a  mov     rcx, rdi
0x14000c67d  call    WinUSB_UnmapIsochBuffer
0x14000c682  lea     r15, [r13+0E8h]
0x14000c689  mov     rcx, r15; SpinLock
0x14000c68c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c693  nop     dword ptr [rax+rax+00h]
0x14000c698  inc     dword ptr [rbx+3Ch]
0x14000c69b  mov     r12b, al
0x14000c69e  cmp     byte ptr [rdi+7Ch], 0
0x14000c6a2  mov     eax, [rbx+3Ch]
0x14000c6a5  mov     dword ptr [rsp+78h+arg_10], eax
0x14000c6ac  jnz     short loc_14000C6D6
0x14000c6ae  lea     rcx, [rdi+30h]
0x14000c6b2  mov     r8, [rcx]
0x14000c6b5  cmp     [r8+8], rcx
0x14000c6b9  jnz     short loc_14000C6CF
0x14000c6bb  mov     rdx, [rcx+8]
0x14000c6bf  cmp     [rdx], rcx
0x14000c6c2  jnz     short loc_14000C6CF
0x14000c6c4  mov     [rdx], r8
0x14000c6c7  xor     ebp, ebp
0x14000c6c9  mov     [r8+8], rdx
0x14000c6cd  jmp     short loc_14000C6E2
0x14000c6cf  mov     ecx, 3
0x14000c6d4  int     29h; Win8: RtlFailFast(ecx)
0x14000c6d6  dec     dword ptr [rbx+8Ch]
0x14000c6dc  mov     ebp, [rbx+8Ch]
0x14000c6e2  mov     r9, [rbx+18h]
0x14000c6e6  test    r9, r9
0x14000c6e9  jz      short loc_14000C715
0x14000c6eb  mov     eax, [r14+84h]
0x14000c6f2  lea     rdx, [r14+8Ch]; Src
0x14000c6f9  lea     r8, [rax+rax*2]
0x14000c6fd  mov     eax, [rbx+40h]
0x14000c700  imul    eax, [rdi+68h]
0x14000c704  shl     r8, 2; Size
0x14000c708  lea     rcx, [rax+rax*2]
0x14000c70c  lea     rcx, [r9+rcx*4]; void *
0x14000c710  call    memmove
0x14000c715  mov     rdi, [rdi+60h]
0x14000c719  mov     rdx, [rsp+78h+arg_0]
0x14000c721  mov     rcx, rdi
0x14000c724  call    WinUSB_FreeChildIsochRequest
0x14000c729  xor     r14d, r14d
0x14000c72c  test    esi, esi
0x14000c72e  jns     short loc_14000C739
0x14000c730  cmp     [rbx+28h], r14d
0x14000c734  jl      short loc_14000C739
0x14000c736  mov     [rbx+28h], esi
0x14000c739  cmp     [rbx+89h], r14b
0x14000c740  jnz     loc_14000C865
0x14000c746  cmp     byte ptr [rbx+88h], 1
0x14000c74d  jnz     short loc_14000C753
0x14000c74f  test    ebp, ebp
0x14000c751  jz      short loc_14000C763
0x14000c753  mov     eax, dword ptr [rsp+78h+arg_10]
0x14000c75a  cmp     eax, [rbx+34h]
0x14000c75d  jnz     loc_14000C865
0x14000c763  cmp     byte ptr [rbx+8Ah], 1
0x14000c76a  jnz     short loc_14000C7E1
0x14000c76c  mov     rax, cs:WdfFunctions_01015
0x14000c773  mov     rdx, rdi
0x14000c776  mov     rcx, cs:WdfDriverGlobals
0x14000c77d  mov     rax, [rax+800h]
0x14000c784  call    _guard_dispatch_icall
0x14000c789  mov     ebp, eax
0x14000c78b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000c792  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000c799  jz      short loc_14000C7CC
0x14000c79b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c7a2  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c7a9  mov     r9d, 46h ; 'F'
0x14000c7af  mov     [rsp+78h+var_48], ebp
0x14000c7b3  mov     [rsp+78h+var_50], rdi
0x14000c7b8  mov     dl, 4
0x14000c7ba  mov     [rsp+78h+var_58], rax
0x14000c7bf  mov     rcx, [rcx+40h]
0x14000c7c3  lea     r8d, [r9-43h]
0x14000c7c7  call    WPP_RECORDER_SF_qd
0x14000c7cc  cmp     ebp, 0C0000120h
0x14000c7d2  jnz     short loc_14000C7E1
0x14000c7d4  cmp     [rbx+88h], r14b
0x14000c7db  jz      loc_14000C865
0x14000c7e1  mov     dl, r12b; NewIrql
0x14000c7e4  mov     byte ptr [rbx+89h], 1
0x14000c7eb  mov     rcx, r15; SpinLock
0x14000c7ee  call    cs:__imp_KeReleaseSpinLock
0x14000c7f5  nop     dword ptr [rax+rax+00h]
0x14000c7fa  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000c801  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000c808  jz      short loc_14000C83E
0x14000c80a  mov     eax, [rbx+28h]
0x14000c80d  mov     r9d, 47h ; 'G'
0x14000c813  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c81a  mov     dl, 4
0x14000c81c  mov     [rsp+78h+var_48], eax
0x14000c820  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c827  mov     [rsp+78h+var_50], rdi
0x14000c82c  lea     r8d, [r9-44h]
0x14000c830  mov     [rsp+78h+var_58], rax
0x14000c835  mov     rcx, [rcx+40h]
0x14000c839  call    WPP_RECORDER_SF_qd
0x14000c83e  mov     rax, cs:WdfFunctions_01015
0x14000c845  mov     rdx, rdi
0x14000c848  mov     r9, [rbx+20h]
0x14000c84c  mov     r8d, [rbx+28h]
0x14000c850  mov     rcx, cs:WdfDriverGlobals
0x14000c857  mov     rax, [rax+848h]
0x14000c85e  call    _guard_dispatch_icall
0x14000c863  jmp     short loc_14000C87E
0x14000c865  mov     dl, r12b; NewIrql
0x14000c868  mov     rcx, r15; SpinLock
0x14000c86b  call    cs:__imp_KeReleaseSpinLock
0x14000c872  nop     dword ptr [rax+rax+00h]
0x14000c877  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000c87e  cmp     esi, 0C00000C0h
0x14000c884  jz      short loc_14000C898
0x14000c886  cmp     esi, 0C000000Eh
0x14000c88c  jz      short loc_14000C898
0x14000c88e  mov     rcx, r13
0x14000c891  call    WinUSB_DispatchIsochRequests
0x14000c896  jmp     short loc_14000C8F0
0x14000c898  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000c89f  jz      short loc_14000C8C9
0x14000c8a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c8a8  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c8af  mov     r9d, 48h ; 'H'
0x14000c8b5  mov     [rsp+78h+var_58], rax
0x14000c8ba  mov     dl, 4
0x14000c8bc  mov     rcx, [rcx+40h]
0x14000c8c0  lea     r8d, [r9-45h]
0x14000c8c4  call    WPP_RECORDER_SF_
0x14000c8c9  mov     rax, cs:WdfFunctions_01015
0x14000c8d0  xor     r9d, r9d
0x14000c8d3  mov     rdx, [r13+0C0h]
0x14000c8da  xor     r8d, r8d
0x14000c8dd  mov     rcx, cs:WdfDriverGlobals
0x14000c8e4  mov     rax, [rax+528h]
0x14000c8eb  call    _guard_dispatch_icall
0x14000c8f0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14000c8f7  jz      short loc_14000C928
0x14000c8f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c900  cmp     [rcx+48h], r14w
0x14000c905  jz      short loc_14000C928
0x14000c907  mov     rcx, [rcx+40h]
0x14000c90b  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c912  mov     r9d, 49h ; 'I'
0x14000c918  mov     [rsp+78h+var_58], rax
0x14000c91d  mov     dl, 5
0x14000c91f  lea     r8d, [r9-48h]
0x14000c923  call    WPP_RECORDER_SF_
0x14000c928  mov     rbx, [rsp+78h+arg_8]
0x14000c930  add     rsp, 40h
0x14000c934  pop     r15
0x14000c936  pop     r14
0x14000c938  pop     r13
0x14000c93a  pop     r12
0x14000c93c  pop     rdi
0x14000c93d  pop     rsi
0x14000c93e  pop     rbp
0x14000c93f  retn
```
