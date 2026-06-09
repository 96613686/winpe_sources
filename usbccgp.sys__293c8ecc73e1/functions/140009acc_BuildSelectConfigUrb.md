# BuildSelectConfigUrb

- ea: `0x140009acc`
- end: `0x140009d0f`
- name: `BuildSelectConfigUrb`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140023214`

## callees

- `0x1400088b4`
- `0x140009acc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009c8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009c8c`
- `ntoskrnl!ExAllocatePool2` at `0x140009ba2`
- `ntoskrnl!ExAllocatePool2` at `0x140009ba2`

## pseudocode

```c
_WORD *__fastcall BuildSelectConfigUrb(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4)
{
  __int64 v6; // rbp
  unsigned __int16 v8; // bx
  unsigned __int16 v9; // di
  int v10; // r8d
  __int64 Pool2; // rax
  _WORD *v12; // rbx
  __int64 v13; // rdx
  unsigned __int16 i; // r8
  _BYTE *v15; // r9
  unsigned int v16; // r10d
  __int64 v17; // r11
  char v18; // al
  __int64 v19; // r9
  __int64 v20; // rcx

  v6 = a2;
  v8 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), a2, 1, 49, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
  }
  v9 = 40;
  while ( v8 < a4 )
  {
    LODWORD(a2) = 2 * v8;
    v10 = (unsigned __int16)(24 * (*(unsigned __int8 *)(*(_QWORD *)(a3 + 16LL * v8) + 4LL) + 1));
    if ( v9 > 0xFFFF - v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), a2, 8, 50, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
      }
      return 0;
    }
    v9 += v10;
    *(_QWORD *)(a3 + 16LL * v8++ + 8) = 0;
  }
  if ( v8 == *(unsigned __int8 *)(v6 + 4) )
  {
    Pool2 = ExAllocatePool2(64, v9, 1130525525);
    v12 = (_WORD *)Pool2;
    if ( Pool2 )
    {
      v13 = Pool2 + 40;
      for ( i = 0; ; ++i )
      {
        if ( i >= a4 )
        {
          *v12 = v9;
          v12[1] = 0;
          *((_QWORD *)v12 + 3) = v6;
          return v12;
        }
        v15 = *(_BYTE **)(a3 + 16LL * i);
        v16 = (unsigned __int8)v15[4];
        v17 = (unsigned __int16)(24 * (v16 + 1));
        if ( v17 + v13 > (unsigned __int64)v12 + v9 )
          break;
        *(_BYTE *)(v13 + 2) = v15[2];
        v18 = v15[3];
        v19 = 0;
        *(_BYTE *)(v13 + 3) = v18;
        for ( *(_DWORD *)(v13 + 16) = v16; (unsigned int)v19 < v16; *(_DWORD *)(v13 + 8 * v20 + 44) = 0 )
        {
          v20 = 3 * v19;
          v19 = (unsigned int)(v19 + 1);
          *(_DWORD *)(v13 + 8 * v20 + 40) = -1;
        }
        *(_WORD *)v13 = v17;
        v13 += v17;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v13, 8, 52, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
      }
      ExFreePoolWithTag(v12, 0x43627355u);
      return 0;
    }
  }
  else
  {
    v12 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), a2, 8, 51, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140009acc  push    rbx
