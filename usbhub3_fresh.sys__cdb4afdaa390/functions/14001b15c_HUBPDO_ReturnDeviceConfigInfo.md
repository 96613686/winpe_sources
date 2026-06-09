# HUBPDO_ReturnDeviceConfigInfo

- ea: `0x14001b15c`
- end: `0x14001b49a`
- name: `HUBPDO_ReturnDeviceConfigInfo`
- size: `830`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400165c0`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14001b15c`
- `0x14001e124`
- `0x14001eaac`
- `0x14001eee0`
- `0x140045640`
- `0x140045940`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001b43c`
- `ntoskrnl!ExAllocatePool2` at `0x14001b43c`

## pseudocode

```c
__int64 __fastcall HUBPDO_ReturnDeviceConfigInfo(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  int v4; // r9d
  NTSTATUS v5; // edi
  int v6; // edx
  int v7; // edx
  __int64 v8; // rax
  int v9; // edx
  __int64 v10; // rbp
  int v11; // edx
  __int64 v12; // rsi
  void *Pool2; // rax

  v3 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
  if ( !v3 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741811;
    v4 = 19;
LABEL_4:
    LOBYTE(a2) = 3;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 1432LL),
      a2,
      5,
      v4,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
    return (unsigned int)-1073741811;
  }
  if ( *(_DWORD *)v3 != 1 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741811;
    v4 = 20;
    goto LABEL_4;
  }
  v6 = *(_DWORD *)(v3 + 4);
  if ( v6 != 204 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 3;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 1432LL),
        v6,
        5,
        21,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        *(_DWORD *)(v3 + 4),
        204);
    }
    return (unsigned int)-1073741789;
  }
  memset((void *)(v3 + 12), 0, 0xC0u);
  *(_DWORD *)v3 = 1;
  v7 = 0;
  *(_QWORD *)(v3 + 4) = 204;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 2512LL) & 2) != 0 )
  {
    *(_DWORD *)(v3 + 8) = 1;
    v7 = 1;
  }
  if ( *(_WORD *)(*(_QWORD *)(a1 + 16) + 2474LL) >= 0x200u )
  {
    *(_DWORD *)(v3 + 8) = 1;
    v7 = 1;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 40LL) & 2) != 0 )
  {
    v7 |= 8u;
    *(_DWORD *)(v3 + 8) = v7;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 40LL) & 2) != 0 )
  {
    v7 |= 4u;
    *(_DWORD *)(v3 + 8) = v7;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 256LL) == 2 )
  {
    v7 |= 2u;
    *(_DWORD *)(v3 + 8) = v7;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 40LL) & 0x100) != 0 )
  {
    v7 |= 0x20u;
    *(_DWORD *)(v3 + 8) = v7;
  }
  if ( !*(_BYTE *)(*(_QWORD *)(a1 + 16) + 240LL) )
  {
    v7 |= 0x10u;
    *(_DWORD *)(v3 + 8) = v7;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 92LL) == 100 )
    *(_DWORD *)(v3 + 8) = v7 | 0x40;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 1640LL) & 1) != 0 )
  {
    *(_DWORD *)(v3 + 132) |= 1u;
    v8 = *(_QWORD *)(a1 + 24);
    *(_OWORD *)(v3 + 136) = *(_OWORD *)(v8 + 1672);
    *(_OWORD *)(v3 + 152) = *(_OWORD *)(v8 + 1688);
    *(_OWORD *)(v3 + 168) = *(_OWORD *)(v8 + 1704);
    *(_OWORD *)(v3 + 184) = *(_OWORD *)(v8 + 1720);
    *(_DWORD *)(v3 + 200) = *(_DWORD *)(v8 + 1736);
  }
  v5 = HUBID_BuildCompatibleID(*(_QWORD *)(a1 + 24), 0, (_OWORD *)(v3 + 28));
  if ( v5 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 3;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 1432LL),
        v9,
        5,
        22,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v5);
    }
    v10 = v3 + 12;
