# SLGenerateTokenActivationChallenge

- ea: `0x18003dae0`
- end: `0x18003dc2d`
- name: `SLGenerateTokenActivationChallenge`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180004ca0`
- `0x180006c10`
- `0x18003dae0`
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

- `sppc!SLpGenerateTokenActivationChallenge` at `0x18003dbe2`
- `sppc!SLpGenerateTokenActivationChallenge` at `0x18003dbe2`

## pseudocode

```c
__int64 __fastcall SLGenerateTokenActivationChallenge(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int TokenActivationChallenge; // edi

  sub_180043088(byte_180084458, byte_18008D0C8);
  if ( !a1 )
  {
    sub_180042514(qword_180085450, qword_18008D030);
    TokenActivationChallenge = -2147024809;
    sub_18004362C(byte_180080A48, &dword_18008D4F4);
LABEL_3:
    sub_180004CA0(2147942487LL);
    goto LABEL_12;
  }
  sub_180043900(qword_1800846B8, &dword_18008D2FC);
  if ( !a2 )
  {
    sub_180043BD8(byte_180081760, byte_18008DF58);
    TokenActivationChallenge = -2147024809;
    goto LABEL_3;
  }
  sub_180042ACC(&dword_180081124, qword_18008DA40);
  if ( !a3 )
  {
    TokenActivationChallenge = -2147024809;
    sub_180043EAC(byte_180081CA0, byte_18008DE00);
    goto LABEL_3;
  }
  if ( a4 )
  {
    TokenActivationChallenge = SLpGenerateTokenActivationChallenge(a1, a2, a3, a4);
    sub_180043364(byte_180080DC8, byte_18008D818);
    if ( (TokenActivationChallenge & 0x80000000) != 0 )
    {
      sub_180004CA0(TokenActivationChallenge);
      sub_1800427F4(byte_180085970, qword_18008D0F0);
    }
  }
  else
  {
    TokenActivationChallenge = -2147024809;
    sub_180004CA0(2147942487LL);
    sub_180042DB0(&dword_18008219C, qword_18008CD80);
  }
LABEL_12:
  sub_180006C10(TokenActivationChallenge);
  return TokenActivationChallenge;
}

```

## disassembly

```asm
0x18003dae0  push    rbx
0x18003dae2  push    rbp
0x18003dae3  push    rsi
0x18003dae4  push    rdi
0x18003dae5  sub     rsp, 28h
0x18003dae9  mov     rsi, rdx
0x18003daec  mov     rbp, rcx
0x18003daef  lea     rdx, byte_18008D0C8
0x18003daf6  mov     rbx, r9
0x18003daf9  lea     rcx, byte_180084458
0x18003db00  mov     rdi, r8
0x18003db03  call    sub_180043088
0x18003db08  test    rbp, rbp
0x18003db0b  jnz     short loc_18003DB46
0x18003db0d  lea     rdx, qword_18008D030
0x18003db14  lea     rcx, qword_180085450
0x18003db1b  call    sub_180042514
0x18003db20  mov     ebx, 80070057h
0x18003db25  lea     rdx, dword_18008D4F4
0x18003db2c  lea     rcx, byte_180080A48
0x18003db33  mov     edi, ebx
0x18003db35  call    sub_18004362C
0x18003db3a  mov     ecx, ebx
0x18003db3c  call    sub_180004CA0
0x18003db41  jmp     loc_18003DC1B
0x18003db46  lea     rdx, dword_18008D2FC
0x18003db4d  lea     rcx, qword_1800846B8
0x18003db54  call    sub_180043900
0x18003db59  test    rsi, rsi
0x18003db5c  jnz     short loc_18003DB7A
0x18003db5e  lea     rdx, byte_18008DF58
0x18003db65  lea     rcx, byte_180081760
0x18003db6c  call    sub_180043BD8
0x18003db71  mov     ebx, 80070057h
0x18003db76  mov     edi, ebx
0x18003db78  jmp     short loc_18003DB3A
0x18003db7a  lea     rdx, qword_18008DA40
0x18003db81  lea     rcx, dword_180081124
0x18003db88  call    sub_180042ACC
0x18003db8d  test    rdi, rdi
0x18003db90  jnz     short loc_18003DBAE
0x18003db92  mov     ebx, 80070057h
0x18003db97  lea     rdx, byte_18008DE00
0x18003db9e  lea     rcx, byte_180081CA0
0x18003dba5  mov     edi, ebx
0x18003dba7  call    sub_180043EAC
0x18003dbac  jmp     short loc_18003DB3A
0x18003dbae  test    rbx, rbx
0x18003dbb1  jnz     short loc_18003DBD6
0x18003dbb3  mov     ebx, 80070057h
0x18003dbb8  mov     ecx, ebx
0x18003dbba  mov     edi, ebx
0x18003dbbc  call    sub_180004CA0
0x18003dbc1  lea     rdx, qword_18008CD80
0x18003dbc8  lea     rcx, dword_18008219C
0x18003dbcf  call    sub_180042DB0
0x18003dbd4  jmp     short loc_18003DC1B
0x18003dbd6  mov     r9, rbx
0x18003dbd9  mov     r8, rdi
0x18003dbdc  mov     rdx, rsi
0x18003dbdf  mov     rcx, rbp
0x18003dbe2  call    cs:SLpGenerateTokenActivationChallenge
0x18003dbe8  lea     rdx, byte_18008D818
0x18003dbef  mov     edi, eax
0x18003dbf1  lea     rcx, byte_180080DC8
0x18003dbf8  call    sub_180043364
0x18003dbfd  test    edi, edi
0x18003dbff  jns     short loc_18003DC1B
0x18003dc01  mov     ecx, edi
0x18003dc03  call    sub_180004CA0
0x18003dc08  lea     rdx, qword_18008D0F0
0x18003dc0f  lea     rcx, byte_180085970
0x18003dc16  call    sub_1800427F4
0x18003dc1b  mov     ecx, edi
0x18003dc1d  call    sub_180006C10
0x18003dc22  mov     eax, edi
0x18003dc24  add     rsp, 28h
0x18003dc28  pop     rdi
0x18003dc29  pop     rsi
0x18003dc2a  pop     rbp
0x18003dc2b  pop     rbx
0x18003dc2c  retn
```
