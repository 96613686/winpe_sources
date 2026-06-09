# SAXWriter::attributeDecl(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041f320`
- end: `0x10041f5d3`
- name: `?attributeDecl@SAXWriter@@UEAAJPEB_WH0H0H0H0H@Z`
- size: `691`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int, const wchar_t *String1, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x10041e430`
- `0x10041f320`
- `0x10041f5e0`
- `0x10042d920`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::attributeDecl(
        SAXWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        const wchar_t *a6,
        unsigned int a7,
        wchar_t *String1,
        unsigned int a9,
        wchar_t *a10,
        int a11)
{
  unsigned int v15; // ebx
  SAXWriter *v16; // rdi
  int v17; // esi
  int v18; // ebx
  unsigned int v20; // [rsp+20h] [rbp-48h]
  int v21; // [rsp+B0h] [rbp+48h]

  v15 = 0;
  v20 = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      if ( a6 )
      {
        if ( *((_DWORD *)this + 9) == 1 )
        {
          *((_DWORD *)this + 9) = 1;
        }
        else
        {
          v15 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 4) + 40LL))((char *)this - 32, 1);
          v20 = v15;
          if ( v15 )
            return v15;
        }
        v16 = (SAXWriter *)((char *)this - 32);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v16 + 88LL))(v16, 60);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v16 + 88LL))(v16, 33);
        (*(void (__fastcall **)(SAXWriter *, const wchar_t *))(*(_QWORD *)v16 + 80LL))(v16, L"ATTLIST");
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v16 + 88LL))(v16, 32);
        (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)v16 + 72LL))(v16, a2, a3);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v16 + 88LL))(v16, 32);
        (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)v16 + 72LL))(v16, a4, a5);
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v16 + 88LL))(v16, 32);
        (*(void (__fastcall **)(SAXWriter *, const wchar_t *, _QWORD))(*(_QWORD *)v16 + 72LL))(v16, a6, a7);
        if ( String1 )
        {
          (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v16 + 88LL))(v16, 32);
          v17 = a9;
          (*(void (__fastcall **)(SAXWriter *, wchar_t *, _QWORD))(*(_QWORD *)v16 + 72LL))(v16, String1, a9);
        }
        else
        {
          v17 = a9;
        }
        if ( a10 )
        {
          v18 = v17 - 1;
          v21 = v17 - 1;
          if ( v17 > 0
            && String1
            && (v17 == 10 && (_mm_lfence(), v18 = 9, !wcsncmp(String1, CodeStringPtr::REQUIRED, v21))
             || v18 == 8 && (_mm_lfence(), !wcsncmp(String1, CodeStringPtr::IMPLIED, v21))) )
          {
            v15 = v20;
          }
          else
          {
            (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v16 + 88LL))(v16, 32);
            v15 = SAXWriter::writeDTDQuoted(v16, a10, a11, 1);
            if ( v15 )
              return v15;
          }
        }
        (*(void (__fastcall **)(SAXWriter *, __int64))(*(_QWORD *)v16 + 88LL))(v16, 62);
        (*(void (__fastcall **)(SAXWriter *))(*(_QWORD *)v16 + 56LL))(v16);
        return v15;
      }
      return (unsigned int)-2147024809;
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
}

```

## disassembly

