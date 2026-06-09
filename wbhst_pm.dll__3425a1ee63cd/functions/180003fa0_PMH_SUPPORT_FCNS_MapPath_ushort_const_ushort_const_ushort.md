# PMH_SUPPORT_FCNS::MapPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180003fa0`
- end: `0x180004089`
- name: `?MapPath@PMH_SUPPORT_FCNS@@UEAAJPEBG0PEAPEAG@Z`
- size: `233`
- prototype: `__int64 __fastcall(PMH_SUPPORT_FCNS *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003fa0`
- `0x1800045fc`
- `0x180004842`
- `0x180004880`
- `0x180005010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000404e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000404e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004067`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004067`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::MapPath(
        PMH_SUPPORT_FCNS *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 v8; // rcx
  int v9; // ebx
  unsigned __int16 *v10; // rax
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[32]; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-A8h]
  int v15; // [rsp+60h] [rbp-A0h]
  __int16 v16; // [rsp+64h] [rbp-9Ch]
  char v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[255]; // [rsp+71h] [rbp-8Fh] BYREF

  memset_0(v18, 0, sizeof(v18));
  v8 = *((_QWORD *)this + 6);
  psz = (OLECHAR *)&v17;
  v17 = 0;
  v15 = 256;
  v16 = 256;
  v12 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v8 + 16LL))(
         v8,
         a2,
         0,
         0,
         &v12);
  if ( v9 >= 0 )
  {
    v9 = MapPath(*((struct INativeConfigurationSystem **)this + 4), v12, a3, (struct BUFFER *)v13);
    if ( v9 >= 0 )
    {
      v10 = SysAllocString(psz);
      *a4 = v10;
      if ( !v10 )
        v9 = -2147024888;
    }
  }
  BUFFER::~BUFFER((BUFFER *)v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003fa0  push    rbp
0x180003fa2  push    rbx
0x180003fa3  push    rsi
0x180003fa4  push    rdi
0x180003fa5  push    r14
0x180003fa7  lea     rbp, [rsp-80h]
0x180003fac  sub     rsp, 180h
0x180003fb3  mov     rax, cs:__security_cookie
0x180003fba  xor     rax, rsp
0x180003fbd  mov     [rbp+0A0h+var_30], rax
0x180003fc1  mov     rsi, r8
0x180003fc4  mov     rbx, rdx
0x180003fc7  mov     rdi, rcx
0x180003fca  xor     edx, edx; Val
0x180003fcc  mov     r8d, 0FFh; Size
0x180003fd2  lea     rcx, [rsp+1A0h+var_12F]; void *
0x180003fd7  mov     r14, r9
0x180003fda  call    memset_0
0x180003fdf  mov     rcx, [rdi+30h]
0x180003fe3  lea     rax, [rsp+1A0h+var_130]
0x180003fe8  mov     [rsp+1A0h+psz], rax
0x180003fed  lea     rdx, [rsp+1A0h+var_170]
0x180003ff2  mov     [rsp+1A0h+var_130], 0
0x180003ff7  xor     r9d, r9d
0x180003ffa  mov     [rsp+1A0h+var_140], 100h
0x180004002  xor     r8d, r8d
0x180004005  mov     [rsp+1A0h+var_13C], 100h
0x18000400c  mov     [rsp+1A0h+var_170], 0
0x180004014  mov     rax, [rcx]
0x180004017  mov     [rsp+1A0h+var_180], rdx
0x18000401c  mov     rdx, rbx
0x18000401f  mov     rax, [rax+10h]
0x180004023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004028  mov     ebx, eax
0x18000402a  test    eax, eax
0x18000402c  js      short loc_180004062
0x18000402e  mov     edx, [rsp+1A0h+var_170]; unsigned int
0x180004032  lea     r9, [rsp+1A0h+var_168]; struct BUFFER *
0x180004037  mov     rcx, [rdi+20h]; struct INativeConfigurationSystem *
0x18000403b  mov     r8, rsi; unsigned __int16 *
0x18000403e  call    ?MapPath@@YAJPEAVINativeConfigurationSystem@@KPEBGPEAVBUFFER@@@Z; MapPath(INativeConfigurationSystem *,ulong,ushort const *,BUFFER *)
0x180004043  mov     ebx, eax
0x180004045  test    eax, eax
0x180004047  js      short loc_180004062
0x180004049  mov     rcx, [rsp+1A0h+psz]; psz
0x18000404e  call    cs:__imp_SysAllocString
0x180004054  test    rax, rax
0x180004057  mov     [r14], rax
0x18000405a  mov     ecx, 80070008h
0x18000405f  cmovz   ebx, ecx
0x180004062  lea     rcx, [rsp+1A0h+var_168]
0x180004067  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000406d  mov     eax, ebx
0x18000406f  mov     rcx, [rbp+0A0h+var_30]
0x180004073  xor     rcx, rsp; StackCookie
0x180004076  call    __security_check_cookie
0x18000407b  add     rsp, 180h
0x180004082  pop     r14
0x180004084  pop     rdi
0x180004085  pop     rsi
0x180004086  pop     rbx
0x180004087  pop     rbp
0x180004088  retn
```
