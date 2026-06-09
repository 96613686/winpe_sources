# JSONParserLib::JSONUtils::CreateNode(IMemObj *,JSONParserLib::JSON_DATATYPE,bool,ulong,CAutoP<JSONParserLib::JSONNode> &)

- ea: `0x100831d50`
- end: `0x100831f34`
- name: `?CreateNode@JSONUtils@JSONParserLib@@SAKPEAVIMemObj@@W4JSON_DATATYPE@2@_NKAEAV?$CAutoP@VJSONNode@JSONParserLib@@@@@Z`
- size: `484`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10082fe90`
- `0x1008303b0`
- `0x100830750`
- `0x100830bd0`

## callees

- `0x10082c530`
- `0x100831d50`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831da5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831e11`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831e9a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831da5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831e11`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100831e9a`

## string_xrefs

- `0x100831d94`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Utils.cpp`
- `0x100831dff`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Utils.cpp`
- `0x100831e89`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JSONParserLib::JSONUtils::CreateNode(
        struct IMemObj *a1,
        int a2,
        char a3,
        int a4,
        JSONParserLib::JSONNode **a5)
{
  unsigned int v9; // edi
  JSONParserLib::JSONNode *v10; // rax
  JSONParserLib::JSONNode *v11; // rsi
  JSONParserLib::JSONNode *v12; // rbx
  _DWORD *v13; // rcx
  _QWORD *v14; // rax
  JSONParserLib::JSONNode *v15; // rcx

  v9 = 0;
  v10 = (JSONParserLib::JSONNode *)operator new(
                                     0x20u,
                                     a1,
                                     1,
                                     "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_Utils.cpp",
                                     290,
                                     6u);
  v11 = v10;
  if ( v10 )
  {
    *(_OWORD *)v10 = 0;
    *((_OWORD *)v10 + 1) = 0;
    *((_QWORD *)v10 + 3) = a1;
  }
  else
  {
    v11 = 0;
  }
  v12 = v11;
  if ( !v11 )
  {
    v9 = 1;
    goto LABEL_22;
  }
  if ( a2 == 2 )
  {
    v13 = operator new(0x38u, a1, 1, "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_Utils.cpp", 302, 6u);
    if ( v13 )
    {
      *(_QWORD *)v13 = &JSONParserLib::CDynamicBuffer<void *>::`vftable';
      v13[2] = 5;
      v13[3] = 5;
      *((_QWORD *)v13 + 2) = 0;
      *((_QWORD *)v13 + 3) = 0;
      v13[8] = v13[3];
      *((_QWORD *)v13 + 5) = a1;
      *((_BYTE *)v13 + 48) = a3;
      v13[9] = v13[2];
    }
    else
    {
      v13 = 0;
    }
    *((_QWORD *)v11 + 2) = v13;
    if ( !v13 )
    {
      v9 = 1;
      goto LABEL_22;
    }
  }
  else if ( a2 == 1 )
  {
    v14 = operator new(0x20u, a1, 1, "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_Utils.cpp", 312, 6u);
    if ( v14 )
    {
      *v14 = &JSONParserLib::CMapTemplate<wchar_t *,void *,JSONParserLib::CMapStringKeyHelper>::`vftable';
      v14[1] = 0;
      *((_DWORD *)v14 + 4) = 0;
      *((_BYTE *)v14 + 20) = 0;
      v14[3] = a1;
    }
    else
    {
      v14 = 0;
    }
    *((_QWORD *)v11 + 2) = v14;
    if ( !v14 )
    {
      v9 = 1;
      goto LABEL_22;
    }
  }
  *(_DWORD *)v11 = a2;
  *((_DWORD *)v11 + 1) = a4;
  v12 = 0;
  v15 = *a5;
  if ( *a5 != v11 && v15 )
    JSONParserLib::JSONNode::`scalar deleting destructor'(v15, 1u);
  *a5 = v11;
LABEL_22:
  if ( v12 )
    JSONParserLib::JSONNode::`scalar deleting destructor'(v12, 1u);
  return v9;
}

