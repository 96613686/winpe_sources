# CMoreInfoPage::_UpdateButtons(void)

- ea: `0x18003cf40`
- end: `0x18003d009`
- name: `?_UpdateButtons@CMoreInfoPage@@UEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(CMoreInfoPage *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18003cf40`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cfe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cfef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cfe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cfef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cff9`
- `USER32!GetSystemMetrics` at `0x18003cf65`
- `USER32!GetSystemMetrics` at `0x18003cf65`

## pseudocode

```c
__int64 __fastcall CMoreInfoPage::_UpdateButtons(CMoreInfoPage *this)
{
  int v1; // edi
  bool v3; // zf
  unsigned int v4; // ebx
  LPVOID pv; // [rsp+50h] [rbp+20h] BYREF
  LPVOID v7; // [rsp+58h] [rbp+28h] BYREF
  LPVOID v8; // [rsp+60h] [rbp+30h] BYREF

  v1 = 0;
  v3 = (*((_BYTE *)this + 48) & 1) == 0;
  pv = 0;
  v7 = 0;
  v8 = 0;
  if ( v3 && !GetSystemMetrics(67) )
    v1 = 16;
  (*(void (__fastcall **)(CMoreInfoPage *, LPVOID *))(*(_QWORD *)this + 120LL))(this, &pv);
  (*(void (__fastcall **)(CMoreInfoPage *, LPVOID *))(*(_QWORD *)this + 136LL))(this, &v7);
  if ( v1 == 16 )
    (*(void (__fastcall **)(CMoreInfoPage *, LPVOID *))(*(_QWORD *)this + 128LL))(this, &v8);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, LPVOID, LPVOID))(**((_QWORD **)this + 3) + 24LL))(
         *((_QWORD *)this + 3),
         v1 | 0x85u,
         pv,
         v7,
         v8);
  CoTaskMemFree(pv);
  CoTaskMemFree(v7);
  CoTaskMemFree(v8);
  return v4;
}

```

## disassembly

```asm
0x18003cf40  push    rbp
0x18003cf42  push    rbx
0x18003cf43  push    rdi
0x18003cf44  mov     rbp, rsp
0x18003cf47  sub     rsp, 30h
0x18003cf4b  xor     edi, edi
0x18003cf4d  mov     rbx, rcx
0x18003cf50  test    byte ptr [rcx+30h], 1
0x18003cf54  mov     [rbp+pv], rdi
0x18003cf58  mov     [rbp+arg_8], rdi
0x18003cf5c  mov     [rbp+arg_10], rdi
0x18003cf60  jnz     short loc_18003CF72
0x18003cf62  lea     ecx, [rdi+43h]; nIndex
0x18003cf65  call    cs:__imp_GetSystemMetrics
0x18003cf6b  test    eax, eax
0x18003cf6d  jnz     short loc_18003CF72
0x18003cf6f  lea     edi, [rax+10h]
0x18003cf72  mov     rax, [rbx]
0x18003cf75  lea     rdx, [rbp+pv]
0x18003cf79  mov     rcx, rbx
0x18003cf7c  mov     rax, [rax+78h]
0x18003cf80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf85  mov     rax, [rbx]
0x18003cf88  lea     rdx, [rbp+arg_8]
0x18003cf8c  mov     rcx, rbx
0x18003cf8f  mov     rax, [rax+88h]
0x18003cf96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf9b  cmp     edi, 10h
0x18003cf9e  jnz     short loc_18003CFB6
0x18003cfa0  mov     rax, [rbx]
0x18003cfa3  lea     rdx, [rbp+arg_10]
0x18003cfa7  mov     rcx, rbx
0x18003cfaa  mov     rax, [rax+80h]
0x18003cfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfb6  mov     rcx, [rbx+18h]
0x18003cfba  or      edi, 85h
0x18003cfc0  mov     r10, [rbp+arg_10]
0x18003cfc4  mov     edx, edi
0x18003cfc6  mov     r9, [rbp+arg_8]
0x18003cfca  mov     r8, [rbp+pv]
0x18003cfce  mov     rax, [rcx]
0x18003cfd1  mov     [rsp+30h+var_10], r10
0x18003cfd6  mov     rax, [rax+18h]
0x18003cfda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfdf  mov     rcx, [rbp+pv]; pv
0x18003cfe3  mov     ebx, eax
0x18003cfe5  call    cs:__imp_CoTaskMemFree
0x18003cfeb  mov     rcx, [rbp+arg_8]; pv
0x18003cfef  call    cs:__imp_CoTaskMemFree
0x18003cff5  mov     rcx, [rbp+arg_10]; pv
0x18003cff9  call    cs:__imp_CoTaskMemFree
0x18003cfff  mov     eax, ebx
0x18003d001  add     rsp, 30h
0x18003d005  pop     rdi
0x18003d006  pop     rbx
0x18003d007  pop     rbp
0x18003d008  retn
```
