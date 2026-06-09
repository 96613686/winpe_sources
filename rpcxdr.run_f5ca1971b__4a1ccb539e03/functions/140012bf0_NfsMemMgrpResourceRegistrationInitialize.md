# NfsMemMgrpResourceRegistrationInitialize

- ea: `0x140012bf0`
- end: `0x140012d85`
- name: `NfsMemMgrpResourceRegistrationInitialize`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001318c`

## callees

- `0x140012bf0`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x140012cf4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140012cf4`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140012d39`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140012d39`

## pseudocode

```c
__int64 __fastcall NfsMemMgrpResourceRegistrationInitialize(__int64 a1)
{
  int v2; // ecx
  NTSTATUS v3; // edi
  POOL_TYPE v4; // r9d
  SIZE_T Size; // rdx
  unsigned int Depth; // ecx
  __int16 v7; // ax
  unsigned __int16 v8; // ax
  __int64 v9; // r8
  struct _LOOKASIDE_LIST_EX *v10; // rsi

  v2 = *(_DWORD *)(a1 + 412);
  if ( (v2 & 0x3A) != 0x3A || (*(_DWORD *)(a1 + 48) & 2) != 0 && (v2 & 0x280) != 0x80 )
    return (unsigned int)-1068285909;
  v3 = 0;
  if ( (*(_DWORD *)(a1 + 48) & 2) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 152) & 0xC) != 4 )
      goto LABEL_27;
    v4 = *(_DWORD *)(a1 + 160);
    if ( (v4 & 0xFFFFFDFE) != 0 || v4 == 513 )
    {
      v3 = -1073741811;
      v10 = (struct _LOOKASIDE_LIST_EX *)(a1 + 288);
      goto LABEL_25;
    }
    Size = 0xFFFF;
    if ( *(_DWORD *)(a1 + 60) == 7 )
    {
      Depth = *(_DWORD *)(a1 + 244);
      if ( Depth > 0xFFFF )
      {
        LOWORD(Depth) = -1;
        goto LABEL_13;
      }
      if ( (_WORD)Depth )
      {
        if ( (unsigned __int16)Depth <= 0x100u )
        {
          LOWORD(Depth) = 256;
          goto LABEL_18;
        }
LABEL_13:
        v7 = 1024;
        if ( (unsigned __int16)Depth < 0x400u )
        {
LABEL_18:
          v8 = *(_WORD *)(a1 + 156);
          v9 = 8;
          if ( v8 > 8u )
          {
            if ( v8 == 0xFFFF )
              goto LABEL_22;
            v9 = *(unsigned __int16 *)(a1 + 156);
          }
          Size = v9;
LABEL_22:
          v10 = (struct _LOOKASIDE_LIST_EX *)(a1 + 288);
          v3 = ExInitializeLookasideListEx(
                 (PLOOKASIDE_LIST_EX)(a1 + 288),
                 0,
                 0,
                 v4,
                 0,
                 Size,
                 *(_DWORD *)(a1 + 40),
                 Depth);
          *(_DWORD *)(a1 + 384) = *(_DWORD *)(a1 + 384) & 0xFFFFFFFE | (v3 >= 0);
          if ( v3 < 0 )
          {
LABEL_25:
            if ( (*(_DWORD *)(a1 + 384) & 1) != 0 )
            {
              ExDeleteLookasideListEx(v10);
              *(_DWORD *)(a1 + 384) &= ~1u;
            }
          }
LABEL_27:
          *(_DWORD *)(a1 + 412) = *(_DWORD *)(a1 + 412) & 0xFFFFFDFF | ~((unsigned int)v3 >> 22) & 0x200;
          return (unsigned int)v3;
        }
LABEL_17:
        LOWORD(Depth) = v7;
        goto LABEL_18;
      }
    }
    v7 = 0;
    goto LABEL_17;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140012bf0  mov     [rsp+arg_0], rbx
0x140012bf5  mov     [rsp+arg_8], rsi
0x140012bfa  push    rdi
0x140012bfb  sub     rsp, 40h
0x140012bff  mov     rbx, rcx
0x140012c02  mov     ecx, [rcx+19Ch]
0x140012c08  mov     eax, ecx
0x140012c0a  and     eax, 3Ah
0x140012c0d  cmp     al, 3Ah ; ':'
0x140012c0f  jnz     loc_140012D6D
0x140012c15  mov     eax, [rbx+30h]
0x140012c18  and     eax, 2
0x140012c1b  jz      short loc_140012C2F
0x140012c1d  and     ecx, 280h
0x140012c23  cmp     ecx, 80h
0x140012c29  jnz     loc_140012D6D
0x140012c2f  xor     edi, edi
0x140012c31  test    eax, eax
0x140012c33  jz      loc_140012D72
0x140012c39  mov     eax, [rbx+98h]
0x140012c3f  and     al, 0Ch
0x140012c41  cmp     al, 4
0x140012c43  jnz     loc_140012D4C
0x140012c49  mov     r9d, [rbx+0A0h]; PoolType
0x140012c50  test    r9d, 0FFFFFDFEh
0x140012c57  jnz     loc_140012D20
0x140012c5d  cmp     r9d, 201h
0x140012c64  jz      loc_140012D20
0x140012c6a  cmp     dword ptr [rbx+3Ch], 7
0x140012c6e  mov     edx, 0FFFFh
0x140012c73  jnz     short loc_140012CAD
0x140012c75  mov     ecx, [rbx+0F4h]
0x140012c7b  mov     r8d, 100h
0x140012c81  cmp     ecx, edx
0x140012c83  jbe     short loc_140012C8A
0x140012c85  movzx   ecx, dx
0x140012c88  jmp     short loc_140012C97
0x140012c8a  xor     eax, eax
0x140012c8c  cmp     ax, cx
0x140012c8f  jz      short loc_140012CAD
0x140012c91  cmp     cx, r8w
0x140012c95  jbe     short loc_140012CA7
0x140012c97  mov     eax, 400h
0x140012c9c  cmp     cx, ax
0x140012c9f  jnb     short loc_140012CAF
0x140012ca1  cmp     cx, r8w
0x140012ca5  ja      short loc_140012CB2
0x140012ca7  movzx   ecx, r8w
0x140012cab  jmp     short loc_140012CB2
0x140012cad  xor     eax, eax
0x140012caf  movzx   ecx, ax
0x140012cb2  movzx   eax, word ptr [rbx+9Ch]
0x140012cb9  mov     r8d, 8
0x140012cbf  cmp     ax, r8w
0x140012cc3  jbe     short loc_140012CCD
0x140012cc5  cmp     ax, dx
0x140012cc8  jnb     short loc_140012CD0
0x140012cca  mov     r8d, eax
0x140012ccd  mov     rdx, r8
0x140012cd0  mov     eax, [rbx+28h]
0x140012cd3  lea     rsi, [rbx+120h]
0x140012cda  mov     [rsp+48h+Depth], cx; Depth
0x140012cdf  xor     r8d, r8d; Free
0x140012ce2  mov     [rsp+48h+Tag], eax; Tag
0x140012ce6  mov     rcx, rsi; Lookaside
0x140012ce9  mov     [rsp+48h+Size], rdx; Size
0x140012cee  xor     edx, edx; Allocate
0x140012cf0  mov     [rsp+48h+Flags], edi; Flags
0x140012cf4  call    cs:__imp_ExInitializeLookasideListEx
0x140012cfb  nop     dword ptr [rax+rax+00h]
0x140012d00  mov     ecx, eax
0x140012d02  mov     edi, eax
0x140012d04  mov     eax, [rbx+180h]
0x140012d0a  not     ecx
0x140012d0c  shr     ecx, 1Fh
0x140012d0f  and     eax, 0FFFFFFFEh
0x140012d12  or      ecx, eax
0x140012d14  mov     [rbx+180h], ecx
0x140012d1a  test    edi, edi
0x140012d1c  jns     short loc_140012D4C
0x140012d1e  jmp     short loc_140012D2C
0x140012d20  mov     edi, 0C000000Dh
0x140012d25  lea     rsi, [rbx+120h]
0x140012d2c  mov     eax, [rbx+180h]
0x140012d32  test    al, 1
0x140012d34  jz      short loc_140012D4C
0x140012d36  mov     rcx, rsi; Lookaside
0x140012d39  call    cs:__imp_ExDeleteLookasideListEx
0x140012d40  nop     dword ptr [rax+rax+00h]
0x140012d45  and     dword ptr [rbx+180h], 0FFFFFFFEh
0x140012d4c  mov     eax, [rbx+19Ch]
0x140012d52  mov     ecx, edi
0x140012d54  shr     ecx, 16h
0x140012d57  btr     eax, 9
0x140012d5b  not     ecx
0x140012d5d  and     ecx, 200h
0x140012d63  or      ecx, eax
0x140012d65  mov     [rbx+19Ch], ecx
0x140012d6b  jmp     short loc_140012D72
0x140012d6d  mov     edi, 0C053402Bh
0x140012d72  mov     rbx, [rsp+48h+arg_0]
0x140012d77  mov     eax, edi
0x140012d79  mov     rsi, [rsp+48h+arg_8]
0x140012d7e  add     rsp, 40h
0x140012d82  pop     rdi
0x140012d83  retn
```
