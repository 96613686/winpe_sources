# GetDavElementHelper(IHttpServer *,ushort const *,ushort const *,INativeConfigurationElement * *,INativeSectionException * *)

- ea: `0x18001c084`
- end: `0x18001c1be`
- name: `?GetDavElementHelper@@YAJPEAVIHttpServer@@PEBG1PEAPEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(struct IHttpServer *, const unsigned __int16 *, const unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180010384`
- `0x18001c1c4`

## callees

- `0x18001c084`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c0dd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c0dd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001c0bd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001c0bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c198`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c198`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c0fd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c110`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c0fd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c110`

## pseudocode

```c
__int64 __fastcall GetDavElementHelper(
        struct IHttpServer *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct INativeConfigurationElement **a4,
        struct INativeSectionException **a5)
{
  int v9; // ebx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rax
  __int64 v12; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v13[32]; // [rsp+48h] [rbp-29h] BYREF
  __int64 v14; // [rsp+68h] [rbp-9h]

  STRU::STRU((STRU *)v13);
  v12 = 0;
  *a4 = 0;
  v9 = STRU::Copy((STRU *)v13, L"MACHINE/WEBROOT/APPHOST");
  if ( v9 >= 0 )
  {
    if ( !a2 || (v9 = STRU::Append((STRU *)v13, L"/"), v9 >= 0) && (v9 = STRU::Append((STRU *)v13, a2), v9 >= 0) )
    {
      v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)a1 + 56LL))(a1);
      v9 = (**v10)(v10, &IID_INativeConfigurationSystem, &v12);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, struct INativeConfigurationElement **, struct INativeSectionException **, _QWORD))(*(_QWORD *)v12 + 24LL))(
               v12,
               a3,
               v14,
               a4,
               a5,
               0);
    }
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  STRU::~STRU((STRU *)v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c084  push    rbp
0x18001c086  push    rbx
0x18001c087  push    rsi
0x18001c088  push    rdi
0x18001c089  push    r12
0x18001c08b  push    r14
0x18001c08d  push    r15
0x18001c08f  lea     rbp, [rsp-1Fh]
0x18001c094  sub     rsp, 90h
0x18001c09b  mov     rax, cs:__security_cookie
0x18001c0a2  xor     rax, rsp
0x18001c0a5  mov     [rbp+4Fh+var_40], rax
0x18001c0a9  mov     r12, [rbp+4Fh+arg_20]
0x18001c0ad  mov     r14, rcx
0x18001c0b0  lea     rcx, [rbp+4Fh+var_78]
0x18001c0b4  mov     rsi, r9
0x18001c0b7  mov     r15, r8
0x18001c0ba  mov     rdi, rdx
0x18001c0bd  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001c0c3  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001c0ca  mov     [rbp+4Fh+var_80], 0
0x18001c0d2  lea     rcx, [rbp+4Fh+var_78]
0x18001c0d6  mov     qword ptr [rsi], 0
0x18001c0dd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001c0e3  mov     ebx, eax
0x18001c0e5  test    eax, eax
0x18001c0e7  js      loc_18001C177
0x18001c0ed  test    rdi, rdi
0x18001c0f0  jz      short loc_18001C11C
0x18001c0f2  lea     rdx, asc_180025EA4; "/"
0x18001c0f9  lea     rcx, [rbp+4Fh+var_78]
0x18001c0fd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001c103  mov     ebx, eax
0x18001c105  test    eax, eax
0x18001c107  js      short loc_18001C177
0x18001c109  mov     rdx, rdi
0x18001c10c  lea     rcx, [rbp+4Fh+var_78]
0x18001c110  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001c116  mov     ebx, eax
0x18001c118  test    eax, eax
0x18001c11a  js      short loc_18001C177
0x18001c11c  mov     rax, [r14]
0x18001c11f  mov     rcx, r14
0x18001c122  mov     rax, [rax+38h]
0x18001c126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c12b  mov     r10, rax
0x18001c12e  lea     r8, [rbp+4Fh+var_80]
0x18001c132  lea     rdx, IID_INativeConfigurationSystem
0x18001c139  mov     rcx, [rax]
0x18001c13c  mov     rax, [rcx]
0x18001c13f  mov     rcx, r10
0x18001c142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c147  mov     ebx, eax
0x18001c149  test    eax, eax
0x18001c14b  js      short loc_18001C177
0x18001c14d  mov     rcx, [rbp+4Fh+var_80]
0x18001c151  mov     r9, rsi
0x18001c154  mov     r8, [rbp+4Fh+var_58]
0x18001c158  mov     rdx, r15
0x18001c15b  mov     [rsp+0C0h+var_98], 0
0x18001c164  mov     [rsp+0C0h+var_A0], r12
0x18001c169  mov     rax, [rcx]
0x18001c16c  mov     rax, [rax+18h]
0x18001c170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c175  mov     ebx, eax
0x18001c177  mov     rcx, [rbp+4Fh+var_80]
0x18001c17b  test    rcx, rcx
0x18001c17e  jz      short loc_18001C194
0x18001c180  mov     rax, [rcx]
0x18001c183  mov     rax, [rax+10h]
0x18001c187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c18c  mov     [rbp+4Fh+var_80], 0
0x18001c194  lea     rcx, [rbp+4Fh+var_78]
0x18001c198  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001c19e  mov     eax, ebx
0x18001c1a0  mov     rcx, [rbp+4Fh+var_40]
0x18001c1a4  xor     rcx, rsp; StackCookie
0x18001c1a7  call    __security_check_cookie
0x18001c1ac  add     rsp, 90h
0x18001c1b3  pop     r15
0x18001c1b5  pop     r14
0x18001c1b7  pop     r12
0x18001c1b9  pop     rdi
0x18001c1ba  pop     rsi
0x18001c1bb  pop     rbx
0x18001c1bc  pop     rbp
0x18001c1bd  retn
```
