# PMH_SUPPORT_FCNS::GetConfigToken(ushort const *,void * *)

- ea: `0x180003b80`
- end: `0x180003cf5`
- name: `?GetConfigToken@PMH_SUPPORT_FCNS@@UEAAJPEBGPEAPEAX@Z`
- size: `373`
- prototype: `__int64 __fastcall(PMH_SUPPORT_FCNS *this, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003b80`
- `0x1800043c8`
- `0x180004842`
- `0x180004880`
- `0x180005010`

## import_xrefs

- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003c93`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003c93`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003cc5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003cc5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003cd0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003cd0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003bfc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003bfc`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003c4d`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003c4d`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::GetConfigToken(PMH_SUPPORT_FCNS *this, const unsigned __int16 *a2, void **a3)
{
  __int64 v6; // rcx
  int UncApplicationToken; // ebx
  __int64 v8; // rcx
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v12[32]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v13; // [rsp+58h] [rbp-A8h]
  int v14; // [rsp+60h] [rbp-A0h]
  _BYTE v15[32]; // [rsp+70h] [rbp-90h] BYREF
  char *v16; // [rsp+90h] [rbp-70h]
  int v17; // [rsp+98h] [rbp-68h]
  __int16 v18; // [rsp+9Ch] [rbp-64h]
  char v19; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v20[255]; // [rsp+A1h] [rbp-5Fh] BYREF
  unsigned __int16 v21[256]; // [rsp+1A0h] [rbp+A0h] BYREF

  memset_0(v20, 0, sizeof(v20));
  v19 = 0;
  v16 = &v19;
  v17 = 256;
  v18 = 256;
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v12, v21, 0x100u);
  v6 = *((_QWORD *)this + 6);
  v10 = v14;
  v11 = 0;
  UncApplicationToken = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *, int *, unsigned int *))(*(_QWORD *)v6 + 16LL))(
                          v6,
                          a2,
                          v13,
                          &v10,
                          &v11);
  if ( UncApplicationToken == -2147024774 )
  {
    UncApplicationToken = STRU::Resize((STRU *)v12, 2 * v10);
    if ( UncApplicationToken < 0 )
      goto LABEL_7;
    v8 = *((_QWORD *)this + 6);
    v10 = v14;
    UncApplicationToken = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *, int *, unsigned int *))(*(_QWORD *)v8 + 16LL))(
                            v8,
                            a2,
                            v13,
                            &v10,
                            &v11);
  }
  if ( UncApplicationToken >= 0 )
  {
    STRU::SyncWithBuffer((STRU *)v12);
    UncApplicationToken = GetUncApplicationToken(*((struct INativeConfigurationSystem **)this + 4), v11, v13, a3);
    if ( UncApplicationToken == -2147023728 )
    {
      *a3 = 0;
      UncApplicationToken = 0;
    }
  }
LABEL_7:
  STRU::~STRU((STRU *)v12);
  BUFFER::~BUFFER((BUFFER *)v15);
  return (unsigned int)UncApplicationToken;
}

```

## disassembly

