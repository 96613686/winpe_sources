# UdfUpdateTimestampsToIcb

- ea: `0x14003dd50`
- end: `0x14003dec1`
- name: `UdfUpdateTimestampsToIcb`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140005e80`

## callees

- `0x14000a870`
- `0x14001c080`
- `0x14003dd50`
- `0x14003f198`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14003deb4`
- `ntoskrnl!ExRaiseStatus` at `0x14003deb4`

## pseudocode

```c
__int64 __fastcall UdfUpdateTimestampsToIcb(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r15
  unsigned __int64 v7; // rcx
  _WORD *v8; // rbx
  _WORD *v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int64 v18; // rax
  __int16 v19; // cx
  int v20; // eax
  _QWORD *v21; // [rsp+20h] [rbp-59h] BYREF
  _WORD *v22; // [rsp+28h] [rbp-51h]
  int v23; // [rsp+30h] [rbp-49h]
  int v24; // [rsp+34h] [rbp-45h]
  __int16 v25; // [rsp+38h] [rbp-41h]
  int v26; // [rsp+3Ah] [rbp-3Fh]
  __int16 v27; // [rsp+3Eh] [rbp-3Bh]
  _QWORD v28[18]; // [rsp+40h] [rbp-39h] BYREF

  v26 = 0;
  v27 = 0;
  v6 = 48;
  memset(v28, 0, 0x60u);
  v8 = *(_WORD **)a3;
  if ( **(_WORD **)a3 == 266 )
  {
    v9 = v8 + 52;
LABEL_3:
    UdfConvertNtTimeToUdfTime(v7, a2, v9);
    goto LABEL_4;
  }
  v16 = *(_OWORD *)(a3 + 8);
  v28[2] = *(_QWORD *)a3;
  v17 = *(_OWORD *)(a3 + 24);
  v21 = v28;
  v18 = 88;
  *(_OWORD *)&v28[3] = v16;
  *(_OWORD *)&v28[5] = v17;
  v19 = *v8;
  if ( *v8 != 261 )
    v18 = 108;
  v22 = &v8[v18];
  if ( v19 == 261 )
    v20 = *((_DWORD *)v8 + 42);
  else
    v20 = *((_DWORD *)v8 + 52);
  v23 = v20;
  v25 = 1;
  v24 = 5;
  if ( UdfLookupEa(a1, (__int64)&v21) && (v22[8] & 1) != 0 )
  {
    v9 = v22 + 10;
    v7 = (unsigned __int64)v22 + *((unsigned int *)v22 + 2);
    if ( (unsigned __int64)(v22 + 16) > v7 )
    {
      *(_DWORD *)(a1 + 24) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
    goto LABEL_3;
  }
LABEL_4:
  v11 = 36;
  if ( *v8 != 261 )
    v11 = 40;
  UdfConvertNtTimeToUdfTime(v10, a2 + 8, &v8[v11]);
  v13 = 42;
  if ( *v8 != 261 )
    v13 = 46;
  UdfConvertNtTimeToUdfTime(v12, a2 + 16, &v8[v13]);
  if ( *v8 != 261 )
    v6 = 58;
  return UdfConvertNtTimeToUdfTime(v14, a2 + 24, &v8[v6]);
}

```

## disassembly