```asm
0x10041f320  mov     [rsp+arg_0], rbx
0x10041f325  mov     [rsp+arg_8], rsi
0x10041f32a  mov     [rsp+arg_10], rdi
0x10041f32f  push    r12
0x10041f331  push    r14
0x10041f333  push    r15
0x10041f335  sub     rsp, 50h
0x10041f339  mov     r14, r9
0x10041f33c  mov     r12d, r8d
0x10041f33f  mov     r15, rdx
0x10041f342  mov     rdi, rcx
0x10041f345  xor     ebx, ebx
0x10041f347  mov     [rsp+68h+var_48], ebx
0x10041f34b  test    rdx, rdx
0x10041f34e  jnz     short loc_10041F35E
0x10041f350  mov     ebx, 80070057h
0x10041f355  mov     [rsp+68h+var_48], ebx
0x10041f359  jmp     loc_10041F5B4
0x10041f35e  test    r14, r14
0x10041f361  jnz     short loc_10041F371
0x10041f363  mov     ebx, 80070057h
0x10041f368  mov     [rsp+68h+var_48], ebx
0x10041f36c  jmp     loc_10041F5B4
0x10041f371  mov     rsi, [rsp+68h+arg_28]
0x10041f379  test    rsi, rsi
0x10041f37c  jnz     short loc_10041F38C
0x10041f37e  mov     ebx, 80070057h
0x10041f383  mov     [rsp+68h+var_48], ebx
0x10041f387  jmp     loc_10041F5B4
0x10041f38c  cmp     dword ptr [rcx+24h], 1
0x10041f390  jnz     short loc_10041F39B
0x10041f392  mov     dword ptr [rcx+24h], 1
0x10041f399  jmp     short loc_10041F3BF
0x10041f39b  add     rcx, 0FFFFFFFFFFFFFFE0h
0x10041f39f  mov     rax, [rcx]
0x10041f3a2  mov     edx, 1
0x10041f3a7  mov     rax, [rax+28h]
0x10041f3ab  call    cs:__guard_dispatch_icall_fptr
0x10041f3b1  mov     ebx, eax
0x10041f3b3  mov     [rsp+68h+var_48], eax
0x10041f3b7  test    eax, eax
0x10041f3b9  jnz     loc_10041F5B4
0x10041f3bf  add     rdi, 0FFFFFFFFFFFFFFE0h
0x10041f3c3  mov     rax, [rdi]
0x10041f3c6  mov     edx, 3Ch ; '<'
0x10041f3cb  mov     rcx, rdi
0x10041f3ce  mov     rax, [rax+58h]
0x10041f3d2  call    cs:__guard_dispatch_icall_fptr
0x10041f3d8  mov     rax, [rdi]
0x10041f3db  mov     edx, 21h ; '!'
0x10041f3e0  mov     rcx, rdi
0x10041f3e3  mov     rax, [rax+58h]
0x10041f3e7  call    cs:__guard_dispatch_icall_fptr
0x10041f3ed  mov     rax, [rdi]
0x10041f3f0  lea     rdx, aAttlist; "ATTLIST"
0x10041f3f7  mov     rcx, rdi
0x10041f3fa  mov     rax, [rax+50h]
0x10041f3fe  call    cs:__guard_dispatch_icall_fptr
0x10041f404  mov     rax, [rdi]
0x10041f407  mov     edx, 20h ; ' '
0x10041f40c  mov     rcx, rdi
0x10041f40f  mov     rax, [rax+58h]
0x10041f413  call    cs:__guard_dispatch_icall_fptr
0x10041f419  mov     rax, [rdi]
0x10041f41c  mov     r8d, r12d
0x10041f41f  mov     rdx, r15
0x10041f422  mov     rcx, rdi
0x10041f425  mov     rax, [rax+48h]
0x10041f429  call    cs:__guard_dispatch_icall_fptr
0x10041f42f  mov     rax, [rdi]
0x10041f432  mov     edx, 20h ; ' '
0x10041f437  mov     rcx, rdi
0x10041f43a  mov     rax, [rax+58h]
0x10041f43e  call    cs:__guard_dispatch_icall_fptr
0x10041f444  mov     rax, [rdi]
0x10041f447  mov     r8d, [rsp+68h+arg_20]
0x10041f44f  mov     rdx, r14
0x10041f452  mov     rcx, rdi
0x10041f455  mov     rax, [rax+48h]
0x10041f459  call    cs:__guard_dispatch_icall_fptr
0x10041f45f  mov     rax, [rdi]
0x10041f462  mov     edx, 20h ; ' '
0x10041f467  mov     rcx, rdi
0x10041f46a  mov     rax, [rax+58h]
0x10041f46e  call    cs:__guard_dispatch_icall_fptr
0x10041f474  mov     rax, [rdi]
0x10041f477  mov     r8d, [rsp+68h+arg_30]
0x10041f47f  mov     rdx, rsi
0x10041f482  mov     rcx, rdi
0x10041f485  mov     rax, [rax+48h]
0x10041f489  call    cs:__guard_dispatch_icall_fptr
0x10041f48f  mov     r14, [rsp+68h+String1]
0x10041f497  test    r14, r14
0x10041f49a  jz      short loc_10041F4D0
0x10041f49c  mov     rax, [rdi]
0x10041f49f  mov     edx, 20h ; ' '
0x10041f4a4  mov     rcx, rdi
0x10041f4a7  mov     rax, [rax+58h]
0x10041f4ab  call    cs:__guard_dispatch_icall_fptr
0x10041f4b1  mov     rax, [rdi]
0x10041f4b4  mov     esi, [rsp+68h+arg_40]
0x10041f4bb  mov     r8d, esi
0x10041f4be  mov     rdx, r14
0x10041f4c1  mov     rcx, rdi
0x10041f4c4  mov     rax, [rax+48h]
0x10041f4c8  call    cs:__guard_dispatch_icall_fptr
0x10041f4ce  jmp     short loc_10041F4D7
0x10041f4d0  mov     esi, [rsp+68h+arg_40]
0x10041f4d7  mov     r15, [rsp+68h+arg_48]
0x10041f4df  test    r15, r15
0x10041f4e2  jz      loc_10041F585
0x10041f4e8  lea     ebx, [rsi-1]
0x10041f4eb  mov     [rsp+68h+arg_40], ebx
0x10041f4f2  test    esi, esi
0x10041f4f4  jle     short loc_10041F550
0x10041f4f6  test    r14, r14
0x10041f4f9  jz      short loc_10041F550
0x10041f4fb  cmp     ebx, cs:dword_1004474C8
0x10041f501  jnz     short loc_10041F524
0x10041f503  lfence
0x10041f506  movsxd  rbx, [rsp+68h+arg_40]
0x10041f50e  mov     r8, rbx; MaxCount
0x10041f511  mov     rdx, cs:?REQUIRED@CodeStringPtr@@2UStringPtr@@A; String2
0x10041f518  mov     rcx, r14; String1
0x10041f51b  call    wcsncmp
0x10041f520  test    eax, eax
0x10041f522  jz      short loc_10041F54A
0x10041f524  cmp     ebx, cs:dword_100447448
0x10041f52a  jnz     short loc_10041F550
0x10041f52c  lfence
0x10041f52f  movsxd  r8, [rsp+68h+arg_40]; MaxCount
0x10041f537  mov     rdx, cs:?IMPLIED@CodeStringPtr@@2UStringPtr@@A; String2
0x10041f53e  mov     rcx, r14; String1
0x10041f541  call    wcsncmp
0x10041f546  test    eax, eax
0x10041f548  jnz     short loc_10041F550
0x10041f54a  mov     ebx, [rsp+68h+var_48]
0x10041f54e  jmp     short loc_10041F585
0x10041f550  mov     rax, [rdi]
0x10041f553  mov     edx, 20h ; ' '
0x10041f558  mov     rcx, rdi
0x10041f55b  mov     rax, [rax+58h]
0x10041f55f  call    cs:__guard_dispatch_icall_fptr
0x10041f565  mov     r9b, 1; bool
0x10041f568  mov     r8d, [rsp+68h+arg_50]; int
0x10041f570  mov     rdx, r15; wchar_t *
0x10041f573  mov     rcx, rdi; this
0x10041f576  call    ?writeDTDQuoted@SAXWriter@@IEAAJPEB_WH_N@Z; SAXWriter::writeDTDQuoted(wchar_t const *,int,bool)
0x10041f57b  mov     ebx, eax
0x10041f57d  mov     [rsp+68h+var_48], eax
0x10041f581  test    eax, eax
0x10041f583  jnz     short loc_10041F5B4
0x10041f585  mov     rax, [rdi]
0x10041f588  mov     edx, 3Eh ; '>'
0x10041f58d  mov     rcx, rdi
0x10041f590  mov     rax, [rax+58h]
0x10041f594  call    cs:__guard_dispatch_icall_fptr
0x10041f59a  mov     rax, [rdi]
0x10041f59d  mov     rcx, rdi
0x10041f5a0  mov     rax, [rax+38h]
0x10041f5a4  call    cs:__guard_dispatch_icall_fptr
0x10041f5aa  jmp     short loc_10041F5B4
0x10041f5ac  mov     ebx, [rsp+68h+var_44]
0x10041f5b0  mov     [rsp+68h+var_48], ebx
0x10041f5b4  mov     eax, ebx
0x10041f5b6  mov     rbx, [rsp+68h+arg_0]
0x10041f5bb  mov     rsi, [rsp+68h+arg_8]
0x10041f5c0  mov     rdi, [rsp+68h+arg_10]
0x10041f5c8  add     rsp, 50h
0x10041f5cc  pop     r15
0x10041f5ce  pop     r14
0x10041f5d0  pop     r12
0x10041f5d2  retn
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
