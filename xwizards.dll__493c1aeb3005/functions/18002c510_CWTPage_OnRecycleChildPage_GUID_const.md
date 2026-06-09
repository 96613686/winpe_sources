# CWTPage::OnRecycleChildPage(_GUID * const)

- ea: `0x18002c510`
- end: `0x18002c762`
- name: `?OnRecycleChildPage@CWTPage@@UEAAJQEAU_GUID@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(CWTPage *__hidden this, struct _GUID *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000e0f0`
- `0x180024c1c`
- `0x18002c510`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c64e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c64e`

## pseudocode

```c
__int64 __fastcall CWTPage::OnRecycleChildPage(CWTPage *this, struct _GUID *const a2)
{
  __int64 v3; // rcx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  unsigned int v9; // edi
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  v3 = *((_QWORD *)this + 17);
  if ( a2 )
  {
    if ( v3 )
    {
      v5 = *((_DWORD *)this + 32);
      if ( v5 )
      {
        *((_DWORD *)this + 32) = v5 - 1;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 17) + 32LL))(
          *((_QWORD *)this + 17),
          *((unsigned int *)this + 32));
      }
    }
  }
  else
  {
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      *((_QWORD *)this + 17) = 0;
      *((_DWORD *)this + 32) = 0;
    }
    if ( *((_DWORD *)this + 24) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 22) + 168LL))(
        *((_QWORD *)this + 22),
        3001,
        0,
        *((_QWORD *)this + 13));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids,
          *((_QWORD *)this + 13));
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 22) + 168LL))(
        *((_QWORD *)this + 22),
        3002,
        0,
        *((_QWORD *)this + 14));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids,
          *((_QWORD *)this + 14));
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 22) + 168LL))(
        *((_QWORD *)this + 22),
        3003,
        0,
        *((_QWORD *)this + 15));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids,
          *((_QWORD *)this + 15));
      CoTaskMemFree(*((LPVOID *)this + 13));
      *((_QWORD *)this + 13) = 0;
      *((_QWORD *)this + 14) = 0;
      *((_QWORD *)this + 15) = 0;
    }
  }
  v6 = *((_QWORD *)this + 21);
  v11 = 0;
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 48LL))(v6, &v11);
  v7 = 0;
  v12 = 0;
  if ( v11 > 1 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 21) + 64LL))(
      *((_QWORD *)this + 21),
      v11 - 2,
      &v12);
    v7 = v12;
  }
  v8 = v7 + 4;
  if ( !v7 )
    v8 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *const, __int64))(**((_QWORD **)this + 18) + 88LL))(
         *((_QWORD *)this + 18),
         a2,
         v8);
  (*(void (__fastcall **)(_QWORD, struct _GUID *const))(**((_QWORD **)this + 19) + 88LL))(*((_QWORD *)this + 19), a2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002c510  mov     [rsp+arg_10], rbx
0x18002c515  push    rsi
0x18002c516  push    rdi
0x18002c517  push    r15
0x18002c519  sub     rsp, 30h
0x18002c51d  xor     edi, edi
0x18002c51f  lea     r15, WPP_GLOBAL_Control
0x18002c526  mov     rbx, rcx
0x18002c529  mov     rcx, [rcx+88h]
0x18002c530  mov     rsi, rdx
0x18002c533  test    rdx, rdx
0x18002c536  jnz     loc_18002C662
0x18002c53c  test    rcx, rcx
0x18002c53f  jz      short loc_18002C55A
0x18002c541  mov     rax, [rcx]
0x18002c544  mov     rax, [rax+10h]
0x18002c548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c54d  mov     [rbx+88h], rdi
0x18002c554  mov     [rbx+80h], edi
0x18002c55a  cmp     [rbx+60h], edi
0x18002c55d  jz      loc_18002C69E
0x18002c563  mov     rcx, [rbx+0B0h]
0x18002c56a  xor     r8d, r8d
0x18002c56d  mov     r9, [rbx+68h]
0x18002c571  mov     edx, 0BB9h
0x18002c576  mov     rax, [rcx]
0x18002c579  mov     rax, [rax+0A8h]
0x18002c580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c585  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c58c  cmp     rcx, r15
0x18002c58f  jz      short loc_18002C5B0
0x18002c591  test    byte ptr [rcx+1Ch], 8
0x18002c595  jz      short loc_18002C5B0
0x18002c597  mov     r9, [rbx+68h]
0x18002c59b  lea     r8, WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids
0x18002c5a2  mov     rcx, [rcx+10h]
0x18002c5a6  mov     edx, 13h
0x18002c5ab  call    WPP_SF_S
0x18002c5b0  mov     rcx, [rbx+0B0h]
0x18002c5b7  xor     r8d, r8d
0x18002c5ba  mov     r9, [rbx+70h]
0x18002c5be  mov     edx, 0BBAh
0x18002c5c3  mov     rax, [rcx]
0x18002c5c6  mov     rax, [rax+0A8h]
0x18002c5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5d9  cmp     rcx, r15
0x18002c5dc  jz      short loc_18002C5FD
0x18002c5de  test    byte ptr [rcx+1Ch], 8
0x18002c5e2  jz      short loc_18002C5FD
0x18002c5e4  mov     r9, [rbx+70h]
0x18002c5e8  lea     r8, WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids
0x18002c5ef  mov     rcx, [rcx+10h]
0x18002c5f3  mov     edx, 14h
0x18002c5f8  call    WPP_SF_q
0x18002c5fd  mov     rcx, [rbx+0B0h]
0x18002c604  xor     r8d, r8d
0x18002c607  mov     r9, [rbx+78h]
0x18002c60b  mov     edx, 0BBBh
0x18002c610  mov     rax, [rcx]
0x18002c613  mov     rax, [rax+0A8h]
0x18002c61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c61f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c626  cmp     rcx, r15
0x18002c629  jz      short loc_18002C64A
0x18002c62b  test    byte ptr [rcx+1Ch], 8
0x18002c62f  jz      short loc_18002C64A
0x18002c631  mov     r9, [rbx+78h]
0x18002c635  lea     r8, WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids
0x18002c63c  mov     rcx, [rcx+10h]
0x18002c640  mov     edx, 15h
0x18002c645  call    WPP_SF_q
0x18002c64a  mov     rcx, [rbx+68h]; pv
0x18002c64e  call    cs:__imp_CoTaskMemFree
0x18002c654  mov     [rbx+68h], rdi
0x18002c658  mov     [rbx+70h], rdi
0x18002c65c  mov     [rbx+78h], rdi
0x18002c660  jmp     short loc_18002C69E
0x18002c662  test    rcx, rcx
0x18002c665  jz      short loc_18002C69E
0x18002c667  mov     eax, [rbx+80h]
0x18002c66d  test    eax, eax
0x18002c66f  jz      short loc_18002C69E
0x18002c671  dec     eax
0x18002c673  mov     [rbx+80h], eax
0x18002c679  mov     rax, [rcx]
0x18002c67c  mov     rax, [rax+28h]
0x18002c680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c685  mov     rcx, [rbx+88h]
0x18002c68c  mov     edx, [rbx+80h]
0x18002c692  mov     rax, [rcx]
0x18002c695  mov     rax, [rax+20h]
0x18002c699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c69e  mov     rcx, [rbx+0A8h]
0x18002c6a5  lea     rdx, [rsp+48h+arg_0]
0x18002c6aa  mov     [rsp+48h+arg_0], edi
0x18002c6ae  mov     rax, [rcx]
0x18002c6b1  mov     rax, [rax+30h]
0x18002c6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6ba  mov     edx, [rsp+48h+arg_0]
0x18002c6be  mov     rcx, rdi
0x18002c6c1  mov     [rsp+48h+arg_8], rcx
0x18002c6c6  cmp     edx, 1
0x18002c6c9  jbe     short loc_18002C6EB
0x18002c6cb  mov     rcx, [rbx+0A8h]
0x18002c6d2  lea     r8, [rsp+48h+arg_8]
0x18002c6d7  add     edx, 0FFFFFFFEh
0x18002c6da  mov     rax, [rcx]
0x18002c6dd  mov     rax, [rax+40h]
0x18002c6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6e6  mov     rcx, [rsp+48h+arg_8]
0x18002c6eb  mov     r9, [rbx+90h]
0x18002c6f2  lea     r8, [rcx+4]
0x18002c6f6  mov     rax, [r9]
0x18002c6f9  test    rcx, rcx
0x18002c6fc  jnz     short loc_18002C701
0x18002c6fe  mov     r8, rdi
0x18002c701  mov     rax, [rax+58h]
0x18002c705  mov     rdx, rsi
0x18002c708  mov     rcx, r9
0x18002c70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c710  mov     rcx, [rbx+98h]
0x18002c717  mov     edi, eax
0x18002c719  mov     rdx, [rcx]
0x18002c71c  mov     rax, [rdx+58h]
0x18002c720  mov     rdx, rsi
0x18002c723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c728  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c72f  cmp     rcx, r15
0x18002c732  jz      short loc_18002C752
0x18002c734  test    byte ptr [rcx+1Ch], 10h
0x18002c738  jz      short loc_18002C752
0x18002c73a  mov     rcx, [rcx+10h]
0x18002c73e  lea     r8, WPP_f8455e9d40b9396bc9f6cea9ffa6b464_Traceguids
0x18002c745  mov     edx, 16h
0x18002c74a  mov     r9d, edi
0x18002c74d  call    WPP_SF_d
0x18002c752  mov     rbx, [rsp+48h+arg_10]
0x18002c757  mov     eax, edi
0x18002c759  add     rsp, 30h
0x18002c75d  pop     r15
0x18002c75f  pop     rdi
0x18002c760  pop     rsi
0x18002c761  retn
```
