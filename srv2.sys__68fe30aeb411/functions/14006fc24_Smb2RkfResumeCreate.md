# Smb2RkfResumeCreate

- ea: `0x14006fc24`
- end: `0x14006fe4b`
- name: `Smb2RkfResumeCreate`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140079710`

## callees

- `0x14001ed38`
- `0x140038490`
- `0x14006ea80`
- `0x14006fc24`
- `0x14007a240`
- `0x14007a84c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006fdd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fdd7`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14006fdb2`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14006fdb2`

## pseudocode

```c
__int64 __fastcall Smb2RkfResumeCreate(_QWORD *a1)
{
  __int64 v1; // rdi
  _DWORD *v3; // rbp
  int Ecps; // ebx
  int v6; // eax
  struct _ECP_LIST *v7; // rcx
  struct _IO_STATUS_BLOCK v8; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v9; // [rsp+D0h] [rbp-38h] BYREF
  int v10; // [rsp+D8h] [rbp-30h]

  v1 = a1[70];
  v3 = *(_DWORD **)(a1[38] + 24LL);
  v9 = 0;
  v10 = 0;
  v8 = 0;
  if ( !*(_BYTE *)(v1 + 378) )
    return 3221225485LL;
  LODWORD(v9) = 12;
  HIDWORD(v9) = v3[17];
  LOWORD(v10) = 0;
  Ecps = Smb2CreateEcps((__int64)a1);
  if ( Ecps >= 0 )
  {
    v6 = Smb2CreateFile(
           (struct _UNICODE_STRING *)(v1 + 192),
           v3[22],
           v3[23],
           v3[24],
           1u,
           v3[26] | 0x100u,
           (union _LARGE_INTEGER *)(v1 + 240),
           *(void **)(v1 + 208),
           *(_DWORD *)(v1 + 216),
           *(_QWORD *)(v1 + 224),
           &v9,
           0,
           (v1 + 232) & -(__int64)(*(_QWORD *)(v1 + 232) != 0),
           0,
           0,
           521,
           a1,
           &v8,
           0,
           *(struct _ECP_LIST **)(v1 + 320),
           *(_QWORD *)(v1 + 361),
           0,
           1u);
    v7 = *(struct _ECP_LIST **)(v1 + 320);
    Ecps = v6;
    if ( v7 && !*(_BYTE *)(v1 + 328) )
    {
      FsRtlFreeExtraCreateParameterList(v7);
      *(_QWORD *)(v1 + 320) = 0;
    }
    if ( Ecps == -2147483603 )
    {
      ExFreePoolWithTag((PVOID)v8.Information, 0);
    }
    else if ( Ecps >= 0 && Ecps != 264 )
    {
      Ecps = Smb2RequestOplockForResumedCreate(a1);
      if ( Ecps >= 0 )
      {
        if ( *(_BYTE *)(v1 + 381) )
        {
          Smb2RkfNotifyComplete(a1[8], *(_QWORD *)(*(_QWORD *)(v1 + 80) + 96LL));
          *(_BYTE *)(v1 + 381) = 0;
        }
      }
    }
  }
  return (unsigned int)Ecps;
}

