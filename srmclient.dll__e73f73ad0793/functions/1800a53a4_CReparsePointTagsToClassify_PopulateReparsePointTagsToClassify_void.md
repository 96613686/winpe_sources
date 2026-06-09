# CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify(void)

- ea: `0x1800a53a4`
- end: `0x1800a570b`
- name: `?PopulateReparsePointTagsToClassify@CReparsePointTagsToClassify@@QEAAXXZ`
- size: `871`
- prototype: `void __fastcall(CReparsePointTagsToClassify *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x180096d3c`

## callees

- `0x180001350`
- `0x18000af40`
- `0x18006b61c`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x180075510`
- `0x180075ab0`
- `0x18007691c`
- `0x1800a50e4`
- `0x1800a53a4`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wtol` at `0x1800a5527`
- `msvcrt!_wtol` at `0x1800a5527`
- `ole32!CoTaskMemFree` at `0x1800a5605`
- `ole32!CoTaskMemFree` at `0x1800a563a`
- `ole32!CoTaskMemFree` at `0x1800a5605`
- `ole32!CoTaskMemFree` at `0x1800a563a`

## string_xrefs

- `0x1800a53e8`: `CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify`
- `0x1800a5561`: `CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify`
- `0x1800a55a8`: `CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify`
- `0x1800a55d0`: `Adding reparse tag to m_reparsePointTagsToClassify: <0x%x>`
- `0x1800a56aa`: `ReparsePointTagsToClassify registry key could not be read, ignoring failure.`
- `0x1800a53dd`: `base\fs\fsrm\utilities\scanner\reparsetagstoclassify.cpp`
- `0x1800a5589`: `Ignoring invalid reparse tag: <0x%x>`
- `0x1800a54ac`: `System\CurrentControlSet\Services\SrmSvc\Settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify(CReparsePointTagsToClassify *this)
{
  _QWORD *v2; // rdi
  _QWORD *i; // rbx
  const unsigned __int16 *v4; // rdx
  const unsigned __int16 *v5; // rdi
  const unsigned __int16 *v6; // r15
  wchar_t *v7; // rbx
  unsigned int v8; // r14d
  __int64 v9; // rax
  bool v10; // [rsp+20h] [rbp-E0h]
  wchar_t *String; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12[2]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v14[3]; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t **v15; // [rsp+60h] [rbp-A0h]
  const wchar_t *v16; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v17; // [rsp+70h] [rbp-90h]
  const wchar_t *v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+80h] [rbp-80h]
  int v20; // [rsp+84h] [rbp-7Ch]
  int v21; // [rsp+88h] [rbp-78h]
  _BYTE v22[96]; // [rsp+90h] [rbp-70h] BYREF
  int v23; // [rsp+F0h] [rbp-10h]
  const wchar_t **v24; // [rsp+F8h] [rbp-8h]
  _QWORD v25[3]; // [rsp+100h] [rbp+0h] BYREF
  int v26; // [rsp+118h] [rbp+18h]
  int v27; // [rsp+11Ch] [rbp+1Ch]
  int v28; // [rsp+120h] [rbp+20h]
  char v29[96]; // [rsp+128h] [rbp+28h] BYREF
  int v30; // [rsp+188h] [rbp+88h]
  char v31[16]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v32[22]; // [rsp+1A0h] [rbp+A0h] BYREF

  *(_QWORD *)v12 = v25;
  v25[0] = L"base\\fs\\fsrm\\utilities\\scanner\\reparsetagstoclassify.cpp";
  v25[1] = L"CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify";
  v25[2] = L"REPTAGSC";
  v26 = 53;
  v27 = 20;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v32, (const struct CSrmDebugInfo *)v25, 0);
  v2 = *(_QWORD **)(*((_QWORD *)this + 1) + 8LL);
  for ( i = v2; !*((_BYTE *)i + 29); v2 = i )
  {
    std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::_Erase(
      this,
      i[2]);
    i = (_QWORD *)*i;
    operator delete(v2);
  }
  *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = *((_QWORD *)this + 1);
  **((_QWORD **)this + 1) = *((_QWORD *)this + 1);
  *(_QWORD *)(*((_QWORD *)this + 1) + 16LL) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 2) = 0;
  v14[2] = 0;
  v14[1] = 0;
  v14[0] = (LPVOID)131353;
  if ( CSrmRegistryKey::Open(
         (CSrmRegistryKey *)v14,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\SrmSvc\\Settings") )
  {
    pv = 0;
    v12[0] = 0;
    if ( CSrmRegistryKey::GetMultiszValue((CSrmRegistryKey *)v14, v4, (unsigned __int16 **)&pv, v12, v10) )
    {
      v5 = (const unsigned __int16 *)pv;
      v6 = (const unsigned __int16 *)((char *)pv + 2 * v12[0]);
      while ( *v5 && v5 < v6 )
      {
        String = 0;
        CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&String, v5);
        v7 = String;
        v8 = _wtol(String);
        v16 = L"base\\fs\\fsrm\\utilities\\scanner\\reparsetagstoclassify.cpp";
        v20 = 20;
        v21 = 255;
        v23 = 0x1000000;
        if ( v8 )
        {
          v15 = &v16;
          v17 = L"CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify";
          v18 = L"REPTAGSC";
          v19 = 92;
          memset_0(v22, 0, sizeof(v22));
          CSrmFunctionTracer::Trace(v32, &v16, L"Adding reparse tag to m_reparsePointTagsToClassify: <0x%x>", v8);
          v12[0] = v8;
          std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<unsigned long>(
            this,
            v31,
            v12);
        }
        else
        {
          v24 = &v16;
          v17 = L"CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify";
          v18 = L"REPTAGSC";
          v19 = 84;
          memset_0(v22, 0, sizeof(v22));
          CSrmFunctionTracer::Trace(v32, &v16, L"Ignoring invalid reparse tag: <0x%x>", 0);
        }
        CoTaskMemFree(v7);
        String = 0;
        v9 = -1;
        do
          ++v9;
        while ( v5[v9] );
        v5 += v9 + 1;
      }
    }
    CoTaskMemFree(pv);
    pv = 0;
    CSrmRegistryKey::~CSrmRegistryKey(v14);
    v32[0] = &CSrmFunctionTracer::`vftable';
  }
  else
  {
    v15 = &v16;
    v16 = L"base\\fs\\fsrm\\utilities\\scanner\\reparsetagstoclassify.cpp";
    v17 = L"CReparsePointTagsToClassify::PopulateReparsePointTagsToClassify";
    v18 = L"REPTAGSC";
    v19 = 103;
    v20 = 20;
    v21 = 255;
    v23 = 0x1000000;
    memset_0(v22, 0, sizeof(v22));
    CSrmFunctionTracer::Trace(
      v32,
      &v16,
      L"ReparsePointTagsToClassify registry key could not be read, ignoring failure.");
    CSrmRegistryKey::~CSrmRegistryKey(v14);
    v32[0] = &CSrmFunctionTracer::`vftable';
  }
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v32);
}

```

## disassembly

```asm
0x1800a53a4  push    rbp
0x1800a53a6  push    rbx
0x1800a53a7  push    rsi
0x1800a53a8  push    rdi
0x1800a53a9  push    r12
0x1800a53ab  push    r13
0x1800a53ad  push    r14
0x1800a53af  push    r15
0x1800a53b1  lea     rbp, [rsp-168h]
0x1800a53b9  sub     rsp, 268h
0x1800a53c0  mov     rax, cs:__security_cookie
0x1800a53c7  xor     rax, rsp
0x1800a53ca  mov     [rbp+1A0h+var_50], rax
0x1800a53d1  mov     rsi, rcx
0x1800a53d4  lea     rax, [rbp+1A0h+var_1A0]
0x1800a53d8  mov     qword ptr [rsp+2A0h+var_268], rax
0x1800a53dd  lea     r13, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\scanner\\rep"...
0x1800a53e4  mov     [rbp+1A0h+var_1A0], r13
0x1800a53e8  lea     r14, aCreparsepointt; "CReparsePointTagsToClassify::PopulateRe"...
0x1800a53ef  mov     [rbp+1A0h+var_198], r14
0x1800a53f3  lea     r15, aReptagsc; "REPTAGSC"
0x1800a53fa  mov     [rbp+1A0h+var_190], r15
0x1800a53fe  mov     [rbp+1A0h+var_188], 35h ; '5'
0x1800a5405  mov     [rbp+1A0h+var_184], 14h
0x1800a540c  mov     [rbp+1A0h+var_180], 0FFh
0x1800a5413  xor     r12d, r12d
0x1800a5416  mov     [rbp+1A0h+var_118], 1000000h
0x1800a5420  xor     edx, edx; Val
0x1800a5422  lea     r8d, [r12+60h]; Size
0x1800a5427  lea     rcx, [rbp+1A0h+var_178]; void *
0x1800a542b  call    memset_0
0x1800a5430  nop
0x1800a5431  xor     r8d, r8d
0x1800a5434  lea     rdx, [rbp+1A0h+var_1A0]
0x1800a5438  lea     rcx, [rbp+1A0h+var_100]
0x1800a543f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a5444  nop
0x1800a5445  mov     rax, [rsi+8]
0x1800a5449  mov     rdi, [rax+8]
0x1800a544d  mov     rbx, rdi
0x1800a5450  cmp     [rdi+1Dh], r12b
0x1800a5454  jnz     short loc_1800A5476
0x1800a5456  mov     rdx, [rbx+10h]
0x1800a545a  mov     rcx, rsi
0x1800a545d  call    ?_Erase@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::_Node *)
0x1800a5462  mov     rbx, [rbx]
0x1800a5465  mov     rcx, rdi; Block
0x1800a5468  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a546d  mov     rdi, rbx
0x1800a5470  cmp     [rbx+1Dh], r12b
0x1800a5474  jz      short loc_1800A5456
0x1800a5476  mov     rax, [rsi+8]
0x1800a547a  mov     [rax+8], rax
0x1800a547e  mov     rax, [rsi+8]
0x1800a5482  mov     [rax], rax
0x1800a5485  mov     rax, [rsi+8]
0x1800a5489  mov     [rax+10h], rax
0x1800a548d  mov     [rsi+10h], r12
0x1800a5491  mov     [rsp+2A0h+var_248], r12
0x1800a5496  mov     [rsp+2A0h+var_250], r12
0x1800a549b  mov     [rsp+2A0h+var_258], 20019h
0x1800a54a4  mov     dword ptr [rsp+2A0h+var_258], 20119h
0x1800a54ac  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Sr"...
0x1800a54b3  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800a54ba  lea     rcx, [rsp+2A0h+var_258]; this
0x1800a54bf  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x1800a54c4  test    al, al
0x1800a54c6  jz      loc_1800A5665
0x1800a54cc  mov     [rsp+2A0h+pv], r12
0x1800a54d1  mov     [rsp+2A0h+var_268], r12d
0x1800a54d6  lea     r9, [rsp+2A0h+var_268]; unsigned int *
0x1800a54db  lea     r8, [rsp+2A0h+pv]; unsigned __int16 **
0x1800a54e0  lea     rcx, [rsp+2A0h+var_258]; this
0x1800a54e5  call    ?GetMultiszValue@CSrmRegistryKey@@QEAA_NPEBGPEAPEAGPEAK_N@Z; CSrmRegistryKey::GetMultiszValue(ushort const *,ushort * *,ulong *,bool)
0x1800a54ea  test    al, al
0x1800a54ec  jz      loc_1800A5635
0x1800a54f2  mov     rdi, [rsp+2A0h+pv]
0x1800a54f7  mov     eax, [rsp+2A0h+var_268]
0x1800a54fb  lea     r15, [rdi+rax*2]
0x1800a54ff  jmp     loc_1800A562B
0x1800a5504  cmp     rdi, r15
0x1800a5507  jnb     loc_1800A5635
0x1800a550d  mov     [rsp+2A0h+String], r12
0x1800a5512  mov     rdx, rdi; unsigned __int16 *
0x1800a5515  lea     rcx, [rsp+2A0h+String]; this
0x1800a551a  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x1800a551f  mov     rbx, [rsp+2A0h+String]
0x1800a5524  mov     rcx, rbx; String
0x1800a5527  call    cs:__imp__wtol
0x1800a552d  mov     r14d, eax
0x1800a5530  mov     [rsp+2A0h+var_238], r13
0x1800a5535  mov     [rbp+1A0h+var_21C], 14h
0x1800a553c  mov     [rbp+1A0h+var_218], 0FFh
0x1800a5543  mov     [rbp+1A0h+var_1B0], 1000000h
0x1800a554a  xor     edx, edx; Val
0x1800a554c  lea     r8d, [rdx+60h]; Size
0x1800a5550  lea     rcx, [rbp+1A0h+var_210]; void *
0x1800a5554  test    eax, eax
0x1800a5556  lea     rax, [rsp+2A0h+var_238]
0x1800a555b  jnz     short loc_1800A55A3
0x1800a555d  mov     [rbp+1A0h+var_1A8], rax
0x1800a5561  lea     rax, aCreparsepointt; "CReparsePointTagsToClassify::PopulateRe"...
0x1800a5568  mov     [rsp+2A0h+var_230], rax
0x1800a556d  lea     rax, aReptagsc; "REPTAGSC"
0x1800a5574  mov     [rsp+2A0h+var_228], rax
0x1800a5579  mov     [rbp+1A0h+var_220], 54h ; 'T'
0x1800a5580  call    memset_0
0x1800a5585  nop
0x1800a5586  xor     r9d, r9d
0x1800a5589  lea     r8, aIgnoringInvali; "Ignoring invalid reparse tag: <0x%x>"
0x1800a5590  lea     rdx, [rsp+2A0h+var_238]
0x1800a5595  lea     rcx, [rbp+1A0h+var_100]
0x1800a559c  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800a55a1  jmp     short loc_1800A5602
0x1800a55a3  mov     [rsp+2A0h+var_240], rax
0x1800a55a8  lea     rax, aCreparsepointt; "CReparsePointTagsToClassify::PopulateRe"...
0x1800a55af  mov     [rsp+2A0h+var_230], rax
0x1800a55b4  lea     rax, aReptagsc; "REPTAGSC"
0x1800a55bb  mov     [rsp+2A0h+var_228], rax
0x1800a55c0  mov     [rbp+1A0h+var_220], 5Ch ; '\'
0x1800a55c7  call    memset_0
0x1800a55cc  nop
0x1800a55cd  mov     r9d, r14d
0x1800a55d0  lea     r8, aAddingReparseT; "Adding reparse tag to m_reparsePointTag"...
0x1800a55d7  lea     rdx, [rsp+2A0h+var_238]
0x1800a55dc  lea     rcx, [rbp+1A0h+var_100]
0x1800a55e3  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800a55e8  mov     [rsp+2A0h+var_268], r14d
0x1800a55ed  lea     r8, [rsp+2A0h+var_268]
0x1800a55f2  lea     rdx, [rbp+1A0h+var_110]
0x1800a55f9  mov     rcx, rsi
0x1800a55fc  call    ??$insert@K@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@@std@@_N@1@$$QEAK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<ulong>(ulong &&)
0x1800a5601  nop
0x1800a5602  mov     rcx, rbx; pv
0x1800a5605  call    cs:__imp_CoTaskMemFree
0x1800a560b  mov     [rsp+2A0h+String], r12
0x1800a5610  mov     [rsp+2A0h+String], r12
0x1800a5615  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a5619  inc     rax
0x1800a561c  cmp     [rdi+rax*2], r12w
0x1800a5621  jnz     short loc_1800A5619
0x1800a5623  lea     rdi, [rdi+rax*2]
0x1800a5627  add     rdi, 2
0x1800a562b  cmp     [rdi], r12w
0x1800a562f  jnz     loc_1800A5504
0x1800a5635  mov     rcx, [rsp+2A0h+pv]; pv
0x1800a563a  call    cs:__imp_CoTaskMemFree
0x1800a5640  mov     [rsp+2A0h+pv], r12
0x1800a5645  mov     [rsp+2A0h+pv], r12
0x1800a564a  lea     rcx, [rsp+2A0h+var_258]; this
0x1800a564f  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x1800a5654  nop
0x1800a5655  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a565c  mov     [rbp+1A0h+var_100], rax
0x1800a5663  jmp     short loc_1800A56DC
0x1800a5665  lea     rax, [rsp+2A0h+var_238]
0x1800a566a  mov     [rsp+2A0h+var_240], rax
0x1800a566f  mov     [rsp+2A0h+var_238], r13
0x1800a5674  mov     [rsp+2A0h+var_230], r14
0x1800a5679  mov     [rsp+2A0h+var_228], r15
0x1800a567e  mov     [rbp+1A0h+var_220], 67h ; 'g'
0x1800a5685  mov     [rbp+1A0h+var_21C], 14h
0x1800a568c  mov     [rbp+1A0h+var_218], 0FFh
0x1800a5693  mov     [rbp+1A0h+var_1B0], 1000000h
0x1800a569a  xor     edx, edx; Val
0x1800a569c  lea     r8d, [rdx+60h]; Size
0x1800a56a0  lea     rcx, [rbp+1A0h+var_210]; void *
0x1800a56a4  call    memset_0
0x1800a56a9  nop
0x1800a56aa  lea     r8, aReparsepointta; "ReparsePointTagsToClassify registry key"...
0x1800a56b1  lea     rdx, [rsp+2A0h+var_238]
0x1800a56b6  lea     rcx, [rbp+1A0h+var_100]
0x1800a56bd  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800a56c2  nop
0x1800a56c3  lea     rcx, [rsp+2A0h+var_258]; this
0x1800a56c8  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x1800a56cd  nop
0x1800a56ce  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a56d5  mov     [rbp+1A0h+var_100], rax
0x1800a56dc  lea     rcx, [rbp+1A0h+var_100]; this
0x1800a56e3  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800a56e8  mov     rcx, [rbp+1A0h+var_50]
0x1800a56ef  xor     rcx, rsp; StackCookie
0x1800a56f2  call    __security_check_cookie
0x1800a56f7  add     rsp, 268h
0x1800a56fe  pop     r15
0x1800a5700  pop     r14
0x1800a5702  pop     r13
0x1800a5704  pop     r12
0x1800a5706  pop     rdi
0x1800a5707  pop     rsi
0x1800a5708  pop     rbx
0x1800a5709  pop     rbp
0x1800a570a  retn
```
