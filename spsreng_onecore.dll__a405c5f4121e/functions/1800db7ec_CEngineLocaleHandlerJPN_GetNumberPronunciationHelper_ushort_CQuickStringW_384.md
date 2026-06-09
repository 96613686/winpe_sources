# CEngineLocaleHandlerJPN::GetNumberPronunciationHelper(ushort *,CQuickStringW<384> *)

- ea: `0x1800db7ec`
- end: `0x1800db94f`
- name: `?GetNumberPronunciationHelper@CEngineLocaleHandlerJPN@@QEAAJPEAGPEAV?$CQuickStringW@$0BIA@@@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800db6a4`

## callees

- `0x1800034b0`
- `0x1800060c0`
- `0x1800765d0`
- `0x1800c91c4`
- `0x1800db7ec`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db92a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db92a`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandlerJPN::GetNumberPronunciationHelper(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v14[12]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[784]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[6160]; // [rsp+370h] [rbp+270h] BYREF

  *(_OWORD *)pv = 0;
  v13 = 0;
  v6 = CEngineLocaleHandler::EnsureLookupLexicon((CEngineLocaleHandler *)a1);
  if ( v6 >= 0 )
  {
    StringCchPrintfW(v14, 0xAu, L"/%s;", a2);
    v7 = *(_QWORD *)(a1 + 72);
    v8 = *(unsigned __int16 *)(a1 + 40);
    v13 = 0;
    *(_OWORD *)pv = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64, __int64, LPVOID *))(*(_QWORD *)v7 + 24LL))(
           v7,
           v14,
           v8,
           4096,
           pv);
    if ( v6 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 368LL))(a1, 4096);
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v9 + 48LL))(v9, v13 + 20, v16);
      if ( v6 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 368LL))(a1, 1);
        v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))(*(_QWORD *)v10 + 40LL))(v10, v16, v15);
        if ( v6 >= 0 )
          v6 = CQuickStringW<384>::Append(a3, v15);
      }
    }
    if ( pv[1] )
      CoTaskMemFree(pv[1]);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800db7ec  push    rbp
0x1800db7ee  push    rbx
0x1800db7ef  push    rsi
0x1800db7f0  push    rdi
0x1800db7f1  push    r14
0x1800db7f3  lea     rbp, [rsp-1A90h]
0x1800db7fb  mov     eax, 1B90h
0x1800db800  call    _alloca_probe
0x1800db805  sub     rsp, rax
0x1800db808  mov     rax, cs:__security_cookie
0x1800db80f  xor     rax, rsp
0x1800db812  mov     [rbp+1AB0h+var_30], rax
0x1800db819  xorps   xmm0, xmm0
0x1800db81c  xor     eax, eax
0x1800db81e  movups  xmmword ptr [rsp+1BB0h+pv], xmm0
0x1800db823  mov     [rsp+1BB0h+var_1B70], rax
0x1800db828  mov     rsi, r8
0x1800db82b  mov     r14, rdx
0x1800db82e  mov     rdi, rcx
0x1800db831  call    ?EnsureLookupLexicon@CEngineLocaleHandler@@IEAAJXZ; CEngineLocaleHandler::EnsureLookupLexicon(void)
0x1800db836  mov     ebx, eax
0x1800db838  test    eax, eax
0x1800db83a  js      loc_1800DB930
0x1800db840  mov     r9, r14
0x1800db843  lea     r8, aS; "/%s;"
0x1800db84a  mov     edx, 0Ah; unsigned __int64
0x1800db84f  lea     rcx, [rsp+1BB0h+var_1B68]; unsigned __int16 *
0x1800db854  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800db859  mov     rcx, [rdi+48h]
0x1800db85d  lea     rdx, [rsp+1BB0h+pv]
0x1800db862  movzx   r8d, word ptr [rdi+28h]
0x1800db867  xor     eax, eax
0x1800db869  mov     [rsp+1BB0h+var_1B70], rax
0x1800db86e  xorps   xmm0, xmm0
0x1800db871  movups  xmmword ptr [rsp+1BB0h+pv], xmm0
0x1800db876  mov     rax, [rcx]
0x1800db879  mov     r14d, 1000h
0x1800db87f  mov     [rsp+1BB0h+var_1B90], rdx
0x1800db884  mov     r9d, r14d
0x1800db887  lea     rdx, [rsp+1BB0h+var_1B68]
0x1800db88c  mov     rax, [rax+18h]
0x1800db890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db895  mov     ebx, eax
0x1800db897  test    eax, eax
0x1800db899  js      loc_1800DB920
0x1800db89f  mov     rax, [rdi]
0x1800db8a2  mov     edx, r14d
0x1800db8a5  mov     rcx, rdi
0x1800db8a8  mov     rax, [rax+170h]
0x1800db8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db8b4  mov     rdx, [rsp+1BB0h+var_1B70]
0x1800db8b9  mov     rcx, rax
0x1800db8bc  add     rdx, 14h
0x1800db8c0  mov     r8, [rax]
0x1800db8c3  mov     rax, [r8+30h]
0x1800db8c7  lea     r8, [rbp+1AB0h+var_1840]
0x1800db8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db8d3  mov     ebx, eax
0x1800db8d5  test    eax, eax
0x1800db8d7  js      short loc_1800DB920
0x1800db8d9  mov     rax, [rdi]
0x1800db8dc  mov     edx, 1
0x1800db8e1  mov     rcx, rdi
0x1800db8e4  mov     rax, [rax+170h]
0x1800db8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db8f0  mov     rcx, rax
0x1800db8f3  lea     r8, [rsp+1BB0h+var_1B50]
0x1800db8f8  mov     rdx, [rax]
0x1800db8fb  mov     rax, [rdx+28h]
0x1800db8ff  lea     rdx, [rbp+1AB0h+var_1840]
0x1800db906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db90b  mov     ebx, eax
0x1800db90d  test    eax, eax
0x1800db90f  js      short loc_1800DB920
0x1800db911  lea     rdx, [rsp+1BB0h+var_1B50]
0x1800db916  mov     rcx, rsi
0x1800db919  call    ?Append@?$CQuickStringW@$0BIA@@@QEAAJQEBG@Z; CQuickStringW<384>::Append(ushort const * const)
0x1800db91e  mov     ebx, eax
0x1800db920  mov     rcx, [rsp+1BB0h+pv+8]; pv
0x1800db925  test    rcx, rcx
0x1800db928  jz      short loc_1800DB930
0x1800db92a  call    cs:__imp_CoTaskMemFree
0x1800db930  mov     eax, ebx
0x1800db932  mov     rcx, [rbp+1AB0h+var_30]
0x1800db939  xor     rcx, rsp; StackCookie
0x1800db93c  call    __security_check_cookie
0x1800db941  add     rsp, 1B90h
0x1800db948  pop     r14
0x1800db94a  pop     rdi
0x1800db94b  pop     rsi
0x1800db94c  pop     rbx
0x1800db94d  pop     rbp
0x1800db94e  retn
```