```

## disassembly

```asm
0x14006fc24  mov     r11, rsp
0x14006fc27  mov     [r11+10h], rbx
0x14006fc2b  mov     [r11+18h], rbp
0x14006fc2f  push    rsi
0x14006fc30  push    rdi
0x14006fc31  push    r14
0x14006fc33  sub     rsp, 0F0h
0x14006fc3a  mov     rax, cs:__security_cookie
0x14006fc41  xor     rax, rsp
0x14006fc44  mov     [rsp+108h+var_28], rax
0x14006fc4c  mov     rax, [rcx+130h]
0x14006fc53  xorps   xmm0, xmm0
0x14006fc56  mov     rdi, [rcx+230h]
0x14006fc5d  xor     r14d, r14d
0x14006fc60  mov     rsi, rcx
0x14006fc63  mov     rbp, [rax+18h]
0x14006fc67  xor     eax, eax
0x14006fc69  mov     [r11-38h], rax
0x14006fc6d  mov     [r11-30h], eax
0x14006fc71  movups  xmmword ptr [r11-48h], xmm0
0x14006fc76  cmp     [rdi+17Ah], r14b
0x14006fc7d  jnz     short loc_14006FC89
0x14006fc7f  mov     eax, 0C000000Dh
0x14006fc84  jmp     loc_14006FE22
0x14006fc89  mov     dword ptr [rsp+108h+var_38], 0Ch
0x14006fc94  mov     eax, [rbp+44h]
0x14006fc97  mov     dword ptr [rsp+108h+var_38+4], eax
0x14006fc9e  mov     word ptr [rsp+108h+var_30], r14w
0x14006fca7  call    Smb2CreateEcps
0x14006fcac  mov     ebx, eax
0x14006fcae  test    eax, eax
0x14006fcb0  js      loc_14006FE20
0x14006fcb6  mov     r9d, [rbp+68h]
0x14006fcba  lea     rcx, [rdi+0E8h]
0x14006fcc1  mov     rax, [rcx]
0x14006fcc4  lea     r8, [rdi+0F0h]
0x14006fccb  mov     [rsp+108h+var_58], 1; char
0x14006fcd3  neg     rax
0x14006fcd6  mov     rax, [rdi+169h]
0x14006fcdd  mov     [rsp+108h+var_60], r14b; char
0x14006fce5  sbb     rdx, rdx
0x14006fce8  mov     [rsp+108h+var_68], rax; __int64
0x14006fcf0  and     rdx, rcx
0x14006fcf3  mov     rax, [rdi+140h]
0x14006fcfa  lea     rcx, [rdi+0C0h]; int
0x14006fd01  mov     [rsp+108h+var_70], rax; __int64
0x14006fd09  bts     r9d, 8
0x14006fd0e  mov     qword ptr [rsp+108h+var_78], r14; int
0x14006fd16  lea     rax, [rsp+108h+var_48]
0x14006fd1e  mov     [rsp+108h+var_80], rax; __int64
0x14006fd26  lea     rax, [rsp+108h+var_38]
0x14006fd2e  mov     [rsp+108h+var_88], rsi; __int64
0x14006fd36  mov     [rsp+108h+var_90], 209h; int
0x14006fd3e  mov     qword ptr [rsp+108h+var_98], r14; int
0x14006fd43  mov     [rsp+108h+var_A0], r14d; int
0x14006fd48  mov     [rsp+108h+var_A8], rdx; __int64
0x14006fd4d  mov     edx, [rbp+58h]; int
0x14006fd50  mov     dword ptr [rsp+108h+var_B0], r14d; char
0x14006fd55  mov     [rsp+108h+var_B8], rax; __int64
0x14006fd5a  mov     rax, [rdi+0E0h]
0x14006fd61  mov     [rsp+108h+var_C0], rax; __int64
0x14006fd66  mov     eax, [rdi+0D8h]
0x14006fd6c  mov     [rsp+108h+var_C8], eax; ULONG
0x14006fd70  mov     rax, [rdi+0D0h]
0x14006fd77  mov     [rsp+108h+var_D0], rax; __int64
0x14006fd7c  mov     [rsp+108h+var_D8], r8; __int64
0x14006fd81  mov     r8d, [rbp+5Ch]; int
0x14006fd85  mov     [rsp+108h+var_E0], r9d; int
0x14006fd8a  mov     r9d, [rbp+60h]; int
0x14006fd8e  mov     [rsp+108h+var_E8], 1; ULONG
0x14006fd96  call    Smb2CreateFile
0x14006fd9b  mov     rcx, [rdi+140h]; EcpList
0x14006fda2  mov     ebx, eax
0x14006fda4  test    rcx, rcx
0x14006fda7  jz      short loc_14006FDC5
0x14006fda9  cmp     [rdi+148h], r14b
0x14006fdb0  jnz     short loc_14006FDC5
0x14006fdb2  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14006fdb9  nop     dword ptr [rax+rax+00h]
0x14006fdbe  mov     [rdi+140h], r14
0x14006fdc5  cmp     ebx, 8000002Dh
0x14006fdcb  jnz     short loc_14006FDE5
0x14006fdcd  mov     rcx, [rsp+108h+P]; P
0x14006fdd5  xor     edx, edx; Tag
0x14006fdd7  call    cs:__imp_ExFreePoolWithTag
0x14006fdde  nop     dword ptr [rax+rax+00h]
0x14006fde3  jmp     short loc_14006FE20
0x14006fde5  test    ebx, ebx
0x14006fde7  js      short loc_14006FE20
0x14006fde9  cmp     ebx, 108h
0x14006fdef  jz      short loc_14006FE20
0x14006fdf1  mov     rcx, rsi
0x14006fdf4  call    Smb2RequestOplockForResumedCreate
0x14006fdf9  mov     ebx, eax
0x14006fdfb  test    eax, eax
0x14006fdfd  js      short loc_14006FE20
0x14006fdff  cmp     [rdi+17Dh], r14b
0x14006fe06  jz      short loc_14006FE20
0x14006fe08  mov     rdx, [rdi+50h]
0x14006fe0c  mov     rcx, [rsi+40h]
0x14006fe10  mov     rdx, [rdx+60h]
0x14006fe14  call    Smb2RkfNotifyComplete
0x14006fe19  mov     [rdi+17Dh], r14b
0x14006fe20  mov     eax, ebx
0x14006fe22  mov     rcx, [rsp+108h+var_28]
0x14006fe2a  xor     rcx, rsp; StackCookie
0x14006fe2d  call    __security_check_cookie
0x14006fe32  lea     r11, [rsp+108h+var_18]
0x14006fe3a  mov     rbx, [r11+28h]
0x14006fe3e  mov     rbp, [r11+30h]
0x14006fe42  mov     rsp, r11
0x14006fe45  pop     r14
0x14006fe47  pop     rdi
0x14006fe48  pop     rsi
0x14006fe49  retn
```
