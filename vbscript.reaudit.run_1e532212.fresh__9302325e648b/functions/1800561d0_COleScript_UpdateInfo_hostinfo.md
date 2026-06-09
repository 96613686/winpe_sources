# COleScript::UpdateInfo(hostinfo)

- ea: `0x1800561d0`
- end: `0x1800562e9`
- name: `?UpdateInfo@COleScript@@UEAAJW4hostinfo@@@Z`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x18003cbbc`
- `0x1800561d0`
- `0x180077010`

## import_xrefs

- `KERNEL32!IsValidCodePage` at `0x180056277`
- `KERNEL32!IsValidCodePage` at `0x180056277`
- `OLE32!CoTaskMemFree` at `0x1800562cf`
- `OLE32!CoTaskMemFree` at `0x1800562cf`

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
  if ( (**v3)(v3, qword_18007F200, &v12) < 0 )
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
0x1800561d0  mov     [rsp+arg_8], rbx
0x1800561d5  push    rbp
0x1800561d6  push    rsi
0x1800561d7  push    rdi
0x1800561d8  sub     rsp, 20h
0x1800561dc  mov     rdi, rcx
0x1800561df  mov     [rsp+38h+arg_10], 0
0x1800561e8  mov     rcx, [rcx+58h]
0x1800561ec  mov     ebx, edx
0x1800561ee  mov     [rsp+38h+pv], 0
0x1800561f7  test    rcx, rcx
0x1800561fa  jnz     short loc_180056206
0x1800561fc  mov     eax, 8000FFFFh
0x180056201  jmp     loc_1800562DC
0x180056206  mov     rax, [rcx]
0x180056209  lea     r8, [rsp+38h+arg_10]
0x18005620e  lea     rdx, qword_18007F200
0x180056215  mov     rax, [rax]
0x180056218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005621d  test    eax, eax
0x18005621f  jns     short loc_18005622B
0x180056221  mov     eax, 80004005h
0x180056226  jmp     loc_1800562DC
0x18005622b  mov     rcx, [rsp+38h+arg_10]
0x180056230  lea     r8, [rsp+38h+pv]
0x180056235  mov     edx, ebx
0x180056237  mov     rax, [rcx]
0x18005623a  mov     rax, [rax+18h]
0x18005623e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056243  mov     rcx, [rsp+38h+arg_10]
0x180056248  mov     ebp, eax
0x18005624a  mov     rdx, [rcx]
0x18005624d  mov     rax, [rdx+10h]
0x180056251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056256  test    ebp, ebp
0x180056258  jns     short loc_18005625E
0x18005625a  mov     eax, ebp
0x18005625c  jmp     short loc_1800562DC
0x18005625e  test    ebx, ebx
0x180056260  jz      short loc_1800562A4
0x180056262  cmp     ebx, 1
0x180056265  jz      short loc_18005626E
0x180056267  mov     ebx, 8000FFFFh
0x18005626c  jmp     short loc_1800562CA
0x18005626e  mov     rax, [rsp+38h+pv]
0x180056273  mov     ebx, [rax]
0x180056275  mov     ecx, ebx; CodePage
0x180056277  call    cs:__imp_IsValidCodePage
0x18005627d  test    eax, eax
0x18005627f  jnz     short loc_180056285
0x180056281  xor     ecx, ecx
0x180056283  jmp     short loc_180056296
0x180056285  mov     ecx, 1
0x18005628a  mov     [rdi+0A4h], ebx
0x180056290  mov     [rdi+0A0h], ecx
0x180056296  xor     eax, eax
0x180056298  mov     ebx, 80070057h
0x18005629d  test    ecx, ecx
0x18005629f  cmovnz  ebx, eax
0x1800562a2  jmp     short loc_1800562CA
0x1800562a4  mov     rdx, [rsp+38h+pv]
0x1800562a9  lea     rcx, [rdi-48h]; this
0x1800562ad  mov     edx, [rdx]; unsigned int
0x1800562af  call    ?SetCurrentLocale@COleScript@@QEAAHK@Z; COleScript::SetCurrentLocale(ulong)
0x1800562b4  test    eax, eax
0x1800562b6  jnz     short loc_1800562BF
0x1800562b8  mov     ebx, 80070057h
0x1800562bd  jmp     short loc_1800562CA
0x1800562bf  mov     eax, [rdi+70h]
0x1800562c2  xor     ebx, ebx
0x1800562c4  mov     [rdi+78h], eax
0x1800562c7  mov     [rdi+7Ch], eax
0x1800562ca  mov     rcx, [rsp+38h+pv]; pv
0x1800562cf  call    cs:__imp_CoTaskMemFree
0x1800562d5  xor     eax, eax
0x1800562d7  test    ebx, ebx
0x1800562d9  cmovs   eax, ebx
0x1800562dc  mov     rbx, [rsp+38h+arg_8]
0x1800562e1  add     rsp, 20h
0x1800562e5  pop     rdi
0x1800562e6  pop     rsi
0x1800562e7  pop     rbp
0x1800562e8  retn
```
