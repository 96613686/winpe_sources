# CWTPage::CanNavigateChildPage(_GUID *)

- ea: `0x18002b920`
- end: `0x18002ba3d`
- name: `?CanNavigateChildPage@CWTPage@@UEAAJPEAU_GUID@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CWTPage *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18002b920`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b972`

## pseudocode

```c
__int64 __fastcall CWTPage::CanNavigateChildPage(CWTPage *this, struct _GUID *a2)
{
  unsigned int v4; // ebx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v10; // [rsp+50h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  pv = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(**((_QWORD **)this + 17) + 24LL))(
         *((_QWORD *)this + 17),
         1,
         &pv);
  if ( !v4 )
  {
    ++*((_DWORD *)this + 32);
    v5 = pv;
    *a2 = *(struct _GUID *)pv;
    CoTaskMemFree(v5);
    v6 = *((_QWORD *)this + 21);
    v10 = 0;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 48LL))(v6, &v10);
    v7 = 0;
    v12 = 0;
    if ( v10 )
    {
      (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 21) + 80LL))(*((_QWORD *)this + 21), &v12);
      v7 = v12;
    }
    if ( v7 )
      v8 = v7 + 4;
    else
      v8 = 0;
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _GUID *))(**((_QWORD **)this + 18) + 80LL))(
           *((_QWORD *)this + 18),
           v8,
           a2);
    if ( !v4 )
      v4 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 19) + 80LL))(
             *((_QWORD *)this + 19),
             a2);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18002b920  push    rbx
0x18002b922  push    rsi
0x18002b923  push    rdi
0x18002b924  sub     rsp, 30h
0x18002b928  mov     rdi, rcx
0x18002b92b  mov     [rsp+48h+pv], 0
0x18002b934  mov     rcx, [rcx+88h]
0x18002b93b  lea     r8, [rsp+48h+pv]
0x18002b940  xor     r9d, r9d
0x18002b943  mov     rsi, rdx
0x18002b946  mov     rax, [rcx]
0x18002b949  lea     edx, [r9+1]
0x18002b94d  mov     rax, [rax+18h]
0x18002b951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b956  mov     ebx, eax
0x18002b958  test    eax, eax
0x18002b95a  jnz     loc_18002BA02
0x18002b960  inc     dword ptr [rdi+80h]
0x18002b966  mov     rcx, [rsp+48h+pv]; pv
0x18002b96b  movups  xmm0, xmmword ptr [rcx]
0x18002b96e  movdqu  xmmword ptr [rsi], xmm0
0x18002b972  call    cs:__imp_CoTaskMemFree
0x18002b978  mov     rcx, [rdi+0A8h]
0x18002b97f  lea     rdx, [rsp+48h+arg_0]
0x18002b984  mov     [rsp+48h+arg_0], ebx
0x18002b988  mov     rax, [rcx]
0x18002b98b  mov     rax, [rax+30h]
0x18002b98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b994  xor     ecx, ecx
0x18002b996  mov     [rsp+48h+arg_18], rcx
0x18002b99b  cmp     [rsp+48h+arg_0], ecx
0x18002b99f  jz      short loc_18002B9BE
0x18002b9a1  mov     rcx, [rdi+0A8h]
0x18002b9a8  lea     rdx, [rsp+48h+arg_18]
0x18002b9ad  mov     rax, [rcx]
0x18002b9b0  mov     rax, [rax+50h]
0x18002b9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9b9  mov     rcx, [rsp+48h+arg_18]
0x18002b9be  mov     r9, [rdi+90h]
0x18002b9c5  mov     rax, [r9]
0x18002b9c8  test    rcx, rcx
0x18002b9cb  jz      short loc_18002B9D3
0x18002b9cd  lea     rdx, [rcx+4]
0x18002b9d1  jmp     short loc_18002B9D5
0x18002b9d3  xor     edx, edx
0x18002b9d5  mov     rax, [rax+50h]
0x18002b9d9  mov     r8, rsi
0x18002b9dc  mov     rcx, r9
0x18002b9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9e4  mov     ebx, eax
0x18002b9e6  test    eax, eax
0x18002b9e8  jnz     short loc_18002BA02
0x18002b9ea  mov     rcx, [rdi+98h]
0x18002b9f1  mov     rdx, rsi
0x18002b9f4  mov     rax, [rcx]
0x18002b9f7  mov     rax, [rax+50h]
0x18002b9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba00  mov     ebx, eax
0x18002ba02  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba09  lea     rax, WPP_GLOBAL_Control
0x18002ba10  cmp     rcx, rax
0x18002ba13  jz      short loc_18002BA33
0x18002ba15  test    byte ptr [rcx+1Ch], 10h
0x18002ba19  jz      short loc_18002BA33
0x18002ba1b  mov     rcx, [rcx+10h]
0x18002ba1f  lea     r8, WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids
0x18002ba26  mov     edx, 12h
0x18002ba2b  mov     r9d, ebx
0x18002ba2e  call    WPP_SF_d
0x18002ba33  mov     eax, ebx
0x18002ba35  add     rsp, 30h
0x18002ba39  pop     rdi
0x18002ba3a  pop     rsi
0x18002ba3b  pop     rbx
0x18002ba3c  retn
```
