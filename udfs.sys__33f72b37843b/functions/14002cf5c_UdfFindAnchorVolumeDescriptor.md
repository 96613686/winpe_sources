# UdfFindAnchorVolumeDescriptor

- ea: `0x14002cf5c`
- end: `0x14002d254`
- name: `UdfFindAnchorVolumeDescriptor`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140003148`
- `0x140049f80`

## callees

- `0x140004340`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cad4`
- `0x14001093c`
- `0x140013430`
- `0x14001c080`
- `0x14002cf5c`
- `0x140049020`
- `0x140049bb0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cfe6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cfe6`

## pseudocode

```c
__int64 __fastcall UdfFindAnchorVolumeDescriptor(__int64 a1, __int64 a2, PVOID *a3)
{
  int v3; // r14d
  SIZE_T v7; // rbp
  PVOID PoolWithTag; // rax
  __int64 v9; // r8
  PVOID v10; // r15
  unsigned int v11; // ebp
  unsigned int v12; // esi
  unsigned int v13; // edi
  int v14; // edi
  unsigned int v15; // eax
  int v16; // ecx

  v3 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      86,
      WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
      *(unsigned int *)(a2 + 244),
      *(_DWORD *)(a2 + 248));
  }
  v7 = ((-*(_DWORD *)(a2 + 68) & (*(_DWORD *)(a2 + 68) + 511)) + 4095) & 0xFFFFF000;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, v7, 0x33666455u);
  v10 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v7);
  v11 = 0;
  *a3 = v10;
  while ( v11 < 0xB )
  {
    switch ( v11 )
    {
      case 0u:
        v12 = *(_DWORD *)(a2 + 244) + 256;
LABEL_13:
        v13 = v12;
        goto LABEL_36;
      case 1u:
        v12 = *(_DWORD *)(a2 + 244) + 512;
        goto LABEL_13;
      case 2u:
        if ( *(_DWORD *)(a2 + 84) != 128 )
          goto LABEL_42;
        v13 = *(_DWORD *)(a2 + 244) + 256;
        goto LABEL_17;
    }
    v14 = *(_DWORD *)(a2 + 248);
    v15 = v11 - 4;
    if ( v11 <= 6 )
      v15 = v11;
    if ( !v14 )
      break;
    if ( v15 == 3 )
    {
      v16 = 258;
    }
    else if ( v15 == 4 )
    {
      v16 = 256;
    }
    else
    {
      v16 = 0;
      if ( v15 == 5 )
        v16 = 2;
    }
    v13 = v14 - v16;
    if ( v11 > 6 )
    {
      if ( *(_DWORD *)(a2 + 84) != 128 )
        break;
LABEL_17:
      v12 = v13 + 7 * (v13 >> 5);
      goto LABEL_36;
    }
    v12 = v13;
LABEL_36:
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_dDD(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 2, v9, v11, v13, v12);
    }
    if ( (int)UdfReadWriteSectors(
                a1,
                (union _LARGE_INTEGER)((unsigned __int64)v12 << *(_DWORD *)(a2 + 72)),
                -*(_DWORD *)(a2 + 68) & (unsigned int)(*(_DWORD *)(a2 + 68) + 511),
                1,
                *a3,
                *(PDEVICE_OBJECT *)(a2 + 24),
                0) >= 0
      && UdfVerifyDescriptor(a1, (__int64)*a3, 2, 0x200u, v13, 3) )
    {
      if ( v12 == v13 )
      {
        *(_DWORD *)(a2 + 48) &= ~8u;
      }
      else
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
            WPP_SF_(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              88,
              WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
              WPP_SF_q(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                89,
                WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
                a2);
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                90,
                WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
            }
          }
        }
        *(_DWORD *)(a2 + 48) |= 0x4018u;
      }
      v3 = 0;
      goto LABEL_31;
    }
    v3 = -1073741489;
LABEL_42:
    ++v11;
  }
  if ( v3 < 0 )
    UdfFreePool(a3);
LABEL_31:
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 91, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002cf5c  push    rbx
0x14002cf5e  push    rbp
0x14002cf5f  push    rsi
0x14002cf60  push    rdi
0x14002cf61  push    r12
0x14002cf63  push    r13
0x14002cf65  push    r14
0x14002cf67  push    r15
0x14002cf69  sub     rsp, 48h
0x14002cf6d  xor     esi, esi
0x14002cf6f  xor     edi, edi
0x14002cf71  xor     r14d, r14d
0x14002cf74  mov     r12, r8
0x14002cf77  mov     rbx, rdx
0x14002cf7a  mov     r13, rcx
0x14002cf7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cf84  lea     rax, WPP_GLOBAL_Control
0x14002cf8b  cmp     rcx, rax
0x14002cf8e  jz      short loc_14002CFBD
0x14002cf90  test    dword ptr [rcx+2Ch], 800h
0x14002cf97  jz      short loc_14002CFBD
0x14002cf99  mov     eax, [rbx+0F8h]
0x14002cf9f  lea     edx, [rsi+56h]
0x14002cfa2  mov     r9d, [rbx+0F4h]
0x14002cfa9  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002cfb0  mov     rcx, [rcx+18h]
0x14002cfb4  mov     dword ptr [rsp+88h+var_68], eax
0x14002cfb8  call    WPP_SF_dd
0x14002cfbd  mov     ecx, [rbx+44h]
0x14002cfc0  mov     eax, 0FFFFF000h
0x14002cfc5  mov     r8d, 33666455h; Tag
0x14002cfcb  lea     ebp, [rcx+1FFh]
0x14002cfd1  neg     ecx
0x14002cfd3  and     ebp, ecx
0x14002cfd5  mov     ecx, 610h; PoolType
0x14002cfda  add     ebp, 0FFFh
0x14002cfe0  and     rbp, rax
0x14002cfe3  mov     rdx, rbp; NumberOfBytes
0x14002cfe6  call    cs:__imp_ExAllocatePoolWithTag
0x14002cfed  nop     dword ptr [rax+rax+00h]
0x14002cff2  cmp     cs:ExPoolZeroingNativelySupported, sil
0x14002cff9  mov     r15, rax
0x14002cffc  jnz     short loc_14002D010
0x14002cffe  test    rax, rax
0x14002d001  jz      short loc_14002D010
0x14002d003  mov     r8, rbp; Size
0x14002d006  xor     edx, edx; Val
0x14002d008  mov     rcx, rax; void *
0x14002d00b  call    memset
0x14002d010  xor     ebp, ebp
0x14002d012  mov     [r12], r15
0x14002d016  lea     r15, WPP_GLOBAL_Control
0x14002d01d  lea     edx, [rbp+2]
0x14002d020  cmp     ebp, 0Bh
0x14002d023  jnb     loc_14002D0CB
0x14002d029  test    ebp, ebp
0x14002d02b  jnz     short loc_14002D03B
0x14002d02d  mov     esi, [rbx+0F4h]
0x14002d033  add     esi, 100h
0x14002d039  jmp     short loc_14002D04C
0x14002d03b  cmp     ebp, 1
0x14002d03e  jnz     short loc_14002D053
0x14002d040  mov     esi, [rbx+0F4h]
0x14002d046  add     esi, 200h
0x14002d04c  mov     edi, esi
0x14002d04e  jmp     loc_14002D11C
0x14002d053  cmp     ebp, edx
0x14002d055  jnz     short loc_14002D07F
0x14002d057  cmp     dword ptr [rbx+54h], 80h
0x14002d05e  jnz     loc_14002D1B8
0x14002d064  mov     edi, [rbx+0F4h]
0x14002d06a  add     edi, 100h
0x14002d070  mov     eax, edi
0x14002d072  shr     eax, 5
0x14002d075  imul    esi, eax, 7
0x14002d078  add     esi, edi
0x14002d07a  jmp     loc_14002D11C
0x14002d07f  cmp     ebp, 3
0x14002d082  jb      loc_14002D11C
0x14002d088  mov     edi, [rbx+0F8h]
0x14002d08e  lea     eax, [rbp-4]
0x14002d091  cmp     ebp, 6
0x14002d094  cmovbe  eax, ebp
0x14002d097  test    edi, edi
0x14002d099  jz      short loc_14002D0CB
0x14002d09b  cmp     eax, 3
0x14002d09e  jnz     short loc_14002D0A7
0x14002d0a0  mov     ecx, 102h
0x14002d0a5  jmp     short loc_14002D0BB
0x14002d0a7  cmp     eax, 4
0x14002d0aa  jnz     short loc_14002D0B3
0x14002d0ac  mov     ecx, 100h
0x14002d0b1  jmp     short loc_14002D0BB
0x14002d0b3  xor     ecx, ecx
0x14002d0b5  cmp     eax, 5
0x14002d0b8  cmovz   ecx, edx
0x14002d0bb  sub     edi, ecx
0x14002d0bd  cmp     ebp, 6
0x14002d0c0  jbe     short loc_14002D11A
0x14002d0c2  cmp     dword ptr [rbx+54h], 80h
0x14002d0c9  jz      short loc_14002D070
0x14002d0cb  test    r14d, r14d
0x14002d0ce  jns     short loc_14002D0D8
0x14002d0d0  mov     rcx, r12
0x14002d0d3  call    UdfFreePool
0x14002d0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d0df  cmp     rcx, r15
0x14002d0e2  jz      short loc_14002D105
0x14002d0e4  test    dword ptr [rcx+2Ch], 800h
0x14002d0eb  jz      short loc_14002D105
0x14002d0ed  mov     rcx, [rcx+18h]
0x14002d0f1  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002d0f8  mov     edx, 5Bh ; '['
0x14002d0fd  mov     r9d, r14d
0x14002d100  call    WPP_SF_d
0x14002d105  mov     eax, r14d
0x14002d108  add     rsp, 48h
0x14002d10c  pop     r15
0x14002d10e  pop     r14
0x14002d110  pop     r13
0x14002d112  pop     r12
0x14002d114  pop     rdi
0x14002d115  pop     rsi
0x14002d116  pop     rbp
0x14002d117  pop     rbx
0x14002d118  retn
0x14002d11a  mov     esi, edi
0x14002d11c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d123  mov     r14d, 800h
0x14002d129  cmp     rcx, r15
0x14002d12c  jz      short loc_14002D148
0x14002d12e  test    [rcx+2Ch], r14d
0x14002d132  jz      short loc_14002D148
0x14002d134  mov     rcx, [rcx+18h]
0x14002d138  mov     r9d, ebp
0x14002d13b  mov     dword ptr [rsp+88h+var_60], esi
0x14002d13f  mov     dword ptr [rsp+88h+var_68], edi
0x14002d143  call    WPP_SF_dDD
0x14002d148  mov     eax, [rbx+44h]
0x14002d14b  mov     r9b, 1
0x14002d14e  mov     ecx, [rbx+48h]
0x14002d151  mov     [rsp+88h+var_58], 0
0x14002d156  mov     edx, esi
0x14002d158  lea     r8d, [rax+1FFh]
0x14002d15f  shl     rdx, cl
0x14002d162  neg     eax
0x14002d164  mov     rcx, r13
0x14002d167  and     r8d, eax
0x14002d16a  mov     rax, [rbx+18h]
0x14002d16e  mov     [rsp+88h+var_60], rax
0x14002d173  mov     rax, [r12]
0x14002d177  mov     [rsp+88h+var_68], rax
0x14002d17c  call    UdfReadWriteSectors
0x14002d181  test    eax, eax
0x14002d183  js      short loc_14002D1AD
0x14002d185  mov     rdx, [r12]
0x14002d189  mov     r8d, 2
0x14002d18f  mov     dword ptr [rsp+88h+var_60], 3
0x14002d197  mov     r9d, 200h
0x14002d19d  mov     rcx, r13
0x14002d1a0  mov     dword ptr [rsp+88h+var_68], edi
0x14002d1a4  call    UdfVerifyDescriptor
0x14002d1a9  test    al, al
0x14002d1ab  jnz     short loc_14002D1BF
0x14002d1ad  mov     edx, 2
0x14002d1b2  mov     r14d, 0C000014Fh
0x14002d1b8  inc     ebp
0x14002d1ba  jmp     loc_14002D020
0x14002d1bf  cmp     esi, edi
0x14002d1c1  jz      loc_14002D248
0x14002d1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d1ce  cmp     rcx, r15
0x14002d1d1  jz      short loc_14002D23F
0x14002d1d3  test    [rcx+2Ch], r14d
0x14002d1d7  jz      short loc_14002D1EE
0x14002d1d9  mov     rcx, [rcx+18h]
0x14002d1dd  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002d1e4  mov     edx, 58h ; 'X'
0x14002d1e9  call    WPP_SF_
0x14002d1ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d1f5  cmp     rcx, r15
0x14002d1f8  jz      short loc_14002D23F
0x14002d1fa  test    [rcx+2Ch], r14d
0x14002d1fe  jz      short loc_14002D218
0x14002d200  mov     rcx, [rcx+18h]
0x14002d204  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002d20b  mov     edx, 59h ; 'Y'
0x14002d210  mov     r9, rbx
0x14002d213  call    WPP_SF_q
0x14002d218  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d21f  cmp     rcx, r15
0x14002d222  jz      short loc_14002D23F
0x14002d224  test    [rcx+2Ch], r14d
0x14002d228  jz      short loc_14002D23F
0x14002d22a  mov     rcx, [rcx+18h]
0x14002d22e  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002d235  mov     edx, 5Ah ; 'Z'
0x14002d23a  call    WPP_SF_
0x14002d23f  or      dword ptr [rbx+30h], 4018h
0x14002d246  jmp     short loc_14002D24C
0x14002d248  and     dword ptr [rbx+30h], 0FFFFFFF7h
0x14002d24c  xor     r14d, r14d
0x14002d24f  jmp     loc_14002D0D8
```
