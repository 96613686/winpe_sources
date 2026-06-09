# TASK_LIST::AddRefFast(WinMetaData const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,TASK_LIST::TASK_ENTRY_MAP &,ETW_PROVIDER_ENTRY *,TASK_ENTRY * &)

- ea: `0x1800342ec`
- end: `0x180034471`
- name: `?AddRefFast@TASK_LIST@@QEBAXAEBVWinMetaData@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUTASK_ENTRY_MAP@1@PEAVETW_PROVIDER_ENTRY@@AEAPEAVTASK_ENTRY@@@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18001ac70`

## callees

- `0x18001e284`
- `0x18002c570`
- `0x18002e8f4`
- `0x18002f104`
- `0x18002f574`
- `0x180030660`
- `0x1800314d0`
- `0x180032cac`
- `0x180033df0`
- `0x1800342ec`
- `0x18003ab5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall TASK_LIST::AddRefFast(STRING_LIST **a1, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5, _QWORD *a6)
{
  __int64 v10; // r9
  __int64 v11; // rbx
  __int64 v12; // rcx
  _QWORD *result; // rax
  __int128 *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rsi
  __int64 v17; // r14
  _QWORD *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int128 v21; // [rsp+40h] [rbp-39h] BYREF
  __int128 v22; // [rsp+50h] [rbp-29h] BYREF
  __int128 v23; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v24[16]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h]
  __int64 v26; // [rsp+E8h] [rbp+6Fh] BYREF

  std::wstring::operator std::wstring_view(a3, &v21);
  std::_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>::_Find_lower_bound<std::wstring_view>(
    v10,
    v24,
    &v21);
  v11 = v25;
  if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring_view,TASK_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TASK_ENTRY *>>,0>>::_Lower_bound_duplicate<std::wstring_view>(
                           v12,
                           v25,
                           &v21)
    || v11 == *a4 )
  {
    v14 = (__int128 *)std::wstring::operator std::wstring_view(a3, v24);
    v21 = 0;
    v22 = *v14;
    v23 = *(_OWORD *)(a2 + 48);
    v15 = WinMetaData::GenericFindOrThrow<WinMetaTask>(&v23, &v22, &v21);
    std::make_unique<TASK_ENTRY,,0>(&v26);
    v16 = v26;
    std::wstring::_Assign<wchar_t>(v26, *(_QWORD *)v15, *(_QWORD *)(v15 + 8));
    std::wstring::_Assign<wchar_t>(v16 + 40, *(_QWORD *)(v15 + 16), *(_QWORD *)(v15 + 24));
    *(_WORD *)(v16 + 32) = *(_WORD *)(v15 + 40);
    v17 = a5;
    STRING_LIST::ReferenceStringFromWinmeta(
      *a1,
      *(struct WinMetaString **)(v15 + 32),
      (__int64)L"task",
      a5,
      v16 + 128,
      v16 + 72);
    v18 = *(_QWORD **)(v17 + 328);
    if ( v18 == *(_QWORD **)(v17 + 336) )
    {
      std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(
        v17 + 320,
        v18,
        &v26);
    }
    else
    {
      v26 = 0;
      *v18 = v16;
      *(_QWORD *)(v17 + 328) += 8LL;
    }
    v19 = *(_QWORD *)(*(_QWORD *)(v17 + 328) - 8LL);
    *a6 = v19;
    v20 = std::wstring::operator std::wstring_view(v19, v24);
    std::map<std::wstring_view,TASK_ENTRY *>::_Try_emplace<std::wstring_view,TASK_ENTRY * &>(a4, &v23, v20);
    return (_QWORD *)std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(&v26);
  }
  else
  {
    result = a6;
    *a6 = *(_QWORD *)(v11 + 48);
  }
  return result;
}

```

## disassembly

