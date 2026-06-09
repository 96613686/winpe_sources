# Sid::FromPSID(void *)

- ea: `0x1400829f4`
- end: `0x140082c23`
- name: `?FromPSID@Sid@@SA?AV1@PEAX@Z`
- size: `559`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14002ce74`
- `0x140082648`
- `0x140082d80`
- `0x140082fe8`

## callees

- `0x140005530`
- `0x140006308`
- `0x140006338`
- `0x14001f6b4`
- `0x14002f828`
- `0x1400604d4`
- `0x140060f58`
- `0x14008273c`
- `0x1400829f4`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!CopySid` at `0x140082a45`
- `ADVAPI32!CopySid` at `0x140082a45`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140082a88`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140082a88`
- `KERNEL32!LocalFree` at `0x140082b32`
- `KERNEL32!LocalFree` at `0x140082b32`
- `KERNEL32!GetLastError` at `0x140082b5f`
- `KERNEL32!GetLastError` at `0x140082bc1`
- `KERNEL32!GetLastError` at `0x140082b5f`
- `KERNEL32!GetLastError` at `0x140082bc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void **__fastcall Sid::FromPSID(void **a1, void *a2)
{
  BOOL v4; // ebx
  __int64 v5; // r8
  _BYTE *v6; // rdx
  void *v7; // r9
  void **v8; // rcx
  unsigned __int64 v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  signed int v13; // eax
  unsigned int v14; // ebx
  signed int LastError; // eax
  unsigned int v16; // ebx
  void *Src; // [rsp+28h] [rbp-81h] BYREF
  LPWSTR v18; // [rsp+30h] [rbp-79h] BYREF
  _QWORD pExceptionObject[11]; // [rsp+38h] [rbp-71h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v21[56]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE *v22; // [rsp+D0h] [rbp+27h]

  pExceptionObject[9] = a1;
  Sid::Sid((Sid *)a1);
  if ( !CopySid(0x44u, a1, a2) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v16);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v16);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Src = 0;
  pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_681c72bba3685db507962fa0cd0a806c_,void,unsigned short *>::`vftable';
  pExceptionObject[1] = &Src;
  pExceptionObject[7] = pExceptionObject;
  stdext::GetPointer<void *>::GetPointer<void *>(&StringSid, pExceptionObject);
  v4 = ConvertSidToStringSidW(a2, &StringSid);
  if ( v22 )
  {
    v18 = StringSid;
    (*(void (__fastcall **)(_BYTE *, LPWSTR *))(*(_QWORD *)v22 + 16LL))(v22, &v18);
    if ( v22 )
    {
      v6 = v21;
      LOBYTE(v6) = v22 != v21;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v22 + 32LL))(v22, v6);
    }
  }
  if ( !v4 )
  {
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v14);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v14);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v7 = Src;
  v8 = a1 + 9;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)Src + v9) );
  if ( v9 > (unsigned __int64)a1[12] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v8, v9, v5, Src);
  }
  else
  {
    if ( (unsigned __int64)a1[12] <= 7 )
      v10 = (char *)(a1 + 9);
    else
      v10 = (char *)*v8;
    a1[11] = (void *)v9;
    v11 = 2 * v9;
    memmove_0(v10, v7, 2 * v9);
    *(_WORD *)&v10[v11] = 0;
  }
  if ( Src )
    LocalFree(Src);
  return a1;
}

