# CVssFunctionTracer::AddContextInternal(CVssDebugInfo,_VssContextType,ushort const *,ushort const *)

- ea: `0x180034484`
- end: `0x18003474c`
- name: `?AddContextInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@W4_VssContextType@@PEBG2@Z`
- size: `712`
- prototype: `void __fastcall(struct CVssFunctionTracer *, const struct CVssDebugInfo *, int, __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034278`
- `0x180034324`
- `0x180034754`
- `0x180034a4c`

## callees

- `0x180001580`
- `0x180017284`
- `0x18002e79c`
- `0x1800332c0`
- `0x180033304`
- `0x1800336cc`
- `0x180033708`
- `0x180033990`
- `0x1800339c0`
- `0x180033c2c`
- `0x180033da4`
- `0x180034484`
- `0x180036af8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800346e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800346e0`

## pseudocode

```c
void __fastcall CVssFunctionTracer::AddContextInternal(
        struct CVssFunctionTracer *a1,
        const struct CVssDebugInfo *a2,
        int a3,
        __int64 a4,
        const unsigned __int16 *a5)
{
  __int64 v6; // r12
  const unsigned __int16 *v9; // rdi
  char *v10; // rbx
  __int64 v11; // rax
  CVssDebugInfo *v12; // rax
  __int64 v13; // r12
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rdx
  const unsigned __int16 *v23; // r8
  int v24; // [rsp+40h] [rbp-1E8h] BYREF
  const struct CVssDebugInfo *v25; // [rsp+50h] [rbp-1D8h]
  _BYTE v26[168]; // [rsp+58h] [rbp-1D0h] BYREF
  unsigned __int16 *v27[4]; // [rsp+100h] [rbp-128h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-108h] BYREF
  _QWORD v29[4]; // [rsp+140h] [rbp-E8h] BYREF
  _QWORD v30[4]; // [rsp+160h] [rbp-C8h] BYREF
  _QWORD v31[4]; // [rsp+180h] [rbp-A8h] BYREF
  _QWORD v32[4]; // [rsp+1A0h] [rbp-88h] BYREF
  _QWORD v33[4]; // [rsp+1C0h] [rbp-68h] BYREF

  v6 = a3;
  v25 = a2;
  v9 = &qword_180050E70;
  if ( a5 )
    v9 = a5;
  std::wstring::wstring(v27);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v10 = (char *)a1 + 8 * v6;
    if ( *((_QWORD *)v10 + 8) )
    {
      v11 = std::wstring::wstring(v28);
      std::wstring::operator=(v27, v11);
      std::wstring::_Tidy_deallocate(v28);
    }
    v12 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v26, a2);
    if ( a4 )
    {
      CVssFunctionTracer::TraceInternalWithFormat(
        a1,
        v12,
        L"CONTEXT",
        120,
        L"Adding context: '%s' = '%s' (%d)",
        a4,
        v9,
        v6);
      v13 = std::wstring::wstring(v30);
      v14 = std::wstring::wstring(v29);
      v15 = std::operator+<unsigned short>(v33, v27);
      std::wstring::wstring(v28, v16, v15, v14);
      v17 = std::operator+<unsigned short>(v32, v28, L": ");
      std::wstring::wstring(v31, v18, v17, v13);
      std::wstring::operator=(v27, v31);
      std::wstring::_Tidy_deallocate(v31);
      std::wstring::_Tidy_deallocate(v32);
      std::wstring::_Tidy_deallocate(v28);
      std::wstring::_Tidy_deallocate(v33);
      std::wstring::_Tidy_deallocate(v29);
      v19 = v30;
    }
    else
    {
      CVssFunctionTracer::TraceInternalWithFormat(a1, v12, L"CONTEXT", 120, L"Adding context: '%s' (%d)", v9, v6);
      v20 = std::wstring::wstring(v29);
      v21 = std::operator+<unsigned short>(v30, v27);
      std::wstring::wstring(v28, v22, v21, v20);
      std::wstring::operator=(v27, v28);
      std::wstring::_Tidy_deallocate(v28);
      std::wstring::_Tidy_deallocate(v30);
      v19 = v29;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v24 = -2147024882;
      throw (long *)&v24;
    }
  }
  std::wstring::_Tidy_deallocate(v19);
  CoTaskMemFree(*((LPVOID *)v10 + 8));
  *((_QWORD *)v10 + 8) = 0;
  v23 = (const unsigned __int16 *)v27;
  if ( v27[3] > (unsigned __int16 *)7 )
    v23 = v27[0];
  ((void (__stdcall *)(struct CVssFunctionTracer *, unsigned __int16 **, const unsigned __int16 *))VssSafeDuplicateStr)(
    a1,
    (unsigned __int16 **)v10 + 8,
    v23);
  std::wstring::_Tidy_deallocate(v27);
  CVssDebugInfo::~CVssDebugInfo(a2);
}

```

