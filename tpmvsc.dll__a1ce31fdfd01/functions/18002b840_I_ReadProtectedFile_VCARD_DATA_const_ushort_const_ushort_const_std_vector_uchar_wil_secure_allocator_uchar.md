# I_ReadProtectedFile(VCARD_DATA const *,ushort const *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> *)

- ea: `0x18002b840`
- end: `0x18002b9e6`
- name: `?I_ReadProtectedFile@@YAKPEBUVCARD_DATA@@PEBG1PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001001c`
- `0x180010298`
- `0x1800105b4`
- `0x180012990`
- `0x180012e58`
- `0x1800146b8`

## callees

- `0x180001ec0`
- `0x18000653c`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c198`
- `0x18002a1c0`
- `0x18002a470`
- `0x18002b4a4`
- `0x18002b840`
- `0x18002b9ec`
- `0x1800348a0`

## string_xrefs

- `0x18002b93c`: `Unable to read file`
- `0x18002b87b`: `I_ReadProtectedFile`

## pseudocode

```c
__int64 __fastcall I_ReadProtectedFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int v12; // edx
  const char *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  unsigned int File; // [rsp+30h] [rbp-29h] BYREF
  int v18; // [rsp+34h] [rbp-25h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v20[3]; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v21[3]; // [rsp+58h] [rbp-1h] BYREF
  char v22[24]; // [rsp+70h] [rbp+17h] BYREF

  File = 0;
  v18 = 0;
  strcpy(v22, "I_ReadProtectedFile");
  v20[0] = v22;
  v20[1] = &v18;
  v20[2] = &File;
  lambda_4ddc7463255b2196f5d15f0f67c342c0_::operator()(v20);
  v18 = 1;
  v19 = v20;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v21);
  File = I_ReadFile(a1, a2, a3, v21);
  if ( File )
  {
    WppTraceIndent(v10, 2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v12 = 42;
    v13 = "Unable to read file";
    goto LABEL_19;
  }
  File = I_UnprotectData(v21, a4);
  if ( !File )
  {
    v15 = 0;
    goto LABEL_22;
  }
  WppTraceIndent(v14, 2);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 43;
    v13 = "Unable to unprotect file";
LABEL_19:
    WPP_SF_sDs(
      v11[2],
      v12,
      (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
      (_DWORD)WPP_pszIndent,
      File,
      (__int64)v13);
  }
LABEL_20:
  v15 = File;
LABEL_22:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v21);
  WppTraceUnwinder__lambda_4ddc7463255b2196f5d15f0f67c342c0____::_WppTraceUnwinder__lambda_4ddc7463255b2196f5d15f0f67c342c0____(&v19);
  return v15;
}

