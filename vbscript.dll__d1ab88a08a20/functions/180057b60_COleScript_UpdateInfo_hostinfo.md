# COleScript::UpdateInfo(hostinfo)

- ea: `0x180057b60`
- end: `0x180057c89`
- name: `?UpdateInfo@COleScript@@UEAAJW4hostinfo@@@Z`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18003e094`
- `0x180057b60`
- `0x18007a010`

## import_xrefs

- `KERNEL32!IsValidCodePage` at `0x180057c0a`
- `KERNEL32!IsValidCodePage` at `0x180057c0a`
- `OLE32!CoTaskMemFree` at `0x180057c68`
- `OLE32!CoTaskMemFree` at `0x180057c68`

## pseudocode

```c
__int64 __fastcall COleScript::UpdateInfo(__int64 a1, unsigned int a2)
{
  int (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 result; // rax
  int v6; // ebp
  int v7; // ebx
  UINT v8; // ebx
  int v9; // ecx
  int v10; // eax
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = 0;
  v3 = *(int (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 88);
  pv = 0;
  if ( !v3 )
    return 2147549183LL;
  if ( (**v3)(v3, qword_180082840, &v12) < 0 )
    return 2147500037LL;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v12 + 24LL))(v12, a2, &pv);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v6 < 0 )
    return (unsigned int)v6;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v8 = *(_DWORD *)pv;
      if ( IsValidCodePage(*(_DWORD *)pv) )
      {
        v9 = 1;
        *(_DWORD *)(a1 + 164) = v8;
        *(_DWORD *)(a1 + 160) = 1;
      }
      else
      {
        v9 = 0;
      }
      v7 = -2147024809;
      if ( v9 )
        v7 = 0;
    }
    else
    {
      v7 = -2147418113;
    }
  }
  else if ( COleScript::SetCurrentLocale((COleScript *)(a1 - 72), *(_DWORD *)pv) )
  {
    v10 = *(_DWORD *)(a1 + 112);
    v7 = 0;
    *(_DWORD *)(a1 + 120) = v10;
    *(_DWORD *)(a1 + 124) = v10;
  }
  else
  {
    v7 = -2147024809;
  }
  CoTaskMemFree(pv);
  result = 0;
  if ( v7 < 0 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x180057b60  mov     [rsp+arg_8], rbx
0x180057b65  push    rbp
0x180057b66  push    rsi
0x180057b67  push    rdi
0x180057b68  sub     rsp, 20h
0x180057b6c  mov     rdi, rcx
0x180057b6f  mov     [rsp+38h+arg_10], 0
0x180057b78  mov     rcx, [rcx+58h]
0x180057b7c  mov     ebx, edx
0x180057b7e  mov     [rsp+38h+pv], 0
0x180057b87  test    rcx, rcx
0x180057b8a  jnz     short loc_180057B96
0x180057b8c  mov     eax, 8000FFFFh
0x180057b91  jmp     loc_180057C7B
0x180057b96  mov     rax, [rcx]
0x180057b99  lea     r8, [rsp+38h+arg_10]
0x180057b9e  lea     rdx, qword_180082840
0x180057ba5  mov     rax, [rax]
0x180057ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bad  test    eax, eax
0x180057baf  jns     short loc_180057BBB
0x180057bb1  mov     eax, 80004005h
0x180057bb6  jmp     loc_180057C7B
0x180057bbb  mov     rcx, [rsp+38h+arg_10]
0x180057bc0  lea     r8, [rsp+38h+pv]
0x180057bc5  mov     edx, ebx
0x180057bc7  mov     rax, [rcx]
0x180057bca  mov     rax, [rax+18h]
0x180057bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bd3  mov     rcx, [rsp+38h+arg_10]
0x180057bd8  mov     ebp, eax
0x180057bda  mov     rdx, [rcx]
0x180057bdd  mov     rax, [rdx+10h]
0x180057be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057be6  test    ebp, ebp
0x180057be8  jns     short loc_180057BF1
0x180057bea  mov     eax, ebp
0x180057bec  jmp     loc_180057C7B
0x180057bf1  test    ebx, ebx
0x180057bf3  jz      short loc_180057C3D
0x180057bf5  cmp     ebx, 1
0x180057bf8  jz      short loc_180057C01
0x180057bfa  mov     ebx, 8000FFFFh
0x180057bff  jmp     short loc_180057C63
0x180057c01  mov     rax, [rsp+38h+pv]
0x180057c06  mov     ebx, [rax]
0x180057c08  mov     ecx, ebx; CodePage
0x180057c0a  call    cs:__imp_IsValidCodePage
0x180057c11  nop     dword ptr [rax+rax+00h]
0x180057c16  test    eax, eax
0x180057c18  jnz     short loc_180057C1E
0x180057c1a  xor     ecx, ecx
0x180057c1c  jmp     short loc_180057C2F
0x180057c1e  mov     ecx, 1
0x180057c23  mov     [rdi+0A4h], ebx
0x180057c29  mov     [rdi+0A0h], ecx
0x180057c2f  xor     eax, eax
0x180057c31  mov     ebx, 80070057h
0x180057c36  test    ecx, ecx
0x180057c38  cmovnz  ebx, eax
0x180057c3b  jmp     short loc_180057C63
0x180057c3d  mov     rdx, [rsp+38h+pv]
0x180057c42  lea     rcx, [rdi-48h]; this
0x180057c46  mov     edx, [rdx]; unsigned int
0x180057c48  call    ?SetCurrentLocale@COleScript@@QEAAHK@Z; COleScript::SetCurrentLocale(ulong)
0x180057c4d  test    eax, eax
0x180057c4f  jnz     short loc_180057C58
0x180057c51  mov     ebx, 80070057h
0x180057c56  jmp     short loc_180057C63
0x180057c58  mov     eax, [rdi+70h]
0x180057c5b  xor     ebx, ebx
0x180057c5d  mov     [rdi+78h], eax
0x180057c60  mov     [rdi+7Ch], eax
0x180057c63  mov     rcx, [rsp+38h+pv]; pv
0x180057c68  call    cs:__imp_CoTaskMemFree
0x180057c6f  nop     dword ptr [rax+rax+00h]
0x180057c74  xor     eax, eax
0x180057c76  test    ebx, ebx
0x180057c78  cmovs   eax, ebx
0x180057c7b  mov     rbx, [rsp+38h+arg_8]
0x180057c80  add     rsp, 20h
0x180057c84  pop     rdi
0x180057c85  pop     rsi
0x180057c86  pop     rbp
0x180057c87  retn
```
