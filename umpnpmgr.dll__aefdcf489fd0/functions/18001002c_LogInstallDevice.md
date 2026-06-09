# LogInstallDevice

- ea: `0x18001002c`
- end: `0x180010141`
- name: `LogInstallDevice`
- size: `277`
- prototype: `__int64 __fastcall(int, int, __int64 *, __int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800027a0`
- `0x1800056d0`

## callees

- `0x180001034`
- `0x18000e7c0`
- `0x18001002c`
- `0x180018970`

## pseudocode

```c
__int64 __fastcall LogInstallDevice(int a1, int a2, __int64 *a3, __int64 a4, __int64 a5, __int64 a6, int a7)
{
  __int64 result; // rax
  __int64 *v8; // r10
  __int64 *v9; // r11
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // [rsp+20h] [rbp-91h]
  int v13; // [rsp+30h] [rbp-81h] BYREF
  int v14; // [rsp+34h] [rbp-7Dh] BYREF
  int v15; // [rsp+38h] [rbp-79h] BYREF
  __int64 v16; // [rsp+40h] [rbp-71h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-61h] BYREF
  int *v18; // [rsp+70h] [rbp-41h]
  __int64 v19; // [rsp+78h] [rbp-39h]
  int *v20; // [rsp+80h] [rbp-31h]
  __int64 v21; // [rsp+88h] [rbp-29h]
  _BYTE v22[16]; // [rsp+90h] [rbp-21h] BYREF
  _BYTE v23[16]; // [rsp+A0h] [rbp-11h] BYREF
  _BYTE v24[16]; // [rsp+B0h] [rbp-1h] BYREF
  __int64 *v25; // [rsp+C0h] [rbp+Fh]
  __int64 v26; // [rsp+C8h] [rbp+17h]
  int *v27; // [rsp+D0h] [rbp+1Fh]
  __int64 v28; // [rsp+D8h] [rbp+27h]

  result = (unsigned int)dword_180023058;
  if ( (unsigned int)dword_180023058 > 5 )
  {
    result = qword_180023068;
    if ( (qword_180023068 & 0x800000000000LL) != 0 )
    {
      result = qword_180023070 & 0x800000000000LL;
      if ( (qword_180023070 & 0x800000000000LL) == qword_180023070 )
      {
        v14 = a2;
        v18 = &v13;
        v13 = a1;
        v20 = &v14;
        v19 = 4;
        v21 = 4;
        tlgCreate1Sz_wchar_t((__int64)v22, a3);
        tlgCreate1Sz_wchar_t((__int64)v23, v8);
        tlgCreate1Sz_wchar_t((__int64)v24, v9);
        v25 = &v16;
        v15 = a7;
        v27 = &v15;
        v16 = a6;
        v26 = 8;
        v28 = 4;
        return tlgWriteTransfer_EtwEventWriteTransfer(
                 a6,
                 (unsigned __int8 *)byte_18001E7B1,
                 v10,
                 v11,
                 v12,
                 (__int64)v17);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001002c  mov     [rsp-8+arg_0], rbx
0x180010031  push    rbp
0x180010032  lea     rbp, [rsp-3Fh]
0x180010037  sub     rsp, 0F0h
0x18001003e  mov     rax, cs:__security_cookie
0x180010045  xor     rax, rsp
0x180010048  mov     [rbp+3Fh+var_10], rax
0x18001004c  mov     eax, cs:dword_180023058
0x180010052  mov     r10, r9
0x180010055  mov     r11, [rbp+3Fh+arg_20]
0x180010059  mov     r9, r8
0x18001005c  cmp     eax, 5
0x18001005f  jbe     loc_180010124
0x180010065  mov     r8, cs:qword_180023070
0x18001006c  mov     rbx, 800000000000h
0x180010076  mov     rax, cs:qword_180023068
0x18001007d  test    rbx, rax
0x180010080  jz      loc_180010124
0x180010086  mov     rax, r8
0x180010089  and     rax, rbx
0x18001008c  cmp     rax, r8
0x18001008f  jnz     loc_180010124
0x180010095  lea     rax, [rsp+0F0h+var_C0]
0x18001009a  mov     [rbp+3Fh+var_BC], edx
0x18001009d  mov     [rbp+3Fh+var_80], rax
0x1800100a1  mov     rdx, r9
0x1800100a4  lea     rax, [rbp+3Fh+var_BC]
0x1800100a8  mov     [rsp+0F0h+var_C0], ecx
0x1800100ac  lea     rcx, [rbp+3Fh+var_60]
0x1800100b0  mov     [rbp+3Fh+var_70], rax
0x1800100b4  mov     [rbp+3Fh+var_78], 4
0x1800100bc  mov     [rbp+3Fh+var_68], 4
0x1800100c4  call    _tlgCreate1Sz_wchar_t
0x1800100c9  mov     rdx, r10
0x1800100cc  lea     rcx, [rbp+3Fh+var_50]
0x1800100d0  call    _tlgCreate1Sz_wchar_t
0x1800100d5  mov     rdx, r11
0x1800100d8  lea     rcx, [rbp+3Fh+var_40]
0x1800100dc  call    _tlgCreate1Sz_wchar_t
0x1800100e1  mov     rcx, [rbp+3Fh+arg_28]
0x1800100e5  lea     rax, [rbp+3Fh+var_B0]
0x1800100e9  mov     [rbp+3Fh+var_30], rax
0x1800100ed  lea     rdx, byte_18001E7B1
0x1800100f4  mov     eax, [rbp+3Fh+arg_30]
0x1800100f7  mov     [rbp+3Fh+var_B8], eax
0x1800100fa  lea     rax, [rbp+3Fh+var_B8]
0x1800100fe  mov     [rbp+3Fh+var_20], rax
0x180010102  lea     rax, [rbp+3Fh+var_A0]
0x180010106  mov     [rsp+0F0h+var_C8], rax
0x18001010b  mov     [rbp+3Fh+var_B0], rcx
0x18001010f  mov     [rbp+3Fh+var_28], 8
0x180010117  mov     [rbp+3Fh+var_18], 4
0x18001011f  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180010124  mov     rcx, [rbp+3Fh+var_10]
0x180010128  xor     rcx, rsp; StackCookie
0x18001012b  call    __security_check_cookie
0x180010130  mov     rbx, [rsp+0F0h+arg_0]
0x180010138  add     rsp, 0F0h
0x18001013f  pop     rbp
0x180010140  retn
```