```asm
0x180003b80  push    rbp
0x180003b82  push    rbx
0x180003b83  push    rsi
0x180003b84  push    rdi
0x180003b85  push    r14
0x180003b87  lea     rbp, [rsp-2B0h]
0x180003b8f  sub     rsp, 3B0h
0x180003b96  mov     rax, cs:__security_cookie
0x180003b9d  xor     rax, rsp
0x180003ba0  mov     [rbp+2D0h+var_30], rax
0x180003ba7  mov     rdi, r8
0x180003baa  mov     r14, rdx
0x180003bad  mov     rsi, rcx
0x180003bb0  xor     edx, edx; Val
0x180003bb2  mov     r8d, 0FFh; Size
0x180003bb8  lea     rcx, [rbp+2D0h+var_32F]; void *
0x180003bbc  call    memset_0
0x180003bc1  lea     rax, [rbp+2D0h+var_330]
0x180003bc5  mov     [rbp+2D0h+var_330], 0
0x180003bc9  mov     ebx, 100h
0x180003bce  mov     [rbp+2D0h+var_340], rax
0x180003bd2  xor     edx, edx; Val
0x180003bd4  mov     [rbp+2D0h+var_338], ebx
0x180003bd7  mov     r8d, 200h; Size
0x180003bdd  mov     [rbp+2D0h+var_334], bx
0x180003be1  lea     rcx, [rbp+2D0h+var_230]; void *
0x180003be8  call    memset_0
0x180003bed  mov     r8d, ebx
0x180003bf0  lea     rdx, [rbp+2D0h+var_230]
0x180003bf7  lea     rcx, [rsp+3D0h+var_398]
0x180003bfc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003c02  mov     eax, [rsp+3D0h+var_370]
0x180003c06  lea     rdx, [rsp+3D0h+var_39C]
0x180003c0b  mov     rcx, [rsi+30h]
0x180003c0f  lea     r9, [rsp+3D0h+var_3A0]
0x180003c14  mov     r8, [rsp+3D0h+var_378]
0x180003c19  mov     [rsp+3D0h+var_3A0], eax
0x180003c1d  mov     [rsp+3D0h+var_39C], 0
0x180003c25  mov     rax, [rcx]
0x180003c28  mov     [rsp+3D0h+var_3B0], rdx
0x180003c2d  mov     rdx, r14
0x180003c30  mov     rax, [rax+10h]
0x180003c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c39  mov     ebx, eax
0x180003c3b  cmp     eax, 8007007Ah
0x180003c40  jnz     short loc_180003C8A
0x180003c42  mov     edx, [rsp+3D0h+var_3A0]
0x180003c46  lea     rcx, [rsp+3D0h+var_398]
0x180003c4b  add     edx, edx
0x180003c4d  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003c53  mov     ebx, eax
0x180003c55  test    eax, eax
0x180003c57  js      short loc_180003CC0
0x180003c59  mov     eax, [rsp+3D0h+var_370]
0x180003c5d  lea     rdx, [rsp+3D0h+var_39C]
0x180003c62  mov     rcx, [rsi+30h]
0x180003c66  lea     r9, [rsp+3D0h+var_3A0]
0x180003c6b  mov     r8, [rsp+3D0h+var_378]
0x180003c70  mov     [rsp+3D0h+var_3A0], eax
0x180003c74  mov     [rsp+3D0h+var_3B0], rdx
0x180003c79  mov     rdx, r14
0x180003c7c  mov     rax, [rcx]
0x180003c7f  mov     rax, [rax+10h]
0x180003c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c88  mov     ebx, eax
0x180003c8a  lea     rcx, [rsp+3D0h+var_398]
0x180003c8f  test    ebx, ebx
0x180003c91  js      short loc_180003CC5
0x180003c93  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003c99  mov     r8, [rsp+3D0h+var_378]; unsigned __int16 *
0x180003c9e  mov     r9, rdi; void **
0x180003ca1  mov     edx, [rsp+3D0h+var_39C]; unsigned int
0x180003ca5  mov     rcx, [rsi+20h]; struct INativeConfigurationSystem *
0x180003ca9  call    ?GetUncApplicationToken@@YAJPEAVINativeConfigurationSystem@@KPEBGPEAPEAX@Z; GetUncApplicationToken(INativeConfigurationSystem *,ulong,ushort const *,void * *)
0x180003cae  mov     ebx, eax
0x180003cb0  cmp     eax, 80070490h
0x180003cb5  jnz     short loc_180003CC0
0x180003cb7  mov     qword ptr [rdi], 0
0x180003cbe  xor     ebx, ebx
0x180003cc0  lea     rcx, [rsp+3D0h+var_398]
0x180003cc5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003ccb  lea     rcx, [rsp+3D0h+var_360]
0x180003cd0  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003cd6  mov     eax, ebx
0x180003cd8  mov     rcx, [rbp+2D0h+var_30]
0x180003cdf  xor     rcx, rsp; StackCookie
0x180003ce2  call    __security_check_cookie
0x180003ce7  add     rsp, 3B0h
0x180003cee  pop     r14
0x180003cf0  pop     rdi
0x180003cf1  pop     rsi
0x180003cf2  pop     rbx
0x180003cf3  pop     rbp
0x180003cf4  retn
```
