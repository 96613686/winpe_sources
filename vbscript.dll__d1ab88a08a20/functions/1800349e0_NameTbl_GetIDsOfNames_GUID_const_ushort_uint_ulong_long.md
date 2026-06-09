# NameTbl::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x1800349e0`
- end: `0x180034b4e`
- name: `?GetIDsOfNames@NameTbl@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `366`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800349e0`
- `0x180079436`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180034a01`
- `KERNEL32!GetCurrentThreadId` at `0x180034a01`

## pseudocode

```c
__int64 __fastcall NameTbl::GetIDsOfNames(
        NameTbl *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        unsigned int a5,
        int *a6)
{
  int v6; // ebx
  __int64 v11; // rax
  unsigned __int16 *v12; // r8
  __int64 v13; // rdx
  unsigned int v14; // r15d
  int v15; // eax
  unsigned __int16 v16; // r9
  int *v17; // rdi
  int v18; // ebx
  bool v19; // sf
  unsigned __int16 *v21; // [rsp+30h] [rbp-38h] BYREF
  __int128 v22; // [rsp+38h] [rbp-30h]
  __int64 v23; // [rsp+70h] [rbp+8h] BYREF

  v6 = *((_DWORD *)this + 8);
  if ( GetCurrentThreadId() != v6 )
    return 2147549183LL;
  v11 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a2->Data1 )
    v11 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)a2->Data4;
  if ( !v11 )
  {
    if ( a4 )
    {
      v12 = *a3;
      v13 = -1;
      v14 = 0;
      v21 = *a3;
      v23 = 0;
      v22 = 0;
      do
        ++v13;
      while ( v12[v13] );
      v15 = 0;
      for ( LODWORD(v22) = v13; (int)v13 > 0; v15 = v16 + 17 * v15 )
      {
        v16 = *v12++;
        LODWORD(v13) = v13 - 1;
        if ( (unsigned __int16)(v16 - 65) <= 0x19u )
          v16 += 32;
      }
      v17 = a6;
      DWORD1(v22) = v15;
      v18 = (*(__int64 (__fastcall **)(NameTbl *, unsigned __int16 **, __int64 *, int *))(*(_QWORD *)this + 240LL))(
              this,
              &v21,
              &v23,
              a6);
      v19 = v18 < 0;
      if ( v18 )
      {
LABEL_13:
        if ( v19 )
          goto LABEL_15;
        goto LABEL_14;
      }
      if ( (*(_BYTE *)(v23 + 24) & 4) != 0 )
      {
LABEL_14:
        v18 = -2147352570;
LABEL_15:
        if ( v14 < a4 )
          memset_0(&v17[v14], -1, 4LL * (a4 - v14));
        return (unsigned int)v18;
      }
      v14 = 1;
      if ( a4 > 1 )
      {
        v19 = 0;
        goto LABEL_13;
      }
    }
    else
    {
      return (unsigned int)-2147352570;
    }
    return (unsigned int)v18;
  }
  return 2147614721LL;
}