```asm
0x1800342ec  push    rbp
0x1800342ee  push    rbx
0x1800342ef  push    rsi
0x1800342f0  push    rdi
0x1800342f1  push    r14
0x1800342f3  push    r15
0x1800342f5  lea     rbp, [rsp-1Fh]
0x1800342fa  sub     rsp, 98h
0x180034301  mov     rdi, r9
0x180034304  mov     rsi, r8
0x180034307  mov     r14, rdx
0x18003430a  mov     r15, rcx
0x18003430d  lea     rdx, [rbp+47h+var_80]
0x180034311  mov     rcx, r8
0x180034314  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180034319  lea     r8, [rbp+47h+var_80]
0x18003431d  lea     rdx, [rbp+47h+var_50]
0x180034321  mov     rcx, r9
0x180034324  call    ??$_Find_lower_bound@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@PEAX@std@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>::_Find_lower_bound<std::wstring_view>(std::wstring_view const &)
0x180034329  lea     r8, [rbp+47h+var_80]
0x18003432d  mov     rbx, [rbp+47h+var_40]
0x180034331  mov     rdx, rbx
0x180034334  call    ??$_Lower_bound_duplicate@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@PEAX@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring_view,TASK_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TASK_ENTRY *>>,0>>::_Lower_bound_duplicate<std::wstring_view>(std::_Tree_node<std::pair<std::wstring_view const,TASK_ENTRY *>,void *> * const,std::wstring_view const &)
0x180034339  test    al, al
0x18003433b  jz      short loc_180034352
0x18003433d  cmp     rbx, [rdi]
0x180034340  jz      short loc_180034352
0x180034342  mov     rcx, [rbx+30h]
0x180034346  mov     rax, [rbp+47h+arg_28]
0x18003434a  mov     [rax], rcx
0x18003434d  jmp     loc_180034461
0x180034352  lea     rdx, [rbp+47h+var_50]
0x180034356  mov     rcx, rsi
0x180034359  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18003435e  xorps   xmm0, xmm0
0x180034361  movdqa  [rbp+47h+var_80], xmm0
0x180034366  movups  xmm1, xmmword ptr [rax]
0x180034369  movdqu  [rbp+47h+var_70], xmm1
0x18003436e  movups  xmm0, xmmword ptr [r14+30h]
0x180034373  movdqu  [rbp+47h+var_60], xmm0
0x180034378  lea     r8, [rbp+47h+var_80]
0x18003437c  lea     rdx, [rbp+47h+var_70]
0x180034380  lea     rcx, [rbp+47h+var_60]
0x180034384  call    ??$GenericFindOrThrow@UWinMetaTask@@@WinMetaData@@SAAEBUWinMetaTask@@V?$span@$$CBUWinMetaTask@@$0?0@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@1@Z; WinMetaData::GenericFindOrThrow<WinMetaTask>(std::span<WinMetaTask const,-1>,std::wstring_view,std::wstring_view)
0x180034389  mov     rbx, rax
0x18003438c  lea     rcx, [rbp+47h+arg_18]
0x180034390  call    ??$make_unique@VTASK_ENTRY@@$$V$0A@@std@@YA?AV?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@0@XZ; std::make_unique<TASK_ENTRY,,0>(void)
0x180034395  nop
0x180034396  mov     r8, [rbx+8]
0x18003439a  mov     rdx, [rbx]
0x18003439d  mov     rsi, [rbp+47h+arg_18]
0x1800343a1  mov     rcx, rsi
0x1800343a4  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800343a9  lea     rcx, [rsi+28h]
0x1800343ad  mov     r8, [rbx+18h]
0x1800343b1  mov     rdx, [rbx+10h]
0x1800343b5  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800343ba  movzx   edx, word ptr [rbx+28h]
0x1800343be  mov     [rsi+20h], dx
0x1800343c2  lea     rax, [rsi+48h]
0x1800343c6  lea     rcx, [rsi+80h]
0x1800343cd  mov     r9d, edx
0x1800343d0  mov     [rsp+0C0h+var_88], rax; __int64
0x1800343d5  mov     [rsp+0C0h+var_90], rcx; __int64
0x1800343da  mov     r14, [rbp+47h+arg_20]
0x1800343de  mov     [rsp+0C0h+var_98], r14; __int64
0x1800343e3  lea     rax, aTask; "task"
0x1800343ea  mov     [rsp+0C0h+var_A0], rax; __int64
0x1800343ef  mov     r8d, 3
0x1800343f5  mov     rdx, [rbx+20h]; struct WinMetaString *
0x1800343f9  mov     rcx, [r15]; this
0x1800343fc  call    ?ReferenceStringFromWinmeta@STRING_LIST@@QEAAXPEBUWinMetaString@@W4TableType@@_KPEB_WAEAVETW_PROVIDER_ENTRY@@PEAPEAVSTRING_ENTRY@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; STRING_LIST::ReferenceStringFromWinmeta(WinMetaString const *,TableType,unsigned __int64,wchar_t const *,ETW_PROVIDER_ENTRY &,STRING_ENTRY * *,std::wstring *)
0x180034401  lea     rcx, [r14+140h]
0x180034408  mov     rdx, [rcx+8]
0x18003440c  cmp     rdx, [rcx+10h]
0x180034410  jz      short loc_180034424
0x180034412  mov     [rbp+47h+arg_18], 0
0x18003441a  mov     [rdx], rsi
0x18003441d  add     qword ptr [rcx+8], 8
0x180034422  jmp     short loc_18003442D
0x180034424  lea     r8, [rbp+47h+arg_18]
0x180034428  call    ??$_Emplace_reallocate@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(std::unique_ptr<OPCODE_ENTRY> * const,std::unique_ptr<OPCODE_ENTRY> &&)
0x18003442d  mov     rax, [r14+148h]
0x180034434  mov     rcx, [rax-8]
0x180034438  mov     r9, [rbp+47h+arg_28]
0x18003443c  mov     [r9], rcx
0x18003443f  lea     rdx, [rbp+47h+var_50]
0x180034443  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180034448  mov     r8, rax
0x18003444b  lea     rdx, [rbp+47h+var_60]
0x18003444f  mov     rcx, rdi
0x180034452  call    ??$_Try_emplace@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAPEAVTASK_ENTRY@@@?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEAPEAVTASK_ENTRY@@@Z; std::map<std::wstring_view,TASK_ENTRY *>::_Try_emplace<std::wstring_view,TASK_ENTRY * &>(std::wstring_view &&,TASK_ENTRY * &)
0x180034457  nop
0x180034458  lea     rcx, [rbp+47h+arg_18]
0x18003445c  call    ??1?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(void)
0x180034461  add     rsp, 98h
0x180034468  pop     r15
0x18003446a  pop     r14
0x18003446c  pop     rdi
0x18003446d  pop     rsi
0x18003446e  pop     rbx
0x18003446f  pop     rbp
0x180034470  retn
```
