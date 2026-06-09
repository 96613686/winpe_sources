# SLGetTokenActivationGrants

- ea: `0x18003dee0`
- end: `0x18003e138`
- name: `SLGetTokenActivationGrants`
- size: `600`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x180004590`
- `0x180004ca0`
- `0x180006c10`
- `0x180007638`
- `0x1800365f4`
- `0x1800368dc`
- `0x1800369e0`
- `0x180037cf8`
- `0x18003a27c`
- `0x18003b1fc`
- `0x18003dee0`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043364`
- `0x18004362c`
- `0x180043900`
- `0x180043bd8`
- `0x180043eac`

## import_xrefs

- `sppc!SLpGetTokenActivationGrantInfo` at `0x18003dfe4`
- `sppc!SLpGetTokenActivationGrantInfo` at `0x18003dfe4`

## pseudocode

```c
__int64 __fastcall SLGetTokenActivationGrants(__int64 a1, __int64 a2, _QWORD *a3)
{
  int TokenActivationGrantInfo; // edi
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // r14
  __int64 v13; // r15
  unsigned int v14; // esi
  __int64 v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h] BYREF
  __int64 v19; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v20; // [rsp+80h] [rbp+30h] BYREF
  int v21; // [rsp+98h] [rbp+48h] BYREF

  v18 = 0;
  sub_180042ACC(byte_180082C48, byte_18008CB70);
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v17 = 0;
  v16 = 0;
  sub_18004362C(qword_180083938, byte_18008DFD0);
  if ( a1 && a2 )
  {
    if ( !a3 )
    {
      sub_180043BD8(qword_180082848, &dword_18008D324);
      TokenActivationGrantInfo = -2147024809;
      sub_180043364(qword_180083528, qword_18008CC40);
      sub_180004CA0(2147942487LL);
      sub_180042514(byte_180082A48, byte_18008D430);
      goto LABEL_19;
    }
    TokenActivationGrantInfo = SLpGetTokenActivationGrantInfo(a1, a2, &v20, &v18, &v21, &v19);
    sub_180043900(qword_180080CE8, qword_18008D768);
    if ( TokenActivationGrantInfo < 0 )
    {
      sub_180004CA0((unsigned int)TokenActivationGrantInfo);
      sub_1800427F4(qword_1800839C8, qword_18008E018);
      goto LABEL_19;
    }
    v10 = sub_1800369E0(v9, v8, &v17);
    TokenActivationGrantInfo = v10;
    if ( v10 >= 0 )
    {
      v11 = v17;
      TokenActivationGrantInfo = sub_18003A27C(v17, v18, v20);
      if ( TokenActivationGrantInfo < 0 )
      {
        sub_180043088(byte_180082458, byte_18008CFB0);
        v7 = (unsigned int)TokenActivationGrantInfo;
        goto LABEL_3;
      }
      v12 = (unsigned int)sub_1800365F4(v11);
      TokenActivationGrantInfo = sub_1800368DC(v12, &v16);
      sub_180042DB0(byte_1800831A8, byte_18008DA80);
      if ( TokenActivationGrantInfo < 0 )
      {
        sub_180004CA0((unsigned int)TokenActivationGrantInfo);
        sub_180043EAC(qword_180085650, qword_18008E2C0);
        goto LABEL_19;
      }
      v13 = v16;
      v14 = 0;
      if ( !(_DWORD)v12 )
      {
LABEL_18:
        v16 = 0;
        *a3 = v13;
        goto LABEL_19;
      }
      while ( 1 )
      {
        v10 = sub_180037CF8(v11, v14, v13 + 8 * (v14 + 1LL));
        TokenActivationGrantInfo = v10;
        if ( v10 < 0 )
          break;
        if ( ++v14 >= (unsigned int)v12 )
          goto LABEL_18;
      }
    }
    v7 = (unsigned int)v10;
  }
  else
  {
    TokenActivationGrantInfo = -2147024809;
    v7 = 2147942487LL;
  }
LABEL_3:
  sub_180004CA0(v7);
LABEL_19:
  sub_180006C10((unsigned int)TokenActivationGrantInfo);
  sub_18003B1FC(&v16);
  sub_180004590(&v17);
  sub_180007638(&v19);
  sub_180007638(&v18);
  return (unsigned int)TokenActivationGrantInfo;
}

```

