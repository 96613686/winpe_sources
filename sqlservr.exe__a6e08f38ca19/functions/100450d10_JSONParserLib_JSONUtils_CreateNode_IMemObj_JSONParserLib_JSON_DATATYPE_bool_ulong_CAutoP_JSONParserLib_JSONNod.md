# JSONParserLib::JSONUtils::CreateNode(IMemObj *,JSONParserLib::JSON_DATATYPE,bool,ulong,CAutoP<JSONParserLib::JSONNode> &)

- ea: `0x100450d10`
- end: `0x100450ef4`
- name: `?CreateNode@JSONUtils@JSONParserLib@@SAKPEAVIMemObj@@W4JSON_DATATYPE@2@_NKAEAV?$CAutoP@VJSONNode@JSONParserLib@@@@@Z`
- size: `484`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10044eff0`
- `0x10044f510`
- `0x10044f8b0`
- `0x10044fd30`

## callees

- `0x10044b8b0`
- `0x100450d10`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100450d65`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100450dd1`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100450e5a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100450d65`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100450dd1`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100450e5a`

## string_xrefs

- `0x100450d54`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Utils.cpp`
- `0x100450dbf`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Utils.cpp`
- `0x100450e49`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Utils.cpp`

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
0x100450d10  mov     rax, rsp
0x100450d13  mov     [rax+8], rcx
0x100450d17  push    rsi
0x100450d18  push    rdi
0x100450d19  push    r12
0x100450d1b  push    r14
0x100450d1d  push    r15
0x100450d1f  sub     rsp, 50h
0x100450d23  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x100450d2b  mov     [rax+10h], rbx
0x100450d2f  mov     [rax+18h], rbp
0x100450d33  mov     r12d, r9d
0x100450d36  movzx   r15d, r8b
0x100450d3a  mov     r14d, edx
0x100450d3d  mov     rbp, rcx
0x100450d40  xor     edi, edi
0x100450d42  mov     dword ptr [rax-48h], 122h
0x100450d49  mov     byte ptr [rax-50h], 6
0x100450d4d  mov     dword ptr [rax-58h], 122h
0x100450d54  lea     r9, aSqlNtdbmsStore_5; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x100450d5b  lea     r8d, [rdi+1]
0x100450d5f  mov     rdx, rcx
0x100450d62  lea     ecx, [rdi+20h]
0x100450d65  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100450d6b  mov     rsi, rax
0x100450d6e  mov     [rsp+78h+var_40], rax
0x100450d73  test    rax, rax
0x100450d76  jz      short loc_100450D88
0x100450d78  xorps   xmm0, xmm0
0x100450d7b  movups  xmmword ptr [rax], xmm0
0x100450d7e  movups  xmmword ptr [rax+10h], xmm0
0x100450d82  mov     [rax+18h], rbp
0x100450d86  jmp     short loc_100450D8B
0x100450d88  mov     rsi, rdi
0x100450d8b  mov     rbx, rsi
0x100450d8e  mov     [rsp+78h+var_40], rbx
0x100450d93  test    rsi, rsi
0x100450d96  jnz     short loc_100450DA0
0x100450d98  lea     edi, [rsi+1]
0x100450d9b  jmp     loc_100450EC7
0x100450da0  cmp     r14d, 2
0x100450da4  jnz     loc_100450E2E
0x100450daa  mov     [rsp+78h+var_48], 12Eh
0x100450db2  mov     [rsp+78h+var_50], 6
0x100450db7  mov     [rsp+78h+var_58], 12Eh
0x100450dbf  lea     r9, aSqlNtdbmsStore_5; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x100450dc6  lea     r8d, [r14-1]
0x100450dca  mov     rdx, rbp
0x100450dcd  lea     ecx, [r14+36h]
0x100450dd1  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100450dd7  mov     rcx, rax
0x100450dda  mov     [rsp+78h+var_30], rax
0x100450ddf  test    rax, rax
0x100450de2  jz      short loc_100450E1A
0x100450de4  lea     rax, ??_7?$CDynamicBuffer@PEAX@JSONParserLib@@6B@; const JSONParserLib::CDynamicBuffer<void *>::`vftable'
0x100450deb  mov     [rcx], rax
0x100450dee  mov     dword ptr [rcx+8], 5
0x100450df5  mov     dword ptr [rcx+0Ch], 5
0x100450dfc  mov     [rcx+10h], rdi
0x100450e00  mov     [rcx+18h], rdi
0x100450e04  mov     eax, [rcx+0Ch]
0x100450e07  mov     [rcx+20h], eax
0x100450e0a  mov     [rcx+28h], rbp
0x100450e0e  mov     [rcx+30h], r15b
0x100450e12  mov     eax, [rcx+8]
0x100450e15  mov     [rcx+24h], eax
0x100450e18  jmp     short loc_100450E1D
0x100450e1a  mov     rcx, rdi
0x100450e1d  mov     [rsi+10h], rcx
0x100450e21  test    rcx, rcx
0x100450e24  jnz     short loc_100450E96
0x100450e26  lea     edi, [rcx+1]
0x100450e29  jmp     loc_100450EC7
0x100450e2e  cmp     r14d, 1
0x100450e32  jnz     short loc_100450E96
0x100450e34  mov     [rsp+78h+var_48], 138h
0x100450e3c  mov     [rsp+78h+var_50], 6
0x100450e41  mov     [rsp+78h+var_58], 138h
0x100450e49  lea     r9, aSqlNtdbmsStore_5; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x100450e50  mov     r8d, r14d
0x100450e53  mov     rdx, rbp
0x100450e56  lea     ecx, [r14+1Fh]
0x100450e5a  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100450e60  mov     [rsp+78h+var_30], rax
0x100450e65  test    rax, rax
0x100450e68  jz      short loc_100450E85
0x100450e6a  lea     rcx, ??_7?$CMapTemplate@PEA_WPEAXVCMapStringKeyHelper@JSONParserLib@@@JSONParserLib@@6B@; const JSONParserLib::CMapTemplate<wchar_t *,void *,JSONParserLib::CMapStringKeyHelper>::`vftable'
0x100450e71  mov     [rax], rcx
0x100450e74  mov     [rax+8], rdi
0x100450e78  mov     [rax+10h], edi
0x100450e7b  mov     byte ptr [rax+14h], 0
0x100450e7f  mov     [rax+18h], rbp
0x100450e83  jmp     short loc_100450E88
0x100450e85  mov     rax, rdi
0x100450e88  mov     [rsi+10h], rax
0x100450e8c  test    rax, rax
0x100450e8f  jnz     short loc_100450E96
0x100450e91  lea     edi, [rax+1]
0x100450e94  jmp     short loc_100450EC7
0x100450e96  mov     [rsi], r14d
0x100450e99  mov     [rsi+4], r12d
0x100450e9d  mov     rbx, rdi
0x100450ea0  mov     [rsp+78h+var_40], rbx
0x100450ea5  mov     r14, [rsp+78h+arg_20]
0x100450ead  mov     rcx, [r14]; this
0x100450eb0  cmp     rcx, rsi
0x100450eb3  jz      short loc_100450EC4
0x100450eb5  test    rcx, rcx
0x100450eb8  jz      short loc_100450EC4
0x100450eba  mov     edx, 1; unsigned int
0x100450ebf  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x100450ec4  mov     [r14], rsi
0x100450ec7  test    rbx, rbx
0x100450eca  jz      short loc_100450ED9
0x100450ecc  mov     edx, 1; unsigned int
0x100450ed1  mov     rcx, rbx; this
0x100450ed4  call    ??_GJSONNode@JSONParserLib@@QEAAPEAXI@Z; JSONParserLib::JSONNode::`scalar deleting destructor'(uint)
0x100450ed9  mov     eax, edi
0x100450edb  lea     r11, [rsp+78h+var_28]
0x100450ee0  mov     rbx, [r11+38h]
0x100450ee4  mov     rbp, [r11+40h]
0x100450ee8  mov     rsp, r11
0x100450eeb  pop     r15
0x100450eed  pop     r14
0x100450eef  pop     r12
0x100450ef1  pop     rdi
0x100450ef2  pop     rsi
0x100450ef3  retn
```
