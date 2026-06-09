# SXWriter::data(tagSXFORMATTYPE,int,IStream *)

- ea: `0x1004089c0`
- end: `0x100408b9d`
- name: `?data@SXWriter@@UEAAJW4tagSXFORMATTYPE@@HPEAUIStream@@@Z`
- size: `477`
- prototype: `int __high(enum tagSXFORMATTYPE, int, struct IStream *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x100401350`
- `0x1004089c0`
- `0x1004092b0`
- `0x100409320`
- `0x100409740`
- `0x1004097a0`
- `0x100409840`
- `0x10040adb0`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::data(__int64 a1, int a2, int a3, struct IStream *a4)
{
  unsigned __int64 v5; // r15
  int v7; // ebx
  SXWriter *v9; // rdi
  int v10; // eax
  unsigned int v11; // r12d
  unsigned int v12; // r8d
  unsigned int v13; // edx
  int v14; // [rsp+30h] [rbp-88h]
  _DWORD v15[5]; // [rsp+3Ch] [rbp-7Ch] BYREF
  unsigned __int64 v16[3]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v17[56]; // [rsp+68h] [rbp-50h] BYREF
  int v18; // [rsp+C0h] [rbp+8h] BYREF

  v5 = a3;
  v7 = 0;
  v14 = 0;
  if ( *(_BYTE *)(a1 + 224) )
    return 2147500037LL;
  v9 = (SXWriter *)(a1 - 24);
  SXWriter::endAttributesCheck((SXWriter *)(a1 - 24));
  v10 = a2 - 100;
  if ( a2 < 128 )
    v10 = a2;
  v11 = *((unsigned __int8 *)&SXFormatDataByType + 8 * v10);
  v15[3] = v11;
  if ( (v11 & 0x40) != 0 )
  {
    SXWriter::WriteByte(v9, a2);
    v13 = v5;
    if ( v11 != 64 )
      v13 = v5 >> 1;
    SXWriter::WriteMb32(v9, v13);
    v12 = v5;
    goto LABEL_20;
  }
  if ( a2 != 140 )
  {
    if ( a2 == 141 )
    {
      if ( (_DWORD)v5 == 48 )
      {
        v7 = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, __int64, _DWORD *))a4->lpVtbl->Read)(a4, v17, 48, v15);
        v14 = v7;
        if ( v7 >= 0 )
        {
          if ( v15[0] == 48 )
          {
            SXWriter::WriteQNameHandleData(v9, (struct QNAME_TRIPLE *)v17);
            return (unsigned int)v7;
          }
LABEL_27:
          MXRRaiseException(-2147467259);
          __debugbreak();
          JUMPOUT(0x100408B9DLL);
        }
LABEL_26:
        _mm_lfence();
        MXRRaiseException(v14);
        goto LABEL_27;
      }
LABEL_25:
      MXRRaiseException(-2147467259);
      goto LABEL_26;
    }
    SXWriter::WriteByte(v9, a2);
    v12 = v11;
