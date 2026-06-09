# GenCompareObj(IMemObj *,CTypeInfo const *,CTypeInfo const *,int,CEnvCollection *)

- ea: `0x10047de00`
- end: `0x10047e0ba`
- name: `?GenCompareObj@@YAPEAVCCompareObject@@PEAVIMemObj@@PEBVCTypeInfo@@1HPEAVCEnvCollection@@@Z`
- size: `698`
- prototype: `struct CCompareObject *(struct IMemObj *, const struct CTypeInfo *, const struct CTypeInfo *, int, struct CEnvCollection *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x100406770`
- `0x10047e340`
- `0x1004d9470`

## callees

- `0x1004013e0`
- `0x1004026b0`
- `0x10047de00`
- `0x10047e540`
- `0x10047ebd0`
- `0x100482db0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047de71`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047deca`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047df3e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047dfa3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047dffd`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e082`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047de71`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047deca`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047df3e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047dfa3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047dffd`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e082`

## string_xrefs

- `0x10047de62`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047debc`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047df2f`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047df95`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047dfee`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047e073`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct CCompareObject *__fastcall GenCompareObj(
        struct IMemObj *a1,
        const struct CTypeInfo *a2,
        const struct CTypeInfo *a3)
{
  __int64 v6; // rcx
  CCompareBlob *v7; // rax
  CCompareWlob *v10; // rax
  struct IMemObj *v11; // rdx
  CCompareBlob *v13; // rax
  CCompareWlob *v15; // rax
  struct IMemObj *v16; // rdx
  CCompareLob *v18; // rax
  CCompareLob *v19; // rbx
  __int64 v20; // rdx
  CCompareBlob *v21; // rax

  v6 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)a2);
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + v6) )
  {
    if ( (*((_DWORD *)a2 + 5) & 0x10800) != 0 )
    {
      v7 = (CCompareBlob *)operator new(0x20u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 177, 6u);
      if ( v7 )
        return CCompareBlob::CCompareBlob(v7, a2, a3);
      else
        return 0;
    }
    else
    {
      v10 = (CCompareWlob *)operator new(0x40u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 179, 6u);
      if ( v10 )
        return CCompareWlob::CCompareWlob(v10, v11, a2, a3);
      else
        return 0;
    }
  }
  else if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v6) )
  {
    if ( CTypeInfo::FAnyBinarySort(a2) )
    {
      v13 = (CCompareBlob *)operator new(0x20u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 184, 6u);
      if ( v13 )
        return CCompareBlob::CCompareBlob(v13, a2, a3);
      else
        return 0;
    }
    else if ( CTypeInfo::FWindowsSort(a2) )
    {
      v15 = (CCompareWlob *)operator new(0x40u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 186, 6u);
      if ( v15 )
        return CCompareWlob::CCompareWlob(v15, v16, a2, a3);
      else
        return 0;
    }
    else
    {
      v18 = (CCompareLob *)operator new(0x28u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 188, 6u);
      v19 = v18;
      if ( !v18 )
        return 0;
      CCompareLob::CCompareLob(v18, a2, a3);
      *(_QWORD *)v19 = &CCompareClob::`vftable';
      v20 = *((_QWORD *)CSortCacheForSqlCollations::m_pSortCache + *((unsigned __int8 *)v19 + 19) + 1);
      *((_QWORD *)v19 + 4) = *(_QWORD *)(v20 + 8);
      *((_QWORD *)v19 + 3) = *(_QWORD *)(v20 + 56);
      return v19;
    }
  }
  else
  {
    v21 = (CCompareBlob *)operator new(0x20u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 194, 6u);
    if ( v21 )
      return CCompareBlob::CCompareBlob(v21, a2, a3);
    else
      return 0;
  }
}

```

## disassembly

```asm
0x10047de00  mov     [rsp+arg_0], rcx
0x10047de05  push    rdi
0x10047de06  sub     rsp, 40h
0x10047de0a  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x10047de13  mov     [rsp+48h+arg_10], rbx
0x10047de18  mov     [rsp+48h+arg_18], rsi
0x10047de1d  mov     rsi, r8
0x10047de20  mov     rdi, rdx
0x10047de23  mov     rbx, rcx
0x10047de26  movzx   eax, byte ptr [rdx]
0x10047de29  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10047de30  movzx   ecx, byte ptr [rax+rdx+45AE60h]
0x10047de38  cmp     byte ptr [rcx+rdx+45AF60h], 0
0x10047de40  jz      loc_10047DF02
0x10047de46  test    dword ptr [rdi+14h], 10800h
0x10047de4d  jz      short loc_10047DEA9
0x10047de4f  mov     [rsp+48h+arg_8], 0B1h
0x10047de57  mov     [rsp+48h+var_28], 6
0x10047de5c  mov     r9d, 0B1h
0x10047de62  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047de69  mov     rdx, rbx
0x10047de6c  mov     ecx, 20h ; ' '
0x10047de71  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047de77  mov     [rsp+48h+var_10], rax
0x10047de7c  test    rax, rax
0x10047de7f  jz      short loc_10047DE94
0x10047de81  mov     r8, rsi; struct CTypeInfo *
0x10047de84  mov     rdx, rdi; struct CTypeInfo *
0x10047de87  mov     rcx, rax; this
0x10047de8a  call    ??0CCompareBlob@@QEAA@PEBVCTypeInfo@@0@Z; CCompareBlob::CCompareBlob(CTypeInfo const *,CTypeInfo const *)
0x10047de8f  mov     rbx, rax
0x10047de92  jmp     short loc_10047DE96
0x10047de94  xor     ebx, ebx
0x10047de96  mov     rax, rbx
0x10047de99  mov     rbx, [rsp+48h+arg_10]
0x10047de9e  mov     rsi, [rsp+48h+arg_18]
0x10047dea3  add     rsp, 40h
0x10047dea7  pop     rdi
0x10047dea8  retn
0x10047dea9  mov     [rsp+48h+arg_8], 0B3h
0x10047deb1  mov     [rsp+48h+var_28], 6
0x10047deb6  mov     r9d, 0B3h
0x10047debc  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047dec3  mov     rdx, rbx
0x10047dec6  lea     ecx, [r9-73h]
0x10047deca  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047ded0  mov     [rsp+48h+var_10], rax
0x10047ded5  test    rax, rax
0x10047ded8  jz      short loc_10047DEED
0x10047deda  mov     r9, rsi; struct CTypeInfo *
0x10047dedd  mov     r8, rdi; struct CTypeInfo *
0x10047dee0  mov     rcx, rax; this
0x10047dee3  call    ??0CCompareWlob@@QEAA@PEAVIMemObj@@PEBVCTypeInfo@@1@Z; CCompareWlob::CCompareWlob(IMemObj *,CTypeInfo const *,CTypeInfo const *)
0x10047dee8  mov     rbx, rax
0x10047deeb  jmp     short loc_10047DEEF
0x10047deed  xor     ebx, ebx
0x10047deef  mov     rax, rbx
0x10047def2  mov     rbx, [rsp+48h+arg_10]
0x10047def7  mov     rsi, [rsp+48h+arg_18]
0x10047defc  add     rsp, 40h
0x10047df00  pop     rdi
0x10047df01  retn
0x10047df02  cmp     byte ptr [rcx+rdx+45BD40h], 0
0x10047df0a  jz      loc_10047E060
0x10047df10  mov     rcx, rdi; this
0x10047df13  call    ?FAnyBinarySort@CTypeInfo@@QEBA_NXZ; CTypeInfo::FAnyBinarySort(void)
0x10047df18  test    al, al
0x10047df1a  jz      short loc_10047DF76
0x10047df1c  mov     [rsp+48h+arg_8], 0B8h
0x10047df24  mov     [rsp+48h+var_28], 6
0x10047df29  mov     r9d, 0B8h
0x10047df2f  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047df36  mov     rdx, rbx
0x10047df39  mov     ecx, 20h ; ' '
0x10047df3e  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047df44  mov     [rsp+48h+var_10], rax
0x10047df49  test    rax, rax
0x10047df4c  jz      short loc_10047DF61
0x10047df4e  mov     r8, rsi; struct CTypeInfo *
0x10047df51  mov     rdx, rdi; struct CTypeInfo *
0x10047df54  mov     rcx, rax; this
0x10047df57  call    ??0CCompareBlob@@QEAA@PEBVCTypeInfo@@0@Z; CCompareBlob::CCompareBlob(CTypeInfo const *,CTypeInfo const *)
0x10047df5c  mov     rbx, rax
0x10047df5f  jmp     short loc_10047DF63
0x10047df61  xor     ebx, ebx
0x10047df63  mov     rax, rbx
0x10047df66  mov     rbx, [rsp+48h+arg_10]
0x10047df6b  mov     rsi, [rsp+48h+arg_18]
0x10047df70  add     rsp, 40h
0x10047df74  pop     rdi
0x10047df75  retn
0x10047df76  mov     rcx, rdi; this
0x10047df79  call    ?FWindowsSort@CTypeInfo@@QEBA_NXZ; CTypeInfo::FWindowsSort(void)
0x10047df7e  test    al, al
0x10047df80  jz      short loc_10047DFDB
0x10047df82  mov     [rsp+48h+arg_8], 0BAh
0x10047df8a  mov     [rsp+48h+var_28], 6
0x10047df8f  mov     r9d, 0BAh
0x10047df95  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047df9c  mov     rdx, rbx
0x10047df9f  lea     ecx, [r9-7Ah]
0x10047dfa3  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047dfa9  mov     [rsp+48h+var_10], rax
0x10047dfae  test    rax, rax
0x10047dfb1  jz      short loc_10047DFC6
0x10047dfb3  mov     r9, rsi; struct CTypeInfo *
0x10047dfb6  mov     r8, rdi; struct CTypeInfo *
0x10047dfb9  mov     rcx, rax; this
0x10047dfbc  call    ??0CCompareWlob@@QEAA@PEAVIMemObj@@PEBVCTypeInfo@@1@Z; CCompareWlob::CCompareWlob(IMemObj *,CTypeInfo const *,CTypeInfo const *)
0x10047dfc1  mov     rbx, rax
0x10047dfc4  jmp     short loc_10047DFC8
0x10047dfc6  xor     ebx, ebx
0x10047dfc8  mov     rax, rbx
0x10047dfcb  mov     rbx, [rsp+48h+arg_10]
0x10047dfd0  mov     rsi, [rsp+48h+arg_18]
0x10047dfd5  add     rsp, 40h
0x10047dfd9  pop     rdi
0x10047dfda  retn
0x10047dfdb  mov     [rsp+48h+arg_8], 0BCh
0x10047dfe3  mov     [rsp+48h+var_28], 6
0x10047dfe8  mov     r9d, 0BCh
0x10047dfee  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047dff5  mov     rdx, rbx
0x10047dff8  mov     ecx, 28h ; '('
0x10047dffd  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047e003  mov     rbx, rax
0x10047e006  mov     [rsp+48h+var_10], rax
0x10047e00b  test    rax, rax
0x10047e00e  jz      short loc_10047E04B
0x10047e010  mov     r8, rsi; struct CTypeInfo *
0x10047e013  mov     rdx, rdi; struct CTypeInfo *
0x10047e016  mov     rcx, rax; this
0x10047e019  call    ??0CCompareLob@@QEAA@PEBVCTypeInfo@@0@Z; CCompareLob::CCompareLob(CTypeInfo const *,CTypeInfo const *)
0x10047e01e  nop
0x10047e01f  lea     rax, ??_7CCompareClob@@6B@; const CCompareClob::`vftable'
0x10047e026  mov     [rbx], rax
0x10047e029  movzx   ecx, byte ptr [rbx+13h]
0x10047e02d  mov     rax, cs:?m_pSortCache@CSortCacheForSqlCollations@@0PEAV1@EA; CSortCacheForSqlCollations * CSortCacheForSqlCollations::m_pSortCache
0x10047e034  mov     rdx, [rax+rcx*8+8]
0x10047e039  mov     rax, [rdx+8]
0x10047e03d  mov     [rbx+20h], rax
0x10047e041  mov     rax, [rdx+38h]
0x10047e045  mov     [rbx+18h], rax
0x10047e049  jmp     short loc_10047E04D
0x10047e04b  xor     ebx, ebx
0x10047e04d  mov     rax, rbx
0x10047e050  mov     rbx, [rsp+48h+arg_10]
0x10047e055  mov     rsi, [rsp+48h+arg_18]
0x10047e05a  add     rsp, 40h
0x10047e05e  pop     rdi
0x10047e05f  retn
0x10047e060  mov     [rsp+48h+arg_8], 0C2h
0x10047e068  mov     [rsp+48h+var_28], 6
0x10047e06d  mov     r9d, 0C2h
0x10047e073  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047e07a  mov     rdx, rbx
0x10047e07d  mov     ecx, 20h ; ' '
0x10047e082  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047e088  mov     [rsp+48h+var_10], rax
0x10047e08d  test    rax, rax
0x10047e090  jz      short loc_10047E0A5
0x10047e092  mov     r8, rsi; struct CTypeInfo *
0x10047e095  mov     rdx, rdi; struct CTypeInfo *
0x10047e098  mov     rcx, rax; this
0x10047e09b  call    ??0CCompareBlob@@QEAA@PEBVCTypeInfo@@0@Z; CCompareBlob::CCompareBlob(CTypeInfo const *,CTypeInfo const *)
0x10047e0a0  mov     rbx, rax
0x10047e0a3  jmp     short loc_10047E0A7
0x10047e0a5  xor     ebx, ebx
0x10047e0a7  mov     rax, rbx
0x10047e0aa  mov     rbx, [rsp+48h+arg_10]
0x10047e0af  mov     rsi, [rsp+48h+arg_18]
0x10047e0b4  add     rsp, 40h
0x10047e0b8  pop     rdi
0x10047e0b9  retn
```
