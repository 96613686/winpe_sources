# WriteBaseTriggerProperties(TaskXmlWriter &,JobTriggerPtr)

- ea: `0x180001fe4`
- end: `0x1800024ad`
- name: `?WriteBaseTriggerProperties@@YAJAEAVTaskXmlWriter@@VJobTriggerPtr@@@Z`
- size: `1225`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001098`
- `0x1800012c0`
- `0x1800015e0`
- `0x18000196c`
- `0x180014b1c`
- `0x180014df0`
- `0x18003a500`
- `0x18003a730`
- `0x180041d90`

## callees

- `0x180001880`
- `0x180001fe4`
- `0x1800024b4`
- `0x180003a30`
- `0x180003f30`
- `0x1800145c0`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002079`
- `OLEAUT32!__imp_SysFreeString` at `0x18000208a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002128`
- `OLEAUT32!__imp_SysFreeString` at `0x180002139`
- `OLEAUT32!__imp_SysFreeString` at `0x18000214a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180002270`
- `OLEAUT32!__imp_SysFreeString` at `0x180002281`
- `OLEAUT32!__imp_SysFreeString` at `0x180002292`
- `OLEAUT32!__imp_SysFreeString` at `0x1800023a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800023f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180002408`
- `OLEAUT32!__imp_SysFreeString` at `0x180002419`
- `OLEAUT32!__imp_SysFreeString` at `0x180002438`
- `OLEAUT32!__imp_SysFreeString` at `0x180002449`
- `OLEAUT32!__imp_SysFreeString` at `0x180002079`
- `OLEAUT32!__imp_SysFreeString` at `0x18000208a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002128`
- `OLEAUT32!__imp_SysFreeString` at `0x180002139`
- `OLEAUT32!__imp_SysFreeString` at `0x18000214a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800021c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180002270`
- `OLEAUT32!__imp_SysFreeString` at `0x180002281`
- `OLEAUT32!__imp_SysFreeString` at `0x180002292`
- `OLEAUT32!__imp_SysFreeString` at `0x1800023a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800023f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180002408`
- `OLEAUT32!__imp_SysFreeString` at `0x180002419`
- `OLEAUT32!__imp_SysFreeString` at `0x180002438`
- `OLEAUT32!__imp_SysFreeString` at `0x180002449`
- `OLEAUT32!__imp_SysStringLen` at `0x18000216e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000223d`
- `OLEAUT32!__imp_SysStringLen` at `0x1800022f3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800023c4`
- `OLEAUT32!__imp_SysStringLen` at `0x180002478`
- `OLEAUT32!__imp_SysStringLen` at `0x18000216e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000223d`
- `OLEAUT32!__imp_SysStringLen` at `0x1800022f3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800023c4`
- `OLEAUT32!__imp_SysStringLen` at `0x180002478`

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
0x180001fe4  mov     [rsp-38h+arg_0], rbx
0x180001fe9  mov     [rsp-38h+arg_8], rdx
0x180001fee  push    rbp
0x180001fef  push    rsi
0x180001ff0  push    rdi
0x180001ff1  push    r12
0x180001ff3  push    r13
0x180001ff5  push    r14
0x180001ff7  push    r15
0x180001ff9  mov     rbp, rsp
0x180001ffc  sub     rsp, 50h
0x180002000  mov     r14, rdx
0x180002003  mov     rsi, rcx
0x180002006  mov     rcx, rdx
0x180002009  call    ?GetRepetition@?$JobTriggerPtrBase@UITrigger@@@@QEAAPEAUIRepetitionPattern@@XZ; JobTriggerPtrBase<ITrigger>::GetRepetition(void)
0x18000200e  mov     rbx, rax
0x180002011  xor     r12d, r12d
0x180002014  test    rax, rax
0x180002017  jnz     loc_180002208
0x18000201d  mov     [rbp+var_8], rbx
0x180002021  test    rbx, rbx
0x180002024  jnz     loc_18000221C
0x18000202a  test    rbx, rbx
0x18000202d  jz      short loc_18000203F
0x18000202f  mov     rax, [rbx]
0x180002032  mov     rcx, rbx
0x180002035  mov     rax, [rax+10h]
0x180002039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000203e  nop
0x18000203f  lea     r13, aFalse; "false"
0x180002046  lea     r15, aTrue; "true"
0x18000204d  test    rbx, rbx
0x180002050  jz      short loc_180002096
0x180002052  mov     [rbp+var_10], r12
0x180002056  mov     [rbp+bstrString], r12
0x18000205a  mov     rax, [rbx]
0x18000205d  lea     rdx, [rbp+var_10]
0x180002061  mov     rcx, rbx
0x180002064  mov     rax, [rax+38h]
0x180002068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000206d  test    eax, eax
0x18000206f  jns     loc_1800022E6
0x180002075  mov     rcx, [rbp+bstrString]; bstrString
0x180002079  call    cs:__imp_SysFreeString
0x180002080  nop     dword ptr [rax+rax+00h]
0x180002085  nop
0x180002086  mov     rcx, [rbp+var_10]; bstrString
0x18000208a  call    cs:__imp_SysFreeString
0x180002091  nop     dword ptr [rax+rax+00h]
0x180002096  mov     [rbp+pbstr], r12
0x18000209a  mov     [rbp+var_28], r12
0x18000209e  mov     [rbp+var_30], r12
0x1800020a2  mov     rcx, [r14]
0x1800020a5  mov     rax, [rcx]
0x1800020a8  lea     rdx, [rbp+pbstr]
0x1800020ac  mov     rax, [rax+70h]
0x1800020b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020b5  test    eax, eax
0x1800020b7  js      short loc_1800020C6
0x1800020b9  mov     rcx, [rbp+pbstr]; pbstr
0x1800020bd  test    rcx, rcx
0x1800020c0  jnz     loc_18000216E
0x1800020c6  mov     rcx, [r14]
0x1800020c9  mov     rax, [rcx]
0x1800020cc  lea     rdx, [rbp+var_28]
0x1800020d0  mov     rax, [rax+80h]
0x1800020d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020dc  test    eax, eax
0x1800020de  jns     loc_180002230
0x1800020e4  mov     rcx, [r14]
0x1800020e7  mov     rax, [rcx]
0x1800020ea  lea     rdx, [rbp+var_30]
0x1800020ee  mov     rax, [rax+60h]
0x1800020f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020f7  test    eax, eax
0x1800020f9  jns     loc_1800023B7
0x1800020ff  mov     [rbp+arg_18], r12w
0x180002104  mov     rcx, [r14]
0x180002107  mov     rax, [rcx]
0x18000210a  lea     rdx, [rbp+arg_18]
0x18000210e  mov     rax, [rax+90h]
0x180002115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000211a  mov     edi, eax
0x18000211c  test    eax, eax
0x18000211e  jns     loc_1800022B9
0x180002124  mov     rcx, [rbp+var_30]; bstrString
0x180002128  call    cs:__imp_SysFreeString
0x18000212f  nop     dword ptr [rax+rax+00h]
0x180002134  nop
0x180002135  mov     rcx, [rbp+var_28]; bstrString
0x180002139  call    cs:__imp_SysFreeString
0x180002140  nop     dword ptr [rax+rax+00h]
0x180002145  nop
0x180002146  mov     rcx, [rbp+pbstr]; bstrString
0x18000214a  call    cs:__imp_SysFreeString
0x180002151  nop     dword ptr [rax+rax+00h]
0x180002156  nop
0x180002157  test    rbx, rbx
0x18000215a  jz      short loc_18000216C
0x18000215c  mov     rax, [rbx]
0x18000215f  mov     rcx, rbx
0x180002162  mov     rax, [rax+10h]
0x180002166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000216b  nop
0x18000216c  jmp     short loc_1800021E5
0x18000216e  call    cs:__imp_SysStringLen
0x180002175  nop     dword ptr [rax+rax+00h]
0x18000217a  test    eax, eax
0x18000217c  jz      loc_1800020C6
0x180002182  mov     r8, [rbp+pbstr]
0x180002186  mov     edx, 11h
0x18000218b  mov     rcx, rsi
0x18000218e  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002193  mov     edi, eax
0x180002195  test    eax, eax
0x180002197  jns     loc_1800020C6
0x18000219d  mov     rcx, [rbp+var_30]; bstrString
0x1800021a1  call    cs:__imp_SysFreeString
0x1800021a8  nop     dword ptr [rax+rax+00h]
0x1800021ad  nop
0x1800021ae  mov     rcx, [rbp+var_28]; bstrString
0x1800021b2  call    cs:__imp_SysFreeString
0x1800021b9  nop     dword ptr [rax+rax+00h]
0x1800021be  nop
0x1800021bf  mov     rcx, [rbp+pbstr]; bstrString
0x1800021c3  call    cs:__imp_SysFreeString
0x1800021ca  nop     dword ptr [rax+rax+00h]
0x1800021cf  nop
0x1800021d0  test    rbx, rbx
0x1800021d3  jz      short loc_1800021E5
0x1800021d5  mov     rax, [rbx]
0x1800021d8  mov     rcx, rbx
0x1800021db  mov     rax, [rax+10h]
0x1800021df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021e4  nop
0x1800021e5  mov     rcx, r14
0x1800021e8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800021ed  mov     eax, edi
0x1800021ef  mov     rbx, [rsp+50h+arg_0]
0x1800021f7  add     rsp, 50h
0x1800021fb  pop     r15
0x1800021fd  pop     r14
0x1800021ff  pop     r13
0x180002201  pop     r12
0x180002203  pop     rdi
0x180002204  pop     rsi
0x180002205  pop     rbp
0x180002206  retn
0x180002208  mov     rdx, [rax]
0x18000220b  mov     rcx, rbx
0x18000220e  mov     rax, [rdx+8]
0x180002212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002217  jmp     loc_18000201D
0x18000221c  mov     rax, [rbx]
0x18000221f  mov     rcx, rbx
0x180002222  mov     rax, [rax+8]
0x180002226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222b  jmp     loc_18000202A
0x180002230  mov     rcx, [rbp+var_28]; pbstr
0x180002234  test    rcx, rcx
0x180002237  jz      loc_1800020E4
0x18000223d  call    cs:__imp_SysStringLen
0x180002244  nop     dword ptr [rax+rax+00h]
0x180002249  test    eax, eax
0x18000224b  jz      loc_1800020E4
0x180002251  mov     r8, [rbp+var_28]
0x180002255  mov     edx, 12h
0x18000225a  mov     rcx, rsi
0x18000225d  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x180002262  mov     edi, eax
0x180002264  test    eax, eax
0x180002266  jns     loc_1800020E4
0x18000226c  mov     rcx, [rbp+var_30]; bstrString
0x180002270  call    cs:__imp_SysFreeString
0x180002277  nop     dword ptr [rax+rax+00h]
0x18000227c  nop
0x18000227d  mov     rcx, [rbp+var_28]; bstrString
0x180002281  call    cs:__imp_SysFreeString
0x180002288  nop     dword ptr [rax+rax+00h]
0x18000228d  nop
0x18000228e  mov     rcx, [rbp+pbstr]; bstrString
0x180002292  call    cs:__imp_SysFreeString
0x180002299  nop     dword ptr [rax+rax+00h]
0x18000229e  nop
0x18000229f  test    rbx, rbx
0x1800022a2  jz      short loc_1800022B4
0x1800022a4  mov     rax, [rbx]
0x1800022a7  mov     rcx, rbx
0x1800022aa  mov     rax, [rax+10h]
0x1800022ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022b3  nop
0x1800022b4  jmp     loc_1800021E5
0x1800022b9  cmp     [rbp+arg_18], r12w
0x1800022be  setnz   al
0x1800022c1  test    al, al
0x1800022c3  cmovz   r15, r13
0x1800022c7  mov     r8, r15
0x1800022ca  mov     edx, 13h
0x1800022cf  mov     rcx, rsi
0x1800022d2  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800022d7  mov     edi, eax
0x1800022d9  test    eax, eax
0x1800022db  jns     loc_180002124
0x1800022e1  jmp     loc_1800023F3
0x1800022e6  mov     rcx, [rbp+var_10]; pbstr
0x1800022ea  test    rcx, rcx
0x1800022ed  jz      loc_180002075
0x1800022f3  call    cs:__imp_SysStringLen
0x1800022fa  nop     dword ptr [rax+rax+00h]
0x1800022ff  test    eax, eax
0x180002301  jz      loc_180002075
0x180002307  mov     edx, 0Dh
0x18000230c  mov     rcx, rsi
0x18000230f  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x180002314  mov     edi, eax
0x180002316  test    eax, eax
0x180002318  js      loc_180002434
0x18000231e  mov     r8, [rbp+var_10]
0x180002322  mov     edx, 0Eh
0x180002327  mov     rcx, rsi
0x18000232a  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000232f  mov     edi, eax
0x180002331  test    eax, eax
0x180002333  js      short loc_1800023A0
0x180002335  mov     rax, [rbx]
0x180002338  lea     rdx, [rbp+bstrString]
0x18000233c  mov     rcx, rbx
0x18000233f  mov     rax, [rax+48h]
0x180002343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002348  test    eax, eax
0x18000234a  jns     loc_18000246B
0x180002350  mov     [rbp+arg_10], r12w
0x180002355  mov     rax, [rbx]
0x180002358  lea     rdx, [rbp+arg_10]
0x18000235c  mov     rcx, rbx
0x18000235f  mov     rax, [rax+58h]
0x180002363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002368  test    eax, eax
0x18000236a  js      short loc_18000238E
0x18000236c  cmp     [rbp+arg_10], r12w
0x180002371  setnz   al
0x180002374  mov     r8, r15
0x180002377  test    al, al
0x180002379  cmovz   r8, r13
0x18000237d  mov     edx, 10h
0x180002382  mov     rcx, rsi
0x180002385  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000238a  test    eax, eax
0x18000238c  js      short loc_18000239E
0x18000238e  mov     rcx, rsi
0x180002391  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x180002396  test    eax, eax
0x180002398  jns     loc_180002075
0x18000239e  mov     edi, eax
0x1800023a0  mov     rcx, [rbp+bstrString]; bstrString
0x1800023a4  call    cs:__imp_SysFreeString
0x1800023ab  nop     dword ptr [rax+rax+00h]
0x1800023b0  nop
0x1800023b1  mov     rcx, [rbp+var_10]
0x1800023b5  jmp     short loc_180002419
0x1800023b7  mov     rcx, [rbp+var_30]; pbstr
0x1800023bb  test    rcx, rcx
0x1800023be  jz      loc_1800020FF
0x1800023c4  call    cs:__imp_SysStringLen
0x1800023cb  nop     dword ptr [rax+rax+00h]
0x1800023d0  test    eax, eax
0x1800023d2  jz      loc_1800020FF
0x1800023d8  mov     r8, [rbp+var_30]
0x1800023dc  mov     edx, 14h
0x1800023e1  mov     rcx, rsi
0x1800023e4  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x1800023e9  mov     edi, eax
0x1800023eb  test    eax, eax
0x1800023ed  jns     loc_1800020FF
0x1800023f3  mov     rcx, [rbp+var_30]; bstrString
0x1800023f7  call    cs:__imp_SysFreeString
0x1800023fe  nop     dword ptr [rax+rax+00h]
0x180002403  nop
0x180002404  mov     rcx, [rbp+var_28]; bstrString
0x180002408  call    cs:__imp_SysFreeString
0x18000240f  nop     dword ptr [rax+rax+00h]
0x180002414  nop
0x180002415  mov     rcx, [rbp+pbstr]; bstrString
0x180002419  call    cs:__imp_SysFreeString
0x180002420  nop     dword ptr [rax+rax+00h]
0x180002425  nop
0x180002426  lea     rcx, [rbp+var_8]
0x18000242a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000242f  jmp     loc_1800021E5
0x180002434  mov     rcx, [rbp+bstrString]; bstrString
0x180002438  call    cs:__imp_SysFreeString
0x18000243f  nop     dword ptr [rax+rax+00h]
0x180002444  nop
0x180002445  mov     rcx, [rbp+var_10]; bstrString
0x180002449  call    cs:__imp_SysFreeString
0x180002450  nop     dword ptr [rax+rax+00h]
0x180002455  nop
0x180002456  mov     rcx, [rbx]
0x180002459  mov     rax, [rcx+10h]
0x18000245d  mov     rcx, rbx
  ... truncated ...
```