## disassembly

```asm
0x180034484  push    rbx
0x180034486  push    rsi
0x180034487  push    rdi
0x180034488  push    r12
0x18003448a  push    r14
0x18003448c  push    r15
0x18003448e  sub     rsp, 1F8h
0x180034495  mov     rax, cs:__security_cookie
0x18003449c  xor     rax, rsp
0x18003449f  mov     [rsp+228h+var_48], rax
0x1800344a7  mov     r14, r9
0x1800344aa  movsxd  r12, r8d
0x1800344ad  mov     rsi, rdx
0x1800344b0  mov     r15, rcx
0x1800344b3  mov     rax, [rsp+228h+arg_20]
0x1800344bb  mov     [rsp+228h+var_1D8], rdx
0x1800344c0  lea     rdi, qword_180050E70
0x1800344c7  test    rax, rax
0x1800344ca  cmovnz  rdi, rax
0x1800344ce  lea     rcx, [rsp+228h+var_128]; void *
0x1800344d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800344db  nop
0x1800344dc  lea     rbx, [r15+r12*8]
0x1800344e0  mov     rdx, [rbx+40h]
0x1800344e4  test    rdx, rdx
0x1800344e7  jz      short loc_180034513
0x1800344e9  lea     rcx, [rsp+228h+var_108]
0x1800344f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800344f6  mov     rdx, rax
0x1800344f9  lea     rcx, [rsp+228h+var_128]
0x180034501  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180034506  lea     rcx, [rsp+228h+var_108]
0x18003450e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034513  mov     rdx, rsi; struct CVssDebugInfo *
0x180034516  lea     rcx, [rsp+228h+var_1D0]; this
0x18003451b  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180034520  mov     r9d, 78h ; 'x'
0x180034526  lea     r8, aContext; "CONTEXT"
0x18003452d  mov     rdx, rax
0x180034530  test    r14, r14
0x180034533  jz      loc_180034644
0x180034539  mov     [rsp+228h+var_1F0], r12d
0x18003453e  mov     [rsp+228h+var_1F8], rdi
0x180034543  mov     [rsp+228h+var_200], r14
0x180034548  lea     rcx, aAddingContextS_0; "Adding context: '%s' = '%s' (%d)"
0x18003454f  mov     [rsp+228h+var_208], rcx
0x180034554  mov     rcx, r15
0x180034557  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1ZZ; CVssFunctionTracer::TraceInternalWithFormat(CVssDebugInfo,ushort const *,ulong,ushort const *,...)
0x18003455c  mov     rdx, rdi
0x18003455f  lea     rcx, [rsp+228h+var_C8]
0x180034567  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003456c  mov     r12, rax
0x18003456f  mov     rdx, r14
0x180034572  lea     rcx, [rsp+228h+var_E8]
0x18003457a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003457f  mov     rdi, rax
0x180034582  lea     rdx, [rsp+228h+var_128]
0x18003458a  lea     rcx, [rsp+228h+var_68]
0x180034592  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180034597  nop
0x180034598  mov     r9, rdi
0x18003459b  mov     r8, rax
0x18003459e  lea     rcx, [rsp+228h+var_108]
0x1800345a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800345ab  nop
0x1800345ac  lea     r8, asc_18005D688; ": "
0x1800345b3  lea     rdx, [rsp+228h+var_108]
0x1800345bb  lea     rcx, [rsp+228h+var_88]
0x1800345c3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800345c8  nop
0x1800345c9  mov     r9, r12
0x1800345cc  mov     r8, rax
0x1800345cf  lea     rcx, [rsp+228h+var_A8]
0x1800345d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800345dc  lea     rdx, [rsp+228h+var_A8]
0x1800345e4  lea     rcx, [rsp+228h+var_128]
0x1800345ec  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800345f1  lea     rcx, [rsp+228h+var_A8]
0x1800345f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800345fe  nop
0x1800345ff  lea     rcx, [rsp+228h+var_88]
0x180034607  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003460c  nop
0x18003460d  lea     rcx, [rsp+228h+var_108]
0x180034615  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003461a  nop
0x18003461b  lea     rcx, [rsp+228h+var_68]
0x180034623  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034628  nop
0x180034629  lea     rcx, [rsp+228h+var_E8]
0x180034631  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034636  nop
0x180034637  lea     rcx, [rsp+228h+var_C8]
0x18003463f  jmp     loc_1800346D7
0x180034644  mov     dword ptr [rsp+228h+var_1F8], r12d
0x180034649  mov     [rsp+228h+var_200], rdi
0x18003464e  lea     rcx, aAddingContextS; "Adding context: '%s' (%d)"
0x180034655  mov     [rsp+228h+var_208], rcx
0x18003465a  mov     rcx, r15
0x18003465d  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1ZZ; CVssFunctionTracer::TraceInternalWithFormat(CVssDebugInfo,ushort const *,ulong,ushort const *,...)
0x180034662  mov     rdx, rdi
0x180034665  lea     rcx, [rsp+228h+var_E8]
0x18003466d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180034672  mov     rdi, rax
0x180034675  lea     rdx, [rsp+228h+var_128]
0x18003467d  lea     rcx, [rsp+228h+var_C8]
0x180034685  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003468a  nop
0x18003468b  mov     r9, rdi
0x18003468e  mov     r8, rax
0x180034691  lea     rcx, [rsp+228h+var_108]
0x180034699  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x18003469e  lea     rdx, [rsp+228h+var_108]
0x1800346a6  lea     rcx, [rsp+228h+var_128]
0x1800346ae  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800346b3  lea     rcx, [rsp+228h+var_108]
0x1800346bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800346c0  nop
0x1800346c1  lea     rcx, [rsp+228h+var_C8]
0x1800346c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800346ce  nop
0x1800346cf  lea     rcx, [rsp+228h+var_E8]
0x1800346d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800346dc  mov     rcx, [rbx+40h]; pv
0x1800346e0  call    cs:__imp_CoTaskMemFree
0x1800346e6  mov     qword ptr [rbx+40h], 0
0x1800346ee  lea     r8, [rsp+228h+var_128]
0x1800346f6  cmp     [rsp+228h+var_110], 7
0x1800346ff  cmova   r8, [rsp+228h+var_128]; unsigned __int16 *
0x180034708  lea     rdx, [rbx+40h]; unsigned __int16 **
0x18003470c  mov     rcx, r15; struct CVssFunctionTracer *
0x18003470f  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x180034714  nop
0x180034715  lea     rcx, [rsp+228h+var_128]
0x18003471d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034722  nop
0x180034723  mov     rcx, rsi; this
0x180034726  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x18003472b  mov     rcx, [rsp+228h+var_48]
0x180034733  xor     rcx, rsp; StackCookie
0x180034736  call    __security_check_cookie
0x18003473b  add     rsp, 1F8h
0x180034742  pop     r15
0x180034744  pop     r14
0x180034746  pop     r12
0x180034748  pop     rdi
0x180034749  pop     rsi
0x18003474a  pop     rbx
0x18003474b  retn
```
