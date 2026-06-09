# DecodePropertyFromString(ushort const *,IPubProperty *)

- ea: `0x180002974`
- end: `0x180002a74`
- name: `?DecodePropertyFromString@@YAJPEBGPEAVIPubProperty@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IPubProperty *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002220`

## callees

- `0x18000283c`
- `0x180002974`
- `0x180003490`
- `0x180004010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800029a3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800029ad`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800029b8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800029a3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800029ad`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800029b8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a37`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a41`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a4b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a37`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a41`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a4b`

## pseudocode

```c
__int64 __fastcall DecodePropertyFromString(const unsigned __int16 *a1, struct IPubProperty *a2)
{
  int v4; // ebx
  unsigned __int16 *v6; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v7; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v8; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v9[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v10[56]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v11[56]; // [rsp+C8h] [rbp-38h] BYREF

  STRU::STRU((STRU *)v11);
  STRU::STRU((STRU *)v10);
  STRU::STRU((STRU *)v9);
  v8 = 0;
  v7 = 0;
  v6 = 0;
  v4 = DecodeAllFields(
         a1,
         (struct STRU *)v11,
         (const unsigned __int16 **)&v8,
         (struct STRU *)v10,
         &v7,
         (struct STRU *)v9,
         &v6);
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(struct IPubProperty *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)a2 + 64LL))(
           a2,
           v8,
           v7,
           v6);
  STRU::~STRU((STRU *)v9);
  STRU::~STRU((STRU *)v10);
  STRU::~STRU((STRU *)v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002974  mov     [rsp-8+arg_10], rbx
0x180002979  mov     [rsp-8+arg_18], rdi
0x18000297e  push    rbp
0x18000297f  lea     rbp, [rsp-10h]
0x180002984  sub     rsp, 110h
0x18000298b  mov     rax, cs:__security_cookie
0x180002992  xor     rax, rsp
0x180002995  mov     [rbp+10h+var_10], rax
0x180002999  mov     rbx, rcx
0x18000299c  mov     rdi, rdx
0x18000299f  lea     rcx, [rbp+10h+var_48]
0x1800029a3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800029a9  lea     rcx, [rbp+10h+var_80]
0x1800029ad  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800029b3  lea     rcx, [rsp+110h+var_B8]
0x1800029b8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800029be  lea     rax, [rsp+110h+var_D0]
0x1800029c3  mov     [rsp+110h+var_C0], 0
0x1800029cc  mov     [rsp+110h+var_E0], rax; unsigned __int16 **
0x1800029d1  lea     r9, [rbp+10h+var_80]; struct STRU *
0x1800029d5  lea     rax, [rsp+110h+var_B8]
0x1800029da  mov     [rsp+110h+var_C8], 0
0x1800029e3  mov     [rsp+110h+var_E8], rax; struct STRU *
0x1800029e8  lea     r8, [rsp+110h+var_C0]; unsigned __int16 **
0x1800029ed  lea     rax, [rsp+110h+var_C8]
0x1800029f2  mov     [rsp+110h+var_D0], 0
0x1800029fb  lea     rdx, [rbp+10h+var_48]; struct STRU *
0x1800029ff  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x180002a04  mov     rcx, rbx; unsigned __int16 *
0x180002a07  call    ?DecodeAllFields@@YAJPEBGPEAVSTRU@@PEAPEBG1212@Z; DecodeAllFields(ushort const *,STRU *,ushort const * *,STRU *,ushort const * *,STRU *,ushort const * *)
0x180002a0c  mov     ebx, eax
0x180002a0e  test    eax, eax
0x180002a10  js      short loc_180002A32
0x180002a12  mov     rax, [rdi]
0x180002a15  mov     rcx, rdi
0x180002a18  mov     r9, [rsp+110h+var_D0]
0x180002a1d  mov     r8, [rsp+110h+var_C8]
0x180002a22  mov     rdx, [rsp+110h+var_C0]
0x180002a27  mov     rax, [rax+40h]
0x180002a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a30  mov     ebx, eax
0x180002a32  lea     rcx, [rsp+110h+var_B8]
0x180002a37  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002a3d  lea     rcx, [rbp+10h+var_80]
0x180002a41  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002a47  lea     rcx, [rbp+10h+var_48]
0x180002a4b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002a51  mov     eax, ebx
0x180002a53  mov     rcx, [rbp+10h+var_10]
0x180002a57  xor     rcx, rsp; StackCookie
0x180002a5a  call    __security_check_cookie
0x180002a5f  lea     r11, [rsp+110h+var_s0]
0x180002a67  mov     rbx, [r11+20h]
0x180002a6b  mov     rdi, [r11+28h]
0x180002a6f  mov     rsp, r11
0x180002a72  pop     rbp
0x180002a73  retn
```
