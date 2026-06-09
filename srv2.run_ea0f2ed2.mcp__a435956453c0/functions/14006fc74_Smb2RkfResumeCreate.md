# Smb2RkfResumeCreate

- ea: `0x14006fc74`
- end: `0x14006fe9b`
- name: `Smb2RkfResumeCreate`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140079760`

## callees

- `0x14001ed38`
- `0x140038490`
- `0x14006ead0`
- `0x14006fc74`
- `0x14007a290`
- `0x14007a89c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006fe27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fe27`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14006fe02`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14006fe02`

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
0x14006fc74  mov     r11, rsp
0x14006fc77  mov     [r11+10h], rbx
0x14006fc7b  mov     [r11+18h], rbp
0x14006fc7f  push    rsi
0x14006fc80  push    rdi
0x14006fc81  push    r14
0x14006fc83  sub     rsp, 0F0h
0x14006fc8a  mov     rax, cs:__security_cookie
0x14006fc91  xor     rax, rsp
0x14006fc94  mov     [rsp+108h+var_28], rax
0x14006fc9c  mov     rax, [rcx+130h]
0x14006fca3  xorps   xmm0, xmm0
0x14006fca6  mov     rdi, [rcx+230h]
0x14006fcad  xor     r14d, r14d
0x14006fcb0  mov     rsi, rcx
0x14006fcb3  mov     rbp, [rax+18h]
0x14006fcb7  xor     eax, eax
0x14006fcb9  mov     [r11-38h], rax
0x14006fcbd  mov     [r11-30h], eax
0x14006fcc1  movups  xmmword ptr [r11-48h], xmm0
0x14006fcc6  cmp     [rdi+17Ah], r14b
0x14006fccd  jnz     short loc_14006FCD9
0x14006fccf  mov     eax, 0C000000Dh
0x14006fcd4  jmp     loc_14006FE72
0x14006fcd9  mov     dword ptr [rsp+108h+var_38], 0Ch
0x14006fce4  mov     eax, [rbp+44h]
0x14006fce7  mov     dword ptr [rsp+108h+var_38+4], eax
0x14006fcee  mov     word ptr [rsp+108h+var_30], r14w
0x14006fcf7  call    Smb2CreateEcps
0x14006fcfc  mov     ebx, eax
0x14006fcfe  test    eax, eax
0x14006fd00  js      loc_14006FE70
0x14006fd06  mov     r9d, [rbp+68h]
0x14006fd0a  lea     rcx, [rdi+0E8h]
0x14006fd11  mov     rax, [rcx]
0x14006fd14  lea     r8, [rdi+0F0h]
0x14006fd1b  mov     [rsp+108h+var_58], 1; char
0x14006fd23  neg     rax
0x14006fd26  mov     rax, [rdi+169h]
0x14006fd2d  mov     [rsp+108h+var_60], r14b; char
0x14006fd35  sbb     rdx, rdx
0x14006fd38  mov     [rsp+108h+var_68], rax; __int64
0x14006fd40  and     rdx, rcx
0x14006fd43  mov     rax, [rdi+140h]
0x14006fd4a  lea     rcx, [rdi+0C0h]; int
0x14006fd51  mov     [rsp+108h+var_70], rax; __int64
0x14006fd59  bts     r9d, 8
0x14006fd5e  mov     qword ptr [rsp+108h+var_78], r14; int
0x14006fd66  lea     rax, [rsp+108h+var_48]
0x14006fd6e  mov     [rsp+108h+var_80], rax; __int64
0x14006fd76  lea     rax, [rsp+108h+var_38]
0x14006fd7e  mov     [rsp+108h+var_88], rsi; __int64
0x14006fd86  mov     [rsp+108h+var_90], 209h; int
0x14006fd8e  mov     qword ptr [rsp+108h+var_98], r14; int
0x14006fd93  mov     [rsp+108h+var_A0], r14d; int
0x14006fd98  mov     [rsp+108h+var_A8], rdx; __int64
0x14006fd9d  mov     edx, [rbp+58h]; int
0x14006fda0  mov     dword ptr [rsp+108h+var_B0], r14d; char
0x14006fda5  mov     [rsp+108h+var_B8], rax; __int64
0x14006fdaa  mov     rax, [rdi+0E0h]
0x14006fdb1  mov     [rsp+108h+var_C0], rax; __int64
0x14006fdb6  mov     eax, [rdi+0D8h]
0x14006fdbc  mov     [rsp+108h+var_C8], eax; ULONG
0x14006fdc0  mov     rax, [rdi+0D0h]
0x14006fdc7  mov     [rsp+108h+var_D0], rax; __int64
0x14006fdcc  mov     [rsp+108h+var_D8], r8; __int64
0x14006fdd1  mov     r8d, [rbp+5Ch]; int
0x14006fdd5  mov     [rsp+108h+var_E0], r9d; int
0x14006fdda  mov     r9d, [rbp+60h]; int
0x14006fdde  mov     [rsp+108h+var_E8], 1; ULONG
0x14006fde6  call    Smb2CreateFile
0x14006fdeb  mov     rcx, [rdi+140h]; EcpList
0x14006fdf2  mov     ebx, eax
0x14006fdf4  test    rcx, rcx
0x14006fdf7  jz      short loc_14006FE15
0x14006fdf9  cmp     [rdi+148h], r14b
0x14006fe00  jnz     short loc_14006FE15
0x14006fe02  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14006fe09  nop     dword ptr [rax+rax+00h]
0x14006fe0e  mov     [rdi+140h], r14
0x14006fe15  cmp     ebx, 8000002Dh
0x14006fe1b  jnz     short loc_14006FE35
0x14006fe1d  mov     rcx, [rsp+108h+P]; P
0x14006fe25  xor     edx, edx; Tag
0x14006fe27  call    cs:__imp_ExFreePoolWithTag
0x14006fe2e  nop     dword ptr [rax+rax+00h]
0x14006fe33  jmp     short loc_14006FE70
0x14006fe35  test    ebx, ebx
0x14006fe37  js      short loc_14006FE70
0x14006fe39  cmp     ebx, 108h
0x14006fe3f  jz      short loc_14006FE70
0x14006fe41  mov     rcx, rsi
0x14006fe44  call    Smb2RequestOplockForResumedCreate
0x14006fe49  mov     ebx, eax
0x14006fe4b  test    eax, eax
0x14006fe4d  js      short loc_14006FE70
0x14006fe4f  cmp     [rdi+17Dh], r14b
0x14006fe56  jz      short loc_14006FE70
0x14006fe58  mov     rdx, [rdi+50h]
0x14006fe5c  mov     rcx, [rsi+40h]
0x14006fe60  mov     rdx, [rdx+60h]
0x14006fe64  call    Smb2RkfNotifyComplete
0x14006fe69  mov     [rdi+17Dh], r14b
0x14006fe70  mov     eax, ebx
0x14006fe72  mov     rcx, [rsp+108h+var_28]
0x14006fe7a  xor     rcx, rsp; StackCookie
0x14006fe7d  call    __security_check_cookie
0x14006fe82  lea     r11, [rsp+108h+var_18]
0x14006fe8a  mov     rbx, [r11+28h]
0x14006fe8e  mov     rbp, [r11+30h]
0x14006fe92  mov     rsp, r11
0x14006fe95  pop     r14
0x14006fe97  pop     rdi
0x14006fe98  pop     rsi
0x14006fe99  retn
```
