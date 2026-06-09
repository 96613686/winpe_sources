# WinUSB_SelectConfiguration

- ea: `0x14001d590`
- end: `0x14001d863`
- name: `WinUSB_SelectConfiguration`
- size: `723`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14001b370`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400013d0`
- `0x1400014bc`
- `0x140010700`
- `0x14001d590`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d6ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d6ed`
- `ntoskrnl!ExAllocatePool2` at `0x14001d70b`
- `ntoskrnl!ExAllocatePool2` at `0x14001d70b`

## pseudocode

```c
__int64 __fastcall WinUSB_SelectConfiguration(__int64 a1)
{
  __int64 v2; // rdx
  int v3; // eax
  int v4; // edx
  unsigned int v5; // esi
  int v6; // edx
  unsigned __int8 v7; // al
  __int64 v8; // r8
  __int64 v9; // rbx
  void *v10; // rcx
  unsigned __int8 *v11; // r14
  unsigned __int8 v12; // al
  __int64 Pool2; // rax
  unsigned __int8 v14; // bp
  __int64 v15; // rbx
  _OWORD v17[6]; // [rsp+40h] [rbp-68h] BYREF

  memset(v17, 0, 32);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      18,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  v2 = *(_QWORD *)(a1 + 8);
  memset((char *)v17 + 8, 0, 24);
  *(_QWORD *)&v17[0] = 0x300000020LL;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _OWORD *))(WdfFunctions_01015 + 2640))(
         WdfDriverGlobals,
         v2,
         0,
         v17);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2632))(
           WdfDriverGlobals,
           *(_QWORD *)(a1 + 8));
    v9 = v7;
    if ( !v7 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v5;
      LOBYTE(v6) = 3;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        20,
        (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
        *(_QWORD *)(a1 + 8));
      goto LABEL_19;
    }
    v10 = *(void **)(a1 + 136);
    v11 = (unsigned __int8 *)(a1 + 128);
    if ( v10 )
    {
      v12 = *v11;
      if ( *v11 == (_BYTE)v9 )
      {
LABEL_17:
        v14 = 0;
        if ( v12 )
        {
          do
          {
            LOBYTE(v8) = v14;
            v15 = 280LL * v14;
            *(_QWORD *)(v15 + *(_QWORD *)(a1 + 136) + 8) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2896))(
                                                             WdfDriverGlobals,
                                                             *(_QWORD *)(a1 + 8),
                                                             v8);
            *(_BYTE *)(v15 + *(_QWORD *)(a1 + 136) + 1) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2904))(
                                                            WdfDriverGlobals,
                                                            *(_QWORD *)(*(_QWORD *)(a1 + 136) + v15 + 8));
            ++v14;
            *(_BYTE *)(v15 + *(_QWORD *)(a1 + 136)) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2856))(
                                                        WdfDriverGlobals,
                                                        *(_QWORD *)(*(_QWORD *)(a1 + 136) + v15 + 8));
          }
          while ( v14 < *v11 );
        }
        goto LABEL_19;
      }
      ExFreePoolWithTag(v10, 0);
    }
    Pool2 = ExAllocatePool2(64, 280 * v9, 1112757591);
    *(_QWORD *)(a1 + 136) = Pool2;
    if ( !Pool2 )
    {
      v5 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v5;
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        21,
        (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
        *(_QWORD *)(a1 + 8),
        154);
      goto LABEL_19;
    }
    *v11 = v9;
    v12 = v9;
    goto LABEL_17;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v5;
  LOBYTE(v4) = 2;
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v4,
    3,
    19,
    (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
    v3);