## disassembly

```asm
0x18003dee0  mov     [rsp-28h+arg_8], rbx
0x18003dee5  mov     [rsp-28h+arg_10], rsi
0x18003deea  push    rbp
0x18003deeb  push    rdi
0x18003deec  push    r12
0x18003deee  push    r14
0x18003def0  push    r15
0x18003def2  mov     rbp, rsp
0x18003def5  sub     rsp, 50h
0x18003def9  mov     rbx, rdx
0x18003defc  mov     [rbp+var_10], 0
0x18003df04  mov     rdi, rcx
0x18003df07  lea     rdx, byte_18008CB70
0x18003df0e  lea     rcx, byte_180082C48
0x18003df15  mov     r12, r8
0x18003df18  call    sub_180042ACC
0x18003df1d  lea     rdx, byte_18008DFD0
0x18003df24  mov     [rbp+arg_0], 0
0x18003df2b  lea     rcx, qword_180083938
0x18003df32  mov     [rbp+var_8], 0
0x18003df3a  mov     [rbp+arg_18], 0
0x18003df41  mov     [rbp+var_18], 0
0x18003df49  mov     [rbp+var_20], 0
0x18003df51  call    sub_18004362C
0x18003df56  test    rdi, rdi
0x18003df59  jnz     short loc_18003DF6E
0x18003df5b  mov     ebx, 80070057h
0x18003df60  mov     edi, ebx
0x18003df62  mov     ecx, ebx
0x18003df64  call    sub_180004CA0
0x18003df69  jmp     loc_18003E0F2
0x18003df6e  test    rbx, rbx
0x18003df71  jz      short loc_18003DF5B
0x18003df73  test    r12, r12
0x18003df76  jnz     short loc_18003DFC4
0x18003df78  lea     rdx, dword_18008D324
0x18003df7f  lea     rcx, qword_180082848
0x18003df86  call    sub_180043BD8
0x18003df8b  mov     ebx, 80070057h
0x18003df90  lea     rdx, qword_18008CC40
0x18003df97  lea     rcx, qword_180083528
0x18003df9e  mov     edi, ebx
0x18003dfa0  call    sub_180043364
0x18003dfa5  mov     ecx, ebx
0x18003dfa7  call    sub_180004CA0
0x18003dfac  lea     rdx, byte_18008D430
0x18003dfb3  lea     rcx, byte_180082A48
0x18003dfba  call    sub_180042514
0x18003dfbf  jmp     loc_18003E0F2
0x18003dfc4  lea     rax, [rbp+var_8]
0x18003dfc8  mov     rdx, rbx
0x18003dfcb  mov     [rsp+50h+var_28], rax
0x18003dfd0  lea     r9, [rbp+var_10]
0x18003dfd4  lea     rax, [rbp+arg_18]
0x18003dfd8  mov     rcx, rdi
0x18003dfdb  lea     r8, [rbp+arg_0]
0x18003dfdf  mov     [rsp+50h+var_30], rax
0x18003dfe4  call    cs:SLpGetTokenActivationGrantInfo
0x18003dfea  lea     rdx, qword_18008D768
0x18003dff1  mov     edi, eax
0x18003dff3  lea     rcx, qword_180080CE8
0x18003dffa  call    sub_180043900
0x18003dfff  test    edi, edi
0x18003e001  jns     short loc_18003E022
0x18003e003  mov     ecx, edi
0x18003e005  call    sub_180004CA0
0x18003e00a  lea     rdx, qword_18008E018
0x18003e011  lea     rcx, qword_1800839C8
0x18003e018  call    sub_1800427F4
0x18003e01d  jmp     loc_18003E0F2
0x18003e022  lea     r8, [rbp+var_18]
0x18003e026  call    sub_1800369E0
0x18003e02b  mov     edi, eax
0x18003e02d  test    eax, eax
0x18003e02f  jns     short loc_18003E038
0x18003e031  mov     ecx, eax
0x18003e033  jmp     loc_18003DF64
0x18003e038  mov     rbx, [rbp+var_18]
0x18003e03c  mov     r8d, [rbp+arg_0]
0x18003e040  mov     rcx, rbx
0x18003e043  mov     rdx, [rbp+var_10]
0x18003e047  call    sub_18003A27C
0x18003e04c  mov     edi, eax
0x18003e04e  test    eax, eax
0x18003e050  jns     short loc_18003E06C
0x18003e052  lea     rdx, byte_18008CFB0
0x18003e059  lea     rcx, byte_180082458
0x18003e060  call    sub_180043088
0x18003e065  mov     ecx, edi
0x18003e067  jmp     loc_18003DF64
0x18003e06c  mov     rcx, rbx
0x18003e06f  call    sub_1800365F4
0x18003e074  lea     rdx, [rbp+var_20]
0x18003e078  mov     ecx, eax
0x18003e07a  mov     r14d, eax
0x18003e07d  call    sub_1800368DC
0x18003e082  lea     rdx, byte_18008DA80
0x18003e089  mov     edi, eax
0x18003e08b  lea     rcx, byte_1800831A8
0x18003e092  call    sub_180042DB0
0x18003e097  test    edi, edi
0x18003e099  jns     short loc_18003E0B7
0x18003e09b  mov     ecx, edi
0x18003e09d  call    sub_180004CA0
0x18003e0a2  lea     rdx, qword_18008E2C0
0x18003e0a9  lea     rcx, qword_180085650
0x18003e0b0  call    sub_180043EAC
0x18003e0b5  jmp     short loc_18003E0F2
0x18003e0b7  mov     r15, [rbp+var_20]
0x18003e0bb  xor     esi, esi
0x18003e0bd  test    r14d, r14d
0x18003e0c0  jz      short loc_18003E0E6
0x18003e0c2  mov     eax, esi
0x18003e0c4  mov     edx, esi
0x18003e0c6  inc     rax
0x18003e0c9  mov     rcx, rbx
0x18003e0cc  lea     r8, [r15+rax*8]
0x18003e0d0  call    sub_180037CF8
0x18003e0d5  mov     edi, eax
0x18003e0d7  test    eax, eax
0x18003e0d9  js      loc_18003E031
0x18003e0df  inc     esi
0x18003e0e1  cmp     esi, r14d
0x18003e0e4  jb      short loc_18003E0C2
0x18003e0e6  mov     [rbp+var_20], 0
0x18003e0ee  mov     [r12], r15
0x18003e0f2  mov     ecx, edi
0x18003e0f4  call    sub_180006C10
0x18003e0f9  lea     rcx, [rbp+var_20]
0x18003e0fd  call    sub_18003B1FC
0x18003e102  lea     rcx, [rbp+var_18]
0x18003e106  call    sub_180004590
0x18003e10b  lea     rcx, [rbp+var_8]
0x18003e10f  call    sub_180007638
0x18003e114  lea     rcx, [rbp+var_10]
0x18003e118  call    sub_180007638
0x18003e11d  lea     r11, [rsp+50h+var_s0]
0x18003e122  mov     eax, edi
0x18003e124  mov     rbx, [r11+38h]
0x18003e128  mov     rsi, [r11+40h]
0x18003e12c  mov     rsp, r11
0x18003e12f  pop     r15
0x18003e131  pop     r14
0x18003e133  pop     r12
0x18003e135  pop     rdi
0x18003e136  pop     rbp
0x18003e137  retn
```
