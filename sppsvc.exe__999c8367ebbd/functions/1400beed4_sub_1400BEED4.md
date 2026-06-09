# sub_1400BEED4

- ea: `0x1400beed4`
- end: `0x1400befcf`
- name: `sub_1400BEED4`
- size: `251`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400b7620`

## callees

- `0x14006adb4`
- `0x14006d2f8`
- `0x14006de60`
- `0x14007b174`
- `0x14007cfb4`
- `0x1400beed4`
- `0x1400db10c`
- `0x140390f60`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1400bef1e`
- `RPCRT4!UuidCreate` at `0x1400bef1e`

## pseudocode

```c
__int64 __fastcall sub_1400BEED4(__int64 a1, _QWORD *a2)
{
  int v4; // edi
  unsigned int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  void *v8; // rsi
  int v9; // ecx
  unsigned int v11; // [rsp+20h] [rbp-30h] BYREF
  int v12; // [rsp+24h] [rbp-2Ch] BYREF
  void *v13; // [rsp+28h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-20h] BYREF

  v13 = 0;
  Uuid = 0;
  v12 = 0;
  v11 = 0;
  v4 = 0;
  while ( 1 )
  {
    v5 = UuidCreate(&Uuid);
    if ( !(unsigned int)sub_14006D2F8(v5, &v11) )
      break;
    v6 = sub_14007B174(&Uuid, &v13);
    v7 = v6;
    if ( v6 < 0 || (v8 = v13, v6 = sub_1400DB10C(a1, 0, v13, &v12), v11 = v6, v7 = v6, v6 < 0) )
    {
      v9 = v6;
      goto LABEL_12;
    }
    if ( !v12 )
    {
      v13 = 0;
      *a2 = v8;
      goto LABEL_13;
    }
    sub_14006ADB4(&v13);
    if ( (unsigned int)++v4 >= 0x64 )
    {
      v7 = -2147467259;
      goto LABEL_11;
    }
  }
  v7 = v11;
LABEL_11:
  v9 = v7;
LABEL_12:
  sub_14006DE60(v9);
LABEL_13:
  sub_14007CFB4(v7);
  sub_14006ADB4(&v13);
  return v7;
}

```

## disassembly

```asm
0x1400beed4  mov     [rsp-28h+arg_10], rbx
0x1400beed9  push    rbp
0x1400beeda  push    rsi
0x1400beedb  push    rdi
0x1400beedc  push    r14
0x1400beede  push    r15
0x1400beee0  mov     rbp, rsp
0x1400beee3  sub     rsp, 50h
0x1400beee7  mov     rax, cs:__security_cookie
0x1400beeee  xor     rax, rsp
0x1400beef1  mov     [rbp+var_10], rax
0x1400beef5  xorps   xmm0, xmm0
0x1400beef8  mov     [rbp+var_28], 0
0x1400bef00  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1400bef04  mov     r14, rdx
0x1400bef07  mov     [rbp+var_2C], 0
0x1400bef0e  mov     r15, rcx
0x1400bef11  mov     [rbp+var_30], 0
0x1400bef18  xor     edi, edi
0x1400bef1a  lea     rcx, [rbp+Uuid]; Uuid
0x1400bef1e  call    cs:UuidCreate
0x1400bef24  mov     ecx, eax
0x1400bef26  lea     rdx, [rbp+var_30]
0x1400bef2a  call    sub_14006D2F8
0x1400bef2f  test    eax, eax
0x1400bef31  jz      short loc_1400BEF92
0x1400bef33  lea     rdx, [rbp+var_28]
0x1400bef37  lea     rcx, [rbp+Uuid]
0x1400bef3b  call    sub_14007B174
0x1400bef40  mov     ebx, eax
0x1400bef42  test    eax, eax
0x1400bef44  js      short loc_1400BEF8E
0x1400bef46  mov     rsi, [rbp+var_28]
0x1400bef4a  lea     r9, [rbp+var_2C]
0x1400bef4e  mov     r8, rsi
0x1400bef51  xor     edx, edx
0x1400bef53  mov     rcx, r15
0x1400bef56  call    sub_1400DB10C
0x1400bef5b  mov     [rbp+var_30], eax
0x1400bef5e  mov     ebx, eax
0x1400bef60  test    eax, eax
0x1400bef62  js      short loc_1400BEF8E
0x1400bef64  cmp     [rbp+var_2C], 0
0x1400bef68  jz      short loc_1400BEF81
0x1400bef6a  lea     rcx, [rbp+var_28]
0x1400bef6e  call    sub_14006ADB4
0x1400bef73  inc     edi
0x1400bef75  cmp     edi, 64h ; 'd'
0x1400bef78  jb      short loc_1400BEF1A
0x1400bef7a  mov     ebx, 80004005h
0x1400bef7f  jmp     short loc_1400BEF95
0x1400bef81  mov     [rbp+var_28], 0
0x1400bef89  mov     [r14], rsi
0x1400bef8c  jmp     short loc_1400BEF9C
0x1400bef8e  mov     ecx, eax
0x1400bef90  jmp     short loc_1400BEF97
0x1400bef92  mov     ebx, [rbp+var_30]
0x1400bef95  mov     ecx, ebx
0x1400bef97  call    sub_14006DE60
0x1400bef9c  mov     ecx, ebx
0x1400bef9e  call    sub_14007CFB4
0x1400befa3  lea     rcx, [rbp+var_28]
0x1400befa7  call    sub_14006ADB4
0x1400befac  mov     eax, ebx
0x1400befae  mov     rcx, [rbp+var_10]
0x1400befb2  xor     rcx, rsp; StackCookie
0x1400befb5  call    __security_check_cookie
0x1400befba  mov     rbx, [rsp+50h+arg_10]
0x1400befc2  add     rsp, 50h
0x1400befc6  pop     r15
0x1400befc8  pop     r14
0x1400befca  pop     rdi
0x1400befcb  pop     rsi
0x1400befcc  pop     rbp
0x1400befcd  retn
```
