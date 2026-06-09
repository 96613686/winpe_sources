# COleControlHost::_Init(void)

- ea: `0x18001eef8`
- end: `0x18001f09b`
- name: `?_Init@COleControlHost@@IEAAJXZ`
- size: `419`
- prototype: `__int64 __fastcall(COleControlHost *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f0a4`

## callees

- `0x180008320`
- `0x180008ff4`
- `0x18001eef8`
- `0x18001f29c`
- `0x18001f3dc`
- `0x180029010`

## import_xrefs

- `SHELL32!__imp_SHExtCoCreateInstance` at `0x18001ef8e`
- `SHELL32!__imp_SHExtCoCreateInstance` at `0x18001ef8e`

## pseudocode

```c
__int64 __fastcall COleControlHost::_Init(COleControlHost *this)
{
  char *v1; // rbx
  _QWORD *v2; // rsi
  int v4; // eax
  __int64 result; // rax
  int v6; // ebx
  struct tagNMHDR v7; // [rsp+30h] [rbp-48h] BYREF
  __int128 v8; // [rsp+48h] [rbp-30h]
  char *v9; // [rsp+58h] [rbp-20h]

  memset(&v7, 0, sizeof(v7));
  v1 = (char *)this + 96;
  v2 = (_QWORD *)((char *)this + 112);
  v8 = *((_OWORD *)this + 6);
  v9 = (char *)this + 112;
  if ( COleControlHost::_SendNotify(this, 0x1301u, &v7) == -1
    || (v4 = memcmp_0(&CLSID_WebBrowser, v1, 0x10u),
        result = SHExtCoCreateInstance(v1, 0, 5, v4 != 0 ? 0 : 2, &GUID_00000112_0000_0000_c000_000000000046, v2),
        (int)result >= 0) )
  {
    if ( *v2 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v2 + 176LL))(
        *v2,
        *((unsigned int *)this + 15),
        (char *)this + 64);
      if ( (*((_DWORD *)this + 16) & 0x20000) != 0 )
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD, COleControlHost *))(*(_QWORD *)*v2 + 24LL))(*v2, this);
        COleControlHost::_PersistInit(this);
      }
      else
      {
        COleControlHost::_PersistInit(this);
        v6 = (*(__int64 (__fastcall **)(_QWORD, COleControlHost *))(*(_QWORD *)*v2 + 24LL))(*v2, this);
      }
      if ( v6 >= 0 )
      {
        if ( (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v2)(*v2, &IID_IViewObject, (char *)this + 120) >= 0 )
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(**((_QWORD **)this + 15) + 56LL))(
            *((_QWORD *)this + 15),
            *((unsigned int *)this + 15),
            0,
            (char *)this + 8);
        (*(void (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)*v2 + 152LL))(
          *v2,
          (char *)this + 8,
          (char *)this + 68);
        (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**((_QWORD **)this + 14) + 40LL))(
          *((_QWORD *)this + 14),
          L"OC Host Window",
          L"OC Host Window");
        return 0;
      }
      else
      {
        return (unsigned int)v6;
      }
    }
    else
    {
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001eef8  mov     r11, rsp
0x18001eefb  mov     [r11+10h], rbx
0x18001eeff  mov     [r11+18h], rsi
0x18001ef03  push    rdi
0x18001ef04  sub     rsp, 70h
0x18001ef08  mov     rax, cs:__security_cookie
0x18001ef0f  xor     rax, rsp
0x18001ef12  mov     [rsp+78h+var_18], rax
0x18001ef17  xorps   xmm0, xmm0
0x18001ef1a  mov     qword ptr [r11-48h], 0
0x18001ef22  movups  [rsp+78h+var_40], xmm0
0x18001ef27  lea     rbx, [rcx+60h]
0x18001ef2b  mov     edx, 1301h; unsigned int
0x18001ef30  movups  xmm0, xmmword ptr [rbx]
0x18001ef33  lea     rsi, [rcx+70h]
0x18001ef37  mov     rdi, rcx
0x18001ef3a  lea     r8, [r11-48h]; struct tagNMHDR *
0x18001ef3e  movdqu  [rsp+78h+var_30], xmm0
0x18001ef44  mov     [r11-20h], rsi
0x18001ef48  call    ?_SendNotify@COleControlHost@@IEAA_JIPEAUtagNMHDR@@@Z; COleControlHost::_SendNotify(uint,tagNMHDR *)
0x18001ef4d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ef51  jz      short loc_18001EF9C
0x18001ef53  mov     r8d, 10h; Size
0x18001ef59  lea     rcx, CLSID_WebBrowser; Buf1
0x18001ef60  mov     rdx, rbx; Buf2
0x18001ef63  call    memcmp_0
0x18001ef68  neg     eax
0x18001ef6a  mov     [rsp+78h+var_50], rsi
0x18001ef6f  lea     rax, _GUID_00000112_0000_0000_c000_000000000046
0x18001ef76  mov     rcx, rbx
0x18001ef79  sbb     r9d, r9d
0x18001ef7c  mov     [rsp+78h+var_58], rax
0x18001ef81  xor     edx, edx
0x18001ef83  not     r9d
0x18001ef86  and     r9d, 2
0x18001ef8a  lea     r8d, [rdx+5]
0x18001ef8e  call    cs:__imp_SHExtCoCreateInstance
0x18001ef94  test    eax, eax
0x18001ef96  js      loc_18001F07C
0x18001ef9c  mov     rcx, [rsi]
0x18001ef9f  test    rcx, rcx
0x18001efa2  jnz     short loc_18001EFAE
0x18001efa4  mov     eax, 80004005h
0x18001efa9  jmp     loc_18001F07C
0x18001efae  mov     rax, [rcx]
0x18001efb1  lea     r8, [rdi+40h]
0x18001efb5  mov     edx, [rdi+3Ch]
0x18001efb8  mov     rax, [rax+0B0h]
0x18001efbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efc4  test    dword ptr [rdi+40h], 20000h
0x18001efcb  jz      short loc_18001EFEB
0x18001efcd  mov     rcx, [rsi]
0x18001efd0  mov     rdx, rdi
0x18001efd3  mov     rax, [rcx]
0x18001efd6  mov     rax, [rax+18h]
0x18001efda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efdf  mov     rcx, rdi; this
0x18001efe2  mov     ebx, eax
0x18001efe4  call    ?_PersistInit@COleControlHost@@IEAAJXZ; COleControlHost::_PersistInit(void)
0x18001efe9  jmp     short loc_18001F007
0x18001efeb  mov     rcx, rdi; this
0x18001efee  call    ?_PersistInit@COleControlHost@@IEAAJXZ; COleControlHost::_PersistInit(void)
0x18001eff3  mov     rcx, [rsi]
0x18001eff6  mov     rdx, rdi
0x18001eff9  mov     rax, [rcx]
0x18001effc  mov     rax, [rax+18h]
0x18001f000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f005  mov     ebx, eax
0x18001f007  test    ebx, ebx
0x18001f009  jns     short loc_18001F00F
0x18001f00b  mov     eax, ebx
0x18001f00d  jmp     short loc_18001F07C
0x18001f00f  mov     rcx, [rsi]
0x18001f012  lea     r8, [rdi+78h]
0x18001f016  lea     rdx, IID_IViewObject
0x18001f01d  mov     rax, [rcx]
0x18001f020  mov     rax, [rax]
0x18001f023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f028  test    eax, eax
0x18001f02a  js      short loc_18001F046
0x18001f02c  mov     rcx, [rdi+78h]
0x18001f030  lea     r9, [rdi+8]
0x18001f034  mov     edx, [rdi+3Ch]
0x18001f037  xor     r8d, r8d
0x18001f03a  mov     rax, [rcx]
0x18001f03d  mov     rax, [rax+38h]
0x18001f041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f046  mov     rcx, [rsi]
0x18001f049  lea     r8, [rdi+44h]
0x18001f04d  lea     rdx, [rdi+8]
0x18001f051  mov     rax, [rcx]
0x18001f054  mov     rax, [rax+98h]
0x18001f05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f060  mov     rcx, [rdi+70h]
0x18001f064  lea     rdx, aOcHostWindow; "OC Host Window"
0x18001f06b  mov     r8, rdx
0x18001f06e  mov     rax, [rcx]
0x18001f071  mov     rax, [rax+28h]
0x18001f075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f07a  xor     eax, eax
0x18001f07c  mov     rcx, [rsp+78h+var_18]
0x18001f081  xor     rcx, rsp; StackCookie
0x18001f084  call    __security_check_cookie
0x18001f089  lea     r11, [rsp+78h+var_8]
0x18001f08e  mov     rbx, [r11+18h]
0x18001f092  mov     rsi, [r11+20h]
0x18001f096  mov     rsp, r11
0x18001f099  pop     rdi
0x18001f09a  retn
```
