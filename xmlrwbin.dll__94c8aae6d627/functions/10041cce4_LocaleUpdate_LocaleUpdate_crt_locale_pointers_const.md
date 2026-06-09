# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x10041cce4`
- end: `0x10041cd7f`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x10041c990`
- `0x10041ceb4`
- `0x10041d1b0`
- `0x10041db50`
- `0x100420320`
- `0x1004203bc`
- `0x10042088c`

## callees

- `0x10041b7bc`
- `0x10041cce4`
- `0x10041f1f0`
- `0x10041f264`

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
0x10041cce4  mov     [rsp+arg_0], rbx
0x10041cce9  mov     [rsp+arg_8], rsi
0x10041ccee  push    rdi
0x10041ccef  sub     rsp, 20h
0x10041ccf3  mov     byte ptr [rcx+18h], 0
0x10041ccf7  mov     rdi, rcx
0x10041ccfa  lea     rsi, [rcx+8]
0x10041ccfe  test    rdx, rdx
0x10041cd01  jz      short loc_10041CD08
0x10041cd03  movups  xmm0, xmmword ptr [rdx]
0x10041cd06  jmp     short loc_10041CD18
0x10041cd08  cmp     cs:__acrt_locale_changed_data, 0
0x10041cd0f  jnz     short loc_10041CD1E
0x10041cd11  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x10041cd18  movdqu  xmmword ptr [rsi], xmm0
0x10041cd1c  jmp     short loc_10041CD6C
0x10041cd1e  call    __acrt_getptd
0x10041cd23  mov     [rdi], rax
0x10041cd26  mov     rdx, rsi
0x10041cd29  mov     rcx, [rax+90h]
0x10041cd30  mov     [rsi], rcx
0x10041cd33  mov     rcx, [rax+88h]
0x10041cd3a  mov     [rdi+10h], rcx
0x10041cd3e  mov     rcx, rax
0x10041cd41  call    __acrt_update_locale_info
0x10041cd46  mov     rcx, [rdi]
0x10041cd49  lea     rdx, [rdi+10h]
0x10041cd4d  call    __acrt_update_multibyte_info
0x10041cd52  mov     rcx, [rdi]
0x10041cd55  mov     eax, [rcx+3A8h]
0x10041cd5b  test    al, 2
0x10041cd5d  jnz     short loc_10041CD6C
0x10041cd5f  or      eax, 2
0x10041cd62  mov     [rcx+3A8h], eax
0x10041cd68  mov     byte ptr [rdi+18h], 1
0x10041cd6c  mov     rbx, [rsp+28h+arg_0]
0x10041cd71  mov     rax, rdi
0x10041cd74  mov     rsi, [rsp+28h+arg_8]
0x10041cd79  add     rsp, 20h
0x10041cd7d  pop     rdi
0x10041cd7e  retn
```