LABEL_44:
    HUBID_FreeID(v3 + 28);
    HUBID_FreeID(v10);
    HUBID_FreeID(v3 + 44);
    return (unsigned int)v5;
  }
  v10 = v3 + 12;
  v5 = HUBID_BuildHardwareID(*(_QWORD *)(a1 + 24), 0, (_OWORD *)(v3 + 12));
  if ( v5 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 3;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL) + 1432LL),
        v11,
        5,
        23,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v5);
    }
    goto LABEL_44;
  }
  v12 = *(_QWORD *)(a1 + 24);
  v5 = 0;
  *(_OWORD *)(v3 + 44) = 0;
  if ( *(_QWORD *)(v12 + 2176) && *(_DWORD *)(v12 + 2172) )
  {
    *(_OWORD *)(v3 + 44) = *(_OWORD *)(v12 + 2168);
    Pool2 = (void *)ExAllocatePool2(64, *(unsigned int *)(v12 + 2172), 1681082453);
    *(_QWORD *)(v3 + 52) = Pool2;
    if ( Pool2 )
      memmove(Pool2, *(const void **)(v12 + 2176), *(unsigned int *)(v12 + 2172));
    else
      v5 = -1073741670;
  }
  if ( v5 < 0 )
    goto LABEL_44;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001b15c  push    rbx