```

## disassembly

```asm
0x1400829f4  mov     [rsp-8+arg_10], rbx
0x1400829f9  mov     [rsp-8+arg_18], rsi
0x1400829fe  push    rbp
0x1400829ff  push    rdi
0x140082a00  push    r14
0x140082a02  lea     rbp, [rsp-47h]
0x140082a07  sub     rsp, 0F0h
0x140082a0e  mov     rax, cs:__security_cookie
0x140082a15  xor     rax, rsp
0x140082a18  mov     [rbp+57h+var_20], rax
0x140082a1c  mov     rbx, rdx
0x140082a1f  mov     rsi, rcx
0x140082a22  mov     [rbp+57h+var_80], rcx
0x140082a26  xor     r14d, r14d
0x140082a29  mov     [rsp+100h+var_E0], r14d
0x140082a2e  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x140082a33  mov     [rsp+100h+var_E0], 1
0x140082a3b  mov     r8, rbx; pSourceSid
0x140082a3e  mov     rdx, rsi; pDestinationSid
0x140082a41  lea     ecx, [r14+44h]; nDestinationSidLength
0x140082a45  call    cs:__imp_CopySid
0x140082a4b  test    eax, eax
0x140082a4d  jz      loc_140082BC1
0x140082a53  mov     [rsp+100h+Src], r14
0x140082a58  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_681c72bba3685db507962fa0cd0a806c_@@XPEAG@std@@6B@; const std::_Func_impl_no_alloc<_lambda_681c72bba3685db507962fa0cd0a806c_,void,ushort *>::`vftable'
0x140082a5f  mov     [rbp+57h+pExceptionObject], rax
0x140082a63  lea     rax, [rsp+100h+Src]
0x140082a68  mov     [rbp+57h+var_C0], rax
0x140082a6c  lea     rax, [rbp+57h+pExceptionObject]
0x140082a70  mov     [rbp+57h+var_90], rax
0x140082a74  lea     rdx, [rbp+57h+pExceptionObject]
0x140082a78  lea     rcx, [rbp+57h+StringSid]
0x140082a7c  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x140082a81  lea     rdx, [rbp+57h+StringSid]; StringSid
0x140082a85  mov     rcx, rbx; Sid
0x140082a88  call    cs:__imp_ConvertSidToStringSidW
0x140082a8e  mov     ebx, eax
0x140082a90  mov     rcx, [rbp+57h+var_30]
0x140082a94  test    rcx, rcx
0x140082a97  jz      short loc_140082AD1
0x140082a99  mov     rdx, [rbp+57h+StringSid]
0x140082a9d  mov     [rbp+57h+var_D0], rdx
0x140082aa1  mov     rdx, [rcx]
0x140082aa4  mov     rax, [rdx+10h]
0x140082aa8  lea     rdx, [rbp+57h+var_D0]
0x140082aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082ab1  mov     rcx, [rbp+57h+var_30]
0x140082ab5  test    rcx, rcx
0x140082ab8  jz      short loc_140082AD1
0x140082aba  mov     rax, [rcx]
0x140082abd  lea     rdx, [rbp+57h+var_68]
0x140082ac1  cmp     rcx, rdx
0x140082ac4  setnz   dl
0x140082ac7  mov     rax, [rax+20h]
0x140082acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082ad0  nop
0x140082ad1  test    ebx, ebx
0x140082ad3  jz      loc_140082B5F
0x140082ad9  mov     r9, [rsp+100h+Src]
0x140082ade  lea     rcx, [rsi+48h]
0x140082ae2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140082ae6  inc     rdx
0x140082ae9  cmp     [r9+rdx*2], r14w
0x140082aee  jnz     short loc_140082AE6
0x140082af0  cmp     rdx, [rcx+18h]
0x140082af4  ja      short loc_140082B22
0x140082af6  cmp     qword ptr [rcx+18h], 7
0x140082afb  jbe     short loc_140082B02
0x140082afd  mov     rdi, [rcx]
0x140082b00  jmp     short loc_140082B05
0x140082b02  mov     rdi, rcx
0x140082b05  mov     [rcx+10h], rdx
0x140082b09  lea     rbx, [rdx+rdx]
0x140082b0d  mov     r8, rbx; Size
0x140082b10  mov     rdx, r9; Src
0x140082b13  mov     rcx, rdi; void *
0x140082b16  call    memmove_0
0x140082b1b  mov     [rbx+rdi], r14w
0x140082b20  jmp     short loc_140082B28
0x140082b22  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x140082b27  nop
0x140082b28  mov     rcx, [rsp+100h+Src]; hMem
0x140082b2d  test    rcx, rcx
0x140082b30  jz      short loc_140082B38
0x140082b32  call    cs:__imp_LocalFree
0x140082b38  mov     rax, rsi
0x140082b3b  mov     rcx, [rbp+57h+var_20]
0x140082b3f  xor     rcx, rsp; StackCookie
0x140082b42  call    __security_check_cookie
0x140082b47  lea     r11, [rsp+100h+var_10]
0x140082b4f  mov     rbx, [r11+30h]
0x140082b53  mov     rsi, [r11+38h]
0x140082b57  mov     rsp, r11
0x140082b5a  pop     r14
0x140082b5c  pop     rdi
0x140082b5d  pop     rbp
0x140082b5e  retn
0x140082b5f  call    cs:__imp_GetLastError
0x140082b65  mov     ebx, eax
0x140082b67  test    eax, eax
0x140082b69  jle     short loc_140082B74
0x140082b6b  movzx   ebx, ax
0x140082b6e  or      ebx, 80070000h
0x140082b74  lea     rax, WPP_GLOBAL_Control
0x140082b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140082b82  cmp     rcx, rax
0x140082b85  jz      short loc_140082BA5
0x140082b87  test    byte ptr [rcx+1Ch], 1
0x140082b8b  jz      short loc_140082BA5
0x140082b8d  mov     edx, 0Bh
0x140082b92  mov     r9d, ebx
0x140082b95  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x140082b9c  mov     rcx, [rcx+10h]
0x140082ba0  call    WPP_SF_d
0x140082ba5  mov     edx, ebx; int
0x140082ba7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140082bab  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140082bb0  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140082bb7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140082bbb  call    _CxxThrowException_0
0x140082bc1  call    cs:__imp_GetLastError
0x140082bc7  mov     ebx, eax
0x140082bc9  test    eax, eax
0x140082bcb  jle     short loc_140082BD6
0x140082bcd  movzx   ebx, ax
0x140082bd0  or      ebx, 80070000h
0x140082bd6  lea     rax, WPP_GLOBAL_Control
0x140082bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140082be4  cmp     rcx, rax
0x140082be7  jz      short loc_140082C07
0x140082be9  test    byte ptr [rcx+1Ch], 1
0x140082bed  jz      short loc_140082C07
0x140082bef  mov     edx, 0Ah
0x140082bf4  mov     r9d, ebx
0x140082bf7  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x140082bfe  mov     rcx, [rcx+10h]
0x140082c02  call    WPP_SF_d
0x140082c07  mov     edx, ebx; int
0x140082c09  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140082c0d  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140082c12  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140082c19  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140082c1d  call    _CxxThrowException_0
```