```

## disassembly

```asm
0x100831d50  mov     rax, rsp
0x100831d53  mov     [rax+8], rcx
0x100831d57  push    rsi
0x100831d58  push    rdi
0x100831d59  push    r12
0x100831d5b  push    r14
0x100831d5d  push    r15
0x100831d5f  sub     rsp, 50h
0x100831d63  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x100831d6b  mov     [rax+10h], rbx
0x100831d6f  mov     [rax+18h], rbp
0x100831d73  mov     r12d, r9d
0x100831d76  movzx   r15d, r8b
0x100831d7a  mov     r14d, edx
0x100831d7d  mov     rbp, rcx
0x100831d80  xor     edi, edi
0x100831d82  mov     dword ptr [rax-48h], 122h
0x100831d89  mov     byte ptr [rax-50h], 6
0x100831d8d  mov     dword ptr [rax-58h], 122h
0x100831d94  lea     r9, aSqlNtdbmsStore_4; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x100831d9b  lea     r8d, [rdi+1]
0x100831d9f  mov     rdx, rcx
0x100831da2  lea     ecx, [rdi+20h]
0x100831da5  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100831dab  mov     rsi, rax
0x100831dae  mov     [rsp+78h+var_40], rax
0x100831db3  test    rax, rax
0x100831db6  jz      short loc_100831DC8
0x100831db8  xorps   xmm0, xmm0
0x100831dbb  movups  xmmword ptr [rax], xmm0
0x100831dbe  movups  xmmword ptr [rax+10h], xmm0
0x100831dc2  mov     [rax+18h], rbp
0x100831dc6  jmp     short loc_100831DCB
0x100831dc8  mov     rsi, rdi
0x100831dcb  mov     rbx, rsi
0x100831dce  mov     [rsp+78h+var_40], rbx
0x100831dd3  test    rsi, rsi
0x100831dd6  jnz     short loc_100831DE0
0x100831dd8  lea     edi, [rsi+1]
0x100831ddb  jmp     loc_100831F07
0x100831de0  cmp     r14d, 2
0x100831de4  jnz     loc_100831E6E
0x100831dea  mov     [rsp+78h+var_48], 12Eh
0x100831df2  mov     [rsp+78h+var_50], 6
0x100831df7  mov     [rsp+78h+var_58], 12Eh
0x100831dff  lea     r9, aSqlNtdbmsStore_4; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x100831e06  lea     r8d, [r14-1]
0x100831e0a  mov     rdx, rbp
0x100831e0d  lea     ecx, [r14+36h]
0x100831e11  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100831e17  mov     rcx, rax
0x100831e1a  mov     [rsp+78h+var_30], rax
0x100831e1f  test    rax, rax
0x100831e22  jz      short loc_100831E5A
0x100831e24  lea     rax, ??_7?$CDynamicBuffer@PEAX@JSONParserLib@@6B@; const JSONParserLib::CDynamicBuffer<void *>::`vftable'
0x100831e2b  mov     [rcx], rax
0x100831e2e  mov     dword ptr [rcx+8], 5
0x100831e35  mov     dword ptr [rcx+0Ch], 5
0x100831e3c  mov     [rcx+10h], rdi
0x100831e40  mov     [rcx+18h], rdi
0x100831e44  mov     eax, [rcx+0Ch]
0x100831e47  mov     [rcx+20h], eax
0x100831e4a  mov     [rcx+28h], rbp
0x100831e4e  mov     [rcx+30h], r15b
0x100831e52  mov     eax, [rcx+8]
0x100831e55  mov     [rcx+24h], eax
0x100831e58  jmp     short loc_100831E5D
0x100831e5a  mov     rcx, rdi
0x100831e5d  mov     [rsi+10h], rcx
0x100831e61  test    rcx, rcx
0x100831e64  jnz     short loc_100831ED6
0x100831e66  lea     edi, [rcx+1]
0x100831e69  jmp     loc_100831F07
0x100831e6e  cmp     r14d, 1
0x100831e72  jnz     short loc_100831ED6
0x100831e74  mov     [rsp+78h+var_48], 138h
0x100831e7c  mov     [rsp+78h+var_50], 6
0x100831e81  mov     [rsp+78h+var_58], 138h
0x100831e89  lea     r9, aSqlNtdbmsStore_4; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x100831e90  mov     r8d, r14d
0x100831e93  mov     rdx, rbp
0x100831e96  lea     ecx, [r14+1Fh]
0x100831e9a  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100831ea0  mov     [rsp+78h+var_30], rax
0x100831ea5  test    rax, rax
0x100831ea8  jz      short loc_100831EC5
0x100831eaa  lea     rcx, ??_7?$CMapTemplate@PEA_WPEAXVCMapStringKeyHelper@JSONParserLib@@@JSONParserLib@@6B@; const JSONParserLib::CMapTemplate<wchar_t *,void *,JSONParserLib::CMapStringKeyHelper>::`vftable'
0x100831eb1  mov     [rax], rcx
0x100831eb4  mov     [rax+8], rdi
0x100831eb8  mov     [rax+10h], edi
0x100831ebb  mov     byte ptr [rax+14h], 0
0x100831ebf  mov     [rax+18h], rbp
0x100831ec3  jmp     short loc_100831EC8
0x100831ec5  mov     rax, rdi
0x100831ec8  mov     [rsi+10h], rax
0x100831ecc  test    rax, rax
0x100831ecf  jnz     short loc_100831ED6
0x100831ed1  lea     edi, [rax+1]
0x100831ed4  jmp     short loc_100831F07
0x100831ed6  mov     [rsi], r14d
0x100831ed9  mov     [rsi+4], r12d
0x100831edd  mov     rbx, rdi
0x100831ee0  mov     [rsp+78h+var_40], rbx
0x100831ee5  mov     r14, [rsp+78h+arg_20]
0x100831eed  mov     rcx, [r14]; this
0x100831ef0  cmp     rcx, rsi
0x100831ef3  jz      short loc_100831F04
0x100831ef5  test    rcx, rcx
0x100831ef8  jz      short loc_100831F04
0x100831efa  mov     edx, 1; unsigned int
0x100831eff  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x100831f04  mov     [r14], rsi
0x100831f07  test    rbx, rbx
0x100831f0a  jz      short loc_100831F19
0x100831f0c  mov     edx, 1; unsigned int
0x100831f11  mov     rcx, rbx; this
0x100831f14  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x100831f19  mov     eax, edi
0x100831f1b  lea     r11, [rsp+78h+var_28]
0x100831f20  mov     rbx, [r11+38h]
0x100831f24  mov     rbp, [r11+40h]
0x100831f28  mov     rsp, r11
0x100831f2b  pop     r15
0x100831f2d  pop     r14
0x100831f2f  pop     r12
0x100831f31  pop     rdi
0x100831f32  pop     rsi
0x100831f33  retn
```
