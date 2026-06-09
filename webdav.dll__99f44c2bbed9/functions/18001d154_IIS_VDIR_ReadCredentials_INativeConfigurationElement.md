# IIS_VDIR::ReadCredentials(INativeConfigurationElement *)

- ea: `0x18001d154`
- end: `0x18001d2af`
- name: `?ReadCredentials@IIS_VDIR@@AEAAJPEAVINativeConfigurationElement@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(IIS_VDIR *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18001c854`

## callees

- `0x18001d154`
- `0x1800224c2`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d21a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d232`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d21a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d232`

## pseudocode

```c
__int64 __fastcall IIS_VDIR::ReadCredentials(IIS_VDIR *this, struct INativeConfigurationElement *a2)
{
  __int64 v3; // rax
  int v5; // ebx
  void *v7; // rcx
  size_t v8; // r8
  const unsigned __int16 *v9; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v10; // [rsp+58h] [rbp+10h] BYREF

  *((_DWORD *)this + 88) = 0;
  v3 = *(_QWORD *)a2;
  v9 = 0;
  v10 = 0;
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v3 + 64))(
         a2,
         L"userName",
         &v9,
         0,
         0);
  if ( v5 < 0 )
    goto LABEL_10;
  if ( !v9 || !*v9 )
    return 0;
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
         a2,
         L"password",
         &v10,
         0,
         0);
  if ( v5 < 0
    || (v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
               a2,
               L"logonMethod",
               (char *)this + 348,
               0,
               0),
        v5 < 0)
    || (v5 = STRU::Copy((IIS_VDIR *)((char *)this + 216), v9), v5 < 0)
    || (v5 = STRU::Copy((IIS_VDIR *)((char *)this + 272), v10), v5 < 0) )
  {
LABEL_10:
    memset_0(*((void **)this + 31), 0, *((_DWORD *)this + 64) & 0xFFFFFFFE);
    **((_WORD **)this + 31) = 0;
    v7 = (void *)*((_QWORD *)this + 38);
    v8 = *((_DWORD *)this + 78) & 0xFFFFFFFE;
    *((_DWORD *)this + 66) = 0;
    memset_0(v7, 0, v8);
    **((_WORD **)this + 38) = 0;
    *((_DWORD *)this + 80) = 0;
  }
  else
  {
    *((_DWORD *)this + 88) = 1;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d154  mov     r11, rsp
0x18001d157  mov     [r11+18h], rbx
0x18001d15b  push    rbp
0x18001d15c  push    rsi
0x18001d15d  push    rdi
0x18001d15e  sub     rsp, 30h
0x18001d162  xor     ebp, ebp
0x18001d164  lea     r8, [r11+8]
0x18001d168  mov     [rcx+160h], ebp
0x18001d16e  mov     rsi, rdx
0x18001d171  mov     rax, [rdx]
0x18001d174  mov     rdi, rcx
0x18001d177  xor     r9d, r9d
0x18001d17a  mov     [r11+8], rbp
0x18001d17e  lea     rdx, aUsername; "userName"
0x18001d185  mov     [r11+10h], rbp
0x18001d189  mov     rcx, rsi
0x18001d18c  mov     [r11-28h], rbp
0x18001d190  mov     rax, [rax+40h]
0x18001d194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d199  mov     ebx, eax
0x18001d19b  test    eax, eax
0x18001d19d  js      loc_18001D24E
0x18001d1a3  mov     rax, [rsp+48h+arg_0]
0x18001d1a8  test    rax, rax
0x18001d1ab  jz      loc_18001D24A
0x18001d1b1  cmp     [rax], bp
0x18001d1b4  jz      loc_18001D24A
0x18001d1ba  mov     rax, [rsi]
0x18001d1bd  lea     r8, [rsp+48h+arg_8]
0x18001d1c2  xor     r9d, r9d
0x18001d1c5  mov     [rsp+48h+var_28], rbp
0x18001d1ca  lea     rdx, aPassword; "password"
0x18001d1d1  mov     rcx, rsi
0x18001d1d4  mov     rax, [rax+40h]
0x18001d1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1dd  mov     ebx, eax
0x18001d1df  test    eax, eax
0x18001d1e1  js      short loc_18001D24E
0x18001d1e3  mov     rax, [rsi]
0x18001d1e6  lea     r8, [rdi+15Ch]
0x18001d1ed  xor     r9d, r9d
0x18001d1f0  mov     [rsp+48h+var_28], rbp
0x18001d1f5  lea     rdx, aLogonmethod; "logonMethod"
0x18001d1fc  mov     rcx, rsi
0x18001d1ff  mov     rax, [rax+30h]
0x18001d203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d208  mov     ebx, eax
0x18001d20a  test    eax, eax
0x18001d20c  js      short loc_18001D24E
0x18001d20e  mov     rdx, [rsp+48h+arg_0]
0x18001d213  lea     rcx, [rdi+0D8h]
0x18001d21a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001d220  mov     ebx, eax
0x18001d222  test    eax, eax
0x18001d224  js      short loc_18001D24E
0x18001d226  mov     rdx, [rsp+48h+arg_8]
0x18001d22b  lea     rcx, [rdi+110h]
0x18001d232  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001d238  mov     ebx, eax
0x18001d23a  test    eax, eax
0x18001d23c  js      short loc_18001D24E
0x18001d23e  mov     dword ptr [rdi+160h], 1
0x18001d248  jmp     short loc_18001D2A0
0x18001d24a  xor     eax, eax
0x18001d24c  jmp     short loc_18001D2A2
0x18001d24e  mov     r8d, [rdi+100h]
0x18001d255  xor     edx, edx; Val
0x18001d257  mov     rcx, [rdi+0F8h]; void *
0x18001d25e  and     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001d262  call    memset_0
0x18001d267  mov     rcx, [rdi+0F8h]
0x18001d26e  xor     edx, edx; Val
0x18001d270  mov     [rcx], bp
0x18001d273  mov     r8d, [rdi+138h]
0x18001d27a  mov     rcx, [rdi+130h]; void *
0x18001d281  and     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001d285  mov     [rdi+108h], ebp
0x18001d28b  call    memset_0
0x18001d290  mov     rcx, [rdi+130h]
0x18001d297  mov     [rcx], bp
0x18001d29a  mov     [rdi+140h], ebp
0x18001d2a0  mov     eax, ebx
0x18001d2a2  mov     rbx, [rsp+48h+arg_10]
0x18001d2a7  add     rsp, 30h
0x18001d2ab  pop     rdi
0x18001d2ac  pop     rsi
0x18001d2ad  pop     rbp
0x18001d2ae  retn
```
