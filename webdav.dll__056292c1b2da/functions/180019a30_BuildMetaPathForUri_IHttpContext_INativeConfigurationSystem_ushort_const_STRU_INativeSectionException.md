# BuildMetaPathForUri(IHttpContext *,INativeConfigurationSystem *,ushort const *,STRU *,INativeSectionException * *)

- ea: `0x180019a30`
- end: `0x180019bbe`
- name: `?BuildMetaPathForUri@@YAJPEAVIHttpContext@@PEAVINativeConfigurationSystem@@PEBGPEAVSTRU@@PEAPEAVINativeSectionException@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct INativeConfigurationSystem *, const unsigned __int16 *, struct STRU *, struct INativeSectionException **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800058e4`
- `0x180011514`
- `0x180011cf8`

## callees

- `0x180019a30`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180019b8e`
- `msvcrt!_wcsupr` at `0x180019b8e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180019b0a`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180019b0a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180019a7f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180019a7f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180019a67`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180019a67`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019b98`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019b98`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180019b85`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180019b85`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180019ab7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180019ace`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180019ab7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180019ace`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180019ae6`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180019ae6`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180019b51`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180019b51`

## pseudocode

```c
__int64 __fastcall BuildMetaPathForUri(
        struct IHttpContext *a1,
        struct INativeConfigurationSystem *a2,
        const unsigned __int16 *a3,
        struct STRU *a4,
        struct INativeSectionException **a5)
{
  int v9; // ebx
  __int64 v10; // rax
  const unsigned __int16 *v11; // rax
  int v12; // eax
  wchar_t **v13; // rdi
  __int64 v14; // r8
  int v16; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v17[32]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v18; // [rsp+58h] [rbp-28h]
  int v19; // [rsp+68h] [rbp-18h]

  STRU::STRU((STRU *)v17);
  v16 = 0;
  v9 = STRU::Copy((STRU *)v17, L"MACHINE/WEBROOT/APPHOST/");
  if ( v9 < 0 )
    goto LABEL_15;
  v10 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a1)(a1);
  v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v9 = STRU::Append((STRU *)v17, v11);
  if ( v9 < 0 )
    goto LABEL_15;
  v9 = STRU::Append((STRU *)v17, a3);
  if ( v9 < 0 )
    goto LABEL_15;
  while ( *(_WORD *)(v18 + 2LL * (unsigned int)(v19 - 1)) == 47 )
    STRU::SetLen((STRU *)v17, v19 - 1);
  if ( a2 )
  {
    v13 = (wchar_t **)((char *)a4 + 32);
    v14 = *((_QWORD *)a4 + 4);
    v16 = *((_DWORD *)a4 + 10) >> 1;
    v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, __int64, __int64, int *, struct INativeSectionException **))(*(_QWORD *)a2 + 32LL))(
           a2,
           v18,
           v14,
           &v16,
           a5);
    if ( v9 != -2147024774 )
      goto LABEL_13;
    v9 = STRU::Resize(a4, 2 * v16);
    if ( v9 < 0 )
      goto LABEL_15;
    v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, __int64, wchar_t *, int *, struct INativeSectionException **))(*(_QWORD *)a2 + 32LL))(
            a2,
            v18,
            *v13,
            &v16,
            a5);
  }
  else
  {
    v12 = STRU::Copy(a4, (const struct STRU *)v17);
    v13 = (wchar_t **)((char *)a4 + 32);
  }
  v9 = v12;
LABEL_13:
  if ( v9 >= 0 )
  {
    STRU::SyncWithBuffer(a4);
    _wcsupr(*v13);
  }
