# uus::UndockedStubTelemetry::UusLogStubExe2Dll<ushort const *,ushort const *,int const &>(ushort const * &&,ushort const * &&,int const &)

- ea: `0x140006eb8`
- end: `0x140006ff7`
- name: `??$UusLogStubExe2Dll@PEBGPEBGAEBH@UndockedStubTelemetry@uus@@SAX$$QEAPEBG0AEBH@Z`
- size: `319`
- prototype: `__int64 __fastcall(int **, int **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000a6a8`

## callees

- `0x14000163c`
- `0x140002130`
- `0x140006eb8`
- `0x1400098ec`

## pseudocode

```c
__int64 __fastcall uus::UndockedStubTelemetry::UusLogStubExe2Dll<unsigned short const *,unsigned short const *,int const &>(
        int **a1,
        int **a2,
        int *a3)
{
  __int64 result; // rax
  __int64 v7; // r11
  __int64 v8; // r10
  __int64 v9; // r9
  int *v10; // r8
  int *v11; // rcx
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // edx
  int v16; // [rsp+30h] [rbp-49h] BYREF
  __int64 v17; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-39h] BYREF
  int *v19; // [rsp+60h] [rbp-19h]
  int v20; // [rsp+68h] [rbp-11h]
  int v21; // [rsp+6Ch] [rbp-Dh]
  int *v22; // [rsp+70h] [rbp-9h]
  int v23; // [rsp+78h] [rbp-1h]
  int v24; // [rsp+7Ch] [rbp+3h]
  int *v25; // [rsp+80h] [rbp+7h]
  __int64 v26; // [rsp+88h] [rbp+Fh]
  __int64 *v27; // [rsp+90h] [rbp+17h]
  __int64 v28; // [rsp+98h] [rbp+1Fh]

  result = (__int64)uus::UndockedStubTelemetry::Provider();
  v7 = result;
  if ( *(_DWORD *)result > 5u )
  {
    v8 = *(_QWORD *)(result + 24);
    v9 = *(_QWORD *)(result + 16);
    result = 0x200000000000LL;
    if ( (v9 & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
    {
      v10 = *a2;
      v11 = *a1;
      v16 = *a3;
      v27 = &v17;
      v12 = 2;
      v17 = 0x1000000;
      v25 = &v16;
      v13 = -1;
      v28 = 8;
      v26 = 4;
      if ( v10 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)v10 + v14) );
        v15 = 2 * v14 + 2;
      }
      else
      {
        v10 = &dword_14000DE7C;
        v15 = 2;
      }
      v22 = v10;
      v23 = v15;
      v24 = 0;
      if ( v11 )
      {
        do
          ++v13;
        while ( *((_WORD *)v11 + v13) );
        v12 = 2 * v13 + 2;
      }
      else
      {
        v11 = &dword_14000DE7C;
      }
      v19 = v11;
      v20 = v12;
      v21 = 0;
      return tlgWriteTransfer_EventWriteTransfer(v7, byte_14000E359, 0, 0, 6, v18, v16, v17);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006eb8  push    rbp
0x140006eba  push    rbx
0x140006ebb  push    rsi
0x140006ebc  push    rdi
0x140006ebd  lea     rbp, [rsp-3Fh]
0x140006ec2  sub     rsp, 0B8h
0x140006ec9  mov     rax, cs:__security_cookie
0x140006ed0  xor     rax, rsp
0x140006ed3  mov     [rbp+57h+var_30], rax
0x140006ed7  mov     rbx, r8
0x140006eda  mov     rdi, rdx
0x140006edd  mov     rsi, rcx
0x140006ee0  call    ?Provider@UndockedStubTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedStubTelemetry::Provider(void)
0x140006ee5  mov     r11, rax
0x140006ee8  mov     r9d, [rax]
0x140006eeb  cmp     r9d, 5
0x140006eef  jbe     loc_140006FDF
0x140006ef5  mov     r10, [rax+18h]
0x140006ef9  mov     r9, [rax+10h]
0x140006efd  mov     rax, 200000000000h
0x140006f07  test    rax, r9
0x140006f0a  jz      loc_140006FDF
0x140006f10  mov     rcx, r10
0x140006f13  and     rcx, rax
0x140006f16  cmp     rcx, r10
0x140006f19  jnz     loc_140006FDF
0x140006f1f  mov     eax, [rbx]
0x140006f21  xor     r10d, r10d
0x140006f24  mov     r8, [rdi]
0x140006f27  mov     rcx, [rsi]
0x140006f2a  mov     [rbp+57h+var_A0], eax
0x140006f2d  lea     rax, [rbp+57h+var_98]
0x140006f31  mov     [rbp+57h+var_40], rax
0x140006f35  lea     r9d, [r10+2]
0x140006f39  lea     rax, [rbp+57h+var_A0]
0x140006f3d  mov     [rbp+57h+var_98], 1000000h
0x140006f45  mov     [rbp+57h+var_50], rax
0x140006f49  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006f4d  mov     [rbp+57h+var_38], 8
0x140006f55  mov     [rbp+57h+var_48], 4
0x140006f5d  test    r8, r8
0x140006f60  jz      short loc_140006F78
0x140006f62  mov     rdx, rax
0x140006f65  inc     rdx
0x140006f68  cmp     [r8+rdx*2], r10w
0x140006f6d  jnz     short loc_140006F65
0x140006f6f  lea     edx, ds:2[rdx*2]
0x140006f76  jmp     short loc_140006F82
0x140006f78  lea     r8, dword_14000DE7C
0x140006f7f  mov     edx, r9d
0x140006f82  mov     [rbp+57h+var_60], r8
0x140006f86  mov     [rbp+57h+var_58], edx
0x140006f89  mov     [rbp+57h+var_54], r10d
0x140006f8d  test    rcx, rcx
0x140006f90  jz      short loc_140006FA6
0x140006f92  inc     rax
0x140006f95  cmp     [rcx+rax*2], r10w
0x140006f9a  jnz     short loc_140006F92
0x140006f9c  lea     r9d, ds:2[rax*2]
0x140006fa4  jmp     short loc_140006FAD
0x140006fa6  lea     rcx, dword_14000DE7C
0x140006fad  lea     rax, [rbp+57h+var_90]
0x140006fb1  mov     [rbp+57h+var_70], rcx
0x140006fb5  mov     [rbp+57h+var_68], r9d
0x140006fb9  lea     rdx, byte_14000E359
0x140006fc0  mov     [rsp+0D0h+var_A8], rax
0x140006fc5  xor     r9d, r9d
0x140006fc8  xor     r8d, r8d
0x140006fcb  mov     [rsp+0D0h+var_B0], 6
0x140006fd3  mov     rcx, r11
0x140006fd6  mov     [rbp+57h+var_64], r10d
0x140006fda  call    _tlgWriteTransfer_EventWriteTransfer
0x140006fdf  mov     rcx, [rbp+57h+var_30]
0x140006fe3  xor     rcx, rsp; StackCookie
0x140006fe6  call    __security_check_cookie
0x140006feb  add     rsp, 0B8h
0x140006ff2  pop     rdi
0x140006ff3  pop     rsi
0x140006ff4  pop     rbx
0x140006ff5  pop     rbp
0x140006ff6  retn
```
