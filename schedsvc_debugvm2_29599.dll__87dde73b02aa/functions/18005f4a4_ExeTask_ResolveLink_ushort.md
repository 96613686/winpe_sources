# ExeTask::ResolveLink(ushort * &)

- ea: `0x18005f4a4`
- end: `0x18005f828`
- name: `?ResolveLink@ExeTask@@IEAAJAEAPEAG@Z`
- size: `900`
- prototype: `__int64 __fastcall(ExeTask *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002a7a4`

## callees

- `0x180019130`
- `0x18002a9e0`
- `0x18002ae80`
- `0x1800339c0`
- `0x18005f4a4`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18005f52e`
- `msvcrt!wcsrchr` at `0x18005f743`
- `msvcrt!wcsrchr` at `0x18005f52e`
- `msvcrt!wcsrchr` at `0x18005f743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7f9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005f678`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005f678`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005f501`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005f501`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ExeTask::ResolveLink(ExeTask *this, unsigned __int16 **a2)
{
  int v4; // ebx
  const unsigned __int16 ***v5; // rsi
  const wchar_t **v6; // rax
  const wchar_t *v7; // rcx
  __int64 v8; // rdi
  const unsigned __int16 **v9; // rax
  const unsigned __int16 *v10; // r8
  int v11; // r14d
  __int64 v12; // rax
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r8
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  unsigned __int16 *v18; // rax
  signed int LastError; // eax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Src[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp+150h] BYREF

  ppv = 0;
  v4 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv);
  if ( v4 < 0 )
  {
LABEL_56:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v5 = (const unsigned __int16 ***)((char *)this + 48);
  v6 = (const wchar_t **)*((_QWORD *)this + 6);
  if ( v6 )
    v7 = *v6;
  else
    v7 = 0;
  v8 = -1;
  if ( wcsrchr(v7, 0x5Cu) || !_bstr_t::length((ExeTask *)((char *)this + 64)) )
  {
    if ( *v5 )
      v14 = **v5;
    else
      v14 = 0;
    v11 = StringCchCopyW(Src, 0x105u, v14);
    if ( v11 < 0 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v11;
    }
  }
  else
  {
    v9 = (const unsigned __int16 **)*((_QWORD *)this + 8);
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    v11 = StringCchCopyW(Src, 0x105u, v10);
    if ( v11 < 0 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v11;
    }
    v12 = -1;
    do
      ++v12;
    while ( Src[v12] );
    if ( Src[v12] != 92 )
    {
      v11 = StringCchCatW(Src, 0x105u, L"\\");
      if ( v11 < 0 )
      {
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return (unsigned int)v11;
      }
    }
    if ( *v5 )
      v13 = **v5;
    else
      v13 = 0;
    v11 = StringCchCatW(Src, 0x105u, v13);
    if ( v11 < 0 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v11;
    }
  }
  if ( ExpandEnvironmentStringsW(Src, Dst, 0x105u) - 1 > 0x104 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v21 = 0;
  v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistFile, &v21);
  if ( v4 < 0 )
    goto LABEL_54;
  v4 = (*(__int64 (__fastcall **)(__int64, WCHAR *, _QWORD))(*(_QWORD *)v21 + 40LL))(v21, Dst, 0);
  if ( v4 < 0 )
    goto LABEL_54;
  v4 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, _QWORD, _DWORD))(*(_QWORD *)ppv + 24LL))(
         ppv,
         Src,
         260,
         0,
         0);
  if ( v4 < 0 )
    goto LABEL_54;
  v16 = -1;
  do
    ++v16;
  while ( Src[v16] );
  if ( !v16 )
  {
    v4 = -2147418113;
    goto LABEL_54;
  }
  _bstr_t::operator=(v5, Src);
  v17 = *v5 ? **v5 : 0LL;
  v18 = wcsrchr(v17, 0x2Eu);
  *a2 = v18;
  if ( v18 )
  {
    do
      ++v8;
    while ( v18[v8] );
    if ( v8 != 1 )
    {
LABEL_54:
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      goto LABEL_56;
    }
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v21 = 0;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 1;
}

