# ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::NewNode(ATL::CComBSTR const &,uint,uint)

- ea: `0x180016080`
- end: `0x180016188`
- name: `?NewNode@?$CAtlMap@VCComBSTR@ATL@@_NV?$CElementTraits@VCComBSTR@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@AEAAPEAVCNode@12@AEBVCComBSTR@2@II@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x180016080`
- `0x1800194ec`
- `0x18002eeb4`
- `0x18002f380`
- `0x18002f56c`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x18001610d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001610d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180016118`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180016118`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::NewNode(
        __int64 a1,
        BSTR *a2,
        unsigned int a3,
        int a4)
{
  __int64 v5; // r14
  struct ATL::CAtlPlex *v8; // rax
  int v9; // r8d
  char *i; // rdx
  __int64 v11; // rbx
  BSTR v12; // rax
  UINT v13; // eax
  unsigned __int64 v14; // rdx
  unsigned int v15; // eax

  v5 = a3;
  if ( !*(_QWORD *)(a1 + 64) )
  {
    v8 = ATL::CAtlPlex::Create((struct ATL::CAtlPlex **)(a1 + 56));
    if ( !v8 )
      goto LABEL_12;
    v9 = *(_DWORD *)(a1 + 52) - 1;
    for ( i = (char *)v8 + 32 * (unsigned int)v9 + 8; v9 >= 0; --v9 )
    {
      *((_QWORD *)i + 2) = *(_QWORD *)(a1 + 64);
      *(_QWORD *)(a1 + 64) = i;
      i -= 32;
    }
  }
  v11 = *(_QWORD *)(a1 + 64);
  if ( !v11 )
    ATL::AtlThrowImpl(-2147467259);
  *(_QWORD *)(a1 + 64) = *(_QWORD *)(v11 + 16);
  if ( *a2 )
  {
    v13 = SysStringByteLen(*a2);
    v12 = SysAllocStringByteLen((LPCSTR)*a2, v13);
  }
  else
  {
    v12 = 0;
  }
  *(_QWORD *)v11 = v12;
  if ( *a2 && !v12 )
LABEL_12:
    ATL::AtlThrowImpl(-2147024882);
  *(_DWORD *)(v11 + 24) = a4;
  ++*(_QWORD *)(a1 + 8);
  *(_QWORD *)(v11 + 16) = *(_QWORD *)(8 * v5 + *(_QWORD *)a1);
  *(_QWORD *)(8 * v5 + *(_QWORD *)a1) = v11;
  v14 = *(_QWORD *)(a1 + 8);
  if ( v14 > *(_QWORD *)(a1 + 32) && !*(_DWORD *)(a1 + 48) )
  {
    v15 = ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::PickSize(
            a1,
            v14);
    ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::Rehash(a1, v15);
  }
  return v11;
}

```

## disassembly

```asm
0x180016080  push    rbx
0x180016082  push    rbp
0x180016083  push    rsi
0x180016084  push    rdi
0x180016085  push    r14
0x180016087  sub     rsp, 20h
0x18001608b  cmp     qword ptr [rcx+40h], 0
0x180016090  mov     ebp, r9d
0x180016093  mov     r14d, r8d
0x180016096  mov     rsi, rdx
0x180016099  mov     rdi, rcx
0x18001609c  jnz     short loc_1800160E5
0x18001609e  mov     edx, [rcx+34h]; unsigned __int64
0x1800160a1  mov     r8d, 20h ; ' '; unsigned __int64
0x1800160a7  add     rcx, 38h ; '8'; struct ATL::CAtlPlex **
0x1800160ab  call    ?Create@CAtlPlex@ATL@@SAPEAU12@AEAPEAU12@_K1@Z; ATL::CAtlPlex::Create(ATL::CAtlPlex * &,unsigned __int64,unsigned __int64)
0x1800160b0  test    rax, rax
0x1800160b3  jz      short loc_18001612C
0x1800160b5  mov     r8d, [rdi+34h]
0x1800160b9  dec     r8d
0x1800160bc  mov     edx, r8d
0x1800160bf  shl     rdx, 5
0x1800160c3  add     rdx, 8
0x1800160c7  add     rdx, rax
0x1800160ca  test    r8d, r8d
0x1800160cd  js      short loc_1800160E5
0x1800160cf  mov     rax, [rdi+40h]
0x1800160d3  mov     [rdx+10h], rax
0x1800160d7  mov     [rdi+40h], rdx
0x1800160db  sub     rdx, 20h ; ' '
0x1800160df  sub     r8d, 1
0x1800160e3  jns     short loc_1800160CF
0x1800160e5  mov     rbx, [rdi+40h]
0x1800160e9  test    rbx, rbx
0x1800160ec  jnz     short loc_1800160F9
0x1800160ee  mov     ecx, 80004005h; int
0x1800160f3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800160f9  mov     rax, [rbx+10h]
0x1800160fd  mov     [rdi+40h], rax
0x180016101  mov     rcx, [rsi]; bstr
0x180016104  test    rcx, rcx
0x180016107  jnz     short loc_18001610D
0x180016109  xor     eax, eax
0x18001610b  jmp     short loc_18001611E
0x18001610d  call    cs:__imp_SysStringByteLen
0x180016113  mov     rcx, [rsi]; psz
0x180016116  mov     edx, eax; len
0x180016118  call    cs:__imp_SysAllocStringByteLen
0x18001611e  mov     [rbx], rax
0x180016121  cmp     qword ptr [rsi], 0
0x180016125  jz      short loc_180016137
0x180016127  test    rax, rax
0x18001612a  jnz     short loc_180016137
0x18001612c  mov     ecx, 8007000Eh; int
0x180016131  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180016137  mov     [rbx+18h], ebp
0x18001613a  lea     rdx, ds:0[r14*8]
0x180016142  inc     qword ptr [rdi+8]
0x180016146  mov     rax, [rdi]
0x180016149  mov     rcx, [rdx+rax]
0x18001614d  mov     [rbx+10h], rcx
0x180016151  mov     rax, [rdi]
0x180016154  mov     [rdx+rax], rbx
0x180016158  mov     rdx, [rdi+8]
0x18001615c  cmp     rdx, [rdi+20h]
0x180016160  jbe     short loc_18001617A
0x180016162  cmp     dword ptr [rdi+30h], 0
0x180016166  jnz     short loc_18001617A
0x180016168  mov     rcx, rdi
0x18001616b  call    ?PickSize@?$CAtlMap@U_GUID@@PEAUHDEVQUERY__@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAUHDEVQUERY__@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::PickSize(unsigned __int64)
0x180016170  mov     edx, eax
0x180016172  mov     rcx, rdi
0x180016175  call    ?Rehash@?$CAtlMap@VCComBSTR@ATL@@_NV?$CElementTraits@VCComBSTR@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@QEAAXI@Z; ATL::CAtlMap<ATL::CComBSTR,bool,ATL::CElementTraits<ATL::CComBSTR>,ATL::CElementTraits<bool>>::Rehash(uint)
0x18001617a  mov     rax, rbx
0x18001617d  add     rsp, 20h
0x180016181  pop     r14
0x180016183  pop     rdi
0x180016184  pop     rsi
0x180016185  pop     rbp
0x180016186  pop     rbx
0x180016187  retn
```
