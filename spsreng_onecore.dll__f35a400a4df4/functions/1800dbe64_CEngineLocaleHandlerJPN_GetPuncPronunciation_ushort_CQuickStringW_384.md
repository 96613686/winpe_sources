# CEngineLocaleHandlerJPN::GetPuncPronunciation(ushort *,CQuickStringW<384> *)

- ea: `0x1800dbe64`
- end: `0x1800dbfad`
- name: `?GetPuncPronunciation@CEngineLocaleHandlerJPN@@QEAAJPEAGPEAV?$CQuickStringW@$0BIA@@@@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800df780`

## callees

- `0x1800034b0`
- `0x1800765d0`
- `0x1800c91c4`
- `0x1800dbe64`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbf82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbf82`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandlerJPN::GetPuncPronunciation(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  LPVOID pv[2]; // [rsp+30h] [rbp-1B68h] BYREF
  __int64 v13; // [rsp+40h] [rbp-1B58h]
  _BYTE v14[784]; // [rsp+50h] [rbp-1B48h] BYREF
  _BYTE v15[6160]; // [rsp+360h] [rbp-1838h] BYREF

  *(_OWORD *)pv = 0;
  v13 = 0;
  v6 = CEngineLocaleHandler::EnsureLookupLexicon((CEngineLocaleHandler *)a1);
  if ( v6 >= 0 )
  {
    v7 = *(_QWORD *)(a1 + 72);
    v8 = *(unsigned __int16 *)(a1 + 40);
    v13 = 0;
    *(_OWORD *)pv = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, LPVOID *))(*(_QWORD *)v7 + 24LL))(
           v7,
           a2,
           v8,
           4096,
           pv);
    if ( v6 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 368LL))(a1, 4096);
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v9 + 48LL))(v9, v13 + 20, v15);
      if ( v6 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 368LL))(a1, 1);
        v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))(*(_QWORD *)v10 + 40LL))(v10, v15, v14);
        if ( v6 >= 0 )
          v6 = CQuickStringW<384>::Append(a3, v14);
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
0x1800dbe64  mov     [rsp+arg_18], rbx
0x1800dbe69  push    rbp
0x1800dbe6a  push    rsi
0x1800dbe6b  push    rdi
0x1800dbe6c  mov     eax, 1B80h
0x1800dbe71  call    _alloca_probe
0x1800dbe76  sub     rsp, rax
0x1800dbe79  mov     rax, cs:__security_cookie
0x1800dbe80  xor     rax, rsp
0x1800dbe83  mov     [rsp+1B98h+var_28], rax
0x1800dbe8b  xorps   xmm0, xmm0
0x1800dbe8e  xor     eax, eax
0x1800dbe90  movups  xmmword ptr [rsp+1B98h+pv], xmm0
0x1800dbe95  mov     [rsp+1B98h+var_1B58], rax
0x1800dbe9a  mov     rsi, r8
0x1800dbe9d  mov     rbp, rdx
0x1800dbea0  mov     rdi, rcx
0x1800dbea3  call    ?EnsureLookupLexicon@CEngineLocaleHandler@@IEAAJXZ; CEngineLocaleHandler::EnsureLookupLexicon(void)
0x1800dbea8  mov     ebx, eax
0x1800dbeaa  test    eax, eax
0x1800dbeac  js      loc_1800DBF88
0x1800dbeb2  mov     rcx, [rdi+48h]
0x1800dbeb6  lea     rdx, [rsp+1B98h+pv]
0x1800dbebb  movzx   r8d, word ptr [rdi+28h]
0x1800dbec0  xor     eax, eax
0x1800dbec2  mov     [rsp+1B98h+var_1B58], rax
0x1800dbec7  xorps   xmm0, xmm0
0x1800dbeca  movups  xmmword ptr [rsp+1B98h+pv], xmm0
0x1800dbecf  mov     rax, [rcx]
0x1800dbed2  mov     r9d, 1000h
0x1800dbed8  mov     [rsp+1B98h+var_1B78], rdx
0x1800dbedd  mov     rdx, rbp
0x1800dbee0  mov     rax, [rax+18h]
0x1800dbee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbee9  mov     ebx, eax
0x1800dbeeb  test    eax, eax
0x1800dbeed  js      loc_1800DBF78
0x1800dbef3  mov     rax, [rdi]
0x1800dbef6  mov     edx, 1000h
0x1800dbefb  mov     rcx, rdi
0x1800dbefe  mov     rax, [rax+170h]
0x1800dbf05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf0a  mov     rdx, [rsp+1B98h+var_1B58]
0x1800dbf0f  mov     rcx, rax
0x1800dbf12  add     rdx, 14h
0x1800dbf16  mov     r8, [rax]
0x1800dbf19  mov     rax, [r8+30h]
0x1800dbf1d  lea     r8, [rsp+1B98h+var_1838]
0x1800dbf25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf2a  mov     ebx, eax
0x1800dbf2c  test    eax, eax
0x1800dbf2e  js      short loc_1800DBF78
0x1800dbf30  mov     rax, [rdi]
0x1800dbf33  mov     edx, 1
0x1800dbf38  mov     rcx, rdi
0x1800dbf3b  mov     rax, [rax+170h]
0x1800dbf42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf47  mov     rcx, rax
0x1800dbf4a  lea     r8, [rsp+1B98h+var_1B48]
0x1800dbf4f  mov     rdx, [rax]
0x1800dbf52  mov     rax, [rdx+28h]
0x1800dbf56  lea     rdx, [rsp+1B98h+var_1838]
0x1800dbf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf63  mov     ebx, eax
0x1800dbf65  test    eax, eax
0x1800dbf67  js      short loc_1800DBF78
0x1800dbf69  lea     rdx, [rsp+1B98h+var_1B48]
0x1800dbf6e  mov     rcx, rsi
0x1800dbf71  call    ?Append@?$CQuickStringW@$0BIA@@@QEAAJQEBG@Z; CQuickStringW<384>::Append(ushort const * const)
0x1800dbf76  mov     ebx, eax
0x1800dbf78  mov     rcx, [rsp+1B98h+pv+8]; pv
0x1800dbf7d  test    rcx, rcx
0x1800dbf80  jz      short loc_1800DBF88
0x1800dbf82  call    cs:__imp_CoTaskMemFree
0x1800dbf88  mov     eax, ebx
0x1800dbf8a  mov     rcx, [rsp+1B98h+var_28]
0x1800dbf92  xor     rcx, rsp; StackCookie
0x1800dbf95  call    __security_check_cookie
0x1800dbf9a  mov     rbx, [rsp+1B98h+arg_18]
0x1800dbfa2  add     rsp, 1B80h
0x1800dbfa9  pop     rdi
0x1800dbfaa  pop     rsi
0x1800dbfab  pop     rbp
0x1800dbfac  retn
```
