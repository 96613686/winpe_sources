# MakeArray(int,VAR *)

- ea: `0x180015e00`
- end: `0x180015f12`
- name: `?MakeArray@@YAPEAUtagSAFEARRAY@@HPEAVVAR@@@Z`
- size: `274`
- prototype: `struct tagSAFEARRAY *__fastcall(signed int cDims, struct VAR *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001f0f0`

## callees

- `0x180002e60`
- `0x180015e00`
- `0x180016a60`
- `0x1800252c0`
- `0x18004237c`
- `0x180079490`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180015e9c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180015e9c`

## pseudocode

```c
struct tagSAFEARRAY *__fastcall MakeArray(signed int cDims, struct VAR *a2, const unsigned __int16 *a3, int a4)
{
  signed int i; // edi
  __int64 v7; // rsi
  struct VAR *v8; // rax
  struct tagSAFEARRAY *result; // rax
  const unsigned __int16 *v10; // r8
  int v11; // r9d
  int Default; // eax
  const unsigned __int16 *v13; // r8
  int v14; // r9d
  struct VAR *v15; // [rsp+20h] [rbp-238h] BYREF
  SAFEARRAYBOUND rgsabound[64]; // [rsp+30h] [rbp-228h] BYREF

  if ( !cDims )
    return 0;
  if ( cDims > 64 )
    RaiseErrorHr(-2146828279, 0, a3, a4);
  for ( i = 0; i < cDims; rgsabound[v7].cElements = *((_DWORD *)VAR::PvarConvert(v8, 3u) + 2) + 1 )
  {
    v7 = i;
    rgsabound[i].lLbound = 0;
    v8 = VAR::PvarCutAll((struct VAR *)((char *)a2 + 24 * (cDims - i) - 24));
    v15 = v8;
    if ( *(_WORD *)v8 == 9 )
    {
      Default = VAR::ObjGetDefault(*((struct IDispatch **)v8 + 1), &v15);
      if ( Default < 0 )
        RaiseErrorHr(Default, 0, v13, v14);
      v8 = v15;
    }
    ++i;
  }
  result = SafeArrayCreate(0xCu, cDims, rgsabound);
  if ( !result )
    RaiseErrorHr(-2146828281, 0, v10, v11);
  return result;
}

```

## disassembly

```asm
0x180015e00  mov     [rsp+arg_10], rbx
0x180015e05  push    rbp
0x180015e06  push    rsi
0x180015e07  push    rdi
0x180015e08  sub     rsp, 240h
0x180015e0f  mov     rax, cs:__security_cookie
0x180015e16  xor     rax, rsp
0x180015e19  mov     [rsp+258h+var_28], rax
0x180015e21  mov     rbp, rdx
0x180015e24  mov     ebx, ecx
0x180015e26  test    ecx, ecx
0x180015e28  jz      loc_180015ED1
0x180015e2e  cmp     ecx, 40h ; '@'
0x180015e31  jg      loc_180015EEE
0x180015e37  xor     edi, edi
0x180015e39  test    ecx, ecx
0x180015e3b  jle     short loc_180015E90
0x180015e3d  mov     eax, ebx
0x180015e3f  movsxd  rsi, edi
0x180015e42  sub     eax, edi
0x180015e44  cdqe
0x180015e46  dec     rax
0x180015e49  mov     [rsp+rsi*8+258h+rgsabound.lLbound], 0
0x180015e51  lea     rcx, [rax+rax*2]
0x180015e55  lea     rcx, ds:0[rcx*8]
0x180015e5d  add     rcx, rbp; this
0x180015e60  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x180015e65  mov     ecx, 9
0x180015e6a  mov     [rsp+258h+var_238], rax
0x180015e6f  cmp     cx, [rax]
0x180015e72  jz      short loc_180015ED5
0x180015e74  mov     edx, 3; vt
0x180015e79  mov     rcx, rax; this
0x180015e7c  call    ?PvarConvert@VAR@@QEAAPEAV1@H@Z; VAR::PvarConvert(int)
0x180015e81  inc     edi
0x180015e83  mov     ecx, [rax+8]
0x180015e86  inc     ecx
0x180015e88  mov     [rsp+rsi*8+258h+rgsabound.cElements], ecx
0x180015e8c  cmp     edi, ebx
0x180015e8e  jl      short loc_180015E3D
0x180015e90  mov     ecx, 0Ch; vt
0x180015e95  lea     r8, [rsp+258h+rgsabound]; rgsabound
0x180015e9a  mov     edx, ebx; cDims
0x180015e9c  call    cs:__imp_SafeArrayCreate
0x180015ea3  nop     dword ptr [rax+rax+00h]
0x180015ea8  test    rax, rax
0x180015eab  jz      short loc_180015F05
0x180015ead  mov     rcx, [rsp+258h+var_28]
0x180015eb5  xor     rcx, rsp; StackCookie
0x180015eb8  call    __security_check_cookie
0x180015ebd  mov     rbx, [rsp+258h+arg_10]
0x180015ec5  add     rsp, 240h
0x180015ecc  pop     rdi
0x180015ecd  pop     rsi
0x180015ece  pop     rbp
0x180015ecf  retn
0x180015ed1  xor     eax, eax
0x180015ed3  jmp     short loc_180015EAD
0x180015ed5  mov     rcx, [rax+8]; struct IDispatch *
0x180015ed9  lea     rdx, [rsp+258h+var_238]; struct VAR **
0x180015ede  call    ?ObjGetDefault@VAR@@SAJPEAUIDispatch@@PEAPEAV1@@Z; VAR::ObjGetDefault(IDispatch *,VAR * *)
0x180015ee3  test    eax, eax
0x180015ee5  js      short loc_180015EFB
0x180015ee7  mov     rax, [rsp+258h+var_238]
0x180015eec  jmp     short loc_180015E74
0x180015eee  xor     edx, edx; struct VAR *
0x180015ef0  mov     ecx, 800A0009h; int
0x180015ef5  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180015efb  xor     edx, edx; struct VAR *
0x180015efd  mov     ecx, eax; int
0x180015eff  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180015f05  xor     edx, edx; struct VAR *
0x180015f07  mov     ecx, 800A0007h; int
0x180015f0c  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
```
