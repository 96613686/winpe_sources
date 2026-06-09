# PdoGetStringDescriptor

- ea: `0x140025d6c`
- end: `0x140025f30`
- name: `PdoGetStringDescriptor`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400253c4`

## callees

- `0x1400088b4`
- `0x14000aed0`
- `0x1400130c4`
- `0x140025d6c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140025ee2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025ee2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f0d`
- `ntoskrnl!ExAllocatePool2` at `0x140025d97`
- `ntoskrnl!ExAllocatePool2` at `0x140025e7a`
- `ntoskrnl!ExAllocatePool2` at `0x140025d97`
- `ntoskrnl!ExAllocatePool2` at `0x140025e7a`

## pseudocode

```c
__int64 __fastcall PdoGetStringDescriptor(_QWORD *a1, char a2, unsigned __int16 a3, _QWORD *a4, _DWORD *a5)
{
  int v9; // edx
  _DWORD *Pool2; // rsi
  int StringDescriptor; // ebx
  int v12; // r9d
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  _DWORD *v16; // rdi
  int v17; // ecx
  int v19; // [rsp+20h] [rbp-58h]

  Pool2 = (_DWORD *)ExAllocatePool2(64, 4, 1130525525);
  if ( !Pool2 )
  {
    StringDescriptor = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_19;
    v12 = 41;
    goto LABEL_4;
  }
  while ( 1 )
  {
    StringDescriptor = GetStringDescriptor(a1[29], a2, a3, Pool2, 4u);
    if ( StringDescriptor >= 0 )
    {
      if ( *(_BYTE *)Pool2 <= 4u )
      {
        StringDescriptor = -1073741668;
        goto LABEL_19;
      }
      v16 = (_DWORD *)ExAllocatePool2(64, *(unsigned __int8 *)Pool2, 1130525525);
      if ( v16 )
      {
        StringDescriptor = GetStringDescriptor(a1[29], a2, a3, v16, *(unsigned __int8 *)Pool2);
        if ( StringDescriptor >= 0 )
        {
          if ( *(_BYTE *)Pool2 == *(_BYTE *)v16 )
          {
            v17 = *(unsigned __int8 *)Pool2;
            goto LABEL_20;
          }
          StringDescriptor = -1073741668;
        }
        ExFreePoolWithTag(v16, 0x43627355u);
        goto LABEL_19;
      }
      StringDescriptor = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_19;
      v12 = 43;
LABEL_4:
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(a1[49], v9, 8, v12, (__int64)WPP_54beca300c4a353e079921b0991edb26_Traceguids);
      goto LABEL_19;
    }
    if ( a3 == 1033 )
      break;
    a3 = 1033;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dqd(a1[49], v13, v14, v15, v19, a2, a1[28], StringDescriptor);
LABEL_19:
  v17 = 0;
  v16 = 0;
LABEL_20:
  *a4 = v16;
  *a5 = v17;
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x43627355u);
  return (unsigned int)StringDescriptor;
}