LABEL_19:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      22,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x14001d590  push    rbx
0x14001d592  push    rbp
0x14001d593  push    rsi
0x14001d594  push    rdi
0x14001d595  push    r12
0x14001d597  push    r13
0x14001d599  push    r14
0x14001d59b  push    r15
0x14001d59d  sub     rsp, 68h
0x14001d5a1  xorps   xmm0, xmm0
0x14001d5a4  mov     rdi, rcx
0x14001d5a7  movups  [rsp+0A8h+var_68], xmm0
0x14001d5ac  movups  [rsp+0A8h+var_58], xmm0
0x14001d5b1  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001d5b8  xor     r15d, r15d
0x14001d5bb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001d5c2  lea     r13, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x14001d5c9  jz      short loc_14001D5F1
0x14001d5cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d5d2  cmp     [rcx+48h], r15w
0x14001d5d7  jz      short loc_14001D5F1
0x14001d5d9  mov     rcx, [rcx+40h]
0x14001d5dd  lea     r9d, [r15+12h]
0x14001d5e1  lea     r8d, [r15+1]
0x14001d5e5  mov     [rsp+0A8h+var_88], r13
0x14001d5ea  mov     dl, 5
0x14001d5ec  call    WPP_RECORDER_SF_
0x14001d5f1  mov     rax, cs:WdfFunctions_01015
0x14001d5f8  lea     r9, [rsp+0A8h+var_68]
0x14001d5fd  mov     rdx, [rdi+8]
0x14001d601  xorps   xmm0, xmm0
0x14001d604  mov     rcx, cs:WdfDriverGlobals
0x14001d60b  mov     ebp, 3
0x14001d610  movdqu  [rsp+0A8h+var_68+8], xmm0
0x14001d616  mov     qword ptr [rsp+0A8h+var_58+8], r15
0x14001d61b  xor     r8d, r8d
0x14001d61e  mov     dword ptr [rsp+0A8h+var_68], 20h ; ' '
0x14001d626  mov     dword ptr [rsp+0A8h+var_68+4], ebp
0x14001d62a  mov     rax, [rax+0A50h]
0x14001d631  call    _guard_dispatch_icall
0x14001d636  mov     esi, eax
0x14001d638  test    eax, eax
0x14001d63a  jns     short loc_14001D670
0x14001d63c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001d643  jz      loc_14001D84F
0x14001d649  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d650  lea     r9d, [rbp+10h]
0x14001d654  mov     dword ptr [rsp+0A8h+var_80], eax
0x14001d658  mov     r8d, ebp
0x14001d65b  mov     dl, 2
0x14001d65d  mov     [rsp+0A8h+var_88], r13
0x14001d662  mov     rcx, [rcx+40h]
0x14001d666  call    WPP_RECORDER_SF_d
0x14001d66b  jmp     loc_14001D81A
0x14001d670  mov     rax, cs:WdfFunctions_01015
0x14001d677  mov     rdx, [rdi+8]
0x14001d67b  mov     rcx, cs:WdfDriverGlobals
0x14001d682  mov     rax, [rax+0A48h]
0x14001d689  call    _guard_dispatch_icall
0x14001d68e  movzx   ebx, al
0x14001d691  test    al, al
0x14001d693  jnz     short loc_14001D6D1
0x14001d695  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001d69c  jz      loc_14001D84F
0x14001d6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d6a9  mov     r9d, 14h
0x14001d6af  mov     rax, [rdi+8]
0x14001d6b3  mov     r8d, ebp
0x14001d6b6  mov     [rsp+0A8h+var_80], rax
0x14001d6bb  mov     dl, bpl
0x14001d6be  mov     [rsp+0A8h+var_88], r13
0x14001d6c3  mov     rcx, [rcx+40h]
0x14001d6c7  call    WPP_RECORDER_SF_q
0x14001d6cc  jmp     loc_14001D81A
0x14001d6d1  mov     rcx, [rdi+88h]; P
0x14001d6d8  lea     r14, [rdi+80h]
0x14001d6df  test    rcx, rcx
0x14001d6e2  jz      short loc_14001D6F9
0x14001d6e4  mov     al, [r14]
0x14001d6e7  cmp     al, bl
0x14001d6e9  jz      short loc_14001D76A
0x14001d6eb  xor     edx, edx; Tag
0x14001d6ed  call    cs:__imp_ExFreePoolWithTag
0x14001d6f4  nop     dword ptr [rax+rax+00h]
0x14001d6f9  imul    rdx, rbx, 118h
0x14001d700  mov     ecx, 40h ; '@'
0x14001d705  mov     r8d, 42535557h
0x14001d70b  call    cs:__imp_ExAllocatePool2
0x14001d712  nop     dword ptr [rax+rax+00h]
0x14001d717  mov     [rdi+88h], rax
0x14001d71e  test    rax, rax
0x14001d721  jnz     short loc_14001D765
0x14001d723  mov     esi, 0C000009Ah
0x14001d728  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001d72f  jz      loc_14001D84F
0x14001d735  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d73c  lea     r9d, [rax+15h]
0x14001d740  mov     rax, [rdi+8]
0x14001d744  mov     r8d, ebp
0x14001d747  mov     [rsp+0A8h+var_78], esi
0x14001d74b  mov     dl, 2
0x14001d74d  mov     [rsp+0A8h+var_80], rax
0x14001d752  mov     rcx, [rcx+40h]
0x14001d756  mov     [rsp+0A8h+var_88], r13
0x14001d75b  call    WPP_RECORDER_SF_qd
0x14001d760  jmp     loc_14001D81A
0x14001d765  mov     [r14], bl
0x14001d768  mov     al, bl
0x14001d76a  mov     bpl, r15b
0x14001d76d  test    al, al
0x14001d76f  jz      loc_14001D81A
0x14001d775  mov     rax, cs:WdfFunctions_01015
0x14001d77c  mov     r8b, bpl
0x14001d77f  mov     rdx, [rdi+8]
0x14001d783  mov     rcx, cs:WdfDriverGlobals
0x14001d78a  mov     rax, [rax+0B50h]
0x14001d791  call    _guard_dispatch_icall
0x14001d796  movzx   ecx, bpl
0x14001d79a  imul    rbx, rcx, 118h
0x14001d7a1  mov     rcx, [rdi+88h]
0x14001d7a8  mov     [rbx+rcx+8], rax
0x14001d7ad  mov     rdx, [rdi+88h]
0x14001d7b4  mov     rax, cs:WdfFunctions_01015
0x14001d7bb  mov     rcx, cs:WdfDriverGlobals
0x14001d7c2  mov     rdx, [rdx+rbx+8]
0x14001d7c7  mov     rax, [rax+0B58h]
0x14001d7ce  call    _guard_dispatch_icall
0x14001d7d3  mov     rcx, [rdi+88h]
0x14001d7da  mov     [rbx+rcx+1], al
0x14001d7de  mov     rdx, [rdi+88h]
0x14001d7e5  mov     rax, cs:WdfFunctions_01015
0x14001d7ec  mov     rcx, cs:WdfDriverGlobals
0x14001d7f3  mov     rdx, [rdx+rbx+8]
0x14001d7f8  mov     rax, [rax+0B28h]
0x14001d7ff  call    _guard_dispatch_icall
0x14001d804  mov     rcx, [rdi+88h]
0x14001d80b  inc     bpl
0x14001d80e  mov     [rbx+rcx], al
0x14001d811  cmp     bpl, [r14]
0x14001d814  jb      loc_14001D775
0x14001d81a  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001d821  jz      short loc_14001D84F
0x14001d823  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d82a  cmp     [rcx+48h], r15w
0x14001d82f  jz      short loc_14001D84F
0x14001d831  mov     rcx, [rcx+40h]
0x14001d835  mov     r9d, 16h
0x14001d83b  mov     dword ptr [rsp+0A8h+var_80], esi
0x14001d83f  mov     dl, 5
0x14001d841  mov     [rsp+0A8h+var_88], r13
0x14001d846  lea     r8d, [r9-15h]
0x14001d84a  call    WPP_RECORDER_SF_d
0x14001d84f  mov     eax, esi
0x14001d851  add     rsp, 68h
0x14001d855  pop     r15
0x14001d857  pop     r14
0x14001d859  pop     r13
0x14001d85b  pop     r12
0x14001d85d  pop     rdi
0x14001d85e  pop     rsi
0x14001d85f  pop     rbp
0x14001d860  pop     rbx
0x14001d861  retn
```
