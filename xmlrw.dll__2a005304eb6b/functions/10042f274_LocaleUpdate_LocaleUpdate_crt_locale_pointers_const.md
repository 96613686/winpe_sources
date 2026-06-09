# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x10042f274`
- end: `0x10042f30f`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x10042ef20`
- `0x10042f444`
- `0x10042f740`
- `0x1004300e0`
- `0x1004338d0`
- `0x10043396c`
- `0x100433e3c`

## callees

- `0x10042dd4c`
- `0x10042f274`
- `0x10043195c`
- `0x1004319d0`

## pseudocode

```c
_LocaleUpdate *__fastcall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct __crt_locale_pointers *const a2)
{
  _OWORD *v3; // rsi
  __int128 v4; // xmm0
  __int64 v5; // rax
  int v6; // eax

  *((_BYTE *)this + 24) = 0;
  v3 = (_OWORD *)((char *)this + 8);
  if ( a2 )
  {
    v4 = (__int128)*a2;
LABEL_5:
    *v3 = v4;
    return this;
  }
  if ( !_acrt_locale_changed_data )
  {
    v4 = *(_OWORD *)&_acrt_initial_locale_pointers;
    goto LABEL_5;
  }
  v5 = _acrt_getptd();
  *(_QWORD *)this = v5;
  *(_QWORD *)v3 = *(_QWORD *)(v5 + 144);
  *((_QWORD *)this + 2) = *(_QWORD *)(v5 + 136);
  _acrt_update_locale_info(v5, v3);
  _acrt_update_multibyte_info(*(_QWORD *)this, (char *)this + 16);
  v6 = *(_DWORD *)(*(_QWORD *)this + 936LL);
  if ( (v6 & 2) == 0 )
  {
    *(_DWORD *)(*(_QWORD *)this + 936LL) = v6 | 2;
    *((_BYTE *)this + 24) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x10042f274  mov     [rsp+arg_0], rbx
0x10042f279  mov     [rsp+arg_8], rsi
0x10042f27e  push    rdi
0x10042f27f  sub     rsp, 20h
0x10042f283  mov     byte ptr [rcx+18h], 0
0x10042f287  mov     rdi, rcx
0x10042f28a  lea     rsi, [rcx+8]
0x10042f28e  test    rdx, rdx
0x10042f291  jz      short loc_10042F298
0x10042f293  movups  xmm0, xmmword ptr [rdx]
0x10042f296  jmp     short loc_10042F2A8
0x10042f298  cmp     cs:__acrt_locale_changed_data, 0
0x10042f29f  jnz     short loc_10042F2AE
0x10042f2a1  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x10042f2a8  movdqu  xmmword ptr [rsi], xmm0
0x10042f2ac  jmp     short loc_10042F2FC
0x10042f2ae  call    __acrt_getptd
0x10042f2b3  mov     [rdi], rax
0x10042f2b6  mov     rdx, rsi
0x10042f2b9  mov     rcx, [rax+90h]
0x10042f2c0  mov     [rsi], rcx
0x10042f2c3  mov     rcx, [rax+88h]
0x10042f2ca  mov     [rdi+10h], rcx
0x10042f2ce  mov     rcx, rax
0x10042f2d1  call    __acrt_update_locale_info
0x10042f2d6  mov     rcx, [rdi]
0x10042f2d9  lea     rdx, [rdi+10h]
0x10042f2dd  call    __acrt_update_multibyte_info
0x10042f2e2  mov     rcx, [rdi]
0x10042f2e5  mov     eax, [rcx+3A8h]
0x10042f2eb  test    al, 2
0x10042f2ed  jnz     short loc_10042F2FC
0x10042f2ef  or      eax, 2
0x10042f2f2  mov     [rcx+3A8h], eax
0x10042f2f8  mov     byte ptr [rdi+18h], 1
0x10042f2fc  mov     rbx, [rsp+28h+arg_0]
0x10042f301  mov     rax, rdi
0x10042f304  mov     rsi, [rsp+28h+arg_8]
0x10042f309  add     rsp, 20h
0x10042f30d  pop     rdi
0x10042f30e  retn
```
