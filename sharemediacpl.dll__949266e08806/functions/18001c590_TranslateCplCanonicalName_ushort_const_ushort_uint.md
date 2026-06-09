# TranslateCplCanonicalName(ushort const *,ushort *,uint)

- ea: `0x18001c590`
- end: `0x18001c664`
- name: `?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z`
- size: `212`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b6b8`

## callees

- `0x18001c590`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001c5cb`
- `ole32!CoCreateInstance` at `0x18001c5cb`

## pseudocode

```c
__int64 __fastcall TranslateCplCanonicalName(unsigned __int16 *a1, unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rax
  unsigned __int16 *v7; // rcx
  LPVOID v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v4 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &v9);
  if ( v4 >= 0 )
  {
    v5 = 260;
    v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, unsigned __int16 *, __int64))(*(_QWORD *)v9 + 32LL))(
           v9,
           a1,
           a2,
           260);
    if ( v4 < 0 )
    {
      v6 = 2147483646;
      do
      {
        if ( !v6 )
          break;
        if ( !*a1 )
          break;
        *a2++ = *a1++;
        --v6;
        --v5;
      }
      while ( v5 );
      v7 = a2 - 1;
      if ( v5 )
        v7 = a2;
      v4 = v5 == 0 ? 0x8007007A : 0;
      *v7 = 0;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c590  mov     r11, rsp
0x18001c593  mov     [r11+8], rbx
0x18001c597  mov     [r11+10h], rbp
0x18001c59b  push    rsi
0x18001c59c  push    rdi
0x18001c59d  push    r14
0x18001c59f  sub     rsp, 30h
0x18001c5a3  xor     ebp, ebp
0x18001c5a5  lea     rax, [r11+20h]
0x18001c5a9  mov     rsi, rdx
0x18001c5ac  mov     [r11+20h], rbp
0x18001c5b0  mov     r14, rcx
0x18001c5b3  mov     [r11-28h], rax
0x18001c5b7  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18001c5be  xor     edx, edx; pUnkOuter
0x18001c5c0  lea     r8d, [rbp+1]; dwClsContext
0x18001c5c4  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18001c5cb  call    cs:__imp_CoCreateInstance
0x18001c5d1  mov     ebx, eax
0x18001c5d3  test    eax, eax
0x18001c5d5  js      short loc_18001C64F
0x18001c5d7  mov     rcx, [rsp+48h+arg_18]
0x18001c5dc  mov     edi, 104h
0x18001c5e1  mov     r9d, edi
0x18001c5e4  mov     r8, rsi
0x18001c5e7  mov     rdx, r14
0x18001c5ea  mov     rax, [rcx]
0x18001c5ed  mov     rax, [rax+20h]
0x18001c5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5f6  mov     ebx, eax
0x18001c5f8  test    eax, eax
0x18001c5fa  jns     short loc_18001C63E
0x18001c5fc  mov     eax, 7FFFFFFEh
0x18001c601  test    rax, rax
0x18001c604  jz      short loc_18001C623
0x18001c606  movzx   ecx, word ptr [r14]
0x18001c60a  test    cx, cx
0x18001c60d  jz      short loc_18001C623
0x18001c60f  mov     [rsi], cx
0x18001c612  add     r14, 2
0x18001c616  add     rsi, 2
0x18001c61a  dec     rax
0x18001c61d  sub     rdi, 1
0x18001c621  jnz     short loc_18001C601
0x18001c623  test    rdi, rdi
0x18001c626  lea     rcx, [rsi-2]
0x18001c62a  cmovnz  rcx, rsi
0x18001c62e  neg     rdi
0x18001c631  sbb     ebx, ebx
0x18001c633  not     ebx
0x18001c635  and     ebx, 8007007Ah
0x18001c63b  mov     [rcx], bp
0x18001c63e  mov     rcx, [rsp+48h+arg_18]
0x18001c643  mov     rax, [rcx]
0x18001c646  mov     rax, [rax+10h]
0x18001c64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c64f  mov     rbp, [rsp+48h+arg_8]
0x18001c654  mov     eax, ebx
0x18001c656  mov     rbx, [rsp+48h+arg_0]
0x18001c65b  add     rsp, 30h
0x18001c65f  pop     r14
0x18001c661  pop     rdi
0x18001c662  pop     rsi
0x18001c663  retn
```