0x140009ace  push    rbp
0x140009acf  push    rsi
0x140009ad0  push    rdi
0x140009ad1  push    r12
0x140009ad3  push    r13
0x140009ad5  push    r14
0x140009ad7  push    r15
0x140009ad9  sub     rsp, 38h
0x140009add  movzx   r14d, r9w
0x140009ae1  mov     r15, r8
0x140009ae4  mov     rbp, rdx
0x140009ae7  mov     rsi, rcx
0x140009aea  xor     ebx, ebx
0x140009aec  lea     r9, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009af3  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140009afa  lea     r10, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140009b01  lea     r13d, [rbx+1]
0x140009b05  jz      short loc_140009B2F
0x140009b07  mov     rcx, [rcx+558h]
0x140009b0e  lea     r9d, [rbx+31h]
0x140009b12  mov     r8d, r13d
0x140009b15  mov     [rsp+78h+var_58], r10
0x140009b1a  mov     dl, 4
0x140009b1c  call    WPP_RECORDER_SF_
0x140009b21  lea     r9, WPP_RECORDER_INITIALIZED
0x140009b28  lea     r10, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140009b2f  mov     edi, 28h ; '('
0x140009b34  cmp     bx, r14w
0x140009b38  jnb     short loc_140009B83
0x140009b3a  movzx   edx, bx
0x140009b3d  add     rdx, rdx
0x140009b40  mov     rax, [r15+rdx*8]
0x140009b44  movzx   ecx, byte ptr [rax+4]
0x140009b48  add     cx, r13w
0x140009b4c  movzx   eax, cx
0x140009b4f  add     ax, ax
0x140009b52  add     cx, ax
0x140009b55  movzx   eax, di
0x140009b58  shl     cx, 3
0x140009b5c  movzx   r8d, cx
0x140009b60  mov     ecx, 0FFFFh
0x140009b65  sub     ecx, r8d
0x140009b68  cmp     eax, ecx
0x140009b6a  jg      loc_140009C67
0x140009b70  add     di, r8w
0x140009b74  mov     qword ptr [r15+rdx*8+8], 0
0x140009b7d  add     bx, r13w
0x140009b81  jmp     short loc_140009B34
0x140009b83  movzx   eax, byte ptr [rbp+4]
0x140009b87  cmp     bx, ax
0x140009b8a  jnz     loc_140009CBB
0x140009b90  movzx   r12d, di
0x140009b94  mov     r8d, 43627355h
0x140009b9a  mov     edx, r12d
0x140009b9d  mov     ecx, 40h ; '@'
0x140009ba2  call    cs:__imp_ExAllocatePool2
0x140009ba9  nop     dword ptr [rax+rax+00h]
0x140009bae  mov     rbx, rax
0x140009bb1  test    rax, rax
0x140009bb4  jz      loc_140009C52
0x140009bba  lea     rdx, [rax+28h]
0x140009bbe  xor     r8d, r8d
0x140009bc1  cmp     r8w, r14w
0x140009bc5  jnb     short loc_140009C45
0x140009bc7  movzx   eax, r8w
0x140009bcb  add     rax, rax
0x140009bce  mov     r9, [r15+rax*8]
0x140009bd2  movzx   r10d, byte ptr [r9+4]
0x140009bd7  lea     ecx, [r10+r13]
0x140009bdb  movzx   eax, cx
0x140009bde  add     ax, ax
0x140009be1  add     cx, ax
0x140009be4  lea     rax, [r12+rbx]
0x140009be8  shl     cx, 3
0x140009bec  movzx   r11d, cx
0x140009bf0  lea     r13, [r11+rdx]
0x140009bf4  cmp     r13, rax
0x140009bf7  ja      short loc_140009C74
0x140009bf9  mov     al, [r9+2]
0x140009bfd  mov     [rdx+2], al
0x140009c00  mov     al, [r9+3]
0x140009c04  xor     r9d, r9d
0x140009c07  mov     [rdx+3], al
0x140009c0a  mov     [rdx+10h], r10d
0x140009c0e  test    r10d, r10d
0x140009c11  jz      short loc_140009C2F
0x140009c13  lea     rcx, [r9+r9*2]
0x140009c17  inc     r9d
0x140009c1a  mov     dword ptr [rdx+rcx*8+28h], 0FFFFFFFFh
0x140009c22  mov     dword ptr [rdx+rcx*8+2Ch], 0
0x140009c2a  cmp     r9d, r10d
0x140009c2d  jb      short loc_140009C13
0x140009c2f  mov     [rdx], r11w
0x140009c33  mov     rdx, r13
0x140009c36  mov     r13d, 1
0x140009c3c  add     r8w, r13w
0x140009c40  jmp     loc_140009BC1
0x140009c45  xor     eax, eax
0x140009c47  mov     [rbx], di
0x140009c4a  mov     [rbx+2], ax
0x140009c4e  mov     [rbx+18h], rbp
0x140009c52  mov     rax, rbx
0x140009c55  add     rsp, 38h
0x140009c59  pop     r15
0x140009c5b  pop     r14
0x140009c5d  pop     r13
0x140009c5f  pop     r12
0x140009c61  pop     rdi
0x140009c62  pop     rsi
0x140009c63  pop     rbp
0x140009c64  pop     rbx
0x140009c65  retn
0x140009c67  cmp     cs:WPP_RECORDER_INITIALIZED, r9; __annotation("TMF:",
0x140009c6e  jnz     short loc_140009C9C
0x140009c70  xor     eax, eax
0x140009c72  jmp     short loc_140009C55
0x140009c74  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009c7b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009c82  jnz     short loc_140009CE6
0x140009c84  mov     edx, 43627355h; Tag
0x140009c89  mov     rcx, rbx; P
0x140009c8c  call    cs:__imp_ExFreePoolWithTag
0x140009c93  nop     dword ptr [rax+rax+00h]
0x140009c98  xor     ebx, ebx
0x140009c9a  jmp     short loc_140009C52
0x140009c9c  mov     rcx, [rsi+558h]
0x140009ca3  mov     r9d, 32h ; '2'
0x140009ca9  mov     dl, 2
0x140009cab  mov     [rsp+78h+var_58], r10
0x140009cb0  lea     r8d, [r9-2Ah]
0x140009cb4  call    WPP_RECORDER_SF_
0x140009cb9  jmp     short loc_140009C70
0x140009cbb  xor     ebx, ebx
0x140009cbd  cmp     cs:WPP_RECORDER_INITIALIZED, r9; __annotation("TMF:",
0x140009cc4  jz      short loc_140009C52
0x140009cc6  mov     rcx, [rsi+558h]
0x140009ccd  lea     r9d, [rbx+33h]
0x140009cd1  lea     r8d, [rbx+8]
0x140009cd5  mov     [rsp+78h+var_58], r10
0x140009cda  mov     dl, 2
0x140009cdc  call    WPP_RECORDER_SF_
0x140009ce1  jmp     loc_140009C52
0x140009ce6  mov     rcx, [rsi+558h]
0x140009ced  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140009cf4  mov     r9d, 34h ; '4'
0x140009cfa  mov     [rsp+78h+var_58], rax
0x140009cff  mov     dl, 2
0x140009d01  lea     r8d, [r9-2Ch]
0x140009d05  call    WPP_RECORDER_SF_
0x140009d0a  jmp     loc_140009C84
```
