# GenCompareObjAlwaysEncrypted(IMemObj *,CTypeInfo const *,CTypeInfo const *,int,CEnvCollection *)

- ea: `0x10047e0c0`
- end: `0x10047e33a`
- name: `?GenCompareObjAlwaysEncrypted@@YAPEAVCCompareObject@@PEAVIMemObj@@PEBVCTypeInfo@@1HPEAVCEnvCollection@@@Z`
- size: `634`
- prototype: `struct CCompareObject *(struct IMemObj *, const struct CTypeInfo *, const struct CTypeInfo *, int, struct CEnvCollection *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10047e340`

## callees

- `0x1004013e0`
- `0x1004026b0`
- `0x10047e0c0`
- `0x1004800a0`
- `0x100480230`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e12e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e17d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e1e9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e244`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e296`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e30d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e12e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e17d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e1e9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e244`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e296`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10047e30d`

## string_xrefs

- `0x10047e11f`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047e16e`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047e1da`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047e235`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047e287`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`
- `0x10047e2fe`: `sql\ntdbms\msql\typesystem\tsfncomp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct CCompareObject *__fastcall GenCompareObjAlwaysEncrypted(
        struct IMemObj *a1,
        const struct CTypeInfo *a2,
        const struct CTypeInfo *a3)
{
  __int64 v6; // rcx
  CCompareBlobChunk *v7; // rax
  const struct CTypeInfo *v8; // r8
  CCompareWlobChunk *v11; // rax
  struct IMemObj *v12; // rdx
  CCompareBlobChunk *v14; // rax
  const struct CTypeInfo *v15; // r8
  CCompareWlobChunk *v17; // rax
  struct IMemObj *v18; // rdx
  _DWORD *v20; // rdx
  int v21; // eax
  CCompareBlobChunk *v22; // rax
  const struct CTypeInfo *v23; // r8

  v6 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)a2);
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + v6) )
  {
    if ( (*((_DWORD *)a2 + 5) & 0x10800) != 0 )
    {
      v7 = (CCompareBlobChunk *)operator new(0x10u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 222, 6u);
      if ( v7 )
        return CCompareBlobChunk::CCompareBlobChunk(v7, a2, v8);
      else
        return 0;
    }
    else
    {
      v11 = (CCompareWlobChunk *)operator new(0x28u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 224, 6u);
      if ( v11 )
        return CCompareWlobChunk::CCompareWlobChunk(v11, v12, a2, a3);
      else
        return 0;
    }
  }
  else if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsNonUnicode + v6) )
  {
    if ( CTypeInfo::FAnyBinarySort(a2) )
    {
      v14 = (CCompareBlobChunk *)operator new(0x10u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 229, 6u);
      if ( v14 )
        return CCompareBlobChunk::CCompareBlobChunk(v14, a2, v15);
      else
        return 0;
    }
    else if ( CTypeInfo::FWindowsSort(a2) )
    {
      v17 = (CCompareWlobChunk *)operator new(0x28u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 231, 6u);
      if ( v17 )
        return CCompareWlobChunk::CCompareWlobChunk(v17, v18, a2, a3);
      else
        return 0;
    }
    else
    {
      v20 = operator new(0x20u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 233, 6u);
      if ( !v20 )
        return 0;
      *(_QWORD *)v20 = &CCompareObject::`vftable';
      *(_QWORD *)v20 = &CCompareClobChunk::`vftable';
      if ( (unsigned __int8)(*(_BYTE *)a2 + 16) <= 1u )
        v21 = 0;
      else
        v21 = *((_DWORD *)a2 + 5);
      v20[2] = v21;
      *((_QWORD *)v20 + 2) = 0;
      *((_QWORD *)v20 + 3) = 0;
      return (struct CCompareObject *)v20;
    }
  }
  else
  {
    v22 = (CCompareBlobChunk *)operator new(0x10u, a1, "sql\\ntdbms\\msql\\typesystem\\tsfncomp.cpp", 239, 6u);
    if ( v22 )
      return CCompareBlobChunk::CCompareBlobChunk(v22, a2, v23);
    else
      return 0;
  }
}

```

## disassembly

