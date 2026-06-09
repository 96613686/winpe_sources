# ATL::CRegObject::ResourceRegister(ushort const *,uint,ushort const *)

- ea: `0x1800124b4`
- end: `0x1800125bc`
- name: `?ResourceRegister@CRegObject@ATL@@QEAAJPEBGI0@Z`
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
- `0x1800124b4`
- `0x180014270`

## import_xrefs

- `msvcrt!free` at `0x18001257e`
- `msvcrt!free` at `0x180012593`
- `msvcrt!free` at `0x18001257e`
- `msvcrt!free` at `0x180012593`
- `msvcrt!malloc` at `0x180012500`
- `msvcrt!malloc` at `0x180012500`
- `KERNEL32!WideCharToMultiByte` at `0x180012550`
- `KERNEL32!WideCharToMultiByte` at `0x180012550`

## string_xrefs

- `0x180012527`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ResourceRegister(
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
    v10 = ATL::CRegObject::RegisterFromResource(this, a2, (const char *)a3, lpMultiByteStr, 1);
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
0x1800124b4  push    rbp
0x1800124b6  push    rbx
0x1800124b7  push    rsi
0x1800124b8  push    rdi
0x1800124b9  push    r14
0x1800124bb  push    r15
0x1800124bd  sub     rsp, 58h
0x1800124c1  lea     rbp, [rsp+40h]
0x1800124c6  mov     rax, cs:__security_cookie
0x1800124cd  xor     rax, rbp
0x1800124d0  mov     [rbp+40h+var_40], rax
0x1800124d4  mov     r15, rcx
0x1800124d7  mov     esi, r8d
0x1800124da  xor     ebx, ebx
0x1800124dc  mov     r14, rdx
0x1800124df  lea     ecx, [rbx+12h]; this
0x1800124e2  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800124e7  test    al, al
0x1800124e9  jz      short loc_1800124FB
0x1800124eb  mov     eax, dword ptr [rsp+80h+lpMultiByteStr]
0x1800124ee  sub     rsp, 20h
0x1800124f2  lea     rdi, [rsp+0A0h+MultiByteStr]
0x1800124f7  mov     eax, [rdi]
0x1800124f9  jmp     short loc_180012519
0x1800124fb  mov     ecx, 22h ; '"'; Size
0x180012500  call    cs:__imp_malloc
0x180012506  test    rax, rax
0x180012509  jnz     short loc_18001250F
0x18001250b  xor     edi, edi
0x18001250d  jmp     short loc_180012519
0x18001250f  mov     [rax], rbx
0x180012512  lea     rdi, [rax+10h]
0x180012516  mov     rbx, rax
0x180012519  test    rdi, rdi
0x18001251c  jz      short loc_180012599
0x18001251e  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180012527  lea     r8, WideCharStr; "REGISTRY"
0x18001252e  xor     edx, edx; dwFlags
0x180012530  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x180012539  mov     [rsp+0A0h+cbMultiByte], 12h; cbMultiByte
0x180012541  or      r9d, 0FFFFFFFFh; cchWideChar
0x180012545  mov     byte ptr [rdi], 0
0x180012548  mov     [rsp+0A0h+lpMultiByteStr], rdi; lpMultiByteStr
0x18001254d  lea     ecx, [rdx+3]; CodePage
0x180012550  call    cs:__imp_WideCharToMultiByte
0x180012556  test    eax, eax
0x180012558  jz      short loc_180012599
0x18001255a  movzx   r8d, si; char *
0x18001255e  mov     r9, rdi; char *
0x180012561  mov     rdx, r14; unsigned __int16 *
0x180012564  mov     dword ptr [rsp+0A0h+lpMultiByteStr], 1; int
0x18001256c  mov     rcx, r15; this
0x18001256f  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)
0x180012574  mov     edi, eax
0x180012576  jmp     short loc_180012584
0x180012578  mov     rcx, rbx; Block
0x18001257b  mov     rbx, [rbx]
0x18001257e  call    cs:__imp_free
0x180012584  test    rbx, rbx
0x180012587  jnz     short loc_180012578
0x180012589  mov     eax, edi
0x18001258b  jmp     short loc_1800125A3
0x18001258d  mov     rcx, rbx; Block
0x180012590  mov     rbx, [rbx]
0x180012593  call    cs:__imp_free
0x180012599  test    rbx, rbx
0x18001259c  jnz     short loc_18001258D
0x18001259e  mov     eax, 8007000Eh
0x1800125a3  mov     rcx, [rbp+40h+var_40]
0x1800125a7  xor     rcx, rbp; StackCookie
0x1800125aa  call    __security_check_cookie
0x1800125af  lea     rsp, [rbp+18h]
0x1800125b3  pop     r15
0x1800125b5  pop     r14
0x1800125b7  pop     rdi
0x1800125b8  pop     rsi
0x1800125b9  pop     rbx
0x1800125ba  pop     rbp
0x1800125bb  retn
```
