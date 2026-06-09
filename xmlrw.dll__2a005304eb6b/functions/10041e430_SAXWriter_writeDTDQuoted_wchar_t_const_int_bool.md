# SAXWriter::writeDTDQuoted(wchar_t const *,int,bool)

- ea: `0x10041e430`
- end: `0x10041e5e9`
- name: `?writeDTDQuoted@SAXWriter@@IEAAJPEB_WH_N@Z`
- size: `441`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this, const wchar_t *, int, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x10041f320`
- `0x10041f5e0`

## callees

- `0x10041e430`
- `0x100423e80`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::writeDTDQuoted(SAXWriter *this, const wchar_t *a2, int a3, char a4)
{
  unsigned int v8; // r14d
  unsigned int v10; // edx

  v8 = 0;
  (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 34);
  if ( !*((_BYTE *)this + 225) )
  {
    if ( !a2 )
      goto LABEL_22;
    if ( a3 < 0 )
      return (unsigned int)-2147024809;
    (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 248LL))(this);
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !a3-- )
        {
          (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 256LL))(this);
          goto LABEL_22;
        }
        v10 = *a2++;
        if ( v10 <= 0x3E )
          break;
LABEL_20:
        (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)this + 88LL))(this);
      }
      switch ( v10 )
      {
        case '"':
          (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"&#34;");
          break;
        case '%':
          if ( a4 )
            goto LABEL_20;
          (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"&#37;");
          break;
        case '&':
          (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"&#38;");
          break;
        default:
          if ( v10 != 60 || !a4 )
            goto LABEL_20;
          (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)this + 80LL))(this, L"&#60;");
          break;
      }
    }
  }
  if ( a2 )
    (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)this + 72LL))(this, a2, (unsigned int)a3);
LABEL_22:
  (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)this + 88LL))(this, 34);
  return v8;
}

```

## disassembly

