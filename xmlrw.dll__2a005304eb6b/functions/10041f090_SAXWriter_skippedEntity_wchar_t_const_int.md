# SAXWriter::skippedEntity(wchar_t const *,int)

- ea: `0x10041f090`
- end: `0x10041f18d`
- name: `?skippedEntity@SAXWriter@@UEAAJPEB_WH@Z`
- size: `253`
- prototype: `int(SAXWriter *__hidden this, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x10041f090`
- `0x10041f5e0`
- `0x10042d920`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::skippedEntity(SAXWriter *this, const wchar_t *a2, unsigned int a3)
{
  unsigned int v6; // edi

  v6 = 0;
  if ( *((_DWORD *)this + 3) == 1 )
  {
    *((_DWORD *)this + 3) = 1;
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 7) + 40LL))((char *)this - 56, 1);
    if ( v6 )
      return v6;
  }
  if ( a2 )
  {
    if ( a3 == 5 && !wcsncmp(L"[dtd]", a2, 5u) )
    {
      return 0;
    }
    else
    {
      if ( !a3 || *a2 != 37 )
        (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this - 7) + 88LL))((char *)this - 56, 38);
      (*(void (__fastcall **)(char *, const wchar_t *, _QWORD))(*((_QWORD *)this - 7) + 72LL))(
        (char *)this - 56,
        a2,
        a3);
      (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this - 7) + 88LL))((char *)this - 56, 59);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x10041f090  mov     [rsp+arg_0], rbx
0x10041f095  mov     [rsp+arg_8], rsi
0x10041f09a  mov     [rsp+arg_10], rdi
0x10041f09f  push    r14
0x10041f0a1  sub     rsp, 50h
0x10041f0a5  mov     r14d, r8d
0x10041f0a8  mov     rsi, rdx
0x10041f0ab  mov     rbx, rcx
0x10041f0ae  xor     edi, edi
0x10041f0b0  mov     [rsp+58h+var_38], edi
0x10041f0b4  cmp     dword ptr [rcx+0Ch], 1
0x10041f0b8  jnz     short loc_10041F0C3
0x10041f0ba  mov     dword ptr [rcx+0Ch], 1
0x10041f0c1  jmp     short loc_10041F0E7
0x10041f0c3  add     rcx, 0FFFFFFFFFFFFFFC8h
0x10041f0c7  mov     rax, [rcx]
0x10041f0ca  mov     edx, 1
0x10041f0cf  mov     rax, [rax+28h]
0x10041f0d3  call    cs:__guard_dispatch_icall_fptr
0x10041f0d9  mov     edi, eax
0x10041f0db  mov     [rsp+58h+var_38], eax
0x10041f0df  test    eax, eax
0x10041f0e1  jnz     loc_10041F175
0x10041f0e7  test    rsi, rsi
0x10041f0ea  jnz     short loc_10041F0F7
0x10041f0ec  mov     edi, 80070057h
0x10041f0f1  mov     [rsp+58h+var_38], edi
0x10041f0f5  jmp     short loc_10041F175
0x10041f0f7  cmp     r14d, 5
0x10041f0fb  jnz     short loc_10041F11B
0x10041f0fd  mov     r8d, r14d; MaxCount
0x10041f100  mov     rdx, rsi; String2
0x10041f103  lea     rcx, aDtd; "[dtd]"
0x10041f10a  call    wcsncmp
0x10041f10f  test    eax, eax
0x10041f111  jnz     short loc_10041F11B
0x10041f113  xor     edi, edi
0x10041f115  mov     [rsp+58h+var_38], edi
0x10041f119  jmp     short loc_10041F175
0x10041f11b  test    r14d, r14d
0x10041f11e  jz      short loc_10041F126
0x10041f120  cmp     word ptr [rsi], 25h ; '%'
0x10041f124  jz      short loc_10041F13C
0x10041f126  lea     rcx, [rbx-38h]
0x10041f12a  mov     rax, [rcx]
0x10041f12d  mov     edx, 26h ; '&'
0x10041f132  mov     rax, [rax+58h]
0x10041f136  call    cs:__guard_dispatch_icall_fptr
0x10041f13c  mov     rax, [rbx-38h]
0x10041f140  mov     r8d, r14d
0x10041f143  mov     rdx, rsi
0x10041f146  lea     rcx, [rbx-38h]
0x10041f14a  mov     rax, [rax+48h]
0x10041f14e  call    cs:__guard_dispatch_icall_fptr
0x10041f154  mov     rax, [rbx-38h]
0x10041f158  mov     edx, 3Bh ; ';'
0x10041f15d  lea     rcx, [rbx-38h]
0x10041f161  mov     rax, [rax+58h]
0x10041f165  call    cs:__guard_dispatch_icall_fptr
0x10041f16b  jmp     short loc_10041F175
0x10041f16d  mov     edi, [rsp+58h+var_34]
0x10041f171  mov     [rsp+58h+var_38], edi
0x10041f175  mov     eax, edi
0x10041f177  mov     rbx, [rsp+58h+arg_0]
0x10041f17c  mov     rsi, [rsp+58h+arg_8]
0x10041f181  mov     rdi, [rsp+58h+arg_10]
0x10041f186  add     rsp, 50h
0x10041f18a  pop     r14
0x10041f18c  retn
0x10043a5c0  push    rbp
0x10043a5c2  sub     rsp, 20h
0x10043a5c6  mov     rbp, rdx
0x10043a5c9  mov     [rbp+40h], rcx
0x10043a5cd  mov     [rbp+38h], rcx
0x10043a5d1  mov     rax, [rbp+38h]
0x10043a5d5  mov     rcx, [rax]
0x10043a5d8  mov     [rbp+30h], rcx
0x10043a5dc  mov     rax, [rbp+30h]
0x10043a5e0  mov     eax, [rax]
0x10043a5e2  cmp     eax, 0C0000005h
0x10043a5e7  jz      short loc_10043A619
0x10043a5e9  add     eax, 1FFFFFFFh
0x10043a5ee  cmp     eax, 1
0x10043a5f1  ja      short loc_10043A609
0x10043a5f3  mov     rax, [rbp+30h]
0x10043a5f7  cmp     dword ptr [rax+18h], 1
0x10043a5fb  jnz     short loc_10043A609
0x10043a5fd  mov     rax, [rbp+30h]
0x10043a601  mov     ecx, [rax+20h]
0x10043a604  mov     [rbp+24h], ecx
0x10043a607  jmp     short loc_10043A610
0x10043a609  mov     dword ptr [rbp+24h], 8000FFFFh
0x10043a610  mov     dword ptr [rbp+28h], 1
0x10043a617  jmp     short loc_10043A620
0x10043a619  mov     dword ptr [rbp+28h], 0
0x10043a620  mov     eax, [rbp+28h]
0x10043a623  add     rsp, 20h
0x10043a627  pop     rbp
0x10043a628  retn
```
