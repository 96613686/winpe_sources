# UpdateTrafficSecretAndDeriveNewKey(unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18006c9c8`
- end: `0x18006cb75`
- name: `?UpdateTrafficSecretAndDeriveNewKey@@YAJ_KPEA_K11@Z`
- size: `429`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180050f90`
- `0x180057400`
- `0x18006bcf0`

## callees

- `0x180021da8`
- `0x180057c8c`
- `0x18006c9c8`

## import_xrefs

- `ncrypt!SslExpandNextGenTrafficKey` at `0x18006ca2c`
- `ncrypt!SslExpandNextGenTrafficKey` at `0x18006ca2c`
- `ncrypt!SslExpandWriteKey` at `0x18006ca8e`
- `ncrypt!SslExpandWriteKey` at `0x18006ca8e`
- `ncrypt!SslFreeObject` at `0x18006cac8`
- `ncrypt!SslFreeObject` at `0x18006cad8`
- `ncrypt!SslFreeObject` at `0x18006cb41`
- `ncrypt!SslFreeObject` at `0x18006cb53`
- `ncrypt!SslFreeObject` at `0x18006cac8`
- `ncrypt!SslFreeObject` at `0x18006cad8`
- `ncrypt!SslFreeObject` at `0x18006cb41`
- `ncrypt!SslFreeObject` at `0x18006cb53`

## pseudocode

```c
__int64 __fastcall UpdateTrafficSecretAndDeriveNewKey(
        __int64 a1,
        unsigned __int64 *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  CCipherMill *v10; // rcx
  __int64 v11; // rdx
  unsigned __int64 v13[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 0;
  v13[0] = 0;
  if ( a1 && a2 && a3 && a4 )
  {
    v8 = SslExpandNextGenTrafficKey(a1, *a2, &v14, 0, 0);
    v9 = v8;
    if ( v8 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v11 = 143;
    }
    else
    {
      v8 = SslExpandWriteKey(a1, v14, v13, 0, 0);
      v9 = v8;
      if ( !v8 )
      {
        if ( *a2 )
          SslFreeObject(*a2, 0);
        if ( *a3 )
          SslFreeObject(*a3, 0);
        *a2 = v14;
        *a3 = v13[0];
        *a4 = 0;
        v14 = 0;
        v13[0] = 0;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return v9;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
LABEL_21:
        if ( v14 )
          SslFreeObject(v14, 0);
        if ( v13[0] )
          SslFreeObject(v13[0], 0);
        return v9;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v11 = 144;
    }
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v8);
    goto LABEL_21;
  }
  return 2148074333LL;
}

```

## disassembly

```asm
0x18006c9c8  mov     rax, rsp
0x18006c9cb  mov     [rax+10h], rbx
0x18006c9cf  mov     [rax+18h], rbp
0x18006c9d3  push    rsi
0x18006c9d4  push    rdi
0x18006c9d5  push    r14
0x18006c9d7  sub     rsp, 40h
0x18006c9db  mov     qword ptr [rax+8], 0
0x18006c9e3  mov     r14, r9
0x18006c9e6  mov     qword ptr [rax-28h], 0
0x18006c9ee  mov     rsi, r8
0x18006c9f1  mov     rdi, rdx
0x18006c9f4  mov     rbp, rcx
0x18006c9f7  test    rcx, rcx
0x18006c9fa  jz      loc_18006CB5D
0x18006ca00  test    rdx, rdx
0x18006ca03  jz      loc_18006CB5D
0x18006ca09  test    r8, r8
0x18006ca0c  jz      loc_18006CB5D
0x18006ca12  test    r9, r9
0x18006ca15  jz      loc_18006CB5D
0x18006ca1b  mov     rdx, [rdx]
0x18006ca1e  lea     r8, [rax+8]
0x18006ca22  xor     r9d, r9d
0x18006ca25  mov     dword ptr [rax-38h], 0
0x18006ca2c  call    cs:__imp_SslExpandNextGenTrafficKey
0x18006ca32  mov     ebx, eax
0x18006ca34  test    eax, eax
0x18006ca36  jz      short loc_18006CA76
0x18006ca38  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ca3f  lea     rdx, WPP_GLOBAL_Control
0x18006ca46  cmp     rcx, rdx
0x18006ca49  jz      loc_18006CB35
0x18006ca4f  test    byte ptr [rcx+1Ch], 1
0x18006ca53  jz      loc_18006CB35
0x18006ca59  mov     edx, 8Fh
0x18006ca5e  mov     rcx, [rcx+10h]
0x18006ca62  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x18006ca69  mov     r9d, eax
0x18006ca6c  call    WPP_SF_d
0x18006ca71  jmp     loc_18006CB35
0x18006ca76  mov     rdx, [rsp+58h+arg_0]
0x18006ca7b  lea     r8, [rsp+58h+var_28]
0x18006ca80  xor     r9d, r9d
0x18006ca83  mov     [rsp+58h+var_38], 0
0x18006ca8b  mov     rcx, rbp
0x18006ca8e  call    cs:__imp_SslExpandWriteKey
0x18006ca94  mov     ebx, eax
0x18006ca96  test    eax, eax
0x18006ca98  jz      short loc_18006CABE
0x18006ca9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006caa1  lea     rdx, WPP_GLOBAL_Control
0x18006caa8  cmp     rcx, rdx
0x18006caab  jz      loc_18006CB35
0x18006cab1  test    byte ptr [rcx+1Ch], 1
0x18006cab5  jz      short loc_18006CB35
0x18006cab7  mov     edx, 90h
0x18006cabc  jmp     short loc_18006CA5E
0x18006cabe  mov     rcx, [rdi]
0x18006cac1  test    rcx, rcx
0x18006cac4  jz      short loc_18006CACE
0x18006cac6  xor     edx, edx
0x18006cac8  call    cs:__imp_SslFreeObject
0x18006cace  mov     rcx, [rsi]
0x18006cad1  test    rcx, rcx
0x18006cad4  jz      short loc_18006CADE
0x18006cad6  xor     edx, edx
0x18006cad8  call    cs:__imp_SslFreeObject
0x18006cade  mov     rax, [rsp+58h+arg_0]
0x18006cae3  mov     [rdi], rax
0x18006cae6  mov     rax, [rsp+58h+var_28]
0x18006caeb  mov     [rsi], rax
0x18006caee  mov     qword ptr [r14], 0
0x18006caf5  mov     [rsp+58h+arg_0], 0
0x18006cafe  mov     [rsp+58h+var_28], 0
0x18006cb07  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cb0e  lea     rdx, WPP_GLOBAL_Control
0x18006cb15  cmp     rcx, rdx
0x18006cb18  jz      short loc_18006CB59
0x18006cb1a  test    byte ptr [rcx+1Ch], 4
0x18006cb1e  jz      short loc_18006CB59
0x18006cb20  mov     rcx, [rcx+10h]
0x18006cb24  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x18006cb2b  mov     edx, 91h
0x18006cb30  call    WPP_SF_
0x18006cb35  mov     rcx, [rsp+58h+arg_0]
0x18006cb3a  test    rcx, rcx
0x18006cb3d  jz      short loc_18006CB47
0x18006cb3f  xor     edx, edx
0x18006cb41  call    cs:__imp_SslFreeObject
0x18006cb47  mov     rcx, [rsp+58h+var_28]
0x18006cb4c  test    rcx, rcx
0x18006cb4f  jz      short loc_18006CB59
0x18006cb51  xor     edx, edx
0x18006cb53  call    cs:__imp_SslFreeObject
0x18006cb59  mov     eax, ebx
0x18006cb5b  jmp     short loc_18006CB62
0x18006cb5d  mov     eax, 8009035Dh
0x18006cb62  mov     rbx, [rsp+58h+arg_8]
0x18006cb67  mov     rbp, [rsp+58h+arg_10]
0x18006cb6c  add     rsp, 40h
0x18006cb70  pop     r14
0x18006cb72  pop     rdi
0x18006cb73  pop     rsi
0x18006cb74  retn
```