0x14001b15e  push    rbp
0x14001b15f  push    rsi
0x14001b160  push    rdi
0x14001b161  push    r14
0x14001b163  sub     rsp, 40h
0x14001b167  mov     rax, [rdx+0B8h]
0x14001b16e  mov     rsi, rcx
0x14001b171  mov     rbx, [rax+8]
0x14001b175  test    rbx, rbx
0x14001b178  jnz     short loc_14001B1C0
0x14001b17a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b181  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b188  jz      short loc_14001B1B6
0x14001b18a  lea     r9d, [rbx+13h]
0x14001b18e  mov     rax, [rcx+18h]
0x14001b192  mov     r8d, 5
0x14001b198  mov     dl, 3
0x14001b19a  mov     rcx, [rax+8]
0x14001b19e  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001b1a5  mov     [rsp+68h+var_48], rax
0x14001b1aa  mov     rcx, [rcx+598h]
0x14001b1b1  call    WPP_RECORDER_SF_
0x14001b1b6  mov     edi, 0C000000Dh
0x14001b1bb  jmp     loc_14001B48C
0x14001b1c0  mov     edi, 1
0x14001b1c5  cmp     [rbx], edi
0x14001b1c7  jz      short loc_14001B1DF
0x14001b1c9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b1d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b1d7  jz      short loc_14001B1B6
0x14001b1d9  lea     r9d, [rdi+13h]
0x14001b1dd  jmp     short loc_14001B18E
0x14001b1df  mov     edx, [rbx+4]
0x14001b1e2  mov     ebp, 0CCh
0x14001b1e7  cmp     edx, ebp
0x14001b1e9  jz      short loc_14001B239
0x14001b1eb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b1f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b1f9  jz      short loc_14001B22F
0x14001b1fb  mov     rax, [rcx+18h]
0x14001b1ff  mov     r9d, 15h
0x14001b205  mov     [rsp+68h+var_38], ebp
0x14001b209  mov     [rsp+68h+var_40], edx
0x14001b20d  mov     dl, 3
0x14001b20f  mov     rcx, [rax+8]
0x14001b213  lea     r8d, [r9-10h]
0x14001b217  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001b21e  mov     [rsp+68h+var_48], rax
0x14001b223  mov     rcx, [rcx+598h]
0x14001b22a  call    WPP_RECORDER_SF_dD
0x14001b22f  mov     edi, 0C0000023h
0x14001b234  jmp     loc_14001B48C
0x14001b239  lea     rcx, [rbx+0Ch]; void *
0x14001b23d  xor     edx, edx; Val
0x14001b23f  mov     r8d, 0C0h; Size
0x14001b245  call    memset
0x14001b24a  mov     [rbx], edi
0x14001b24c  xor     edx, edx
0x14001b24e  mov     [rbx+4], rbp
0x14001b252  mov     rax, [rsi+10h]
0x14001b256  mov     ecx, [rax+9D0h]
0x14001b25c  test    cl, 2
0x14001b25f  jz      short loc_14001B266
0x14001b261  mov     [rbx+8], edi
0x14001b264  mov     edx, edi
0x14001b266  mov     rax, [rsi+10h]
0x14001b26a  mov     ecx, 200h
0x14001b26f  cmp     [rax+9AAh], cx
0x14001b276  jb      short loc_14001B27D
0x14001b278  mov     [rbx+8], edi
0x14001b27b  mov     edx, edi
0x14001b27d  mov     rax, [rsi+10h]
0x14001b281  mov     ecx, [rax+28h]
0x14001b284  test    cl, 2
0x14001b287  jz      short loc_14001B28F
0x14001b289  or      edx, 8
0x14001b28c  mov     [rbx+8], edx
0x14001b28f  mov     rax, [rsi+10h]
0x14001b293  mov     ecx, [rax+28h]
0x14001b296  test    cl, 2
0x14001b299  jz      short loc_14001B2A1
0x14001b29b  or      edx, 4
0x14001b29e  mov     [rbx+8], edx
0x14001b2a1  mov     rax, [rsi+10h]
0x14001b2a5  cmp     dword ptr [rax+100h], 2
0x14001b2ac  jnz     short loc_14001B2B4
0x14001b2ae  or      edx, 2
0x14001b2b1  mov     [rbx+8], edx
0x14001b2b4  mov     rax, [rsi+10h]
0x14001b2b8  test    dword ptr [rax+28h], 100h
0x14001b2bf  jz      short loc_14001B2C7
0x14001b2c1  or      edx, 20h
0x14001b2c4  mov     [rbx+8], edx
0x14001b2c7  mov     rax, [rsi+10h]
0x14001b2cb  cmp     byte ptr [rax+0F0h], 0
0x14001b2d2  jnz     short loc_14001B2DA
0x14001b2d4  or      edx, 10h
0x14001b2d7  mov     [rbx+8], edx
0x14001b2da  mov     rax, [rsi+10h]
0x14001b2de  cmp     dword ptr [rax+5Ch], 64h ; 'd'
0x14001b2e2  jnz     short loc_14001B2EA
0x14001b2e4  or      edx, 40h
0x14001b2e7  mov     [rbx+8], edx
0x14001b2ea  mov     rax, [rsi+18h]
0x14001b2ee  mov     ecx, [rax+668h]
0x14001b2f4  test    dil, cl
0x14001b2f7  jz      short loc_14001B347
0x14001b2f9  or      [rbx+84h], edi
0x14001b2ff  mov     rax, [rsi+18h]
0x14001b303  movups  xmm0, xmmword ptr [rax+688h]
0x14001b30a  movups  xmmword ptr [rbx+88h], xmm0
0x14001b311  movups  xmm1, xmmword ptr [rax+698h]
0x14001b318  movups  xmmword ptr [rbx+98h], xmm1
0x14001b31f  movups  xmm0, xmmword ptr [rax+6A8h]
0x14001b326  movups  xmmword ptr [rbx+0A8h], xmm0
0x14001b32d  movups  xmm1, xmmword ptr [rax+6B8h]
0x14001b334  movups  xmmword ptr [rbx+0B8h], xmm1
0x14001b33b  mov     eax, [rax+6C8h]
0x14001b341  mov     [rbx+0C8h], eax
0x14001b347  mov     rcx, [rsi+18h]
0x14001b34b  lea     r8, [rbx+1Ch]
0x14001b34f  xor     edx, edx
0x14001b351  call    HUBID_BuildCompatibleID
0x14001b356  mov     edi, eax
0x14001b358  test    eax, eax
0x14001b35a  jns     short loc_14001B3A5
0x14001b35c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b363  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b36a  jz      short loc_14001B39C
0x14001b36c  mov     rcx, [rsi+18h]
0x14001b370  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001b377  mov     r9d, 16h
0x14001b37d  mov     [rsp+68h+var_40], edi
0x14001b381  mov     dl, 3
0x14001b383  mov     [rsp+68h+var_48], rax
0x14001b388  mov     rcx, [rcx+8]
0x14001b38c  lea     r8d, [r9-11h]
0x14001b390  mov     rcx, [rcx+598h]
0x14001b397  call    WPP_RECORDER_SF_d
0x14001b39c  lea     rbp, [rbx+0Ch]
0x14001b3a0  jmp     loc_14001B472
0x14001b3a5  mov     rcx, [rsi+18h]
0x14001b3a9  lea     rbp, [rbx+0Ch]
0x14001b3ad  mov     r8, rbp
0x14001b3b0  xor     edx, edx
0x14001b3b2  call    HUBID_BuildHardwareID
0x14001b3b7  mov     edi, eax
0x14001b3b9  test    eax, eax
0x14001b3bb  jns     short loc_14001B403
0x14001b3bd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b3c4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b3cb  jz      loc_14001B472
0x14001b3d1  mov     rax, [rsi+18h]
0x14001b3d5  mov     r9d, 17h
0x14001b3db  mov     [rsp+68h+var_40], edi
0x14001b3df  mov     dl, 3
0x14001b3e1  mov     rcx, [rax+8]
0x14001b3e5  lea     r8d, [r9-12h]
0x14001b3e9  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001b3f0  mov     [rsp+68h+var_48], rax
0x14001b3f5  mov     rcx, [rcx+598h]
0x14001b3fc  call    WPP_RECORDER_SF_d
0x14001b401  jmp     short loc_14001B472
0x14001b403  mov     rsi, [rsi+18h]
0x14001b407  xorps   xmm0, xmm0
0x14001b40a  xor     edi, edi
0x14001b40c  movups  xmmword ptr [rbx+2Ch], xmm0
0x14001b410  cmp     [rsi+880h], rdi
0x14001b417  jz      short loc_14001B46E
0x14001b419  cmp     [rsi+87Ch], edi
0x14001b41f  jz      short loc_14001B46E
0x14001b421  movups  xmm0, xmmword ptr [rsi+878h]
0x14001b428  lea     ecx, [rdi+40h]
0x14001b42b  mov     r8d, 64334855h
0x14001b431  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x14001b436  mov     edx, [rsi+87Ch]
0x14001b43c  call    cs:__imp_ExAllocatePool2
0x14001b443  nop     dword ptr [rax+rax+00h]
0x14001b448  mov     [rbx+34h], rax
0x14001b44c  test    rax, rax
0x14001b44f  jnz     short loc_14001B458
0x14001b451  mov     edi, 0C000009Ah
0x14001b456  jmp     short loc_14001B46E
0x14001b458  mov     r8d, [rsi+87Ch]; Size
0x14001b45f  mov     rcx, rax; void *
0x14001b462  mov     rdx, [rsi+880h]; Src
0x14001b469  call    memmove
0x14001b46e  test    edi, edi
0x14001b470  jns     short loc_14001B48C
0x14001b472  lea     rcx, [rbx+1Ch]
0x14001b476  call    HUBID_FreeID
0x14001b47b  mov     rcx, rbp
0x14001b47e  call    HUBID_FreeID
0x14001b483  lea     rcx, [rbx+2Ch]
0x14001b487  call    HUBID_FreeID
0x14001b48c  mov     eax, edi
0x14001b48e  add     rsp, 40h
0x14001b492  pop     r14
0x14001b494  pop     rdi
0x14001b495  pop     rsi
0x14001b496  pop     rbp
0x14001b497  pop     rbx
0x14001b498  retn
```
