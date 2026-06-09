# ATL::CRegObject::ResourceUnregister(ushort const *,uint,ushort const *)

- ea: `0x1800127d8`
- end: `0x1800128e0`
- name: `?ResourceUnregister@CRegObject@ATL@@QEAAJPEBGI0@Z`
- size: `264`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012cac`

## callees

- `0x1800099ac`
- `0x180011800`
- `0x1800127d8`
- `0x180014270`

## import_xrefs

- `msvcrt!free` at `0x1800128a2`
- `msvcrt!free` at `0x1800128b7`
- `msvcrt!free` at `0x1800128a2`
- `msvcrt!free` at `0x1800128b7`
- `msvcrt!malloc` at `0x180012824`
- `msvcrt!malloc` at `0x180012824`
- `KERNEL32!WideCharToMultiByte` at `0x180012874`
- `KERNEL32!WideCharToMultiByte` at `0x180012874`

## string_xrefs

- `0x18001284b`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ResourceUnregister(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        const unsigned __int16 *a4)
{
  _QWORD *v6; // rbx
  CHAR *lpMultiByteStr; // rdi
  _QWORD *v9; // rax
  unsigned int v10; // edi
  void *v11; // rcx
  void *v13; // rcx
  CHAR MultiByteStr[8]; // [rsp+20h] [rbp-20h] BYREF

  v6 = 0;
  if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x12, (unsigned __int64)a2) )
  {
    lpMultiByteStr = MultiByteStr;
  }
  else
  {
    v9 = malloc(0x22u);
    if ( v9 )
    {
      *v9 = 0;
      lpMultiByteStr = (CHAR *)(v9 + 2);
      v6 = v9;
    }
    else
    {
      lpMultiByteStr = 0;
    }
  }
  if ( lpMultiByteStr && (*lpMultiByteStr = 0, WideCharToMultiByte(3u, 0, L"REGISTRY", -1, lpMultiByteStr, 18, 0, 0)) )
  {
    v10 = ATL::CRegObject::RegisterFromResource(this, a2, (const char *)a3, lpMultiByteStr, 0);
    while ( v6 )
    {
      v11 = v6;
      v6 = (_QWORD *)*v6;
      free(v11);
    }
    return v10;
  }
  else
  {
    while ( v6 )
    {
      v13 = v6;
      v6 = (_QWORD *)*v6;
      free(v13);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800127d8  push    rbp
0x1800127da  push    rbx
0x1800127db  push    rsi
0x1800127dc  push    rdi
0x1800127dd  push    r14
0x1800127df  push    r15
0x1800127e1  sub     rsp, 58h
0x1800127e5  lea     rbp, [rsp+40h]
0x1800127ea  mov     rax, cs:__security_cookie
0x1800127f1  xor     rax, rbp
0x1800127f4  mov     [rbp+40h+var_40], rax
0x1800127f8  mov     r15, rcx
0x1800127fb  mov     esi, r8d
0x1800127fe  xor     ebx, ebx
0x180012800  mov     r14, rdx
0x180012803  lea     ecx, [rbx+12h]; this
0x180012806  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18001280b  test    al, al
0x18001280d  jz      short loc_18001281F
0x18001280f  mov     eax, dword ptr [rsp+80h+lpMultiByteStr]
0x180012812  sub     rsp, 20h
0x180012816  lea     rdi, [rsp+0A0h+MultiByteStr]
0x18001281b  mov     eax, [rdi]
0x18001281d  jmp     short loc_18001283D
0x18001281f  mov     ecx, 22h ; '"'; Size
0x180012824  call    cs:__imp_malloc
0x18001282a  test    rax, rax
0x18001282d  jnz     short loc_180012833
0x18001282f  xor     edi, edi
0x180012831  jmp     short loc_18001283D
0x180012833  mov     [rax], rbx
0x180012836  lea     rdi, [rax+10h]
0x18001283a  mov     rbx, rax
0x18001283d  test    rdi, rdi
0x180012840  jz      short loc_1800128BD
0x180012842  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001284b  lea     r8, WideCharStr; "REGISTRY"
0x180012852  xor     edx, edx; dwFlags
0x180012854  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x18001285d  mov     [rsp+0A0h+cbMultiByte], 12h; cbMultiByte
0x180012865  or      r9d, 0FFFFFFFFh; cchWideChar
0x180012869  mov     byte ptr [rdi], 0
0x18001286c  mov     [rsp+0A0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180012871  lea     ecx, [rdx+3]; CodePage
0x180012874  call    cs:__imp_WideCharToMultiByte
0x18001287a  test    eax, eax
0x18001287c  jz      short loc_1800128BD
0x18001287e  movzx   r8d, si; char *
0x180012882  mov     r9, rdi; char *
0x180012885  mov     rdx, r14; unsigned __int16 *
0x180012888  mov     dword ptr [rsp+0A0h+lpMultiByteStr], 0; int
0x180012890  mov     rcx, r15; this
0x180012893  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)
0x180012898  mov     edi, eax
0x18001289a  jmp     short loc_1800128A8
0x18001289c  mov     rcx, rbx; Block
0x18001289f  mov     rbx, [rbx]
0x1800128a2  call    cs:__imp_free
0x1800128a8  test    rbx, rbx
0x1800128ab  jnz     short loc_18001289C
0x1800128ad  mov     eax, edi
0x1800128af  jmp     short loc_1800128C7
0x1800128b1  mov     rcx, rbx; Block
0x1800128b4  mov     rbx, [rbx]
0x1800128b7  call    cs:__imp_free
0x1800128bd  test    rbx, rbx
0x1800128c0  jnz     short loc_1800128B1
0x1800128c2  mov     eax, 8007000Eh
0x1800128c7  mov     rcx, [rbp+40h+var_40]
0x1800128cb  xor     rcx, rbp; StackCookie
0x1800128ce  call    __security_check_cookie
0x1800128d3  lea     rsp, [rbp+18h]
0x1800128d7  pop     r15
0x1800128d9  pop     r14
0x1800128db  pop     rdi
0x1800128dc  pop     rsi
0x1800128dd  pop     rbx
0x1800128de  pop     rbp
0x1800128df  retn
```
