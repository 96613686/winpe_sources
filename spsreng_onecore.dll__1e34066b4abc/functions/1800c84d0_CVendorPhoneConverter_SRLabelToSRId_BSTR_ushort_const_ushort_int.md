# CVendorPhoneConverter::SRLabelToSRId_BSTR(ushort const *,ushort * *,int)

- ea: `0x1800c84d0`
- end: `0x1800c8682`
- name: `?SRLabelToSRId_BSTR@CVendorPhoneConverter@@UEAAJPEBGPEAPEAGH@Z`
- size: `434`
- prototype: `int(CVendorPhoneConverter *__hidden this, const unsigned __int16 *, unsigned __int16 **, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800034b0`
- `0x1800055cc`
- `0x1800adc24`
- `0x1800b1210`
- `0x1800c84d0`
- `0x1800e46b0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800c862d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800c862d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c856b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c856b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c85a2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c85a2`

## pseudocode

```c
__int64 __fastcall CVendorPhoneConverter::SRLabelToSRId_BSTR(
        PHN_DICT **this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        int a4)
{
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rax
  int cbMultiByte; // esi
  int Win32Error; // ebx
  char *lpMultiByteStr; // rax
  char *v15; // rbp
  OLECHAR *v16; // rsi
  signed int v17; // edi
  char *v18; // rax
  unsigned __int8 v19; // al
  char *v20; // rax
  unsigned __int16 *v21; // rax
  int v22; // ecx
  char *v24; // [rsp+40h] [rbp-368h] BYREF
  OLECHAR strIn[392]; // [rsp+50h] [rbp-358h] BYREF

  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 && !(unsigned int)SPIsBadStringPtr(a2, (unsigned int)a2) )
  {
    *a3 = 0;
    v10 = v9;
    do
      ++v10;
    while ( a2[v10] );
    v11 = v10 + 1;
    cbMultiByte = v11;
    if ( (unsigned int)v11 == v11
      && (lpMultiByteStr = (char *)CoTaskMemAlloc((unsigned int)v11), (v15 = lpMultiByteStr) != 0) )
    {
      Win32Error = 0;
      v24 = lpMultiByteStr;
      if ( WideCharToMultiByte(0, 0x400u, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0)
        || (Win32Error = HrFromLastWin32Error(), Win32Error >= 0) )
      {
        v16 = strIn;
        v17 = 0;
        while ( *v24 )
        {
          if ( v17 >= 384 )
            break;
          v18 = nxtarg(&v24);
          if ( !*v18 )
            break;
          v19 = PHN_DICT::PhoneIdFromNamePriv(this[1], v18);
          if ( v19 == 0xFF )
          {
            if ( a4 )
              goto LABEL_24;
          }
          else
          {
            *v16++ = v19;
            ++v17;
          }
        }
        v20 = v24;
        *v16 = 0;
        if ( *v20 && v17 == 384 )
        {
LABEL_24:
          Win32Error = -2147024809;
          goto LABEL_28;
        }
        v21 = SysAllocStringLen(strIn, v17);
        v22 = Win32Error;
        *a3 = v21;
        if ( !v21 )
          v22 = -2147024882;
        Win32Error = v22;
      }
LABEL_28:
      CoTaskMemFree(v15);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800c84d0  mov     [rsp+arg_18], rbx
0x1800c84d5  push    rbp
0x1800c84d6  push    rsi
0x1800c84d7  push    rdi
0x1800c84d8  push    r12
0x1800c84da  push    r13
0x1800c84dc  push    r14
0x1800c84de  push    r15
0x1800c84e0  sub     rsp, 370h
0x1800c84e7  mov     rax, cs:__security_cookie
0x1800c84ee  xor     rax, rsp
0x1800c84f1  mov     [rsp+3A8h+var_48], rax
0x1800c84f9  xor     r12d, r12d
0x1800c84fc  mov     r15d, r9d
0x1800c84ff  mov     r14, r8
0x1800c8502  mov     rdi, rdx
0x1800c8505  mov     r13, rcx
0x1800c8508  test    rdx, rdx
0x1800c850b  jz      loc_1800C8650
0x1800c8511  test    r8, r8
0x1800c8514  jz      loc_1800C8650
0x1800c851a  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c851e  mov     rax, r8
0x1800c8521  inc     rax
0x1800c8524  cmp     [rdx+rax*2], r12w
0x1800c8529  jnz     short loc_1800C8521
0x1800c852b  test    rax, rax
0x1800c852e  jz      loc_1800C8650
0x1800c8534  mov     rcx, rdi; unsigned __int16 *
0x1800c8537  call    ?SPIsBadStringPtr@@YAHPEBGK@Z; SPIsBadStringPtr(ushort const *,ulong)
0x1800c853c  test    eax, eax
0x1800c853e  jnz     loc_1800C8650
0x1800c8544  mov     [r14], r12
0x1800c8547  mov     rax, r8
0x1800c854a  inc     rax
0x1800c854d  cmp     [rdi+rax*2], r12w
0x1800c8552  jnz     short loc_1800C854A
0x1800c8554  inc     rax
0x1800c8557  mov     esi, eax
0x1800c8559  cmp     rsi, rax
0x1800c855c  jz      short loc_1800C8568
0x1800c855e  mov     ebx, 8007000Eh
0x1800c8563  jmp     loc_1800C8655
0x1800c8568  mov     rcx, rsi; cb
0x1800c856b  call    cs:__imp_CoTaskMemAlloc
0x1800c8571  mov     rbp, rax
0x1800c8574  test    rax, rax
0x1800c8577  jz      short loc_1800C855E
0x1800c8579  mov     [rsp+3A8h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1800c857e  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800c8582  mov     [rsp+3A8h+lpDefaultChar], r12; lpDefaultChar
0x1800c8587  mov     r8, rdi; lpWideCharStr
0x1800c858a  mov     [rsp+3A8h+cbMultiByte], esi; cbMultiByte
0x1800c858e  mov     edx, 400h; dwFlags
0x1800c8593  xor     ecx, ecx; CodePage
0x1800c8595  mov     [rsp+3A8h+lpMultiByteStr], rax; lpMultiByteStr
0x1800c859a  mov     ebx, r12d
0x1800c859d  mov     [rsp+3A8h+var_368], rax
0x1800c85a2  call    cs:__imp_WideCharToMultiByte
0x1800c85a8  test    eax, eax
0x1800c85aa  jnz     short loc_1800C85BB
0x1800c85ac  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800c85b1  mov     ebx, eax
0x1800c85b3  test    eax, eax
0x1800c85b5  js      loc_1800C8645
0x1800c85bb  lea     rsi, [rsp+3A8h+strIn]
0x1800c85c0  mov     edi, r12d
0x1800c85c3  mov     rcx, [rsp+3A8h+var_368]
0x1800c85c8  cmp     [rcx], r12b
0x1800c85cb  jz      short loc_1800C8609
0x1800c85cd  cmp     edi, 180h
0x1800c85d3  jge     short loc_1800C8609
0x1800c85d5  lea     rcx, [rsp+3A8h+var_368]; char **
0x1800c85da  call    ?nxtarg@@YAPEADPEAPEAD@Z; nxtarg(char * *)
0x1800c85df  cmp     [rax], r12b
0x1800c85e2  jz      short loc_1800C8609
0x1800c85e4  mov     rcx, [r13+8]; this
0x1800c85e8  mov     rdx, rax; char *
0x1800c85eb  call    ?PhoneIdFromNamePriv@PHN_DICT@@QEBAEPEBD@Z; PHN_DICT::PhoneIdFromNamePriv(char const *)
0x1800c85f0  cmp     al, 0FFh
0x1800c85f2  jnz     short loc_1800C85FB
0x1800c85f4  test    r15d, r15d
0x1800c85f7  jz      short loc_1800C85C3
0x1800c85f9  jmp     short loc_1800C861F
0x1800c85fb  movzx   eax, al
0x1800c85fe  mov     [rsi], ax
0x1800c8601  add     rsi, 2
0x1800c8605  inc     edi
0x1800c8607  jmp     short loc_1800C85C3
0x1800c8609  mov     rax, [rsp+3A8h+var_368]
0x1800c860e  mov     [rsi], r12w
0x1800c8612  cmp     [rax], r12b
0x1800c8615  jz      short loc_1800C8626
0x1800c8617  cmp     edi, 180h
0x1800c861d  jnz     short loc_1800C8626
0x1800c861f  mov     ebx, 80070057h
0x1800c8624  jmp     short loc_1800C8645
0x1800c8626  mov     edx, edi; ui
0x1800c8628  lea     rcx, [rsp+3A8h+strIn]; strIn
0x1800c862d  call    cs:__imp_SysAllocStringLen
0x1800c8633  mov     ecx, ebx
0x1800c8635  mov     ebx, 8007000Eh
0x1800c863a  test    rax, rax
0x1800c863d  mov     [r14], rax
0x1800c8640  cmovz   ecx, ebx
0x1800c8643  mov     ebx, ecx
0x1800c8645  mov     rcx, rbp; pv
0x1800c8648  call    cs:__imp_CoTaskMemFree
0x1800c864e  jmp     short loc_1800C8655
0x1800c8650  mov     ebx, 80070057h
0x1800c8655  mov     eax, ebx
0x1800c8657  mov     rcx, [rsp+3A8h+var_48]
0x1800c865f  xor     rcx, rsp; StackCookie
0x1800c8662  call    __security_check_cookie
0x1800c8667  mov     rbx, [rsp+3A8h+arg_18]
0x1800c866f  add     rsp, 370h
0x1800c8676  pop     r15
0x1800c8678  pop     r14
0x1800c867a  pop     r13
0x1800c867c  pop     r12
0x1800c867e  pop     rdi
0x1800c867f  pop     rsi
0x1800c8680  pop     rbp
0x1800c8681  retn
```