```

## disassembly

```asm
0x18005f4a4  mov     [rsp-8+arg_10], rbx
0x18005f4a9  push    rbp
0x18005f4aa  push    rsi
0x18005f4ab  push    rdi
0x18005f4ac  push    r12
0x18005f4ae  push    r13
0x18005f4b0  push    r14
0x18005f4b2  push    r15
0x18005f4b4  lea     rbp, [rsp-370h]
0x18005f4bc  sub     rsp, 470h
0x18005f4c3  mov     rax, cs:__security_cookie
0x18005f4ca  xor     rax, rsp
0x18005f4cd  mov     [rbp+3A0h+var_40], rax
0x18005f4d4  mov     r15, rdx
0x18005f4d7  mov     r14, rcx
0x18005f4da  xor     r12d, r12d
0x18005f4dd  mov     [rsp+4A0h+var_470], r12
0x18005f4e2  lea     rax, [rsp+4A0h+var_470]
0x18005f4e7  mov     [rsp+4A0h+ppv], rax; ppv
0x18005f4ec  lea     r9, IID_IShellLinkW; riid
0x18005f4f3  xor     edx, edx; pUnkOuter
0x18005f4f5  lea     r8d, [r12+1]; dwClsContext
0x18005f4fa  lea     rcx, CLSID_ShellLink; rclsid
0x18005f501  call    cs:__imp_CoCreateInstance
0x18005f507  mov     ebx, eax
0x18005f509  test    eax, eax
0x18005f50b  js      loc_18005F7B6
0x18005f511  lea     rsi, [r14+30h]
0x18005f515  mov     rax, [rsi]
0x18005f518  test    rax, rax
0x18005f51b  jz      short loc_18005F522
0x18005f51d  mov     rcx, [rax]
0x18005f520  jmp     short loc_18005F525
0x18005f522  mov     rcx, r12; Str
0x18005f525  mov     r13d, 5Ch ; '\'
0x18005f52b  mov     edx, r13d; Ch
0x18005f52e  call    cs:__imp_wcsrchr
0x18005f534  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005f538  test    rax, rax
0x18005f53b  jnz     loc_18005F622
0x18005f541  lea     rcx, [r14+40h]; this
0x18005f545  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18005f54a  test    eax, eax
0x18005f54c  jz      loc_18005F622
0x18005f552  mov     rax, [r14+40h]
0x18005f556  test    rax, rax
0x18005f559  jz      short loc_18005F560
0x18005f55b  mov     r8, [rax]
0x18005f55e  jmp     short loc_18005F563
0x18005f560  mov     r8, r12; unsigned __int16 *
0x18005f563  mov     ebx, 105h
0x18005f568  mov     edx, ebx; unsigned __int64
0x18005f56a  lea     rcx, [rsp+4A0h+Src]; unsigned __int16 *
0x18005f56f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005f574  mov     r14d, eax
0x18005f577  test    eax, eax
0x18005f579  jns     short loc_18005F597
0x18005f57b  mov     rcx, [rsp+4A0h+var_470]
0x18005f580  test    rcx, rcx
0x18005f583  jz      short loc_18005F592
0x18005f585  mov     rax, [rcx]
0x18005f588  mov     rax, [rax+10h]
0x18005f58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f591  nop
0x18005f592  jmp     loc_18005F661
0x18005f597  lea     rcx, [rsp+4A0h+Src]
0x18005f59c  mov     rax, rdi
0x18005f59f  inc     rax
0x18005f5a2  cmp     [rcx+rax*2], r12w
0x18005f5a7  jnz     short loc_18005F59F
0x18005f5a9  cmp     [rsp+rax*2+4A0h+Src], r13w
0x18005f5af  jz      short loc_18005F5E5
0x18005f5b1  lea     r8, asc_1800A3DA8; "\\"
0x18005f5b8  mov     rdx, rbx; unsigned __int64
0x18005f5bb  lea     rcx, [rsp+4A0h+Src]; unsigned __int16 *
0x18005f5c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005f5c5  mov     r14d, eax
0x18005f5c8  test    eax, eax
0x18005f5ca  jns     short loc_18005F5E5
0x18005f5cc  mov     rcx, [rsp+4A0h+var_470]
0x18005f5d1  test    rcx, rcx
0x18005f5d4  jz      short loc_18005F5E3
0x18005f5d6  mov     rax, [rcx]
0x18005f5d9  mov     rax, [rax+10h]
0x18005f5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f5e2  nop
0x18005f5e3  jmp     short loc_18005F661
0x18005f5e5  mov     rax, [rsi]
0x18005f5e8  test    rax, rax
0x18005f5eb  jz      short loc_18005F5F2
0x18005f5ed  mov     r8, [rax]
0x18005f5f0  jmp     short loc_18005F5F5
0x18005f5f2  mov     r8, r12; unsigned __int16 *
0x18005f5f5  mov     rdx, rbx; unsigned __int64
0x18005f5f8  lea     rcx, [rsp+4A0h+Src]; unsigned __int16 *
0x18005f5fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005f602  mov     r14d, eax
0x18005f605  test    eax, eax
0x18005f607  jns     short loc_18005F669
0x18005f609  mov     rcx, [rsp+4A0h+var_470]
0x18005f60e  test    rcx, rcx
0x18005f611  jz      short loc_18005F620
0x18005f613  mov     rax, [rcx]
0x18005f616  mov     rax, [rax+10h]
0x18005f61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f61f  nop
0x18005f620  jmp     short loc_18005F661
0x18005f622  mov     rax, [rsi]
0x18005f625  test    rax, rax
0x18005f628  jz      short loc_18005F62F
0x18005f62a  mov     r8, [rax]
0x18005f62d  jmp     short loc_18005F632
0x18005f62f  mov     r8, r12; unsigned __int16 *
0x18005f632  mov     ebx, 105h
0x18005f637  mov     edx, ebx; unsigned __int64
0x18005f639  lea     rcx, [rsp+4A0h+Src]; unsigned __int16 *
0x18005f63e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005f643  mov     r14d, eax
0x18005f646  test    eax, eax
0x18005f648  jns     short loc_18005F669
0x18005f64a  mov     rcx, [rsp+4A0h+var_470]
0x18005f64f  test    rcx, rcx
0x18005f652  jz      short loc_18005F661
0x18005f654  mov     rax, [rcx]
0x18005f657  mov     rax, [rax+10h]
0x18005f65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f660  nop
0x18005f661  mov     eax, r14d
0x18005f664  jmp     loc_18005F7CF
0x18005f669  mov     r8d, ebx; nSize
0x18005f66c  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x18005f673  lea     rcx, [rsp+4A0h+Src]; lpSrc
0x18005f678  call    cs:__imp_ExpandEnvironmentStringsW
0x18005f67e  dec     eax
0x18005f680  mov     r14d, 104h
0x18005f686  cmp     eax, r14d
0x18005f689  ja      loc_18005F7F9
0x18005f68f  mov     [rsp+4A0h+var_468], r12
0x18005f694  mov     rcx, [rsp+4A0h+var_470]
0x18005f699  mov     rax, [rcx]
0x18005f69c  lea     r8, [rsp+4A0h+var_468]
0x18005f6a1  lea     rdx, IID_IPersistFile
0x18005f6a8  mov     rax, [rax]
0x18005f6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f6b0  mov     ebx, eax
0x18005f6b2  test    eax, eax
0x18005f6b4  js      loc_18005F79F
0x18005f6ba  mov     rcx, [rsp+4A0h+var_468]
0x18005f6bf  mov     rax, [rcx]
0x18005f6c2  xor     r8d, r8d
0x18005f6c5  lea     rdx, [rbp+3A0h+Dst]
0x18005f6cc  mov     rax, [rax+28h]
0x18005f6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f6d5  mov     ebx, eax
0x18005f6d7  test    eax, eax
0x18005f6d9  js      loc_18005F79F
0x18005f6df  mov     rcx, [rsp+4A0h+var_470]
0x18005f6e4  mov     rax, [rcx]
0x18005f6e7  mov     dword ptr [rsp+4A0h+ppv], r12d
0x18005f6ec  xor     r9d, r9d
0x18005f6ef  mov     r8d, r14d
0x18005f6f2  lea     rdx, [rsp+4A0h+Src]
0x18005f6f7  mov     rax, [rax+18h]
0x18005f6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f700  mov     ebx, eax
0x18005f702  test    eax, eax
0x18005f704  js      loc_18005F79F
0x18005f70a  lea     rcx, [rsp+4A0h+Src]
0x18005f70f  mov     rax, rdi
0x18005f712  inc     rax
0x18005f715  cmp     [rcx+rax*2], r12w
0x18005f71a  jnz     short loc_18005F712
0x18005f71c  test    rax, rax
0x18005f71f  jz      short loc_18005F79A
0x18005f721  lea     rdx, [rsp+4A0h+Src]
0x18005f726  mov     rcx, rsi
0x18005f729  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18005f72e  mov     rcx, [rsi]
0x18005f731  test    rcx, rcx
0x18005f734  jz      short loc_18005F73B
0x18005f736  mov     rcx, [rcx]
0x18005f739  jmp     short loc_18005F73E
0x18005f73b  mov     rcx, r12; Str
0x18005f73e  mov     edx, 2Eh ; '.'; Ch
0x18005f743  call    cs:__imp_wcsrchr
0x18005f749  mov     [r15], rax
0x18005f74c  test    rax, rax
0x18005f74f  jz      short loc_18005F761
0x18005f751  inc     rdi
0x18005f754  cmp     [rax+rdi*2], r12w
0x18005f759  jnz     short loc_18005F751
0x18005f75b  cmp     rdi, 1
0x18005f75f  jnz     short loc_18005F79F
0x18005f761  mov     rcx, [rsp+4A0h+var_468]
0x18005f766  test    rcx, rcx
0x18005f769  jz      short loc_18005F777
0x18005f76b  mov     rax, [rcx]
0x18005f76e  mov     rax, [rax+10h]
0x18005f772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f777  mov     [rsp+4A0h+var_468], r12
0x18005f77c  mov     rcx, [rsp+4A0h+var_470]
0x18005f781  test    rcx, rcx
0x18005f784  jz      short loc_18005F793
0x18005f786  mov     rdx, [rcx]
0x18005f789  mov     rax, [rdx+10h]
0x18005f78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f792  nop
0x18005f793  mov     eax, 1
0x18005f798  jmp     short loc_18005F7CF
0x18005f79a  mov     ebx, 8000FFFFh
0x18005f79f  mov     rcx, [rsp+4A0h+var_468]
0x18005f7a4  test    rcx, rcx
0x18005f7a7  jz      short loc_18005F7B6
0x18005f7a9  mov     rax, [rcx]
0x18005f7ac  mov     rax, [rax+10h]
0x18005f7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f7b5  nop
0x18005f7b6  mov     rcx, [rsp+4A0h+var_470]
0x18005f7bb  test    rcx, rcx
0x18005f7be  jz      short loc_18005F7CD
0x18005f7c0  mov     rax, [rcx]
0x18005f7c3  mov     rax, [rax+10h]
0x18005f7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f7cc  nop
0x18005f7cd  mov     eax, ebx
0x18005f7cf  mov     rcx, [rbp+3A0h+var_40]
0x18005f7d6  xor     rcx, rsp; StackCookie
0x18005f7d9  call    __security_check_cookie
0x18005f7de  mov     rbx, [rsp+4A0h+arg_10]
0x18005f7e6  add     rsp, 470h
0x18005f7ed  pop     r15
0x18005f7ef  pop     r14
0x18005f7f1  pop     r13
0x18005f7f3  pop     r12
0x18005f7f5  pop     rdi
0x18005f7f6  pop     rsi
0x18005f7f7  pop     rbp
0x18005f7f8  retn
0x18005f7f9  call    cs:__imp_GetLastError
0x18005f7ff  nop
0x18005f800  mov     ebx, eax
0x18005f802  test    eax, eax
0x18005f804  jle     short loc_18005F80F
0x18005f806  movzx   ebx, ax
0x18005f809  or      ebx, 80070000h
0x18005f80f  mov     rcx, [rsp+4A0h+var_470]
0x18005f814  test    rcx, rcx
0x18005f817  jz      short loc_18005F826
0x18005f819  mov     rdx, [rcx]
0x18005f81c  mov     rax, [rdx+10h]
0x18005f820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f825  nop
0x18005f826  jmp     short loc_18005F7CD
```