LABEL_20:
    SXWriter::WriteBytesFromStream(v9, a4, v12);
    return (unsigned int)v7;
  }
  if ( (_DWORD)v5 != 8 )
  {
    MXRRaiseException(-2147467259);
    goto LABEL_23;
  }
  v7 = ((__int64 (__fastcall *)(struct IStream *, unsigned __int64 *, __int64, int *))a4->lpVtbl->Read)(
         a4,
         v16,
         8,
         &v18);
  v14 = v7;
  if ( v7 < 0 )
  {
LABEL_23:
    _mm_lfence();
    MXRRaiseException(v14);
    goto LABEL_24;
  }
  if ( v18 != 8 )
  {
LABEL_24:
    MXRRaiseException(-2147467259);
    goto LABEL_25;
  }
  SXWriter::WriteQNameHandleData(v9, v16[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1004089c0  mov     [rsp+arg_8], rbx
0x1004089c5  mov     [rsp+arg_10], rsi
0x1004089ca  mov     [rsp+arg_18], rdi
0x1004089cf  push    r12
0x1004089d1  push    r14
0x1004089d3  push    r15
0x1004089d5  sub     rsp, 0A0h
0x1004089dc  mov     r14, r9
0x1004089df  movsxd  r15, r8d
0x1004089e2  mov     esi, edx
0x1004089e4  xor     ebx, ebx
0x1004089e6  mov     [rsp+0B8h+var_88], ebx
0x1004089ea  cmp     [rcx+0E0h], bl
0x1004089f0  jz      short loc_1004089FC
0x1004089f2  mov     eax, 80004005h
0x1004089f7  jmp     loc_100408B3D
0x1004089fc  lea     rdi, [rcx-18h]
0x100408a00  mov     rcx, rdi; this
0x100408a03  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x100408a08  lea     eax, [rsi-64h]
0x100408a0b  cmp     esi, 80h
0x100408a11  cmovl   eax, esi
0x100408a14  cdqe
0x100408a16  lea     rcx, ?SXFormatDataByType@@3PAUSXFORMATTYPEDATA@@A; SXFORMATTYPEDATA near * SXFormatDataByType
0x100408a1d  movzx   r12d, byte ptr [rcx+rax*8]
0x100408a22  mov     [rsp+0B8h+var_70], r12d
0x100408a27  test    r12b, 40h
0x100408a2b  jnz     loc_100408AFF
0x100408a31  cmp     esi, 8Ch
0x100408a37  jnz     short loc_100408A94
0x100408a39  cmp     r15d, 8
0x100408a3d  jnz     loc_100408B5B
0x100408a43  mov     rax, [r14]
0x100408a46  lea     r9, [rsp+0B8h+arg_0]
0x100408a4e  mov     r8d, 8
0x100408a54  lea     rdx, [rsp+0B8h+var_68]
0x100408a59  mov     rcx, r14
0x100408a5c  mov     rax, [rax+18h]
0x100408a60  call    cs:__guard_dispatch_icall_fptr
0x100408a66  mov     ebx, eax
0x100408a68  mov     [rsp+0B8h+var_88], eax
0x100408a6c  test    eax, eax
0x100408a6e  js      loc_100408B65
0x100408a74  cmp     [rsp+0B8h+arg_0], 8
0x100408a7c  jnz     loc_100408B71
0x100408a82  mov     rdx, [rsp+0B8h+var_68]; unsigned __int64
0x100408a87  mov     rcx, rdi; this
0x100408a8a  call    ?WriteQNameHandleData@SXWriter@@AEAAX_K@Z; SXWriter::WriteQNameHandleData(unsigned __int64)
0x100408a8f  jmp     loc_100408B31
0x100408a94  cmp     esi, 8Dh
0x100408a9a  jnz     short loc_100408AEE
0x100408a9c  cmp     r15d, 30h ; '0'
0x100408aa0  jnz     loc_100408B7B
0x100408aa6  mov     rax, [r14]
0x100408aa9  lea     r9, [rsp+0B8h+var_7C]
0x100408aae  mov     r8d, 30h ; '0'
0x100408ab4  lea     rdx, [rsp+0B8h+var_50]
0x100408ab9  mov     rcx, r14
0x100408abc  mov     rax, [rax+18h]
0x100408ac0  call    cs:__guard_dispatch_icall_fptr
0x100408ac6  mov     ebx, eax
0x100408ac8  mov     [rsp+0B8h+var_88], eax
0x100408acc  test    eax, eax
0x100408ace  js      loc_100408B85
0x100408ad4  cmp     [rsp+0B8h+var_7C], 30h ; '0'
0x100408ad9  jnz     loc_100408B91
0x100408adf  lea     rdx, [rsp+0B8h+var_50]; struct QNAME_TRIPLE *
0x100408ae4  mov     rcx, rdi; this
0x100408ae7  call    ?WriteQNameHandleData@SXWriter@@AEAAXPEAUQNAME_TRIPLE@@@Z; SXWriter::WriteQNameHandleData(QNAME_TRIPLE *)
0x100408aec  jmp     short loc_100408B31
0x100408aee  movzx   edx, sil; unsigned __int8
0x100408af2  mov     rcx, rdi; this
0x100408af5  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100408afa  mov     r8d, r12d
0x100408afd  jmp     short loc_100408B26
0x100408aff  movzx   edx, sil; unsigned __int8
0x100408b03  mov     rcx, rdi; this
0x100408b06  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100408b0b  mov     rdx, r15
0x100408b0e  mov     rax, r15
0x100408b11  shr     rax, 1
0x100408b14  cmp     r12d, 40h ; '@'
0x100408b18  cmovnz  edx, eax; unsigned int
0x100408b1b  mov     rcx, rdi; this
0x100408b1e  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x100408b23  mov     r8d, r15d; unsigned int
0x100408b26  mov     rdx, r14; struct IStream *
0x100408b29  mov     rcx, rdi; this
0x100408b2c  call    ?WriteBytesFromStream@SXWriter@@IEAAXPEAUIStream@@H@Z; SXWriter::WriteBytesFromStream(IStream *,int)
0x100408b31  jmp     short loc_100408B3B
0x100408b33  mov     ebx, [rsp+0B8h+var_84]
0x100408b37  mov     [rsp+0B8h+var_88], ebx
0x100408b3b  mov     eax, ebx
0x100408b3d  lea     r11, [rsp+0B8h+var_18]
0x100408b45  mov     rbx, [r11+28h]
0x100408b49  mov     rsi, [r11+30h]
0x100408b4d  mov     rdi, [r11+38h]
0x100408b51  mov     rsp, r11
0x100408b54  pop     r15
0x100408b56  pop     r14
0x100408b58  pop     r12
0x100408b5a  retn
0x100408b5b  mov     ecx, 80004005h; int
0x100408b60  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b65  lfence
0x100408b68  mov     ecx, [rsp+0B8h+var_88]; int
0x100408b6c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b71  mov     ecx, 80004005h; int
0x100408b76  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b7b  mov     ecx, 80004005h; int
0x100408b80  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b85  lfence
0x100408b88  mov     ecx, [rsp+0B8h+var_88]; int
0x100408b8c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b91  mov     ecx, 80004005h; int
0x100408b96  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408b9b  nop
0x100408b9c  int     3; Trap to Debugger
0x100424770  push    rbp
0x100424772  sub     rsp, 30h
0x100424776  mov     rbp, rdx
0x100424779  mov     [rbp+60h], rcx
0x10042477d  mov     [rbp+58h], rcx
0x100424781  mov     rax, [rbp+58h]
0x100424785  mov     rcx, [rax]
0x100424788  mov     [rbp+40h], rcx
0x10042478c  mov     rax, [rbp+40h]
0x100424790  mov     eax, [rax]
0x100424792  cmp     eax, 0C0000005h
0x100424797  jz      short loc_1004247C9
0x100424799  add     eax, 1FFFFFFFh
0x10042479e  cmp     eax, 1
0x1004247a1  ja      short loc_1004247B9
0x1004247a3  mov     rax, [rbp+40h]
0x1004247a7  cmp     dword ptr [rax+18h], 1
0x1004247ab  jnz     short loc_1004247B9
0x1004247ad  mov     rax, [rbp+40h]
0x1004247b1  mov     ecx, [rax+20h]
0x1004247b4  mov     [rbp+34h], ecx
0x1004247b7  jmp     short loc_1004247C0
0x1004247b9  mov     dword ptr [rbp+34h], 8000FFFFh
0x1004247c0  mov     dword ptr [rbp+38h], 1
0x1004247c7  jmp     short loc_1004247D0
0x1004247c9  mov     dword ptr [rbp+38h], 0
0x1004247d0  mov     eax, [rbp+38h]
0x1004247d3  add     rsp, 30h
0x1004247d7  pop     rbp
0x1004247d8  retn
```
