# CMSCContextMenu::_CreatePIDL(ushort const *)

- ea: `0x18006aae0`
- end: `0x18006ac49`
- name: `?_CreatePIDL@CMSCContextMenu@@AEAAJPEBG@Z`
- size: `361`
- prototype: `__int64 __fastcall(CMSCContextMenu *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18006a710`

## callees

- `0x180014748`
- `0x18002feb4`
- `0x18002ff5c`
- `0x180035590`
- `0x180069dc0`
- `0x18006aae0`
- `0x180078010`

## import_xrefs

- `ole32!CreateBindCtx` at `0x18006ab88`
- `ole32!CreateBindCtx` at `0x18006ab88`
- `SHELL32!SHParseDisplayName` at `0x18006abc9`
- `SHELL32!SHParseDisplayName` at `0x18006abc9`
- `SHELL32!__imp_ILFree` at `0x18006ab2b`
- `SHELL32!__imp_ILFree` at `0x18006ab2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSCContextMenu::_CreatePIDL(CMSCContextMenu *this, const unsigned __int16 *a2)
{
  HRESULT v4; // edi
  LPITEMIDLIST *v5; // rsi
  LPBC ppbc; // [rsp+30h] [rbp-38h] BYREF
  int v8; // [rsp+38h] [rbp-30h] BYREF
  PCWSTR pszName; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v10[2]; // [rsp+48h] [rbp-20h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&pszName);
  if ( !a2 )
  {
    v4 = -2147024809;
LABEL_13:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids,
        (unsigned int)v4);
    goto LABEL_16;
  }
  v5 = (LPITEMIDLIST *)((char *)this + 24);
  v10[0] = v5;
  if ( *v5 )
  {
    ILFree(*v5);
    *v5 = 0;
  }
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &pszName,
      L"%ws\\%ws",
      L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}",
      a2);
  }
  catch ( ATL::CAtlException v8 )
  {
    LODWORD(ppbc) = v8;
    if ( v8 < 0 )
    {
      v4 = (int)ppbc;
      goto LABEL_13;
    }
    v5 = (LPITEMIDLIST *)v10[0];
  }
  ppbc = 0;
  v10[0] = 16;
  v10[1] = 4096;
  v4 = CreateBindCtx(0, &ppbc);
  if ( v4 < 0 )
    goto LABEL_13;
  v4 = ((__int64 (__fastcall *)(LPBC, _QWORD *))ppbc->lpVtbl->SetBindOptions)(ppbc, v10);
  if ( v4 >= 0 )
    v4 = SHParseDisplayName(pszName, ppbc, v5, 0, 0);
  ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( v4 < 0 )
    goto LABEL_13;
LABEL_16:
  ATL::CStringData::Release((ATL::CStringData *)(pszName - 12));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006aae0  mov     [rsp+arg_10], rsi
0x18006aae5  push    rdi
0x18006aae6  sub     rsp, 60h
0x18006aaea  mov     rax, cs:__security_cookie
0x18006aaf1  xor     rax, rsp
0x18006aaf4  mov     [rsp+68h+var_10], rax
0x18006aaf9  mov     rdi, rdx
0x18006aafc  mov     rsi, rcx
0x18006aaff  lea     rcx, [rsp+68h+pszName]
0x18006ab04  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18006ab09  nop
0x18006ab0a  test    rdi, rdi
0x18006ab0d  jnz     short loc_18006AB19
0x18006ab0f  mov     edi, 80070057h
0x18006ab14  jmp     loc_18006ABEC
0x18006ab19  add     rsi, 18h
0x18006ab1d  mov     [rsp+68h+var_20], rsi
0x18006ab22  cmp     qword ptr [rsi], 0
0x18006ab26  jz      short loc_18006AB38
0x18006ab28  mov     rcx, [rsi]; pidl
0x18006ab2b  call    cs:__imp_ILFree
0x18006ab31  mov     qword ptr [rsi], 0
0x18006ab38  mov     r9, rdi
0x18006ab3b  lea     r8, a20d04fe03aea10; "::{20D04FE0-3AEA-1069-A2D8-08002B30309D"...
0x18006ab42  lea     rdx, aWsWs_0; "%ws\\%ws"
0x18006ab49  lea     rcx, [rsp+68h+pszName]
0x18006ab4e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18006ab53  nop
0x18006ab54  jmp     short loc_18006AB66
0x18006ab56  cmp     [rsp+68h+var_30], 0
0x18006ab5b  jl      loc_18006ABE8
0x18006ab61  mov     rsi, [rsp+68h+var_20]
0x18006ab66  mov     [rsp+68h+ppbc], 0
0x18006ab6f  mov     [rsp+68h+var_20], 10h
0x18006ab78  mov     [rsp+68h+var_18], 1000h
0x18006ab81  lea     rdx, [rsp+68h+ppbc]; ppbc
0x18006ab86  xor     ecx, ecx; reserved
0x18006ab88  call    cs:__imp_CreateBindCtx
0x18006ab8e  mov     edi, eax
0x18006ab90  test    eax, eax
0x18006ab92  js      short loc_18006ABEC
0x18006ab94  mov     rcx, [rsp+68h+ppbc]
0x18006ab99  mov     rax, [rcx]
0x18006ab9c  lea     rdx, [rsp+68h+var_20]
0x18006aba1  mov     rax, [rax+30h]
0x18006aba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abaa  mov     edi, eax
0x18006abac  test    eax, eax
0x18006abae  js      short loc_18006ABD1
0x18006abb0  mov     [rsp+68h+psfgaoOut], 0; psfgaoOut
0x18006abb9  xor     r9d, r9d; sfgaoIn
0x18006abbc  mov     r8, rsi; ppidl
0x18006abbf  mov     rdx, [rsp+68h+ppbc]; pbc
0x18006abc4  mov     rcx, [rsp+68h+pszName]; pszName
0x18006abc9  call    cs:__imp_SHParseDisplayName
0x18006abcf  mov     edi, eax
0x18006abd1  mov     rcx, [rsp+68h+ppbc]
0x18006abd6  mov     rax, [rcx]
0x18006abd9  mov     rax, [rax+10h]
0x18006abdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abe2  test    edi, edi
0x18006abe4  jns     short loc_18006AC1E
0x18006abe6  jmp     short loc_18006ABEC
0x18006abe8  mov     edi, dword ptr [rsp+68h+ppbc]
0x18006abec  lea     rax, WPP_GLOBAL_Control
0x18006abf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006abfa  cmp     rcx, rax
0x18006abfd  jz      short loc_18006AC1E
0x18006abff  test    byte ptr [rcx+1Ch], 2
0x18006ac03  jz      short loc_18006AC1E
0x18006ac05  mov     edx, 1Dh
0x18006ac0a  mov     r9d, edi
0x18006ac0d  lea     r8, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids
0x18006ac14  mov     rcx, [rcx+10h]
0x18006ac18  call    WPP_SF_d
0x18006ac1d  nop
0x18006ac1e  mov     rcx, [rsp+68h+pszName]
0x18006ac23  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18006ac27  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18006ac2c  mov     eax, edi
0x18006ac2e  mov     rcx, [rsp+68h+var_10]
0x18006ac33  xor     rcx, rsp; StackCookie
0x18006ac36  call    __security_check_cookie
0x18006ac3b  mov     rsi, [rsp+68h+arg_10]
0x18006ac43  add     rsp, 60h
0x18006ac47  pop     rdi
0x18006ac48  retn
```