```asm
0x14003dd50  push    rbp
0x14003dd52  push    rbx
0x14003dd53  push    rsi
0x14003dd54  push    rdi
0x14003dd55  push    r12
0x14003dd57  push    r14
0x14003dd59  push    r15
0x14003dd5b  lea     rbp, [rsp-27h]
0x14003dd60  sub     rsp, 0A0h
0x14003dd67  xor     eax, eax
0x14003dd69  mov     [rbp+57h+var_96], 0
0x14003dd70  mov     r14, r8
0x14003dd73  mov     [rbp+57h+var_92], ax
0x14003dd77  mov     rdi, rdx
0x14003dd7a  mov     rsi, rcx
0x14003dd7d  xor     edx, edx; Val
0x14003dd7f  lea     rcx, [rbp+57h+var_90]; void *
0x14003dd83  lea     r15d, [rax+60h]
0x14003dd87  mov     r8d, r15d; Size
0x14003dd8a  call    memset
0x14003dd8f  mov     rbx, [r14]
0x14003dd92  mov     eax, 10Ah
0x14003dd97  lea     r12d, [rax-5]
0x14003dd9b  cmp     [rbx], ax
0x14003dd9e  jnz     short loc_14003DE13
0x14003dda0  lea     r8, [rbx+68h]
0x14003dda4  mov     rdx, rdi
0x14003dda7  call    UdfConvertNtTimeToUdfTime
0x14003ddac  cmp     [rbx], r12w
0x14003ddb0  lea     rdx, [rdi+8]
0x14003ddb4  mov     eax, 50h ; 'P'
0x14003ddb9  lea     r8d, [rax-8]
0x14003ddbd  cmovnz  r8d, eax
0x14003ddc1  add     r8, rbx
0x14003ddc4  call    UdfConvertNtTimeToUdfTime
0x14003ddc9  cmp     [rbx], r12w
0x14003ddcd  lea     rdx, [rdi+10h]
0x14003ddd1  mov     eax, 5Ch ; '\'
0x14003ddd6  lea     r8d, [rax-8]
0x14003ddda  cmovnz  r8d, eax
0x14003ddde  add     r8, rbx
0x14003dde1  call    UdfConvertNtTimeToUdfTime
0x14003dde6  cmp     [rbx], r12w
0x14003ddea  lea     rdx, [rdi+18h]
0x14003ddee  mov     eax, 74h ; 't'
0x14003ddf3  cmovnz  r15, rax
0x14003ddf7  lea     r8, [rbx+r15]
0x14003ddfb  call    UdfConvertNtTimeToUdfTime
0x14003de00  add     rsp, 0A0h
0x14003de07  pop     r15
0x14003de09  pop     r14
0x14003de0b  pop     r12
0x14003de0d  pop     rdi
0x14003de0e  pop     rsi
0x14003de0f  pop     rbx
0x14003de10  pop     rbp
0x14003de11  retn
0x14003de13  movups  xmm0, xmmword ptr [r14+8]
0x14003de18  lea     rax, [rbp+57h+var_90]
0x14003de1c  mov     [rbp+57h+var_80], rbx
0x14003de20  movups  xmm1, xmmword ptr [r14+18h]
0x14003de25  mov     [rbp+57h+var_B0], rax
0x14003de29  mov     eax, 0B0h
0x14003de2e  movups  [rbp+57h+var_78], xmm0
0x14003de32  movups  [rbp+57h+var_68], xmm1
0x14003de36  movzx   ecx, word ptr [rbx]
0x14003de39  lea     edx, [rax+28h]
0x14003de3c  cmp     cx, r12w
0x14003de40  cmovnz  eax, edx
0x14003de43  add     rax, rbx
0x14003de46  mov     [rbp+57h+var_A8], rax
0x14003de4a  cmp     cx, r12w
0x14003de4e  jnz     short loc_14003DE58
0x14003de50  mov     eax, [rbx+0A8h]
0x14003de56  jmp     short loc_14003DE5E
0x14003de58  mov     eax, [rbx+0D0h]
0x14003de5e  mov     r14d, 1
0x14003de64  mov     [rbp+57h+var_A0], eax
0x14003de67  lea     rdx, [rbp+57h+var_B0]
0x14003de6b  mov     [rbp+57h+var_98], r14w
0x14003de70  mov     rcx, rsi
0x14003de73  mov     [rbp+57h+var_9C], 5
0x14003de7a  call    UdfLookupEa
0x14003de7f  test    al, al
0x14003de81  jz      loc_14003DDAC
0x14003de87  mov     rdx, [rbp+57h+var_A8]
0x14003de8b  test    [rdx+10h], r14b
0x14003de8f  jz      loc_14003DDAC
0x14003de95  mov     ecx, [rdx+8]
0x14003de98  lea     r8, [rdx+14h]
0x14003de9c  add     rcx, rdx
0x14003de9f  lea     rax, [r8+0Ch]
0x14003dea3  cmp     rax, rcx
0x14003dea6  jbe     loc_14003DDA4
0x14003deac  mov     ecx, 0C0000102h; Status
0x14003deb1  mov     [rsi+18h], ecx
0x14003deb4  call    cs:__imp_ExRaiseStatus
```
