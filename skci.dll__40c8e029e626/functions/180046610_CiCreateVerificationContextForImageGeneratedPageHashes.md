# CiCreateVerificationContextForImageGeneratedPageHashes

- ea: `0x180046610`
- end: `0x1800466ae`
- name: `CiCreateVerificationContextForImageGeneratedPageHashes`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011ef0`

## callees

- `0x180046350`
- `0x18004640c`
- `0x180046610`
- `0x18004f970`

## pseudocode

```c
__int64 __fastcall CiCreateVerificationContextForImageGeneratedPageHashes(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        __int64 a7,
        _QWORD *a8,
        ULONG *a9)
{
  __int64 v9; // rbx
  int v13; // edx
  __int64 result; // rax

  v9 = a2;
  v13 = a2 & 0xFFF;
  if ( v13 && !(unsigned __int8)CipIsZeroFilled(a3 + v9, (unsigned int)(4096 - v13)) )
    return 3221225990LL;
  result = CiCreateImageHashContext(a1, v9, a3, a6, a7);
  if ( (int)result >= 0 )
    return CiCreatePageHashContextForImageMapping(a1, v9, a3, a4, a5, a8, a9);
  return result;
}

```

## disassembly

```asm
0x180046610  push    rbx
0x180046612  push    rbp
0x180046613  push    rsi
0x180046614  push    rdi
0x180046615  sub     rsp, 48h
0x180046619  mov     ebx, edx
0x18004661b  mov     ebp, r9d
0x18004661e  mov     rdi, r8
0x180046621  mov     rsi, rcx
0x180046624  and     edx, 0FFFh
0x18004662a  jz      short loc_180046649
0x18004662c  mov     eax, 1000h
0x180046631  lea     rcx, [r8+rbx]
0x180046635  sub     eax, edx
0x180046637  mov     edx, eax
0x180046639  call    CipIsZeroFilled
0x18004663e  test    al, al
0x180046640  jnz     short loc_180046649
0x180046642  mov     eax, 0C0000206h
0x180046647  jmp     short loc_1800466A4
0x180046649  mov     rax, [rsp+68h+arg_30]
0x180046651  mov     r8, rdi
0x180046654  mov     r9d, [rsp+68h+arg_28]
0x18004665c  mov     edx, ebx
0x18004665e  mov     rcx, rsi
0x180046661  mov     [rsp+68h+var_48], rax
0x180046666  call    CiCreateImageHashContext
0x18004666b  test    eax, eax
0x18004666d  js      short loc_1800466A4
0x18004666f  mov     rax, [rsp+68h+arg_40]
0x180046677  mov     r9d, ebp
0x18004667a  mov     [rsp+68h+var_38], rax
0x18004667f  mov     r8, rdi
0x180046682  mov     rax, [rsp+68h+arg_38]
0x18004668a  mov     edx, ebx
0x18004668c  mov     [rsp+68h+var_40], rax
0x180046691  mov     rcx, rsi
0x180046694  mov     eax, [rsp+68h+arg_20]
0x18004669b  mov     dword ptr [rsp+68h+var_48], eax
0x18004669f  call    CiCreatePageHashContextForImageMapping
0x1800466a4  add     rsp, 48h
0x1800466a8  pop     rdi
0x1800466a9  pop     rsi
0x1800466aa  pop     rbp
0x1800466ab  pop     rbx
0x1800466ac  retn
```