```

## disassembly

```asm
0x1800349e0  mov     [rsp+arg_10], rbx
0x1800349e5  mov     [rsp+arg_18], rbp
0x1800349ea  push    rsi
0x1800349eb  push    rdi
0x1800349ec  push    r14
0x1800349ee  sub     rsp, 50h
0x1800349f2  mov     ebx, [rcx+20h]
0x1800349f5  mov     ebp, r9d
0x1800349f8  mov     rsi, r8
0x1800349fb  mov     rdi, rdx
0x1800349fe  mov     r14, rcx
0x180034a01  call    cs:__imp_GetCurrentThreadId
0x180034a08  nop     dword ptr [rax+rax+00h]
0x180034a0d  cmp     eax, ebx
0x180034a0f  jnz     loc_180034B02
0x180034a15  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180034a1c  sub     rax, [rdi]
0x180034a1f  jnz     short loc_180034A2C
0x180034a21  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180034a28  sub     rax, [rdi+8]
0x180034a2c  test    rax, rax
0x180034a2f  jnz     loc_180034B3C
0x180034a35  test    ebp, ebp
0x180034a37  jz      loc_180034B43
0x180034a3d  mov     r8, [rsi]
0x180034a40  xorps   xmm0, xmm0
0x180034a43  mov     [rsp+68h+arg_8], r15
0x180034a48  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180034a4f  xor     r15d, r15d
0x180034a52  mov     [rsp+68h+var_38], r8
0x180034a57  mov     [rsp+68h+arg_0], r15
0x180034a5c  movdqu  [rsp+68h+var_30], xmm0
0x180034a62  inc     rdx
0x180034a65  cmp     [r8+rdx*2], r15w
0x180034a6a  jnz     short loc_180034A62
0x180034a6c  xor     eax, eax
0x180034a6e  mov     dword ptr [rsp+68h+var_30], edx
0x180034a72  test    edx, edx
0x180034a74  jle     short loc_180034AA1
0x180034a76  nop     word ptr [rax+rax+00000000h]
0x180034a80  movzx   r9d, word ptr [r8]
0x180034a84  lea     r8, [r8+2]
0x180034a88  dec     edx
0x180034a8a  lea     ecx, [r9-41h]
0x180034a8e  cmp     cx, 19h
0x180034a92  jbe     short loc_180034AFB
0x180034a94  imul    eax, 11h
0x180034a97  movzx   ecx, r9w
0x180034a9b  add     eax, ecx
0x180034a9d  test    edx, edx
0x180034a9f  jg      short loc_180034A80
0x180034aa1  mov     rdi, [rsp+68h+arg_28]
0x180034aa9  lea     r8, [rsp+68h+arg_0]
0x180034aae  mov     dword ptr [rsp+68h+var_30+4], eax
0x180034ab2  lea     rdx, [rsp+68h+var_38]
0x180034ab7  mov     rax, [r14]
0x180034aba  mov     r9, rdi
0x180034abd  mov     rcx, r14
0x180034ac0  mov     rax, [rax+0F0h]
0x180034ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034acc  mov     ebx, eax
0x180034ace  test    eax, eax
0x180034ad0  jz      short loc_180034B09
0x180034ad2  js      short loc_180034AD9
0x180034ad4  mov     ebx, 80020006h
0x180034ad9  cmp     r15d, ebp
0x180034adc  jnb     short loc_180034B1F
0x180034ade  mov     eax, r15d
0x180034ae1  sub     ebp, r15d
0x180034ae4  mov     r8d, ebp
0x180034ae7  mov     edx, 0FFFFFFFFh; Val
0x180034aec  shl     r8, 2; Size
0x180034af0  lea     rcx, [rdi+rax*4]; void *
0x180034af4  call    memset_0
0x180034af9  jmp     short loc_180034B1F
0x180034afb  add     r9w, 20h ; ' '
0x180034b00  jmp     short loc_180034A94
0x180034b02  mov     eax, 8000FFFFh
0x180034b07  jmp     short loc_180034B26
0x180034b09  mov     rcx, [rsp+68h+arg_0]
0x180034b0e  test    byte ptr [rcx+18h], 4
0x180034b12  jnz     short loc_180034AD4
0x180034b14  mov     r15d, 1
0x180034b1a  cmp     ebp, r15d
0x180034b1d  ja      short loc_180034B4A
0x180034b1f  mov     r15, [rsp+68h+arg_8]
0x180034b24  mov     eax, ebx
0x180034b26  lea     r11, [rsp+68h+var_18]
0x180034b2b  mov     rbx, [r11+30h]
0x180034b2f  mov     rbp, [r11+38h]
0x180034b33  mov     rsp, r11
0x180034b36  pop     r14
0x180034b38  pop     rdi
0x180034b39  pop     rsi
0x180034b3a  retn
0x180034b3c  mov     eax, 80020001h
0x180034b41  jmp     short loc_180034B26
0x180034b43  mov     ebx, 80020006h
0x180034b48  jmp     short loc_180034B24
0x180034b4a  test    eax, eax
0x180034b4c  jmp     short loc_180034AD2
```
