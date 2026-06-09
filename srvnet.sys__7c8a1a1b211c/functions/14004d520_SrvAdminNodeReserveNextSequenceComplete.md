# SrvAdminNodeReserveNextSequenceComplete

- ea: `0x14004d520`
- end: `0x14004d704`
- name: `SrvAdminNodeReserveNextSequenceComplete`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400488a0`
- `0x14004d4e8`

## callees

- `0x14001389c`
- `0x140016384`
- `0x140024278`
- `0x1400242e8`
- `0x14004d520`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d6ea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004d6ea`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004d546`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004d546`

## pseudocode

```c
__int64 __fastcall SrvAdminNodeReserveNextSequenceComplete(unsigned int a1, __int64 a2, __int64 a3, unsigned __int8 a4)
{
  int v4; // r14d
  int v5; // ebp
  unsigned int v6; // ebx
  signed __int32 v8; // esi
  __int64 result; // rax

  v4 = a4;
  v5 = a3;
  v6 = a2;
  if ( !a4 )
    ExAcquirePushLockExclusiveEx(&NodeInfo, 0);
  v8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_dDDd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, (unsigned int)v5, a1, v6, v4);
  }
  if ( v5 >= 0 )
  {
    if ( (_BYTE)v4 )
    {
      dword_140036A18 = 0;
      dword_140036A1C = v6;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids, v6);
      }
LABEL_24:
      v8 = 2;
      goto LABEL_29;
    }
    if ( a1 == dword_140036A14 )
    {
      if ( (int)((v6 - dword_140036A1C) << 8) > 0 || a1 != dword_140036A18 )
      {
        dword_140036A18 = a1;
        dword_140036A1C = v6;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids, a1, v6);
        }
        goto LABEL_24;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          (unsigned int)dword_140036A18,
          (unsigned int)dword_140036A1C,
          a1,
          v6,
          dword_140036A18,
          dword_140036A1C);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_65854c2b783f3b66712a66400b9887aa_Traceguids,
        (unsigned int)dword_140036A14,
        a1);
    }
  }
LABEL_29:
  result = (unsigned int)_InterlockedCompareExchange(&dword_140036A10, v8, 1);
  if ( !(_BYTE)v4 )
    return ExReleasePushLockExclusiveEx(&NodeInfo, 0);
  return result;
}

```

## disassembly

