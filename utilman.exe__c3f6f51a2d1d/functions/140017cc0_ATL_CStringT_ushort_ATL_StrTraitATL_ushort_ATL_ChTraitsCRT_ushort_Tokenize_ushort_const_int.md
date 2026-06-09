# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x140017cc0`
- end: `0x140017de9`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140014128`

## callees

- `0x14000d678`
- `0x140013a90`
- `0x14001440c`
- `0x14001519c`
- `0x140016608`
- `0x1400171ec`
- `0x140017cc0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x140017d18`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x140017d18`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x140017d3a`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x140017d3a`

## pseudocode

```c
char **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        __int64 *a1,
        char **a2,
        const wchar_t *a3,
        int *a4)
{
  __int64 v5; // rdx
  __int64 v9; // rcx
  const wchar_t *v10; // r15
  unsigned __int64 v11; // rbp
  int v12; // r12d
  const wchar_t *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rax
  _BYTE *v17; // rdi
  __int64 v18; // rax
  __int64 Manager; // rax

  v5 = *a4;
  if ( (int)v5 < 0 )
  {
    ATL::AtlThrowImpl(-2147024809);
    __debugbreak();
  }
  if ( a3 && *a3 )
  {
    v9 = *a1;
    v10 = (const wchar_t *)(v9 + 2 * v5);
    v11 = v9 + 2LL * *(int *)(v9 - 16);
    if ( (unsigned __int64)v10 < v11 )
    {
      v12 = wcsspn(v10, a3);
      v13 = &v10[v12];
      if ( (unsigned __int64)v13 < v11 )
      {
        v14 = wcscspn(v13, a3);
        v15 = (unsigned int)(v12 + *a4);
        *a4 = v15 + v14 + 1;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
          a1,
          a2,
          v15,
          v14);
        return a2;
      }
    }
LABEL_15:
    *a4 = -1;
    Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(a1);
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a2, Manager);
    return a2;
  }
  if ( (int)v5 >= *(_DWORD *)(*a1 - 16) )
    goto LABEL_15;
  v16 = ((__int64 (*)(void))ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager)();
  v17 = (_BYTE *)(*a1 + 2LL * *a4);
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a2, v16);
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           a2,
                           v17) )
  {
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)&v17[2 * v18] );
    }
    else
    {
      LODWORD(v18) = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v17, v18);
  }
  return a2;
}

```

## disassembly

```asm
0x140017cc0  push    rbx
0x140017cc2  push    rbp
0x140017cc3  push    rsi
0x140017cc4  push    rdi
0x140017cc5  push    r12
0x140017cc7  push    r14
0x140017cc9  push    r15
0x140017ccb  sub     rsp, 20h
0x140017ccf  mov     rbx, rdx
0x140017cd2  xor     ebp, ebp
0x140017cd4  movsxd  rdx, dword ptr [r9]
0x140017cd7  mov     r14, r9
0x140017cda  mov     rsi, r8
0x140017cdd  mov     rdi, rcx
0x140017ce0  test    edx, edx
0x140017ce2  jns     short loc_140017CEF
0x140017ce4  mov     ecx, 80070057h; int
0x140017ce9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140017cee  int     3; Trap to Debugger
0x140017cef  test    rsi, rsi
0x140017cf2  jz      short loc_140017D65
0x140017cf4  cmp     [r8], bp
0x140017cf8  jz      short loc_140017D65
0x140017cfa  mov     rcx, [rcx]
0x140017cfd  movsxd  rax, dword ptr [rcx-10h]
0x140017d01  lea     r15, [rcx+rdx*2]
0x140017d05  lea     rbp, [rcx+rax*2]
0x140017d09  cmp     r15, rbp
0x140017d0c  jnb     loc_140017DBC
0x140017d12  mov     rdx, rsi; Control
0x140017d15  mov     rcx, r15; String
0x140017d18  call    cs:__imp_wcsspn
0x140017d1f  nop     dword ptr [rax+rax+00h]
0x140017d24  movsxd  rcx, eax
0x140017d27  mov     r12, rax
0x140017d2a  lea     rcx, [r15+rcx*2]; String
0x140017d2e  cmp     rcx, rbp
0x140017d31  jnb     loc_140017DBC
0x140017d37  mov     rdx, rsi; Control
0x140017d3a  call    cs:__imp_wcscspn
0x140017d41  nop     dword ptr [rax+rax+00h]
0x140017d46  mov     r8d, [r14]
0x140017d49  mov     rdx, rbx
0x140017d4c  add     r8d, r12d
0x140017d4f  mov     r9d, eax
0x140017d52  lea     ecx, [rax+1]
0x140017d55  add     ecx, r8d
0x140017d58  mov     [r14], ecx
0x140017d5b  mov     rcx, rdi
0x140017d5e  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140017d63  jmp     short loc_140017DD6
0x140017d65  mov     rax, [rcx]
0x140017d68  cmp     edx, [rax-10h]
0x140017d6b  jge     short loc_140017DBC
0x140017d6d  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x140017d72  movsxd  rdx, dword ptr [r14]
0x140017d75  mov     rcx, [rdi]
0x140017d78  lea     rdi, [rcx+rdx*2]
0x140017d7c  mov     rdx, rax
0x140017d7f  mov     rcx, rbx
0x140017d82  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x140017d87  mov     rdx, rdi
0x140017d8a  mov     rcx, rbx
0x140017d8d  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140017d92  test    al, al
0x140017d94  jnz     short loc_140017DD6
0x140017d96  test    rdi, rdi
0x140017d99  jnz     short loc_140017D9F
0x140017d9b  mov     eax, ebp
0x140017d9d  jmp     short loc_140017DAC
0x140017d9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017da3  inc     rax
0x140017da6  cmp     [rdi+rax*2], bp
0x140017daa  jnz     short loc_140017DA3
0x140017dac  mov     r8d, eax
0x140017daf  mov     rdx, rdi
0x140017db2  mov     rcx, rbx
0x140017db5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140017dba  jmp     short loc_140017DD6
0x140017dbc  mov     rcx, rdi
0x140017dbf  mov     dword ptr [r14], 0FFFFFFFFh
0x140017dc6  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x140017dcb  mov     rdx, rax
0x140017dce  mov     rcx, rbx
0x140017dd1  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x140017dd6  mov     rax, rbx
0x140017dd9  add     rsp, 20h
0x140017ddd  pop     r15
0x140017ddf  pop     r14
0x140017de1  pop     r12
0x140017de3  pop     rdi
0x140017de4  pop     rsi
0x140017de5  pop     rbp
0x140017de6  pop     rbx
0x140017de7  retn
```