LABEL_15:
  STRU::~STRU((STRU *)v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180019a30  push    rbp
0x180019a32  push    rbx
0x180019a33  push    rsi
0x180019a34  push    rdi
0x180019a35  push    r12
0x180019a37  push    r14
0x180019a39  push    r15
0x180019a3b  mov     rbp, rsp
0x180019a3e  sub     rsp, 80h
0x180019a45  mov     rax, cs:__security_cookie
0x180019a4c  xor     rax, rsp
0x180019a4f  mov     [rbp+var_10], rax
0x180019a53  mov     r15, [rbp+arg_20]
0x180019a57  mov     r12, rcx
0x180019a5a  lea     rcx, [rbp+var_48]
0x180019a5e  mov     rsi, r9
0x180019a61  mov     rdi, r8
0x180019a64  mov     r14, rdx
0x180019a67  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180019a6d  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x180019a74  mov     [rbp+var_50], 0
0x180019a7b  lea     rcx, [rbp+var_48]
0x180019a7f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180019a85  mov     ebx, eax
0x180019a87  test    eax, eax
0x180019a89  js      loc_180019B94
0x180019a8f  mov     rax, [r12]
0x180019a93  mov     rcx, r12
0x180019a96  mov     rax, [rax]
0x180019a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a9e  mov     r8, rax
0x180019aa1  mov     rcx, [rax]
0x180019aa4  mov     rax, [rcx+8]
0x180019aa8  mov     rcx, r8
0x180019aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ab0  mov     rdx, rax
0x180019ab3  lea     rcx, [rbp+var_48]
0x180019ab7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180019abd  mov     ebx, eax
0x180019abf  test    eax, eax
0x180019ac1  js      loc_180019B94
0x180019ac7  mov     rdx, rdi
0x180019aca  lea     rcx, [rbp+var_48]
0x180019ace  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180019ad4  mov     ebx, eax
0x180019ad6  test    eax, eax
0x180019ad8  js      loc_180019B94
0x180019ade  jmp     short loc_180019AEC
0x180019ae0  dec     edx
0x180019ae2  lea     rcx, [rbp+var_48]
0x180019ae6  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180019aec  mov     edx, [rbp+var_18]
0x180019aef  mov     r10, [rbp+var_28]
0x180019af3  lea     eax, [rdx-1]
0x180019af6  cmp     word ptr [r10+rax*2], 2Fh ; '/'
0x180019afc  jz      short loc_180019AE0
0x180019afe  test    r14, r14
0x180019b01  jnz     short loc_180019B16
0x180019b03  lea     rdx, [rbp+var_48]
0x180019b07  mov     rcx, rsi
0x180019b0a  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180019b10  lea     rdi, [rsi+20h]
0x180019b14  jmp     short loc_180019B7C
0x180019b16  mov     eax, [rsi+28h]
0x180019b19  lea     rdi, [rsi+20h]
0x180019b1d  mov     r8, [rdi]
0x180019b20  lea     r9, [rbp+var_50]
0x180019b24  shr     eax, 1
0x180019b26  mov     rdx, r10
0x180019b29  mov     [rbp+var_50], eax
0x180019b2c  mov     rcx, r14
0x180019b2f  mov     rax, [r14]
0x180019b32  mov     [rsp+80h+var_60], r15
0x180019b37  mov     rax, [rax+20h]
0x180019b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b40  mov     ebx, eax
0x180019b42  cmp     eax, 8007007Ah
0x180019b47  jnz     short loc_180019B7E
0x180019b49  mov     edx, [rbp+var_50]
0x180019b4c  mov     rcx, rsi
0x180019b4f  add     edx, edx
0x180019b51  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180019b57  mov     ebx, eax
0x180019b59  test    eax, eax
0x180019b5b  js      short loc_180019B94
0x180019b5d  mov     rax, [r14]
0x180019b60  lea     r9, [rbp+var_50]
0x180019b64  mov     r8, [rdi]
0x180019b67  mov     rcx, r14
0x180019b6a  mov     rdx, [rbp+var_28]
0x180019b6e  mov     [rsp+80h+var_60], r15
0x180019b73  mov     rax, [rax+20h]
0x180019b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b7c  mov     ebx, eax
0x180019b7e  test    ebx, ebx
0x180019b80  js      short loc_180019B94
0x180019b82  mov     rcx, rsi
0x180019b85  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180019b8b  mov     rcx, [rdi]; String
0x180019b8e  call    cs:__imp__wcsupr
0x180019b94  lea     rcx, [rbp+var_48]
0x180019b98  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180019b9e  mov     eax, ebx
0x180019ba0  mov     rcx, [rbp+var_10]
0x180019ba4  xor     rcx, rsp; StackCookie
0x180019ba7  call    __security_check_cookie
0x180019bac  add     rsp, 80h
0x180019bb3  pop     r15
0x180019bb5  pop     r14
0x180019bb7  pop     r12
0x180019bb9  pop     rdi
0x180019bba  pop     rsi
0x180019bbb  pop     rbx
0x180019bbc  pop     rbp
0x180019bbd  retn
```