```asm
0x10047e0c0  mov     [rsp+arg_18], r9d
0x10047e0c5  mov     [rsp+arg_0], rcx
0x10047e0ca  push    rbx
0x10047e0cb  push    rsi
0x10047e0cc  push    rdi
0x10047e0cd  sub     rsp, 40h
0x10047e0d1  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x10047e0da  mov     rsi, r8
0x10047e0dd  mov     rbx, rdx
0x10047e0e0  mov     rdi, rcx
0x10047e0e3  movzx   eax, byte ptr [rdx]
0x10047e0e6  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10047e0ed  movzx   ecx, byte ptr [rax+rdx+45AE60h]
0x10047e0f5  cmp     byte ptr [rcx+rdx+45AF60h], 0
0x10047e0fd  jz      loc_10047E1AD
0x10047e103  test    dword ptr [rbx+14h], 10800h
0x10047e10a  jz      short loc_10047E15B
0x10047e10c  mov     [rsp+58h+arg_18], 0DEh
0x10047e114  mov     [rsp+58h+var_38], 6
0x10047e119  mov     r9d, 0DEh
0x10047e11f  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047e126  mov     rdx, rdi
0x10047e129  mov     ecx, 10h
0x10047e12e  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047e134  mov     [rsp+58h+arg_8], rax
0x10047e139  test    rax, rax
0x10047e13c  jz      short loc_10047E14E
0x10047e13e  mov     rdx, rbx; struct CTypeInfo *
0x10047e141  mov     rcx, rax; this
0x10047e144  call    ??0CCompareBlobChunk@@QEAA@PEBVCTypeInfo@@0@Z; CCompareBlobChunk::CCompareBlobChunk(CTypeInfo const *,CTypeInfo const *)
0x10047e149  mov     rcx, rax
0x10047e14c  jmp     short loc_10047E150
0x10047e14e  xor     ecx, ecx
0x10047e150  mov     rax, rcx
0x10047e153  add     rsp, 40h
0x10047e157  pop     rdi
0x10047e158  pop     rsi
0x10047e159  pop     rbx
0x10047e15a  retn
0x10047e15b  mov     [rsp+58h+arg_18], 0E0h
0x10047e163  mov     [rsp+58h+var_38], 6
0x10047e168  mov     r9d, 0E0h
0x10047e16e  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047e175  mov     rdx, rdi
0x10047e178  mov     ecx, 28h ; '('
0x10047e17d  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047e183  mov     [rsp+58h+arg_8], rax
0x10047e188  test    rax, rax
0x10047e18b  jz      short loc_10047E1A0
0x10047e18d  mov     r9, rsi; struct CTypeInfo *
0x10047e190  mov     r8, rbx; struct CTypeInfo *
0x10047e193  mov     rcx, rax; this
0x10047e196  call    ??0CCompareWlobChunk@@QEAA@PEAVIMemObj@@PEBVCTypeInfo@@1@Z; CCompareWlobChunk::CCompareWlobChunk(IMemObj *,CTypeInfo const *,CTypeInfo const *)
0x10047e19b  mov     rcx, rax
0x10047e19e  jmp     short loc_10047E1A2
0x10047e1a0  xor     ecx, ecx
0x10047e1a2  mov     rax, rcx
0x10047e1a5  add     rsp, 40h
0x10047e1a9  pop     rdi
0x10047e1aa  pop     rsi
0x10047e1ab  pop     rbx
0x10047e1ac  retn
0x10047e1ad  cmp     byte ptr [rcx+rdx+45BD40h], 0
0x10047e1b5  jz      loc_10047E2EB
0x10047e1bb  mov     rcx, rbx; this
0x10047e1be  call    ?FAnyBinarySort@CTypeInfo@@QEBA_NXZ; CTypeInfo::FAnyBinarySort(void)
0x10047e1c3  test    al, al
0x10047e1c5  jz      short loc_10047E216
0x10047e1c7  mov     [rsp+58h+arg_18], 0E5h
0x10047e1cf  mov     [rsp+58h+var_38], 6
0x10047e1d4  mov     r9d, 0E5h
0x10047e1da  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047e1e1  mov     rdx, rdi
0x10047e1e4  mov     ecx, 10h
0x10047e1e9  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047e1ef  mov     [rsp+58h+arg_8], rax
0x10047e1f4  test    rax, rax
0x10047e1f7  jz      short loc_10047E209
0x10047e1f9  mov     rdx, rbx; struct CTypeInfo *
0x10047e1fc  mov     rcx, rax; this
0x10047e1ff  call    ??0CCompareBlobChunk@@QEAA@PEBVCTypeInfo@@0@Z; CCompareBlobChunk::CCompareBlobChunk(CTypeInfo const *,CTypeInfo const *)
0x10047e204  mov     rcx, rax
0x10047e207  jmp     short loc_10047E20B
0x10047e209  xor     ecx, ecx
0x10047e20b  mov     rax, rcx
0x10047e20e  add     rsp, 40h
0x10047e212  pop     rdi
0x10047e213  pop     rsi
0x10047e214  pop     rbx
0x10047e215  retn
0x10047e216  mov     rcx, rbx; this
0x10047e219  call    ?FWindowsSort@CTypeInfo@@QEBA_NXZ; CTypeInfo::FWindowsSort(void)
0x10047e21e  test    al, al
0x10047e220  jz      short loc_10047E274
0x10047e222  mov     [rsp+58h+arg_18], 0E7h
0x10047e22a  mov     [rsp+58h+var_38], 6
0x10047e22f  mov     r9d, 0E7h
0x10047e235  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047e23c  mov     rdx, rdi
0x10047e23f  mov     ecx, 28h ; '('
0x10047e244  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047e24a  mov     [rsp+58h+arg_8], rax
0x10047e24f  test    rax, rax
0x10047e252  jz      short loc_10047E267
0x10047e254  mov     r9, rsi; struct CTypeInfo *
0x10047e257  mov     r8, rbx; struct CTypeInfo *
0x10047e25a  mov     rcx, rax; this
0x10047e25d  call    ??0CCompareWlobChunk@@QEAA@PEAVIMemObj@@PEBVCTypeInfo@@1@Z; CCompareWlobChunk::CCompareWlobChunk(IMemObj *,CTypeInfo const *,CTypeInfo const *)
0x10047e262  mov     rcx, rax
0x10047e265  jmp     short loc_10047E269
0x10047e267  xor     ecx, ecx
0x10047e269  mov     rax, rcx
0x10047e26c  add     rsp, 40h
0x10047e270  pop     rdi
0x10047e271  pop     rsi
0x10047e272  pop     rbx
0x10047e273  retn
0x10047e274  mov     [rsp+58h+arg_18], 0E9h
0x10047e27c  mov     [rsp+58h+var_38], 6
0x10047e281  mov     r9d, 0E9h
0x10047e287  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047e28e  mov     rdx, rdi
0x10047e291  mov     ecx, 20h ; ' '
0x10047e296  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047e29c  mov     rdx, rax
0x10047e29f  mov     [rsp+58h+arg_8], rax
0x10047e2a4  test    rax, rax
0x10047e2a7  jz      short loc_10047E2DC
0x10047e2a9  lea     rax, ??_7CCompareObject@@6B@; const CCompareObject::`vftable'
0x10047e2b0  mov     [rdx], rax
0x10047e2b3  lea     rax, ??_7CCompareClobChunk@@6B@; const CCompareClobChunk::`vftable'
0x10047e2ba  mov     [rdx], rax
0x10047e2bd  movzx   eax, byte ptr [rbx]
0x10047e2c0  add     al, 10h
0x10047e2c2  xor     ecx, ecx
0x10047e2c4  cmp     al, 1
0x10047e2c6  jbe     short loc_10047E2CD
0x10047e2c8  mov     eax, [rbx+14h]
0x10047e2cb  jmp     short loc_10047E2CF
0x10047e2cd  mov     eax, ecx
0x10047e2cf  mov     [rdx+8], eax
0x10047e2d2  mov     [rdx+10h], rcx
0x10047e2d6  mov     [rdx+18h], rcx
0x10047e2da  jmp     short loc_10047E2E0
0x10047e2dc  xor     ecx, ecx
0x10047e2de  mov     edx, ecx
0x10047e2e0  mov     rax, rdx
0x10047e2e3  add     rsp, 40h
0x10047e2e7  pop     rdi
0x10047e2e8  pop     rsi
0x10047e2e9  pop     rbx
0x10047e2ea  retn
0x10047e2eb  mov     [rsp+58h+arg_18], 0EFh
0x10047e2f3  mov     [rsp+58h+var_38], 6
0x10047e2f8  mov     r9d, 0EFh
0x10047e2fe  lea     r8, aSqlNtdbmsMsqlT_9; "sql\\ntdbms\\msql\\typesystem\\tsfncomp"...
0x10047e305  mov     rdx, rdi
0x10047e308  mov     ecx, 10h
0x10047e30d  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10047e313  mov     [rsp+58h+arg_8], rax
0x10047e318  test    rax, rax
0x10047e31b  jz      short loc_10047E32D
0x10047e31d  mov     rdx, rbx; struct CTypeInfo *
0x10047e320  mov     rcx, rax; this
0x10047e323  call    ??0CCompareBlobChunk@@QEAA@PEBVCTypeInfo@@0@Z; CCompareBlobChunk::CCompareBlobChunk(CTypeInfo const *,CTypeInfo const *)
0x10047e328  mov     rcx, rax
0x10047e32b  jmp     short loc_10047E32F
0x10047e32d  xor     ecx, ecx
0x10047e32f  mov     rax, rcx
0x10047e332  add     rsp, 40h
0x10047e336  pop     rdi
0x10047e337  pop     rsi
0x10047e338  pop     rbx
0x10047e339  retn
```
