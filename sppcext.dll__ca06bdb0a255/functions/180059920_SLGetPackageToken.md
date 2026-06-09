# SLGetPackageToken

- ea: `0x180059920`
- end: `0x180059a6d`
- name: `SLGetPackageToken`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180004ca0`
- `0x180006c10`
- `0x180007638`
- `0x180056630`
- `0x1800567d0`
- `0x1800567fc`
- `0x180056c38`
- `0x1800575ec`
- `0x18005762c`
- `0x180057a6c`
- `0x180057e24`
- `0x180059920`
- `0x18006ef80`

## pseudocode

```c
__int64 __fastcall SLGetPackageToken(unsigned int a1, const void *a2, unsigned int a3, _QWORD *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  _BYTE v12[4]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v13; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[352]; // [rsp+40h] [rbp-C0h] BYREF

  v12[0] = 0;
  sub_180056630(v16);
  v14 = 0;
  v13 = 0;
  v15 = 0;
  if ( !a4 || !a2 || !a1 )
    goto LABEL_12;
  v8 = sub_180057A6C(v12);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_5;
  v8 = sub_180057E24((__int64)v16, a2, a1);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_5;
  v8 = sub_18005762C(v16, &v13);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_5;
  if ( v13 <= a3 )
  {
LABEL_12:
    v10 = 2147942487LL;
    v9 = -2147024809;
    goto LABEL_13;
  }
  v8 = sub_1800575EC(v16, a3, &v15);
  v9 = v8;
  if ( v8 < 0 || (v8 = sub_180056C38(v15, &v14), v9 = v8, v8 < 0) )
  {
LABEL_5:
    v10 = (unsigned int)v8;
LABEL_13:
    sub_180004CA0(v10);
    goto LABEL_14;
  }
  *a4 = v14;
  v14 = 0;
LABEL_14:
  sub_180006C10(v9);
  sub_180007638(&v14);
  sub_1800567FC(v16);
  sub_1800567D0(v12);
  return v9;
}

```

## disassembly

```asm
0x180059920  push    rbp
0x180059922  push    rbx
0x180059923  push    rsi
0x180059924  push    rdi
0x180059925  push    r14
0x180059927  push    r15
0x180059929  lea     rbp, [rsp-0B8h]
0x180059931  sub     rsp, 1B8h
0x180059938  mov     rax, cs:__security_cookie
0x18005993f  xor     rax, rsp
0x180059942  mov     [rbp+0E0h+var_40], rax
0x180059949  mov     esi, ecx
0x18005994b  mov     [rsp+1E0h+var_1C0], 0
0x180059950  lea     rcx, [rsp+1E0h+var_1A0]
0x180059955  mov     r15, r9
0x180059958  mov     edi, r8d
0x18005995b  mov     r14, rdx
0x18005995e  call    sub_180056630
0x180059963  mov     [rsp+1E0h+var_1B8], 0
0x18005996c  mov     [rsp+1E0h+var_1BC], 0
0x180059974  mov     [rsp+1E0h+var_1B0], 0
0x18005997d  test    r15, r15
0x180059980  jz      loc_180059A1B
0x180059986  test    r14, r14
0x180059989  jz      loc_180059A1B
0x18005998f  test    esi, esi
0x180059991  jz      loc_180059A1B
0x180059997  lea     rcx, [rsp+1E0h+var_1C0]
0x18005999c  call    sub_180057A6C
0x1800599a1  mov     ebx, eax
0x1800599a3  test    eax, eax
0x1800599a5  jns     short loc_1800599AB
0x1800599a7  mov     ecx, eax
0x1800599a9  jmp     short loc_180059A22
0x1800599ab  mov     r8d, esi
0x1800599ae  lea     rcx, [rsp+1E0h+var_1A0]
0x1800599b3  mov     rdx, r14
0x1800599b6  call    sub_180057E24
0x1800599bb  mov     ebx, eax
0x1800599bd  test    eax, eax
0x1800599bf  js      short loc_1800599A7
0x1800599c1  lea     rdx, [rsp+1E0h+var_1BC]
0x1800599c6  lea     rcx, [rsp+1E0h+var_1A0]
0x1800599cb  call    sub_18005762C
0x1800599d0  mov     ebx, eax
0x1800599d2  test    eax, eax
0x1800599d4  js      short loc_1800599A7
0x1800599d6  cmp     [rsp+1E0h+var_1BC], edi
0x1800599da  jbe     short loc_180059A1B
0x1800599dc  lea     r8, [rsp+1E0h+var_1B0]
0x1800599e1  mov     edx, edi
0x1800599e3  lea     rcx, [rsp+1E0h+var_1A0]
0x1800599e8  call    sub_1800575EC
0x1800599ed  mov     ebx, eax
0x1800599ef  test    eax, eax
0x1800599f1  js      short loc_1800599A7
0x1800599f3  mov     rcx, [rsp+1E0h+var_1B0]
0x1800599f8  lea     rdx, [rsp+1E0h+var_1B8]
0x1800599fd  call    sub_180056C38
0x180059a02  mov     ebx, eax
0x180059a04  test    eax, eax
0x180059a06  js      short loc_1800599A7
0x180059a08  mov     rax, [rsp+1E0h+var_1B8]
0x180059a0d  mov     [r15], rax
0x180059a10  mov     [rsp+1E0h+var_1B8], 0
0x180059a19  jmp     short loc_180059A27
0x180059a1b  mov     ecx, 80070057h
0x180059a20  mov     ebx, ecx
0x180059a22  call    sub_180004CA0
0x180059a27  mov     ecx, ebx
0x180059a29  call    sub_180006C10
0x180059a2e  lea     rcx, [rsp+1E0h+var_1B8]
0x180059a33  call    sub_180007638
0x180059a38  lea     rcx, [rsp+1E0h+var_1A0]
0x180059a3d  call    sub_1800567FC
0x180059a42  lea     rcx, [rsp+1E0h+var_1C0]
0x180059a47  call    sub_1800567D0
0x180059a4c  mov     eax, ebx
0x180059a4e  mov     rcx, [rbp+0E0h+var_40]
0x180059a55  xor     rcx, rsp; StackCookie
0x180059a58  call    __security_check_cookie
0x180059a5d  add     rsp, 1B8h
0x180059a64  pop     r15
0x180059a66  pop     r14
0x180059a68  pop     rdi
0x180059a69  pop     rsi
0x180059a6a  pop     rbx
0x180059a6b  pop     rbp
0x180059a6c  retn
```