```

## disassembly

```asm
0x140025d6c  push    rbx
0x140025d6e  push    rbp
0x140025d6f  push    rsi
0x140025d70  push    rdi
0x140025d71  push    r12
0x140025d73  push    r14
0x140025d75  push    r15
0x140025d77  sub     rsp, 40h
0x140025d7b  movzx   r15d, dl
0x140025d7f  movzx   r14d, r8w
0x140025d83  mov     edx, 4
0x140025d88  mov     rbp, rcx
0x140025d8b  mov     r8d, 43627355h
0x140025d91  mov     r12, r9
0x140025d94  lea     ecx, [rdx+3Ch]
0x140025d97  call    cs:__imp_ExAllocatePool2
0x140025d9e  nop     dword ptr [rax+rax+00h]
0x140025da3  mov     rsi, rax
0x140025da6  test    rax, rax
0x140025da9  jnz     short loc_140025DED
0x140025dab  mov     ebx, 0C000009Ah
0x140025db0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140025db7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140025dbe  jz      loc_140025EEE
0x140025dc4  lea     r9d, [rsi+29h]
0x140025dc8  mov     rcx, [rbp+188h]
0x140025dcf  lea     rax, WPP_54beca300c4a353e079921b0991edb26_Traceguids
0x140025dd6  mov     r8d, 8
0x140025ddc  mov     [rsp+78h+var_58], rax
0x140025de1  mov     dl, 2
0x140025de3  call    WPP_RECORDER_SF_
0x140025de8  jmp     loc_140025EEE
0x140025ded  mov     edi, 409h
0x140025df2  mov     rcx, [rbp+0E8h]
0x140025df9  mov     r9, rsi
0x140025dfc  movzx   r8d, r14w
0x140025e00  mov     dword ptr [rsp+78h+var_58], 4
0x140025e08  mov     dl, r15b
0x140025e0b  call    GetStringDescriptor
0x140025e10  mov     ebx, eax
0x140025e12  test    eax, eax
0x140025e14  jns     short loc_140025E5B
0x140025e16  cmp     r14w, di
0x140025e1a  jz      short loc_140025E21
0x140025e1c  mov     r14d, edi
0x140025e1f  jmp     short loc_140025DF2
0x140025e21  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140025e28  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140025e2f  jz      loc_140025EEE
0x140025e35  mov     rax, [rbp+0E0h]
0x140025e3c  mov     rcx, [rbp+188h]
0x140025e43  mov     [rsp+78h+var_40], ebx
0x140025e47  mov     [rsp+78h+var_48], rax
0x140025e4c  mov     [rsp+78h+var_50], r15d
0x140025e51  call    WPP_RECORDER_SF_dqd
0x140025e56  jmp     loc_140025EEE
0x140025e5b  movzx   eax, byte ptr [rsi]
0x140025e5e  cmp     al, 4
0x140025e60  ja      short loc_140025E6C
0x140025e62  mov     ebx, 0C000009Ch
0x140025e67  jmp     loc_140025EEE
0x140025e6c  mov     rdx, rax
0x140025e6f  mov     ecx, 40h ; '@'
0x140025e74  mov     r8d, 43627355h
0x140025e7a  call    cs:__imp_ExAllocatePool2
0x140025e81  nop     dword ptr [rax+rax+00h]
0x140025e86  mov     rdi, rax
0x140025e89  test    rax, rax
0x140025e8c  jnz     short loc_140025EAC
0x140025e8e  mov     ebx, 0C000009Ah
0x140025e93  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140025e9a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140025ea1  jz      short loc_140025EEE
0x140025ea3  lea     r9d, [rdi+2Bh]
0x140025ea7  jmp     loc_140025DC8
0x140025eac  movzx   eax, byte ptr [rsi]
0x140025eaf  mov     r9, rdi
0x140025eb2  mov     rcx, [rbp+0E8h]
0x140025eb9  movzx   r8d, r14w
0x140025ebd  mov     dl, r15b
0x140025ec0  mov     dword ptr [rsp+78h+var_58], eax
0x140025ec4  call    GetStringDescriptor
0x140025ec9  mov     ebx, eax
0x140025ecb  test    eax, eax
0x140025ecd  js      short loc_140025EDA
0x140025ecf  mov     al, [rdi]
0x140025ed1  cmp     [rsi], al
0x140025ed3  jz      short loc_140025F2B
0x140025ed5  mov     ebx, 0C000009Ch
0x140025eda  mov     edx, 43627355h; Tag
0x140025edf  mov     rcx, rdi; P
0x140025ee2  call    cs:__imp_ExFreePoolWithTag
0x140025ee9  nop     dword ptr [rax+rax+00h]
0x140025eee  xor     ecx, ecx
0x140025ef0  xor     edi, edi
0x140025ef2  mov     rax, [rsp+78h+arg_20]
0x140025efa  mov     [r12], rdi
0x140025efe  mov     [rax], ecx
0x140025f00  test    rsi, rsi
0x140025f03  jz      short loc_140025F19
0x140025f05  mov     edx, 43627355h; Tag
0x140025f0a  mov     rcx, rsi; P
0x140025f0d  call    cs:__imp_ExFreePoolWithTag
0x140025f14  nop     dword ptr [rax+rax+00h]
0x140025f19  mov     eax, ebx
0x140025f1b  add     rsp, 40h
0x140025f1f  pop     r15
0x140025f21  pop     r14
0x140025f23  pop     r12
0x140025f25  pop     rdi
0x140025f26  pop     rsi
0x140025f27  pop     rbp
0x140025f28  pop     rbx
0x140025f29  retn
0x140025f2b  movzx   ecx, byte ptr [rsi]
0x140025f2e  jmp     short loc_140025EF2
```
