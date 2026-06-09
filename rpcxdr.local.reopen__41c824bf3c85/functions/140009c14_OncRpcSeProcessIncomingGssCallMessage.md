# OncRpcSeProcessIncomingGssCallMessage

- ea: `0x140009c14`
- end: `0x140009dbb`
- name: `OncRpcSeProcessIncomingGssCallMessage`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002f50`

## callees

- `0x1400020c0`
- `0x140009c14`
- `0x14000b624`
- `0x14000bb64`
- `0x14000caec`
- `0x14000d0b8`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140009c49`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009c49`

## pseudocode

```c
__int64 __fastcall OncRpcSeProcessIncomingGssCallMessage(_DWORD *a1, _DWORD *a2, unsigned int *a3)
{
  unsigned int v7; // eax
  __int64 v8; // r8
  __int64 Timer_high; // rdx
  unsigned int v10; // ebx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // eax

  if ( a1[69] != 100003 || a1[74] != 6 )
    return 0;
  if ( KeGetCurrentIrql() >= 2u )
    return 3226730511LL;
  v7 = OncRpcSepValidateRpcsecGssCallMessage(a1);
  *a3 = v7;
  if ( !v7 )
  {
    if ( !byte_14001AA20 )
      return (unsigned int)-1073741790;
    v11 = a1[78];
    if ( !v11 )
    {
      v10 = OncRpcSepProcessIncomingCallGssData((__int64)a1, a2);
      if ( (v10 & 0x80000000) != 0 )
      {
        if ( *a2 > 2u && *a2 != 4 && *a2 != 8 )
        {
          if ( *a2 == 458752 || *a2 == 720896 )
            *a3 = 13;
          else
            *a3 = 14;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, v10);
        }
      }
      return v10;
    }
    v12 = v11 - 1;
    if ( v12 && (v13 = v12 - 1) != 0 )
    {
      if ( v13 != 1 )
        return (unsigned int)-1073741811;
    }
    else
    {
      v14 = OncRpcSepProcessIncomingCallGssInit((__int64)a1, a2);
      v10 = v14;
      if ( v14 >= 0 )
        return v10;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          50,
          WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
          (unsigned int)v14);
      if ( *a2 <= 1u )
        return v10;
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 0x40) != 0 )
      WPP_SF_l(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v8, v7);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x140009c14  mov     [rsp+arg_0], rbx