```

## disassembly

```asm
0x18002b840  push    rbp
0x18002b842  push    rbx
0x18002b843  push    rsi
0x18002b844  push    rdi
0x18002b845  push    r14
0x18002b847  lea     rbp, [rsp-37h]
0x18002b84c  sub     rsp, 90h
0x18002b853  mov     rax, cs:__security_cookie
0x18002b85a  xor     rax, rsp
0x18002b85d  mov     [rbp+57h+var_28], rax
0x18002b861  mov     rbx, r9
0x18002b864  mov     rsi, r8
0x18002b867  mov     rdi, rdx
0x18002b86a  mov     r14, rcx
0x18002b86d  mov     [rbp+57h+var_80], 0
0x18002b874  mov     [rbp+57h+var_7C], 0
0x18002b87b  movups  xmm0, xmmword ptr cs:aIReadprotected; "I_ReadProtectedFile"
0x18002b882  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18002b886  mov     eax, dword ptr cs:aIReadprotected+10h; "ile"
0x18002b88c  mov     dword ptr [rbp+57h+var_40+10h], eax
0x18002b88f  lea     rax, [rbp+57h+var_40]
0x18002b893  mov     [rbp+57h+var_70], rax
0x18002b897  lea     rax, [rbp+57h+var_7C]
0x18002b89b  mov     [rbp+57h+var_68], rax
0x18002b89f  lea     rax, [rbp+57h+var_80]
0x18002b8a3  mov     [rbp+57h+var_60], rax
0x18002b8a7  lea     rcx, [rbp+57h+var_70]
0x18002b8ab  call    _lambda_4ddc7463255b2196f5d15f0f67c342c0___operator__
0x18002b8b0  mov     [rbp+57h+var_7C], 1
0x18002b8b7  lea     rax, [rbp+57h+var_70]
0x18002b8bb  mov     [rbp+57h+var_78], rax
0x18002b8bf  test    r14, r14
0x18002b8c2  jnz     short loc_18002B8C9
0x18002b8c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b8c9  test    rdi, rdi
0x18002b8cc  jnz     short loc_18002B8D3
0x18002b8ce  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b8d3  test    rsi, rsi
0x18002b8d6  jnz     short loc_18002B8DD
0x18002b8d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b8dd  test    rbx, rbx
0x18002b8e0  jnz     short loc_18002B8E7
0x18002b8e2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b8e7  lea     rcx, [rbp+57h+var_58]
0x18002b8eb  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002b8f0  nop
0x18002b8f1  lea     r9, [rbp+57h+var_58]
0x18002b8f5  mov     r8, rsi
0x18002b8f8  mov     rdx, rdi
0x18002b8fb  mov     rcx, r14
0x18002b8fe  call    ?I_ReadFile@@YAKPEBUVCARD_DATA@@PEBG1PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_ReadFile(VCARD_DATA const *,ushort const *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x18002b903  mov     [rbp+57h+var_80], eax
0x18002b906  test    eax, eax
0x18002b908  jz      short loc_18002B945
0x18002b90a  mov     edx, 2
0x18002b90f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b914  lea     rax, WPP_GLOBAL_Control
0x18002b91b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b922  cmp     rcx, rax
0x18002b925  jz      loc_18002B9B0
0x18002b92b  test    byte ptr [rcx+1Ch], 1
0x18002b92f  jz      short loc_18002B9B0
0x18002b931  cmp     byte ptr [rcx+19h], 2
0x18002b935  jb      short loc_18002B9B0
0x18002b937  mov     edx, 2Ah ; '*'
0x18002b93c  lea     rax, aUnableToReadFi; "Unable to read file"
0x18002b943  jmp     short loc_18002B98D
0x18002b945  mov     rdx, rbx
0x18002b948  lea     rcx, [rbp+57h+var_58]
0x18002b94c  call    ?I_UnprotectData@@YAKAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@@Z; I_UnprotectData(std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x18002b951  mov     [rbp+57h+var_80], eax
0x18002b954  test    eax, eax
0x18002b956  jz      short loc_18002B9B5
0x18002b958  mov     edx, 2
0x18002b95d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002b962  lea     rax, WPP_GLOBAL_Control
0x18002b969  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b970  cmp     rcx, rax
0x18002b973  jz      short loc_18002B9B0
0x18002b975  test    byte ptr [rcx+1Ch], 1
0x18002b979  jz      short loc_18002B9B0
0x18002b97b  cmp     byte ptr [rcx+19h], 2
0x18002b97f  jb      short loc_18002B9B0
0x18002b981  mov     edx, 2Bh ; '+'
0x18002b986  lea     rax, aUnableToUnprot_1; "Unable to unprotect file"
0x18002b98d  mov     [rsp+0B0h+var_88], rax
0x18002b992  mov     eax, [rbp+57h+var_80]
0x18002b995  mov     [rsp+0B0h+var_90], eax
0x18002b999  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002b9a0  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002b9a7  mov     rcx, [rcx+10h]
0x18002b9ab  call    WPP_SF_sDs
0x18002b9b0  mov     ebx, [rbp+57h+var_80]
0x18002b9b3  jmp     short loc_18002B9B7
0x18002b9b5  xor     ebx, ebx
0x18002b9b7  lea     rcx, [rbp+57h+var_58]
0x18002b9bb  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18002b9c0  nop
0x18002b9c1  lea     rcx, [rbp+57h+var_78]
0x18002b9c5  call    WppTraceUnwinder__lambda_4ddc7463255b2196f5d15f0f67c342c0_______WppTraceUnwinder__lambda_4ddc7463255b2196f5d15f0f67c342c0____
0x18002b9ca  mov     eax, ebx
0x18002b9cc  mov     rcx, [rbp+57h+var_28]
0x18002b9d0  xor     rcx, rsp; StackCookie
0x18002b9d3  call    __security_check_cookie
0x18002b9d8  add     rsp, 90h
0x18002b9df  pop     r14
0x18002b9e1  pop     rdi
0x18002b9e2  pop     rsi
0x18002b9e3  pop     rbx
0x18002b9e4  pop     rbp
0x18002b9e5  retn
```
