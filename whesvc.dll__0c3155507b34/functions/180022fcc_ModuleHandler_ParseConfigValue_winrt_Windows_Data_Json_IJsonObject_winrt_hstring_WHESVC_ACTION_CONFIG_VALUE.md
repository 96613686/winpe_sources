# ModuleHandler::ParseConfigValue(winrt::Windows::Data::Json::IJsonObject,winrt::hstring &,_WHESVC_ACTION_CONFIG_VALUE &)

- ea: `0x180022fcc`
- end: `0x180023371`
- name: `?ParseConfigValue@ModuleHandler@@AEAAJUIJsonObject@Json@Data@Windows@winrt@@AEAUhstring@6@AEAU_WHESVC_ACTION_CONFIG_VALUE@@@Z`
- size: `933`
- prototype: `__int64 __fastcall(__int64, _QWORD *, volatile signed __int32 **, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800227bc`

## callees

- `0x180003e10`
- `0x180003e34`
- `0x180006424`
- `0x1800066dc`
- `0x180017b60`
- `0x1800202a8`
- `0x180020310`
- `0x180022fcc`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023001`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023050`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800230b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800231fd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800232fa`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023001`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023050`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800230b7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800231fd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800232fa`

## pseudocode

```c
__int64 __fastcall ModuleHandler::ParseConfigValue(__int64 a1, _QWORD *a2, volatile signed __int32 **a3, __int64 a4)
{
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // r8d
  __int64 v12; // r14
  struct winrt::impl::hstring_header *hstring_on_heap; // rdi
  volatile signed __int32 *v14; // r13
  int v15; // eax
  HANDLE ProcessHeap; // rax
  void *v17; // rdi
  int v18; // esi
  HANDLE v19; // rax
  __int64 result; // rax
  int v21; // eax
  void *v22; // rdi
  int v23; // esi
  HANDLE v24; // rax
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-B8h]
  int v27; // [rsp+20h] [rbp-B8h]
  __int64 v28; // [rsp+20h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-B0h] BYREF
  double v30; // [rsp+30h] [rbp-A8h] BYREF
  int v31; // [rsp+38h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+40h] [rbp-98h]
  int *v33; // [rsp+50h] [rbp-88h]
  int v34; // [rsp+58h] [rbp-80h] BYREF
  int v35; // [rsp+5Ch] [rbp-7Ch]
  const wchar_t *v36; // [rsp+68h] [rbp-70h]
  _DWORD *v37; // [rsp+70h] [rbp-68h] BYREF
  _DWORD v38[4]; // [rsp+78h] [rbp-60h] BYREF
  const wchar_t *v39; // [rsp+88h] [rbp-50h]
  const winrt::hresult_error *v40; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  __int64 v42; // [rsp+E0h] [rbp+8h] BYREF
  _QWORD *v43; // [rsp+E8h] [rbp+10h]
  _QWORD *v44; // [rsp+F0h] [rbp+18h]

  v44 = a3;
  v43 = a2;
  v42 = a1;
  if ( aKey[3] )
    abort();
  try
  {
    v38[0] = 1;
    v38[1] = 3;
    v39 = L"key";
    v37 = v38;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
      a2,
      &lpMem,
      &v37);
    if ( aValuetype[9] )
      abort();
    v34 = 1;
    v35 = 9;
    v36 = L"valueType";
    v33 = &v34;
    v30 = 0.0;
    v7 = *a2;
    v31 = 0;
    v32 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, int *, double *))(*(_QWORD *)v7 + 88LL))(v7, &v34, &v30);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8, &v31);
    if ( aValue[5] )
      abort();
    v34 = 1;
    v35 = 5;
    v36 = L"value";
    v33 = &v34;
    v42 = 0;
    v9 = *a2;
    v31 = 0;
    v32 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v9 + 48LL))(v9, &v34, &v42);
    if ( v10 < 0 )
      winrt::throw_hresult((unsigned int)v10, &v31);
    v12 = v42;
    v28 = v42;
    hstring_on_heap = (struct winrt::impl::hstring_header *)lpMem;
    if ( lpMem )
    {
      if ( (*(_BYTE *)lpMem & 1) != 0 )
      {
        hstring_on_heap = winrt::impl::create_hstring_on_heap(
                            *((winrt::impl **)lpMem + 2),
                            (const unsigned __int16 *)*((unsigned int *)lpMem + 1),
                            v11);
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)lpMem + 6);
        v12 = v42;
      }
    }
    else
    {
      hstring_on_heap = 0;
    }
    v14 = *a3;
    if ( *a3 )
    {
      v15 = _InterlockedDecrement(v14 + 6);
      if ( v15 )
      {
        if ( v15 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v14);
      }
      v12 = v42;
    }
    *v44 = hstring_on_heap;
    switch ( (int)v30 )
    {
      case 4:
      case 5:
        *(_QWORD *)(a4 + 8) = (unsigned int)(int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(&v28);
        *(_DWORD *)a4 = 2;
        break;
      case 9:
        *(double *)(a4 + 8) = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(&v28);
        *(_DWORD *)a4 = 3;
        break;
      case 11:
        LOBYTE(v42) = 0;
        v31 = 0;
        v32 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 80LL))(v12, &v42);
        if ( v21 < 0 )
          winrt::throw_hresult((unsigned int)v21, &v31);
        *(_DWORD *)(a4 + 8) = (_BYTE)v42 != 0;
        *(_DWORD *)a4 = 1;
        break;
      default:
        if ( v12 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
        v17 = lpMem;
        if ( !lpMem )
          goto LABEL_31;
        v18 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( !v18 )
        {
          v19 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v19, 0, v17);
LABEL_30:
          lpMem = 0;
LABEL_31:
          if ( *a2 )
            winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a2);
          return 2147500033LL;
        }
        if ( v18 >= 0 )
          goto LABEL_30;
LABEL_47:
        abort();
    }
    if ( v12 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v28);
    v22 = lpMem;
    if ( lpMem )
    {
      v23 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v23 )
      {
        if ( v23 < 0 )
          goto LABEL_47;
      }
      else
      {
        v24 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v24, 0, v22);
      }
    }
    if ( *a2 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a2);
    result = 0;
  }
  catch ( const winrt::hresult_error *v40 )
  {
    v25 = (const char *)*((unsigned int *)v40 + 3);
    LODWORD(v42) = (_DWORD)v25;
    if ( (int)v25 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37D,
        (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
        v25,
        v27);
    if ( *v43 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v43);
    return (unsigned int)v42;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x382,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)0x80004005LL,
      v26);
    if ( *v43 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v43);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180022fcc  mov     [rsp+arg_10], r8
0x180022fd1  mov     [rsp+arg_8], rdx
0x180022fd6  mov     [rsp+arg_0], rcx
0x180022fdb  push    rbx
0x180022fdc  push    rsi
0x180022fdd  push    rdi
0x180022fde  push    r12
0x180022fe0  push    r13
0x180022fe2  push    r14
0x180022fe4  push    r15
0x180022fe6  sub     rsp, 0A0h
0x180022fed  mov     r12, r9
0x180022ff0  mov     rsi, r8
0x180022ff3  mov     r15, rdx
0x180022ff6  xor     ebx, ebx
0x180022ff8  cmp     word ptr cs:aKey+6, bx; ""
0x180022fff  jz      short loc_180023008
0x180023001  call    cs:__imp_abort
0x180023008  mov     r13d, 1
0x18002300e  mov     [rsp+0D8h+var_60], r13d
0x180023013  mov     [rsp+0D8h+var_5C], 3
0x18002301b  lea     rax, aKey; "key"
0x180023022  mov     [rsp+0D8h+var_50], rax
0x18002302a  lea     rax, [rsp+0D8h+var_60]
0x18002302f  mov     [rsp+0D8h+var_68], rax
0x180023034  lea     r8, [rsp+0D8h+var_68]
0x180023039  lea     rdx, [rsp+0D8h+lpMem]
0x18002303e  mov     rcx, r15
0x180023041  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x180023046  nop
0x180023047  cmp     word ptr cs:aValuetype+12h, bx; ""
0x18002304e  jz      short loc_180023057
0x180023050  call    cs:__imp_abort
0x180023057  mov     [rsp+0D8h+var_80], r13d
0x18002305c  mov     [rsp+0D8h+var_7C], 9
0x180023064  lea     rax, aValuetype; "valueType"
0x18002306b  mov     [rsp+0D8h+var_70], rax
0x180023070  lea     rax, [rsp+0D8h+var_80]
0x180023075  mov     [rsp+0D8h+var_88], rax
0x18002307a  xorps   xmm0, xmm0
0x18002307d  movsd   [rsp+0D8h+var_A8], xmm0
0x180023083  mov     rcx, [r15]
0x180023086  mov     [rsp+0D8h+var_A0], ebx
0x18002308a  movdqu  [rsp+0D8h+var_98], xmm0
0x180023090  mov     rax, [rcx]
0x180023093  lea     r8, [rsp+0D8h+var_A8]
0x180023098  lea     rdx, [rsp+0D8h+var_80]
0x18002309d  mov     rax, [rax+58h]
0x1800230a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230a6  test    eax, eax
0x1800230a8  js      loc_18002334A
0x1800230ae  cmp     word ptr cs:aValue+0Ah, bx; ""
0x1800230b5  jz      short loc_1800230BE
0x1800230b7  call    cs:__imp_abort
0x1800230be  mov     [rsp+0D8h+var_80], r13d
0x1800230c3  mov     [rsp+0D8h+var_7C], 5
0x1800230cb  lea     rax, aValue; "value"
0x1800230d2  mov     [rsp+0D8h+var_70], rax
0x1800230d7  lea     rax, [rsp+0D8h+var_80]
0x1800230dc  mov     [rsp+0D8h+var_88], rax
0x1800230e1  mov     [rsp+0D8h+arg_0], rbx
0x1800230e9  mov     rcx, [r15]
0x1800230ec  mov     [rsp+0D8h+var_A0], ebx
0x1800230f0  xorps   xmm0, xmm0
0x1800230f3  movdqu  [rsp+0D8h+var_98], xmm0
0x1800230f9  mov     rax, [rcx]
0x1800230fc  lea     r8, [rsp+0D8h+arg_0]
0x180023104  lea     rdx, [rsp+0D8h+var_80]
0x180023109  mov     rax, [rax+30h]
0x18002310d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023112  test    eax, eax
0x180023114  js      loc_180023356
0x18002311a  mov     r14, [rsp+0D8h+arg_0]
0x180023122  mov     [rsp+0D8h+var_B8], r14
0x180023127  mov     rdi, [rsp+0D8h+lpMem]
0x18002312c  test    rdi, rdi
0x18002312f  jnz     short loc_180023136
0x180023131  mov     rdi, rbx
0x180023134  jmp     short loc_180023158
0x180023136  test    [rdi], r13b
0x180023139  jnz     short loc_180023149
0x18002313b  lock inc dword ptr [rdi+18h]
0x18002313f  mov     r14, [rsp+0D8h+arg_0]
0x180023147  jmp     short loc_180023158
0x180023149  mov     edx, [rdi+4]; unsigned __int16 *
0x18002314c  mov     rcx, [rdi+10h]; this
0x180023150  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x180023155  mov     rdi, rax
0x180023158  mov     r13, [rsi]
0x18002315b  or      esi, 0FFFFFFFFh
0x18002315e  test    r13, r13
0x180023161  jz      short loc_18002318F
0x180023163  mov     eax, esi
0x180023165  lock xadd [r13+18h], eax
0x18002316b  sub     eax, 1
0x18002316e  jnz     loc_1800231F9
0x180023174  nop
0x180023175  call    WINRT_IMPL_GetProcessHeap
0x18002317a  mov     rcx, rax; hHeap
0x18002317d  mov     r8, r13; lpMem
0x180023180  xor     edx, edx; dwFlags
0x180023182  call    WINRT_IMPL_HeapFree
0x180023187  mov     r14, [rsp+0D8h+arg_0]
0x18002318f  mov     rax, [rsp+0D8h+arg_10]
0x180023197  mov     [rax], rdi
0x18002319a  cvttsd2si ecx, [rsp+0D8h+var_A8]
0x1800231a0  sub     ecx, 4
0x1800231a3  jz      loc_180023291
0x1800231a9  sub     ecx, 1
0x1800231ac  jz      loc_180023291
0x1800231b2  sub     ecx, 4
0x1800231b5  jz      loc_180023276
0x1800231bb  cmp     ecx, 2
0x1800231be  jz      short loc_180023228
0x1800231c0  test    r14, r14
0x1800231c3  jz      short loc_1800231D0
0x1800231c5  lea     rcx, [rsp+0D8h+var_B8]
0x1800231ca  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800231cf  nop
0x1800231d0  mov     rdi, [rsp+0D8h+lpMem]
0x1800231d5  test    rdi, rdi
0x1800231d8  jz      short loc_180023211
0x1800231da  lock xadd [rdi+18h], esi
0x1800231df  sub     esi, 1
0x1800231e2  jnz     short loc_180023204
0x1800231e4  nop
0x1800231e5  call    WINRT_IMPL_GetProcessHeap
0x1800231ea  mov     rcx, rax; hHeap
0x1800231ed  mov     r8, rdi; lpMem
0x1800231f0  xor     edx, edx; dwFlags
0x1800231f2  call    WINRT_IMPL_HeapFree
0x1800231f7  jmp     short loc_18002320C
0x1800231f9  test    eax, eax
0x1800231fb  jns     short loc_180023187
0x1800231fd  call    cs:__imp_abort
0x180023204  test    esi, esi
0x180023206  js      loc_1800232FA
0x18002320c  mov     [rsp+0D8h+lpMem], rbx
0x180023211  cmp     [r15], rbx
0x180023214  jz      short loc_18002321E
0x180023216  mov     rcx, r15
0x180023219  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18002321e  mov     eax, 80004001h
0x180023223  jmp     loc_180023337
0x180023228  mov     byte ptr [rsp+0D8h+arg_0], bl
0x18002322f  mov     [rsp+0D8h+var_A0], ebx
0x180023233  xorps   xmm0, xmm0
0x180023236  movdqu  [rsp+0D8h+var_98], xmm0
0x18002323c  mov     rax, [r14]
0x18002323f  lea     rdx, [rsp+0D8h+arg_0]
0x180023247  mov     rcx, r14
0x18002324a  mov     rax, [rax+50h]
0x18002324e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023253  test    eax, eax
0x180023255  js      loc_180023363
0x18002325b  mov     eax, ebx
0x18002325d  cmp     byte ptr [rsp+0D8h+arg_0], bl
0x180023264  setnz   al
0x180023267  mov     [r12+8], eax
0x18002326c  mov     dword ptr [r12], 1
0x180023274  jmp     short loc_1800232AD
0x180023276  lea     rcx, [rsp+0D8h+var_B8]
0x18002327b  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180023280  movsd   qword ptr [r12+8], xmm0
0x180023287  mov     dword ptr [r12], 3
0x18002328f  jmp     short loc_1800232AD
0x180023291  lea     rcx, [rsp+0D8h+var_B8]
0x180023296  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x18002329b  cvttsd2si rax, xmm0
0x1800232a0  mov     [r12+8], rax
0x1800232a5  mov     dword ptr [r12], 2
0x1800232ad  test    r14, r14
0x1800232b0  jz      short loc_1800232BD
0x1800232b2  lea     rcx, [rsp+0D8h+var_B8]
0x1800232b7  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800232bc  nop
0x1800232bd  mov     rdi, [rsp+0D8h+lpMem]
0x1800232c2  test    rdi, rdi
0x1800232c5  jz      short loc_1800232E5
0x1800232c7  lock xadd [rdi+18h], esi
0x1800232cc  sub     esi, 1
0x1800232cf  jnz     short loc_1800232F6
0x1800232d1  nop
0x1800232d2  call    WINRT_IMPL_GetProcessHeap
0x1800232d7  mov     rcx, rax; hHeap
0x1800232da  mov     r8, rdi; lpMem
0x1800232dd  xor     edx, edx; dwFlags
0x1800232df  call    WINRT_IMPL_HeapFree
0x1800232e4  nop
0x1800232e5  cmp     [r15], rbx
0x1800232e8  jz      short loc_1800232F2
0x1800232ea  mov     rcx, r15
0x1800232ed  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800232f2  xor     eax, eax
0x1800232f4  jmp     short loc_180023337
0x1800232f6  test    esi, esi
0x1800232f8  jns     short loc_1800232E5
0x1800232fa  call    cs:__imp_abort
0x180023301  xor     ebx, ebx
0x180023303  mov     rcx, [rsp+0D8h+arg_8]
0x18002330b  cmp     [rcx], rbx
0x18002330e  jz      short loc_180023315
0x180023310  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023315  mov     eax, dword ptr [rsp+0D8h+arg_0]
0x18002331c  jmp     short loc_180023337
0x18002331e  xor     ebx, ebx
0x180023320  mov     rcx, [rsp+0D8h+arg_8]
0x180023328  cmp     [rcx], rbx
0x18002332b  jz      short loc_180023332
0x18002332d  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023332  mov     eax, 80004005h
0x180023337  add     rsp, 0A0h
0x18002333e  pop     r15
0x180023340  pop     r14
0x180023342  pop     r13
0x180023344  pop     r12
0x180023346  pop     rdi
0x180023347  pop     rsi
0x180023348  pop     rbx
0x180023349  retn
0x18002334a  lea     rdx, [rsp+0D8h+var_A0]
0x18002334f  mov     ecx, eax
0x180023351  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023356  lea     rdx, [rsp+0D8h+var_A0]
0x18002335b  mov     ecx, eax
0x18002335d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023363  lea     rdx, [rsp+0D8h+var_A0]
0x180023368  mov     ecx, eax
0x18002336a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