0x140009c19  mov     [rsp+arg_8], rsi
0x140009c1e  push    rdi
0x140009c1f  sub     rsp, 20h
0x140009c23  cmp     dword ptr [rcx+114h], 186A3h
0x140009c2d  mov     rsi, r8
0x140009c30  mov     rdi, rdx
0x140009c33  mov     rbx, rcx
0x140009c36  jnz     loc_140009DA8
0x140009c3c  cmp     dword ptr [rcx+128h], 6
0x140009c43  jnz     loc_140009DA8
0x140009c49  call    cs:__imp_KeGetCurrentIrql
0x140009c50  nop     dword ptr [rax+rax+00h]
0x140009c55  cmp     al, 2
0x140009c57  jb      short loc_140009C63
0x140009c59  mov     eax, 0C054000Fh
0x140009c5e  jmp     loc_140009DAA
0x140009c63  mov     rcx, rbx
0x140009c66  call    OncRpcSepValidateRpcsecGssCallMessage
0x140009c6b  mov     [rsi], eax
0x140009c6d  test    eax, eax
0x140009c6f  jz      short loc_140009CA2
0x140009c71  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c78  lea     rdx, WPP_GLOBAL_Control
0x140009c7f  cmp     rcx, rdx
0x140009c82  jz      short loc_140009C98
0x140009c84  mov     edx, [rcx+2Ch]
0x140009c87  test    dl, 40h
0x140009c8a  jz      short loc_140009C98
0x140009c8c  mov     rcx, [rcx+18h]
0x140009c90  mov     r9d, eax
0x140009c93  call    WPP_SF_l
0x140009c98  mov     eax, 0C0000001h
0x140009c9d  jmp     loc_140009DAA
0x140009ca2  cmp     cs:byte_14001AA20, 0
0x140009ca9  jnz     short loc_140009CB5
0x140009cab  mov     ebx, 0C0000022h
0x140009cb0  jmp     loc_140009DA4
0x140009cb5  mov     ecx, [rbx+138h]
0x140009cbb  test    ecx, ecx
0x140009cbd  jz      short loc_140009D29
0x140009cbf  sub     ecx, 1
0x140009cc2  jz      short loc_140009CD8
0x140009cc4  sub     ecx, 1
0x140009cc7  jz      short loc_140009CD8
0x140009cc9  cmp     ecx, 1
0x140009ccc  jz      short loc_140009D25
0x140009cce  mov     ebx, 0C000000Dh
0x140009cd3  jmp     loc_140009DA4
0x140009cd8  mov     rdx, rdi
0x140009cdb  mov     rcx, rbx
0x140009cde  call    OncRpcSepProcessIncomingCallGssInit
0x140009ce3  mov     ebx, eax
0x140009ce5  test    eax, eax
0x140009ce7  jns     loc_140009DA4
0x140009ced  mov     rcx, cs:WPP_GLOBAL_Control
0x140009cf4  lea     rdx, WPP_GLOBAL_Control
0x140009cfb  cmp     rcx, rdx
0x140009cfe  jz      short loc_140009D20
0x140009d00  mov     edx, [rcx+2Ch]
0x140009d03  test    dl, 40h
0x140009d06  jz      short loc_140009D20
0x140009d08  mov     rcx, [rcx+18h]
0x140009d0c  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140009d13  mov     edx, 32h ; '2'
0x140009d18  mov     r9d, eax
0x140009d1b  call    WPP_SF_d
0x140009d20  cmp     dword ptr [rdi], 1
0x140009d23  jbe     short loc_140009DA4
0x140009d25  xor     ebx, ebx
0x140009d27  jmp     short loc_140009DA4
0x140009d29  mov     rdx, rdi
0x140009d2c  mov     rcx, rbx
0x140009d2f  call    OncRpcSepProcessIncomingCallGssData
0x140009d34  mov     ebx, eax
0x140009d36  test    eax, eax
0x140009d38  jns     short loc_140009DA4
0x140009d3a  mov     ecx, [rdi]
0x140009d3c  test    ecx, ecx
0x140009d3e  jz      short loc_140009D72
0x140009d40  sub     ecx, 1
0x140009d43  jz      short loc_140009D72
0x140009d45  sub     ecx, 1
0x140009d48  jz      short loc_140009D72
0x140009d4a  sub     ecx, 2
0x140009d4d  jz      short loc_140009D72
0x140009d4f  sub     ecx, 4
0x140009d52  jz      short loc_140009D72
0x140009d54  sub     ecx, 6FFF8h
0x140009d5a  jz      short loc_140009D6C
0x140009d5c  cmp     ecx, 40000h
0x140009d62  jz      short loc_140009D6C
0x140009d64  mov     dword ptr [rsi], 0Eh
0x140009d6a  jmp     short loc_140009D72
0x140009d6c  mov     dword ptr [rsi], 0Dh
0x140009d72  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d79  lea     rdx, WPP_GLOBAL_Control
0x140009d80  cmp     rcx, rdx
0x140009d83  jz      short loc_140009DA4
0x140009d85  mov     eax, [rcx+2Ch]
0x140009d88  test    al, 40h
0x140009d8a  jz      short loc_140009DA4
0x140009d8c  mov     rcx, [rcx+18h]
0x140009d90  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x140009d97  mov     edx, 34h ; '4'
0x140009d9c  mov     r9d, ebx
0x140009d9f  call    WPP_SF_d
0x140009da4  mov     eax, ebx
0x140009da6  jmp     short loc_140009DAA
0x140009da8  xor     eax, eax
0x140009daa  mov     rbx, [rsp+28h+arg_0]
0x140009daf  mov     rsi, [rsp+28h+arg_8]
0x140009db4  add     rsp, 20h
0x140009db8  pop     rdi
0x140009db9  retn
```
