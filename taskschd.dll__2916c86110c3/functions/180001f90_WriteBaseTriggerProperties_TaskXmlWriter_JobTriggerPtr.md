# WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180001f90`
- end: `0x1800023d4`
- name: `?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `1092`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001098`
- `0x18000129c`
- `0x180001588`
- `0x180001924`
- `0x180013c6c`
- `0x180013f20`
- `0x1800374a8`
- `0x180037640`
- `0x18003e830`

## callees

- `0x1800017f0`
- `0x180001f90`
- `0x1800023dc`
- `0x180003840`
- `0x180003d1c`
- `0x1800136e0`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002025`
- `OLEAUT32!__imp_SysFreeString` at `0x180002030`
- `OLEAUT32!__imp_SysFreeString` at `0x1800020c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800020d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800020de`
- `OLEAUT32!__imp_SysFreeString` at `0x180002129`
- `OLEAUT32!__imp_SysFreeString` at `0x180002134`
- `OLEAUT32!__imp_SysFreeString` at `0x18000213f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800022fb`
- `OLEAUT32!__imp_SysFreeString` at `0x180002342`
- `OLEAUT32!__imp_SysFreeString` at `0x18000234d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002358`
- `OLEAUT32!__imp_SysFreeString` at `0x180002371`
- `OLEAUT32!__imp_SysFreeString` at `0x18000237c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002025`
- `OLEAUT32!__imp_SysFreeString` at `0x180002030`
- `OLEAUT32!__imp_SysFreeString` at `0x1800020c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800020d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800020de`
- `OLEAUT32!__imp_SysFreeString` at `0x180002129`
- `OLEAUT32!__imp_SysFreeString` at `0x180002134`
- `OLEAUT32!__imp_SysFreeString` at `0x18000213f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021df`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800022fb`
- `OLEAUT32!__imp_SysFreeString` at `0x180002342`
- `OLEAUT32!__imp_SysFreeString` at `0x18000234d`
- `OLEAUT32!__imp_SysFreeString` at `0x180002358`
- `OLEAUT32!__imp_SysFreeString` at `0x180002371`
- `OLEAUT32!__imp_SysFreeString` at `0x18000237c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800020fc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800021b2`
- `OLEAUT32!__imp_SysStringLen` at `0x180002250`
- `OLEAUT32!__imp_SysStringLen` at `0x180002315`
- `OLEAUT32!__imp_SysStringLen` at `0x1800023a5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800020fc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800021b2`
- `OLEAUT32!__imp_SysStringLen` at `0x180002250`
- `OLEAUT32!__imp_SysStringLen` at `0x180002315`
- `OLEAUT32!__imp_SysStringLen` at `0x1800023a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WriteBaseTriggerProperties(int *a1, __int64 *a2)
{
  __int64 Repetition; // rax
  __int64 v5; // rbx
  const wchar_t *v6; // r15
  int started; // edi
  const wchar_t *v9; // r8
  int v10; // eax
  OLECHAR *v11; // rcx
  BSTR v12; // [rsp+20h] [rbp-30h] BYREF
  BSTR v13; // [rsp+28h] [rbp-28h] BYREF
  BSTR pbstr; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  BSTR v16; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+48h] [rbp-8h] BYREF
  __int16 v18; // [rsp+A0h] [rbp+50h] BYREF
  __int16 v19; // [rsp+A8h] [rbp+58h] BYREF

  Repetition = JobTriggerPtrBase<ITrigger>::GetRepetition(a2);
  v5 = Repetition;
  if ( Repetition )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)Repetition + 8LL))(Repetition);
  v17 = v5;
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = L"true";
  if ( v5 )
  {
    v16 = 0;
    bstrString = 0;
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v5 + 56LL))(v5, &v16) >= 0 && v16 && SysStringLen(v16) )
    {
      started = TaskXmlWriter::StartElement(a1, (struct IErrorInfo *)0xD);
      if ( started < 0 )
      {
        SysFreeString(bstrString);
        SysFreeString(v16);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        goto LABEL_20;
      }
      started = TaskXmlWriter::Element((unsigned int *)a1, 14, (__int64)v16);
      if ( started < 0 )
        goto LABEL_42;
      if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v5 + 72LL))(v5, &bstrString) >= 0 )
      {
        if ( bstrString )
        {
          if ( SysStringLen(bstrString) )
          {
            started = TaskXmlWriter::Element((unsigned int *)a1, 15, (__int64)bstrString);
            if ( started < 0 )
              goto LABEL_42;
          }
        }
      }
      v18 = 0;
      if ( (*(int (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v5 + 88LL))(v5, &v18) >= 0 )
      {
        v9 = L"true";
        if ( !v18 )
          v9 = L"false";
        v10 = TaskXmlWriter::Element((unsigned int *)a1, 16, (__int64)v9);
        if ( v10 < 0 )
          goto LABEL_41;
      }
      v10 = TaskXmlWriter::EndElement((__int64)a1);
      if ( v10 < 0 )
      {
LABEL_41:
        started = v10;
LABEL_42:
        SysFreeString(bstrString);
        v11 = v16;
LABEL_47:
        SysFreeString(v11);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
        goto LABEL_20;
      }
    }
    SysFreeString(bstrString);
    SysFreeString(v16);
  }
  pbstr = 0;
  v13 = 0;
  v12 = 0;
  if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)*a2 + 112LL))(*a2, &pbstr) >= 0
    && pbstr
    && SysStringLen(pbstr)
    && (started = TaskXmlWriter::Element((unsigned int *)a1, 17, (__int64)pbstr), started < 0) )
  {
    SysFreeString(v12);
    SysFreeString(v13);
    SysFreeString(pbstr);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)*a2 + 128LL))(*a2, &v13) >= 0
         && v13
         && SysStringLen(v13)
         && (started = TaskXmlWriter::Element((unsigned int *)a1, 18, (__int64)v13), started < 0) )
  {
    SysFreeString(v12);
    SysFreeString(v13);
    SysFreeString(pbstr);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)*a2 + 96LL))(*a2, &v12) >= 0 )
    {
      if ( v12 )
      {
        if ( SysStringLen(v12) )
        {
          started = TaskXmlWriter::Element((unsigned int *)a1, 20, (__int64)v12);
          if ( started < 0 )
            goto LABEL_46;
        }
      }
    }
    v19 = 0;
    started = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)*a2 + 144LL))(*a2, &v19);
    if ( started >= 0 )
    {
      if ( !v19 )
        v6 = L"false";
      started = TaskXmlWriter::Element((unsigned int *)a1, 19, (__int64)v6);
      if ( started < 0 )
      {
LABEL_46:
        SysFreeString(v12);
        SysFreeString(v13);
        v11 = pbstr;
        goto LABEL_47;
      }
    }
    SysFreeString(v12);
    SysFreeString(v13);
    SysFreeString(pbstr);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
LABEL_20:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a2);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180001f90  mov     [rsp-38h+arg_0], rbx
0x180001f95  mov     [rsp-38h+arg_8], rdx
0x180001f9a  push    rbp
0x180001f9b  push    rsi
0x180001f9c  push    rdi
0x180001f9d  push    r12
0x180001f9f  push    r13
0x180001fa1  push    r14
0x180001fa3  push    r15
0x180001fa5  mov     rbp, rsp
0x180001fa8  sub     rsp, 50h
0x180001fac  mov     r14, rdx
0x180001faf  mov     rsi, rcx
0x180001fb2  mov     rcx, rdx
0x180001fb5  call    ?GetRepetition@?$JobTriggerPtrBase@UITrigger@@@@QEAAPEAUIRepetitionPattern@@XZ; JobTriggerPtrBase<ITrigger>::GetRepetition(void)
0x180001fba  mov     rbx, rax
0x180001fbd  xor     r12d, r12d
0x180001fc0  test    rax, rax
0x180001fc3  jnz     loc_18000217D
0x180001fc9  mov     [rbp+var_8], rbx
0x180001fcd  test    rbx, rbx
0x180001fd0  jnz     loc_180002191
0x180001fd6  test    rbx, rbx
0x180001fd9  jz      short loc_180001FEB
0x180001fdb  mov     rax, [rbx]
0x180001fde  mov     rcx, rbx
0x180001fe1  mov     rax, [rax+10h]
0x180001fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fea  nop
0x180001feb  lea     r13, aFalse; "false"
0x180001ff2  lea     r15, aTrue; "true"
0x180001ff9  test    rbx, rbx
0x180001ffc  jz      short loc_180002036
0x180001ffe  mov     [rbp+var_10], r12
0x180002002  mov     [rbp+bstrString], r12
0x180002006  mov     rax, [rbx]
0x180002009  lea     rdx, [rbp+var_10]
0x18000200d  mov     rcx, rbx
0x180002010  mov     rax, [rax+38h]
0x180002014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002019  test    eax, eax
0x18000201b  jns     loc_180002243
0x180002021  mov     rcx, [rbp+bstrString]; bstrString
0x180002025  call    cs:__imp_SysFreeString
0x18000202b  nop
0x18000202c  mov     rcx, [rbp+var_10]; bstrString
0x180002030  call    cs:__imp_SysFreeString
0x180002036  mov     [rbp+pbstr], r12
0x18000203a  mov     [rbp+var_28], r12
0x18000203e  mov     [rbp+var_30], r12
0x180002042  mov     rcx, [r14]
0x180002045  mov     rax, [rcx]
0x180002048  lea     rdx, [rbp+pbstr]
0x18000204c  mov     rax, [rax+70h]
0x180002050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002055  test    eax, eax
0x180002057  js      short loc_180002066
0x180002059  mov     rcx, [rbp+pbstr]; pbstr
0x18000205d  test    rcx, rcx
0x180002060  jnz     loc_1800020FC
0x180002066  mov     rcx, [r14]
0x180002069  mov     rax, [rcx]
0x18000206c  lea     rdx, [rbp+var_28]
0x180002070  mov     rax, [rax+80h]
0x180002077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000207c  test    eax, eax
0x18000207e  jns     loc_1800021A5
0x180002084  mov     rcx, [r14]
0x180002087  mov     rax, [rcx]
0x18000208a  lea     rdx, [rbp+var_30]
0x18000208e  mov     rax, [rax+60h]
0x180002092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002097  test    eax, eax
0x180002099  jns     loc_180002308
0x18000209f  mov     [rbp+arg_18], r12w
0x1800020a4  mov     rcx, [r14]
0x1800020a7  mov     rax, [rcx]
0x1800020aa  lea     rdx, [rbp+arg_18]
0x1800020ae  mov     rax, [rax+90h]
0x1800020b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ba  mov     edi, eax
0x1800020bc  test    eax, eax
0x1800020be  jns     loc_180002216
0x1800020c4  mov     rcx, [rbp+var_30]; bstrString
0x1800020c8  call    cs:__imp_SysFreeString
0x1800020ce  nop
0x1800020cf  mov     rcx, [rbp+var_28]; bstrString
0x1800020d3  call    cs:__imp_SysFreeString
0x1800020d9  nop
0x1800020da  mov     rcx, [rbp+pbstr]; bstrString
0x1800020de  call    cs:__imp_SysFreeString
0x1800020e4  nop
0x1800020e5  test    rbx, rbx
0x1800020e8  jz      short loc_1800020FA
0x1800020ea  mov     rax, [rbx]
0x1800020ed  mov     rcx, rbx
0x1800020f0  mov     rax, [rax+10h]
0x1800020f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020f9  nop
0x1800020fa  jmp     short loc_18000215B
0x1800020fc  call    cs:__imp_SysStringLen
0x180002102  test    eax, eax
0x180002104  jz      loc_180002066
0x18000210a  mov     r8, [rbp+pbstr]
0x18000210e  mov     edx, 11h
0x180002113  mov     rcx, rsi
0x180002116  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000211b  mov     edi, eax
0x18000211d  test    eax, eax
0x18000211f  jns     loc_180002066
0x180002125  mov     rcx, [rbp+var_30]; bstrString
0x180002129  call    cs:__imp_SysFreeString
0x18000212f  nop
0x180002130  mov     rcx, [rbp+var_28]; bstrString
0x180002134  call    cs:__imp_SysFreeString
0x18000213a  nop
0x18000213b  mov     rcx, [rbp+pbstr]; bstrString
0x18000213f  call    cs:__imp_SysFreeString
0x180002145  nop
0x180002146  test    rbx, rbx
0x180002149  jz      short loc_18000215B
0x18000214b  mov     rax, [rbx]
0x18000214e  mov     rcx, rbx
0x180002151  mov     rax, [rax+10h]
0x180002155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000215a  nop
0x18000215b  mov     rcx, r14
0x18000215e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180002163  mov     eax, edi
0x180002165  mov     rbx, [rsp+50h+arg_0]
0x18000216d  add     rsp, 50h
0x180002171  pop     r15
0x180002173  pop     r14
0x180002175  pop     r13
0x180002177  pop     r12
0x180002179  pop     rdi
0x18000217a  pop     rsi
0x18000217b  pop     rbp
0x18000217c  retn
0x18000217d  mov     rdx, [rax]
0x180002180  mov     rcx, rbx
0x180002183  mov     rax, [rdx+8]
0x180002187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000218c  jmp     loc_180001FC9
0x180002191  mov     rax, [rbx]
0x180002194  mov     rcx, rbx
0x180002197  mov     rax, [rax+8]
0x18000219b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a0  jmp     loc_180001FD6
0x1800021a5  mov     rcx, [rbp+var_28]; pbstr
0x1800021a9  test    rcx, rcx
0x1800021ac  jz      loc_180002084
0x1800021b2  call    cs:__imp_SysStringLen
0x1800021b8  test    eax, eax
0x1800021ba  jz      loc_180002084
0x1800021c0  mov     r8, [rbp+var_28]
0x1800021c4  mov     edx, 12h
0x1800021c9  mov     rcx, rsi
0x1800021cc  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800021d1  mov     edi, eax
0x1800021d3  test    eax, eax
0x1800021d5  jns     loc_180002084
0x1800021db  mov     rcx, [rbp+var_30]; bstrString
0x1800021df  call    cs:__imp_SysFreeString
0x1800021e5  nop
0x1800021e6  mov     rcx, [rbp+var_28]; bstrString
0x1800021ea  call    cs:__imp_SysFreeString
0x1800021f0  nop
0x1800021f1  mov     rcx, [rbp+pbstr]; bstrString
0x1800021f5  call    cs:__imp_SysFreeString
0x1800021fb  nop
0x1800021fc  test    rbx, rbx
0x1800021ff  jz      short loc_180002211
0x180002201  mov     rax, [rbx]
0x180002204  mov     rcx, rbx
0x180002207  mov     rax, [rax+10h]
0x18000220b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002210  nop
0x180002211  jmp     loc_18000215B
0x180002216  cmp     [rbp+arg_18], r12w
0x18000221b  setnz   al
0x18000221e  test    al, al
0x180002220  cmovz   r15, r13
0x180002224  mov     r8, r15
0x180002227  mov     edx, 13h
0x18000222c  mov     rcx, rsi
0x18000222f  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002234  mov     edi, eax
0x180002236  test    eax, eax
0x180002238  jns     loc_1800020C4
0x18000223e  jmp     loc_18000233E
0x180002243  mov     rcx, [rbp+var_10]; pbstr
0x180002247  test    rcx, rcx
0x18000224a  jz      loc_180002021
0x180002250  call    cs:__imp_SysStringLen
0x180002256  test    eax, eax
0x180002258  jz      loc_180002021
0x18000225e  mov     edx, 0Dh
0x180002263  mov     rcx, rsi
0x180002266  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18000226b  mov     edi, eax
0x18000226d  test    eax, eax
0x18000226f  js      loc_18000236D
0x180002275  mov     r8, [rbp+var_10]
0x180002279  mov     edx, 0Eh
0x18000227e  mov     rcx, rsi
0x180002281  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002286  mov     edi, eax
0x180002288  test    eax, eax
0x18000228a  js      short loc_1800022F7
0x18000228c  mov     rax, [rbx]
0x18000228f  lea     rdx, [rbp+bstrString]
0x180002293  mov     rcx, rbx
0x180002296  mov     rax, [rax+48h]
0x18000229a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000229f  test    eax, eax
0x1800022a1  jns     loc_180002398
0x1800022a7  mov     [rbp+arg_10], r12w
0x1800022ac  mov     rax, [rbx]
0x1800022af  lea     rdx, [rbp+arg_10]
0x1800022b3  mov     rcx, rbx
0x1800022b6  mov     rax, [rax+58h]
0x1800022ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022bf  test    eax, eax
0x1800022c1  js      short loc_1800022E5
0x1800022c3  cmp     [rbp+arg_10], r12w
0x1800022c8  setnz   al
0x1800022cb  mov     r8, r15
0x1800022ce  test    al, al
0x1800022d0  cmovz   r8, r13
0x1800022d4  mov     edx, 10h
0x1800022d9  mov     rcx, rsi
0x1800022dc  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800022e1  test    eax, eax
0x1800022e3  js      short loc_1800022F5
0x1800022e5  mov     rcx, rsi
0x1800022e8  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x1800022ed  test    eax, eax
0x1800022ef  jns     loc_180002021
0x1800022f5  mov     edi, eax
0x1800022f7  mov     rcx, [rbp+bstrString]; bstrString
0x1800022fb  call    cs:__imp_SysFreeString
0x180002301  nop
0x180002302  mov     rcx, [rbp+var_10]
0x180002306  jmp     short loc_180002358
0x180002308  mov     rcx, [rbp+var_30]; pbstr
0x18000230c  test    rcx, rcx
0x18000230f  jz      loc_18000209F
0x180002315  call    cs:__imp_SysStringLen
0x18000231b  test    eax, eax
0x18000231d  jz      loc_18000209F
0x180002323  mov     r8, [rbp+var_30]
0x180002327  mov     edx, 14h
0x18000232c  mov     rcx, rsi
0x18000232f  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002334  mov     edi, eax
0x180002336  test    eax, eax
0x180002338  jns     loc_18000209F
0x18000233e  mov     rcx, [rbp+var_30]; bstrString
0x180002342  call    cs:__imp_SysFreeString
0x180002348  nop
0x180002349  mov     rcx, [rbp+var_28]; bstrString
0x18000234d  call    cs:__imp_SysFreeString
0x180002353  nop
0x180002354  mov     rcx, [rbp+pbstr]; bstrString
0x180002358  call    cs:__imp_SysFreeString
0x18000235e  nop
0x18000235f  lea     rcx, [rbp+var_8]
0x180002363  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180002368  jmp     loc_18000215B
0x18000236d  mov     rcx, [rbp+bstrString]; bstrString
0x180002371  call    cs:__imp_SysFreeString
0x180002377  nop
0x180002378  mov     rcx, [rbp+var_10]; bstrString
0x18000237c  call    cs:__imp_SysFreeString
0x180002382  nop
0x180002383  mov     rcx, [rbx]
0x180002386  mov     rax, [rcx+10h]
0x18000238a  mov     rcx, rbx
0x18000238d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002392  nop
0x180002393  jmp     loc_18000215B
0x180002398  mov     rcx, [rbp+bstrString]; pbstr
0x18000239c  test    rcx, rcx
0x18000239f  jz      loc_1800022A7
0x1800023a5  call    cs:__imp_SysStringLen
0x1800023ab  test    eax, eax
0x1800023ad  jz      loc_1800022A7
0x1800023b3  mov     r8, [rbp+bstrString]
0x1800023b7  mov     edx, 0Fh
0x1800023bc  mov     rcx, rsi
0x1800023bf  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800023c4  mov     edi, eax
0x1800023c6  test    eax, eax
0x1800023c8  js      loc_1800022F7
0x1800023ce  jmp     loc_1800022A7
```