```asm
0x14004d520  push    rbx
0x14004d522  push    rbp
0x14004d523  push    rsi
0x14004d524  push    rdi
0x14004d525  push    r12
0x14004d527  push    r14
0x14004d529  sub     rsp, 48h
0x14004d52d  movzx   r14d, r9b
0x14004d531  mov     ebp, r8d
0x14004d534  mov     ebx, edx
0x14004d536  mov     edi, ecx
0x14004d538  test    r9b, r9b
0x14004d53b  jnz     short loc_14004D552
0x14004d53d  xor     edx, edx
0x14004d53f  lea     rcx, NodeInfo
0x14004d546  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14004d54d  nop     dword ptr [rax+rax+00h]
0x14004d552  xor     esi, esi
0x14004d554  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d55b  lea     r12, WPP_GLOBAL_Control
0x14004d562  cmp     rcx, r12
0x14004d565  jz      short loc_14004D58D
0x14004d567  mov     eax, [rcx+2Ch]
0x14004d56a  test    al, 20h
0x14004d56c  jz      short loc_14004D58D
0x14004d56e  cmp     byte ptr [rcx+29h], 4
0x14004d572  jb      short loc_14004D58D
0x14004d574  mov     rcx, [rcx+18h]
0x14004d578  mov     r9d, ebp
0x14004d57b  mov     [rsp+78h+var_48], r14d
0x14004d580  mov     [rsp+78h+var_50], ebx
0x14004d584  mov     [rsp+78h+var_58], edi
0x14004d588  call    WPP_SF_dDDd
0x14004d58d  test    ebp, ebp
0x14004d58f  js      loc_14004D6CF
0x14004d595  test    r14b, r14b
0x14004d598  jz      short loc_14004D5E8
0x14004d59a  mov     cs:dword_140036A18, esi
0x14004d5a0  mov     cs:dword_140036A1C, ebx
0x14004d5a6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d5ad  cmp     rcx, r12
0x14004d5b0  jz      loc_14004D696
0x14004d5b6  mov     eax, [rcx+2Ch]
0x14004d5b9  test    al, 20h
0x14004d5bb  jz      loc_14004D696
0x14004d5c1  cmp     byte ptr [rcx+29h], 2
0x14004d5c5  jb      loc_14004D696
0x14004d5cb  mov     rcx, [rcx+18h]
0x14004d5cf  lea     r8, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids
0x14004d5d6  mov     edx, 0Bh
0x14004d5db  mov     r9d, ebx
0x14004d5de  call    WPP_SF_d
0x14004d5e3  jmp     loc_14004D696
0x14004d5e8  mov     r9d, cs:dword_140036A14
0x14004d5ef  cmp     edi, r9d
0x14004d5f2  jnz     loc_14004D69D
0x14004d5f8  mov     r8d, cs:dword_140036A1C
0x14004d5ff  mov     eax, ebx
0x14004d601  sub     eax, r8d
0x14004d604  shl     eax, 8
0x14004d607  test    eax, eax
0x14004d609  jg      short loc_14004D655
0x14004d60b  mov     edx, cs:dword_140036A18
0x14004d611  cmp     edi, edx
0x14004d613  jnz     short loc_14004D655
0x14004d615  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d61c  cmp     rcx, r12
0x14004d61f  jz      loc_14004D6CF
0x14004d625  mov     eax, [rcx+2Ch]
0x14004d628  test    al, 20h
0x14004d62a  jz      loc_14004D6CF
0x14004d630  cmp     byte ptr [rcx+29h], 2
0x14004d634  jb      loc_14004D6CF
0x14004d63a  mov     rcx, [rcx+18h]
0x14004d63e  mov     r9d, edi
0x14004d641  mov     [rsp+78h+var_48], r8d
0x14004d646  mov     [rsp+78h+var_50], edx
0x14004d64a  mov     [rsp+78h+var_58], ebx
0x14004d64e  call    WPP_SF_DDDD
0x14004d653  jmp     short loc_14004D6CF
0x14004d655  mov     cs:dword_140036A18, edi
0x14004d65b  mov     cs:dword_140036A1C, ebx
0x14004d661  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d668  cmp     rcx, r12
0x14004d66b  jz      short loc_14004D696
0x14004d66d  mov     eax, [rcx+2Ch]
0x14004d670  test    al, 20h
0x14004d672  jz      short loc_14004D696
0x14004d674  cmp     byte ptr [rcx+29h], 4
0x14004d678  jb      short loc_14004D696
0x14004d67a  mov     rcx, [rcx+18h]
0x14004d67e  lea     r8, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids
0x14004d685  mov     edx, 0Ch
0x14004d68a  mov     [rsp+78h+var_58], ebx
0x14004d68e  mov     r9d, edi
0x14004d691  call    WPP_SF_Dd
0x14004d696  mov     esi, 2
0x14004d69b  jmp     short loc_14004D6CF
0x14004d69d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004d6a4  cmp     rcx, r12
0x14004d6a7  jz      short loc_14004D6CF
0x14004d6a9  mov     eax, [rcx+2Ch]
0x14004d6ac  test    al, 20h
0x14004d6ae  jz      short loc_14004D6CF
0x14004d6b0  cmp     byte ptr [rcx+29h], 2
0x14004d6b4  jb      short loc_14004D6CF
0x14004d6b6  mov     rcx, [rcx+18h]
0x14004d6ba  lea     r8, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids
0x14004d6c1  mov     edx, 0Eh
0x14004d6c6  mov     [rsp+78h+var_58], edi
0x14004d6ca  call    WPP_SF_Dd
0x14004d6cf  mov     eax, 1
0x14004d6d4  lock cmpxchg cs:dword_140036A10, esi
0x14004d6dc  test    r14b, r14b
0x14004d6df  jnz     short loc_14004D6F6
0x14004d6e1  xor     edx, edx
0x14004d6e3  lea     rcx, NodeInfo
0x14004d6ea  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004d6f1  nop     dword ptr [rax+rax+00h]
0x14004d6f6  add     rsp, 48h
0x14004d6fa  pop     r14
0x14004d6fc  pop     r12
0x14004d6fe  pop     rdi
0x14004d6ff  pop     rsi
0x14004d700  pop     rbp
0x14004d701  pop     rbx
0x14004d702  retn
```