```asm
0x10041e430  mov     [rsp+arg_0], rbx
0x10041e435  mov     [rsp+arg_18], rsi
0x10041e43a  mov     [rsp+arg_10], r8d
0x10041e43f  mov     [rsp+arg_8], rdx
0x10041e444  push    rdi
0x10041e445  push    r14
0x10041e447  push    r15
0x10041e449  sub     rsp, 50h
0x10041e44d  movzx   r15d, r9b
0x10041e451  mov     esi, r8d
0x10041e454  mov     rdi, rdx
0x10041e457  mov     rbx, rcx
0x10041e45a  xor     r14d, r14d
0x10041e45d  mov     [rsp+68h+var_40], r14d
0x10041e462  mov     rax, [rcx]
0x10041e465  lea     edx, [r14+22h]
0x10041e469  mov     rax, [rax+58h]
0x10041e46d  call    cs:__guard_dispatch_icall_fptr
0x10041e473  cmp     [rbx+0E1h], r14b
0x10041e47a  jz      short loc_10041E4A0
0x10041e47c  test    rdi, rdi
0x10041e47f  jz      loc_10041E5AE
0x10041e485  mov     rax, [rbx]
0x10041e488  mov     r8d, esi
0x10041e48b  mov     rdx, rdi
0x10041e48e  mov     rcx, rbx
0x10041e491  mov     rax, [rax+48h]
0x10041e495  call    cs:__guard_dispatch_icall_fptr
0x10041e49b  jmp     loc_10041E5AE
0x10041e4a0  test    rdi, rdi
0x10041e4a3  jz      loc_10041E5AE
0x10041e4a9  test    esi, esi
0x10041e4ab  jns     short loc_10041E4BD
0x10041e4ad  mov     r14d, 80070057h
0x10041e4b3  mov     [rsp+68h+var_40], r14d
0x10041e4b8  jmp     loc_10041E5CF
0x10041e4bd  mov     rax, [rbx]
0x10041e4c0  mov     rcx, rbx
0x10041e4c3  mov     rax, [rax+0F8h]
0x10041e4ca  call    cs:__guard_dispatch_icall_fptr
0x10041e4d0  mov     eax, esi
0x10041e4d2  dec     esi
0x10041e4d4  mov     [rsp+68h+arg_10], esi
0x10041e4db  test    eax, eax
0x10041e4dd  jz      loc_10041E59B
0x10041e4e3  movzx   edx, word ptr [rdi]
0x10041e4e6  mov     [rsp+68h+var_3C], edx
0x10041e4ea  add     rdi, 2
0x10041e4ee  mov     [rsp+68h+arg_8], rdi
0x10041e4f3  cmp     edx, 3Eh ; '>'
0x10041e4f6  ja      loc_10041E586
0x10041e4fc  mov     ecx, edx
0x10041e4fe  sub     ecx, 22h ; '"'
0x10041e501  jz      short loc_10041E56A
0x10041e503  sub     ecx, 3
0x10041e506  jz      short loc_10041E549
0x10041e508  sub     ecx, 1
0x10041e50b  jz      short loc_10041E530
0x10041e50d  cmp     ecx, 16h
0x10041e510  jnz     short loc_10041E586
0x10041e512  test    r15b, r15b
0x10041e515  jz      short loc_10041E586
0x10041e517  mov     rax, [rbx]
0x10041e51a  lea     rdx, a60; "&#60;"
0x10041e521  mov     rcx, rbx
0x10041e524  mov     rax, [rax+50h]
0x10041e528  call    cs:__guard_dispatch_icall_fptr
0x10041e52e  jmp     short loc_10041E4D0
0x10041e530  mov     rax, [rbx]
0x10041e533  lea     rdx, a38; "&#38;"
0x10041e53a  mov     rcx, rbx
0x10041e53d  mov     rax, [rax+50h]
0x10041e541  call    cs:__guard_dispatch_icall_fptr
0x10041e547  jmp     short loc_10041E4D0
0x10041e549  test    r15b, r15b
0x10041e54c  jnz     short loc_10041E586
0x10041e54e  mov     rax, [rbx]
0x10041e551  lea     rdx, a37; "&#37;"
0x10041e558  mov     rcx, rbx
0x10041e55b  mov     rax, [rax+50h]
0x10041e55f  call    cs:__guard_dispatch_icall_fptr
0x10041e565  jmp     loc_10041E4D0
0x10041e56a  mov     rax, [rbx]
0x10041e56d  lea     rdx, a34; "&#34;"
0x10041e574  mov     rcx, rbx
0x10041e577  mov     rax, [rax+50h]
0x10041e57b  call    cs:__guard_dispatch_icall_fptr
0x10041e581  jmp     loc_10041E4D0
0x10041e586  mov     rax, [rbx]
0x10041e589  mov     rcx, rbx
0x10041e58c  mov     rax, [rax+58h]
0x10041e590  call    cs:__guard_dispatch_icall_fptr
0x10041e596  jmp     loc_10041E4D0
0x10041e59b  mov     rax, [rbx]
0x10041e59e  mov     rcx, rbx
0x10041e5a1  mov     rax, [rax+100h]
0x10041e5a8  call    cs:__guard_dispatch_icall_fptr
0x10041e5ae  mov     rax, [rbx]
0x10041e5b1  mov     edx, 22h ; '"'
0x10041e5b6  mov     rcx, rbx
0x10041e5b9  mov     rax, [rax+58h]
0x10041e5bd  call    cs:__guard_dispatch_icall_fptr
0x10041e5c3  jmp     short loc_10041E5CF
0x10041e5c5  mov     r14d, [rsp+68h+var_48]
0x10041e5ca  mov     [rsp+68h+var_40], r14d
0x10041e5cf  mov     eax, r14d
0x10041e5d2  mov     rbx, [rsp+68h+arg_0]
0x10041e5d7  mov     rsi, [rsp+68h+arg_18]
0x10041e5df  add     rsp, 50h
0x10041e5e3  pop     r15
0x10041e5e5  pop     r14
0x10041e5e7  pop     rdi
0x10041e5e8  retn
0x10043a070  push    rbp
0x10043a072  sub     rsp, 20h
0x10043a076  mov     rbp, rdx
0x10043a079  mov     [rbp+40h], rcx
0x10043a07d  mov     [rbp+38h], rcx
0x10043a081  mov     rax, [rbp+38h]
0x10043a085  mov     rcx, [rax]
0x10043a088  mov     [rbp+30h], rcx
0x10043a08c  mov     rax, [rbp+30h]
0x10043a090  mov     eax, [rax]
0x10043a092  cmp     eax, 0C0000005h
0x10043a097  jz      short loc_10043A0C9
0x10043a099  add     eax, 1FFFFFFFh
0x10043a09e  cmp     eax, 1
0x10043a0a1  ja      short loc_10043A0B9
0x10043a0a3  mov     rax, [rbp+30h]
0x10043a0a7  cmp     dword ptr [rax+18h], 1
0x10043a0ab  jnz     short loc_10043A0B9
0x10043a0ad  mov     rax, [rbp+30h]
0x10043a0b1  mov     ecx, [rax+20h]
0x10043a0b4  mov     [rbp+20h], ecx
0x10043a0b7  jmp     short loc_10043A0C0
0x10043a0b9  mov     dword ptr [rbp+20h], 8000FFFFh
0x10043a0c0  mov     dword ptr [rbp+24h], 1
0x10043a0c7  jmp     short loc_10043A0D0
0x10043a0c9  mov     dword ptr [rbp+24h], 0
0x10043a0d0  mov     eax, [rbp+24h]
0x10043a0d3  add     rsp, 20h
0x10043a0d7  pop     rbp
0x10043a0d8  retn
```
