# MakeArray(int,VAR *)

- ea: `0x18001bd44`
- end: `0x18001be4f`
- name: `?MakeArray@@YAPEAUtagSAFEARRAY@@HPEAVVAR@@@Z`
- size: `267`
- prototype: `struct tagSAFEARRAY *__fastcall(signed int cDims, struct VAR *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180023ad0`

## callees

- `0x1800040d4`
- `0x18001bd20`
- `0x18001bd44`
- `0x18001c950`
- `0x180040cc4`
- `0x1800767a0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001bde0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001bde0`

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
0x18001bd44  mov     [rsp+arg_10], rbx
0x18001bd49  push    rbp
0x18001bd4a  push    rsi
0x18001bd4b  push    rdi
0x18001bd4c  sub     rsp, 240h
0x18001bd53  mov     rax, cs:__security_cookie
0x18001bd5a  xor     rax, rsp
0x18001bd5d  mov     [rsp+258h+var_28], rax
0x18001bd65  mov     rbp, rdx
0x18001bd68  mov     ebx, ecx
0x18001bd6a  test    ecx, ecx
0x18001bd6c  jz      loc_18001BE0E
0x18001bd72  cmp     ecx, 40h ; '@'
0x18001bd75  jg      loc_18001BE2B
0x18001bd7b  xor     edi, edi
0x18001bd7d  test    ecx, ecx
0x18001bd7f  jle     short loc_18001BDD4
0x18001bd81  mov     eax, ebx
0x18001bd83  movsxd  rsi, edi
0x18001bd86  sub     eax, edi
0x18001bd88  cdqe
0x18001bd8a  dec     rax
0x18001bd8d  mov     [rsp+rsi*8+258h+rgsabound.lLbound], 0
0x18001bd95  lea     rcx, [rax+rax*2]
0x18001bd99  lea     rcx, ds:0[rcx*8]
0x18001bda1  add     rcx, rbp; this
0x18001bda4  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18001bda9  mov     ecx, 9
0x18001bdae  mov     [rsp+258h+var_238], rax
0x18001bdb3  cmp     cx, [rax]
0x18001bdb6  jz      short loc_18001BE12
0x18001bdb8  mov     edx, 3; vt
0x18001bdbd  mov     rcx, rax; this
0x18001bdc0  call    ?PvarConvert@VAR@@QEAAPEAV1@H@Z; VAR::PvarConvert(int)
0x18001bdc5  inc     edi
0x18001bdc7  mov     ecx, [rax+8]
0x18001bdca  inc     ecx
0x18001bdcc  mov     [rsp+rsi*8+258h+rgsabound.cElements], ecx
0x18001bdd0  cmp     edi, ebx
0x18001bdd2  jl      short loc_18001BD81
0x18001bdd4  mov     ecx, 0Ch; vt
0x18001bdd9  lea     r8, [rsp+258h+rgsabound]; rgsabound
0x18001bdde  mov     edx, ebx; cDims
0x18001bde0  call    cs:__imp_SafeArrayCreate
0x18001bde6  test    rax, rax
0x18001bde9  jz      short loc_18001BE42
0x18001bdeb  mov     rcx, [rsp+258h+var_28]
0x18001bdf3  xor     rcx, rsp; StackCookie
0x18001bdf6  call    __security_check_cookie
0x18001bdfb  mov     rbx, [rsp+258h+arg_10]
0x18001be03  add     rsp, 240h
0x18001be0a  pop     rdi
0x18001be0b  pop     rsi
0x18001be0c  pop     rbp
0x18001be0d  retn
0x18001be0e  xor     eax, eax
0x18001be10  jmp     short loc_18001BDEB
0x18001be12  mov     rcx, [rax+8]; struct IDispatch *
0x18001be16  lea     rdx, [rsp+258h+var_238]; struct VAR **
0x18001be1b  call    ?ObjGetDefault@VAR@@SAJPEAUIDispatch@@PEAPEAV1@@Z; VAR::ObjGetDefault(IDispatch *,VAR * *)
0x18001be20  test    eax, eax
0x18001be22  js      short loc_18001BE38
0x18001be24  mov     rax, [rsp+258h+var_238]
0x18001be29  jmp     short loc_18001BDB8
0x18001be2b  xor     edx, edx; struct VAR *
0x18001be2d  mov     ecx, 800A0009h; int
0x18001be32  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001be38  xor     edx, edx; struct VAR *
0x18001be3a  mov     ecx, eax; int
0x18001be3c  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001be42  xor     edx, edx; struct VAR *
0x18001be44  mov     ecx, 800A0007h; int
0x18001be49  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
```
